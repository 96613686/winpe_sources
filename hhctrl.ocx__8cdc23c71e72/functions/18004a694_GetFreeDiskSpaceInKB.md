# GetFreeDiskSpaceInKB

- ea: `0x18004a694`
- end: `0x18004a7c8`
- name: `GetFreeDiskSpaceInKB`
- size: `308`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004af3c`

## callees

- `0x18004a694`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetFullPathNameA` at `0x18004a6e9`
- `KERNEL32!GetFullPathNameA` at `0x18004a6e9`
- `KERNEL32!GetDiskFreeSpaceExA` at `0x18004a785`
- `KERNEL32!GetDiskFreeSpaceExA` at `0x18004a785`
- `USER32!CharNextA` at `0x18004a714`
- `USER32!CharNextA` at `0x18004a735`
- `USER32!CharNextA` at `0x18004a748`
- `USER32!CharNextA` at `0x18004a714`
- `USER32!CharNextA` at `0x18004a735`
- `USER32!CharNextA` at `0x18004a748`

## pseudocode

```c
unsigned __int64 __fastcall GetFreeDiskSpaceInKB(LPCSTR lpFileName)
{
  CHAR v2; // cl
  CHAR *p_Buffer; // rax
  bool v4; // zf
  const CHAR *v5; // rcx
  LPSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+28h] [rbp-D8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+30h] [rbp-D0h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+38h] [rbp-C8h] BYREF
  __int16 Buffer; // [rsp+40h] [rbp-C0h] BYREF
  CHAR sz[270]; // [rsp+42h] [rbp-BEh] BYREF

  LOBYTE(Buffer) = 0;
  memset_0((char *)&Buffer + 1, 0, 0x103u);
  FilePart = 0;
  GetFullPathNameA(lpFileName, 0x104u, (LPSTR)&Buffer, &FilePart);
  if ( Buffer != 23644 )
  {
    p_Buffer = (CHAR *)&Buffer;
    goto LABEL_10;
  }
  v2 = sz[0];
  p_Buffer = sz;
  FilePart = sz;
  while ( v2 )
  {
    v4 = v2 == 92;
    v5 = p_Buffer;
    if ( v4 )
      goto LABEL_9;
    p_Buffer = CharNextA(p_Buffer);
    FilePart = p_Buffer;
    v2 = *p_Buffer;
  }
  while ( *p_Buffer )
  {
    v5 = p_Buffer;
    if ( *p_Buffer == 92 )
    {
      FilePart = CharNextA(p_Buffer);
      *FilePart = 0;
      break;
    }
LABEL_9:
    p_Buffer = CharNextA(v5);
LABEL_10:
    FilePart = p_Buffer;
  }
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !GetDiskFreeSpaceExA((LPCSTR)&Buffer, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
    return 0xFFFFFFFFLL;
  if ( TotalNumberOfFreeBytes.HighPart )
    return 0x7FFFFFFF;
  return (unsigned __int64)TotalNumberOfFreeBytes.LowPart >> 10;
}

```

## disassembly

```asm
0x18004a694  mov     [rsp-8+arg_8], rbx
0x18004a699  push    rbp
0x18004a69a  lea     rbp, [rsp-60h]
0x18004a69f  sub     rsp, 160h
0x18004a6a6  mov     rax, cs:__security_cookie
0x18004a6ad  xor     rax, rsp
0x18004a6b0  mov     [rbp+60h+var_10], rax
0x18004a6b4  mov     rbx, rcx
0x18004a6b7  mov     byte ptr [rsp+160h+Buffer], 0
0x18004a6bc  lea     rcx, [rsp+160h+Buffer+1]; void *
0x18004a6c1  xor     edx, edx; Val
0x18004a6c3  mov     r8d, 103h; Size
0x18004a6c9  call    memset_0
0x18004a6ce  lea     r9, [rsp+160h+FilePart]; lpFilePart
0x18004a6d3  mov     [rsp+160h+FilePart], 0
0x18004a6dc  lea     r8, [rsp+160h+Buffer]; lpBuffer
0x18004a6e1  mov     edx, 104h; nBufferLength
0x18004a6e6  mov     rcx, rbx; lpFileName
0x18004a6e9  call    cs:__imp_GetFullPathNameA
0x18004a6ef  mov     bl, 5Ch ; '\'
0x18004a6f1  cmp     byte ptr [rsp+160h+Buffer], bl
0x18004a6f5  jnz     short loc_18004A727
0x18004a6f7  cmp     byte ptr [rsp+160h+Buffer+1], bl
0x18004a6fb  jnz     short loc_18004A727
0x18004a6fd  mov     cl, [rsp+160h+sz]
0x18004a701  lea     rax, [rsp+160h+sz]
0x18004a706  mov     [rsp+160h+FilePart], rax
0x18004a70b  jmp     short loc_18004A721
0x18004a70d  cmp     cl, bl
0x18004a70f  mov     rcx, rax; lpsz
0x18004a712  jz      short loc_18004A735
0x18004a714  call    cs:__imp_CharNextA
0x18004a71a  mov     [rsp+160h+FilePart], rax
0x18004a71f  mov     cl, [rax]
0x18004a721  test    cl, cl
0x18004a723  jnz     short loc_18004A70D
0x18004a725  jmp     short loc_18004A740
0x18004a727  lea     rax, [rsp+160h+Buffer]
0x18004a72c  jmp     short loc_18004A73B
0x18004a72e  cmp     cl, bl
0x18004a730  mov     rcx, rax; lpsz
0x18004a733  jz      short loc_18004A748
0x18004a735  call    cs:__imp_CharNextA
0x18004a73b  mov     [rsp+160h+FilePart], rax
0x18004a740  mov     cl, [rax]
0x18004a742  test    cl, cl
0x18004a744  jnz     short loc_18004A72E
0x18004a746  jmp     short loc_18004A756
0x18004a748  call    cs:__imp_CharNextA
0x18004a74e  mov     [rsp+160h+FilePart], rax
0x18004a753  mov     byte ptr [rax], 0
0x18004a756  lea     r9, [rsp+160h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18004a75b  mov     qword ptr [rsp+160h+FreeBytesAvailableToCaller], 0
0x18004a764  lea     r8, [rsp+160h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18004a769  mov     qword ptr [rsp+160h+TotalNumberOfBytes], 0
0x18004a772  lea     rdx, [rsp+160h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18004a777  mov     qword ptr [rsp+160h+TotalNumberOfFreeBytes], 0
0x18004a780  lea     rcx, [rsp+160h+Buffer]; lpDirectoryName
0x18004a785  call    cs:__imp_GetDiskFreeSpaceExA
0x18004a78b  test    eax, eax
0x18004a78d  jnz     short loc_18004A794
0x18004a78f  or      eax, 0FFFFFFFFh
0x18004a792  jmp     short loc_18004A7AB
0x18004a794  cmp     dword ptr [rsp+160h+TotalNumberOfFreeBytes+4], 0
0x18004a799  jbe     short loc_18004A7A2
0x18004a79b  mov     eax, 7FFFFFFFh
0x18004a7a0  jmp     short loc_18004A7AB
0x18004a7a2  mov     rax, qword ptr [rsp+160h+TotalNumberOfFreeBytes]
0x18004a7a7  shr     rax, 0Ah
0x18004a7ab  mov     rcx, [rbp+60h+var_10]
0x18004a7af  xor     rcx, rsp; StackCookie
0x18004a7b2  call    __security_check_cookie
0x18004a7b7  mov     rbx, [rsp+160h+arg_8]
0x18004a7bf  add     rsp, 160h
0x18004a7c6  pop     rbp
0x18004a7c7  retn
```
