# CWinTaskClassFactoryT<AOMDHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001ccb0`
- end: `0x18001cd16`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001ccb0`
- `0x180023010`

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
0x18001ccb0  sub     rsp, 28h
0x18001ccb4  test    r8, r8
0x18001ccb7  jnz     short loc_18001CCC0
0x18001ccb9  mov     eax, 80070057h
0x18001ccbe  jmp     short loc_18001CD11
0x18001ccc0  mov     rax, [rdx]
0x18001ccc3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18001ccca  jnz     short loc_18001CCD9
0x18001cccc  mov     rax, [rdx+8]
0x18001ccd0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18001ccd7  jz      short loc_18001CCF2
0x18001ccd9  mov     rax, [rdx]
0x18001ccdc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18001cce3  jnz     short loc_18001CD05
0x18001cce5  mov     rax, [rdx+8]
0x18001cce9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18001ccf0  jnz     short loc_18001CD05
0x18001ccf2  mov     [r8], rcx
0x18001ccf5  mov     rax, [rcx]
0x18001ccf8  mov     rax, [rax+8]
0x18001ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd01  xor     eax, eax
0x18001cd03  jmp     short loc_18001CD11
0x18001cd05  mov     qword ptr [r8], 0
0x18001cd0c  mov     eax, 80004002h
0x18001cd11  add     rsp, 28h
0x18001cd15  retn
```
