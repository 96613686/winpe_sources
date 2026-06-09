# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18001db80`
- end: `0x18001dc56`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001dc5c`

## callees

- `0x18001db80`

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
0x18001db80  push    rbx
0x18001db82  push    rsi
0x18001db83  push    rdi
0x18001db84  mov     r8d, [rcx]
0x18001db87  lea     r10, [r9+8]
0x18001db8b  xor     edi, edi
0x18001db8d  mov     ebx, edx
0x18001db8f  cmp     edx, 4
0x18001db92  mov     rsi, rcx
0x18001db95  setz    dil
0x18001db99  mov     eax, r8d
0x18001db9c  mov     dword ptr [r9+4], 0
0x18001dba4  or      eax, 1
0x18001dba7  mov     ecx, eax
0x18001dba9  shr     ecx, 0Eh
0x18001dbac  and     ecx, 1
0x18001dbaf  cmp     ecx, edi
0x18001dbb1  jz      short loc_18001DBF5
0x18001dbb3  mov     r11d, eax
0x18001dbb6  shr     r11d, 5
0x18001dbba  and     r11d, 1FFh
0x18001dbc1  jbe     short loc_18001DBDE
0x18001dbc3  mov     ecx, ebx
0x18001dbc5  mov     [r9+4], r11d
0x18001dbc9  neg     ecx
0x18001dbcb  lea     r10, [r9+8]
0x18001dbcf  sbb     edx, edx
0x18001dbd1  not     edx
0x18001dbd3  and     edx, 4
0x18001dbd6  mov     [r10], edx
0x18001dbd9  and     eax, 0FFFFC01Fh
0x18001dbde  xor     edx, edx
0x18001dbe0  mov     ecx, 4000h
0x18001dbe5  cmp     ebx, 4
0x18001dbe8  cmovz   edx, ecx
0x18001dbeb  mov     ecx, eax
0x18001dbed  btr     ecx, 0Eh
0x18001dbf1  mov     eax, edx
0x18001dbf3  or      eax, ecx
0x18001dbf5  mov     ecx, eax
0x18001dbf7  shr     ecx, 5
0x18001dbfa  and     ecx, 1FFh
0x18001dc00  lea     edx, [rcx+1]
0x18001dc03  cmp     edx, 1FFh
0x18001dc09  ja      short loc_18001DC15
0x18001dc0b  cmp     edx, ecx
0x18001dc0d  jb      short loc_18001DC15
0x18001dc0f  lea     r10, [r9+8]
0x18001dc13  jmp     short loc_18001DC21
0x18001dc15  mov     edx, 1
0x18001dc1a  mov     [r10], ebx
0x18001dc1d  mov     [r9+4], ecx
0x18001dc21  shl     edx, 5
0x18001dc24  xor     edx, eax
0x18001dc26  and     edx, 3FE0h
0x18001dc2c  xor     edx, eax
0x18001dc2e  mov     eax, r8d
0x18001dc31  lock cmpxchg [rsi], edx
0x18001dc35  jz      short loc_18001DC3F
0x18001dc37  mov     r8d, eax
0x18001dc3a  jmp     loc_18001DB99
0x18001dc3f  not     r8d
0x18001dc42  mov     dword ptr [r9+10h], 0
0x18001dc4a  and     r8d, 1
0x18001dc4e  mov     [r9], r8d
0x18001dc51  pop     rdi
0x18001dc52  pop     rsi
0x18001dc53  pop     rbx
0x18001dc54  retn
```
