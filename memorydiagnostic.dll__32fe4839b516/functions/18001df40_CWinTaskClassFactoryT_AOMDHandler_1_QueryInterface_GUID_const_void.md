# CWinTaskClassFactoryT<AOMDHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001df40`
- end: `0x18001dfa4`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001df40`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<AOMDHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x18001df40  sub     rsp, 28h
0x18001df44  test    r8, r8
0x18001df47  jnz     short loc_18001DF50
0x18001df49  mov     eax, 80070057h
0x18001df4e  jmp     short loc_18001DF9E
0x18001df50  mov     rax, [rdx]
0x18001df53  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18001df5a  jnz     short loc_18001DF69
0x18001df5c  mov     rax, [rdx+8]
0x18001df60  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18001df67  jz      short loc_18001DF82
0x18001df69  mov     rax, [rdx]
0x18001df6c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18001df73  jnz     short loc_18001DF95
0x18001df75  mov     rax, [rdx+8]
0x18001df79  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18001df80  jnz     short loc_18001DF95
0x18001df82  mov     [r8], rcx
0x18001df85  mov     rax, [rcx]
0x18001df88  mov     rax, [rax+8]
0x18001df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df91  xor     eax, eax
0x18001df93  jmp     short loc_18001DF9E
0x18001df95  and     qword ptr [r8], 0
0x18001df99  mov     eax, 80004002h
0x18001df9e  add     rsp, 28h
0x18001dfa2  retn
```
