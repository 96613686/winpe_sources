# AllocAndCopyWStr(ushort const *)

- ea: `0x18000590c`
- end: `0x180005977`
- name: `?AllocAndCopyWStr@@YAPEAGPEBG@Z`
- size: `107`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *Src)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c6c`
- `0x18000a3ec`
- `0x18000a79c`
- `0x18000f2b0`
- `0x1800107b0`
- `0x1800108c8`
- `0x180011d34`
- `0x180012030`
- `0x180017978`
- `0x180017f94`
- `0x1800186d4`
- `0x1800190d8`
- `0x18001dd3c`
- `0x18001ea90`
- `0x18001ed1c`
- `0x18001ef18`
- `0x180027a80`
- `0x180029bdc`
- `0x18002e55c`
- `0x180034fa0`
- `0x180035b18`

## callees

- `0x180001f66`
- `0x18000590c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005940`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005953`

## pseudocode

```c
unsigned __int16 *__fastcall AllocAndCopyWStr(const unsigned __int16 *Src)
{
  __int64 v2; // rax
  SIZE_T v3; // rdi
  HLOCAL v4; // rax
  HLOCAL v5; // rsi

  if ( Src )
  {
    v2 = -1;
    do
      ++v2;
    while ( Src[v2] );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  v3 = 2LL * ((int)v2 + 1);
  v4 = LocalAlloc(0x40u, v3);
  v5 = v4;
  if ( v4 )
  {
    memcpy_0(v4, Src, v3);
    return (unsigned __int16 *)v5;
  }
  else
  {
    SetLastError(0x8007000E);
    return 0;
  }
}

```

## disassembly

```asm
0x18000590c  push    rbx
0x18000590e  push    rbp
0x18000590f  push    rsi
0x180005910  push    rdi
0x180005911  sub     rsp, 28h
0x180005915  xor     ebp, ebp
0x180005917  mov     rbx, rcx
0x18000591a  test    rcx, rcx
0x18000591d  jz      short loc_18000592E
0x18000591f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005923  inc     rax
0x180005926  cmp     [rcx+rax*2], bp
0x18000592a  jnz     short loc_180005923
0x18000592c  jmp     short loc_180005930
0x18000592e  mov     eax, ebp
0x180005930  inc     eax
0x180005932  mov     ecx, 40h ; '@'; uFlags
0x180005937  movsxd  rdi, eax
0x18000593a  add     rdi, rdi
0x18000593d  mov     rdx, rdi; uBytes
0x180005940  call    cs:__imp_LocalAlloc
0x180005946  mov     rsi, rax
0x180005949  test    rax, rax
0x18000594c  jnz     short loc_18000595D
0x18000594e  mov     ecx, 8007000Eh; dwErrCode
0x180005953  call    cs:__imp_SetLastError
0x180005959  xor     eax, eax
0x18000595b  jmp     short loc_18000596E
0x18000595d  mov     r8, rdi; Size
0x180005960  mov     rdx, rbx; Src
0x180005963  mov     rcx, rsi; void *
0x180005966  call    memcpy_0
0x18000596b  mov     rax, rsi
0x18000596e  add     rsp, 28h
0x180005972  pop     rdi
0x180005973  pop     rsi
0x180005974  pop     rbp
0x180005975  pop     rbx
0x180005976  retn
```
