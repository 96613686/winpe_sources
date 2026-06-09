# CINDFHelperClassImpl::GetComponentName(ushort * *)

- ea: `0x180007140`
- end: `0x180007168`
- name: `?GetComponentName@CINDFHelperClassImpl@@UEAAJPEAPEAG@Z`
- size: `40`
- prototype: `__int64 __fastcall(CINDFHelperClassImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007140`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CINDFHelperClassImpl::GetComponentName(CINDFHelperClassImpl *this, unsigned __int16 **a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 8) + 24LL))(
           *((_QWORD *)this + 8),
           a2);
}

```

## disassembly

```asm
0x180007140  sub     rsp, 28h
0x180007144  mov     rcx, [rcx+40h]
0x180007148  mov     rax, [rcx]
0x18000714b  mov     rax, [rax+18h]
0x18000714f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007154  jmp     short loc_180007162
0x180007156  mov     eax, 8007000Eh
0x18000715b  jmp     short loc_180007162
0x18000715d  mov     eax, 80004005h
0x180007162  add     rsp, 28h
0x180007166  retn
```
