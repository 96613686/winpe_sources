# encode_uncompressed_block

- ea: `0x180011068`
- end: `0x18001112e`
- name: `encode_uncompressed_block`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e558`

## callees

- `0x18000ea34`
- `0x180011068`
- `0x180011134`

## pseudocode

```c
__int64 __fastcall encode_uncompressed_block(__int64 a1, unsigned int a2, int a3)
{
  __int64 i; // rcx
  unsigned int v7; // edx
  unsigned int v8; // r8d
  __int64 result; // rax
  int v10; // edi
  __int64 v11; // rdx

  output_bits(a1, (unsigned int)(*(char *)(a1 + 44) - 16), 0);
  for ( i = 0; i != 3; ++i )
  {
    v7 = *(_DWORD *)(a1 + 4 * i + 88);
    v8 = 0;
    do
    {
      result = *(_QWORD *)(a1 + 2184);
      ++v8;
      *(_BYTE *)result = v7;
      ++*(_QWORD *)(a1 + 2184);
      v7 >>= 8;
    }
    while ( v8 < 4 );
  }
  v10 = a3 & 1;
  while ( a3 )
  {
    --a3;
    v11 = a2++;
    *(_BYTE *)(*(_QWORD *)(a1 + 2184))++ = *(_BYTE *)(v11 + *(_QWORD *)a1);
    result = (unsigned int)(*(_DWORD *)(a1 + 2200) + 1);
    *(_DWORD *)(a1 + 2200) = result;
    if ( (_DWORD)result == 0x8000 )
    {
      result = perform_flush_output_callback(a1);
      *(_BYTE *)(a1 + 2224) = 0;
    }
  }
  if ( v10 )
  {
    result = *(_QWORD *)(a1 + 2184);
    *(_BYTE *)result = 0;
    ++*(_QWORD *)(a1 + 2184);
  }
  *(_BYTE *)(a1 + 44) = 32;
  *(_DWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180011068  push    rbx
0x18001106a  push    rbp
0x18001106b  push    rsi
0x18001106c  push    rdi
0x18001106d  sub     rsp, 28h
0x180011071  mov     ebp, edx
0x180011073  mov     esi, r8d
0x180011076  movsx   edx, byte ptr [rcx+2Ch]
0x18001107a  xor     r8d, r8d
0x18001107d  sub     edx, 10h
0x180011080  mov     rbx, rcx
0x180011083  call    output_bits
0x180011088  xor     ecx, ecx
0x18001108a  mov     edx, [rbx+rcx*4+58h]
0x18001108e  xor     r8d, r8d
0x180011091  mov     rax, [rbx+888h]
0x180011098  inc     r8d
0x18001109b  mov     [rax], dl
0x18001109d  inc     qword ptr [rbx+888h]
0x1800110a4  shr     edx, 8
0x1800110a7  cmp     r8d, 4
0x1800110ab  jb      short loc_180011091
0x1800110ad  inc     rcx
0x1800110b0  cmp     rcx, 3
0x1800110b4  jnz     short loc_18001108A
0x1800110b6  mov     edi, esi
0x1800110b8  and     edi, 1
0x1800110bb  jmp     short loc_1800110CC
0x1800110bd  mov     rcx, rbx
0x1800110c0  call    perform_flush_output_callback
0x1800110c5  mov     byte ptr [rbx+8B0h], 0
0x1800110cc  test    esi, esi
0x1800110ce  jz      short loc_180011103
0x1800110d0  mov     rax, [rbx]
0x1800110d3  dec     esi
0x1800110d5  mov     rcx, [rbx+888h]
0x1800110dc  mov     edx, ebp
0x1800110de  inc     ebp
0x1800110e0  mov     al, [rdx+rax]
0x1800110e3  mov     [rcx], al
0x1800110e5  inc     qword ptr [rbx+888h]
0x1800110ec  mov     eax, [rbx+898h]
0x1800110f2  inc     eax
0x1800110f4  mov     [rbx+898h], eax
0x1800110fa  cmp     eax, 8000h
0x1800110ff  jnz     short loc_1800110CC
0x180011101  jmp     short loc_1800110BD
0x180011103  test    edi, edi
0x180011105  jnz     short loc_18001111B
0x180011107  mov     byte ptr [rbx+2Ch], 20h ; ' '
0x18001110b  mov     dword ptr [rbx+28h], 0
0x180011112  add     rsp, 28h
0x180011116  pop     rdi
0x180011117  pop     rsi
0x180011118  pop     rbp
0x180011119  pop     rbx
0x18001111a  retn
0x18001111b  mov     rax, [rbx+888h]
0x180011122  mov     byte ptr [rax], 0
0x180011125  inc     qword ptr [rbx+888h]
0x18001112c  jmp     short loc_180011107
```
