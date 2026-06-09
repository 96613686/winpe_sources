# FolderBrowser(HWND__ *,ushort *)

- ea: `0x14003f93c`
- end: `0x14003fa8d`
- name: `?FolderBrowser@@YAJPEAUHWND__@@PEAG@Z`
- size: `337`
- prototype: `int(HWND, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14002e470`
- `0x14003c470`

## callees

- `0x1400039b1`
- `0x140020420`
- `0x14003f93c`
- `0x140041c54`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003fa15`
- `KERNEL32!GetLastError` at `0x14003fa15`
- `SHELL32!SHBrowseForFolderW` at `0x14003f9e2`
- `SHELL32!SHBrowseForFolderW` at `0x14003f9e2`
- `SHELL32!SHGetPathFromIDListW` at `0x14003fa01`
- `SHELL32!SHGetPathFromIDListW` at `0x14003fa01`
- `ole32!CoTaskMemFree` at `0x14003fa59`
- `ole32!CoTaskMemFree` at `0x14003fa59`

## pseudocode

```c
__int64 __fastcall FolderBrowser(HWND a1, unsigned __int16 *a2)
{
  int LocalString; // eax
  signed int v5; // ebx
  const ITEMIDLIST *v6; // rax
  ITEMIDLIST *v7; // rdi
  signed int LastError; // eax
  struct _browseinfoW bi; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[256]; // [rsp+70h] [rbp-218h] BYREF

  memset_0(&bi, 0, sizeof(bi));
  *a2 = 0;
  Buffer[0] = 0;
  LocalString = DwzLoadLocalString(0xFDu, Buffer, 0x100u);
  v5 = LocalString;
  if ( LocalString >= 0 )
  {
    bi.hwndOwner = a1;
    bi.lpszTitle = Buffer;
    bi.pszDisplayName = a2;
    bi.ulFlags = 80;
    v6 = SHBrowseForFolderW(&bi);
    v7 = (ITEMIDLIST *)v6;
    if ( v6 )
    {
      if ( SHGetPathFromIDListW(v6, a2) )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FolderBrowser", 170, v5);
      }
      CoTaskMemFree(v7);
    }
    else
    {
      return 1;
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FolderBrowser", 153, LocalString);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003f93c  mov     [rsp+arg_10], rbx
0x14003f941  mov     [rsp+arg_18], rsi
0x14003f946  push    rdi
0x14003f947  sub     rsp, 280h
0x14003f94e  mov     rax, cs:__security_cookie
0x14003f955  xor     rax, rsp
0x14003f958  mov     [rsp+288h+var_18], rax
0x14003f960  mov     rsi, rdx
0x14003f963  mov     rdi, rcx
0x14003f966  xor     edx, edx; Val
0x14003f968  lea     rcx, [rsp+288h+bi]; void *
0x14003f96d  lea     r8d, [rdx+40h]; Size
0x14003f971  call    memset_0
0x14003f976  xor     eax, eax
0x14003f978  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x14003f97d  mov     r8d, 100h; cchBufferMax
0x14003f983  mov     [rsi], ax
0x14003f986  mov     [rsp+288h+Buffer], ax
0x14003f98b  lea     ecx, [r8-3]; uID
0x14003f98f  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003f994  mov     ebx, eax
0x14003f996  test    eax, eax
0x14003f998  jns     short loc_14003F9C1
0x14003f99a  mov     r9d, 99h
0x14003f9a0  mov     [rsp+288h+var_268], eax
0x14003f9a4  lea     r8, aFolderbrowser; "FolderBrowser"
0x14003f9ab  mov     ecx, 1; Level
0x14003f9b0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f9b7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f9bc  jmp     loc_14003FA65
0x14003f9c1  lea     rax, [rsp+288h+Buffer]
0x14003f9c6  mov     [rsp+288h+bi.hwndOwner], rdi
0x14003f9cb  lea     rcx, [rsp+288h+bi]; lpbi
0x14003f9d0  mov     [rsp+288h+bi.lpszTitle], rax
0x14003f9d5  mov     [rsp+288h+bi.pszDisplayName], rsi
0x14003f9da  mov     [rsp+288h+bi.ulFlags], 50h ; 'P'
0x14003f9e2  call    cs:__imp_SHBrowseForFolderW
0x14003f9e9  nop     dword ptr [rax+rax+00h]
0x14003f9ee  mov     rdi, rax
0x14003f9f1  test    rax, rax
0x14003f9f4  jnz     short loc_14003F9FB
0x14003f9f6  lea     ebx, [rax+1]
0x14003f9f9  jmp     short loc_14003FA65
0x14003f9fb  mov     rdx, rsi; pszPath
0x14003f9fe  mov     rcx, rdi; pidl
0x14003fa01  call    cs:__imp_SHGetPathFromIDListW
0x14003fa08  nop     dword ptr [rax+rax+00h]
0x14003fa0d  test    eax, eax
0x14003fa0f  jz      short loc_14003FA15
0x14003fa11  xor     ebx, ebx
0x14003fa13  jmp     short loc_14003FA56
0x14003fa15  call    cs:__imp_GetLastError
0x14003fa1c  nop     dword ptr [rax+rax+00h]
0x14003fa21  mov     ebx, eax
0x14003fa23  test    eax, eax
0x14003fa25  jle     short loc_14003FA30
0x14003fa27  movzx   ebx, ax
0x14003fa2a  or      ebx, 80070000h
0x14003fa30  test    ebx, ebx
0x14003fa32  jns     short loc_14003FA56
0x14003fa34  mov     r9d, 0AAh
0x14003fa3a  mov     [rsp+288h+var_268], ebx
0x14003fa3e  lea     r8, aFolderbrowser; "FolderBrowser"
0x14003fa45  mov     ecx, 1; Level
0x14003fa4a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003fa51  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003fa56  mov     rcx, rdi; pv
0x14003fa59  call    cs:__imp_CoTaskMemFree
0x14003fa60  nop     dword ptr [rax+rax+00h]
0x14003fa65  mov     eax, ebx
0x14003fa67  mov     rcx, [rsp+288h+var_18]
0x14003fa6f  xor     rcx, rsp; StackCookie
0x14003fa72  call    __security_check_cookie
0x14003fa77  lea     r11, [rsp+288h+var_8]
0x14003fa7f  mov     rbx, [r11+20h]
0x14003fa83  mov     rsi, [r11+28h]
0x14003fa87  mov     rsp, r11
0x14003fa8a  pop     rdi
0x14003fa8b  retn
```
