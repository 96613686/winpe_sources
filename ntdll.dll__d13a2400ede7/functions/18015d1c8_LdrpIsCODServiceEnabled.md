# LdrpIsCODServiceEnabled

- ea: `0x18015d1c8`
- end: `0x18015d24f`
- name: `LdrpIsCODServiceEnabled`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d9b5c`

## callees

- `0x18015d1c8`
- `0x18015ecc0`
- `0x180161030`

## string_xrefs

- `0x18015d1e7`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant\`

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
0x18015d1c8  mov     [rsp-8+arg_8], rbx
0x18015d1cd  push    rbp
0x18015d1ce  mov     rbp, rsp
0x18015d1d1  sub     rsp, 60h
0x18015d1d5  xor     eax, eax
0x18015d1d7  mov     [rbp+var_30], 30h ; '0'
0x18015d1df  mov     [rbp+Handle], rax
0x18015d1e3  lea     r8, [rbp+var_30]
0x18015d1e7  lea     rax, aRegistryMachin_22; "\\Registry\\Machine\\Software\\Microsof"...
0x18015d1ee  mov     [rbp+var_18], 40h ; '@'
0x18015d1f6  mov     [rbp+var_38], rax
0x18015d1fa  lea     rcx, [rbp+Handle]
0x18015d1fe  lea     rax, [rbp+var_40]
0x18015d202  mov     [rbp+var_40], 0CE00CCh
0x18015d20a  xorps   xmm0, xmm0
0x18015d20d  mov     [rbp+var_20], rax
0x18015d211  xor     r9d, r9d
0x18015d214  mov     [rbp+var_28], 0
0x18015d21c  mov     edx, 20119h
0x18015d221  movdqu  [rbp+var_10], xmm0
0x18015d226  call    NtOpenKeyEx
0x18015d22b  mov     rcx, [rbp+Handle]; Handle
0x18015d22f  mov     ebx, eax
0x18015d231  shr     ebx, 1Fh
0x18015d234  xor     bl, 1
0x18015d237  test    rcx, rcx
0x18015d23a  jz      short loc_18015D241
0x18015d23c  call    NtClose
0x18015d241  mov     al, bl
0x18015d243  mov     rbx, [rsp+60h+arg_8]
0x18015d248  add     rsp, 60h
0x18015d24c  pop     rbp
0x18015d24d  retn
```
