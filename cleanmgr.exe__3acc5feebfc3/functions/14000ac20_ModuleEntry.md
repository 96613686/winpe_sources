# ModuleEntry

- ea: `0x14000ac20`
- end: `0x14000acf9`
- name: `ModuleEntry`
- size: `217`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ad00`

## callees

- `0x140003390`
- `0x140009d34`
- `0x14000ac20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000acd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000acd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000ac4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14000ac4b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000ac3d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14000ac3d`
- `KERNEL32!GetStartupInfoA` at `0x14000acb9`
- `KERNEL32!GetStartupInfoA` at `0x14000acb9`

## pseudocode

```c
__int64 ModuleEntry()
{
  LPWSTR CommandLineW; // rbx
  unsigned __int16 v1; // ax
  LPWSTR v2; // rdx
  WCHAR v3; // cx
  __int64 v4; // rbx
  WCHAR v5; // ax
  int wShowWindow; // edi
  HMODULE ModuleHandleW; // rax
  _STARTUPINFOA StartupInfo; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  CommandLineW = GetCommandLineW();
  SetErrorMode(1u);
  v1 = *CommandLineW;
  if ( *CommandLineW == 34 )
  {
    do
    {
      v2 = CommandLineW++;
      v3 = *CommandLineW;
    }
    while ( *CommandLineW && v3 != 34 );
    v4 = 2;
    if ( v3 != 34 )
      v4 = 1;
    CommandLineW = &v2[v4];
    v1 = *CommandLineW;
  }
  else
  {
    while ( v1 > 0x20u )
      v1 = *++CommandLineW;
  }
  if ( v1 )
  {
    v5 = *CommandLineW;
    do
    {
      if ( v5 > 0x20u )
        break;
      v5 = *++CommandLineW;
    }
    while ( *CommandLineW );
  }
  StartupInfo.dwFlags = 0;
  GetStartupInfoA(&StartupInfo);
  wShowWindow = StartupInfo.wShowWindow;
  if ( (StartupInfo.dwFlags & 1) == 0 )
    wShowWindow = 10;
  ModuleHandleW = GetModuleHandleW(0);
  return WinMainT(ModuleHandleW, 0, CommandLineW, wShowWindow);
}

```

## disassembly

```asm
0x14000ac20  mov     [rsp+arg_0], rbx
0x14000ac25  push    rdi
0x14000ac26  sub     rsp, 90h
0x14000ac2d  xor     edx, edx; Val
0x14000ac2f  lea     rcx, [rsp+98h+StartupInfo]; void *
0x14000ac34  lea     r8d, [rdx+68h]; Size
0x14000ac38  call    memset_0
0x14000ac3d  call    cs:__imp_GetCommandLineW
0x14000ac43  mov     ecx, 1; uMode
0x14000ac48  mov     rbx, rax
0x14000ac4b  call    cs:__imp_SetErrorMode
0x14000ac51  movzx   eax, word ptr [rbx]
0x14000ac54  xor     r8d, r8d
0x14000ac57  lea     r9d, [r8+2]
0x14000ac5b  cmp     ax, 22h ; '"'
0x14000ac5f  jnz     short loc_14000AC90
0x14000ac61  mov     rdx, rbx
0x14000ac64  add     rbx, r9
0x14000ac67  movzx   ecx, word ptr [rbx]
0x14000ac6a  test    cx, cx
0x14000ac6d  jz      short loc_14000AC75
0x14000ac6f  cmp     cx, 22h ; '"'
0x14000ac73  jnz     short loc_14000AC61
0x14000ac75  cmp     cx, 22h ; '"'
0x14000ac79  mov     ebx, 4
0x14000ac7e  cmovnz  rbx, r9
0x14000ac82  add     rbx, rdx
0x14000ac85  movzx   eax, word ptr [rbx]
0x14000ac88  jmp     short loc_14000AC96
0x14000ac8a  add     rbx, r9
0x14000ac8d  movzx   eax, word ptr [rbx]
0x14000ac90  cmp     ax, 20h ; ' '
0x14000ac94  ja      short loc_14000AC8A
0x14000ac96  test    ax, ax
0x14000ac99  jz      short loc_14000ACAF
0x14000ac9b  movzx   eax, word ptr [rbx]
0x14000ac9e  cmp     ax, 20h ; ' '
0x14000aca2  ja      short loc_14000ACAF
0x14000aca4  add     rbx, r9
0x14000aca7  movzx   eax, word ptr [rbx]
0x14000acaa  test    ax, ax
0x14000acad  jnz     short loc_14000AC9E
0x14000acaf  lea     rcx, [rsp+98h+StartupInfo]; lpStartupInfo
0x14000acb4  mov     [rsp+98h+StartupInfo.dwFlags], r8d
0x14000acb9  call    cs:__imp_GetStartupInfoA
0x14000acbf  test    byte ptr [rsp+98h+StartupInfo.dwFlags], 1
0x14000acc4  movzx   edi, [rsp+98h+StartupInfo.wShowWindow]
0x14000acc9  jnz     short loc_14000ACD0
0x14000accb  mov     edi, 0Ah
0x14000acd0  xor     ecx, ecx; lpModuleName
0x14000acd2  call    cs:__imp_GetModuleHandleW
0x14000acd8  mov     r9d, edi; int
0x14000acdb  mov     r8, rbx; unsigned __int16 *
0x14000acde  mov     rcx, rax; HINSTANCE
0x14000ace1  xor     edx, edx; HINSTANCE
0x14000ace3  call    ?WinMainT@@YAHPEAUHINSTANCE__@@0PEAGH@Z; WinMainT(HINSTANCE__ *,HINSTANCE__ *,ushort *,int)
0x14000ace8  mov     rbx, [rsp+98h+arg_0]
0x14000acf0  add     rsp, 90h
0x14000acf7  pop     rdi
0x14000acf8  retn
```
