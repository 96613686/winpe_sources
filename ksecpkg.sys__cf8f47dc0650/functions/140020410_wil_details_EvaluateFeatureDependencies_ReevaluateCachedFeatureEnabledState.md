# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140020410`
- end: `0x14002051d`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400203d4`

## callees

- `0x1400203d4`
- `0x140020410`

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
0x140020410  mov     [rsp+arg_8], rbx
0x140020415  mov     [rsp+arg_10], rbp
0x14002041a  push    rsi
0x14002041b  push    rdi
0x14002041c  push    r13
0x14002041e  push    r14
0x140020420  push    r15
0x140020422  sub     rsp, 20h
0x140020426  mov     r13d, 1
0x14002042c  mov     [rsp+48h+arg_0], 0
0x140020435  mov     esi, edx
0x140020437  mov     r15, rcx
0x14002043a  shr     esi, 6
0x14002043d  mov     ecx, 0C00h
0x140020442  mov     eax, edx
0x140020444  and     esi, r13d
0x140020447  and     eax, ecx
0x140020449  mov     rbx, rdx
0x14002044c  mov     edi, r13d
0x14002044f  cmp     eax, ecx
0x140020451  jz      short loc_14002045B
0x140020453  test    esi, esi
0x140020455  jnz     short loc_14002045B
0x140020457  xor     ebp, ebp
0x140020459  jmp     short loc_1400204C9
0x14002045b  mov     r14, [r8+20h]
0x14002045f  xor     ebp, ebp
0x140020461  cmp     eax, ecx
0x140020463  setz    bpl
0x140020467  test    r14, r14
0x14002046a  jz      short loc_1400204C9
0x14002046c  mov     rax, [r14]
0x14002046f  test    rax, rax
0x140020472  jz      short loc_1400204BA
0x140020474  cmp     byte ptr [rax+1Eh], 0
0x140020478  jnz     short loc_1400204A5
0x14002047a  cmp     byte ptr [rax+1Dh], 0
0x14002047e  jnz     short loc_1400204A5
0x140020480  mov     rcx, [rax]
0x140020483  mov     rdx, rax
0x140020486  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14002048b  test    edi, edi
0x14002048d  jz      short loc_140020499
0x14002048f  test    r13b, al
0x140020492  jz      short loc_140020499
0x140020494  mov     edi, r13d
0x140020497  jmp     short loc_14002049B
0x140020499  xor     edi, edi
0x14002049b  add     r14, 8
0x14002049f  test    edi, edi
0x1400204a1  jnz     short loc_14002046C
0x1400204a3  jmp     short loc_1400204BA
0x1400204a5  test    edi, edi
0x1400204a7  jz      short loc_1400204B8
0x1400204a9  cmp     byte ptr [rax+1Fh], 0
0x1400204ad  jz      short loc_1400204B8
0x1400204af  mov     edi, r13d
0x1400204b2  add     r14, 8
0x1400204b6  jmp     short loc_14002046C
0x1400204b8  xor     edi, edi
0x1400204ba  test    esi, esi
0x1400204bc  jz      short loc_1400204C7
0x1400204be  test    edi, edi
0x1400204c0  jz      short loc_1400204C7
0x1400204c2  mov     esi, r13d
0x1400204c5  jmp     short loc_1400204C9
0x1400204c7  xor     esi, esi
0x1400204c9  mov     edx, ebx
0x1400204cb  and     edx, 0FFFFFFFEh
0x1400204ce  or      edx, esi
0x1400204d0  test    ebp, ebp
0x1400204d2  jz      short loc_1400204DC
0x1400204d4  test    edi, edi
0x1400204d6  jnz     short loc_1400204DC
0x1400204d8  btr     edx, 0Ah
0x1400204dc  mov     eax, ebx
0x1400204de  mov     ecx, edx
0x1400204e0  and     eax, r13d
0x1400204e3  and     ecx, 0FFFFFFCFh
0x1400204e6  cmp     eax, esi
0x1400204e8  mov     eax, ebx
0x1400204ea  cmovz   ecx, edx
0x1400204ed  btr     ecx, 9
0x1400204f1  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400204f5  lock cmpxchg [r15], ecx
0x1400204fa  jz      short loc_140020500
0x1400204fc  mov     ebx, eax
0x1400204fe  jmp     short loc_1400204C9
0x140020500  mov     rax, [rsp+48h+arg_0]
0x140020505  mov     rbx, [rsp+48h+arg_8]
0x14002050a  mov     rbp, [rsp+48h+arg_10]
0x14002050f  add     rsp, 20h
0x140020513  pop     r15
0x140020515  pop     r14
0x140020517  pop     r13
0x140020519  pop     rdi
0x14002051a  pop     rsi
0x14002051b  retn
```
