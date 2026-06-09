# ATL::CComObject<CPnpxPairingHandler>::Release(void)

- ea: `0x180008510`
- end: `0x180008591`
- name: `?Release@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800085a0`
- `0x1800085b0`

## callees

- `0x180008510`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 6, i - 1, i);
        i = *((_DWORD *)a1 + 6) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180008510  mov     [rsp+arg_0], rbx
0x180008515  push    rdi
0x180008516  sub     rsp, 20h
0x18000851a  mov     r8d, [rcx+18h]
0x18000851e  mov     rbx, rcx
0x180008521  mov     ecx, 7FFFFFFFh
0x180008526  jmp     short loc_18000853A
0x180008528  lea     edx, [r8-1]
0x18000852c  mov     eax, r8d
0x18000852f  lock cmpxchg [rbx+18h], edx
0x180008534  jz      short loc_18000853F
0x180008536  mov     r8d, [rbx+18h]
0x18000853a  cmp     r8d, ecx
0x18000853d  jnz     short loc_180008528
0x18000853f  lea     edi, [r8-1]
0x180008543  test    edi, edi
0x180008545  jnz     short loc_180008584
0x180008547  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000854e  mov     rax, [rcx]
0x180008551  mov     rax, [rax+8]
0x180008555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000855a  test    rbx, rbx
0x18000855d  jz      short loc_180008571
0x18000855f  mov     rax, [rbx]
0x180008562  lea     edx, [rdi+1]
0x180008565  mov     rcx, rbx
0x180008568  mov     rax, [rax+20h]
0x18000856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008571  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008578  mov     rdx, [rcx]
0x18000857b  mov     rax, [rdx+10h]
0x18000857f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008584  mov     rbx, [rsp+28h+arg_0]
0x180008589  mov     eax, edi
0x18000858b  add     rsp, 20h
0x18000858f  pop     rdi
0x180008590  retn
```
