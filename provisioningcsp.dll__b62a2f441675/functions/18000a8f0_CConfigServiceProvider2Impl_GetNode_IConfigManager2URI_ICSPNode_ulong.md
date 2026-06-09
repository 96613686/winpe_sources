# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x18000a8f0`
- end: `0x18000a9e6`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `246`
- prototype: `int(CConfigServiceProvider2Impl *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005ac0`

## callees

- `0x18000a8f0`
- `0x180010f8c`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::GetNode(
        const struct CspNodeMapBase **this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  int v8; // ecx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  const struct CSP_NODEMAP_ENTRY *v11; // r8
  __int64 (__fastcall *v12)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *); // rax
  unsigned int v14; // [rsp+40h] [rbp-38h] BYREF
  struct ICSPNode *v15; // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+88h] [rbp+10h] BYREF

  v16 = 0;
  if ( a2 && a3 && (*a3 = 0, a4) )
  {
    *a4 = 0;
    v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v16);
    if ( v8 >= 0 )
    {
      if ( v16 && (v9 = this[4]) != 0 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, a2)) != 0 )
      {
        v15 = 0;
        v11 = NodeMapEntryForURI;
        v12 = (__int64 (__fastcall *)(CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODEMAP_ENTRY *, _QWORD, struct ICSPNode **, unsigned int *))*((_QWORD *)NodeMapEntryForURI + 4);
        v14 = 0;
        v8 = v12((CConfigServiceProvider2Impl *)this, a2, v11, 0, &v15, &v14);
        if ( v8 >= 0 )
        {
          if ( v15 )
          {
            *a3 = v15;
            *a4 = v14;
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
      else
      {
        return (unsigned int)-2046820350;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a8f0  mov     rax, rsp
0x18000a8f3  push    rbx
0x18000a8f4  push    rbp
0x18000a8f5  push    rsi
0x18000a8f6  push    rdi
0x18000a8f7  sub     rsp, 58h
0x18000a8fb  mov     dword ptr [rax+10h], 0
0x18000a902  mov     rsi, r9
0x18000a905  mov     rbx, r8
0x18000a908  mov     rdi, rdx
0x18000a90b  mov     rbp, rcx
0x18000a90e  test    rdx, rdx
0x18000a911  jnz     short loc_18000A91D
0x18000a913  mov     ecx, 80004003h
0x18000a918  jmp     loc_18000A9DA
0x18000a91d  test    rbx, rbx
0x18000a920  jz      short loc_18000A913
0x18000a922  mov     qword ptr [r8], 0
0x18000a929  test    rsi, rsi
0x18000a92c  jz      short loc_18000A913
0x18000a92e  mov     dword ptr [r9], 0
0x18000a935  mov     rcx, rdi
0x18000a938  mov     rax, [rdx]
0x18000a93b  lea     rdx, [rsp+78h+arg_8]
0x18000a943  mov     rax, [rax+88h]
0x18000a94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a94f  mov     ecx, eax
0x18000a951  test    eax, eax
0x18000a953  js      loc_18000A9DA
0x18000a959  cmp     [rsp+78h+arg_8], 0
0x18000a961  jz      short loc_18000A9D5
0x18000a963  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x18000a967  test    rcx, rcx
0x18000a96a  jz      short loc_18000A9D5
0x18000a96c  mov     rdx, rdi; struct IConfigManager2URI *
0x18000a96f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000a974  test    rax, rax
0x18000a977  jz      short loc_18000A9D5
0x18000a979  lea     rcx, [rsp+78h+var_38]
0x18000a97e  mov     [rsp+78h+var_30], 0
0x18000a987  mov     [rsp+78h+var_50], rcx
0x18000a98c  mov     r8, rax
0x18000a98f  mov     rax, [rax+20h]
0x18000a993  lea     rcx, [rsp+78h+var_30]
0x18000a998  mov     [rsp+78h+var_58], rcx
0x18000a99d  xor     r9d, r9d
0x18000a9a0  mov     rcx, rbp
0x18000a9a3  mov     [rsp+78h+var_38], 0
0x18000a9ab  mov     rdx, rdi
0x18000a9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b3  mov     ecx, eax
0x18000a9b5  test    eax, eax
0x18000a9b7  js      short loc_18000A9DA
0x18000a9b9  mov     rax, [rsp+78h+var_30]
0x18000a9be  test    rax, rax
0x18000a9c1  jnz     short loc_18000A9CA
0x18000a9c3  mov     ecx, 8007000Eh
0x18000a9c8  jmp     short loc_18000A9DA
0x18000a9ca  mov     [rbx], rax
0x18000a9cd  mov     eax, [rsp+78h+var_38]
0x18000a9d1  mov     [rsi], eax
0x18000a9d3  jmp     short loc_18000A9DA
0x18000a9d5  mov     ecx, 86000002h
0x18000a9da  mov     eax, ecx
0x18000a9dc  add     rsp, 58h
0x18000a9e0  pop     rdi
0x18000a9e1  pop     rsi
0x18000a9e2  pop     rbp
0x18000a9e3  pop     rbx
0x18000a9e4  retn
```
