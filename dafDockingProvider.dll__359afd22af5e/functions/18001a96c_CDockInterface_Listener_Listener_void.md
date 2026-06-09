# CDockInterface::Listener::~Listener(void)

- ea: `0x18001a96c`
- end: `0x18001a996`
- name: `??1Listener@CDockInterface@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(CDockInterface::Listener *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a884`
- `0x18001be10`
- `0x18001c330`
- `0x18001c544`
- `0x18001e1c3`

## callees

- `0x18001a96c`
- `0x18001f010`

## pseudocode

```c
void __fastcall CDockInterface::Listener::~Listener(CDockInterface::Listener *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18001a96c  push    rbx
0x18001a96e  sub     rsp, 20h
0x18001a972  mov     rbx, rcx
0x18001a975  mov     rcx, [rcx]
0x18001a978  test    rcx, rcx
0x18001a97b  jz      short loc_18001A990
0x18001a97d  mov     rax, [rcx]
0x18001a980  mov     rax, [rax+10h]
0x18001a984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a989  mov     qword ptr [rbx], 0
0x18001a990  add     rsp, 20h
0x18001a994  pop     rbx
0x18001a995  retn
```
