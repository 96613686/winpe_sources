# MibGetNextVar

- ea: `0x180001b5c`
- end: `0x180001bf9`
- name: `MibGetNextVar`
- size: `157`
- prototype: `__int64 __fastcall(AsnObjectIdentifier *pOidDst, unsigned __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c00`
- `0x180001dd4`

## callees

- `0x180001b5c`
- `0x180004010`

## import_xrefs

- `snmpapi!SnmpUtilOidCpy` at `0x180001ba2`
- `snmpapi!SnmpUtilOidCpy` at `0x180001ba2`
- `snmpapi!SnmpUtilOidFree` at `0x180001b96`
- `snmpapi!SnmpUtilOidFree` at `0x180001b96`
- `snmpapi!SnmpUtilOidAppend` at `0x180001bae`
- `snmpapi!SnmpUtilOidAppend` at `0x180001bae`

## pseudocode

```c
__int64 __fastcall MibGetNextVar(AsnObjectIdentifier *pOidDst, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v6; // rcx
  unsigned int v8; // r14d
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rbp
  unsigned int (__fastcall *v11)(AsnObjectIdentifier *, __int64, unsigned __int64, __int64, __int64); // rax

  v6 = *(_QWORD *)(a3 + 16);
  v8 = 2;
  if ( a2 >= v6 )
  {
    v9 = a2 + 40;
    v10 = v6 + 40LL * *(int *)(a3 + 8);
    while ( v9 < v10 )
    {
      SnmpUtilOidFree(pOidDst);
      SnmpUtilOidCpy(pOidDst, *(AsnObjectIdentifier **)a3);
      SnmpUtilOidAppend(pOidDst, (AsnObjectIdentifier *)v9);
      v11 = *(unsigned int (__fastcall **)(AsnObjectIdentifier *, __int64, unsigned __int64, __int64, __int64))(v9 + 24);
      if ( v11 && *(_BYTE *)(v9 + 32) != 68 )
        return v11(pOidDst, 224, v9, a3, a4);
      v9 += 40LL;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180001b5c  push    rbx
0x180001b5e  push    rbp
0x180001b5f  push    rsi
0x180001b60  push    rdi
0x180001b61  push    r14
0x180001b63  push    r15
0x180001b65  sub     rsp, 38h
0x180001b69  mov     rsi, rcx
0x180001b6c  mov     r15, r9
0x180001b6f  mov     rcx, [r8+10h]
0x180001b73  mov     rdi, r8
0x180001b76  mov     r14d, 2
0x180001b7c  cmp     rdx, rcx
0x180001b7f  jb      short loc_180001BE9
0x180001b81  movsxd  rax, dword ptr [r8+8]
0x180001b85  lea     rbx, [rdx+28h]
0x180001b89  lea     r10, [rax+rax*4]
0x180001b8d  lea     rbp, [rcx+r10*8]
0x180001b91  jmp     short loc_180001BC7
0x180001b93  mov     rcx, rsi; pOid
0x180001b96  call    cs:__imp_SnmpUtilOidFree
0x180001b9c  mov     rdx, [rdi]; pOidSrc
0x180001b9f  mov     rcx, rsi; pOidDst
0x180001ba2  call    cs:__imp_SnmpUtilOidCpy
0x180001ba8  mov     rdx, rbx; pOidSrc
0x180001bab  mov     rcx, rsi; pOidDst
0x180001bae  call    cs:__imp_SnmpUtilOidAppend
0x180001bb4  mov     rax, [rbx+18h]
0x180001bb8  test    rax, rax
0x180001bbb  jz      short loc_180001BC3
0x180001bbd  cmp     byte ptr [rbx+20h], 44h ; 'D'
0x180001bc1  jnz     short loc_180001BCE
0x180001bc3  add     rbx, 28h ; '('
0x180001bc7  cmp     rbx, rbp
0x180001bca  jb      short loc_180001B93
0x180001bcc  jmp     short loc_180001BE9
0x180001bce  mov     r9, rdi
0x180001bd1  mov     [rsp+68h+var_48], r15
0x180001bd6  mov     r8, rbx
0x180001bd9  mov     edx, 0E0h
0x180001bde  mov     rcx, rsi
0x180001be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be6  mov     r14d, eax
0x180001be9  mov     eax, r14d
0x180001bec  add     rsp, 38h
0x180001bf0  pop     r15
0x180001bf2  pop     r14
0x180001bf4  pop     rdi
0x180001bf5  pop     rsi
0x180001bf6  pop     rbp
0x180001bf7  pop     rbx
0x180001bf8  retn
```
