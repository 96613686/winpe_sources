# wistd::unique_ptr<_W32KCDD_INTERFACE,wistd::default_delete<_W32KCDD_INTERFACE>>::reset(_W32KCDD_INTERFACE *)

- ea: `0x140027970`
- end: `0x140027994`
- name: `?reset@?$unique_ptr@U_W32KCDD_INTERFACE@@U?$default_delete@U_W32KCDD_INTERFACE@@@wistd@@@wistd@@QEAAXPEAU_W32KCDD_INTERFACE@@@Z`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a4f0`

## callees

- `0x140027970`

## import_xrefs

- `WIN32K!EngFreeMem` at `0x140027982`
- `WIN32K!EngFreeMem` at `0x140027982`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_W32KCDD_INTERFACE,wistd::default_delete<_W32KCDD_INTERFACE>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    EngFreeMem(v2);
}

```

## disassembly

```asm
0x140027970  sub     rsp, 28h
0x140027974  mov     rax, [rcx]
0x140027977  mov     [rcx], rdx
0x14002797a  test    rax, rax
0x14002797d  jz      short loc_14002798E
0x14002797f  mov     rcx, rax; pv
0x140027982  call    cs:__imp_EngFreeMem
0x140027989  nop     dword ptr [rax+rax+00h]
0x14002798e  add     rsp, 28h
0x140027992  retn
```
