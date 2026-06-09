# CPopupCommand::get_Handler(IPopupCommandHandler * *)

- ea: `0x180002950`
- end: `0x180002989`
- name: `?get_Handler@CPopupCommand@@UEAAJPEAPEAUIPopupCommandHandler@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(CPopupCommand *__hidden this, struct IPopupCommandHandler **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002950`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CPopupCommand::get_Handler(CPopupCommand *this, struct IPopupCommandHandler **a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  *a2 = (struct IPopupCommandHandler *)*((_QWORD *)this + 3);
  return 0;
}

```

## disassembly

```asm
0x180002950  mov     [rsp+arg_0], rbx
0x180002955  push    rdi
0x180002956  sub     rsp, 20h
0x18000295a  mov     rbx, rcx
0x18000295d  mov     rdi, rdx
0x180002960  mov     rcx, [rcx+18h]
0x180002964  test    rcx, rcx
0x180002967  jz      short loc_180002975
0x180002969  mov     rax, [rcx]
0x18000296c  mov     rax, [rax+8]
0x180002970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002975  mov     rax, [rbx+18h]
0x180002979  mov     rbx, [rsp+28h+arg_0]
0x18000297e  mov     [rdi], rax
0x180002981  xor     eax, eax
0x180002983  add     rsp, 20h
0x180002987  pop     rdi
0x180002988  retn
```
