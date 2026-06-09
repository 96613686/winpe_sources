# CWinTaskClassFactoryT<CmCleanupWim,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005340`
- end: `0x1800053a6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180005340`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 && a2[1] == *(_QWORD *)IID_IClassFactory.Data4
    || *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180005340  sub     rsp, 28h
0x180005344  test    r8, r8
0x180005347  jnz     short loc_180005350
0x180005349  mov     eax, 80070057h
0x18000534e  jmp     short loc_1800053A1
0x180005350  mov     rax, [rdx]
0x180005353  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000535a  jnz     short loc_180005369
0x18000535c  mov     rax, [rdx+8]
0x180005360  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180005367  jz      short loc_180005382
0x180005369  mov     rax, [rdx]
0x18000536c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180005373  jnz     short loc_180005395
0x180005375  mov     rax, [rdx+8]
0x180005379  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180005380  jnz     short loc_180005395
0x180005382  mov     [r8], rcx
0x180005385  mov     rax, [rcx]
0x180005388  mov     rax, [rax+8]
0x18000538c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005391  xor     eax, eax
0x180005393  jmp     short loc_1800053A1
0x180005395  mov     qword ptr [r8], 0
0x18000539c  mov     eax, 80004002h
0x1800053a1  add     rsp, 28h
0x1800053a5  retn
```
