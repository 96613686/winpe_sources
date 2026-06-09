# AicGetTokenForMSI(HWND__ *,ushort const *,_MSI_ACTION,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,ulong,int,void *,void * *)

- ea: `0x180259fb0`
- end: `0x18025a3a9`
- name: `?AicGetTokenForMSI@@YAJPEAUHWND__@@PEBGW4_MSI_ACTION@@111111KPEAPEBG3KHPEAXPEAPEAX@Z`
- size: `1017`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180142ba8`

## callees

- `0x1801701a6`
- `0x1801701b2`
- `0x180259fb0`
- `0x18025a3b0`
- `0x18025a3dc`
- `0x18025a468`
- `0x18025a4c0`
- `0x18025a61c`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18025b394`
- `RPCRT4!I_RpcExceptionFilter` at `0x18025b394`
- `RPCRT4!RpcBindingFree` at `0x18025a139`
- `RPCRT4!RpcBindingFree` at `0x18025a139`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18025a2f8`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18025a2f8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025a1f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025a363`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025a1f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025a363`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025a1d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025a21f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025a1d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025a21f`

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
    if ( qword_18030A908 )
      goto LABEL_23;
    started = AicpCreateBindingHandle(v19, v18, &Binding);
    if ( !started )
    {
      if ( _InterlockedCompareExchange64(&qword_18030A908, (signed __int64)Binding, 0) )
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
            (MIDL_STUBLESS_PROXY_INFO *)&stru_18026B250,
            0,
            0,
            &pAsync,
            qword_18030A908,
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
0x180259fb0  push    rbx
0x180259fb2  push    rsi
0x180259fb3  push    rdi
0x180259fb4  push    r12
0x180259fb6  push    r13
0x180259fb8  push    r14
0x180259fba  push    r15
0x180259fbc  sub     rsp, 1C0h
0x180259fc3  mov     rax, cs:__security_cookie
0x180259fca  xor     rax, rsp
0x180259fcd  mov     [rsp+1F8h+var_48], rax
0x180259fd5  mov     rax, r9
0x180259fd8  mov     [rsp+1F8h+var_128], rax
0x180259fe0  mov     [rsp+1F8h+var_140], r8d
0x180259fe8  mov     [rsp+1F8h+var_108], rcx
0x180259ff0  mov     [rsp+1F8h+var_E8], rcx
0x180259ff8  mov     [rsp+1F8h+var_130], r8d
0x18025a000  mov     [rsp+1F8h+var_E0], rax
0x18025a008  mov     r12, [rsp+1F8h+arg_20]
0x18025a010  mov     [rsp+1F8h+var_D8], r12
0x18025a018  mov     r13, [rsp+1F8h+arg_28]
0x18025a020  mov     [rsp+1F8h+var_D0], r13
0x18025a028  mov     rdi, [rsp+1F8h+arg_30]
0x18025a030  mov     [rsp+1F8h+var_100], rdi
0x18025a038  mov     rax, [rsp+1F8h+arg_38]
0x18025a040  mov     [rsp+1F8h+var_120], rax
0x18025a048  mov     rax, [rsp+1F8h+arg_40]
0x18025a050  mov     [rsp+1F8h+var_118], rax
0x18025a058  mov     rax, [rsp+1F8h+arg_50]
0x18025a060  mov     [rsp+1F8h+var_F8], rax
0x18025a068  mov     rax, [rsp+1F8h+arg_58]
0x18025a070  mov     [rsp+1F8h+var_F0], rax
0x18025a078  mov     rax, [rsp+1F8h+arg_70]
0x18025a080  mov     [rsp+1F8h+hToken], rax
0x18025a088  mov     r15, [rsp+1F8h+arg_78]
0x18025a090  mov     [rsp+1F8h+var_C8], r15
0x18025a098  xor     ebx, ebx
0x18025a09a  mov     [rsp+1F8h+Binding], rbx
0x18025a0a2  mov     r14d, ebx
0x18025a0a5  mov     [rsp+1F8h+var_144], ebx
0x18025a0ac  xor     edx, edx; Val
0x18025a0ae  lea     r8d, [rbx+70h]; Size
0x18025a0b2  lea     rcx, [rsp+1F8h+pAsync]; void *
0x18025a0ba  call    memset_0
0x18025a0bf  mov     esi, ebx
0x18025a0c1  mov     [rsp+1F8h+var_148], ebx
0x18025a0c8  mov     [r15], rbx
0x18025a0cb  cmp     [rsp+1F8h+var_128], rbx
0x18025a0d3  jz      short loc_18025A14C
0x18025a0d5  test    r12, r12
0x18025a0d8  jz      short loc_18025A14C
0x18025a0da  test    r13, r13
0x18025a0dd  jz      short loc_18025A14C
0x18025a0df  test    rdi, rdi
0x18025a0e2  jz      short loc_18025A14C
0x18025a0e4  cmp     [rsp+1F8h+var_120], rbx
0x18025a0ec  jz      short loc_18025A14C
0x18025a0ee  cmp     [rsp+1F8h+var_118], rbx
0x18025a0f6  jz      short loc_18025A14C
0x18025a0f8  cmp     cs:qword_18030A908, rbx
0x18025a0ff  jnz     loc_18025A200
0x18025a105  lea     r8, [rsp+1F8h+Binding]; void **
0x18025a10d  call    ?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z; AicpCreateBindingHandle(ushort *,int,void * *)
0x18025a112  mov     edi, eax
0x18025a114  test    eax, eax
0x18025a116  jnz     short loc_18025A151
0x18025a118  mov     rcx, [rsp+1F8h+Binding]
0x18025a120  xor     eax, eax
0x18025a122  lock cmpxchg cs:qword_18030A908, rcx
0x18025a12b  jz      loc_18025A200
0x18025a131  lea     rcx, [rsp+1F8h+Binding]; Binding
0x18025a139  call    cs:__imp_RpcBindingFree
0x18025a13f  mov     [rsp+1F8h+Binding], rbx
0x18025a147  jmp     loc_18025A200
0x18025a14c  mov     edi, 57h ; 'W'
0x18025a151  test    esi, esi
0x18025a153  jz      short loc_18025A170
0x18025a155  mov     r9d, edi; unsigned int
0x18025a158  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x18025a160  call    ?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z; AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)
0x18025a165  mov     edi, eax
0x18025a167  mov     esi, ebx
0x18025a169  mov     [rsp+1F8h+var_148], ebx
0x18025a170  lea     rcx, [rsp+1F8h+pAsync]; struct _RPC_ASYNC_STATE *
0x18025a178  call    ?AicpAsyncCloseHandle@@YAXPEAU_RPC_ASYNC_STATE@@@Z; AicpAsyncCloseHandle(_RPC_ASYNC_STATE *)
0x18025a17d  test    edi, edi
0x18025a17f  jz      loc_18025A384
0x18025a185  cmp     [r15], rbx
0x18025a188  jz      short loc_18025A195
0x18025a18a  mov     rcx, [r15]; hObject
0x18025a18d  call    CloseHandle_0
0x18025a192  mov     [r15], rbx
0x18025a195  lea     eax, [rdi-6ACh]
0x18025a19b  cmp     eax, 2Dh ; '-'
0x18025a19e  ja      loc_18025A373
0x18025a1a4  mov     rcx, 200000004201h
0x18025a1ae  bt      rcx, rax
0x18025a1b2  jnb     loc_18025A373
0x18025a1b8  cmp     r14d, 1
0x18025a1bc  ja      loc_18025A36E
0x18025a1c2  inc     r14d
0x18025a1c5  mov     [rsp+1F8h+var_144], r14d
0x18025a1cd  mov     rcx, [rsp+1F8h+hToken]; hToken
0x18025a1d5  call    cs:__imp_ImpersonateLoggedOnUser
0x18025a1db  test    eax, eax
0x18025a1dd  jnz     short loc_18025A1EB
0x18025a1df  call    GetLastError_0
0x18025a1e4  mov     edi, eax
0x18025a1e6  jmp     loc_18025A151
0x18025a1eb  call    ?AicpStartAIS@@YAKK@Z; AicpStartAIS(ulong)
0x18025a1f0  mov     edi, eax
0x18025a1f2  call    cs:__imp_RevertToSelf
0x18025a1f8  test    edi, edi
0x18025a1fa  jnz     loc_18025A151
0x18025a200  lea     rcx, [rsp+1F8h+pAsync]; struct _RPC_ASYNC_STATE *
0x18025a208  call    ?AicpAsyncInitializeHandle@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; AicpAsyncInitializeHandle(_RPC_ASYNC_STATE *,ulong)
0x18025a20d  mov     edi, eax
0x18025a20f  test    eax, eax
0x18025a211  jnz     loc_18025A151
0x18025a217  mov     rcx, [rsp+1F8h+hToken]; hToken
0x18025a21f  call    cs:__imp_ImpersonateLoggedOnUser
0x18025a225  test    eax, eax
0x18025a227  jz      short loc_18025A1DF
0x18025a229  mov     [rsp+1F8h+var_158], r15
0x18025a231  mov     dword ptr [rsp+1F8h+var_160], 0FFFFFFFFh
0x18025a23c  mov     rax, [rsp+1F8h+var_F0]
0x18025a244  mov     [rsp+1F8h+var_168], rax
0x18025a24c  mov     rax, [rsp+1F8h+var_F8]
0x18025a254  mov     [rsp+1F8h+var_170], rax
0x18025a25c  mov     eax, [rsp+1F8h+arg_48]
0x18025a263  mov     dword ptr [rsp+1F8h+var_178], eax
0x18025a26a  mov     rax, [rsp+1F8h+var_118]
0x18025a272  mov     [rsp+1F8h+var_180], rax
0x18025a277  mov     rax, [rsp+1F8h+var_120]
0x18025a27f  mov     [rsp+1F8h+var_188], rax
0x18025a284  mov     rax, [rsp+1F8h+var_100]
0x18025a28c  mov     [rsp+1F8h+var_190], rax
0x18025a291  mov     [rsp+1F8h+var_198], r13
0x18025a296  mov     [rsp+1F8h+var_1A0], r12
0x18025a29b  mov     rax, [rsp+1F8h+var_128]
0x18025a2a3  mov     [rsp+1F8h+var_1A8], rax
0x18025a2a8  mov     eax, [rsp+1F8h+var_140]
0x18025a2af  mov     dword ptr [rsp+1F8h+var_1B0], eax
0x18025a2b3  lea     rax, aWinsta0Default_0; "Winsta0\\Default"
0x18025a2ba  mov     [rsp+1F8h+var_1B8], rax
0x18025a2bf  mov     dword ptr [rsp+1F8h+var_1C0], ebx
0x18025a2c3  mov     dword ptr [rsp+1F8h+var_1C8], 2
0x18025a2cb  mov     rax, [rsp+1F8h+var_108]
0x18025a2d3  mov     [rsp+1F8h+var_1D0], rax
0x18025a2d8  mov     rax, cs:qword_18030A908
0x18025a2df  mov     [rsp+1F8h+var_1D8], rax
0x18025a2e4  lea     r9, [rsp+1F8h+pAsync]
0x18025a2ec  xor     r8d, r8d; pReturnValue
0x18025a2ef  xor     edx, edx; nProcNum
0x18025a2f1  lea     rcx, stru_18026B250; pProxyInfo
0x18025a2f8  call    cs:__imp_Ndr64AsyncClientCall
0x18025a2fe  lea     esi, [rdi+1]
0x18025a301  mov     [rsp+1F8h+var_148], esi
0x18025a308  jmp     short loc_18025A363
0x18025a30a  mov     edi, eax
0x18025a30c  xor     ebx, ebx
0x18025a30e  mov     r14d, [rsp+1F8h+var_144]
0x18025a316  mov     esi, [rsp+1F8h+var_148]
0x18025a31d  mov     rax, [rsp+1F8h+var_E8]
0x18025a325  mov     [rsp+1F8h+var_108], rax
0x18025a32d  mov     eax, [rsp+1F8h+var_130]
0x18025a334  mov     [rsp+1F8h+var_140], eax
0x18025a33b  mov     rax, [rsp+1F8h+var_E0]
0x18025a343  mov     [rsp+1F8h+var_128], rax
0x18025a34b  mov     r12, [rsp+1F8h+var_D8]
0x18025a353  mov     r13, [rsp+1F8h+var_D0]
0x18025a35b  mov     r15, [rsp+1F8h+var_C8]
0x18025a363  call    cs:__imp_RevertToSelf
0x18025a369  jmp     loc_18025A151
0x18025a36e  mov     edi, 425h
0x18025a373  test    edi, edi
0x18025a375  jz      short loc_18025A384
0x18025a377  jle     short loc_18025A382
0x18025a379  movzx   edi, di
0x18025a37c  or      edi, 80070000h
0x18025a382  mov     ebx, edi
0x18025a384  mov     eax, ebx
0x18025a386  mov     rcx, [rsp+1F8h+var_48]
0x18025a38e  xor     rcx, rsp; StackCookie
0x18025a391  call    __security_check_cookie
0x18025a396  add     rsp, 1C0h
0x18025a39d  pop     r15
0x18025a39f  pop     r14
0x18025a3a1  pop     r13
0x18025a3a3  pop     r12
0x18025a3a5  pop     rdi
0x18025a3a6  pop     rsi
0x18025a3a7  pop     rbx
0x18025a3a8  retn
0x18025b383  push    rbp
0x18025b385  sub     rsp, 0B0h
0x18025b38c  mov     rbp, rdx
0x18025b38f  mov     rcx, [rcx]
0x18025b392  mov     ecx, [rcx]; ExceptionCode
0x18025b394  call    cs:__imp_I_RpcExceptionFilter
0x18025b39a  nop
0x18025b39b  add     rsp, 0B0h
0x18025b3a2  pop     rbp
0x18025b3a3  retn
```
