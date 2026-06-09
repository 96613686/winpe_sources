# CEraseEvent::Update(IDispatch *,long,long)

- ea: `0x1400093a0`
- end: `0x1400093cc`
- name: `?Update@CEraseEvent@@UEAAXPEAUIDispatch@@JJ@Z`
- size: `44`
- prototype: `void __fastcall(CEraseEvent *__hidden this, struct IDispatch *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1400093a0`
- `0x140010010`

## pseudocode

```c
void __fastcall CEraseEvent::Update(CEraseEvent *this, struct IDispatch *a2, unsigned int a3, int a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    if ( a4 > 0 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, a3, (unsigned int)a4);
  }
}

```

## disassembly

```asm
0x1400093a0  sub     rsp, 28h
0x1400093a4  mov     rcx, [rcx+70h]
0x1400093a8  mov     r10d, r8d
0x1400093ab  test    rcx, rcx
0x1400093ae  jz      short loc_1400093C7
0x1400093b0  test    r9d, r9d
0x1400093b3  jle     short loc_1400093C7
0x1400093b5  mov     rax, [rcx]
0x1400093b8  mov     r8d, r9d
0x1400093bb  mov     edx, r10d
0x1400093be  mov     rax, [rax+20h]
0x1400093c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093c7  add     rsp, 28h
0x1400093cb  retn
```
