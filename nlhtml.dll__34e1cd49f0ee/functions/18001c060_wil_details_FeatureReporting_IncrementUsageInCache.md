# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18001c060`
- end: `0x18001c135`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c13c`

## callees

- `0x18001c060`

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
0x18001c060  push    rbx
0x18001c062  push    rsi
0x18001c063  push    rdi
0x18001c064  mov     r8d, [rcx]
0x18001c067  lea     r10, [r9+8]
0x18001c06b  xor     edi, edi
0x18001c06d  mov     ebx, edx
0x18001c06f  cmp     edx, 4
0x18001c072  mov     rsi, rcx
0x18001c075  setz    dil
0x18001c079  mov     eax, r8d
0x18001c07c  mov     dword ptr [r9+4], 0
0x18001c084  or      eax, 1
0x18001c087  mov     ecx, eax
0x18001c089  shr     ecx, 0Eh
0x18001c08c  and     ecx, 1
0x18001c08f  cmp     ecx, edi
0x18001c091  jz      short loc_18001C0D5
0x18001c093  mov     r11d, eax
0x18001c096  shr     r11d, 5
0x18001c09a  and     r11d, 1FFh
0x18001c0a1  jbe     short loc_18001C0BE
0x18001c0a3  mov     ecx, ebx
0x18001c0a5  mov     [r9+4], r11d
0x18001c0a9  neg     ecx
0x18001c0ab  lea     r10, [r9+8]
0x18001c0af  sbb     edx, edx
0x18001c0b1  not     edx
0x18001c0b3  and     edx, 4
0x18001c0b6  mov     [r10], edx
0x18001c0b9  and     eax, 0FFFFC01Fh
0x18001c0be  xor     edx, edx
0x18001c0c0  mov     ecx, 4000h
0x18001c0c5  cmp     ebx, 4
0x18001c0c8  cmovz   edx, ecx
0x18001c0cb  mov     ecx, eax
0x18001c0cd  btr     ecx, 0Eh
0x18001c0d1  mov     eax, edx
0x18001c0d3  or      eax, ecx
0x18001c0d5  mov     ecx, eax
0x18001c0d7  shr     ecx, 5
0x18001c0da  and     ecx, 1FFh
0x18001c0e0  lea     edx, [rcx+1]
0x18001c0e3  cmp     edx, 1FFh
0x18001c0e9  ja      short loc_18001C0F5
0x18001c0eb  cmp     edx, ecx
0x18001c0ed  jb      short loc_18001C0F5
0x18001c0ef  lea     r10, [r9+8]
0x18001c0f3  jmp     short loc_18001C101
0x18001c0f5  mov     edx, 1
0x18001c0fa  mov     [r10], ebx
0x18001c0fd  mov     [r9+4], ecx
0x18001c101  shl     edx, 5
0x18001c104  xor     edx, eax
0x18001c106  and     edx, 3FE0h
0x18001c10c  xor     edx, eax
0x18001c10e  mov     eax, r8d
0x18001c111  lock cmpxchg [rsi], edx
0x18001c115  jz      short loc_18001C11F
0x18001c117  mov     r8d, eax
0x18001c11a  jmp     loc_18001C079
0x18001c11f  not     r8d
0x18001c122  mov     dword ptr [r9+10h], 0
0x18001c12a  and     r8d, 1
0x18001c12e  mov     [r9], r8d
0x18001c131  pop     rdi
0x18001c132  pop     rsi
0x18001c133  pop     rbx
0x18001c134  retn
```
