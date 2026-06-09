# AicGetTokenForMSI(HWND__ *,ushort const *,_MSI_ACTION,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,ulong,int,void *,void * *)

- ea: `0x1802645bc`
- end: `0x1802649da`
- name: `?AicGetTokenForMSI@@YAJPEAUHWND__@@PEBGW4_MSI_ACTION@@111111KPEAPEBG3KHPEAXPEAPEAX@Z`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180147efc`

## callees

- `0x180176366`
- `0x180176372`
- `0x1802645bc`
- `0x1802649e0`
- `0x180264a0c`
- `0x180264aa4`
- `0x180264b04`
- `0x180264c88`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180265aca`
- `RPCRT4!I_RpcExceptionFilter` at `0x180265aca`
- `RPCRT4!RpcBindingFree` at `0x180264745`
- `RPCRT4!RpcBindingFree` at `0x180264745`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18026491c`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18026491c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18026480a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18026498d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18026480a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18026498d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802647e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18026483d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802647e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18026483d`

## pseudocode

```c
__int64 __fastcall AicGetTokenForMSI(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        void *a15,
        HANDLE *a16)
{
  unsigned int v16; // ebx
  unsigned int v17; // r14d
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  unsigned int v20; // r8d
  int v21; // esi
  signed int started; // edi
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v26; // [rsp+30h] [rbp-1C8h]
  __int64 v27; // [rsp+38h] [rbp-1C0h]
  __int64 v28; // [rsp+48h] [rbp-1B0h]
  __int64 v29; // [rsp+80h] [rbp-178h]
  __int64 v30; // [rsp+98h] [rbp-160h]
  RPC_BINDING_HANDLE Binding; // [rsp+C0h] [rbp-138h] BYREF
  int v33; // [rsp+C8h] [rbp-130h]
  __int64 v34; // [rsp+D0h] [rbp-128h]
  __int64 v35; // [rsp+D8h] [rbp-120h]
  __int64 v36; // [rsp+E0h] [rbp-118h]
  HANDLE hToken; // [rsp+E8h] [rbp-110h]
  __int64 v38; // [rsp+F0h] [rbp-108h]
  __int64 v39; // [rsp+F8h] [rbp-100h]
  __int64 v40; // [rsp+100h] [rbp-F8h]
  __int64 v41; // [rsp+108h] [rbp-F0h]
  __int64 v42; // [rsp+110h] [rbp-E8h]
  __int64 v43; // [rsp+118h] [rbp-E0h]
  __int64 v44; // [rsp+120h] [rbp-D8h]
  __int64 v45; // [rsp+128h] [rbp-D0h]
  HANDLE *v46; // [rsp+130h] [rbp-C8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+140h] [rbp-B8h] BYREF

  v34 = a4;
  v38 = a1;
  v42 = a1;
  v33 = a3;
  v43 = a4;
  v44 = a5;
  v45 = a6;
  v39 = a7;
  v35 = a8;
  v36 = a9;
  v40 = a11;
  v41 = a12;
  hToken = a15;
  v46 = a16;
  v16 = 0;
  Binding = 0;
  v17 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v21 = 0;
  *a16 = 0;
  if ( v34 && a5 && a6 && a7 && v35 && v36 )
  {
    if ( qword_1803148D8 )
      goto LABEL_23;
    started = AicpCreateBindingHandle(v19, v18, &Binding);
    if ( !started )
    {
      if ( _InterlockedCompareExchange64(&qword_1803148D8, (signed __int64)Binding, 0) )
      {
        RpcBindingFree(&Binding);
        Binding = 0;
      }
      goto LABEL_23;
    }
  }
  else
  {
    started = 87;
  }
  while ( 1 )
  {
    if ( v21 )
    {
      started = AicpAsyncFinishCall(&pAsync, v18, v20, started);
      v21 = 0;
    }
    AicpAsyncCloseHandle(&pAsync);
    if ( !started )
      return v16;
    if ( *a16 )
    {
      CloseHandle_0(*a16);
      *a16 = 0;
    }
    v23 = (unsigned int)(started - 1708);
    if ( (unsigned int)v23 > 0x2D )
      goto LABEL_27;
    v24 = 0x200000004201LL;
    if ( !_bittest64(&v24, v23) )
      goto LABEL_27;
    if ( v17 > 1 )
    {
      started = 1061;
LABEL_27:
      if ( started > 0 )
        return (unsigned __int16)started | 0x80070000;
      return (unsigned int)started;
    }
    ++v17;
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      started = AicpStartAIS();
      RevertToSelf();
      if ( !started )
      {
LABEL_23:
        started = AicpAsyncInitializeHandle(&pAsync, v18);
        if ( !started )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
            goto LABEL_21;
          LODWORD(v30) = -1;
          LODWORD(v29) = a10;
          LODWORD(v28) = a3;
          LODWORD(v27) = 0;
          LODWORD(v26) = 2;
          Ndr64AsyncClientCall(
            (MIDL_STUBLESS_PROXY_INFO *)&stru_180275260,
            0,
            0,
            &pAsync,
            qword_1803148D8,
            v38,
            v26,
            v27,
            L"Winsta0\\Default",
            v28,
            v34,
            a5,
            a6,
            v39,
            v35,
            v36,
            v29,
            v40,
            v41,
            v30,
            a16);
          v21 = started + 1;
          RevertToSelf();
        }
      }
    }
    else
    {
LABEL_21:
      started = GetLastError_0();
    }
  }
}

```

## disassembly

```asm
0x1802645bc  push    rbx
0x1802645be  push    rsi
0x1802645bf  push    rdi
0x1802645c0  push    r12
0x1802645c2  push    r13
0x1802645c4  push    r14
0x1802645c6  push    r15
0x1802645c8  sub     rsp, 1C0h
0x1802645cf  mov     rax, cs:__security_cookie
0x1802645d6  xor     rax, rsp
0x1802645d9  mov     [rsp+1F8h+var_48], rax
0x1802645e1  mov     rax, r9
0x1802645e4  mov     [rsp+1F8h+var_128], rax
0x1802645ec  mov     [rsp+1F8h+var_140], r8d
0x1802645f4  mov     [rsp+1F8h+var_108], rcx
0x1802645fc  mov     [rsp+1F8h+var_E8], rcx
0x180264604  mov     [rsp+1F8h+var_130], r8d
0x18026460c  mov     [rsp+1F8h+var_E0], rax
0x180264614  mov     r12, [rsp+1F8h+arg_20]
0x18026461c  mov     [rsp+1F8h+var_D8], r12
0x180264624  mov     r13, [rsp+1F8h+arg_28]
0x18026462c  mov     [rsp+1F8h+var_D0], r13
0x180264634  mov     rdi, [rsp+1F8h+arg_30]
0x18026463c  mov     [rsp+1F8h+var_100], rdi
0x180264644  mov     rax, [rsp+1F8h+arg_38]
0x18026464c  mov     [rsp+1F8h+var_120], rax
0x180264654  mov     rax, [rsp+1F8h+arg_40]
0x18026465c  mov     [rsp+1F8h+var_118], rax
0x180264664  mov     rax, [rsp+1F8h+arg_50]
0x18026466c  mov     [rsp+1F8h+var_F8], rax
0x180264674  mov     rax, [rsp+1F8h+arg_58]
0x18026467c  mov     [rsp+1F8h+var_F0], rax
0x180264684  mov     rax, [rsp+1F8h+arg_70]
0x18026468c  mov     [rsp+1F8h+hToken], rax
0x180264694  mov     r15, [rsp+1F8h+arg_78]
0x18026469c  mov     [rsp+1F8h+var_C8], r15
0x1802646a4  xor     ebx, ebx
0x1802646a6  mov     [rsp+1F8h+Binding], rbx
0x1802646ae  mov     r14d, ebx
0x1802646b1  mov     [rsp+1F8h+var_144], ebx
0x1802646b8  xor     edx, edx; Val
0x1802646ba  lea     r8d, [rbx+70h]; Size
0x1802646be  lea     rcx, [rsp+1F8h+pAsync]; void *
0x1802646c6  call    memset_0
0x1802646cb  mov     esi, ebx
0x1802646cd  mov     [rsp+1F8h+var_148], ebx
0x1802646d4  mov     [r15], rbx
0x1802646d7  cmp     [rsp+1F8h+var_128], rbx
0x1802646df  jz      short loc_18026475E
0x1802646e1  test    r12, r12
0x1802646e4  jz      short loc_18026475E
0x1802646e6  test    r13, r13
0x1802646e9  jz      short loc_18026475E
0x1802646eb  test    rdi, rdi
0x1802646ee  jz      short loc_18026475E
0x1802646f0  cmp     [rsp+1F8h+var_120], rbx
0x1802646f8  jz      short loc_18026475E
0x1802646fa  cmp     [rsp+1F8h+var_118], rbx
0x180264702  jz      short loc_18026475E
0x180264704  cmp     cs:qword_1803148D8, rbx
0x18026470b  jnz     loc_18026481E
0x180264711  lea     r8, [rsp+1F8h+Binding]; void **
0x180264719  call    ?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z; AicpCreateBindingHandle(ushort *,int,void * *)
0x18026471e  mov     edi, eax
0x180264720  test    eax, eax
0x180264722  jnz     short loc_180264763
0x180264724  mov     rcx, [rsp+1F8h+Binding]
0x18026472c  xor     eax, eax
0x18026472e  lock cmpxchg cs:qword_1803148D8, rcx
0x180264737  jz      loc_18026481E
0x18026473d  lea     rcx, [rsp+1F8h+Binding]; Binding
0x180264745  call    cs:__imp_RpcBindingFree
0x18026474c  nop     dword ptr [rax+rax+00h]
0x180264751  mov     [rsp+1F8h+Binding], rbx
0x180264759  jmp     loc_18026481E
0x18026475e  mov     edi, 57h ; 'W'
0x180264763  test    esi, esi
0x180264765  jz      short loc_180264782
0x180264767  mov     r9d, edi; unsigned int
0x18026476a  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x180264772  call    ?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z; AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)
0x180264777  mov     edi, eax
0x180264779  mov     esi, ebx
0x18026477b  mov     [rsp+1F8h+var_148], ebx
0x180264782  lea     rcx, [rsp+1F8h+pAsync]; struct _RPC_ASYNC_STATE *
0x18026478a  call    ?AicpAsyncCloseHandle@@YAXPEAU_RPC_ASYNC_STATE@@@Z; AicpAsyncCloseHandle(_RPC_ASYNC_STATE *)
0x18026478f  test    edi, edi
0x180264791  jz      loc_1802649B4
0x180264797  cmp     [r15], rbx
0x18026479a  jz      short loc_1802647A7
0x18026479c  mov     rcx, [r15]; hObject
0x18026479f  call    CloseHandle_0
0x1802647a4  mov     [r15], rbx
0x1802647a7  lea     eax, [rdi-6ACh]
0x1802647ad  cmp     eax, 2Dh ; '-'
0x1802647b0  ja      loc_1802649A3
0x1802647b6  mov     rcx, 200000004201h
0x1802647c0  bt      rcx, rax
0x1802647c4  jnb     loc_1802649A3
0x1802647ca  cmp     r14d, 1
0x1802647ce  ja      loc_18026499E
0x1802647d4  inc     r14d
0x1802647d7  mov     [rsp+1F8h+var_144], r14d
0x1802647df  mov     rcx, [rsp+1F8h+hToken]; hToken
0x1802647e7  call    cs:__imp_ImpersonateLoggedOnUser
0x1802647ee  nop     dword ptr [rax+rax+00h]
0x1802647f3  test    eax, eax
0x1802647f5  jnz     short loc_180264803
0x1802647f7  call    GetLastError_0
0x1802647fc  mov     edi, eax
0x1802647fe  jmp     loc_180264763
0x180264803  call    ?AicpStartAIS@@YAKK@Z; AicpStartAIS(ulong)
0x180264808  mov     edi, eax
0x18026480a  call    cs:__imp_RevertToSelf
0x180264811  nop     dword ptr [rax+rax+00h]
0x180264816  test    edi, edi
0x180264818  jnz     loc_180264763
0x18026481e  lea     rcx, [rsp+1F8h+pAsync]; struct _RPC_ASYNC_STATE *
0x180264826  call    ?AicpAsyncInitializeHandle@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; AicpAsyncInitializeHandle(_RPC_ASYNC_STATE *,ulong)
0x18026482b  mov     edi, eax
0x18026482d  test    eax, eax
0x18026482f  jnz     loc_180264763
0x180264835  mov     rcx, [rsp+1F8h+hToken]; hToken
0x18026483d  call    cs:__imp_ImpersonateLoggedOnUser
0x180264844  nop     dword ptr [rax+rax+00h]
0x180264849  test    eax, eax
0x18026484b  jz      short loc_1802647F7
0x18026484d  mov     [rsp+1F8h+var_158], r15
0x180264855  mov     dword ptr [rsp+1F8h+var_160], 0FFFFFFFFh
0x180264860  mov     rax, [rsp+1F8h+var_F0]
0x180264868  mov     [rsp+1F8h+var_168], rax
0x180264870  mov     rax, [rsp+1F8h+var_F8]
0x180264878  mov     [rsp+1F8h+var_170], rax
0x180264880  mov     eax, [rsp+1F8h+arg_48]
0x180264887  mov     dword ptr [rsp+1F8h+var_178], eax
0x18026488e  mov     rax, [rsp+1F8h+var_118]
0x180264896  mov     [rsp+1F8h+var_180], rax
0x18026489b  mov     rax, [rsp+1F8h+var_120]
0x1802648a3  mov     [rsp+1F8h+var_188], rax
0x1802648a8  mov     rax, [rsp+1F8h+var_100]
0x1802648b0  mov     [rsp+1F8h+var_190], rax
0x1802648b5  mov     [rsp+1F8h+var_198], r13
0x1802648ba  mov     [rsp+1F8h+var_1A0], r12
0x1802648bf  mov     rax, [rsp+1F8h+var_128]
0x1802648c7  mov     [rsp+1F8h+var_1A8], rax
0x1802648cc  mov     eax, [rsp+1F8h+var_140]
0x1802648d3  mov     dword ptr [rsp+1F8h+var_1B0], eax
0x1802648d7  lea     rax, aWinsta0Default_0; "Winsta0\\Default"
0x1802648de  mov     [rsp+1F8h+var_1B8], rax
0x1802648e3  mov     dword ptr [rsp+1F8h+var_1C0], ebx
0x1802648e7  mov     dword ptr [rsp+1F8h+var_1C8], 2
0x1802648ef  mov     rax, [rsp+1F8h+var_108]
0x1802648f7  mov     [rsp+1F8h+var_1D0], rax
0x1802648fc  mov     rax, cs:qword_1803148D8
0x180264903  mov     [rsp+1F8h+var_1D8], rax
0x180264908  lea     r9, [rsp+1F8h+pAsync]
0x180264910  xor     r8d, r8d; pReturnValue
0x180264913  xor     edx, edx; nProcNum
0x180264915  lea     rcx, stru_180275260; pProxyInfo
0x18026491c  call    cs:__imp_Ndr64AsyncClientCall
0x180264923  nop     dword ptr [rax+rax+00h]
0x180264928  lea     esi, [rdi+1]
0x18026492b  mov     [rsp+1F8h+var_148], esi
0x180264932  jmp     short loc_18026498D
0x180264934  mov     edi, eax
0x180264936  xor     ebx, ebx
0x180264938  mov     r14d, [rsp+1F8h+var_144]
0x180264940  mov     esi, [rsp+1F8h+var_148]
0x180264947  mov     rax, [rsp+1F8h+var_E8]
0x18026494f  mov     [rsp+1F8h+var_108], rax
0x180264957  mov     eax, [rsp+1F8h+var_130]
0x18026495e  mov     [rsp+1F8h+var_140], eax
0x180264965  mov     rax, [rsp+1F8h+var_E0]
0x18026496d  mov     [rsp+1F8h+var_128], rax
0x180264975  mov     r12, [rsp+1F8h+var_D8]
0x18026497d  mov     r13, [rsp+1F8h+var_D0]
0x180264985  mov     r15, [rsp+1F8h+var_C8]
0x18026498d  call    cs:__imp_RevertToSelf
0x180264994  nop     dword ptr [rax+rax+00h]
0x180264999  jmp     loc_180264763
0x18026499e  mov     edi, 425h
0x1802649a3  test    edi, edi
0x1802649a5  jz      short loc_1802649B4
0x1802649a7  jle     short loc_1802649B2
0x1802649a9  movzx   edi, di
0x1802649ac  or      edi, 80070000h
0x1802649b2  mov     ebx, edi
0x1802649b4  mov     eax, ebx
0x1802649b6  mov     rcx, [rsp+1F8h+var_48]
0x1802649be  xor     rcx, rsp; StackCookie
0x1802649c1  call    __security_check_cookie
0x1802649c6  add     rsp, 1C0h
0x1802649cd  pop     r15
0x1802649cf  pop     r14
0x1802649d1  pop     r13
0x1802649d3  pop     r12
0x1802649d5  pop     rdi
0x1802649d6  pop     rsi
0x1802649d7  pop     rbx
0x1802649d8  retn
0x180265ab9  push    rbp
0x180265abb  sub     rsp, 0B0h
0x180265ac2  mov     rbp, rdx
0x180265ac5  mov     rcx, [rcx]
0x180265ac8  mov     ecx, [rcx]; ExceptionCode
0x180265aca  call    cs:__imp_I_RpcExceptionFilter
0x180265ad1  nop     dword ptr [rax+rax+00h]
0x180265ad6  nop
0x180265ad7  add     rsp, 0B0h
0x180265ade  pop     rbp
0x180265adf  retn
```
