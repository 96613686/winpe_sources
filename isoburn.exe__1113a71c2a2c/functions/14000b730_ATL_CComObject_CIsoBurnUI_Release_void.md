# ATL::CComObject<CIsoBurnUI>::Release(void)

- ea: `0x14000b730`
- end: `0x14000b7b2`
- name: `?Release@?$CComObject@VCIsoBurnUI@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b730`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurnUI>::Release(__int64 a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *(_DWORD *)(a1 + 8);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), i - 1, i);
        i = *(_DWORD *)(a1 + 8) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 != 64 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 - 64) + 8LL))(a1 - 64, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x14000b730  mov     [rsp+arg_0], rbx
0x14000b735  push    rdi
0x14000b736  sub     rsp, 20h
0x14000b73a  mov     r8d, [rcx+8]
0x14000b73e  mov     rbx, rcx
0x14000b741  mov     ecx, 7FFFFFFFh
0x14000b746  jmp     short loc_14000B75A
0x14000b748  lea     edx, [r8-1]
0x14000b74c  mov     eax, r8d
0x14000b74f  lock cmpxchg [rbx+8], edx
0x14000b754  jz      short loc_14000B75F
0x14000b756  mov     r8d, [rbx+8]
0x14000b75a  cmp     r8d, ecx
0x14000b75d  jnz     short loc_14000B748
0x14000b75f  lea     edi, [r8-1]
0x14000b763  test    edi, edi
0x14000b765  jnz     short loc_14000B7A5
0x14000b767  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000b76e  mov     rax, [rcx]
0x14000b771  mov     rax, [rax+8]
0x14000b775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b77a  lea     rcx, [rbx-40h]
0x14000b77e  test    rcx, rcx
0x14000b781  jz      short loc_14000B792
0x14000b783  mov     rax, [rcx]
0x14000b786  lea     edx, [rdi+1]
0x14000b789  mov     rax, [rax+8]
0x14000b78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b792  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000b799  mov     rdx, [rcx]
0x14000b79c  mov     rax, [rdx+10h]
0x14000b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7a5  mov     rbx, [rsp+28h+arg_0]
0x14000b7aa  mov     eax, edi
0x14000b7ac  add     rsp, 20h
0x14000b7b0  pop     rdi
0x14000b7b1  retn
```
