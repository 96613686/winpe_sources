# ATL::CComObject<CINDFHelperClassImpl>::Release(void)

- ea: `0x180009950`
- end: `0x1800099d5`
- name: `?Release@?$CComObject@VCINDFHelperClassImpl@@@ATL@@UEAAKXZ`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009950`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CINDFHelperClassImpl>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, v3 + 1);
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180009950  mov     [rsp+arg_0], rbx
0x180009955  push    rdi
0x180009956  sub     rsp, 20h
0x18000995a  mov     r8d, [rcx+8]
0x18000995e  mov     rbx, rcx
0x180009961  mov     ecx, 7FFFFFFFh
0x180009966  jmp     short loc_18000997A
0x180009968  lea     edx, [r8-1]
0x18000996c  mov     eax, r8d
0x18000996f  lock cmpxchg [rbx+8], edx
0x180009974  jz      short loc_18000997F
0x180009976  mov     r8d, [rbx+8]
0x18000997a  cmp     r8d, ecx
0x18000997d  jnz     short loc_180009968
0x18000997f  lea     edi, [r8-1]
0x180009983  test    edi, edi
0x180009985  jnz     short loc_1800099C7
0x180009987  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000998e  mov     rax, [rcx]
0x180009991  mov     rax, [rax+8]
0x180009995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999a  test    rbx, rbx
0x18000999d  jz      short loc_1800099B4
0x18000999f  mov     rax, [rbx]
0x1800099a2  lea     edx, [rdi+1]
0x1800099a5  mov     rcx, rbx
0x1800099a8  mov     rax, [rax+98h]
0x1800099af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099b4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800099bb  mov     rdx, [rcx]
0x1800099be  mov     rax, [rdx+10h]
0x1800099c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c7  mov     rbx, [rsp+28h+arg_0]
0x1800099cc  mov     eax, edi
0x1800099ce  add     rsp, 20h
0x1800099d2  pop     rdi
0x1800099d3  retn
```
