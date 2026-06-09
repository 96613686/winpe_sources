# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000d75c`
- end: `0x18000d825`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d908`

## callees

- `0x18000d75c`

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
0x18000d75c  push    rbx
0x18000d75e  push    rsi
0x18000d75f  push    rdi
0x18000d760  mov     r8d, [rcx]
0x18000d763  lea     r10, [r9+8]
0x18000d767  xor     ebx, ebx
0x18000d769  mov     r11d, edx
0x18000d76c  cmp     edx, 5
0x18000d76f  mov     rdi, rcx
0x18000d772  mov     esi, 1
0x18000d777  setz    bl
0x18000d77a  mov     eax, r8d
0x18000d77d  mov     dword ptr [r9+4], 0
0x18000d785  or      eax, esi
0x18000d787  mov     ecx, eax
0x18000d789  shr     ecx, 16h
0x18000d78c  and     ecx, esi
0x18000d78e  cmp     ecx, ebx
0x18000d790  jz      short loc_18000D7CF
0x18000d792  mov     edx, eax
0x18000d794  shr     edx, 0Fh
0x18000d797  and     edx, 7Fh
0x18000d79a  jbe     short loc_18000D7B7
0x18000d79c  cmp     r11d, esi
0x18000d79f  mov     [r9+4], edx
0x18000d7a3  mov     ecx, 5
0x18000d7a8  lea     r10, [r9+8]
0x18000d7ac  cmovnz  ecx, esi
0x18000d7af  and     eax, 0FFC07FFFh
0x18000d7b4  mov     [r10], ecx
0x18000d7b7  xor     edx, edx
0x18000d7b9  mov     ecx, 400000h
0x18000d7be  cmp     r11d, 5
0x18000d7c2  cmovz   edx, ecx
0x18000d7c5  mov     ecx, eax
0x18000d7c7  btr     ecx, 16h
0x18000d7cb  mov     eax, edx
0x18000d7cd  or      eax, ecx
0x18000d7cf  mov     ecx, eax
0x18000d7d1  shr     ecx, 0Fh
0x18000d7d4  and     ecx, 7Fh
0x18000d7d7  lea     edx, [rcx+1]
0x18000d7da  cmp     edx, 7Fh
0x18000d7dd  ja      short loc_18000D7E9
0x18000d7df  cmp     edx, ecx
0x18000d7e1  jb      short loc_18000D7E9
0x18000d7e3  lea     r10, [r9+8]
0x18000d7e7  jmp     short loc_18000D7F2
0x18000d7e9  mov     edx, esi
0x18000d7eb  mov     [r10], r11d
0x18000d7ee  mov     [r9+4], ecx
0x18000d7f2  shl     edx, 0Fh
0x18000d7f5  xor     edx, eax
0x18000d7f7  and     edx, 3F8000h
0x18000d7fd  xor     edx, eax
0x18000d7ff  mov     eax, r8d
0x18000d802  lock cmpxchg [rdi], edx
0x18000d806  jz      short loc_18000D810
0x18000d808  mov     r8d, eax
0x18000d80b  jmp     loc_18000D77A
0x18000d810  not     r8d
0x18000d813  mov     dword ptr [r9+10h], 0
0x18000d81b  and     r8d, esi
0x18000d81e  mov     [r9], r8d
0x18000d821  pop     rdi
0x18000d822  pop     rsi
0x18000d823  pop     rbx
0x18000d824  retn
```
