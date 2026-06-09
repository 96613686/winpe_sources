# CPSDuplicateContext(void *,void * *)

- ea: `0x18001fd64`
- end: `0x18001ff13`
- name: `?CPSDuplicateContext@@YAKPEAXPEAPEAX@Z`
- size: `431`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019d00`
- `0x18002c4f8`

## callees

- `0x180007f10`
- `0x18001fd64`
- `0x18001ff1c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001feb0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001feb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fec0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fd9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fd9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe6f`

## string_xrefs

- `0x18001fed2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSDuplicateContext(void *a1, void **a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  __int64 v7; // rdx
  _OWORD *v8; // rcx
  __int128 v9; // xmm1
  __int64 v10; // rcx
  __int64 v11; // rax
  SIZE_T v12; // rbp
  HLOCAL v13; // rax
  DWORD LastError; // edi

  if ( !a1 || *(_DWORD *)a1 != 624 || !a2 )
    return 87;
  v4 = LocalAlloc(0, 0x270u);
  v5 = v4;
  if ( !v4 )
    return 1130;
  v7 = 4;
  v8 = a1;
  do
  {
    *v4 = *v8;
    v4[1] = v8[1];
    v4[2] = v8[2];
    v4[3] = v8[3];
    v4[4] = v8[4];
    v4[5] = v8[5];
    v4[6] = v8[6];
    v9 = v8[7];
    v8 += 8;
    v4[7] = v9;
    v4 += 8;
    --v7;
  }
  while ( v7 );
  *v4 = *v8;
  v4[1] = v8[1];
  v4[2] = v8[2];
  v4[3] = v8[3];
  v4[4] = v8[4];
  v4[5] = v8[5];
  v4[6] = v8[6];
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 9) = 0;
  v10 = *((_QWORD *)a1 + 5);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    v12 = 2LL * (unsigned int)(v11 + 1);
    v13 = LocalAlloc(0, v12);
    *((_QWORD *)v5 + 5) = v13;
    if ( v13 )
      memcpy_0(v13, *((const void **)a1 + 5), v12);
  }
  if ( DuplicateTokenEx(*((HANDLE *)a1 + 3), 0, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)v5 + 3) )
  {
    LastError = 0;
    *a2 = v5;
  }
  else
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 669);
    *((_QWORD *)v5 + 3) = 0;
    CPSFreeContext(v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001fd64  push    rbx
0x18001fd66  push    rbp
0x18001fd67  push    rsi
0x18001fd68  push    rdi
0x18001fd69  push    r14
0x18001fd6b  push    r15
0x18001fd6d  sub     rsp, 38h
0x18001fd71  xor     r15d, r15d
0x18001fd74  mov     rsi, rdx
0x18001fd77  mov     rdi, rcx
0x18001fd7a  test    rcx, rcx
0x18001fd7d  jz      loc_18001FF00
0x18001fd83  mov     edx, 270h; uBytes
0x18001fd88  cmp     [rcx], edx
0x18001fd8a  jnz     loc_18001FF00
0x18001fd90  test    rsi, rsi
0x18001fd93  jz      loc_18001FF00
0x18001fd99  xor     ecx, ecx; uFlags
0x18001fd9b  call    cs:__imp_LocalAlloc
0x18001fda2  nop     dword ptr [rax+rax+00h]
0x18001fda7  mov     rbx, rax
0x18001fdaa  test    rax, rax
0x18001fdad  jnz     short loc_18001FDB9
0x18001fdaf  mov     eax, 46Ah
0x18001fdb4  jmp     loc_18001FF05
0x18001fdb9  mov     edx, 4
0x18001fdbe  mov     rcx, rdi
0x18001fdc1  lea     r8d, [rdx+7Ch]
0x18001fdc5  movups  xmm0, xmmword ptr [rcx]
0x18001fdc8  movups  xmmword ptr [rax], xmm0
0x18001fdcb  movups  xmm1, xmmword ptr [rcx+10h]
0x18001fdcf  movups  xmmword ptr [rax+10h], xmm1
0x18001fdd3  movups  xmm0, xmmword ptr [rcx+20h]
0x18001fdd7  movups  xmmword ptr [rax+20h], xmm0
0x18001fddb  movups  xmm1, xmmword ptr [rcx+30h]
0x18001fddf  movups  xmmword ptr [rax+30h], xmm1
0x18001fde3  movups  xmm0, xmmword ptr [rcx+40h]
0x18001fde7  movups  xmmword ptr [rax+40h], xmm0
0x18001fdeb  movups  xmm1, xmmword ptr [rcx+50h]
0x18001fdef  movups  xmmword ptr [rax+50h], xmm1
0x18001fdf3  movups  xmm0, xmmword ptr [rcx+60h]
0x18001fdf7  movups  xmmword ptr [rax+60h], xmm0
0x18001fdfb  movups  xmm1, xmmword ptr [rcx+70h]
0x18001fdff  add     rcx, r8
0x18001fe02  movups  xmmword ptr [rax+70h], xmm1
0x18001fe06  add     rax, r8
0x18001fe09  sub     rdx, 1
0x18001fe0d  jnz     short loc_18001FDC5
0x18001fe0f  movups  xmm0, xmmword ptr [rcx]
0x18001fe12  movups  xmmword ptr [rax], xmm0
0x18001fe15  movups  xmm1, xmmword ptr [rcx+10h]
0x18001fe19  movups  xmmword ptr [rax+10h], xmm1
0x18001fe1d  movups  xmm0, xmmword ptr [rcx+20h]
0x18001fe21  movups  xmmword ptr [rax+20h], xmm0
0x18001fe25  movups  xmm1, xmmword ptr [rcx+30h]
0x18001fe29  movups  xmmword ptr [rax+30h], xmm1
0x18001fe2d  movups  xmm0, xmmword ptr [rcx+40h]
0x18001fe31  movups  xmmword ptr [rax+40h], xmm0
0x18001fe35  movups  xmm1, xmmword ptr [rcx+50h]
0x18001fe39  movups  xmmword ptr [rax+50h], xmm1
0x18001fe3d  movups  xmm0, xmmword ptr [rcx+60h]
0x18001fe41  movups  xmmword ptr [rax+60h], xmm0
0x18001fe45  mov     [rbx+8], r15
0x18001fe49  mov     [rbx+48h], r15
0x18001fe4d  mov     rcx, [rdi+28h]
0x18001fe51  test    rcx, rcx
0x18001fe54  jz      short loc_18001FE93
0x18001fe56  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fe5a  inc     rax
0x18001fe5d  cmp     [rcx+rax*2], r15w
0x18001fe62  jnz     short loc_18001FE5A
0x18001fe64  lea     ebp, [rax+1]
0x18001fe67  xor     ecx, ecx; uFlags
0x18001fe69  add     rbp, rbp
0x18001fe6c  mov     rdx, rbp; uBytes
0x18001fe6f  call    cs:__imp_LocalAlloc
0x18001fe76  nop     dword ptr [rax+rax+00h]
0x18001fe7b  mov     [rbx+28h], rax
0x18001fe7f  test    rax, rax
0x18001fe82  jz      short loc_18001FE93
0x18001fe84  mov     rdx, [rdi+28h]; Src
0x18001fe88  mov     r8, rbp; Size
0x18001fe8b  mov     rcx, rax; void *
0x18001fe8e  call    memcpy_0
0x18001fe93  mov     rcx, [rdi+18h]; hExistingToken
0x18001fe97  lea     r14, [rbx+18h]
0x18001fe9b  mov     r9d, 2; ImpersonationLevel
0x18001fea1  mov     [rsp+68h+phNewToken], r14; phNewToken
0x18001fea6  xor     r8d, r8d; lpTokenAttributes
0x18001fea9  mov     [rsp+68h+TokenType], r9d; TokenType
0x18001feae  xor     edx, edx; dwDesiredAccess
0x18001feb0  call    cs:__imp_DuplicateTokenEx
0x18001feb7  nop     dword ptr [rax+rax+00h]
0x18001febc  test    eax, eax
0x18001febe  jnz     short loc_18001FEF6
0x18001fec0  call    cs:__imp_GetLastError
0x18001fec7  nop     dword ptr [rax+rax+00h]
0x18001fecc  mov     r9d, 29Dh
0x18001fed2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001fed9  mov     ecx, eax
0x18001fedb  lea     rdx, aDwlasterror; "dwLastError"
0x18001fee2  mov     edi, eax
0x18001fee4  call    DebugTraceError
0x18001fee9  mov     rcx, rbx; hMem
0x18001feec  mov     [r14], r15
0x18001feef  call    ?CPSFreeContext@@YAKPEAX@Z; CPSFreeContext(void *)
0x18001fef4  jmp     short loc_18001FEFC
0x18001fef6  mov     edi, r15d
0x18001fef9  mov     [rsi], rbx
0x18001fefc  mov     eax, edi
0x18001fefe  jmp     short loc_18001FF05
0x18001ff00  mov     eax, 57h ; 'W'
0x18001ff05  add     rsp, 38h
0x18001ff09  pop     r15
0x18001ff0b  pop     r14
0x18001ff0d  pop     rdi
0x18001ff0e  pop     rsi
0x18001ff0f  pop     rbp
0x18001ff10  pop     rbx
0x18001ff11  retn
```
