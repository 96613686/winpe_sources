# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000e81c`
- end: `0x14000e929`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e7e0`

## callees

- `0x14000e7e0`
- `0x14000e81c`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  int v4; // esi
  signed __int32 v5; // ebx
  BOOL v6; // edi
  BOOL v7; // ebp
  _QWORD *v8; // r14
  __int64 v9; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v11; // edx
  unsigned int v12; // ecx
  signed __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  HIDWORD(v15) = 0;
  v4 = (a2 >> 6) & 1;
  v5 = a2;
  v6 = 1;
  if ( (a2 & 0xC00) == 0xC00 || v4 )
  {
    v8 = *(_QWORD **)(a3 + 32);
    v7 = (a2 & 0xC00) == 3072;
    if ( v8 )
    {
      while ( 1 )
      {
        v9 = *v8;
        if ( !*v8 )
          break;
        if ( *(_BYTE *)(v9 + 30) || *(_BYTE *)(v9 + 29) )
        {
          if ( !*(_BYTE *)(v9 + 31) )
          {
            v6 = 0;
            break;
          }
          v6 = 1;
          ++v8;
        }
        else
        {
          CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                        *(_QWORD *)v9,
                                        *v8);
          v6 = (CachedFeatureEnabledState & 1) != 0;
          ++v8;
          if ( (CachedFeatureEnabledState & 1) == 0 )
            break;
        }
      }
      v4 = v4 && v6;
    }
  }
  else
  {
    v7 = 0;
  }
  while ( 1 )
  {
    v11 = v4 | v5 & 0xFFFFFFFE;
    if ( v7 && !v6 )
      v11 = v4 & 0xFFFFFBFF | v5 & 0xFFFFFBFE;
    v12 = v11 & 0xFFFFFFCF;
    if ( (v5 & 1) == v4 )
      v12 = v11;
    v13 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v5);
    if ( v5 == v13 )
      break;
    v5 = v13;
  }
  LODWORD(v15) = v12 & 0xFFFFFDFF;
  return v15;
}

```

## disassembly

```asm
0x14000e81c  mov     [rsp+arg_8], rbx
0x14000e821  mov     [rsp+arg_10], rbp
0x14000e826  push    rsi
0x14000e827  push    rdi
0x14000e828  push    r13
0x14000e82a  push    r14
0x14000e82c  push    r15
0x14000e82e  sub     rsp, 20h
0x14000e832  mov     r13d, 1
0x14000e838  mov     [rsp+48h+arg_0], 0
0x14000e841  mov     esi, edx
0x14000e843  mov     r15, rcx
0x14000e846  shr     esi, 6
0x14000e849  mov     ecx, 0C00h
0x14000e84e  mov     eax, edx
0x14000e850  and     esi, r13d
0x14000e853  and     eax, ecx
0x14000e855  mov     rbx, rdx
0x14000e858  mov     edi, r13d
0x14000e85b  cmp     eax, ecx
0x14000e85d  jz      short loc_14000E867
0x14000e85f  test    esi, esi
0x14000e861  jnz     short loc_14000E867
0x14000e863  xor     ebp, ebp
0x14000e865  jmp     short loc_14000E8D5
0x14000e867  mov     r14, [r8+20h]
0x14000e86b  xor     ebp, ebp
0x14000e86d  cmp     eax, ecx
0x14000e86f  setz    bpl
0x14000e873  test    r14, r14
0x14000e876  jz      short loc_14000E8D5
0x14000e878  mov     rax, [r14]
0x14000e87b  test    rax, rax
0x14000e87e  jz      short loc_14000E8C6
0x14000e880  cmp     byte ptr [rax+1Eh], 0
0x14000e884  jnz     short loc_14000E8B1
0x14000e886  cmp     byte ptr [rax+1Dh], 0
0x14000e88a  jnz     short loc_14000E8B1
0x14000e88c  mov     rcx, [rax]
0x14000e88f  mov     rdx, rax
0x14000e892  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000e897  test    edi, edi
0x14000e899  jz      short loc_14000E8A5
0x14000e89b  test    r13b, al
0x14000e89e  jz      short loc_14000E8A5
0x14000e8a0  mov     edi, r13d
0x14000e8a3  jmp     short loc_14000E8A7
0x14000e8a5  xor     edi, edi
0x14000e8a7  add     r14, 8
0x14000e8ab  test    edi, edi
0x14000e8ad  jnz     short loc_14000E878
0x14000e8af  jmp     short loc_14000E8C6
0x14000e8b1  test    edi, edi
0x14000e8b3  jz      short loc_14000E8C4
0x14000e8b5  cmp     byte ptr [rax+1Fh], 0
0x14000e8b9  jz      short loc_14000E8C4
0x14000e8bb  mov     edi, r13d
0x14000e8be  add     r14, 8
0x14000e8c2  jmp     short loc_14000E878
0x14000e8c4  xor     edi, edi
0x14000e8c6  test    esi, esi
0x14000e8c8  jz      short loc_14000E8D3
0x14000e8ca  test    edi, edi
0x14000e8cc  jz      short loc_14000E8D3
0x14000e8ce  mov     esi, r13d
0x14000e8d1  jmp     short loc_14000E8D5
0x14000e8d3  xor     esi, esi
0x14000e8d5  mov     edx, ebx
0x14000e8d7  and     edx, 0FFFFFFFEh
0x14000e8da  or      edx, esi
0x14000e8dc  test    ebp, ebp
0x14000e8de  jz      short loc_14000E8E8
0x14000e8e0  test    edi, edi
0x14000e8e2  jnz     short loc_14000E8E8
0x14000e8e4  btr     edx, 0Ah
0x14000e8e8  mov     eax, ebx
0x14000e8ea  mov     ecx, edx
0x14000e8ec  and     eax, r13d
0x14000e8ef  and     ecx, 0FFFFFFCFh
0x14000e8f2  cmp     eax, esi
0x14000e8f4  mov     eax, ebx
0x14000e8f6  cmovz   ecx, edx
0x14000e8f9  btr     ecx, 9
0x14000e8fd  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000e901  lock cmpxchg [r15], ecx
0x14000e906  jz      short loc_14000E90C
0x14000e908  mov     ebx, eax
0x14000e90a  jmp     short loc_14000E8D5
0x14000e90c  mov     rax, [rsp+48h+arg_0]
0x14000e911  mov     rbx, [rsp+48h+arg_8]
0x14000e916  mov     rbp, [rsp+48h+arg_10]
0x14000e91b  add     rsp, 20h
0x14000e91f  pop     r15
0x14000e921  pop     r14
0x14000e923  pop     r13
0x14000e925  pop     rdi
0x14000e926  pop     rsi
0x14000e927  retn
```
