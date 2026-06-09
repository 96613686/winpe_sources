# CreateFontIndirectA

- ea: `0x18002ef90`
- end: `0x18002f113`
- name: `CreateFontIndirectA`
- size: `387`
- prototype: `HFONT __stdcall(const LOGFONTA *lplf)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800177f0`
- `0x180024c40`
- `0x1800270d8`
- `0x18002eee0`
- `0x1800479b0`
- `0x1800741cc`
- `0x18009d9e4`

## callees

- `0x18002ef90`
- `0x18002fb70`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f0f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f0f7`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002f08a`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18002f08a`
- `USER32!GetAppCompatFlags2` at `0x18002f0a9`
- `USER32!GetAppCompatFlags2` at `0x18002f0a9`

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
0x18002ef90  push    rbp
0x18002ef92  push    rbx
0x18002ef93  push    rsi
0x18002ef94  push    rdi
0x18002ef95  lea     rbp, [rsp-0F8h]
0x18002ef9d  sub     rsp, 1F8h
0x18002efa4  mov     rax, cs:__security_cookie
0x18002efab  xor     rax, rsp
0x18002efae  mov     [rbp+110h+var_30], rax
0x18002efb5  mov     rbx, rcx
0x18002efb8  xor     edx, edx; Val
0x18002efba  lea     rcx, [rsp+210h+var_1E0]; void *
0x18002efbf  mov     r8d, 1A4h; Size
0x18002efc5  call    memset_0
0x18002efca  test    rbx, rbx
0x18002efcd  jz      loc_18002F0E1
0x18002efd3  mov     eax, [rbx]
0x18002efd5  lea     rdi, [rbx+1Ch]
0x18002efd9  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfHeight], eax
0x18002efdd  mov     eax, [rbx+4]
0x18002efe0  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfWidth], eax
0x18002efe4  mov     eax, [rbx+8]
0x18002efe7  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfEscapement], eax
0x18002efeb  mov     eax, [rbx+0Ch]
0x18002efee  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfOrientation], eax
0x18002eff2  mov     eax, [rbx+10h]
0x18002eff5  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfWeight], eax
0x18002eff9  mov     al, [rbx+14h]
0x18002effc  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfItalic], al
0x18002f000  mov     al, [rbx+15h]
0x18002f003  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfUnderline], al
0x18002f007  mov     al, [rbx+16h]
0x18002f00a  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfStrikeOut], al
0x18002f00e  mov     al, [rbx+17h]
0x18002f011  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet], al
0x18002f015  mov     al, [rbx+18h]
0x18002f018  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfOutPrecision], al
0x18002f01c  mov     al, [rbx+19h]
0x18002f01f  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfClipPrecision], al
0x18002f023  mov     al, [rbx+1Ah]
0x18002f026  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfQuality], al
0x18002f02a  mov     al, [rbx+1Bh]
0x18002f02d  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfPitchAndFamily], al
0x18002f031  xor     eax, eax
0x18002f033  xor     ebx, ebx
0x18002f035  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfFullName], ax
0x18002f039  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfStyle], ax
0x18002f03d  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfScript], ax
0x18002f041  mov     rax, rdi
0x18002f044  mov     qword ptr [rbp+110h+var_1E0.elfDesignVector.dvReserved], 8007664h
0x18002f04f  lea     esi, [rbx+1]
0x18002f052  cmp     ebx, 20h ; ' '
0x18002f055  jnb     short loc_18002F063
0x18002f057  cmp     byte ptr [rax], 0
0x18002f05a  jz      short loc_18002F068
0x18002f05c  add     rax, rsi
0x18002f05f  add     ebx, esi
0x18002f061  jmp     short loc_18002F052
0x18002f063  mov     ebx, 20h ; ' '
0x18002f068  xor     edx, edx; Val
0x18002f06a  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]; void *
0x18002f06f  lea     r8d, [rdx+40h]; Size
0x18002f073  call    memset_0
0x18002f078  lea     edx, [rbx+rbx]; MaxBytesInUnicodeString
0x18002f07b  mov     [rsp+210h+BytesInMultiByteString], ebx; BytesInMultiByteString
0x18002f07f  mov     r9, rdi; MultiByteString
0x18002f082  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]; UnicodeString
0x18002f087  xor     r8d, r8d; BytesInUnicodeString
0x18002f08a  call    cs:__imp_RtlMultiByteToUnicodeN
0x18002f091  nop     dword ptr [rax+rax+00h]
0x18002f096  xor     eax, eax
0x18002f098  cmp     ebx, 20h ; ' '
0x18002f09b  jz      short loc_18002F0E5
0x18002f09d  mov     ecx, ebx
0x18002f09f  mov     [rsp+rcx*2+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName], ax
0x18002f0a4  mov     ecx, 400h
0x18002f0a9  call    cs:__imp_GetAppCompatFlags2
0x18002f0b0  nop     dword ptr [rax+rax+00h]
0x18002f0b5  bt      eax, 0Eh
0x18002f0b9  jb      short loc_18002F0EB
0x18002f0bb  lea     rcx, [rsp+210h+var_1E0]; ENUMLOGFONTEXDVW *
0x18002f0c0  call    CreateFontIndirectExW
0x18002f0c5  mov     rcx, [rbp+110h+var_30]
0x18002f0cc  xor     rcx, rsp; StackCookie
0x18002f0cf  call    __security_check_cookie
0x18002f0d4  add     rsp, 1F8h
0x18002f0db  pop     rdi
0x18002f0dc  pop     rsi
0x18002f0dd  pop     rbx
0x18002f0de  pop     rbp
0x18002f0df  retn
0x18002f0e1  xor     eax, eax
0x18002f0e3  jmp     short loc_18002F0C5
0x18002f0e5  mov     [rbp+110h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName+3Eh], ax
0x18002f0e9  jmp     short loc_18002F0A4
0x18002f0eb  lea     rdx, aOcrA; "OCR-A"
0x18002f0f2  lea     rcx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfFaceName]
0x18002f0f7  call    cs:__imp__o__wcsicmp
0x18002f0fe  nop     dword ptr [rax+rax+00h]
0x18002f103  movzx   ecx, [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet]
0x18002f108  test    eax, eax
0x18002f10a  cmovz   ecx, esi
0x18002f10d  mov     [rsp+210h+var_1E0.elfEnumLogfontEx.elfLogFont.lfCharSet], cl
0x18002f111  jmp     short loc_18002F0BB
```
