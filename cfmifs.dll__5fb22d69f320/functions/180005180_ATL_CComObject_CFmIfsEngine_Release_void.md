# ATL::CComObject<CFmIfsEngine>::Release(void)

- ea: `0x180005180`
- end: `0x180005201`
- name: `?Release@?$CComObject@VCFmIfsEngine@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005180`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFmIfsEngine>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005180  mov     [rsp+arg_0], rbx
0x180005185  push    rdi
0x180005186  sub     rsp, 20h
0x18000518a  mov     r8d, [rcx+8]
0x18000518e  mov     rbx, rcx
0x180005191  mov     ecx, 7FFFFFFFh
0x180005196  jmp     short loc_1800051AA
0x180005198  lea     edx, [r8-1]
0x18000519c  mov     eax, r8d
0x18000519f  lock cmpxchg [rbx+8], edx
0x1800051a4  jz      short loc_1800051AF
0x1800051a6  mov     r8d, [rbx+8]
0x1800051aa  cmp     r8d, ecx
0x1800051ad  jnz     short loc_180005198
0x1800051af  lea     edi, [r8-1]
0x1800051b3  test    edi, edi
0x1800051b5  jnz     short loc_1800051F4
0x1800051b7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800051be  mov     rax, [rcx]
0x1800051c1  mov     rax, [rax+8]
0x1800051c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ca  test    rbx, rbx
0x1800051cd  jz      short loc_1800051E1
0x1800051cf  mov     rax, [rbx]
0x1800051d2  lea     edx, [rdi+1]
0x1800051d5  mov     rcx, rbx
0x1800051d8  mov     rax, [rax+30h]
0x1800051dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800051e8  mov     rdx, [rcx]
0x1800051eb  mov     rax, [rdx+10h]
0x1800051ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f4  mov     rbx, [rsp+28h+arg_0]
0x1800051f9  mov     eax, edi
0x1800051fb  add     rsp, 20h
0x1800051ff  pop     rdi
0x180005200  retn
```
