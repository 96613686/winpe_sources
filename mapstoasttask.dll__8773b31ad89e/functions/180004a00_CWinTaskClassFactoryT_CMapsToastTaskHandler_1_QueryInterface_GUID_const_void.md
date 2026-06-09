# CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004a00`
- end: `0x180004a66`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004a00`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180004a00  sub     rsp, 28h
0x180004a04  test    r8, r8
0x180004a07  jnz     short loc_180004A10
0x180004a09  mov     eax, 80070057h
0x180004a0e  jmp     short loc_180004A61
0x180004a10  mov     rax, [rdx]
0x180004a13  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180004a1a  jnz     short loc_180004A29
0x180004a1c  mov     rax, [rdx+8]
0x180004a20  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180004a27  jz      short loc_180004A42
0x180004a29  mov     rax, [rdx]
0x180004a2c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180004a33  jnz     short loc_180004A55
0x180004a35  mov     rax, [rdx+8]
0x180004a39  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180004a40  jnz     short loc_180004A55
0x180004a42  mov     [r8], rcx
0x180004a45  mov     rax, [rcx]
0x180004a48  mov     rax, [rax+8]
0x180004a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a51  xor     eax, eax
0x180004a53  jmp     short loc_180004A61
0x180004a55  mov     qword ptr [r8], 0
0x180004a5c  mov     eax, 80004002h
0x180004a61  add     rsp, 28h
0x180004a65  retn
```
