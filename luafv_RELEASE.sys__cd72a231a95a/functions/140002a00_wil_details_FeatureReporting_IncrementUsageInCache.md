# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140002a00`
- end: `0x140002ad6`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002adc`

## callees

- `0x140002a00`

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
0x140002a00  push    rbx
0x140002a02  push    rsi
0x140002a03  push    rdi
0x140002a04  mov     r8d, [rcx]
0x140002a07  lea     r10, [r9+8]
0x140002a0b  xor     edi, edi
0x140002a0d  mov     ebx, edx
0x140002a0f  cmp     edx, 4
0x140002a12  mov     rsi, rcx
0x140002a15  setz    dil
0x140002a19  mov     eax, r8d
0x140002a1c  mov     dword ptr [r9+4], 0
0x140002a24  or      eax, 1
0x140002a27  mov     ecx, eax
0x140002a29  shr     ecx, 0Eh
0x140002a2c  and     ecx, 1
0x140002a2f  cmp     ecx, edi
0x140002a31  jz      short loc_140002A75
0x140002a33  mov     r11d, eax
0x140002a36  shr     r11d, 5
0x140002a3a  and     r11d, 1FFh
0x140002a41  jbe     short loc_140002A5E
0x140002a43  mov     ecx, ebx
0x140002a45  mov     [r9+4], r11d
0x140002a49  neg     ecx
0x140002a4b  lea     r10, [r9+8]
0x140002a4f  sbb     edx, edx
0x140002a51  not     edx
0x140002a53  and     edx, 4
0x140002a56  mov     [r10], edx
0x140002a59  and     eax, 0FFFFC01Fh
0x140002a5e  xor     edx, edx
0x140002a60  mov     ecx, 4000h
0x140002a65  cmp     ebx, 4
0x140002a68  cmovz   edx, ecx
0x140002a6b  mov     ecx, eax
0x140002a6d  btr     ecx, 0Eh
0x140002a71  mov     eax, edx
0x140002a73  or      eax, ecx
0x140002a75  mov     ecx, eax
0x140002a77  shr     ecx, 5
0x140002a7a  and     ecx, 1FFh
0x140002a80  lea     edx, [rcx+1]
0x140002a83  cmp     edx, 1FFh
0x140002a89  ja      short loc_140002A95
0x140002a8b  cmp     edx, ecx
0x140002a8d  jb      short loc_140002A95
0x140002a8f  lea     r10, [r9+8]
0x140002a93  jmp     short loc_140002AA1
0x140002a95  mov     edx, 1
0x140002a9a  mov     [r10], ebx
0x140002a9d  mov     [r9+4], ecx
0x140002aa1  shl     edx, 5
0x140002aa4  xor     edx, eax
0x140002aa6  and     edx, 3FE0h
0x140002aac  xor     edx, eax
0x140002aae  mov     eax, r8d
0x140002ab1  lock cmpxchg [rsi], edx
0x140002ab5  jz      short loc_140002ABF
0x140002ab7  mov     r8d, eax
0x140002aba  jmp     loc_140002A19
0x140002abf  not     r8d
0x140002ac2  mov     dword ptr [r9+10h], 0
0x140002aca  and     r8d, 1
0x140002ace  mov     [r9], r8d
0x140002ad1  pop     rdi
0x140002ad2  pop     rsi
0x140002ad3  pop     rbx
0x140002ad4  retn
```
