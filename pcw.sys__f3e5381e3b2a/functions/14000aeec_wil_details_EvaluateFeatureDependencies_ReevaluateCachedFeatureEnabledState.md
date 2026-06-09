# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000aeec`
- end: `0x14000aff9`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ad9c`
- `0x14000aeb0`

## callees

- `0x14000aeb0`
- `0x14000aeec`

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
0x14000aeec  mov     [rsp+arg_8], rbx
0x14000aef1  mov     [rsp+arg_10], rbp
0x14000aef6  push    rsi
0x14000aef7  push    rdi
0x14000aef8  push    r13
0x14000aefa  push    r14
0x14000aefc  push    r15
0x14000aefe  sub     rsp, 20h
0x14000af02  mov     r13d, 1
0x14000af08  mov     [rsp+48h+arg_0], 0
0x14000af11  mov     esi, edx
0x14000af13  mov     r15, rcx
0x14000af16  shr     esi, 6
0x14000af19  mov     ecx, 0C00h
0x14000af1e  mov     eax, edx
0x14000af20  and     esi, r13d
0x14000af23  and     eax, ecx
0x14000af25  mov     rbx, rdx
0x14000af28  mov     edi, r13d
0x14000af2b  cmp     eax, ecx
0x14000af2d  jz      short loc_14000AF37
0x14000af2f  test    esi, esi
0x14000af31  jnz     short loc_14000AF37
0x14000af33  xor     ebp, ebp
0x14000af35  jmp     short loc_14000AFA5
0x14000af37  mov     r14, [r8+20h]
0x14000af3b  xor     ebp, ebp
0x14000af3d  cmp     eax, ecx
0x14000af3f  setz    bpl
0x14000af43  test    r14, r14
0x14000af46  jz      short loc_14000AFA5
0x14000af48  mov     rax, [r14]
0x14000af4b  test    rax, rax
0x14000af4e  jz      short loc_14000AF96
0x14000af50  cmp     byte ptr [rax+1Eh], 0
0x14000af54  jnz     short loc_14000AF81
0x14000af56  cmp     byte ptr [rax+1Dh], 0
0x14000af5a  jnz     short loc_14000AF81
0x14000af5c  mov     rcx, [rax]
0x14000af5f  mov     rdx, rax
0x14000af62  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000af67  test    edi, edi
0x14000af69  jz      short loc_14000AF75
0x14000af6b  test    r13b, al
0x14000af6e  jz      short loc_14000AF75
0x14000af70  mov     edi, r13d
0x14000af73  jmp     short loc_14000AF77
0x14000af75  xor     edi, edi
0x14000af77  add     r14, 8
0x14000af7b  test    edi, edi
0x14000af7d  jnz     short loc_14000AF48
0x14000af7f  jmp     short loc_14000AF96
0x14000af81  test    edi, edi
0x14000af83  jz      short loc_14000AF94
0x14000af85  cmp     byte ptr [rax+1Fh], 0
0x14000af89  jz      short loc_14000AF94
0x14000af8b  mov     edi, r13d
0x14000af8e  add     r14, 8
0x14000af92  jmp     short loc_14000AF48
0x14000af94  xor     edi, edi
0x14000af96  test    esi, esi
0x14000af98  jz      short loc_14000AFA3
0x14000af9a  test    edi, edi
0x14000af9c  jz      short loc_14000AFA3
0x14000af9e  mov     esi, r13d
0x14000afa1  jmp     short loc_14000AFA5
0x14000afa3  xor     esi, esi
0x14000afa5  mov     edx, ebx
0x14000afa7  and     edx, 0FFFFFFFEh
0x14000afaa  or      edx, esi
0x14000afac  test    ebp, ebp
0x14000afae  jz      short loc_14000AFB8
0x14000afb0  test    edi, edi
0x14000afb2  jnz     short loc_14000AFB8
0x14000afb4  btr     edx, 0Ah
0x14000afb8  mov     eax, ebx
0x14000afba  mov     ecx, edx
0x14000afbc  and     eax, r13d
0x14000afbf  and     ecx, 0FFFFFFCFh
0x14000afc2  cmp     eax, esi
0x14000afc4  mov     eax, ebx
0x14000afc6  cmovz   ecx, edx
0x14000afc9  btr     ecx, 9
0x14000afcd  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000afd1  lock cmpxchg [r15], ecx
0x14000afd6  jz      short loc_14000AFDC
0x14000afd8  mov     ebx, eax
0x14000afda  jmp     short loc_14000AFA5
0x14000afdc  mov     rax, [rsp+48h+arg_0]
0x14000afe1  mov     rbx, [rsp+48h+arg_8]
0x14000afe6  mov     rbp, [rsp+48h+arg_10]
0x14000afeb  add     rsp, 20h
0x14000afef  pop     r15
0x14000aff1  pop     r14
0x14000aff3  pop     r13
0x14000aff5  pop     rdi
0x14000aff6  pop     rsi
0x14000aff7  retn
```
