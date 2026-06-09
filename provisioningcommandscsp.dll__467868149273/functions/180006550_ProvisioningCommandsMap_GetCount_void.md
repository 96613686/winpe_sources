# ProvisioningCommandsMap::GetCount(void)

- ea: `0x180006550`
- end: `0x180006599`
- name: `?GetCount@ProvisioningCommandsMap@@UEBAKXZ`
- size: `73`
- prototype: `unsigned int __fastcall(ProvisioningCommandsMap *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006550`
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
0x180006550  sub     rsp, 28h
0x180006554  mov     rax, [rcx]
0x180006557  mov     rax, [rax+8]
0x18000655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006560  xor     r9d, r9d
0x180006563  mov     r8, rax
0x180006566  test    rax, rax
0x180006569  jnz     short loc_180006570
0x18000656b  or      eax, 0FFFFFFFFh
0x18000656e  jmp     short loc_180006593
0x180006570  mov     ecx, r9d
0x180006573  mov     eax, ecx
0x180006575  lea     rdx, [rax+rax*4]
0x180006579  cmp     [r8+rdx*8], r9
0x18000657d  jnz     short loc_18000658D
0x18000657f  cmp     [r8+rdx*8+8], r9d
0x180006584  jnz     short loc_18000658D
0x180006586  cmp     [r8+rdx*8+0Ch], r9d
0x18000658b  jz      short loc_180006591
0x18000658d  inc     ecx
0x18000658f  jmp     short loc_180006573
0x180006591  mov     eax, ecx
0x180006593  add     rsp, 28h
0x180006597  retn
```
