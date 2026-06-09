# RxcMinMaxCompare

- ea: `0x180032038`
- end: `0x18003249f`
- name: `RxcMinMaxCompare`
- size: `1127`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032660`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x180031674`
- `0x180032038`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003222b`
- `msvcrt!_wcsicmp` at `0x18003222b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003212e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003232a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180032372`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180032449`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003212e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003232a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180032372`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180032449`

## string_xrefs

- `0x180032123`: `mpunits.dll`
- `0x18003231e`: `mpunits.dll`
- `0x18003235f`: `mpunits.dll`
- `0x18003243d`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall RxcMinMaxCompare(__int64 a1, __int64 *a2, __int64 *a3, _DWORD *a4)
{
  unsigned int v4; // r15d
  __int64 i; // rcx
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 *v10; // rdi
  __int64 v11; // r12
  unsigned int v12; // ebx
  HMODULE v13; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 result; // rax
  __int64 *v17; // rdx
  __int64 v18; // r9
  __int64 v19; // r8
  __int128 v20; // xmm2
  int v21; // eax
  __int128 v22; // xmm3
  HMODULE v23; // rax
  wchar_t *v24; // rdi
  HMODULE v25; // rax
  __int128 v26; // xmm0
  __int64 v27; // rcx
  __int128 v28; // xmm1
  __int64 v29; // r10
  int v30; // eax
  __int64 v31; // rdx
  __int64 *v32; // rax
  __int128 v33; // xmm0
  HMODULE ModuleHandleA; // rax
  unsigned int v35; // [rsp+50h] [rbp-89h] BYREF
  int v36; // [rsp+54h] [rbp-85h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-81h] BYREF
  wchar_t *String1[2]; // [rsp+60h] [rbp-79h] BYREF
  __int64 *v39; // [rsp+70h] [rbp-69h] BYREF
  __int128 v40; // [rsp+78h] [rbp-61h]
  __int128 v41; // [rsp+88h] [rbp-51h]
  unsigned int v42; // [rsp+98h] [rbp-41h] BYREF
  __int64 v43; // [rsp+9Ch] [rbp-3Dh] BYREF
  int v44; // [rsp+A4h] [rbp-35h]
  __int64 *v45; // [rsp+A8h] [rbp-31h] BYREF
  __int128 v46; // [rsp+B0h] [rbp-29h]
  __int128 v47; // [rsp+C0h] [rbp-19h]
  unsigned int v48; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v49; // [rsp+D4h] [rbp-5h] BYREF
  int v50; // [rsp+DCh] [rbp+3h]

  v4 = 0;
  for ( i = 0; i != 2; ++i )
  {
    v8 = 56 * i;
    *(__int64 *)((char *)&v43 + v8 + 4) = 0;
  }
  v9 = *((unsigned int *)a2 + 10);
  if ( (_DWORD)v9 != 15
    || *((_DWORD *)a3 + 10) != 15
    || (*((_DWORD *)a2 + 11) & 0x20000000) != 0
    || (*((_DWORD *)a3 + 11) & 0x20000000) != 0 )
  {
    v26 = *(_OWORD *)(a2 + 1);
    v27 = *(__int64 *)((char *)a2 + 44);
    v28 = *(_OWORD *)(a2 + 3);
    v29 = *((unsigned int *)a3 + 10);
    v39 = (__int64 *)*a2;
    v30 = *((_DWORD *)a2 + 13);
    v31 = *(__int64 *)((char *)a3 + 44);
    v44 = v30;
    v32 = (__int64 *)*a3;
    v40 = v26;
    v43 = v27;
    v45 = v32;
    v50 = *((_DWORD *)a3 + 13);
    v42 = v9;
    v48 = v29;
    v49 = v31;
    v33 = *(_OWORD *)(a3 + 1);
    v41 = v28;
    v46 = v33;
    v47 = *(_OWORD *)(a3 + 3);
    if ( (((unsigned int)v31 | (unsigned int)v27) & 0x20000000) == 0
      && ((unsigned int)v9 >= 0x10 || (unsigned int)v29 >= 0x10 || dword_18005F0E0[v9] != dword_18005F0E0[v29]) )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_GetString_LoadString(ModuleHandleA, 2101);
      goto LABEL_14;
    }
    return InvokeComparisonBuiltin(a1, &v39, a3, a4);
  }
  v10 = (__int64 *)*a2;
  v35 = 0;
  v36 = 0;
  if ( !v10 || !*v10 )
    return 4;
  v11 = *a3;
  v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v10 + 56))(v10, &v35);
  if ( v12 )
    return v12;
  if ( !*v10 )
    return 4;
  v12 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v10 + 56))(v10, &v36);
  if ( v12 )
    return v12;
  if ( v36 != v35 )
  {
    *(_OWORD *)String1 = 0;
    v13 = GetModuleHandleA("mpunits.dll");
    String1[0] = (wchar_t *)Intlstr_GetString_LoadString(v13, 2099);
    LOBYTE(String1[1]) = 0;
LABEL_14:
    v12 = 4;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    return v12;
  }
  if ( v35 )
  {
    while ( 1 )
    {
      v14 = *v10;
      String1[0] = 0;
      String2 = 0;
      if ( !v14 )
        return 4;
      v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, wchar_t **, __int64 **, unsigned int *, __int64 *))(v14 + 96))(
              v10,
              v4,
              String1,
              &v39,
              &v42,
              &v43);
      if ( v12 )
        return v12;
      if ( !v11 || !*(_QWORD *)v11 )
        return 4;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **, __int64 **, unsigned int *, __int64 *))(*(_QWORD *)v11 + 96LL))(
              v11,
              v4,
              &String2,
              &v45,
              &v48,
              &v49);
      if ( v12 )
        return v12;
      if ( _wcsicmp(String1[0], String2) )
      {
        v24 = String1[0];
        v25 = GetModuleHandleA("mpunits.dll");
        Intlstr_FormatString_FormatMessage(v25, 2100, v24);
        goto LABEL_14;
      }
      if ( (((unsigned int)v49 | (unsigned int)v43) & 0x20000000) == 0
        && (v42 >= 0x10 || v48 >= 0x10 || dword_18005F0E0[v42] != dword_18005F0E0[v48]) )
      {
        v23 = GetModuleHandleA("mpunits.dll");
        Intlstr_GetString_LoadString(v23, 2101);
        goto LABEL_14;
      }
      result = InvokeComparisonBuiltin(a1, &v39, v15, a4);
      if ( (_DWORD)result )
        return result;
      if ( *a4 )
        return 0;
      v17 = v39;
      v18 = v43;
      v19 = v42;
      v20 = v40;
      v21 = v44;
      v22 = v41;
      v39 = v45;
      v42 = v48;
      v43 = v49;
      v44 = v50;
      v45 = v17;
      v49 = v18;
      v40 = v46;
      v48 = v19;
      v41 = v47;
      v50 = v21;
      v46 = v20;
      v47 = v22;
      result = InvokeComparisonBuiltin(a1, &v39, v19, a4);
      if ( (_DWORD)result )
        return result;
      if ( !*a4 && ++v4 < v35 )
        continue;
      break;
    }
  }
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x180032038  push    rbp
0x18003203a  push    rbx
0x18003203b  push    rsi
0x18003203c  push    rdi
0x18003203d  push    r12
0x18003203f  push    r13
0x180032041  push    r14
0x180032043  push    r15
0x180032045  lea     rbp, [rsp-1Fh]
0x18003204a  sub     rsp, 0F8h
0x180032051  mov     rax, cs:__security_cookie
0x180032058  xor     rax, rsp
0x18003205b  mov     [rbp+57h+var_50], rax
0x18003205f  xor     r15d, r15d
0x180032062  mov     r13, rcx
0x180032065  mov     ecx, r15d
0x180032068  mov     r14, r9
0x18003206b  imul    rax, rcx, 38h ; '8'
0x18003206f  inc     rcx
0x180032072  mov     [rbp+rax+57h+var_94+4], r15
0x180032077  cmp     rcx, 2
0x18003207b  jnz     short loc_18003206B
0x18003207d  mov     r9d, [rdx+28h]
0x180032081  mov     r11d, 20000000h
0x180032087  cmp     r9d, 0Fh
0x18003208b  jnz     loc_1800323BD
0x180032091  cmp     [r8+28h], r9d
0x180032095  jnz     loc_1800323BD
0x18003209b  test    [rdx+2Ch], r11d
0x18003209f  jnz     loc_1800323BD
0x1800320a5  test    [r8+2Ch], r11d
0x1800320a9  jnz     loc_1800323BD
0x1800320af  mov     rdi, [rdx]
0x1800320b2  mov     [rsp+130h+var_E0], r15d
0x1800320b7  mov     [rsp+130h+var_DC], r15d
0x1800320bc  test    rdi, rdi
0x1800320bf  jz      loc_1800323B1
0x1800320c5  mov     rax, [rdi]
0x1800320c8  test    rax, rax
0x1800320cb  jz      loc_1800323B1
0x1800320d1  mov     rax, [rax+38h]
0x1800320d5  lea     rdx, [rsp+130h+var_E0]
0x1800320da  mov     r12, [r8]
0x1800320dd  mov     rcx, rdi
0x1800320e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320e5  mov     ebx, eax
0x1800320e7  test    eax, eax
0x1800320e9  jnz     loc_1800323B6
0x1800320ef  mov     rax, [rdi]
0x1800320f2  test    rax, rax
0x1800320f5  jz      loc_1800323B1
0x1800320fb  mov     rax, [rax+38h]
0x1800320ff  lea     rdx, [rsp+130h+var_DC]
0x180032104  mov     rcx, rdi
0x180032107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003210c  mov     ebx, eax
0x18003210e  test    eax, eax
0x180032110  jnz     loc_1800323B6
0x180032116  mov     eax, [rsp+130h+var_E0]
0x18003211a  cmp     [rsp+130h+var_DC], eax
0x18003211e  jz      short loc_18003217F
0x180032120  xorps   xmm0, xmm0
0x180032123  lea     rcx, ModuleName; "mpunits.dll"
0x18003212a  movups  xmmword ptr [rbp+57h+String1], xmm0
0x18003212e  call    cs:__imp_GetModuleHandleA
0x180032134  mov     rcx, rax
0x180032137  mov     edx, 833h
0x18003213c  call    _Intlstr_GetString_LoadString
0x180032141  mov     [rbp+57h+String1], rax
0x180032145  mov     byte ptr [rbp+57h+String1+8], r15b
0x180032149  movaps  xmm0, xmmword ptr [rbp+57h+String1]
0x18003214d  mov     [rsp+130h+var_108], r15; __int64
0x180032152  mov     [rsp+130h+var_110], r15; __int64
0x180032157  mov     r8d, 5
0x18003215d  movdqa  [rsp+130h+var_F0], xmm0
0x180032163  lea     r9, [rsp+130h+var_F0]
0x180032168  lea     rdx, aMi; "MI"
0x18003216f  lea     ebx, [r8-1]
0x180032173  mov     ecx, ebx; int
0x180032175  call    MI_ReportErrorDetails_ForCustomError
0x18003217a  jmp     loc_1800323B6
0x18003217f  xor     ebx, ebx
0x180032181  test    eax, eax
0x180032183  jz      loc_180032311
0x180032189  lea     rsi, dword_18005F0E0
0x180032190  mov     rax, [rdi]
0x180032193  mov     [rbp+57h+String1], rbx
0x180032197  mov     [rsp+130h+String2], rbx
0x18003219c  test    rax, rax
0x18003219f  jz      loc_1800323B1
0x1800321a5  mov     rax, [rax+60h]
0x1800321a9  lea     rcx, [rbp+57h+var_94]
0x1800321ad  mov     [rsp+130h+var_108], rcx
0x1800321b2  lea     r9, [rbp+57h+var_C0]
0x1800321b6  lea     rcx, [rbp+57h+var_98]
0x1800321ba  mov     edx, r15d
0x1800321bd  mov     [rsp+130h+var_110], rcx
0x1800321c2  lea     r8, [rbp+57h+String1]
0x1800321c6  mov     rcx, rdi
0x1800321c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321ce  mov     ebx, eax
0x1800321d0  test    eax, eax
0x1800321d2  jnz     loc_1800323B6
0x1800321d8  test    r12, r12
0x1800321db  jz      loc_1800323B1
0x1800321e1  mov     rax, [r12]
0x1800321e5  test    rax, rax
0x1800321e8  jz      loc_1800323B1
0x1800321ee  mov     rax, [rax+60h]
0x1800321f2  lea     rcx, [rbp+57h+var_5C]
0x1800321f6  mov     [rsp+130h+var_108], rcx
0x1800321fb  lea     r9, [rbp+57h+var_88]
0x1800321ff  lea     rcx, [rbp+57h+var_60]
0x180032203  mov     edx, r15d
0x180032206  mov     [rsp+130h+var_110], rcx
0x18003220b  lea     r8, [rsp+130h+String2]
0x180032210  mov     rcx, r12
0x180032213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032218  mov     ebx, eax
0x18003221a  test    eax, eax
0x18003221c  jnz     loc_1800323B6
0x180032222  mov     rdx, [rsp+130h+String2]; String2
0x180032227  mov     rcx, [rbp+57h+String1]; String1
0x18003222b  call    cs:__imp__wcsicmp
0x180032231  xor     ebx, ebx
0x180032233  test    eax, eax
0x180032235  jnz     loc_18003235A
0x18003223b  mov     eax, dword ptr [rbp+57h+var_94]
0x18003223e  or      eax, dword ptr [rbp+57h+var_5C]
0x180032241  bt      eax, 1Dh
0x180032245  jb      short loc_18003226D
0x180032247  cmp     [rbp+57h+var_98], 10h
0x18003224b  jnb     loc_18003231B
0x180032251  cmp     [rbp+57h+var_60], 10h
0x180032255  jnb     loc_18003231B
0x18003225b  mov     eax, [rbp+57h+var_60]
0x18003225e  mov     ecx, [rbp+57h+var_98]
0x180032261  mov     eax, [rsi+rax*4]
0x180032264  cmp     [rsi+rcx*4], eax
0x180032267  jnz     loc_18003231B
0x18003226d  mov     r9, r14
0x180032270  lea     rdx, [rbp+57h+var_C0]
0x180032274  mov     rcx, r13
0x180032277  call    InvokeComparisonBuiltin
0x18003227c  test    eax, eax
0x18003227e  jnz     loc_18003247F
0x180032284  cmp     [r14], ebx
0x180032287  jnz     loc_180032314
0x18003228d  mov     rcx, [rbp+57h+var_88]
0x180032291  mov     rdx, [rbp+57h+var_C0]
0x180032295  mov     r9, [rbp+57h+var_94]
0x180032299  mov     r8d, [rbp+57h+var_98]
0x18003229d  movups  xmm2, [rbp+57h+var_B8]
0x1800322a1  mov     eax, [rbp+57h+var_8C]
0x1800322a4  movups  xmm3, [rbp+57h+var_A8]
0x1800322a8  mov     [rbp+57h+var_C0], rcx
0x1800322ac  mov     ecx, [rbp+57h+var_60]
0x1800322af  movaps  xmm0, [rbp+57h+var_80]
0x1800322b3  movaps  xmm1, [rbp+57h+var_70]
0x1800322b7  mov     [rbp+57h+var_98], ecx
0x1800322ba  mov     rcx, [rbp+57h+var_5C]
0x1800322be  mov     [rbp+57h+var_94], rcx
0x1800322c2  mov     ecx, [rbp+57h+var_54]
0x1800322c5  mov     [rbp+57h+var_8C], ecx
0x1800322c8  mov     rcx, r13
0x1800322cb  mov     [rbp+57h+var_88], rdx
0x1800322cf  lea     rdx, [rbp+57h+var_C0]
0x1800322d3  mov     [rbp+57h+var_5C], r9
0x1800322d7  mov     r9, r14
0x1800322da  movups  [rbp+57h+var_B8], xmm0
0x1800322de  mov     [rbp+57h+var_60], r8d
0x1800322e2  movups  [rbp+57h+var_A8], xmm1
0x1800322e6  mov     [rbp+57h+var_54], eax
0x1800322e9  movaps  [rbp+57h+var_80], xmm2
0x1800322ed  movaps  [rbp+57h+var_70], xmm3
0x1800322f1  call    InvokeComparisonBuiltin
0x1800322f6  test    eax, eax
0x1800322f8  jnz     loc_18003247F
0x1800322fe  cmp     [r14], ebx
0x180032301  jnz     short loc_180032311
0x180032303  inc     r15d
0x180032306  cmp     r15d, [rsp+130h+var_E0]
0x18003230b  jb      loc_180032190
0x180032311  mov     [r14], ebx
0x180032314  xor     eax, eax
0x180032316  jmp     loc_18003247F
0x18003231b  xorps   xmm0, xmm0
0x18003231e  lea     rcx, ModuleName; "mpunits.dll"
0x180032325  movups  [rsp+130h+var_F0], xmm0
0x18003232a  call    cs:__imp_GetModuleHandleA
0x180032330  mov     rcx, rax
0x180032333  mov     edx, 835h
0x180032338  call    _Intlstr_GetString_LoadString
0x18003233d  mov     qword ptr [rsp+130h+var_F0], rax
0x180032342  mov     byte ptr [rsp+130h+var_F0+8], bl
0x180032346  movaps  xmm0, [rsp+130h+var_F0]
0x18003234b  mov     [rsp+130h+var_108], rbx
0x180032350  mov     [rsp+130h+var_110], rbx
0x180032355  jmp     loc_180032157
0x18003235a  mov     rbx, [rsp+130h+String2]
0x18003235f  lea     rcx, ModuleName; "mpunits.dll"
0x180032366  mov     rdi, [rbp+57h+String1]
0x18003236a  xorps   xmm0, xmm0
0x18003236d  movups  [rsp+130h+var_F0], xmm0
0x180032372  call    cs:__imp_GetModuleHandleA
0x180032378  mov     r9, rbx
0x18003237b  mov     r8, rdi
0x18003237e  mov     rcx, rax
0x180032381  mov     edx, 834h
0x180032386  call    _Intlstr_FormatString_FormatMessage
0x18003238b  mov     qword ptr [rsp+130h+var_F0], rax
0x180032390  mov     byte ptr [rsp+130h+var_F0+8], 1
0x180032395  movaps  xmm0, [rsp+130h+var_F0]
0x18003239a  mov     [rsp+130h+var_108], 0
0x1800323a3  mov     [rsp+130h+var_110], 0
0x1800323ac  jmp     loc_180032157
0x1800323b1  mov     ebx, 4
0x1800323b6  mov     eax, ebx
0x1800323b8  jmp     loc_18003247F
0x1800323bd  mov     rax, [rdx]
0x1800323c0  movups  xmm0, xmmword ptr [rdx+8]
0x1800323c4  mov     rcx, [rdx+2Ch]
0x1800323c8  movups  xmm1, xmmword ptr [rdx+18h]
0x1800323cc  mov     r10d, [r8+28h]
0x1800323d0  mov     [rbp+57h+var_C0], rax
0x1800323d4  mov     eax, [rdx+34h]
0x1800323d7  mov     rdx, [r8+2Ch]
0x1800323db  mov     [rbp+57h+var_8C], eax
0x1800323de  mov     rax, [r8]
0x1800323e1  movups  [rbp+57h+var_B8], xmm0
0x1800323e5  mov     [rbp+57h+var_94], rcx
0x1800323e9  or      ecx, edx
0x1800323eb  mov     [rbp+57h+var_88], rax
0x1800323ef  mov     eax, [r8+34h]
0x1800323f3  mov     [rbp+57h+var_54], eax
0x1800323f6  mov     [rbp+57h+var_98], r9d
0x1800323fa  mov     [rbp+57h+var_60], r10d
0x1800323fe  mov     [rbp+57h+var_5C], rdx
0x180032402  movups  xmm0, xmmword ptr [r8+8]
0x180032407  movups  [rbp+57h+var_A8], xmm1
0x18003240b  movaps  [rbp+57h+var_80], xmm0
0x18003240f  movups  xmm1, xmmword ptr [r8+18h]
0x180032414  movaps  [rbp+57h+var_70], xmm1
0x180032418  test    r11d, ecx
0x18003241b  jnz     short loc_180032470
0x18003241d  cmp     r9d, 10h
0x180032421  jnb     short loc_18003243A
0x180032423  cmp     r10d, 10h
0x180032427  jnb     short loc_18003243A
0x180032429  lea     rsi, dword_18005F0E0
0x180032430  mov     eax, [rsi+r10*4]
0x180032434  cmp     [rsi+r9*4], eax
0x180032438  jz      short loc_180032470
0x18003243a  xorps   xmm0, xmm0
0x18003243d  lea     rcx, ModuleName; "mpunits.dll"
0x180032444  movups  [rsp+130h+var_F0], xmm0
0x180032449  call    cs:__imp_GetModuleHandleA
0x18003244f  mov     rcx, rax
0x180032452  mov     edx, 835h
0x180032457  call    _Intlstr_GetString_LoadString
0x18003245c  mov     qword ptr [rsp+130h+var_F0], rax
0x180032461  mov     byte ptr [rsp+130h+var_F0+8], r15b
0x180032466  movaps  xmm0, [rsp+130h+var_F0]
0x18003246b  jmp     loc_18003214D
0x180032470  mov     r9, r14
0x180032473  lea     rdx, [rbp+57h+var_C0]
0x180032477  mov     rcx, r13
0x18003247a  call    InvokeComparisonBuiltin
0x18003247f  mov     rcx, [rbp+57h+var_50]
0x180032483  xor     rcx, rsp; StackCookie
0x180032486  call    __security_check_cookie
0x18003248b  add     rsp, 0F8h
0x180032492  pop     r15
0x180032494  pop     r14
0x180032496  pop     r13
0x180032498  pop     r12
0x18003249a  pop     rdi
0x18003249b  pop     rsi
0x18003249c  pop     rbx
0x18003249d  pop     rbp
0x18003249e  retn
```
