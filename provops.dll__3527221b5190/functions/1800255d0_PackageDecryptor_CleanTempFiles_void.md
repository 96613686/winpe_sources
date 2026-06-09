# PackageDecryptor::CleanTempFiles(void)

- ea: `0x1800255d0`
- end: `0x180025657`
- name: `?CleanTempFiles@PackageDecryptor@@QEAAXXZ`
- size: `135`
- prototype: `void __fastcall(PackageDecryptor *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f8d0`
- `0x180024f5c`

## callees

- `0x1800255d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002561c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002561c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800255fd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800255fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PackageDecryptor::CleanTempFiles(PackageDecryptor *this)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  const WCHAR *v4; // rcx
  __int64 v5; // rdi
  __int64 i; // rbx

  v1 = *(_QWORD *)this;
  v3 = *((_QWORD *)this + 1);
  while ( v1 != v3 )
  {
    if ( *(_QWORD *)(v1 + 24) < 8u )
      v4 = (const WCHAR *)v1;
    else
      v4 = *(const WCHAR **)v1;
    DeleteFileW(v4);
    v1 += 32;
  }
  v5 = *((_QWORD *)this + 1);
  for ( i = *(_QWORD *)this; i != v5; i += 32 )
  {
    if ( *(_QWORD *)(i + 24) >= 8u )
      operator delete(*(void **)i);
    *(_QWORD *)(i + 24) = 7;
    *(_QWORD *)(i + 16) = 0;
    *(_WORD *)i = 0;
  }
  *((_QWORD *)this + 1) = *(_QWORD *)this;
}

```

## disassembly

```asm
0x1800255d0  mov     [rsp+arg_0], rbx
0x1800255d5  mov     [rsp+arg_8], rsi
0x1800255da  push    rdi
0x1800255db  sub     rsp, 20h
0x1800255df  mov     rbx, [rcx]
0x1800255e2  mov     rsi, rcx
0x1800255e5  mov     rdi, [rcx+8]
0x1800255e9  cmp     rbx, rdi
0x1800255ec  jz      short loc_180025609
0x1800255ee  cmp     qword ptr [rbx+18h], 8
0x1800255f3  jb      short loc_1800255FA
0x1800255f5  mov     rcx, [rbx]
0x1800255f8  jmp     short loc_1800255FD
0x1800255fa  mov     rcx, rbx; lpFileName
0x1800255fd  call    cs:__imp_DeleteFileW
0x180025603  add     rbx, 20h ; ' '
0x180025607  jmp     short loc_1800255E9
0x180025609  mov     rdi, [rsi+8]
0x18002560d  mov     rbx, [rsi]
0x180025610  jmp     short loc_18002563B
0x180025612  cmp     qword ptr [rbx+18h], 8
0x180025617  jb      short loc_180025622
0x180025619  mov     rcx, [rbx]
0x18002561c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025622  xor     eax, eax
0x180025624  mov     qword ptr [rbx+18h], 7
0x18002562c  mov     qword ptr [rbx+10h], 0
0x180025634  mov     [rbx], ax
0x180025637  add     rbx, 20h ; ' '
0x18002563b  cmp     rbx, rdi
0x18002563e  jnz     short loc_180025612
0x180025640  mov     rax, [rsi]
0x180025643  mov     rbx, [rsp+28h+arg_0]
0x180025648  mov     [rsi+8], rax
0x18002564c  mov     rsi, [rsp+28h+arg_8]
0x180025651  add     rsp, 20h
0x180025655  pop     rdi
0x180025656  retn
```
