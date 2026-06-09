# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x180002c60`
- end: `0x180002d38`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `216`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180002c60`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // rbx
  BOOL v8; // r10d
  unsigned int v9; // eax
  int v10; // edx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
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
        v10 = 4;
        if ( a2 )
          v10 = 0;
        v9 = v4 & 0xFFFFC01E | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 4 )
        v11 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v11;
    }
    v12 = (v9 >> 5) & 0x1FF;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x1FF || v13 < v12 )
    {
      LOWORD(v13) = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v13)) & 0x3FE0,
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
0x180002c60  push    rbx
0x180002c62  push    rbp
0x180002c63  push    rdi
0x180002c64  push    r14
0x180002c66  mov     r8d, [rcx]
0x180002c69  lea     rbx, [r9+8]
0x180002c6d  xor     ebp, ebp
0x180002c6f  mov     [rsp+20h+arg_0], rsi
0x180002c74  cmp     edx, 4
0x180002c77  mov     r10d, ebp
0x180002c7a  mov     edi, edx
0x180002c7c  mov     r11, rcx
0x180002c7f  setz    r10b
0x180002c83  mov     r14d, 4000h
0x180002c89  mov     eax, r8d
0x180002c8c  mov     [r9+4], ebp
0x180002c90  or      eax, 1
0x180002c93  mov     ecx, eax
0x180002c95  shr     ecx, 0Eh
0x180002c98  and     ecx, 1
0x180002c9b  cmp     ecx, r10d
0x180002c9e  jz      short loc_180002CD5
0x180002ca0  mov     esi, eax
0x180002ca2  shr     esi, 5
0x180002ca5  and     esi, 1FFh
0x180002cab  jbe     short loc_180002CC2
0x180002cad  test    edi, edi
0x180002caf  mov     [r9+4], esi
0x180002cb3  mov     edx, 4
0x180002cb8  cmovnz  edx, ebp
0x180002cbb  and     eax, 0FFFFC01Fh
0x180002cc0  mov     [rbx], edx
0x180002cc2  mov     ecx, eax
0x180002cc4  cmp     edi, 4
0x180002cc7  mov     edx, ebp
0x180002cc9  cmovz   edx, r14d
0x180002ccd  btr     ecx, 0Eh
0x180002cd1  mov     eax, edx
0x180002cd3  or      eax, ecx
0x180002cd5  mov     ecx, eax
0x180002cd7  shr     ecx, 5
0x180002cda  and     ecx, 1FFh
0x180002ce0  lea     edx, [rcx+1]
0x180002ce3  cmp     edx, 1FFh
0x180002ce9  ja      short loc_180002CF5
0x180002ceb  cmp     edx, ecx
0x180002ced  jb      short loc_180002CF5
0x180002cef  lea     rbx, [r9+8]
0x180002cf3  jmp     short loc_180002D00
0x180002cf5  mov     edx, 1
0x180002cfa  mov     [rbx], edi
0x180002cfc  mov     [r9+4], ecx
0x180002d00  shl     edx, 5
0x180002d03  xor     edx, eax
0x180002d05  and     edx, 3FE0h
0x180002d0b  xor     edx, eax
0x180002d0d  mov     eax, r8d
0x180002d10  lock cmpxchg [r11], edx
0x180002d15  jz      short loc_180002D1F
0x180002d17  mov     r8d, eax
0x180002d1a  jmp     loc_180002C89
0x180002d1f  mov     rsi, [rsp+20h+arg_0]
0x180002d24  not     r8d
0x180002d27  and     r8d, 1
0x180002d2b  mov     [r9+10h], ebp
0x180002d2f  mov     [r9], r8d
0x180002d32  pop     r14
0x180002d34  pop     rdi
0x180002d35  pop     rbp
0x180002d36  pop     rbx
0x180002d37  retn
```
