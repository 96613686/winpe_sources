# PathCchSkipRoot(ushort *,ushort * *)

- ea: `0x18000f6b0`
- end: `0x18000f813`
- name: `?PathCchSkipRoot@@YAJPEAGPEAPEAG@Z`
- size: `355`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x180007f78`
- `0x1800100a8`

## callees

- `0x18000f6b0`
- `0x18000f81c`
- `0x18000f8b4`
- `0x180018434`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f7ce`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f7ce`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f715`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f72c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f715`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f72c`

## pseudocode

```c
__int64 __fastcall PathCchSkipRoot(unsigned __int16 *a1, unsigned __int16 **a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rdi
  wchar_t *v7; // rax
  unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int16 v11; // bp
  __int64 v12; // rbx
  unsigned __int16 *v13; // rbx
  __int64 v14; // rax

  if ( a1 && *a1 && a2 )
  {
    *a2 = 0;
    if ( (unsigned int)PathIsUnc2(a1) )
    {
      v4 = wcschr(0, 0x5Cu);
      v5 = v4;
      if ( v4 )
      {
        v6 = v4 + 1;
        v7 = wcschr(v4 + 1, 0x5Cu);
        if ( v7 )
        {
          v8 = v7 + 1;
          if ( v7 == v6 )
            v8 = v7;
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( v5[v9] );
          v8 = &v5[v9];
        }
      }
      else
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(2 * v10) );
        v8 = (unsigned __int16 *)(2 * v10);
      }
LABEL_30:
      *a2 = v8;
      return 0;
    }
    v11 = *a1;
    if ( *a1 == 92 )
    {
      v8 = a1 + 1;
      if ( a1[1] != 92 )
        goto LABEL_30;
    }
    if ( PathIsVolumeGUIDWorker(a1) )
    {
      v12 = 49;
      if ( a1[48] != 92 )
        v12 = 48;
      v8 = &a1[v12];
      goto LABEL_30;
    }
    if ( !wcsncmp_0(a1, L"\\\\?\\", 4u) )
    {
      v13 = a1 + 4;
      v11 = a1[4];
    }
    else
    {
      v13 = a1;
    }
    if ( (unsigned int)_o_iswalpha(v11) && v13[1] == 58 )
    {
      v14 = 3;
      if ( v13[2] != 92 )
        v14 = 2;
      v8 = &v13[v14];
      goto LABEL_30;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000f6b0  mov     rax, rsp
0x18000f6b3  mov     [rax+10h], rbx
0x18000f6b7  mov     [rax+18h], rbp
0x18000f6bb  push    rsi
0x18000f6bc  push    rdi
0x18000f6bd  push    r12
0x18000f6bf  push    r14
0x18000f6c1  push    r15
0x18000f6c3  sub     rsp, 20h
0x18000f6c7  xor     r15d, r15d
0x18000f6ca  mov     r14, rdx
0x18000f6cd  mov     [rax+8], r15
0x18000f6d1  mov     rdi, rcx
0x18000f6d4  test    rcx, rcx
0x18000f6d7  jz      loc_18000F7F7
0x18000f6dd  cmp     [rcx], r15w
0x18000f6e1  jz      loc_18000F7F7
0x18000f6e7  test    rdx, rdx
0x18000f6ea  jz      loc_18000F7F7
0x18000f6f0  mov     [rdx], r15
0x18000f6f3  lea     r8, IsBackslash
0x18000f6fa  lea     rdx, [rax+8]
0x18000f6fe  call    PathIsUnc2
0x18000f703  lea     esi, [r15+5Ch]
0x18000f707  test    eax, eax
0x18000f709  jz      short loc_18000F772
0x18000f70b  mov     rdi, [rsp+48h+Str]
0x18000f710  mov     edx, esi; Ch
0x18000f712  mov     rcx, rdi; Str
0x18000f715  call    cs:__imp_wcschr
0x18000f71b  mov     rbx, rax
0x18000f71e  test    rax, rax
0x18000f721  jz      short loc_18000F75E
0x18000f723  lea     rdi, [rax+2]
0x18000f727  mov     edx, esi; Ch
0x18000f729  mov     rcx, rdi; Str
0x18000f72c  call    cs:__imp_wcschr
0x18000f732  test    rax, rax
0x18000f735  jz      short loc_18000F747
0x18000f737  cmp     rax, rdi
0x18000f73a  lea     rbx, [rax+2]
0x18000f73e  cmovz   rbx, rax
0x18000f742  jmp     loc_18000F7EF
0x18000f747  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f74b  inc     rax
0x18000f74e  cmp     [rbx+rax*2], r15w
0x18000f753  jnz     short loc_18000F74B
0x18000f755  lea     rbx, [rbx+rax*2]
0x18000f759  jmp     loc_18000F7EF
0x18000f75e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f762  inc     rax
0x18000f765  cmp     [rdi+rax*2], r15w
0x18000f76a  jnz     short loc_18000F762
0x18000f76c  lea     rbx, [rdi+rax*2]
0x18000f770  jmp     short loc_18000F7EF
0x18000f772  movzx   ebp, word ptr [rdi]
0x18000f775  cmp     bp, si
0x18000f778  jnz     short loc_18000F783
0x18000f77a  lea     rbx, [rdi+2]
0x18000f77e  cmp     [rbx], si
0x18000f781  jnz     short loc_18000F7EF
0x18000f783  mov     rcx, rdi; unsigned __int16 *
0x18000f786  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18000f78b  test    al, al
0x18000f78d  jz      short loc_18000F7A3
0x18000f78f  cmp     [rdi+60h], si
0x18000f793  mov     ebx, 62h ; 'b'
0x18000f798  lea     eax, [rbx-2]
0x18000f79b  cmovnz  ebx, eax
0x18000f79e  add     rbx, rdi
0x18000f7a1  jmp     short loc_18000F7EF
0x18000f7a3  mov     r12d, 4
0x18000f7a9  lea     rdx, asc_18001EE88; "\\\\?\\"
0x18000f7b0  mov     r8d, r12d; MaxCount
0x18000f7b3  mov     rcx, rdi; String1
0x18000f7b6  call    wcsncmp_0
0x18000f7bb  test    eax, eax
0x18000f7bd  jz      short loc_18000F7C4
0x18000f7bf  mov     rbx, rdi
0x18000f7c2  jmp     short loc_18000F7CB
0x18000f7c4  lea     rbx, [rdi+8]
0x18000f7c8  movzx   ebp, word ptr [rbx]
0x18000f7cb  movzx   ecx, bp
0x18000f7ce  call    cs:__imp__o_iswalpha
0x18000f7d4  test    eax, eax
0x18000f7d6  jz      short loc_18000F7F7
0x18000f7d8  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18000f7dd  jnz     short loc_18000F7F7
0x18000f7df  cmp     [rbx+4], si
0x18000f7e3  mov     eax, 6
0x18000f7e8  cmovnz  rax, r12
0x18000f7ec  add     rbx, rax
0x18000f7ef  mov     [r14], rbx
0x18000f7f2  mov     eax, r15d
0x18000f7f5  jmp     short loc_18000F7FC
0x18000f7f7  mov     eax, 80070057h
0x18000f7fc  mov     rbx, [rsp+48h+arg_8]
0x18000f801  mov     rbp, [rsp+48h+arg_10]
0x18000f806  add     rsp, 20h
0x18000f80a  pop     r15
0x18000f80c  pop     r14
0x18000f80e  pop     r12
0x18000f810  pop     rdi
0x18000f811  pop     rsi
0x18000f812  retn
```
