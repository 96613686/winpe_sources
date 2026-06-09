# ATL::CComObject<ColorCaptureShellExt>::Release(void)

- ea: `0x180009580`
- end: `0x1800095f3`
- name: `?Release@?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009600`

## callees

- `0x180009580`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorCaptureShellExt>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[8];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[8] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180009580  mov     [rsp+arg_0], rbx
0x180009585  push    rdi
0x180009586  sub     rsp, 20h
0x18000958a  mov     ebx, [rcx+20h]
0x18000958d  mov     rdi, rcx
0x180009590  cmp     ebx, 7FFFFFFFh
0x180009596  jnz     short loc_18000959F
0x180009598  mov     ebx, 7FFFFFFEh
0x18000959d  jmp     short loc_1800095E6
0x18000959f  sub     ebx, 1
0x1800095a2  mov     [rcx+20h], ebx
0x1800095a5  jnz     short loc_1800095E6
0x1800095a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800095ae  mov     rax, [rcx]
0x1800095b1  mov     rax, [rax+8]
0x1800095b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ba  test    rdi, rdi
0x1800095bd  jz      short loc_1800095D3
0x1800095bf  mov     rax, [rdi]
0x1800095c2  mov     edx, 1
0x1800095c7  mov     rcx, rdi
0x1800095ca  mov     rax, [rax+20h]
0x1800095ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800095da  mov     rdx, [rcx]
0x1800095dd  mov     rax, [rdx+10h]
0x1800095e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e6  mov     eax, ebx
0x1800095e8  mov     rbx, [rsp+28h+arg_0]
0x1800095ed  add     rsp, 20h
0x1800095f1  pop     rdi
0x1800095f2  retn
```
