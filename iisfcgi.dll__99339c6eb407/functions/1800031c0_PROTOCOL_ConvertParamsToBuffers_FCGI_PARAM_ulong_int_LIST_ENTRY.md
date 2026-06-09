# PROTOCOL::ConvertParamsToBuffers(_FCGI_PARAM *,ulong,int,_LIST_ENTRY *)

- ea: `0x1800031c0`
- end: `0x1800033ad`
- name: `?ConvertParamsToBuffers@PROTOCOL@@SAJPEAU_FCGI_PARAM@@KHPEAU_LIST_ENTRY@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct _FCGI_PARAM *, unsigned int, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006a0c`

## callees

- `0x1800031c0`
- `0x180008f90`
- `0x18000edc6`

## pseudocode

```c
__int64 __fastcall PROTOCOL::ConvertParamsToBuffers(
        struct _FCGI_PARAM *a1,
        unsigned int a2,
        int a3,
        struct _LIST_ENTRY *a4)
{
  unsigned int v5; // r10d
  unsigned int i; // r9d
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 result; // rax
  struct FCGI_BUFFER *v13; // rax
  struct FCGI_BUFFER *v14; // rdi
  char *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // r12d
  __int64 v18; // rsi
  unsigned int v19; // ecx
  __int64 v20; // rax
  char *v21; // r8
  unsigned int v22; // ecx
  __int64 v23; // rax
  char *v24; // rbx
  char *v25; // rbx
  struct _LIST_ENTRY *Blink; // rdx
  int v27; // [rsp+78h] [rbp+10h]
  int v28; // [rsp+78h] [rbp+10h]

  v5 = 0;
  for ( i = 0;
        v5 < a2;
        i += *(_DWORD *)((char *)a1 + v10 + 8)
           + *(_DWORD *)((char *)a1 + v10 + 24)
           + (*(_DWORD *)((char *)a1 + v10 + 24) < 0x80u ? 1 : 4)
           + (*(_DWORD *)((char *)a1 + v10 + 8) < 0x80u ? 1 : 4) )
  {
    v10 = 32LL * v5++;
  }
  v11 = i + 16;
  if ( !a3 )
    v11 = i;
  if ( v11 > 0xFFFF )
    return 2147942511LL;
  v13 = FCGI_BUFFER::Alloc(v11);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = *(char **)v13;
  *((_QWORD *)v13 + 2) = *(_QWORD *)v13;
  v16 = v11 - 16;
  if ( !a3 )
    v16 = v11;
  *((_DWORD *)v14 + 6) = v16;
  v17 = 0;
  for ( *((_DWORD *)v14 + 7) = (a3 != 0) + 1; v17 < a2; v15 = &v25[*(unsigned int *)((char *)a1 + v18 + 24)] )
  {
    v18 = 32LL * v17;
    v19 = *(_DWORD *)((char *)a1 + v18 + 8);
    if ( v19 >= 0x80 )
    {
      HIBYTE(v27) = *(_DWORD *)((char *)a1 + v18 + 8);
      BYTE1(v27) = BYTE2(*(_DWORD *)((char *)a1 + v18 + 8));
      BYTE2(v27) = BYTE1(*(_DWORD *)((char *)a1 + v18 + 8));
      LOBYTE(v27) = HIBYTE(v19) | 0x80;
      *(_DWORD *)v15 = v27;
      v20 = 4;
    }
    else
    {
      *v15 = v19;
      v20 = 1;
    }
    v21 = &v15[v20];
    if ( !&v15[v20] )
      return 2147942414LL;
    v22 = *(_DWORD *)((char *)a1 + v18 + 24);
    if ( v22 >= 0x80 )
    {
      HIBYTE(v28) = *(_DWORD *)((char *)a1 + v18 + 24);
      BYTE1(v28) = BYTE2(*(_DWORD *)((char *)a1 + v18 + 24));
      BYTE2(v28) = BYTE1(*(_DWORD *)((char *)a1 + v18 + 24));
      LOBYTE(v28) = HIBYTE(v22) | 0x80;
      *(_DWORD *)v21 = v28;
      v23 = 4;
    }
    else
    {
      *v21 = v22;
      v23 = 1;
    }
    v24 = &v21[v23];
    if ( !&v21[v23] )
      return 2147942414LL;
    memcpy_0(v24, *(const void **)((char *)a1 + v18), *(unsigned int *)((char *)a1 + v18 + 8));
    v25 = &v24[*(unsigned int *)((char *)a1 + v18 + 8)];
    memcpy_0(v25, *(const void **)((char *)a1 + v18 + 16), *(unsigned int *)((char *)a1 + v18 + 24));
    ++v17;
  }
  Blink = a4->Blink;
  if ( Blink->Flink != a4 )
    __fastfail(3u);
  result = 0;
  *((_QWORD *)v14 + 4) = a4;
  *((_QWORD *)v14 + 5) = Blink;
  Blink->Flink = (struct _LIST_ENTRY *)((char *)v14 + 32);
  a4->Blink = (struct _LIST_ENTRY *)((char *)v14 + 32);
  return result;
}

```

## disassembly

```asm
0x1800031c0  push    rbx
0x1800031c2  push    rbp
0x1800031c3  push    rsi
0x1800031c4  push    rdi
0x1800031c5  push    r12
0x1800031c7  push    r13
0x1800031c9  push    r14
0x1800031cb  push    r15
0x1800031cd  sub     rsp, 28h
0x1800031d1  mov     rbp, r9
0x1800031d4  xor     r10d, r10d
0x1800031d7  xor     r9d, r9d
0x1800031da  mov     esi, r8d
0x1800031dd  mov     r15d, edx
0x1800031e0  mov     r14, rcx
0x1800031e3  mov     r13d, 80h
0x1800031e9  test    edx, edx
0x1800031eb  jz      short loc_18000322C
0x1800031ed  mov     r11d, 0FFFFFFFDh
0x1800031f3  mov     eax, r10d
0x1800031f6  shl     rax, 5
0x1800031fa  mov     r8d, [rax+r14+8]
0x1800031ff  mov     edx, [rax+r14+18h]
0x180003204  cmp     edx, r13d
0x180003207  sbb     eax, eax
0x180003209  and     eax, r11d
0x18000320c  add     eax, 4
0x18000320f  cmp     r8d, r13d
0x180003212  sbb     ecx, ecx
0x180003214  add     eax, edx
0x180003216  and     ecx, r11d
0x180003219  inc     r10d
0x18000321c  add     ecx, 4
0x18000321f  add     ecx, eax
0x180003221  add     ecx, r8d
0x180003224  add     r9d, ecx
0x180003227  cmp     r10d, r15d
0x18000322a  jb      short loc_1800031F3
0x18000322c  test    esi, esi
0x18000322e  lea     ebx, [r9+10h]
0x180003232  cmovz   ebx, r9d
0x180003236  cmp     ebx, 0FFFFh
0x18000323c  jbe     short loc_180003248
0x18000323e  mov     eax, 8007006Fh
0x180003243  jmp     loc_18000339C
0x180003248  mov     ecx, ebx; unsigned int
0x18000324a  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x18000324f  mov     rdi, rax
0x180003252  test    rax, rax
0x180003255  jnz     short loc_180003261
0x180003257  mov     eax, 8007000Eh
0x18000325c  jmp     loc_18000339C
0x180003261  mov     rdx, [rax]
0x180003264  test    esi, esi
0x180003266  mov     [rax+10h], rdx
0x18000326a  lea     eax, [rbx-10h]
0x18000326d  cmovz   eax, ebx
0x180003270  neg     esi
0x180003272  mov     [rdi+18h], eax
0x180003275  sbb     eax, eax
0x180003277  xor     r12d, r12d
0x18000327a  neg     eax
0x18000327c  inc     eax
0x18000327e  mov     [rdi+1Ch], eax
0x180003281  test    r15d, r15d
0x180003284  jz      loc_180003378
0x18000328a  mov     esi, r12d
0x18000328d  shl     rsi, 5
0x180003291  mov     [rsp+68h+arg_8], 0
0x180003299  mov     ecx, [rsi+r14+8]
0x18000329e  cmp     ecx, r13d
0x1800032a1  jnb     short loc_1800032AC
0x1800032a3  mov     [rdx], cl
0x1800032a5  mov     eax, 1
0x1800032aa  jmp     short loc_1800032D7
0x1800032ac  mov     eax, ecx
0x1800032ae  mov     byte ptr [rsp+68h+arg_8+3], cl
0x1800032b2  shr     eax, 10h
0x1800032b5  mov     byte ptr [rsp+68h+arg_8+1], al
0x1800032b9  mov     eax, ecx
0x1800032bb  shr     eax, 8
0x1800032be  mov     byte ptr [rsp+68h+arg_8+2], al
0x1800032c2  shr     ecx, 18h
0x1800032c5  or      cl, r13b
0x1800032c8  mov     byte ptr [rsp+68h+arg_8], cl
0x1800032cc  mov     eax, [rsp+68h+arg_8]
0x1800032d0  mov     [rdx], eax
0x1800032d2  mov     eax, 4
0x1800032d7  lea     r8, [rax+rdx]
0x1800032db  test    r8, r8
0x1800032de  jz      loc_180003257
0x1800032e4  mov     ecx, [rsi+r14+18h]
0x1800032e9  mov     [rsp+68h+arg_8], 0
0x1800032f1  cmp     ecx, r13d
0x1800032f4  jnb     short loc_180003300
0x1800032f6  mov     [r8], cl
0x1800032f9  mov     eax, 1
0x1800032fe  jmp     short loc_18000332C
0x180003300  mov     eax, ecx
0x180003302  mov     byte ptr [rsp+68h+arg_8+3], cl
0x180003306  shr     eax, 10h
0x180003309  mov     byte ptr [rsp+68h+arg_8+1], al
0x18000330d  mov     eax, ecx
0x18000330f  shr     eax, 8
0x180003312  mov     byte ptr [rsp+68h+arg_8+2], al
0x180003316  shr     ecx, 18h
0x180003319  or      cl, r13b
0x18000331c  mov     byte ptr [rsp+68h+arg_8], cl
0x180003320  mov     eax, [rsp+68h+arg_8]
0x180003324  mov     [r8], eax
0x180003327  mov     eax, 4
0x18000332c  lea     rbx, [r8+rax]
0x180003330  test    rbx, rbx
0x180003333  jz      loc_180003257
0x180003339  mov     r8d, [rsi+r14+8]; Size
0x18000333e  mov     rcx, rbx; void *
0x180003341  mov     rdx, [rsi+r14]; Src
0x180003345  call    memcpy_0
0x18000334a  mov     eax, [rsi+r14+8]
0x18000334f  mov     r8d, [rsi+r14+18h]; Size
0x180003354  add     rbx, rax
0x180003357  mov     rdx, [rsi+r14+10h]; Src
0x18000335c  mov     rcx, rbx; void *
0x18000335f  call    memcpy_0
0x180003364  mov     edx, [rsi+r14+18h]
0x180003369  inc     r12d
0x18000336c  add     rdx, rbx
0x18000336f  cmp     r12d, r15d
0x180003372  jb      loc_18000328A
0x180003378  mov     rdx, [rbp+8]
0x18000337c  cmp     [rdx], rbp
0x18000337f  jz      short loc_180003388
0x180003381  mov     ecx, 3
0x180003386  int     29h; Win8: RtlFailFast(ecx)
0x180003388  lea     rcx, [rdi+20h]
0x18000338c  xor     eax, eax
0x18000338e  mov     [rcx], rbp
0x180003391  mov     [rcx+8], rdx
0x180003395  mov     [rdx], rcx
0x180003398  mov     [rbp+8], rcx
0x18000339c  add     rsp, 28h
0x1800033a0  pop     r15
0x1800033a2  pop     r14
0x1800033a4  pop     r13
0x1800033a6  pop     r12
0x1800033a8  pop     rdi
0x1800033a9  pop     rsi
0x1800033aa  pop     rbp
0x1800033ab  pop     rbx
0x1800033ac  retn
```
