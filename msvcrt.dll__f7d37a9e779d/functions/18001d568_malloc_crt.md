# _malloc_crt

- ea: `0x18001d568`
- end: `0x18001d5b9`
- name: `_malloc_crt`
- size: `81`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `62`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023c0`
- `0x180002550`
- `0x1800094e0`
- `0x180009f60`
- `0x180017784`
- `0x180017970`
- `0x180017fec`
- `0x180021c08`
- `0x180024390`
- `0x18002b790`
- `0x18002c804`
- `0x18002cc48`
- `0x18002d80c`
- `0x18002e310`
- `0x180031cc0`
- `0x180033c84`
- `0x180033cf8`
- `0x1800343b0`
- `0x180034950`
- `0x180036d94`
- `0x18003714c`
- `0x18003e790`
- `0x18003e900`
- `0x18003ec6c`
- `0x18003efe0`
- `0x18003f2e4`
- `0x18003fbac`
- `0x18003fc0c`
- `0x180040068`
- `0x1800400c8`
- `0x1800407b0`
- `0x1800412f0`
- `0x180042500`
- `0x180045280`
- `0x180045e80`
- `0x1800472a0`
- `0x180048000`
- `0x180048248`
- `0x180049274`
- `0x180049404`
- `0x180052350`
- `0x180052650`
- `0x180052e60`
- `0x180053b40`
- `0x180054e40`
- `0x180055c10`
- `0x180057034`
- `0x180057260`
- `0x180059b90`
- `0x18005aa28`

## callees

- `0x18001d350`
- `0x18001d568`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d592`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d592`

## pseudocode

```c
void *__fastcall malloc_crt(size_t Size)
{
  int v1; // edi
  DWORD v3; // ebx
  void *v4; // rsi

  v1 = maxwait;
  v3 = 0;
  do
  {
    v4 = malloc(Size);
    if ( v4 )
      break;
    if ( !v1 )
      break;
    Sleep(v3);
    v1 = maxwait;
    v3 += 1000;
    if ( v3 > maxwait )
      break;
  }
  while ( v3 != -1 );
  return v4;
}

```

## disassembly

```asm
0x18001d568  push    rbx
0x18001d56a  push    rbp
0x18001d56b  push    rsi
0x18001d56c  push    rdi
0x18001d56d  sub     rsp, 28h
0x18001d571  mov     edi, cs:_maxwait
0x18001d577  mov     rbp, rcx
0x18001d57a  xor     ebx, ebx
0x18001d57c  mov     rcx, rbp; Size
0x18001d57f  call    malloc
0x18001d584  mov     rsi, rax
0x18001d587  test    rax, rax
0x18001d58a  jnz     short loc_18001D5AD
0x18001d58c  test    edi, edi
0x18001d58e  jz      short loc_18001D5AD
0x18001d590  mov     ecx, ebx; dwMilliseconds
0x18001d592  call    cs:__imp_Sleep
0x18001d598  mov     edi, cs:_maxwait
0x18001d59e  add     ebx, 3E8h
0x18001d5a4  cmp     ebx, edi
0x18001d5a6  ja      short loc_18001D5AD
0x18001d5a8  cmp     ebx, 0FFFFFFFFh
0x18001d5ab  jnz     short loc_18001D57C
0x18001d5ad  mov     rax, rsi
0x18001d5b0  add     rsp, 28h
0x18001d5b4  pop     rdi
0x18001d5b5  pop     rsi
0x18001d5b6  pop     rbp
0x18001d5b7  pop     rbx
0x18001d5b8  retn
```
