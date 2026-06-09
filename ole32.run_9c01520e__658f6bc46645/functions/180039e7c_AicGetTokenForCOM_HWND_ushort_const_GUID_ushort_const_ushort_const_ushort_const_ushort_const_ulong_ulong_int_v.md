# AicGetTokenForCOM(HWND__ *,ushort const *,_GUID *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,int,void *,void * *)

- ea: `0x180039e7c`
- end: `0x18003a242`
- name: `?AicGetTokenForCOM@@YAJPEAUHWND__@@PEBGPEAU_GUID@@1111KKHPEAXPEAPEAX@Z`
- size: `966`
- prototype: `HRESULT __fastcall(HWND__ *hwndParent, const wchar_t *lpDesktop, _GUID *lpGuid, const wchar_t *lpFriendlyName, const wchar_t *lpServerBinary, const wchar_t *lpIconReference, const wchar_t *lpRequestorPath, unsigned int dwRunLevel, unsigned int dwClientFlags, int fAdjustTokenSD, void *hTokenIn, void **phNewToken)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004ad80`

## callees

- `0x180039e7c`
- `0x18003a248`
- `0x180042eac`
- `0x180043b14`
- `0x180046460`
- `0x180047484`
- `0x1800475e8`
- `0x1800475f4`
- `0x1800c6bdc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a0a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a1f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a0a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a1f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a082`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a0d3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a082`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a0d3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18003a184`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18003a184`
- `RPCRT4!RpcBindingFree` at `0x180039fd2`
- `RPCRT4!RpcBindingFree` at `0x180039fd2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800d6eeb`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800d6eeb`

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
  unsigned int v13; // esi
  unsigned int v14; // r14d
  unsigned int v15; // edx
  wchar_t *v16; // rcx
  unsigned int v17; // r8d
  signed int started; // edi
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // ecx
  __int64 v23; // [rsp+30h] [rbp-198h]
  __int64 v24; // [rsp+38h] [rbp-190h]
  __int64 v25; // [rsp+40h] [rbp-188h]
  __int64 v26; // [rsp+78h] [rbp-150h]
  int bRPCInitiated; // [rsp+90h] [rbp-138h]
  void *hLocalBinding; // [rsp+98h] [rbp-130h] BYREF
  const wchar_t *v29; // [rsp+A8h] [rbp-120h]
  const wchar_t *v30; // [rsp+B0h] [rbp-118h]
  const wchar_t *v31; // [rsp+B8h] [rbp-110h]
  HWND__ *v32; // [rsp+C0h] [rbp-108h]
  _GUID *v33; // [rsp+C8h] [rbp-100h]
  const wchar_t *v34; // [rsp+D0h] [rbp-F8h]
  HWND__ *v35; // [rsp+D8h] [rbp-F0h]
  const wchar_t *v36; // [rsp+E0h] [rbp-E8h]
  _GUID *v37; // [rsp+E8h] [rbp-E0h]
  const wchar_t *v38; // [rsp+F0h] [rbp-D8h]
  HANDLE v39; // [rsp+F8h] [rbp-D0h]
  void **v40; // [rsp+100h] [rbp-C8h]
  _RPC_ASYNC_STATE AsyncState; // [rsp+110h] [rbp-B8h] BYREF

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
  bRPCInitiated = 0;
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
    if ( bRPCInitiated )
    {
      started = AicpAsyncFinishCall(&AsyncState, v15, v17, started);
      bRPCInitiated = 0;
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
    v19 = (unsigned int)(started - 1708);
    if ( (unsigned int)v19 > 0x2D )
      goto LABEL_29;
    v20 = 0x200000004201LL;
    if ( !_bittest64(&v20, v19) )
      goto LABEL_29;
    if ( v14 > 1 )
    {
      started = 1061;
LABEL_29:
      if ( started > 0 )
        return (unsigned __int16)started | 0x80070000;
      else
        return (unsigned int)started;
    }
    ++v14;
    if ( ImpersonateLoggedOnUser(hTokenIn) )
    {
      started = AicpStartAIS(v21);
      RevertToSelf();
      if ( !started )
      {
$MakeServerCall:
        started = AicpAsyncInitializeHandle(&AsyncState, v15);
        if ( !started )
        {
          if ( !ImpersonateLoggedOnUser(hTokenIn) )
            goto LABEL_23;
          LODWORD(v26) = -1;
          LODWORD(v25) = fAdjustTokenSD;
          LODWORD(v24) = dwClientFlags;
          LODWORD(v23) = dwRunLevel;
          Ndr64AsyncClientCall(
            &IAisCOMInfo_ProxyInfo,
            0,
            0,
            &AsyncState,
            s_hServiceBinding,
            v32,
            v23,
            v24,
            v25,
            lpDesktop,
            v33,
            v29,
            v34,
            v30,
            v31,
            v26,
            phNewToken);
          bRPCInitiated = 1;
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
0x180039e7c  push    rbx
0x180039e7e  push    rsi
0x180039e7f  push    rdi
0x180039e80  push    r12
0x180039e82  push    r13
0x180039e84  push    r14
0x180039e86  push    r15
0x180039e88  sub     rsp, 190h
0x180039e8f  mov     rax, cs:__security_cookie
0x180039e96  xor     rax, rsp
0x180039e99  mov     [rsp+1C8h+var_48], rax
0x180039ea1  mov     rax, lpFriendlyName
0x180039ea4  mov     [rsp+1C8h+var_120], rax
0x180039eac  mov     [rsp+1C8h+var_100], lpGuid
0x180039eb4  mov     r15, lpDesktop
0x180039eb7  mov     [rsp+1C8h+var_108], hwndParent
0x180039ebf  mov     [rsp+1C8h+var_F0], hwndParent
0x180039ec7  mov     [rsp+1C8h+var_E8], lpDesktop
0x180039ecf  mov     [rsp+1C8h+var_E0], lpGuid
0x180039ed7  mov     [rsp+1C8h+var_D8], rax
0x180039edf  mov     rdi, [rsp+1C8h+arg_20]
0x180039ee7  mov     [rsp+1C8h+var_F8], rdi
0x180039eef  mov     rax, [rsp+1C8h+arg_28]
0x180039ef7  mov     [rsp+1C8h+var_118], rax
0x180039eff  mov     rax, [rsp+1C8h+arg_30]
0x180039f07  mov     [rsp+1C8h+var_110], rax
0x180039f0f  mov     r13, [rsp+1C8h+hToken]
0x180039f17  mov     [rsp+1C8h+var_D0], r13
0x180039f1f  mov     r12, [rsp+1C8h+arg_58]
0x180039f27  mov     [rsp+1C8h+var_C8], r12
0x180039f2f  xor     ebx, ebx
0x180039f31  mov     esi, ebx
0x180039f33  mov     [rsp+1C8h+hLocalBinding], rbx
0x180039f3b  mov     r14d, ebx
0x180039f3e  mov     [rsp+1C8h+dwNumTries], ebx
0x180039f45  xor     edx, edx; Val
0x180039f47  lea     r8d, [rbx+70h]; Size
0x180039f4b  lea     hwndParent, [rsp+1C8h+AsyncState]; void *
0x180039f53  call    memset_0
0x180039f58  mov     [rsp+1C8h+bRPCInitiated], ebx
0x180039f5f  mov     [r12], rbx
0x180039f63  cmp     [rsp+1C8h+var_120], rbx
0x180039f6b  jz      short loc_180039FEB
0x180039f6d  test    rdi, rdi
0x180039f70  jz      short loc_180039FEB
0x180039f72  cmp     [rsp+1C8h+var_118], rbx
0x180039f7a  jz      short loc_180039FEB
0x180039f7c  cmp     [rsp+1C8h+var_110], rbx
0x180039f84  jz      short loc_180039FEB
0x180039f86  test    r15, r15
0x180039f89  jz      short loc_180039FEB
0x180039f8b  cmp     [r15], bx
0x180039f8f  jz      short loc_180039FEB
0x180039f91  cmp     cs:s_hServiceBinding, rbx
0x180039f98  jnz     $MakeServerCall
0x180039f9e  lea     lpGuid, [rsp+1C8h+hLocalBinding]; bDynamicIdentityTracking
0x180039fa6  call    ?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z; AicpCreateBindingHandle(ushort *,int,void * *)
0x180039fab  mov     edi, eax
0x180039fad  test    eax, eax
0x180039faf  jnz     short $CleanExit
0x180039fb1  mov     hwndParent, [rsp+1C8h+hLocalBinding]
0x180039fb9  xor     eax, eax
0x180039fbb  lock cmpxchg cs:s_hServiceBinding, hwndParent
0x180039fc4  jz      $MakeServerCall
0x180039fca  lea     hwndParent, [rsp+1C8h+hLocalBinding]; Binding
0x180039fd2  call    cs:__imp_RpcBindingFree
0x180039fd9  nop     dword ptr [rax+rax+00h]
0x180039fde  mov     [rsp+1C8h+hLocalBinding], rbx
0x180039fe6  jmp     $MakeServerCall
0x180039feb  mov     edi, 57h ; 'W'
0x180039ff0  cmp     [rsp+1C8h+bRPCInitiated], ebx
0x180039ff7  jz      short loc_18003A012
0x180039ff9  mov     r9d, edi; fPumpMessages
0x180039ffc  lea     hwndParent, [rsp+1C8h+AsyncState]; pAsyncState
0x18003a004  call    ?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z; AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)
0x18003a009  mov     edi, eax
0x18003a00b  mov     [rsp+1C8h+bRPCInitiated], ebx
0x18003a012  mov     hwndParent, qword ptr [rsp+1C8h+AsyncState.u]; hObject
0x18003a01a  test    hwndParent, hwndParent
0x18003a01d  jz      short loc_18003A02C
0x18003a01f  call    CloseHandle_0
0x18003a024  mov     qword ptr [rsp+1C8h+AsyncState.u], rbx
0x18003a02c  test    edi, edi
0x18003a02e  jz      loc_18003A21C
0x18003a034  cmp     [r12], rbx
0x18003a038  jz      short loc_18003A047
0x18003a03a  mov     hwndParent, [r12]; hObject
0x18003a03e  call    CloseHandle_0
0x18003a043  mov     [r12], rbx
0x18003a047  lea     eax, [rdi-6ACh]
0x18003a04d  cmp     eax, 2Dh ; '-'
0x18003a050  ja      loc_18003A209
0x18003a056  mov     hwndParent, 200000004201h
0x18003a060  bt      hwndParent, rax
0x18003a064  jnb     loc_18003A209
0x18003a06a  cmp     r14d, 1
0x18003a06e  ja      loc_18003A204
0x18003a074  inc     r14d
0x18003a077  mov     [rsp+1C8h+dwNumTries], r14d
0x18003a07f  mov     hwndParent, r13; hToken
0x18003a082  call    cs:__imp_ImpersonateLoggedOnUser
0x18003a089  nop     dword ptr [rax+rax+00h]
0x18003a08e  test    eax, eax
0x18003a090  jnz     short loc_18003A09E
0x18003a092  call    GetLastError_0
0x18003a097  mov     edi, eax
0x18003a099  jmp     $CleanExit
0x18003a09e  call    ?AicpStartAIS@@YAKK@Z; AicpStartAIS(ulong)
0x18003a0a3  mov     edi, eax
0x18003a0a5  call    cs:__imp_RevertToSelf
0x18003a0ac  nop     dword ptr [rax+rax+00h]
0x18003a0b1  test    edi, edi
0x18003a0b3  jnz     $CleanExit
0x18003a0b9  lea     hwndParent, [rsp+1C8h+AsyncState]; pAsyncState
0x18003a0c1  call    ?AicpAsyncInitializeHandle@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; AicpAsyncInitializeHandle(_RPC_ASYNC_STATE *,ulong)
0x18003a0c6  mov     edi, eax
0x18003a0c8  test    eax, eax
0x18003a0ca  jnz     $CleanExit
0x18003a0d0  mov     hwndParent, r13; hToken
0x18003a0d3  call    cs:__imp_ImpersonateLoggedOnUser
0x18003a0da  nop     dword ptr [rax+rax+00h]
0x18003a0df  test    eax, eax
0x18003a0e1  jz      short loc_18003A092
0x18003a0e3  mov     [rsp+1C8h+var_148], r12
0x18003a0eb  or      dword ptr [rsp+1C8h+var_150], 0FFFFFFFFh
0x18003a0f0  mov     rax, [rsp+1C8h+var_110]
0x18003a0f8  mov     [rsp+1C8h+var_158], rax
0x18003a0fd  mov     rax, [rsp+1C8h+var_118]
0x18003a105  mov     [rsp+1C8h+var_160], rax
0x18003a10a  mov     rax, [rsp+1C8h+var_F8]
0x18003a112  mov     [rsp+1C8h+var_168], rax
0x18003a117  mov     rax, [rsp+1C8h+var_120]
0x18003a11f  mov     [rsp+1C8h+var_170], rax
0x18003a124  mov     rax, [rsp+1C8h+var_100]
0x18003a12c  mov     [rsp+1C8h+var_178], rax
0x18003a131  mov     [rsp+1C8h+var_180], r15
0x18003a136  mov     eax, [rsp+1C8h+arg_48]
0x18003a13d  mov     dword ptr [rsp+1C8h+var_188], eax
0x18003a141  mov     eax, [rsp+1C8h+arg_40]
0x18003a148  mov     dword ptr [rsp+1C8h+var_190], eax
0x18003a14c  mov     eax, [rsp+1C8h+arg_38]
0x18003a153  mov     dword ptr [rsp+1C8h+var_198], eax
0x18003a157  mov     rax, [rsp+1C8h+var_108]
0x18003a15f  mov     [rsp+1C8h+var_1A0], rax
0x18003a164  mov     rax, cs:s_hServiceBinding
0x18003a16b  mov     [rsp+1C8h+var_1A8], rax
0x18003a170  lea     lpFriendlyName, [rsp+1C8h+AsyncState]
0x18003a178  xor     r8d, r8d; pReturnValue
0x18003a17b  xor     edx, edx; nProcNum
0x18003a17d  lea     hwndParent, IAisCOMInfo_ProxyInfo; pProxyInfo
0x18003a184  call    cs:__imp_Ndr64AsyncClientCall
0x18003a18b  nop     dword ptr [rax+rax+00h]
0x18003a190  mov     [rsp+1C8h+bRPCInitiated], 1
0x18003a19b  jmp     short loc_18003A1F3
0x18003a19d  mov     edi, eax
0x18003a19f  xor     ebx, ebx
0x18003a1a1  mov     esi, ebx
0x18003a1a3  mov     r14d, [rsp+1C8h+dwNumTries]
0x18003a1ab  mov     rax, [rsp+1C8h+var_F0]
0x18003a1b3  mov     [rsp+1C8h+var_108], rax
0x18003a1bb  mov     r15, [rsp+1C8h+var_E8]
0x18003a1c3  mov     rax, [rsp+1C8h+var_E0]
0x18003a1cb  mov     [rsp+1C8h+var_100], rax
0x18003a1d3  mov     rax, [rsp+1C8h+var_D8]
0x18003a1db  mov     [rsp+1C8h+var_120], rax
0x18003a1e3  mov     r13, [rsp+1C8h+var_D0]
0x18003a1eb  mov     r12, [rsp+1C8h+var_C8]
0x18003a1f3  call    cs:__imp_RevertToSelf
0x18003a1fa  nop     dword ptr [rax+rax+00h]
0x18003a1ff  jmp     $CleanExit
0x18003a204  mov     edi, 425h
0x18003a209  test    edi, edi
0x18003a20b  jz      short loc_18003A21C
0x18003a20d  jg      short loc_18003A213
0x18003a20f  mov     esi, edi
0x18003a211  jmp     short loc_18003A21C
0x18003a213  movzx   esi, di
0x18003a216  or      esi, 80070000h
0x18003a21c  mov     eax, esi
0x18003a21e  mov     hwndParent, [rsp+1C8h+var_48]
0x18003a226  xor     hwndParent, rsp; StackCookie
0x18003a229  call    __security_check_cookie
0x18003a22e  add     rsp, 190h
0x18003a235  pop     r15
0x18003a237  pop     r14
0x18003a239  pop     r13
0x18003a23b  pop     r12
0x18003a23d  pop     rdi
0x18003a23e  pop     rsi
0x18003a23f  pop     rbx
0x18003a240  retn
0x1800d6eda  push    rbp
0x1800d6edc  sub     rsp, 90h
0x1800d6ee3  mov     rbp, rdx
0x1800d6ee6  mov     rax, [rcx]
0x1800d6ee9  mov     ecx, [rax]; ExceptionCode
0x1800d6eeb  call    cs:__imp_I_RpcExceptionFilter
0x1800d6ef2  nop     dword ptr [rax+rax+00h]
0x1800d6ef7  nop
0x1800d6ef8  add     rsp, 90h
0x1800d6eff  pop     rbp
0x1800d6f00  retn
```
