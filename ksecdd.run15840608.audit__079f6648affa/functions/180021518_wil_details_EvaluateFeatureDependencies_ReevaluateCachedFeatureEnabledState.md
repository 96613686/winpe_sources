# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x180021518`
- end: `0x180021625`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800214dc`

## callees

- `0x1800214dc`
- `0x180021518`

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
0x180021518  mov     [rsp+arg_8], rbx
0x18002151d  mov     [rsp+arg_10], rbp
0x180021522  push    rsi
0x180021523  push    rdi
0x180021524  push    r13
0x180021526  push    r14
0x180021528  push    r15
0x18002152a  sub     rsp, 20h
0x18002152e  mov     r13d, 1
0x180021534  mov     [rsp+48h+arg_0], 0
0x18002153d  mov     esi, edx
0x18002153f  mov     r15, rcx
0x180021542  shr     esi, 6
0x180021545  mov     ecx, 0C00h
0x18002154a  mov     eax, edx
0x18002154c  and     esi, r13d
0x18002154f  and     eax, ecx
0x180021551  mov     rbx, rdx
0x180021554  mov     edi, r13d
0x180021557  cmp     eax, ecx
0x180021559  jz      short loc_180021563
0x18002155b  test    esi, esi
0x18002155d  jnz     short loc_180021563
0x18002155f  xor     ebp, ebp
0x180021561  jmp     short loc_1800215D1
0x180021563  mov     r14, [r8+20h]
0x180021567  xor     ebp, ebp
0x180021569  cmp     eax, ecx
0x18002156b  setz    bpl
0x18002156f  test    r14, r14
0x180021572  jz      short loc_1800215D1
0x180021574  mov     rax, [r14]
0x180021577  test    rax, rax
0x18002157a  jz      short loc_1800215C2
0x18002157c  cmp     byte ptr [rax+1Eh], 0
0x180021580  jnz     short loc_1800215AD
0x180021582  cmp     byte ptr [rax+1Dh], 0
0x180021586  jnz     short loc_1800215AD
0x180021588  mov     rcx, [rax]
0x18002158b  mov     rdx, rax
0x18002158e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x180021593  test    edi, edi
0x180021595  jz      short loc_1800215A1
0x180021597  test    r13b, al
0x18002159a  jz      short loc_1800215A1
0x18002159c  mov     edi, r13d
0x18002159f  jmp     short loc_1800215A3
0x1800215a1  xor     edi, edi
0x1800215a3  add     r14, 8
0x1800215a7  test    edi, edi
0x1800215a9  jnz     short loc_180021574
0x1800215ab  jmp     short loc_1800215C2
0x1800215ad  test    edi, edi
0x1800215af  jz      short loc_1800215C0
0x1800215b1  cmp     byte ptr [rax+1Fh], 0
0x1800215b5  jz      short loc_1800215C0
0x1800215b7  mov     edi, r13d
0x1800215ba  add     r14, 8
0x1800215be  jmp     short loc_180021574
0x1800215c0  xor     edi, edi
0x1800215c2  test    esi, esi
0x1800215c4  jz      short loc_1800215CF
0x1800215c6  test    edi, edi
0x1800215c8  jz      short loc_1800215CF
0x1800215ca  mov     esi, r13d
0x1800215cd  jmp     short loc_1800215D1
0x1800215cf  xor     esi, esi
0x1800215d1  mov     edx, ebx
0x1800215d3  and     edx, 0FFFFFFFEh
0x1800215d6  or      edx, esi
0x1800215d8  test    ebp, ebp
0x1800215da  jz      short loc_1800215E4
0x1800215dc  test    edi, edi
0x1800215de  jnz     short loc_1800215E4
0x1800215e0  btr     edx, 0Ah
0x1800215e4  mov     eax, ebx
0x1800215e6  mov     ecx, edx
0x1800215e8  and     eax, r13d
0x1800215eb  and     ecx, 0FFFFFFCFh
0x1800215ee  cmp     eax, esi
0x1800215f0  mov     eax, ebx
0x1800215f2  cmovz   ecx, edx
0x1800215f5  btr     ecx, 9
0x1800215f9  mov     dword ptr [rsp+48h+arg_0], ecx
0x1800215fd  lock cmpxchg [r15], ecx
0x180021602  jz      short loc_180021608
0x180021604  mov     ebx, eax
0x180021606  jmp     short loc_1800215D1
0x180021608  mov     rax, [rsp+48h+arg_0]
0x18002160d  mov     rbx, [rsp+48h+arg_8]
0x180021612  mov     rbp, [rsp+48h+arg_10]
0x180021617  add     rsp, 20h
0x18002161b  pop     r15
0x18002161d  pop     r14
0x18002161f  pop     r13
0x180021621  pop     rdi
0x180021622  pop     rsi
0x180021623  retn
```
