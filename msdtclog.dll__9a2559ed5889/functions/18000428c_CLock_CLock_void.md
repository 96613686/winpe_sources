# CLock::~CLock(void)

- ea: `0x18000428c`
- end: `0x1800042ab`
- name: `??1CLock@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(CLock *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180013090`
- `0x180013194`
- `0x18001320d`
- `0x18001330f`
- `0x1800136aa`
- `0x180013740`
- `0x1800137a6`
- `0x1800137b8`
- `0x1800137ca`
- `0x1800137dc`
- `0x180013de2`
- `0x180014132`

## callees

- `0x18000428c`
- `0x180015010`

## pseudocode

```c
void __fastcall CLock::~CLock(CLock *this)
{
  if ( *(_DWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18000428c  sub     rsp, 28h
0x180004290  cmp     dword ptr [rcx], 0
0x180004293  jz      short loc_1800042A6
0x180004295  mov     rcx, [rcx+8]
0x180004299  mov     rax, [rcx]
0x18000429c  mov     rax, [rax+8]
0x1800042a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a5  nop
0x1800042a6  add     rsp, 28h
0x1800042aa  retn
```
