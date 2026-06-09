# ATL::CComAggObject<CDpSearchProtocol>::Release(void)

- ea: `0x180005e10`
- end: `0x180005e91`
- name: `?Release@?$CComAggObject@VCDpSearchProtocol@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005e10`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CDpSearchProtocol>::Release(volatile signed __int32 *a1)
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
0x180005e10  mov     [rsp+arg_0], rbx
0x180005e15  push    rdi
0x180005e16  sub     rsp, 20h
0x180005e1a  mov     r8d, [rcx+8]
0x180005e1e  mov     rbx, rcx
0x180005e21  mov     ecx, 7FFFFFFFh
0x180005e26  jmp     short loc_180005E3A
0x180005e28  lea     edx, [r8-1]
0x180005e2c  mov     eax, r8d
0x180005e2f  lock cmpxchg [rbx+8], edx
0x180005e34  jz      short loc_180005E3F
0x180005e36  mov     r8d, [rbx+8]
0x180005e3a  cmp     r8d, ecx
0x180005e3d  jnz     short loc_180005E28
0x180005e3f  lea     edi, [r8-1]
0x180005e43  test    edi, edi
0x180005e45  jnz     short loc_180005E84
0x180005e47  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005e4e  mov     rax, [rcx]
0x180005e51  mov     rax, [rax+8]
0x180005e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5a  test    rbx, rbx
0x180005e5d  jz      short loc_180005E71
0x180005e5f  mov     rax, [rbx]
0x180005e62  lea     edx, [rdi+1]
0x180005e65  mov     rcx, rbx
0x180005e68  mov     rax, [rax+18h]
0x180005e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e71  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005e78  mov     rdx, [rcx]
0x180005e7b  mov     rax, [rdx+10h]
0x180005e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e84  mov     rbx, [rsp+28h+arg_0]
0x180005e89  mov     eax, edi
0x180005e8b  add     rsp, 20h
0x180005e8f  pop     rdi
0x180005e90  retn
```
