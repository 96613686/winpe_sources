# sl_compress_init

- ea: `0x14002e8dc`
- end: `0x14002e995`
- name: `sl_compress_init`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002b270`
- `0x14002bab0`

## callees

- `0x140016700`
- `0x14002e8dc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002e901`
- `ntoskrnl!ExAllocatePool2` at `0x14002e901`

## pseudocode

```c
__int64 __fastcall sl_compress_init(_QWORD **a1, unsigned __int8 a2)
{
  _QWORD *Pool2; // rbx
  __int64 v4; // rbp
  __int64 result; // rax
  _QWORD *v6; // rdi
  __int64 i; // r8
  __int64 v8; // rdx

  Pool2 = *a1;
  v4 = a2;
  if ( !*a1 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 4656, 1215193431);
    if ( !Pool2 )
      return 3221225626LL;
  }
  v6 = Pool2 + 6;
  memset(Pool2, 0, 0x1230u);
  for ( i = (unsigned int)(v4 - 1); (_DWORD)i; v6[v8] = &v6[18 * i] )
  {
    v8 = 18 * i;
    BYTE2(v6[v8 + 1]) = i;
    i = (unsigned int)(i - 1);
  }
  *((_BYTE *)Pool2 + 58) = 0;
  *v6 = &v6[18 * v4 - 18];
  result = 0;
  *Pool2 = v6;
  *((_DWORD *)Pool2 + 2) = 0x1FFFF;
  *((_BYTE *)Pool2 + 12) = v4;
  *a1 = Pool2;
  return result;
}

```

## disassembly

```asm
0x14002e8dc  push    rbx
0x14002e8de  push    rbp
0x14002e8df  push    rsi
0x14002e8e0  push    rdi
0x14002e8e1  sub     rsp, 28h
0x14002e8e5  mov     rbx, [rcx]
0x14002e8e8  mov     rsi, rcx
0x14002e8eb  movzx   ebp, dl
0x14002e8ee  test    rbx, rbx
0x14002e8f1  jnz     short loc_14002E91C
0x14002e8f3  mov     edx, 1230h
0x14002e8f8  lea     ecx, [rbx+40h]
0x14002e8fb  mov     r8d, 486E6157h
0x14002e901  call    cs:__imp_ExAllocatePool2
0x14002e908  nop     dword ptr [rax+rax+00h]
0x14002e90d  mov     rbx, rax
0x14002e910  test    rax, rax
0x14002e913  jnz     short loc_14002E91C
0x14002e915  mov     eax, 0C000009Ah
0x14002e91a  jmp     short loc_14002E98B
0x14002e91c  xor     edx, edx; Val
0x14002e91e  lea     rdi, [rbx+30h]
0x14002e922  mov     r8d, 1230h; Size
0x14002e928  mov     rcx, rbx; void *
0x14002e92b  call    memset
0x14002e930  lea     r8d, [rbp-1]
0x14002e934  jmp     short loc_14002E954
0x14002e936  lea     rdx, [r8+r8*8]
0x14002e93a  add     rdx, rdx
0x14002e93d  mov     [rdi+rdx*8+0Ah], r8b
0x14002e942  dec     r8d
0x14002e945  lea     rcx, [r8+r8*8]
0x14002e949  shl     rcx, 4
0x14002e94d  add     rcx, rdi
0x14002e950  mov     [rdi+rdx*8], rcx
0x14002e954  test    r8d, r8d
0x14002e957  jnz     short loc_14002E936
0x14002e959  mov     [rdi+0Ah], r8b
0x14002e95d  lea     rax, ds:0[rbp*8]
0x14002e965  add     rax, rbp
0x14002e968  shl     rax, 4
0x14002e96c  add     rax, 0FFFFFFFFFFFFFF70h
0x14002e972  add     rax, rdi
0x14002e975  mov     [rdi], rax
0x14002e978  xor     eax, eax
0x14002e97a  mov     [rbx], rdi
0x14002e97d  mov     dword ptr [rbx+8], 1FFFFh
0x14002e984  mov     [rbx+0Ch], bpl
0x14002e988  mov     [rsi], rbx
0x14002e98b  add     rsp, 28h
0x14002e98f  pop     rdi
0x14002e990  pop     rsi
0x14002e991  pop     rbp
0x14002e992  pop     rbx
0x14002e993  retn
```
