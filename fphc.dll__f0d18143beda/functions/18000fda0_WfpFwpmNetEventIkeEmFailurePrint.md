# WfpFwpmNetEventIkeEmFailurePrint

- ea: `0x18000fda0`
- end: `0x180010082`
- name: `WfpFwpmNetEventIkeEmFailurePrint`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001055c`

## callees

- `0x18000f020`
- `0x18000fda0`
- `0x180010830`
- `0x180010c94`
- `0x180012010`

## string_xrefs

- `0x18000ffc7`: `%sLocal Principal Group SIDs:\n`
- `0x180010007`: `%sRemote Principal Group SIDs:\n`

## pseudocode

```c
__int64 __fastcall WfpFwpmNetEventIkeEmFailurePrint(
        void (*a1)(__int64, const wchar_t *, ...),
        __int64 a2,
        unsigned int a3,
        unsigned int *a4)
{
  wchar_t **v5; // rcx
  wchar_t **v8; // r14
  wchar_t *v9; // r14
  __int64 v10; // rbx
  wchar_t *v11; // r12
  __int64 v12; // rax
  const wchar_t *v13; // r15
  const wchar_t *v14; // r9
  __int64 v15; // rax
  const wchar_t *v16; // r9
  __int64 v17; // rax
  const wchar_t *v18; // r9
  const wchar_t *v19; // r9
  const wchar_t *v20; // rbx
  const wchar_t *v21; // r9
  __int64 i; // rbx
  __int64 j; // rbx
  __int64 v24; // rax

  v5 = off_180014148;
  if ( a3 < 7 )
    v8 = (wchar_t **)((char *)&off_180014118 + 8 * a3);
  else
    v8 = off_180014148;
  v9 = *v8;
  v10 = a3 + 1;
  if ( (unsigned int)v10 < 7 )
    v5 = (wchar_t **)((char *)&off_180014118 + 8 * v10);
  v11 = *v5;
  a1(a2, L"%sFailure error code: 0x%x\n", v9, *a4);
  WfpWin32ErrorPrint(a1, a2, (unsigned int)v10, *a4);
  v12 = (int)a4[1];
  v13 = L"<invalid>";
  if ( (unsigned int)v12 > 2 )
    v14 = L"<invalid>";
  else
    v14 = off_1800143A0[v12];
  a1(a2, L"%sFailure point: %s\n", v9, v14);
  a1(a2, L"%sFlags: 0x%08x\n", v9, a4[2]);
  WfpFlagsPrint((_DWORD)a1, a2, v10, 2, (__int64)&qword_180014230, a4[2]);
  v15 = (int)a4[3];
  if ( (unsigned int)v15 > 5 )
    v16 = L"<invalid>";
  else
    v16 = off_180014360[v15];
  a1(a2, L"%sEM State: %s\n", v9, v16);
  v17 = (int)a4[4];
  if ( (unsigned int)v17 > 1 )
    v18 = L"<invalid>";
  else
    v18 = off_180014268[v17];
  a1(a2, L"%sEM SA role: %s\n", v9, v18);
  if ( a4[5] >= 0xE )
    v19 = L"<invalid>";
  else
    v19 = off_180014150[a4[5]];
  a1(a2, L"%sEM auth method: %s\n", v9, v19);
  a1(a2, L"%sCert hash:\n", v9);
  WfpIkeCertHashPrint(a1, a2, a4 + 6);
  a1(a2, L"%sMM ID: 0x%016I64x\n", v9, *((_QWORD *)a4 + 6));
  a1(a2, L"%sQM Filter ID: 0x%016I64x\n", v9, *((_QWORD *)a4 + 7));
  v20 = L"<unspecified>";
  v21 = L"<unspecified>";
  if ( *((_QWORD *)a4 + 8) )
    v21 = (const wchar_t *)*((_QWORD *)a4 + 8);
  a1(a2, L"%sLocal Principal Name: %s\n", v9, v21);
  if ( *((_QWORD *)a4 + 9) )
    v20 = (const wchar_t *)*((_QWORD *)a4 + 9);
  a1(a2, L"%sRemote Principal Name: %s\n", v9, v20);
  a1(a2, L"%sLocal Principal Group SIDs:\n", v9);
  for ( i = 0; (unsigned int)i < a4[20]; i = (unsigned int)(i + 1) )
    a1(a2, L"%s%s\n", v11, *(_QWORD *)(*((_QWORD *)a4 + 11) + 8 * i));
  a1(a2, L"%sRemote Principal Group SIDs:\n", v9);
  for ( j = 0; (unsigned int)j < a4[24]; j = (unsigned int)(j + 1) )
    a1(a2, L"%s%s\n", v11, *(_QWORD *)(*((_QWORD *)a4 + 13) + 8 * j));
  v24 = (int)a4[28];
  if ( (unsigned int)v24 <= 2 )
    v13 = off_1800141E0[v24];
  return ((__int64 (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sMode: %s\n", v9, v13);
}

```

## disassembly

```asm
0x18000fda0  push    rbx
0x18000fda2  push    rbp
0x18000fda3  push    rsi
0x18000fda4  push    rdi
0x18000fda5  push    r12
0x18000fda7  push    r13
0x18000fda9  push    r14
0x18000fdab  push    r15
0x18000fdad  sub     rsp, 38h
0x18000fdb1  lea     r13, cs:180000000h
0x18000fdb8  mov     rbp, rcx
0x18000fdbb  lea     rcx, off_180014148; "            "
0x18000fdc2  mov     rdi, r9
0x18000fdc5  mov     rsi, rdx
0x18000fdc8  cmp     r8d, 7
0x18000fdcc  jb      short loc_18000FDD3
0x18000fdce  mov     r14, rcx
0x18000fdd1  jmp     short loc_18000FDE1
0x18000fdd3  mov     eax, r8d
0x18000fdd6  lea     r14, rva off_180014118[r13]
0x18000fddd  lea     r14, [r14+rax*8]
0x18000fde1  mov     r14, [r14]
0x18000fde4  lea     ebx, [r8+1]
0x18000fde8  cmp     ebx, 7
0x18000fdeb  jnb     short loc_18000FDF8
0x18000fded  lea     rcx, rva off_180014118[r13]
0x18000fdf4  lea     rcx, [rcx+rbx*8]
0x18000fdf8  mov     r12, [rcx]
0x18000fdfb  lea     rdx, aSfailureErrorC_0; "%sFailure error code: 0x%x\n"
0x18000fe02  mov     r9d, [r9]
0x18000fe05  mov     rcx, rsi
0x18000fe08  mov     r8, r14
0x18000fe0b  mov     rax, rbp
0x18000fe0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe13  mov     r9d, [rdi]
0x18000fe16  mov     r8d, ebx
0x18000fe19  mov     rdx, rsi
0x18000fe1c  mov     rcx, rbp
0x18000fe1f  call    WfpWin32ErrorPrint
0x18000fe24  movsxd  rax, dword ptr [rdi+4]
0x18000fe28  lea     r15, aInvalid; "<invalid>"
0x18000fe2f  test    eax, eax
0x18000fe31  js      short loc_18000FE42
0x18000fe33  cmp     eax, 3
0x18000fe36  jnb     short loc_18000FE42
0x18000fe38  mov     r9, ds:rva off_1800143A0[r13+rax*8]; "None" ...
0x18000fe40  jmp     short loc_18000FE45
0x18000fe42  mov     r9, r15
0x18000fe45  mov     r8, r14
0x18000fe48  lea     rdx, aSfailurePointS; "%sFailure point: %s\n"
0x18000fe4f  mov     rcx, rsi
0x18000fe52  mov     rax, rbp
0x18000fe55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5a  mov     r9d, [rdi+8]
0x18000fe5e  lea     rdx, aSflags0x08x; "%sFlags: 0x%08x\n"
0x18000fe65  mov     r8, r14
0x18000fe68  mov     rcx, rsi
0x18000fe6b  mov     rax, rbp
0x18000fe6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe73  mov     eax, [rdi+8]
0x18000fe76  mov     r9d, 2
0x18000fe7c  mov     [rsp+78h+var_50], eax
0x18000fe80  mov     r8d, ebx
0x18000fe83  lea     rax, qword_180014230
0x18000fe8a  mov     rdx, rsi
0x18000fe8d  mov     rcx, rbp
0x18000fe90  mov     [rsp+78h+var_58], rax
0x18000fe95  call    WfpFlagsPrint
0x18000fe9a  movsxd  rax, dword ptr [rdi+0Ch]
0x18000fe9e  test    eax, eax
0x18000fea0  js      short loc_18000FEB1
0x18000fea2  cmp     eax, 6
0x18000fea5  jnb     short loc_18000FEB1
0x18000fea7  mov     r9, ds:rva off_180014360[r13+rax*8]; "Initial state, no EM packets sent" ...
0x18000feaf  jmp     short loc_18000FEB4
0x18000feb1  mov     r9, r15
0x18000feb4  mov     r8, r14
0x18000feb7  lea     rdx, aSemStateS; "%sEM State: %s\n"
0x18000febe  mov     rcx, rsi
0x18000fec1  mov     rax, rbp
0x18000fec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec9  movsxd  rax, dword ptr [rdi+10h]
0x18000fecd  test    eax, eax
0x18000fecf  js      short loc_18000FEE0
0x18000fed1  cmp     eax, 2
0x18000fed4  jnb     short loc_18000FEE0
0x18000fed6  mov     r9, ds:rva off_180014268[r13+rax*8]; "Initiator" ...
0x18000fede  jmp     short loc_18000FEE3
0x18000fee0  mov     r9, r15
0x18000fee3  mov     r8, r14
0x18000fee6  lea     rdx, aSemSaRoleS; "%sEM SA role: %s\n"
0x18000feed  mov     rcx, rsi
0x18000fef0  mov     rax, rbp
0x18000fef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fef8  cmp     dword ptr [rdi+14h], 0Eh
0x18000fefc  jnb     short loc_18000FF0B
0x18000fefe  mov     eax, [rdi+14h]
0x18000ff01  mov     r9, ds:rva off_180014150[r13+rax*8]; "Preshared Key" ...
0x18000ff09  jmp     short loc_18000FF0E
0x18000ff0b  mov     r9, r15
0x18000ff0e  mov     r8, r14
0x18000ff11  lea     rdx, aSemAuthMethodS; "%sEM auth method: %s\n"
0x18000ff18  mov     rcx, rsi
0x18000ff1b  mov     rax, rbp
0x18000ff1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff23  mov     r8, r14
0x18000ff26  lea     rdx, aScertHash; "%sCert hash:\n"
0x18000ff2d  mov     rcx, rsi
0x18000ff30  mov     rax, rbp
0x18000ff33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff38  lea     r8, [rdi+18h]
0x18000ff3c  mov     rdx, rsi
0x18000ff3f  mov     rcx, rbp
0x18000ff42  call    WfpIkeCertHashPrint
0x18000ff47  mov     r9, [rdi+30h]
0x18000ff4b  lea     rdx, aSmmId0x016i64x; "%sMM ID: 0x%016I64x\n"
0x18000ff52  mov     r8, r14
0x18000ff55  mov     rcx, rsi
0x18000ff58  mov     rax, rbp
0x18000ff5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff60  mov     r9, [rdi+38h]
0x18000ff64  lea     rdx, aSqmFilterId0x0; "%sQM Filter ID: 0x%016I64x\n"
0x18000ff6b  mov     r8, r14
0x18000ff6e  mov     rcx, rsi
0x18000ff71  mov     rax, rbp
0x18000ff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff79  cmp     qword ptr [rdi+40h], 0
0x18000ff7e  lea     rbx, aUnspecified; "<unspecified>"
0x18000ff85  mov     r9, rbx
0x18000ff88  lea     rdx, aSlocalPrincipa_0; "%sLocal Principal Name: %s\n"
0x18000ff8f  cmovnz  r9, [rdi+40h]
0x18000ff94  mov     r8, r14
0x18000ff97  mov     rcx, rsi
0x18000ff9a  mov     rax, rbp
0x18000ff9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa2  cmp     qword ptr [rdi+48h], 0
0x18000ffa7  lea     rdx, aSremotePrincip_0; "%sRemote Principal Name: %s\n"
0x18000ffae  mov     r8, r14
0x18000ffb1  mov     rcx, rsi
0x18000ffb4  cmovnz  rbx, [rdi+48h]
0x18000ffb9  mov     rax, rbp
0x18000ffbc  mov     r9, rbx
0x18000ffbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc4  mov     r8, r14
0x18000ffc7  lea     rdx, aSlocalPrincipa; "%sLocal Principal Group SIDs:\n"
0x18000ffce  mov     rcx, rsi
0x18000ffd1  mov     rax, rbp
0x18000ffd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd9  xor     ebx, ebx
0x18000ffdb  cmp     [rdi+50h], ebx
0x18000ffde  jbe     short loc_180010004
0x18000ffe0  mov     r9, [rdi+58h]
0x18000ffe4  lea     rdx, aSS_0; "%s%s\n"
0x18000ffeb  mov     r8, r12
0x18000ffee  mov     rcx, rsi
0x18000fff1  mov     rax, rbp
0x18000fff4  mov     r9, [r9+rbx*8]
0x18000fff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fffd  inc     ebx
0x18000ffff  cmp     ebx, [rdi+50h]
0x180010002  jb      short loc_18000FFE0
0x180010004  mov     r8, r14
0x180010007  lea     rdx, aSremotePrincip; "%sRemote Principal Group SIDs:\n"
0x18001000e  mov     rcx, rsi
0x180010011  mov     rax, rbp
0x180010014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010019  xor     ebx, ebx
0x18001001b  cmp     [rdi+60h], ebx
0x18001001e  jbe     short loc_180010044
0x180010020  mov     r9, [rdi+68h]
0x180010024  lea     rdx, aSS_0; "%s%s\n"
0x18001002b  mov     r8, r12
0x18001002e  mov     rcx, rsi
0x180010031  mov     rax, rbp
0x180010034  mov     r9, [r9+rbx*8]
0x180010038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001003d  inc     ebx
0x18001003f  cmp     ebx, [rdi+60h]
0x180010042  jb      short loc_180010020
0x180010044  movsxd  rax, dword ptr [rdi+70h]
0x180010048  test    eax, eax
0x18001004a  js      short loc_180010059
0x18001004c  cmp     eax, 3
0x18001004f  jnb     short loc_180010059
0x180010051  mov     r15, ds:rva off_1800141E0[r13+rax*8]; "Transport Mode" ...
0x180010059  mov     r9, r15
0x18001005c  lea     rdx, aSmodeS; "%sMode: %s\n"
0x180010063  mov     r8, r14
0x180010066  mov     rcx, rsi
0x180010069  mov     rax, rbp
0x18001006c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010071  add     rsp, 38h
0x180010075  pop     r15
0x180010077  pop     r14
0x180010079  pop     r13
0x18001007b  pop     r12
0x18001007d  pop     rdi
0x18001007e  pop     rsi
0x18001007f  pop     rbp
0x180010080  pop     rbx
0x180010081  retn
```
