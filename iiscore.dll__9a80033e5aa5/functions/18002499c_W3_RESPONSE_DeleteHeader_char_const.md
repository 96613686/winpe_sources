# W3_RESPONSE::DeleteHeader(char const *)

- ea: `0x18002499c`
- end: `0x180024a51`
- name: `?DeleteHeader@W3_RESPONSE@@QEAAJPEBD@Z`
- size: `181`
- prototype: `int(W3_RESPONSE *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fe00`

## callees

- `0x1800100f4`
- `0x18002499c`
- `0x18003438e`

## import_xrefs

- `msvcrt!_stricmp` at `0x180024a06`
- `msvcrt!_stricmp` at `0x180024a06`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::DeleteHeader(W3_RESPONSE *this, const char *a2)
{
  unsigned int Index; // eax
  __int64 v6; // rdi

  if ( !a2 )
    return 2147942487LL;
  ++*((_DWORD *)this + 156);
  Index = RESPONSE_HEADER_HASH::GetIndex(a2);
  if ( Index > 0x1D )
  {
    v6 = 0;
    while ( (unsigned int)v6 < *((unsigned __int16 *)this + 40) )
    {
      if ( !_stricmp(*(const char **)(*((_QWORD *)this + 11) + 24 * v6 + 8), a2) )
      {
        memmove_0(
          (void *)(*((_QWORD *)this + 11) + 24 * v6),
          (const void *)(*((_QWORD *)this + 11) + 24 * v6 + 24),
          24LL * (*((unsigned __int16 *)this + 40) - (unsigned int)v6 - 1));
        --*((_WORD *)this + 40);
      }
      else
      {
        v6 = (unsigned int)(v6 + 1);
      }
    }
  }
  else
  {
    *((_QWORD *)this + 2 * Index + 15) = 0;
    *((_WORD *)this + 8 * Index + 56) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002499c  push    rbx
0x18002499e  push    rbp
0x18002499f  push    rsi
0x1800249a0  push    rdi
0x1800249a1  sub     rsp, 28h
0x1800249a5  mov     rsi, rdx
0x1800249a8  mov     rbx, rcx
0x1800249ab  test    rdx, rdx
0x1800249ae  jnz     short loc_1800249BA
0x1800249b0  mov     eax, 80070057h
0x1800249b5  jmp     loc_180024A48
0x1800249ba  inc     dword ptr [rcx+270h]
0x1800249c0  mov     rcx, rsi; char *
0x1800249c3  call    ?GetIndex@RESPONSE_HEADER_HASH@@SAKPEBD@Z; RESPONSE_HEADER_HASH::GetIndex(char const *)
0x1800249c8  cmp     eax, 1Dh
0x1800249cb  ja      short loc_1800249EC
0x1800249cd  mov     ecx, eax
0x1800249cf  mov     eax, eax
0x1800249d1  add     rcx, 7
0x1800249d5  add     rax, rax
0x1800249d8  add     rcx, rcx
0x1800249db  mov     qword ptr [rbx+rax*8+78h], 0
0x1800249e4  xor     eax, eax
0x1800249e6  mov     [rbx+rcx*8], ax
0x1800249ea  jmp     short loc_180024A46
0x1800249ec  xor     edi, edi
0x1800249ee  xor     eax, eax
0x1800249f0  cmp     ax, [rbx+50h]
0x1800249f4  jnb     short loc_180024A46
0x1800249f6  mov     rcx, [rbx+58h]
0x1800249fa  lea     rbp, [rdi+rdi*2]
0x1800249fe  mov     rdx, rsi; String2
0x180024a01  mov     rcx, [rcx+rbp*8+8]; String1
0x180024a06  call    cs:__imp__stricmp
0x180024a0c  test    eax, eax
0x180024a0e  jnz     short loc_180024A3C
0x180024a10  mov     rax, [rbx+58h]
0x180024a14  lea     rcx, [rax+rbp*8]; void *
0x180024a18  movzx   eax, word ptr [rbx+50h]
0x180024a1c  sub     eax, edi
0x180024a1e  lea     rdx, [rcx+18h]; Src
0x180024a22  dec     eax
0x180024a24  lea     r8, [rax+rax*2]
0x180024a28  shl     r8, 3; Size
0x180024a2c  call    memmove_0
0x180024a31  mov     eax, 0FFFFh
0x180024a36  add     [rbx+50h], ax
0x180024a3a  jmp     short loc_180024A3E
0x180024a3c  inc     edi
0x180024a3e  movzx   eax, word ptr [rbx+50h]
0x180024a42  cmp     edi, eax
0x180024a44  jb      short loc_1800249F6
0x180024a46  xor     eax, eax
0x180024a48  add     rsp, 28h
0x180024a4c  pop     rdi
0x180024a4d  pop     rsi
0x180024a4e  pop     rbp
0x180024a4f  pop     rbx
0x180024a50  retn
```
