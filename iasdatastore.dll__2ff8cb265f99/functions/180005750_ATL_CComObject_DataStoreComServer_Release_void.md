# ATL::CComObject<DataStoreComServer>::Release(void)

- ea: `0x180005750`
- end: `0x1800057d1`
- name: `?Release@?$CComObject@VDataStoreComServer@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005750`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<DataStoreComServer>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005750  mov     [rsp+arg_0], rbx
0x180005755  push    rdi
0x180005756  sub     rsp, 20h
0x18000575a  mov     r8d, [rcx+8]
0x18000575e  mov     rbx, rcx
0x180005761  mov     ecx, 7FFFFFFFh
0x180005766  jmp     short loc_18000577A
0x180005768  lea     edx, [r8-1]
0x18000576c  mov     eax, r8d
0x18000576f  lock cmpxchg [rbx+8], edx
0x180005774  jz      short loc_18000577F
0x180005776  mov     r8d, [rbx+8]
0x18000577a  cmp     r8d, ecx
0x18000577d  jnz     short loc_180005768
0x18000577f  lea     edi, [r8-1]
0x180005783  test    edi, edi
0x180005785  jnz     short loc_1800057C4
0x180005787  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000578e  mov     rax, [rcx]
0x180005791  mov     rax, [rax+8]
0x180005795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000579a  test    rbx, rbx
0x18000579d  jz      short loc_1800057B1
0x18000579f  mov     rax, [rbx]
0x1800057a2  lea     edx, [rdi+1]
0x1800057a5  mov     rcx, rbx
0x1800057a8  mov     rax, [rax+60h]
0x1800057ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800057b8  mov     rdx, [rcx]
0x1800057bb  mov     rax, [rdx+10h]
0x1800057bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c4  mov     rbx, [rsp+28h+arg_0]
0x1800057c9  mov     eax, edi
0x1800057cb  add     rsp, 20h
0x1800057cf  pop     rdi
0x1800057d0  retn
```
