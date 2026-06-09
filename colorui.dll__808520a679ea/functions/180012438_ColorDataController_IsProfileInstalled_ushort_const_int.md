# ColorDataController::IsProfileInstalled(ushort const *,int *)

- ea: `0x180012438`
- end: `0x180012521`
- name: `?IsProfileInstalled@ColorDataController@@QEBAJPEBGPEAH@Z`
- size: `233`
- prototype: `__int64 __fastcall(ColorDataController *this, WCHAR *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000bd60`
- `0x18000f074`
- `0x180016a70`

## callees

- `0x180012438`
- `0x180014284`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800124e3`
- `KERNEL32!GetFileAttributesW` at `0x1800124e3`
- `USER32!CharPrevW` at `0x18001249a`
- `USER32!CharPrevW` at `0x18001249a`
- `USER32!CharNextW` at `0x1800124b3`
- `USER32!CharNextW` at `0x1800124b3`

## pseudocode

```c
__int64 __fastcall ColorDataController::IsProfileInstalled(ColorDataController *this, WCHAR *a2, int *a3)
{
  __int64 v5; // rax
  WCHAR *v6; // rax
  unsigned __int16 *v7; // r8
  WCHAR v8; // cx
  signed int ColorProfileFullPath; // ebx
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  *a3 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( !(_DWORD)v5 )
    return (unsigned int)-2147024809;
  v6 = &a2[(unsigned int)v5];
  while ( 1 )
  {
    v6 = CharPrevW(a2, v6);
    v8 = *v6;
    if ( *v6 == 92 )
      break;
    if ( a2 >= v6 )
      goto LABEL_10;
  }
  v6 = CharNextW(v6);
  v8 = *v6;
LABEL_10:
  if ( v8 && v6 && *v6 )
  {
    ColorProfileFullPath = Helper::GetColorProfileFullPath((Helper *)v6, FileName, v7);
    if ( ColorProfileFullPath >= 0 )
      *a3 = GetFileAttributesW(FileName) != -1;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ColorProfileFullPath;
}

```

## disassembly

```asm
0x180012438  mov     [rsp+arg_0], rbx
0x18001243d  mov     [rsp+arg_18], rsi
0x180012442  push    rdi
0x180012443  sub     rsp, 240h
0x18001244a  mov     rax, cs:__security_cookie
0x180012451  xor     rax, rsp
0x180012454  mov     [rsp+248h+var_18], rax
0x18001245c  mov     rdi, r8
0x18001245f  lea     rcx, [rsp+248h+FileName]; void *
0x180012464  mov     rbx, rdx
0x180012467  mov     r8d, 208h; Size
0x18001246d  xor     edx, edx; Val
0x18001246f  call    memset_0
0x180012474  xor     esi, esi
0x180012476  mov     [rdi], esi
0x180012478  test    rbx, rbx
0x18001247b  jz      short loc_1800124F5
0x18001247d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012481  inc     rax
0x180012484  cmp     [rbx+rax*2], si
0x180012488  jnz     short loc_180012481
0x18001248a  test    eax, eax
0x18001248c  jz      short loc_1800124F5
0x18001248e  mov     eax, eax
0x180012490  lea     rax, [rbx+rax*2]
0x180012494  mov     rdx, rax; lpszCurrent
0x180012497  mov     rcx, rbx; lpszStart
0x18001249a  call    cs:__imp_CharPrevW
0x1800124a0  movzx   ecx, word ptr [rax]
0x1800124a3  cmp     cx, 5Ch ; '\'
0x1800124a7  jz      short loc_1800124B0
0x1800124a9  cmp     rbx, rax
0x1800124ac  jb      short loc_180012494
0x1800124ae  jmp     short loc_1800124BC
0x1800124b0  mov     rcx, rax; lpsz
0x1800124b3  call    cs:__imp_CharNextW
0x1800124b9  movzx   ecx, word ptr [rax]
0x1800124bc  test    cx, cx
0x1800124bf  jz      short loc_1800124F5
0x1800124c1  test    rax, rax
0x1800124c4  jz      short loc_1800124F5
0x1800124c6  cmp     [rax], si
0x1800124c9  jz      short loc_1800124F5
0x1800124cb  lea     rdx, [rsp+248h+FileName]; unsigned __int16 *
0x1800124d0  mov     rcx, rax; this
0x1800124d3  call    ?GetColorProfileFullPath@Helper@@YAJPEBGPEAGK@Z; Helper::GetColorProfileFullPath(ushort const *,ushort *,ulong)
0x1800124d8  mov     ebx, eax
0x1800124da  test    eax, eax
0x1800124dc  js      short loc_1800124FA
0x1800124de  lea     rcx, [rsp+248h+FileName]; lpFileName
0x1800124e3  call    cs:__imp_GetFileAttributesW
0x1800124e9  mov     ecx, esi
0x1800124eb  cmp     eax, 0FFFFFFFFh
0x1800124ee  setnz   cl
0x1800124f1  mov     [rdi], ecx
0x1800124f3  jmp     short loc_1800124FA
0x1800124f5  mov     ebx, 80070057h
0x1800124fa  mov     eax, ebx
0x1800124fc  mov     rcx, [rsp+248h+var_18]
0x180012504  xor     rcx, rsp; StackCookie
0x180012507  call    __security_check_cookie
0x18001250c  lea     r11, [rsp+248h+var_8]
0x180012514  mov     rbx, [r11+10h]
0x180012518  mov     rsi, [r11+28h]
0x18001251c  mov     rsp, r11
0x18001251f  pop     rdi
0x180012520  retn
```
