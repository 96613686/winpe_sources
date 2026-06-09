# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140044dbc`
- end: `0x140044ec9`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140044d80`

## callees

- `0x140044d80`
- `0x140044dbc`

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
0x140044dbc  mov     [rsp+arg_8], rbx
0x140044dc1  mov     [rsp+arg_10], rbp
0x140044dc6  push    rsi
0x140044dc7  push    rdi
0x140044dc8  push    r13
0x140044dca  push    r14
0x140044dcc  push    r15
0x140044dce  sub     rsp, 20h
0x140044dd2  mov     r13d, 1
0x140044dd8  mov     [rsp+48h+arg_0], 0
0x140044de1  mov     esi, edx
0x140044de3  mov     r15, rcx
0x140044de6  shr     esi, 6
0x140044de9  mov     ecx, 0C00h
0x140044dee  mov     eax, edx
0x140044df0  and     esi, r13d
0x140044df3  and     eax, ecx
0x140044df5  mov     rbx, rdx
0x140044df8  mov     edi, r13d
0x140044dfb  cmp     eax, ecx
0x140044dfd  jz      short loc_140044E07
0x140044dff  test    esi, esi
0x140044e01  jnz     short loc_140044E07
0x140044e03  xor     ebp, ebp
0x140044e05  jmp     short loc_140044E75
0x140044e07  mov     r14, [r8+20h]
0x140044e0b  xor     ebp, ebp
0x140044e0d  cmp     eax, ecx
0x140044e0f  setz    bpl
0x140044e13  test    r14, r14
0x140044e16  jz      short loc_140044E75
0x140044e18  mov     rax, [r14]
0x140044e1b  test    rax, rax
0x140044e1e  jz      short loc_140044E66
0x140044e20  cmp     byte ptr [rax+1Eh], 0
0x140044e24  jnz     short loc_140044E51
0x140044e26  cmp     byte ptr [rax+1Dh], 0
0x140044e2a  jnz     short loc_140044E51
0x140044e2c  mov     rcx, [rax]
0x140044e2f  mov     rdx, rax
0x140044e32  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140044e37  test    edi, edi
0x140044e39  jz      short loc_140044E45
0x140044e3b  test    r13b, al
0x140044e3e  jz      short loc_140044E45
0x140044e40  mov     edi, r13d
0x140044e43  jmp     short loc_140044E47
0x140044e45  xor     edi, edi
0x140044e47  add     r14, 8
0x140044e4b  test    edi, edi
0x140044e4d  jnz     short loc_140044E18
0x140044e4f  jmp     short loc_140044E66
0x140044e51  test    edi, edi
0x140044e53  jz      short loc_140044E64
0x140044e55  cmp     byte ptr [rax+1Fh], 0
0x140044e59  jz      short loc_140044E64
0x140044e5b  mov     edi, r13d
0x140044e5e  add     r14, 8
0x140044e62  jmp     short loc_140044E18
0x140044e64  xor     edi, edi
0x140044e66  test    esi, esi
0x140044e68  jz      short loc_140044E73
0x140044e6a  test    edi, edi
0x140044e6c  jz      short loc_140044E73
0x140044e6e  mov     esi, r13d
0x140044e71  jmp     short loc_140044E75
0x140044e73  xor     esi, esi
0x140044e75  mov     edx, ebx
0x140044e77  and     edx, 0FFFFFFFEh
0x140044e7a  or      edx, esi
0x140044e7c  test    ebp, ebp
0x140044e7e  jz      short loc_140044E88
0x140044e80  test    edi, edi
0x140044e82  jnz     short loc_140044E88
0x140044e84  btr     edx, 0Ah
0x140044e88  mov     eax, ebx
0x140044e8a  mov     ecx, edx
0x140044e8c  and     eax, r13d
0x140044e8f  and     ecx, 0FFFFFFCFh
0x140044e92  cmp     eax, esi
0x140044e94  mov     eax, ebx
0x140044e96  cmovz   ecx, edx
0x140044e99  btr     ecx, 9
0x140044e9d  mov     dword ptr [rsp+48h+arg_0], ecx
0x140044ea1  lock cmpxchg [r15], ecx
0x140044ea6  jz      short loc_140044EAC
0x140044ea8  mov     ebx, eax
0x140044eaa  jmp     short loc_140044E75
0x140044eac  mov     rax, [rsp+48h+arg_0]
0x140044eb1  mov     rbx, [rsp+48h+arg_8]
0x140044eb6  mov     rbp, [rsp+48h+arg_10]
0x140044ebb  add     rsp, 20h
0x140044ebf  pop     r15
0x140044ec1  pop     r14
0x140044ec3  pop     r13
0x140044ec5  pop     rdi
0x140044ec6  pop     rsi
0x140044ec7  retn
```
