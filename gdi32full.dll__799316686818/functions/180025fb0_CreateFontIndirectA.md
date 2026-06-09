# CreateFontIndirectA

- ea: `0x180025fb0`
- end: `0x180026120`
- name: `CreateFontIndirectA`
- size: `368`
- prototype: `HFONT __stdcall(const LOGFONTA *lplf)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ee34`
- `0x180011fc0`
- `0x180025f00`
- `0x18003bd30`
- `0x1800532d4`
- `0x18006f4e0`
- `0x18009ac00`

## callees

- `0x180025fb0`
- `0x180026af0`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002610a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002610a`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800260aa`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800260aa`
- `USER32!GetAppCompatFlags2` at `0x1800260c3`
- `USER32!GetAppCompatFlags2` at `0x1800260c3`

## pseudocode

```c
HFONT __stdcall CreateFontIndirectA(const LOGFONTA *lplf)
{
  CHAR *lfFaceName; // rdi
  ULONG BytesInMultiByteString; // ebx
  CHAR *v4; // rax
  int v6; // eax
  BYTE lfCharSet; // cl
  ENUMLOGFONTEXDVW v8; // [rsp+30h] [rbp-D0h] BYREF

  memset_0(&v8, 0, sizeof(v8));
  if ( !lplf )
    return 0;
  lfFaceName = lplf->lfFaceName;
  v8.elfEnumLogfontEx.elfLogFont.lfHeight = lplf->lfHeight;
  v8.elfEnumLogfontEx.elfLogFont.lfWidth = lplf->lfWidth;
  v8.elfEnumLogfontEx.elfLogFont.lfEscapement = lplf->lfEscapement;
  v8.elfEnumLogfontEx.elfLogFont.lfOrientation = lplf->lfOrientation;
  v8.elfEnumLogfontEx.elfLogFont.lfWeight = lplf->lfWeight;
  v8.elfEnumLogfontEx.elfLogFont.lfItalic = lplf->lfItalic;
  v8.elfEnumLogfontEx.elfLogFont.lfUnderline = lplf->lfUnderline;
  v8.elfEnumLogfontEx.elfLogFont.lfStrikeOut = lplf->lfStrikeOut;
  v8.elfEnumLogfontEx.elfLogFont.lfCharSet = lplf->lfCharSet;
  v8.elfEnumLogfontEx.elfLogFont.lfOutPrecision = lplf->lfOutPrecision;
  v8.elfEnumLogfontEx.elfLogFont.lfClipPrecision = lplf->lfClipPrecision;
  v8.elfEnumLogfontEx.elfLogFont.lfQuality = lplf->lfQuality;
  v8.elfEnumLogfontEx.elfLogFont.lfPitchAndFamily = lplf->lfPitchAndFamily;
  BytesInMultiByteString = 0;
  v8.elfEnumLogfontEx.elfFullName[0] = 0;
  v8.elfEnumLogfontEx.elfStyle[0] = 0;
  v8.elfEnumLogfontEx.elfScript[0] = 0;
  v4 = lfFaceName;
  *(_QWORD *)&v8.elfDesignVector.dvReserved = 134248036;
  while ( BytesInMultiByteString < 0x20 )
  {
    if ( !*v4 )
      goto LABEL_7;
    ++v4;
    ++BytesInMultiByteString;
  }
  BytesInMultiByteString = 32;
LABEL_7:
  memset_0(v8.elfEnumLogfontEx.elfLogFont.lfFaceName, 0, sizeof(v8.elfEnumLogfontEx.elfLogFont.lfFaceName));
  RtlMultiByteToUnicodeN(
    v8.elfEnumLogfontEx.elfLogFont.lfFaceName,
    2 * BytesInMultiByteString,
    0,
    lfFaceName,
    BytesInMultiByteString);
  if ( BytesInMultiByteString == 32 )
    v8.elfEnumLogfontEx.elfLogFont.lfFaceName[31] = 0;
  else
    v8.elfEnumLogfontEx.elfLogFont.lfFaceName[BytesInMultiByteString] = 0;
  if ( (GetAppCompatFlags2(1024) & 0x4000) != 0 )
  {
    v6 = _o__wcsicmp(v8.elfEnumLogfontEx.elfLogFont.lfFaceName, L"OCR-A");
    lfCharSet = v8.elfEnumLogfontEx.elfLogFont.lfCharSet;
    if ( !v6 )
      lfCharSet = 1;
    v8.elfEnumLogfontEx.elfLogFont.lfCharSet = lfCharSet;
  }
  return CreateFontIndirectExW(&v8);
}

```

## disassembly

```asm
0x180025fb0  push    rbp
0x180025fb2  push    rbx
0x180025fb3  push    rsi
0x180025fb4  push    rdi
0x180025fb5  lea     rbp, [rsp-0F8h]
0x180025fbd  sub     rsp, 1F8h
0x180025fc4  mov     rax, cs:__security_cookie
0x180025fcb  xor     rax, rsp
0x180025fce  mov     [rbp+110h+var_30], rax
0x180025fd5  mov     rbx, rcx
0x180025fd8  xor     edx, edx; Val
0x180025fda  lea     rcx, [rsp+210h+var_1E0]; void *
0x180025fdf  mov     r8d, 1A4h; Size
0x180025fe5  call    memset_0
0x180025fea  test    rbx, rbx
0x180025fed  jz      loc_1800260F4
0x180025ff3  mov     eax, [rbx]
0x180025ff5  lea     rdi, [rbx+1Ch]
0x180025ff9  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfHeight], eax
0x180025ffd  mov     eax, [rbx+4]
0x180026000  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfWidth], eax
0x180026004  mov     eax, [rbx+8]
0x180026007  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfEscapement], eax
0x18002600b  mov     eax, [rbx+0Ch]
0x18002600e  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfOrientation], eax
0x180026012  mov     eax, [rbx+10h]
0x180026015  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfWeight], eax
0x180026019  mov     al, [rbx+14h]
0x18002601c  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfItalic], al
0x180026020  mov     al, [rbx+15h]
0x180026023  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfUnderline], al
0x180026027  mov     al, [rbx+16h]
0x18002602a  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfStrikeOut], al
0x18002602e  mov     al, [rbx+17h]
0x180026031  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet], al
0x180026035  mov     al, [rbx+18h]
0x180026038  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfOutPrecision], al
0x18002603c  mov     al, [rbx+19h]
0x18002603f  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfClipPrecision], al
0x180026043  mov     al, [rbx+1Ah]
0x180026046  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfQuality], al
0x18002604a  mov     al, [rbx+1Bh]
0x18002604d  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfPitchAndFamily], al
0x180026051  xor     eax, eax
0x180026053  xor     ebx, ebx
0x180026055  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfFullName], ax
0x180026059  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfStyle], ax
0x18002605d  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfScript], ax
0x180026061  mov     rax, rdi
0x180026064  mov     qword ptr [rbp+110h+var_1E0.elfDesignVector.dvReserved], 8007664h
0x18002606f  lea     esi, [rbx+1]
0x180026072  cmp     ebx, 20h ; ' '
0x180026075  jnb     short loc_180026083
0x180026077  cmp     byte ptr [rax], 0
0x18002607a  jz      short loc_180026088
0x18002607c  add     rax, rsi
0x18002607f  add     ebx, esi
0x180026081  jmp     short loc_180026072
0x180026083  mov     ebx, 20h ; ' '
0x180026088  xor     edx, edx; Val
0x18002608a  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]; void *
0x18002608f  lea     r8d, [rdx+40h]; Size
0x180026093  call    memset_0
0x180026098  lea     edx, [rbx+rbx]; MaxBytesInUnicodeString
0x18002609b  mov     [rsp+210h+BytesInMultiByteString], ebx; BytesInMultiByteString
0x18002609f  mov     r9, rdi; MultiByteString
0x1800260a2  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]; UnicodeString
0x1800260a7  xor     r8d, r8d; BytesInUnicodeString
0x1800260aa  call    cs:__imp_RtlMultiByteToUnicodeN
0x1800260b0  xor     eax, eax
0x1800260b2  cmp     ebx, 20h ; ' '
0x1800260b5  jz      short loc_1800260F8
0x1800260b7  mov     ecx, ebx
0x1800260b9  mov     [rsp+rcx*2+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName], ax
0x1800260be  mov     ecx, 400h
0x1800260c3  call    cs:__imp_GetAppCompatFlags2
0x1800260c9  bt      eax, 0Eh
0x1800260cd  jb      short loc_1800260FE
0x1800260cf  lea     rcx, [rsp+210h+var_1E0]; ENUMLOGFONTEXDVW *
0x1800260d4  call    CreateFontIndirectExW
0x1800260d9  mov     rcx, [rbp+110h+var_30]
0x1800260e0  xor     rcx, rsp; StackCookie
0x1800260e3  call    __security_check_cookie
0x1800260e8  add     rsp, 1F8h
0x1800260ef  pop     rdi
0x1800260f0  pop     rsi
0x1800260f1  pop     rbx
0x1800260f2  pop     rbp
0x1800260f3  retn
0x1800260f4  xor     eax, eax
0x1800260f6  jmp     short loc_1800260D9
0x1800260f8  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName+3Eh], ax
0x1800260fc  jmp     short loc_1800260BE
0x1800260fe  lea     rdx, aOcrA; "OCR-A"
0x180026105  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]
0x18002610a  call    cs:__imp__o__wcsicmp
0x180026110  movzx   ecx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet]
0x180026115  test    eax, eax
0x180026117  cmovz   ecx, esi
0x18002611a  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet], cl
0x18002611e  jmp     short loc_1800260CF
```
