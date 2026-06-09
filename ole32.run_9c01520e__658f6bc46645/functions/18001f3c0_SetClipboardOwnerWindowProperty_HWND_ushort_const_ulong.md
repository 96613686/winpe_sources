# SetClipboardOwnerWindowProperty(HWND__ *,ushort const *,ulong)

- ea: `0x18001f3c0`
- end: `0x18001f4ee`
- name: `?SetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEBGK@Z`
- size: `302`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, const wchar_t *pszPackageFulllName, unsigned int pid)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e5b4`

## callees

- `0x18001c778`
- `0x18001f3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ac`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18001f41d`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18001f41d`
- `USER32!RemovePropW` at `0x18001f3ef`
- `USER32!RemovePropW` at `0x18001f405`
- `USER32!RemovePropW` at `0x18001f4a0`
- `USER32!RemovePropW` at `0x18001f3ef`
- `USER32!RemovePropW` at `0x18001f405`
- `USER32!RemovePropW` at `0x18001f4a0`
- `USER32!SetPropW` at `0x18001f441`
- `USER32!SetPropW` at `0x18001f486`
- `USER32!SetPropW` at `0x18001f441`
- `USER32!SetPropW` at `0x18001f486`

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
0x18001f3c0  mov     rax, rsp
0x18001f3c3  mov     [rax+8], rbx
0x18001f3c7  mov     [rax+10h], rbp
0x18001f3cb  mov     [rax+18h], rsi
0x18001f3cf  mov     [rax+20h], rdi
0x18001f3d3  push    r14
0x18001f3d5  sub     rsp, 20h
0x18001f3d9  mov     rsi, pszPackageFulllName
0x18001f3dc  mov     ebp, pid
0x18001f3df  xor     r14d, r14d
0x18001f3e2  lea     pszPackageFulllName, aOleclipprocess; "OleClipProcessOwner"
0x18001f3e9  mov     ebx, r14d
0x18001f3ec  mov     rdi, hClipWnd
0x18001f3ef  call    cs:__imp_RemovePropW
0x18001f3f6  nop     dword ptr [rax+rax+00h]
0x18001f3fb  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x18001f402  mov     hClipWnd, rdi; hWnd
0x18001f405  call    cs:__imp_RemovePropW
0x18001f40c  nop     dword ptr [rax+rax+00h]
0x18001f411  test    rsi, rsi
0x18001f414  jz      loc_18001F4D0
0x18001f41a  mov     hClipWnd, rsi; lpString
0x18001f41d  call    cs:__imp_GlobalAddAtomW
0x18001f424  nop     dword ptr [rax+rax+00h]
0x18001f429  mov     esi, 12Eh
0x18001f42e  test    ax, ax
0x18001f431  jz      short loc_18001F451
0x18001f433  movzx   pid, ax; hData
0x18001f437  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x18001f43e  mov     hClipWnd, rdi; hWnd
0x18001f441  call    cs:__imp_SetPropW
0x18001f448  nop     dword ptr [rax+rax+00h]
0x18001f44d  test    eax, eax
0x18001f44f  jnz     short loc_18001F479
0x18001f451  call    cs:__imp_GetLastError
0x18001f458  nop     dword ptr [rax+rax+00h]
0x18001f45d  mov     ebx, eax
0x18001f45f  test    eax, eax
0x18001f461  jle     short loc_18001F46C
0x18001f463  movzx   ebx, ax
0x18001f466  or      ebx, 80070000h
0x18001f46c  mov     edx, esi; messageID
0x18001f46e  mov     ecx, ebx; hr
0x18001f470  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001f475  test    ebx, ebx
0x18001f477  js      short loc_18001F4D0
0x18001f479  mov     r8, rbp; hData
0x18001f47c  lea     pszPackageFulllName, aOleclipprocess; "OleClipProcessOwner"
0x18001f483  mov     hClipWnd, rdi; hWnd
0x18001f486  call    cs:__imp_SetPropW
0x18001f48d  nop     dword ptr [rax+rax+00h]
0x18001f492  test    eax, eax
0x18001f494  jnz     short loc_18001F4D0
0x18001f496  lea     pszPackageFulllName, aOleclippackgeo; "OLEClipPackgeOwner"
0x18001f49d  mov     hClipWnd, rdi; hWnd
0x18001f4a0  call    cs:__imp_RemovePropW
0x18001f4a7  nop     dword ptr [rax+rax+00h]
0x18001f4ac  call    cs:__imp_GetLastError
0x18001f4b3  nop     dword ptr [rax+rax+00h]
0x18001f4b8  mov     ebx, eax
0x18001f4ba  test    eax, eax
0x18001f4bc  jle     short loc_18001F4C7
0x18001f4be  movzx   ebx, ax
0x18001f4c1  or      ebx, 80070000h
0x18001f4c7  mov     edx, esi; messageID
0x18001f4c9  mov     ecx, ebx; hr
0x18001f4cb  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001f4d0  mov     rbp, [rsp+28h+arg_8]
0x18001f4d5  mov     eax, ebx
0x18001f4d7  mov     rbx, [rsp+28h+arg_0]
0x18001f4dc  mov     rsi, [rsp+28h+arg_10]
0x18001f4e1  mov     rdi, [rsp+28h+arg_18]
0x18001f4e6  add     rsp, 20h
0x18001f4ea  pop     r14
0x18001f4ec  retn
```
