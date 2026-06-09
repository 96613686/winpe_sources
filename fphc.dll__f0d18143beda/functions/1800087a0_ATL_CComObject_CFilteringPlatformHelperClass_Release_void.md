# ATL::CComObject<CFilteringPlatformHelperClass>::Release(void)

- ea: `0x1800087a0`
- end: `0x180008824`
- name: `?Release@?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008830`
- `0x180008840`

## callees

- `0x1800087a0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFilteringPlatformHelperClass>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 16);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 16, i - 1, i);
        i = *((_DWORD *)a1 + 16) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800087a0  mov     [rsp+arg_0], rbx
0x1800087a5  push    rdi
0x1800087a6  sub     rsp, 20h
0x1800087aa  mov     r8d, [rcx+40h]
0x1800087ae  mov     rbx, rcx
0x1800087b1  mov     ecx, 7FFFFFFFh
0x1800087b6  jmp     short loc_1800087CA
0x1800087b8  lea     edx, [r8-1]
0x1800087bc  mov     eax, r8d
0x1800087bf  lock cmpxchg [rbx+40h], edx
0x1800087c4  jz      short loc_1800087CF
0x1800087c6  mov     r8d, [rbx+40h]
0x1800087ca  cmp     r8d, ecx
0x1800087cd  jnz     short loc_1800087B8
0x1800087cf  lea     edi, [r8-1]
0x1800087d3  test    edi, edi
0x1800087d5  jnz     short loc_180008817
0x1800087d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800087de  mov     rax, [rcx]
0x1800087e1  mov     rax, [rax+8]
0x1800087e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ea  test    rbx, rbx
0x1800087ed  jz      short loc_180008804
0x1800087ef  mov     rax, [rbx]
0x1800087f2  lea     edx, [rdi+1]
0x1800087f5  mov     rcx, rbx
0x1800087f8  mov     rax, [rax+0A8h]
0x1800087ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008804  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000880b  mov     rdx, [rcx]
0x18000880e  mov     rax, [rdx+10h]
0x180008812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008817  mov     rbx, [rsp+28h+arg_0]
0x18000881c  mov     eax, edi
0x18000881e  add     rsp, 20h
0x180008822  pop     rdi
0x180008823  retn
```
