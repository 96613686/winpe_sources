# COMPRESSION_CONTEXT::DeleteEncodedChunkExtension(void)

- ea: `0x18000664c`
- end: `0x1800066b1`
- name: `?DeleteEncodedChunkExtension@COMPRESSION_CONTEXT@@QEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800068b0`

## callees

- `0x180002ef0`
- `0x18000664c`
- `0x18000674c`

## pseudocode

```c
signed int __fastcall COMPRESSION_CONTEXT::DeleteEncodedChunkExtension(COMPRESSION_CONTEXT *this)
{
  unsigned int v2; // edx
  COMPRESSION_CONTEXT *v3; // rcx
  unsigned int v4; // r8d
  signed int result; // eax
  signed int v6; // eax
  int v7; // ecx

  if ( *((_DWORD *)this + 24) >= *((_DWORD *)this + 22) )
    return 0;
  while ( *COMPRESSION_CONTEXT::QueryBytePtr(this) != 13 )
  {
    result = COMPRESSION_CONTEXT::IncrementPointerInULChunk(v3, 1u);
    if ( result < 0 )
      return result;
    if ( *((_DWORD *)this + 24) >= *((_DWORD *)this + 22) )
      return 0;
  }
  if ( v2 >= v4 )
    return 0;
  *((_DWORD *)this + 6) = 2;
  v6 = COMPRESSION_CONTEXT::IncrementPointerInULChunk(v3, 1u);
  v7 = 0;
  if ( v6 < 0 )
    return v6;
  return v7;
}

```

## disassembly

```asm
0x18000664c  push    rbx
0x18000664e  sub     rsp, 20h
0x180006652  mov     edx, [rcx+60h]
0x180006655  mov     rbx, rcx
0x180006658  mov     r8d, [rcx+58h]
0x18000665c  cmp     edx, r8d
0x18000665f  jnb     short loc_180006688
0x180006661  mov     rcx, rbx; this
0x180006664  call    ?QueryBytePtr@COMPRESSION_CONTEXT@@QEAAPEAEXZ; COMPRESSION_CONTEXT::QueryBytePtr(void)
0x180006669  cmp     byte ptr [rax], 0Dh
0x18000666c  jz      short loc_180006690
0x18000666e  mov     edx, 1; unsigned int
0x180006673  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x180006678  test    eax, eax
0x18000667a  js      short loc_18000668A
0x18000667c  mov     edx, [rbx+60h]
0x18000667f  mov     r8d, [rbx+58h]
0x180006683  cmp     edx, r8d
0x180006686  jb      short loc_180006661
0x180006688  xor     eax, eax
0x18000668a  add     rsp, 20h
0x18000668e  pop     rbx
0x18000668f  retn
0x180006690  cmp     edx, r8d
0x180006693  jnb     short loc_180006688
0x180006695  mov     edx, 1; unsigned int
0x18000669a  mov     dword ptr [rbx+18h], 2
0x1800066a1  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x1800066a6  xor     ecx, ecx
0x1800066a8  test    eax, eax
0x1800066aa  cmovs   ecx, eax
0x1800066ad  mov     eax, ecx
0x1800066af  jmp     short loc_18000668A
```
