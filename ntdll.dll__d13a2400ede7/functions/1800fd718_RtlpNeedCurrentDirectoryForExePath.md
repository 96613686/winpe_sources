# RtlpNeedCurrentDirectoryForExePath

- ea: `0x1800fd718`
- end: `0x1800fd76e`
- name: `RtlpNeedCurrentDirectoryForExePath`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800fd6c0`

## callees

- `0x18009a6b0`
- `0x1800fd718`
- `0x18012d210`

## string_xrefs

- `0x1800fd749`: `NoDefaultCurrentDirectoryInExePath`

## pseudocode

```c
bool __fastcall RtlpNeedCurrentDirectoryForExePath(const wchar_t *a1)
{
  return wcschr(a1, 0x5Cu)
      || (unsigned int)RtlQueryEnvironmentVariable(0, L"NoDefaultCurrentDirectoryInExePath", 34) == -1073741568;
}

```

## disassembly

```asm
0x1800fd718  sub     rsp, 38h
0x1800fd71c  mov     edx, 5Ch ; '\'; Ch
0x1800fd721  mov     [rsp+38h+arg_8], 0
0x1800fd72a  call    wcschr
0x1800fd72f  test    rax, rax
0x1800fd732  jz      short loc_1800FD73C
0x1800fd734  mov     al, 1
0x1800fd736  add     rsp, 38h
0x1800fd73a  retn
0x1800fd73c  xor     r9d, r9d
0x1800fd73f  lea     rax, [rsp+38h+arg_8]
0x1800fd744  mov     [rsp+38h+var_10], rax
0x1800fd749  lea     rdx, aNodefaultcurre; "NoDefaultCurrentDirectoryInExePath"
0x1800fd750  xor     ecx, ecx
0x1800fd752  mov     [rsp+38h+var_18], 0
0x1800fd75b  lea     r8d, [r9+22h]
0x1800fd75f  call    RtlQueryEnvironmentVariable
0x1800fd764  cmp     eax, 0C0000100h
0x1800fd769  setz    al
0x1800fd76c  jmp     short loc_1800FD736
```
