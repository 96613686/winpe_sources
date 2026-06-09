# ATL::CComObject<ColorDataProxy>::Release(void)

- ea: `0x180009610`
- end: `0x180009683`
- name: `?Release@?$CComObject@VColorDataProxy@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009610`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorDataProxy>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 120LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180009610  mov     [rsp+arg_0], rbx
0x180009615  push    rdi
0x180009616  sub     rsp, 20h
0x18000961a  mov     ebx, [rcx+8]
0x18000961d  mov     rdi, rcx
0x180009620  cmp     ebx, 7FFFFFFFh
0x180009626  jnz     short loc_18000962F
0x180009628  mov     ebx, 7FFFFFFEh
0x18000962d  jmp     short loc_180009676
0x18000962f  sub     ebx, 1
0x180009632  mov     [rcx+8], ebx
0x180009635  jnz     short loc_180009676
0x180009637  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000963e  mov     rax, [rcx]
0x180009641  mov     rax, [rax+8]
0x180009645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964a  test    rdi, rdi
0x18000964d  jz      short loc_180009663
0x18000964f  mov     rax, [rdi]
0x180009652  mov     edx, 1
0x180009657  mov     rcx, rdi
0x18000965a  mov     rax, [rax+78h]
0x18000965e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009663  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000966a  mov     rdx, [rcx]
0x18000966d  mov     rax, [rdx+10h]
0x180009671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009676  mov     eax, ebx
0x180009678  mov     rbx, [rsp+28h+arg_0]
0x18000967d  add     rsp, 20h
0x180009681  pop     rdi
0x180009682  retn
```
