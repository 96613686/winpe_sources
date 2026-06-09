# lldpUpdateTxTtl

- ea: `0x140011a40`
- end: `0x140011a8e`
- name: `lldpUpdateTxTtl`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140010150`
- `0x1400114d0`
- `0x140011914`
- `0x140011aa0`

## callees

- `0x140004340`
- `0x140004444`
- `0x140011a40`

## pseudocode

```c
void __fastcall lldpUpdateTxTtl(__int64 a1)
{
  __int64 v1; // rcx
  unsigned int Config; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned __int64 v5; // r9
  unsigned int v6; // edx

  lldpGetConfig(a1, 1);
  Config = lldpGetConfig(v1, 2);
  v5 = v4 * Config;
  if ( v5 > 0xFFFFFFFF || (v6 = v5 + 1, (int)v5 + 1 < (unsigned int)v5) || v6 > 0xFFFF )
    LOWORD(v6) = -1;
  lldpSetMibTtl(v3, v6);
}

```

## disassembly

```asm
0x140011a40  sub     rsp, 28h
0x140011a44  mov     edx, 1
0x140011a49  call    lldpGetConfig
0x140011a4e  mov     edx, 2
0x140011a53  mov     r8d, eax
0x140011a56  call    lldpGetConfig
0x140011a5b  mov     r9d, eax
0x140011a5e  mov     eax, 0FFFFFFFFh
0x140011a63  imul    r9, r8
0x140011a67  mov     r8d, 0FFFFh
0x140011a6d  cmp     r9, rax
0x140011a70  ja      short loc_140011A80
0x140011a72  lea     edx, [r9+1]
0x140011a76  cmp     edx, r9d
0x140011a79  jb      short loc_140011A80
0x140011a7b  cmp     edx, r8d
0x140011a7e  jbe     short loc_140011A83
0x140011a80  mov     edx, r8d
0x140011a83  call    lldpSetMibTtl
0x140011a88  add     rsp, 28h
0x140011a8c  retn
```
