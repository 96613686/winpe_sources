# LdrpTraceLoadMUIDll

- ea: `0x1800a5b48`
- end: `0x1800a5c28`
- name: `LdrpTraceLoadMUIDll`
- size: `224`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180057760`
- `0x180059200`
- `0x1800a1cc8`
- `0x1800a2b20`
- `0x1800a34b0`
- `0x1800a4760`
- `0x1800a4cf0`
- `0x1800a52a0`
- `0x1800a5470`
- `0x1800a5610`
- `0x1800a5c30`
- `0x1800a6250`
- `0x1800a6cb0`
- `0x1800a6dcc`
- `0x1800d1858`
- `0x1800d33a0`
- `0x180100800`
- `0x18010ed70`

## callees

- `0x1800a5b48`
- `0x18015ee80`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpTraceLoadMUIDll(unsigned __int16 *a1, unsigned int a2)
{
  __int64 v2; // rbp
  unsigned __int16 v4; // ax
  unsigned int v5; // edi
  _OWORD v7[3]; // [rsp+20h] [rbp-278h] BYREF
  _WORD v8[272]; // [rsp+50h] [rbp-248h] BYREF

  v2 = a2;
  memset_thunk_772440563353939046(v8, 0, 0x218u);
  v4 = *a1 & 0xFFFE;
  memset(v7, 0, sizeof(v7));
  if ( v4 >= 0x212u )
    v5 = 265;
  else
    v5 = *a1 >> 1;
  memmove(v8, *((const void **)a1 + 1), 2LL * v5);
  v8[v5] = 0;
  BYTE4(v7[0]) = 0;
  LOWORD(v7[0]) = 2 * (v5 + 25);
  *(_OWORD *)((char *)&v7[1] + 8) = LoadMUIDllGuid;
  return NtTraceEvent(v2, 256, 48, v7);
}

```

## disassembly

```asm
0x1800a5b48  mov     [rsp+arg_10], rbx
0x1800a5b4d  push    rbp
0x1800a5b4e  push    rsi
0x1800a5b4f  push    rdi
0x1800a5b50  sub     rsp, 280h
0x1800a5b57  mov     rax, cs:__security_cookie
0x1800a5b5e  xor     rax, rsp
0x1800a5b61  mov     [rsp+298h+var_28], rax
0x1800a5b69  mov     ebp, edx
0x1800a5b6b  mov     rsi, rcx
0x1800a5b6e  xor     edx, edx; Val
0x1800a5b70  lea     rcx, [rsp+298h+var_248]; void *
0x1800a5b75  mov     r8d, 218h; Size
0x1800a5b7b  call    memset$thunk$772440563353939046
0x1800a5b80  movzx   eax, word ptr [rsi]
0x1800a5b83  xorps   xmm0, xmm0
0x1800a5b86  mov     ecx, 0FFFEh
0x1800a5b8b  and     ax, cx
0x1800a5b8e  mov     ecx, 212h
0x1800a5b93  movups  [rsp+298h+var_278], xmm0
0x1800a5b98  movups  [rsp+298h+var_268], xmm0
0x1800a5b9d  movups  [rsp+298h+var_258], xmm0
0x1800a5ba2  cmp     ax, cx
0x1800a5ba5  jnb     short loc_1800A5C21
0x1800a5ba7  movzx   edi, word ptr [rsi]
0x1800a5baa  shr     edi, 1
0x1800a5bac  mov     rdx, [rsi+8]; Src
0x1800a5bb0  lea     rcx, [rsp+298h+var_248]; void *
0x1800a5bb5  mov     eax, edi
0x1800a5bb7  lea     rbx, [rax+rax]
0x1800a5bbb  mov     r8, rbx; Size
0x1800a5bbe  call    memmove
0x1800a5bc3  movups  xmm0, cs:LoadMUIDllGuid
0x1800a5bca  xor     eax, eax
0x1800a5bcc  lea     r9, [rsp+298h+var_278]
0x1800a5bd1  mov     [rsp+rbx+298h+var_248], ax
0x1800a5bd6  add     di, 19h
0x1800a5bda  add     di, di
0x1800a5bdd  mov     byte ptr [rsp+298h+var_278+4], al
0x1800a5be1  mov     rcx, rbp
0x1800a5be4  mov     word ptr [rsp+298h+var_278], di
0x1800a5be9  lea     r8d, [rax+30h]
0x1800a5bed  mov     edx, 100h
0x1800a5bf2  movdqu  [rsp+298h+var_268+8], xmm0
0x1800a5bf8  call    NtTraceEvent
0x1800a5bfd  mov     rcx, [rsp+298h+var_28]
0x1800a5c05  xor     rcx, rsp; StackCookie
0x1800a5c08  call    __security_check_cookie
0x1800a5c0d  mov     rbx, [rsp+298h+arg_10]
0x1800a5c15  add     rsp, 280h
0x1800a5c1c  pop     rdi
0x1800a5c1d  pop     rsi
0x1800a5c1e  pop     rbp
0x1800a5c1f  retn
0x1800a5c21  mov     edi, 109h
0x1800a5c26  jmp     short loc_1800A5BAC
```
