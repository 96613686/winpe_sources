# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18001330c`
- end: `0x1800133e1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800133e8`

## callees

- `0x18001330c`

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
0x18001330c  push    rbx
0x18001330e  push    rsi
0x18001330f  push    rdi
0x180013310  mov     r8d, [rcx]
0x180013313  lea     r10, [r9+8]
0x180013317  xor     edi, edi
0x180013319  mov     ebx, edx
0x18001331b  cmp     edx, 4
0x18001331e  mov     rsi, rcx
0x180013321  setz    dil
0x180013325  mov     eax, r8d
0x180013328  mov     dword ptr [r9+4], 0
0x180013330  or      eax, 1
0x180013333  mov     ecx, eax
0x180013335  shr     ecx, 0Eh
0x180013338  and     ecx, 1
0x18001333b  cmp     ecx, edi
0x18001333d  jz      short loc_180013381
0x18001333f  mov     r11d, eax
0x180013342  shr     r11d, 5
0x180013346  and     r11d, 1FFh
0x18001334d  jbe     short loc_18001336A
0x18001334f  mov     ecx, ebx
0x180013351  mov     [r9+4], r11d
0x180013355  neg     ecx
0x180013357  lea     r10, [r9+8]
0x18001335b  sbb     edx, edx
0x18001335d  not     edx
0x18001335f  and     edx, 4
0x180013362  mov     [r10], edx
0x180013365  and     eax, 0FFFFC01Fh
0x18001336a  xor     edx, edx
0x18001336c  mov     ecx, 4000h
0x180013371  cmp     ebx, 4
0x180013374  cmovz   edx, ecx
0x180013377  mov     ecx, eax
0x180013379  btr     ecx, 0Eh
0x18001337d  mov     eax, edx
0x18001337f  or      eax, ecx
0x180013381  mov     ecx, eax
0x180013383  shr     ecx, 5
0x180013386  and     ecx, 1FFh
0x18001338c  lea     edx, [rcx+1]
0x18001338f  cmp     edx, 1FFh
0x180013395  ja      short loc_1800133A1
0x180013397  cmp     edx, ecx
0x180013399  jb      short loc_1800133A1
0x18001339b  lea     r10, [r9+8]
0x18001339f  jmp     short loc_1800133AD
0x1800133a1  mov     edx, 1
0x1800133a6  mov     [r10], ebx
0x1800133a9  mov     [r9+4], ecx
0x1800133ad  shl     edx, 5
0x1800133b0  xor     edx, eax
0x1800133b2  and     edx, 3FE0h
0x1800133b8  xor     edx, eax
0x1800133ba  mov     eax, r8d
0x1800133bd  lock cmpxchg [rsi], edx
0x1800133c1  jz      short loc_1800133CB
0x1800133c3  mov     r8d, eax
0x1800133c6  jmp     loc_180013325
0x1800133cb  not     r8d
0x1800133ce  mov     dword ptr [r9+10h], 0
0x1800133d6  and     r8d, 1
0x1800133da  mov     [r9], r8d
0x1800133dd  pop     rdi
0x1800133de  pop     rsi
0x1800133df  pop     rbx
0x1800133e0  retn
```
