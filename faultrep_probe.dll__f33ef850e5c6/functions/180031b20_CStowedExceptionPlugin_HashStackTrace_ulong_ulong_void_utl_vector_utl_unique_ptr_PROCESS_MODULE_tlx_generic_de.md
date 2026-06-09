# CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)

- ea: `0x180031b20`
- end: `0x180031d45`
- name: `?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z`
- size: `549`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031d50`

## callees

- `0x180002890`
- `0x180031850`
- `0x180031b20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031c62`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031c62`
- `bcrypt!BCryptDestroyHash` at `0x180031d06`
- `bcrypt!BCryptDestroyHash` at `0x180031d06`
- `bcrypt!BCryptHashData` at `0x180031c82`
- `bcrypt!BCryptHashData` at `0x180031cb4`
- `bcrypt!BCryptHashData` at `0x180031c82`
- `bcrypt!BCryptHashData` at `0x180031cb4`
- `bcrypt!BCryptCreateHash` at `0x180031b96`
- `bcrypt!BCryptCreateHash` at `0x180031b96`
- `bcrypt!BCryptFinishHash` at `0x180031cf1`
- `bcrypt!BCryptFinishHash` at `0x180031cf1`

## pseudocode

```c
__int64 __fastcall CStowedExceptionPlugin::HashStackTrace(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 *v5; // rdi
  __int64 v6; // rsi
  unsigned int *v8; // rbx
  _QWORD *v9; // r15
  unsigned int v10; // r14d
  unsigned __int64 v11; // r8
  __int64 i; // rax
  unsigned int v13; // ebx
  __int64 k; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 j; // rax
  UCHAR pbInput[8]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h]
  unsigned int *v23; // [rsp+58h] [rbp-28h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+70h] [rbp-10h]

  v22 = a3;
  v5 = a4;
  v23 = a1;
  v6 = a3;
  *a1 = 0;
  v8 = a1;
  v25 = 0;
  *(_QWORD *)pbInput = 0;
  *(_OWORD *)phHash = 0;
  v9 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  v10 = 0;
  if ( a2 )
  {
    do
    {
      v11 = *(_QWORD *)(v6 + 8LL * v10);
      for ( i = *v5; i != v5[1]; i += 8 )
      {
        if ( **(_QWORD **)i <= v11 && v11 < **(_QWORD **)i + (unsigned __int64)*(unsigned int *)(*(_QWORD *)i + 8LL) )
        {
          v9 = *(_QWORD **)i;
          v13 = 0;
LABEL_18:
          v16 = v9[3];
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)(v16 + 2 * v17) );
          for ( j = v17; j; --j )
          {
            if ( *(_WORD *)(v16 + 2 * j) == 46 )
            {
              v17 = j;
              goto LABEL_25;
            }
          }
          do
          {
LABEL_25:
            if ( !(unsigned int)_o__wcsnicmp(v16, off_18004D9A0[v13], v17) )
            {
              v6 = v22;
              goto LABEL_32;
            }
            ++v13;
          }
          while ( v13 < 0xC );
          if ( BCryptHashData(phHash[0], (PUCHAR)v9[3], 2 * v17, 0) < 0 )
            __fastfail(7u);
          v6 = v22;
          *(_QWORD *)pbInput = *(_QWORD *)(v22 + 8LL * v10) - *v9;
          if ( BCryptHashData(phHash[0], pbInput, 8u, 0) < 0 )
            __fastfail(7u);
LABEL_32:
          v5 = a4;
          goto LABEL_33;
        }
      }
      for ( k = *a5; k != a5[1]; k += 8 )
      {
        if ( **(_QWORD **)k <= v11 && v11 < **(_QWORD **)k + (unsigned __int64)*(unsigned int *)(*(_QWORD *)k + 8LL) )
        {
          v13 = 0;
          v9 = *(_QWORD **)k;
          v15 = 0;
          goto LABEL_17;
        }
      }
      v15 = -2147023728;
      v13 = 0;
LABEL_17:
      if ( v15 >= 0 )
        goto LABEL_18;
LABEL_33:
      ++v10;
    }
    while ( v10 < a2 );
    v8 = v23;
  }
  if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(phHash[0]);
  phHash[0] = 0;
  CStowedExceptionPlugin::CompactMD5Digest(v8, (unsigned __int8 *)&phHash[1]);
  return 0;
}

```

## disassembly

```asm
0x180031b20  mov     [rsp-38h+arg_8], rbx
0x180031b25  push    rbp
0x180031b26  push    rsi
0x180031b27  push    rdi
0x180031b28  push    r12
0x180031b2a  push    r13
0x180031b2c  push    r14
0x180031b2e  push    r15
0x180031b30  mov     rbp, rsp
0x180031b33  sub     rsp, 80h
0x180031b3a  mov     rax, cs:__security_cookie
0x180031b41  xor     rax, rsp
0x180031b44  mov     [rbp+var_8], rax
0x180031b48  xor     r12d, r12d
0x180031b4b  mov     [rbp+var_40], r9
0x180031b4f  xor     eax, eax
0x180031b51  mov     [rbp+var_30], r8
0x180031b55  mov     rdi, r9
0x180031b58  mov     [rbp+var_28], rcx
0x180031b5c  mov     rsi, r8
0x180031b5f  mov     [rcx], r12d
0x180031b62  mov     r13d, edx
0x180031b65  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x180031b6a  mov     rbx, rcx
0x180031b6d  mov     [rsp+80h+cbSecret], r12d; cbSecret
0x180031b72  xorps   xmm0, xmm0
0x180031b75  mov     [rbp+var_10], rax
0x180031b79  lea     ecx, [rax+21h]; hAlgorithm
0x180031b7c  mov     qword ptr [rbp+pbInput], r12
0x180031b80  xor     r9d, r9d; cbHashObject
0x180031b83  mov     [rsp+80h+pbSecret], r12; pbSecret
0x180031b88  xor     r8d, r8d; pbHashObject
0x180031b8b  lea     rdx, [rbp+phHash]; phHash
0x180031b8f  movups  xmmword ptr [rbp+phHash], xmm0
0x180031b93  mov     r15d, r12d
0x180031b96  call    cs:__imp_BCryptCreateHash
0x180031b9c  test    eax, eax
0x180031b9e  jns     short loc_180031BA7
0x180031ba0  lea     ecx, [r12+7]
0x180031ba5  int     29h; Win8: RtlFailFast(ecx)
0x180031ba7  mov     r14d, r12d
0x180031baa  test    r13d, r13d
0x180031bad  jz      loc_180031CE2
0x180031bb3  mov     r12, [rbp+arg_20]
0x180031bb7  mov     eax, r14d
0x180031bba  mov     r8, [rsi+rax*8]
0x180031bbe  mov     rax, [rdi]
0x180031bc1  cmp     rax, [rdi+8]
0x180031bc5  jz      short loc_180031BE7
0x180031bc7  mov     rdx, [rax]
0x180031bca  cmp     [rdx], r8
0x180031bcd  ja      short loc_180031BDA
0x180031bcf  mov     ecx, [rdx+8]
0x180031bd2  add     rcx, [rdx]
0x180031bd5  cmp     r8, rcx
0x180031bd8  jb      short loc_180031BE0
0x180031bda  add     rax, 8
0x180031bde  jmp     short loc_180031BC1
0x180031be0  mov     r15, rdx
0x180031be3  xor     ebx, ebx
0x180031be5  jmp     short loc_180031C23
0x180031be7  mov     rax, [r12]
0x180031beb  cmp     rax, [r12+8]
0x180031bf0  jz      short loc_180031C14
0x180031bf2  mov     rdx, [rax]
0x180031bf5  cmp     [rdx], r8
0x180031bf8  ja      short loc_180031C05
0x180031bfa  mov     ecx, [rdx+8]
0x180031bfd  add     rcx, [rdx]
0x180031c00  cmp     r8, rcx
0x180031c03  jb      short loc_180031C0B
0x180031c05  add     rax, 8
0x180031c09  jmp     short loc_180031BEB
0x180031c0b  xor     ebx, ebx
0x180031c0d  mov     r15, rdx
0x180031c10  mov     eax, ebx
0x180031c12  jmp     short loc_180031C1B
0x180031c14  mov     eax, 80070490h
0x180031c19  xor     ebx, ebx
0x180031c1b  test    eax, eax
0x180031c1d  js      loc_180031CCF
0x180031c23  mov     rsi, [r15+18h]
0x180031c27  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031c2b  inc     rdi
0x180031c2e  cmp     [rsi+rdi*2], bx
0x180031c32  jnz     short loc_180031C2B
0x180031c34  mov     rax, rdi
0x180031c37  test    rdi, rdi
0x180031c3a  jz      short loc_180031C4E
0x180031c3c  cmp     word ptr [rsi+rax*2], 2Eh ; '.'
0x180031c41  jz      short loc_180031C4B
0x180031c43  sub     rax, 1
0x180031c47  jnz     short loc_180031C3C
0x180031c49  jmp     short loc_180031C4E
0x180031c4b  mov     rdi, rax
0x180031c4e  lea     rax, off_18004D9A0; "ntdll"
0x180031c55  movsxd  rdx, ebx
0x180031c58  mov     r8, rdi
0x180031c5b  mov     rcx, rsi
0x180031c5e  mov     rdx, [rax+rdx*8]
0x180031c62  call    cs:__imp__o__wcsnicmp
0x180031c68  test    eax, eax
0x180031c6a  jz      short loc_180031CC7
0x180031c6c  inc     ebx
0x180031c6e  cmp     ebx, 0Ch
0x180031c71  jb      short loc_180031C4E
0x180031c73  mov     rdx, [r15+18h]; pbInput
0x180031c77  lea     r8d, [rdi+rdi]; cbInput
0x180031c7b  mov     rcx, [rbp+phHash]; hHash
0x180031c7f  xor     r9d, r9d; dwFlags
0x180031c82  call    cs:__imp_BCryptHashData
0x180031c88  test    eax, eax
0x180031c8a  jns     short loc_180031C93
0x180031c8c  mov     ecx, 7
0x180031c91  int     29h; Win8: RtlFailFast(ecx)
0x180031c93  mov     rsi, [rbp+var_30]
0x180031c97  lea     rdx, [rbp+pbInput]; pbInput
0x180031c9b  mov     rcx, [rbp+phHash]; hHash
0x180031c9f  xor     r9d, r9d; dwFlags
0x180031ca2  mov     eax, r14d
0x180031ca5  lea     r8d, [r9+8]; cbInput
0x180031ca9  mov     rax, [rsi+rax*8]
0x180031cad  sub     rax, [r15]
0x180031cb0  mov     qword ptr [rbp+pbInput], rax
0x180031cb4  call    cs:__imp_BCryptHashData
0x180031cba  test    eax, eax
0x180031cbc  jns     short loc_180031CCB
0x180031cbe  mov     ecx, 7
0x180031cc3  int     29h; Win8: RtlFailFast(ecx)
0x180031cc5  jmp     short loc_180031CCB
0x180031cc7  mov     rsi, [rbp+var_30]
0x180031ccb  mov     rdi, [rbp+var_40]
0x180031ccf  inc     r14d
0x180031cd2  cmp     r14d, r13d
0x180031cd5  jb      loc_180031BB7
0x180031cdb  mov     rbx, [rbp+var_28]
0x180031cdf  xor     r12d, r12d
0x180031ce2  mov     rcx, [rbp+phHash]; hHash
0x180031ce6  lea     rdx, [rbp+phHash+8]; pbOutput
0x180031cea  xor     r9d, r9d; dwFlags
0x180031ced  lea     r8d, [r9+10h]; cbOutput
0x180031cf1  call    cs:__imp_BCryptFinishHash
0x180031cf7  test    eax, eax
0x180031cf9  jns     short loc_180031D02
0x180031cfb  mov     ecx, 7
0x180031d00  int     29h; Win8: RtlFailFast(ecx)
0x180031d02  mov     rcx, [rbp+phHash]; hHash
0x180031d06  call    cs:__imp_BCryptDestroyHash
0x180031d0c  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x180031d10  mov     [rbp+phHash], r12
0x180031d14  mov     rcx, rbx; unsigned int *
0x180031d17  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x180031d1c  xor     eax, eax
0x180031d1e  mov     rcx, [rbp+var_8]
0x180031d22  xor     rcx, rsp; StackCookie
0x180031d25  call    __security_check_cookie
0x180031d2a  mov     rbx, [rsp+80h+arg_8]
0x180031d32  add     rsp, 80h
0x180031d39  pop     r15
0x180031d3b  pop     r14
0x180031d3d  pop     r13
0x180031d3f  pop     r12
0x180031d41  pop     rdi
0x180031d42  pop     rsi
0x180031d43  pop     rbp
0x180031d44  retn
```
