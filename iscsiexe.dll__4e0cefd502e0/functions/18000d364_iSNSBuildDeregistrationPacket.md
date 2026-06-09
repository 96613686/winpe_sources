# iSNSBuildDeregistrationPacket

- ea: `0x18000d364`
- end: `0x18000d427`
- name: `iSNSBuildDeregistrationPacket`
- size: `195`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c124`
- `0x18000c474`
- `0x18000d6f0`

## callees

- `0x18000cd7c`
- `0x18000d364`
- `0x18000d5c0`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x18000d414`
- `ISCSIUM!DiscpFreeMemory` at `0x18000d414`

## pseudocode

```c
__int64 __fastcall iSNSBuildDeregistrationPacket(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  DWORD EID; // edi
  int v9; // r9d
  CHAR *v10; // rbx
  unsigned int v11; // eax
  CHAR *v13; // [rsp+30h] [rbp-38h] BYREF

  v13 = 0;
  EID = DiscpGetEID(&v13);
  if ( !EID )
  {
    v9 = (unsigned __int16)TransactionID;
    v10 = v13;
    qword_1800272A8 = (__int64)v13;
    qword_180027288 = a4;
    qword_1800272B8 = a3;
    v11 = (unsigned __int16)(*(_WORD *)(a3 + 2) << 8) | *(unsigned __int8 *)(a3 + 3);
    qword_1800272D8 = a4;
    qword_1800272C8 = _byteswap_ulong(v11);
    ++TransactionID;
    EID = iSNSBuildRequestPacket(a1, 2048, 4, v9, (__int64)&DeregistrationAttrList, a5);
    DiscpFreeMemory(v10);
  }
  return EID;
}

```

## disassembly

```asm
0x18000d364  push    rbx
0x18000d366  push    rbp
0x18000d367  push    rsi
0x18000d368  push    rdi
0x18000d369  push    r14
0x18000d36b  sub     rsp, 40h
0x18000d36f  mov     r14, rcx
0x18000d372  mov     [rsp+68h+var_38], 0
0x18000d37b  lea     rcx, [rsp+68h+var_38]
0x18000d380  mov     rbp, r9
0x18000d383  mov     rsi, r8
0x18000d386  call    DiscpGetEID
0x18000d38b  mov     edi, eax
0x18000d38d  test    eax, eax
0x18000d38f  jnz     loc_18000D41A
0x18000d395  movzx   r9d, cs:TransactionID
0x18000d39d  lea     r8d, [rdi+4]
0x18000d3a1  mov     rbx, [rsp+68h+var_38]
0x18000d3a6  mov     edx, 800h
0x18000d3ab  mov     cs:qword_1800272A8, rbx
0x18000d3b2  mov     cs:qword_180027288, rbp
0x18000d3b9  mov     cs:qword_1800272B8, rsi
0x18000d3c0  movzx   eax, word ptr [rsi+2]
0x18000d3c4  shl     ax, 8
0x18000d3c8  movzx   ecx, ax
0x18000d3cb  movzx   eax, byte ptr [rsi+3]
0x18000d3cf  or      eax, ecx
0x18000d3d1  mov     cs:qword_1800272D8, rbp
0x18000d3d8  bswap   eax
0x18000d3da  mov     eax, eax
0x18000d3dc  mov     rcx, r14
0x18000d3df  mov     cs:qword_1800272C8, rax
0x18000d3e6  lea     eax, [r9+1]
0x18000d3ea  mov     cs:TransactionID, ax
0x18000d3f1  mov     rax, [rsp+68h+arg_20]
0x18000d3f9  mov     [rsp+68h+var_40], rax
0x18000d3fe  lea     rax, DeregistrationAttrList
0x18000d405  mov     [rsp+68h+var_48], rax
0x18000d40a  call    iSNSBuildRequestPacket
0x18000d40f  mov     rcx, rbx
0x18000d412  mov     edi, eax
0x18000d414  call    cs:__imp_DiscpFreeMemory
0x18000d41a  mov     eax, edi
0x18000d41c  add     rsp, 40h
0x18000d420  pop     r14
0x18000d422  pop     rdi
0x18000d423  pop     rsi
0x18000d424  pop     rbp
0x18000d425  pop     rbx
0x18000d426  retn
```
