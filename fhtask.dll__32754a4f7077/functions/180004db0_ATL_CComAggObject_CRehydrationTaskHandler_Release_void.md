# ATL::CComAggObject<CRehydrationTaskHandler>::Release(void)

- ea: `0x180004db0`
- end: `0x180004e31`
- name: `?Release@?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004db0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRehydrationTaskHandler>::Release(volatile signed __int32 *a1)
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
0x180004db0  mov     [rsp+arg_0], rbx
0x180004db5  push    rdi
0x180004db6  sub     rsp, 20h
0x180004dba  mov     r8d, [rcx+8]
0x180004dbe  mov     rbx, rcx
0x180004dc1  mov     ecx, 7FFFFFFFh
0x180004dc6  jmp     short loc_180004DDA
0x180004dc8  lea     edx, [r8-1]
0x180004dcc  mov     eax, r8d
0x180004dcf  lock cmpxchg [rbx+8], edx
0x180004dd4  jz      short loc_180004DDF
0x180004dd6  mov     r8d, [rbx+8]
0x180004dda  cmp     r8d, ecx
0x180004ddd  jnz     short loc_180004DC8
0x180004ddf  lea     edi, [r8-1]
0x180004de3  test    edi, edi
0x180004de5  jnz     short loc_180004E24
0x180004de7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004dee  mov     rax, [rcx]
0x180004df1  mov     rax, [rax+8]
0x180004df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dfa  test    rbx, rbx
0x180004dfd  jz      short loc_180004E11
0x180004dff  mov     rax, [rbx]
0x180004e02  lea     edx, [rdi+1]
0x180004e05  mov     rcx, rbx
0x180004e08  mov     rax, [rax+18h]
0x180004e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e11  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004e18  mov     rdx, [rcx]
0x180004e1b  mov     rax, [rdx+10h]
0x180004e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e24  mov     rbx, [rsp+28h+arg_0]
0x180004e29  mov     eax, edi
0x180004e2b  add     rsp, 20h
0x180004e2f  pop     rdi
0x180004e30  retn
```
