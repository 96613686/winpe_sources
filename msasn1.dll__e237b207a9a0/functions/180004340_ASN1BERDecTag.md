# ASN1BERDecTag

- ea: `0x180004340`
- end: `0x18000443c`
- name: `ASN1BERDecTag`
- size: `252`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f80`
- `0x1800022c0`
- `0x180003070`
- `0x1800030d0`
- `0x180009c10`
- `0x180009e70`
- `0x180009f20`
- `0x180009fa0`

## callees

- `0x180001f50`
- `0x180004310`
- `0x180004340`

## pseudocode

```c
__int64 __fastcall ASN1BERDecTag(_DWORD *a1, int a2, int *a3)
{
  __int64 v5; // rbx
  char *v6; // rax
  char v7; // di
  int v8; // esi
  int v9; // edi
  __int64 v10; // rax
  int v12; // r15d
  char *v13; // rax
  char v14; // cl

  v5 = (__int64)a1;
  if ( a1[4] + a1[6] == a1[10] )
  {
    ASN1DecSetError((__int64)a1, 0xFFFFFC16);
    return 0;
  }
  v6 = (char *)*((_QWORD *)a1 + 5);
  v7 = *v6;
  v8 = *v6 & 0x1F;
  *((_QWORD *)a1 + 5) = v6 + 1;
  if ( v8 == 31 )
  {
    v8 = 0;
    v12 = 0;
    while ( (unsigned int)ASN1BERDecCheck((_DWORD *)v5, 1u) )
    {
      v13 = *(char **)(v5 + 40);
      v14 = *v13;
      *(_QWORD *)(v5 + 40) = v13 + 1;
      if ( (v8 & 0xE0000000) == 0 )
      {
        v8 = (v8 << 7) | v14 & 0x7F;
        if ( v14 >= 0 )
          goto LABEL_3;
        if ( (unsigned int)++v12 < 4 )
          continue;
      }
      ASN1DecSetError(v5, 0xFFFFFC0D);
      return 0;
    }
    return 0;
  }
LABEL_3:
  v9 = v7 & 0xE0;
  if ( a3 )
  {
    *a3 = v9 & 0x20;
    v9 &= ~0x20u;
  }
  if ( a2 != (v8 | (v9 << 24)) )
  {
    do
    {
      v10 = *(_QWORD *)(v5 + 56);
      *(_DWORD *)(v5 + 32) = -1011;
      if ( v5 == v10 )
        break;
      v5 = v10;
    }
    while ( v10 );
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180004340  push    rbx
0x180004342  push    rbp
0x180004343  push    rsi
0x180004344  push    rdi
0x180004345  push    r14
0x180004347  push    r15
0x180004349  sub     rsp, 28h
0x18000434d  mov     eax, [rcx+18h]
0x180004350  mov     r14, r8
0x180004353  add     eax, [rcx+10h]
0x180004356  mov     ebp, edx
0x180004358  sub     eax, [rcx+28h]
0x18000435b  mov     rbx, rcx
0x18000435e  cmp     eax, 1
0x180004361  jb      short loc_1800043D3
0x180004363  mov     rax, [rcx+28h]
0x180004367  movzx   edi, byte ptr [rax]
0x18000436a  mov     esi, edi
0x18000436c  and     esi, 1Fh
0x18000436f  inc     rax
0x180004372  mov     [rcx+28h], rax
0x180004376  cmp     esi, 1Fh
0x180004379  jz      short loc_1800043DF
0x18000437b  and     edi, 0E0h
0x180004381  test    r14, r14
0x180004384  jz      short loc_180004391
0x180004386  mov     eax, edi
0x180004388  and     eax, 20h
0x18000438b  mov     [r14], eax
0x18000438e  and     edi, 0FFFFFFDFh
0x180004391  shl     edi, 18h
0x180004394  or      edi, esi
0x180004396  cmp     ebp, edi
0x180004398  jz      short loc_1800043C1
0x18000439a  mov     rax, [rbx+38h]
0x18000439e  mov     dword ptr [rbx+20h], 0FFFFFC0Dh
0x1800043a5  cmp     rbx, rax
0x1800043a8  jz      short loc_1800043B2
0x1800043aa  mov     rbx, rax
0x1800043ad  test    rax, rax
0x1800043b0  jnz     short loc_18000439A
0x1800043b2  xor     eax, eax
0x1800043b4  add     rsp, 28h
0x1800043b8  pop     r15
0x1800043ba  pop     r14
0x1800043bc  pop     rdi
0x1800043bd  pop     rsi
0x1800043be  pop     rbp
0x1800043bf  pop     rbx
0x1800043c0  retn
0x1800043c1  mov     eax, 1
0x1800043c6  add     rsp, 28h
0x1800043ca  pop     r15
0x1800043cc  pop     r14
0x1800043ce  pop     rdi
0x1800043cf  pop     rsi
0x1800043d0  pop     rbp
0x1800043d1  pop     rbx
0x1800043d2  retn
0x1800043d3  mov     edx, 0FFFFFC16h
0x1800043d8  call    ASN1DecSetError
0x1800043dd  jmp     short loc_1800043B2
0x1800043df  xor     esi, esi
0x1800043e1  xor     r15d, r15d
0x1800043e4  mov     edx, 1
0x1800043e9  mov     rcx, rbx
0x1800043ec  call    ASN1BERDecCheck
0x1800043f1  test    eax, eax
0x1800043f3  jz      short loc_1800043B2
0x1800043f5  mov     rax, [rbx+28h]
0x1800043f9  movzx   ecx, byte ptr [rax]
0x1800043fc  inc     rax
0x1800043ff  mov     [rbx+28h], rax
0x180004403  test    esi, 0E0000000h
0x180004409  jnz     short loc_18000442A
0x18000440b  mov     eax, esi
0x18000440d  mov     edx, ecx
0x18000440f  and     ecx, 7Fh
0x180004412  shl     eax, 7
0x180004415  mov     esi, ecx
0x180004417  or      esi, eax
0x180004419  test    dl, dl
0x18000441b  jns     loc_18000437B
0x180004421  inc     r15d
0x180004424  cmp     r15d, 4
0x180004428  jb      short loc_1800043E4
0x18000442a  mov     edx, 0FFFFFC0Dh
0x18000442f  mov     rcx, rbx
0x180004432  call    ASN1DecSetError
0x180004437  jmp     loc_1800043B2
```
