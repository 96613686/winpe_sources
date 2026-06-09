# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180002ad0`
- end: `0x180002c58`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `392`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800071bc`

## callees

- `0x180002ad0`
- `0x180002c60`
- `0x180006fc0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  int v6; // edx
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  signed __int32 i; // ecx
  signed __int32 v11; // r8d
  signed __int32 v12; // eax
  BOOL v13; // edx
  __int64 result; // rax
  int v15; // edi
  unsigned __int32 v16; // eax
  BOOL v17; // ecx
  unsigned __int32 v18; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( (_DWORD)a3 == 4 )
  {
LABEL_32:
    wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
    return a1;
  }
  else
  {
    switch ( (int)a3 )
    {
      case 0:
        goto LABEL_32;
      case 1:
      case 5:
        wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
        result = a1;
        break;
      case 2:
      case 3:
      case 6:
      case 7:
        v6 = 0;
        v7 = a3 - 2;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 3;
            if ( v9 )
            {
              if ( v9 == 1 )
                v6 = 16;
            }
            else
            {
              v6 = 4;
            }
          }
          else
          {
            v6 = 8;
          }
        }
        else
        {
          v6 = 2;
        }
        for ( i = *a2; ; i = v12 )
        {
          v11 = i | v6 | 1;
          *(_DWORD *)(a1 + 16) = (i | v6) == i;
          if ( (i | v6) == i )
            v11 = i | v6;
          v12 = _InterlockedCompareExchange(a2, v11, i);
          if ( i == v12 )
            break;
        }
        v13 = (v11 & 1) != 0 && (i & 1) == 0;
        *(_DWORD *)a1 = v13;
        result = a1;
        break;
      default:
        v15 = a3 - 320;
        if ( (int)a3 - 320 >= 64 )
          goto LABEL_30;
        v16 = *((_DWORD *)a2 + 1);
        do
        {
          v17 = (v16 & 0x10) != 0 && ((v16 >> 5) & 0x3F) == v15;
          *(_DWORD *)(a1 + 16) = v17;
          v18 = v16;
          v16 = _InterlockedCompareExchange(
                  a2 + 1,
                  v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)(32 * v15)) & 0x7E0 | 0x10,
                  v16);
        }
        while ( v18 != v16 );
        if ( !*(_DWORD *)(a1 + 16) )
        {
LABEL_30:
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = 1;
          *(_DWORD *)(a1 + 12) = a4;
        }
        result = a1;
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002ad0  push    rbx
0x180002ad2  sub     rsp, 20h
0x180002ad6  xor     eax, eax
0x180002ad8  xorps   xmm0, xmm0
0x180002adb  mov     r10, rdx
0x180002ade  mov     rbx, rcx
0x180002ae1  movups  xmmword ptr [rcx], xmm0
0x180002ae4  mov     [rcx+10h], rax
0x180002ae8  cmp     r8d, 4
0x180002aec  jz      loc_180002C1F; jumptable 0000000180002B10 case 0
0x180002af2  cmp     r8d, 7; switch 8 cases
0x180002af6  ja      def_180002B10; jumptable 0000000180002B10 default case, case 4
0x180002afc  lea     rdx, __ImageBase
0x180002b03  movsxd  rax, r8d
0x180002b06  mov     ecx, ds:(jpt_180002B10 - 180000000h)[rdx+rax*4]
0x180002b0d  add     rcx, rdx
0x180002b10  jmp     rcx; switch jump
0x180002b12  xor     edx, edx; jumptable 0000000180002B10 cases 2,3,6,7
0x180002b14  sub     r8d, 2
0x180002b18  jz      short loc_180002B41
0x180002b1a  sub     r8d, 1
0x180002b1e  jz      short loc_180002B3A
0x180002b20  sub     r8d, 3
0x180002b24  jz      short loc_180002B33
0x180002b26  cmp     r8d, 1
0x180002b2a  jnz     short loc_180002B46
0x180002b2c  mov     edx, 10h
0x180002b31  jmp     short loc_180002B46
0x180002b33  mov     edx, 4
0x180002b38  jmp     short loc_180002B46
0x180002b3a  mov     edx, 8
0x180002b3f  jmp     short loc_180002B46
0x180002b41  mov     edx, 2
0x180002b46  mov     ecx, [r10]
0x180002b49  nop     dword ptr [rax+00000000h]
0x180002b50  xor     eax, eax
0x180002b52  mov     r9d, edx
0x180002b55  or      r9d, ecx
0x180002b58  cmp     r9d, ecx
0x180002b5b  mov     r8d, r9d
0x180002b5e  setz    al
0x180002b61  or      r8d, 1
0x180002b65  cmp     r9d, ecx
0x180002b68  mov     [rbx+10h], eax
0x180002b6b  mov     eax, ecx
0x180002b6d  cmovz   r8d, r9d
0x180002b71  lock cmpxchg [r10], r8d
0x180002b76  jz      short loc_180002B7C
0x180002b78  mov     ecx, eax
0x180002b7a  jmp     short loc_180002B50
0x180002b7c  test    r8b, 1
0x180002b80  jz      short loc_180002B8E
0x180002b82  test    cl, 1
0x180002b85  jnz     short loc_180002B8E
0x180002b87  mov     edx, 1
0x180002b8c  jmp     short loc_180002B90
0x180002b8e  xor     edx, edx
0x180002b90  mov     [rbx], edx
0x180002b92  mov     rax, rbx
0x180002b95  add     rsp, 20h
0x180002b99  pop     rbx
0x180002b9a  retn
0x180002b9b  mov     r9, rbx; jumptable 0000000180002B10 cases 1,5
0x180002b9e  mov     edx, r8d
0x180002ba1  mov     rcx, r10
0x180002ba4  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180002ba9  mov     rax, rbx
0x180002bac  jmp     short loc_180002C19
0x180002bae  mov     [rsp+28h+arg_0], rdi; jumptable 0000000180002B10 default case, case 4
0x180002bb3  mov     edx, 1
0x180002bb8  lea     edi, [r8-140h]
0x180002bbf  cmp     edi, 40h ; '@'
0x180002bc2  jge     short loc_180002C06
0x180002bc4  mov     eax, [r10+4]
0x180002bc8  mov     r11d, edi
0x180002bcb  shl     r11d, 5
0x180002bcf  test    al, 10h
0x180002bd1  jz      short loc_180002BE3
0x180002bd3  mov     ecx, eax
0x180002bd5  shr     ecx, 5
0x180002bd8  and     ecx, 3Fh
0x180002bdb  cmp     ecx, edi
0x180002bdd  jnz     short loc_180002BE3
0x180002bdf  mov     ecx, edx
0x180002be1  jmp     short loc_180002BE5
0x180002be3  xor     ecx, ecx
0x180002be5  mov     [rbx+10h], ecx
0x180002be8  mov     ecx, r11d
0x180002beb  xor     ecx, eax
0x180002bed  and     ecx, 7E0h
0x180002bf3  xor     ecx, eax
0x180002bf5  or      ecx, 10h
0x180002bf8  lock cmpxchg [r10+4], ecx
0x180002bfe  jnz     short loc_180002BCF
0x180002c00  cmp     dword ptr [rbx+10h], 0
0x180002c04  jnz     short loc_180002C11
0x180002c06  mov     [rbx+8], r8d
0x180002c0a  mov     [rbx+4], edx
0x180002c0d  mov     [rbx+0Ch], r9d
0x180002c11  mov     rdi, [rsp+28h+arg_0]
0x180002c16  mov     rax, rbx
0x180002c19  add     rsp, 20h
0x180002c1d  pop     rbx
0x180002c1e  retn
0x180002c1f  mov     r9, rbx; jumptable 0000000180002B10 case 0
0x180002c22  mov     edx, r8d
0x180002c25  mov     rcx, r10
0x180002c28  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180002c2d  mov     rax, rbx
0x180002c30  add     rsp, 20h
0x180002c34  pop     rbx
0x180002c35  retn
```
