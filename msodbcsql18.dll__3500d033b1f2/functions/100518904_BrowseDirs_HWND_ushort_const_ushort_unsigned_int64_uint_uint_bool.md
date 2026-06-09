# BrowseDirs(HWND__ *,ushort const *,ushort *,unsigned __int64,uint,uint,bool)

- ea: `0x100518904`
- end: `0x100518abb`
- name: `?BrowseDirs@@YAHPEAUHWND__@@PEBGPEAG_KII_N@Z`
- size: `439`
- prototype: `int(HWND, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1005172d0`
- `0x1005190b0`

## callees

- `0x1004056a8`
- `0x100518904`
- `0x100548140`
- `0x100548210`
- `0x100548a18`

## import_xrefs

- `USER32!LoadStringW` at `0x10051899b`
- `USER32!LoadStringW` at `0x1005189b8`
- `USER32!LoadStringW` at `0x10051899b`
- `USER32!LoadStringW` at `0x1005189b8`
- `COMDLG32!GetSaveFileNameW` at `0x100518a70`
- `COMDLG32!GetSaveFileNameW` at `0x100518a70`
- `COMDLG32!GetOpenFileNameW` at `0x100518a78`
- `COMDLG32!GetOpenFileNameW` at `0x100518a78`

## pseudocode

```c
__int64 __fastcall BrowseDirs(HWND a1, char *a2, unsigned __int16 *a3, unsigned __int64 a4, UINT uID, UINT a6, bool a7)
{
  signed __int64 v8; // rdx
  unsigned __int16 *v10; // r8
  __int64 v12; // r9
  unsigned __int16 v13; // ax
  unsigned __int16 *v14; // rax
  HINSTANCE v15; // rcx
  bool v16; // sf
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  BOOL SaveFileNameW; // eax
  unsigned int v22; // ebx
  tagOFNW v24; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR v25[200]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[104]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v27[264]; // [rsp+320h] [rbp+220h] BYREF

  v8 = a2 - (char *)v27;
  v10 = v27;
  v12 = 261;
  do
  {
    if ( v12 == -2147483385 )
      break;
    v13 = *(unsigned __int16 *)((char *)v10 + v8);
    if ( !v13 )
      break;
    *v10++ = v13;
    --v12;
  }
  while ( v12 );
  v14 = v10 - 1;
  v15 = g_hinstance_language;
  if ( v12 )
    v14 = v10;
  *v14 = 0;
  LoadStringW(v15, uID, Buffer, 100);
  v17 = LoadStringW(g_hinstance_language, a6, v25, 200) - 1;
  v16 = v17 < 0;
  v19 = v17;
  while ( !v16 )
  {
    if ( v25[v19] == 124 )
    {
      if ( v19 >= 0xC8 )
        _report_rangecheckfailure(v19, v18);
      v25[v19] = 0;
    }
    v16 = (--v19 & 0x8000000000000000uLL) != 0LL;
  }
  memset_0(&v24, 0, sizeof(v24));
  v24.hInstance = (HINSTANCE)g_hinstance;
  v24.lpstrFilter = v25;
  v20 = -1;
  v24.lStructSize = 152;
  v24.hwndOwner = a1;
  do
    ++v20;
  while ( v25[v20] );
  v24.nMaxFile = 261;
  v24.lpstrDefExt = &v25[v20 + 3];
  v24.lpstrInitialDir = 0;
  v24.lpstrFile = v27;
  v24.lpstrTitle = Buffer;
  v24.Flags = 83980;
  if ( a7 )
    SaveFileNameW = GetSaveFileNameW(&v24);
  else
    SaveFileNameW = GetOpenFileNameW(&v24);
  v22 = SaveFileNameW;
  if ( SaveFileNameW )
    StringCchCopyW(a3, a4, v27);
  return v22;
}

```

## disassembly

```asm
0x100518904  push    rbp
0x100518906  push    rbx
0x100518907  push    rsi
0x100518908  push    rdi
0x100518909  push    r15
0x10051890b  lea     rbp, [rsp-440h]
0x100518913  sub     rsp, 540h
0x10051891a  mov     rax, cs:__security_cookie
0x100518921  xor     rax, rsp
0x100518924  mov     [rbp+460h+var_30], rax
0x10051892b  lea     rax, [rbp+460h+var_240]
0x100518932  mov     rsi, r9
0x100518935  sub     rdx, rax
0x100518938  mov     rdi, r8
0x10051893b  xor     r15d, r15d
0x10051893e  lea     r8, [rbp+460h+var_240]
0x100518945  mov     rbx, rcx
0x100518948  mov     r9d, 105h
0x10051894e  lea     rax, [r9+7FFFFEF9h]
0x100518955  test    rax, rax
0x100518958  jz      short loc_100518972
0x10051895a  movzx   eax, word ptr [rdx+r8]
0x10051895f  test    ax, ax
0x100518962  jz      short loc_100518972
0x100518964  mov     [r8], ax
0x100518968  add     r8, 2
0x10051896c  sub     r9, 1
0x100518970  jnz     short loc_10051894E
0x100518972  mov     edx, [rbp+460h+uID]; uID
0x100518978  lea     rax, [r8-2]
0x10051897c  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x100518983  test    r9, r9
0x100518986  mov     r9d, 64h ; 'd'; cchBufferMax
0x10051898c  cmovnz  rax, r8
0x100518990  lea     r8, [rbp+460h+Buffer]; lpBuffer
0x100518997  mov     [rax], r15w
0x10051899b  call    cs:__imp_LoadStringW
0x1005189a1  mov     edx, [rbp+460h+arg_28]; uID
0x1005189a7  lea     r8, [rbp+460h+var_4A0]; lpBuffer
0x1005189ab  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1005189b2  mov     r9d, 0C8h; cchBufferMax
0x1005189b8  call    cs:__imp_LoadStringW
0x1005189be  sub     eax, 1
0x1005189c1  movsxd  rcx, eax
0x1005189c4  js      short loc_1005189E7
0x1005189c6  cmp     [rbp+rcx*2+460h+var_4A0], 7Ch ; '|'
0x1005189cc  jnz     short loc_1005189E1
0x1005189ce  cmp     rcx, 0C8h
0x1005189d5  jnb     loc_100518AB5
0x1005189db  mov     [rbp+rcx*2+460h+var_4A0], r15w
0x1005189e1  sub     rcx, 1
0x1005189e5  jmp     short loc_1005189C4
0x1005189e7  xor     edx, edx; Val
0x1005189e9  lea     rcx, [rsp+560h+var_540]; void *
0x1005189ee  mov     r8d, 98h; Size
0x1005189f4  call    memset_0
0x1005189f9  mov     rax, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance
0x100518a00  lea     rcx, [rbp+460h+var_4A0]
0x100518a04  mov     [rsp+560h+var_540.hInstance], rax
0x100518a09  lea     rax, [rbp+460h+var_4A0]
0x100518a0d  mov     [rsp+560h+var_540.lpstrFilter], rax
0x100518a12  or      rax, 0FFFFFFFFFFFFFFFFh
0x100518a16  mov     [rsp+560h+var_540.lStructSize], 98h
0x100518a1e  mov     [rsp+560h+var_540.hwndOwner], rbx
0x100518a23  inc     rax
0x100518a26  cmp     [rcx+rax*2], r15w
0x100518a2b  jnz     short loc_100518A23
0x100518a2d  lea     rax, [rbp+rax*2+460h+var_49A]
0x100518a32  mov     [rsp+560h+var_540.nMaxFile], 105h
0x100518a3a  lea     rcx, [rsp+560h+var_540]; LPOPENFILENAMEW
0x100518a3f  mov     [rbp+460h+var_540.lpstrDefExt], rax
0x100518a43  lea     rax, [rbp+460h+var_240]
0x100518a4a  mov     [rsp+560h+var_540.lpstrInitialDir], r15
0x100518a4f  mov     [rsp+560h+var_540.lpstrFile], rax
0x100518a54  lea     rax, [rbp+460h+Buffer]
0x100518a5b  mov     [rsp+560h+var_540.lpstrTitle], rax
0x100518a60  mov     [rbp+460h+var_540.Flags], 1480Ch
0x100518a67  cmp     [rbp+460h+arg_30], r15b
0x100518a6e  jz      short loc_100518A78
0x100518a70  call    cs:__imp_GetSaveFileNameW
0x100518a76  jmp     short loc_100518A7E
0x100518a78  call    cs:__imp_GetOpenFileNameW
0x100518a7e  mov     ebx, eax
0x100518a80  test    eax, eax
0x100518a82  jz      short loc_100518A96
0x100518a84  lea     r8, [rbp+460h+var_240]; unsigned __int16 *
0x100518a8b  mov     rdx, rsi; unsigned __int64
0x100518a8e  mov     rcx, rdi; unsigned __int16 *
0x100518a91  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x100518a96  mov     eax, ebx
0x100518a98  mov     rcx, [rbp+460h+var_30]
0x100518a9f  xor     rcx, rsp; StackCookie
0x100518aa2  call    __security_check_cookie
0x100518aa7  add     rsp, 540h
0x100518aae  pop     r15
0x100518ab0  pop     rdi
0x100518ab1  pop     rsi
0x100518ab2  pop     rbx
0x100518ab3  pop     rbp
0x100518ab4  retn
0x100518ab5  call    __report_rangecheckfailure
```
