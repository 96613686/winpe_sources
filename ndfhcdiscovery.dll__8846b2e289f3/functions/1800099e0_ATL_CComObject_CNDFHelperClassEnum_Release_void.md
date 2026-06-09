# ATL::CComObject<CNDFHelperClassEnum>::Release(void)

- ea: `0x1800099e0`
- end: `0x180009a62`
- name: `?Release@?$CComObject@VCNDFHelperClassEnum@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800099e0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CNDFHelperClassEnum>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800099e0  mov     [rsp+arg_0], rbx
0x1800099e5  push    rdi
0x1800099e6  sub     rsp, 20h
0x1800099ea  mov     r8d, [rcx+8]
0x1800099ee  mov     rbx, rcx
0x1800099f1  mov     ecx, 7FFFFFFFh
0x1800099f6  jmp     short loc_180009A0A
0x1800099f8  lea     edx, [r8-1]
0x1800099fc  mov     eax, r8d
0x1800099ff  lock cmpxchg [rbx+8], edx
0x180009a04  jz      short loc_180009A0F
0x180009a06  mov     r8d, [rbx+8]
0x180009a0a  cmp     r8d, ecx
0x180009a0d  jnz     short loc_1800099F8
0x180009a0f  lea     edi, [r8-1]
0x180009a13  test    edi, edi
0x180009a15  jnz     short loc_180009A54
0x180009a17  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009a1e  mov     rax, [rcx]
0x180009a21  mov     rax, [rax+8]
0x180009a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a2a  test    rbx, rbx
0x180009a2d  jz      short loc_180009A41
0x180009a2f  mov     rax, [rbx]
0x180009a32  lea     edx, [rdi+1]
0x180009a35  mov     rcx, rbx
0x180009a38  mov     rax, [rax+28h]
0x180009a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a41  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009a48  mov     rdx, [rcx]
0x180009a4b  mov     rax, [rdx+10h]
0x180009a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a54  mov     rbx, [rsp+28h+arg_0]
0x180009a59  mov     eax, edi
0x180009a5b  add     rsp, 20h
0x180009a5f  pop     rdi
0x180009a60  retn
```
