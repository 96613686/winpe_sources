# CQueryCallback::Create(_PROVIDER_QUERY_TYPE,ushort const *,ushort const *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ushort const *,ulong,void *,void *,CQueryCallback * *)

- ea: `0x140016d70`
- end: `0x140016fde`
- name: `?Create@CQueryCallback@@SAJW4_PROVIDER_QUERY_TYPE@@PEBG1KPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@1KPEAX4PEAPEAV1@@Z`
- size: `622`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *Src, __int64, __int64, void *, int, void *, void *, RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400160d8`

## callees

- `0x14000190c`
- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x140016d70`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140016f74`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140016f74`

## pseudocode

```c
__int64 __fastcall CQueryCallback::Create(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void *Src,
        __int64 a6,
        __int64 a7,
        void *a8,
        int a9,
        void *a10,
        void *a11,
        RTL_SRWLOCK **a12)
{
  __int64 v12; // r13
  unsigned __int16 *v15; // r15
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  unsigned int v19; // edi
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rax
  unsigned __int64 v22; // rdi
  unsigned __int16 *v23; // rax
  unsigned __int64 v24; // rdi
  unsigned __int16 *v25; // rax
  _QWORD *v26; // r12
  _QWORD *v27; // rax
  unsigned int i; // ecx
  RTL_SRWLOCK *v29; // r14
  unsigned __int16 *v32; // [rsp+60h] [rbp+18h]
  unsigned __int16 *v33; // [rsp+80h] [rbp+38h]
  void *v34; // [rsp+88h] [rbp+40h]

  v12 = a4;
  v15 = 0;
  v32 = 0;
  v16 = 0;
  v33 = 0;
  if ( a10 && a2 && a12 )
  {
    v17 = 0x7FFFFFFF;
    v18 = a2;
    while ( *v18 )
    {
      ++v18;
      if ( !--v17 )
        goto LABEL_7;
    }
    v22 = 2 * (0x80000000LL - v17);
    v23 = (unsigned __int16 *)DAF_user_alloc(v22);
    v15 = v23;
    v32 = v23;
    if ( v23 )
      v19 = StringCbCopyW(v23, v22, a2);
    else
      v19 = -2147024882;
  }
  else
  {
LABEL_7:
    v19 = -2147024809;
  }
  if ( a3 )
  {
    if ( v19 )
    {
LABEL_29:
      if ( v15 )
        MIDL_user_free(v15);
      if ( v16 )
        MIDL_user_free(v16);
      return v19;
    }
    v20 = 184;
    v21 = a3;
    while ( *v21 )
    {
      ++v21;
      if ( !--v20 )
      {
        v19 = -2147024809;
        goto LABEL_29;
      }
    }
    v24 = 2 * (185 - v20);
    v25 = (unsigned __int16 *)DAF_user_alloc(v24);
    v16 = v25;
    v33 = v25;
    if ( !v25 )
      goto LABEL_22;
    v19 = StringCbCopyW(v25, v24, a3);
  }
  if ( v19 )
    goto LABEL_29;
  v26 = 0;
  v34 = 0;
  if ( (_DWORD)v12 )
  {
    v27 = (_QWORD *)DAF_user_alloc(32 * v12);
    v26 = v27;
    v34 = v27;
    if ( !v27 )
    {
LABEL_22:
      v19 = -2147024882;
      goto LABEL_29;
    }
    memcpy_0(v27, Src, 32 * v12);
    for ( i = 0; i < (unsigned int)v12; ++i )
      v26[4 * i + 3] = 0;
  }
  try
  {
    v29 = (RTL_SRWLOCK *)operator new(0x78u);
    v29->Ptr = &CQueryCallback::`vftable'{for `IAepQueryCallback'};
    v29[1].Ptr = &CQueryCallback::`vftable'{for `IFederatedAepStoreQueryCallback'};
    v29[2].Ptr = &CQueryCallback::`vftable'{for `IAepServiceQueryCallback'};
    v29[3].Ptr = &CQueryCallback::`vftable'{for `IDafPrivImpersonationToken'};
    v29[4].Ptr = &CQueryCallback::`vftable'{for `IServiceProvider'};
    LODWORD(v29[5].Ptr) = 1;
    HIDWORD(v29[5].Ptr) = a1;
    v29[6].Ptr = a10;
    v29[7].Ptr = v15;
    v29[8].Ptr = v16;
    LODWORD(v29[9].Ptr) = v12;
    v29[10].Ptr = v26;
    HIDWORD(v29[11].Ptr) = a9;
    v29[13].Ptr = (PVOID)1;
    v29[14].Ptr = a11;
    InitializeSRWLock(v29 + 12);
    *a12 = v29;
  }
  catch ( std::bad_alloc )
  {
    if ( v34 )
      MIDL_user_free(v34);
    v16 = v33;
    v15 = v32;
    v19 = -2147024882;
    goto LABEL_29;
  }
  v29 = (RTL_SRWLOCK *)operator new(0x78u);
}

```

## disassembly

```asm
0x140016d70  mov     [rsp+arg_8], rbx
0x140016d75  mov     [rsp+arg_18], rsi
0x140016d7a  mov     [rsp+arg_0], ecx
0x140016d7e  push    rdi
0x140016d7f  push    r12
0x140016d81  push    r13
0x140016d83  push    r14
0x140016d85  push    r15
0x140016d87  sub     rsp, 20h
0x140016d8b  mov     r13d, r9d
0x140016d8e  mov     r12, r8
0x140016d91  mov     r14, rdx
0x140016d94  xor     ebx, ebx
0x140016d96  mov     r15d, ebx
0x140016d99  mov     [rsp+48h+arg_10], rbx
0x140016d9e  mov     esi, ebx
0x140016da0  mov     [rsp+48h+arg_30], rbx
0x140016da8  cmp     [rsp+48h+arg_48], rbx
0x140016db0  jz      short loc_140016DD8
0x140016db2  test    rdx, rdx
0x140016db5  jz      short loc_140016DD8
0x140016db7  cmp     [rsp+48h+arg_58], rbx
0x140016dbf  jz      short loc_140016DD8
0x140016dc1  mov     ecx, 7FFFFFFFh
0x140016dc6  mov     rax, rdx
0x140016dc9  cmp     [rax], bx
0x140016dcc  jz      short loc_140016E0F
0x140016dce  add     rax, 2
0x140016dd2  sub     rcx, 1
0x140016dd6  jnz     short loc_140016DC9
0x140016dd8  mov     edi, 80070057h
0x140016ddd  test    r12, r12
0x140016de0  jz      loc_140016E7B
0x140016de6  test    edi, edi
0x140016de8  jnz     loc_140016FAA
0x140016dee  mov     ecx, 0B8h
0x140016df3  mov     rax, r12
0x140016df6  cmp     [rax], bx
0x140016df9  jz      short loc_140016E48
0x140016dfb  add     rax, 2
0x140016dff  sub     rcx, 1
0x140016e03  jnz     short loc_140016DF6
0x140016e05  mov     edi, 80070057h
0x140016e0a  jmp     loc_140016FAA
0x140016e0f  mov     edi, 80000000h
0x140016e14  sub     rdi, rcx
0x140016e17  add     rdi, rdi
0x140016e1a  mov     rcx, rdi
0x140016e1d  call    DAF_user_alloc
0x140016e22  mov     r15, rax
0x140016e25  mov     [rsp+48h+arg_10], rax
0x140016e2a  test    rax, rax
0x140016e2d  jnz     short loc_140016E36
0x140016e2f  mov     edi, 8007000Eh
0x140016e34  jmp     short loc_140016DDD
0x140016e36  mov     r8, r14; unsigned __int16 *
0x140016e39  mov     rdx, rdi; unsigned __int64
0x140016e3c  mov     rcx, rax; unsigned __int16 *
0x140016e3f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140016e44  mov     edi, eax
0x140016e46  jmp     short loc_140016DDD
0x140016e48  mov     edi, 0B9h
0x140016e4d  sub     rdi, rcx
0x140016e50  add     rdi, rdi
0x140016e53  mov     rcx, rdi
0x140016e56  call    DAF_user_alloc
0x140016e5b  mov     rsi, rax
0x140016e5e  mov     [rsp+48h+arg_30], rax
0x140016e66  test    rax, rax
0x140016e69  jz      short loc_140016EB2
0x140016e6b  mov     r8, r12; unsigned __int16 *
0x140016e6e  mov     rdx, rdi; unsigned __int64
0x140016e71  mov     rcx, rax; unsigned __int16 *
0x140016e74  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140016e79  mov     edi, eax
0x140016e7b  test    edi, edi
0x140016e7d  jnz     loc_140016FAA
0x140016e83  mov     r12, rbx
0x140016e86  mov     [rsp+48h+arg_38], rbx
0x140016e8e  test    r13d, r13d
0x140016e91  jz      short loc_140016EE2
0x140016e93  mov     r14, r13
0x140016e96  shl     r14, 5
0x140016e9a  mov     rcx, r14
0x140016e9d  call    DAF_user_alloc
0x140016ea2  mov     r12, rax
0x140016ea5  mov     [rsp+48h+arg_38], rax
0x140016ead  test    rax, rax
0x140016eb0  jnz     short loc_140016EBC
0x140016eb2  mov     edi, 8007000Eh
0x140016eb7  jmp     loc_140016FAA
0x140016ebc  mov     r8, r14; Size
0x140016ebf  mov     rdx, [rsp+48h+Src]; Src
0x140016ec4  mov     rcx, r12; void *
0x140016ec7  call    memcpy_0
0x140016ecc  mov     ecx, ebx
0x140016ece  cmp     ecx, r13d
0x140016ed1  jnb     short loc_140016EE2
0x140016ed3  mov     eax, ecx
0x140016ed5  shl     rax, 5
0x140016ed9  mov     [rax+r12+18h], rbx
0x140016ede  inc     ecx
0x140016ee0  jmp     short loc_140016ECE
0x140016ee2  mov     ecx, 78h ; 'x'; Size
0x140016ee7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016eec  mov     r14, rax
0x140016eef  lea     rax, ??_7CQueryCallback@@6BIAepQueryCallback@@@; const CQueryCallback::`vftable'{for `IAepQueryCallback'}
0x140016ef6  mov     [r14], rax
0x140016ef9  lea     rax, ??_7CQueryCallback@@6BIFederatedAepStoreQueryCallback@@@; const CQueryCallback::`vftable'{for `IFederatedAepStoreQueryCallback'}
0x140016f00  mov     [r14+8], rax
0x140016f04  lea     rax, ??_7CQueryCallback@@6BIAepServiceQueryCallback@@@; const CQueryCallback::`vftable'{for `IAepServiceQueryCallback'}
0x140016f0b  mov     [r14+10h], rax
0x140016f0f  lea     rax, ??_7CQueryCallback@@6BIDafPrivImpersonationToken@@@; const CQueryCallback::`vftable'{for `IDafPrivImpersonationToken'}
0x140016f16  mov     [r14+18h], rax
0x140016f1a  lea     rax, ??_7CQueryCallback@@6BIServiceProvider@@@; const CQueryCallback::`vftable'{for `IServiceProvider'}
0x140016f21  mov     [r14+20h], rax
0x140016f25  mov     dword ptr [r14+28h], 1
0x140016f2d  mov     eax, [rsp+48h+arg_0]
0x140016f31  mov     [r14+2Ch], eax
0x140016f35  mov     rax, [rsp+48h+arg_48]
0x140016f3d  mov     [r14+30h], rax
0x140016f41  mov     [r14+38h], r15
0x140016f45  mov     [r14+40h], rsi
0x140016f49  mov     [r14+48h], r13d
0x140016f4d  mov     [r14+50h], r12
0x140016f51  mov     eax, [rsp+48h+arg_40]
0x140016f58  mov     [r14+5Ch], eax
0x140016f5c  mov     qword ptr [r14+68h], 1
0x140016f64  mov     rax, [rsp+48h+arg_50]
0x140016f6c  mov     [r14+70h], rax
0x140016f70  lea     rcx, [r14+60h]; SRWLock
0x140016f74  call    cs:__imp_InitializeSRWLock
0x140016f7a  mov     rax, [rsp+48h+arg_58]
0x140016f82  mov     [rax], r14
0x140016f85  jmp     short loc_140016FC4
0x140016f87  mov     rcx, [rsp+48h+arg_38]; void *
0x140016f8f  test    rcx, rcx
0x140016f92  jz      short loc_140016F99
0x140016f94  call    MIDL_user_free
0x140016f99  mov     rsi, [rsp+48h+arg_30]
0x140016fa1  mov     r15, [rsp+48h+arg_10]
0x140016fa6  mov     edi, [rsp+48h+arg_28]
0x140016faa  test    r15, r15
0x140016fad  jz      short loc_140016FB7
0x140016faf  mov     rcx, r15; void *
0x140016fb2  call    MIDL_user_free
0x140016fb7  test    rsi, rsi
0x140016fba  jz      short loc_140016FC4
0x140016fbc  mov     rcx, rsi; void *
0x140016fbf  call    MIDL_user_free
0x140016fc4  mov     eax, edi
0x140016fc6  mov     rbx, [rsp+48h+arg_8]
0x140016fcb  mov     rsi, [rsp+48h+arg_18]
0x140016fd0  add     rsp, 20h
0x140016fd4  pop     r15
0x140016fd6  pop     r14
0x140016fd8  pop     r13
0x140016fda  pop     r12
0x140016fdc  pop     rdi
0x140016fdd  retn
```
