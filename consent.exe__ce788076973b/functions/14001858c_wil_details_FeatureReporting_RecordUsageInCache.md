# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14001858c`
- end: `0x140018707`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: `int *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001783c`
- `0x14001d178`

## callees

- `0x1400183e0`
- `0x1400184b0`
- `0x14001858c`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  int *v6; // r9
  int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x14001858c  mov     [rsp+arg_0], rbx
0x140018591  mov     [rsp+arg_8], rsi
0x140018596  push    rdi
0x140018597  sub     rsp, 20h
0x14001859b  xor     eax, eax
0x14001859d  xorps   xmm0, xmm0
0x1400185a0  mov     esi, r9d
0x1400185a3  mov     r11, rdx
0x1400185a6  mov     r9, rcx
0x1400185a9  mov     r10d, r8d
0x1400185ac  movups  xmmword ptr [rcx], xmm0
0x1400185af  mov     [rcx+10h], rax
0x1400185b3  test    r8d, r8d
0x1400185b6  jz      loc_1400186E9
0x1400185bc  sub     r10d, 1
0x1400185c0  jz      loc_1400186DC
0x1400185c6  sub     r10d, 1
0x1400185ca  jz      loc_140018663
0x1400185d0  sub     r10d, 1
0x1400185d4  jz      loc_140018663
0x1400185da  sub     r10d, 1
0x1400185de  jz      loc_1400186E9
0x1400185e4  sub     r10d, 1
0x1400185e8  jz      loc_1400186DC
0x1400185ee  sub     r10d, 1
0x1400185f2  jz      short loc_140018663
0x1400185f4  cmp     r10d, 1
0x1400185f8  jz      short loc_140018663
0x1400185fa  lea     ebx, [r8-140h]
0x140018601  lea     r10d, [rax+1]
0x140018605  cmp     ebx, 40h ; '@'
0x140018608  jge     short loc_140018652
0x14001860a  mov     eax, [rdx+4]
0x14001860d  lea     ecx, [r10+0Fh]
0x140018611  mov     edi, ebx
0x140018613  shl     edi, 5
0x140018616  test    cl, al
0x140018618  jz      short loc_14001862B
0x14001861a  mov     edx, eax
0x14001861c  shr     edx, 5
0x14001861f  and     edx, 3Fh
0x140018622  cmp     edx, ebx
0x140018624  jnz     short loc_14001862B
0x140018626  mov     edx, r10d
0x140018629  jmp     short loc_14001862D
0x14001862b  xor     edx, edx
0x14001862d  mov     [r9+10h], edx
0x140018631  mov     edx, edi
0x140018633  xor     edx, eax
0x140018635  and     edx, 7E0h
0x14001863b  xor     edx, eax
0x14001863d  or      edx, ecx
0x14001863f  lock cmpxchg [r11+4], edx
0x140018645  jnz     short loc_140018616
0x140018647  cmp     dword ptr [r9+10h], 0
0x14001864c  jnz     loc_1400186F4
0x140018652  mov     [r9+8], r8d
0x140018656  mov     [r9+4], r10d
0x14001865a  mov     [r9+0Ch], esi
0x14001865e  jmp     loc_1400186F4
0x140018663  xor     ecx, ecx
0x140018665  sub     r8d, 2
0x140018669  jz      short loc_140018691
0x14001866b  sub     r8d, 1
0x14001866f  jz      short loc_14001868A
0x140018671  sub     r8d, 3
0x140018675  jz      short loc_140018683
0x140018677  cmp     r8d, 1
0x14001867b  jnz     short loc_140018696
0x14001867d  lea     ecx, [r8+0Fh]
0x140018681  jmp     short loc_140018696
0x140018683  mov     ecx, 4
0x140018688  jmp     short loc_140018696
0x14001868a  mov     ecx, 8
0x14001868f  jmp     short loc_140018696
0x140018691  mov     ecx, 2
0x140018696  mov     edx, [rdx]
0x140018698  mov     r10d, 1
0x14001869e  xor     eax, eax
0x1400186a0  mov     r8d, ecx
0x1400186a3  or      r8d, edx
0x1400186a6  cmp     r8d, edx
0x1400186a9  mov     ebx, r8d
0x1400186ac  setz    al
0x1400186af  or      ebx, r10d
0x1400186b2  cmp     r8d, edx
0x1400186b5  mov     [r9+10h], eax
0x1400186b9  mov     eax, edx
0x1400186bb  cmovz   ebx, r8d
0x1400186bf  lock cmpxchg [r11], ebx
0x1400186c4  jz      short loc_1400186CA
0x1400186c6  mov     edx, eax
0x1400186c8  jmp     short loc_14001869E
0x1400186ca  test    r10b, bl
0x1400186cd  jz      short loc_1400186D4
0x1400186cf  test    r10b, dl
0x1400186d2  jz      short loc_1400186D7
0x1400186d4  xor     r10d, r10d
0x1400186d7  mov     [r9], r10d
0x1400186da  jmp     short loc_1400186F4
0x1400186dc  mov     edx, r8d
0x1400186df  mov     rcx, r11
0x1400186e2  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1400186e7  jmp     short loc_1400186F4
0x1400186e9  mov     edx, r8d
0x1400186ec  mov     rcx, r11
0x1400186ef  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1400186f4  mov     rbx, [rsp+28h+arg_0]
0x1400186f9  mov     rax, r9
0x1400186fc  mov     rsi, [rsp+28h+arg_8]
0x140018701  add     rsp, 20h
0x140018705  pop     rdi
0x140018706  retn
```
