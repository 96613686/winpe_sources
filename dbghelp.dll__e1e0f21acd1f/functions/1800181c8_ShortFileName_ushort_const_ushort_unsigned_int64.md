# ShortFileName(ushort const *,ushort *,unsigned __int64)

- ea: `0x1800181c8`
- end: `0x180018451`
- name: `?ShortFileName@@YAHPEBGPEAG_K@Z`
- size: `649`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800130f4`
- `0x1801a85f8`
- `0x1801a895c`

## callees

- `0x1800181c8`
- `0x1800273f0`
- `0x1800273fc`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180018235`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180018235`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018260`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800182cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001831a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018367`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800183b4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018419`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018426`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001842e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018436`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018260`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800182cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001831a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018367`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800183b4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018419`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018426`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001842e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018436`

## pseudocode

```c
__int64 __fastcall ShortFileName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  wchar_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  wchar_t *i; // rcx
  unsigned int v13; // edi
  wchar_t *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  wchar_t *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  __int64 v30; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  wchar_t Drive[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Source[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Dir[264]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t Ext[264]; // [rsp+690h] [rbp+590h] BYREF

  _wsplitpath_s(a1, Drive, 4u, Dir, 0x101u, Source, 0x101u, Ext, 0x101u);
  v6 = 257;
  v7 = Source;
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
    {
      Destination[0] = 0;
      *(_DWORD *)_o__errno(0, v3, v4, v5) = 34;
      goto LABEL_6;
    }
  }
  wcscpy_s(Destination, 0x101u, Source);
LABEL_6:
  v11 = -1;
  do
    ++v11;
  while ( Destination[v11] );
  for ( i = &Drive[v11 + 7]; ; --i )
  {
    if ( i < Destination )
    {
LABEL_10:
      v13 = 0;
      goto LABEL_11;
    }
    if ( *i == 126 )
      break;
    if ( (unsigned __int16)(*i - 48) > 9u )
      goto LABEL_10;
  }
  *(_DWORD *)(i + 1) = 88;
  v13 = 1;
LABEL_11:
  if ( a2 )
  {
    v14 = Drive;
    v15 = 261;
    while ( *v14 )
    {
      ++v14;
      if ( !--v15 )
      {
        *a2 = 0;
        *(_DWORD *)_o__errno(0, v8, v9, v10) = 34;
        goto LABEL_17;
      }
    }
    wcscpy_s(a2, 0x105u, Drive);
LABEL_17:
    v19 = a2;
    v20 = 261;
    while ( *v19 )
    {
      ++v19;
      if ( !--v20 )
      {
LABEL_24:
        *a2 = 0;
        *(_DWORD *)_o__errno(v19, v16, v17, v18) = 34;
        goto LABEL_26;
      }
    }
    v19 = Dir;
    while ( *v19 )
    {
      ++v19;
      if ( !--v20 )
        goto LABEL_24;
    }
    wcscat_s(a2, 0x105u, Dir);
LABEL_26:
    v24 = a2;
    v25 = 261;
    while ( *v24 )
    {
      ++v24;
      if ( !--v25 )
      {
LABEL_33:
        *a2 = 0;
        *(_DWORD *)_o__errno(v24, v21, v22, v23) = 34;
        goto LABEL_35;
      }
    }
    v24 = Source;
    while ( *v24 )
    {
      ++v24;
      if ( !--v25 )
        goto LABEL_33;
    }
    wcscat_s(a2, 0x105u, Source);
LABEL_35:
    v29 = a2;
    v30 = 261;
    while ( *v29 )
    {
      ++v29;
      if ( !--v30 )
      {
LABEL_42:
        *a2 = 0;
        *(_DWORD *)_o__errno(v29, v26, v27, v28) = 34;
        return v13;
      }
    }
    v29 = Ext;
    while ( *v29 )
    {
      ++v29;
      if ( !--v30 )
        goto LABEL_42;
    }
    wcscat_s(a2, 0x105u, Ext);
  }
  else
  {
    *(_DWORD *)_o__errno(i, v8, v9, v10) = 22;
    *(_DWORD *)_o__errno(v33, v32, v34, v35) = 22;
    *(_DWORD *)_o__errno(v37, v36, v38, v39) = 22;
    *(_DWORD *)_o__errno(v41, v40, v42, v43) = 22;
  }
  return v13;
}

```

## disassembly

```asm
0x1800181c8  mov     [rsp-8+arg_10], rbx
0x1800181cd  push    rbp
0x1800181ce  push    rsi
0x1800181cf  push    rdi
0x1800181d0  push    r13
0x1800181d2  push    r15
0x1800181d4  lea     rbp, [rsp-7B0h]
0x1800181dc  sub     rsp, 8B0h
0x1800181e3  mov     rax, cs:__security_cookie
0x1800181ea  xor     rax, rsp
0x1800181ed  mov     [rbp+7D0h+var_30], rax
0x1800181f4  mov     edi, 101h
0x1800181f9  lea     rax, [rbp+7D0h+var_240]
0x180018200  mov     [rsp+8D0h+ExtCount], rdi; ExtCount
0x180018205  lea     r9, [rbp+7D0h+Dir]; Dir
0x18001820c  mov     [rsp+8D0h+Ext], rax; Ext
0x180018211  mov     rbx, rdx
0x180018214  lea     rax, [rbp+7D0h+Source]
0x18001821b  mov     [rsp+8D0h+FilenameCount], rdi; FilenameCount
0x180018220  mov     [rsp+8D0h+Filename], rax; Filename
0x180018225  lea     rdx, [rsp+8D0h+Drive]; Drive
0x18001822a  mov     r8d, 4; DriveCount
0x180018230  mov     [rsp+8D0h+DirCount], rdi; DirCount
0x180018235  call    cs:__imp__wsplitpath_s
0x18001823b  mov     ecx, edi
0x18001823d  lea     rax, [rbp+7D0h+Source]
0x180018244  xor     esi, esi
0x180018246  mov     r13d, 22h ; '"'
0x18001824c  cmp     [rax], si
0x18001824f  jz      short loc_18001826B
0x180018251  add     rax, 2
0x180018255  sub     rcx, 1
0x180018259  jnz     short loc_180018246
0x18001825b  mov     [rsp+8D0h+Destination], si
0x180018260  call    cs:__imp__o__errno
0x180018266  mov     [rax], r13d
0x180018269  jmp     short loc_18001827F
0x18001826b  lea     r8, [rbp+7D0h+Source]; Source
0x180018272  mov     rdx, rdi; SizeInWords
0x180018275  lea     rcx, [rsp+8D0h+Destination]; Destination
0x18001827a  call    wcscpy_s
0x18001827f  lea     rcx, [rsp+8D0h+Destination]
0x180018284  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018288  inc     rax
0x18001828b  cmp     [rcx+rax*2], si
0x18001828f  jnz     short loc_180018288
0x180018291  lea     rcx, [rsp+rax*2+8D0h+var_872]
0x180018296  lea     rax, [rsp+8D0h+Destination]
0x18001829b  cmp     rcx, rax
0x18001829e  jnb     loc_1800183F9
0x1800182a4  mov     edi, esi
0x1800182a6  test    rbx, rbx
0x1800182a9  jz      loc_180018419
0x1800182af  mov     r15d, 105h
0x1800182b5  lea     rax, [rsp+8D0h+Drive]
0x1800182ba  mov     ecx, r15d
0x1800182bd  cmp     [rax], si
0x1800182c0  jz      short loc_1800182DA
0x1800182c2  add     rax, 2
0x1800182c6  sub     rcx, 1
0x1800182ca  jnz     short loc_1800182BD
0x1800182cc  mov     [rbx], si
0x1800182cf  call    cs:__imp__o__errno
0x1800182d5  mov     [rax], r13d
0x1800182d8  jmp     short loc_1800182EA
0x1800182da  lea     r8, [rsp+8D0h+Drive]; Source
0x1800182df  mov     rdx, r15; SizeInWords
0x1800182e2  mov     rcx, rbx; Destination
0x1800182e5  call    wcscpy_s
0x1800182ea  mov     rcx, rbx
0x1800182ed  mov     rax, r15
0x1800182f0  cmp     [rcx], si
0x1800182f3  jz      short loc_180018301
0x1800182f5  add     rcx, 2
0x1800182f9  sub     rax, 1
0x1800182fd  jnz     short loc_1800182F0
0x1800182ff  jmp     short loc_180018317
0x180018301  lea     rcx, [rbp+7D0h+Dir]
0x180018308  cmp     [rcx], si
0x18001830b  jz      short loc_180018325
0x18001830d  add     rcx, 2
0x180018311  sub     rax, 1
0x180018315  jnz     short loc_180018308
0x180018317  mov     [rbx], si
0x18001831a  call    cs:__imp__o__errno
0x180018320  mov     [rax], r13d
0x180018323  jmp     short loc_180018337
0x180018325  lea     r8, [rbp+7D0h+Dir]; Source
0x18001832c  mov     rdx, r15; SizeInWords
0x18001832f  mov     rcx, rbx; Destination
0x180018332  call    wcscat_s
0x180018337  mov     rcx, rbx
0x18001833a  mov     rax, r15
0x18001833d  cmp     [rcx], si
0x180018340  jz      short loc_18001834E
0x180018342  add     rcx, 2
0x180018346  sub     rax, 1
0x18001834a  jnz     short loc_18001833D
0x18001834c  jmp     short loc_180018364
0x18001834e  lea     rcx, [rbp+7D0h+Source]
0x180018355  cmp     [rcx], si
0x180018358  jz      short loc_180018372
0x18001835a  add     rcx, 2
0x18001835e  sub     rax, 1
0x180018362  jnz     short loc_180018355
0x180018364  mov     [rbx], si
0x180018367  call    cs:__imp__o__errno
0x18001836d  mov     [rax], r13d
0x180018370  jmp     short loc_180018384
0x180018372  lea     r8, [rbp+7D0h+Source]; Source
0x180018379  mov     rdx, r15; SizeInWords
0x18001837c  mov     rcx, rbx; Destination
0x18001837f  call    wcscat_s
0x180018384  mov     rcx, rbx
0x180018387  mov     rax, r15
0x18001838a  cmp     [rcx], si
0x18001838d  jz      short loc_18001839B
0x18001838f  add     rcx, 2
0x180018393  sub     rax, 1
0x180018397  jnz     short loc_18001838A
0x180018399  jmp     short loc_1800183B1
0x18001839b  lea     rcx, [rbp+7D0h+var_240]
0x1800183a2  cmp     [rcx], si
0x1800183a5  jz      short loc_1800183BF
0x1800183a7  add     rcx, 2
0x1800183ab  sub     rax, 1
0x1800183af  jnz     short loc_1800183A2
0x1800183b1  mov     [rbx], si
0x1800183b4  call    cs:__imp__o__errno
0x1800183ba  mov     [rax], r13d
0x1800183bd  jmp     short loc_1800183D1
0x1800183bf  lea     r8, [rbp+7D0h+var_240]; Source
0x1800183c6  mov     rdx, r15; SizeInWords
0x1800183c9  mov     rcx, rbx; Destination
0x1800183cc  call    wcscat_s
0x1800183d1  mov     eax, edi
0x1800183d3  mov     rcx, [rbp+7D0h+var_30]
0x1800183da  xor     rcx, rsp; StackCookie
0x1800183dd  call    __security_check_cookie
0x1800183e2  mov     rbx, [rsp+8D0h+arg_10]
0x1800183ea  add     rsp, 8B0h
0x1800183f1  pop     r15
0x1800183f3  pop     r13
0x1800183f5  pop     rdi
0x1800183f6  pop     rsi
0x1800183f7  pop     rbp
0x1800183f8  retn
0x1800183f9  movzx   eax, word ptr [rcx]
0x1800183fc  cmp     ax, 7Eh ; '~'
0x180018400  jz      short loc_180018440
0x180018402  sub     ax, 30h ; '0'
0x180018406  cmp     ax, 9
0x18001840a  ja      loc_1800182A4
0x180018410  sub     rcx, 2
0x180018414  jmp     loc_180018296
0x180018419  call    cs:__imp__o__errno
0x18001841f  mov     ebx, 16h
0x180018424  mov     [rax], ebx
0x180018426  call    cs:__imp__o__errno
0x18001842c  mov     [rax], ebx
0x18001842e  call    cs:__imp__o__errno
0x180018434  mov     [rax], ebx
0x180018436  call    cs:__imp__o__errno
0x18001843c  mov     [rax], ebx
0x18001843e  jmp     short loc_1800183D1
0x180018440  mov     dword ptr [rcx+2], 58h ; 'X'
0x180018447  mov     edi, 1
0x18001844c  jmp     loc_1800182A6
```
