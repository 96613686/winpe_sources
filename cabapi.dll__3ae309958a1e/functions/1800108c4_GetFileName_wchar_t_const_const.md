# GetFileName(wchar_t const * const)

- ea: `0x1800108c4`
- end: `0x1800109cc`
- name: `?GetFileName@@YAPEB_WQEB_W@Z`
- size: `264`
- prototype: `const wchar_t *__fastcall(const wchar_t *FullPath)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001084c`

## callees

- `0x180001540`
- `0x180001f8e`
- `0x180001fd6`
- `0x1800108c4`

## pseudocode

```c
const wchar_t *__fastcall GetFileName(const wchar_t *FullPath)
{
  int *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  wchar_t Filename[256]; // [rsp+50h] [rbp-418h] BYREF
  wchar_t Ext[256]; // [rsp+250h] [rbp-218h] BYREF

  v2 = &dword_1800180D4;
  memset_0(Filename, 0, sizeof(Filename));
  memset_0(Ext, 0, sizeof(Ext));
  if ( FullPath && *FullPath && !wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u) )
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( Filename[v4] );
    v5 = -1;
    do
      ++v5;
    while ( Ext[v5] );
    do
      ++v3;
    while ( FullPath[v3] );
    return &FullPath[v3 - v5 - v4];
  }
  return (const wchar_t *)v2;
}

```

## disassembly

```asm
0x1800108c4  mov     [rsp+arg_8], rbx
0x1800108c9  mov     [rsp+arg_10], rsi
0x1800108ce  push    rdi
0x1800108cf  sub     rsp, 460h
0x1800108d6  mov     rax, cs:__security_cookie
0x1800108dd  xor     rax, rsp
0x1800108e0  mov     [rsp+468h+var_18], rax
0x1800108e8  mov     rbx, rcx
0x1800108eb  lea     rdi, dword_1800180D4
0x1800108f2  mov     esi, 200h
0x1800108f7  lea     rcx, [rsp+468h+var_418]; void *
0x1800108fc  mov     r8d, esi; Size
0x1800108ff  xor     edx, edx; Val
0x180010901  call    memset_0
0x180010906  mov     r8d, esi; Size
0x180010909  lea     rcx, [rsp+468h+var_218]; void *
0x180010911  xor     edx, edx; Val
0x180010913  call    memset_0
0x180010918  xor     esi, esi
0x18001091a  test    rbx, rbx
0x18001091d  jz      loc_1800109A4
0x180010923  cmp     [rbx], si
0x180010926  jz      short loc_1800109A4
0x180010928  mov     ecx, 100h
0x18001092d  lea     rax, [rsp+468h+var_218]
0x180010935  mov     [rsp+468h+ExtCount], rcx; ExtCount
0x18001093a  xor     r9d, r9d; Dir
0x18001093d  mov     [rsp+468h+Ext], rax; Ext
0x180010942  xor     r8d, r8d; DriveCount
0x180010945  mov     [rsp+468h+FilenameCount], rcx; FilenameCount
0x18001094a  lea     rax, [rsp+468h+var_418]
0x18001094f  mov     [rsp+468h+Filename], rax; Filename
0x180010954  xor     edx, edx; Drive
0x180010956  mov     rcx, rbx; FullPath
0x180010959  mov     [rsp+468h+DirCount], rsi; DirCount
0x18001095e  call    _wsplitpath_s
0x180010963  test    eax, eax
0x180010965  jnz     short loc_1800109A4
0x180010967  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001096b  lea     rdx, [rsp+468h+var_418]
0x180010970  mov     rcx, rax
0x180010973  inc     rcx
0x180010976  cmp     [rdx+rcx*2], si
0x18001097a  jnz     short loc_180010973
0x18001097c  lea     r8, [rsp+468h+var_218]
0x180010984  mov     rdx, rax
0x180010987  inc     rdx
0x18001098a  cmp     [r8+rdx*2], si
0x18001098f  jnz     short loc_180010987
0x180010991  inc     rax
0x180010994  cmp     [rbx+rax*2], si
0x180010998  jnz     short loc_180010991
0x18001099a  sub     rax, rdx
0x18001099d  sub     rax, rcx
0x1800109a0  lea     rdi, [rbx+rax*2]
0x1800109a4  mov     rax, rdi
0x1800109a7  mov     rcx, [rsp+468h+var_18]
0x1800109af  xor     rcx, rsp; StackCookie
0x1800109b2  call    __security_check_cookie
0x1800109b7  lea     r11, [rsp+468h+var_8]
0x1800109bf  mov     rbx, [r11+18h]
0x1800109c3  mov     rsi, [r11+20h]
0x1800109c7  mov     rsp, r11
0x1800109ca  pop     rdi
0x1800109cb  retn
```
