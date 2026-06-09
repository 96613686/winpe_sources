# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14004325c`
- end: `0x140043369`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140043220`

## callees

- `0x140043220`
- `0x14004325c`

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
0x14004325c  mov     [rsp+arg_8], rbx
0x140043261  mov     [rsp+arg_10], rbp
0x140043266  push    rsi
0x140043267  push    rdi
0x140043268  push    r13
0x14004326a  push    r14
0x14004326c  push    r15
0x14004326e  sub     rsp, 20h
0x140043272  mov     r13d, 1
0x140043278  mov     [rsp+48h+arg_0], 0
0x140043281  mov     esi, edx
0x140043283  mov     r15, rcx
0x140043286  shr     esi, 6
0x140043289  mov     ecx, 0C00h
0x14004328e  mov     eax, edx
0x140043290  and     esi, r13d
0x140043293  and     eax, ecx
0x140043295  mov     rbx, rdx
0x140043298  mov     edi, r13d
0x14004329b  cmp     eax, ecx
0x14004329d  jz      short loc_1400432A7
0x14004329f  test    esi, esi
0x1400432a1  jnz     short loc_1400432A7
0x1400432a3  xor     ebp, ebp
0x1400432a5  jmp     short loc_140043315
0x1400432a7  mov     r14, [r8+20h]
0x1400432ab  xor     ebp, ebp
0x1400432ad  cmp     eax, ecx
0x1400432af  setz    bpl
0x1400432b3  test    r14, r14
0x1400432b6  jz      short loc_140043315
0x1400432b8  mov     rax, [r14]
0x1400432bb  test    rax, rax
0x1400432be  jz      short loc_140043306
0x1400432c0  cmp     byte ptr [rax+1Eh], 0
0x1400432c4  jnz     short loc_1400432F1
0x1400432c6  cmp     byte ptr [rax+1Dh], 0
0x1400432ca  jnz     short loc_1400432F1
0x1400432cc  mov     rcx, [rax]
0x1400432cf  mov     rdx, rax
0x1400432d2  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400432d7  test    edi, edi
0x1400432d9  jz      short loc_1400432E5
0x1400432db  test    r13b, al
0x1400432de  jz      short loc_1400432E5
0x1400432e0  mov     edi, r13d
0x1400432e3  jmp     short loc_1400432E7
0x1400432e5  xor     edi, edi
0x1400432e7  add     r14, 8
0x1400432eb  test    edi, edi
0x1400432ed  jnz     short loc_1400432B8
0x1400432ef  jmp     short loc_140043306
0x1400432f1  test    edi, edi
0x1400432f3  jz      short loc_140043304
0x1400432f5  cmp     byte ptr [rax+1Fh], 0
0x1400432f9  jz      short loc_140043304
0x1400432fb  mov     edi, r13d
0x1400432fe  add     r14, 8
0x140043302  jmp     short loc_1400432B8
0x140043304  xor     edi, edi
0x140043306  test    esi, esi
0x140043308  jz      short loc_140043313
0x14004330a  test    edi, edi
0x14004330c  jz      short loc_140043313
0x14004330e  mov     esi, r13d
0x140043311  jmp     short loc_140043315
0x140043313  xor     esi, esi
0x140043315  mov     edx, ebx
0x140043317  and     edx, 0FFFFFFFEh
0x14004331a  or      edx, esi
0x14004331c  test    ebp, ebp
0x14004331e  jz      short loc_140043328
0x140043320  test    edi, edi
0x140043322  jnz     short loc_140043328
0x140043324  btr     edx, 0Ah
0x140043328  mov     eax, ebx
0x14004332a  mov     ecx, edx
0x14004332c  and     eax, r13d
0x14004332f  and     ecx, 0FFFFFFCFh
0x140043332  cmp     eax, esi
0x140043334  mov     eax, ebx
0x140043336  cmovz   ecx, edx
0x140043339  btr     ecx, 9
0x14004333d  mov     dword ptr [rsp+48h+arg_0], ecx
0x140043341  lock cmpxchg [r15], ecx
0x140043346  jz      short loc_14004334C
0x140043348  mov     ebx, eax
0x14004334a  jmp     short loc_140043315
0x14004334c  mov     rax, [rsp+48h+arg_0]
0x140043351  mov     rbx, [rsp+48h+arg_8]
0x140043356  mov     rbp, [rsp+48h+arg_10]
0x14004335b  add     rsp, 20h
0x14004335f  pop     r15
0x140043361  pop     r14
0x140043363  pop     r13
0x140043365  pop     rdi
0x140043366  pop     rsi
0x140043367  retn
```
