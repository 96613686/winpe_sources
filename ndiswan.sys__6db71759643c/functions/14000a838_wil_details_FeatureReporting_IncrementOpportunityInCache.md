# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000a838`
- end: `0x14000a902`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a9e4`

## callees

- `0x14000a838`

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
0x14000a838  push    rbx
0x14000a83a  push    rsi
0x14000a83b  push    rdi
0x14000a83c  mov     r8d, [rcx]
0x14000a83f  lea     r10, [r9+8]
0x14000a843  xor     ebx, ebx
0x14000a845  mov     r11d, edx
0x14000a848  cmp     edx, 5
0x14000a84b  mov     rdi, rcx
0x14000a84e  mov     esi, 1
0x14000a853  setz    bl
0x14000a856  mov     eax, r8d
0x14000a859  mov     dword ptr [r9+4], 0
0x14000a861  or      eax, esi
0x14000a863  mov     ecx, eax
0x14000a865  shr     ecx, 16h
0x14000a868  and     ecx, esi
0x14000a86a  cmp     ecx, ebx
0x14000a86c  jz      short loc_14000A8AB
0x14000a86e  mov     edx, eax
0x14000a870  shr     edx, 0Fh
0x14000a873  and     edx, 7Fh
0x14000a876  jbe     short loc_14000A893
0x14000a878  cmp     r11d, esi
0x14000a87b  mov     [r9+4], edx
0x14000a87f  mov     ecx, 5
0x14000a884  lea     r10, [r9+8]
0x14000a888  cmovnz  ecx, esi
0x14000a88b  and     eax, 0FFC07FFFh
0x14000a890  mov     [r10], ecx
0x14000a893  xor     edx, edx
0x14000a895  mov     ecx, 400000h
0x14000a89a  cmp     r11d, 5
0x14000a89e  cmovz   edx, ecx
0x14000a8a1  mov     ecx, eax
0x14000a8a3  btr     ecx, 16h
0x14000a8a7  mov     eax, edx
0x14000a8a9  or      eax, ecx
0x14000a8ab  mov     ecx, eax
0x14000a8ad  shr     ecx, 0Fh
0x14000a8b0  and     ecx, 7Fh
0x14000a8b3  lea     edx, [rcx+1]
0x14000a8b6  cmp     edx, 7Fh
0x14000a8b9  ja      short loc_14000A8C5
0x14000a8bb  cmp     edx, ecx
0x14000a8bd  jb      short loc_14000A8C5
0x14000a8bf  lea     r10, [r9+8]
0x14000a8c3  jmp     short loc_14000A8CE
0x14000a8c5  mov     edx, esi
0x14000a8c7  mov     [r10], r11d
0x14000a8ca  mov     [r9+4], ecx
0x14000a8ce  shl     edx, 0Fh
0x14000a8d1  xor     edx, eax
0x14000a8d3  and     edx, 3F8000h
0x14000a8d9  xor     edx, eax
0x14000a8db  mov     eax, r8d
0x14000a8de  lock cmpxchg [rdi], edx
0x14000a8e2  jz      short loc_14000A8EC
0x14000a8e4  mov     r8d, eax
0x14000a8e7  jmp     loc_14000A856
0x14000a8ec  not     r8d
0x14000a8ef  mov     dword ptr [r9+10h], 0
0x14000a8f7  and     r8d, esi
0x14000a8fa  mov     [r9], r8d
0x14000a8fd  pop     rdi
0x14000a8fe  pop     rsi
0x14000a8ff  pop     rbx
0x14000a900  retn
```
