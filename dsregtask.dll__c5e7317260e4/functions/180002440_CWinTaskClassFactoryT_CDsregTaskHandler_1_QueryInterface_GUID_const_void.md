# CWinTaskClassFactoryT<CDsregTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002440`
- end: `0x1800024a6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCDsregTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002440`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDsregTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180002440  sub     rsp, 28h
0x180002444  test    r8, r8
0x180002447  jnz     short loc_180002450
0x180002449  mov     eax, 80070057h
0x18000244e  jmp     short loc_1800024A1
0x180002450  mov     rax, [rdx]
0x180002453  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000245a  jnz     short loc_180002469
0x18000245c  mov     rax, [rdx+8]
0x180002460  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180002467  jz      short loc_180002482
0x180002469  mov     rax, [rdx]
0x18000246c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002473  jnz     short loc_180002495
0x180002475  mov     rax, [rdx+8]
0x180002479  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002480  jnz     short loc_180002495
0x180002482  mov     [r8], rcx
0x180002485  mov     rax, [rcx]
0x180002488  mov     rax, [rax+8]
0x18000248c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002491  xor     eax, eax
0x180002493  jmp     short loc_1800024A1
0x180002495  mov     qword ptr [r8], 0
0x18000249c  mov     eax, 80004002h
0x1800024a1  add     rsp, 28h
0x1800024a5  retn
```
