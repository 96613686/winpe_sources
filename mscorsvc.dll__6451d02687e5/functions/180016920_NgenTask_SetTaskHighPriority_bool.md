# NgenTask::SetTaskHighPriority(bool)

- ea: `0x180016920`
- end: `0x180016a99`
- name: `?SetTaskHighPriority@NgenTask@@YAX_N@Z`
- size: `377`
- prototype: `void __fastcall(NgenTask *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016fd4`
- `0x1800171a8`

## callees

- `0x180001e8c`
- `0x1800068a8`
- `0x180016920`
- `0x180030d84`
- `0x1800373e0`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016a34`
- `ADVAPI32!RegCloseKey` at `0x180016a34`
- `KERNEL32!HeapFree` at `0x180016a6f`
- `KERNEL32!HeapFree` at `0x180016a6f`
- `KERNEL32!GetProcessHeap` at `0x180016a5a`
- `KERNEL32!GetProcessHeap` at `0x180016a5a`

## string_xrefs

- `0x180016984`: `\NgenService`
- `0x180016a1c`: `TaskHighPriorityMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall NgenTask::SetTaskHighPriority(NgenTask *this)
{
  __int64 v1; // r8
  unsigned __int16 *v2; // r9
  bool v3; // cl
  unsigned __int16 *v4; // r8
  int v5; // eax
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v8; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  int v10; // [rsp+60h] [rbp-A0h]
  HKEY *p_hKey; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+70h] [rbp-90h] BYREF
  __int64 v13; // [rsp+74h] [rbp-8Ch]
  LPVOID lpMem; // [rsp+80h] [rbp-80h]
  __int16 v15; // [rsp+88h] [rbp-78h] BYREF

  v13 = 512;
  lpMem = &v15;
  v12 = 2;
  v15 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v12);
  SString::Append((SString *)&v12, L"\\NgenService");
  SString::Append((SString *)&v12, L"\\State");
  v10 = 0;
  p_hKey = &hKey;
  hKey = 0;
  SString::ConvertToUnicode((SString *)&v12);
  v3 = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v1, v2, 0, 0x2001Bu, v8, &hKey) != 0;
  v5 = v10;
  if ( hKey )
    v5 = 1;
  v10 = v5;
  if ( !v3 )
    REGUTIL::SetOrCreateLong(L"TaskHighPriorityMode", 1, v4, hKey);
  if ( v10 )
  {
    RegCloseKey(hKey);
    v10 = 0;
  }
  if ( (v13 & 0x800000000LL) != 0 )
  {
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v6);
    }
  }
}

```

## disassembly

```asm
0x180016920  mov     [rsp-8+arg_0], rbx
0x180016925  mov     [rsp-8+arg_8], rdi
0x18001692a  push    rbp
0x18001692b  lea     rbp, [rsp-1A0h]
0x180016933  sub     rsp, 2A0h
0x18001693a  mov     rax, cs:__security_cookie
0x180016941  xor     rax, rsp
0x180016944  mov     [rbp+1A0h+var_10], rax
0x18001694b  xor     edi, edi
0x18001694d  mov     [rsp+2A0h+var_250], edi
0x180016951  mov     [rsp+2A0h+var_230], rdi
0x180016956  mov     [rsp+2A0h+var_230+4], 200h
0x18001695f  mov     [rbp+1A0h+lpMem], rdi
0x180016963  lea     rax, [rbp+1A0h+var_218]
0x180016967  mov     [rbp+1A0h+lpMem], rax
0x18001696b  mov     dword ptr [rsp+2A0h+var_230], 2
0x180016973  mov     rax, [rbp+1A0h+lpMem]
0x180016977  mov     [rax], di
0x18001697a  lea     rcx, [rsp+2A0h+var_230]; this
0x18001697f  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x180016984  lea     rdx, aNgenservice_0; "\\NgenService"
0x18001698b  lea     rcx, [rsp+2A0h+var_230]; this
0x180016990  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016995  lea     rdx, aState; "\\State"
0x18001699c  lea     rcx, [rsp+2A0h+var_230]; this
0x1800169a1  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1800169a6  mov     [rsp+2A0h+hKey], rdi
0x1800169ab  mov     [rsp+2A0h+var_240], edi
0x1800169af  lea     rax, [rsp+2A0h+hKey]
0x1800169b4  mov     [rsp+2A0h+var_238], rax
0x1800169b9  mov     [rsp+2A0h+hKey], rdi
0x1800169be  lea     ebx, [rdi+1]
0x1800169c1  mov     [rsp+2A0h+var_250], ebx
0x1800169c5  lea     rcx, [rsp+2A0h+var_230]; this
0x1800169ca  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800169cf  lea     rax, [rsp+2A0h+hKey]
0x1800169d4  mov     [rsp+2A0h+var_268], rax; HKEY *
0x1800169d9  mov     [rsp+2A0h+var_278], 2001Bh; REGSAM
0x1800169e1  mov     [rsp+2A0h+var_280], edi; DWORD
0x1800169e5  mov     rdx, [rbp+1A0h+lpMem]; unsigned __int16 *
0x1800169e9  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800169f0  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1800169f5  test    eax, eax
0x1800169f7  setnz   cl
0x1800169fa  mov     eax, ebx
0x1800169fc  and     eax, 0FFFFFFFEh
0x1800169ff  mov     [rsp+2A0h+var_250], eax
0x180016a03  mov     eax, [rsp+2A0h+var_240]
0x180016a07  mov     r9, [rsp+2A0h+hKey]; HKEY
0x180016a0c  test    r9, r9
0x180016a0f  cmovnz  eax, ebx
0x180016a12  mov     [rsp+2A0h+var_240], eax
0x180016a16  test    cl, cl
0x180016a18  jnz     short loc_180016A29
0x180016a1a  mov     edx, ebx; int
0x180016a1c  lea     rcx, aTaskhighpriori; "TaskHighPriorityMode"
0x180016a23  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x180016a28  nop
0x180016a29  cmp     [rsp+2A0h+var_240], edi
0x180016a2d  jz      short loc_180016A3E
0x180016a2f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180016a34  call    cs:__imp_RegCloseKey
0x180016a3a  mov     [rsp+2A0h+var_240], edi
0x180016a3e  test    [rsp+2A0h+var_228], 8
0x180016a43  jz      short loc_180016A75
0x180016a45  mov     rbx, [rbp+1A0h+lpMem]
0x180016a49  test    rbx, rbx
0x180016a4c  jz      short loc_180016A75
0x180016a4e  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016a55  test    rax, rax
0x180016a58  jnz     short loc_180016A67
0x180016a5a  call    cs:__imp_GetProcessHeap
0x180016a60  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016a67  mov     r8, rbx; lpMem
0x180016a6a  xor     edx, edx; dwFlags
0x180016a6c  mov     rcx, rax; hHeap
0x180016a6f  call    cs:__imp_HeapFree
0x180016a75  mov     rcx, [rbp+1A0h+var_10]
0x180016a7c  xor     rcx, rsp; StackCookie
0x180016a7f  call    __security_check_cookie
0x180016a84  lea     r11, [rsp+2A0h+var_s0]
0x180016a8c  mov     rbx, [r11+10h]
0x180016a90  mov     rdi, [r11+18h]
0x180016a94  mov     rsp, r11
0x180016a97  pop     rbp
0x180016a98  retn
```
