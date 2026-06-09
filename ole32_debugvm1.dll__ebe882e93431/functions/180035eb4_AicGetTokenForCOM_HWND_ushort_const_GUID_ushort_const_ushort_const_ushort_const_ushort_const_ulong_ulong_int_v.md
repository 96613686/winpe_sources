# AicGetTokenForCOM(HWND__ *,ushort const *,_GUID *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,int,void *,void * *)

- ea: `0x180035eb4`
- end: `0x180036257`
- name: `?AicGetTokenForCOM@@YAJPEAUHWND__@@PEBGPEAU_GUID@@1111KKHPEAXPEAPEAX@Z`
- size: `931`
- prototype: `HRESULT __fastcall(HWND__ *hwndParent, const wchar_t *lpDesktop, _GUID *lpGuid, const wchar_t *lpFriendlyName, const wchar_t *lpServerBinary, const wchar_t *lpIconReference, const wchar_t *lpRequestorPath, unsigned int dwRunLevel, unsigned int dwClientFlags, int fAdjustTokenSD, void *hTokenIn, void **phNewToken)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057730`

## callees

- `0x180035eb4`
- `0x180036260`
- `0x180040d0c`
- `0x1800416a4`
- `0x180052390`
- `0x180053014`
- `0x18005315c`
- `0x180053168`
- `0x1800bd9c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800360ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180036211`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800360ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180036211`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800360b1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800360f6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800360b1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800360f6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800361a4`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800361a4`
- `RPCRT4!RpcBindingFree` at `0x18003600a`
- `RPCRT4!RpcBindingFree` at `0x18003600a`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800ccbba`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800ccbba`

## pseudocode

```c
__int64 __fastcall AicGetTokenForCOM(
        HWND__ *hwndParent,
        const wchar_t *lpDesktop,
        _GUID *lpGuid,
        const wchar_t *lpFriendlyName,
        const wchar_t *lpServerBinary,
        const wchar_t *lpIconReference,
        const wchar_t *lpRequestorPath,
        unsigned int dwRunLevel,
        unsigned int dwClientFlags,
        int fAdjustTokenSD,
        HANDLE hTokenIn,
        void **phNewToken)
{
  unsigned int v13; // ebx
  unsigned int v14; // r14d
  unsigned int v15; // edx
  wchar_t *v16; // rcx
  unsigned int v17; // r8d
  int v18; // esi
  signed int started; // edi
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // ecx
  __int64 v24; // [rsp+30h] [rbp-188h]
  __int64 v25; // [rsp+38h] [rbp-180h]
  __int64 v26; // [rsp+40h] [rbp-178h]
  __int64 v27; // [rsp+78h] [rbp-140h]
  void *hLocalBinding; // [rsp+98h] [rbp-120h] BYREF
  const wchar_t *v29; // [rsp+A0h] [rbp-118h]
  const wchar_t *v30; // [rsp+A8h] [rbp-110h]
  const wchar_t *v31; // [rsp+B0h] [rbp-108h]
  HWND__ *v32; // [rsp+B8h] [rbp-100h]
  _GUID *v33; // [rsp+C0h] [rbp-F8h]
  const wchar_t *v34; // [rsp+C8h] [rbp-F0h]
  HWND__ *v35; // [rsp+D0h] [rbp-E8h]
  const wchar_t *v36; // [rsp+D8h] [rbp-E0h]
  _GUID *v37; // [rsp+E0h] [rbp-D8h]
  const wchar_t *v38; // [rsp+E8h] [rbp-D0h]
  HANDLE v39; // [rsp+F0h] [rbp-C8h]
  void **v40; // [rsp+F8h] [rbp-C0h]
  _RPC_ASYNC_STATE AsyncState; // [rsp+100h] [rbp-B8h] BYREF

  v29 = lpFriendlyName;
  v33 = lpGuid;
  v32 = hwndParent;
  v35 = hwndParent;
  v36 = lpDesktop;
  v37 = lpGuid;
  v38 = lpFriendlyName;
  v34 = lpServerBinary;
  v30 = lpIconReference;
  v31 = lpRequestorPath;
  v39 = hTokenIn;
  v40 = phNewToken;
  v13 = 0;
  hLocalBinding = 0;
  v14 = 0;
  memset_0(&AsyncState, 0, sizeof(AsyncState));
  v18 = 0;
  *phNewToken = 0;
  if ( v29 && lpServerBinary && v30 && v31 && lpDesktop && *lpDesktop )
  {
    if ( s_hServiceBinding )
      goto $MakeServerCall;
    started = AicpCreateBindingHandle(v16, v15, &hLocalBinding);
    if ( !started )
    {
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)&s_hServiceBinding,
             (signed __int64)hLocalBinding,
             0) )
      {
        RpcBindingFree(&hLocalBinding);
        hLocalBinding = 0;
      }
      goto $MakeServerCall;
    }
  }
  else
  {
    started = 87;
  }
  while ( 1 )
  {
    if ( v18 )
    {
      started = AicpAsyncFinishCall(&AsyncState, v15, v17, started);
      v18 = 0;
    }
    if ( AsyncState.u.APC.NotificationRoutine )
    {
      CloseHandle_0(AsyncState.u.APC.NotificationRoutine);
      AsyncState.u.APC.NotificationRoutine = 0;
    }
    if ( !started )
      return v13;
    if ( *phNewToken )
    {
      CloseHandle_0(*phNewToken);
      *phNewToken = 0;
    }
    v20 = (unsigned int)(started - 1708);
    if ( (unsigned int)v20 > 0x2D )
      goto LABEL_29;
    v21 = 0x200000004201LL;
    if ( !_bittest64(&v21, v20) )
      goto LABEL_29;
    if ( v14 > 1 )
    {
      started = 1061;
LABEL_29:
      if ( started > 0 )
        return (unsigned __int16)started | 0x80070000;
      return (unsigned int)started;
    }
    ++v14;
    if ( ImpersonateLoggedOnUser(hTokenIn) )
    {
      started = AicpStartAIS(v22);
      RevertToSelf();
      if ( !started )
      {
$MakeServerCall:
        started = AicpAsyncInitializeHandle(&AsyncState, v15);
        if ( !started )
        {
          if ( !ImpersonateLoggedOnUser(hTokenIn) )
            goto LABEL_23;
          LODWORD(v27) = -1;
          LODWORD(v26) = fAdjustTokenSD;
          LODWORD(v25) = dwClientFlags;
          LODWORD(v24) = dwRunLevel;
          Ndr64AsyncClientCall(
            &IAisCOMInfo_ProxyInfo,
            0,
            0,
            &AsyncState,
            s_hServiceBinding,
            v32,
            v24,
            v25,
            v26,
            lpDesktop,
            v33,
            v29,
            v34,
            v30,
            v31,
            v27,
            phNewToken);
          v18 = started + 1;
          RevertToSelf();
        }
      }
    }
    else
    {
LABEL_23:
      started = GetLastError_0();
    }
  }
}

```

## disassembly

```asm
0x180035eb4  push    rbx
0x180035eb6  push    rsi
0x180035eb7  push    rdi
0x180035eb8  push    r12
0x180035eba  push    r13
0x180035ebc  push    r14
0x180035ebe  push    r15
0x180035ec0  sub     rsp, 180h
0x180035ec7  mov     rax, cs:__security_cookie
0x180035ece  xor     rax, rsp
0x180035ed1  mov     [rsp+1B8h+var_48], rax
0x180035ed9  mov     rax, lpFriendlyName
0x180035edc  mov     [rsp+1B8h+var_118], rax
0x180035ee4  mov     [rsp+1B8h+var_F8], lpGuid
0x180035eec  mov     r15, lpDesktop
0x180035eef  mov     [rsp+1B8h+var_100], hwndParent
0x180035ef7  mov     [rsp+1B8h+var_E8], hwndParent
0x180035eff  mov     [rsp+1B8h+var_E0], lpDesktop
0x180035f07  mov     [rsp+1B8h+var_D8], lpGuid
0x180035f0f  mov     [rsp+1B8h+var_D0], rax
0x180035f17  mov     rdi, [rsp+1B8h+arg_20]
0x180035f1f  mov     [rsp+1B8h+var_F0], rdi
0x180035f27  mov     rax, [rsp+1B8h+arg_28]
0x180035f2f  mov     [rsp+1B8h+var_110], rax
0x180035f37  mov     rax, [rsp+1B8h+arg_30]
0x180035f3f  mov     [rsp+1B8h+var_108], rax
0x180035f47  mov     r13, [rsp+1B8h+hToken]
0x180035f4f  mov     [rsp+1B8h+var_C8], r13
0x180035f57  mov     r12, [rsp+1B8h+arg_58]
0x180035f5f  mov     [rsp+1B8h+var_C0], r12
0x180035f67  xor     ebx, ebx
0x180035f69  mov     [rsp+1B8h+hLocalBinding], rbx
0x180035f71  mov     r14d, ebx
0x180035f74  mov     [rsp+1B8h+dwNumTries], ebx
0x180035f7b  xor     edx, edx; Val
0x180035f7d  lea     r8d, [rbx+70h]; Size
0x180035f81  lea     hwndParent, [rsp+1B8h+AsyncState]; void *
0x180035f89  call    memset_0
0x180035f8e  mov     esi, ebx
0x180035f90  mov     [rsp+1B8h+bRPCInitiated], ebx
0x180035f97  mov     [r12], rbx
0x180035f9b  cmp     [rsp+1B8h+var_118], rbx
0x180035fa3  jz      short loc_18003601D
0x180035fa5  test    rdi, rdi
0x180035fa8  jz      short loc_18003601D
0x180035faa  cmp     [rsp+1B8h+var_110], rbx
0x180035fb2  jz      short loc_18003601D
0x180035fb4  cmp     [rsp+1B8h+var_108], rbx
0x180035fbc  jz      short loc_18003601D
0x180035fbe  test    r15, r15
0x180035fc1  jz      short loc_18003601D
0x180035fc3  cmp     [r15], bx
0x180035fc7  jz      short loc_18003601D
0x180035fc9  cmp     cs:s_hServiceBinding, rbx
0x180035fd0  jnz     $MakeServerCall
0x180035fd6  lea     lpGuid, [rsp+1B8h+hLocalBinding]; bDynamicIdentityTracking
0x180035fde  call    ?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z; AicpCreateBindingHandle(ushort *,int,void * *)
0x180035fe3  mov     edi, eax
0x180035fe5  test    eax, eax
0x180035fe7  jnz     short $CleanExit
0x180035fe9  mov     hwndParent, [rsp+1B8h+hLocalBinding]
0x180035ff1  xor     eax, eax
0x180035ff3  lock cmpxchg cs:s_hServiceBinding, hwndParent
0x180035ffc  jz      $MakeServerCall
0x180036002  lea     hwndParent, [rsp+1B8h+hLocalBinding]; Binding
0x18003600a  call    cs:__imp_RpcBindingFree
0x180036010  mov     [rsp+1B8h+hLocalBinding], rbx
0x180036018  jmp     $MakeServerCall
0x18003601d  mov     edi, 57h ; 'W'
0x180036022  test    esi, esi
0x180036024  jz      short loc_180036041
0x180036026  mov     r9d, edi; fPumpMessages
0x180036029  lea     hwndParent, [rsp+1B8h+AsyncState]; pAsyncState
0x180036031  call    ?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z; AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)
0x180036036  mov     edi, eax
0x180036038  mov     esi, ebx
0x18003603a  mov     [rsp+1B8h+bRPCInitiated], ebx
0x180036041  mov     hwndParent, qword ptr [rsp+1B8h+AsyncState.u]; hObject
0x180036049  test    hwndParent, hwndParent
0x18003604c  jz      short loc_18003605B
0x18003604e  call    CloseHandle_0
0x180036053  mov     qword ptr [rsp+1B8h+AsyncState.u], rbx
0x18003605b  test    edi, edi
0x18003605d  jz      loc_180036232
0x180036063  cmp     [r12], rbx
0x180036067  jz      short loc_180036076
0x180036069  mov     hwndParent, [r12]; hObject
0x18003606d  call    CloseHandle_0
0x180036072  mov     [r12], rbx
0x180036076  lea     eax, [rdi-6ACh]
0x18003607c  cmp     eax, 2Dh ; '-'
0x18003607f  ja      loc_180036221
0x180036085  mov     hwndParent, 200000004201h
0x18003608f  bt      hwndParent, rax
0x180036093  jnb     loc_180036221
0x180036099  cmp     r14d, 1
0x18003609d  ja      loc_18003621C
0x1800360a3  inc     r14d
0x1800360a6  mov     [rsp+1B8h+dwNumTries], r14d
0x1800360ae  mov     hwndParent, r13; hToken
0x1800360b1  call    cs:__imp_ImpersonateLoggedOnUser
0x1800360b7  test    eax, eax
0x1800360b9  jnz     short loc_1800360C7
0x1800360bb  call    GetLastError_0
0x1800360c0  mov     edi, eax
0x1800360c2  jmp     $CleanExit
0x1800360c7  call    ?AicpStartAIS@@YAKK@Z; AicpStartAIS(ulong)
0x1800360cc  mov     edi, eax
0x1800360ce  call    cs:__imp_RevertToSelf
0x1800360d4  test    edi, edi
0x1800360d6  jnz     $CleanExit
0x1800360dc  lea     hwndParent, [rsp+1B8h+AsyncState]; pAsyncState
0x1800360e4  call    ?AicpAsyncInitializeHandle@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; AicpAsyncInitializeHandle(_RPC_ASYNC_STATE *,ulong)
0x1800360e9  mov     edi, eax
0x1800360eb  test    eax, eax
0x1800360ed  jnz     $CleanExit
0x1800360f3  mov     hwndParent, r13; hToken
0x1800360f6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800360fc  test    eax, eax
0x1800360fe  jz      short loc_1800360BB
0x180036100  mov     [rsp+1B8h+var_138], r12
0x180036108  mov     dword ptr [rsp+1B8h+var_140], 0FFFFFFFFh
0x180036110  mov     rax, [rsp+1B8h+var_108]
0x180036118  mov     [rsp+1B8h+var_148], rax
0x18003611d  mov     rax, [rsp+1B8h+var_110]
0x180036125  mov     [rsp+1B8h+var_150], rax
0x18003612a  mov     rax, [rsp+1B8h+var_F0]
0x180036132  mov     [rsp+1B8h+var_158], rax
0x180036137  mov     rax, [rsp+1B8h+var_118]
0x18003613f  mov     [rsp+1B8h+var_160], rax
0x180036144  mov     rax, [rsp+1B8h+var_F8]
0x18003614c  mov     [rsp+1B8h+var_168], rax
0x180036151  mov     [rsp+1B8h+var_170], r15
0x180036156  mov     eax, [rsp+1B8h+arg_48]
0x18003615d  mov     dword ptr [rsp+1B8h+var_178], eax
0x180036161  mov     eax, [rsp+1B8h+arg_40]
0x180036168  mov     dword ptr [rsp+1B8h+var_180], eax
0x18003616c  mov     eax, [rsp+1B8h+arg_38]
0x180036173  mov     dword ptr [rsp+1B8h+var_188], eax
0x180036177  mov     rax, [rsp+1B8h+var_100]
0x18003617f  mov     [rsp+1B8h+var_190], rax
0x180036184  mov     rax, cs:s_hServiceBinding
0x18003618b  mov     [rsp+1B8h+var_198], rax
0x180036190  lea     lpFriendlyName, [rsp+1B8h+AsyncState]
0x180036198  xor     r8d, r8d; pReturnValue
0x18003619b  xor     edx, edx; nProcNum
0x18003619d  lea     hwndParent, IAisCOMInfo_ProxyInfo; pProxyInfo
0x1800361a4  call    cs:__imp_Ndr64AsyncClientCall
0x1800361aa  lea     esi, [rdi+1]
0x1800361ad  mov     [rsp+1B8h+bRPCInitiated], esi
0x1800361b4  jmp     short loc_180036211
0x1800361b6  mov     edi, eax
0x1800361b8  xor     ebx, ebx
0x1800361ba  mov     r14d, [rsp+1B8h+dwNumTries]
0x1800361c2  mov     esi, [rsp+1B8h+bRPCInitiated]
0x1800361c9  mov     rax, [rsp+1B8h+var_E8]
0x1800361d1  mov     [rsp+1B8h+var_100], rax
0x1800361d9  mov     r15, [rsp+1B8h+var_E0]
0x1800361e1  mov     rax, [rsp+1B8h+var_D8]
0x1800361e9  mov     [rsp+1B8h+var_F8], rax
0x1800361f1  mov     rax, [rsp+1B8h+var_D0]
0x1800361f9  mov     [rsp+1B8h+var_118], rax
0x180036201  mov     r13, [rsp+1B8h+var_C8]
0x180036209  mov     r12, [rsp+1B8h+var_C0]
0x180036211  call    cs:__imp_RevertToSelf
0x180036217  jmp     $CleanExit
0x18003621c  mov     edi, 425h
0x180036221  test    edi, edi
0x180036223  jz      short loc_180036232
0x180036225  jle     short loc_180036230
0x180036227  movzx   edi, di
0x18003622a  or      edi, 80070000h
0x180036230  mov     ebx, edi
0x180036232  mov     eax, ebx
0x180036234  mov     hwndParent, [rsp+1B8h+var_48]
0x18003623c  xor     hwndParent, rsp; StackCookie
0x18003623f  call    __security_check_cookie
0x180036244  add     rsp, 180h
0x18003624b  pop     r15
0x18003624d  pop     r14
0x18003624f  pop     r13
0x180036251  pop     r12
0x180036253  pop     rdi
0x180036254  pop     rsi
0x180036255  pop     rbx
0x180036256  retn
0x1800ccba9  push    rbp
0x1800ccbab  sub     rsp, 90h
0x1800ccbb2  mov     rbp, rdx
0x1800ccbb5  mov     rcx, [rcx]
0x1800ccbb8  mov     ecx, [rcx]; ExceptionCode
0x1800ccbba  call    cs:__imp_I_RpcExceptionFilter
0x1800ccbc0  nop
0x1800ccbc1  add     rsp, 90h
0x1800ccbc8  pop     rbp
0x1800ccbc9  retn
```
