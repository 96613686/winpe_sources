# AccessRegistryKeyMapped

- ea: `0x180056c70`
- end: `0x180056cfa`
- name: `AccessRegistryKeyMapped`
- size: `138`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180056ed8`

## callees

- `0x180056bb0`
- `0x180056c70`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180056cb7`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180056cb7`

## string_xrefs

- `0x180056c9f`: `\Registry\Machine\SYSTEM\RNG`

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
0x180056c70  sub     rsp, 158h
0x180056c77  mov     rax, cs:__security_cookie
0x180056c7e  xor     rax, rsp
0x180056c81  mov     [rsp+158h+var_18], rax
0x180056c89  mov     [rsp+158h+var_128], 0
0x180056c92  lea     rax, [rsp+158h+SourceString]
0x180056c97  mov     [rsp+158h+var_130], 100h
0x180056c9f  lea     r8, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x180056ca6  xor     r9d, r9d
0x180056ca9  mov     [rsp+158h+var_138], rax
0x180056cae  xor     edx, edx
0x180056cb0  lea     rcx, aCngrng; "CngRng"
0x180056cb7  call    cs:__imp_RtlGetPersistedStateLocation
0x180056cbe  nop     dword ptr [rax+rax+00h]
0x180056cc3  test    eax, eax
0x180056cc5  jns     short loc_180056CCB
0x180056cc7  xor     eax, eax
0x180056cc9  jmp     short loc_180056CE1
0x180056ccb  lea     r8, KeyHandle; KeyHandle
0x180056cd2  mov     edx, 0F003Fh; DesiredAccess
0x180056cd7  lea     rcx, [rsp+158h+SourceString]; SourceString
0x180056cdc  call    AccessRegistryKey
0x180056ce1  mov     rcx, [rsp+158h+var_18]
0x180056ce9  xor     rcx, rsp; StackCookie
0x180056cec  call    __security_check_cookie
0x180056cf1  add     rsp, 158h
0x180056cf8  retn
```
