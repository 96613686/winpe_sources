# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180001b50`
- end: `0x180001bb4`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001b50`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x180001b50  sub     rsp, 28h
0x180001b54  test    r8, r8
0x180001b57  jnz     short loc_180001B60
0x180001b59  mov     eax, 80070057h
0x180001b5e  jmp     short loc_180001BAE
0x180001b60  mov     rax, [rdx]
0x180001b63  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180001b6a  jnz     short loc_180001B79
0x180001b6c  mov     rax, [rdx+8]
0x180001b70  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180001b77  jz      short loc_180001B92
0x180001b79  mov     rax, [rdx]
0x180001b7c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180001b83  jnz     short loc_180001BA5
0x180001b85  mov     rax, [rdx+8]
0x180001b89  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180001b90  jnz     short loc_180001BA5
0x180001b92  mov     [r8], rcx
0x180001b95  mov     rax, [rcx]
0x180001b98  mov     rax, [rax+8]
0x180001b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba1  xor     eax, eax
0x180001ba3  jmp     short loc_180001BAE
0x180001ba5  and     qword ptr [r8], 0
0x180001ba9  mov     eax, 80004002h
0x180001bae  add     rsp, 28h
0x180001bb2  retn
```
