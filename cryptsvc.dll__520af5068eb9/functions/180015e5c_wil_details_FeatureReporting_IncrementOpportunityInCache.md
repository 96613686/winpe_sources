# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180015e5c`
- end: `0x180015f25`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016008`

## callees

- `0x180015e5c`

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
0x180015e5c  push    rbx
0x180015e5e  push    rsi
0x180015e5f  push    rdi
0x180015e60  mov     r8d, [rcx]
0x180015e63  lea     r10, [r9+8]
0x180015e67  xor     ebx, ebx
0x180015e69  mov     r11d, edx
0x180015e6c  cmp     edx, 5
0x180015e6f  mov     rdi, rcx
0x180015e72  mov     esi, 1
0x180015e77  setz    bl
0x180015e7a  mov     eax, r8d
0x180015e7d  mov     dword ptr [r9+4], 0
0x180015e85  or      eax, esi
0x180015e87  mov     ecx, eax
0x180015e89  shr     ecx, 16h
0x180015e8c  and     ecx, esi
0x180015e8e  cmp     ecx, ebx
0x180015e90  jz      short loc_180015ECF
0x180015e92  mov     edx, eax
0x180015e94  shr     edx, 0Fh
0x180015e97  and     edx, 7Fh
0x180015e9a  jbe     short loc_180015EB7
0x180015e9c  cmp     r11d, esi
0x180015e9f  mov     [r9+4], edx
0x180015ea3  mov     ecx, 5
0x180015ea8  lea     r10, [r9+8]
0x180015eac  cmovnz  ecx, esi
0x180015eaf  and     eax, 0FFC07FFFh
0x180015eb4  mov     [r10], ecx
0x180015eb7  xor     edx, edx
0x180015eb9  mov     ecx, 400000h
0x180015ebe  cmp     r11d, 5
0x180015ec2  cmovz   edx, ecx
0x180015ec5  mov     ecx, eax
0x180015ec7  btr     ecx, 16h
0x180015ecb  mov     eax, edx
0x180015ecd  or      eax, ecx
0x180015ecf  mov     ecx, eax
0x180015ed1  shr     ecx, 0Fh
0x180015ed4  and     ecx, 7Fh
0x180015ed7  lea     edx, [rcx+1]
0x180015eda  cmp     edx, 7Fh
0x180015edd  ja      short loc_180015EE9
0x180015edf  cmp     edx, ecx
0x180015ee1  jb      short loc_180015EE9
0x180015ee3  lea     r10, [r9+8]
0x180015ee7  jmp     short loc_180015EF2
0x180015ee9  mov     edx, esi
0x180015eeb  mov     [r10], r11d
0x180015eee  mov     [r9+4], ecx
0x180015ef2  shl     edx, 0Fh
0x180015ef5  xor     edx, eax
0x180015ef7  and     edx, 3F8000h
0x180015efd  xor     edx, eax
0x180015eff  mov     eax, r8d
0x180015f02  lock cmpxchg [rdi], edx
0x180015f06  jz      short loc_180015F10
0x180015f08  mov     r8d, eax
0x180015f0b  jmp     loc_180015E7A
0x180015f10  not     r8d
0x180015f13  mov     dword ptr [r9+10h], 0
0x180015f1b  and     r8d, esi
0x180015f1e  mov     [r9], r8d
0x180015f21  pop     rdi
0x180015f22  pop     rsi
0x180015f23  pop     rbx
0x180015f24  retn
```
