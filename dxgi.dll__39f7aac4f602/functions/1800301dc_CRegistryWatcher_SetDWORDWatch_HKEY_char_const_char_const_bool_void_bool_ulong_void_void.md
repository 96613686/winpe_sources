# CRegistryWatcher::SetDWORDWatch(HKEY__ *,char const *,char const *,bool,void (*)(bool,ulong,void *),void *)

- ea: `0x1800301dc`
- end: `0x18003029f`
- name: `?SetDWORDWatch@CRegistryWatcher@@QEAAJPEAUHKEY__@@PEBD1_NP6AX2KPEAX@Z3@Z`
- size: `195`
- prototype: `__int64 __usercall@<rax>(CRegistryWatcher *__hidden this@<rcx>, HKEY@<rdx>, const char *@<r8>, const char *@<r9>, bool, void (*)(bool, unsigned int, void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f008`

## callees

- `0x1800301dc`
- `0x1800302a8`
- `0x180035040`
- `0x1800a73c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003023f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003023f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003025b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003025b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003020f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003020f`

## pseudocode

```c
__int64 __fastcall CRegistryWatcher::SetDWORDWatch(
        CRegistryWatcher *this,
        HKEY a2,
        const char *a3,
        const char *a4,
        bool a5,
        void (*a6)(bool, unsigned int, void *),
        void *a7)
{
  unsigned int v7; // ebx
  HANDLE EventA; // rax
  PTP_WAIT ThreadpoolWait; // rax

  v7 = 0;
  if ( *((_QWORD *)this + 4)
    || RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppOnHMD",
         0,
         0x11u,
         (PHKEY)this + 3)
    || (EventA = CreateEventA(0, 1, 0, 0), (*((_QWORD *)this + 4) = EventA) == 0)
    || (ThreadpoolWait = CreateThreadpoolWait(WaitCallback, this, 0), (*(_QWORD *)this = ThreadpoolWait) == 0) )
  {
    v7 = -2147467259;
    CRegistryWatcher::Cleanup(this);
  }
  else
  {
    *((_QWORD *)this + 1) = CDXGIFactory::RegistryAppOnHMDChangedCallback;
    *((_QWORD *)this + 2) = a7;
    StringCchCopyA((char *)this + 40, 0x104u, "AppOnHMD");
    WaitWorker(this, *(struct _TP_WAIT **)this);
  }
  return v7;
}

```

## disassembly

```asm
0x1800301dc  mov     [rsp+arg_0], rbx
0x1800301e1  push    rdi
0x1800301e2  sub     rsp, 30h
0x1800301e6  xor     ebx, ebx
0x1800301e8  mov     rdi, rcx
0x1800301eb  cmp     [rcx+20h], rbx
0x1800301ef  jnz     short loc_180030219
0x1800301f1  lea     rax, [rcx+18h]
0x1800301f5  xor     r8d, r8d; ulOptions
0x1800301f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800301ff  mov     [rsp+38h+phkResult], rax; phkResult
0x180030204  lea     r9d, [rbx+11h]; samDesired
0x180030208  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003020f  call    cs:__imp_RegOpenKeyExA
0x180030215  test    eax, eax
0x180030217  jz      short loc_180030233
0x180030219  mov     rcx, rdi; this
0x18003021c  mov     ebx, 80004005h
0x180030221  call    ?Cleanup@CRegistryWatcher@@AEAAXXZ; CRegistryWatcher::Cleanup(void)
0x180030226  mov     eax, ebx
0x180030228  mov     rbx, [rsp+38h+arg_0]
0x18003022d  add     rsp, 30h
0x180030231  pop     rdi
0x180030232  retn
0x180030233  xor     r9d, r9d; lpName
0x180030236  xor     r8d, r8d; bInitialState
0x180030239  xor     ecx, ecx; lpEventAttributes
0x18003023b  lea     edx, [r9+1]; bManualReset
0x18003023f  call    cs:__imp_CreateEventA
0x180030245  mov     [rdi+20h], rax
0x180030249  test    rax, rax
0x18003024c  jz      short loc_180030219
0x18003024e  xor     r8d, r8d; pcbe
0x180030251  lea     rcx, ?WaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180030258  mov     rdx, rdi; pv
0x18003025b  call    cs:__imp_CreateThreadpoolWait
0x180030261  mov     [rdi], rax
0x180030264  test    rax, rax
0x180030267  jz      short loc_180030219
0x180030269  lea     rax, ?RegistryAppOnHMDChangedCallback@CDXGIFactory@@SAX_NKPEAX@Z; CDXGIFactory::RegistryAppOnHMDChangedCallback(bool,ulong,void *)
0x180030270  mov     edx, 104h; unsigned __int64
0x180030275  mov     [rdi+8], rax
0x180030279  lea     rcx, [rdi+28h]; char *
0x18003027d  mov     rax, [rsp+38h+arg_30]
0x180030282  lea     r8, aApponhmd; "AppOnHMD"
0x180030289  mov     [rdi+10h], rax
0x18003028d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180030292  mov     rdx, [rdi]; struct _TP_WAIT *
0x180030295  mov     rcx, rdi; struct CRegistryWatcher *
0x180030298  call    ?WaitWorker@@YAXPEAVCRegistryWatcher@@PEAU_TP_WAIT@@@Z; WaitWorker(CRegistryWatcher *,_TP_WAIT *)
0x18003029d  jmp     short loc_180030226
```
