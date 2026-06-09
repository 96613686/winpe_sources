# fsBCryptOpenAlgorithmProvider(void * *,ushort const *,ushort const *,ulong)

- ea: `0x180032464`
- end: `0x1800324c0`
- name: `?fsBCryptOpenAlgorithmProvider@@YAJPEAPEAXPEBG1K@Z`
- size: `92`
- prototype: `__int64 __fastcall(void **, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180031c48`

## callees

- `0x180032464`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180032488`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180032488`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18003249d`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800324ad`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18003249d`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x1800324ad`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180032477`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180032477`

## pseudocode

```c
__int64 __fastcall fsBCryptOpenAlgorithmProvider(void **a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v4; // ebx

  v4 = BCryptOpenAlgorithmProvider(a1, a2, 0, 0);
  if ( v4 || DbgIsSSActive(0x404u) )
  {
    CSPrintErrorLineFileData(a2, 0x4040C25u, v4);
    CSPrintErrorLineFileData(0, 0x4050C25u, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x180032464  mov     [rsp+arg_0], rbx
0x180032469  push    rdi
0x18003246a  sub     rsp, 20h
0x18003246e  xor     r9d, r9d; dwFlags
0x180032471  xor     r8d, r8d; pszImplementation
0x180032474  mov     rdi, rdx
0x180032477  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003247d  mov     ebx, eax
0x18003247f  test    eax, eax
0x180032481  jnz     short loc_180032492
0x180032483  mov     ecx, 404h
0x180032488  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x18003248e  test    eax, eax
0x180032490  jz      short loc_1800324B3
0x180032492  mov     r8d, ebx
0x180032495  mov     edx, 4040C25h
0x18003249a  mov     rcx, rdi
0x18003249d  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x1800324a3  xor     r8d, r8d
0x1800324a6  mov     edx, 4050C25h
0x1800324ab  xor     ecx, ecx
0x1800324ad  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x1800324b3  mov     eax, ebx
0x1800324b5  mov     rbx, [rsp+28h+arg_0]
0x1800324ba  add     rsp, 20h
0x1800324be  pop     rdi
0x1800324bf  retn
```
