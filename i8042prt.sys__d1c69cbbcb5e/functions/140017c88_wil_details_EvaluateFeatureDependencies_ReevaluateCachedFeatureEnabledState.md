# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140017c88`
- end: `0x140017d3e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017c4c`

## callees

- `0x140017c4c`
- `0x140017c88`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  signed __int32 v3; // ebx
  int v5; // edi
  __int64 *v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edx
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+8h]

  HIDWORD(v11) = 0;
  v3 = a2;
  v5 = (a2 >> 6) & 1;
  if ( v5 )
  {
    v6 = *(__int64 **)(a3 + 32);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        if ( *(_BYTE *)(v7 + 30) || *(_BYTE *)(v7 + 29) )
        {
          if ( !*(_BYTE *)(v7 + 31) )
          {
            v5 = 0;
            goto LABEL_11;
          }
          v5 = 1;
          ++v6;
        }
        else
        {
          v5 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)v7, *v6++) & 1) != 0;
          if ( !v5 )
            goto LABEL_11;
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_11:
    v8 = v5 & 0xFFFFFFCF | v3 & 0xFFFFFFCE;
    if ( (v3 & 1) == v5 )
      v8 = v5 | v3 & 0xFFFFFFFE;
    v9 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v3);
    if ( v3 == v9 )
      break;
    v3 = v9;
  }
  LODWORD(v11) = v8 & 0xFFFFFDFF;
  return v11;
}

```

## disassembly

```asm
0x140017c88  push    rbx
0x140017c8a  push    rbp
0x140017c8b  push    rsi
0x140017c8c  push    rdi
0x140017c8d  sub     rsp, 28h
0x140017c91  mov     edi, edx
0x140017c93  mov     [rsp+48h+arg_0], 0
0x140017c9c  shr     edi, 6
0x140017c9f  mov     rbx, rdx
0x140017ca2  mov     rbp, rcx
0x140017ca5  and     edi, 1
0x140017ca8  jz      short loc_140017D04
0x140017caa  mov     rsi, [r8+20h]
0x140017cae  test    rsi, rsi
0x140017cb1  jz      short loc_140017D04
0x140017cb3  mov     rax, [rsi]
0x140017cb6  test    rax, rax
0x140017cb9  jz      short loc_140017D04
0x140017cbb  cmp     byte ptr [rax+1Eh], 0
0x140017cbf  jnz     short loc_140017CED
0x140017cc1  cmp     byte ptr [rax+1Dh], 0
0x140017cc5  jnz     short loc_140017CED
0x140017cc7  mov     rcx, [rax]
0x140017cca  mov     rdx, rax
0x140017ccd  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140017cd2  test    edi, edi
0x140017cd4  jz      short loc_140017CE1
0x140017cd6  test    al, 1
0x140017cd8  jz      short loc_140017CE1
0x140017cda  mov     edi, 1
0x140017cdf  jmp     short loc_140017CE3
0x140017ce1  xor     edi, edi
0x140017ce3  add     rsi, 8
0x140017ce7  test    edi, edi
0x140017ce9  jnz     short loc_140017CB3
0x140017ceb  jmp     short loc_140017D04
0x140017ced  test    edi, edi
0x140017cef  jz      short loc_140017D02
0x140017cf1  cmp     byte ptr [rax+1Fh], 0
0x140017cf5  jz      short loc_140017D02
0x140017cf7  mov     edi, 1
0x140017cfc  add     rsi, 8
0x140017d00  jmp     short loc_140017CB3
0x140017d02  xor     edi, edi
0x140017d04  mov     ecx, ebx
0x140017d06  mov     eax, ebx
0x140017d08  and     ecx, 0FFFFFFFEh
0x140017d0b  and     eax, 1
0x140017d0e  or      ecx, edi
0x140017d10  mov     edx, ecx
0x140017d12  and     edx, 0FFFFFFCFh
0x140017d15  cmp     eax, edi
0x140017d17  mov     eax, ebx
0x140017d19  cmovz   edx, ecx
0x140017d1c  btr     edx, 9
0x140017d20  mov     dword ptr [rsp+48h+arg_0], edx
0x140017d24  lock cmpxchg [rbp+0], edx
0x140017d29  jz      short loc_140017D2F
0x140017d2b  mov     ebx, eax
0x140017d2d  jmp     short loc_140017D04
0x140017d2f  mov     rax, [rsp+48h+arg_0]
0x140017d34  add     rsp, 28h
0x140017d38  pop     rdi
0x140017d39  pop     rsi
0x140017d3a  pop     rbp
0x140017d3b  pop     rbx
0x140017d3c  retn
```
