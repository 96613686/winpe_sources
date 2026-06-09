# ATL::CComObject<CFileStream>::Release(void)

- ea: `0x1800070f0`
- end: `0x180007171`
- name: `?Release@?$CComObject@VCFileStream@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800070f0`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFileStream>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp+arg_0], rbx
0x1800070f5  push    rdi
0x1800070f6  sub     rsp, 20h
0x1800070fa  mov     r8d, [rcx+8]
0x1800070fe  mov     rbx, rcx
0x180007101  mov     ecx, 7FFFFFFFh
0x180007106  jmp     short loc_18000711A
0x180007108  lea     edx, [r8-1]
0x18000710c  mov     eax, r8d
0x18000710f  lock cmpxchg [rbx+8], edx
0x180007114  jz      short loc_18000711F
0x180007116  mov     r8d, [rbx+8]
0x18000711a  cmp     r8d, ecx
0x18000711d  jnz     short loc_180007108
0x18000711f  lea     edi, [r8-1]
0x180007123  test    edi, edi
0x180007125  jnz     short loc_180007164
0x180007127  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000712e  mov     rax, [rcx]
0x180007131  mov     rax, [rax+8]
0x180007135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000713a  test    rbx, rbx
0x18000713d  jz      short loc_180007151
0x18000713f  mov     rax, [rbx]
0x180007142  lea     edx, [rdi+1]
0x180007145  mov     rcx, rbx
0x180007148  mov     rax, [rax+70h]
0x18000714c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007151  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007158  mov     rdx, [rcx]
0x18000715b  mov     rax, [rdx+10h]
0x18000715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007164  mov     rbx, [rsp+28h+arg_0]
0x180007169  mov     eax, edi
0x18000716b  add     rsp, 20h
0x18000716f  pop     rdi
0x180007170  retn
```
