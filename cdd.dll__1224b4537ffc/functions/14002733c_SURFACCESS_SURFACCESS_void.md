# SURFACCESS::~SURFACCESS(void)

- ea: `0x14002733c`
- end: `0x14002735f`
- name: `??1SURFACCESS@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(SURFACCESS *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`
- `0x140034a60`
- `0x140034b30`
- `0x1400355b0`
- `0x140035630`
- `0x1400357a0`
- `0x1400358d0`
- `0x1400359f0`
- `0x140035a90`
- `0x1400361e0`
- `0x1400363d0`
- `0x140036510`
- `0x1400365a0`
- `0x140036670`
- `0x140036830`
- `0x1400368b0`

## callees

- `0x14002733c`

## pseudocode

```c
void __fastcall SURFACCESS::~SURFACCESS(SURFACCESS *this)
{
  if ( *(_QWORD *)this )
  {
    if ( *((_DWORD *)this + 6) )
    {
      *(_QWORD *)(*(_QWORD *)this + 16LL) = *((_QWORD *)this + 1);
      *(_WORD *)(*(_QWORD *)this + 78LL) &= ~0x4000u;
    }
  }
}

```

## disassembly

```asm
0x14002733c  mov     rdx, [rcx]
0x14002733f  test    rdx, rdx
0x140027342  jz      short locret_14002735E
0x140027344  cmp     dword ptr [rcx+18h], 0
0x140027348  jz      short locret_14002735E
0x14002734a  mov     rax, [rcx+8]
0x14002734e  mov     [rdx+10h], rax
0x140027352  mov     rax, [rcx]
0x140027355  mov     ecx, 0BFFFh
0x14002735a  and     [rax+4Eh], cx
0x14002735e  retn
```
