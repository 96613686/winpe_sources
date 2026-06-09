# ATL::CComObject<CCtTuner>::Release(void)

- ea: `0x140004b30`
- end: `0x140004ba3`
- name: `?Release@?$CComObject@VCCtTuner@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004b30`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCtTuner>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 80LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140004b30  mov     [rsp+arg_0], rbx
0x140004b35  push    rdi
0x140004b36  sub     rsp, 20h
0x140004b3a  mov     ebx, [rcx+8]
0x140004b3d  mov     rdi, rcx
0x140004b40  cmp     ebx, 7FFFFFFFh
0x140004b46  jnz     short loc_140004B4F
0x140004b48  mov     ebx, 7FFFFFFEh
0x140004b4d  jmp     short loc_140004B96
0x140004b4f  sub     ebx, 1
0x140004b52  mov     [rcx+8], ebx
0x140004b55  jnz     short loc_140004B96
0x140004b57  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004b5e  mov     rax, [rcx]
0x140004b61  mov     rax, [rax+8]
0x140004b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b6a  test    rdi, rdi
0x140004b6d  jz      short loc_140004B83
0x140004b6f  mov     rax, [rdi]
0x140004b72  mov     edx, 1
0x140004b77  mov     rcx, rdi
0x140004b7a  mov     rax, [rax+50h]
0x140004b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b83  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004b8a  mov     rdx, [rcx]
0x140004b8d  mov     rax, [rdx+10h]
0x140004b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b96  mov     eax, ebx
0x140004b98  mov     rbx, [rsp+28h+arg_0]
0x140004b9d  add     rsp, 20h
0x140004ba1  pop     rdi
0x140004ba2  retn
```
