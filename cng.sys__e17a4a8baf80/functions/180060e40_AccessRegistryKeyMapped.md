# AccessRegistryKeyMapped

- ea: `0x180060e40`
- end: `0x180060eca`
- name: `AccessRegistryKeyMapped`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800610a8`

## callees

- `0x180060d80`
- `0x180060e40`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180060e87`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180060e87`

## string_xrefs

- `0x180060e6f`: `\Registry\Machine\SYSTEM\RNG`

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
0x180060e40  sub     rsp, 158h
0x180060e47  mov     rax, cs:__security_cookie
0x180060e4e  xor     rax, rsp
0x180060e51  mov     [rsp+158h+var_18], rax
0x180060e59  mov     [rsp+158h+var_128], 0
0x180060e62  lea     rax, [rsp+158h+SourceString]
0x180060e67  mov     [rsp+158h+var_130], 100h
0x180060e6f  lea     r8, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\RNG"
0x180060e76  xor     r9d, r9d
0x180060e79  mov     [rsp+158h+var_138], rax
0x180060e7e  xor     edx, edx
0x180060e80  lea     rcx, aCngrng; "CngRng"
0x180060e87  call    cs:__imp_RtlGetPersistedStateLocation
0x180060e8e  nop     dword ptr [rax+rax+00h]
0x180060e93  test    eax, eax
0x180060e95  jns     short loc_180060E9B
0x180060e97  xor     eax, eax
0x180060e99  jmp     short loc_180060EB1
0x180060e9b  lea     r8, KeyHandle; KeyHandle
0x180060ea2  mov     edx, 0F003Fh; DesiredAccess
0x180060ea7  lea     rcx, [rsp+158h+SourceString]; SourceString
0x180060eac  call    AccessRegistryKey
0x180060eb1  mov     rcx, [rsp+158h+var_18]
0x180060eb9  xor     rcx, rsp; StackCookie
0x180060ebc  call    __security_check_cookie
0x180060ec1  add     rsp, 158h
0x180060ec8  retn
```
