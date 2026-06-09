# IrtlTrace

- ea: `0x180012ea0`
- end: `0x180012f5d`
- name: `IrtlTrace`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180008000`
- `0x180012ea0`
- `0x18002e560`
- `0x18002e5f0`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x180012ef9`
- `msvcrt!_vsnwprintf_s` at `0x180012ef9`

## string_xrefs

- `0x180012f33`: `servercommon\inetsrv\iis\iisrearc\core\common\util\irtldbg.cpp`

## pseudocode

```c
int IrtlTrace(const wchar_t *a1, ...)
{
  int result; // eax
  wchar_t Buffer[2048]; // [rsp+40h] [rbp-1018h] BYREF
  va_list va; // [rsp+1068h] [rbp+10h] BYREF

  va_start(va, a1);
  result = _vsnwprintf_s(Buffer, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, a1, va);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    return PuDbgPrint(
             (struct _DEBUG_PRINTS *)g_pDebug,
             "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\irtldbg.cpp",
             0x1Eu,
             "IrtlTrace",
             "%ls",
             (char)Buffer);
  return result;
}

```

## disassembly

```asm
0x180012ea0  mov     rax, rsp
0x180012ea3  mov     [rax+8], rcx
0x180012ea7  mov     [rax+10h], rdx
0x180012eab  mov     [rax+18h], r8
0x180012eaf  mov     [rax+20h], r9
0x180012eb3  mov     eax, 1058h
0x180012eb8  call    _alloca_probe
0x180012ebd  sub     rsp, rax
0x180012ec0  mov     rax, cs:__security_cookie
0x180012ec7  xor     rax, rsp
0x180012eca  mov     [rsp+1058h+var_18], rax
0x180012ed2  lea     rax, [rsp+1058h+arg_8]
0x180012eda  mov     [rsp+1058h+var_1028], 0
0x180012ee3  mov     r9, rcx; Format
0x180012ee6  mov     [rsp+1058h+ArgList], rax; ArgList
0x180012eeb  lea     rcx, [rsp+1058h+Buffer]; Buffer
0x180012ef0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180012ef4  mov     edx, 800h; BufferCount
0x180012ef9  call    cs:__imp__vsnwprintf_s
0x180012f00  nop     dword ptr [rax+rax+00h]
0x180012f05  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012f0c  jz      short loc_180012F44
0x180012f0e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180012f15  lea     rax, [rsp+1058h+Buffer]
0x180012f1a  mov     qword ptr [rsp+1058h+var_1030], rax; char
0x180012f1f  lea     r9, aIrtltrace_0; "IrtlTrace"
0x180012f26  lea     rax, aLs; "%ls"
0x180012f2d  mov     r8d, 1Eh; unsigned int
0x180012f33  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012f3a  mov     [rsp+1058h+ArgList], rax; char *
0x180012f3f  call    PuDbgPrint
0x180012f44  mov     rcx, [rsp+1058h+var_18]
0x180012f4c  xor     rcx, rsp; StackCookie
0x180012f4f  call    __security_check_cookie
0x180012f54  add     rsp, 1058h
0x180012f5b  retn
```
