# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000a9a8`
- end: `0x14000aab5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a858`
- `0x14000a96c`

## callees

- `0x14000a96c`
- `0x14000a9a8`

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
0x14000a9a8  mov     [rsp+arg_8], rbx
0x14000a9ad  mov     [rsp+arg_10], rbp
0x14000a9b2  push    rsi
0x14000a9b3  push    rdi
0x14000a9b4  push    r13
0x14000a9b6  push    r14
0x14000a9b8  push    r15
0x14000a9ba  sub     rsp, 20h
0x14000a9be  mov     r13d, 1
0x14000a9c4  mov     [rsp+48h+arg_0], 0
0x14000a9cd  mov     esi, edx
0x14000a9cf  mov     r15, rcx
0x14000a9d2  shr     esi, 6
0x14000a9d5  mov     ecx, 0C00h
0x14000a9da  mov     eax, edx
0x14000a9dc  and     esi, r13d
0x14000a9df  and     eax, ecx
0x14000a9e1  mov     rbx, rdx
0x14000a9e4  mov     edi, r13d
0x14000a9e7  cmp     eax, ecx
0x14000a9e9  jz      short loc_14000A9F3
0x14000a9eb  test    esi, esi
0x14000a9ed  jnz     short loc_14000A9F3
0x14000a9ef  xor     ebp, ebp
0x14000a9f1  jmp     short loc_14000AA61
0x14000a9f3  mov     r14, [r8+20h]
0x14000a9f7  xor     ebp, ebp
0x14000a9f9  cmp     eax, ecx
0x14000a9fb  setz    bpl
0x14000a9ff  test    r14, r14
0x14000aa02  jz      short loc_14000AA61
0x14000aa04  mov     rax, [r14]
0x14000aa07  test    rax, rax
0x14000aa0a  jz      short loc_14000AA52
0x14000aa0c  cmp     byte ptr [rax+1Eh], 0
0x14000aa10  jnz     short loc_14000AA3D
0x14000aa12  cmp     byte ptr [rax+1Dh], 0
0x14000aa16  jnz     short loc_14000AA3D
0x14000aa18  mov     rcx, [rax]
0x14000aa1b  mov     rdx, rax
0x14000aa1e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000aa23  test    edi, edi
0x14000aa25  jz      short loc_14000AA31
0x14000aa27  test    r13b, al
0x14000aa2a  jz      short loc_14000AA31
0x14000aa2c  mov     edi, r13d
0x14000aa2f  jmp     short loc_14000AA33
0x14000aa31  xor     edi, edi
0x14000aa33  add     r14, 8
0x14000aa37  test    edi, edi
0x14000aa39  jnz     short loc_14000AA04
0x14000aa3b  jmp     short loc_14000AA52
0x14000aa3d  test    edi, edi
0x14000aa3f  jz      short loc_14000AA50
0x14000aa41  cmp     byte ptr [rax+1Fh], 0
0x14000aa45  jz      short loc_14000AA50
0x14000aa47  mov     edi, r13d
0x14000aa4a  add     r14, 8
0x14000aa4e  jmp     short loc_14000AA04
0x14000aa50  xor     edi, edi
0x14000aa52  test    esi, esi
0x14000aa54  jz      short loc_14000AA5F
0x14000aa56  test    edi, edi
0x14000aa58  jz      short loc_14000AA5F
0x14000aa5a  mov     esi, r13d
0x14000aa5d  jmp     short loc_14000AA61
0x14000aa5f  xor     esi, esi
0x14000aa61  mov     edx, ebx
0x14000aa63  and     edx, 0FFFFFFFEh
0x14000aa66  or      edx, esi
0x14000aa68  test    ebp, ebp
0x14000aa6a  jz      short loc_14000AA74
0x14000aa6c  test    edi, edi
0x14000aa6e  jnz     short loc_14000AA74
0x14000aa70  btr     edx, 0Ah
0x14000aa74  mov     eax, ebx
0x14000aa76  mov     ecx, edx
0x14000aa78  and     eax, r13d
0x14000aa7b  and     ecx, 0FFFFFFCFh
0x14000aa7e  cmp     eax, esi
0x14000aa80  mov     eax, ebx
0x14000aa82  cmovz   ecx, edx
0x14000aa85  btr     ecx, 9
0x14000aa89  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000aa8d  lock cmpxchg [r15], ecx
0x14000aa92  jz      short loc_14000AA98
0x14000aa94  mov     ebx, eax
0x14000aa96  jmp     short loc_14000AA61
0x14000aa98  mov     rax, [rsp+48h+arg_0]
0x14000aa9d  mov     rbx, [rsp+48h+arg_8]
0x14000aaa2  mov     rbp, [rsp+48h+arg_10]
0x14000aaa7  add     rsp, 20h
0x14000aaab  pop     r15
0x14000aaad  pop     r14
0x14000aaaf  pop     r13
0x14000aab1  pop     rdi
0x14000aab2  pop     rsi
0x14000aab3  retn
```
