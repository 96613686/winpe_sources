# Smb2IsTrafficCompressionActive

- ea: `0x1400191c0`
- end: `0x140019218`
- name: `Smb2IsTrafficCompressionActive`
- size: `88`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a8d0`

## callees

- `0x1400191c0`

## import_xrefs

- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x1400191c9`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x1400191c9`

## pseudocode

```c
_BOOL8 __fastcall Smb2IsTrafficCompressionActive(__int64 a1)
{
  __int64 v3; // rcx

  if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 2) != 0
    || (*(_DWORD *)(a1 + 68) & 0x4000000) == 0
    || !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL) + 592LL) )
  {
    return 0;
  }
  v3 = *(_QWORD *)(a1 + 504);
  return !v3 || *(_DWORD *)(v3 + 40) != 2;
}

```

## disassembly

```asm
0x1400191c0  push    rbx
0x1400191c2  sub     rsp, 20h
0x1400191c6  mov     rbx, rcx
0x1400191c9  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x1400191d0  nop     dword ptr [rax+rax+00h]
0x1400191d5  test    byte ptr [rax+1Ah], 2
0x1400191d9  jnz     short loc_1400191E4
0x1400191db  mov     eax, [rbx+44h]
0x1400191de  bt      eax, 1Ah
0x1400191e2  jb      short loc_1400191ED
0x1400191e4  xor     eax, eax
0x1400191e6  add     rsp, 20h
0x1400191ea  pop     rbx
0x1400191eb  retn
0x1400191ed  mov     rax, [rbx+60h]
0x1400191f1  mov     rcx, [rax+188h]
0x1400191f8  cmp     dword ptr [rcx+250h], 0
0x1400191ff  jz      short loc_1400191E4
0x140019201  mov     rcx, [rbx+1F8h]
0x140019208  test    rcx, rcx
0x14001920b  jnz     loc_14003B7E0
0x140019211  mov     eax, 1
0x140019216  jmp     short loc_1400191E6
0x14003b7e0  xor     eax, eax
0x14003b7e2  cmp     dword ptr [rcx+28h], 2
0x14003b7e6  setnz   al
0x14003b7e9  jmp     loc_1400191E6
```
