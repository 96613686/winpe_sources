# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000bc04`
- end: `0x18000bcd5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedRoots_Flighting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bb18`

## callees

- `0x18000bc04`
- `0x1800157d4`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedRoots_Flighting>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, _QWORD); // rax
  int v4; // edx
  int v5; // ecx
  int v6; // eax
  int v7; // edi
  char v8; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_internalGetFeatureEnabledState;
  v4 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, _QWORD))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(51577548, 0);
  }
  *a2 = 0;
  v5 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v6 = 0;
    if ( (v4 & 0xFFFFFF3F) == 2 )
      v6 = 64;
    v5 |= v6;
  }
  *(_DWORD *)a2 = v5;
  v7 = 1;
  if ( (v5 & 0xC00) == 0xC00 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    IsEnabled = 0;
    if ( (v5 & 0x40) == 0 )
      goto LABEL_14;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v8 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_14:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v7 = 0;
  result = a2;
  *(_DWORD *)a2 = v7 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18000bc04  push    rbx
0x18000bc06  push    rbp
0x18000bc07  push    rsi
0x18000bc08  push    rdi
0x18000bc09  sub     rsp, 28h
0x18000bc0d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000bc14  mov     rbx, rdx
0x18000bc17  xor     edx, edx
0x18000bc19  test    rax, rax
0x18000bc1c  jnz     short loc_18000BC2A
0x18000bc1e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000bc25  test    rax, rax
0x18000bc28  jz      short loc_18000BC36
0x18000bc2a  mov     ecx, 31302CCh
0x18000bc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc34  mov     edx, eax
0x18000bc36  mov     r8d, edx
0x18000bc39  mov     qword ptr [rbx], 0
0x18000bc40  and     r8d, 0FFFFFF3Fh
0x18000bc47  mov     eax, edx
0x18000bc49  and     edx, 80h
0x18000bc4f  mov     ecx, r8d
0x18000bc52  and     ecx, 3
0x18000bc55  mov     ebp, 40h ; '@'
0x18000bc5a  shl     ecx, 2
0x18000bc5d  and     eax, ebp
0x18000bc5f  or      ecx, eax
0x18000bc61  shl     ecx, 2
0x18000bc64  or      ecx, edx
0x18000bc66  shl     ecx, 3
0x18000bc69  test    r8d, r8d
0x18000bc6c  jz      short loc_18000BC79
0x18000bc6e  xor     eax, eax
0x18000bc70  cmp     r8d, 2
0x18000bc74  cmovz   eax, ebp
0x18000bc77  or      ecx, eax
0x18000bc79  mov     edx, 0C00h
0x18000bc7e  mov     [rbx], ecx
0x18000bc80  mov     eax, ecx
0x18000bc82  mov     edi, 1
0x18000bc87  and     eax, edx
0x18000bc89  cmp     eax, edx
0x18000bc8b  jnz     short loc_18000BC92
0x18000bc8d  mov     sil, dil
0x18000bc90  jmp     short loc_18000BC9C
0x18000bc92  xor     sil, sil
0x18000bc95  xor     al, al
0x18000bc97  test    bpl, cl
0x18000bc9a  jz      short loc_18000BCB5
0x18000bc9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000bca3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000bca8  test    sil, sil
0x18000bcab  jz      short loc_18000BCB5
0x18000bcad  test    al, al
0x18000bcaf  jnz     short loc_18000BCB5
0x18000bcb1  btr     dword ptr [rbx], 0Ah
0x18000bcb5  mov     ecx, [rbx]
0x18000bcb7  test    bpl, cl
0x18000bcba  jz      short loc_18000BCC0
0x18000bcbc  test    al, al
0x18000bcbe  jnz     short loc_18000BCC2
0x18000bcc0  xor     edi, edi
0x18000bcc2  and     ecx, 0FFFFFFFEh
0x18000bcc5  mov     rax, rbx
0x18000bcc8  or      ecx, edi
0x18000bcca  mov     [rbx], ecx
0x18000bccc  add     rsp, 28h
0x18000bcd0  pop     rdi
0x18000bcd1  pop     rsi
0x18000bcd2  pop     rbp
0x18000bcd3  pop     rbx
0x18000bcd4  retn
```
