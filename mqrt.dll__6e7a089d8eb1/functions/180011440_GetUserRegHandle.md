# GetUserRegHandle

- ea: `0x180011440`
- end: `0x1800114b8`
- name: `GetUserRegHandle`
- size: `120`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800113d8`
- `0x180011b8c`
- `0x18001275c`

## callees

- `0x180011440`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18001149b`
- `ADVAPI32!RegCreateKeyExW` at `0x18001149b`

## pseudocode

```c
__int64 GetUserRegHandle()
{
  DWORD v1; // [rsp+60h] [rbp+8h] BYREF

  if ( !byte_18003DAFC )
  {
    v1 = 0;
    byte_18003DAFC = RegCreateKeyExW(
                       HKEY_CURRENT_USER,
                       L"SOFTWARE\\Microsoft\\MSMQ",
                       0,
                       (LPWSTR)&Class,
                       0,
                       0xF003Fu,
                       0,
                       (PHKEY)&qword_18003D178,
                       &v1) == 0;
  }
  return qword_18003D178;
}

```

## disassembly

```asm
0x180011440  mov     r11, rsp
0x180011443  sub     rsp, 58h
0x180011447  cmp     cs:byte_18003DAFC, 0
0x18001144e  jnz     short loc_1800114AC
0x180011450  lea     rax, [r11+8]
0x180011454  mov     [rsp+58h+arg_0], 0
0x18001145c  mov     [r11-18h], rax
0x180011460  lea     r9, Class; lpClass
0x180011467  lea     rax, qword_18003D178
0x18001146e  xor     r8d, r8d; Reserved
0x180011471  mov     [r11-20h], rax
0x180011475  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ"
0x18001147c  mov     qword ptr [r11-28h], 0
0x180011484  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001148b  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180011493  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001149b  call    cs:__imp_RegCreateKeyExW
0x1800114a1  test    eax, eax
0x1800114a3  jnz     short loc_1800114AC
0x1800114a5  mov     cs:byte_18003DAFC, 1
0x1800114ac  mov     rax, cs:qword_18003D178
0x1800114b3  add     rsp, 58h
0x1800114b7  retn
```
