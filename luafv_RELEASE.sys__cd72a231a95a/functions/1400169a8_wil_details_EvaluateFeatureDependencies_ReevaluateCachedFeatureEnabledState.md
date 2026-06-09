# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x1400169a8`
- end: `0x140016a5e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
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
0x1400169a8  push    rbx
0x1400169aa  push    rbp
0x1400169ab  push    rsi
0x1400169ac  push    rdi
0x1400169ad  sub     rsp, 28h
0x1400169b1  mov     edi, edx
0x1400169b3  mov     [rsp+48h+arg_0], 0
0x1400169bc  shr     edi, 6
0x1400169bf  mov     rbx, rdx
0x1400169c2  mov     rbp, rcx
0x1400169c5  and     edi, 1
0x1400169c8  jz      short loc_140016A24
0x1400169ca  mov     rsi, [r8+20h]
0x1400169ce  test    rsi, rsi
0x1400169d1  jz      short loc_140016A24
0x1400169d3  mov     rax, [rsi]
0x1400169d6  test    rax, rax
0x1400169d9  jz      short loc_140016A24
0x1400169db  cmp     byte ptr [rax+1Eh], 0
0x1400169df  jnz     short loc_140016A0D
0x1400169e1  cmp     byte ptr [rax+1Dh], 0
0x1400169e5  jnz     short loc_140016A0D
0x1400169e7  mov     rcx, [rax]
0x1400169ea  mov     rdx, rax
0x1400169ed  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400169f2  test    edi, edi
0x1400169f4  jz      short loc_140016A01
0x1400169f6  test    al, 1
0x1400169f8  jz      short loc_140016A01
0x1400169fa  mov     edi, 1
0x1400169ff  jmp     short loc_140016A03
0x140016a01  xor     edi, edi
0x140016a03  add     rsi, 8
0x140016a07  test    edi, edi
0x140016a09  jnz     short loc_1400169D3
0x140016a0b  jmp     short loc_140016A24
0x140016a0d  test    edi, edi
0x140016a0f  jz      short loc_140016A22
0x140016a11  cmp     byte ptr [rax+1Fh], 0
0x140016a15  jz      short loc_140016A22
0x140016a17  mov     edi, 1
0x140016a1c  add     rsi, 8
0x140016a20  jmp     short loc_1400169D3
0x140016a22  xor     edi, edi
0x140016a24  mov     ecx, ebx
0x140016a26  mov     eax, ebx
0x140016a28  and     ecx, 0FFFFFFFEh
0x140016a2b  and     eax, 1
0x140016a2e  or      ecx, edi
0x140016a30  mov     edx, ecx
0x140016a32  and     edx, 0FFFFFFCFh
0x140016a35  cmp     eax, edi
0x140016a37  mov     eax, ebx
0x140016a39  cmovz   edx, ecx
0x140016a3c  btr     edx, 9
0x140016a40  mov     dword ptr [rsp+48h+arg_0], edx
0x140016a44  lock cmpxchg [rbp+0], edx
0x140016a49  jz      short loc_140016A4F
0x140016a4b  mov     ebx, eax
0x140016a4d  jmp     short loc_140016A24
0x140016a4f  mov     rax, [rsp+48h+arg_0]
0x140016a54  add     rsp, 28h
0x140016a58  pop     rdi
0x140016a59  pop     rsi
0x140016a5a  pop     rbp
0x140016a5b  pop     rbx
0x140016a5c  retn
```
