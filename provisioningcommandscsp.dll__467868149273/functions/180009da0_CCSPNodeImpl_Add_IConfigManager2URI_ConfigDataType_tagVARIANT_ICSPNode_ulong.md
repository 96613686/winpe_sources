# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180009da0`
- end: `0x180009e58`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800094a0`

## callees

- `0x180009da0`
- `0x18000a240`
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
0x180009da0  mov     r11, rsp
0x180009da3  mov     [r11+8], rbx
0x180009da7  push    rdi
0x180009da8  sub     rsp, 40h
0x180009dac  mov     r8, [rsp+48h+arg_20]
0x180009db1  mov     rdi, rcx
0x180009db4  xor     ecx, ecx
0x180009db6  mov     [r11-18h], rcx
0x180009dba  test    r8, r8
0x180009dbd  jz      short loc_180009E34
0x180009dbf  mov     rax, [rsp+48h+arg_28]
0x180009dc4  test    rax, rax
0x180009dc7  jz      short loc_180009E34
0x180009dc9  mov     [r8], rcx
0x180009dcc  xor     r9d, r9d
0x180009dcf  mov     [rax], ecx
0x180009dd1  lea     r8, [r11-18h]
0x180009dd5  mov     rcx, [rdi+18h]
0x180009dd9  mov     [r11-28h], r8
0x180009ddd  xor     r8d, r8d
0x180009de0  mov     rax, [rcx]
0x180009de3  mov     rax, [rax+0A8h]
0x180009dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009def  mov     ebx, eax
0x180009df1  test    eax, eax
0x180009df3  js      short loc_180009E26
0x180009df5  mov     rax, [rdi+10h]
0x180009df9  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x180009dfd  test    rcx, rcx
0x180009e00  jz      short loc_180009E2D
0x180009e02  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x180009e07  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x180009e0c  test    rax, rax
0x180009e0f  jz      short loc_180009E2D
0x180009e11  mov     eax, [rax+14h]
0x180009e14  and     al, 4
0x180009e16  neg     al
0x180009e18  sbb     ebx, ebx
0x180009e1a  and     ebx, 0FA003FF0h
0x180009e20  add     ebx, 86000011h
0x180009e26  mov     rcx, [rsp+48h+var_18]
0x180009e2b  jmp     short loc_180009E39
0x180009e2d  mov     ebx, 86000011h
0x180009e32  jmp     short loc_180009E26
0x180009e34  mov     ebx, 80070057h
0x180009e39  test    rcx, rcx
0x180009e3c  jz      short loc_180009E4A
0x180009e3e  mov     rax, [rcx]
0x180009e41  mov     rax, [rax+10h]
0x180009e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e4a  mov     eax, ebx
0x180009e4c  mov     rbx, [rsp+48h+arg_0]
0x180009e51  add     rsp, 40h
0x180009e55  pop     rdi
0x180009e56  retn
```
