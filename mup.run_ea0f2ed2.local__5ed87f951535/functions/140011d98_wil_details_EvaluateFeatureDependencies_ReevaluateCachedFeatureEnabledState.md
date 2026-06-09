# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140011d98`
- end: `0x140011e4e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
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
0x140011d98  push    rbx
0x140011d9a  push    rbp
0x140011d9b  push    rsi
0x140011d9c  push    rdi
0x140011d9d  sub     rsp, 28h
0x140011da1  mov     edi, edx
0x140011da3  mov     [rsp+48h+arg_0], 0
0x140011dac  shr     edi, 6
0x140011daf  mov     rbx, rdx
0x140011db2  mov     rbp, rcx
0x140011db5  and     edi, 1
0x140011db8  jz      short loc_140011E14
0x140011dba  mov     rsi, [r8+20h]
0x140011dbe  test    rsi, rsi
0x140011dc1  jz      short loc_140011E14
0x140011dc3  mov     rax, [rsi]
0x140011dc6  test    rax, rax
0x140011dc9  jz      short loc_140011E14
0x140011dcb  cmp     byte ptr [rax+1Eh], 0
0x140011dcf  jnz     short loc_140011DFD
0x140011dd1  cmp     byte ptr [rax+1Dh], 0
0x140011dd5  jnz     short loc_140011DFD
0x140011dd7  mov     rcx, [rax]
0x140011dda  mov     rdx, rax
0x140011ddd  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140011de2  test    edi, edi
0x140011de4  jz      short loc_140011DF1
0x140011de6  test    al, 1
0x140011de8  jz      short loc_140011DF1
0x140011dea  mov     edi, 1
0x140011def  jmp     short loc_140011DF3
0x140011df1  xor     edi, edi
0x140011df3  add     rsi, 8
0x140011df7  test    edi, edi
0x140011df9  jnz     short loc_140011DC3
0x140011dfb  jmp     short loc_140011E14
0x140011dfd  test    edi, edi
0x140011dff  jz      short loc_140011E12
0x140011e01  cmp     byte ptr [rax+1Fh], 0
0x140011e05  jz      short loc_140011E12
0x140011e07  mov     edi, 1
0x140011e0c  add     rsi, 8
0x140011e10  jmp     short loc_140011DC3
0x140011e12  xor     edi, edi
0x140011e14  mov     ecx, ebx
0x140011e16  mov     eax, ebx
0x140011e18  and     ecx, 0FFFFFFFEh
0x140011e1b  and     eax, 1
0x140011e1e  or      ecx, edi
0x140011e20  mov     edx, ecx
0x140011e22  and     edx, 0FFFFFFCFh
0x140011e25  cmp     eax, edi
0x140011e27  mov     eax, ebx
0x140011e29  cmovz   edx, ecx
0x140011e2c  btr     edx, 9
0x140011e30  mov     dword ptr [rsp+48h+arg_0], edx
0x140011e34  lock cmpxchg [rbp+0], edx
0x140011e39  jz      short loc_140011E3F
0x140011e3b  mov     ebx, eax
0x140011e3d  jmp     short loc_140011E14
0x140011e3f  mov     rax, [rsp+48h+arg_0]
0x140011e44  add     rsp, 28h
0x140011e48  pop     rdi
0x140011e49  pop     rsi
0x140011e4a  pop     rbp
0x140011e4b  pop     rbx
0x140011e4c  retn
```
