# GetPropSheetFont

- ea: `0x1800c09a8`
- end: `0x1800c0bfa`
- name: `GetPropSheetFont`
- size: `594`
- prototype: `HFONT__ *__fastcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c1534`

## callees

- `0x180046460`
- `0x180047484`
- `0x1800c09a8`
- `0x1800ce967`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800c0a44`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800c0a44`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c0b61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c0b61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c0a08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c0a2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c0a08`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c0a2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800c0a99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800c0a99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0a61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0a61`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800c0aa8`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800c0aa8`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800c0a87`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800c0a87`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800c0b9c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800c0b9c`
- `GDI32!CreateFontIndirectW` at `0x1800c0bc4`
- `GDI32!CreateFontIndirectW` at `0x1800c0bc4`
- `GDI32!GetDeviceCaps` at `0x1800c0b86`
- `GDI32!GetDeviceCaps` at `0x1800c0b86`
- `USER32!ReleaseDC` at `0x1800c0bb3`
- `USER32!ReleaseDC` at `0x1800c0bb3`
- `USER32!GetDC` at `0x1800c0b6f`
- `USER32!GetDC` at `0x1800c0b6f`

## pseudocode

```c
HFONT __fastcall GetPropSheetFont()
{
  int v0; // esi
  int v1; // edi
  HMODULE Library; // rax
  HMODULE v3; // rbx
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  _DWORD *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned __int16 *v9; // rdx
  unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  HDC DC; // rbx
  int DeviceCaps; // eax
  tagLOGFONTW logfontW; // [rsp+20h] [rbp-98h] BYREF
  wchar_t wszlfHeight[16]; // [rsp+80h] [rbp-38h] BYREF

  memset_0(&logfontW, 0, sizeof(logfontW));
  v0 = 8;
  logfontW.lfWeight = 400;
  logfontW.lfCharSet = 1;
  v1 = 32;
  LoadStringW(g_hinstDLL, 0x64u, logfontW.lfFaceName, 32);
  if ( LoadStringW(g_hinstDLL, 0x65u, wszlfHeight, 16) )
    v0 = _o__wtoi(wszlfHeight);
  Library = LoadLibraryExW(wszCOMCTL32, 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ResourceW = FindResourceW(Library, (LPCWSTR)0x3EE, (LPCWSTR)5);
    Resource = LoadResource(v3, ResourceW);
    v6 = LockResource(Resource);
    if ( v6 )
    {
      v7 = 3;
      if ( (*v6 & 0xFFFF0000) != 0xFFFF0000 )
        v7 = 1;
      v8 = 26;
      if ( (*v6 & 0xFFFF0000) != 0xFFFF0000 )
        v8 = 18;
      v9 = (unsigned __int16 *)((char *)v6 + v8);
      if ( *v9 == 0xFFFF )
      {
        v9 += 2;
      }
      else
      {
        while ( *v9++ )
          ;
      }
      if ( *v9 == 0xFFFF )
      {
        v9 += 2;
      }
      else
      {
        while ( *v9++ )
          ;
      }
      while ( *v9++ )
        ;
      v0 = *v9;
      v13 = &v9[v7];
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( v13[v15] );
      if ( (unsigned __int64)(v15 + 1) <= 0x20 )
      {
        do
          ++v14;
        while ( v13[v14] );
        v1 = v14 + 1;
      }
      memcpy_0(logfontW.lfFaceName, v13, 2LL * v1);
    }
    FreeLibrary(v3);
  }
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 90);
  logfontW.lfHeight = -MulDiv(v0, DeviceCaps, 72);
  ReleaseDC(0, DC);
  return CreateFontIndirectW(&logfontW);
}

```

## disassembly

```asm
0x1800c09a8  mov     [rsp+arg_0], rbx
0x1800c09ad  mov     [rsp+arg_8], rbp
0x1800c09b2  mov     [rsp+arg_10], rsi
0x1800c09b7  push    rdi
0x1800c09b8  sub     rsp, 0B0h
0x1800c09bf  mov     rax, cs:__security_cookie
0x1800c09c6  xor     rax, rsp
0x1800c09c9  mov     [rsp+0B8h+var_18], rax
0x1800c09d1  xor     edx, edx; Val
0x1800c09d3  lea     rcx, [rsp+0B8h+logfontW]; void *
0x1800c09d8  lea     r8d, [rdx+5Ch]; Size
0x1800c09dc  call    memset_0
0x1800c09e1  mov     rcx, cs:g_hinstDLL; hInstance
0x1800c09e8  lea     r8, [rsp+0B8h+logfontW.lfFaceName]; lpBuffer
0x1800c09ed  mov     esi, 8
0x1800c09f2  mov     [rsp+0B8h+logfontW.lfWeight], 190h
0x1800c09fa  mov     [rsp+0B8h+logfontW.lfCharSet], 1
0x1800c09ff  lea     edi, [rsi+18h]
0x1800c0a02  mov     r9d, edi; cchBufferMax
0x1800c0a05  lea     edx, [rsi+5Ch]; uID
0x1800c0a08  call    cs:__imp_LoadStringW
0x1800c0a0f  nop     dword ptr [rax+rax+00h]
0x1800c0a14  mov     rcx, cs:g_hinstDLL; hInstance
0x1800c0a1b  lea     r9d, [rsi+8]; cchBufferMax
0x1800c0a1f  lea     r8, [rsp+0B8h+wszlfHeight]; lpBuffer
0x1800c0a27  lea     edx, [rsi+5Dh]; uID
0x1800c0a2a  call    cs:__imp_LoadStringW
0x1800c0a31  nop     dword ptr [rax+rax+00h]
0x1800c0a36  xor     ebp, ebp
0x1800c0a38  test    eax, eax
0x1800c0a3a  jz      short loc_1800C0A52
0x1800c0a3c  lea     rcx, [rsp+0B8h+wszlfHeight]
0x1800c0a44  call    cs:__imp__o__wtoi
0x1800c0a4b  nop     dword ptr [rax+rax+00h]
0x1800c0a50  mov     esi, eax
0x1800c0a52  xor     edx, edx; hFile
0x1800c0a54  lea     rcx, wszCOMCTL32; lpLibFileName
0x1800c0a5b  mov     r8d, 800h; dwFlags
0x1800c0a61  call    cs:__imp_LoadLibraryExW
0x1800c0a68  nop     dword ptr [rax+rax+00h]
0x1800c0a6d  mov     rbx, rax
0x1800c0a70  test    rax, rax
0x1800c0a73  jz      loc_1800C0B6D
0x1800c0a79  mov     edx, 3EEh; lpName
0x1800c0a7e  mov     r8d, 5; lpType
0x1800c0a84  mov     rcx, rax; hModule
0x1800c0a87  call    cs:__imp_FindResourceW
0x1800c0a8e  nop     dword ptr [rax+rax+00h]
0x1800c0a93  mov     rdx, rax; hResInfo
0x1800c0a96  mov     rcx, rbx; hModule
0x1800c0a99  call    cs:__imp_LoadResource
0x1800c0aa0  nop     dword ptr [rax+rax+00h]
0x1800c0aa5  mov     rcx, rax; hResData
0x1800c0aa8  call    cs:__imp_LockResource
0x1800c0aaf  nop     dword ptr [rax+rax+00h]
0x1800c0ab4  test    rax, rax
0x1800c0ab7  jz      loc_1800C0B5E
0x1800c0abd  mov     ecx, [rax]
0x1800c0abf  mov     r8d, 6
0x1800c0ac5  mov     r10d, 0FFFF0000h
0x1800c0acb  and     ecx, r10d
0x1800c0ace  cmp     ecx, r10d
0x1800c0ad1  mov     ecx, 0FFFFh
0x1800c0ad6  lea     r11d, [r8-4]
0x1800c0ada  cmovnz  r8d, r11d
0x1800c0ade  lea     edx, [r11+18h]
0x1800c0ae2  lea     r9d, [r11+10h]
0x1800c0ae6  cmovnz  edx, r9d
0x1800c0aea  add     rdx, rax
0x1800c0aed  cmp     [rdx], cx
0x1800c0af0  jnz     short loc_1800C0AF8
0x1800c0af2  add     rdx, 4
0x1800c0af6  jmp     short loc_1800C0B03
0x1800c0af8  movzx   eax, word ptr [rdx]
0x1800c0afb  add     rdx, r11
0x1800c0afe  test    ax, ax
0x1800c0b01  jnz     short loc_1800C0AF8
0x1800c0b03  cmp     [rdx], cx
0x1800c0b06  jnz     short loc_1800C0B0E
0x1800c0b08  add     rdx, 4
0x1800c0b0c  jmp     short loc_1800C0B19
0x1800c0b0e  movzx   eax, word ptr [rdx]
0x1800c0b11  add     rdx, r11
0x1800c0b14  test    ax, ax
0x1800c0b17  jnz     short loc_1800C0B0E
0x1800c0b19  movzx   eax, word ptr [rdx]
0x1800c0b1c  add     rdx, r11
0x1800c0b1f  test    ax, ax
0x1800c0b22  jnz     short loc_1800C0B19
0x1800c0b24  movzx   esi, word ptr [rdx]
0x1800c0b27  add     rdx, r8; Src
0x1800c0b2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c0b2e  mov     rcx, rax
0x1800c0b31  inc     rcx
0x1800c0b34  cmp     [rdx+rcx*2], bp
0x1800c0b38  jnz     short loc_1800C0B31
0x1800c0b3a  inc     rcx
0x1800c0b3d  cmp     rcx, rdi
0x1800c0b40  ja      short loc_1800C0B4E
0x1800c0b42  inc     rax
0x1800c0b45  cmp     [rdx+rax*2], bp
0x1800c0b49  jnz     short loc_1800C0B42
0x1800c0b4b  lea     edi, [rax+1]
0x1800c0b4e  movsxd  r8, edi
0x1800c0b51  lea     rcx, [rsp+0B8h+logfontW.lfFaceName]; void *
0x1800c0b56  add     r8, r8; Size
0x1800c0b59  call    memcpy_0
0x1800c0b5e  mov     rcx, rbx; hLibModule
0x1800c0b61  call    cs:__imp_FreeLibrary
0x1800c0b68  nop     dword ptr [rax+rax+00h]
0x1800c0b6d  xor     ecx, ecx; hWnd
0x1800c0b6f  call    cs:__imp_GetDC
0x1800c0b76  nop     dword ptr [rax+rax+00h]
0x1800c0b7b  mov     rcx, rax; hdc
0x1800c0b7e  mov     edx, 5Ah ; 'Z'; index
0x1800c0b83  mov     rbx, rax
0x1800c0b86  call    cs:__imp_GetDeviceCaps
0x1800c0b8d  nop     dword ptr [rax+rax+00h]
0x1800c0b92  mov     r8d, 48h ; 'H'; nDenominator
0x1800c0b98  mov     ecx, esi; nNumber
0x1800c0b9a  mov     edx, eax; nNumerator
0x1800c0b9c  call    cs:__imp_MulDiv
0x1800c0ba3  nop     dword ptr [rax+rax+00h]
0x1800c0ba8  mov     rdx, rbx; hDC
0x1800c0bab  xor     ecx, ecx; hWnd
0x1800c0bad  neg     eax
0x1800c0baf  mov     [rsp+0B8h+logfontW.lfHeight], eax
0x1800c0bb3  call    cs:__imp_ReleaseDC
0x1800c0bba  nop     dword ptr [rax+rax+00h]
0x1800c0bbf  lea     rcx, [rsp+0B8h+logfontW]; lplf
0x1800c0bc4  call    cs:__imp_CreateFontIndirectW
0x1800c0bcb  nop     dword ptr [rax+rax+00h]
0x1800c0bd0  mov     rcx, [rsp+0B8h+var_18]
0x1800c0bd8  xor     rcx, rsp; StackCookie
0x1800c0bdb  call    __security_check_cookie
0x1800c0be0  lea     r11, [rsp+0B8h+var_8]
0x1800c0be8  mov     rbx, [r11+10h]
0x1800c0bec  mov     rbp, [r11+18h]
0x1800c0bf0  mov     rsi, [r11+20h]
0x1800c0bf4  mov     rsp, r11
0x1800c0bf7  pop     rdi
0x1800c0bf8  retn
```
