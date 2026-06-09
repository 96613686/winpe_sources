# DxgAppCompat::SetAppCompatStringPointerImpl(unsigned __int64,char const *)

- ea: `0x180010fb4`
- end: `0x180010feb`
- name: `?SetAppCompatStringPointerImpl@DxgAppCompat@@YAX_KPEBD@Z`
- size: `55`
- prototype: `void __fastcall(DxgAppCompat *__hidden this, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000f034`

## pseudocode

```c
void __fastcall DxgAppCompat::SetAppCompatStringPointerImpl(DxgAppCompat *this, char *a2, const char *a3)
{
  char **v3; // rax

  DxgAppCompat::g_ShimmedAppCompatStringBufferLength = (unsigned __int64)this;
  v3 = &DxgAppCompat::g_CompatStringCache;
  DxgAppCompat::g_ShimmedAppCompatString = a2;
  qword_18001E890 = 0;
  if ( (unsigned __int64)qword_18001E898 > 0xF )
    v3 = (char **)DxgAppCompat::g_CompatStringCache;
  DxgAppCompat::g_AttemptReadString = 0;
  *(_BYTE *)v3 = 0;
}

```

## disassembly

```asm
0x180010fb4  mov     cs:?g_ShimmedAppCompatStringBufferLength@DxgAppCompat@@3_KA, rcx; unsigned __int64 DxgAppCompat::g_ShimmedAppCompatStringBufferLength
0x180010fbb  lea     rax, ?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010fc2  xor     ecx, ecx
0x180010fc4  mov     cs:?g_ShimmedAppCompatString@DxgAppCompat@@3PEBDEB, rdx; char const * const DxgAppCompat::g_ShimmedAppCompatString
0x180010fcb  cmp     cs:qword_18001E898, 0Fh
0x180010fd3  mov     cs:qword_18001E890, rcx
0x180010fda  cmova   rax, cs:?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010fe2  mov     cs:?g_AttemptReadString@DxgAppCompat@@3HA, ecx; int DxgAppCompat::g_AttemptReadString
0x180010fe8  mov     [rax], cl
0x180010fea  retn
```
