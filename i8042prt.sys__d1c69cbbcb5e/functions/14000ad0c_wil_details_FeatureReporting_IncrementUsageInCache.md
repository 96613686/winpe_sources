# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000ad0c`
- end: `0x14000ade2`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ade8`

## callees

- `0x14000ad0c`

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
0x14000ad0c  push    rbx
0x14000ad0e  push    rsi
0x14000ad0f  push    rdi
0x14000ad10  mov     r8d, [rcx]
0x14000ad13  lea     r10, [r9+8]
0x14000ad17  xor     edi, edi
0x14000ad19  mov     ebx, edx
0x14000ad1b  cmp     edx, 4
0x14000ad1e  mov     rsi, rcx
0x14000ad21  setz    dil
0x14000ad25  mov     eax, r8d
0x14000ad28  mov     dword ptr [r9+4], 0
0x14000ad30  or      eax, 1
0x14000ad33  mov     ecx, eax
0x14000ad35  shr     ecx, 0Eh
0x14000ad38  and     ecx, 1
0x14000ad3b  cmp     ecx, edi
0x14000ad3d  jz      short loc_14000AD81
0x14000ad3f  mov     r11d, eax
0x14000ad42  shr     r11d, 5
0x14000ad46  and     r11d, 1FFh
0x14000ad4d  jbe     short loc_14000AD6A
0x14000ad4f  mov     ecx, ebx
0x14000ad51  mov     [r9+4], r11d
0x14000ad55  neg     ecx
0x14000ad57  lea     r10, [r9+8]
0x14000ad5b  sbb     edx, edx
0x14000ad5d  not     edx
0x14000ad5f  and     edx, 4
0x14000ad62  mov     [r10], edx
0x14000ad65  and     eax, 0FFFFC01Fh
0x14000ad6a  xor     edx, edx
0x14000ad6c  mov     ecx, 4000h
0x14000ad71  cmp     ebx, 4
0x14000ad74  cmovz   edx, ecx
0x14000ad77  mov     ecx, eax
0x14000ad79  btr     ecx, 0Eh
0x14000ad7d  mov     eax, edx
0x14000ad7f  or      eax, ecx
0x14000ad81  mov     ecx, eax
0x14000ad83  shr     ecx, 5
0x14000ad86  and     ecx, 1FFh
0x14000ad8c  lea     edx, [rcx+1]
0x14000ad8f  cmp     edx, 1FFh
0x14000ad95  ja      short loc_14000ADA1
0x14000ad97  cmp     edx, ecx
0x14000ad99  jb      short loc_14000ADA1
0x14000ad9b  lea     r10, [r9+8]
0x14000ad9f  jmp     short loc_14000ADAD
0x14000ada1  mov     edx, 1
0x14000ada6  mov     [r10], ebx
0x14000ada9  mov     [r9+4], ecx
0x14000adad  shl     edx, 5
0x14000adb0  xor     edx, eax
0x14000adb2  and     edx, 3FE0h
0x14000adb8  xor     edx, eax
0x14000adba  mov     eax, r8d
0x14000adbd  lock cmpxchg [rsi], edx
0x14000adc1  jz      short loc_14000ADCB
0x14000adc3  mov     r8d, eax
0x14000adc6  jmp     loc_14000AD25
0x14000adcb  not     r8d
0x14000adce  mov     dword ptr [r9+10h], 0
0x14000add6  and     r8d, 1
0x14000adda  mov     [r9], r8d
0x14000addd  pop     rdi
0x14000adde  pop     rsi
0x14000addf  pop     rbx
0x14000ade0  retn
```
