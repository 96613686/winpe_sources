# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x180008520`
- end: `0x180008616`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `246`
- prototype: `int(CConfigServiceProvider2Impl *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800065a0`

## callees

- `0x180008520`
- `0x18000a240`
- `0x18000e010`

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
0x180008520  mov     rax, rsp
0x180008523  push    rbx
0x180008524  push    rbp
0x180008525  push    rsi
0x180008526  push    rdi
0x180008527  sub     rsp, 58h
0x18000852b  mov     dword ptr [rax+10h], 0
0x180008532  mov     rsi, r9
0x180008535  mov     rbx, r8
0x180008538  mov     rdi, rdx
0x18000853b  mov     rbp, rcx
0x18000853e  test    rdx, rdx
0x180008541  jnz     short loc_18000854D
0x180008543  mov     ecx, 80004003h
0x180008548  jmp     loc_18000860A
0x18000854d  test    rbx, rbx
0x180008550  jz      short loc_180008543
0x180008552  mov     qword ptr [r8], 0
0x180008559  test    rsi, rsi
0x18000855c  jz      short loc_180008543
0x18000855e  mov     dword ptr [r9], 0
0x180008565  mov     rcx, rdi
0x180008568  mov     rax, [rdx]
0x18000856b  lea     rdx, [rsp+78h+arg_8]
0x180008573  mov     rax, [rax+88h]
0x18000857a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857f  mov     ecx, eax
0x180008581  test    eax, eax
0x180008583  js      loc_18000860A
0x180008589  cmp     [rsp+78h+arg_8], 0
0x180008591  jz      short loc_180008605
0x180008593  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x180008597  test    rcx, rcx
0x18000859a  jz      short loc_180008605
0x18000859c  mov     rdx, rdi; struct IConfigManager2URI *
0x18000859f  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800085a4  test    rax, rax
0x1800085a7  jz      short loc_180008605
0x1800085a9  lea     rcx, [rsp+78h+var_38]
0x1800085ae  mov     [rsp+78h+var_30], 0
0x1800085b7  mov     [rsp+78h+var_50], rcx
0x1800085bc  mov     r8, rax
0x1800085bf  mov     rax, [rax+20h]
0x1800085c3  lea     rcx, [rsp+78h+var_30]
0x1800085c8  mov     [rsp+78h+var_58], rcx
0x1800085cd  xor     r9d, r9d
0x1800085d0  mov     rcx, rbp
0x1800085d3  mov     [rsp+78h+var_38], 0
0x1800085db  mov     rdx, rdi
0x1800085de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e3  mov     ecx, eax
0x1800085e5  test    eax, eax
0x1800085e7  js      short loc_18000860A
0x1800085e9  mov     rax, [rsp+78h+var_30]
0x1800085ee  test    rax, rax
0x1800085f1  jnz     short loc_1800085FA
0x1800085f3  mov     ecx, 8007000Eh
0x1800085f8  jmp     short loc_18000860A
0x1800085fa  mov     [rbx], rax
0x1800085fd  mov     eax, [rsp+78h+var_38]
0x180008601  mov     [rsi], eax
0x180008603  jmp     short loc_18000860A
0x180008605  mov     ecx, 86000002h
0x18000860a  mov     eax, ecx
0x18000860c  add     rsp, 58h
0x180008610  pop     rdi
0x180008611  pop     rsi
0x180008612  pop     rbp
0x180008613  pop     rbx
0x180008614  retn
```
