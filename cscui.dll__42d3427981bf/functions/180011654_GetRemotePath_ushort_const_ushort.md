# GetRemotePath(ushort const *,ushort * *)

- ea: `0x180011654`
- end: `0x1800117ee`
- name: `?GetRemotePath@@YAJPEBGPEAPEAG@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004b80`
- `0x180007dd4`
- `0x18002bae4`
- `0x18003b254`

## callees

- `0x180003d60`
- `0x180011654`
- `0x18001182c`
- `0x180011aa4`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180011799`
- `SHLWAPI!PathIsUNCW` at `0x180011799`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800117b8`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800117b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011719`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011719`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800116ad`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800116ad`
- `MPR!WNetGetConnectionW` at `0x1800116d3`
- `MPR!WNetGetConnectionW` at `0x1800116d3`

## pseudocode

```c
__int64 __fastcall GetRemotePath(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  WCHAR v4; // ax
  signed int ConnectionW; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned int v12; // [rsp+28h] [rbp-D8h]
  DWORD nLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR RootPathName; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ah] [rbp-B6h]
  WCHAR RemoteName[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  if ( a1[1] == 58 )
  {
    v4 = *a1;
    v17 = 58;
    RootPathName = v4;
    if ( GetDriveTypeW(&RootPathName) == 4 )
    {
      nLength = 260;
      ConnectionW = WNetGetConnectionW(&RootPathName, RemoteName, &nLength);
      v6 = ConnectionW;
      if ( ConnectionW )
      {
        if ( ConnectionW == 2250 )
          return 1;
        if ( ConnectionW > 0 )
          v6 = (unsigned __int16)ConnectionW | 0x80070000;
      }
      else
      {
        v7 = -1;
        v8 = -1;
        do
          ++v8;
        while ( RemoteName[v8] );
        do
          ++v7;
        while ( a1[v7 + 2] );
        v9 = v8 + v7 + 1;
        v14 = v9;
        v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v9);
        *a2 = v10;
        if ( v10 )
        {
          v15 = 0;
          StringCchCopyExW(v10, v9, RemoteName, &v15, &v14, v12);
          v6 = StringCchCopyW(v15, v14, a1 + 2);
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = 1;
    }
    if ( !v6 )
LABEL_20:
      PathRemoveBackslashW(*a2);
  }
  else
  {
    v6 = -2147024735;
    if ( PathIsUNCW(a1) )
    {
      if ( !LocalAllocString(a2, a1) )
        return (unsigned int)-2147024882;
      v6 = 0;
      goto LABEL_20;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180011654  mov     [rsp-8+arg_10], rbx
0x180011659  mov     [rsp-8+arg_18], rsi
0x18001165e  push    rbp
0x18001165f  push    rdi
0x180011660  push    r14
0x180011662  lea     rbp, [rsp-170h]
0x18001166a  sub     rsp, 270h
0x180011671  mov     rax, cs:__security_cookie
0x180011678  xor     rax, rsp
0x18001167b  mov     [rbp+180h+var_20], rax
0x180011682  xor     r14d, r14d
0x180011685  mov     rdi, rcx
0x180011688  mov     [rdx], r14
0x18001168b  mov     rsi, rdx
0x18001168e  lea     ecx, [r14+3Ah]
0x180011692  cmp     [rdi+2], cx
0x180011696  jnz     loc_180011791
0x18001169c  movzx   eax, word ptr [rdi]
0x18001169f  mov     [rsp+280h+var_236], ecx
0x1800116a3  lea     rcx, [rsp+280h+RootPathName]; lpRootPathName
0x1800116a8  mov     [rsp+280h+RootPathName], ax
0x1800116ad  call    cs:__imp_GetDriveTypeW
0x1800116b3  cmp     eax, 4
0x1800116b6  jnz     loc_180011786
0x1800116bc  lea     r8, [rsp+280h+nLength]; lpnLength
0x1800116c1  mov     [rsp+280h+nLength], 104h
0x1800116c9  lea     rdx, [rsp+280h+RemoteName]; lpRemoteName
0x1800116ce  lea     rcx, [rsp+280h+RootPathName]; lpLocalName
0x1800116d3  call    cs:__imp_WNetGetConnectionW
0x1800116d9  mov     ebx, eax
0x1800116db  test    eax, eax
0x1800116dd  jnz     loc_180011769
0x1800116e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800116e7  lea     rdx, [rsp+280h+RemoteName]
0x1800116ec  mov     rcx, rax
0x1800116ef  inc     rcx
0x1800116f2  cmp     [rdx+rcx*2], r14w
0x1800116f7  jnz     short loc_1800116EF
0x1800116f9  inc     rax
0x1800116fc  cmp     [rdi+rax*2+4], r14w
0x180011702  jnz     short loc_1800116F9
0x180011704  lea     rbx, [rax+1]
0x180011708  add     rbx, rcx
0x18001170b  mov     ecx, 40h ; '@'; uFlags
0x180011710  mov     [rsp+280h+var_248], rbx
0x180011715  lea     rdx, [rbx+rbx]; uBytes
0x180011719  call    cs:__imp_LocalAlloc
0x18001171f  mov     [rsi], rax
0x180011722  test    rax, rax
0x180011725  jz      short loc_180011762
0x180011727  lea     rcx, [rsp+280h+var_248]
0x18001172c  mov     [rsp+280h+var_240], r14
0x180011731  mov     [rsp+280h+var_260], rcx; unsigned __int64 *
0x180011736  lea     r9, [rsp+280h+var_240]; unsigned __int16 **
0x18001173b  mov     rcx, rax; unsigned __int16 *
0x18001173e  lea     r8, [rsp+280h+RemoteName]; unsigned __int16 *
0x180011743  mov     rdx, rbx; unsigned __int64
0x180011746  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001174b  mov     rdx, [rsp+280h+var_248]; unsigned __int64
0x180011750  lea     r8, [rdi+4]; unsigned __int16 *
0x180011754  mov     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x180011759  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001175e  mov     ebx, eax
0x180011760  jmp     short loc_18001178B
0x180011762  mov     ebx, 8007000Eh
0x180011767  jmp     short loc_18001178B
0x180011769  cmp     eax, 8CAh
0x18001176e  jnz     short loc_180011777
0x180011770  mov     ebx, 1
0x180011775  jmp     short loc_1800117C5
0x180011777  test    eax, eax
0x180011779  jle     short loc_18001178B
0x18001177b  movzx   ebx, ax
0x18001177e  or      ebx, 80070000h
0x180011784  jmp     short loc_18001178B
0x180011786  mov     ebx, 1
0x18001178b  test    ebx, ebx
0x18001178d  jnz     short loc_1800117C5
0x18001178f  jmp     short loc_1800117B5
0x180011791  mov     rcx, rdi; pszPath
0x180011794  mov     ebx, 800700A1h
0x180011799  call    cs:__imp_PathIsUNCW
0x18001179f  test    eax, eax
0x1800117a1  jz      short loc_1800117C5
0x1800117a3  mov     rdx, rdi; unsigned __int16 *
0x1800117a6  mov     rcx, rsi; unsigned __int16 **
0x1800117a9  call    ?LocalAllocString@@YAHPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x1800117ae  test    eax, eax
0x1800117b0  jz      short loc_1800117C0
0x1800117b2  mov     ebx, r14d
0x1800117b5  mov     rcx, [rsi]; pszPath
0x1800117b8  call    cs:__imp_PathRemoveBackslashW
0x1800117be  jmp     short loc_1800117C5
0x1800117c0  mov     ebx, 8007000Eh
0x1800117c5  mov     eax, ebx
0x1800117c7  mov     rcx, [rbp+180h+var_20]
0x1800117ce  xor     rcx, rsp; StackCookie
0x1800117d1  call    __security_check_cookie
0x1800117d6  lea     r11, [rsp+280h+var_10]
0x1800117de  mov     rbx, [r11+30h]
0x1800117e2  mov     rsi, [r11+38h]
0x1800117e6  mov     rsp, r11
0x1800117e9  pop     r14
0x1800117eb  pop     rdi
0x1800117ec  pop     rbp
0x1800117ed  retn
```
