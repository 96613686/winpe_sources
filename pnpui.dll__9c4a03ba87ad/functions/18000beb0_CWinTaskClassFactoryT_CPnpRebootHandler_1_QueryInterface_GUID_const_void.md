# CWinTaskClassFactoryT<CPnpRebootHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000beb0`
- end: `0x18000bf16`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000beb0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
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
0x18000beb0  sub     rsp, 28h
0x18000beb4  test    r8, r8
0x18000beb7  jnz     short loc_18000BEC0
0x18000beb9  mov     eax, 80070057h
0x18000bebe  jmp     short loc_18000BF11
0x18000bec0  mov     rax, [rdx]
0x18000bec3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000beca  jnz     short loc_18000BED9
0x18000becc  mov     rax, [rdx+8]
0x18000bed0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000bed7  jz      short loc_18000BEF2
0x18000bed9  mov     rax, [rdx]
0x18000bedc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000bee3  jnz     short loc_18000BF05
0x18000bee5  mov     rax, [rdx+8]
0x18000bee9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000bef0  jnz     short loc_18000BF05
0x18000bef2  mov     [r8], rcx
0x18000bef5  mov     rax, [rcx]
0x18000bef8  mov     rax, [rax+8]
0x18000befc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf01  xor     eax, eax
0x18000bf03  jmp     short loc_18000BF11
0x18000bf05  mov     qword ptr [r8], 0
0x18000bf0c  mov     eax, 80004002h
0x18000bf11  add     rsp, 28h
0x18000bf15  retn
```
