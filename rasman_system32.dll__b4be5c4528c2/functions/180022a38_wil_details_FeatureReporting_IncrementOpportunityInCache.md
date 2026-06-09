# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180022a38`
- end: `0x180022b02`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022be4`

## callees

- `0x180022a38`

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
0x180022a38  push    rbx
0x180022a3a  push    rsi
0x180022a3b  push    rdi
0x180022a3c  mov     r8d, [rcx]
0x180022a3f  lea     r10, [r9+8]
0x180022a43  xor     ebx, ebx
0x180022a45  mov     r11d, edx
0x180022a48  cmp     edx, 5
0x180022a4b  mov     rdi, rcx
0x180022a4e  mov     esi, 1
0x180022a53  setz    bl
0x180022a56  mov     eax, r8d
0x180022a59  mov     dword ptr [r9+4], 0
0x180022a61  or      eax, esi
0x180022a63  mov     ecx, eax
0x180022a65  shr     ecx, 16h
0x180022a68  and     ecx, esi
0x180022a6a  cmp     ecx, ebx
0x180022a6c  jz      short loc_180022AAB
0x180022a6e  mov     edx, eax
0x180022a70  shr     edx, 0Fh
0x180022a73  and     edx, 7Fh
0x180022a76  jbe     short loc_180022A93
0x180022a78  cmp     r11d, esi
0x180022a7b  mov     [r9+4], edx
0x180022a7f  mov     ecx, 5
0x180022a84  lea     r10, [r9+8]
0x180022a88  cmovnz  ecx, esi
0x180022a8b  and     eax, 0FFC07FFFh
0x180022a90  mov     [r10], ecx
0x180022a93  xor     edx, edx
0x180022a95  mov     ecx, 400000h
0x180022a9a  cmp     r11d, 5
0x180022a9e  cmovz   edx, ecx
0x180022aa1  mov     ecx, eax
0x180022aa3  btr     ecx, 16h
0x180022aa7  mov     eax, edx
0x180022aa9  or      eax, ecx
0x180022aab  mov     ecx, eax
0x180022aad  shr     ecx, 0Fh
0x180022ab0  and     ecx, 7Fh
0x180022ab3  lea     edx, [rcx+1]
0x180022ab6  cmp     edx, 7Fh
0x180022ab9  ja      short loc_180022AC5
0x180022abb  cmp     edx, ecx
0x180022abd  jb      short loc_180022AC5
0x180022abf  lea     r10, [r9+8]
0x180022ac3  jmp     short loc_180022ACE
0x180022ac5  mov     edx, esi
0x180022ac7  mov     [r10], r11d
0x180022aca  mov     [r9+4], ecx
0x180022ace  shl     edx, 0Fh
0x180022ad1  xor     edx, eax
0x180022ad3  and     edx, 3F8000h
0x180022ad9  xor     edx, eax
0x180022adb  mov     eax, r8d
0x180022ade  lock cmpxchg [rdi], edx
0x180022ae2  jz      short loc_180022AEC
0x180022ae4  mov     r8d, eax
0x180022ae7  jmp     loc_180022A56
0x180022aec  not     r8d
0x180022aef  mov     dword ptr [r9+10h], 0
0x180022af7  and     r8d, esi
0x180022afa  mov     [r9], r8d
0x180022afd  pop     rdi
0x180022afe  pop     rsi
0x180022aff  pop     rbx
0x180022b00  retn
```
