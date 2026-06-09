# create_slot_lookup_table

- ea: `0x1800174f0`
- end: `0x180017587`
- name: `create_slot_lookup_table`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016eac`

## callees

- `0x18001562a`
- `0x1800174f0`

## pseudocode

```c
void *__fastcall create_slot_lookup_table(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // r15
  char v4; // si
  int v5; // edi
  int v6; // ebp
  void *result; // rax
  char v8; // si
  int v9; // ebp

  v1 = 2;
  *(_WORD *)(a1 + 1149) = 513;
  v2 = a1 + 1148;
  *(_BYTE *)(a1 + 1151) = 3;
  *(_BYTE *)(a1 + 1148) = 0;
  v4 = 4;
  v5 = 4;
  do
  {
    v6 = v1;
    if ( v1 > 0 )
    {
      result = memset_0((void *)(v2 + v5), v4, v1);
      do
      {
        ++v5;
        --v6;
      }
      while ( v6 > 0 );
    }
    v8 = v4 + 1;
    v9 = v1;
    if ( v1 > 0 )
    {
      result = memset_0((void *)(a1 + v5 + 1148LL), v8, v1);
      do
      {
        ++v5;
        --v9;
      }
      while ( v9 > 0 );
    }
    v4 = v8 + 1;
    v1 *= 2;
  }
  while ( v5 < 1024 );
  return result;
}

```

## disassembly

```asm
0x1800174f0  push    rbx
0x1800174f2  push    rbp
0x1800174f3  push    rsi
0x1800174f4  push    rdi
0x1800174f5  push    r14
0x1800174f7  push    r15
0x1800174f9  sub     rsp, 28h
0x1800174fd  mov     ebx, 2
0x180017502  mov     word ptr [rcx+47Dh], 201h
0x18001750b  lea     r15, [rcx+47Ch]
0x180017512  mov     byte ptr [rcx+47Fh], 3
0x180017519  mov     r14, rcx
0x18001751c  mov     byte ptr [r15], 0
0x180017520  lea     esi, [rbx+2]
0x180017523  mov     edi, esi
0x180017525  mov     ebp, ebx
0x180017527  test    ebx, ebx
0x180017529  jle     short loc_180017544
0x18001752b  movsxd  rcx, edi
0x18001752e  mov     dl, sil; Val
0x180017531  add     rcx, r15; void *
0x180017534  movsxd  r8, ebx; Size
0x180017537  call    memset_0
0x18001753c  inc     edi
0x18001753e  dec     ebp
0x180017540  test    ebp, ebp
0x180017542  jg      short loc_18001753C
0x180017544  inc     sil
0x180017547  mov     ebp, ebx
0x180017549  test    ebx, ebx
0x18001754b  jle     short loc_18001756D
0x18001754d  movsxd  rcx, edi
0x180017550  mov     dl, sil; Val
0x180017553  add     rcx, 47Ch
0x18001755a  movsxd  r8, ebx; Size
0x18001755d  add     rcx, r14; void *
0x180017560  call    memset_0
0x180017565  inc     edi
0x180017567  dec     ebp
0x180017569  test    ebp, ebp
0x18001756b  jg      short loc_180017565
0x18001756d  inc     sil
0x180017570  add     ebx, ebx
0x180017572  cmp     edi, 400h
0x180017578  jl      short loc_180017525
0x18001757a  add     rsp, 28h
0x18001757e  pop     r15
0x180017580  pop     r14
0x180017582  pop     rdi
0x180017583  pop     rsi
0x180017584  pop     rbp
0x180017585  pop     rbx
0x180017586  retn
```
