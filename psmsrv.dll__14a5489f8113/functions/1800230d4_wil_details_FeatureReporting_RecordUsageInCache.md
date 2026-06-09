# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800230d4`
- end: `0x180023263`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002339c`

## callees

- `0x180022f20`
- `0x180022ff4`
- `0x1800230d4`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  int *v8; // r9
  int v9; // r8d
  unsigned __int32 v10; // eax
  BOOL v11; // edx
  unsigned __int32 v12; // ett
  int v13; // ecx
  signed __int32 v14; // edx
  int v15; // r10d
  signed __int32 v16; // r11d
  signed __int32 v17; // eax

  v8 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a5, a1);
      return v8;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a5, a1);
      return v8;
    case 5u:
      goto LABEL_34;
  }
  if ( a3 - 6 >= 2 )
  {
    v9 = a3 - 320;
    if ( v9 >= 64 )
      goto LABEL_16;
    v10 = *((_DWORD *)a2 + 1);
    do
    {
      v11 = (v10 & 0x10) != 0 && ((v10 >> 5) & 0x3F) == v9;
      *(_DWORD *)(a1 + 16) = v11;
      v12 = v10;
      v10 = _InterlockedCompareExchange(
              a2 + 1,
              v10 ^ ((unsigned __int16)v10 ^ (unsigned __int16)(32 * v9)) & 0x7E0 | 0x10,
              v10);
    }
    while ( v12 != v10 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 4) = a5;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v8;
  }
LABEL_17:
  v13 = 0;
  switch ( a3 )
  {
    case 2u:
      v13 = 2;
      break;
    case 3u:
      v13 = 8;
      break;
    case 6u:
      v13 = 4;
      break;
    case 7u:
      v13 = 16;
      break;
  }
  v14 = *a2;
  v15 = 1;
  while ( 1 )
  {
    v16 = v14 | v13 | 1;
    v8[4] = (v14 | v13) == v14;
    if ( (v14 | v13) == v14 )
      v16 = v14 | v13;
    v17 = _InterlockedCompareExchange(a2, v16, v14);
    if ( v14 == v17 )
      break;
    v14 = v17;
  }
  if ( (v16 & 1) == 0 || (v14 & 1) != 0 )
    v15 = 0;
  *v8 = v15;
  return v8;
}

```

## disassembly

```asm
0x1800230d4  mov     [rsp+arg_0], rbx
0x1800230d9  mov     [rsp+arg_8], rsi
0x1800230de  push    rdi
0x1800230df  sub     rsp, 20h
0x1800230e3  xor     eax, eax
0x1800230e5  xorps   xmm0, xmm0
0x1800230e8  mov     esi, r9d
0x1800230eb  mov     r11d, r8d
0x1800230ee  mov     rbx, rdx
0x1800230f1  mov     r9, rcx
0x1800230f4  mov     r10d, r8d
0x1800230f7  movups  xmmword ptr [rcx], xmm0
0x1800230fa  mov     [rcx+10h], rax
0x1800230fe  test    r8d, r8d
0x180023101  jz      loc_180023240
0x180023107  sub     r10d, 1
0x18002310b  jz      loc_18002322E
0x180023111  sub     r10d, 1
0x180023115  jz      loc_1800231B5
0x18002311b  sub     r10d, 1
0x18002311f  jz      loc_1800231B5
0x180023125  sub     r10d, 1
0x180023129  jz      loc_180023240
0x18002312f  sub     r10d, 1
0x180023133  jz      loc_18002322E
0x180023139  sub     r10d, 1
0x18002313d  jz      short loc_1800231B5
0x18002313f  cmp     r10d, 1
0x180023143  jz      short loc_1800231B5
0x180023145  add     r8d, 0FFFFFEC0h
0x18002314c  cmp     r8d, 40h ; '@'
0x180023150  jge     short loc_1800231A0
0x180023152  mov     eax, [rdx+4]
0x180023155  mov     ecx, 10h
0x18002315a  mov     edi, r8d
0x18002315d  shl     edi, 5
0x180023160  lea     r10d, [rcx-0Fh]
0x180023164  test    cl, al
0x180023166  jz      short loc_18002317A
0x180023168  mov     edx, eax
0x18002316a  shr     edx, 5
0x18002316d  and     edx, 3Fh
0x180023170  cmp     edx, r8d
0x180023173  jnz     short loc_18002317A
0x180023175  mov     edx, r10d
0x180023178  jmp     short loc_18002317C
0x18002317a  xor     edx, edx
0x18002317c  mov     [r9+10h], edx
0x180023180  mov     edx, edi
0x180023182  xor     edx, eax
0x180023184  and     edx, 7E0h
0x18002318a  xor     edx, eax
0x18002318c  or      edx, ecx
0x18002318e  lock cmpxchg [rbx+4], edx
0x180023193  jnz     short loc_180023164
0x180023195  cmp     dword ptr [r9+10h], 0
0x18002319a  jnz     loc_180023250
0x1800231a0  mov     eax, [rsp+28h+arg_20]
0x1800231a4  mov     [r9+4], eax
0x1800231a8  mov     [r9+8], r11d
0x1800231ac  mov     [r9+0Ch], esi
0x1800231b0  jmp     loc_180023250
0x1800231b5  xor     ecx, ecx
0x1800231b7  sub     r11d, 2
0x1800231bb  jz      short loc_1800231E3
0x1800231bd  sub     r11d, 1
0x1800231c1  jz      short loc_1800231DC
0x1800231c3  sub     r11d, 3
0x1800231c7  jz      short loc_1800231D5
0x1800231c9  cmp     r11d, 1
0x1800231cd  jnz     short loc_1800231E8
0x1800231cf  lea     ecx, [r11+0Fh]
0x1800231d3  jmp     short loc_1800231E8
0x1800231d5  mov     ecx, 4
0x1800231da  jmp     short loc_1800231E8
0x1800231dc  mov     ecx, 8
0x1800231e1  jmp     short loc_1800231E8
0x1800231e3  mov     ecx, 2
0x1800231e8  mov     edx, [rdx]
0x1800231ea  mov     r10d, 1
0x1800231f0  xor     eax, eax
0x1800231f2  mov     r8d, ecx
0x1800231f5  or      r8d, edx
0x1800231f8  cmp     r8d, edx
0x1800231fb  mov     r11d, r8d
0x1800231fe  setz    al
0x180023201  or      r11d, r10d
0x180023204  cmp     r8d, edx
0x180023207  mov     [r9+10h], eax
0x18002320b  mov     eax, edx
0x18002320d  cmovz   r11d, r8d
0x180023211  lock cmpxchg [rbx], r11d
0x180023216  jz      short loc_18002321C
0x180023218  mov     edx, eax
0x18002321a  jmp     short loc_1800231F0
0x18002321c  test    r10b, r11b
0x18002321f  jz      short loc_180023226
0x180023221  test    r10b, dl
0x180023224  jz      short loc_180023229
0x180023226  xor     r10d, r10d
0x180023229  mov     [r9], r10d
0x18002322c  jmp     short loc_180023250
0x18002322e  mov     r8d, [rsp+28h+arg_20]
0x180023233  mov     edx, r11d
0x180023236  mov     rcx, rbx
0x180023239  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18002323e  jmp     short loc_180023250
0x180023240  mov     r8d, [rsp+28h+arg_20]
0x180023245  mov     edx, r11d
0x180023248  mov     rcx, rbx
0x18002324b  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180023250  mov     rbx, [rsp+28h+arg_0]
0x180023255  mov     rax, r9
0x180023258  mov     rsi, [rsp+28h+arg_8]
0x18002325d  add     rsp, 20h
0x180023261  pop     rdi
0x180023262  retn
```
