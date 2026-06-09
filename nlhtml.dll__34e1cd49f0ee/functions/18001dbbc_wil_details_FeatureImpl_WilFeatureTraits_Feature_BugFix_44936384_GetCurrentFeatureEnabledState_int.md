# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001dbbc`
- end: `0x18001dc7b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d09c`

## callees

- `0x18001beec`
- `0x18001dbbc`
- `0x18001f004`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2ADACC0, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18001dbbc  push    rbx
0x18001dbbe  push    rbp
0x18001dbbf  push    rsi
0x18001dbc0  push    rdi
0x18001dbc1  sub     rsp, 28h
0x18001dbc5  mov     ecx, 2ADACC0h; this
0x18001dbca  mov     rbx, rdx
0x18001dbcd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001dbd2  mov     edx, eax
0x18001dbd4  mov     qword ptr [rbx], 0
0x18001dbdb  and     edx, 0FFFFFF3Fh
0x18001dbe1  mov     ecx, eax
0x18001dbe3  and     eax, 80h
0x18001dbe8  mov     r8d, edx
0x18001dbeb  and     r8d, 3
0x18001dbef  mov     ebp, 40h ; '@'
0x18001dbf4  shl     r8d, 2
0x18001dbf8  and     ecx, ebp
0x18001dbfa  or      r8d, ecx
0x18001dbfd  shl     r8d, 2
0x18001dc01  or      r8d, eax
0x18001dc04  shl     r8d, 3
0x18001dc08  test    edx, edx
0x18001dc0a  jnz     short loc_18001DC10
0x18001dc0c  mov     eax, ebp
0x18001dc0e  jmp     short loc_18001DC18
0x18001dc10  xor     eax, eax
0x18001dc12  cmp     edx, 2
0x18001dc15  cmovz   eax, ebp
0x18001dc18  or      r8d, eax
0x18001dc1b  mov     edi, 1
0x18001dc20  mov     [rbx], r8d
0x18001dc23  bt      r8d, 0Ah
0x18001dc28  jnb     short loc_18001DC38
0x18001dc2a  cmp     r8d, 800h
0x18001dc31  jb      short loc_18001DC38
0x18001dc33  mov     sil, dil
0x18001dc36  jmp     short loc_18001DC42
0x18001dc38  xor     sil, sil
0x18001dc3b  xor     al, al
0x18001dc3d  test    bpl, r8b
0x18001dc40  jz      short loc_18001DC5B
0x18001dc42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18001dc49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18001dc4e  test    sil, sil
0x18001dc51  jz      short loc_18001DC5B
0x18001dc53  test    al, al
0x18001dc55  jnz     short loc_18001DC5B
0x18001dc57  btr     dword ptr [rbx], 0Ah
0x18001dc5b  mov     ecx, [rbx]
0x18001dc5d  test    bpl, cl
0x18001dc60  jz      short loc_18001DC66
0x18001dc62  test    al, al
0x18001dc64  jnz     short loc_18001DC68
0x18001dc66  xor     edi, edi
0x18001dc68  and     ecx, 0FFFFFFFEh
0x18001dc6b  mov     rax, rbx
0x18001dc6e  or      ecx, edi
0x18001dc70  mov     [rbx], ecx
0x18001dc72  add     rsp, 28h
0x18001dc76  pop     rdi
0x18001dc77  pop     rsi
0x18001dc78  pop     rbp
0x18001dc79  pop     rbx
0x18001dc7a  retn
```
