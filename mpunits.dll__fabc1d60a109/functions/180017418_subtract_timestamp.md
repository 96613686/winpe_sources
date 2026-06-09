# subtract_timestamp

- ea: `0x180017418`
- end: `0x180017647`
- name: `subtract_timestamp`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800149b0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000e010`
- `0x18000e4f0`
- `0x18000f040`
- `0x180017418`
- `0x180017650`
- `0x1800177a4`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180017558`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180017558`

## string_xrefs

- `0x18001754d`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall subtract_timestamp(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v5; // r8d
  unsigned int v7; // eax
  int *v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // edx
  int *v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rax
  _OWORD *v14; // rax
  HMODULE ModuleHandleA; // rax
  int v16; // eax
  int v17; // eax
  unsigned __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  int *v20; // [rsp+38h] [rbp-38h]
  unsigned __int64 v21; // [rsp+40h] [rbp-30h] BYREF
  int *v22; // [rsp+48h] [rbp-28h]
  __int128 v23; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-10h] BYREF

  *(_QWORD *)a1 = 271;
  *(_QWORD *)(a1 + 8) = 0;
  v5 = *a3;
  v21 = 271;
  v7 = a3[1];
  v8 = (int *)*((_QWORD *)a3 + 1);
  v22 = 0;
  v19 = 271;
  v20 = 0;
  if ( (_BYTE)v5 == 12 && (v5 & 0x100) == 0 && v8[4] )
  {
    if ( *v8 != -1 )
      ++*v8;
  }
  else
  {
    *((_QWORD *)&v23 + 1) = v8;
    *(_QWORD *)&v23 = __PAIR64__(v7, v5);
    v9 = MintValue_CoerceToTimestampImpl((__int64)v24, (__int64)&v23);
    v8 = *(int **)(v9 + 8);
    v5 = *(_DWORD *)v9;
    v7 = *(_DWORD *)(v9 + 4);
  }
  v20 = v8;
  v10 = *a3;
  v19 = __PAIR64__(v7, v5);
  v11 = (int *)*((_QWORD *)a3 + 1);
  v12 = a3[1];
  if ( (_BYTE)v10 != 12 || (v10 & 0x100) != 0 || v11[4] )
  {
    *(_QWORD *)&v23 = __PAIR64__(v12, v10);
    *((_QWORD *)&v23 + 1) = v11;
    v13 = MintValue_CoerceToIntervalImpl((__int64)v24, (__int64)&v23);
    v11 = *(int **)(v13 + 8);
    v10 = *(_DWORD *)v13;
    v12 = *(_DWORD *)(v13 + 4);
  }
  else if ( *v11 != -1 )
  {
    ++*v11;
  }
  v21 = __PAIR64__(v12, v10);
  v22 = v11;
  if ( (_BYTE)v19 != 0xFF )
  {
    if ( (_BYTE)v10 != 0xFF )
    {
      v23 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v23 = Intlstr_GetString_LoadString(ModuleHandleA, 2054);
      BYTE8(v23) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_19;
    }
    v14 = (_OWORD *)subtract_timestamp_timestamp((__int64)v24, a2, (__int64)&v19);
LABEL_21:
    *(_OWORD *)a1 = *v14;
    goto LABEL_22;
  }
  if ( (_BYTE)v10 != 0xFF )
  {
    v14 = (_OWORD *)subtract_timestamp_interval(v24, a2, &v21);
    goto LABEL_21;
  }
  v23 = *(_OWORD *)a3;
  MintValue_CoerceAndRaiseInvalidCastException_Impl((__int64)v24, (unsigned int *)&v23, 0xCu);
LABEL_19:
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
LABEL_22:
  if ( (char)v19 >= 12 && (v19 & 0x100) == 0 && *v20 != -1 )
  {
    v16 = *v20 - 1;
    *v20 = v16;
    if ( !v16 )
      (*((void (__fastcall **)(unsigned __int64 *))v20 + 1))(&v19);
  }
  if ( (char)v21 >= 12 && (v21 & 0x100) == 0 && *v22 != -1 )
  {
    v17 = *v22 - 1;
    *v22 = v17;
    if ( !v17 )
      (*((void (__fastcall **)(unsigned __int64 *))v22 + 1))(&v21);
  }
  return a1;
}

```

## disassembly

```asm
0x180017418  push    rbp
0x18001741a  push    rbx
0x18001741b  push    rsi
0x18001741c  push    rdi
0x18001741d  push    r13
0x18001741f  mov     rbp, rsp
0x180017422  sub     rsp, 70h
0x180017426  mov     rdi, r8
0x180017429  mov     qword ptr [rcx], 10Fh
0x180017430  mov     qword ptr [rcx+8], 0
0x180017438  mov     rsi, rdx
0x18001743b  mov     r8d, [r8]
0x18001743e  mov     rbx, rcx
0x180017441  mov     [rbp+var_30], 10Fh
0x180017449  mov     r13d, 100h
0x18001744f  mov     eax, [rdi+4]
0x180017452  mov     rdx, [rdi+8]
0x180017456  mov     [rbp+var_28], 0
0x18001745e  mov     [rbp+var_40], 10Fh
0x180017466  mov     [rbp+var_38], 0
0x18001746e  cmp     r8b, 0Ch
0x180017472  jnz     short loc_18001748C
0x180017474  test    r13d, r8d
0x180017477  jnz     short loc_18001748C
0x180017479  cmp     dword ptr [rdx+10h], 0
0x18001747d  jz      short loc_18001748C
0x18001747f  mov     ecx, [rdx]
0x180017481  cmp     ecx, 0FFFFFFFFh
0x180017484  jz      short loc_1800174AE
0x180017486  inc     ecx
0x180017488  mov     [rdx], ecx
0x18001748a  jmp     short loc_1800174AE
0x18001748c  mov     qword ptr [rbp+var_20+8], rdx
0x180017490  lea     rcx, [rbp+var_10]
0x180017494  lea     rdx, [rbp+var_20]
0x180017498  mov     dword ptr [rbp+var_20], r8d
0x18001749c  mov     dword ptr [rbp+var_20+4], eax
0x18001749f  call    MintValue_CoerceToTimestampImpl
0x1800174a4  mov     rdx, [rax+8]
0x1800174a8  mov     r8d, [rax]
0x1800174ab  mov     eax, [rax+4]
0x1800174ae  mov     [rbp+var_38], rdx
0x1800174b2  mov     edx, [rdi]
0x1800174b4  mov     dword ptr [rbp+var_40], r8d
0x1800174b8  mov     r8, [rdi+8]
0x1800174bc  mov     dword ptr [rbp+var_40+4], eax
0x1800174bf  mov     eax, [rdi+4]
0x1800174c2  cmp     dl, 0Ch
0x1800174c5  jnz     short loc_1800174E2
0x1800174c7  test    r13d, edx
0x1800174ca  jnz     short loc_1800174E2
0x1800174cc  cmp     dword ptr [r8+10h], 0
0x1800174d1  jnz     short loc_1800174E2
0x1800174d3  mov     ecx, [r8]
0x1800174d6  cmp     ecx, 0FFFFFFFFh
0x1800174d9  jz      short loc_180017502
0x1800174db  inc     ecx
0x1800174dd  mov     [r8], ecx
0x1800174e0  jmp     short loc_180017502
0x1800174e2  mov     dword ptr [rbp+var_20], edx
0x1800174e5  lea     rcx, [rbp+var_10]
0x1800174e9  lea     rdx, [rbp+var_20]
0x1800174ed  mov     dword ptr [rbp+var_20+4], eax
0x1800174f0  mov     qword ptr [rbp+var_20+8], r8
0x1800174f4  call    MintValue_CoerceToIntervalImpl
0x1800174f9  mov     r8, [rax+8]
0x1800174fd  mov     edx, [rax]
0x1800174ff  mov     eax, [rax+4]
0x180017502  cmp     byte ptr [rbp+var_40], 0FFh
0x180017506  mov     dword ptr [rbp+var_30], edx
0x180017509  mov     dword ptr [rbp+var_30+4], eax
0x18001750c  mov     [rbp+var_28], r8
0x180017510  jnz     short loc_180017545
0x180017512  lea     rcx, [rbp+var_10]
0x180017516  cmp     dl, 0FFh
0x180017519  jnz     short loc_180017534
0x18001751b  movups  xmm0, xmmword ptr [rdi]
0x18001751e  mov     r8d, 0Ch
0x180017524  lea     rdx, [rbp+var_20]
0x180017528  movdqu  [rbp+var_20], xmm0
0x18001752d  call    MintValue_CoerceAndRaiseInvalidCastException_Impl
0x180017532  jmp     short loc_1800175A8
0x180017534  lea     r8, [rbp+var_30]
0x180017538  mov     rdx, rsi
0x18001753b  call    subtract_timestamp_interval
0x180017540  jmp     loc_1800175D4
0x180017545  cmp     dl, 0FFh
0x180017548  jz      short loc_1800175C4
0x18001754a  xorps   xmm0, xmm0
0x18001754d  lea     rcx, ModuleName; "mpunits.dll"
0x180017554  movups  [rbp+var_20], xmm0
0x180017558  call    cs:__imp_GetModuleHandleA
0x18001755e  mov     rcx, rax
0x180017561  mov     edx, 806h
0x180017566  call    _Intlstr_GetString_LoadString
0x18001756b  mov     qword ptr [rbp+var_20], rax
0x18001756f  lea     r9, [rbp+var_20]
0x180017573  mov     byte ptr [rbp+var_20+8], 0
0x180017577  lea     rdx, aMi; "MI"
0x18001757e  movaps  xmm0, [rbp+var_20]
0x180017582  mov     r8d, 5
0x180017588  mov     [rsp+70h+var_48], 0; __int64
0x180017591  movdqa  [rbp+var_20], xmm0
0x180017596  mov     [rsp+70h+var_50], 0; __int64
0x18001759f  lea     ecx, [r8-1]; int
0x1800175a3  call    MI_ReportErrorDetails_ForCustomError
0x1800175a8  xor     edx, edx
0x1800175aa  xor     ecx, ecx
0x1800175ac  mov     eax, 0FFh
0x1800175b1  mov     [rbx+4], edx
0x1800175b4  and     eax, 0FFFFFFFEh
0x1800175b7  mov     [rbx+8], rcx
0x1800175bb  or      eax, 0FEh
0x1800175c0  mov     [rbx], eax
0x1800175c2  jmp     short loc_1800175DB
0x1800175c4  lea     r8, [rbp+var_40]
0x1800175c8  mov     rdx, rsi
0x1800175cb  lea     rcx, [rbp+var_10]
0x1800175cf  call    subtract_timestamp_timestamp
0x1800175d4  movups  xmm0, xmmword ptr [rax]
0x1800175d7  movdqu  xmmword ptr [rbx], xmm0
0x1800175db  cmp     byte ptr [rbp+var_40], 0Ch
0x1800175df  jl      short loc_18001760A
0x1800175e1  test    dword ptr [rbp+var_40], r13d
0x1800175e5  jnz     short loc_18001760A
0x1800175e7  mov     rcx, [rbp+var_38]
0x1800175eb  mov     eax, [rcx]
0x1800175ed  cmp     eax, 0FFFFFFFFh
0x1800175f0  jz      short loc_18001760A
0x1800175f2  sub     eax, 1
0x1800175f5  mov     [rcx], eax
0x1800175f7  jnz     short loc_18001760A
0x1800175f9  mov     rax, [rbp+var_38]
0x1800175fd  lea     rcx, [rbp+var_40]
0x180017601  mov     rax, [rax+8]
0x180017605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001760a  cmp     byte ptr [rbp+var_30], 0Ch
0x18001760e  jl      short loc_180017639
0x180017610  test    dword ptr [rbp+var_30], r13d
0x180017614  jnz     short loc_180017639
0x180017616  mov     rcx, [rbp+var_28]
0x18001761a  mov     eax, [rcx]
0x18001761c  cmp     eax, 0FFFFFFFFh
0x18001761f  jz      short loc_180017639
0x180017621  sub     eax, 1
0x180017624  mov     [rcx], eax
0x180017626  jnz     short loc_180017639
0x180017628  mov     rax, [rbp+var_28]
0x18001762c  lea     rcx, [rbp+var_30]
0x180017630  mov     rax, [rax+8]
0x180017634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017639  mov     rax, rbx
0x18001763c  add     rsp, 70h
0x180017640  pop     r13
0x180017642  pop     rdi
0x180017643  pop     rsi
0x180017644  pop     rbx
0x180017645  pop     rbp
0x180017646  retn
```
