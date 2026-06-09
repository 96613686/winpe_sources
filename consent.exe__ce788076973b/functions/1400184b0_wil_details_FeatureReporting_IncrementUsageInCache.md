# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1400184b0`
- end: `0x140018585`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001858c`

## callees

- `0x1400184b0`

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
0x1400184b0  push    rbx
0x1400184b2  push    rsi
0x1400184b3  push    rdi
0x1400184b4  mov     r8d, [rcx]
0x1400184b7  lea     r10, [r9+8]
0x1400184bb  xor     edi, edi
0x1400184bd  mov     ebx, edx
0x1400184bf  cmp     edx, 4
0x1400184c2  mov     rsi, rcx
0x1400184c5  setz    dil
0x1400184c9  mov     eax, r8d
0x1400184cc  mov     dword ptr [r9+4], 0
0x1400184d4  or      eax, 1
0x1400184d7  mov     ecx, eax
0x1400184d9  shr     ecx, 0Eh
0x1400184dc  and     ecx, 1
0x1400184df  cmp     ecx, edi
0x1400184e1  jz      short loc_140018525
0x1400184e3  mov     r11d, eax
0x1400184e6  shr     r11d, 5
0x1400184ea  and     r11d, 1FFh
0x1400184f1  jbe     short loc_14001850E
0x1400184f3  mov     ecx, ebx
0x1400184f5  mov     [r9+4], r11d
0x1400184f9  neg     ecx
0x1400184fb  lea     r10, [r9+8]
0x1400184ff  sbb     edx, edx
0x140018501  not     edx
0x140018503  and     edx, 4
0x140018506  mov     [r10], edx
0x140018509  and     eax, 0FFFFC01Fh
0x14001850e  xor     edx, edx
0x140018510  mov     ecx, 4000h
0x140018515  cmp     ebx, 4
0x140018518  cmovz   edx, ecx
0x14001851b  mov     ecx, eax
0x14001851d  btr     ecx, 0Eh
0x140018521  mov     eax, edx
0x140018523  or      eax, ecx
0x140018525  mov     ecx, eax
0x140018527  shr     ecx, 5
0x14001852a  and     ecx, 1FFh
0x140018530  lea     edx, [rcx+1]
0x140018533  cmp     edx, 1FFh
0x140018539  ja      short loc_140018545
0x14001853b  cmp     edx, ecx
0x14001853d  jb      short loc_140018545
0x14001853f  lea     r10, [r9+8]
0x140018543  jmp     short loc_140018551
0x140018545  mov     edx, 1
0x14001854a  mov     [r10], ebx
0x14001854d  mov     [r9+4], ecx
0x140018551  shl     edx, 5
0x140018554  xor     edx, eax
0x140018556  and     edx, 3FE0h
0x14001855c  xor     edx, eax
0x14001855e  mov     eax, r8d
0x140018561  lock cmpxchg [rsi], edx
0x140018565  jz      short loc_14001856F
0x140018567  mov     r8d, eax
0x14001856a  jmp     loc_1400184C9
0x14001856f  not     r8d
0x140018572  mov     dword ptr [r9+10h], 0
0x14001857a  and     r8d, 1
0x14001857e  mov     [r9], r8d
0x140018581  pop     rdi
0x140018582  pop     rsi
0x140018583  pop     rbx
0x140018584  retn
```
