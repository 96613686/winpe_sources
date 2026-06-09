# ShouldUseCompactLayout(void)

- ea: `0x14000eaa8`
- end: `0x14000eadc`
- name: `?ShouldUseCompactLayout@@YAHXZ`
- size: `52`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000bae4`
- `0x14000c994`

## callees

- `0x14000eaa8`
- `0x14000ebe4`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x14000eac1`
- `USER32!GetSystemMetrics` at `0x14000eac1`

## pseudocode

```c
_BOOL8 ShouldUseCompactLayout(void)
{
  return (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetImpl'::`2'::impl)
      && GetSystemMetrics(1) < 500;
}

```

## disassembly

```asm
0x14000eaa8  sub     rsp, 28h
0x14000eaac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom> `wil::Feature<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::GetImpl(void)'::`2'::impl
0x14000eab3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDiskCleanupOn200Zoom>::__private_IsEnabled(void)
0x14000eab8  test    al, al
0x14000eaba  jz      short loc_14000EAD5
0x14000eabc  mov     ecx, 1; nIndex
0x14000eac1  call    cs:__imp_GetSystemMetrics
0x14000eac7  xor     ecx, ecx
0x14000eac9  cmp     eax, 1F4h
0x14000eace  setl    cl
0x14000ead1  mov     eax, ecx
0x14000ead3  jmp     short loc_14000EAD7
0x14000ead5  xor     eax, eax
0x14000ead7  add     rsp, 28h
0x14000eadb  retn
```
