# ProvisioningCommandsMap::GetCount(void)

- ea: `0x180006250`
- end: `0x180006298`
- name: `?GetCount@ProvisioningCommandsMap@@UEBAKXZ`
- size: `72`
- prototype: `__int64 __fastcall(ProvisioningCommandsMap *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006250`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ProvisioningCommandsMap::GetCount(ProvisioningCommandsMap *this)
{
  __int64 v1; // r8
  unsigned int i; // ecx

  v1 = (*(__int64 (__fastcall **)(ProvisioningCommandsMap *))(*(_QWORD *)this + 8LL))(this);
  if ( !v1 )
    return 0xFFFFFFFFLL;
  for ( i = 0; *(_QWORD *)(v1 + 40LL * i) || *(_DWORD *)(v1 + 40LL * i + 8) || *(_DWORD *)(v1 + 40LL * i + 12); ++i )
    ;
  return i;
}

```

## disassembly

```asm
0x180006250  sub     rsp, 28h
0x180006254  mov     rax, [rcx]
0x180006257  mov     rax, [rax+8]
0x18000625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006260  xor     r9d, r9d
0x180006263  mov     r8, rax
0x180006266  test    rax, rax
0x180006269  jnz     short loc_180006270
0x18000626b  or      eax, 0FFFFFFFFh
0x18000626e  jmp     short loc_180006293
0x180006270  mov     ecx, r9d
0x180006273  mov     eax, ecx
0x180006275  lea     rdx, [rax+rax*4]
0x180006279  cmp     [r8+rdx*8], r9
0x18000627d  jnz     short loc_18000628D
0x18000627f  cmp     [r8+rdx*8+8], r9d
0x180006284  jnz     short loc_18000628D
0x180006286  cmp     [r8+rdx*8+0Ch], r9d
0x18000628b  jz      short loc_180006291
0x18000628d  inc     ecx
0x18000628f  jmp     short loc_180006273
0x180006291  mov     eax, ecx
0x180006293  add     rsp, 28h
0x180006297  retn
```
