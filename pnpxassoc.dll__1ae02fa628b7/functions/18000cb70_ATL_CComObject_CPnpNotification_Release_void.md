# ATL::CComObject<CPnpNotification>::Release(void)

- ea: `0x18000cb70`
- end: `0x18000cbf1`
- name: `?Release@?$CComObject@VCPnpNotification@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000cb70`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpNotification>::Release(volatile signed __int32 *a1)
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
0x18000cb70  mov     [rsp+arg_0], rbx
0x18000cb75  push    rdi
0x18000cb76  sub     rsp, 20h
0x18000cb7a  mov     r8d, [rcx+8]
0x18000cb7e  mov     rbx, rcx
0x18000cb81  mov     ecx, 7FFFFFFFh
0x18000cb86  jmp     short loc_18000CB9A
0x18000cb88  lea     edx, [r8-1]
0x18000cb8c  mov     eax, r8d
0x18000cb8f  lock cmpxchg [rbx+8], edx
0x18000cb94  jz      short loc_18000CB9F
0x18000cb96  mov     r8d, [rbx+8]
0x18000cb9a  cmp     r8d, ecx
0x18000cb9d  jnz     short loc_18000CB88
0x18000cb9f  lea     edi, [r8-1]
0x18000cba3  test    edi, edi
0x18000cba5  jnz     short loc_18000CBE4
0x18000cba7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cbae  mov     rax, [rcx]
0x18000cbb1  mov     rax, [rax+8]
0x18000cbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbba  test    rbx, rbx
0x18000cbbd  jz      short loc_18000CBD1
0x18000cbbf  mov     rax, [rbx]
0x18000cbc2  lea     edx, [rdi+1]
0x18000cbc5  mov     rcx, rbx
0x18000cbc8  mov     rax, [rax+30h]
0x18000cbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cbd8  mov     rdx, [rcx]
0x18000cbdb  mov     rax, [rdx+10h]
0x18000cbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe4  mov     rbx, [rsp+28h+arg_0]
0x18000cbe9  mov     eax, edi
0x18000cbeb  add     rsp, 20h
0x18000cbef  pop     rdi
0x18000cbf0  retn
```
