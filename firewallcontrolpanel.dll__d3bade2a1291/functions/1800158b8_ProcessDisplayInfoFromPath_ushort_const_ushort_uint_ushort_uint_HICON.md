# ProcessDisplayInfoFromPath(ushort const *,ushort *,uint,ushort *,uint,HICON__ * *)

- ea: `0x1800158b8`
- end: `0x180015a76`
- name: `?ProcessDisplayInfoFromPath@@YAJPEBGPEAGI1IPEAPEAUHICON__@@@Z`
- size: `446`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszFile@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned int, HICON *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013270`

## callees

- `0x180008178`
- `0x1800158b8`
- `0x180015ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180015a23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180015a23`
- `SHLWAPI!AssocQueryStringW` at `0x180015925`
- `SHLWAPI!AssocQueryStringW` at `0x180015925`
- `SHLWAPI!PathFindFileNameW` at `0x18001598c`
- `SHLWAPI!PathFindFileNameW` at `0x18001598c`
- `SHELL32!ExtractIconExW` at `0x180015a3c`
- `SHELL32!ExtractIconExW` at `0x180015a3c`
- `USER32!LoadIconW` at `0x180015a4d`
- `USER32!LoadIconW` at `0x180015a4d`
- `FirewallAPI!FwGetVersionField` at `0x1800159bf`
- `FirewallAPI!FwGetVersionField` at `0x1800159bf`

## string_xrefs

- `0x1800159b2`: `CompanyName`

## pseudocode

```c
__int64 __fastcall ProcessDisplayInfoFromPath(
        LPCWSTR lpszFile,
        unsigned __int16 *a2,
        DWORD a3,
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

  v17 = a3;
  if ( a2 && a4 )
  {
    v9 = phiconLarge;
    *a4 = 0;
    *a2 = 0;
    *v9 = 0;
    v17 = 260;
    v10 = AssocQueryStringW(2u, ASSOCSTR_FRIENDLYAPPNAME, lpszFile, 0, a2, &v17);
    if ( v10 >= 0 && wcsspnp(a2) )
    {
      v11 = (unsigned __int16 *)wcsspnp(a2);
      if ( v11 && v11 != a2 )
      {
        LODWORD(v12) = 0;
        if ( !*v11 )
          goto LABEL_12;
        do
        {
          if ( (unsigned int)v12 < 0x103 )
            a2[(unsigned int)v12] = v11[(unsigned int)v12];
          v12 = (unsigned int)(v12 + 1);
        }
        while ( v11[v12] );
        if ( (unsigned int)v12 <= 0x103 )
LABEL_12:
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
          goto LABEL_22;
        do
        {
          if ( (unsigned int)v15 < 0x103 )
            a4[(unsigned int)v15] = v14[(unsigned int)v15];
          v15 = (unsigned int)(v15 + 1);
        }
        while ( v14[v15] );
        if ( (unsigned int)v15 <= 0x103 )
LABEL_22:
          a4[(unsigned int)v15] = 0;
      }
    }
    else
    {
      LoadStringW(hInst, 0x2FB4u, a4, 260);
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
0x1800158b8  mov     r11, rsp
0x1800158bb  mov     [r11+8], rbx
0x1800158bf  mov     [r11+10h], rbp
0x1800158c3  mov     [r11+18h], r8d
0x1800158c7  push    rsi
0x1800158c8  push    rdi
0x1800158c9  push    r12
0x1800158cb  push    r14
0x1800158cd  push    r15
0x1800158cf  sub     rsp, 30h
0x1800158d3  xor     r15d, r15d
0x1800158d6  mov     rdi, r9
0x1800158d9  mov     rbx, rdx
0x1800158dc  mov     rsi, rcx
0x1800158df  test    rdx, rdx
0x1800158e2  jz      loc_180015A5A
0x1800158e8  test    r9, r9
0x1800158eb  jz      loc_180015A5A
0x1800158f1  mov     r14, [rsp+58h+phiconLarge]
0x1800158f9  lea     rax, [r11+18h]
0x1800158fd  mov     [r9], r15w
0x180015901  mov     r8, rcx; pszAssoc
0x180015904  mov     [rdx], r15w
0x180015908  xor     r9d, r9d; pszExtra
0x18001590b  mov     [r11-30h], rax
0x18001590f  mov     [r11-38h], rdx
0x180015913  lea     edx, [r15+4]; str
0x180015917  lea     ecx, [rdx-2]; flags
0x18001591a  mov     [r14], r15
0x18001591d  mov     [rsp+58h+arg_10], 104h
0x180015925  call    cs:__imp_AssocQueryStringW
0x18001592b  mov     ebp, eax
0x18001592d  mov     r12d, 103h
0x180015933  test    eax, eax
0x180015935  js      short loc_180015989
0x180015937  mov     rcx, rbx
0x18001593a  call    _wcsspnp
0x18001593f  test    rax, rax
0x180015942  jz      short loc_180015989
0x180015944  mov     rcx, rbx
0x180015947  call    _wcsspnp
0x18001594c  mov     r8, rax
0x18001594f  test    rax, rax
0x180015952  jz      short loc_1800159AC
0x180015954  cmp     rax, rbx
0x180015957  jz      short loc_1800159AC
0x180015959  mov     edx, r15d
0x18001595c  cmp     [rax], r15w
0x180015960  jz      short loc_180015980
0x180015962  cmp     edx, r12d
0x180015965  jnb     short loc_180015972
0x180015967  mov     ecx, edx
0x180015969  movzx   eax, word ptr [r8+rcx*2]
0x18001596e  mov     [rbx+rcx*2], ax
0x180015972  inc     edx
0x180015974  cmp     [r8+rdx*2], r15w
0x180015979  jnz     short loc_180015962
0x18001597b  cmp     edx, r12d
0x18001597e  ja      short loc_1800159AC
0x180015980  mov     ecx, edx
0x180015982  mov     [rbx+rcx*2], r15w
0x180015987  jmp     short loc_1800159AC
0x180015989  mov     rcx, rsi; pszPath
0x18001598c  call    cs:__imp_PathFindFileNameW
0x180015992  mov     edx, 104h; unsigned __int64
0x180015997  mov     rcx, rbx; unsigned __int16 *
0x18001599a  mov     r8, rax; unsigned __int16 *
0x18001599d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800159a2  mov     ebp, eax
0x1800159a4  test    eax, eax
0x1800159a6  js      loc_180015A56
0x1800159ac  mov     r9d, 104h
0x1800159b2  lea     rdx, aCompanyname; "CompanyName"
0x1800159b9  mov     r8, rdi
0x1800159bc  mov     rcx, rsi
0x1800159bf  call    cs:__imp_?FwGetVersionField@@YAJPEBG0PEAGI@Z; FwGetVersionField(ushort const *,ushort const *,ushort *,uint)
0x1800159c5  test    eax, eax
0x1800159c7  js      short loc_180015A0E
0x1800159c9  mov     rcx, rdi
0x1800159cc  call    _wcsspnp
0x1800159d1  mov     r8, rax
0x1800159d4  test    rax, rax
0x1800159d7  jz      short loc_180015A0E
0x1800159d9  cmp     rax, rdi
0x1800159dc  jz      short loc_180015A29
0x1800159de  mov     edx, r15d
0x1800159e1  cmp     [rax], r15w
0x1800159e5  jz      short loc_180015A05
0x1800159e7  cmp     edx, r12d
0x1800159ea  jnb     short loc_1800159F7
0x1800159ec  mov     ecx, edx
0x1800159ee  movzx   eax, word ptr [r8+rcx*2]
0x1800159f3  mov     [rdi+rcx*2], ax
0x1800159f7  inc     edx
0x1800159f9  cmp     [r8+rdx*2], r15w
0x1800159fe  jnz     short loc_1800159E7
0x180015a00  cmp     edx, r12d
0x180015a03  ja      short loc_180015A29
0x180015a05  mov     ecx, edx
0x180015a07  mov     [rdi+rcx*2], r15w
0x180015a0c  jmp     short loc_180015A29
0x180015a0e  mov     rcx, cs:hInst; hInstance
0x180015a15  mov     r9d, 104h; cchBufferMax
0x180015a1b  mov     r8, rdi; lpBuffer
0x180015a1e  mov     edx, 2FB4h; uID
0x180015a23  call    cs:__imp_LoadStringW
0x180015a29  xor     r9d, r9d; phiconSmall
0x180015a2c  mov     [rsp+58h+nIcons], 1; nIcons
0x180015a34  mov     r8, r14; phiconLarge
0x180015a37  xor     edx, edx; nIconIndex
0x180015a39  mov     rcx, rsi; lpszFile
0x180015a3c  call    cs:__imp_ExtractIconExW
0x180015a42  test    eax, eax
0x180015a44  jnz     short loc_180015A56
0x180015a46  mov     edx, 7F00h; lpIconName
0x180015a4b  xor     ecx, ecx; hInstance
0x180015a4d  call    cs:__imp_LoadIconW
0x180015a53  mov     [r14], rax
0x180015a56  mov     eax, ebp
0x180015a58  jmp     short loc_180015A5F
0x180015a5a  mov     eax, 80070057h
0x180015a5f  mov     rbx, [rsp+58h+arg_0]
0x180015a64  mov     rbp, [rsp+58h+arg_8]
0x180015a69  add     rsp, 30h
0x180015a6d  pop     r15
0x180015a6f  pop     r14
0x180015a71  pop     r12
0x180015a73  pop     rdi
0x180015a74  pop     rsi
0x180015a75  retn
```
