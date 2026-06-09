# ATL::CComObject<CPnpCleanTaskHandler>::Release(void)

- ea: `0x180003be0`
- end: `0x180003c53`
- name: `?Release@?$CComObject@VCPnpCleanTaskHandler@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003be0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpCleanTaskHandler>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[14];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[14] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp+arg_0], rbx
0x180003be5  push    rdi
0x180003be6  sub     rsp, 20h
0x180003bea  mov     ebx, [rcx+38h]
0x180003bed  mov     rdi, rcx
0x180003bf0  cmp     ebx, 7FFFFFFFh
0x180003bf6  jnz     short loc_180003BFF
0x180003bf8  mov     ebx, 7FFFFFFEh
0x180003bfd  jmp     short loc_180003C46
0x180003bff  sub     ebx, 1
0x180003c02  mov     [rcx+38h], ebx
0x180003c05  jnz     short loc_180003C46
0x180003c07  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003c0e  mov     rax, [rcx]
0x180003c11  mov     rax, [rax+8]
0x180003c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1a  test    rdi, rdi
0x180003c1d  jz      short loc_180003C33
0x180003c1f  mov     rax, [rdi]
0x180003c22  mov     edx, 1
0x180003c27  mov     rcx, rdi
0x180003c2a  mov     rax, [rax+38h]
0x180003c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c33  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003c3a  mov     rdx, [rcx]
0x180003c3d  mov     rax, [rdx+10h]
0x180003c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c46  mov     eax, ebx
0x180003c48  mov     rbx, [rsp+28h+arg_0]
0x180003c4d  add     rsp, 20h
0x180003c51  pop     rdi
0x180003c52  retn
```
