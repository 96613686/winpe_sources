# PerfpAddInstance(PERFLIBCI_MULTI_INSTS *,PCW_INSTANCE_BUFFER *,unsigned __int64)

- ea: `0x180003090`
- end: `0x180003418`
- name: `?PerfpAddInstance@@YAKPEAUPERFLIBCI_MULTI_INSTS@@PEAUPCW_INSTANCE_BUFFER@@_K@Z`
- size: `904`
- prototype: `__int64 __fastcall(struct PERFLIBCI_MULTI_INSTS *, struct PCW_INSTANCE_BUFFER *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005e70`
- `0x1800169ec`

## callees

- `0x180003090`
- `0x180008042`
- `0x18000805c`
- `0x18000db9c`
- `0x18000dbf0`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800030e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800030e6`

## pseudocode

```c
__int64 __fastcall PerfpAddInstance(struct PERFLIBCI_MULTI_INSTS *a1, struct PCW_INSTANCE_BUFFER *a2, __int64 a3)
{
  _QWORD *v3; // rsi
  unsigned int v4; // ebp
  __int64 v5; // r9
  struct PERFLIBCI_MULTI_INSTS *v7; // r12
  __int64 v8; // rbx
  __int64 v9; // r15
  int v10; // eax
  unsigned int v13; // r13d
  int v14; // r15d
  unsigned int v15; // ebp
  unsigned int *v16; // rdx
  unsigned int i; // r8d
  _DWORD *v18; // rax
  _DWORD *v19; // rsi
  __int64 v20; // r8
  unsigned int v21; // r13d
  _DWORD *v22; // rdi
  unsigned int *v23; // rbx
  __int64 v24; // rcx
  char *v25; // r9
  __int64 v26; // rdx
  __int64 *v27; // rcx
  __int64 v28; // rax
  char *v29; // [rsp+30h] [rbp-58h]
  int v31; // [rsp+98h] [rbp+10h]
  _QWORD *v33; // [rsp+A8h] [rbp+20h]

  v3 = (_QWORD *)*((_QWORD *)a1 + 1);
  v4 = *((_DWORD *)a2 + 1);
  v5 = a3;
  v29 = (char *)a1 + 8;
  v7 = a1;
  v8 = -1;
  if ( v3 )
  {
    while ( 1 )
    {
      v9 = v3[4];
      v10 = CompareStringOrdinal((LPCWCH)a2 + 8, -1, (LPCWCH)(v9 + 16), -1, 1);
      v31 = v10 - 2;
      if ( v10 == 2 )
      {
        if ( v4 >= *(_DWORD *)(v9 + 12) )
        {
          if ( v4 <= *(_DWORD *)(v9 + 12) )
            return 0;
          v31 = 1;
        }
        else
        {
          v31 = -1;
        }
      }
      v33 = v3;
      v3 = (_QWORD *)v3[1];
      if ( !v3 )
      {
        v5 = a3;
        goto LABEL_11;
      }
    }
  }
  v33 = 0;
  v31 = 0;
LABEL_11:
  while ( *((_WORD *)a2 + v8++ + 9) != 0 )
    ;
  v13 = 2 * v8 + 2;
  v14 = (2 * v8 + 9) & 0xFFFFFFF8;
  v15 = v14 + 64;
  if ( v14 + 64 < v13 )
    return 534;
  v16 = (unsigned int *)((char *)a2 + *((unsigned int *)a2 + 2));
  for ( i = 0; i < *((_DWORD *)a2 + 3); ++i )
  {
    if ( _bittest64(&v5, *((unsigned __int8 *)v16 + 4)) )
    {
      v15 += ((*((unsigned __int16 *)v16 + 3) + 7) & 0xFFFFFFF8) + 8;
      if ( v15 < (unsigned __int64)((*((unsigned __int16 *)v16 + 3) + 7) & 0xFFFFFFF8) + 8 )
        return 534;
    }
    v16 = (unsigned int *)((char *)v16 + *v16);
  }
  v18 = operator new(v15, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v18;
  if ( !v18 )
    return 14;
  memset_0(v18, 0, v15);
  v19[15] = *((_DWORD *)a2 + 1);
  v19[14] = v14 + 8;
  memcpy_0(v19 + 16, (char *)a2 + 16, v13);
  v21 = 0;
  v22 = (_DWORD *)((char *)v19 + (unsigned int)v19[14] + 56);
  v23 = (unsigned int *)((char *)a2 + *((unsigned int *)a2 + 2));
  if ( *((_DWORD *)a2 + 3) )
  {
    v24 = a3;
    do
    {
      if ( _bittest64(&v24, *((unsigned __int8 *)v23 + 4)) )
      {
        v22[1] = ((*((unsigned __int16 *)v23 + 3) + 7) & 0xFFFFFFF8) + 8;
        *v22 = *((unsigned __int16 *)v23 + 3);
        memcpy_0(v22 + 2, v23 + 2, *((unsigned __int16 *)v23 + 3));
        v24 = a3;
        v22 = (_DWORD *)((char *)v22 + (unsigned int)v22[1]);
      }
      ++v21;
      v23 = (unsigned int *)((char *)v23 + *v23);
    }
    while ( v21 < *((_DWORD *)a2 + 3) );
    v7 = a1;
  }
  *((_QWORD *)v19 + 4) = v19 + 12;
  *((_QWORD *)v19 + 2) = v33;
  v19[10] = 1;
  v19[12] = v15 - v14 - 64;
  *((_QWORD *)v19 + 3) = *(_QWORD *)v7;
  *(_QWORD *)v7 = v19;
  if ( v33 )
  {
    v25 = v29;
    if ( v31 >= 0 )
      v33[1] = v19;
    else
      *v33 = v19;
  }
  else
  {
    v25 = (char *)v7 + 8;
    *((_QWORD *)v7 + 1) = v19;
  }
  if ( v25 && *(_QWORD *)v25 && v19 != *(_DWORD **)v25 )
  {
    do
    {
      v26 = *((_QWORD *)v19 + 2);
      if ( !v26 )
        break;
      if ( !*(_DWORD *)(v26 + 40) )
        break;
      v27 = *(__int64 **)(v26 + 16);
      if ( !v27 )
        break;
      v28 = *v27;
      if ( v26 == *v27 )
      {
        v28 = v27[1];
        if ( !v28 || *(_DWORD *)(v28 + 40) != 1 )
        {
          if ( v19 == *(_DWORD **)(v26 + 8) )
          {
            v19 = (_DWORD *)*((_QWORD *)v19 + 2);
            PerflibciRotateLeft(v25, v26);
          }
          *(_DWORD *)(*((_QWORD *)v19 + 2) + 40LL) = 0;
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v19 + 2) + 16LL) + 40LL) = 1;
          PerflibciRotateRight(v25, *(_QWORD *)(*((_QWORD *)v19 + 2) + 16LL), v20, v25);
          continue;
        }
      }
      else if ( !v28 || *(_DWORD *)(v28 + 40) != 1 )
      {
        if ( v19 == *(_DWORD **)v26 )
        {
          v19 = (_DWORD *)*((_QWORD *)v19 + 2);
          PerflibciRotateRight(v25, v26, v20, v25);
        }
        *(_DWORD *)(*((_QWORD *)v19 + 2) + 40LL) = 0;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v19 + 2) + 16LL) + 40LL) = 1;
        PerflibciRotateLeft(v25, *(_QWORD *)(*((_QWORD *)v19 + 2) + 16LL));
        continue;
      }
      *(_DWORD *)(v26 + 40) = 0;
      *(_DWORD *)(v28 + 40) = 0;
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v19 + 2) + 16LL) + 40LL) = 1;
      v19 = *(_DWORD **)(*((_QWORD *)v19 + 2) + 16LL);
    }
    while ( v19 != *(_DWORD **)v25 );
  }
  *(_DWORD *)(*(_QWORD *)v25 + 40LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180003090  mov     [rsp+arg_10], r8
0x180003095  mov     [rsp+arg_0], rcx
0x18000309a  push    rbx
0x18000309b  push    rbp
0x18000309c  push    rsi
0x18000309d  push    rdi
0x18000309e  push    r12
0x1800030a0  push    r14
0x1800030a2  push    r15
0x1800030a4  sub     rsp, 50h
0x1800030a8  mov     rsi, [rcx+8]
0x1800030ac  lea     rax, [rcx+8]
0x1800030b0  mov     ebp, [rdx+4]
0x1800030b3  mov     r9, r8
0x1800030b6  mov     [rsp+88h+var_58], rax
0x1800030bb  mov     r14, rdx
0x1800030be  mov     r12, rcx
0x1800030c1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800030c8  test    rsi, rsi
0x1800030cb  jz      short loc_180003138
0x1800030cd  mov     r15, [rsi+20h]
0x1800030d1  lea     rcx, [r14+10h]; lpString1
0x1800030d5  mov     r9d, ebx; cchCount2
0x1800030d8  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800030e0  mov     edx, ebx; cchCount1
0x1800030e2  lea     r8, [r15+10h]; lpString2
0x1800030e6  call    cs:__imp_CompareStringOrdinal
0x1800030ec  lea     ecx, [rax-2]
0x1800030ef  mov     [rsp+88h+arg_8], ecx
0x1800030f6  test    ecx, ecx
0x1800030f8  jnz     short loc_180003116
0x1800030fa  cmp     ebp, [r15+0Ch]
0x1800030fe  jnb     short loc_180003109
0x180003100  mov     [rsp+88h+arg_8], ebx
0x180003107  jmp     short loc_180003116
0x180003109  jbe     short loc_180003131
0x18000310b  mov     [rsp+88h+arg_8], 1
0x180003116  mov     [rsp+88h+arg_18], rsi
0x18000311e  mov     rsi, [rsi+8]
0x180003122  test    rsi, rsi
0x180003125  jnz     short loc_1800030CD
0x180003127  mov     r9, [rsp+88h+arg_10]
0x18000312f  jmp     short loc_180003149
0x180003131  xor     eax, eax
0x180003133  jmp     loc_180003409
0x180003138  xor     eax, eax
0x18000313a  mov     [rsp+88h+arg_18], rax
0x180003142  mov     [rsp+88h+arg_8], eax
0x180003149  mov     [rsp+88h+var_40], r13
0x18000314e  xchg    ax, ax
0x180003150  cmp     word ptr [r14+rbx*2+12h], 0
0x180003157  lea     rbx, [rbx+1]
0x18000315b  jnz     short loc_180003150
0x18000315d  lea     r13d, ds:2[rbx*2]
0x180003165  mov     r10d, 0FFFFFFF8h
0x18000316b  lea     r15d, [r13+7]
0x18000316f  and     r15d, r10d
0x180003172  lea     ebp, [r15+40h]
0x180003176  cmp     ebp, r13d
0x180003179  jb      loc_1800033FF
0x18000317f  mov     edx, [r14+8]
0x180003183  add     rdx, r14
0x180003186  xor     r8d, r8d
0x180003189  cmp     r8d, [r14+0Ch]
0x18000318d  jnb     short loc_1800031C6
0x18000318f  movzx   eax, byte ptr [rdx+4]
0x180003193  bt      r9, rax
0x180003197  jnb     short loc_1800031BC
0x180003199  movzx   ecx, word ptr [rdx+6]
0x18000319d  add     ecx, 7
0x1800031a0  mov     eax, ecx
0x1800031a2  and     rcx, r10
0x1800031a5  and     eax, r10d
0x1800031a8  add     rcx, 8
0x1800031ac  add     eax, 8
0x1800031af  add     ebp, eax
0x1800031b1  mov     eax, ebp
0x1800031b3  cmp     rax, rcx
0x1800031b6  jb      loc_1800033FF
0x1800031bc  mov     eax, [rdx]
0x1800031be  add     rdx, rax
0x1800031c1  inc     r8d
0x1800031c4  jmp     short loc_180003189
0x1800031c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800031cd  mov     ecx, ebp; unsigned __int64
0x1800031cf  mov     ebx, ebp
0x1800031d1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800031d6  mov     rsi, rax
0x1800031d9  test    rax, rax
0x1800031dc  jz      loc_1800033F8
0x1800031e2  mov     r8d, ebx; Size
0x1800031e5  xor     edx, edx; Val
0x1800031e7  mov     rcx, rax; void *
0x1800031ea  call    memset_0
0x1800031ef  mov     eax, [r14+4]
0x1800031f3  lea     rbx, [rsi+38h]
0x1800031f7  mov     [rbx+4], eax
0x1800031fa  lea     rcx, [rbx+8]; void *
0x1800031fe  lea     eax, [r15+8]
0x180003202  mov     r8d, r13d; Size
0x180003205  lea     rdx, [r14+10h]; Src
0x180003209  mov     [rbx], eax
0x18000320b  call    memcpy_0
0x180003210  mov     edi, [rbx]
0x180003212  xor     r13d, r13d
0x180003215  add     rdi, rbx
0x180003218  mov     ebx, [r14+8]
0x18000321c  add     rbx, r14
0x18000321f  cmp     [r14+0Ch], r13d
0x180003223  jbe     short loc_180003289
0x180003225  mov     rcx, [rsp+88h+arg_10]
0x18000322d  mov     r12d, 0FFFFFFF8h
0x180003233  movzx   eax, byte ptr [rbx+4]
0x180003237  bt      rcx, rax
0x18000323b  jnb     short loc_180003273
0x18000323d  movzx   eax, word ptr [rbx+6]
0x180003241  lea     rdx, [rbx+8]; Src
0x180003245  add     eax, 7
0x180003248  lea     rcx, [rdi+8]; void *
0x18000324c  and     eax, r12d
0x18000324f  add     eax, 8
0x180003252  mov     [rdi+4], eax
0x180003255  movzx   eax, word ptr [rbx+6]
0x180003259  mov     [rdi], eax
0x18000325b  movzx   r8d, word ptr [rbx+6]; Size
0x180003260  call    memcpy_0
0x180003265  mov     eax, [rdi+4]
0x180003268  mov     rcx, [rsp+88h+arg_10]
0x180003270  add     rdi, rax
0x180003273  mov     eax, [rbx]
0x180003275  inc     r13d
0x180003278  add     rbx, rax
0x18000327b  cmp     r13d, [r14+0Ch]
0x18000327f  jb      short loc_180003233
0x180003281  mov     r12, [rsp+88h+arg_0]
0x180003289  mov     rcx, [rsp+88h+arg_18]
0x180003291  lea     rax, [rsi+30h]
0x180003295  mov     [rsi+20h], rax
0x180003299  sub     ebp, r15d
0x18000329c  mov     [rsi+10h], rcx
0x1800032a0  sub     ebp, 40h ; '@'
0x1800032a3  mov     dword ptr [rsi+28h], 1
0x1800032aa  mov     [rax], ebp
0x1800032ac  mov     rax, [r12]
0x1800032b0  mov     [rsi+18h], rax
0x1800032b4  mov     [r12], rsi
0x1800032b8  test    rcx, rcx
0x1800032bb  jnz     short loc_1800032C7
0x1800032bd  lea     r9, [r12+8]
0x1800032c2  mov     [r9], rsi
0x1800032c5  jmp     short loc_1800032DF
0x1800032c7  cmp     [rsp+88h+arg_8], 0
0x1800032cf  mov     r9, [rsp+88h+var_58]
0x1800032d4  jge     short loc_1800032DB
0x1800032d6  mov     [rcx], rsi
0x1800032d9  jmp     short loc_1800032DF
0x1800032db  mov     [rcx+8], rsi
0x1800032df  test    r9, r9
0x1800032e2  jz      loc_1800033EA
0x1800032e8  mov     rax, [r9]
0x1800032eb  test    rax, rax
0x1800032ee  jz      loc_1800033EA
0x1800032f4  cmp     rsi, rax
0x1800032f7  jz      loc_1800033EA
0x1800032fd  mov     rdx, [rsi+10h]
0x180003301  test    rdx, rdx
0x180003304  jz      loc_1800033EA
0x18000330a  cmp     dword ptr [rdx+28h], 0
0x18000330e  jz      loc_1800033EA
0x180003314  mov     rcx, [rdx+10h]
0x180003318  test    rcx, rcx
0x18000331b  jz      loc_1800033EA
0x180003321  mov     rax, [rcx]
0x180003324  cmp     rdx, rax
0x180003327  jnz     short loc_180003375
0x180003329  mov     rax, [rcx+8]
0x18000332d  test    rax, rax
0x180003330  jz      short loc_180003338
0x180003332  cmp     dword ptr [rax+28h], 1
0x180003336  jz      short loc_180003380
0x180003338  cmp     rsi, [rdx+8]
0x18000333c  jnz     short loc_180003349
0x18000333e  mov     rcx, r9
0x180003341  mov     rsi, rdx
0x180003344  call    PerflibciRotateLeft
0x180003349  mov     rax, [rsi+10h]
0x18000334d  mov     dword ptr [rax+28h], 0
0x180003354  mov     rax, [rsi+10h]
0x180003358  mov     rcx, [rax+10h]
0x18000335c  mov     dword ptr [rcx+28h], 1
0x180003363  mov     rcx, r9
0x180003366  mov     rdx, [rsi+10h]
0x18000336a  mov     rdx, [rdx+10h]
0x18000336e  call    PerflibciRotateRight
0x180003373  jmp     short loc_1800033E1
0x180003375  test    rax, rax
0x180003378  jz      short loc_1800033A7
0x18000337a  cmp     dword ptr [rax+28h], 1
0x18000337e  jnz     short loc_1800033A7
0x180003380  mov     dword ptr [rdx+28h], 0
0x180003387  mov     dword ptr [rax+28h], 0
0x18000338e  mov     rax, [rsi+10h]
0x180003392  mov     rcx, [rax+10h]
0x180003396  mov     dword ptr [rcx+28h], 1
0x18000339d  mov     rax, [rsi+10h]
0x1800033a1  mov     rsi, [rax+10h]
0x1800033a5  jmp     short loc_1800033E1
0x1800033a7  cmp     rsi, [rdx]
0x1800033aa  jnz     short loc_1800033B7
0x1800033ac  mov     rcx, r9
0x1800033af  mov     rsi, rdx
0x1800033b2  call    PerflibciRotateRight
0x1800033b7  mov     rax, [rsi+10h]
0x1800033bb  mov     dword ptr [rax+28h], 0
0x1800033c2  mov     rax, [rsi+10h]
0x1800033c6  mov     rcx, [rax+10h]
0x1800033ca  mov     dword ptr [rcx+28h], 1
0x1800033d1  mov     rcx, r9
0x1800033d4  mov     rdx, [rsi+10h]
0x1800033d8  mov     rdx, [rdx+10h]
0x1800033dc  call    PerflibciRotateLeft
0x1800033e1  cmp     rsi, [r9]
0x1800033e4  jnz     loc_1800032FD
0x1800033ea  mov     rax, [r9]
0x1800033ed  mov     dword ptr [rax+28h], 0
0x1800033f4  xor     eax, eax
0x1800033f6  jmp     short loc_180003404
0x1800033f8  mov     eax, 0Eh
0x1800033fd  jmp     short loc_180003404
0x1800033ff  mov     eax, 216h
0x180003404  mov     r13, [rsp+88h+var_40]
0x180003409  add     rsp, 50h
0x18000340d  pop     r15
0x18000340f  pop     r14
0x180003411  pop     r12
0x180003413  pop     rdi
0x180003414  pop     rsi
0x180003415  pop     rbp
0x180003416  pop     rbx
0x180003417  retn
```
