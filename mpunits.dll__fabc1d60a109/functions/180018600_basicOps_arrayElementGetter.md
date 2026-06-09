# basicOps_arrayElementGetter

- ea: `0x180018600`
- end: `0x180018828`
- name: `basicOps_arrayElementGetter`
- size: `552`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000e010`
- `0x18000ec70`
- `0x180010570`
- `0x180018600`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018758`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018765`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018780`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018758`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018765`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180018780`

## string_xrefs

- `0x180018748`: `mpunits.dll`
- `0x180018775`: `mpunits.dll`

## pseudocode

```c
__m128i *__fastcall basicOps_arrayElementGetter(__m128i *a1, __int64 a2, __m128i *a3)
{
  __m128i v3; // xmm0
  __int64 v6; // rax
  __m128i v7; // xmm0
  __int8 v8; // dl
  __int64 v9; // xmm0_8
  __int64 v10; // xmm0_8
  __int64 v11; // r8
  __int64 v12; // rcx
  __m128i v13; // xmm6
  int v14; // eax
  bool v15; // zf
  HMODULE ModuleHandleA; // rax
  __int64 v17; // rdx
  int v18; // eax
  __m128i v20; // [rsp+30h] [rbp-19h] BYREF
  __m128i v21; // [rsp+40h] [rbp-9h] BYREF
  __m128i v22; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp+17h] BYREF

  v3 = *a3;
  v20 = (__m128i)0x10FuLL;
  v22 = v3;
  v21 = v3;
  v6 = MintValue_CoerceToSint64(v23, &v21);
  if ( *(_BYTE *)v6 == 0xFF )
  {
    v7 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException_Impl(v23, &v22, 8);
    v8 = _mm_cvtsi128_si32(v7);
  }
  else
  {
    v9 = *(_QWORD *)(v6 + 1);
    v8 = *(_BYTE *)v6;
    *(__int32 *)((char *)&v21.m128i_i32[2] + 1) = *(_DWORD *)(v6 + 9);
    *(__int16 *)((char *)&v21.m128i_i16[6] + 1) = *(_WORD *)(v6 + 13);
    v21.m128i_i8[15] = *(_BYTE *)(v6 + 15);
    v21.m128i_i8[0] = v8;
    *(__int64 *)((char *)v21.m128i_i64 + 1) = v9;
    v7 = v21;
  }
  v20 = v7;
  if ( v8 == -2 )
    goto LABEL_24;
  if ( *(_BYTE *)a2 == 0xFF || (*(_DWORD *)a2 & 0x100) != 0 )
  {
    v21 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v17 = 2072;
LABEL_23:
    v21.m128i_i64[0] = Intlstr_GetString_LoadString(ModuleHandleA, v17);
    v21.m128i_i8[8] = 0;
    v22 = v21;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_24;
  }
  if ( (*(_BYTE *)a2 & 0xF0) != 0x10 )
  {
    v15 = *(_BYTE *)a2 == 13;
    v21 = 0;
    if ( v15 )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v17 = 2073;
    }
    else
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v17 = 2074;
    }
    goto LABEL_23;
  }
  v10 = _mm_srli_si128(v7, 8).m128i_u64[0];
  v11 = v10;
  v12 = *(unsigned int *)(*(_QWORD *)(a2 + 8) + 24LL);
  if ( v10 < 0 )
  {
    v11 = v12 + v10;
    if ( v12 + v10 >= 0 )
      goto LABEL_10;
LABEL_18:
    v21 = (__m128i)0x10FuLL;
    v13 = (__m128i)0x10FuLL;
LABEL_11:
    if ( v20.m128i_i8[0] >= 12 && (v20.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v20.m128i_i64[1] != -1 )
    {
      v14 = *(_DWORD *)v20.m128i_i64[1] - 1;
      *(_DWORD *)v20.m128i_i64[1] = v14;
      if ( !v14 )
        (*(void (__fastcall **)(__m128i *))(v20.m128i_i64[1] + 8))(&v20);
    }
    *a1 = v13;
    return a1;
  }
  if ( v10 >= v12 )
    goto LABEL_18;
LABEL_10:
  v13 = *(__m128i *)MintValue_GetArrayElement(v23, a2, v11);
  if ( (unsigned __int8)_mm_cvtsi128_si32(v13) != 0xFE )
    goto LABEL_11;
LABEL_24:
  if ( v20.m128i_i8[0] >= 12 && (v20.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v20.m128i_i64[1] != -1 )
  {
    v18 = *(_DWORD *)v20.m128i_i64[1] - 1;
    *(_DWORD *)v20.m128i_i64[1] = v18;
    if ( !v18 )
      (*(void (__fastcall **)(__m128i *))(v20.m128i_i64[1] + 8))(&v20);
  }
  a1->m128i_i32[1] = 0;
  a1->m128i_i64[1] = 0;
  a1->m128i_i32[0] = 254;
  return a1;
}

```

## disassembly

```asm
0x180018600  push    rbp
0x180018602  push    rbx
0x180018603  push    rsi
0x180018604  push    rdi
0x180018605  lea     rbp, [rsp-3Fh]
0x18001860a  sub     rsp, 88h
0x180018611  movups  xmm0, xmmword ptr [r8]
0x180018615  mov     rdi, rdx
0x180018618  mov     rbx, rcx
0x18001861b  lea     rdx, [rbp+57h+var_60]
0x18001861f  movaps  [rsp+0A0h+var_30], xmm6
0x180018624  xor     esi, esi
0x180018626  mov     qword ptr [rbp+57h+var_70], 10Fh
0x18001862e  lea     rcx, [rbp+57h+var_40]
0x180018632  mov     qword ptr [rbp+57h+var_70+8], rsi
0x180018636  movdqu  [rbp+57h+var_50], xmm0
0x18001863b  movdqu  [rbp+57h+var_60], xmm0
0x180018640  call    MintValue_CoerceToSint64
0x180018645  mov     rcx, rax
0x180018648  cmp     byte ptr [rax], 0FFh
0x18001864b  jnz     short loc_180018667
0x18001864d  lea     r8d, [rsi+8]
0x180018651  lea     rdx, [rbp+57h+var_50]
0x180018655  lea     rcx, [rbp+57h+var_40]
0x180018659  call    MintValue_CoerceAndRaiseInvalidCastException_Impl
0x18001865e  movups  xmm0, xmmword ptr [rax]
0x180018661  movd    edx, xmm0
0x180018665  jmp     short loc_18001868E
0x180018667  movsd   xmm0, qword ptr [rax+1]
0x18001866c  mov     dl, [rax]
0x18001866e  mov     eax, [rax+9]
0x180018671  mov     dword ptr [rbp+57h+var_60+9], eax
0x180018674  movzx   eax, word ptr [rcx+0Dh]
0x180018678  mov     word ptr [rbp+57h+var_60+0Dh], ax
0x18001867c  mov     al, [rcx+0Fh]
0x18001867f  mov     byte ptr [rbp+57h+var_60+0Fh], al
0x180018682  mov     byte ptr [rbp+57h+var_60], dl
0x180018685  movsd   qword ptr [rbp+57h+var_60+1], xmm0
0x18001868a  movaps  xmm0, [rbp+57h+var_60]
0x18001868e  movdqa  [rbp+57h+var_70], xmm0
0x180018693  cmp     dl, 0FEh
0x180018696  jz      loc_1800187C8
0x18001869c  cmp     byte ptr [rdi], 0FFh
0x18001869f  jz      loc_180018772
0x1800186a5  test    dword ptr [rdi], 100h
0x1800186ab  jnz     loc_180018772
0x1800186b1  mov     al, [rdi]
0x1800186b3  and     al, 0F0h
0x1800186b5  cmp     al, 10h
0x1800186b7  jnz     loc_180018745
0x1800186bd  mov     rax, [rdi+8]
0x1800186c1  psrldq  xmm0, 8
0x1800186c6  movq    r8, xmm0
0x1800186cb  mov     ecx, [rax+18h]
0x1800186ce  test    r8, r8
0x1800186d1  jns     short loc_18001872E
0x1800186d3  add     r8, rcx
0x1800186d6  js      short loc_180018733
0x1800186d8  mov     rdx, rdi
0x1800186db  lea     rcx, [rbp+57h+var_40]
0x1800186df  call    MintValue_GetArrayElement
0x1800186e4  movups  xmm6, xmmword ptr [rax]
0x1800186e7  movd    eax, xmm6
0x1800186eb  cmp     al, 0FEh
0x1800186ed  jz      loc_1800187C8
0x1800186f3  cmp     byte ptr [rbp+57h+var_70], 0Ch
0x1800186f7  jl      short loc_180018725
0x1800186f9  test    dword ptr [rbp+57h+var_70], 100h
0x180018700  jnz     short loc_180018725
0x180018702  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x180018706  mov     eax, [rcx]
0x180018708  cmp     eax, 0FFFFFFFFh
0x18001870b  jz      short loc_180018725
0x18001870d  sub     eax, 1
0x180018710  mov     [rcx], eax
0x180018712  jnz     short loc_180018725
0x180018714  mov     rax, qword ptr [rbp+57h+var_70+8]
0x180018718  lea     rcx, [rbp+57h+var_70]
0x18001871c  mov     rax, [rax+8]
0x180018720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018725  movdqu  xmmword ptr [rbx], xmm6
0x180018729  jmp     loc_180018814
0x18001872e  cmp     r8, rcx
0x180018731  jl      short loc_1800186D8
0x180018733  mov     qword ptr [rbp+57h+var_60], 10Fh
0x18001873b  mov     qword ptr [rbp+57h+var_60+8], rsi
0x18001873f  movaps  xmm6, [rbp+57h+var_60]
0x180018743  jmp     short loc_1800186F3
0x180018745  cmp     byte ptr [rdi], 0Dh
0x180018748  lea     rcx, ModuleName; "mpunits.dll"
0x18001874f  xorps   xmm0, xmm0
0x180018752  movups  [rbp+57h+var_60], xmm0
0x180018756  jnz     short loc_180018765
0x180018758  call    cs:__imp_GetModuleHandleA
0x18001875e  mov     edx, 819h
0x180018763  jmp     short loc_18001878B
0x180018765  call    cs:__imp_GetModuleHandleA
0x18001876b  mov     edx, 81Ah
0x180018770  jmp     short loc_18001878B
0x180018772  xorps   xmm0, xmm0
0x180018775  lea     rcx, ModuleName; "mpunits.dll"
0x18001877c  movups  [rbp+57h+var_60], xmm0
0x180018780  call    cs:__imp_GetModuleHandleA
0x180018786  mov     edx, 818h
0x18001878b  mov     rcx, rax
0x18001878e  call    _Intlstr_GetString_LoadString
0x180018793  mov     r8d, 5
0x180018799  mov     qword ptr [rbp+57h+var_60], rax
0x18001879d  mov     byte ptr [rbp+57h+var_60+8], sil
0x1800187a1  lea     r9, [rbp+57h+var_50]
0x1800187a5  movaps  xmm0, [rbp+57h+var_60]
0x1800187a9  lea     rdx, aMi; "MI"
0x1800187b0  mov     [rsp+0A0h+var_78], rsi; __int64
0x1800187b5  lea     ecx, [r8-1]; int
0x1800187b9  mov     [rsp+0A0h+var_80], rsi; __int64
0x1800187be  movdqa  [rbp+57h+var_50], xmm0
0x1800187c3  call    MI_ReportErrorDetails_ForCustomError
0x1800187c8  cmp     byte ptr [rbp+57h+var_70], 0Ch
0x1800187cc  jl      short loc_1800187FA
0x1800187ce  test    dword ptr [rbp+57h+var_70], 100h
0x1800187d5  jnz     short loc_1800187FA
0x1800187d7  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x1800187db  mov     eax, [rcx]
0x1800187dd  cmp     eax, 0FFFFFFFFh
0x1800187e0  jz      short loc_1800187FA
0x1800187e2  sub     eax, 1
0x1800187e5  mov     [rcx], eax
0x1800187e7  jnz     short loc_1800187FA
0x1800187e9  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1800187ed  lea     rcx, [rbp+57h+var_70]
0x1800187f1  mov     rax, [rax+8]
0x1800187f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187fa  xor     edx, edx
0x1800187fc  xor     ecx, ecx
0x1800187fe  mov     eax, 0FFh
0x180018803  mov     [rbx+4], edx
0x180018806  and     eax, 0FFFFFFFEh
0x180018809  mov     [rbx+8], rcx
0x18001880d  or      eax, 0FEh
0x180018812  mov     [rbx], eax
0x180018814  movaps  xmm6, [rsp+0A0h+var_30]
0x180018819  mov     rax, rbx
0x18001881c  add     rsp, 88h
0x180018823  pop     rdi
0x180018824  pop     rsi
0x180018825  pop     rbx
0x180018826  pop     rbp
0x180018827  retn
```
