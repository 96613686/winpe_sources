# OpenUACControlPanel(IUnknown *,HWND__ *)

- ea: `0x180008a00`
- end: `0x180008a5a`
- name: `?OpenUACControlPanel@@YAJPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(struct IUnknown *, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180009e16`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180008a42`
- `SHELL32!ShellExecuteExW` at `0x180008a42`

## string_xrefs

- `0x180008a24`: `%systemroot%\system32\UserAccountControlSettings.exe`

## pseudocode

```c
__int64 __fastcall OpenUACControlPanel(struct IUnknown *a1, HWND a2)
{
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-78h] BYREF

  pExecInfo.cbSize = 112;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.fMask = 512;
  pExecInfo.lpFile = L"%systemroot%\\system32\\UserAccountControlSettings.exe";
  pExecInfo.hwnd = a2;
  ShellExecuteExW(&pExecInfo);
  return 0;
}

```

## disassembly

```asm
0x180008a00  push    rbx
0x180008a02  sub     rsp, 90h
0x180008a09  mov     rbx, rdx
0x180008a0c  mov     [rsp+98h+pExecInfo.cbSize], 70h ; 'p'
0x180008a14  xor     edx, edx; Val
0x180008a16  lea     rcx, [rsp+98h+pExecInfo.fMask]; void *
0x180008a1b  lea     r8d, [rdx+6Ch]; Size
0x180008a1f  call    memset_0
0x180008a24  lea     rax, aSystemrootSyst_1; "%systemroot%\\system32\\UserAccountCont"...
0x180008a2b  mov     [rsp+98h+pExecInfo.fMask], 200h
0x180008a33  lea     rcx, [rsp+98h+pExecInfo]; pExecInfo
0x180008a38  mov     [rsp+98h+pExecInfo.lpFile], rax
0x180008a3d  mov     [rsp+98h+pExecInfo.hwnd], rbx
0x180008a42  call    cs:__imp_ShellExecuteExW
0x180008a49  nop     dword ptr [rax+rax+00h]
0x180008a4e  xor     eax, eax
0x180008a50  add     rsp, 90h
0x180008a57  pop     rbx
0x180008a58  retn
```
