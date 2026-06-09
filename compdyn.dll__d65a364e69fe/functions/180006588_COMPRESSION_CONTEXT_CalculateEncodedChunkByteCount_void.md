# COMPRESSION_CONTEXT::CalculateEncodedChunkByteCount(void)

- ea: `0x180006588`
- end: `0x180006643`
- name: `?CalculateEncodedChunkByteCount@COMPRESSION_CONTEXT@@QEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800068b0`

## callees

- `0x180002ef0`
- `0x180006588`
- `0x18000674c`

## import_xrefs

- `msvcrt!isxdigit` at `0x1800065ad`
- `msvcrt!isxdigit` at `0x1800065ad`

## pseudocode

```c
signed int __fastcall COMPRESSION_CONTEXT::CalculateEncodedChunkByteCount(COMPRESSION_CONTEXT *this)
{
  unsigned __int8 v1; // di
  int v3; // eax
  int v4; // ecx
  int v5; // edx
  signed int result; // eax
  int v7; // eax
  signed int v8; // eax
  int v9; // ecx

  v1 = 0;
  if ( *((_DWORD *)this + 24) < *((_DWORD *)this + 22) )
  {
    while ( 1 )
    {
      v1 = *COMPRESSION_CONTEXT::QueryBytePtr(this);
      if ( !isxdigit(v1) )
        break;
      v3 = (char)v1;
      v4 = 16 * *((_DWORD *)this + 5);
      if ( (unsigned __int8)(v1 - 48) > 9u )
      {
        v3 = (char)v1 | 0x20;
        v5 = v4 - 87;
      }
      else
      {
        v5 = v4 - 48;
      }
      *((_DWORD *)this + 5) = v3 + v5;
      result = COMPRESSION_CONTEXT::IncrementPointerInULChunk(this, 1u);
      if ( result < 0 )
        return result;
      if ( *((_DWORD *)this + 24) >= *((_DWORD *)this + 22) )
        return 0;
    }
  }
  if ( *((_DWORD *)this + 24) >= *((_DWORD *)this + 22) )
    return 0;
  if ( v1 == 59 )
  {
    v7 = 1;
  }
  else
  {
    if ( v1 != 13 )
      return -2147024883;
    v7 = 2;
  }
  *((_DWORD *)this + 6) = v7;
  v8 = COMPRESSION_CONTEXT::IncrementPointerInULChunk(this, 1u);
  v9 = 0;
  if ( v8 < 0 )
    return v8;
  return v9;
}

```

## disassembly

```asm
0x180006588  mov     [rsp+arg_0], rbx
0x18000658d  push    rdi
0x18000658e  sub     rsp, 20h
0x180006592  mov     eax, [rcx+58h]
0x180006595  xor     dil, dil
0x180006598  mov     rbx, rcx
0x18000659b  cmp     [rcx+60h], eax
0x18000659e  jnb     short loc_180006601
0x1800065a0  mov     rcx, rbx; this
0x1800065a3  call    ?QueryBytePtr@COMPRESSION_CONTEXT@@QEAAPEAEXZ; COMPRESSION_CONTEXT::QueryBytePtr(void)
0x1800065a8  movzx   edi, byte ptr [rax]
0x1800065ab  mov     ecx, edi; C
0x1800065ad  call    cs:__imp_isxdigit
0x1800065b3  test    eax, eax
0x1800065b5  jz      short loc_180006601
0x1800065b7  mov     ecx, [rbx+14h]
0x1800065ba  movsx   eax, dil
0x1800065be  sub     dil, 30h ; '0'
0x1800065c2  shl     ecx, 4
0x1800065c5  cmp     dil, 9
0x1800065c9  ja      short loc_1800065D0
0x1800065cb  lea     edx, [rcx-30h]
0x1800065ce  jmp     short loc_1800065D6
0x1800065d0  or      eax, 20h
0x1800065d3  lea     edx, [rcx-57h]
0x1800065d6  add     edx, eax
0x1800065d8  mov     rcx, rbx; this
0x1800065db  mov     [rbx+14h], edx
0x1800065de  mov     edx, 1; unsigned int
0x1800065e3  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x1800065e8  test    eax, eax
0x1800065ea  js      short loc_1800065F6
0x1800065ec  mov     eax, [rbx+58h]
0x1800065ef  cmp     [rbx+60h], eax
0x1800065f2  jb      short loc_1800065A0
0x1800065f4  xor     eax, eax
0x1800065f6  mov     rbx, [rsp+28h+arg_0]
0x1800065fb  add     rsp, 20h
0x1800065ff  pop     rdi
0x180006600  retn
0x180006601  mov     eax, [rbx+58h]
0x180006604  cmp     [rbx+60h], eax
0x180006607  jnb     short loc_1800065F4
0x180006609  cmp     dil, 3Bh ; ';'
0x18000660d  jnz     short loc_180006616
0x18000660f  mov     eax, 1
0x180006614  jmp     short loc_180006621
0x180006616  cmp     dil, 0Dh
0x18000661a  jnz     short loc_18000663C
0x18000661c  mov     eax, 2
0x180006621  mov     edx, 1; unsigned int
0x180006626  mov     [rbx+18h], eax
0x180006629  mov     rcx, rbx; this
0x18000662c  call    ?IncrementPointerInULChunk@COMPRESSION_CONTEXT@@QEAAJK@Z; COMPRESSION_CONTEXT::IncrementPointerInULChunk(ulong)
0x180006631  xor     ecx, ecx
0x180006633  test    eax, eax
0x180006635  cmovs   ecx, eax
0x180006638  mov     eax, ecx
0x18000663a  jmp     short loc_1800065F6
0x18000663c  mov     eax, 8007000Dh
0x180006641  jmp     short loc_1800065F6
```
