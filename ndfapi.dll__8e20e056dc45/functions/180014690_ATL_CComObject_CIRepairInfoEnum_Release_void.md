# ATL::CComObject<CIRepairInfoEnum>::Release(void)

- ea: `0x180014690`
- end: `0x180014711`
- name: `?Release@?$CComObject@VCIRepairInfoEnum@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180014690`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIRepairInfoEnum>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 80LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180014690  mov     [rsp+arg_0], rbx
0x180014695  push    rdi
0x180014696  sub     rsp, 20h
0x18001469a  mov     r8d, [rcx+8]
0x18001469e  mov     rbx, rcx
0x1800146a1  mov     ecx, 7FFFFFFFh
0x1800146a6  jmp     short loc_1800146BA
0x1800146a8  lea     edx, [r8-1]
0x1800146ac  mov     eax, r8d
0x1800146af  lock cmpxchg [rbx+8], edx
0x1800146b4  jz      short loc_1800146BF
0x1800146b6  mov     r8d, [rbx+8]
0x1800146ba  cmp     r8d, ecx
0x1800146bd  jnz     short loc_1800146A8
0x1800146bf  lea     edi, [r8-1]
0x1800146c3  test    edi, edi
0x1800146c5  jnz     short loc_180014704
0x1800146c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800146ce  mov     rax, [rcx]
0x1800146d1  mov     rax, [rax+8]
0x1800146d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146da  test    rbx, rbx
0x1800146dd  jz      short loc_1800146F1
0x1800146df  mov     rax, [rbx]
0x1800146e2  lea     edx, [rdi+1]
0x1800146e5  mov     rcx, rbx
0x1800146e8  mov     rax, [rax+50h]
0x1800146ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800146f8  mov     rdx, [rcx]
0x1800146fb  mov     rax, [rdx+10h]
0x1800146ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014704  mov     rbx, [rsp+28h+arg_0]
0x180014709  mov     eax, edi
0x18001470b  add     rsp, 20h
0x18001470f  pop     rdi
0x180014710  retn
```
