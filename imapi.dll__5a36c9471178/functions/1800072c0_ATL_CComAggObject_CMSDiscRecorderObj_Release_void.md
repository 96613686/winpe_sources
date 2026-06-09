# ATL::CComAggObject<CMSDiscRecorderObj>::Release(void)

- ea: `0x1800072c0`
- end: `0x180007341`
- name: `?Release@?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800072c0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSDiscRecorderObj>::Release(volatile signed __int32 *a1)
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
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800072c0  mov     [rsp+arg_0], rbx
0x1800072c5  push    rdi
0x1800072c6  sub     rsp, 20h
0x1800072ca  mov     r8d, [rcx+8]
0x1800072ce  mov     rbx, rcx
0x1800072d1  mov     ecx, 7FFFFFFFh
0x1800072d6  jmp     short loc_1800072EA
0x1800072d8  lea     edx, [r8-1]
0x1800072dc  mov     eax, r8d
0x1800072df  lock cmpxchg [rbx+8], edx
0x1800072e4  jz      short loc_1800072EF
0x1800072e6  mov     r8d, [rbx+8]
0x1800072ea  cmp     r8d, ecx
0x1800072ed  jnz     short loc_1800072D8
0x1800072ef  lea     edi, [r8-1]
0x1800072f3  test    edi, edi
0x1800072f5  jnz     short loc_180007334
0x1800072f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800072fe  mov     rax, [rcx]
0x180007301  mov     rax, [rax+8]
0x180007305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730a  test    rbx, rbx
0x18000730d  jz      short loc_180007321
0x18000730f  mov     rax, [rbx]
0x180007312  lea     edx, [rdi+1]
0x180007315  mov     rcx, rbx
0x180007318  mov     rax, [rax+18h]
0x18000731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007321  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007328  mov     rdx, [rcx]
0x18000732b  mov     rax, [rdx+10h]
0x18000732f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007334  mov     rbx, [rsp+28h+arg_0]
0x180007339  mov     eax, edi
0x18000733b  add     rsp, 20h
0x18000733f  pop     rdi
0x180007340  retn
```
