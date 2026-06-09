# NpReadParameters

- ea: `0x14001841c`
- end: `0x1400184ab`
- name: `NpReadParameters`
- size: `143`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018080`

## callees

- `0x140002240`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018496`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018496`

## string_xrefs

- `0x14001843c`: `CompatFlags`

## pseudocode

```c
__int64 NpReadParameters()
{
  _QWORD v1[15]; // [rsp+30h] [rbp-78h] BYREF
  int v2; // [rsp+B0h] [rbp+8h] BYREF

  v2 = 0;
  memset(v1, 0, 0x70u);
  LODWORD(v1[1]) = 304;
  v1[2] = L"CompatFlags";
  LODWORD(v1[4]) = 0x4000000;
  v1[3] = &NpCompatFlags;
  LODWORD(v1[6]) = 4;
  v1[5] = &v2;
  return RtlQueryRegistryValuesEx(2147483649LL, L"Npfs\\Parameters", v1, 0, 0);
}

```

## disassembly

```asm
0x14001841c  mov     rax, rsp
0x14001841f  sub     rsp, 0A8h
0x140018426  xor     edx, edx; Val
0x140018428  mov     dword ptr [rax+8], 0
0x14001842f  lea     rcx, [rax-78h]; void *
0x140018433  lea     r8d, [rdx+70h]; Size
0x140018437  call    memset
0x14001843c  lea     rax, aCompatflags; "CompatFlags"
0x140018443  mov     [rsp+0A8h+var_70], 130h
0x14001844b  mov     [rsp+0A8h+var_68], rax
0x140018450  lea     r8, [rsp+0A8h+var_78]
0x140018455  lea     rax, NpCompatFlags
0x14001845c  mov     [rsp+0A8h+var_58], 4000000h
0x140018464  mov     [rsp+0A8h+var_60], rax
0x140018469  lea     rdx, aNpfsParameters; "Npfs\\Parameters"
0x140018470  lea     rax, [rsp+0A8h+arg_0]
0x140018478  mov     [rsp+0A8h+var_48], 4
0x140018480  xor     r9d, r9d
0x140018483  mov     [rsp+0A8h+var_50], rax
0x140018488  mov     ecx, 80000001h
0x14001848d  mov     [rsp+0A8h+var_88], 0
0x140018496  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001849d  nop     dword ptr [rax+rax+00h]
0x1400184a2  add     rsp, 0A8h
0x1400184a9  retn
```
