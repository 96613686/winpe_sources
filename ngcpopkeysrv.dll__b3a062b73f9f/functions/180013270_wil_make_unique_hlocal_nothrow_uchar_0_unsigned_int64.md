# wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x180013270`
- end: `0x1800132b0`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180013834`
- `0x180013994`
- `0x180013b38`
- `0x180013c98`
- `0x180013e3c`
- `0x1800140bc`
- `0x1800141e4`
- `0x1800146fc`
- `0x18001496c`
- `0x1800181a0`
- `0x180018d9c`
- `0x18001e330`
- `0x18001ea50`
- `0x18001ed50`
- `0x18001f050`
- `0x180022a64`
- `0x180022ef4`
- `0x180023124`

## callees

- `0x180013270`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013282`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013282`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rdx

  v4 = LocalAlloc(0, a2);
  *a1 = v4;
  if ( v4 )
  {
    v5 = &v4[a2];
    while ( v4 != v5 )
      *v4++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180013270  mov     [rsp+arg_0], rbx
0x180013275  push    rdi
0x180013276  sub     rsp, 20h
0x18001327a  mov     rbx, rcx
0x18001327d  mov     rdi, rdx
0x180013280  xor     ecx, ecx; uFlags
0x180013282  call    cs:__imp_LocalAlloc
0x180013288  mov     [rbx], rax
0x18001328b  test    rax, rax
0x18001328e  jz      short loc_1800132A2
0x180013290  lea     rdx, [rax+rdi]
0x180013294  jmp     short loc_18001329D
0x180013296  xor     ecx, ecx
0x180013298  mov     [rax], cl
0x18001329a  inc     rax
0x18001329d  cmp     rax, rdx
0x1800132a0  jnz     short loc_180013296
0x1800132a2  mov     rax, rbx
0x1800132a5  mov     rbx, [rsp+28h+arg_0]
0x1800132aa  add     rsp, 20h
0x1800132ae  pop     rdi
0x1800132af  retn
```
