# Loader_RxC_Invoke_GetDate

- ea: `0x1800021a0`
- end: `0x18000253e`
- name: `Loader_RxC_Invoke_GetDate`
- size: `926`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1800021a0`
- `0x18000416c`
- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x180008fb0`
- `0x1800122a4`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180002249`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800022bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800024dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180002249`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800022bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800024dc`

## string_xrefs

- `0x18000223d`: `mpunits.dll`
- `0x1800022b1`: `mpunits.dll`
- `0x1800024d0`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_RxC_Invoke_GetDate(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  char v8; // r12
  __m128i v9; // xmm1
  __int128 v10; // xmm0
  HMODULE ModuleHandleA; // rax
  unsigned int v12; // ebx
  __int64 result; // rax
  HMODULE v14; // rax
  char v15; // r14
  const wchar_t *v16; // rcx
  char v17; // r15
  char v18; // r9
  char v19; // dl
  char v20; // r10
  char v21; // r8
  char v22; // cl
  HMODULE v23; // rax
  __int128 v24; // xmm1
  unsigned int v25; // [rsp+60h] [rbp-81h] BYREF
  unsigned int v26; // [rsp+64h] [rbp-7Dh] BYREF
  unsigned int v27; // [rsp+68h] [rbp-79h] BYREF
  unsigned int v28; // [rsp+6Ch] [rbp-75h] BYREF
  int v29; // [rsp+70h] [rbp-71h] BYREF
  int v30; // [rsp+74h] [rbp-6Dh] BYREF
  int v31; // [rsp+78h] [rbp-69h] BYREF
  __int128 v32; // [rsp+80h] [rbp-61h] BYREF
  __int128 v33; // [rsp+90h] [rbp-51h]
  unsigned int v34; // [rsp+A0h] [rbp-41h]
  __m128i v35; // [rsp+A8h] [rbp-39h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-29h]
  int v37; // [rsp+C8h] [rbp-19h]

  v31 = 0;
  v30 = 0;
  v37 = 0;
  v8 = *(_BYTE *)(a7 + 140);
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v32 = 0;
  v33 = 0;
  if ( v8 )
  {
    v9 = *(__m128i *)(a7 + 104);
    v10 = *(_OWORD *)(a7 + 120);
    v37 = *(_DWORD *)(a7 + 136);
    v35 = v9;
    v36 = v10;
    if ( !_mm_cvtsi128_si32(v9) )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2108, L"Date");
LABEL_4:
      v12 = 4;
      result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_12;
    }
    if ( !(unsigned __int8)Timestamp_IsValid((char *)v35.m128i_i64 + 4) )
    {
      v14 = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(v14, 2135, L"Date");
      goto LABEL_4;
    }
  }
  v15 = *(_BYTE *)(a7 + 148);
  if ( v15 )
  {
    v31 = *(_DWORD *)(a7 + 144);
    if ( (unsigned int)(v31 - 1) > 0x270E )
    {
      v16 = L"Year";
LABEL_10:
      result = MI_ReportErrorDetails_OutOfRangeParameter(v16);
LABEL_11:
      v12 = 4;
      goto LABEL_12;
    }
  }
  v17 = *(_BYTE *)(a7 + 156);
  if ( v17 )
  {
    v30 = *(_DWORD *)(a7 + 152);
    if ( (unsigned int)(v30 - 1) > 0xB )
    {
      v16 = L"Month";
      goto LABEL_10;
    }
  }
  v18 = *(_BYTE *)(a7 + 164);
  if ( v18 )
  {
    v29 = *(_DWORD *)(a7 + 160);
    if ( (unsigned int)(v29 - 1) > 0x1E )
    {
      v16 = L"Day";
      goto LABEL_10;
    }
  }
  v19 = *(_BYTE *)(a7 + 172);
  if ( v19 )
  {
    v28 = *(_DWORD *)(a7 + 168);
    if ( v28 > 0x17 )
    {
      v16 = L"Hour";
      goto LABEL_10;
    }
  }
  v20 = *(_BYTE *)(a7 + 180);
  if ( v20 )
  {
    v27 = *(_DWORD *)(a7 + 176);
    if ( v27 > 0x3B )
    {
      v16 = L"Minute";
      goto LABEL_10;
    }
  }
  v21 = *(_BYTE *)(a7 + 188);
  if ( v21 )
  {
    v26 = *(_DWORD *)(a7 + 184);
    if ( v26 > 0x3B )
    {
      v16 = L"Second";
      goto LABEL_10;
    }
  }
  v22 = *(_BYTE *)(a7 + 196);
  if ( v22 )
  {
    v25 = *(_DWORD *)(a7 + 192);
    if ( v25 > 0x3E7 )
    {
      v16 = L"Millisecond";
      goto LABEL_10;
    }
  }
  result = GetDate(
             (unsigned __int64)&v35 & -(__int64)(v8 != 0),
             (unsigned __int64)&v31 & -(__int64)(v15 != 0),
             (unsigned __int64)&v30 & -(__int64)(v17 != 0),
             (unsigned __int64)&v29 & -(__int64)(v18 != 0),
             (unsigned __int64)&v28 & -(__int64)(v19 != 0),
             (unsigned __int64)&v27 & -(__int64)(v20 != 0),
             (unsigned __int64)&v26 & -(__int64)(v21 != 0),
             (unsigned __int64)&v25 & -(__int64)(v22 != 0),
             (__int64)&v32);
  v12 = result;
  if ( !(_DWORD)result )
  {
    if ( !(unsigned __int8)Timestamp_IsValid((char *)&v32 + 4) )
    {
      v23 = GetModuleHandleA("mpunits.dll");
      Intlstr_GetString_LoadString(v23, 2109);
      goto LABEL_4;
    }
    result = v34;
    *(_BYTE *)(a7 + 100) = 1;
    v24 = v33;
    *(_OWORD *)(a7 + 64) = v32;
    *(_OWORD *)(a7 + 80) = v24;
    *(_DWORD *)(a7 + 96) = result;
    if ( !a2 )
      goto LABEL_11;
    result = *a2;
    if ( !*a2 )
      goto LABEL_11;
    result = (*(__int64 (__fastcall **)(__int64 *, __int64))(result + 8))(a2, a7);
    v12 = result;
  }
LABEL_12:
  if ( a2 )
  {
    result = *a2;
    if ( *a2 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800021a0  push    rbp
0x1800021a2  push    rbx
0x1800021a3  push    rsi
0x1800021a4  push    rdi
0x1800021a5  push    r12
0x1800021a7  push    r13
0x1800021a9  push    r14
0x1800021ab  push    r15
0x1800021ad  lea     rbp, [rsp-7]
0x1800021b2  sub     rsp, 0E8h
0x1800021b9  mov     rax, cs:__security_cookie
0x1800021c0  xor     rax, rsp
0x1800021c3  mov     [rbp+3Fh+var_50], rax
0x1800021c7  mov     rdi, [rbp+3Fh+arg_30]
0x1800021cb  xor     r13d, r13d
0x1800021ce  xorps   xmm0, xmm0
0x1800021d1  mov     [rbp+3Fh+var_A8], r13d
0x1800021d5  xor     eax, eax
0x1800021d7  mov     [rbp+3Fh+var_AC], r13d
0x1800021db  mov     rsi, rdx
0x1800021de  mov     [rbp+3Fh+var_58], eax
0x1800021e1  mov     r12b, [rdi+8Ch]
0x1800021e8  mov     [rbp+3Fh+var_B0], r13d
0x1800021ec  mov     [rbp+3Fh+var_B4], r13d
0x1800021f0  mov     [rbp+3Fh+var_B8], r13d
0x1800021f4  mov     [rbp+3Fh+var_BC], r13d
0x1800021f8  mov     [rsp+120h+var_C0], r13d
0x1800021fd  mov     [rbp+3Fh+var_80], eax
0x180002200  movups  [rbp+3Fh+var_78], xmm0
0x180002204  movups  [rbp+3Fh+var_68], xmm0
0x180002208  movups  [rbp+3Fh+var_A0], xmm0
0x18000220c  movups  [rbp+3Fh+var_90], xmm0
0x180002210  test    r12b, r12b
0x180002213  jz      loc_1800022E0
0x180002219  movups  xmm1, xmmword ptr [rdi+68h]
0x18000221d  mov     eax, [rdi+88h]
0x180002223  movups  xmm0, xmmword ptr [rdi+78h]
0x180002227  mov     [rbp+3Fh+var_58], eax
0x18000222a  movd    eax, xmm1
0x18000222e  movups  [rbp+3Fh+var_78], xmm1
0x180002232  movups  [rbp+3Fh+var_68], xmm0
0x180002236  test    eax, eax
0x180002238  jnz     short loc_1800022A1
0x18000223a  xorps   xmm0, xmm0
0x18000223d  lea     rcx, ModuleName; "mpunits.dll"
0x180002244  movups  [rsp+120h+var_D0], xmm0
0x180002249  call    cs:__imp_GetModuleHandleA
0x18000224f  lea     r8, aDate; "Date"
0x180002256  mov     edx, 83Ch
0x18000225b  mov     rcx, rax
0x18000225e  call    _Intlstr_FormatString_FormatMessage
0x180002263  mov     byte ptr [rsp+120h+var_D0+8], 1
0x180002268  mov     qword ptr [rsp+120h+var_D0], rax
0x18000226d  lea     r9, [rsp+120h+var_D0]
0x180002272  movaps  xmm0, [rsp+120h+var_D0]
0x180002277  lea     rdx, aMi; "MI"
0x18000227e  mov     r8d, 5
0x180002284  mov     [rsp+120h+var_F8], r13; __int64
0x180002289  movdqa  [rsp+120h+var_D0], xmm0
0x18000228f  mov     [rsp+120h+var_100], r13; __int64
0x180002294  lea     ebx, [r8-1]
0x180002298  mov     ecx, ebx; int
0x18000229a  call    MI_ReportErrorDetails_ForCustomError
0x18000229f  jmp     short loc_18000230F
0x1800022a1  lea     rcx, [rbp+3Fh+var_78+4]
0x1800022a5  call    Timestamp_IsValid
0x1800022aa  test    al, al
0x1800022ac  jnz     short loc_1800022E0
0x1800022ae  xorps   xmm0, xmm0
0x1800022b1  lea     rcx, ModuleName; "mpunits.dll"
0x1800022b8  movups  [rsp+120h+var_D0], xmm0
0x1800022bd  call    cs:__imp_GetModuleHandleA
0x1800022c3  lea     r9, aGetDate; "Get-Date"
0x1800022ca  mov     edx, 857h
0x1800022cf  mov     rcx, rax
0x1800022d2  lea     r8, aDate; "Date"
0x1800022d9  call    _Intlstr_FormatString_FormatMessage
0x1800022de  jmp     short loc_180002263
0x1800022e0  mov     r14b, [rdi+94h]
0x1800022e7  test    r14b, r14b
0x1800022ea  jz      short loc_180002349
0x1800022ec  mov     eax, [rdi+90h]
0x1800022f2  mov     [rbp+3Fh+var_A8], eax
0x1800022f5  dec     eax
0x1800022f7  cmp     eax, 270Eh
0x1800022fc  jbe     short loc_180002349
0x1800022fe  lea     rcx, aYear_0; "Year"
0x180002305  call    MI_ReportErrorDetails_OutOfRangeParameter
0x18000230a  mov     ebx, 4
0x18000230f  test    rsi, rsi
0x180002312  jz      short loc_180002329
0x180002314  mov     rax, [rsi]
0x180002317  test    rax, rax
0x18000231a  jz      short loc_180002329
0x18000231c  mov     rax, [rax]
0x18000231f  mov     edx, ebx
0x180002321  mov     rcx, rsi
0x180002324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002329  mov     rcx, [rbp+3Fh+var_50]
0x18000232d  xor     rcx, rsp; StackCookie
0x180002330  call    __security_check_cookie
0x180002335  add     rsp, 0E8h
0x18000233c  pop     r15
0x18000233e  pop     r14
0x180002340  pop     r13
0x180002342  pop     r12
0x180002344  pop     rdi
0x180002345  pop     rsi
0x180002346  pop     rbx
0x180002347  pop     rbp
0x180002348  retn
0x180002349  mov     r15b, [rdi+9Ch]
0x180002350  test    r15b, r15b
0x180002353  jz      short loc_18000236E
0x180002355  mov     eax, [rdi+98h]
0x18000235b  mov     [rbp+3Fh+var_AC], eax
0x18000235e  dec     eax
0x180002360  cmp     eax, 0Bh
0x180002363  jbe     short loc_18000236E
0x180002365  lea     rcx, aMonth; "Month"
0x18000236c  jmp     short loc_180002305
0x18000236e  mov     r9b, [rdi+0A4h]
0x180002375  test    r9b, r9b
0x180002378  jz      short loc_180002396
0x18000237a  mov     eax, [rdi+0A0h]
0x180002380  mov     [rbp+3Fh+var_B0], eax
0x180002383  dec     eax
0x180002385  cmp     eax, 1Eh
0x180002388  jbe     short loc_180002396
0x18000238a  lea     rcx, aDay_0; "Day"
0x180002391  jmp     loc_180002305
0x180002396  mov     dl, [rdi+0ACh]
0x18000239c  test    dl, dl
0x18000239e  jz      short loc_1800023BA
0x1800023a0  mov     eax, [rdi+0A8h]
0x1800023a6  mov     [rbp+3Fh+var_B4], eax
0x1800023a9  cmp     eax, 17h
0x1800023ac  jbe     short loc_1800023BA
0x1800023ae  lea     rcx, aHour; "Hour"
0x1800023b5  jmp     loc_180002305
0x1800023ba  mov     r10b, [rdi+0B4h]
0x1800023c1  test    r10b, r10b
0x1800023c4  jz      short loc_1800023E0
0x1800023c6  mov     eax, [rdi+0B0h]
0x1800023cc  mov     [rbp+3Fh+var_B8], eax
0x1800023cf  cmp     eax, 3Bh ; ';'
0x1800023d2  jbe     short loc_1800023E0
0x1800023d4  lea     rcx, aMinute_0; "Minute"
0x1800023db  jmp     loc_180002305
0x1800023e0  mov     r8b, [rdi+0BCh]
0x1800023e7  test    r8b, r8b
0x1800023ea  jz      short loc_180002406
0x1800023ec  mov     eax, [rdi+0B8h]
0x1800023f2  mov     [rbp+3Fh+var_BC], eax
0x1800023f5  cmp     eax, 3Bh ; ';'
0x1800023f8  jbe     short loc_180002406
0x1800023fa  lea     rcx, aSecond_0; "Second"
0x180002401  jmp     loc_180002305
0x180002406  mov     cl, [rdi+0C4h]
0x18000240c  test    cl, cl
0x18000240e  jz      short loc_18000242D
0x180002410  mov     eax, [rdi+0C0h]
0x180002416  mov     [rsp+120h+var_C0], eax
0x18000241a  cmp     eax, 3E7h
0x18000241f  jbe     short loc_18000242D
0x180002421  lea     rcx, aMillisecond; "Millisecond"
0x180002428  jmp     loc_180002305
0x18000242d  neg     cl
0x18000242f  lea     rax, [rsp+120h+var_C0]
0x180002434  lea     rcx, [rbp+3Fh+var_B4]
0x180002438  sbb     rbx, rbx
0x18000243b  and     rbx, rax
0x18000243e  lea     rax, [rbp+3Fh+var_BC]
0x180002442  neg     r8b
0x180002445  sbb     r11, r11
0x180002448  and     r11, rax
0x18000244b  lea     rax, [rbp+3Fh+var_B8]
0x18000244f  neg     r10b
0x180002452  sbb     r10, r10
0x180002455  and     r10, rax
0x180002458  neg     dl
0x18000245a  sbb     rax, rax
0x18000245d  and     rax, rcx
0x180002460  lea     rcx, [rbp+3Fh+var_B0]
0x180002464  neg     r9b
0x180002467  sbb     r9, r9
0x18000246a  and     r9, rcx
0x18000246d  lea     rcx, [rbp+3Fh+var_AC]
0x180002471  neg     r15b
0x180002474  sbb     r8, r8
0x180002477  and     r8, rcx
0x18000247a  lea     rcx, [rbp+3Fh+var_A8]
0x18000247e  neg     r14b
0x180002481  lea     r14, [rbp+3Fh+var_78]
0x180002485  sbb     rdx, rdx
0x180002488  and     rdx, rcx
0x18000248b  neg     r12b
0x18000248e  sbb     rcx, rcx
0x180002491  and     rcx, r14
0x180002494  lea     r14, [rbp+3Fh+var_A0]
0x180002498  mov     [rsp+120h+var_E0], r14
0x18000249d  mov     [rsp+120h+var_E8], rbx
0x1800024a2  mov     [rsp+120h+var_F0], r11
0x1800024a7  mov     [rsp+120h+var_F8], r10
0x1800024ac  mov     [rsp+120h+var_100], rax
0x1800024b1  call    GetDate
0x1800024b6  mov     ebx, eax
0x1800024b8  test    eax, eax
0x1800024ba  jnz     loc_18000230F
0x1800024c0  lea     rcx, [rbp+3Fh+var_A0+4]
0x1800024c4  call    Timestamp_IsValid
0x1800024c9  test    al, al
0x1800024cb  jnz     short loc_1800024F9
0x1800024cd  xorps   xmm0, xmm0
0x1800024d0  lea     rcx, ModuleName; "mpunits.dll"
0x1800024d7  movups  [rsp+120h+var_D0], xmm0
0x1800024dc  call    cs:__imp_GetModuleHandleA
0x1800024e2  mov     rcx, rax
0x1800024e5  mov     edx, 83Dh
0x1800024ea  call    _Intlstr_GetString_LoadString
0x1800024ef  mov     byte ptr [rsp+120h+var_D0+8], r13b
0x1800024f4  jmp     loc_180002268
0x1800024f9  mov     eax, [rbp+3Fh+var_80]
0x1800024fc  mov     byte ptr [rdi+64h], 1
0x180002500  movups  xmm0, [rbp+3Fh+var_A0]
0x180002504  movups  xmm1, [rbp+3Fh+var_90]
0x180002508  movups  xmmword ptr [rdi+40h], xmm0
0x18000250c  movups  xmmword ptr [rdi+50h], xmm1
0x180002510  mov     [rdi+60h], eax
0x180002513  test    rsi, rsi
0x180002516  jz      loc_18000230A
0x18000251c  mov     rax, [rsi]
0x18000251f  test    rax, rax
0x180002522  jz      loc_18000230A
0x180002528  mov     rax, [rax+8]
0x18000252c  mov     rdx, rdi
0x18000252f  mov     rcx, rsi
0x180002532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002537  mov     ebx, eax
0x180002539  jmp     loc_18000230F
```
