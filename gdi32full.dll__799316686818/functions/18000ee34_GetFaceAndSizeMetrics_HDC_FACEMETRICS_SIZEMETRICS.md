# GetFaceAndSizeMetrics(HDC__ *,FACEMETRICS *,SIZEMETRICS *)

- ea: `0x18000ee34`
- end: `0x18000f26a`
- name: `?GetFaceAndSizeMetrics@@YAJPEAUHDC__@@PEAUFACEMETRICS@@PEAUSIZEMETRICS@@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(HDC hdc, struct FACEMETRICS *, struct SIZEMETRICS *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800142f4`

## callees

- `0x180009d00`
- `0x18000a090`
- `0x18000d620`
- `0x18000d6c0`
- `0x18000e5a0`
- `0x18000ed60`
- `0x18000ee34`
- `0x180010210`
- `0x180010690`
- `0x1800141c0`
- `0x180025fb0`
- `0x18004b8d0`
- `0x180057800`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef7a`
- `GDI32!GetTextMetricsA` at `0x18000f133`
- `GDI32!GetTextMetricsA` at `0x18000f1d6`
- `GDI32!GetTextMetricsA` at `0x18000f133`
- `GDI32!GetTextMetricsA` at `0x18000f1d6`
- `GDI32!SelectObject` at `0x18000f123`
- `GDI32!SelectObject` at `0x18000f152`
- `GDI32!SelectObject` at `0x18000f185`
- `GDI32!SelectObject` at `0x18000f123`
- `GDI32!SelectObject` at `0x18000f152`
- `GDI32!SelectObject` at `0x18000f185`
- `GDI32!DeleteObject` at `0x18000f15b`
- `GDI32!DeleteObject` at `0x18000f197`
- `GDI32!DeleteObject` at `0x18000f15b`
- `GDI32!DeleteObject` at `0x18000f197`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x18000ef4a`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x18000efae`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x18000ef4a`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x18000efae`
- `win32u!NtGdiGetTextFaceW` at `0x18000f0f8`
- `win32u!NtGdiGetTextFaceW` at `0x18000f0f8`

## pseudocode

```c
__int64 __fastcall GetFaceAndSizeMetrics(HDC hdc, struct FACEMETRICS *a2, struct tagSIZE *a3)
{
  LONG v6; // ecx
  bool v7; // zf
  void *DCObject; // rax
  int v9; // eax
  signed __int64 v10; // r15
  char *v11; // rax
  char *v12; // rdi
  signed __int64 v13; // rax
  int v14; // edx
  wchar_t *v15; // r9
  signed __int64 v16; // rax
  __int64 v17; // rax
  LONG lfEscapement; // ecx
  unsigned int EscapementID; // eax
  LONG v20; // r9d
  unsigned int v21; // eax
  unsigned int v22; // ebx
  __int64 result; // rax
  HFONT v24; // rax
  HGDIOBJ v25; // rdi
  HGDIOBJ v26; // rax
  HGDIOBJ v27; // rax
  LONG v28; // ecx
  __int64 v29; // [rsp+20h] [rbp-69h] BYREF
  int v30; // [rsp+28h] [rbp-61h]
  tagTEXTMETRICA tm; // [rsp+30h] [rbp-59h] BYREF
  LOGFONTA pv; // [rsp+68h] [rbp-21h] BYREF

  memset(&tm, 0, sizeof(tm));
  if ( !hdc || !a2 || !a3 )
    return 2147942487LL;
  GetWindowExtEx(hdc, a3 + 2);
  GetViewportExtEx(hdc, a3 + 3);
  v29 = 0;
  v30 = 0;
  if ( !(unsigned int)GdiRealizationInfo(hdc, &v29) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v6 = HIDWORD(v29);
  v7 = BYTE1(v29) == 0;
  a3[6].cx = BYTE1(v29);
  if ( !v7 )
    v6 = 0;
  a3[6].cy = v6;
  a3[7].cx = GetDCDpiScaleValue(hdc);
  memset(&pv, 0, sizeof(pv));
  DCObject = (void *)GetDCObject(hdc, 655360);
  if ( !DCObject || !GetObjectA(DCObject, 60, &pv) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v7 = pv.lfWidth == 0;
  a3[1].cx = 0;
  if ( !v7 )
  {
    pv.lfWidth = 0;
    v24 = CreateFontIndirectA(&pv);
    v25 = SelectObject(hdc, v24);
    if ( !GetTextMetricsA(hdc, &tm) )
    {
      if ( v25 )
      {
        v27 = SelectObject(hdc, v25);
        if ( v27 )
          DeleteObject(v27);
      }
      return HRESULT_FROM_LAST_WIN32_ERROR();
    }
    a3[1].cx = tm.tmAveCharWidth;
    if ( v25 )
    {
      v26 = SelectObject(hdc, v25);
      DeleteObject(v26);
    }
  }
  v29 = 0;
  v9 = ((__int64 (__fastcall *)(HDC, _QWORD, _QWORD, __int64 *))NtGdiGetOutlineTextMetricsInternalW)(hdc, 0, 0, &v29);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 < 0 )
      return (unsigned int)-2147024809;
    if ( !(unsigned int)CheckInitUspMemory() )
      return (unsigned int)-2147024882;
    v11 = (char *)HeapAlloc(ghHeap, 0, v10);
    v12 = v11;
    if ( !v11 )
      return (unsigned int)-2147024882;
    memset_0(v11, 0, v10);
    v29 = 0;
    if ( (unsigned int)((__int64 (__fastcall *)(HDC, _QWORD, char *, __int64 *))NtGdiGetOutlineTextMetricsInternalW)(
                         hdc,
                         (unsigned int)v10,
                         v12,
                         &v29) )
    {
      v13 = *((_QWORD *)v12 + 26);
      if ( !v13 || v13 >= v10 )
      {
        v22 = -2147024882;
        goto LABEL_26;
      }
      v14 = 64;
      *(_DWORD *)a2 = *((_DWORD *)v12 + 8);
      *((_BYTE *)a2 + 138) = v12[56];
      *((_BYTE *)a2 + 139) = v12[57];
      *((_BYTE *)a2 + 140) = v12[58];
      *((_BYTE *)a2 + 141) = v12[59];
      *((_BYTE *)a2 + 142) = v12[60];
      *((_WORD *)a2 + 67) = *((_WORD *)v12 + 24);
      *((_WORD *)a2 + 68) = *((_WORD *)v12 + 26);
      v15 = (wchar_t *)&v12[*((_QWORD *)v12 + 26)];
      if ( *v15 != 64 && (v16 = *((_QWORD *)v12 + 25)) != 0 && v16 < v10 && *(_WORD *)&v12[v16] == 64 )
      {
        *((_WORD *)a2 + 2) = 64;
        v17 = 6;
        v15 = (wchar_t *)&v12[*((_QWORD *)v12 + 26)];
      }
      else
      {
        v14 = 65;
        v17 = 4;
      }
      UnicodeCopyString((wchar_t *)((char *)a2 + v17), v15, v14);
      lfEscapement = pv.lfEscapement;
      *((_WORD *)a2 + 66) = 0;
      a3->cx = *((_DWORD *)v12 + 1);
      a3[4].cx = *((_DWORD *)v12 + 2);
      a3[4].cy = *((_DWORD *)v12 + 9);
      a3[5].cx = *((_DWORD *)v12 + 4);
      a3->cy = *((_DWORD *)v12 + 6);
      EscapementID = GetEscapementID(lfEscapement);
      v7 = a3[1].cx == 0;
      a3[1].cy = EscapementID;
      if ( v7 )
        a3[1].cx = v20;
      a3[5].cy = *((_DWORD *)v12 + 24);
      v21 = 0;
    }
    else
    {
      v21 = HRESULT_FROM_LAST_WIN32_ERROR();
    }
    v22 = v21;
LABEL_26:
    UspFreeMem(v12);
    return v22;
  }
  if ( !(unsigned int)NtGdiGetTextFaceW(hdc, 65, (char *)a2 + 4, 0) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  *((_WORD *)a2 + 66) = 0;
  if ( !GetTextMetricsA(hdc, &tm) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v28 = pv.lfEscapement;
  *(_DWORD *)a2 = tm.tmWeight;
  *((_BYTE *)a2 + 138) = tm.tmItalic;
  *((_BYTE *)a2 + 139) = tm.tmUnderlined;
  *((_BYTE *)a2 + 140) = tm.tmStruckOut;
  *((_BYTE *)a2 + 141) = tm.tmPitchAndFamily;
  *((_BYTE *)a2 + 142) = tm.tmCharSet;
  *((_WORD *)a2 + 67) = tm.tmFirstChar;
  *((_WORD *)a2 + 68) = tm.tmDefaultChar;
  a3->cx = tm.tmHeight;
  a3[4].cx = tm.tmAscent;
  a3[4].cy = tm.tmOverhang;
  a3[5].cx = tm.tmInternalLeading;
  a3->cy = tm.tmAveCharWidth;
  a3[1].cy = GetEscapementID(v28);
  result = 0;
  a3[5].cy = 0;
  return result;
}

```

## disassembly

```asm
0x18000ee34  push    rbp
0x18000ee36  push    rbx
0x18000ee37  push    rsi
0x18000ee38  push    rdi
0x18000ee39  push    r12
0x18000ee3b  push    r14
0x18000ee3d  push    r15
0x18000ee3f  lea     rbp, [rsp-27h]
0x18000ee44  sub     rsp, 0B0h
0x18000ee4b  mov     rax, cs:__security_cookie
0x18000ee52  xor     rax, rsp
0x18000ee55  mov     [rbp+57h+var_38], rax
0x18000ee59  xorps   xmm0, xmm0
0x18000ee5c  xor     eax, eax
0x18000ee5e  mov     qword ptr [rbp+57h+tm.tmItalic], rax
0x18000ee62  mov     rbx, r8
0x18000ee65  mov     r14, rdx
0x18000ee68  mov     rsi, rcx
0x18000ee6b  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x18000ee6f  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x18000ee73  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x18000ee77  test    rcx, rcx
0x18000ee7a  jz      loc_18000F0E3
0x18000ee80  test    rdx, rdx
0x18000ee83  jz      loc_18000F0E3
0x18000ee89  test    rbx, rbx
0x18000ee8c  jz      loc_18000F0E3
0x18000ee92  lea     rdx, [r8+10h]; lpsize
0x18000ee96  call    GetWindowExtEx
0x18000ee9b  lea     rdx, [rbx+18h]; lpsize
0x18000ee9f  mov     rcx, rsi; hdc
0x18000eea2  call    GetViewportExtEx
0x18000eea7  xor     eax, eax
0x18000eea9  lea     rdx, [rbp+57h+var_C0]
0x18000eead  mov     rcx, rsi
0x18000eeb0  mov     [rbp+57h+var_C0], rax
0x18000eeb4  mov     [rbp+57h+var_B8], eax
0x18000eeb7  call    GdiRealizationInfo
0x18000eebc  test    eax, eax
0x18000eebe  jz      loc_18000F106
0x18000eec4  movzx   edx, byte ptr [rbp+57h+var_C0+1]
0x18000eec8  xor     eax, eax
0x18000eeca  mov     ecx, dword ptr [rbp+57h+var_C0+4]
0x18000eecd  test    edx, edx
0x18000eecf  mov     [rbx+30h], edx
0x18000eed2  cmovnz  ecx, eax
0x18000eed5  mov     [rbx+34h], ecx
0x18000eed8  mov     rcx, rsi
0x18000eedb  call    GetDCDpiScaleValue
0x18000eee0  xorps   xmm0, xmm0
0x18000eee3  mov     [rbx+38h], eax
0x18000eee6  movups  [rbp+57h+var_58], xmm0
0x18000eeea  mov     edx, 0A0000h
0x18000eeef  mov     rcx, rsi
0x18000eef2  movups  [rbp+57h+var_58+0Ch], xmm0
0x18000eef6  movups  [rbp+57h+pv], xmm0
0x18000eefa  movups  [rbp+57h+var_68], xmm0
0x18000eefe  call    GetDCObject
0x18000ef03  test    rax, rax
0x18000ef06  jz      loc_18000F106
0x18000ef0c  lea     r8, [rbp+57h+pv]; pv
0x18000ef10  mov     edx, 3Ch ; '<'; c
0x18000ef15  mov     rcx, rax; h
0x18000ef18  call    GetObjectA
0x18000ef1d  test    eax, eax
0x18000ef1f  jz      loc_18000F106
0x18000ef25  cmp     dword ptr [rbp+57h+pv+4], 0
0x18000ef29  mov     dword ptr [rbx+8], 0
0x18000ef30  jnz     loc_18000F10D
0x18000ef36  lea     r9, [rbp+57h+var_C0]
0x18000ef3a  mov     [rbp+57h+var_C0], 0
0x18000ef42  xor     r8d, r8d
0x18000ef45  xor     edx, edx
0x18000ef47  mov     rcx, rsi
0x18000ef4a  call    cs:__imp_NtGdiGetOutlineTextMetricsInternalW
0x18000ef50  movsxd  r15, eax
0x18000ef53  test    eax, eax
0x18000ef55  jz      loc_18000F0EA
0x18000ef5b  js      loc_18000F1A2
0x18000ef61  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x18000ef66  test    eax, eax
0x18000ef68  jz      loc_18000F166
0x18000ef6e  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x18000ef75  mov     r8, r15; dwBytes
0x18000ef78  xor     edx, edx; dwFlags
0x18000ef7a  call    cs:__imp_HeapAlloc
0x18000ef80  mov     rdi, rax
0x18000ef83  test    rax, rax
0x18000ef86  jz      loc_18000F166
0x18000ef8c  mov     r8, r15; Size
0x18000ef8f  xor     edx, edx; Val
0x18000ef91  mov     rcx, rax; void *
0x18000ef94  call    memset_0
0x18000ef99  lea     r9, [rbp+57h+var_C0]
0x18000ef9d  mov     [rbp+57h+var_C0], 0
0x18000efa5  mov     r8, rdi
0x18000efa8  mov     edx, r15d
0x18000efab  mov     rcx, rsi
0x18000efae  call    cs:__imp_NtGdiGetOutlineTextMetricsInternalW
0x18000efb4  test    eax, eax
0x18000efb6  jz      loc_18000F170
0x18000efbc  mov     rax, [rdi+0D0h]
0x18000efc3  test    rax, rax
0x18000efc6  jz      loc_18000F0DC
0x18000efcc  cmp     rax, r15
0x18000efcf  jge     loc_18000F0DC
0x18000efd5  mov     eax, [rdi+20h]
0x18000efd8  mov     edx, 40h ; '@'
0x18000efdd  mov     [r14], eax
0x18000efe0  mov     al, [rdi+38h]
0x18000efe3  mov     [r14+8Ah], al
0x18000efea  mov     al, [rdi+39h]
0x18000efed  mov     [r14+8Bh], al
0x18000eff4  mov     al, [rdi+3Ah]
0x18000eff7  mov     [r14+8Ch], al
0x18000effe  mov     al, [rdi+3Bh]
0x18000f001  mov     [r14+8Dh], al
0x18000f008  mov     al, [rdi+3Ch]
0x18000f00b  mov     [r14+8Eh], al
0x18000f012  movzx   eax, word ptr [rdi+30h]
0x18000f016  mov     [r14+86h], ax
0x18000f01e  movzx   eax, word ptr [rdi+34h]
0x18000f022  mov     [r14+88h], ax
0x18000f02a  mov     r9, [rdi+0D0h]
0x18000f031  add     r9, rdi
0x18000f034  cmp     [r9], dx
0x18000f038  jz      short loc_18000F055
0x18000f03a  mov     rax, [rdi+0C8h]
0x18000f041  test    rax, rax
0x18000f044  jz      short loc_18000F055
0x18000f046  cmp     rax, r15
0x18000f049  jge     short loc_18000F055
0x18000f04b  cmp     [rax+rdi], dx
0x18000f04f  jz      loc_18000F1AC
0x18000f055  mov     edx, 41h ; 'A'
0x18000f05a  lea     eax, [rdx-3Dh]
0x18000f05d  mov     r8d, edx; int
0x18000f060  lea     rcx, [rax+r14]; wchar_t *
0x18000f064  mov     rdx, r9; wchar_t *
0x18000f067  call    ?UnicodeCopyString@@YAHPEA_W0H@Z; UnicodeCopyString(wchar_t *,wchar_t *,int)
0x18000f06c  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x18000f06f  xor     eax, eax
0x18000f071  mov     [r14+84h], ax
0x18000f079  mov     eax, [rdi+4]
0x18000f07c  mov     [rbx], eax
0x18000f07e  mov     eax, [rdi+8]
0x18000f081  mov     [rbx+20h], eax
0x18000f084  mov     eax, [rdi+24h]
0x18000f087  mov     [rbx+24h], eax
0x18000f08a  mov     eax, [rdi+10h]
0x18000f08d  mov     [rbx+28h], eax
0x18000f090  mov     r9d, [rdi+18h]
0x18000f094  mov     [rbx+4], r9d
0x18000f098  call    ?GetEscapementID@@YAIJ@Z; GetEscapementID(long)
0x18000f09d  cmp     dword ptr [rbx+8], 0
0x18000f0a1  mov     [rbx+0Ch], eax
0x18000f0a4  jnz     short loc_18000F0AA
0x18000f0a6  mov     [rbx+8], r9d
0x18000f0aa  mov     eax, [rdi+60h]
0x18000f0ad  mov     [rbx+2Ch], eax
0x18000f0b0  xor     eax, eax
0x18000f0b2  mov     ebx, eax
0x18000f0b4  mov     rcx, rdi; lpMem
0x18000f0b7  call    UspFreeMem
0x18000f0bc  mov     eax, ebx
0x18000f0be  mov     rcx, [rbp+57h+var_38]
0x18000f0c2  xor     rcx, rsp; StackCookie
0x18000f0c5  call    __security_check_cookie
0x18000f0ca  add     rsp, 0B0h
0x18000f0d1  pop     r15
0x18000f0d3  pop     r14
0x18000f0d5  pop     r12
0x18000f0d7  pop     rdi
0x18000f0d8  pop     rsi
0x18000f0d9  pop     rbx
0x18000f0da  pop     rbp
0x18000f0db  retn
0x18000f0dc  mov     ebx, 8007000Eh
0x18000f0e1  jmp     short loc_18000F0B4
0x18000f0e3  mov     eax, 80070057h
0x18000f0e8  jmp     short loc_18000F0BE
0x18000f0ea  xor     r9d, r9d
0x18000f0ed  lea     r8, [r14+4]
0x18000f0f1  mov     rcx, rsi
0x18000f0f4  lea     edx, [r9+41h]
0x18000f0f8  call    cs:__imp_NtGdiGetTextFaceW
0x18000f0fe  test    eax, eax
0x18000f100  jnz     loc_18000F1C5
0x18000f106  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18000f10b  jmp     short loc_18000F0BE
0x18000f10d  lea     rcx, [rbp+57h+pv]; lplf
0x18000f111  mov     dword ptr [rbp+57h+pv+4], 0
0x18000f118  call    CreateFontIndirectA
0x18000f11d  mov     rdx, rax; h
0x18000f120  mov     rcx, rsi; hdc
0x18000f123  call    cs:__imp_SelectObject
0x18000f129  lea     rdx, [rbp+57h+tm]; lptm
0x18000f12d  mov     rcx, rsi; hdc
0x18000f130  mov     rdi, rax
0x18000f133  call    cs:__imp_GetTextMetricsA
0x18000f139  test    eax, eax
0x18000f13b  jz      short loc_18000F17A
0x18000f13d  mov     ecx, [rbp+57h+tm.tmAveCharWidth]
0x18000f140  mov     [rbx+8], ecx
0x18000f143  test    rdi, rdi
0x18000f146  jz      loc_18000EF36
0x18000f14c  mov     rdx, rdi; h
0x18000f14f  mov     rcx, rsi; hdc
0x18000f152  call    cs:__imp_SelectObject
0x18000f158  mov     rcx, rax; ho
0x18000f15b  call    cs:__imp_DeleteObject
0x18000f161  jmp     loc_18000EF36
0x18000f166  mov     ebx, 8007000Eh
0x18000f16b  jmp     loc_18000F0BC
0x18000f170  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18000f175  jmp     loc_18000F0B2
0x18000f17a  test    rdi, rdi
0x18000f17d  jz      short loc_18000F106
0x18000f17f  mov     rdx, rdi; h
0x18000f182  mov     rcx, rsi; hdc
0x18000f185  call    cs:__imp_SelectObject
0x18000f18b  test    rax, rax
0x18000f18e  jz      loc_18000F106
0x18000f194  mov     rcx, rax; ho
0x18000f197  call    cs:__imp_DeleteObject
0x18000f19d  jmp     loc_18000F106
0x18000f1a2  mov     ebx, 80070057h
0x18000f1a7  jmp     loc_18000F0BC
0x18000f1ac  mov     [r14+4], dx
0x18000f1b1  mov     eax, 6
0x18000f1b6  mov     r9, [rdi+0D0h]
0x18000f1bd  add     r9, rdi
0x18000f1c0  jmp     loc_18000F05D
0x18000f1c5  xor     eax, eax
0x18000f1c7  lea     rdx, [rbp+57h+tm]; lptm
0x18000f1cb  mov     rcx, rsi; hdc
0x18000f1ce  mov     [r14+84h], ax
0x18000f1d6  call    cs:__imp_GetTextMetricsA
0x18000f1dc  test    eax, eax
0x18000f1de  jz      loc_18000F106
0x18000f1e4  mov     eax, [rbp+57h+tm.tmWeight]
0x18000f1e7  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x18000f1ea  mov     [r14], eax
0x18000f1ed  mov     al, [rbp+57h+tm.tmItalic]
0x18000f1f0  mov     [r14+8Ah], al
0x18000f1f7  mov     al, [rbp+57h+tm.tmUnderlined]
0x18000f1fa  mov     [r14+8Bh], al
0x18000f201  mov     al, [rbp+57h+tm.tmStruckOut]
0x18000f204  mov     [r14+8Ch], al
0x18000f20b  mov     al, [rbp+57h+tm.tmPitchAndFamily]
0x18000f20e  mov     [r14+8Dh], al
0x18000f215  mov     al, [rbp+57h+tm.tmCharSet]
0x18000f218  mov     [r14+8Eh], al
0x18000f21f  movzx   eax, [rbp+57h+tm.tmFirstChar]
0x18000f223  mov     [r14+86h], ax
0x18000f22b  movzx   eax, [rbp+57h+tm.tmDefaultChar]
0x18000f22f  mov     [r14+88h], ax
0x18000f237  mov     eax, [rbp+57h+tm.tmHeight]
0x18000f23a  mov     [rbx], eax
0x18000f23c  mov     eax, [rbp+57h+tm.tmAscent]
0x18000f23f  mov     [rbx+20h], eax
0x18000f242  mov     eax, [rbp+57h+tm.tmOverhang]
0x18000f245  mov     [rbx+24h], eax
0x18000f248  mov     eax, [rbp+57h+tm.tmInternalLeading]
0x18000f24b  mov     [rbx+28h], eax
0x18000f24e  mov     eax, [rbp+57h+tm.tmAveCharWidth]
0x18000f251  mov     [rbx+4], eax
0x18000f254  call    ?GetEscapementID@@YAIJ@Z; GetEscapementID(long)
0x18000f259  mov     [rbx+0Ch], eax
0x18000f25c  xor     eax, eax
0x18000f25e  mov     dword ptr [rbx+2Ch], 0
0x18000f265  jmp     loc_18000F0BE
```
