# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000afdc`
- end: `0x14000b0b1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b0b8`

## callees

- `0x14000afdc`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
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
0x14000afdc  push    rbx
0x14000afde  push    rsi
0x14000afdf  push    rdi
0x14000afe0  mov     r8d, [rcx]
0x14000afe3  lea     r10, [r9+8]
0x14000afe7  xor     edi, edi
0x14000afe9  mov     ebx, edx
0x14000afeb  cmp     edx, 4
0x14000afee  mov     rsi, rcx
0x14000aff1  setz    dil
0x14000aff5  mov     eax, r8d
0x14000aff8  mov     dword ptr [r9+4], 0
0x14000b000  or      eax, 1
0x14000b003  mov     ecx, eax
0x14000b005  shr     ecx, 0Eh
0x14000b008  and     ecx, 1
0x14000b00b  cmp     ecx, edi
0x14000b00d  jz      short loc_14000B051
0x14000b00f  mov     r11d, eax
0x14000b012  shr     r11d, 5
0x14000b016  and     r11d, 1FFh
0x14000b01d  jbe     short loc_14000B03A
0x14000b01f  mov     ecx, ebx
0x14000b021  mov     [r9+4], r11d
0x14000b025  neg     ecx
0x14000b027  lea     r10, [r9+8]
0x14000b02b  sbb     edx, edx
0x14000b02d  not     edx
0x14000b02f  and     edx, 4
0x14000b032  mov     [r10], edx
0x14000b035  and     eax, 0FFFFC01Fh
0x14000b03a  xor     edx, edx
0x14000b03c  mov     ecx, 4000h
0x14000b041  cmp     ebx, 4
0x14000b044  cmovz   edx, ecx
0x14000b047  mov     ecx, eax
0x14000b049  btr     ecx, 0Eh
0x14000b04d  mov     eax, edx
0x14000b04f  or      eax, ecx
0x14000b051  mov     ecx, eax
0x14000b053  shr     ecx, 5
0x14000b056  and     ecx, 1FFh
0x14000b05c  lea     edx, [rcx+1]
0x14000b05f  cmp     edx, 1FFh
0x14000b065  ja      short loc_14000B071
0x14000b067  cmp     edx, ecx
0x14000b069  jb      short loc_14000B071
0x14000b06b  lea     r10, [r9+8]
0x14000b06f  jmp     short loc_14000B07D
0x14000b071  mov     edx, 1
0x14000b076  mov     [r10], ebx
0x14000b079  mov     [r9+4], ecx
0x14000b07d  shl     edx, 5
0x14000b080  xor     edx, eax
0x14000b082  and     edx, 3FE0h
0x14000b088  xor     edx, eax
0x14000b08a  mov     eax, r8d
0x14000b08d  lock cmpxchg [rsi], edx
0x14000b091  jz      short loc_14000B09B
0x14000b093  mov     r8d, eax
0x14000b096  jmp     loc_14000AFF5
0x14000b09b  not     r8d
0x14000b09e  mov     dword ptr [r9+10h], 0
0x14000b0a6  and     r8d, 1
0x14000b0aa  mov     [r9], r8d
0x14000b0ad  pop     rdi
0x14000b0ae  pop     rsi
0x14000b0af  pop     rbx
0x14000b0b0  retn
```
