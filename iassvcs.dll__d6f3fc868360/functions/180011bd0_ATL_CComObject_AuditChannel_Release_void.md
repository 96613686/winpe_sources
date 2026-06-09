# ATL::CComObject<AuditChannel>::Release(void)

- ea: `0x180011bd0`
- end: `0x180011c51`
- name: `?Release@?$CComObject@VAuditChannel@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011c60`

## callees

- `0x180011bd0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AuditChannel>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 4, i - 1, i);
        i = *((_DWORD *)a1 + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180011bd0  mov     [rsp+arg_0], rbx
0x180011bd5  push    rdi
0x180011bd6  sub     rsp, 20h
0x180011bda  mov     r8d, [rcx+10h]
0x180011bde  mov     rbx, rcx
0x180011be1  mov     ecx, 7FFFFFFFh
0x180011be6  jmp     short loc_180011BFA
0x180011be8  lea     edx, [r8-1]
0x180011bec  mov     eax, r8d
0x180011bef  lock cmpxchg [rbx+10h], edx
0x180011bf4  jz      short loc_180011BFF
0x180011bf6  mov     r8d, [rbx+10h]
0x180011bfa  cmp     r8d, ecx
0x180011bfd  jnz     short loc_180011BE8
0x180011bff  lea     edi, [r8-1]
0x180011c03  test    edi, edi
0x180011c05  jnz     short loc_180011C44
0x180011c07  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011c0e  mov     rax, [rcx]
0x180011c11  mov     rax, [rax+8]
0x180011c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c1a  test    rbx, rbx
0x180011c1d  jz      short loc_180011C31
0x180011c1f  mov     rax, [rbx]
0x180011c22  lea     edx, [rdi+1]
0x180011c25  mov     rcx, rbx
0x180011c28  mov     rax, [rax+28h]
0x180011c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c31  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011c38  mov     rdx, [rcx]
0x180011c3b  mov     rax, [rdx+10h]
0x180011c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c44  mov     rbx, [rsp+28h+arg_0]
0x180011c49  mov     eax, edi
0x180011c4b  add     rsp, 20h
0x180011c4f  pop     rdi
0x180011c50  retn
```
