# AccessRegistryKeyMapped

- ea: `0x180057560`
- end: `0x1800575ea`
- name: `AccessRegistryKeyMapped`
- size: `138`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800577c8`

## callees

- `0x1800574a0`
- `0x180057560`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800575a7`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800575a7`

## string_xrefs

- `0x18005758f`: `\Registry\Machine\SYSTEM\RNG`

## pseudocode

```c
_BOOL8 AccessRegistryKeyMapped()
{
  WCHAR SourceString[128]; // [rsp+40h] [rbp-118h] BYREF

  return (int)RtlGetPersistedStateLocation(L"CngRng", 0, L"\\Registry\\Machine\\SYSTEM\\RNG", 0, SourceString, 256, 0) >= 0
      && AccessRegistryKey(SourceString, 0xF003Fu, &KeyHandle);
}

```

## disassembly

```asm
0x180057560  sub     rsp, 158h
0x180057567  mov     rax, cs:__security_cookie
0x18005756e  xor     rax, rsp
0x180057571  mov     [rsp+158h+var_18], rax
0x180057579  mov     [rsp+158h+var_128], 0
0x180057582  lea     rax, [rsp+158h+SourceString]
0x180057587  mov     [rsp+158h+var_130], 100h
0x18005758f  lea     r8, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x180057596  xor     r9d, r9d
0x180057599  mov     [rsp+158h+var_138], rax
0x18005759e  xor     edx, edx
0x1800575a0  lea     rcx, aCngrng; "CngRng"
0x1800575a7  call    cs:__imp_RtlGetPersistedStateLocation
0x1800575ae  nop     dword ptr [rax+rax+00h]
0x1800575b3  test    eax, eax
0x1800575b5  jns     short loc_1800575BB
0x1800575b7  xor     eax, eax
0x1800575b9  jmp     short loc_1800575D1
0x1800575bb  lea     r8, KeyHandle; KeyHandle
0x1800575c2  mov     edx, 0F003Fh; DesiredAccess
0x1800575c7  lea     rcx, [rsp+158h+SourceString]; SourceString
0x1800575cc  call    AccessRegistryKey
0x1800575d1  mov     rcx, [rsp+158h+var_18]
0x1800575d9  xor     rcx, rsp; StackCookie
0x1800575dc  call    __security_check_cookie
0x1800575e1  add     rsp, 158h
0x1800575e8  retn
```
