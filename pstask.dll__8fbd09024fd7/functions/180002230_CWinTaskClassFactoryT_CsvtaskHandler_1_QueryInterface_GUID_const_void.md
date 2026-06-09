# CWinTaskClassFactoryT<CsvtaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002230`
- end: `0x180002296`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCsvtaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002230`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CsvtaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180002230  sub     rsp, 28h
0x180002234  test    r8, r8
0x180002237  jnz     short loc_180002240
0x180002239  mov     eax, 80070057h
0x18000223e  jmp     short loc_180002291
0x180002240  mov     rax, [rdx]
0x180002243  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000224a  jnz     short loc_180002259
0x18000224c  mov     rax, [rdx+8]
0x180002250  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180002257  jz      short loc_180002272
0x180002259  mov     rax, [rdx]
0x18000225c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002263  jnz     short loc_180002285
0x180002265  mov     rax, [rdx+8]
0x180002269  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002270  jnz     short loc_180002285
0x180002272  mov     [r8], rcx
0x180002275  mov     rax, [rcx]
0x180002278  mov     rax, [rax+8]
0x18000227c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002281  xor     eax, eax
0x180002283  jmp     short loc_180002291
0x180002285  mov     qword ptr [r8], 0
0x18000228c  mov     eax, 80004002h
0x180002291  add     rsp, 28h
0x180002295  retn
```
