# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140011d98`
- end: `0x140011ea5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011d5c`

## callees

- `0x140011d5c`
- `0x140011d98`

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
0x140011d98  mov     [rsp+arg_8], rbx
0x140011d9d  mov     [rsp+arg_10], rbp
0x140011da2  push    rsi
0x140011da3  push    rdi
0x140011da4  push    r13
0x140011da6  push    r14
0x140011da8  push    r15
0x140011daa  sub     rsp, 20h
0x140011dae  mov     r13d, 1
0x140011db4  mov     [rsp+48h+arg_0], 0
0x140011dbd  mov     esi, edx
0x140011dbf  mov     r15, rcx
0x140011dc2  shr     esi, 6
0x140011dc5  mov     ecx, 0C00h
0x140011dca  mov     eax, edx
0x140011dcc  and     esi, r13d
0x140011dcf  and     eax, ecx
0x140011dd1  mov     rbx, rdx
0x140011dd4  mov     edi, r13d
0x140011dd7  cmp     eax, ecx
0x140011dd9  jz      short loc_140011DE3
0x140011ddb  test    esi, esi
0x140011ddd  jnz     short loc_140011DE3
0x140011ddf  xor     ebp, ebp
0x140011de1  jmp     short loc_140011E51
0x140011de3  mov     r14, [r8+20h]
0x140011de7  xor     ebp, ebp
0x140011de9  cmp     eax, ecx
0x140011deb  setz    bpl
0x140011def  test    r14, r14
0x140011df2  jz      short loc_140011E51
0x140011df4  mov     rax, [r14]
0x140011df7  test    rax, rax
0x140011dfa  jz      short loc_140011E42
0x140011dfc  cmp     byte ptr [rax+1Eh], 0
0x140011e00  jnz     short loc_140011E2D
0x140011e02  cmp     byte ptr [rax+1Dh], 0
0x140011e06  jnz     short loc_140011E2D
0x140011e08  mov     rcx, [rax]
0x140011e0b  mov     rdx, rax
0x140011e0e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140011e13  test    edi, edi
0x140011e15  jz      short loc_140011E21
0x140011e17  test    r13b, al
0x140011e1a  jz      short loc_140011E21
0x140011e1c  mov     edi, r13d
0x140011e1f  jmp     short loc_140011E23
0x140011e21  xor     edi, edi
0x140011e23  add     r14, 8
0x140011e27  test    edi, edi
0x140011e29  jnz     short loc_140011DF4
0x140011e2b  jmp     short loc_140011E42
0x140011e2d  test    edi, edi
0x140011e2f  jz      short loc_140011E40
0x140011e31  cmp     byte ptr [rax+1Fh], 0
0x140011e35  jz      short loc_140011E40
0x140011e37  mov     edi, r13d
0x140011e3a  add     r14, 8
0x140011e3e  jmp     short loc_140011DF4
0x140011e40  xor     edi, edi
0x140011e42  test    esi, esi
0x140011e44  jz      short loc_140011E4F
0x140011e46  test    edi, edi
0x140011e48  jz      short loc_140011E4F
0x140011e4a  mov     esi, r13d
0x140011e4d  jmp     short loc_140011E51
0x140011e4f  xor     esi, esi
0x140011e51  mov     edx, ebx
0x140011e53  and     edx, 0FFFFFFFEh
0x140011e56  or      edx, esi
0x140011e58  test    ebp, ebp
0x140011e5a  jz      short loc_140011E64
0x140011e5c  test    edi, edi
0x140011e5e  jnz     short loc_140011E64
0x140011e60  btr     edx, 0Ah
0x140011e64  mov     eax, ebx
0x140011e66  mov     ecx, edx
0x140011e68  and     eax, r13d
0x140011e6b  and     ecx, 0FFFFFFCFh
0x140011e6e  cmp     eax, esi
0x140011e70  mov     eax, ebx
0x140011e72  cmovz   ecx, edx
0x140011e75  btr     ecx, 9
0x140011e79  mov     dword ptr [rsp+48h+arg_0], ecx
0x140011e7d  lock cmpxchg [r15], ecx
0x140011e82  jz      short loc_140011E88
0x140011e84  mov     ebx, eax
0x140011e86  jmp     short loc_140011E51
0x140011e88  mov     rax, [rsp+48h+arg_0]
0x140011e8d  mov     rbx, [rsp+48h+arg_8]
0x140011e92  mov     rbp, [rsp+48h+arg_10]
0x140011e97  add     rsp, 20h
0x140011e9b  pop     r15
0x140011e9d  pop     r14
0x140011e9f  pop     r13
0x140011ea1  pop     rdi
0x140011ea2  pop     rsi
0x140011ea3  retn
```
