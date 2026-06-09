# RemoveFontResourceTracking

- ea: `0x180083320`
- end: `0x180083409`
- name: `RemoveFontResourceTracking`
- size: `233`
- prototype: `__int64 __fastcall(CHAR *MultiByteString)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180044f30`
- `0x180045a00`
- `0x18007f800`
- `0x180080604`
- `0x180083250`
- `0x180083320`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180083362`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180083362`
- `GDI32!RemoveFontResourceW` at `0x180083395`
- `GDI32!RemoveFontResourceW` at `0x180083395`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180083384`
- `ntdll!RtlMultiByteToUnicodeN` at `0x180083384`

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
0x180083320  mov     [rsp+arg_8], rbx
0x180083325  push    rdi
0x180083326  sub     rsp, 470h
0x18008332d  mov     rax, cs:__security_cookie
0x180083334  xor     rax, rsp
0x180083337  mov     [rsp+478h+var_18], rax
0x18008333f  mov     edi, edx
0x180083341  mov     [rsp+478h+FilePart], 0
0x18008334a  mov     rbx, rcx
0x18008334d  xor     edx, edx; Val
0x18008334f  lea     rcx, [rsp+478h+UnicodeString]; void *
0x180083354  mov     r8d, 208h; Size
0x18008335a  call    memset_0
0x18008335f  mov     rcx, rbx; lpString
0x180083362  call    cs:__imp_lstrlenA
0x180083369  nop     dword ptr [rax+rax+00h]
0x18008336e  mov     r9, rbx; MultiByteString
0x180083371  lea     rcx, [rsp+478h+UnicodeString]; UnicodeString
0x180083376  inc     eax
0x180083378  xor     r8d, r8d; BytesInUnicodeString
0x18008337b  mov     edx, 208h; MaxBytesInUnicodeString
0x180083380  mov     [rsp+478h+BytesInMultiByteString], eax; BytesInMultiByteString
0x180083384  call    cs:__imp_RtlMultiByteToUnicodeN
0x18008338b  nop     dword ptr [rax+rax+00h]
0x180083390  lea     rcx, [rsp+478h+UnicodeString]; lpFileName
0x180083395  call    cs:__imp_RemoveFontResourceW
0x18008339c  nop     dword ptr [rax+rax+00h]
0x1800833a1  mov     ebx, eax
0x1800833a3  test    eax, eax
0x1800833a5  jz      short loc_1800833E7
0x1800833a7  xor     r9d, r9d
0x1800833aa  lea     r8, [rsp+478h+FilePart]; lpFilePart
0x1800833af  lea     rdx, [rsp+478h+UnicodeString]; lpFileName
0x1800833b4  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x1800833bc  call    bMakePathNameW
0x1800833c1  test    eax, eax
0x1800833c3  jz      short loc_1800833E5
0x1800833c5  lea     rcx, [rsp+478h+Buffer]
0x1800833cd  call    bFileIsOnTheHardDrive
0x1800833d2  test    eax, eax
0x1800833d4  jnz     short loc_1800833E5
0x1800833d6  lea     rdx, [rsp+478h+Buffer]
0x1800833de  mov     ecx, edi
0x1800833e0  call    RemoveFontResourceEntry
0x1800833e5  mov     eax, ebx
0x1800833e7  mov     rcx, [rsp+478h+var_18]
0x1800833ef  xor     rcx, rsp; StackCookie
0x1800833f2  call    __security_check_cookie
0x1800833f7  mov     rbx, [rsp+478h+arg_8]
0x1800833ff  add     rsp, 470h
0x180083406  pop     rdi
0x180083407  retn
```
