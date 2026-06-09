# CRestriction::AddRestriction(tagCACLSID *,ulong,ulong)

- ea: `0x180016d80`
- end: `0x180016ddb`
- name: `?AddRestriction@CRestriction@@QEAAXPEAUtagCACLSID@@KK@Z`
- size: `91`
- prototype: `void __fastcall(CRestriction *__hidden this, struct tagCACLSID *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003b5c`
- `0x180003ecc`
- `0x180016a80`

## pseudocode

```c
void __fastcall CRestriction::AddRestriction(CRestriction *this, struct tagCACLSID *a2, int a3, int a4)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  struct tagPROPVARIANT v7; // [rsp+28h] [rbp-20h] BYREF

  v7.vt = 0;
  v6[0] = a4;
  v6[1] = a3;
  MQFreeVariant(&v7);
  CMQVariant::_setCACLSID((CMQVariant *)&v7, a2);
  CRestriction::AddChild(this, (const struct CPropertyRestriction *)v6);
  MQFreeVariant(&v7);
}

```

## disassembly

```asm
0x180016d80  mov     r11, rsp
0x180016d83  mov     [r11+8], rbx
0x180016d87  push    rdi
0x180016d88  sub     rsp, 40h
0x180016d8c  mov     rbx, rdx
0x180016d8f  mov     rdi, rcx
0x180016d92  xor     eax, eax
0x180016d94  mov     word ptr [rsp+48h+var_20], ax
0x180016d99  mov     [r11-28h], r9d
0x180016d9d  mov     [r11-24h], r8d
0x180016da1  lea     rcx, [r11-20h]; struct tagPROPVARIANT *
0x180016da5  call    ?MQFreeVariant@@YAXAEAUtagPROPVARIANT@@@Z; MQFreeVariant(tagPROPVARIANT &)
0x180016daa  mov     rdx, rbx; struct tagCACLSID *
0x180016dad  lea     rcx, [rsp+48h+var_20]; this
0x180016db2  call    ?_setCACLSID@CMQVariant@@AEAAXAEBUtagCACLSID@@@Z; CMQVariant::_setCACLSID(tagCACLSID const &)
0x180016db7  lea     rdx, [rsp+48h+var_28]; struct CPropertyRestriction *
0x180016dbc  mov     rcx, rdi; this
0x180016dbf  call    ?AddChild@CRestriction@@QEAAXAEBVCPropertyRestriction@@@Z; CRestriction::AddChild(CPropertyRestriction const &)
0x180016dc4  nop
0x180016dc5  lea     rcx, [rsp+48h+var_20]; struct tagPROPVARIANT *
0x180016dca  call    ?MQFreeVariant@@YAXAEAUtagPROPVARIANT@@@Z; MQFreeVariant(tagPROPVARIANT &)
0x180016dcf  nop
0x180016dd0  mov     rbx, [rsp+48h+arg_0]
0x180016dd5  add     rsp, 40h
0x180016dd9  pop     rdi
0x180016dda  retn
```
