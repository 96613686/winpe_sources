# ATL::CComAggObject<CCtTuner>::Release(void)

- ea: `0x140004a90`
- end: `0x140004b03`
- name: `?Release@?$CComAggObject@VCCtTuner@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004a90`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CCtTuner>::Release(_DWORD *a1)
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
0x140004a90  mov     [rsp+arg_0], rbx
0x140004a95  push    rdi
0x140004a96  sub     rsp, 20h
0x140004a9a  mov     ebx, [rcx+8]
0x140004a9d  mov     rdi, rcx
0x140004aa0  cmp     ebx, 7FFFFFFFh
0x140004aa6  jnz     short loc_140004AAF
0x140004aa8  mov     ebx, 7FFFFFFEh
0x140004aad  jmp     short loc_140004AF6
0x140004aaf  sub     ebx, 1
0x140004ab2  mov     [rcx+8], ebx
0x140004ab5  jnz     short loc_140004AF6
0x140004ab7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004abe  mov     rax, [rcx]
0x140004ac1  mov     rax, [rax+8]
0x140004ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004aca  test    rdi, rdi
0x140004acd  jz      short loc_140004AE3
0x140004acf  mov     rax, [rdi]
0x140004ad2  mov     edx, 1
0x140004ad7  mov     rcx, rdi
0x140004ada  mov     rax, [rax+18h]
0x140004ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ae3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004aea  mov     rdx, [rcx]
0x140004aed  mov     rax, [rdx+10h]
0x140004af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004af6  mov     eax, ebx
0x140004af8  mov     rbx, [rsp+28h+arg_0]
0x140004afd  add     rsp, 20h
0x140004b01  pop     rdi
0x140004b02  retn
```
