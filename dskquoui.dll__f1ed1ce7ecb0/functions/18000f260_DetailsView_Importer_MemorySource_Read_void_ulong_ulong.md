# DetailsView::Importer::MemorySource::Read(void *,ulong,ulong *)

- ea: `0x18000f260`
- end: `0x18000f2ab`
- name: `?Read@MemorySource@Importer@DetailsView@@UEAAJPEAXKPEAK@Z`
- size: `75`
- prototype: `int(DetailsView::Importer::MemorySource *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f260`
- `0x18001ce4c`

## pseudocode

```c
__int64 __fastcall DetailsView::Importer::MemorySource::Read(
        const void **this,
        void *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v6; // rdi
  __int64 result; // rax

  v6 = a3;
  result = 2147500037LL;
  if ( *((_DWORD *)this + 4) >= a3 )
  {
    memcpy_0(a2, this[1], a3);
    this[1] = (char *)this[1] + v6;
    *((_DWORD *)this + 4) -= v6;
    if ( a4 )
      *a4 = v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f260  push    rbx
0x18000f262  push    rsi
0x18000f263  push    rdi
0x18000f264  push    r14
0x18000f266  sub     rsp, 28h
0x18000f26a  mov     r14, r9
0x18000f26d  mov     r9, rdx
0x18000f270  mov     rsi, rcx
0x18000f273  mov     edi, r8d
0x18000f276  mov     eax, 80004005h
0x18000f27b  cmp     [rcx+10h], r8d
0x18000f27f  jb      short loc_18000F2A1
0x18000f281  mov     rdx, [rcx+8]; Src
0x18000f285  mov     r8d, edi; Size
0x18000f288  mov     rcx, r9; void *
0x18000f28b  call    memcpy_0
0x18000f290  add     [rsi+8], rdi
0x18000f294  sub     [rsi+10h], edi
0x18000f297  test    r14, r14
0x18000f29a  jz      short loc_18000F29F
0x18000f29c  mov     [r14], edi
0x18000f29f  xor     eax, eax
0x18000f2a1  add     rsp, 28h
0x18000f2a5  pop     r14
0x18000f2a7  pop     rdi
0x18000f2a8  pop     rsi
0x18000f2a9  pop     rbx
0x18000f2aa  retn
```
