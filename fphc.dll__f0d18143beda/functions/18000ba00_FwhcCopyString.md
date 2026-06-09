# FwhcCopyString

- ea: `0x18000ba00`
- end: `0x18000baca`
- name: `FwhcCopyString`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf3c`

## callees

- `0x18000ba00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ba45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ba45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba37`

## pseudocode

```c
__int64 __fastcall FwhcCopyString(const wchar_t *a1, _QWORD *a2)
{
  const wchar_t *v3; // rdi
  __int64 v4; // rbx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v7; // rax
  _WORD *v8; // rdx
  __int64 result; // rax
  unsigned __int64 v10; // rbx
  __int64 v11; // rax
  _WORD *v12; // rcx

  v3 = a1;
  if ( !a1 || !*a1 )
    v3 = L"-";
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  v5 = 2 * v4 + 2;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, v5);
  *a2 = v7;
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v10 = v5 >> 1;
  if ( !v10 )
    return 2147942487LL;
  if ( v10 <= 0x7FFFFFFF )
  {
    v11 = 2147483646;
    do
    {
      if ( !v11 )
        break;
      if ( !*v3 )
        break;
      *v8++ = *v3++;
      --v11;
      --v10;
    }
    while ( v10 );
    v12 = v8 - 1;
    if ( v10 )
      v12 = v8;
    result = v10 == 0 ? 0x8007007A : 0;
    *v12 = 0;
  }
  else
  {
    result = 2147942487LL;
    *v8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba00  push    rbx
0x18000ba02  push    rbp
0x18000ba03  push    rsi
0x18000ba04  push    rdi
0x18000ba05  sub     rsp, 28h
0x18000ba09  xor     ebp, ebp
0x18000ba0b  mov     rsi, rdx
0x18000ba0e  mov     rdi, rcx
0x18000ba11  test    rcx, rcx
0x18000ba14  jz      short loc_18000BA1B
0x18000ba16  cmp     [rcx], bp
0x18000ba19  jnz     short loc_18000BA22
0x18000ba1b  lea     rdi, asc_1800167BC; "-"
0x18000ba22  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ba26  inc     rbx
0x18000ba29  cmp     [rdi+rbx*2], bp
0x18000ba2d  jnz     short loc_18000BA26
0x18000ba2f  lea     rbx, ds:2[rbx*2]
0x18000ba37  call    cs:__imp_GetProcessHeap
0x18000ba3d  mov     r8, rbx; dwBytes
0x18000ba40  xor     edx, edx; dwFlags
0x18000ba42  mov     rcx, rax; hHeap
0x18000ba45  call    cs:__imp_HeapAlloc
0x18000ba4b  mov     [rsi], rax
0x18000ba4e  mov     rdx, rax
0x18000ba51  test    rax, rax
0x18000ba54  jnz     short loc_18000BA5D
0x18000ba56  mov     eax, 8007000Eh
0x18000ba5b  jmp     short loc_18000BAC1
0x18000ba5d  shr     rbx, 1
0x18000ba60  jz      short loc_18000BAB4
0x18000ba62  cmp     rbx, 7FFFFFFFh
0x18000ba69  jbe     short loc_18000BA72
0x18000ba6b  mov     eax, 80070057h
0x18000ba70  jmp     short loc_18000BABE
0x18000ba72  mov     eax, 7FFFFFFEh
0x18000ba77  test    rax, rax
0x18000ba7a  jz      short loc_18000BA98
0x18000ba7c  movzx   ecx, word ptr [rdi]
0x18000ba7f  test    cx, cx
0x18000ba82  jz      short loc_18000BA98
0x18000ba84  mov     [rdx], cx
0x18000ba87  add     rdi, 2
0x18000ba8b  add     rdx, 2
0x18000ba8f  dec     rax
0x18000ba92  sub     rbx, 1
0x18000ba96  jnz     short loc_18000BA77
0x18000ba98  test    rbx, rbx
0x18000ba9b  lea     rcx, [rdx-2]
0x18000ba9f  cmovnz  rcx, rdx
0x18000baa3  neg     rbx
0x18000baa6  sbb     eax, eax
0x18000baa8  not     eax
0x18000baaa  and     eax, 8007007Ah
0x18000baaf  mov     [rcx], bp
0x18000bab2  jmp     short loc_18000BAC1
0x18000bab4  mov     eax, 80070057h
0x18000bab9  test    rbx, rbx
0x18000babc  jz      short loc_18000BAC1
0x18000babe  mov     [rdx], bp
0x18000bac1  add     rsp, 28h
0x18000bac5  pop     rdi
0x18000bac6  pop     rsi
0x18000bac7  pop     rbp
0x18000bac8  pop     rbx
0x18000bac9  retn
```
