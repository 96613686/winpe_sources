# RasAuthAttributeCopyWithAlloc

- ea: `0x18001aba0`
- end: `0x18001ac4a`
- name: `RasAuthAttributeCopyWithAlloc`
- size: `170`
- prototype: `_DWORD *__fastcall(_DWORD *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023c0`
- `0x18000a9f0`

## callees

- `0x18001aba0`
- `0x18001ac50`
- `0x18001acd8`
- `0x18001b4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac3c`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeCopyWithAlloc(_DWORD *a1, unsigned int a2)
{
  _DWORD *v4; // rbx
  int v6; // ecx
  __int64 v7; // r9
  int i; // esi
  int v9; // r8d
  DWORD v10; // r14d
  size_t Size; // [rsp+20h] [rbp-38h]

  if ( a1 )
  {
    v6 = 0;
    if ( *a1 )
    {
      do
        ++v6;
      while ( a1[4 * v6] );
    }
    v4 = RasAuthAttributeCreate(a2 + v6);
    if ( v4 )
    {
      for ( i = 0; ; ++i )
      {
        v9 = a1[4 * i];
        if ( !v9 )
          break;
        LODWORD(Size) = a1[4 * i + 1];
        v10 = RasAuthAttributeInsert(i + a2, (__int64)v4, v9, v7, Size, *(void **)&a1[4 * i + 2]);
        if ( v10 )
        {
          RasAuthAttributeDestroy(v4);
          SetLastError(v10);
          return 0;
        }
      }
      return v4;
    }
  }
  else
  {
    v4 = RasAuthAttributeCreate(a2);
    if ( v4 )
      return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18001aba0  push    rbx
0x18001aba2  push    rbp
0x18001aba3  push    rsi
0x18001aba4  push    rdi
0x18001aba5  push    r14
0x18001aba7  sub     rsp, 30h
0x18001abab  mov     ebp, edx
0x18001abad  mov     rdi, rcx
0x18001abb0  test    rcx, rcx
0x18001abb3  jnz     short loc_18001ABD3
0x18001abb5  mov     ecx, edx
0x18001abb7  call    RasAuthAttributeCreate
0x18001abbc  mov     rbx, rax
0x18001abbf  test    rax, rax
0x18001abc2  jz      short loc_18001ABF5
0x18001abc4  mov     rax, rbx
0x18001abc7  add     rsp, 30h
0x18001abcb  pop     r14
0x18001abcd  pop     rdi
0x18001abce  pop     rsi
0x18001abcf  pop     rbp
0x18001abd0  pop     rbx
0x18001abd1  retn
0x18001abd3  xor     ecx, ecx
0x18001abd5  cmp     [rdi], ecx
0x18001abd7  jz      short loc_18001ABE6
0x18001abd9  inc     ecx
0x18001abdb  mov     eax, ecx
0x18001abdd  add     rax, rax
0x18001abe0  cmp     dword ptr [rdi+rax*8], 0
0x18001abe4  jnz     short loc_18001ABD9
0x18001abe6  add     ecx, ebp
0x18001abe8  call    RasAuthAttributeCreate
0x18001abed  mov     rbx, rax
0x18001abf0  test    rax, rax
0x18001abf3  jnz     short loc_18001ABF9
0x18001abf5  xor     eax, eax
0x18001abf7  jmp     short loc_18001ABC7
0x18001abf9  xor     esi, esi
0x18001abfb  mov     edx, esi
0x18001abfd  add     rdx, rdx
0x18001ac00  mov     r8d, [rdi+rdx*8]; int
0x18001ac04  test    r8d, r8d
0x18001ac07  jz      short loc_18001ABC4
0x18001ac09  mov     rax, [rdi+rdx*8+8]
0x18001ac0e  lea     ecx, [rsi+rbp]; int
0x18001ac11  mov     [rsp+58h+Src], rax; Src
0x18001ac16  mov     eax, [rdi+rdx*8+4]
0x18001ac1a  mov     rdx, rbx; int
0x18001ac1d  mov     dword ptr [rsp+58h+Size], eax; Size
0x18001ac21  call    RasAuthAttributeInsert
0x18001ac26  mov     r14d, eax
0x18001ac29  test    eax, eax
0x18001ac2b  jnz     short loc_18001AC31
0x18001ac2d  inc     esi
0x18001ac2f  jmp     short loc_18001ABFB
0x18001ac31  mov     rcx, rbx; hMem
0x18001ac34  call    RasAuthAttributeDestroy
0x18001ac39  mov     ecx, r14d; dwErrCode
0x18001ac3c  call    cs:__imp_SetLastError
0x18001ac43  nop     dword ptr [rax+rax+00h]
0x18001ac48  jmp     short loc_18001ABF5
```
