# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400169a8`
- end: `0x140016ab5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: `__int64 __fastcall(volatile signed __int32 *, unsigned __int32, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001696c`

## callees

- `0x14001696c`
- `0x1400169a8`

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
  __int64 *v8; // r14
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
    v8 = *(__int64 **)(a3 + 32);
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
                                        *(_DWORD **)v9,
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
0x1400169a8  mov     [rsp+arg_8], rbx
0x1400169ad  mov     [rsp+arg_10], rbp
0x1400169b2  push    rsi
0x1400169b3  push    rdi
0x1400169b4  push    r13
0x1400169b6  push    r14
0x1400169b8  push    r15
0x1400169ba  sub     rsp, 20h
0x1400169be  mov     r13d, 1
0x1400169c4  mov     [rsp+48h+arg_0], 0
0x1400169cd  mov     esi, edx
0x1400169cf  mov     r15, rcx
0x1400169d2  shr     esi, 6
0x1400169d5  mov     ecx, 0C00h
0x1400169da  mov     eax, edx
0x1400169dc  and     esi, r13d
0x1400169df  and     eax, ecx
0x1400169e1  mov     rbx, rdx
0x1400169e4  mov     edi, r13d
0x1400169e7  cmp     eax, ecx
0x1400169e9  jz      short loc_1400169F3
0x1400169eb  test    esi, esi
0x1400169ed  jnz     short loc_1400169F3
0x1400169ef  xor     ebp, ebp
0x1400169f1  jmp     short loc_140016A61
0x1400169f3  mov     r14, [r8+20h]
0x1400169f7  xor     ebp, ebp
0x1400169f9  cmp     eax, ecx
0x1400169fb  setz    bpl
0x1400169ff  test    r14, r14
0x140016a02  jz      short loc_140016A61
0x140016a04  mov     rax, [r14]
0x140016a07  test    rax, rax
0x140016a0a  jz      short loc_140016A52
0x140016a0c  cmp     byte ptr [rax+1Eh], 0
0x140016a10  jnz     short loc_140016A3D
0x140016a12  cmp     byte ptr [rax+1Dh], 0
0x140016a16  jnz     short loc_140016A3D
0x140016a18  mov     rcx, [rax]
0x140016a1b  mov     rdx, rax
0x140016a1e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140016a23  test    edi, edi
0x140016a25  jz      short loc_140016A31
0x140016a27  test    r13b, al
0x140016a2a  jz      short loc_140016A31
0x140016a2c  mov     edi, r13d
0x140016a2f  jmp     short loc_140016A33
0x140016a31  xor     edi, edi
0x140016a33  add     r14, 8
0x140016a37  test    edi, edi
0x140016a39  jnz     short loc_140016A04
0x140016a3b  jmp     short loc_140016A52
0x140016a3d  test    edi, edi
0x140016a3f  jz      short loc_140016A50
0x140016a41  cmp     byte ptr [rax+1Fh], 0
0x140016a45  jz      short loc_140016A50
0x140016a47  mov     edi, r13d
0x140016a4a  add     r14, 8
0x140016a4e  jmp     short loc_140016A04
0x140016a50  xor     edi, edi
0x140016a52  test    esi, esi
0x140016a54  jz      short loc_140016A5F
0x140016a56  test    edi, edi
0x140016a58  jz      short loc_140016A5F
0x140016a5a  mov     esi, r13d
0x140016a5d  jmp     short loc_140016A61
0x140016a5f  xor     esi, esi
0x140016a61  mov     edx, ebx
0x140016a63  and     edx, 0FFFFFFFEh
0x140016a66  or      edx, esi
0x140016a68  test    ebp, ebp
0x140016a6a  jz      short loc_140016A74
0x140016a6c  test    edi, edi
0x140016a6e  jnz     short loc_140016A74
0x140016a70  btr     edx, 0Ah
0x140016a74  mov     eax, ebx
0x140016a76  mov     ecx, edx
0x140016a78  and     eax, r13d
0x140016a7b  and     ecx, 0FFFFFFCFh
0x140016a7e  cmp     eax, esi
0x140016a80  mov     eax, ebx
0x140016a82  cmovz   ecx, edx
0x140016a85  btr     ecx, 9
0x140016a89  mov     dword ptr [rsp+48h+arg_0], ecx
0x140016a8d  lock cmpxchg [r15], ecx
0x140016a92  jz      short loc_140016A98
0x140016a94  mov     ebx, eax
0x140016a96  jmp     short loc_140016A61
0x140016a98  mov     rax, [rsp+48h+arg_0]
0x140016a9d  mov     rbx, [rsp+48h+arg_8]
0x140016aa2  mov     rbp, [rsp+48h+arg_10]
0x140016aa7  add     rsp, 20h
0x140016aab  pop     r15
0x140016aad  pop     r14
0x140016aaf  pop     r13
0x140016ab1  pop     rdi
0x140016ab2  pop     rsi
0x140016ab3  retn
```
