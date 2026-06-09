# RtlpNeedCurrentDirectoryForExePath

- ea: `0x1800fd0f8`
- end: `0x1800fd14e`
- name: `RtlpNeedCurrentDirectoryForExePath`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800fd0a0`

## callees

- `0x18008e8e0`
- `0x1800fd0f8`
- `0x18012c720`

## string_xrefs

- `0x1800fd129`: `NoDefaultCurrentDirectoryInExePath`

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
0x1800fd0f8  sub     rsp, 38h
0x1800fd0fc  mov     edx, 5Ch ; '\'; Ch
0x1800fd101  mov     [rsp+38h+arg_8], 0
0x1800fd10a  call    wcschr
0x1800fd10f  test    rax, rax
0x1800fd112  jz      short loc_1800FD11C
0x1800fd114  mov     al, 1
0x1800fd116  add     rsp, 38h
0x1800fd11a  retn
0x1800fd11c  xor     r9d, r9d
0x1800fd11f  lea     rax, [rsp+38h+arg_8]
0x1800fd124  mov     [rsp+38h+var_10], rax
0x1800fd129  lea     rdx, aNodefaultcurre; "NoDefaultCurrentDirectoryInExePath"
0x1800fd130  xor     ecx, ecx
0x1800fd132  mov     [rsp+38h+var_18], 0
0x1800fd13b  lea     r8d, [r9+22h]
0x1800fd13f  call    RtlQueryEnvironmentVariable
0x1800fd144  cmp     eax, 0C0000100h
0x1800fd149  setz    al
0x1800fd14c  jmp     short loc_1800FD116
```
