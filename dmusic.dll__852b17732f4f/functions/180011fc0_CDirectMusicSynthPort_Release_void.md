# CDirectMusicSynthPort::Release(void)

- ea: `0x180011fc0`
- end: `0x180011ff2`
- name: `?Release@CDirectMusicSynthPort@@UEAAKXZ`
- size: `50`
- prototype: `unsigned int __fastcall(CDirectMusicSynthPort *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800111fc`
- `0x180012000`
- `0x180012020`
- `0x180012040`
- `0x180012060`

## callees

- `0x180011fc0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort::Release(CDirectMusicSynthPort *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 102);
  if ( !v1 && this )
    (*(void (__fastcall **)(CDirectMusicSynthPort *, __int64))(*(_QWORD *)this + 72LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180011fc0  push    rbx
0x180011fc2  sub     rsp, 20h
0x180011fc6  or      ebx, 0FFFFFFFFh
0x180011fc9  lock xadd [rcx+198h], ebx
0x180011fd1  sub     ebx, 1
0x180011fd4  jnz     short loc_180011FEA
0x180011fd6  test    rcx, rcx
0x180011fd9  jz      short loc_180011FEA
0x180011fdb  mov     rdx, [rcx]
0x180011fde  mov     rax, [rdx+48h]
0x180011fe2  lea     edx, [rbx+1]
0x180011fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fea  mov     eax, ebx
0x180011fec  add     rsp, 20h
0x180011ff0  pop     rbx
0x180011ff1  retn
```
