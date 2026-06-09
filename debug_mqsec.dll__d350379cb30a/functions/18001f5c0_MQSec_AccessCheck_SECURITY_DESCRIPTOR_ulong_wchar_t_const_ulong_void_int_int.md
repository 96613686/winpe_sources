# MQSec_AccessCheck(_SECURITY_DESCRIPTOR *,ulong,wchar_t const *,ulong,void *,int,int)

- ea: `0x18001f5c0`
- end: `0x18001fa2b`
- name: `?MQSec_AccessCheck@@YAJPEAU_SECURITY_DESCRIPTOR@@KPEB_WKPEAXHH@Z`
- size: `1131`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int, const wchar_t *, char, void *, int, WINBOOL)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004074`
- `0x1800041cc`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x180017430`
- `0x18001adf4`
- `0x18001f3e0`
- `0x18001f5c0`
- `0x180020050`
- `0x18002036c`
- `0x180020680`
- `0x180021890`
- `0x180027500`
- `0x180028214`
- `0x180028cc0`
- `0x180031010`

## import_xrefs

- `msvcrt!free` at `0x18001f979`
- `msvcrt!free` at `0x18001f979`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001f845`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001f845`
- `KERNEL32!GetLastError` at `0x18001f84f`
- `KERNEL32!GetLastError` at `0x18001f897`
- `KERNEL32!GetLastError` at `0x18001f84f`
- `KERNEL32!GetLastError` at `0x18001f897`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MQSec_AccessCheck(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned int a2,
        wchar_t *a3,
        DWORD a4,
        void *HandleId,
        int a6,
        WINBOOL bDaclPresent)
{
  CImpersonate *v11; // rdi
  void *v12; // rax
  int v13; // ebx
  unsigned int AccessToken; // eax
  void *v15; // r14
  void *LocalMachineSid; // rdi
  DWORD LastError; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // eax
  HANDLE ClientToken; // [rsp+60h] [rbp-41h] BYREF
  char *v23; // [rsp+68h] [rbp-39h] BYREF
  CImpersonate *v24; // [rsp+70h] [rbp-31h] BYREF
  _OWORD pSecurityDescriptora[2]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v26; // [rsp+98h] [rbp-9h]
  void *Block; // [rsp+F0h] [rbp+4Fh] BYREF

  if ( !pSecurityDescriptor
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 33, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
  }
  v24 = 0;
  v11 = 0;
  if ( bDaclPresent )
  {
    v12 = MmAllocate(0x20u);
    Block = v12;
    if ( v12 )
      v11 = CImpersonate::CImpersonate((CImpersonate *)v12, a6, 1);
    else
      v11 = 0;
    v24 = v11;
    if ( (*(unsigned int (__fastcall **)(CImpersonate *))(*(_QWORD *)v11 + 8LL))(v11) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 34, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
      v13 = -1072824284;
      goto LABEL_52;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 35, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
    MQSec_TraceThreadTokenInfo();
  }
  ClientToken = 0;
  AccessToken = GetAccessToken(&ClientToken, 0, (__int64)a3, 1);
  if ( !AccessToken )
  {
    v15 = HandleId;
    v13 = DoAccessCheck(pSecurityDescriptor, a2, a3, a4, HandleId, ClientToken);
    v23 = 0;
    if ( v13 >= 0 )
    {
LABEL_51:
      CHandle::~CHandle((CHandle *)&ClientToken);
      goto LABEL_52;
    }
    if ( pSecurityDescriptor
      && (*(unsigned int (__fastcall **)(CImpersonate *, char **))(*(_QWORD *)v11 + 24LL))(v11, &v23) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32), 0x25u, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, v23);
      LocalMachineSid = MQSec_GetLocalMachineSid(0, 0);
      if ( !LocalMachineSid )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
        goto LABEL_51;
      }
      memset(pSecurityDescriptora, 0, sizeof(pSecurityDescriptora));
      v26 = 0;
      if ( !InitializeSecurityDescriptor(pSecurityDescriptora, 1u) )
      {
        LastError = GetLastError();
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
          goto LABEL_51;
        v19 = 39;
        goto LABEL_41;
      }
      if ( !(unsigned int)MQSec_CopySecurityDescriptor(pSecurityDescriptora, pSecurityDescriptor, 3, 0) )
      {
        LastError = GetLastError();
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
          goto LABEL_51;
        v19 = 40;
LABEL_41:
        WPP_SF_d(v18[32], v19, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
        goto LABEL_51;
      }
      bDaclPresent = 0;
      Block = 0;
      if ( (int)ReplaceSidWithSystemService(
                  pSecurityDescriptora,
                  pSecurityDescriptor,
                  LocalMachineSid,
                  v23,
                  (PACL *)&Block,
                  &bDaclPresent) >= 0
        && bDaclPresent )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 41, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
        v13 = DoAccessCheck(pSecurityDescriptora, a2, a3, a4, v15, ClientToken);
      }
      free(Block);
      if ( v13 >= 0 )
        goto LABEL_51;
    }
    LOWORD(bDaclPresent) = 120;
    LODWORD(Block) = v13;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v20 = mqwcslen(L"acssctrl/acsschck");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v20 + 1),
        L"acssctrl/acsschck",
        2,
        &bDaclPresent,
        4,
        &Block,
        0,
        0);
    }
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 36, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, AccessToken);
  CHandle::~CHandle((CHandle *)&ClientToken);
  v13 = -1072824283;
LABEL_52:
  P<CImpersonate>::~P<CImpersonate>(&v24);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001f5c0  push    rbp
0x18001f5c2  push    rbx
0x18001f5c3  push    rsi
0x18001f5c4  push    rdi
0x18001f5c5  push    r12
0x18001f5c7  push    r13
0x18001f5c9  push    r14
0x18001f5cb  push    r15
0x18001f5cd  lea     rbp, [rsp-7]
0x18001f5d2  sub     rsp, 0A8h
0x18001f5d9  mov     r15d, r9d
0x18001f5dc  mov     r12, r8
0x18001f5df  mov     r13d, edx
0x18001f5e2  mov     rsi, rcx
0x18001f5e5  mov     r14d, 1
0x18001f5eb  lea     rax, WPP_GLOBAL_Control
0x18001f5f2  xor     ebx, ebx
0x18001f5f4  test    rcx, rcx
0x18001f5f7  jnz     short loc_18001F624
0x18001f5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f600  cmp     rcx, rax
0x18001f603  jz      short loc_18001F624
0x18001f605  test    [rcx+10Ch], r14b
0x18001f60c  jz      short loc_18001F624
0x18001f60e  lea     edx, [rsi+21h]
0x18001f611  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f618  mov     rcx, [rcx+100h]
0x18001f61f  call    WPP_SF_
0x18001f624  mov     [rbp+3Fh+var_70], rbx
0x18001f628  mov     rdi, rbx
0x18001f62b  cmp     [rbp+3Fh+arg_30], ebx
0x18001f62e  jz      loc_18001F6EB
0x18001f634  mov     ecx, 20h ; ' '; unsigned __int64
0x18001f639  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001f63e  mov     [rbp+3Fh+Block], rax
0x18001f642  test    rax, rax
0x18001f645  jz      short loc_18001F65A
0x18001f647  mov     r8d, r14d; int
0x18001f64a  mov     edx, [rbp+3Fh+arg_28]; int
0x18001f64d  mov     rcx, rax; this
0x18001f650  call    ??0CImpersonate@@QEAA@HH@Z; CImpersonate::CImpersonate(int,int)
0x18001f655  mov     rdi, rax
0x18001f658  jmp     short loc_18001F65D
0x18001f65a  mov     rdi, rbx
0x18001f65d  mov     [rbp+3Fh+var_70], rdi
0x18001f661  mov     rax, [rdi]
0x18001f664  mov     rcx, rdi
0x18001f667  mov     rax, [rax+8]
0x18001f66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f670  test    eax, eax
0x18001f672  jz      short loc_18001F6B2
0x18001f674  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f67b  lea     rdx, WPP_GLOBAL_Control
0x18001f682  cmp     rcx, rdx
0x18001f685  jz      short loc_18001F6A8
0x18001f687  test    [rcx+10Ch], r14b
0x18001f68e  jz      short loc_18001F6A8
0x18001f690  mov     edx, 22h ; '"'
0x18001f695  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f69c  mov     rcx, [rcx+100h]
0x18001f6a3  call    WPP_SF_
0x18001f6a8  mov     ebx, 0C00E0024h
0x18001f6ad  jmp     loc_18001FA0C
0x18001f6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6b9  lea     rax, WPP_GLOBAL_Control
0x18001f6c0  cmp     rcx, rax
0x18001f6c3  jz      short loc_18001F6E6
0x18001f6c5  test    byte ptr [rcx+10Ch], 4
0x18001f6cc  jz      short loc_18001F6E6
0x18001f6ce  mov     edx, 23h ; '#'
0x18001f6d3  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f6da  mov     rcx, [rcx+100h]
0x18001f6e1  call    WPP_SF_
0x18001f6e6  call    ?MQSec_TraceThreadTokenInfo@@YAXXZ; MQSec_TraceThreadTokenInfo(void)
0x18001f6eb  mov     [rbp+3Fh+ClientToken], rbx
0x18001f6ef  mov     r9d, r14d; int
0x18001f6f2  xor     edx, edx; int
0x18001f6f4  lea     rcx, [rbp+3Fh+ClientToken]; TokenHandle
0x18001f6f8  call    ?GetAccessToken@@YAKPEAPEAXHKH@Z; GetAccessToken(void * *,int,ulong,int)
0x18001f6fd  test    eax, eax
0x18001f6ff  jz      short loc_18001F74C
0x18001f701  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f708  lea     rdx, WPP_GLOBAL_Control
0x18001f70f  cmp     rcx, rdx
0x18001f712  jz      short loc_18001F739
0x18001f714  test    [rcx+10Ch], r14b
0x18001f71b  jz      short loc_18001F739
0x18001f71d  mov     edx, 24h ; '$'
0x18001f722  mov     r9d, eax
0x18001f725  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f72c  mov     rcx, [rcx+100h]
0x18001f733  call    WPP_SF_d
0x18001f738  nop
0x18001f739  lea     rcx, [rbp+3Fh+ClientToken]; this
0x18001f73d  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001f742  mov     ebx, 0C00E0025h
0x18001f747  jmp     loc_18001FA0C
0x18001f74c  mov     rax, [rbp+3Fh+ClientToken]
0x18001f750  mov     qword ptr [rsp+0E0h+bDaclPresent], rax; ClientToken
0x18001f755  mov     r14, [rbp+3Fh+arg_20]
0x18001f759  mov     [rsp+0E0h+HandleId], r14; HandleId
0x18001f75e  mov     r9d, r15d; char
0x18001f761  mov     r8, r12; wchar_t *
0x18001f764  mov     edx, r13d; unsigned int
0x18001f767  mov     rcx, rsi; pSecurityDescriptor
0x18001f76a  call    _DoAccessCheck
0x18001f76f  mov     ebx, eax
0x18001f771  mov     [rbp+3Fh+var_78], 0
0x18001f779  test    eax, eax
0x18001f77b  jns     loc_18001FA02
0x18001f781  test    rsi, rsi
0x18001f784  jz      loc_18001F984
0x18001f78a  mov     rdx, [rdi]
0x18001f78d  mov     rax, [rdx+18h]
0x18001f791  lea     rdx, [rbp+3Fh+var_78]
0x18001f795  mov     rcx, rdi
0x18001f798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f79d  test    eax, eax
0x18001f79f  jz      loc_18001F984
0x18001f7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7ac  lea     rax, WPP_GLOBAL_Control
0x18001f7b3  cmp     rcx, rax
0x18001f7b6  jz      short loc_18001F7DD
0x18001f7b8  test    byte ptr [rcx+10Ch], 4
0x18001f7bf  jz      short loc_18001F7DD
0x18001f7c1  mov     edx, 25h ; '%'
0x18001f7c6  mov     r9, [rbp+3Fh+var_78]
0x18001f7ca  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f7d1  mov     rcx, [rcx+100h]; LoggerHandle
0x18001f7d8  call    WPP_SF__sid_
0x18001f7dd  xor     edx, edx; unsigned int *
0x18001f7df  xor     ecx, ecx; int
0x18001f7e1  call    ?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x18001f7e6  mov     rdi, rax
0x18001f7e9  test    rax, rax
0x18001f7ec  jnz     short loc_18001F82D
0x18001f7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7f5  lea     rax, WPP_GLOBAL_Control
0x18001f7fc  cmp     rcx, rax
0x18001f7ff  jz      loc_18001FA02
0x18001f805  test    byte ptr [rcx+10Ch], 1
0x18001f80c  jz      loc_18001FA02
0x18001f812  lea     edx, [rdi+26h]
0x18001f815  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f81c  mov     rcx, [rcx+100h]
0x18001f823  call    WPP_SF_
0x18001f828  jmp     loc_18001FA02
0x18001f82d  xorps   xmm0, xmm0
0x18001f830  xor     eax, eax
0x18001f832  movups  [rbp+3Fh+pSecurityDescriptor], xmm0
0x18001f836  movups  [rbp+3Fh+var_58], xmm0
0x18001f83a  mov     [rbp+3Fh+var_48], rax
0x18001f83e  lea     edx, [rax+1]; dwRevision
0x18001f841  lea     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18001f845  call    cs:__imp_InitializeSecurityDescriptor
0x18001f84b  test    eax, eax
0x18001f84d  jnz     short loc_18001F880
0x18001f84f  call    cs:__imp_GetLastError
0x18001f855  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f85c  lea     rdx, WPP_GLOBAL_Control
0x18001f863  cmp     rcx, rdx
0x18001f866  jz      loc_18001FA02
0x18001f86c  test    byte ptr [rcx+10Ch], 1
0x18001f873  jz      loc_18001FA02
0x18001f879  mov     edx, 27h ; '''
0x18001f87e  jmp     short loc_18001F8C6
0x18001f880  xor     r9d, r9d
0x18001f883  lea     r8d, [r9+3]
0x18001f887  mov     rdx, rsi
0x18001f88a  lea     rcx, [rbp+3Fh+pSecurityDescriptor]
0x18001f88e  call    ?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z; MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)
0x18001f893  test    eax, eax
0x18001f895  jnz     short loc_18001F8E1
0x18001f897  call    cs:__imp_GetLastError
0x18001f89d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a4  lea     rdx, WPP_GLOBAL_Control
0x18001f8ab  cmp     rcx, rdx
0x18001f8ae  jz      loc_18001FA02
0x18001f8b4  test    byte ptr [rcx+10Ch], 1
0x18001f8bb  jz      loc_18001FA02
0x18001f8c1  mov     edx, 28h ; '('
0x18001f8c6  mov     r9d, eax
0x18001f8c9  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f8d0  mov     rcx, [rcx+100h]
0x18001f8d7  call    WPP_SF_d
0x18001f8dc  jmp     loc_18001FA02
0x18001f8e1  mov     [rbp+3Fh+arg_30], 0
0x18001f8e8  mov     [rbp+3Fh+Block], 0
0x18001f8f0  lea     rax, [rbp+3Fh+arg_30]
0x18001f8f4  mov     qword ptr [rsp+0E0h+bDaclPresent], rax; bDaclPresent
0x18001f8f9  lea     rax, [rbp+3Fh+Block]
0x18001f8fd  mov     [rsp+0E0h+HandleId], rax; __int64
0x18001f902  mov     r9, [rbp+3Fh+var_78]
0x18001f906  mov     r8, rdi
0x18001f909  mov     rdx, rsi; PSECURITY_DESCRIPTOR
0x18001f90c  lea     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18001f910  call    ReplaceSidWithSystemService
0x18001f915  test    eax, eax
0x18001f917  js      short loc_18001F975
0x18001f919  cmp     [rbp+3Fh+arg_30], 0
0x18001f91d  jz      short loc_18001F975
0x18001f91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f926  lea     rax, WPP_GLOBAL_Control
0x18001f92d  cmp     rcx, rax
0x18001f930  jz      short loc_18001F953
0x18001f932  test    byte ptr [rcx+10Ch], 4
0x18001f939  jz      short loc_18001F953
0x18001f93b  mov     edx, 29h ; ')'
0x18001f940  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001f947  mov     rcx, [rcx+100h]
0x18001f94e  call    WPP_SF_
0x18001f953  mov     rax, [rbp+3Fh+ClientToken]
0x18001f957  mov     qword ptr [rsp+0E0h+bDaclPresent], rax; ClientToken
0x18001f95c  mov     [rsp+0E0h+HandleId], r14; HandleId
0x18001f961  mov     r9d, r15d; char
0x18001f964  mov     r8, r12; wchar_t *
0x18001f967  mov     edx, r13d; unsigned int
0x18001f96a  lea     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18001f96e  call    _DoAccessCheck
0x18001f973  mov     ebx, eax
0x18001f975  mov     rcx, [rbp+3Fh+Block]; Block
0x18001f979  call    cs:__imp_free
0x18001f97f  nop
0x18001f980  test    ebx, ebx
0x18001f982  jns     short loc_18001FA02
0x18001f984  mov     eax, 78h ; 'x'
0x18001f989  mov     word ptr [rbp+3Fh+arg_30], ax
0x18001f98d  mov     dword ptr [rbp+3Fh+Block], ebx
0x18001f990  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f998  jz      short loc_18001FA02
0x18001f99a  lea     rdi, aAcssctrlAcssch; "acssctrl/acsschck"
0x18001f9a1  mov     rcx, rdi; wchar_t *
0x18001f9a4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001f9a9  mov     ecx, 1
0x18001f9ae  lea     r9d, [rcx+rax]
0x18001f9b2  add     r9, r9
0x18001f9b5  mov     [rsp+0E0h+var_90], 0
0x18001f9be  mov     [rsp+0E0h+var_98], 0
0x18001f9c7  lea     rax, [rbp+3Fh+Block]
0x18001f9cb  mov     [rsp+0E0h+var_A0], rax
0x18001f9d0  mov     [rsp+0E0h+var_A8], 4
0x18001f9d9  lea     rax, [rbp+3Fh+arg_30]
0x18001f9dd  mov     [rsp+0E0h+var_B0], rax
0x18001f9e2  mov     qword ptr [rsp+0E0h+bDaclPresent], 2
0x18001f9eb  mov     [rsp+0E0h+HandleId], rdi
0x18001f9f0  mov     r8d, ecx
0x18001f9f3  mov     edx, ecx
0x18001f9f5  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f9fc  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001fa01  nop
0x18001fa02  lea     rcx, [rbp+3Fh+ClientToken]; this
0x18001fa06  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001fa0b  nop
0x18001fa0c  lea     rcx, [rbp+3Fh+var_70]
0x18001fa10  call    ??1?$P@VCImpersonate@@@@QEAA@XZ; P<CImpersonate>::~P<CImpersonate>(void)
0x18001fa15  mov     eax, ebx
0x18001fa17  add     rsp, 0A8h
0x18001fa1e  pop     r15
0x18001fa20  pop     r14
0x18001fa22  pop     r13
0x18001fa24  pop     r12
0x18001fa26  pop     rdi
0x18001fa27  pop     rsi
0x18001fa28  pop     rbx
0x18001fa29  pop     rbp
0x18001fa2a  retn
```
