# RasAuthAttributeCopy

- ea: `0x18001ab0c`
- end: `0x18001ab9a`
- name: `RasAuthAttributeCopy`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ecac`
- `0x180012d54`
- `0x180012e38`

## callees

- `0x18001ab0c`
- `0x18001ac50`
- `0x18001acd8`
- `0x18001b4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab7d`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeCopy(_DWORD *a1)
{
  unsigned int v2; // ecx
  _DWORD *v3; // rdi
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
      ++v2;
    while ( a1[4 * v2] );
  }
  v3 = RasAuthAttributeCreate(v2);
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
0x18001ab0c  push    rbx
0x18001ab0e  push    rbp
0x18001ab0f  push    rsi
0x18001ab10  push    rdi
0x18001ab11  sub     rsp, 38h
0x18001ab15  mov     rbx, rcx
0x18001ab18  test    rcx, rcx
0x18001ab1b  jz      short loc_18001AB89
0x18001ab1d  xor     ecx, ecx
0x18001ab1f  cmp     [rbx], ecx
0x18001ab21  jz      short loc_18001AB30
0x18001ab23  inc     ecx
0x18001ab25  mov     eax, ecx
0x18001ab27  add     rax, rax
0x18001ab2a  cmp     dword ptr [rbx+rax*8], 0
0x18001ab2e  jnz     short loc_18001AB23
0x18001ab30  call    RasAuthAttributeCreate
0x18001ab35  mov     rdi, rax
0x18001ab38  test    rax, rax
0x18001ab3b  jz      short loc_18001AB89
0x18001ab3d  xor     esi, esi
0x18001ab3f  mov     ecx, esi
0x18001ab41  add     rcx, rcx
0x18001ab44  mov     r8d, [rbx+rcx*8]; int
0x18001ab48  test    r8d, r8d
0x18001ab4b  jz      short loc_18001AB95
0x18001ab4d  mov     rax, [rbx+rcx*8+8]
0x18001ab52  mov     rdx, rdi; int
0x18001ab55  mov     [rsp+58h+Src], rax; Src
0x18001ab5a  mov     eax, [rbx+rcx*8+4]
0x18001ab5e  mov     ecx, esi; int
0x18001ab60  mov     dword ptr [rsp+58h+Size], eax; Size
0x18001ab64  call    RasAuthAttributeInsert
0x18001ab69  mov     ebp, eax
0x18001ab6b  test    eax, eax
0x18001ab6d  jnz     short loc_18001AB73
0x18001ab6f  inc     esi
0x18001ab71  jmp     short loc_18001AB3F
0x18001ab73  mov     rcx, rdi; hMem
0x18001ab76  call    RasAuthAttributeDestroy
0x18001ab7b  mov     ecx, ebp; dwErrCode
0x18001ab7d  call    cs:__imp_SetLastError
0x18001ab84  nop     dword ptr [rax+rax+00h]
0x18001ab89  xor     eax, eax
0x18001ab8b  add     rsp, 38h
0x18001ab8f  pop     rdi
0x18001ab90  pop     rsi
0x18001ab91  pop     rbp
0x18001ab92  pop     rbx
0x18001ab93  retn
0x18001ab95  mov     rax, rdi
0x18001ab98  jmp     short loc_18001AB8B
```
