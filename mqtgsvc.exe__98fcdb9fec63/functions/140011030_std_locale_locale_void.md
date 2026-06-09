# std::locale::~locale(void)

- ea: `0x140011030`
- end: `0x140011062`
- name: `??1locale@std@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(std::locale::facet **this)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x1400020f8`
- `0x140011104`
- `0x140011554`
- `0x1400127c0`
- `0x1400133e0`
- `0x1400144f0`
- `0x140014dbc`
- `0x14001e8db`
- `0x14001eb99`
- `0x14001ec3d`
- `0x14001ec85`
- `0x14001ecbb`
- `0x14001f0c0`

## callees

- `0x140011030`
- `0x14001257c`
- `0x140020010`

## pseudocode

```c
void __fastcall std::locale::~locale(std::locale::facet **this)
{
  std::locale::facet *v1; // rcx
  struct std::locale::facet *v2; // rax

  v1 = *this;
  if ( v1 )
  {
    v2 = std::locale::facet::_Decref(v1);
    if ( v2 )
      (**(void (__fastcall ***)(struct std::locale::facet *, __int64))v2)(v2, 1);
  }
}

```

## disassembly

```asm
0x140011030  sub     rsp, 28h
0x140011034  mov     rcx, [rcx]; this
0x140011037  test    rcx, rcx
0x14001103a  jz      short loc_14001105D
0x14001103c  call    ?_Decref@facet@locale@std@@QEAAPEAV123@XZ; std::locale::facet::_Decref(void)
0x140011041  mov     r8, rax
0x140011044  test    rax, rax
0x140011047  jz      short loc_14001105D
0x140011049  mov     rcx, [rax]
0x14001104c  mov     rax, [rcx]
0x14001104f  mov     edx, 1
0x140011054  mov     rcx, r8
0x140011057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001105c  nop
0x14001105d  add     rsp, 28h
0x140011061  retn
```
