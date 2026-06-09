# CopyStrippingLeadTrailSpace(ushort *,ushort const *,ulong)

- ea: `0x18001f1f0`
- end: `0x18001f272`
- name: `?CopyStrippingLeadTrailSpace@@YAXPEAGPEBGK@Z`
- size: `130`
- prototype: `void __fastcall(wchar_t *Destination, wchar_t *String, rsize_t SizeInWords)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020658`

## callees

- `0x18001f1f0`

## import_xrefs

- `msvcrt!wcsspn` at `0x18001f210`
- `msvcrt!wcsspn` at `0x18001f210`
- `msvcrt!wcsncpy_s` at `0x18001f222`
- `msvcrt!wcsncpy_s` at `0x18001f222`

## pseudocode

```c
void __fastcall CopyStrippingLeadTrailSpace(wchar_t *Destination, wchar_t *String, rsize_t SizeInWords)
{
  unsigned int v4; // esi
  unsigned int v6; // ebx
  size_t v7; // rax
  wchar_t *v8; // rdx
  unsigned int v9; // r8d
  wchar_t *v10; // rcx

  v4 = SizeInWords;
  v6 = SizeInWords - 1;
  v7 = wcsspn(String, L" ");
  wcsncpy_s(Destination, v4, &String[v7], v6);
  v8 = 0;
  v9 = 0;
  if ( v4 )
  {
    do
    {
      v10 = &Destination[v9];
      if ( !*v10 )
        break;
      if ( *v10 == 32 )
      {
        if ( v8 )
          v10 = v8;
        v8 = v10;
      }
      else
      {
        v8 = 0;
      }
      ++v9;
    }
    while ( v9 < v4 );
    if ( v8 )
      *v8 = 0;
  }
}

```

## disassembly

```asm
0x18001f1f0  push    rbx
0x18001f1f2  push    rsi
0x18001f1f3  push    rdi
0x18001f1f4  push    r14
0x18001f1f6  sub     rsp, 28h
0x18001f1fa  mov     rdi, rdx
0x18001f1fd  mov     esi, r8d
0x18001f200  mov     r14, rcx
0x18001f203  lea     rdx, asc_180028E08; " "
0x18001f20a  mov     rcx, rdi; String
0x18001f20d  lea     ebx, [rsi-1]
0x18001f210  call    cs:__imp_wcsspn
0x18001f216  mov     edx, esi; SizeInWords
0x18001f218  mov     r9d, ebx; MaxCount
0x18001f21b  mov     rcx, r14; Destination
0x18001f21e  lea     r8, [rdi+rax*2]; Source
0x18001f222  call    cs:__imp_wcsncpy_s
0x18001f228  xor     r9d, r9d
0x18001f22b  mov     edx, r9d
0x18001f22e  mov     r8d, r9d
0x18001f231  test    esi, esi
0x18001f233  jz      short loc_18001F268
0x18001f235  mov     eax, r8d
0x18001f238  lea     rcx, [r14+rax*2]
0x18001f23c  cmp     [rcx], r9w
0x18001f240  jz      short loc_18001F25F
0x18001f242  cmp     word ptr [rcx], 20h ; ' '
0x18001f246  jnz     short loc_18001F254
0x18001f248  test    rdx, rdx
0x18001f24b  cmovnz  rcx, rdx
0x18001f24f  mov     rdx, rcx
0x18001f252  jmp     short loc_18001F257
0x18001f254  mov     rdx, r9
0x18001f257  inc     r8d
0x18001f25a  cmp     r8d, esi
0x18001f25d  jb      short loc_18001F235
0x18001f25f  test    rdx, rdx
0x18001f262  jz      short loc_18001F268
0x18001f264  mov     [rdx], r9w
0x18001f268  add     rsp, 28h
0x18001f26c  pop     r14
0x18001f26e  pop     rdi
0x18001f26f  pop     rsi
0x18001f270  pop     rbx
0x18001f271  retn
```
