# ATL::CComAggObject<CAdvancedConfig>::Release(void)

- ea: `0x1800059c0`
- end: `0x180005a41`
- name: `?Release@?$CComAggObject@VCAdvancedConfig@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800059c0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CAdvancedConfig>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800059c0  mov     [rsp+arg_0], rbx
0x1800059c5  push    rdi
0x1800059c6  sub     rsp, 20h
0x1800059ca  mov     r8d, [rcx+8]
0x1800059ce  mov     rbx, rcx
0x1800059d1  mov     ecx, 7FFFFFFFh
0x1800059d6  jmp     short loc_1800059EA
0x1800059d8  lea     edx, [r8-1]
0x1800059dc  mov     eax, r8d
0x1800059df  lock cmpxchg [rbx+8], edx
0x1800059e4  jz      short loc_1800059EF
0x1800059e6  mov     r8d, [rbx+8]
0x1800059ea  cmp     r8d, ecx
0x1800059ed  jnz     short loc_1800059D8
0x1800059ef  lea     edi, [r8-1]
0x1800059f3  test    edi, edi
0x1800059f5  jnz     short loc_180005A34
0x1800059f7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800059fe  mov     rax, [rcx]
0x180005a01  mov     rax, [rax+8]
0x180005a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0a  test    rbx, rbx
0x180005a0d  jz      short loc_180005A21
0x180005a0f  mov     rax, [rbx]
0x180005a12  lea     edx, [rdi+1]
0x180005a15  mov     rcx, rbx
0x180005a18  mov     rax, [rax+18h]
0x180005a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a21  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005a28  mov     rdx, [rcx]
0x180005a2b  mov     rax, [rdx+10h]
0x180005a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a34  mov     rbx, [rsp+28h+arg_0]
0x180005a39  mov     eax, edi
0x180005a3b  add     rsp, 20h
0x180005a3f  pop     rdi
0x180005a40  retn
```
