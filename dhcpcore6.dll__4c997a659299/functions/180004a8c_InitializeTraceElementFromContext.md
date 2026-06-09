# InitializeTraceElementFromContext

- ea: `0x180004a8c`
- end: `0x180004b2a`
- name: `InitializeTraceElementFromContext`
- size: `158`
- prototype: `__int64 __fastcall(_DWORD *, __int64, int, int)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18000490c`
- `0x180004d78`
- `0x180005368`
- `0x18001225c`
- `0x180012634`
- `0x18001b314`
- `0x18001e110`
- `0x1800225c8`
- `0x180022b80`
- `0x180023344`
- `0x180023dc0`
- `0x18002458c`
- `0x180025094`

## callees

- `0x180004a8c`
- `0x18001a3ee`

## pseudocode

```c
__int64 __fastcall InitializeTraceElementFromContext(_DWORD *a1, __int64 a2, int a3, int a4)
{
  __int64 result; // rax
  _WORD *v9; // r8
  __int64 *v10; // rcx
  __int64 v11; // rdx
  _WORD *v12; // rcx

  result = (__int64)memset_0(a1, 0, 0xA0u);
  *a1 = a3;
  a1[3] = a4;
  v9 = a1 + 40;
  *((_WORD *)a1 + 80) = 0;
  if ( a2 )
  {
    v10 = &qword_180037F50;
    *((_QWORD *)a1 + 13) = *(_QWORD *)(a2 + 24);
    v11 = 2147483646;
    a1[4] = *(_DWORD *)(a2 + 48);
    result = 80;
    if ( *(_QWORD *)(a2 + 56) )
      v10 = *(__int64 **)(a2 + 56);
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)v10 )
        break;
      *v9 = *(_WORD *)v10;
      v10 = (__int64 *)((char *)v10 + 2);
      ++v9;
      --v11;
      --result;
    }
    while ( result );
    v12 = v9 - 1;
    if ( result )
      v12 = v9;
    *v12 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004a8c  push    rbx
0x180004a8e  push    rbp
0x180004a8f  push    rsi
0x180004a90  push    rdi
0x180004a91  sub     rsp, 28h
0x180004a95  mov     ebx, r8d
0x180004a98  mov     rbp, rdx
0x180004a9b  xor     edx, edx; Val
0x180004a9d  mov     r8d, 0A0h; Size
0x180004aa3  mov     edi, r9d
0x180004aa6  mov     rsi, rcx
0x180004aa9  call    memset_0
0x180004aae  xor     r10d, r10d
0x180004ab1  mov     [rsi], ebx
0x180004ab3  mov     [rsi+0Ch], edi
0x180004ab6  lea     r8, [rsi+0A0h]
0x180004abd  mov     [r8], r10w
0x180004ac1  test    rbp, rbp
0x180004ac4  jz      short loc_180004B20
0x180004ac6  mov     rax, [rbp+18h]
0x180004aca  lea     rcx, qword_180037F50
0x180004ad1  mov     [rsi+68h], rax
0x180004ad5  mov     edx, 7FFFFFFEh
0x180004ada  mov     eax, [rbp+30h]
0x180004add  mov     [rsi+10h], eax
0x180004ae0  lea     eax, [r10+50h]
0x180004ae4  cmp     [rbp+38h], r10
0x180004ae8  cmovnz  rcx, [rbp+38h]
0x180004aed  test    rdx, rdx
0x180004af0  jz      short loc_180004B11
0x180004af2  movzx   r9d, word ptr [rcx]
0x180004af6  test    r9w, r9w
0x180004afa  jz      short loc_180004B11
0x180004afc  mov     [r8], r9w
0x180004b00  add     rcx, 2
0x180004b04  add     r8, 2
0x180004b08  dec     rdx
0x180004b0b  sub     rax, 1
0x180004b0f  jnz     short loc_180004AED
0x180004b11  test    rax, rax
0x180004b14  lea     rcx, [r8-2]
0x180004b18  cmovnz  rcx, r8
0x180004b1c  mov     [rcx], r10w
0x180004b20  add     rsp, 28h
0x180004b24  pop     rdi
0x180004b25  pop     rsi
0x180004b26  pop     rbp
0x180004b27  pop     rbx
0x180004b28  retn
```
