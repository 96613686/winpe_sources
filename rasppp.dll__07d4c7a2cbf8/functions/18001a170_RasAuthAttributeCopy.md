# RasAuthAttributeCopy

- ea: `0x18001a170`
- end: `0x18001a1f7`
- name: `RasAuthAttributeCopy`
- size: `135`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e86c`
- `0x1800126b8`
- `0x180012794`

## callees

- `0x18001a170`
- `0x18001a2ac`
- `0x18001a330`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e1`

## pseudocode

```c
void *__fastcall RasAuthAttributeCopy(_DWORD *a1)
{
  __int64 v2; // rcx
  void *v3; // rdi
  int v4; // r9d
  unsigned int i; // esi
  int v6; // r8d
  DWORD v7; // ebp
  size_t Size; // [rsp+20h] [rbp-38h]

  if ( !a1 )
    return 0;
  v2 = 0;
  if ( *a1 )
  {
    do
      v2 = (unsigned int)(v2 + 1);
    while ( a1[4 * (unsigned int)v2] );
  }
  v3 = (void *)RasAuthAttributeCreate(v2);
  if ( !v3 )
    return 0;
  for ( i = 0; ; ++i )
  {
    v6 = a1[4 * i];
    if ( !v6 )
      break;
    LODWORD(Size) = a1[4 * i + 1];
    v7 = RasAuthAttributeInsert(i, (int)v3, v6, v4, Size, *(void **)&a1[4 * i + 2]);
    if ( v7 )
    {
      RasAuthAttributeDestroy(v3);
      SetLastError(v7);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001a170  push    rbx
0x18001a172  push    rbp
0x18001a173  push    rsi
0x18001a174  push    rdi
0x18001a175  sub     rsp, 38h
0x18001a179  mov     rbx, rcx
0x18001a17c  test    rcx, rcx
0x18001a17f  jz      short loc_18001A1E7
0x18001a181  xor     ecx, ecx
0x18001a183  cmp     [rbx], ecx
0x18001a185  jz      short loc_18001A194
0x18001a187  inc     ecx
0x18001a189  mov     eax, ecx
0x18001a18b  add     rax, rax
0x18001a18e  cmp     dword ptr [rbx+rax*8], 0
0x18001a192  jnz     short loc_18001A187
0x18001a194  call    RasAuthAttributeCreate
0x18001a199  mov     rdi, rax
0x18001a19c  test    rax, rax
0x18001a19f  jz      short loc_18001A1E7
0x18001a1a1  xor     esi, esi
0x18001a1a3  mov     ecx, esi
0x18001a1a5  add     rcx, rcx
0x18001a1a8  mov     r8d, [rbx+rcx*8]; int
0x18001a1ac  test    r8d, r8d
0x18001a1af  jz      short loc_18001A1F2
0x18001a1b1  mov     rax, [rbx+rcx*8+8]
0x18001a1b6  mov     rdx, rdi; int
0x18001a1b9  mov     [rsp+58h+Src], rax; Src
0x18001a1be  mov     eax, [rbx+rcx*8+4]
0x18001a1c2  mov     ecx, esi; int
0x18001a1c4  mov     dword ptr [rsp+58h+Size], eax; Size
0x18001a1c8  call    RasAuthAttributeInsert
0x18001a1cd  mov     ebp, eax
0x18001a1cf  test    eax, eax
0x18001a1d1  jnz     short loc_18001A1D7
0x18001a1d3  inc     esi
0x18001a1d5  jmp     short loc_18001A1A3
0x18001a1d7  mov     rcx, rdi; hMem
0x18001a1da  call    RasAuthAttributeDestroy
0x18001a1df  mov     ecx, ebp; dwErrCode
0x18001a1e1  call    cs:__imp_SetLastError
0x18001a1e7  xor     eax, eax
0x18001a1e9  add     rsp, 38h
0x18001a1ed  pop     rdi
0x18001a1ee  pop     rsi
0x18001a1ef  pop     rbp
0x18001a1f0  pop     rbx
0x18001a1f1  retn
0x18001a1f2  mov     rax, rdi
0x18001a1f5  jmp     short loc_18001A1E9
```
