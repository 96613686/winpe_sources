# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x14000f1f4`
- end: `0x14000f26d`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000ee7c`

## callees

- `0x14000f1f4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f244`
- `msvcrt!memcpy_s` at `0x14000f244`
- `ole32!CoTaskMemAlloc` at `0x14000f229`
- `ole32!CoTaskMemAlloc` at `0x14000f229`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Source, struct tagPROPVARIANT *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rax
  __int64 v6; // rbp
  void *v7; // rax

  v2 = 0;
  if ( !Source )
  {
    v2 = -2147024809;
LABEL_8:
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    return v2;
  }
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  v6 = 2 * v5 + 2;
  v7 = CoTaskMemAlloc(v6);
  a2->hVal.QuadPart = (LONGLONG)v7;
  if ( !v7 )
  {
    v2 = -2147024882;
    goto LABEL_8;
  }
  memcpy_s(v7, v6, Source, v6);
  a2->vt = 31;
  return v2;
}

```

## disassembly

```asm
0x14000f1f4  push    rbx
0x14000f1f6  push    rbp
0x14000f1f7  push    rsi
0x14000f1f8  push    rdi
0x14000f1f9  sub     rsp, 28h
0x14000f1fd  xor     ebx, ebx
0x14000f1ff  mov     rdi, rdx
0x14000f202  mov     rsi, rcx
0x14000f205  test    rcx, rcx
0x14000f208  jnz     short loc_14000F211
0x14000f20a  mov     ebx, 80070057h
0x14000f20f  jmp     short loc_14000F256
0x14000f211  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f215  inc     rax
0x14000f218  cmp     [rcx+rax*2], bx
0x14000f21c  jnz     short loc_14000F215
0x14000f21e  lea     rbp, ds:2[rax*2]
0x14000f226  mov     rcx, rbp; cb
0x14000f229  call    cs:__imp_CoTaskMemAlloc
0x14000f22f  mov     [rdi+8], rax
0x14000f233  test    rax, rax
0x14000f236  jz      short loc_14000F251
0x14000f238  mov     r9, rbp; SourceSize
0x14000f23b  mov     r8, rsi; Source
0x14000f23e  mov     rdx, rbp; DestinationSize
0x14000f241  mov     rcx, rax; Destination
0x14000f244  call    cs:__imp_memcpy_s
0x14000f24a  mov     word ptr [rdi], 1Fh
0x14000f24f  jmp     short loc_14000F262
0x14000f251  mov     ebx, 8007000Eh
0x14000f256  xorps   xmm0, xmm0
0x14000f259  xor     eax, eax
0x14000f25b  movups  xmmword ptr [rdi], xmm0
0x14000f25e  mov     [rdi+10h], rax
0x14000f262  mov     eax, ebx
0x14000f264  add     rsp, 28h
0x14000f268  pop     rdi
0x14000f269  pop     rsi
0x14000f26a  pop     rbp
0x14000f26b  pop     rbx
0x14000f26c  retn
```
