# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14002f6c0`
- end: `0x14002f7cd`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002f684`

## callees

- `0x14002f684`
- `0x14002f6c0`

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
0x14002f6c0  mov     [rsp+arg_8], rbx
0x14002f6c5  mov     [rsp+arg_10], rbp
0x14002f6ca  push    rsi
0x14002f6cb  push    rdi
0x14002f6cc  push    r13
0x14002f6ce  push    r14
0x14002f6d0  push    r15
0x14002f6d2  sub     rsp, 20h
0x14002f6d6  mov     r13d, 1
0x14002f6dc  mov     [rsp+48h+arg_0], 0
0x14002f6e5  mov     esi, edx
0x14002f6e7  mov     r15, rcx
0x14002f6ea  shr     esi, 6
0x14002f6ed  mov     ecx, 0C00h
0x14002f6f2  mov     eax, edx
0x14002f6f4  and     esi, r13d
0x14002f6f7  and     eax, ecx
0x14002f6f9  mov     rbx, rdx
0x14002f6fc  mov     edi, r13d
0x14002f6ff  cmp     eax, ecx
0x14002f701  jz      short loc_14002F70B
0x14002f703  test    esi, esi
0x14002f705  jnz     short loc_14002F70B
0x14002f707  xor     ebp, ebp
0x14002f709  jmp     short loc_14002F779
0x14002f70b  mov     r14, [r8+20h]
0x14002f70f  xor     ebp, ebp
0x14002f711  cmp     eax, ecx
0x14002f713  setz    bpl
0x14002f717  test    r14, r14
0x14002f71a  jz      short loc_14002F779
0x14002f71c  mov     rax, [r14]
0x14002f71f  test    rax, rax
0x14002f722  jz      short loc_14002F76A
0x14002f724  cmp     byte ptr [rax+1Eh], 0
0x14002f728  jnz     short loc_14002F755
0x14002f72a  cmp     byte ptr [rax+1Dh], 0
0x14002f72e  jnz     short loc_14002F755
0x14002f730  mov     rcx, [rax]
0x14002f733  mov     rdx, rax
0x14002f736  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14002f73b  test    edi, edi
0x14002f73d  jz      short loc_14002F749
0x14002f73f  test    r13b, al
0x14002f742  jz      short loc_14002F749
0x14002f744  mov     edi, r13d
0x14002f747  jmp     short loc_14002F74B
0x14002f749  xor     edi, edi
0x14002f74b  add     r14, 8
0x14002f74f  test    edi, edi
0x14002f751  jnz     short loc_14002F71C
0x14002f753  jmp     short loc_14002F76A
0x14002f755  test    edi, edi
0x14002f757  jz      short loc_14002F768
0x14002f759  cmp     byte ptr [rax+1Fh], 0
0x14002f75d  jz      short loc_14002F768
0x14002f75f  mov     edi, r13d
0x14002f762  add     r14, 8
0x14002f766  jmp     short loc_14002F71C
0x14002f768  xor     edi, edi
0x14002f76a  test    esi, esi
0x14002f76c  jz      short loc_14002F777
0x14002f76e  test    edi, edi
0x14002f770  jz      short loc_14002F777
0x14002f772  mov     esi, r13d
0x14002f775  jmp     short loc_14002F779
0x14002f777  xor     esi, esi
0x14002f779  mov     edx, ebx
0x14002f77b  and     edx, 0FFFFFFFEh
0x14002f77e  or      edx, esi
0x14002f780  test    ebp, ebp
0x14002f782  jz      short loc_14002F78C
0x14002f784  test    edi, edi
0x14002f786  jnz     short loc_14002F78C
0x14002f788  btr     edx, 0Ah
0x14002f78c  mov     eax, ebx
0x14002f78e  mov     ecx, edx
0x14002f790  and     eax, r13d
0x14002f793  and     ecx, 0FFFFFFCFh
0x14002f796  cmp     eax, esi
0x14002f798  mov     eax, ebx
0x14002f79a  cmovz   ecx, edx
0x14002f79d  btr     ecx, 9
0x14002f7a1  mov     dword ptr [rsp+48h+arg_0], ecx
0x14002f7a5  lock cmpxchg [r15], ecx
0x14002f7aa  jz      short loc_14002F7B0
0x14002f7ac  mov     ebx, eax
0x14002f7ae  jmp     short loc_14002F779
0x14002f7b0  mov     rax, [rsp+48h+arg_0]
0x14002f7b5  mov     rbx, [rsp+48h+arg_8]
0x14002f7ba  mov     rbp, [rsp+48h+arg_10]
0x14002f7bf  add     rsp, 20h
0x14002f7c3  pop     r15
0x14002f7c5  pop     r14
0x14002f7c7  pop     r13
0x14002f7c9  pop     rdi
0x14002f7ca  pop     rsi
0x14002f7cb  retn
```
