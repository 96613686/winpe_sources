# CWinTaskClassFactoryT<CpnppolicyHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002f50`
- end: `0x180002fb6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002f50`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180002f50  sub     rsp, 28h
0x180002f54  test    r8, r8
0x180002f57  jnz     short loc_180002F60
0x180002f59  mov     eax, 80070057h
0x180002f5e  jmp     short loc_180002FB1
0x180002f60  mov     rax, [rdx]
0x180002f63  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180002f6a  jnz     short loc_180002F79
0x180002f6c  mov     rax, [rdx+8]
0x180002f70  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180002f77  jz      short loc_180002F92
0x180002f79  mov     rax, [rdx]
0x180002f7c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002f83  jnz     short loc_180002FA5
0x180002f85  mov     rax, [rdx+8]
0x180002f89  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002f90  jnz     short loc_180002FA5
0x180002f92  mov     [r8], rcx
0x180002f95  mov     rax, [rcx]
0x180002f98  mov     rax, [rax+8]
0x180002f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa1  xor     eax, eax
0x180002fa3  jmp     short loc_180002FB1
0x180002fa5  mov     qword ptr [r8], 0
0x180002fac  mov     eax, 80004002h
0x180002fb1  add     rsp, 28h
0x180002fb5  retn
```
