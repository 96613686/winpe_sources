# LVBuildDescriptionString(HWND__ *,int,int *,int,ushort * *)

- ea: `0x18002ef5c`
- end: `0x18002f2b6`
- name: `?LVBuildDescriptionString@@YAJPEAUHWND__@@HPEAHHPEAPEAG@Z`
- size: `858`
- prototype: `__int64 __fastcall(HWND, int, int *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18002f2bc`
- `0x18002f4a8`

## callees

- `0x18000d1cc`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180026230`
- `0x18002ef5c`
- `0x18002f80c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002f096`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002f096`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f0bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f157`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f1ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f1f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f212`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f0bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f157`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f1ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f1f2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002f212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f27d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f27d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f014`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f014`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002f02e`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002f02e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002f044`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002f044`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f258`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f258`

## pseudocode

```c
__int64 __fastcall LVBuildDescriptionString(HWND a1, int a2, int *a3, unsigned int a4, unsigned __int16 **a5)
{
  __int64 v6; // r15
  OLECHAR *v7; // r14
  LCID ThreadLocale; // eax
  int LocaleInfoW; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r11d
  unsigned __int64 v14; // rsi
  int v15; // eax
  __int16 v16; // r11
  int v17; // eax
  const unsigned __int16 *v18; // rbx
  unsigned int v19; // edi
  int v20; // r13d
  int i; // r12d
  WPARAM v22; // r15
  int Item; // eax
  HWND v24; // rcx
  unsigned int v25; // edi
  const unsigned __int16 *v26; // rbx
  unsigned __int16 **v27; // rbx
  unsigned __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v29; // [rsp+40h] [rbp-C0h]
  HWND v30; // [rsp+48h] [rbp-B8h]
  int *v31; // [rsp+50h] [rbp-B0h]
  tagLVCOLUMNW v32; // [rsp+58h] [rbp-A8h] BYREF
  struct tagLVITEMW v33; // [rsp+90h] [rbp-70h] BYREF
  WCHAR LCData[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v36; // [rsp+110h] [rbp+10h] BYREF
  char v37; // [rsp+1C0h] [rbp+C0h] BYREF

  v6 = a4;
  v31 = a3;
  v30 = a1;
  v29 = a4;
  memset_0(&v33.iSubItem, 0, 0x50u);
  v33.mask = 1;
  v33.iItem = a2;
  memset(&v32.iSubItem, 0, 28);
  v32.pszText = (LPWSTR)&v37;
  *(_OWORD *)&v32.mask = 0;
  v32.mask = 4;
  v32.cchTextMax = 80;
  if ( (unsigned __int64)(362 * v6) <= 0xFFFFFFFF )
  {
    v7 = (OLECHAR *)LocalAlloc(0x40u, (unsigned int)(362 * v6));
    if ( !v7 )
      return 2147942414LL;
    ThreadLocale = GetThreadLocale();
    LocaleInfoW = GetLocaleInfoW(ThreadLocale, 0xCu, LCData, 15);
    v28 = LocaleInfoW;
    if ( LocaleInfoW && LCData[0] )
    {
      if ( (int)StringCchLengthW(LCData, 0x10u, &v28) < 0 )
        goto LABEL_36;
      v14 = v28;
      if ( LCData[v28 - 1] == 32 )
      {
        v16 = 0;
      }
      else
      {
        v15 = _o_wcscat_s(LCData, v13, L" ");
        v16 = 0;
        if ( v15 )
        {
LABEL_35:
          v27 = a5;
          goto LABEL_37;
        }
        ++v14;
      }
    }
    else
    {
      v17 = _o_wcscpy_s(LCData, 16, L", ");
      v16 = 0;
      if ( v17 )
        goto LABEL_36;
      v14 = 2;
    }
    v18 = v7;
    v19 = (unsigned int)(362 * v6) >> 1;
    v20 = 1;
    for ( i = 0; i < (int)v6; ++i )
    {
      v22 = v31[i];
      if ( (int)v22 > 0 )
      {
        v33.pszText = (LPWSTR)&v36;
        v33.iSubItem = v22;
        v33.cchTextMax = 80;
        v36 = v16;
        Item = XSend_ListView_GetItem(v30, v11, v12, &v33);
        v16 = 0;
        if ( Item >= 0 && v33.pszText && *v33.pszText )
        {
          if ( v20 )
          {
            v20 = 0;
          }
          else
          {
            if ( (unsigned int)_o_wcscpy_s(v18, v19, LCData) )
              goto LABEL_36;
            v18 += v14;
            v19 -= v14;
          }
          v24 = v30;
          v32.iSubItem = v22;
          *v32.pszText = 0;
          if ( (int)XSend_ListView_GetColumn(v24, v11, v22, &v32) >= 0 && *v32.pszText )
          {
            if ( (unsigned int)_o_wcscpy_s(v18, v19, v32.pszText) )
              goto LABEL_36;
            v28 = 0;
            if ( (int)StringCchLengthW(v18, v19, &v28) < 0 )
              goto LABEL_36;
            v25 = v19 - v28;
            v26 = &v18[v28];
            if ( (unsigned int)_o_wcscpy_s(v26, v25, L": ") )
              goto LABEL_35;
            v18 = v26 + 2;
            v19 = v25 - 2;
          }
          if ( (unsigned int)_o_wcscpy_s(v18, v19, v33.pszText) )
            goto LABEL_36;
          v28 = 0;
          if ( (int)StringCchLengthW(v18, v19, &v28) < 0 )
            goto LABEL_36;
          v19 -= v28;
          v18 += v28;
        }
      }
      LODWORD(v6) = v29;
    }
    if ( v18 != v7 )
    {
      v27 = a5;
      *a5 = SysAllocString(v7);
LABEL_37:
      LocalFree(v7);
      return *v27 == 0;
    }
LABEL_36:
    v27 = a5;
    goto LABEL_37;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002ef5c  push    rbp
0x18002ef5e  push    rbx
0x18002ef5f  push    rsi
0x18002ef60  push    rdi
0x18002ef61  push    r12
0x18002ef63  push    r13
0x18002ef65  push    r14
0x18002ef67  push    r15
0x18002ef69  lea     rbp, [rsp-188h]
0x18002ef71  sub     rsp, 288h
0x18002ef78  mov     rax, cs:__security_cookie
0x18002ef7f  xor     rax, rsp
0x18002ef82  mov     [rbp+1C0h+var_50], rax
0x18002ef89  mov     rax, [rbp+1C0h+arg_20]
0x18002ef90  mov     ebx, edx
0x18002ef92  mov     r15d, r9d
0x18002ef95  mov     edi, 50h ; 'P'
0x18002ef9a  mov     [rsp+2C0h+var_270], r8
0x18002ef9f  xor     edx, edx; Val
0x18002efa1  mov     [rsp+2C0h+var_278], rcx
0x18002efa6  mov     r8d, edi; Size
0x18002efa9  lea     rcx, [rbp+1C0h+var_230.iSubItem]; void *
0x18002efad  mov     [rsp+2C0h+var_280], r15d
0x18002efb2  mov     [rsp+2C0h+var_290], rax
0x18002efb7  call    memset_0
0x18002efbc  xor     eax, eax
0x18002efbe  mov     [rbp+1C0h+var_230.mask], 1
0x18002efc5  xorps   xmm0, xmm0
0x18002efc8  mov     qword ptr [rbp+1C0h+var_268.cxIdeal], rax
0x18002efcc  lea     rax, [rbp+1C0h+var_100]
0x18002efd3  mov     [rbp+1C0h+var_230.iItem], ebx
0x18002efd6  movups  xmmword ptr [rsp+2C0h+var_268.pszText], xmm0
0x18002efdb  mov     [rsp+2C0h+var_268.pszText], rax
0x18002efe0  mov     eax, 0FFFFFFFFh
0x18002efe5  imul    rcx, r15, 16Ah
0x18002efec  movups  xmmword ptr [rsp+2C0h+var_268.mask], xmm0
0x18002eff1  movups  xmmword ptr [rsp+2C0h+var_268.iImage], xmm0
0x18002eff6  mov     [rsp+2C0h+var_268.mask], 4
0x18002effe  mov     [rsp+2C0h+var_268.cchTextMax], edi
0x18002f002  cmp     rcx, rax
0x18002f005  ja      loc_18002F28E
0x18002f00b  mov     edi, ecx
0x18002f00d  mov     edx, ecx; uBytes
0x18002f00f  mov     ecx, 40h ; '@'; uFlags
0x18002f014  call    cs:__imp_LocalAlloc
0x18002f01a  xor     ebx, ebx
0x18002f01c  mov     r14, rax
0x18002f01f  test    rax, rax
0x18002f022  jnz     short loc_18002F02E
0x18002f024  mov     eax, 8007000Eh
0x18002f029  jmp     loc_18002F293
0x18002f02e  call    cs:__imp_GetThreadLocale
0x18002f034  mov     r9d, 0Fh; cchData
0x18002f03a  lea     r8, [rbp+1C0h+LCData]; lpLCData
0x18002f03e  mov     ecx, eax; Locale
0x18002f040  lea     edx, [r9-3]; LCType
0x18002f044  call    cs:__imp_GetLocaleInfoW
0x18002f04a  movsxd  rcx, eax
0x18002f04d  mov     [rsp+2C0h+var_288], rcx
0x18002f052  test    eax, eax
0x18002f054  jz      short loc_18002F0AC
0x18002f056  cmp     [rbp+1C0h+LCData], bx
0x18002f05a  jz      short loc_18002F0AC
0x18002f05c  mov     r11d, 10h
0x18002f062  lea     r8, [rsp+2C0h+var_288]; unsigned __int64 *
0x18002f067  mov     edx, r11d; unsigned __int64
0x18002f06a  lea     rcx, [rbp+1C0h+LCData]; unsigned __int16 *
0x18002f06e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f073  test    eax, eax
0x18002f075  js      loc_18002F272
0x18002f07b  mov     rsi, [rsp+2C0h+var_288]
0x18002f080  cmp     [rbp+rsi*2+1C0h+var_1D2], 20h ; ' '
0x18002f086  jz      short loc_18002F0D2
0x18002f088  lea     r8, asc_180053FDC; " "
0x18002f08f  mov     edx, r11d
0x18002f092  lea     rcx, [rbp+1C0h+LCData]
0x18002f096  call    cs:__imp__o_wcscat_s
0x18002f09c  xor     r11d, r11d
0x18002f09f  test    eax, eax
0x18002f0a1  jnz     loc_18002F268
0x18002f0a7  inc     rsi
0x18002f0aa  jmp     short loc_18002F0D5
0x18002f0ac  lea     r8, asc_1800573F0; ", "
0x18002f0b3  mov     edx, 10h
0x18002f0b8  lea     rcx, [rbp+1C0h+LCData]
0x18002f0bc  call    cs:__imp__o_wcscpy_s
0x18002f0c2  xor     r11d, r11d
0x18002f0c5  test    eax, eax
0x18002f0c7  jnz     loc_18002F272
0x18002f0cd  lea     esi, [rax+2]
0x18002f0d0  jmp     short loc_18002F0D5
0x18002f0d2  xor     r11d, r11d
0x18002f0d5  mov     rbx, r14
0x18002f0d8  shr     edi, 1
0x18002f0da  mov     r13d, 1
0x18002f0e0  mov     r12d, r11d
0x18002f0e3  cmp     r12d, r15d
0x18002f0e6  jge     loc_18002F250
0x18002f0ec  mov     rcx, [rsp+2C0h+var_270]
0x18002f0f1  movsxd  rax, r12d
0x18002f0f4  movsxd  r15, dword ptr [rcx+rax*4]
0x18002f0f8  test    r15d, r15d
0x18002f0fb  jle     loc_18002F243
0x18002f101  mov     rcx, [rsp+2C0h+var_278]; HWND
0x18002f106  lea     rax, [rbp+1C0h+var_1B0]
0x18002f10a  lea     r9, [rbp+1C0h+var_230]; struct tagLVITEMW *
0x18002f10e  mov     [rbp+1C0h+var_230.pszText], rax
0x18002f112  mov     [rbp+1C0h+var_230.iSubItem], r15d
0x18002f116  mov     [rbp+1C0h+var_230.cchTextMax], 50h ; 'P'
0x18002f11d  mov     [rbp+1C0h+var_1B0], r11w
0x18002f122  call    ?XSend_ListView_GetItem@@YAJPEAUHWND__@@I_KPEAUtagLVITEMW@@I@Z; XSend_ListView_GetItem(HWND__ *,uint,unsigned __int64,tagLVITEMW *,uint)
0x18002f127  xor     r11d, r11d
0x18002f12a  test    eax, eax
0x18002f12c  js      loc_18002F243
0x18002f132  mov     rax, [rbp+1C0h+var_230.pszText]
0x18002f136  test    rax, rax
0x18002f139  jz      loc_18002F243
0x18002f13f  cmp     [rax], r11w
0x18002f143  jz      loc_18002F243
0x18002f149  test    r13d, r13d
0x18002f14c  jnz     short loc_18002F170
0x18002f14e  mov     edx, edi
0x18002f150  lea     r8, [rbp+1C0h+LCData]
0x18002f154  mov     rcx, rbx
0x18002f157  call    cs:__imp__o_wcscpy_s
0x18002f15d  xor     r11d, r11d
0x18002f160  test    eax, eax
0x18002f162  jnz     loc_18002F272
0x18002f168  lea     rbx, [rbx+rsi*2]
0x18002f16c  sub     edi, esi
0x18002f16e  jmp     short loc_18002F173
0x18002f170  mov     r13d, r11d
0x18002f173  mov     rax, [rsp+2C0h+var_268.pszText]
0x18002f178  lea     r9, [rsp+2C0h+var_268]; struct tagLVCOLUMNW *
0x18002f17d  mov     rcx, [rsp+2C0h+var_278]; HWND
0x18002f182  mov     r8, r15; unsigned __int64
0x18002f185  mov     [rsp+2C0h+var_268.iSubItem], r15d
0x18002f18a  mov     [rax], r11w
0x18002f18e  call    ?XSend_ListView_GetColumn@@YAJPEAUHWND__@@I_KPEAUtagLVCOLUMNW@@I@Z; XSend_ListView_GetColumn(HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,uint)
0x18002f193  xor     r15d, r15d
0x18002f196  test    eax, eax
0x18002f198  js      short loc_18002F206
0x18002f19a  mov     r8, [rsp+2C0h+var_268.pszText]
0x18002f19f  cmp     [r8], r15w
0x18002f1a3  jz      short loc_18002F206
0x18002f1a5  mov     edx, edi
0x18002f1a7  mov     rcx, rbx
0x18002f1aa  mov     r15d, edi
0x18002f1ad  call    cs:__imp__o_wcscpy_s
0x18002f1b3  xor     r11d, r11d
0x18002f1b6  test    eax, eax
0x18002f1b8  jnz     loc_18002F272
0x18002f1be  lea     r8, [rsp+2C0h+var_288]; unsigned __int64 *
0x18002f1c3  mov     [rsp+2C0h+var_288], r11
0x18002f1c8  mov     edx, r15d; unsigned __int64
0x18002f1cb  mov     rcx, rbx; unsigned __int16 *
0x18002f1ce  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f1d3  test    eax, eax
0x18002f1d5  js      loc_18002F272
0x18002f1db  mov     rax, [rsp+2C0h+var_288]
0x18002f1e0  lea     r8, asc_1800573F8; ": "
0x18002f1e7  sub     edi, eax
0x18002f1e9  mov     edx, edi
0x18002f1eb  lea     rbx, [rbx+rax*2]
0x18002f1ef  mov     rcx, rbx
0x18002f1f2  call    cs:__imp__o_wcscpy_s
0x18002f1f8  xor     r15d, r15d
0x18002f1fb  test    eax, eax
0x18002f1fd  jnz     short loc_18002F26B
0x18002f1ff  add     rbx, 4
0x18002f203  add     edi, 0FFFFFFFEh
0x18002f206  mov     r8, [rbp+1C0h+var_230.pszText]
0x18002f20a  mov     rcx, rbx
0x18002f20d  mov     edx, edi
0x18002f20f  mov     r15d, edi
0x18002f212  call    cs:__imp__o_wcscpy_s
0x18002f218  xor     r11d, r11d
0x18002f21b  test    eax, eax
0x18002f21d  jnz     short loc_18002F272
0x18002f21f  lea     r8, [rsp+2C0h+var_288]; unsigned __int64 *
0x18002f224  mov     [rsp+2C0h+var_288], r11
0x18002f229  mov     edx, r15d; unsigned __int64
0x18002f22c  mov     rcx, rbx; unsigned __int16 *
0x18002f22f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f234  test    eax, eax
0x18002f236  js      short loc_18002F272
0x18002f238  mov     rax, [rsp+2C0h+var_288]
0x18002f23d  sub     edi, eax
0x18002f23f  lea     rbx, [rbx+rax*2]
0x18002f243  mov     r15d, [rsp+2C0h+var_280]
0x18002f248  inc     r12d
0x18002f24b  jmp     loc_18002F0E3
0x18002f250  cmp     rbx, r14
0x18002f253  jz      short loc_18002F272
0x18002f255  mov     rcx, r14; psz
0x18002f258  call    cs:__imp_SysAllocString
0x18002f25e  mov     rbx, [rsp+2C0h+var_290]
0x18002f263  mov     [rbx], rax
0x18002f266  jmp     short loc_18002F277
0x18002f268  xor     r15d, r15d
0x18002f26b  mov     rbx, [rsp+2C0h+var_290]
0x18002f270  jmp     short loc_18002F27A
0x18002f272  mov     rbx, [rsp+2C0h+var_290]
0x18002f277  xor     r15d, r15d
0x18002f27a  mov     rcx, r14; hMem
0x18002f27d  call    cs:__imp_LocalFree
0x18002f283  cmp     [rbx], r15
0x18002f286  mov     eax, r15d
0x18002f289  setz    al
0x18002f28c  jmp     short loc_18002F293
0x18002f28e  mov     eax, 80070057h
0x18002f293  mov     rcx, [rbp+1C0h+var_50]
0x18002f29a  xor     rcx, rsp; StackCookie
0x18002f29d  call    __security_check_cookie
0x18002f2a2  add     rsp, 288h
0x18002f2a9  pop     r15
0x18002f2ab  pop     r14
0x18002f2ad  pop     r13
0x18002f2af  pop     r12
0x18002f2b1  pop     rdi
0x18002f2b2  pop     rsi
0x18002f2b3  pop     rbx
0x18002f2b4  pop     rbp
0x18002f2b5  retn
```
