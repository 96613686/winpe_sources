# CFileMapping::Init(ushort const *,ulong,ulong,ulong,ulong,ulong)

- ea: `0x140001edc`
- end: `0x14000204b`
- name: `?Init@CFileMapping@@QEAAJPEBGKKKKK@Z`
- size: `367`
- prototype: `__int64 __fastcall(CFileMapping *__hidden this, LPCWCH lpWideCharStr, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140001e1c`

## callees

- `0x140001edc`
- `0x140014fd4`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140001f68`
- `KERNEL32!WideCharToMultiByte` at `0x140001fe9`
- `KERNEL32!WideCharToMultiByte` at `0x140001f68`
- `KERNEL32!WideCharToMultiByte` at `0x140001fe9`
- `KERNEL32!GetLastError` at `0x140001f75`
- `KERNEL32!GetLastError` at `0x140001f75`
- `KERNEL32!CreateFileA` at `0x14000201b`
- `KERNEL32!CreateFileA` at `0x14000201b`
- `KERNEL32!CreateFileW` at `0x140001f2f`
- `KERNEL32!CreateFileW` at `0x140001f2f`

## pseudocode

```c
signed int __fastcall CFileMapping::Init(CFileMapping *this, LPCWCH lpWideCharStr)
{
  HANDLE FileW; // rax
  unsigned int v5; // r8d
  int v6; // eax
  signed int result; // eax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  CHAR MultiByteStr[48]; // [rsp+40h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    FileW = CreateFileW(lpWideCharStr, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  }
  else
  {
    v6 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v6 )
      goto LABEL_4;
    v8 = v6 + 15LL;
    if ( v8 < v6 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    if ( !MultiByteStr )
      return -2147024882;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v6, 0, 0) )
      goto LABEL_4;
    FileW = CreateFileA(MultiByteStr, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  }
  if ( FileW != (HANDLE)-1LL )
    return CFileMapping::Init(this, FileW, v5);
LABEL_4:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140001edc  push    rbp
0x140001ede  push    rbx
0x140001edf  push    rsi
0x140001ee0  push    rdi
0x140001ee1  sub     rsp, 58h
0x140001ee5  lea     rbp, [rsp+40h]
0x140001eea  mov     rax, cs:__security_cookie
0x140001ef1  xor     rax, rbp
0x140001ef4  mov     qword ptr [rbp+30h+MultiByteStr], rax
0x140001ef8  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140001eff  mov     rdi, rdx
0x140001f02  mov     rsi, rcx
0x140001f05  jz      short loc_140001F3A
0x140001f07  xor     r9d, r9d; lpSecurityAttributes
0x140001f0a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140001f13  mov     [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140001f1b  mov     edx, 80000000h; dwDesiredAccess
0x140001f20  mov     rcx, rdi; lpFileName
0x140001f23  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x140001f2b  lea     r8d, [r9+1]; dwShareMode
0x140001f2f  call    cs:__imp_CreateFileW
0x140001f35  jmp     loc_140002021
0x140001f3a  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140001f43  or      r9d, 0FFFFFFFFh; cchWideChar
0x140001f47  mov     [rsp+70h+hTemplateFile], 0; lpDefaultChar
0x140001f50  mov     r8, rdi; lpWideCharStr
0x140001f53  mov     [rsp+70h+dwFlagsAndAttributes], 0; cbMultiByte
0x140001f5b  xor     edx, edx; dwFlags
0x140001f5d  xor     ecx, ecx; CodePage
0x140001f5f  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpMultiByteStr
0x140001f68  call    cs:__imp_WideCharToMultiByte
0x140001f6e  movsxd  rdx, eax
0x140001f71  test    eax, eax
0x140001f73  jnz     short loc_140001F90
0x140001f75  call    cs:__imp_GetLastError
0x140001f7b  test    eax, eax
0x140001f7d  jle     loc_140002036
0x140001f83  movzx   eax, ax
0x140001f86  or      eax, 80070000h
0x140001f8b  jmp     loc_140002036
0x140001f90  lea     rcx, [rdx+0Fh]
0x140001f94  cmp     rcx, rdx
0x140001f97  ja      short loc_140001FA3
0x140001f99  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140001fa3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140001fa7  mov     rax, rcx
0x140001faa  call    _alloca_probe
0x140001faf  sub     rsp, rcx
0x140001fb2  lea     rbx, [rsp+70h+MultiByteStr]
0x140001fb7  test    rbx, rbx
0x140001fba  jnz     short loc_140001FC3
0x140001fbc  mov     eax, 8007000Eh
0x140001fc1  jmp     short loc_140002036
0x140001fc3  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140001fcc  or      r9d, 0FFFFFFFFh; cchWideChar
0x140001fd0  mov     [rsp+70h+hTemplateFile], 0; lpDefaultChar
0x140001fd9  mov     r8, rdi; lpWideCharStr
0x140001fdc  mov     [rsp+70h+dwFlagsAndAttributes], edx; cbMultiByte
0x140001fe0  xor     ecx, ecx; CodePage
0x140001fe2  xor     edx, edx; dwFlags
0x140001fe4  mov     qword ptr [rsp+70h+dwCreationDisposition], rbx; lpMultiByteStr
0x140001fe9  call    cs:__imp_WideCharToMultiByte
0x140001fef  test    eax, eax
0x140001ff1  jz      short loc_140001F75
0x140001ff3  xor     r9d, r9d; lpSecurityAttributes
0x140001ff6  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140001fff  mov     [rsp+70h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140002007  mov     edx, 80000000h; dwDesiredAccess
0x14000200c  mov     rcx, rbx; lpFileName
0x14000200f  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x140002017  lea     r8d, [r9+1]; dwShareMode
0x14000201b  call    cs:__imp_CreateFileA
0x140002021  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002025  jz      loc_140001F75
0x14000202b  mov     rdx, rax; void *
0x14000202e  mov     rcx, rsi; this
0x140002031  call    ?Init@CFileMapping@@QEAAJPEAXK@Z; CFileMapping::Init(void *,ulong)
0x140002036  mov     rcx, qword ptr [rbp+30h+MultiByteStr]
0x14000203a  xor     rcx, rbp; StackCookie
0x14000203d  call    __security_check_cookie
0x140002042  lea     rsp, [rbp+18h]
0x140002046  pop     rdi
0x140002047  pop     rsi
0x140002048  pop     rbx
0x140002049  pop     rbp
0x14000204a  retn
```
