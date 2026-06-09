# SetClipboardOwnerWindowProperty(HWND__ *,ushort const *,ulong)

- ea: `0x180011958`
- end: `0x180011a35`
- name: `?SetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEBGK@Z`
- size: `221`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, const wchar_t *pszPackageFulllName, unsigned int pid)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f900`

## callees

- `0x180011958`
- `0x180019454`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0b`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18001199b`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18001199b`
- `USER32!RemovePropW` at `0x180011979`
- `USER32!RemovePropW` at `0x180011989`
- `USER32!RemovePropW` at `0x180011a05`
- `USER32!RemovePropW` at `0x180011979`
- `USER32!RemovePropW` at `0x180011989`
- `USER32!RemovePropW` at `0x180011a05`
- `USER32!SetPropW` at `0x1800119b9`
- `USER32!SetPropW` at `0x1800119f1`
- `USER32!SetPropW` at `0x1800119b9`
- `USER32!SetPropW` at `0x1800119f1`

## pseudocode

```c
__int64 __fastcall SetClipboardOwnerWindowProperty(HWND hClipWnd, const wchar_t *pszPackageFulllName, unsigned int pid)
{
  void *v4; // rbp
  HRESULT v5; // ebx
  ATOM v7; // ax
  signed int LastError; // eax
  signed int v9; // eax

  v4 = (void *)pid;
  v5 = 0;
  RemovePropW(hClipWnd, L"OleClipProcessOwner");
  RemovePropW(hClipWnd, L"OLEClipPackgeOwner");
  if ( pszPackageFulllName )
  {
    v7 = GlobalAddAtomW(pszPackageFulllName);
    if ( v7 )
    {
      if ( SetPropW(hClipWnd, L"OLEClipPackgeOwner", (HANDLE)v7) )
        goto LABEL_14;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    OleInternalOriginateError(v5, 0x12Eu);
    if ( v5 >= 0 )
    {
LABEL_14:
      if ( !SetPropW(hClipWnd, L"OleClipProcessOwner", v4) )
      {
        RemovePropW(hClipWnd, L"OLEClipPackgeOwner");
        v9 = GetLastError();
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        OleInternalOriginateError(v5, 0x12Eu);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011958  push    rbx
0x18001195a  push    rbp
0x18001195b  push    rsi
0x18001195c  push    rdi
0x18001195d  push    r14
0x18001195f  sub     rsp, 20h
0x180011963  mov     rsi, pszPackageFulllName
0x180011966  mov     ebp, pid
0x180011969  xor     r14d, r14d
0x18001196c  lea     pszPackageFulllName, aOleclipprocess; "OleClipProcessOwner"
0x180011973  mov     ebx, r14d
0x180011976  mov     rdi, hClipWnd
0x180011979  call    cs:__imp_RemovePropW
0x18001197f  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x180011986  mov     hClipWnd, rdi; hWnd
0x180011989  call    cs:__imp_RemovePropW
0x18001198f  test    rsi, rsi
0x180011992  jz      loc_180011A28
0x180011998  mov     hClipWnd, rsi; lpString
0x18001199b  call    cs:__imp_GlobalAddAtomW
0x1800119a1  mov     esi, 80070000h
0x1800119a6  test    ax, ax
0x1800119a9  jz      short loc_1800119C3
0x1800119ab  movzx   pid, ax; hData
0x1800119af  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x1800119b6  mov     hClipWnd, rdi; hWnd
0x1800119b9  call    cs:__imp_SetPropW
0x1800119bf  test    eax, eax
0x1800119c1  jnz     short loc_1800119E4
0x1800119c3  call    cs:__imp_GetLastError
0x1800119c9  mov     ebx, eax
0x1800119cb  test    eax, eax
0x1800119cd  jle     short loc_1800119D4
0x1800119cf  movzx   ebx, ax
0x1800119d2  or      ebx, esi
0x1800119d4  mov     edx, 12Eh; messageID
0x1800119d9  mov     ecx, ebx; hr
0x1800119db  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800119e0  test    ebx, ebx
0x1800119e2  js      short loc_180011A28
0x1800119e4  mov     r8, rbp; hData
0x1800119e7  lea     pszPackageFulllName, aOleclipprocess; "OleClipProcessOwner"
0x1800119ee  mov     hClipWnd, rdi; hWnd
0x1800119f1  call    cs:__imp_SetPropW
0x1800119f7  test    eax, eax
0x1800119f9  jnz     short loc_180011A28
0x1800119fb  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x180011a02  mov     hClipWnd, rdi; hWnd
0x180011a05  call    cs:__imp_RemovePropW
0x180011a0b  call    cs:__imp_GetLastError
0x180011a11  mov     ebx, eax
0x180011a13  test    eax, eax
0x180011a15  jle     short loc_180011A1C
0x180011a17  movzx   ebx, ax
0x180011a1a  or      ebx, esi
0x180011a1c  mov     edx, 12Eh; messageID
0x180011a21  mov     ecx, ebx; hr
0x180011a23  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x180011a28  mov     eax, ebx
0x180011a2a  add     rsp, 20h
0x180011a2e  pop     r14
0x180011a30  pop     rdi
0x180011a31  pop     rsi
0x180011a32  pop     rbp
0x180011a33  pop     rbx
0x180011a34  retn
```
