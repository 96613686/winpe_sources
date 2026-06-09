# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000dec0`
- end: `0x14000df96`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000df9c`

## callees

- `0x14000dec0`

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
0x14000dec0  push    rbx
0x14000dec2  push    rsi
0x14000dec3  push    rdi
0x14000dec4  mov     r8d, [rcx]
0x14000dec7  lea     r10, [r9+8]
0x14000decb  xor     edi, edi
0x14000decd  mov     ebx, edx
0x14000decf  cmp     edx, 4
0x14000ded2  mov     rsi, rcx
0x14000ded5  setz    dil
0x14000ded9  mov     eax, r8d
0x14000dedc  mov     dword ptr [r9+4], 0
0x14000dee4  or      eax, 1
0x14000dee7  mov     ecx, eax
0x14000dee9  shr     ecx, 0Eh
0x14000deec  and     ecx, 1
0x14000deef  cmp     ecx, edi
0x14000def1  jz      short loc_14000DF35
0x14000def3  mov     r11d, eax
0x14000def6  shr     r11d, 5
0x14000defa  and     r11d, 1FFh
0x14000df01  jbe     short loc_14000DF1E
0x14000df03  mov     ecx, ebx
0x14000df05  mov     [r9+4], r11d
0x14000df09  neg     ecx
0x14000df0b  lea     r10, [r9+8]
0x14000df0f  sbb     edx, edx
0x14000df11  not     edx
0x14000df13  and     edx, 4
0x14000df16  mov     [r10], edx
0x14000df19  and     eax, 0FFFFC01Fh
0x14000df1e  xor     edx, edx
0x14000df20  mov     ecx, 4000h
0x14000df25  cmp     ebx, 4
0x14000df28  cmovz   edx, ecx
0x14000df2b  mov     ecx, eax
0x14000df2d  btr     ecx, 0Eh
0x14000df31  mov     eax, edx
0x14000df33  or      eax, ecx
0x14000df35  mov     ecx, eax
0x14000df37  shr     ecx, 5
0x14000df3a  and     ecx, 1FFh
0x14000df40  lea     edx, [rcx+1]
0x14000df43  cmp     edx, 1FFh
0x14000df49  ja      short loc_14000DF55
0x14000df4b  cmp     edx, ecx
0x14000df4d  jb      short loc_14000DF55
0x14000df4f  lea     r10, [r9+8]
0x14000df53  jmp     short loc_14000DF61
0x14000df55  mov     edx, 1
0x14000df5a  mov     [r10], ebx
0x14000df5d  mov     [r9+4], ecx
0x14000df61  shl     edx, 5
0x14000df64  xor     edx, eax
0x14000df66  and     edx, 3FE0h
0x14000df6c  xor     edx, eax
0x14000df6e  mov     eax, r8d
0x14000df71  lock cmpxchg [rsi], edx
0x14000df75  jz      short loc_14000DF7F
0x14000df77  mov     r8d, eax
0x14000df7a  jmp     loc_14000DED9
0x14000df7f  not     r8d
0x14000df82  mov     dword ptr [r9+10h], 0
0x14000df8a  and     r8d, 1
0x14000df8e  mov     [r9], r8d
0x14000df91  pop     rdi
0x14000df92  pop     rsi
0x14000df93  pop     rbx
0x14000df94  retn
```
