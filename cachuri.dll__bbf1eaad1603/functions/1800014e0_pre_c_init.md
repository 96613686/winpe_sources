# pre_c_init

- ea: `0x1800014e0`
- end: `0x180001517`
- name: `pre_c_init`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800014e0`

## import_xrefs

- `msvcrt!malloc` at `0x1800014e9`
- `msvcrt!malloc` at `0x1800014e9`

## pseudocode

```c
__int64 pre_c_init()
{
  _QWORD *v0; // rax

  v0 = malloc(0x100u);
  _onexitbegin = v0;
  _onexitend = (__int64)v0;
  if ( !v0 )
    return 1;
  *v0 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800014e0  sub     rsp, 28h
0x1800014e4  mov     ecx, 100h; Size
0x1800014e9  call    cs:__imp_malloc
0x1800014ef  mov     cs:__onexitbegin, rax
0x1800014f6  mov     cs:__onexitend, rax
0x1800014fd  test    rax, rax
0x180001500  jnz     short loc_180001509
0x180001502  mov     eax, 1
0x180001507  jmp     short loc_180001512
0x180001509  mov     qword ptr [rax], 0
0x180001510  xor     eax, eax
0x180001512  add     rsp, 28h
0x180001516  retn
```
