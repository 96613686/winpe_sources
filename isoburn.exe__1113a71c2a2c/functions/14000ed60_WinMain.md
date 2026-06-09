# WinMain

- ea: `0x14000ed60`
- end: `0x14000edf7`
- name: `WinMain`
- size: `151`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001df0`

## callees

- `0x140002bc6`
- `0x14000e89c`
- `0x14000ed60`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x14000ed69`
- `KERNEL32!GetCommandLineW` at `0x14000ed69`
- `KERNEL32!GetStartupInfoW` at `0x14000edd8`
- `KERNEL32!GetStartupInfoW` at `0x14000edd8`
- `KERNEL32!GetModuleHandleW` at `0x14000ede0`
- `KERNEL32!GetModuleHandleW` at `0x14000ede0`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  LPWSTR CommandLineW; // rax
  const unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rcx
  unsigned __int16 v7; // ax
  __int64 v8; // rbx
  HINSTANCE v9; // rdx
  HINSTANCE v10; // rcx
  struct _STARTUPINFOW StartupInfo; // [rsp+20h] [rbp-78h] BYREF

  CommandLineW = GetCommandLineW();
  v5 = CommandLineW;
  if ( *CommandLineW == 34 )
  {
    do
    {
      v6 = v5++;
      v7 = *v5;
    }
    while ( *v5 && v7 != 34 );
    v8 = 2;
    if ( v7 != 34 )
      v8 = 1;
    v5 = &v6[v8];
  }
  else if ( *CommandLineW > 0x20u )
  {
    do
      ++v5;
    while ( *v5 > 0x20u );
  }
  while ( *v5 == 32 || *v5 == 9 )
    ++v5;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  GetStartupInfoW(&StartupInfo);
  GetModuleHandleW(0);
  return WinMainT(v10, v9, v5);
}

```

## disassembly

```asm
0x14000ed60  push    rbx
0x14000ed62  sub     rsp, 90h
0x14000ed69  call    cs:__imp_GetCommandLineW
0x14000ed6f  mov     rbx, rax
0x14000ed72  mov     edx, 2
0x14000ed77  cmp     word ptr [rax], 22h ; '"'
0x14000ed7b  jnz     short loc_14000EDA3
0x14000ed7d  mov     rcx, rbx
0x14000ed80  add     rbx, rdx
0x14000ed83  movzx   eax, word ptr [rbx]
0x14000ed86  test    ax, ax
0x14000ed89  jz      short loc_14000ED91
0x14000ed8b  cmp     ax, 22h ; '"'
0x14000ed8f  jnz     short loc_14000ED7D
0x14000ed91  cmp     ax, 22h ; '"'
0x14000ed95  mov     ebx, 4
0x14000ed9a  cmovnz  rbx, rdx
0x14000ed9e  add     rbx, rcx
0x14000eda1  jmp     short loc_14000EDB2
0x14000eda3  cmp     word ptr [rax], 20h ; ' '
0x14000eda7  jbe     short loc_14000EDB2
0x14000eda9  add     rbx, rdx
0x14000edac  cmp     word ptr [rbx], 20h ; ' '
0x14000edb0  ja      short loc_14000EDA9
0x14000edb2  cmp     word ptr [rbx], 20h ; ' '
0x14000edb6  jz      short loc_14000EDBE
0x14000edb8  cmp     word ptr [rbx], 9
0x14000edbc  jnz     short loc_14000EDC3
0x14000edbe  add     rbx, rdx
0x14000edc1  jmp     short loc_14000EDB2
0x14000edc3  xor     edx, edx; Val
0x14000edc5  lea     rcx, [rsp+98h+StartupInfo]; void *
0x14000edca  lea     r8d, [rdx+68h]; Size
0x14000edce  call    memset_0
0x14000edd3  lea     rcx, [rsp+98h+StartupInfo]; lpStartupInfo
0x14000edd8  call    cs:__imp_GetStartupInfoW
0x14000edde  xor     ecx, ecx; lpModuleName
0x14000ede0  call    cs:__imp_GetModuleHandleW
0x14000ede6  mov     r8, rbx; unsigned __int16 *
0x14000ede9  call    ?WinMainT@@YAHPEAUHINSTANCE__@@0PEBGH@Z; WinMainT(HINSTANCE__ *,HINSTANCE__ *,ushort const *,int)
0x14000edee  add     rsp, 90h
0x14000edf5  pop     rbx
0x14000edf6  retn
```
