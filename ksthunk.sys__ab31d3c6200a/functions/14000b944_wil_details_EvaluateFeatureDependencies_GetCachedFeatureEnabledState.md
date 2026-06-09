# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000b944`
- end: `0x14000ba15`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `209`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b858`
- `0x14000b944`

## callees

- `0x14000b944`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // esi
  int v4; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  unsigned __int32 v7; // eax
  unsigned int v8; // r8d
  __int64 v10; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v10 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v10) = 0;
    v4 = (v2 >> 6) & 1;
    if ( v4 )
    {
      v5 = *(__int64 **)(a2 + 32);
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = *v5;
          if ( !*v5 )
            break;
          if ( *(_BYTE *)(v6 + 30) || *(_BYTE *)(v6 + 29) )
          {
            if ( !*(_BYTE *)(v6 + 31) )
            {
              v4 = 0;
              goto LABEL_12;
            }
            v4 = 1;
            ++v5;
          }
          else
          {
            v4 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_QWORD *)v6, *v5++) & 1) != 0;
            if ( !v4 )
              goto LABEL_12;
          }
        }
      }
    }
    do
    {
LABEL_12:
      v7 = v2;
      v8 = v4 & 0xFFFFFFCF | v2 & 0xFFFFFFCE;
      if ( (v2 & 1) == v4 )
        v8 = v4 | v2 & 0xFFFFFFFE;
      LODWORD(v10) = v8 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v2);
    }
    while ( v7 != v2 );
  }
  return v10;
}

```

## disassembly

```asm
0x14000b944  push    rbx
0x14000b946  push    rsi
0x14000b947  push    rdi
0x14000b948  push    r14
0x14000b94a  sub     rsp, 28h
0x14000b94e  mov     esi, [rcx]
0x14000b950  mov     r14, rcx
0x14000b953  mov     [rsp+48h+arg_0], 0
0x14000b95c  mov     dword ptr [rsp+48h+arg_0], esi
0x14000b960  bt      esi, 9
0x14000b964  jnb     loc_14000BA05
0x14000b96a  mov     ebx, esi
0x14000b96c  mov     [rsp+48h+arg_0], 0
0x14000b975  shr     ebx, 6
0x14000b978  and     ebx, 1
0x14000b97b  jz      short loc_14000B9D7
0x14000b97d  mov     rdi, [rdx+20h]
0x14000b981  test    rdi, rdi
0x14000b984  jz      short loc_14000B9D7
0x14000b986  mov     rax, [rdi]
0x14000b989  test    rax, rax
0x14000b98c  jz      short loc_14000B9D7
0x14000b98e  cmp     byte ptr [rax+1Eh], 0
0x14000b992  jnz     short loc_14000B9C0
0x14000b994  cmp     byte ptr [rax+1Dh], 0
0x14000b998  jnz     short loc_14000B9C0
0x14000b99a  mov     rcx, [rax]
0x14000b99d  mov     rdx, rax
0x14000b9a0  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000b9a5  test    ebx, ebx
0x14000b9a7  jz      short loc_14000B9B4
0x14000b9a9  test    al, 1
0x14000b9ab  jz      short loc_14000B9B4
0x14000b9ad  mov     ebx, 1
0x14000b9b2  jmp     short loc_14000B9B6
0x14000b9b4  xor     ebx, ebx
0x14000b9b6  add     rdi, 8
0x14000b9ba  test    ebx, ebx
0x14000b9bc  jnz     short loc_14000B986
0x14000b9be  jmp     short loc_14000B9D7
0x14000b9c0  test    ebx, ebx
0x14000b9c2  jz      short loc_14000B9D5
0x14000b9c4  cmp     byte ptr [rax+1Fh], 0
0x14000b9c8  jz      short loc_14000B9D5
0x14000b9ca  mov     ebx, 1
0x14000b9cf  add     rdi, 8
0x14000b9d3  jmp     short loc_14000B986
0x14000b9d5  xor     ebx, ebx
0x14000b9d7  mov     edx, esi
0x14000b9d9  mov     ecx, esi
0x14000b9db  and     edx, 0FFFFFFFEh
0x14000b9de  and     ecx, 1
0x14000b9e1  or      edx, ebx
0x14000b9e3  mov     eax, esi
0x14000b9e5  mov     r8d, edx
0x14000b9e8  and     r8d, 0FFFFFFCFh
0x14000b9ec  cmp     ecx, ebx
0x14000b9ee  cmovz   r8d, edx
0x14000b9f2  btr     r8d, 9
0x14000b9f7  mov     dword ptr [rsp+48h+arg_0], r8d
0x14000b9fc  lock cmpxchg [r14], r8d
0x14000ba01  mov     esi, eax
0x14000ba03  jnz     short loc_14000B9D7
0x14000ba05  mov     rax, [rsp+48h+arg_0]
0x14000ba0a  add     rsp, 28h
0x14000ba0e  pop     r14
0x14000ba10  pop     rdi
0x14000ba11  pop     rsi
0x14000ba12  pop     rbx
0x14000ba13  retn
```
