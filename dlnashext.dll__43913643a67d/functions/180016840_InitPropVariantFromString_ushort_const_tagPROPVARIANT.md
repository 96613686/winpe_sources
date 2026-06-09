# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x180016840`
- end: `0x1800168b8`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, struct tagPROPVARIANT *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018864`
- `0x180018934`
- `0x180027260`
- `0x18002d49c`
- `0x18002f7dc`

## callees

- `0x18000a3d0`
- `0x180016840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016875`

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
0x180016840  push    rbx
0x180016842  push    rbp
0x180016843  push    rsi
0x180016844  push    rdi
0x180016845  sub     rsp, 28h
0x180016849  xor     ebx, ebx
0x18001684b  mov     rdi, rdx
0x18001684e  mov     rsi, rcx
0x180016851  test    rcx, rcx
0x180016854  jnz     short loc_18001685D
0x180016856  mov     ebx, 80070057h
0x18001685b  jmp     short loc_1800168A1
0x18001685d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016861  inc     rax
0x180016864  cmp     [rcx+rax*2], bx
0x180016868  jnz     short loc_180016861
0x18001686a  lea     rbp, ds:2[rax*2]
0x180016872  mov     rcx, rbp; cb
0x180016875  call    cs:__imp_CoTaskMemAlloc
0x18001687b  mov     [rdi+8], rax
0x18001687f  test    rax, rax
0x180016882  jz      short loc_18001689C
0x180016884  mov     r9, rbp; SourceSize
0x180016887  mov     r8, rsi; Source
0x18001688a  mov     rdx, rbp; DestinationSize
0x18001688d  mov     rcx, rax; Destination
0x180016890  call    memcpy_s
0x180016895  mov     word ptr [rdi], 1Fh
0x18001689a  jmp     short loc_1800168AD
0x18001689c  mov     ebx, 8007000Eh
0x1800168a1  xorps   xmm0, xmm0
0x1800168a4  xor     eax, eax
0x1800168a6  movups  xmmword ptr [rdi], xmm0
0x1800168a9  mov     [rdi+10h], rax
0x1800168ad  mov     eax, ebx
0x1800168af  add     rsp, 28h
0x1800168b3  pop     rdi
0x1800168b4  pop     rsi
0x1800168b5  pop     rbp
0x1800168b6  pop     rbx
0x1800168b7  retn
```
