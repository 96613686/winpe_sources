# GetAppDisplayInfoFromPath(ushort const *,ushort *,uint,ushort *,uint,HICON__ * *)

- ea: `0x180015304`
- end: `0x1800154d6`
- name: `?GetAppDisplayInfoFromPath@@YAJPEBGPEAGI1IPEAPEAUHICON__@@@Z`
- size: `466`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszFile@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned int, HICON *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012704`

## callees

- `0x180008178`
- `0x180015304`
- `0x180015ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180015483`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180015483`
- `SHLWAPI!AssocQueryStringW` at `0x180015371`
- `SHLWAPI!AssocQueryStringW` at `0x180015371`
- `SHLWAPI!PathFindFileNameW` at `0x1800153e2`
- `SHLWAPI!PathFindFileNameW` at `0x1800153e2`
- `SHELL32!ExtractIconExW` at `0x18001549c`
- `SHELL32!ExtractIconExW` at `0x18001549c`
- `USER32!LoadIconW` at `0x1800154ad`
- `USER32!LoadIconW` at `0x1800154ad`
- `FirewallAPI!FwGetVersionField` at `0x180015415`
- `FirewallAPI!FwGetVersionField` at `0x180015415`

## string_xrefs

- `0x180015408`: `CompanyName`

## pseudocode

```c
__int64 __fastcall GetAppDisplayInfoFromPath(
        LPCWSTR lpszFile,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        HICON *phiconLarge)
{
  HICON *v9; // r14
  HRESULT v10; // ebp
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  const unsigned __int16 *FileNameW; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  DWORD v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = 260;
  if ( a2 && a4 )
  {
    v9 = phiconLarge;
    *a4 = 0;
    *a2 = 0;
    *v9 = 0;
    v10 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, lpszFile, 0, a2, &v17);
    if ( v10 >= 0 && wcsspnp(a2) )
    {
      v11 = (unsigned __int16 *)wcsspnp(a2);
      if ( v11 && v11 != a2 )
      {
        LODWORD(v12) = 0;
        if ( !*v11 )
          goto LABEL_13;
        do
        {
          if ( (unsigned int)v12 < 0x103 )
            a2[(unsigned int)v12] = v11[(unsigned int)v12];
          v12 = (unsigned int)(v12 + 1);
        }
        while ( v11[v12] );
        if ( (unsigned int)v12 > 0x103 )
          a2[259] = 0;
        else
LABEL_13:
          a2[(unsigned int)v12] = 0;
      }
    }
    else
    {
      FileNameW = PathFindFileNameW(lpszFile);
      v10 = StringCchCopyW(a2, 0x104u, FileNameW);
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    if ( (int)FwGetVersionField(lpszFile, L"CompanyName", a4, 0x104u) >= 0
      && (v14 = (unsigned __int16 *)wcsspnp(a4)) != 0 )
    {
      if ( v14 != a4 )
      {
        LODWORD(v15) = 0;
        if ( !*v14 )
          goto LABEL_24;
        do
        {
          if ( (unsigned int)v15 < 0x103 )
            a4[(unsigned int)v15] = v14[(unsigned int)v15];
          v15 = (unsigned int)(v15 + 1);
        }
        while ( v14[v15] );
        if ( (unsigned int)v15 > 0x103 )
          a4[259] = 0;
        else
LABEL_24:
          a4[(unsigned int)v15] = 0;
      }
    }
    else
    {
      LoadStringW(hInst, 0x546u, a4, 260);
    }
    if ( !ExtractIconExW(lpszFile, 0, v9, 0, 1u) )
      *v9 = LoadIconW(0, (LPCWSTR)0x7F00);
    return (unsigned int)v10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180015304  mov     r11, rsp
0x180015307  mov     [r11+8], rbx
0x18001530b  mov     [r11+10h], rbp
0x18001530f  mov     [r11+18h], r8d
0x180015313  push    rsi
0x180015314  push    rdi
0x180015315  push    r13
0x180015317  push    r14
0x180015319  push    r15
0x18001531b  sub     rsp, 30h
0x18001531f  xor     r15d, r15d
0x180015322  mov     [rsp+58h+arg_10], 104h
0x18001532a  mov     rdi, r9
0x18001532d  mov     rbx, rdx
0x180015330  mov     rsi, rcx
0x180015333  test    rdx, rdx
0x180015336  jz      loc_1800154BA
0x18001533c  test    r9, r9
0x18001533f  jz      loc_1800154BA
0x180015345  mov     r14, [rsp+58h+phiconLarge]
0x18001534d  lea     rax, [r11+18h]
0x180015351  mov     [r9], r15w
0x180015355  mov     r8, rcx; pszAssoc
0x180015358  mov     [rdx], r15w
0x18001535c  xor     r9d, r9d; pszExtra
0x18001535f  mov     [r11-30h], rax
0x180015363  mov     [r11-38h], rdx
0x180015367  lea     edx, [r15+4]; str
0x18001536b  lea     ecx, [rdx-2]; flags
0x18001536e  mov     [r14], r15
0x180015371  call    cs:__imp_AssocQueryStringW
0x180015377  mov     ebp, eax
0x180015379  mov     r13d, 103h
0x18001537f  test    eax, eax
0x180015381  js      short loc_1800153DF
0x180015383  mov     rcx, rbx
0x180015386  call    _wcsspnp
0x18001538b  test    rax, rax
0x18001538e  jz      short loc_1800153DF
0x180015390  mov     rcx, rbx
0x180015393  call    _wcsspnp
0x180015398  mov     r8, rax
0x18001539b  test    rax, rax
0x18001539e  jz      short loc_180015402
0x1800153a0  cmp     rax, rbx
0x1800153a3  jz      short loc_180015402
0x1800153a5  mov     edx, r15d
0x1800153a8  cmp     [rax], r15w
0x1800153ac  jz      short loc_1800153D6
0x1800153ae  cmp     edx, r13d
0x1800153b1  jnb     short loc_1800153BE
0x1800153b3  mov     ecx, edx
0x1800153b5  movzx   eax, word ptr [r8+rcx*2]
0x1800153ba  mov     [rbx+rcx*2], ax
0x1800153be  inc     edx
0x1800153c0  cmp     [r8+rdx*2], r15w
0x1800153c5  jnz     short loc_1800153AE
0x1800153c7  cmp     edx, r13d
0x1800153ca  jbe     short loc_1800153D6
0x1800153cc  mov     [rbx+206h], r15w
0x1800153d4  jmp     short loc_180015402
0x1800153d6  mov     ecx, edx
0x1800153d8  mov     [rbx+rcx*2], r15w
0x1800153dd  jmp     short loc_180015402
0x1800153df  mov     rcx, rsi; pszPath
0x1800153e2  call    cs:__imp_PathFindFileNameW
0x1800153e8  mov     edx, 104h; unsigned __int64
0x1800153ed  mov     rcx, rbx; unsigned __int16 *
0x1800153f0  mov     r8, rax; unsigned __int16 *
0x1800153f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800153f8  mov     ebp, eax
0x1800153fa  test    eax, eax
0x1800153fc  js      loc_1800154B6
0x180015402  mov     r9d, 104h
0x180015408  lea     rdx, aCompanyname; "CompanyName"
0x18001540f  mov     r8, rdi
0x180015412  mov     rcx, rsi
0x180015415  call    cs:__imp_?FwGetVersionField@@YAJPEBG0PEAGI@Z; FwGetVersionField(ushort const *,ushort const *,ushort *,uint)
0x18001541b  test    eax, eax
0x18001541d  js      short loc_18001546E
0x18001541f  mov     rcx, rdi
0x180015422  call    _wcsspnp
0x180015427  mov     r8, rax
0x18001542a  test    rax, rax
0x18001542d  jz      short loc_18001546E
0x18001542f  cmp     rax, rdi
0x180015432  jz      short loc_180015489
0x180015434  mov     edx, r15d
0x180015437  cmp     [rax], r15w
0x18001543b  jz      short loc_180015465
0x18001543d  cmp     edx, r13d
0x180015440  jnb     short loc_18001544D
0x180015442  mov     ecx, edx
0x180015444  movzx   eax, word ptr [r8+rcx*2]
0x180015449  mov     [rdi+rcx*2], ax
0x18001544d  inc     edx
0x18001544f  cmp     [r8+rdx*2], r15w
0x180015454  jnz     short loc_18001543D
0x180015456  cmp     edx, r13d
0x180015459  jbe     short loc_180015465
0x18001545b  mov     [rdi+206h], r15w
0x180015463  jmp     short loc_180015489
0x180015465  mov     ecx, edx
0x180015467  mov     [rdi+rcx*2], r15w
0x18001546c  jmp     short loc_180015489
0x18001546e  mov     rcx, cs:hInst; hInstance
0x180015475  mov     r9d, 104h; cchBufferMax
0x18001547b  mov     r8, rdi; lpBuffer
0x18001547e  mov     edx, 546h; uID
0x180015483  call    cs:__imp_LoadStringW
0x180015489  xor     r9d, r9d; phiconSmall
0x18001548c  mov     [rsp+58h+nIcons], 1; nIcons
0x180015494  mov     r8, r14; phiconLarge
0x180015497  xor     edx, edx; nIconIndex
0x180015499  mov     rcx, rsi; lpszFile
0x18001549c  call    cs:__imp_ExtractIconExW
0x1800154a2  test    eax, eax
0x1800154a4  jnz     short loc_1800154B6
0x1800154a6  mov     edx, 7F00h; lpIconName
0x1800154ab  xor     ecx, ecx; hInstance
0x1800154ad  call    cs:__imp_LoadIconW
0x1800154b3  mov     [r14], rax
0x1800154b6  mov     eax, ebp
0x1800154b8  jmp     short loc_1800154BF
0x1800154ba  mov     eax, 80070057h
0x1800154bf  mov     rbx, [rsp+58h+arg_0]
0x1800154c4  mov     rbp, [rsp+58h+arg_8]
0x1800154c9  add     rsp, 30h
0x1800154cd  pop     r15
0x1800154cf  pop     r14
0x1800154d1  pop     r13
0x1800154d3  pop     rdi
0x1800154d4  pop     rsi
0x1800154d5  retn
```
