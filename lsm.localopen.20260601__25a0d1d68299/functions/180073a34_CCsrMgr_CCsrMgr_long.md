# CCsrMgr::CCsrMgr(long *)

- ea: `0x180073a34`
- end: `0x180073c8f`
- name: `??0CCsrMgr@@QEAA@PEAJ@Z`
- size: `603`
- prototype: `CCsrMgr *__fastcall(CCsrMgr *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c2c4`

## callees

- `0x1800077a0`
- `0x180016740`
- `0x18002701c`
- `0x18007399c`
- `0x180073a34`
- `0x180073f4c`

## import_xrefs

- `ntdll!RtlConnectToSm` at `0x180073b10`
- `ntdll!RtlConnectToSm` at `0x180073b10`
- `ntdll!TpAllocAlpcCompletion` at `0x180073ba4`
- `ntdll!TpAllocAlpcCompletion` at `0x180073ba4`
- `ntdll!NtAlpcQueryInformation` at `0x180073b69`
- `ntdll!NtAlpcQueryInformation` at `0x180073b69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073bdc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073c63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073c3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073c3f`

## string_xrefs

- `0x180073b41`: `CreateLpcPort failed: 0x%x in %s`
- `0x180073bf7`: `RegOpenKeyEx on session manager control failed. Cannot determine initial command override.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
CCsrMgr *__fastcall CCsrMgr::CCsrMgr(CCsrMgr *this, unsigned int *a2)
{
  int LpcPort; // eax
  unsigned int v5; // ebx
  const char *v6; // rdx
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  const char *v14; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+50h] BYREF

  v14 = (const char *)this;
  CTSPrivateObject<ICsrMgr>::CTSPrivateObject<ICsrMgr>();
  *(_QWORD *)this = &CCsrMgr::`vftable';
  *((_DWORD *)this + 422) = 0;
  *((_QWORD *)this + 212) = &DynArray<SmartArray<CCsrPipe,long>::CCleanType,long>::`vftable';
  *((_QWORD *)this + 213) = 0;
  *((_QWORD *)this + 214) = 0;
  *((_DWORD *)this + 454) = 0;
  *((_QWORD *)this + 228) = 0;
  *((_QWORD *)this + 229) = 0;
  *((_DWORD *)this + 460) = 0;
  *((_QWORD *)this + 231) = 0;
  v13 = 0;
  LpcPort = CResource::Initialize((CCsrMgr *)((char *)this + 1592));
  v5 = LpcPort;
  if ( LpcPort < 0 )
  {
    v6 = "Lock.Initialize failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v6, (unsigned int)LpcPort, "CCsrMgr::CCsrMgr");
    goto LABEL_21;
  }
  LpcPort = CResource::Initialize((CCsrMgr *)((char *)this + 1720));
  v5 = LpcPort;
  if ( LpcPort < 0 )
  {
    v6 = "CsrPipesLock.Initialize failed: 0x%x in %s";
    goto LABEL_3;
  }
  v7 = RtlConnectToSm(0, 0, 0, (char *)this + 1832);
  v5 = v7 | 0x10000000;
  if ( v7 >= 0 )
  {
    LpcPort = CCsrMgr::CreateLpcPort(this);
    v5 = LpcPort;
    if ( LpcPort < 0 )
    {
      v6 = "CreateLpcPort failed: 0x%x in %s";
      goto LABEL_3;
    }
    *((_DWORD *)this + 464) = 0;
    v8 = NtAlpcQueryInformation(*((_QWORD *)this + 228), 0, &v13, 16, 0);
    if ( v8 < 0
      || (*((_DWORD *)this + 464) = DWORD1(v13),
          v8 = TpAllocAlpcCompletion((char *)this + 1848, *((_QWORD *)this + 228), CCsrMgr::staticLpcWorker, this, 0),
          v8 < 0) )
    {
      v5 = v8 | 0x10000000;
    }
    else
    {
      hkey = 0;
      pcbData = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Session Manager", 0, 0x20019u, &hkey) )
      {
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          v14 = "RegOpenKeyEx on session manager control failed. Cannot determine initial command override.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v9,
            (unsigned int)byte_1800CB2A9,
            v10,
            v11,
            (__int64)&v14);
        }
      }
      else
      {
        if ( !RegGetValueW(hkey, 0, L"Execute", 0x20u, 0, 0, &pcbData) && pcbData > 6 )
          *((_DWORD *)this + 465) = 1;
        RegCloseKey(hkey);
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "SmConnectToSm failed: 0x%x in %s", v5, "CCsrMgr::CCsrMgr");
  }
LABEL_21:
  *a2 = v5;
  return this;
}

```

## disassembly

```asm
0x180073a34  mov     [rsp-38h+arg_18], rbx
0x180073a39  mov     [rsp-38h+arg_0], rcx
0x180073a3e  push    rbp
0x180073a3f  push    rsi
0x180073a40  push    rdi
0x180073a41  push    r12
0x180073a43  push    r13
0x180073a45  push    r14
0x180073a47  push    r15
0x180073a49  mov     rbp, rsp
0x180073a4c  sub     rsp, 50h
0x180073a50  mov     r12, rdx
0x180073a53  mov     rdi, rcx
0x180073a56  call    ??0?$CTSPrivateObject@VICsrMgr@@@@QEAA@PEBD@Z; CTSPrivateObject<ICsrMgr>::CTSPrivateObject<ICsrMgr>(char const *)
0x180073a5b  nop
0x180073a5c  lea     rax, ??_7CCsrMgr@@6B@; const CCsrMgr::`vftable'
0x180073a63  mov     [rdi], rax
0x180073a66  lea     rcx, [rdi+638h]; this
0x180073a6d  xor     r13d, r13d
0x180073a70  mov     [rcx+60h], r13d
0x180073a74  lea     rax, ??_7?$DynArray@VCCleanType@?$SmartArray@VCCsrPipe@@J@@J@@6B@; const DynArray<SmartArray<CCsrPipe,long>::CCleanType,long>::`vftable'
0x180073a7b  mov     [rdi+6A0h], rax
0x180073a82  mov     [rdi+6A8h], r13
0x180073a89  mov     [rdi+6B0h], r13
0x180073a90  lea     rsi, [rdi+6B8h]
0x180073a97  mov     [rsi+60h], r13d
0x180073a9b  mov     [rdi+720h], r13
0x180073aa2  lea     r14, [rdi+728h]
0x180073aa9  mov     [r14], r13
0x180073aac  mov     [rdi+730h], r13d
0x180073ab3  lea     r15, [rdi+738h]
0x180073aba  mov     [r15], r13
0x180073abd  xorps   xmm0, xmm0
0x180073ac0  movups  [rbp+var_10], xmm0
0x180073ac4  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180073ac9  mov     ebx, eax
0x180073acb  test    eax, eax
0x180073acd  jns     short loc_180073AEF
0x180073acf  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x180073ad6  mov     r8d, eax
0x180073ad9  lea     r9, aCcsrmgrCcsrmgr; "CCsrMgr::CCsrMgr"
0x180073ae0  mov     ecx, 8; int
0x180073ae5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180073aea  jmp     loc_180073C6F
0x180073aef  mov     rcx, rsi; this
0x180073af2  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180073af7  mov     ebx, eax
0x180073af9  test    eax, eax
0x180073afb  jns     short loc_180073B06
0x180073afd  lea     rdx, aCsrpipeslockIn; "CsrPipesLock.Initialize failed: 0x%x in"...
0x180073b04  jmp     short loc_180073AD6
0x180073b06  mov     r9, r14
0x180073b09  xor     r8d, r8d
0x180073b0c  xor     edx, edx
0x180073b0e  xor     ecx, ecx
0x180073b10  call    cs:__imp_RtlConnectToSm
0x180073b17  nop     dword ptr [rax+rax+00h]
0x180073b1c  mov     ebx, eax
0x180073b1e  mov     esi, 10000000h
0x180073b23  or      ebx, esi
0x180073b25  jge     short loc_180073B33
0x180073b27  mov     r8d, ebx
0x180073b2a  lea     rdx, aSmconnecttosmF; "SmConnectToSm failed: 0x%x in %s"
0x180073b31  jmp     short loc_180073AD9
0x180073b33  mov     rcx, rdi; this
0x180073b36  call    ?CreateLpcPort@CCsrMgr@@AEAAJXZ; CCsrMgr::CreateLpcPort(void)
0x180073b3b  mov     ebx, eax
0x180073b3d  test    eax, eax
0x180073b3f  jns     short loc_180073B4A
0x180073b41  lea     rdx, aCreatelpcportF; "CreateLpcPort failed: 0x%x in %s"
0x180073b48  jmp     short loc_180073AD6
0x180073b4a  mov     [rdi+740h], r13d
0x180073b51  mov     [rsp+50h+phkResult], r13
0x180073b56  mov     r9d, 10h
0x180073b5c  lea     r8, [rbp+var_10]
0x180073b60  xor     edx, edx
0x180073b62  mov     rcx, [rdi+720h]
0x180073b69  call    cs:__imp_NtAlpcQueryInformation
0x180073b70  nop     dword ptr [rax+rax+00h]
0x180073b75  test    eax, eax
0x180073b77  jns     short loc_180073B82
0x180073b79  mov     ebx, eax
0x180073b7b  or      ebx, esi
0x180073b7d  jmp     loc_180073C6F
0x180073b82  mov     eax, dword ptr [rbp+var_10+4]
0x180073b85  mov     [rdi+740h], eax
0x180073b8b  mov     [rsp+50h+phkResult], r13
0x180073b90  mov     r9, rdi
0x180073b93  lea     r8, ?staticLpcWorker@CCsrMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@@Z; CCsrMgr::staticLpcWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *)
0x180073b9a  mov     rdx, [rdi+720h]
0x180073ba1  mov     rcx, r15
0x180073ba4  call    cs:__imp_TpAllocAlpcCompletion
0x180073bab  nop     dword ptr [rax+rax+00h]
0x180073bb0  test    eax, eax
0x180073bb2  js      short loc_180073B79
0x180073bb4  mov     [rbp+hkey], r13
0x180073bb8  mov     [rbp+arg_8], r13d
0x180073bbc  lea     rax, [rbp+hkey]
0x180073bc0  mov     [rsp+50h+phkResult], rax; phkResult
0x180073bc5  mov     r9d, 20019h; samDesired
0x180073bcb  xor     r8d, r8d; ulOptions
0x180073bce  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x180073bd5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073bdc  call    cs:__imp_RegOpenKeyExW
0x180073be3  nop     dword ptr [rax+rax+00h]
0x180073be8  test    eax, eax
0x180073bea  jz      short loc_180073C19
0x180073bec  mov     eax, cs:dword_1800DF020
0x180073bf2  cmp     eax, 2
0x180073bf5  jbe     short loc_180073C6F
0x180073bf7  lea     rax, aRegopenkeyexOn; "RegOpenKeyEx on session manager control"...
0x180073bfe  mov     [rbp+arg_0], rax
0x180073c02  lea     rax, [rbp+arg_0]
0x180073c06  mov     [rsp+50h+phkResult], rax
0x180073c0b  lea     rdx, byte_1800CB2A9
0x180073c12  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180073c17  jmp     short loc_180073C6F
0x180073c19  lea     rax, [rbp+arg_8]
0x180073c1d  mov     [rsp+50h+pcbData], rax; pcbData
0x180073c22  mov     [rsp+50h+pvData], r13; pvData
0x180073c27  mov     [rsp+50h+phkResult], r13; pdwType
0x180073c2c  mov     r9d, 20h ; ' '; dwFlags
0x180073c32  lea     r8, aExecute; "Execute"
0x180073c39  xor     edx, edx; lpSubKey
0x180073c3b  mov     rcx, [rbp+hkey]; hkey
0x180073c3f  call    cs:__imp_RegGetValueW
0x180073c46  nop     dword ptr [rax+rax+00h]
0x180073c4b  test    eax, eax
0x180073c4d  jnz     short loc_180073C5F
0x180073c4f  cmp     [rbp+arg_8], 6
0x180073c53  jbe     short loc_180073C5F
0x180073c55  mov     dword ptr [rdi+744h], 1
0x180073c5f  mov     rcx, [rbp+hkey]; hKey
0x180073c63  call    cs:__imp_RegCloseKey
0x180073c6a  nop     dword ptr [rax+rax+00h]
0x180073c6f  mov     [r12], ebx
0x180073c73  mov     rax, rdi
0x180073c76  mov     rbx, [rsp+50h+arg_18]
0x180073c7e  add     rsp, 50h
0x180073c82  pop     r15
0x180073c84  pop     r14
0x180073c86  pop     r13
0x180073c88  pop     r12
0x180073c8a  pop     rdi
0x180073c8b  pop     rsi
0x180073c8c  pop     rbp
0x180073c8d  retn
```
