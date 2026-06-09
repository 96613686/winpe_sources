# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180009910`
- end: `0x1800099c7`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009080`

## callees

- `0x180009910`
- `0x180009d7c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
{
  struct IConfigManager2URI *v7; // rcx
  int v8; // ebx
  const struct CspNodeMapBase *v9; // rcx
  const struct CSP_NODEMAP_ENTRY *NodeMapEntryForURI; // rax
  struct IConfigManager2URI *v12; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  v12 = 0;
  if ( a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24)
                                                                                                  + 168LL))(
           *(_QWORD *)(a1 + 24),
           a2,
           0,
           0,
           &v12);
    if ( v8 >= 0 )
    {
      v9 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
      if ( v9 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v9, v12)) != 0 )
        v8 = (*((_DWORD *)NodeMapEntryForURI + 5) & 4) != 0 ? -2147467263 : -2046820335;
      else
        v8 = -2046820335;
    }
    v7 = v12;
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009910  mov     r11, rsp
0x180009913  mov     [r11+8], rbx
0x180009917  push    rdi
0x180009918  sub     rsp, 40h
0x18000991c  mov     r8, [rsp+48h+arg_20]
0x180009921  mov     rdi, rcx
0x180009924  xor     ecx, ecx
0x180009926  mov     [r11-18h], rcx
0x18000992a  test    r8, r8
0x18000992d  jz      short loc_1800099A4
0x18000992f  mov     rax, [rsp+48h+arg_28]
0x180009934  test    rax, rax
0x180009937  jz      short loc_1800099A4
0x180009939  mov     [r8], rcx
0x18000993c  xor     r9d, r9d
0x18000993f  mov     [rax], ecx
0x180009941  lea     r8, [r11-18h]
0x180009945  mov     rcx, [rdi+18h]
0x180009949  mov     [r11-28h], r8
0x18000994d  xor     r8d, r8d
0x180009950  mov     rax, [rcx]
0x180009953  mov     rax, [rax+0A8h]
0x18000995a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995f  mov     ebx, eax
0x180009961  test    eax, eax
0x180009963  js      short loc_180009996
0x180009965  mov     rax, [rdi+10h]
0x180009969  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18000996d  test    rcx, rcx
0x180009970  jz      short loc_18000999D
0x180009972  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x180009977  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000997c  test    rax, rax
0x18000997f  jz      short loc_18000999D
0x180009981  mov     eax, [rax+14h]
0x180009984  and     al, 4
0x180009986  neg     al
0x180009988  sbb     ebx, ebx
0x18000998a  and     ebx, 0FA003FF0h
0x180009990  add     ebx, 86000011h
0x180009996  mov     rcx, [rsp+48h+var_18]
0x18000999b  jmp     short loc_1800099A9
0x18000999d  mov     ebx, 86000011h
0x1800099a2  jmp     short loc_180009996
0x1800099a4  mov     ebx, 80070057h
0x1800099a9  test    rcx, rcx
0x1800099ac  jz      short loc_1800099BA
0x1800099ae  mov     rax, [rcx]
0x1800099b1  mov     rax, [rax+10h]
0x1800099b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ba  mov     eax, ebx
0x1800099bc  mov     rbx, [rsp+48h+arg_0]
0x1800099c1  add     rsp, 40h
0x1800099c5  pop     rdi
0x1800099c6  retn
```
