# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800107b0`
- end: `0x180010885`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003964`

## callees

- `0x1800107b0`

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
0x1800107b0  push    rbx
0x1800107b2  push    rsi
0x1800107b3  push    rdi
0x1800107b4  mov     r8d, [rcx]
0x1800107b7  lea     r10, [r9+8]
0x1800107bb  xor     edi, edi
0x1800107bd  mov     ebx, edx
0x1800107bf  cmp     edx, 4
0x1800107c2  mov     rsi, rcx
0x1800107c5  setz    dil
0x1800107c9  mov     eax, r8d
0x1800107cc  mov     dword ptr [r9+4], 0
0x1800107d4  or      eax, 1
0x1800107d7  mov     ecx, eax
0x1800107d9  shr     ecx, 0Eh
0x1800107dc  and     ecx, 1
0x1800107df  cmp     ecx, edi
0x1800107e1  jz      short loc_180010825
0x1800107e3  mov     r11d, eax
0x1800107e6  shr     r11d, 5
0x1800107ea  and     r11d, 1FFh
0x1800107f1  jbe     short loc_18001080E
0x1800107f3  mov     ecx, ebx
0x1800107f5  mov     [r9+4], r11d
0x1800107f9  neg     ecx
0x1800107fb  lea     r10, [r9+8]
0x1800107ff  sbb     edx, edx
0x180010801  not     edx
0x180010803  and     edx, 4
0x180010806  mov     [r10], edx
0x180010809  and     eax, 0FFFFC01Fh
0x18001080e  xor     edx, edx
0x180010810  mov     ecx, 4000h
0x180010815  cmp     ebx, 4
0x180010818  cmovz   edx, ecx
0x18001081b  mov     ecx, eax
0x18001081d  btr     ecx, 0Eh
0x180010821  mov     eax, edx
0x180010823  or      eax, ecx
0x180010825  mov     ecx, eax
0x180010827  shr     ecx, 5
0x18001082a  and     ecx, 1FFh
0x180010830  lea     edx, [rcx+1]
0x180010833  cmp     edx, 1FFh
0x180010839  ja      short loc_180010845
0x18001083b  cmp     edx, ecx
0x18001083d  jb      short loc_180010845
0x18001083f  lea     r10, [r9+8]
0x180010843  jmp     short loc_180010851
0x180010845  mov     edx, 1
0x18001084a  mov     [r10], ebx
0x18001084d  mov     [r9+4], ecx
0x180010851  shl     edx, 5
0x180010854  xor     edx, eax
0x180010856  and     edx, 3FE0h
0x18001085c  xor     edx, eax
0x18001085e  mov     eax, r8d
0x180010861  lock cmpxchg [rsi], edx
0x180010865  jz      short loc_18001086F
0x180010867  mov     r8d, eax
0x18001086a  jmp     loc_1800107C9
0x18001086f  not     r8d
0x180010872  mov     dword ptr [r9+10h], 0
0x18001087a  and     r8d, 1
0x18001087e  mov     [r9], r8d
0x180010881  pop     rdi
0x180010882  pop     rsi
0x180010883  pop     rbx
0x180010884  retn
```
