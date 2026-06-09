# OpenTaskManagerUI(IUnknown *,HWND__ *)

- ea: `0x180007a00`
- end: `0x180007a7a`
- name: `?OpenTaskManagerUI@@YAJPEAUIUnknown@@PEAUHWND__@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(struct IUnknown *, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180009e16`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180007a62`
- `SHELL32!ShellExecuteExW` at `0x180007a62`

## string_xrefs

- `0x180007a24`: `%systemroot%\system32\Taskmgr.exe`
- `0x180007a4e`: `%systemroot%\system32`

## pseudocode

```c
__int64 __fastcall OpenTaskManagerUI(struct IUnknown *a1, HWND a2)
{
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-78h] BYREF

  pExecInfo.cbSize = 112;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.fMask = 512;
  pExecInfo.lpFile = L"%systemroot%\\system32\\Taskmgr.exe";
  pExecInfo.hwnd = a2;
  pExecInfo.lpParameters = L"/8 /Startup";
  pExecInfo.lpDirectory = L"%systemroot%\\system32";
  pExecInfo.nShow = 1;
  ShellExecuteExW(&pExecInfo);
  return 0;
}

```

## disassembly

```asm
0x180007a00  push    rbx
0x180007a02  sub     rsp, 90h
0x180007a09  mov     rbx, rdx
0x180007a0c  mov     [rsp+98h+pExecInfo.cbSize], 70h ; 'p'
0x180007a14  xor     edx, edx; Val
0x180007a16  lea     rcx, [rsp+98h+pExecInfo.fMask]; void *
0x180007a1b  lea     r8d, [rdx+6Ch]; Size
0x180007a1f  call    memset_0
0x180007a24  lea     rax, aSystemrootSyst_0; "%systemroot%\\system32\\Taskmgr.exe"
0x180007a2b  mov     [rsp+98h+pExecInfo.fMask], 200h
0x180007a33  mov     [rsp+98h+pExecInfo.lpFile], rax
0x180007a38  lea     rcx, [rsp+98h+pExecInfo]; pExecInfo
0x180007a3d  lea     rax, a8Startup; "/8 /Startup"
0x180007a44  mov     [rsp+98h+pExecInfo.hwnd], rbx
0x180007a49  mov     [rsp+98h+pExecInfo.lpParameters], rax
0x180007a4e  lea     rax, aSystemrootSyst; "%systemroot%\\system32"
0x180007a55  mov     [rsp+98h+pExecInfo.lpDirectory], rax
0x180007a5a  mov     [rsp+98h+pExecInfo.nShow], 1
0x180007a62  call    cs:__imp_ShellExecuteExW
0x180007a69  nop     dword ptr [rax+rax+00h]
0x180007a6e  xor     eax, eax
0x180007a70  add     rsp, 90h
0x180007a77  pop     rbx
0x180007a78  retn
```
