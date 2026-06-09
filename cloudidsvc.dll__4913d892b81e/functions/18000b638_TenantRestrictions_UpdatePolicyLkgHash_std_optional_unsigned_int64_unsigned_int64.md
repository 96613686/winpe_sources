# TenantRestrictions::UpdatePolicyLkgHash(std::optional<unsigned __int64> &,unsigned __int64)

- ea: `0x18000b638`
- end: `0x18000b676`
- name: `?UpdatePolicyLkgHash@TenantRestrictions@@CA_NAEAV?$optional@_K@std@@_K@Z`
- size: `62`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000ae7c`

## callees

- `0x18000b638`

## pseudocode

```c
bool __fastcall TenantRestrictions::UpdatePolicyLkgHash(__int64 a1, __int64 a2)
{
  bool v2; // r8
  int v4; // [rsp+9h] [rbp-Fh]
  __int16 v5; // [rsp+Dh] [rbp-Bh]
  char v6; // [rsp+Fh] [rbp-9h]

  v2 = 0;
  if ( *(_BYTE *)(a1 + 8) )
    v2 = *(_QWORD *)a1 != a2;
  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 9) = v4;
  *(_WORD *)(a1 + 13) = v5;
  *(_BYTE *)(a1 + 15) = v6;
  return v2;
}

```

## disassembly

```asm
0x18000b638  sub     rsp, 18h
0x18000b63c  xor     r8d, r8d
0x18000b63f  mov     rax, rcx
0x18000b642  cmp     [rcx+8], r8b
0x18000b646  jz      short loc_18000B650
0x18000b648  cmp     [rcx], rdx
0x18000b64b  jz      short loc_18000B650
0x18000b64d  mov     r8b, 1
0x18000b650  mov     [rcx], rdx
0x18000b653  mov     byte ptr [rcx+8], 1
0x18000b657  mov     ecx, [rsp+18h+var_F]
0x18000b65b  mov     [rax+9], ecx
0x18000b65e  movzx   ecx, [rsp+18h+var_B]
0x18000b663  mov     [rax+0Dh], cx
0x18000b667  mov     cl, [rsp+18h+var_9]
0x18000b66b  mov     [rax+0Fh], cl
0x18000b66e  mov     al, r8b
0x18000b671  add     rsp, 18h
0x18000b675  retn
```
