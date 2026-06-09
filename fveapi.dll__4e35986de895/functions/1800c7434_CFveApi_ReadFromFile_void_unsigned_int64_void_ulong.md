# CFveApi::ReadFromFile(void *,unsigned __int64,void *,ulong)

- ea: `0x1800c7434`
- end: `0x1800c74e5`
- name: `?ReadFromFile@CFveApi@@AEAAJPEAX_K0K@Z`
- size: `177`
- prototype: `int(CFveApi *__hidden this, void *, unsigned __int64, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800c74f0`

## callees

- `0x1800c7434`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74a9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7499`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c7499`

## pseudocode

```c
int __fastcall CFveApi::ReadFromFile(CFveApi *this, void *a2, void *a3, void *a4, DWORD nNumberOfBytesToRead)
{
  int result; // eax
  struct _OVERLAPPED v6; // [rsp+30h] [rbp-38h] BYREF
  DWORD v7; // [rsp+50h] [rbp-18h] BYREF

  v6.Pointer = a3;
  v6.Internal = 0;
  v6.InternalHigh = 0;
  v7 = 0;
  v6.hEvent = 0;
  if ( ReadFile(a2, a4, nNumberOfBytesToRead, &v7, &v6) )
  {
    result = 0;
    if ( v7 != nNumberOfBytesToRead )
      return -2147467259;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800c7434  mov     r11, rsp
0x1800c7437  push    rbx
0x1800c7438  sub     rsp, 60h
0x1800c743c  mov     rax, cs:__security_cookie
0x1800c7443  xor     rax, rsp
0x1800c7446  mov     [rsp+68h+var_10], rax
0x1800c744b  mov     ebx, [rsp+68h+nNumberOfBytesToRead]
0x1800c7452  lea     rcx, [r11-38h]
0x1800c7456  mov     [r11-28h], r8d
0x1800c745a  mov     r10, r9
0x1800c745d  shr     r8, 20h
0x1800c7461  lea     r9, [r11-18h]; lpNumberOfBytesRead
0x1800c7465  mov     rax, rdx
0x1800c7468  mov     [r11-24h], r8d
0x1800c746c  mov     [r11-48h], rcx
0x1800c7470  mov     r8d, ebx; nNumberOfBytesToRead
0x1800c7473  mov     rdx, r10; lpBuffer
0x1800c7476  mov     qword ptr [r11-38h], 0
0x1800c747e  mov     rcx, rax; hFile
0x1800c7481  mov     qword ptr [r11-30h], 0
0x1800c7489  mov     [rsp+68h+var_18], 0
0x1800c7491  mov     qword ptr [r11-20h], 0
0x1800c7499  call    cs:__imp_ReadFile
0x1800c74a0  nop     dword ptr [rax+rax+00h]
0x1800c74a5  test    eax, eax
0x1800c74a7  jnz     short loc_1800C74C3
0x1800c74a9  call    cs:__imp_GetLastError
0x1800c74b0  nop     dword ptr [rax+rax+00h]
0x1800c74b5  test    eax, eax
0x1800c74b7  jle     short loc_1800C74D1
0x1800c74b9  movzx   eax, ax
0x1800c74bc  or      eax, 80070000h
0x1800c74c1  jmp     short loc_1800C74D1
0x1800c74c3  xor     eax, eax
0x1800c74c5  mov     ecx, 80004005h
0x1800c74ca  cmp     [rsp+68h+var_18], ebx
0x1800c74ce  cmovnz  eax, ecx
0x1800c74d1  mov     rcx, [rsp+68h+var_10]
0x1800c74d6  xor     rcx, rsp; StackCookie
0x1800c74d9  call    __security_check_cookie
0x1800c74de  add     rsp, 60h
0x1800c74e2  pop     rbx
0x1800c74e3  retn
```
