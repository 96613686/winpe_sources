# TUIGoLink(HWND__ *,ushort const *)

- ea: `0x18003c2c8`
- end: `0x18003c3f0`
- name: `?TUIGoLink@@YAJPEAUHWND__@@PEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(HWND hwnd, LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003cd70`

## callees

- `0x18003c2c8`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3c4`
- `USER32!SetWindowPos` at `0x18003c365`
- `USER32!SetWindowPos` at `0x18003c365`
- `USER32!LoadCursorW` at `0x18003c372`
- `USER32!LoadCursorW` at `0x18003c372`
- `USER32!SetCursor` at `0x18003c37b`
- `USER32!SetCursor` at `0x18003c3bc`
- `USER32!SetCursor` at `0x18003c37b`
- `USER32!SetCursor` at `0x18003c3bc`
- `SHELL32!ShellExecuteW` at `0x18003c3a5`
- `SHELL32!ShellExecuteW` at `0x18003c3a5`
- `WININET!InternetCrackUrlW` at `0x18003c31c`
- `WININET!InternetCrackUrlW` at `0x18003c31c`

## pseudocode

```c
__int64 __fastcall TUIGoLink(HWND hwnd, LPCWSTR lpFile)
{
  unsigned int v5; // edi
  HCURSOR CursorW; // rax
  HCURSOR v7; // rbx
  HINSTANCE v8; // rax
  signed int LastError; // eax
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+40h] [rbp-78h] BYREF

  if ( !lpFile )
    return 2147500035LL;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.nScheme = INTERNET_SCHEME_UNKNOWN;
  if ( InternetCrackUrlW(lpFile, 0, 0, &UrlComponents) )
  {
    if ( (unsigned int)(UrlComponents.nScheme - 3) <= 1 )
    {
      SetWindowPos(hwnd, (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, 0, 0, 3u);
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      v7 = SetCursor(CursorW);
      v8 = ShellExecuteW(hwnd, L"open", lpFile, 0, 0, 1);
      v5 = -2147467259;
      if ( (unsigned __int64)v8 > 0x20 )
        v5 = 0;
      SetCursor(v7);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x18003c2c8  mov     [rsp+arg_0], rbx
0x18003c2cd  mov     [rsp+arg_8], rsi
0x18003c2d2  push    rdi
0x18003c2d3  sub     rsp, 0B0h
0x18003c2da  mov     rdi, rdx
0x18003c2dd  mov     rsi, rcx
0x18003c2e0  test    rdx, rdx
0x18003c2e3  jnz     short loc_18003C2EF
0x18003c2e5  mov     eax, 80004003h
0x18003c2ea  jmp     loc_18003C3DB
0x18003c2ef  mov     ebx, 68h ; 'h'
0x18003c2f4  lea     rcx, [rsp+0B8h+UrlComponents]; void *
0x18003c2f9  mov     r8d, ebx; Size
0x18003c2fc  xor     edx, edx; Val
0x18003c2fe  call    memset_0
0x18003c303  lea     r9, [rsp+0B8h+UrlComponents]; lpUrlComponents
0x18003c308  mov     [rsp+0B8h+UrlComponents.dwStructSize], ebx
0x18003c30c  xor     r8d, r8d; dwFlags
0x18003c30f  mov     [rsp+0B8h+UrlComponents.nScheme], 0FFFFFFFFh
0x18003c317  xor     edx, edx; dwUrlLength
0x18003c319  mov     rcx, rdi; lpszUrl
0x18003c31c  call    cs:__imp_InternetCrackUrlW
0x18003c322  test    eax, eax
0x18003c324  jz      loc_18003C3C4
0x18003c32a  mov     eax, [rsp+0B8h+UrlComponents.nScheme]
0x18003c32e  add     eax, 0FFFFFFFDh
0x18003c331  cmp     eax, 1
0x18003c334  jbe     short loc_18003C340
0x18003c336  mov     edi, 80070057h
0x18003c33b  jmp     loc_18003C3D9
0x18003c340  xor     r9d, r9d; Y
0x18003c343  mov     [rsp+0B8h+uFlags], 3; uFlags
0x18003c34b  mov     [rsp+0B8h+cy], 0; cy
0x18003c353  xor     r8d, r8d; X
0x18003c356  mov     rcx, rsi; hWnd
0x18003c359  mov     dword ptr [rsp+0B8h+lpDirectory], 0; cx
0x18003c361  lea     rdx, [r9-2]; hWndInsertAfter
0x18003c365  call    cs:__imp_SetWindowPos
0x18003c36b  mov     edx, 7F02h; lpCursorName
0x18003c370  xor     ecx, ecx; hInstance
0x18003c372  call    cs:__imp_LoadCursorW
0x18003c378  mov     rcx, rax; hCursor
0x18003c37b  call    cs:__imp_SetCursor
0x18003c381  xor     r9d, r9d; lpParameters
0x18003c384  mov     [rsp+0B8h+cy], 1; nShowCmd
0x18003c38c  mov     r8, rdi; lpFile
0x18003c38f  mov     [rsp+0B8h+lpDirectory], 0; lpDirectory
0x18003c398  lea     rdx, Operation; "open"
0x18003c39f  mov     rcx, rsi; hwnd
0x18003c3a2  mov     rbx, rax
0x18003c3a5  call    cs:__imp_ShellExecuteW
0x18003c3ab  xor     ecx, ecx
0x18003c3ad  mov     edi, 80004005h
0x18003c3b2  cmp     rax, 20h ; ' '
0x18003c3b6  cmova   edi, ecx
0x18003c3b9  mov     rcx, rbx; hCursor
0x18003c3bc  call    cs:__imp_SetCursor
0x18003c3c2  jmp     short loc_18003C3D9
0x18003c3c4  call    cs:__imp_GetLastError
0x18003c3ca  mov     edi, eax
0x18003c3cc  test    eax, eax
0x18003c3ce  jle     short loc_18003C3D9
0x18003c3d0  movzx   edi, ax
0x18003c3d3  or      edi, 80070000h
0x18003c3d9  mov     eax, edi
0x18003c3db  lea     r11, [rsp+0B8h+var_8]
0x18003c3e3  mov     rbx, [r11+10h]
0x18003c3e7  mov     rsi, [r11+18h]
0x18003c3eb  mov     rsp, r11
0x18003c3ee  pop     rdi
0x18003c3ef  retn
```
