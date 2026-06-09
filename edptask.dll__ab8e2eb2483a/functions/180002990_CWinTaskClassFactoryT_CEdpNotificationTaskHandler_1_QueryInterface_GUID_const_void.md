# CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002990`
- end: `0x1800029f6`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002990`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
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
0x180002990  sub     rsp, 28h
0x180002994  test    r8, r8
0x180002997  jnz     short loc_1800029A0
0x180002999  mov     eax, 80070057h
0x18000299e  jmp     short loc_1800029F1
0x1800029a0  mov     rax, [rdx]
0x1800029a3  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800029aa  jnz     short loc_1800029B9
0x1800029ac  mov     rax, [rdx+8]
0x1800029b0  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800029b7  jz      short loc_1800029D2
0x1800029b9  mov     rax, [rdx]
0x1800029bc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800029c3  jnz     short loc_1800029E5
0x1800029c5  mov     rax, [rdx+8]
0x1800029c9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800029d0  jnz     short loc_1800029E5
0x1800029d2  mov     [r8], rcx
0x1800029d5  mov     rax, [rcx]
0x1800029d8  mov     rax, [rax+8]
0x1800029dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e1  xor     eax, eax
0x1800029e3  jmp     short loc_1800029F1
0x1800029e5  mov     qword ptr [r8], 0
0x1800029ec  mov     eax, 80004002h
0x1800029f1  add     rsp, 28h
0x1800029f5  retn
```
