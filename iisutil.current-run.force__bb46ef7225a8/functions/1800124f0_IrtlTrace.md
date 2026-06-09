# IrtlTrace

- ea: `0x1800124f0`
- end: `0x1800125a6`
- name: `IrtlTrace`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007300`
- `0x1800124f0`
- `0x18002c4c0`
- `0x18002c550`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x180012549`
- `msvcrt!_vsnwprintf_s` at `0x180012549`

## string_xrefs

- `0x18001257d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\irtldbg.cpp`

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
0x1800124f0  mov     rax, rsp
0x1800124f3  mov     [rax+8], rcx
0x1800124f7  mov     [rax+10h], rdx
0x1800124fb  mov     [rax+18h], r8
0x1800124ff  mov     [rax+20h], r9
0x180012503  mov     eax, 1058h
0x180012508  call    _alloca_probe
0x18001250d  sub     rsp, rax
0x180012510  mov     rax, cs:__security_cookie
0x180012517  xor     rax, rsp
0x18001251a  mov     [rsp+1058h+var_18], rax
0x180012522  lea     rax, [rsp+1058h+arg_8]
0x18001252a  mov     [rsp+1058h+var_1028], 0
0x180012533  mov     r9, rcx; Format
0x180012536  mov     [rsp+1058h+ArgList], rax; ArgList
0x18001253b  lea     rcx, [rsp+1058h+Buffer]; Buffer
0x180012540  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180012544  mov     edx, 800h; BufferCount
0x180012549  call    cs:__imp__vsnwprintf_s
0x18001254f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180012556  jz      short loc_18001258E
0x180012558  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001255f  lea     rax, [rsp+1058h+Buffer]
0x180012564  mov     qword ptr [rsp+1058h+var_1030], rax; char
0x180012569  lea     r9, aIrtltrace_0; "IrtlTrace"
0x180012570  lea     rax, aLs; "%ls"
0x180012577  mov     r8d, 1Eh; unsigned int
0x18001257d  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012584  mov     [rsp+1058h+ArgList], rax; char *
0x180012589  call    PuDbgPrint
0x18001258e  mov     rcx, [rsp+1058h+var_18]
0x180012596  xor     rcx, rsp; StackCookie
0x180012599  call    __security_check_cookie
0x18001259e  add     rsp, 1058h
0x1800125a5  retn
```
