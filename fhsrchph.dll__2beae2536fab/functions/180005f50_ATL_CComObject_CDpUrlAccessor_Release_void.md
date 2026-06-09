# ATL::CComObject<CDpUrlAccessor>::Release(void)

- ea: `0x180005f50`
- end: `0x180005fd4`
- name: `?Release@?$CComObject@VCDpUrlAccessor@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005f50`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDpUrlAccessor>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005f50  mov     [rsp+arg_0], rbx
0x180005f55  push    rdi
0x180005f56  sub     rsp, 20h
0x180005f5a  mov     r8d, [rcx+8]
0x180005f5e  mov     rbx, rcx
0x180005f61  mov     ecx, 7FFFFFFFh
0x180005f66  jmp     short loc_180005F7A
0x180005f68  lea     edx, [r8-1]
0x180005f6c  mov     eax, r8d
0x180005f6f  lock cmpxchg [rbx+8], edx
0x180005f74  jz      short loc_180005F7F
0x180005f76  mov     r8d, [rbx+8]
0x180005f7a  cmp     r8d, ecx
0x180005f7d  jnz     short loc_180005F68
0x180005f7f  lea     edi, [r8-1]
0x180005f83  test    edi, edi
0x180005f85  jnz     short loc_180005FC7
0x180005f87  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005f8e  mov     rax, [rcx]
0x180005f91  mov     rax, [rax+8]
0x180005f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9a  test    rbx, rbx
0x180005f9d  jz      short loc_180005FB4
0x180005f9f  mov     rax, [rbx]
0x180005fa2  lea     edx, [rdi+1]
0x180005fa5  mov     rcx, rbx
0x180005fa8  mov     rax, [rax+98h]
0x180005faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005fbb  mov     rdx, [rcx]
0x180005fbe  mov     rax, [rdx+10h]
0x180005fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc7  mov     rbx, [rsp+28h+arg_0]
0x180005fcc  mov     eax, edi
0x180005fce  add     rsp, 20h
0x180005fd2  pop     rdi
0x180005fd3  retn
```
