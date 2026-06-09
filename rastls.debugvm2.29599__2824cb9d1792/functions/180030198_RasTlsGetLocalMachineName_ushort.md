# RasTlsGetLocalMachineName(ushort * *)

- ea: `0x180030198`
- end: `0x180030238`
- name: `?RasTlsGetLocalMachineName@@YAKPEAPEAG@Z`
- size: `160`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002131c`
- `0x1800706d8`

## callees

- `0x180030198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800301e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800301e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030220`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030220`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800301bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003020c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800301bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003020c`

## pseudocode

```c
__int64 __fastcall RasTlsGetLocalMachineName(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize)
    || (v2 = 0, LastError = GetLastError(), LastError == 234) )
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize + 2);
    v2 = v4;
    if ( v4 && GetComputerNameExW(ComputerNameDnsFullyQualified, v4, &nSize) )
    {
      *a1 = v2;
      v2 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  LocalFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x180030198  mov     rax, rsp
0x18003019b  mov     [rax+8], rbx
0x18003019f  mov     [rax+18h], rsi
0x1800301a3  push    rdi
0x1800301a4  sub     rsp, 20h
0x1800301a8  xor     edx, edx; lpBuffer
0x1800301aa  mov     dword ptr [rax+10h], 0
0x1800301b1  mov     rsi, rcx
0x1800301b4  lea     r8, [rax+10h]; nSize
0x1800301b8  lea     ecx, [rdx+3]; NameType
0x1800301bb  call    cs:__imp_GetComputerNameExW
0x1800301c1  test    eax, eax
0x1800301c3  jnz     short loc_1800301D6
0x1800301c5  xor     edi, edi
0x1800301c7  call    cs:__imp_GetLastError
0x1800301cd  mov     ebx, eax
0x1800301cf  cmp     eax, 0EAh
0x1800301d4  jnz     short loc_18003021D
0x1800301d6  mov     edx, [rsp+28h+nSize]
0x1800301da  mov     ecx, 40h ; '@'; uFlags
0x1800301df  lea     rdx, ds:2[rdx*2]; uBytes
0x1800301e7  call    cs:__imp_LocalAlloc
0x1800301ed  mov     rdi, rax
0x1800301f0  test    rax, rax
0x1800301f3  jnz     short loc_1800301FF
0x1800301f5  call    cs:__imp_GetLastError
0x1800301fb  mov     ebx, eax
0x1800301fd  jmp     short loc_18003021D
0x1800301ff  lea     r8, [rsp+28h+nSize]; nSize
0x180030204  mov     rdx, rdi; lpBuffer
0x180030207  mov     ecx, 3; NameType
0x18003020c  call    cs:__imp_GetComputerNameExW
0x180030212  test    eax, eax
0x180030214  jz      short loc_1800301F5
0x180030216  mov     [rsi], rdi
0x180030219  xor     edi, edi
0x18003021b  xor     ebx, ebx
0x18003021d  mov     rcx, rdi; hMem
0x180030220  call    cs:__imp_LocalFree
0x180030226  mov     rsi, [rsp+28h+arg_10]
0x18003022b  mov     eax, ebx
0x18003022d  mov     rbx, [rsp+28h+arg_0]
0x180030232  add     rsp, 20h
0x180030236  pop     rdi
0x180030237  retn
```
