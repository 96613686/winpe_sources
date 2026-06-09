# IsDictionaryReady(ulong)

- ea: `0x1800d5858`
- end: `0x1800d5a93`
- name: `?IsDictionaryReady@@YAHK@Z`
- size: `571`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800d5b30`

## callees

- `0x18009c868`
- `0x18009eaea`
- `0x1800d5858`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x1800d5a43`
- `msvcrt!wcsncat_s` at `0x1800d5a43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800d59e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800d59e1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d5a4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d5a4d`

## string_xrefs

- `0x1800d58ad`: `\system32\ja-jp\SDDS0411.DIC`
- `0x1800d58be`: `\system32\zh-tw\SDDS0404.DIC`
- `0x1800d58fc`: `\system32\zh-cn\ChsPinyin.lm`
- `0x1800d58e4`: `\system32\zh-tw\chtmain.DIC`
- `0x1800d591d`: `\System32\bn-in\SDDS0445.dic`
- `0x1800d5928`: `\System32\pa-in\SDDS0446.dic`
- `0x1800d5907`: `\system32\zh-hk\ChtAP.sdc`
- `0x1800d5912`: `\System32\hi-in\SDDS0439.dic`
- `0x1800d5949`: `\System32\ta-in\SDDS0449.dic`
- `0x1800d5954`: `\System32\te-in\SDDS044A.dic`
- `0x1800d5933`: `\System32\gu-in\SDDS0447.dic`
- `0x1800d593e`: `\System32\or-in\SDDS0448.dic`
- `0x1800d597e`: `\System32\mr-in\SDDS044E.dic`
- `0x1800d595f`: `\System32\kn-in\SDDS044B.dic`
- `0x1800d596a`: `\System32\ml-in\SDDS044C.dic`

## pseudocode

```c
_BOOL8 __fastcall IsDictionaryReady(int a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  char v6; // si
  int *i; // rbx
  const wchar_t *v8; // r8
  rsize_t v9; // r9
  int v11; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v12; // [rsp+28h] [rbp-D8h]
  int v13; // [rsp+30h] [rbp-D0h]
  const wchar_t *v14; // [rsp+38h] [rbp-C8h]
  int v15; // [rsp+40h] [rbp-C0h]
  const wchar_t *v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+50h] [rbp-B0h]
  const wchar_t *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  const wchar_t *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  const wchar_t *v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h]
  const wchar_t *v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+A0h] [rbp-60h]
  const wchar_t *v28; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+B0h] [rbp-50h]
  const wchar_t *v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  const wchar_t *v32; // [rsp+C8h] [rbp-38h]
  int v33; // [rsp+D0h] [rbp-30h]
  const wchar_t *v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E0h] [rbp-20h]
  const wchar_t *v36; // [rsp+E8h] [rbp-18h]
  int v37; // [rsp+F0h] [rbp-10h]
  const wchar_t *v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+100h] [rbp+0h]
  const wchar_t *v40; // [rsp+108h] [rbp+8h]
  int v41; // [rsp+110h] [rbp+10h]
  const wchar_t *v42; // [rsp+118h] [rbp+18h]
  int v43; // [rsp+120h] [rbp+20h]
  const wchar_t *v44; // [rsp+128h] [rbp+28h]
  int v45; // [rsp+130h] [rbp+30h]
  const wchar_t *v46; // [rsp+138h] [rbp+38h]
  wchar_t Buffer[264]; // [rsp+140h] [rbp+40h] BYREF

  v25 = 3076;
  v27 = 1081;
  v11 = 1041;
  v12 = L"\\IME\\IMEJP\\DICTS\\SDDS0411.DIC";
  v13 = 1041;
  v14 = L"\\system32\\ja-jp\\SDDS0411.DIC";
  v15 = 1028;
  v16 = L"\\system32\\zh-tw\\SDDS0404.DIC";
  v17 = 1028;
  v18 = L"\\IME\\IMETC\\DICTS\\IMTCT.IMD";
  v20 = L"\\system32\\zh-tw\\chtmain.DIC";
  v22 = L"\\InputMethod\\CHS\\ChsPinyin.lm";
  v24 = L"\\system32\\zh-cn\\ChsPinyin.lm";
  v26 = L"\\system32\\zh-hk\\ChtAP.sdc";
  v28 = L"\\System32\\hi-in\\SDDS0439.dic";
  v30 = L"\\System32\\bn-in\\SDDS0445.dic";
  v32 = L"\\System32\\pa-in\\SDDS0446.dic";
  v34 = L"\\System32\\gu-in\\SDDS0447.dic";
  v36 = L"\\System32\\or-in\\SDDS0448.dic";
  v38 = L"\\System32\\ta-in\\SDDS0449.dic";
  v40 = L"\\System32\\te-in\\SDDS044A.dic";
  v42 = L"\\System32\\kn-in\\SDDS044B.dic";
  v19 = 1028;
  v44 = L"\\System32\\ml-in\\SDDS044C.dic";
  v21 = 2052;
  v23 = 2052;
  v46 = L"\\System32\\mr-in\\SDDS044E.dic";
  v29 = 1093;
  v31 = 1094;
  v33 = 1095;
  v35 = 1096;
  v37 = 1097;
  v39 = 1098;
  v41 = 1099;
  v43 = 1100;
  v45 = 1102;
  memset_0(Buffer, 0, 0x208u);
  GetSystemWindowsDirectoryW(Buffer, 0x104u);
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  v6 = 0;
  for ( i = &v11; i != (int *)Buffer; i += 4 )
  {
    if ( *i == a1 )
    {
      if ( (unsigned __int64)(2 * v5) >= 0x208 )
        _report_rangecheckfailure(
          2 * v5,
          v2,
          v3,
          v4,
          v11,
          v12,
          v13,
          v14,
          v15,
          v16,
          v17,
          v18,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24,
          v25,
          v26,
          v27,
          v28,
          v29,
          v30,
          v31,
          v32,
          v33,
          v34);
      v8 = (const wchar_t *)*((_QWORD *)i + 1);
      v6 = 1;
      Buffer[v5] = 0;
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      wcsncat_s(Buffer, 0x104u, v8, v9);
      if ( GetFileAttributesW(Buffer) != -1 )
        return 1;
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800d5858  push    rbp
0x1800d585a  push    rbx
0x1800d585b  push    rsi
0x1800d585c  push    rdi
0x1800d585d  push    r14
0x1800d585f  push    r15
0x1800d5861  lea     rbp, [rsp-268h]
0x1800d5869  sub     rsp, 368h
0x1800d5870  mov     rax, cs:__security_cookie
0x1800d5877  xor     rax, rsp
0x1800d587a  mov     [rbp+290h+var_40], rax
0x1800d5881  mov     r14d, ecx
0x1800d5884  mov     [rbp+290h+var_300], 0C04h
0x1800d588b  mov     ecx, 411h
0x1800d5890  mov     [rbp+290h+var_2F0], 439h
0x1800d5897  mov     [rsp+390h+var_370], ecx
0x1800d589b  lea     rax, aImeImejpDictsS; "\\IME\\IMEJP\\DICTS\\SDDS0411.DIC"
0x1800d58a2  mov     [rsp+390h+var_368], rax
0x1800d58a7  xor     edx, edx; Val
0x1800d58a9  mov     [rsp+390h+var_360], ecx
0x1800d58ad  lea     rax, aSystem32JaJpSd; "\\system32\\ja-jp\\SDDS0411.DIC"
0x1800d58b4  mov     [rsp+390h+var_358], rax
0x1800d58b9  mov     ecx, 404h
0x1800d58be  lea     rax, aSystem32ZhTwSd; "\\system32\\zh-tw\\SDDS0404.DIC"
0x1800d58c5  mov     [rsp+390h+var_350], ecx
0x1800d58c9  mov     [rsp+390h+var_348], rax
0x1800d58ce  mov     r8d, 208h; Size
0x1800d58d4  lea     rax, aImeImetcDictsI; "\\IME\\IMETC\\DICTS\\IMTCT.IMD"
0x1800d58db  mov     [rsp+390h+var_340], ecx
0x1800d58df  mov     [rsp+390h+var_338], rax
0x1800d58e4  lea     rax, aSystem32ZhTwCh; "\\system32\\zh-tw\\chtmain.DIC"
0x1800d58eb  mov     [rsp+390h+var_328], rax
0x1800d58f0  lea     rax, aInputmethodChs; "\\InputMethod\\CHS\\ChsPinyin.lm"
0x1800d58f7  mov     [rsp+390h+var_318], rax
0x1800d58fc  lea     rax, aSystem32ZhCnCh; "\\system32\\zh-cn\\ChsPinyin.lm"
0x1800d5903  mov     [rbp+290h+var_308], rax
0x1800d5907  lea     rax, aSystem32ZhHkCh; "\\system32\\zh-hk\\ChtAP.sdc"
0x1800d590e  mov     [rbp+290h+var_2F8], rax
0x1800d5912  lea     rax, aSystem32HiInSd; "\\System32\\hi-in\\SDDS0439.dic"
0x1800d5919  mov     [rbp+290h+var_2E8], rax
0x1800d591d  lea     rax, aSystem32BnInSd; "\\System32\\bn-in\\SDDS0445.dic"
0x1800d5924  mov     [rbp+290h+var_2D8], rax
0x1800d5928  lea     rax, aSystem32PaInSd; "\\System32\\pa-in\\SDDS0446.dic"
0x1800d592f  mov     [rbp+290h+var_2C8], rax
0x1800d5933  lea     rax, aSystem32GuInSd; "\\System32\\gu-in\\SDDS0447.dic"
0x1800d593a  mov     [rbp+290h+var_2B8], rax
0x1800d593e  lea     rax, aSystem32OrInSd; "\\System32\\or-in\\SDDS0448.dic"
0x1800d5945  mov     [rbp+290h+var_2A8], rax
0x1800d5949  lea     rax, aSystem32TaInSd; "\\System32\\ta-in\\SDDS0449.dic"
0x1800d5950  mov     [rbp+290h+var_298], rax
0x1800d5954  lea     rax, aSystem32TeInSd; "\\System32\\te-in\\SDDS044A.dic"
0x1800d595b  mov     [rbp+290h+var_288], rax
0x1800d595f  lea     rax, aSystem32KnInSd; "\\System32\\kn-in\\SDDS044B.dic"
0x1800d5966  mov     [rbp+290h+var_278], rax
0x1800d596a  lea     rax, aSystem32MlInSd; "\\System32\\ml-in\\SDDS044C.dic"
0x1800d5971  mov     [rsp+390h+var_330], ecx
0x1800d5975  mov     ecx, 804h
0x1800d597a  mov     [rbp+290h+var_268], rax
0x1800d597e  lea     rax, aSystem32MrInSd; "\\System32\\mr-in\\SDDS044E.dic"
0x1800d5985  mov     [rsp+390h+var_320], ecx
0x1800d5989  mov     [rbp+290h+var_310], ecx
0x1800d598c  lea     rcx, [rbp+290h+Buffer]; void *
0x1800d5990  mov     [rbp+290h+var_258], rax
0x1800d5994  mov     [rbp+290h+var_2E0], 445h
0x1800d599b  mov     [rbp+290h+var_2D0], 446h
0x1800d59a2  mov     [rbp+290h+var_2C0], 447h
0x1800d59a9  mov     [rbp+290h+var_2B0], 448h
0x1800d59b0  mov     [rbp+290h+var_2A0], 449h
0x1800d59b7  mov     [rbp+290h+var_290], 44Ah
0x1800d59be  mov     [rbp+290h+var_280], 44Bh
0x1800d59c5  mov     [rbp+290h+var_270], 44Ch
0x1800d59cc  mov     [rbp+290h+var_260], 44Eh
0x1800d59d3  call    memset_0
0x1800d59d8  mov     edx, 104h; uSize
0x1800d59dd  lea     rcx, [rbp+290h+Buffer]; lpBuffer
0x1800d59e1  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800d59e7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d59eb  lea     rax, [rbp+290h+Buffer]
0x1800d59ef  xor     r15d, r15d
0x1800d59f2  inc     rdi
0x1800d59f5  cmp     [rax+rdi*2], r15w
0x1800d59fa  jnz     short loc_1800D59F2
0x1800d59fc  mov     sil, r15b
0x1800d59ff  lea     rbx, [rsp+390h+var_370]
0x1800d5a04  lea     rax, [rbp+290h+Buffer]
0x1800d5a08  cmp     rbx, rax
0x1800d5a0b  jz      short loc_1800D5A6B
0x1800d5a0d  cmp     [rbx], r14d
0x1800d5a10  jnz     short loc_1800D5A58
0x1800d5a12  lea     rcx, [rdi+rdi]
0x1800d5a16  cmp     rcx, 208h
0x1800d5a1d  jnb     short loc_1800D5A65
0x1800d5a1f  mov     r8, [rbx+8]; Source
0x1800d5a23  mov     sil, 1
0x1800d5a26  mov     [rbp+rcx+290h+Buffer], r15w
0x1800d5a2c  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800d5a30  inc     r9; MaxCount
0x1800d5a33  cmp     [r8+r9*2], r15w
0x1800d5a38  jnz     short loc_1800D5A30
0x1800d5a3a  mov     edx, 104h; SizeInWords
0x1800d5a3f  lea     rcx, [rbp+290h+Buffer]; Destination
0x1800d5a43  call    cs:__imp_wcsncat_s
0x1800d5a49  lea     rcx, [rbp+290h+Buffer]; lpFileName
0x1800d5a4d  call    cs:__imp_GetFileAttributesW
0x1800d5a53  cmp     eax, 0FFFFFFFFh
0x1800d5a56  jnz     short loc_1800D5A5E
0x1800d5a58  add     rbx, 10h
0x1800d5a5c  jmp     short loc_1800D5A04
0x1800d5a5e  mov     eax, 1
0x1800d5a63  jmp     short loc_1800D5A74
0x1800d5a65  call    __report_rangecheckfailure
0x1800d5a6b  test    sil, sil
0x1800d5a6e  mov     eax, r15d
0x1800d5a71  setz    al
0x1800d5a74  mov     rcx, [rbp+290h+var_40]
0x1800d5a7b  xor     rcx, rsp; StackCookie
0x1800d5a7e  call    __security_check_cookie
0x1800d5a83  add     rsp, 368h
0x1800d5a8a  pop     r15
0x1800d5a8c  pop     r14
0x1800d5a8e  pop     rdi
0x1800d5a8f  pop     rsi
0x1800d5a90  pop     rbx
0x1800d5a91  pop     rbp
0x1800d5a92  retn
```
