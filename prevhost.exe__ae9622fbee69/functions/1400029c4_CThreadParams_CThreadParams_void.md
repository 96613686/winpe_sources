# CThreadParams::~CThreadParams(void)

- ea: `0x1400029c4`
- end: `0x140002a0f`
- name: `??1CThreadParams@@AEAA@XZ`
- size: `75`
- prototype: `void __fastcall(CThreadParams *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004cf0`

## callees

- `0x1400029c4`
- `0x140006010`

## pseudocode

```c
void __fastcall CThreadParams::~CThreadParams(CThreadParams *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CThreadParams::`vftable';
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x1400029c4  push    rbx
0x1400029c6  sub     rsp, 20h
0x1400029ca  lea     rax, ??_7CThreadParams@@6B@; const CThreadParams::`vftable'
0x1400029d1  mov     rbx, rcx
0x1400029d4  mov     [rcx], rax
0x1400029d7  mov     rcx, [rcx+40h]
0x1400029db  test    rcx, rcx
0x1400029de  jz      short loc_1400029EC
0x1400029e0  mov     rax, [rcx]
0x1400029e3  mov     rax, [rax+10h]
0x1400029e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029ec  mov     rcx, [rbx+48h]
0x1400029f0  test    rcx, rcx
0x1400029f3  jz      short loc_140002A09
0x1400029f5  mov     qword ptr [rbx+48h], 0
0x1400029fd  mov     rax, [rcx]
0x140002a00  mov     rax, [rax+10h]
0x140002a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a09  add     rsp, 20h
0x140002a0d  pop     rbx
0x140002a0e  retn
```
