# LaunchApplicationW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180008ad0`
- end: `0x180008baf`
- name: `?LaunchApplicationW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `223`
- prototype: `void __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008ad0`
- `0x18000e240`
- `0x1800191a2`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180008b0e`
- `msvcrt!_wcsdup` at `0x180008b0e`
- `msvcrt!free` at `0x180008b94`
- `msvcrt!free` at `0x180008b94`
- `KERNEL32!CloseHandle` at `0x180008b86`
- `KERNEL32!CloseHandle` at `0x180008b86`
- `SHELL32!ShellExecuteExW` at `0x180008b73`
- `SHELL32!ShellExecuteExW` at `0x180008b73`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180008b28`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180008b28`
- `SHLWAPI!PathUnquoteSpacesW` at `0x180008b1f`
- `SHLWAPI!PathUnquoteSpacesW` at `0x180008b1f`

## string_xrefs

- `0x180008aed`: `CommandLine: %ws`

## pseudocode

```c
void __fastcall LaunchApplicationW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  WCHAR *v5; // rax
  WCHAR *v6; // rbx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-78h] BYREF

  AslLogCallPrintf(3, "LaunchApplicationW", 1044, "CommandLine: %ws", a3);
  v5 = _wcsdup(a3);
  v6 = v5;
  if ( v5 )
  {
    PathUnquoteSpacesW(v5);
    PathRemoveFileSpecW(v6);
  }
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.hwnd = a1;
  pExecInfo.lpFile = a3;
  pExecInfo.lpDirectory = v6;
  pExecInfo.lpParameters = 0;
  pExecInfo.nShow = 1;
  pExecInfo.fMask = 1024;
  ShellExecuteExW(&pExecInfo);
  if ( pExecInfo.hProcess )
    CloseHandle(pExecInfo.hProcess);
  if ( v6 )
    free(v6);
}

```

## disassembly

```asm
0x180008ad0  mov     [rsp+arg_0], rbx
0x180008ad5  mov     [rsp+arg_8], rsi
0x180008ada  push    rdi
0x180008adb  sub     rsp, 0A0h
0x180008ae2  mov     rdi, r8
0x180008ae5  mov     [rsp+0A8h+var_88], r8
0x180008aea  mov     rsi, rcx
0x180008aed  lea     r9, aCommandlineWs; "CommandLine: %ws"
0x180008af4  mov     r8d, 414h
0x180008afa  lea     rdx, aLaunchapplicat_0; "LaunchApplicationW"
0x180008b01  mov     ecx, 3
0x180008b06  call    AslLogCallPrintf
0x180008b0b  mov     rcx, rdi; String
0x180008b0e  call    cs:__imp__wcsdup
0x180008b14  mov     rbx, rax
0x180008b17  test    rax, rax
0x180008b1a  jz      short loc_180008B2E
0x180008b1c  mov     rcx, rax; lpsz
0x180008b1f  call    cs:__imp_PathUnquoteSpacesW
0x180008b25  mov     rcx, rbx; pszPath
0x180008b28  call    cs:__imp_PathRemoveFileSpecW
0x180008b2e  xor     edx, edx; Val
0x180008b30  lea     rcx, [rsp+0A8h+pExecInfo]; void *
0x180008b35  lea     r8d, [rdx+70h]; Size
0x180008b39  call    memset_0
0x180008b3e  lea     rcx, [rsp+0A8h+pExecInfo]; pExecInfo
0x180008b43  mov     [rsp+0A8h+pExecInfo.cbSize], 70h ; 'p'
0x180008b4b  mov     [rsp+0A8h+pExecInfo.hwnd], rsi
0x180008b50  mov     [rsp+0A8h+pExecInfo.lpFile], rdi
0x180008b55  mov     [rsp+0A8h+pExecInfo.lpDirectory], rbx
0x180008b5a  mov     [rsp+0A8h+pExecInfo.lpParameters], 0
0x180008b63  mov     [rsp+0A8h+pExecInfo.nShow], 1
0x180008b6b  mov     [rsp+0A8h+pExecInfo.fMask], 400h
0x180008b73  call    cs:__imp_ShellExecuteExW
0x180008b79  mov     rcx, [rsp+0A8h+pExecInfo.hProcess]; hObject
0x180008b81  test    rcx, rcx
0x180008b84  jz      short loc_180008B8C
0x180008b86  call    cs:__imp_CloseHandle
0x180008b8c  test    rbx, rbx
0x180008b8f  jz      short loc_180008B9A
0x180008b91  mov     rcx, rbx; Block
0x180008b94  call    cs:__imp_free
0x180008b9a  lea     r11, [rsp+0A8h+var_8]
0x180008ba2  mov     rbx, [r11+10h]
0x180008ba6  mov     rsi, [r11+18h]
0x180008baa  mov     rsp, r11
0x180008bad  pop     rdi
0x180008bae  retn
```
