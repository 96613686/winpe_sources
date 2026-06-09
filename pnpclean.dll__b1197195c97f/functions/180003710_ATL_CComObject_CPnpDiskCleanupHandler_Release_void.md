# ATL::CComObject<CPnpDiskCleanupHandler>::Release(void)

- ea: `0x180003710`
- end: `0x180003783`
- name: `?Release@?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003710`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpDiskCleanupHandler>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003710  mov     [rsp+arg_0], rbx
0x180003715  push    rdi
0x180003716  sub     rsp, 20h
0x18000371a  mov     ebx, [rcx+8]
0x18000371d  mov     rdi, rcx
0x180003720  cmp     ebx, 7FFFFFFFh
0x180003726  jnz     short loc_18000372F
0x180003728  mov     ebx, 7FFFFFFEh
0x18000372d  jmp     short loc_180003776
0x18000372f  sub     ebx, 1
0x180003732  mov     [rcx+8], ebx
0x180003735  jnz     short loc_180003776
0x180003737  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000373e  mov     rax, [rcx]
0x180003741  mov     rax, [rax+8]
0x180003745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374a  test    rdi, rdi
0x18000374d  jz      short loc_180003763
0x18000374f  mov     rax, [rdi]
0x180003752  mov     edx, 1
0x180003757  mov     rcx, rdi
0x18000375a  mov     rax, [rax+48h]
0x18000375e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003763  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000376a  mov     rdx, [rcx]
0x18000376d  mov     rax, [rdx+10h]
0x180003771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003776  mov     eax, ebx
0x180003778  mov     rbx, [rsp+28h+arg_0]
0x18000377d  add     rsp, 20h
0x180003781  pop     rdi
0x180003782  retn
```
