# WfpFwpmNetEventIkeMmFailurePrint

- ea: `0x180010088`
- end: `0x180010374`
- name: `WfpFwpmNetEventIkeMmFailurePrint`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001055c`

## callees

- `0x18000f020`
- `0x180010088`
- `0x180010830`
- `0x180010c94`
- `0x180012010`

## string_xrefs

- `0x1800102de`: `%sLocal Principal Group SIDs:\n`
- `0x180010322`: `%sRemote Principal Group SIDs:\n`

## pseudocode

```c
__int64 __fastcall WfpFwpmNetEventIkeMmFailurePrint(
        void (*a1)(__int64, const wchar_t *, ...),
        __int64 a2,
        unsigned int a3,
        unsigned int *a4)
{
  wchar_t **v5; // rcx
  wchar_t **v8; // r14
  wchar_t *v9; // r14
  __int64 v10; // r15
  wchar_t *v11; // r12
  __int64 v12; // rax
  const wchar_t *v13; // rbx
  const wchar_t *v14; // r9
  __int64 v15; // rax
  const wchar_t *v16; // r9
  __int64 v17; // rax
  const wchar_t *v18; // r9
  __int64 v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // rbx
  const wchar_t *v22; // r9
  unsigned int i; // ebx
  __int64 result; // rax
  unsigned int j; // ebx

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
  a1(a2, L"%sFailure error code:0x%08x\n", v9, *a4);
  WfpWin32ErrorPrint(a1, a2, (unsigned int)v10, *a4);
  v12 = (int)a4[1];
  v13 = L"<invalid>";
  if ( (unsigned int)v12 > 2 )
    v14 = L"<invalid>";
  else
    v14 = off_1800143A0[v12];
  a1(a2, L"%sFailure point: %s\n", v9, v14);
  a1(a2, L"%sFlags: 0x%08x\n", v9, a4[2]);
  WfpFlagsPrint((_DWORD)a1, a2, v10, 2, (__int64)&qword_1800141C0, a4[2]);
  v15 = (int)a4[3];
  if ( (unsigned int)v15 > 2 )
    v16 = L"<invalid>";
  else
    v16 = off_180014250[v15];
  a1(a2, L"%sKeying module type: %s\n", v9, v16);
  v17 = (int)a4[4];
  if ( (unsigned int)v17 > 5 )
    v18 = L"<invalid>";
  else
    v18 = off_180014330[v17];
  a1(a2, L"%sMM State: %s\n", v9, v18);
  v19 = (int)a4[5];
  if ( (unsigned int)v19 > 1 )
    v20 = L"<invalid>";
  else
    v20 = off_180014268[v19];
  a1(a2, L"%sMM SA role: %s\n", v9, v20);
  if ( a4[6] < 0xE )
    v13 = off_180014150[a4[6]];
  a1(a2, L"%sMM auth method: %s\n", v9, v13);
  a1(a2, L"%sCert hash:\n", v9);
  WfpIkeCertHashPrint(a1, a2, a4 + 7);
  a1(a2, L"%sMM ID: 0x%016I64x\n", v9, *((_QWORD *)a4 + 6));
  a1(a2, L"%sMM Filter ID: 0x%016I64x\n", v9, *((_QWORD *)a4 + 7));
  v21 = L"<unspecified>";
  v22 = L"<unspecified>";
  if ( *((_QWORD *)a4 + 8) )
    v22 = (const wchar_t *)*((_QWORD *)a4 + 8);
  a1(a2, L"%sLocal Principal Name: %s\n", v9, v22);
  if ( *((_QWORD *)a4 + 9) )
    v21 = (const wchar_t *)*((_QWORD *)a4 + 9);
  a1(a2, L"%sRemote Principal Name: %s\n", v9, v21);
  a1(a2, L"%sLocal Principal Group SIDs:\n", v9);
  for ( i = 0; i < a4[20]; ++i )
    a1(a2, L"%s%s\n", v11, *(_QWORD *)(*((_QWORD *)a4 + 11) + 8LL * i));
  result = ((__int64 (*)(__int64, const wchar_t *, ...))a1)(a2, L"%sRemote Principal Group SIDs:\n", v9);
  for ( j = 0; j < a4[24]; ++j )
    result = ((__int64 (*)(__int64, const wchar_t *, ...))a1)(
               a2,
               L"%s%s\n",
               v11,
               *(_QWORD *)(*((_QWORD *)a4 + 13) + 8LL * j));
  return result;
}

```

## disassembly

```asm
0x180010088  push    rbx
0x18001008a  push    rbp
0x18001008b  push    rsi
0x18001008c  push    rdi
0x18001008d  push    r12
0x18001008f  push    r13
0x180010091  push    r14
0x180010093  push    r15
0x180010095  sub     rsp, 38h
0x180010099  lea     r13, cs:180000000h
0x1800100a0  mov     rbp, rcx
0x1800100a3  lea     rcx, off_180014148; "            "
0x1800100aa  mov     rdi, r9
0x1800100ad  mov     rsi, rdx
0x1800100b0  cmp     r8d, 7
0x1800100b4  jb      short loc_1800100BB
0x1800100b6  mov     r14, rcx
0x1800100b9  jmp     short loc_1800100C9
0x1800100bb  mov     eax, r8d
0x1800100be  lea     r14, rva off_180014118[r13]
0x1800100c5  lea     r14, [r14+rax*8]
0x1800100c9  mov     r14, [r14]
0x1800100cc  lea     r15d, [r8+1]
0x1800100d0  cmp     r15d, 7
0x1800100d4  jnb     short loc_1800100E1
0x1800100d6  lea     rcx, rva off_180014118[r13]
0x1800100dd  lea     rcx, [rcx+r15*8]
0x1800100e1  mov     r12, [rcx]
0x1800100e4  lea     rdx, aSfailureErrorC; "%sFailure error code:0x%08x\n"
0x1800100eb  mov     r9d, [r9]
0x1800100ee  mov     rcx, rsi
0x1800100f1  mov     r8, r14
0x1800100f4  mov     rax, rbp
0x1800100f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100fc  mov     r9d, [rdi]
0x1800100ff  mov     r8d, r15d
0x180010102  mov     rdx, rsi
0x180010105  mov     rcx, rbp
0x180010108  call    WfpWin32ErrorPrint
0x18001010d  movsxd  rax, dword ptr [rdi+4]
0x180010111  lea     rbx, aInvalid; "<invalid>"
0x180010118  test    eax, eax
0x18001011a  js      short loc_18001012B
0x18001011c  cmp     eax, 3
0x18001011f  jnb     short loc_18001012B
0x180010121  mov     r9, ds:rva off_1800143A0[r13+rax*8]; "None" ...
0x180010129  jmp     short loc_18001012E
0x18001012b  mov     r9, rbx
0x18001012e  mov     r8, r14
0x180010131  lea     rdx, aSfailurePointS; "%sFailure point: %s\n"
0x180010138  mov     rcx, rsi
0x18001013b  mov     rax, rbp
0x18001013e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010143  mov     r9d, [rdi+8]
0x180010147  lea     rdx, aSflags0x08x; "%sFlags: 0x%08x\n"
0x18001014e  mov     r8, r14
0x180010151  mov     rcx, rsi
0x180010154  mov     rax, rbp
0x180010157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001015c  mov     eax, [rdi+8]
0x18001015f  mov     r9d, 2
0x180010165  mov     [rsp+78h+var_50], eax
0x180010169  mov     r8d, r15d
0x18001016c  lea     rax, qword_1800141C0
0x180010173  mov     rdx, rsi
0x180010176  mov     rcx, rbp
0x180010179  mov     [rsp+78h+var_58], rax
0x18001017e  call    WfpFlagsPrint
0x180010183  movsxd  rax, dword ptr [rdi+0Ch]
0x180010187  xor     r15d, r15d
0x18001018a  test    eax, eax
0x18001018c  js      short loc_18001019D
0x18001018e  cmp     eax, 3
0x180010191  jnb     short loc_18001019D
0x180010193  mov     r9, ds:rva off_180014250[r13+rax*8]; "Ike" ...
0x18001019b  jmp     short loc_1800101A0
0x18001019d  mov     r9, rbx
0x1800101a0  mov     r8, r14
0x1800101a3  lea     rdx, aSkeyingModuleT; "%sKeying module type: %s\n"
0x1800101aa  mov     rcx, rsi
0x1800101ad  mov     rax, rbp
0x1800101b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b5  movsxd  rax, dword ptr [rdi+10h]
0x1800101b9  test    eax, eax
0x1800101bb  js      short loc_1800101CC
0x1800101bd  cmp     eax, 6
0x1800101c0  jnb     short loc_1800101CC
0x1800101c2  mov     r9, ds:rva off_180014330[r13+rax*8]; "Initial state, no packets sent" ...
0x1800101ca  jmp     short loc_1800101CF
0x1800101cc  mov     r9, rbx
0x1800101cf  mov     r8, r14
0x1800101d2  lea     rdx, aSmmStateS; "%sMM State: %s\n"
0x1800101d9  mov     rcx, rsi
0x1800101dc  mov     rax, rbp
0x1800101df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e4  movsxd  rax, dword ptr [rdi+14h]
0x1800101e8  test    eax, eax
0x1800101ea  js      short loc_1800101FB
0x1800101ec  cmp     eax, 2
0x1800101ef  jnb     short loc_1800101FB
0x1800101f1  mov     r9, ds:rva off_180014268[r13+rax*8]; "Initiator" ...
0x1800101f9  jmp     short loc_1800101FE
0x1800101fb  mov     r9, rbx
0x1800101fe  mov     r8, r14
0x180010201  lea     rdx, aSmmSaRoleS; "%sMM SA role: %s\n"
0x180010208  mov     rcx, rsi
0x18001020b  mov     rax, rbp
0x18001020e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010213  cmp     dword ptr [rdi+18h], 0Eh
0x180010217  jnb     short loc_180010224
0x180010219  mov     eax, [rdi+18h]
0x18001021c  mov     rbx, ds:rva off_180014150[r13+rax*8]; "Preshared Key" ...
0x180010224  mov     r9, rbx
0x180010227  lea     rdx, aSmmAuthMethodS; "%sMM auth method: %s\n"
0x18001022e  mov     r8, r14
0x180010231  mov     rcx, rsi
0x180010234  mov     rax, rbp
0x180010237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023c  mov     r8, r14
0x18001023f  lea     rdx, aScertHash; "%sCert hash:\n"
0x180010246  mov     rcx, rsi
0x180010249  mov     rax, rbp
0x18001024c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010251  lea     r8, [rdi+1Ch]
0x180010255  mov     rdx, rsi
0x180010258  mov     rcx, rbp
0x18001025b  call    WfpIkeCertHashPrint
0x180010260  mov     r9, [rdi+30h]
0x180010264  lea     rdx, aSmmId0x016i64x; "%sMM ID: 0x%016I64x\n"
0x18001026b  mov     r8, r14
0x18001026e  mov     rcx, rsi
0x180010271  mov     rax, rbp
0x180010274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010279  mov     r9, [rdi+38h]
0x18001027d  lea     rdx, aSmmFilterId0x0; "%sMM Filter ID: 0x%016I64x\n"
0x180010284  mov     r8, r14
0x180010287  mov     rcx, rsi
0x18001028a  mov     rax, rbp
0x18001028d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010292  cmp     [rdi+40h], r15
0x180010296  lea     rbx, aUnspecified; "<unspecified>"
0x18001029d  mov     r9, rbx
0x1800102a0  lea     rdx, aSlocalPrincipa_0; "%sLocal Principal Name: %s\n"
0x1800102a7  cmovnz  r9, [rdi+40h]
0x1800102ac  mov     r8, r14
0x1800102af  mov     rcx, rsi
0x1800102b2  mov     rax, rbp
0x1800102b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ba  cmp     [rdi+48h], r15
0x1800102be  lea     rdx, aSremotePrincip_0; "%sRemote Principal Name: %s\n"
0x1800102c5  mov     r8, r14
0x1800102c8  mov     rcx, rsi
0x1800102cb  cmovnz  rbx, [rdi+48h]
0x1800102d0  mov     rax, rbp
0x1800102d3  mov     r9, rbx
0x1800102d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102db  mov     r8, r14
0x1800102de  lea     rdx, aSlocalPrincipa; "%sLocal Principal Group SIDs:\n"
0x1800102e5  mov     rcx, rsi
0x1800102e8  mov     rax, rbp
0x1800102eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102f0  mov     ebx, r15d
0x1800102f3  cmp     [rdi+50h], r15d
0x1800102f7  jbe     short loc_18001031F
0x1800102f9  mov     r9, [rdi+58h]
0x1800102fd  lea     rdx, aSS_0; "%s%s\n"
0x180010304  mov     eax, ebx
0x180010306  mov     r8, r12
0x180010309  mov     rcx, rsi
0x18001030c  mov     r9, [r9+rax*8]
0x180010310  mov     rax, rbp
0x180010313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010318  inc     ebx
0x18001031a  cmp     ebx, [rdi+50h]
0x18001031d  jb      short loc_1800102F9
0x18001031f  mov     r8, r14
0x180010322  lea     rdx, aSremotePrincip; "%sRemote Principal Group SIDs:\n"
0x180010329  mov     rcx, rsi
0x18001032c  mov     rax, rbp
0x18001032f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010334  mov     ebx, r15d
0x180010337  cmp     [rdi+60h], r15d
0x18001033b  jbe     short loc_180010363
0x18001033d  mov     r9, [rdi+68h]
0x180010341  lea     rdx, aSS_0; "%s%s\n"
0x180010348  mov     eax, ebx
0x18001034a  mov     r8, r12
0x18001034d  mov     rcx, rsi
0x180010350  mov     r9, [r9+rax*8]
0x180010354  mov     rax, rbp
0x180010357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001035c  inc     ebx
0x18001035e  cmp     ebx, [rdi+60h]
0x180010361  jb      short loc_18001033D
0x180010363  add     rsp, 38h
0x180010367  pop     r15
0x180010369  pop     r14
0x18001036b  pop     r13
0x18001036d  pop     r12
0x18001036f  pop     rdi
0x180010370  pop     rsi
0x180010371  pop     rbp
0x180010372  pop     rbx
0x180010373  retn
```
