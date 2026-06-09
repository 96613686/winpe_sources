# DxgAppCompat::GetAppCompatStringPointerImpl(unsigned __int64 *,char const * *)

- ea: `0x1800071a0`
- end: `0x1800071b5`
- name: `?GetAppCompatStringPointerImpl@DxgAppCompat@@YAXPEA_KPEAPEBD@Z`
- size: `21`
- prototype: `void __fastcall(DxgAppCompat *__hidden this, unsigned __int64 *, const char **)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005e54`

## pseudocode

```c
void __fastcall DxgAppCompat::GetAppCompatStringPointerImpl(DxgAppCompat *this, unsigned __int64 *a2, const char **a3)
{
  *(_QWORD *)this = DxgAppCompat::g_ShimmedAppCompatStringBufferLength;
  *a2 = (unsigned __int64)DxgAppCompat::g_ShimmedAppCompatString;
}

```

## disassembly

```asm
0x1800071a0  mov     rax, cs:?g_ShimmedAppCompatStringBufferLength@DxgAppCompat@@3_KA; unsigned __int64 DxgAppCompat::g_ShimmedAppCompatStringBufferLength
0x1800071a7  mov     [rcx], rax
0x1800071aa  mov     rax, cs:?g_ShimmedAppCompatString@DxgAppCompat@@3PEBDEB; char const * const DxgAppCompat::g_ShimmedAppCompatString
0x1800071b1  mov     [rdx], rax
0x1800071b4  retn
```
