# CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180010590`
- end: `0x180010648`
- name: `?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6e0`

## callees

- `0x180010590`
- `0x180010f8c`
- `0x180038010`

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
0x180010590  mov     r11, rsp
0x180010593  mov     [r11+8], rbx
0x180010597  push    rdi
0x180010598  sub     rsp, 40h
0x18001059c  mov     r8, [rsp+48h+arg_20]
0x1800105a1  mov     rdi, rcx
0x1800105a4  xor     ecx, ecx
0x1800105a6  mov     [r11-18h], rcx
0x1800105aa  test    r8, r8
0x1800105ad  jz      short loc_180010624
0x1800105af  mov     rax, [rsp+48h+arg_28]
0x1800105b4  test    rax, rax
0x1800105b7  jz      short loc_180010624
0x1800105b9  mov     [r8], rcx
0x1800105bc  xor     r9d, r9d
0x1800105bf  mov     [rax], ecx
0x1800105c1  lea     r8, [r11-18h]
0x1800105c5  mov     rcx, [rdi+18h]
0x1800105c9  mov     [r11-28h], r8
0x1800105cd  xor     r8d, r8d
0x1800105d0  mov     rax, [rcx]
0x1800105d3  mov     rax, [rax+0A8h]
0x1800105da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105df  mov     ebx, eax
0x1800105e1  test    eax, eax
0x1800105e3  js      short loc_180010616
0x1800105e5  mov     rax, [rdi+10h]
0x1800105e9  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800105ed  test    rcx, rcx
0x1800105f0  jz      short loc_18001061D
0x1800105f2  mov     rdx, [rsp+48h+var_18]; struct IConfigManager2URI *
0x1800105f7  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800105fc  test    rax, rax
0x1800105ff  jz      short loc_18001061D
0x180010601  mov     eax, [rax+14h]
0x180010604  and     al, 4
0x180010606  neg     al
0x180010608  sbb     ebx, ebx
0x18001060a  and     ebx, 0FA003FF0h
0x180010610  add     ebx, 86000011h
0x180010616  mov     rcx, [rsp+48h+var_18]
0x18001061b  jmp     short loc_180010629
0x18001061d  mov     ebx, 86000011h
0x180010622  jmp     short loc_180010616
0x180010624  mov     ebx, 80070057h
0x180010629  test    rcx, rcx
0x18001062c  jz      short loc_18001063A
0x18001062e  mov     rax, [rcx]
0x180010631  mov     rax, [rax+10h]
0x180010635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063a  mov     eax, ebx
0x18001063c  mov     rbx, [rsp+48h+arg_0]
0x180010641  add     rsp, 40h
0x180010645  pop     rdi
0x180010646  retn
```
