# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14004177c`
- end: `0x140041889`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140041628`
- `0x140041740`

## callees

- `0x140041740`
- `0x14004177c`

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
0x14004177c  mov     [rsp+arg_8], rbx
0x140041781  mov     [rsp+arg_10], rbp
0x140041786  push    rsi
0x140041787  push    rdi
0x140041788  push    r13
0x14004178a  push    r14
0x14004178c  push    r15
0x14004178e  sub     rsp, 20h
0x140041792  mov     r13d, 1
0x140041798  mov     [rsp+48h+arg_0], 0
0x1400417a1  mov     esi, edx
0x1400417a3  mov     r15, rcx
0x1400417a6  shr     esi, 6
0x1400417a9  mov     ecx, 0C00h
0x1400417ae  mov     eax, edx
0x1400417b0  and     esi, r13d
0x1400417b3  and     eax, ecx
0x1400417b5  mov     rbx, rdx
0x1400417b8  mov     edi, r13d
0x1400417bb  cmp     eax, ecx
0x1400417bd  jz      short loc_1400417C7
0x1400417bf  test    esi, esi
0x1400417c1  jnz     short loc_1400417C7
0x1400417c3  xor     ebp, ebp
0x1400417c5  jmp     short loc_140041835
0x1400417c7  mov     r14, [r8+20h]
0x1400417cb  xor     ebp, ebp
0x1400417cd  cmp     eax, ecx
0x1400417cf  setz    bpl
0x1400417d3  test    r14, r14
0x1400417d6  jz      short loc_140041835
0x1400417d8  mov     rax, [r14]
0x1400417db  test    rax, rax
0x1400417de  jz      short loc_140041826
0x1400417e0  cmp     byte ptr [rax+1Eh], 0
0x1400417e4  jnz     short loc_140041811
0x1400417e6  cmp     byte ptr [rax+1Dh], 0
0x1400417ea  jnz     short loc_140041811
0x1400417ec  mov     rcx, [rax]
0x1400417ef  mov     rdx, rax
0x1400417f2  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400417f7  test    edi, edi
0x1400417f9  jz      short loc_140041805
0x1400417fb  test    r13b, al
0x1400417fe  jz      short loc_140041805
0x140041800  mov     edi, r13d
0x140041803  jmp     short loc_140041807
0x140041805  xor     edi, edi
0x140041807  add     r14, 8
0x14004180b  test    edi, edi
0x14004180d  jnz     short loc_1400417D8
0x14004180f  jmp     short loc_140041826
0x140041811  test    edi, edi
0x140041813  jz      short loc_140041824
0x140041815  cmp     byte ptr [rax+1Fh], 0
0x140041819  jz      short loc_140041824
0x14004181b  mov     edi, r13d
0x14004181e  add     r14, 8
0x140041822  jmp     short loc_1400417D8
0x140041824  xor     edi, edi
0x140041826  test    esi, esi
0x140041828  jz      short loc_140041833
0x14004182a  test    edi, edi
0x14004182c  jz      short loc_140041833
0x14004182e  mov     esi, r13d
0x140041831  jmp     short loc_140041835
0x140041833  xor     esi, esi
0x140041835  mov     edx, ebx
0x140041837  and     edx, 0FFFFFFFEh
0x14004183a  or      edx, esi
0x14004183c  test    ebp, ebp
0x14004183e  jz      short loc_140041848
0x140041840  test    edi, edi
0x140041842  jnz     short loc_140041848
0x140041844  btr     edx, 0Ah
0x140041848  mov     eax, ebx
0x14004184a  mov     ecx, edx
0x14004184c  and     eax, r13d
0x14004184f  and     ecx, 0FFFFFFCFh
0x140041852  cmp     eax, esi
0x140041854  mov     eax, ebx
0x140041856  cmovz   ecx, edx
0x140041859  btr     ecx, 9
0x14004185d  mov     dword ptr [rsp+48h+arg_0], ecx
0x140041861  lock cmpxchg [r15], ecx
0x140041866  jz      short loc_14004186C
0x140041868  mov     ebx, eax
0x14004186a  jmp     short loc_140041835
0x14004186c  mov     rax, [rsp+48h+arg_0]
0x140041871  mov     rbx, [rsp+48h+arg_8]
0x140041876  mov     rbp, [rsp+48h+arg_10]
0x14004187b  add     rsp, 20h
0x14004187f  pop     r15
0x140041881  pop     r14
0x140041883  pop     r13
0x140041885  pop     rdi
0x140041886  pop     rsi
0x140041887  retn
```
