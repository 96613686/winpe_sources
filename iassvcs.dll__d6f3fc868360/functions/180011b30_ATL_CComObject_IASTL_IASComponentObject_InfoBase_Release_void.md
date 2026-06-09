# ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release(void)

- ea: `0x180011b30`
- end: `0x180011bb4`
- name: `?Release@?$CComObject@V?$IASComponentObject@VInfoBase@@@IASTL@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180011b30`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<IASTL::IASComponentObject<InfoBase>>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 128LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180011b30  mov     [rsp+arg_0], rbx
0x180011b35  push    rdi
0x180011b36  sub     rsp, 20h
0x180011b3a  mov     r8d, [rcx+8]
0x180011b3e  mov     rbx, rcx
0x180011b41  mov     ecx, 7FFFFFFFh
0x180011b46  jmp     short loc_180011B5A
0x180011b48  lea     edx, [r8-1]
0x180011b4c  mov     eax, r8d
0x180011b4f  lock cmpxchg [rbx+8], edx
0x180011b54  jz      short loc_180011B5F
0x180011b56  mov     r8d, [rbx+8]
0x180011b5a  cmp     r8d, ecx
0x180011b5d  jnz     short loc_180011B48
0x180011b5f  lea     edi, [r8-1]
0x180011b63  test    edi, edi
0x180011b65  jnz     short loc_180011BA7
0x180011b67  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011b6e  mov     rax, [rcx]
0x180011b71  mov     rax, [rax+8]
0x180011b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7a  test    rbx, rbx
0x180011b7d  jz      short loc_180011B94
0x180011b7f  mov     rax, [rbx]
0x180011b82  lea     edx, [rdi+1]
0x180011b85  mov     rcx, rbx
0x180011b88  mov     rax, [rax+80h]
0x180011b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b94  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011b9b  mov     rdx, [rcx]
0x180011b9e  mov     rax, [rdx+10h]
0x180011ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba7  mov     rbx, [rsp+28h+arg_0]
0x180011bac  mov     eax, edi
0x180011bae  add     rsp, 20h
0x180011bb2  pop     rdi
0x180011bb3  retn
```
