# CDDWORKERTHREADTRACKER::~CDDWORKERTHREADTRACKER(void)

- ea: `0x1400193a8`
- end: `0x1400193d5`
- name: `??1CDDWORKERTHREADTRACKER@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(CDDWORKERTHREADTRACKER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b5f0`

## callees

- `0x1400193a8`
- `0x1400372d0`

## pseudocode

```c
void __fastcall CDDWORKERTHREADTRACKER::~CDDWORKERTHREADTRACKER(CDDWORKERTHREADTRACKER *this)
{
  if ( *((_DWORD *)this + 2) )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)this + 304LL))(
      *(_QWORD *)(*(_QWORD *)this + 2488LL),
      *(_QWORD *)(*(_QWORD *)this + 2504LL));
}

```

## disassembly

```asm
0x1400193a8  sub     rsp, 28h
0x1400193ac  cmp     dword ptr [rcx+8], 0
0x1400193b0  jz      short loc_1400193CF
0x1400193b2  mov     rcx, [rcx]
0x1400193b5  mov     rax, [rcx+130h]
0x1400193bc  mov     rdx, [rcx+9C8h]
0x1400193c3  mov     rcx, [rcx+9B8h]
0x1400193ca  call    _guard_dispatch_icall
0x1400193cf  add     rsp, 28h
0x1400193d3  retn
```
