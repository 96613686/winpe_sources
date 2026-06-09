# FakePdbName(_IMGHLP_DEBUG_DATA *)

- ea: `0x1800190e0`
- end: `0x180019220`
- name: `?FakePdbName@@YAHPEAU_IMGHLP_DEBUG_DATA@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(struct _IMGHLP_DEBUG_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800032a8`

## callees

- `0x1800190e0`
- `0x1800273f0`
- `0x1800273fc`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001915c`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001915c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001918b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800191dc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001918b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800191dc`

## pseudocode

```c
__int64 __fastcall FakePdbName(struct _IMGHLP_DEBUG_DATA *a1)
{
  wchar_t *v1; // rbx
  const wchar_t *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  wchar_t *v6; // rax
  __int64 v7; // rcx
  const wchar_t *v8; // rdx
  const wchar_t *v9; // r8
  __int64 v10; // r9
  wchar_t *v11; // rcx
  __int64 v12; // rax
  wchar_t Source[256]; // [rsp+50h] [rbp-218h] BYREF

  v1 = (wchar_t *)((char *)a1 + 2260);
  if ( *((_WORD *)a1 + 1130) )
    return 0;
  if ( *((_DWORD *)a1 + 558) )
    return 0;
  v2 = (const wchar_t *)((char *)a1 + 3604);
  if ( !*v2 )
    return 0;
  _wsplitpath_s(v2, 0, 0, 0, 0, Source, 0x100u, 0, 0);
  if ( !Source[0] )
    return 0;
  v6 = Source;
  v7 = 261;
  while ( *v6 )
  {
    ++v6;
    if ( !--v7 )
    {
      *v1 = 0;
      *(_DWORD *)_o__errno(0, v3, v4, v5) = 34;
      goto LABEL_10;
    }
  }
  wcscpy_s(v1, 0x105u, Source);
LABEL_10:
  v11 = v1;
  v12 = 261;
  while ( *v1 )
  {
    ++v1;
    if ( !--v12 )
    {
LABEL_17:
      *v11 = 0;
      *(_DWORD *)_o__errno(v11, v8, v9, v10) = 34;
      return 1;
    }
  }
  v9 = L".pdb";
  v8 = L".pdb";
  while ( *v8 )
  {
    ++v8;
    if ( !--v12 )
      goto LABEL_17;
  }
  wcscat_s(v11, 0x105u, L".pdb");
  return 1;
}

```

## disassembly

```asm
0x1800190e0  mov     [rsp+arg_8], rbx
0x1800190e5  mov     [rsp+arg_10], rsi
0x1800190ea  push    rdi
0x1800190eb  sub     rsp, 260h
0x1800190f2  mov     rax, cs:__security_cookie
0x1800190f9  xor     rax, rsp
0x1800190fc  mov     [rsp+268h+var_18], rax
0x180019104  lea     rbx, [rcx+8D4h]
0x18001910b  xor     edi, edi
0x18001910d  cmp     [rbx], di
0x180019110  jnz     loc_18001921C
0x180019116  cmp     [rcx+8B8h], edi
0x18001911c  jnz     loc_18001921C
0x180019122  add     rcx, 0E14h; FullPath
0x180019129  cmp     [rcx], di
0x18001912c  jz      loc_18001921C
0x180019132  mov     [rsp+268h+ExtCount], rdi; ExtCount
0x180019137  lea     rax, [rsp+268h+Source]
0x18001913c  mov     [rsp+268h+Ext], rdi; Ext
0x180019141  xor     r9d, r9d; Dir
0x180019144  mov     [rsp+268h+FilenameCount], 100h; FilenameCount
0x18001914d  xor     r8d, r8d; DriveCount
0x180019150  mov     [rsp+268h+Filename], rax; Filename
0x180019155  xor     edx, edx; Drive
0x180019157  mov     [rsp+268h+DirCount], rdi; DirCount
0x18001915c  call    cs:__imp__wsplitpath_s
0x180019162  cmp     [rsp+268h+Source], di
0x180019167  jz      loc_18001921C
0x18001916d  mov     esi, 105h
0x180019172  lea     rax, [rsp+268h+Source]
0x180019177  mov     ecx, esi
0x180019179  cmp     [rax], di
0x18001917c  jz      short loc_180019199
0x18001917e  add     rax, 2
0x180019182  sub     rcx, 1
0x180019186  jnz     short loc_180019179
0x180019188  mov     [rbx], di
0x18001918b  call    cs:__imp__o__errno
0x180019191  mov     dword ptr [rax], 22h ; '"'
0x180019197  jmp     short loc_1800191A9
0x180019199  lea     r8, [rsp+268h+Source]; Source
0x18001919e  mov     rdx, rsi; SizeInWords
0x1800191a1  mov     rcx, rbx; Destination
0x1800191a4  call    wcscpy_s
0x1800191a9  mov     rcx, rbx; Destination
0x1800191ac  mov     rax, rsi
0x1800191af  cmp     [rbx], di
0x1800191b2  jz      short loc_1800191C0
0x1800191b4  add     rbx, 2
0x1800191b8  sub     rax, 1
0x1800191bc  jnz     short loc_1800191AF
0x1800191be  jmp     short loc_1800191D9
0x1800191c0  lea     r8, aPdb_3; ".pdb"
0x1800191c7  mov     rdx, r8
0x1800191ca  cmp     [rdx], di
0x1800191cd  jz      short loc_1800191EA
0x1800191cf  add     rdx, 2
0x1800191d3  sub     rax, 1
0x1800191d7  jnz     short loc_1800191CA
0x1800191d9  mov     [rcx], di
0x1800191dc  call    cs:__imp__o__errno
0x1800191e2  mov     dword ptr [rax], 22h ; '"'
0x1800191e8  jmp     short loc_1800191F2
0x1800191ea  mov     rdx, rsi; SizeInWords
0x1800191ed  call    wcscat_s
0x1800191f2  mov     eax, 1
0x1800191f7  mov     rcx, [rsp+268h+var_18]
0x1800191ff  xor     rcx, rsp; StackCookie
0x180019202  call    __security_check_cookie
0x180019207  lea     r11, [rsp+268h+var_8]
0x18001920f  mov     rbx, [r11+18h]
0x180019213  mov     rsi, [r11+20h]
0x180019217  mov     rsp, r11
0x18001921a  pop     rdi
0x18001921b  retn
0x18001921c  xor     eax, eax
0x18001921e  jmp     short loc_1800191F7
```
