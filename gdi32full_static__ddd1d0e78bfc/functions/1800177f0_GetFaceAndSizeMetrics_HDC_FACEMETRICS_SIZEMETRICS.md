# GetFaceAndSizeMetrics(HDC__ *,FACEMETRICS *,SIZEMETRICS *)

- ea: `0x1800177f0`
- end: `0x180017c5a`
- name: `?GetFaceAndSizeMetrics@@YAJPEAUHDC__@@PEAUFACEMETRICS@@PEAUSIZEMETRICS@@@Z`
- size: `1130`
- prototype: `__int64 __fastcall(HDC hdc, struct FACEMETRICS *, struct SIZEMETRICS *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x1800235f0`

## callees

- `0x180004c00`
- `0x180006978`
- `0x180006a28`
- `0x18000d040`
- `0x18000d410`
- `0x180017650`
- `0x180017690`
- `0x1800176d0`
- `0x180017710`
- `0x1800177f0`
- `0x180018940`
- `0x180018df0`
- `0x180024bb0`
- `0x18002ef90`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001793c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001793c`
- `GDI32!GetTextMetricsA` at `0x180017afb`
- `GDI32!GetTextMetricsA` at `0x180017bc0`
- `GDI32!GetTextMetricsA` at `0x180017afb`
- `GDI32!GetTextMetricsA` at `0x180017bc0`
- `GDI32!SelectObject` at `0x180017ae5`
- `GDI32!SelectObject` at `0x180017b20`
- `GDI32!SelectObject` at `0x180017b63`
- `GDI32!SelectObject` at `0x180017ae5`
- `GDI32!SelectObject` at `0x180017b20`
- `GDI32!SelectObject` at `0x180017b63`
- `GDI32!DeleteObject` at `0x180017b2f`
- `GDI32!DeleteObject` at `0x180017b7b`
- `GDI32!DeleteObject` at `0x180017b2f`
- `GDI32!DeleteObject` at `0x180017b7b`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x180017906`
- `win32u!NtGdiGetOutlineTextMetricsInternalW` at `0x180017906`
- `win32u!NtGdiGetTextFaceW` at `0x180017ab4`
- `win32u!NtGdiGetTextFaceW` at `0x180017ab4`

## pseudocode

```c
__int64 __fastcall GetFaceAndSizeMetrics(HDC hdc, struct FACEMETRICS *a2, struct tagSIZE *a3)
{
  LONG v6; // ecx
  bool v7; // zf
  void *DCObject; // rax
  int v9; // eax
  signed __int64 v10; // r15
  struct _OUTLINETEXTMETRICW *v11; // rax
  struct _OUTLINETEXTMETRICW *v12; // rdi
  PSTR otmpFaceName; // rax
  int v14; // edx
  wchar_t *v15; // r9
  PSTR otmpFamilyName; // rax
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
    v11 = (struct _OUTLINETEXTMETRICW *)HeapAlloc(ghHeap, 0, v10);
    v12 = v11;
    if ( !v11 )
      return (unsigned int)-2147024882;
    memset_0(v11, 0, v10);
    if ( GetOutlineTextMetricsW(hdc, v10, v12) )
    {
      otmpFaceName = v12->otmpFaceName;
      if ( !otmpFaceName || (__int64)otmpFaceName >= v10 )
      {
        v22 = -2147024882;
        goto LABEL_26;
      }
      v14 = 64;
      *(_DWORD *)a2 = v12->otmTextMetrics.tmWeight;
      *((_BYTE *)a2 + 138) = v12->otmTextMetrics.tmItalic;
      *((_BYTE *)a2 + 139) = v12->otmTextMetrics.tmUnderlined;
      *((_BYTE *)a2 + 140) = v12->otmTextMetrics.tmStruckOut;
      *((_BYTE *)a2 + 141) = v12->otmTextMetrics.tmPitchAndFamily;
      *((_BYTE *)a2 + 142) = v12->otmTextMetrics.tmCharSet;
      *((_WORD *)a2 + 67) = v12->otmTextMetrics.tmFirstChar;
      *((_WORD *)a2 + 68) = v12->otmTextMetrics.tmDefaultChar;
      v15 = (wchar_t *)((char *)v12 + (unsigned __int64)v12->otmpFaceName);
      if ( *v15 != 64
        && (otmpFamilyName = v12->otmpFamilyName) != 0
        && (__int64)otmpFamilyName < v10
        && *(_WORD *)((char *)&v12->otmSize + (_QWORD)otmpFamilyName) == 64 )
      {
        *((_WORD *)a2 + 2) = 64;
        v17 = 6;
        v15 = (wchar_t *)((char *)v12 + (unsigned __int64)v12->otmpFaceName);
      }
      else
      {
        v14 = 65;
        v17 = 4;
      }
      UnicodeCopyString((wchar_t *)((char *)a2 + v17), v15, v14);
      lfEscapement = pv.lfEscapement;
      *((_WORD *)a2 + 66) = 0;
      a3->cx = v12->otmTextMetrics.tmHeight;
      a3[4].cx = v12->otmTextMetrics.tmAscent;
      a3[4].cy = v12->otmTextMetrics.tmOverhang;
      a3[5].cx = v12->otmTextMetrics.tmInternalLeading;
      a3->cy = v12->otmTextMetrics.tmAveCharWidth;
      EscapementID = GetEscapementID(lfEscapement);
      v7 = a3[1].cx == 0;
      a3[1].cy = EscapementID;
      if ( v7 )
        a3[1].cx = v20;
      a3[5].cy = v12->otmEMSquare;
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
  if ( !(unsigned int)NtGdiGetTextFaceW(hdc, 65, (char *)a2 + 4) )
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
0x1800177f0  push    rbp
0x1800177f2  push    rbx
0x1800177f3  push    rsi
0x1800177f4  push    rdi
0x1800177f5  push    r12
0x1800177f7  push    r14
0x1800177f9  push    r15
0x1800177fb  lea     rbp, [rsp-27h]
0x180017800  sub     rsp, 0B0h
0x180017807  mov     rax, cs:__security_cookie
0x18001780e  xor     rax, rsp
0x180017811  mov     [rbp+57h+var_38], rax
0x180017815  xorps   xmm0, xmm0
0x180017818  xor     eax, eax
0x18001781a  mov     qword ptr [rbp+57h+tm.tmItalic], rax
0x18001781e  mov     rbx, r8
0x180017821  mov     r14, rdx
0x180017824  mov     rsi, rcx
0x180017827  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x18001782b  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x18001782f  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x180017833  test    rcx, rcx
0x180017836  jz      loc_180017A9F
0x18001783c  test    rdx, rdx
0x18001783f  jz      loc_180017A9F
0x180017845  test    rbx, rbx
0x180017848  jz      loc_180017A9F
0x18001784e  lea     rdx, [r8+10h]; lpsize
0x180017852  call    GetWindowExtEx
0x180017857  lea     rdx, [rbx+18h]; lpsize
0x18001785b  mov     rcx, rsi; hdc
0x18001785e  call    GetViewportExtEx
0x180017863  xor     eax, eax
0x180017865  lea     rdx, [rbp+57h+var_C0]
0x180017869  mov     rcx, rsi
0x18001786c  mov     [rbp+57h+var_C0], rax
0x180017870  mov     [rbp+57h+var_B8], eax
0x180017873  call    GdiRealizationInfo
0x180017878  test    eax, eax
0x18001787a  jz      loc_180017AC8
0x180017880  movzx   edx, byte ptr [rbp+57h+var_C0+1]
0x180017884  xor     eax, eax
0x180017886  mov     ecx, dword ptr [rbp+57h+var_C0+4]
0x180017889  test    edx, edx
0x18001788b  mov     [rbx+30h], edx
0x18001788e  cmovnz  ecx, eax
0x180017891  mov     [rbx+34h], ecx
0x180017894  mov     rcx, rsi
0x180017897  call    GetDCDpiScaleValue
0x18001789c  xorps   xmm0, xmm0
0x18001789f  mov     [rbx+38h], eax
0x1800178a2  movups  [rbp+57h+var_58], xmm0
0x1800178a6  mov     edx, 0A0000h
0x1800178ab  mov     rcx, rsi
0x1800178ae  movups  [rbp+57h+var_58+0Ch], xmm0
0x1800178b2  movups  [rbp+57h+pv], xmm0
0x1800178b6  movups  [rbp+57h+var_68], xmm0
0x1800178ba  call    GetDCObject
0x1800178bf  test    rax, rax
0x1800178c2  jz      loc_180017AC8
0x1800178c8  lea     r8, [rbp+57h+pv]; pv
0x1800178cc  mov     edx, 3Ch ; '<'; c
0x1800178d1  mov     rcx, rax; h
0x1800178d4  call    GetObjectA
0x1800178d9  test    eax, eax
0x1800178db  jz      loc_180017AC8
0x1800178e1  cmp     dword ptr [rbp+57h+pv+4], 0
0x1800178e5  mov     dword ptr [rbx+8], 0
0x1800178ec  jnz     loc_180017ACF
0x1800178f2  lea     r9, [rbp+57h+var_C0]
0x1800178f6  mov     [rbp+57h+var_C0], 0
0x1800178fe  xor     r8d, r8d
0x180017901  xor     edx, edx
0x180017903  mov     rcx, rsi
0x180017906  call    cs:__imp_NtGdiGetOutlineTextMetricsInternalW
0x18001790d  nop     dword ptr [rax+rax+00h]
0x180017912  movsxd  r15, eax
0x180017915  test    eax, eax
0x180017917  jz      loc_180017AA6
0x18001791d  js      loc_180017B8C
0x180017923  call    ?CheckInitUspMemory@@YAHXZ; CheckInitUspMemory(void)
0x180017928  test    eax, eax
0x18001792a  jz      loc_180017B40
0x180017930  mov     rcx, cs:?ghHeap@@3PEAXEA; hHeap
0x180017937  mov     r8, r15; dwBytes
0x18001793a  xor     edx, edx; dwFlags
0x18001793c  call    cs:__imp_HeapAlloc
0x180017943  nop     dword ptr [rax+rax+00h]
0x180017948  mov     rdi, rax
0x18001794b  test    rax, rax
0x18001794e  jz      loc_180017B40
0x180017954  mov     r8, r15; Size
0x180017957  xor     edx, edx; Val
0x180017959  mov     rcx, rax; void *
0x18001795c  call    memset_0
0x180017961  mov     r8, rdi; potm
0x180017964  mov     edx, r15d; cjCopy
0x180017967  mov     rcx, rsi; hdc
0x18001796a  call    GetOutlineTextMetricsW
0x18001796f  test    eax, eax
0x180017971  jz      loc_180017B4A
0x180017977  mov     rax, [rdi+0D0h]
0x18001797e  test    rax, rax
0x180017981  jz      loc_180017A98
0x180017987  cmp     rax, r15
0x18001798a  jge     loc_180017A98
0x180017990  mov     eax, [rdi+20h]
0x180017993  mov     edx, 40h ; '@'
0x180017998  mov     [r14], eax
0x18001799b  mov     al, [rdi+38h]
0x18001799e  mov     [r14+8Ah], al
0x1800179a5  mov     al, [rdi+39h]
0x1800179a8  mov     [r14+8Bh], al
0x1800179af  mov     al, [rdi+3Ah]
0x1800179b2  mov     [r14+8Ch], al
0x1800179b9  mov     al, [rdi+3Bh]
0x1800179bc  mov     [r14+8Dh], al
0x1800179c3  mov     al, [rdi+3Ch]
0x1800179c6  mov     [r14+8Eh], al
0x1800179cd  movzx   eax, word ptr [rdi+30h]
0x1800179d1  mov     [r14+86h], ax
0x1800179d9  movzx   eax, word ptr [rdi+34h]
0x1800179dd  mov     [r14+88h], ax
0x1800179e5  mov     r9, [rdi+0D0h]
0x1800179ec  add     r9, rdi
0x1800179ef  cmp     [r9], dx
0x1800179f3  jz      short loc_180017A10
0x1800179f5  mov     rax, [rdi+0C8h]
0x1800179fc  test    rax, rax
0x1800179ff  jz      short loc_180017A10
0x180017a01  cmp     rax, r15
0x180017a04  jge     short loc_180017A10
0x180017a06  cmp     [rax+rdi], dx
0x180017a0a  jz      loc_180017B96
0x180017a10  mov     edx, 41h ; 'A'
0x180017a15  lea     eax, [rdx-3Dh]
0x180017a18  mov     r8d, edx; int
0x180017a1b  lea     rcx, [rax+r14]; wchar_t *
0x180017a1f  mov     rdx, r9; wchar_t *
0x180017a22  call    ?UnicodeCopyString@@YAHPEA_W0H@Z; UnicodeCopyString(wchar_t *,wchar_t *,int)
0x180017a27  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x180017a2a  xor     eax, eax
0x180017a2c  mov     [r14+84h], ax
0x180017a34  mov     eax, [rdi+4]
0x180017a37  mov     [rbx], eax
0x180017a39  mov     eax, [rdi+8]
0x180017a3c  mov     [rbx+20h], eax
0x180017a3f  mov     eax, [rdi+24h]
0x180017a42  mov     [rbx+24h], eax
0x180017a45  mov     eax, [rdi+10h]
0x180017a48  mov     [rbx+28h], eax
0x180017a4b  mov     r9d, [rdi+18h]
0x180017a4f  mov     [rbx+4], r9d
0x180017a53  call    ?GetEscapementID@@YAIJ@Z; GetEscapementID(long)
0x180017a58  cmp     dword ptr [rbx+8], 0
0x180017a5c  mov     [rbx+0Ch], eax
0x180017a5f  jnz     short loc_180017A65
0x180017a61  mov     [rbx+8], r9d
0x180017a65  mov     eax, [rdi+60h]
0x180017a68  mov     [rbx+2Ch], eax
0x180017a6b  xor     eax, eax
0x180017a6d  mov     ebx, eax
0x180017a6f  mov     rcx, rdi; lpMem
0x180017a72  call    UspFreeMem
0x180017a77  mov     eax, ebx
0x180017a79  mov     rcx, [rbp+57h+var_38]
0x180017a7d  xor     rcx, rsp; StackCookie
0x180017a80  call    __security_check_cookie
0x180017a85  add     rsp, 0B0h
0x180017a8c  pop     r15
0x180017a8e  pop     r14
0x180017a90  pop     r12
0x180017a92  pop     rdi
0x180017a93  pop     rsi
0x180017a94  pop     rbx
0x180017a95  pop     rbp
0x180017a96  retn
0x180017a98  mov     ebx, 8007000Eh
0x180017a9d  jmp     short loc_180017A6F
0x180017a9f  mov     eax, 80070057h
0x180017aa4  jmp     short loc_180017A79
0x180017aa6  xor     r9d, r9d
0x180017aa9  lea     r8, [r14+4]
0x180017aad  mov     rcx, rsi
0x180017ab0  lea     edx, [r9+41h]
0x180017ab4  call    cs:__imp_NtGdiGetTextFaceW
0x180017abb  nop     dword ptr [rax+rax+00h]
0x180017ac0  test    eax, eax
0x180017ac2  jnz     loc_180017BAF
0x180017ac8  call    HRESULT_FROM_LAST_WIN32_ERROR
0x180017acd  jmp     short loc_180017A79
0x180017acf  lea     rcx, [rbp+57h+pv]; lplf
0x180017ad3  mov     dword ptr [rbp+57h+pv+4], 0
0x180017ada  call    CreateFontIndirectA
0x180017adf  mov     rdx, rax; h
0x180017ae2  mov     rcx, rsi; hdc
0x180017ae5  call    cs:__imp_SelectObject
0x180017aec  nop     dword ptr [rax+rax+00h]
0x180017af1  lea     rdx, [rbp+57h+tm]; lptm
0x180017af5  mov     rcx, rsi; hdc
0x180017af8  mov     rdi, rax
0x180017afb  call    cs:__imp_GetTextMetricsA
0x180017b02  nop     dword ptr [rax+rax+00h]
0x180017b07  test    eax, eax
0x180017b09  jz      short loc_180017B54
0x180017b0b  mov     ecx, [rbp+57h+tm.tmAveCharWidth]
0x180017b0e  mov     [rbx+8], ecx
0x180017b11  test    rdi, rdi
0x180017b14  jz      loc_1800178F2
0x180017b1a  mov     rdx, rdi; h
0x180017b1d  mov     rcx, rsi; hdc
0x180017b20  call    cs:__imp_SelectObject
0x180017b27  nop     dword ptr [rax+rax+00h]
0x180017b2c  mov     rcx, rax; ho
0x180017b2f  call    cs:__imp_DeleteObject
0x180017b36  nop     dword ptr [rax+rax+00h]
0x180017b3b  jmp     loc_1800178F2
0x180017b40  mov     ebx, 8007000Eh
0x180017b45  jmp     loc_180017A77
0x180017b4a  call    HRESULT_FROM_LAST_WIN32_ERROR
0x180017b4f  jmp     loc_180017A6D
0x180017b54  test    rdi, rdi
0x180017b57  jz      loc_180017AC8
0x180017b5d  mov     rdx, rdi; h
0x180017b60  mov     rcx, rsi; hdc
0x180017b63  call    cs:__imp_SelectObject
0x180017b6a  nop     dword ptr [rax+rax+00h]
0x180017b6f  test    rax, rax
0x180017b72  jz      loc_180017AC8
0x180017b78  mov     rcx, rax; ho
0x180017b7b  call    cs:__imp_DeleteObject
0x180017b82  nop     dword ptr [rax+rax+00h]
0x180017b87  jmp     loc_180017AC8
0x180017b8c  mov     ebx, 80070057h
0x180017b91  jmp     loc_180017A77
0x180017b96  mov     [r14+4], dx
0x180017b9b  mov     eax, 6
0x180017ba0  mov     r9, [rdi+0D0h]
0x180017ba7  add     r9, rdi
0x180017baa  jmp     loc_180017A18
0x180017baf  xor     eax, eax
0x180017bb1  lea     rdx, [rbp+57h+tm]; lptm
0x180017bb5  mov     rcx, rsi; hdc
0x180017bb8  mov     [r14+84h], ax
0x180017bc0  call    cs:__imp_GetTextMetricsA
0x180017bc7  nop     dword ptr [rax+rax+00h]
0x180017bcc  test    eax, eax
0x180017bce  jz      loc_180017AC8
0x180017bd4  mov     eax, [rbp+57h+tm.tmWeight]
0x180017bd7  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x180017bda  mov     [r14], eax
0x180017bdd  mov     al, [rbp+57h+tm.tmItalic]
0x180017be0  mov     [r14+8Ah], al
0x180017be7  mov     al, [rbp+57h+tm.tmUnderlined]
0x180017bea  mov     [r14+8Bh], al
0x180017bf1  mov     al, [rbp+57h+tm.tmStruckOut]
0x180017bf4  mov     [r14+8Ch], al
0x180017bfb  mov     al, [rbp+57h+tm.tmPitchAndFamily]
0x180017bfe  mov     [r14+8Dh], al
0x180017c05  mov     al, [rbp+57h+tm.tmCharSet]
0x180017c08  mov     [r14+8Eh], al
0x180017c0f  movzx   eax, [rbp+57h+tm.tmFirstChar]
0x180017c13  mov     [r14+86h], ax
0x180017c1b  movzx   eax, [rbp+57h+tm.tmDefaultChar]
0x180017c1f  mov     [r14+88h], ax
0x180017c27  mov     eax, [rbp+57h+tm.tmHeight]
0x180017c2a  mov     [rbx], eax
0x180017c2c  mov     eax, [rbp+57h+tm.tmAscent]
0x180017c2f  mov     [rbx+20h], eax
0x180017c32  mov     eax, [rbp+57h+tm.tmOverhang]
0x180017c35  mov     [rbx+24h], eax
0x180017c38  mov     eax, [rbp+57h+tm.tmInternalLeading]
0x180017c3b  mov     [rbx+28h], eax
0x180017c3e  mov     eax, [rbp+57h+tm.tmAveCharWidth]
0x180017c41  mov     [rbx+4], eax
0x180017c44  call    ?GetEscapementID@@YAIJ@Z; GetEscapementID(long)
0x180017c49  mov     [rbx+0Ch], eax
0x180017c4c  xor     eax, eax
0x180017c4e  mov     dword ptr [rbx+2Ch], 0
0x180017c55  jmp     loc_180017A79
```
