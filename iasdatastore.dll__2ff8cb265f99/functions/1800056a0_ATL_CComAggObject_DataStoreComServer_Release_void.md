# ATL::CComAggObject<DataStoreComServer>::Release(void)

- ea: `0x1800056a0`
- end: `0x180005721`
- name: `?Release@?$CComAggObject@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800056a0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<DataStoreComServer>::Release(volatile signed __int32 *a1)
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
0x1800056a0  mov     [rsp+arg_0], rbx
0x1800056a5  push    rdi
0x1800056a6  sub     rsp, 20h
0x1800056aa  mov     r8d, [rcx+8]
0x1800056ae  mov     rbx, rcx
0x1800056b1  mov     ecx, 7FFFFFFFh
0x1800056b6  jmp     short loc_1800056CA
0x1800056b8  lea     edx, [r8-1]
0x1800056bc  mov     eax, r8d
0x1800056bf  lock cmpxchg [rbx+8], edx
0x1800056c4  jz      short loc_1800056CF
0x1800056c6  mov     r8d, [rbx+8]
0x1800056ca  cmp     r8d, ecx
0x1800056cd  jnz     short loc_1800056B8
0x1800056cf  lea     edi, [r8-1]
0x1800056d3  test    edi, edi
0x1800056d5  jnz     short loc_180005714
0x1800056d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800056de  mov     rax, [rcx]
0x1800056e1  mov     rax, [rax+8]
0x1800056e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ea  test    rbx, rbx
0x1800056ed  jz      short loc_180005701
0x1800056ef  mov     rax, [rbx]
0x1800056f2  lea     edx, [rdi+1]
0x1800056f5  mov     rcx, rbx
0x1800056f8  mov     rax, [rax+18h]
0x1800056fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005701  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005708  mov     rdx, [rcx]
0x18000570b  mov     rax, [rdx+10h]
0x18000570f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005714  mov     rbx, [rsp+28h+arg_0]
0x180005719  mov     eax, edi
0x18000571b  add     rsp, 20h
0x18000571f  pop     rdi
0x180005720  retn
```
