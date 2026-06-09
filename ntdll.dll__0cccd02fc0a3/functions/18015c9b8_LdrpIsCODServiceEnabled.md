# LdrpIsCODServiceEnabled

- ea: `0x18015c9b8`
- end: `0x18015ca3f`
- name: `LdrpIsCODServiceEnabled`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d90dc`

## callees

- `0x18015c9b8`
- `0x18015e4b0`
- `0x180160820`

## string_xrefs

- `0x18015c9d7`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant\`

## pseudocode

```c
bool LdrpIsCODServiceEnabled()
{
  bool v0; // bl
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v3[4]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v4; // [rsp+50h] [rbp-10h]
  HANDLE Handle; // [rsp+70h] [rbp+10h] BYREF

  v3[0] = 48;
  Handle = 0;
  v3[3] = 64;
  v2[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant\\";
  v2[0] = 13500620;
  v3[2] = v2;
  v3[1] = 0;
  v4 = 0;
  v0 = (int)NtOpenKeyEx(&Handle, 131353, v3, 0) >= 0;
  if ( Handle )
    NtClose(Handle);
  return v0;
}

```

## disassembly

```asm
0x18015c9b8  mov     [rsp-8+arg_8], rbx
0x18015c9bd  push    rbp
0x18015c9be  mov     rbp, rsp
0x18015c9c1  sub     rsp, 60h
0x18015c9c5  xor     eax, eax
0x18015c9c7  mov     [rbp+var_30], 30h ; '0'
0x18015c9cf  mov     [rbp+Handle], rax
0x18015c9d3  lea     r8, [rbp+var_30]
0x18015c9d7  lea     rax, aRegistryMachin_22; "\\Registry\\Machine\\Software\\Microsof"...
0x18015c9de  mov     [rbp+var_18], 40h ; '@'
0x18015c9e6  mov     [rbp+var_38], rax
0x18015c9ea  lea     rcx, [rbp+Handle]
0x18015c9ee  lea     rax, [rbp+var_40]
0x18015c9f2  mov     [rbp+var_40], 0CE00CCh
0x18015c9fa  xorps   xmm0, xmm0
0x18015c9fd  mov     [rbp+var_20], rax
0x18015ca01  xor     r9d, r9d
0x18015ca04  mov     [rbp+var_28], 0
0x18015ca0c  mov     edx, 20119h
0x18015ca11  movdqu  [rbp+var_10], xmm0
0x18015ca16  call    NtOpenKeyEx
0x18015ca1b  mov     rcx, [rbp+Handle]; Handle
0x18015ca1f  mov     ebx, eax
0x18015ca21  shr     ebx, 1Fh
0x18015ca24  xor     bl, 1
0x18015ca27  test    rcx, rcx
0x18015ca2a  jz      short loc_18015CA31
0x18015ca2c  call    NtClose
0x18015ca31  mov     al, bl
0x18015ca33  mov     rbx, [rsp+60h+arg_8]
0x18015ca38  add     rsp, 60h
0x18015ca3c  pop     rbp
0x18015ca3d  retn
```
