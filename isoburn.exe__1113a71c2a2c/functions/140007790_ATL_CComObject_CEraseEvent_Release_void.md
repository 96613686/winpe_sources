# ATL::CComObject<CEraseEvent>::Release(void)

- ea: `0x140007790`
- end: `0x140007811`
- name: `?Release@?$CComObject@VCEraseEvent@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007820`

## callees

- `0x140007790`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEraseEvent>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 14);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 14, i - 1, i);
        i = *((_DWORD *)a1 + 14) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140007790  mov     [rsp+arg_0], rbx
0x140007795  push    rdi
0x140007796  sub     rsp, 20h
0x14000779a  mov     r8d, [rcx+38h]
0x14000779e  mov     rbx, rcx
0x1400077a1  mov     ecx, 7FFFFFFFh
0x1400077a6  jmp     short loc_1400077BA
0x1400077a8  lea     edx, [r8-1]
0x1400077ac  mov     eax, r8d
0x1400077af  lock cmpxchg [rbx+38h], edx
0x1400077b4  jz      short loc_1400077BF
0x1400077b6  mov     r8d, [rbx+38h]
0x1400077ba  cmp     r8d, ecx
0x1400077bd  jnz     short loc_1400077A8
0x1400077bf  lea     edi, [r8-1]
0x1400077c3  test    edi, edi
0x1400077c5  jnz     short loc_140007804
0x1400077c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400077ce  mov     rax, [rcx]
0x1400077d1  mov     rax, [rax+8]
0x1400077d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077da  test    rbx, rbx
0x1400077dd  jz      short loc_1400077F1
0x1400077df  mov     rax, [rbx]
0x1400077e2  lea     edx, [rdi+1]
0x1400077e5  mov     rcx, rbx
0x1400077e8  mov     rax, [rax+40h]
0x1400077ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400077f8  mov     rdx, [rcx]
0x1400077fb  mov     rax, [rdx+10h]
0x1400077ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007804  mov     rbx, [rsp+28h+arg_0]
0x140007809  mov     eax, edi
0x14000780b  add     rsp, 20h
0x14000780f  pop     rdi
0x140007810  retn
```
