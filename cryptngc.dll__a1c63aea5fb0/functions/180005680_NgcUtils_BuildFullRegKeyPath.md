# NgcUtils::BuildFullRegKeyPath

- ea: `0x180005680`
- end: `0x180005c7a`
- name: `NgcUtils::BuildFullRegKeyPath`
- size: `1530`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024a20`

## callees

- `0x180004720`
- `0x180005680`
- `0x180006538`
- `0x180028418`
- `0x18002c898`
- `0x180031894`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000592a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000592a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005bfb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800058be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800058be`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800056d4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000572e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800056d4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000572e`

## string_xrefs

- `0x1800057d4`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800058dd`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180005bbb`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180005be7`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800057b4`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005801`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005914`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005a08`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180005826`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`
- `0x180005c12`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::BuildFullRegKeyPath(_WORD *a1, __int128 *a2)
{
  _WORD *v4; // rdi
  int PersistedRegistryLocationW; // eax
  unsigned int v6; // esi
  _BYTE *v7; // rax
  void *v8; // rbx
  _BYTE *i; // r8
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  _WORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r14
  const unsigned __int16 *v17; // rax
  const char *v18; // r9
  _WORD *v20; // rax
  unsigned __int64 v21; // rdi
  _WORD *v22; // rbp
  __int64 v23; // r8
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  __int64 v26; // r10
  __int64 v27; // rcx
  __int16 *v28; // rdx
  unsigned __int64 v29; // r8
  _WORD *v30; // r9
  __int16 v31; // ax
  _WORD *v32; // rcx
  unsigned __int64 v33; // rcx
  _WORD *v34; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  unsigned __int16 *v38; // r8
  unsigned __int16 v39; // ax
  int v40; // r9d
  unsigned __int16 *v41; // rcx
  unsigned __int64 v42; // rcx
  _WORD *v43; // rax
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rdi
  _WORD *v46; // rdx
  __int16 v47; // ax
  _WORD *v48; // rcx
  int v49; // [rsp+20h] [rbp-78h]
  int v50; // [rsp+20h] [rbp-78h]
  SIZE_T uBytes; // [rsp+30h] [rbp-68h] BYREF
  _WORD *v52; // [rsp+38h] [rbp-60h]
  __int128 v53; // [rsp+40h] [rbp-58h] BYREF
  __int128 v54; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = 0;
  v52 = 0;
  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"NgcCredprov",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6"
                                  "886603-9D2F-4EB2-B667-1971041FA96B}",
                                 0,
                                 0);
  v6 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      goto LABEL_29;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v6,
      (int)&uBytes);
    goto LABEL_28;
  }
  v7 = LocalAlloc(0, (unsigned int)uBytes);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      (int)&uBytes);
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
      (const char *)v6,
      v49);
    return v6;
  }
  for ( i = &v7[(unsigned int)uBytes]; v7 != i; ++v7 )
    *v7 = 0;
  v10 = GetPersistedRegistryLocationW(
          L"NgcCredprov",
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
          v8,
          (unsigned int)uBytes);
  if ( v10 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC0,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
           (const char *)v10,
           (unsigned int)&uBytes);
    LocalFree(v8);
LABEL_28:
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_17;
    goto LABEL_29;
  }
  if ( !a1 )
  {
    v4 = v8;
    v52 = v8;
    goto LABEL_29;
  }
  v11 = 260;
  v12 = 260;
  v13 = v8;
  while ( *v13 )
  {
    ++v13;
    if ( !--v12 )
    {
      v6 = -2147024809;
      v14 = 179;
      goto LABEL_25;
    }
  }
  v15 = 260;
  v16 = L"\\";
  v17 = L"\\";
  v18 = (const char *)(260 - v12);
  while ( *v17 )
  {
    ++v17;
    if ( !--v15 )
    {
      v6 = -2147024809;
      v14 = 185;
      goto LABEL_25;
    }
  }
  v20 = a1;
  while ( *v20 )
  {
    ++v20;
    if ( !--v11 )
    {
      v6 = -2147024809;
      v14 = 191;
      goto LABEL_25;
    }
  }
  v21 = (unsigned __int64)&v18[260 - v15 - v11 + 261];
  if ( v21 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v18);
  v22 = LocalAlloc(0, 2 * v21 + 2);
  if ( !v22 )
  {
    v6 = -2147024882;
    v14 = 199;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v6,
      (int)&uBytes);
    goto LABEL_16;
  }
  *v22 = 0;
  v22[v21] = 0;
  if ( !v21 )
  {
    v6 = -2147024809;
    goto LABEL_15;
  }
  if ( v21 > 0x7FFFFFFF )
  {
    v6 = -2147024809;
    *v22 = 0;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v6,
      (int)&uBytes);
    LocalFree(v22);
    goto LABEL_16;
  }
  v26 = 2147483646;
  v27 = 2147483646;
  v28 = (__int16 *)v8;
  v29 = v21;
  v30 = v22;
  do
  {
    if ( !v27 )
      break;
    v31 = *v28;
    if ( !*v28 )
      break;
    ++v28;
    *v30++ = v31;
    --v27;
    --v29;
  }
  while ( v29 );
  v32 = v30 - 1;
  if ( v29 )
    v32 = v30;
  *v32 = 0;
  v6 = -2147024774;
  if ( !v29 )
    goto LABEL_15;
  v33 = v21;
  v34 = v22;
  do
  {
    if ( !*v34 )
      break;
    ++v34;
    --v33;
  }
  while ( v33 );
  v6 = -2147024809;
  if ( !v33 )
  {
    v6 = -2147024809;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v6,
      (int)&uBytes);
    LocalFree(v22);
    goto LABEL_16;
  }
  v35 = v21 - v33;
  v36 = 2147483646;
  v37 = v21 - v35;
  v38 = &v22[v35];
  if ( v21 != v35 )
  {
    do
    {
      if ( !v36 )
        break;
      v39 = *v16;
      if ( !*v16 )
        break;
      ++v16;
      *v38++ = v39;
      --v36;
      --v37;
    }
    while ( v37 );
  }
  v40 = -2147024774;
  if ( v37 )
    v40 = 0;
  v41 = v38 - 1;
  if ( v37 )
    v41 = v38;
  *v41 = 0;
  if ( !v37 )
  {
    v6 = v40;
    goto LABEL_84;
  }
  v42 = v21;
  v43 = v22;
  do
  {
    if ( !*v43 )
      break;
    ++v43;
    --v42;
  }
  while ( v42 );
  if ( !v42 )
    goto LABEL_82;
  v44 = v21 - v42;
  v45 = v42;
  v46 = &v22[v44];
  do
  {
    if ( !v26 )
      break;
    v47 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v46++ = v47;
    --v26;
    --v45;
  }
  while ( v45 );
  v6 = -2147024774;
  if ( v45 )
    v6 = 0;
  v48 = v46 - 1;
  if ( v45 )
    v48 = v46;
  *v48 = 0;
  if ( !v45 )
  {
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v6,
      (int)&uBytes);
    LocalFree(v22);
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)v6,
      v50);
    LocalFree(v8);
    goto LABEL_17;
  }
  v4 = v22;
  v52 = v22;
  LocalFree(v8);
LABEL_29:
  v53 = 0;
  v54 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v4[v23] );
  std::wstring::_Construct<1,unsigned short const *>(&v53, v4, v23);
  if ( a2 == &v53 )
  {
    v25 = *((_QWORD *)&v54 + 1);
  }
  else
  {
    v24 = *((_QWORD *)a2 + 3);
    if ( v24 > 7 )
      std::_Deallocate<16>(*(_QWORD *)a2, 2 * v24 + 2);
    *a2 = v53;
    a2[1] = v54;
    v25 = 7;
    LOWORD(v53) = 0;
  }
  if ( v25 > 7 )
    std::_Deallocate<16>(v53, 2 * v25 + 2);
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x180005680  mov     [rsp+arg_0], rbx
0x180005685  mov     [rsp+arg_10], rbp
0x18000568a  push    rsi
0x18000568b  push    rdi
0x18000568c  push    r12
0x18000568e  push    r14
0x180005690  push    r15
0x180005692  sub     rsp, 70h
0x180005696  mov     rax, cs:__security_cookie
0x18000569d  xor     rax, rsp
0x1800056a0  mov     [rsp+98h+var_38], rax
0x1800056a5  mov     r12, rdx
0x1800056a8  mov     r15, rcx
0x1800056ab  xor     edi, edi
0x1800056ad  mov     [rsp+98h+var_60], rdi
0x1800056b2  mov     dword ptr [rsp+98h+uBytes], edi
0x1800056b6  lea     rax, [rsp+98h+uBytes]
0x1800056bb  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800056c0  xor     r9d, r9d
0x1800056c3  xor     r8d, r8d
0x1800056c6  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800056cd  lea     rcx, aNgccredprov; "NgcCredprov"
0x1800056d4  call    cs:__imp_GetPersistedRegistryLocationW
0x1800056da  mov     esi, eax
0x1800056dc  cmp     eax, 0EAh
0x1800056e1  jnz     loc_1800059F1
0x1800056e7  mov     esi, dword ptr [rsp+98h+uBytes]
0x1800056eb  mov     edx, esi; uBytes
0x1800056ed  xor     ecx, ecx; uFlags
0x1800056ef  call    cs:__imp_LocalAlloc
0x1800056f5  mov     rbx, rax
0x1800056f8  test    rax, rax
0x1800056fb  jz      loc_1800057A4
0x180005701  lea     r8, [rax+rsi]
0x180005705  cmp     rax, r8
0x180005708  jnz     loc_1800059D0
0x18000570e  lea     rax, [rsp+98h+uBytes]
0x180005713  mov     qword ptr [rsp+98h+var_78], rax; int
0x180005718  mov     r9d, dword ptr [rsp+98h+uBytes]
0x18000571d  mov     r8, rbx
0x180005720  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180005727  lea     rcx, aNgccredprov; "NgcCredprov"
0x18000572e  call    cs:__imp_GetPersistedRegistryLocationW
0x180005734  test    eax, eax
0x180005736  jnz     loc_180005909
0x18000573c  test    r15, r15
0x18000573f  jz      loc_1800059E4
0x180005745  mov     r8d, 104h
0x18000574b  mov     ecx, r8d
0x18000574e  mov     rax, rbx
0x180005751  cmp     [rax], di
0x180005754  jz      short loc_18000576F
0x180005756  add     rax, 2
0x18000575a  sub     rcx, 1
0x18000575e  jnz     short loc_180005751
0x180005760  mov     esi, 80070057h
0x180005765  mov     edx, 0B3h
0x18000576a  jmp     loc_1800058DA
0x18000576f  mov     rdx, r8
0x180005772  lea     r14, asc_180050E74; "\\"
0x180005779  mov     rax, r14
0x18000577c  mov     r9, r8
0x18000577f  sub     r9, rcx; char *
0x180005782  cmp     [rax], di
0x180005785  jz      loc_180005860
0x18000578b  add     rax, 2
0x18000578f  sub     rdx, 1
0x180005793  jnz     short loc_180005782
0x180005795  mov     esi, 80070057h
0x18000579a  mov     edx, 0B9h
0x18000579f  jmp     loc_1800058DA
0x1800057a4  mov     rcx, [rsp+98h]; this
0x1800057ac  mov     esi, 8007000Eh
0x1800057b1  mov     r9d, esi; char *
0x1800057b4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800057bb  mov     edx, 0B9h; void *
0x1800057c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057c5  jmp     short loc_18000581B
0x1800057c7  xor     edi, edi
0x1800057c9  mov     rcx, [rsp+98h]; this
0x1800057d1  mov     r9d, esi; char *
0x1800057d4  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800057db  mov     edx, 0CDh; void *
0x1800057e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057e5  mov     rcx, rbp; hMem
0x1800057e8  call    cs:__imp_LocalFree
0x1800057ee  test    esi, esi
0x1800057f0  jns     loc_1800058F9
0x1800057f6  mov     rcx, [rsp+98h]; this
0x1800057fe  mov     r9d, esi; char *
0x180005801  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005808  mov     edx, 0C9h; void *
0x18000580d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005812  mov     rcx, rbx; hMem
0x180005815  call    cs:__imp_LocalFree
0x18000581b  mov     rcx, [rsp+98h]; this
0x180005823  mov     r9d, esi; char *
0x180005826  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000582d  mov     edx, 1Fh; void *
0x180005832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005837  nop
0x180005838  mov     eax, esi
0x18000583a  mov     rcx, [rsp+98h+var_38]
0x18000583f  xor     rcx, rsp; StackCookie
0x180005842  call    __security_check_cookie
0x180005847  lea     r11, [rsp+98h+var_28]
0x18000584c  mov     rbx, [r11+30h]
0x180005850  mov     rbp, [r11+40h]
0x180005854  mov     rsp, r11
0x180005857  pop     r15
0x180005859  pop     r14
0x18000585b  pop     r12
0x18000585d  pop     rdi
0x18000585e  pop     rsi
0x18000585f  retn
0x180005860  mov     rax, r15
0x180005863  mov     rcx, r8
0x180005866  sub     rcx, rdx
0x180005869  nop     dword ptr [rax+00000000h]
0x180005870  cmp     [rax], di
0x180005873  jz      short loc_18000588B
0x180005875  add     rax, 2
0x180005879  sub     r8, 1
0x18000587d  jnz     short loc_180005870
0x18000587f  mov     esi, 80070057h
0x180005884  mov     edx, 0BFh
0x180005889  jmp     short loc_1800058DA
0x18000588b  sub     rcx, r8
0x18000588e  lea     rdi, [rcx+105h]
0x180005895  add     rdi, r9
0x180005898  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000589c  jnz     loc_180005C0B
0x1800058a2  mov     al, 1
0x1800058a4  mov     rcx, [rsp+98h]; this
0x1800058ac  test    al, al
0x1800058ae  jnz     loc_180005C12
0x1800058b4  lea     rdx, ds:2[rdi*2]; uBytes
0x1800058bc  xor     ecx, ecx; uFlags
0x1800058be  call    cs:__imp_LocalAlloc
0x1800058c4  mov     rbp, rax
0x1800058c7  test    rax, rax
0x1800058ca  jnz     loc_180005A29
0x1800058d0  mov     esi, 8007000Eh
0x1800058d5  mov     edx, 0C7h; void *
0x1800058da  mov     r9d, esi; char *
0x1800058dd  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800058e4  mov     rcx, [rsp+98h]; this
0x1800058ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058f1  jmp     loc_1800057F6
0x1800058f6  mov     rdi, rbp
0x1800058f9  mov     [rsp+98h+var_60], rdi
0x1800058fe  mov     rcx, rbx; hMem
0x180005901  call    cs:__imp_LocalFree
0x180005907  jmp     short loc_180005938
0x180005909  mov     rcx, [rsp+98h]; this
0x180005911  mov     r9d, eax; char *
0x180005914  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000591b  mov     edx, 0C0h; void *
0x180005920  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005925  mov     esi, eax
0x180005927  mov     rcx, rbx; hMem
0x18000592a  call    cs:__imp_LocalFree
0x180005930  test    esi, esi
0x180005932  js      loc_18000581B
0x180005938  xorps   xmm0, xmm0
0x18000593b  movups  [rsp+98h+var_58], xmm0
0x180005940  xorps   xmm1, xmm1
0x180005943  movdqu  [rsp+98h+var_48], xmm1
0x180005949  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005950  inc     r8
0x180005953  cmp     word ptr [rdi+r8*2], 0
0x180005959  jnz     short loc_180005950
0x18000595b  mov     rdx, rdi
0x18000595e  lea     rcx, [rsp+98h+var_58]
0x180005963  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180005968  lea     rax, [rsp+98h+var_58]
0x18000596d  cmp     r12, rax
0x180005970  jz      loc_180005C58
0x180005976  mov     rdx, [r12+18h]
0x18000597b  cmp     rdx, 7
0x18000597f  ja      loc_180005C42
0x180005985  movups  xmm0, [rsp+98h+var_58]
0x18000598a  movups  xmmword ptr [r12], xmm0
0x18000598f  movups  xmm1, [rsp+98h+var_48]
0x180005994  movups  xmmword ptr [r12+10h], xmm1
0x18000599a  mov     edx, 7
0x18000599f  xor     eax, eax
0x1800059a1  mov     word ptr [rsp+98h+var_58], ax
0x1800059a6  cmp     rdx, 7
0x1800059aa  ja      loc_180005C62
0x1800059b0  test    rdi, rdi
0x1800059b3  jz      short loc_1800059BE
0x1800059b5  mov     rcx, rdi; hMem
0x1800059b8  call    cs:__imp_LocalFree
0x1800059be  xor     eax, eax
0x1800059c0  jmp     loc_18000583A
0x1800059d0  xor     r9d, r9d
0x1800059d3  mov     [rax], r9b
0x1800059d6  inc     rax
0x1800059d9  cmp     rax, r8
0x1800059dc  jz      loc_18000570E
0x1800059e2  jmp     short loc_1800059D0
0x1800059e4  mov     rdi, rbx
0x1800059e7  mov     [rsp+98h+var_60], rbx
0x1800059ec  jmp     loc_180005938
0x1800059f1  test    eax, eax
0x1800059f3  jg      short loc_180005A1E
0x1800059f5  test    esi, esi
0x1800059f7  jns     loc_180005938
0x1800059fd  mov     rcx, [rsp+98h]; this
0x180005a05  mov     r9d, esi; char *
0x180005a08  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180005a0f  mov     edx, 0B6h; void *
0x180005a14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a19  jmp     loc_180005930
0x180005a1e  movzx   esi, ax
0x180005a21  or      esi, 80070000h
0x180005a27  jmp     short loc_1800059F5
0x180005a29  xor     eax, eax
0x180005a2b  mov     [rbp+0], ax
0x180005a2f  mov     [rbp+rdi*2+0], ax
0x180005a34  test    rdi, rdi
0x180005a37  jz      loc_180005C2B
0x180005a3d  cmp     rdi, 7FFFFFFFh
0x180005a44  ja      loc_180005C24
0x180005a4a  mov     r10d, 7FFFFFFEh
0x180005a50  mov     ecx, r10d
0x180005a53  mov     rdx, rbx
0x180005a56  mov     r8, rdi
0x180005a59  mov     r9, rbp
0x180005a5c  nop     dword ptr [rax+00h]
0x180005a60  test    rcx, rcx
0x180005a63  jz      short loc_180005A82
0x180005a65  movzx   eax, word ptr [rdx]
0x180005a68  test    ax, ax
0x180005a6b  jz      short loc_180005A82
0x180005a6d  add     rdx, 2
0x180005a71  mov     [r9], ax
0x180005a75  add     r9, 2
0x180005a79  dec     rcx
0x180005a7c  sub     r8, 1
0x180005a80  jnz     short loc_180005A60
0x180005a82  lea     rcx, [r9-2]
0x180005a86  test    r8, r8
0x180005a89  cmovnz  rcx, r9
0x180005a8d  xor     eax, eax
0x180005a8f  mov     [rcx], ax
0x180005a92  mov     esi, 8007007Ah
0x180005a97  test    r8, r8
0x180005a9a  cmovnz  esi, eax
0x180005a9d  jz      loc_1800057C7
0x180005aa3  mov     rcx, rdi
0x180005aa6  mov     rax, rbp
0x180005aa9  nop     dword ptr [rax+00000000h]
0x180005ab0  cmp     word ptr [rax], 0
0x180005ab4  jz      short loc_180005AC0
0x180005ab6  add     rax, 2
0x180005aba  sub     rcx, 1
0x180005abe  jnz     short loc_180005AB0
0x180005ac0  mov     esi, 80070057h
0x180005ac5  mov     edx, esi
0x180005ac7  xor     eax, eax
0x180005ac9  test    rcx, rcx
0x180005acc  cmovnz  edx, eax
0x180005acf  jz      loc_180005BDA
0x180005ad5  mov     rax, rdi
0x180005ad8  sub     rax, rcx
0x180005adb  test    rcx, rcx
0x180005ade  jz      loc_180005BDA
0x180005ae4  mov     rcx, r10
0x180005ae7  mov     rdx, rdi
0x180005aea  sub     rdx, rax
0x180005aed  lea     r8, [rbp+rax*2+0]
0x180005af2  jz      short loc_180005B17
0x180005af4  test    rcx, rcx
0x180005af7  jz      short loc_180005B17
0x180005af9  movzx   eax, word ptr [r14]
0x180005afd  test    ax, ax
0x180005b00  jz      short loc_180005B17
0x180005b02  add     r14, 2
0x180005b06  mov     [r8], ax
0x180005b0a  add     r8, 2
0x180005b0e  dec     rcx
0x180005b11  sub     rdx, 1
0x180005b15  jnz     short loc_180005AF4
0x180005b17  xor     eax, eax
0x180005b19  mov     r9d, 8007007Ah
0x180005b1f  test    rdx, rdx
0x180005b22  cmovnz  r9d, eax
0x180005b26  lea     rcx, [r8-2]
0x180005b2a  cmovnz  rcx, r8
0x180005b2e  mov     [rcx], ax
0x180005b31  jz      loc_180005C06
0x180005b37  mov     rcx, rdi
0x180005b3a  mov     rax, rbp
0x180005b3d  nop     dword ptr [rax]
0x180005b40  cmp     word ptr [rax], 0
0x180005b44  jz      short loc_180005B50
0x180005b46  add     rax, 2
0x180005b4a  sub     rcx, 1
  ... truncated ...
```
