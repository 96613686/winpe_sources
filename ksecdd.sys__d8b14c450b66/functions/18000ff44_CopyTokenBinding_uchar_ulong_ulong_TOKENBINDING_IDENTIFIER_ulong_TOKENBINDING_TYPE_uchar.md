# _CopyTokenBinding(uchar *,ulong *,ulong,TOKENBINDING_IDENTIFIER *,ulong *,TOKENBINDING_TYPE *,uchar *)

- ea: `0x18000ff44`
- end: `0x18001005f`
- name: `?_CopyTokenBinding@@YAJPEAEPEAKKPEAUTOKENBINDING_IDENTIFIER@@1PEAW4TOKENBINDING_TYPE@@0@Z`
- size: `283`
- prototype: `int(unsigned __int8 *, unsigned int *, unsigned int, struct TOKENBINDING_IDENTIFIER *, unsigned int *, enum TOKENBINDING_TYPE *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023760`

## callees

- `0x18000ff44`
- `0x180010980`

## pseudocode

```c
__int64 __fastcall _CopyTokenBinding(
        unsigned __int8 *a1,
        unsigned int *a2,
        __int64 a3,
        struct TOKENBINDING_IDENTIFIER *a4,
        unsigned int *a5,
        enum TOKENBINDING_TYPE *a6,
        unsigned __int8 *a7)
{
  __int64 v7; // rax
  unsigned int v8; // esi
  int v11; // r10d
  unsigned __int8 *v12; // rbp
  int v13; // ecx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ebx
  __int64 v17; // rbx
  int v18; // ebx
  int v19; // r8d
  size_t v20; // r8
  int v21; // r9d

  v7 = *a2;
  v8 = 0;
  v11 = a1[v7];
  v12 = &a1[(unsigned int)(v7 + 1)];
  *a7 = 0;
  v13 = *v12;
  v14 = (unsigned int)(v7 + 4);
  *a2 = v14;
  if ( !v13 || (v15 = v13 - 1) == 0 )
  {
    v19 = (unsigned __int16)(*(_WORD *)&a1[v14] << 8) | a1[v14 + 1];
    v18 = v19 + a1[(unsigned int)(v19 + v7 + 6)] + 3;
    goto LABEL_9;
  }
  if ( v15 == 1 )
  {
    v18 = a1[v14] + 1;
LABEL_9:
    v17 = (unsigned int)(v14 + v18);
    v20 = (unsigned int)(v17 - (v7 + 1));
    *(_DWORD *)a6 = v11;
    *a5 = v20;
    memmove(a4, v12, v20);
    goto LABEL_10;
  }
  if ( (_BYTE)v11 == 1 )
  {
    v16 = (unsigned __int16)(*(_WORD *)&a1[(unsigned int)(v7 + 2)] << 8) | a1[(unsigned int)(v7 + 2) + 1];
    *a7 = 1;
    v17 = (unsigned int)(v14 + v16);
LABEL_10:
    v21 = a1[v17 + 1] | (unsigned __int16)(*(_WORD *)&a1[v17] << 8);
    *a2 = v17
        + v21
        + ((unsigned __int16)(*(_WORD *)&a1[(unsigned int)(v21 + v17 + 2)] << 8) | a1[(unsigned int)(v21 + v17 + 2) + 1])
        + 4;
    return v8;
  }
  return (unsigned int)-2146893816;
}

```

## disassembly

```asm
0x18000ff44  push    rbx
0x18000ff46  push    rbp
0x18000ff47  push    rsi
0x18000ff48  push    rdi
0x18000ff49  push    r14
0x18000ff4b  push    r15
0x18000ff4d  sub     rsp, 28h
0x18000ff51  mov     eax, [rdx]
0x18000ff53  xor     esi, esi
0x18000ff55  mov     r11, [rsp+58h+arg_30]
0x18000ff5d  mov     r14, rdx
0x18000ff60  mov     rdi, rcx
0x18000ff63  movzx   r10d, byte ptr [rax+rcx]
0x18000ff68  lea     r8d, [rax+1]
0x18000ff6c  mov     ebp, r8d
0x18000ff6f  mov     r15d, r8d
0x18000ff72  add     rbp, rcx
0x18000ff75  mov     [r11], sil
0x18000ff78  inc     r8d
0x18000ff7b  movzx   ecx, byte ptr [rbp+0]
0x18000ff7f  lea     edx, [r8+2]
0x18000ff83  mov     [r14], edx
0x18000ff86  test    ecx, ecx
0x18000ff88  jz      short loc_18000FFC7
0x18000ff8a  sub     ecx, 1
0x18000ff8d  jz      short loc_18000FFC7
0x18000ff8f  cmp     ecx, 1
0x18000ff92  jz      short loc_18000FFBF
0x18000ff94  cmp     r10b, 1
0x18000ff98  jnz     short loc_18000FFB5
0x18000ff9a  movzx   eax, word ptr [r8+rdi]
0x18000ff9f  movzx   ebx, byte ptr [r8+rdi+1]
0x18000ffa5  shl     ax, 8
0x18000ffa9  movzx   eax, ax
0x18000ffac  or      ebx, eax
0x18000ffae  mov     [r11], r10b
0x18000ffb1  add     ebx, edx
0x18000ffb3  jmp     short loc_180010014
0x18000ffb5  mov     esi, 80090008h
0x18000ffba  jmp     loc_18001004F
0x18000ffbf  movzx   ebx, byte ptr [rdx+rdi]
0x18000ffc3  inc     ebx
0x18000ffc5  jmp     short loc_18000FFEB
0x18000ffc7  movzx   eax, word ptr [rdx+rdi]
0x18000ffcb  movzx   r8d, byte ptr [rdx+rdi+1]
0x18000ffd1  shl     ax, 8
0x18000ffd5  movzx   eax, ax
0x18000ffd8  or      r8d, eax
0x18000ffdb  lea     eax, [rdx+2]
0x18000ffde  add     eax, r8d
0x18000ffe1  movzx   ebx, byte ptr [rax+rdi]
0x18000ffe5  add     ebx, 3
0x18000ffe8  add     ebx, r8d
0x18000ffeb  mov     rax, [rsp+58h+arg_28]
0x18000fff3  add     ebx, edx
0x18000fff5  mov     r8d, ebx
0x18000fff8  mov     rdx, rbp; Src
0x18000fffb  sub     r8d, r15d; Size
0x18000fffe  mov     rcx, r9; void *
0x180010001  mov     [rax], r10d
0x180010004  mov     rax, [rsp+58h+arg_20]
0x18001000c  mov     [rax], r8d
0x18001000f  call    memmove
0x180010014  movzx   eax, word ptr [rbx+rdi]
0x180010018  lea     ecx, [rbx+2]
0x18001001b  shl     ax, 8
0x18001001f  movzx   r9d, ax
0x180010023  movzx   eax, byte ptr [rbx+rdi+1]
0x180010028  or      r9d, eax
0x18001002b  add     ecx, r9d
0x18001002e  mov     edx, ecx
0x180010030  movzx   ecx, word ptr [rcx+rdi]
0x180010034  shl     cx, 8
0x180010038  movzx   r8d, cx
0x18001003c  movzx   ecx, byte ptr [rdx+rdi+1]
0x180010041  or      ecx, r8d
0x180010044  add     ecx, 4
0x180010047  add     ecx, r9d
0x18001004a  add     ecx, ebx
0x18001004c  mov     [r14], ecx
0x18001004f  mov     eax, esi
0x180010051  add     rsp, 28h
0x180010055  pop     r15
0x180010057  pop     r14
0x180010059  pop     rdi
0x18001005a  pop     rsi
0x18001005b  pop     rbp
0x18001005c  pop     rbx
0x18001005d  retn
```
