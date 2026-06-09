# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000ac3c`
- end: `0x14000ad06`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ade8`

## callees

- `0x14000ac3c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x14000ac3c  push    rbx
0x14000ac3e  push    rsi
0x14000ac3f  push    rdi
0x14000ac40  mov     r8d, [rcx]
0x14000ac43  lea     r10, [r9+8]
0x14000ac47  xor     ebx, ebx
0x14000ac49  mov     r11d, edx
0x14000ac4c  cmp     edx, 5
0x14000ac4f  mov     rdi, rcx
0x14000ac52  mov     esi, 1
0x14000ac57  setz    bl
0x14000ac5a  mov     eax, r8d
0x14000ac5d  mov     dword ptr [r9+4], 0
0x14000ac65  or      eax, esi
0x14000ac67  mov     ecx, eax
0x14000ac69  shr     ecx, 16h
0x14000ac6c  and     ecx, esi
0x14000ac6e  cmp     ecx, ebx
0x14000ac70  jz      short loc_14000ACAF
0x14000ac72  mov     edx, eax
0x14000ac74  shr     edx, 0Fh
0x14000ac77  and     edx, 7Fh
0x14000ac7a  jbe     short loc_14000AC97
0x14000ac7c  cmp     r11d, esi
0x14000ac7f  mov     [r9+4], edx
0x14000ac83  mov     ecx, 5
0x14000ac88  lea     r10, [r9+8]
0x14000ac8c  cmovnz  ecx, esi
0x14000ac8f  and     eax, 0FFC07FFFh
0x14000ac94  mov     [r10], ecx
0x14000ac97  xor     edx, edx
0x14000ac99  mov     ecx, 400000h
0x14000ac9e  cmp     r11d, 5
0x14000aca2  cmovz   edx, ecx
0x14000aca5  mov     ecx, eax
0x14000aca7  btr     ecx, 16h
0x14000acab  mov     eax, edx
0x14000acad  or      eax, ecx
0x14000acaf  mov     ecx, eax
0x14000acb1  shr     ecx, 0Fh
0x14000acb4  and     ecx, 7Fh
0x14000acb7  lea     edx, [rcx+1]
0x14000acba  cmp     edx, 7Fh
0x14000acbd  ja      short loc_14000ACC9
0x14000acbf  cmp     edx, ecx
0x14000acc1  jb      short loc_14000ACC9
0x14000acc3  lea     r10, [r9+8]
0x14000acc7  jmp     short loc_14000ACD2
0x14000acc9  mov     edx, esi
0x14000accb  mov     [r10], r11d
0x14000acce  mov     [r9+4], ecx
0x14000acd2  shl     edx, 0Fh
0x14000acd5  xor     edx, eax
0x14000acd7  and     edx, 3F8000h
0x14000acdd  xor     edx, eax
0x14000acdf  mov     eax, r8d
0x14000ace2  lock cmpxchg [rdi], edx
0x14000ace6  jz      short loc_14000ACF0
0x14000ace8  mov     r8d, eax
0x14000aceb  jmp     loc_14000AC5A
0x14000acf0  not     r8d
0x14000acf3  mov     dword ptr [r9+10h], 0
0x14000acfb  and     r8d, esi
0x14000acfe  mov     [r9], r8d
0x14000ad01  pop     rdi
0x14000ad02  pop     rsi
0x14000ad03  pop     rbx
0x14000ad04  retn
```
