# EAPSession::initialize(void)

- ea: `0x18001a434`
- end: `0x18001a62d`
- name: `?initialize@EAPSession@@SAJXZ`
- size: `505`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180016bcc`

## callees

- `0x18000ab90`
- `0x18000b614`
- `0x18001a434`
- `0x18002b4a0`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x18001a482`
- `ntdll!RtlRandomEx` at `0x18001a482`
- `iassvcs!IASGlobalLock` at `0x18001a44f`
- `iassvcs!IASGlobalLock` at `0x18001a44f`
- `iassvcs!IASGlobalUnlock` at `0x18001a60e`
- `iassvcs!IASGlobalUnlock` at `0x18001a60e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001a46f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001a46f`
- `ADVAPI32!RegisterEventSourceW` at `0x18001a5db`
- `ADVAPI32!RegisterEventSourceW` at `0x18001a5f1`
- `ADVAPI32!RegisterEventSourceW` at `0x18001a5db`
- `ADVAPI32!RegisterEventSourceW` at `0x18001a5f1`

## string_xrefs

- `0x18001a5e1`: `RemoteAccess`

## pseudocode

```c
__int64 EAPSession::initialize(void)
{
  __int64 v0; // rcx
  int v1; // eax
  int v2; // eax
  bool v3; // r8
  unsigned int v4; // ebx
  struct _IASATTRIBUTE *v5; // rdx
  bool v6; // r8
  struct _IASATTRIBUTE *v7; // rdx
  bool v8; // r8
  struct _IASATTRIBUTE *v9; // rdx
  bool v10; // r8
  ULONG Seed; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-38h] BYREF
  struct _IASATTRIBUTE *v14[2]; // [rsp+30h] [rbp-30h] BYREF
  struct _IASATTRIBUTE *v15[2]; // [rsp+40h] [rbp-20h]

  IASGlobalLock();
  v1 = EAPSession::theRefCount;
  if ( EAPSession::theRefCount )
    goto LABEL_6;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Seed = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
  EAPSession::theNextID = RtlRandomEx(&Seed);
  *(_OWORD *)v14 = 0;
  *(_OWORD *)v15 = 0;
  v2 = IASAttributeAlloc(4, (LPVOID *)v14);
  v4 = v2;
  if ( !v2 )
  {
    IASTL::IASAttribute::attach((IASTL::IASAttribute *)&EAPSession::theNormalTimeout, v14[0], v3);
    v5 = v14[1];
    *(_DWORD *)(EAPSession::theNormalTimeout + 8) = 27;
    *(_DWORD *)(EAPSession::theNormalTimeout + 16) = 2;
    *(_DWORD *)(EAPSession::theNormalTimeout + 24) = 60;
    *(_DWORD *)(EAPSession::theNormalTimeout + 4) |= 4u;
    IASTL::IASAttribute::attach((IASTL::IASAttribute *)&EAPSession::theInteractiveTimeout, v5, v6);
    v7 = v15[0];
    *(_DWORD *)(EAPSession::theInteractiveTimeout + 8) = 27;
    *(_DWORD *)(EAPSession::theInteractiveTimeout + 16) = 2;
    *(_DWORD *)(EAPSession::theInteractiveTimeout + 24) = 30;
    *(_DWORD *)(EAPSession::theInteractiveTimeout + 4) |= 4u;
    IASTL::IASAttribute::attach((IASTL::IASAttribute *)&EAPSession::theReplay, v7, v8);
    v9 = v15[1];
    *(_DWORD *)(EAPSession::theReplay + 8LL) = 8106;
    *(_DWORD *)(EAPSession::theReplay + 16LL) = 1;
    *(_DWORD *)(EAPSession::theReplay + 24LL) = 1;
    *(_DWORD *)(EAPSession::theReplay + 4LL) |= 4u;
    IASTL::IASAttribute::attach((IASTL::IASAttribute *)&EAPSession::thePeapChannelUp, v9, v10);
    *(_DWORD *)(EAPSession::thePeapChannelUp + 8LL) = 8113;
    *(_DWORD *)(EAPSession::thePeapChannelUp + 16LL) = 1;
    *(_DWORD *)(EAPSession::thePeapChannelUp + 24LL) = -1;
    *(_DWORD *)(EAPSession::thePeapChannelUp + 4LL) |= 4u;
    EAPSession::theIASEventLog = RegisterEventSourceW(0, L"IAS");
    EAPSession::theRASEventLog = RegisterEventSourceW(0, L"RemoteAccess");
    v1 = EAPSession::theRefCount;
LABEL_6:
    EAPSession::theRefCount = v1 + 1;
    v4 = 0;
    goto LABEL_7;
  }
  if ( v2 > 0 )
    v4 = (unsigned __int16)v2 | 0x80070000;
LABEL_7:
  IASGlobalUnlock(v0);
  return v4;
}

```

## disassembly

```asm
0x18001a434  mov     [rsp-8+arg_0], rbx
0x18001a439  push    rbp
0x18001a43a  mov     rbp, rsp
0x18001a43d  sub     rsp, 60h
0x18001a441  mov     rax, cs:__security_cookie
0x18001a448  xor     rax, rsp
0x18001a44b  mov     [rbp+var_10], rax
0x18001a44f  call    cs:__imp_IASGlobalLock
0x18001a455  mov     eax, cs:?theRefCount@EAPSession@@1JA; long EAPSession::theRefCount
0x18001a45b  test    eax, eax
0x18001a45d  jnz     loc_18001A604
0x18001a463  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a467  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a46f  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a475  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18001a478  lea     rcx, [rbp+Seed]; Seed
0x18001a47c  xor     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001a47f  mov     [rbp+Seed], eax
0x18001a482  call    cs:__imp_RtlRandomEx
0x18001a488  xorps   xmm0, xmm0
0x18001a48b  lea     rdx, [rbp+var_30]
0x18001a48f  mov     ecx, 4
0x18001a494  mov     cs:?theNextID@EAPSession@@1JA, eax; long EAPSession::theNextID
0x18001a49a  movups  xmmword ptr [rbp+var_30], xmm0
0x18001a49e  movups  xmmword ptr [rbp+var_20], xmm0
0x18001a4a2  call    IASAttributeAlloc
0x18001a4a7  mov     ebx, eax
0x18001a4a9  test    eax, eax
0x18001a4ab  jz      short loc_18001A4C1
0x18001a4ad  jle     loc_18001A60E
0x18001a4b3  movzx   ebx, ax
0x18001a4b6  or      ebx, 80070000h
0x18001a4bc  jmp     loc_18001A60E
0x18001a4c1  mov     rdx, [rbp+var_30]; struct _IASATTRIBUTE *
0x18001a4c5  lea     rcx, ?theNormalTimeout@EAPSession@@1VIASAttribute@IASTL@@A; this
0x18001a4cc  call    ?attach@IASAttribute@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttribute::attach(_IASATTRIBUTE *,bool)
0x18001a4d1  mov     rax, cs:?theNormalTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theNormalTimeout
0x18001a4d8  lea     rcx, ?theInteractiveTimeout@EAPSession@@1VIASAttribute@IASTL@@A; this
0x18001a4df  mov     rdx, [rbp+var_30+8]; struct _IASATTRIBUTE *
0x18001a4e3  mov     ebx, 2
0x18001a4e8  mov     dword ptr [rax+8], 1Bh
0x18001a4ef  mov     rax, cs:?theNormalTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theNormalTimeout
0x18001a4f6  mov     [rax+10h], ebx
0x18001a4f9  mov     rax, cs:?theNormalTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theNormalTimeout
0x18001a500  mov     dword ptr [rax+18h], 3Ch ; '<'
0x18001a507  mov     rax, cs:?theNormalTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theNormalTimeout
0x18001a50e  or      dword ptr [rax+4], 4
0x18001a512  call    ?attach@IASAttribute@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttribute::attach(_IASATTRIBUTE *,bool)
0x18001a517  mov     rax, cs:?theInteractiveTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theInteractiveTimeout
0x18001a51e  lea     rcx, ?theReplay@EAPSession@@1VIASAttribute@IASTL@@A; this
0x18001a525  mov     rdx, [rbp+var_20]; struct _IASATTRIBUTE *
0x18001a529  mov     dword ptr [rax+8], 1Bh
0x18001a530  mov     rax, cs:?theInteractiveTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theInteractiveTimeout
0x18001a537  mov     [rax+10h], ebx
0x18001a53a  mov     rax, cs:?theInteractiveTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theInteractiveTimeout
0x18001a541  mov     dword ptr [rax+18h], 1Eh
0x18001a548  mov     rax, cs:?theInteractiveTimeout@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theInteractiveTimeout
0x18001a54f  or      dword ptr [rax+4], 4
0x18001a553  call    ?attach@IASAttribute@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttribute::attach(_IASATTRIBUTE *,bool)
0x18001a558  mov     rax, cs:?theReplay@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theReplay
0x18001a55f  lea     rcx, ?thePeapChannelUp@EAPSession@@1VIASAttribute@IASTL@@A; this
0x18001a566  mov     rdx, [rbp+var_20+8]; struct _IASATTRIBUTE *
0x18001a56a  mov     dword ptr [rax+8], 1FAAh
0x18001a571  mov     rax, cs:?theReplay@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theReplay
0x18001a578  mov     dword ptr [rax+10h], 1
0x18001a57f  mov     rax, cs:?theReplay@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theReplay
0x18001a586  mov     dword ptr [rax+18h], 1
0x18001a58d  mov     rax, cs:?theReplay@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::theReplay
0x18001a594  or      dword ptr [rax+4], 4
0x18001a598  call    ?attach@IASAttribute@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttribute::attach(_IASATTRIBUTE *,bool)
0x18001a59d  mov     rax, cs:?thePeapChannelUp@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::thePeapChannelUp
0x18001a5a4  lea     rdx, aIas; "IAS"
0x18001a5ab  xor     ecx, ecx; lpUNCServerName
0x18001a5ad  mov     dword ptr [rax+8], 1FB1h
0x18001a5b4  mov     rax, cs:?thePeapChannelUp@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::thePeapChannelUp
0x18001a5bb  mov     dword ptr [rax+10h], 1
0x18001a5c2  mov     rax, cs:?thePeapChannelUp@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::thePeapChannelUp
0x18001a5c9  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x18001a5d0  mov     rax, cs:?thePeapChannelUp@EAPSession@@1VIASAttribute@IASTL@@A; IASTL::IASAttribute EAPSession::thePeapChannelUp
0x18001a5d7  or      dword ptr [rax+4], 4
0x18001a5db  call    cs:__imp_RegisterEventSourceW
0x18001a5e1  lea     rdx, aRemoteaccess; "RemoteAccess"
0x18001a5e8  xor     ecx, ecx; lpUNCServerName
0x18001a5ea  mov     cs:?theIASEventLog@EAPSession@@1PEAXEA, rax; void * EAPSession::theIASEventLog
0x18001a5f1  call    cs:__imp_RegisterEventSourceW
0x18001a5f7  mov     cs:?theRASEventLog@EAPSession@@1PEAXEA, rax; void * EAPSession::theRASEventLog
0x18001a5fe  mov     eax, cs:?theRefCount@EAPSession@@1JA; long EAPSession::theRefCount
0x18001a604  inc     eax
0x18001a606  mov     cs:?theRefCount@EAPSession@@1JA, eax; long EAPSession::theRefCount
0x18001a60c  xor     ebx, ebx
0x18001a60e  call    cs:__imp_IASGlobalUnlock
0x18001a614  mov     eax, ebx
0x18001a616  mov     rcx, [rbp+var_10]
0x18001a61a  xor     rcx, rsp; StackCookie
0x18001a61d  call    __security_check_cookie
0x18001a622  mov     rbx, [rsp+60h+arg_0]
0x18001a627  add     rsp, 60h
0x18001a62b  pop     rbp
0x18001a62c  retn
```
