# LdrpTraceLoadMUIDll

- ea: `0x1800ae518`
- end: `0x1800ae5f8`
- name: `LdrpTraceLoadMUIDll`
- size: `224`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180074140`
- `0x180075be0`
- `0x1800aa698`
- `0x1800ab4f0`
- `0x1800abe80`
- `0x1800ad130`
- `0x1800ad6c0`
- `0x1800adc70`
- `0x1800ade40`
- `0x1800adfe0`
- `0x1800ae600`
- `0x1800aec20`
- `0x1800af680`
- `0x1800af79c`
- `0x1800d2f88`
- `0x1800d7650`
- `0x180100e20`
- `0x1801100d0`

## callees

- `0x1800ae518`
- `0x18015f690`
- `0x180162810`
- `0x180164280`
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
0x1800ae518  mov     [rsp+arg_10], rbx
0x1800ae51d  push    rbp
0x1800ae51e  push    rsi
0x1800ae51f  push    rdi
0x1800ae520  sub     rsp, 280h
0x1800ae527  mov     rax, cs:__security_cookie
0x1800ae52e  xor     rax, rsp
0x1800ae531  mov     [rsp+298h+var_28], rax
0x1800ae539  mov     ebp, edx
0x1800ae53b  mov     rsi, rcx
0x1800ae53e  xor     edx, edx; Val
0x1800ae540  lea     rcx, [rsp+298h+var_248]; void *
0x1800ae545  mov     r8d, 218h; Size
0x1800ae54b  call    memset$thunk$772440563353939046
0x1800ae550  movzx   eax, word ptr [rsi]
0x1800ae553  xorps   xmm0, xmm0
0x1800ae556  mov     ecx, 0FFFEh
0x1800ae55b  and     ax, cx
0x1800ae55e  mov     ecx, 212h
0x1800ae563  movups  [rsp+298h+var_278], xmm0
0x1800ae568  movups  [rsp+298h+var_268], xmm0
0x1800ae56d  movups  [rsp+298h+var_258], xmm0
0x1800ae572  cmp     ax, cx
0x1800ae575  jnb     short loc_1800AE5F1
0x1800ae577  movzx   edi, word ptr [rsi]
0x1800ae57a  shr     edi, 1
0x1800ae57c  mov     rdx, [rsi+8]; Src
0x1800ae580  lea     rcx, [rsp+298h+var_248]; void *
0x1800ae585  mov     eax, edi
0x1800ae587  lea     rbx, [rax+rax]
0x1800ae58b  mov     r8, rbx; Size
0x1800ae58e  call    memmove
0x1800ae593  movups  xmm0, cs:LoadMUIDllGuid
0x1800ae59a  xor     eax, eax
0x1800ae59c  lea     r9, [rsp+298h+var_278]
0x1800ae5a1  mov     [rsp+rbx+298h+var_248], ax
0x1800ae5a6  add     di, 19h
0x1800ae5aa  add     di, di
0x1800ae5ad  mov     byte ptr [rsp+298h+var_278+4], al
0x1800ae5b1  mov     rcx, rbp
0x1800ae5b4  mov     word ptr [rsp+298h+var_278], di
0x1800ae5b9  lea     r8d, [rax+30h]
0x1800ae5bd  mov     edx, 100h
0x1800ae5c2  movdqu  [rsp+298h+var_268+8], xmm0
0x1800ae5c8  call    NtTraceEvent
0x1800ae5cd  mov     rcx, [rsp+298h+var_28]
0x1800ae5d5  xor     rcx, rsp; StackCookie
0x1800ae5d8  call    __security_check_cookie
0x1800ae5dd  mov     rbx, [rsp+298h+arg_10]
0x1800ae5e5  add     rsp, 280h
0x1800ae5ec  pop     rdi
0x1800ae5ed  pop     rsi
0x1800ae5ee  pop     rbp
0x1800ae5ef  retn
0x1800ae5f1  mov     edi, 109h
0x1800ae5f6  jmp     short loc_1800AE57C
```
