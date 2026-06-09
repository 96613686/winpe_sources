# CMDMPushConfiguration::Initialize(ushort const *,EnrollmentEnrollType)

- ea: `0x18002ccec`
- end: `0x18002cef2`
- name: `?Initialize@CMDMPushConfiguration@@QEAAJPEBGW4EnrollmentEnrollType@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ea90`

## callees

- `0x1800039f0`
- `0x18000bab4`
- `0x180026d84`
- `0x180026e44`
- `0x18002c6f0`
- `0x18002ccec`
- `0x18002cef8`
- `0x18002de9c`
- `0x18002e054`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ce92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ce92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ce33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ce33`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18002cdb9`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18002cdb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cddb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cddb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMDMPushConfiguration::Initialize(__int64 a1, const OLECHAR *a2, int a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  BSTR v9; // rax
  __int64 v10; // r14
  void **v11; // rdi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[34]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "InitializeActivity");
  v17[0] = &MDMPushProvider::InitializeActivity::`vftable';
  MDMPushProvider::InitializeActivity::StartActivity((MDMPushProvider::InitializeActivity *)v17);
  if ( *(_DWORD *)a1 )
  {
    v6 = -2147483634;
    v7 = 127;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
    goto LABEL_20;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 128;
    goto LABEL_5;
  }
  v8 = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0, 0);
  if ( v8 < 0 )
  {
    v6 = 0;
    if ( v8 != -2147417831 )
      v6 = v8;
    if ( v6 < 0 )
    {
      v7 = 140;
      goto LABEL_5;
    }
  }
  v9 = SysAllocString(a2);
  *(_QWORD *)(a1 + 8) = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 144;
    goto LABEL_5;
  }
  *(_DWORD *)(a1 + 16) = a3;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, c_szTestHookLocation, L"MDMPushTestHook", 0x18u, 0, 0, 0) )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v17, SRWLock);
    v10 = v18;
    v11 = (void **)(v18 + 56);
    if ( *(_BYTE *)(v18 + 64) )
    {
      v12 = *v11;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *(_BYTE *)(v10 + 64) = 0;
    }
    *v11 = 0;
    *v11 = L"TestHook";
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    *(_DWORD *)(a1 + 20) = 1;
  }
  *(_DWORD *)a1 = 1;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
  v6 = 0;
LABEL_20:
  v17[0] = &MDMPushProvider::InitializeActivity::`vftable';
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002ccec  mov     [rsp-8+arg_10], rbx
0x18002ccf1  push    rbp
0x18002ccf2  push    rsi
0x18002ccf3  push    rdi
0x18002ccf4  push    r13
0x18002ccf6  push    r14
0x18002ccf8  lea     rbp, [rsp-0C0h]
0x18002cd00  sub     rsp, 1C0h
0x18002cd07  mov     rax, cs:__security_cookie
0x18002cd0e  xor     rax, rsp
0x18002cd11  mov     [rbp+0E0h+var_30], rax
0x18002cd18  mov     r14d, r8d
0x18002cd1b  mov     rdi, rdx
0x18002cd1e  mov     rsi, rcx
0x18002cd21  lea     rdx, aInitializeacti; "InitializeActivity"
0x18002cd28  lea     rcx, [rsp+1E0h+var_180]
0x18002cd2d  call    ??0?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002cd32  lea     r13, ??_7InitializeActivity@MDMPushProvider@@6B@; const MDMPushProvider::InitializeActivity::`vftable'
0x18002cd39  mov     [rsp+1E0h+var_180], r13
0x18002cd3e  lea     rcx, [rsp+1E0h+var_180]; this
0x18002cd43  call    ?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::InitializeActivity::StartActivity(void)
0x18002cd48  nop
0x18002cd49  cmp     dword ptr [rsi], 0
0x18002cd4c  jz      short loc_18002CD5A
0x18002cd4e  mov     ebx, 8000000Eh
0x18002cd53  mov     edx, 7Fh
0x18002cd58  jmp     short loc_18002CD69
0x18002cd5a  test    rdi, rdi
0x18002cd5d  jnz     short loc_18002CD84
0x18002cd5f  mov     ebx, 80070057h
0x18002cd64  mov     edx, 80h; void *
0x18002cd69  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002cd70  mov     r9d, ebx; char *
0x18002cd73  mov     rcx, [rbp+0E8h]; this
0x18002cd7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd7f  jmp     loc_18002CEB1
0x18002cd84  mov     [rsp+1E0h+pReserved3], 0; pReserved3
0x18002cd8d  mov     [rsp+1E0h+dwCapabilities], 0; dwCapabilities
0x18002cd95  mov     [rsp+1E0h+pAuthList], 0; pAuthList
0x18002cd9e  mov     [rsp+1E0h+dwImpLevel], 3; dwImpLevel
0x18002cda6  mov     [rsp+1E0h+dwAuthnLevel], 1; dwAuthnLevel
0x18002cdae  xor     r9d, r9d; pReserved1
0x18002cdb1  xor     r8d, r8d; asAuthSvc
0x18002cdb4  or      edx, 0FFFFFFFFh; cAuthSvc
0x18002cdb7  xor     ecx, ecx; pSecDesc
0x18002cdb9  call    cs:__imp_CoInitializeSecurity
0x18002cdbf  test    eax, eax
0x18002cdc1  jns     short loc_18002CDD8
0x18002cdc3  xor     ebx, ebx
0x18002cdc5  cmp     eax, 80010119h
0x18002cdca  cmovnz  ebx, eax
0x18002cdcd  test    ebx, ebx
0x18002cdcf  jns     short loc_18002CDD8
0x18002cdd1  mov     edx, 8Ch
0x18002cdd6  jmp     short loc_18002CD69
0x18002cdd8  mov     rcx, rdi; psz
0x18002cddb  call    cs:__imp_SysAllocString
0x18002cde1  mov     [rsi+8], rax
0x18002cde5  test    rax, rax
0x18002cde8  jnz     short loc_18002CDF9
0x18002cdea  mov     ebx, 8007000Eh
0x18002cdef  mov     edx, 90h
0x18002cdf4  jmp     loc_18002CD69
0x18002cdf9  mov     [rsi+10h], r14d
0x18002cdfd  mov     [rsp+1E0h+pAuthList], 0; pcbData
0x18002ce06  mov     qword ptr [rsp+1E0h+dwImpLevel], 0; pvData
0x18002ce0f  mov     qword ptr [rsp+1E0h+dwAuthnLevel], 0; pdwType
0x18002ce18  mov     r9d, 18h; dwFlags
0x18002ce1e  lea     r8, aMdmpushtesthoo; "MDMPushTestHook"
0x18002ce25  mov     rdx, cs:?c_szTestHookLocation@@3PEBGEB; lpSubKey
0x18002ce2c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002ce33  call    cs:__imp_RegGetValueW
0x18002ce39  test    eax, eax
0x18002ce3b  jnz     short loc_18002CE9F
0x18002ce3d  lea     rdx, [rsp+1E0h+SRWLock]
0x18002ce42  lea     rcx, [rsp+1E0h+var_180]
0x18002ce47  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002ce4c  mov     r14, [rbp+0E0h+var_70]
0x18002ce50  lea     rdi, [r14+38h]
0x18002ce54  cmp     byte ptr [r14+40h], 0
0x18002ce59  jz      short loc_18002CE77
0x18002ce5b  mov     rbx, [rdi]
0x18002ce5e  call    cs:__imp_GetProcessHeap
0x18002ce64  mov     r8, rbx; lpMem
0x18002ce67  xor     edx, edx; dwFlags
0x18002ce69  mov     rcx, rax; hHeap
0x18002ce6c  call    cs:__imp_HeapFree
0x18002ce72  mov     byte ptr [r14+40h], 0
0x18002ce77  mov     qword ptr [rdi], 0
0x18002ce7e  lea     rax, aTesthook; "TestHook"
0x18002ce85  mov     [rdi], rax
0x18002ce88  mov     rcx, [rsp+1E0h+SRWLock]; SRWLock
0x18002ce8d  test    rcx, rcx
0x18002ce90  jz      short loc_18002CE98
0x18002ce92  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ce98  mov     dword ptr [rsi+14h], 1
0x18002ce9f  mov     dword ptr [rsi], 1
0x18002cea5  lea     rcx, [rsp+1E0h+var_180]
0x18002ceaa  call    ?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002ceaf  xor     ebx, ebx
0x18002ceb1  mov     [rsp+1E0h+var_180], r13
0x18002ceb6  lea     rcx, [rsp+1E0h+var_180]
0x18002cebb  call    ?Destroy@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002cec0  lea     rcx, [rsp+1E0h+var_180]
0x18002cec5  call    ??1?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002ceca  mov     eax, ebx
0x18002cecc  mov     rcx, [rbp+0E0h+var_30]
0x18002ced3  xor     rcx, rsp; StackCookie
0x18002ced6  call    __security_check_cookie
0x18002cedb  mov     rbx, [rsp+1E0h+arg_10]
0x18002cee3  add     rsp, 1C0h
0x18002ceea  pop     r14
0x18002ceec  pop     r13
0x18002ceee  pop     rdi
0x18002ceef  pop     rsi
0x18002cef0  pop     rbp
0x18002cef1  retn
```
