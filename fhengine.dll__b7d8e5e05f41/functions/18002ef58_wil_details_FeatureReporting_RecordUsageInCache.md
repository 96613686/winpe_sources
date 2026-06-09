# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18002ef58`
- end: `0x18002f0cf`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ccf4`

## callees

- `0x18002edac`
- `0x18002ee7c`
- `0x18002ef58`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x18002ef58  mov     [rsp+arg_0], rbx
0x18002ef5d  push    rdi
0x18002ef5e  sub     rsp, 20h
0x18002ef62  xor     eax, eax
0x18002ef64  xorps   xmm0, xmm0
0x18002ef67  mov     r10, rdx
0x18002ef6a  mov     rbx, rcx
0x18002ef6d  mov     r9d, r8d
0x18002ef70  movups  xmmword ptr [rcx], xmm0
0x18002ef73  mov     [rcx+10h], rax
0x18002ef77  test    r8d, r8d
0x18002ef7a  jz      loc_18002F0B3
0x18002ef80  sub     r9d, 1
0x18002ef84  jz      loc_18002F0A3
0x18002ef8a  sub     r9d, 1
0x18002ef8e  jz      loc_18002F02B
0x18002ef94  sub     r9d, 1
0x18002ef98  jz      loc_18002F02B
0x18002ef9e  sub     r9d, 1
0x18002efa2  jz      loc_18002F0B3
0x18002efa8  sub     r9d, 1
0x18002efac  jz      loc_18002F0A3
0x18002efb2  sub     r9d, 1
0x18002efb6  jz      short loc_18002F02B
0x18002efb8  cmp     r9d, 1
0x18002efbc  jz      short loc_18002F02B
0x18002efbe  lea     r11d, [r8-140h]
0x18002efc5  lea     r9d, [rax+1]
0x18002efc9  cmp     r11d, 40h ; '@'
0x18002efcd  jge     short loc_18002F017
0x18002efcf  mov     eax, [rdx+4]
0x18002efd2  lea     ecx, [r9+0Fh]
0x18002efd6  mov     edi, r11d
0x18002efd9  shl     edi, 5
0x18002efdc  test    cl, al
0x18002efde  jz      short loc_18002EFF2
0x18002efe0  mov     edx, eax
0x18002efe2  shr     edx, 5
0x18002efe5  and     edx, 3Fh
0x18002efe8  cmp     edx, r11d
0x18002efeb  jnz     short loc_18002EFF2
0x18002efed  mov     edx, r9d
0x18002eff0  jmp     short loc_18002EFF4
0x18002eff2  xor     edx, edx
0x18002eff4  mov     [rbx+10h], edx
0x18002eff7  mov     edx, edi
0x18002eff9  xor     edx, eax
0x18002effb  and     edx, 7E0h
0x18002f001  xor     edx, eax
0x18002f003  or      edx, ecx
0x18002f005  lock cmpxchg [r10+4], edx
0x18002f00b  jnz     short loc_18002EFDC
0x18002f00d  cmp     dword ptr [rbx+10h], 0
0x18002f011  jnz     loc_18002F0C1
0x18002f017  mov     [rbx+8], r8d
0x18002f01b  mov     [rbx+4], r9d
0x18002f01f  mov     dword ptr [rbx+0Ch], 0
0x18002f026  jmp     loc_18002F0C1
0x18002f02b  xor     ecx, ecx
0x18002f02d  sub     r8d, 2
0x18002f031  jz      short loc_18002F059
0x18002f033  sub     r8d, 1
0x18002f037  jz      short loc_18002F052
0x18002f039  sub     r8d, 3
0x18002f03d  jz      short loc_18002F04B
0x18002f03f  cmp     r8d, 1
0x18002f043  jnz     short loc_18002F05E
0x18002f045  lea     ecx, [r8+0Fh]
0x18002f049  jmp     short loc_18002F05E
0x18002f04b  mov     ecx, 4
0x18002f050  jmp     short loc_18002F05E
0x18002f052  mov     ecx, 8
0x18002f057  jmp     short loc_18002F05E
0x18002f059  mov     ecx, 2
0x18002f05e  mov     edx, [rdx]
0x18002f060  mov     r9d, 1
0x18002f066  xor     eax, eax
0x18002f068  mov     r8d, ecx
0x18002f06b  or      r8d, edx
0x18002f06e  cmp     r8d, edx
0x18002f071  mov     r11d, r8d
0x18002f074  setz    al
0x18002f077  or      r11d, r9d
0x18002f07a  cmp     r8d, edx
0x18002f07d  mov     [rbx+10h], eax
0x18002f080  mov     eax, edx
0x18002f082  cmovz   r11d, r8d
0x18002f086  lock cmpxchg [r10], r11d
0x18002f08b  jz      short loc_18002F091
0x18002f08d  mov     edx, eax
0x18002f08f  jmp     short loc_18002F066
0x18002f091  test    r9b, r11b
0x18002f094  jz      short loc_18002F09B
0x18002f096  test    r9b, dl
0x18002f099  jz      short loc_18002F09E
0x18002f09b  xor     r9d, r9d
0x18002f09e  mov     [rbx], r9d
0x18002f0a1  jmp     short loc_18002F0C1
0x18002f0a3  mov     r9, rbx
0x18002f0a6  mov     edx, r8d
0x18002f0a9  mov     rcx, r10
0x18002f0ac  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18002f0b1  jmp     short loc_18002F0C1
0x18002f0b3  mov     r9, rbx
0x18002f0b6  mov     edx, r8d
0x18002f0b9  mov     rcx, r10
0x18002f0bc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18002f0c1  mov     rax, rbx
0x18002f0c4  mov     rbx, [rsp+28h+arg_0]
0x18002f0c9  add     rsp, 20h
0x18002f0cd  pop     rdi
0x18002f0ce  retn
```
