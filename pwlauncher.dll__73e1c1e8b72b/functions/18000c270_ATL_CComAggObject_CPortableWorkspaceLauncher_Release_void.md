# ATL::CComAggObject<CPortableWorkspaceLauncher>::Release(void)

- ea: `0x18000c270`
- end: `0x18000c2e3`
- name: `?Release@?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c270`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPortableWorkspaceLauncher>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000c270  mov     [rsp+arg_0], rbx
0x18000c275  push    rdi
0x18000c276  sub     rsp, 20h
0x18000c27a  mov     ebx, [rcx+8]
0x18000c27d  mov     rdi, rcx
0x18000c280  cmp     ebx, 7FFFFFFFh
0x18000c286  jnz     short loc_18000C28F
0x18000c288  mov     ebx, 7FFFFFFEh
0x18000c28d  jmp     short loc_18000C2D6
0x18000c28f  sub     ebx, 1
0x18000c292  mov     [rcx+8], ebx
0x18000c295  jnz     short loc_18000C2D6
0x18000c297  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c29e  mov     rax, [rcx]
0x18000c2a1  mov     rax, [rax+8]
0x18000c2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2aa  test    rdi, rdi
0x18000c2ad  jz      short loc_18000C2C3
0x18000c2af  mov     rax, [rdi]
0x18000c2b2  mov     edx, 1
0x18000c2b7  mov     rcx, rdi
0x18000c2ba  mov     rax, [rax+18h]
0x18000c2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c2ca  mov     rdx, [rcx]
0x18000c2cd  mov     rax, [rdx+10h]
0x18000c2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d6  mov     eax, ebx
0x18000c2d8  mov     rbx, [rsp+28h+arg_0]
0x18000c2dd  add     rsp, 20h
0x18000c2e1  pop     rdi
0x18000c2e2  retn
```
