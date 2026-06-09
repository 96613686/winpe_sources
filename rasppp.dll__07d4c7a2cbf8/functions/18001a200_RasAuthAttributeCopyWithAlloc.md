# RasAuthAttributeCopyWithAlloc

- ea: `0x18001a200`
- end: `0x18001a2a3`
- name: `RasAuthAttributeCopyWithAlloc`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023a8`
- `0x18000a610`

## callees

- `0x18001a200`
- `0x18001a2ac`
- `0x18001a330`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a29b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a29b`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeCopyWithAlloc(_DWORD *a1, unsigned int a2)
{
  _DWORD *v4; // rbx
  int v6; // ecx
  int v7; // r9d
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
        v10 = RasAuthAttributeInsert(i + a2, (int)v4, v9, v7, Size, *(void **)&a1[4 * i + 2]);
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
0x18001a200  push    rbx
0x18001a202  push    rbp
0x18001a203  push    rsi
0x18001a204  push    rdi
0x18001a205  push    r14
0x18001a207  sub     rsp, 30h
0x18001a20b  mov     ebp, edx
0x18001a20d  mov     rdi, rcx
0x18001a210  test    rcx, rcx
0x18001a213  jnz     short loc_18001A232
0x18001a215  mov     ecx, edx
0x18001a217  call    RasAuthAttributeCreate
0x18001a21c  mov     rbx, rax
0x18001a21f  test    rax, rax
0x18001a222  jz      short loc_18001A254
0x18001a224  mov     rax, rbx
0x18001a227  add     rsp, 30h
0x18001a22b  pop     r14
0x18001a22d  pop     rdi
0x18001a22e  pop     rsi
0x18001a22f  pop     rbp
0x18001a230  pop     rbx
0x18001a231  retn
0x18001a232  xor     ecx, ecx
0x18001a234  cmp     [rdi], ecx
0x18001a236  jz      short loc_18001A245
0x18001a238  inc     ecx
0x18001a23a  mov     eax, ecx
0x18001a23c  add     rax, rax
0x18001a23f  cmp     dword ptr [rdi+rax*8], 0
0x18001a243  jnz     short loc_18001A238
0x18001a245  add     ecx, ebp
0x18001a247  call    RasAuthAttributeCreate
0x18001a24c  mov     rbx, rax
0x18001a24f  test    rax, rax
0x18001a252  jnz     short loc_18001A258
0x18001a254  xor     eax, eax
0x18001a256  jmp     short loc_18001A227
0x18001a258  xor     esi, esi
0x18001a25a  mov     edx, esi
0x18001a25c  add     rdx, rdx
0x18001a25f  mov     r8d, [rdi+rdx*8]; int
0x18001a263  test    r8d, r8d
0x18001a266  jz      short loc_18001A224
0x18001a268  mov     rax, [rdi+rdx*8+8]
0x18001a26d  lea     ecx, [rsi+rbp]; int
0x18001a270  mov     [rsp+58h+Src], rax; Src
0x18001a275  mov     eax, [rdi+rdx*8+4]
0x18001a279  mov     rdx, rbx; int
0x18001a27c  mov     dword ptr [rsp+58h+Size], eax; Size
0x18001a280  call    RasAuthAttributeInsert
0x18001a285  mov     r14d, eax
0x18001a288  test    eax, eax
0x18001a28a  jnz     short loc_18001A290
0x18001a28c  inc     esi
0x18001a28e  jmp     short loc_18001A25A
0x18001a290  mov     rcx, rbx; hMem
0x18001a293  call    RasAuthAttributeDestroy
0x18001a298  mov     ecx, r14d; dwErrCode
0x18001a29b  call    cs:__imp_SetLastError
0x18001a2a1  jmp     short loc_18001A254
```
