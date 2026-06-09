# wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x180017440`
- end: `0x180017480`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `64`
- prototype: `_QWORD *__fastcall(_QWORD *, SIZE_T)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180018944`
- `0x18001c9ac`
- `0x18001cc04`
- `0x18001cff4`
- `0x18001d624`
- `0x18001d748`

## callees

- `0x180017440`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017452`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017452`

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
0x180017440  mov     [rsp+arg_0], rbx
0x180017445  push    rdi
0x180017446  sub     rsp, 30h
0x18001744a  mov     rbx, rcx
0x18001744d  mov     rdi, rdx
0x180017450  xor     ecx, ecx; uFlags
0x180017452  call    cs:__imp_LocalAlloc
0x180017458  mov     [rbx], rax
0x18001745b  test    rax, rax
0x18001745e  jz      short loc_180017472
0x180017460  lea     rdx, [rax+rdi]
0x180017464  jmp     short loc_18001746D
0x180017466  xor     ecx, ecx
0x180017468  mov     [rax], cl
0x18001746a  inc     rax
0x18001746d  cmp     rax, rdx
0x180017470  jnz     short loc_180017466
0x180017472  mov     rax, rbx
0x180017475  mov     rbx, [rsp+38h+arg_0]
0x18001747a  add     rsp, 30h
0x18001747e  pop     rdi
0x18001747f  retn
```
