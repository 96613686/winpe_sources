# CADMCOMW::UnmarshalInterface(IMSAdminBaseW * *)

- ea: `0x180009a90`
- end: `0x180009abc`
- name: `?UnmarshalInterface@CADMCOMW@@UEAAJPEAPEAUIMSAdminBaseW@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, struct IMSAdminBaseW **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::UnmarshalInterface(struct IMSAdminBaseW *this, struct IMSAdminBaseW **a2)
{
  ((void (__fastcall *)(struct IMSAdminBaseW *))this->lpVtbl->AddRef)(this);
  *a2 = this;
  return 0;
}

```

## disassembly

```asm
0x180009a90  mov     [rsp+arg_0], rbx
0x180009a95  push    rdi
0x180009a96  sub     rsp, 20h
0x180009a9a  mov     rax, [rcx]
0x180009a9d  mov     rdi, rdx
0x180009aa0  mov     rbx, rcx
0x180009aa3  mov     rax, [rax+8]
0x180009aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aac  mov     [rdi], rbx
0x180009aaf  xor     eax, eax
0x180009ab1  mov     rbx, [rsp+28h+arg_0]
0x180009ab6  add     rsp, 20h
0x180009aba  pop     rdi
0x180009abb  retn
```
