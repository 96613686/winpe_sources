# CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)

- ea: `0x18000d780`
- end: `0x18000d864`
- name: `?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d870`
- `0x18000e7f8`

## callees

- `0x18000d780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d7c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d7c0`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000d815`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000d815`

## pseudocode

```c
signed int __fastcall CDynamicArray<_TASK_TRIGGER>::Add(char **a1, _OWORD *a2)
{
  char *v2; // r9
  unsigned __int16 v4; // bx
  char *v6; // rax
  signed int result; // eax
  _WORD *v8; // rsi
  unsigned __int16 v9; // bx
  char *v10; // rax
  __int64 v11; // rcx

  v2 = *a1;
  v4 = *((_WORD *)a1 + 5);
  if ( !*a1 )
  {
    if ( !v4 )
    {
      *((_WORD *)a1 + 5) = 1;
      v4 = 1;
    }
    v6 = (char *)LocalAlloc(0, 48LL * v4);
    *a1 = v6;
    v2 = v6;
    if ( !v6 )
      goto LABEL_5;
    v8 = a1 + 1;
LABEL_14:
    v11 = 6LL * (unsigned __int16)*v8;
    *(_OWORD *)&v2[8 * v11] = *a2;
    *(_OWORD *)&v2[8 * v11 + 16] = a2[1];
    *(_OWORD *)&v2[8 * v11 + 32] = a2[2];
    ++*v8;
    return 0;
  }
  v8 = a1 + 1;
  if ( *((_WORD *)a1 + 4) != v4 )
    goto LABEL_14;
  if ( v4 )
    v9 = 2 * v4;
  else
    v9 = 1;
  v10 = (char *)LocalReAlloc(*a1, 48LL * v9, 2u);
  v2 = v10;
  if ( v10 )
  {
    *a1 = v10;
    *((_WORD *)a1 + 5) = v9;
    goto LABEL_14;
  }
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000d780  push    rbx
0x18000d782  push    rbp
0x18000d783  push    rsi
0x18000d784  push    rdi
0x18000d785  push    r14
0x18000d787  push    r15
0x18000d789  sub     rsp, 28h
0x18000d78d  mov     r9, [rcx]
0x18000d790  mov     rbp, rdx
0x18000d793  movzx   ebx, word ptr [rcx+0Ah]
0x18000d797  mov     rdi, rcx
0x18000d79a  mov     r15d, 1
0x18000d7a0  test    r9, r9
0x18000d7a3  jnz     short loc_18000D7EB
0x18000d7a5  test    bx, bx
0x18000d7a8  jnz     short loc_18000D7B3
0x18000d7aa  mov     [rcx+0Ah], r15w
0x18000d7af  movzx   ebx, r15w
0x18000d7b3  movzx   eax, bx
0x18000d7b6  xor     ecx, ecx; uFlags
0x18000d7b8  lea     rdx, [rax+rax*2]
0x18000d7bc  shl     rdx, 4; uBytes
0x18000d7c0  call    cs:__imp_LocalAlloc
0x18000d7c6  mov     [rdi], rax
0x18000d7c9  mov     r9, rax
0x18000d7cc  test    rax, rax
0x18000d7cf  jnz     short loc_18000D7E5
0x18000d7d1  call    cs:__imp_GetLastError
0x18000d7d7  test    eax, eax
0x18000d7d9  jle     short loc_18000D857
0x18000d7db  movzx   eax, ax
0x18000d7de  or      eax, 80070000h
0x18000d7e3  jmp     short loc_18000D857
0x18000d7e5  lea     rsi, [rdi+8]
0x18000d7e9  jmp     short loc_18000D82A
0x18000d7eb  lea     rsi, [rcx+8]
0x18000d7ef  cmp     [rsi], bx
0x18000d7f2  jnz     short loc_18000D82A
0x18000d7f4  test    bx, bx
0x18000d7f7  jz      short loc_18000D7FE
0x18000d7f9  add     bx, bx
0x18000d7fc  jmp     short loc_18000D801
0x18000d7fe  mov     ebx, r15d
0x18000d801  movzx   eax, bx
0x18000d804  mov     r8d, 2; uFlags
0x18000d80a  mov     rcx, r9; hMem
0x18000d80d  lea     rdx, [rax+rax*2]
0x18000d811  shl     rdx, 4; uBytes
0x18000d815  call    cs:__imp_LocalReAlloc
0x18000d81b  mov     r9, rax
0x18000d81e  test    rax, rax
0x18000d821  jz      short loc_18000D7D1
0x18000d823  mov     [rdi], rax
0x18000d826  mov     [rdi+0Ah], bx
0x18000d82a  movzx   eax, word ptr [rsi]
0x18000d82d  movups  xmm0, xmmword ptr [rbp+0]
0x18000d831  lea     rcx, [rax+rax*2]
0x18000d835  add     rcx, rcx
0x18000d838  movups  xmmword ptr [r9+rcx*8], xmm0
0x18000d83d  movups  xmm1, xmmword ptr [rbp+10h]
0x18000d841  movups  xmmword ptr [r9+rcx*8+10h], xmm1
0x18000d847  movups  xmm0, xmmword ptr [rbp+20h]
0x18000d84b  movups  xmmword ptr [r9+rcx*8+20h], xmm0
0x18000d851  add     [rsi], r15w
0x18000d855  xor     eax, eax
0x18000d857  add     rsp, 28h
0x18000d85b  pop     r15
0x18000d85d  pop     r14
0x18000d85f  pop     rdi
0x18000d860  pop     rsi
0x18000d861  pop     rbp
0x18000d862  pop     rbx
0x18000d863  retn
```
