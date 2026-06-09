# RemoveFontResourceTracking

- ea: `0x18007e620`
- end: `0x18007e6f6`
- name: `RemoveFontResourceTracking`
- size: `214`
- prototype: `__int64 __fastcall(CHAR *MultiByteString)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800394e0`
- `0x180039f54`
- `0x18007ac50`
- `0x18007ba24`
- `0x18007e560`
- `0x18007e620`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007e662`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18007e662`
- `GDI32!RemoveFontResourceW` at `0x18007e689`
- `GDI32!RemoveFontResourceW` at `0x18007e689`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007e67e`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18007e67e`

## pseudocode

```c
BOOL __fastcall RemoveFontResourceTracking(CHAR *MultiByteString, unsigned int a2)
{
  int v4; // eax
  BOOL result; // eax
  BOOL v6; // ebx
  LPWSTR FilePart; // [rsp+30h] [rbp-448h] BYREF
  WCHAR UnicodeString[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-228h] BYREF

  FilePart = 0;
  memset_0(UnicodeString, 0, 0x208u);
  v4 = lstrlenA(MultiByteString);
  RtlMultiByteToUnicodeN(UnicodeString, 0x208u, 0, MultiByteString, v4 + 1);
  result = RemoveFontResourceW(UnicodeString);
  v6 = result;
  if ( result )
  {
    if ( bMakePathNameW(Buffer, UnicodeString, &FilePart, 0) && !(unsigned int)bFileIsOnTheHardDrive(Buffer) )
      RemoveFontResourceEntry(a2, Buffer);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18007e620  mov     [rsp+arg_8], rbx
0x18007e625  push    rdi
0x18007e626  sub     rsp, 470h
0x18007e62d  mov     rax, cs:__security_cookie
0x18007e634  xor     rax, rsp
0x18007e637  mov     [rsp+478h+var_18], rax
0x18007e63f  mov     edi, edx
0x18007e641  mov     [rsp+478h+FilePart], 0
0x18007e64a  mov     rbx, rcx
0x18007e64d  xor     edx, edx; Val
0x18007e64f  lea     rcx, [rsp+478h+UnicodeString]; void *
0x18007e654  mov     r8d, 208h; Size
0x18007e65a  call    memset_0
0x18007e65f  mov     rcx, rbx; lpString
0x18007e662  call    cs:__imp_lstrlenA
0x18007e668  mov     r9, rbx; MultiByteString
0x18007e66b  lea     rcx, [rsp+478h+UnicodeString]; UnicodeString
0x18007e670  inc     eax
0x18007e672  xor     r8d, r8d; BytesInUnicodeString
0x18007e675  mov     edx, 208h; MaxBytesInUnicodeString
0x18007e67a  mov     [rsp+478h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18007e67e  call    cs:__imp_RtlMultiByteToUnicodeN
0x18007e684  lea     rcx, [rsp+478h+UnicodeString]; lpFileName
0x18007e689  call    cs:__imp_RemoveFontResourceW
0x18007e68f  mov     ebx, eax
0x18007e691  test    eax, eax
0x18007e693  jz      short loc_18007E6D5
0x18007e695  xor     r9d, r9d
0x18007e698  lea     r8, [rsp+478h+FilePart]; lpFilePart
0x18007e69d  lea     rdx, [rsp+478h+UnicodeString]; lpFileName
0x18007e6a2  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x18007e6aa  call    bMakePathNameW
0x18007e6af  test    eax, eax
0x18007e6b1  jz      short loc_18007E6D3
0x18007e6b3  lea     rcx, [rsp+478h+Buffer]
0x18007e6bb  call    bFileIsOnTheHardDrive
0x18007e6c0  test    eax, eax
0x18007e6c2  jnz     short loc_18007E6D3
0x18007e6c4  lea     rdx, [rsp+478h+Buffer]
0x18007e6cc  mov     ecx, edi
0x18007e6ce  call    RemoveFontResourceEntry
0x18007e6d3  mov     eax, ebx
0x18007e6d5  mov     rcx, [rsp+478h+var_18]
0x18007e6dd  xor     rcx, rsp; StackCookie
0x18007e6e0  call    __security_check_cookie
0x18007e6e5  mov     rbx, [rsp+478h+arg_8]
0x18007e6ed  add     rsp, 470h
0x18007e6f4  pop     rdi
0x18007e6f5  retn
```
