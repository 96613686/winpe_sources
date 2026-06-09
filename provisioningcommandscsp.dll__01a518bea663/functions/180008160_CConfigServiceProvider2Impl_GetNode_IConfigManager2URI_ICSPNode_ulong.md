# CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x180008160`
- end: `0x180008255`
- name: `?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `245`
- prototype: `__int64 __fastcall(const struct CspNodeMapBase **this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x180008160`
- `0x180009d7c`
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
0x180008160  mov     rax, rsp
0x180008163  push    rbx
0x180008164  push    rbp
0x180008165  push    rsi
0x180008166  push    rdi
0x180008167  sub     rsp, 58h
0x18000816b  mov     dword ptr [rax+10h], 0
0x180008172  mov     rsi, r9
0x180008175  mov     rbx, r8
0x180008178  mov     rdi, rdx
0x18000817b  mov     rbp, rcx
0x18000817e  test    rdx, rdx
0x180008181  jnz     short loc_18000818D
0x180008183  mov     ecx, 80004003h
0x180008188  jmp     loc_18000824A
0x18000818d  test    rbx, rbx
0x180008190  jz      short loc_180008183
0x180008192  mov     qword ptr [r8], 0
0x180008199  test    rsi, rsi
0x18000819c  jz      short loc_180008183
0x18000819e  mov     dword ptr [r9], 0
0x1800081a5  mov     rcx, rdi
0x1800081a8  mov     rax, [rdx]
0x1800081ab  lea     rdx, [rsp+78h+arg_8]
0x1800081b3  mov     rax, [rax+88h]
0x1800081ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081bf  mov     ecx, eax
0x1800081c1  test    eax, eax
0x1800081c3  js      loc_18000824A
0x1800081c9  cmp     [rsp+78h+arg_8], 0
0x1800081d1  jz      short loc_180008245
0x1800081d3  mov     rcx, [rbp+20h]; struct CspNodeMapBase *
0x1800081d7  test    rcx, rcx
0x1800081da  jz      short loc_180008245
0x1800081dc  mov     rdx, rdi; struct IConfigManager2URI *
0x1800081df  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800081e4  test    rax, rax
0x1800081e7  jz      short loc_180008245
0x1800081e9  lea     rcx, [rsp+78h+var_38]
0x1800081ee  mov     [rsp+78h+var_30], 0
0x1800081f7  mov     [rsp+78h+var_50], rcx
0x1800081fc  mov     r8, rax
0x1800081ff  mov     rax, [rax+20h]
0x180008203  lea     rcx, [rsp+78h+var_30]
0x180008208  mov     [rsp+78h+var_58], rcx
0x18000820d  xor     r9d, r9d
0x180008210  mov     rcx, rbp
0x180008213  mov     [rsp+78h+var_38], 0
0x18000821b  mov     rdx, rdi
0x18000821e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008223  mov     ecx, eax
0x180008225  test    eax, eax
0x180008227  js      short loc_18000824A
0x180008229  mov     rax, [rsp+78h+var_30]
0x18000822e  test    rax, rax
0x180008231  jnz     short loc_18000823A
0x180008233  mov     ecx, 8007000Eh
0x180008238  jmp     short loc_18000824A
0x18000823a  mov     [rbx], rax
0x18000823d  mov     eax, [rsp+78h+var_38]
0x180008241  mov     [rsi], eax
0x180008243  jmp     short loc_18000824A
0x180008245  mov     ecx, 86000002h
0x18000824a  mov     eax, ecx
0x18000824c  add     rsp, 58h
0x180008250  pop     rdi
0x180008251  pop     rsi
0x180008252  pop     rbp
0x180008253  pop     rbx
0x180008254  retn
```
