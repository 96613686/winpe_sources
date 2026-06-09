# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x180018c00`
- end: `0x180018d00`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d430`

## callees

- `0x180018c00`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 result; // rax
  int v4; // eax
  __int64 v5; // rcx

  if ( *a2 == -1873145888
    && a2[1] == *(_DWORD *)&GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data2
    && a2[2] == *(_DWORD *)GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data4
    && a2[3] == *(_DWORD *)&GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data4[4]
    || (a1 += 8, *a2 == 56)
    && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4]
    || (a1 += 8, *a2 == -1873145873)
    && a2[1] == *(_DWORD *)&GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data2
    && a2[2] == *(_DWORD *)GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data4
    && a2[3] == *(_DWORD *)&GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data4[4]
    || (v4 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4], a1 += 8, *a2 == 3)
    && a2[1] == *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    return 0;
  }
  v5 = a1 + 8;
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      return 2147500034LL;
    }
    v4 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
  }
  else if ( *a2 != 3
         || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
         || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
  {
    return 2147500034LL;
  }
  if ( a2[3] == v4 )
  {
    result = 0;
    *a3 = v5;
    return result;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180018c00  cmp     dword ptr [rdx], 905A0FE0h
0x180018c06  jnz     short loc_180018C29
0x180018c08  mov     eax, dword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data2
0x180018c0e  cmp     [rdx+4], eax
0x180018c11  jnz     short loc_180018C29
0x180018c13  mov     eax, dword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data4
0x180018c19  cmp     [rdx+8], eax
0x180018c1c  jnz     short loc_180018C29
0x180018c1e  mov     eax, dword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data4+4
0x180018c24  cmp     [rdx+0Ch], eax
0x180018c27  jz      short loc_180018C53
0x180018c29  add     rcx, 8
0x180018c2d  cmp     dword ptr [rdx], 38h ; '8'
0x180018c30  jnz     short loc_180018C59
0x180018c32  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x180018c38  cmp     [rdx+4], eax
0x180018c3b  jnz     short loc_180018C59
0x180018c3d  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x180018c43  cmp     [rdx+8], eax
0x180018c46  jnz     short loc_180018C59
0x180018c48  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x180018c4e  cmp     [rdx+0Ch], eax
0x180018c51  jnz     short loc_180018C59
0x180018c53  mov     [r8], rcx
0x180018c56  xor     eax, eax
0x180018c58  retn
0x180018c59  add     rcx, 8
0x180018c5d  cmp     dword ptr [rdx], 905A0FEFh
0x180018c63  jnz     short loc_180018C86
0x180018c65  mov     eax, dword ptr cs:_GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data2
0x180018c6b  cmp     [rdx+4], eax
0x180018c6e  jnz     short loc_180018C86
0x180018c70  mov     eax, dword ptr cs:_GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data4
0x180018c76  cmp     [rdx+8], eax
0x180018c79  jnz     short loc_180018C86
0x180018c7b  mov     eax, dword ptr cs:_GUID_905a0fef_bc53_11df_8c49_001e4fc686da.Data4+4
0x180018c81  cmp     [rdx+0Ch], eax
0x180018c84  jz      short loc_180018C53
0x180018c86  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180018c8c  add     rcx, 8
0x180018c90  cmp     dword ptr [rdx], 3
0x180018c93  mov     r9d, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180018c9a  mov     r10d, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180018ca1  jnz     short loc_180018CB4
0x180018ca3  cmp     [rdx+4], r10d
0x180018ca7  jnz     short loc_180018CB4
0x180018ca9  cmp     [rdx+8], r9d
0x180018cad  jnz     short loc_180018CB4
0x180018caf  cmp     [rdx+0Ch], eax
0x180018cb2  jz      short loc_180018C53
0x180018cb4  add     rcx, 8
0x180018cb8  cmp     dword ptr [rdx], 94EA2B94h
0x180018cbe  jnz     short loc_180018CDE
0x180018cc0  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180018cc6  cmp     [rdx+4], eax
0x180018cc9  jnz     short loc_180018CFA
0x180018ccb  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180018cd1  cmp     [rdx+8], eax
0x180018cd4  jnz     short loc_180018CFA
0x180018cd6  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180018cdc  jmp     short loc_180018CEF
0x180018cde  cmp     dword ptr [rdx], 3
0x180018ce1  jnz     short loc_180018CFA
0x180018ce3  cmp     [rdx+4], r10d
0x180018ce7  jnz     short loc_180018CFA
0x180018ce9  cmp     [rdx+8], r9d
0x180018ced  jnz     short loc_180018CFA
0x180018cef  cmp     [rdx+0Ch], eax
0x180018cf2  jnz     short loc_180018CFA
0x180018cf4  xor     eax, eax
0x180018cf6  mov     [r8], rcx
0x180018cf9  retn
0x180018cfa  mov     eax, 80004002h
0x180018cff  retn
```
