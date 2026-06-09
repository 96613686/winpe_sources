# _Misc_HFGD_Create(void const *,void *)

- ea: `0x1800254f0`
- end: `0x180025773`
- name: `?_Misc_HFGD_Create@@YAHPEBXPEAX@Z`
- size: `643`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18001bda4`
- `0x18001c7a8`
- `0x18001d840`
- `0x18001db50`
- `0x180021888`
- `0x1800219cc`
- `0x180023d8c`
- `0x180023e40`
- `0x1800254f0`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180025552`
- `SHELL32!__imp_ILFindLastID` at `0x180025552`
- `KERNEL32!lstrlenW` at `0x180025716`
- `KERNEL32!lstrlenW` at `0x180025746`
- `KERNEL32!lstrlenW` at `0x180025716`
- `KERNEL32!lstrlenW` at `0x180025746`
- `KERNEL32!lstrlenA` at `0x1800256ba`
- `KERNEL32!lstrlenA` at `0x1800256e7`
- `KERNEL32!lstrlenA` at `0x1800256ba`
- `KERNEL32!lstrlenA` at `0x1800256e7`

## pseudocode

```c
__int64 __fastcall _Misc_HFGD_Create(const struct _ITEMIDLIST *p, _QWORD *pData)
{
  _DWORD *v2; // r9
  _DWORD *v3; // r8
  __int64 v6; // rcx
  _DWORD *v7; // rsi
  __int64 v8; // rcx
  _DWORD *v9; // r14
  LPITEMIDLIST ID; // rax
  int v11; // edx
  int v12; // edx
  int v13; // ecx
  struct _FILETIME FileTime; // rax
  int v15; // edx
  int v16; // ecx
  struct _FILETIME v17; // rax
  const struct _ITEMIDLIST *v18; // rbp
  const struct _ITEMIDLIST *v19; // rdi
  _BYTE *v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // r8d
  const char *v23; // r9
  _WORD *v24; // rdx
  unsigned int v25; // r8d
  unsigned int v26; // eax
  unsigned int v27; // r8d
  const unsigned __int16 *v28; // r9

  v2 = (_DWORD *)*pData;
  v3 = (_DWORD *)pData[1];
  if ( *pData )
  {
    v6 = (unsigned int)*v2;
    *v2 = v6 + 1;
    v7 = &v2[83 * v6 + 1];
  }
  else
  {
    v7 = 0;
  }
  if ( v3 )
  {
    v8 = (unsigned int)*v3;
    *v3 = v8 + 1;
    v9 = &v3[148 * v8 + 1];
  }
  else
  {
    v9 = 0;
  }
  ID = ILFindLastID(p);
  v11 = 0;
  if ( v7 )
  {
    *v7 = 16508;
    if ( ID->mkid.cb >= 0x27u && (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) == 0 )
      v11 = *(_DWORD *)((char *)&ID[3].mkid.cb + 1);
    v7[9] = v11;
    if ( ID->mkid.cb < 0x27u || (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) != 0 )
      v12 = 0;
    else
      v12 = *(_DWORD *)ID[4].mkid.abID;
    v7[17] = v12;
    if ( ID->mkid.cb < 0x27u || (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) != 0 )
      v13 = 0;
    else
      v13 = *(_DWORD *)&ID[6].mkid.cb;
    v7[16] = v13;
    FileTime = FtpPidl_GetFileTime(ID);
    *((struct _FILETIME *)v7 + 5) = FileTime;
    *((struct _FILETIME *)v7 + 7) = FileTime;
    *((struct _FILETIME *)v7 + 6) = FileTime;
  }
  else
  {
    *v9 = 16508;
    if ( ID->mkid.cb >= 0x27u && (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) == 0 )
      v11 = *(_DWORD *)((char *)&ID[3].mkid.cb + 1);
    v9[9] = v11;
    if ( ID->mkid.cb < 0x27u || (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) != 0 )
      v15 = 0;
    else
      v15 = *(_DWORD *)ID[4].mkid.abID;
    v9[17] = v15;
    if ( ID->mkid.cb < 0x27u || (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) != 0 )
      v16 = 0;
    else
      v16 = *(_DWORD *)&ID[6].mkid.cb;
    v9[16] = v16;
    v17 = FtpPidl_GetFileTime(ID);
    *((struct _FILETIME *)v9 + 5) = v17;
    *((struct _FILETIME *)v9 + 7) = v17;
    *((struct _FILETIME *)v9 + 6) = v17;
  }
  if ( p )
  {
    v18 = (const struct _ITEMIDLIST *)pData[2];
    if ( (unsigned int)FtpID_IsServerItemID(v18) )
      v19 = (const struct _ITEMIDLIST *)((char *)v18 + v18->mkid.cb);
    else
      v19 = v18;
    if ( (unsigned int)FtpID_IsServerItemID(p) )
      p = (const struct _ITEMIDLIST *)((char *)p + p->mkid.cb);
    if ( v19 )
    {
      while ( v19->mkid.cb )
      {
        if ( !p )
          return 1;
        if ( !p->mkid.cb || (unsigned int)_FtpItemID_CompareOneID(0, v19, p, 0) )
          goto LABEL_45;
        p = (const struct _ITEMIDLIST *)((char *)p + p->mkid.cb);
        v19 = (const struct _ITEMIDLIST *)((char *)v19 + v19->mkid.cb);
        if ( !v19 )
          break;
      }
    }
    if ( p )
    {
LABEL_45:
      if ( v7 )
      {
        UrlGetAbstractPathFromPidl(p, 0, 1, (char *)v7 + 72, 0x104u);
        v20 = (char *)v7 + lstrlenA((LPCSTR)v7 + 72) + 71;
        if ( v20 >= (_BYTE *)v7 + 72 && *v20 == 47 )
          *v20 = 0;
        if ( v7 != (_DWORD *)-72LL && *((_BYTE *)v7 + 72) == 47 )
        {
          v21 = lstrlenA((LPCSTR)v7 + 72);
          CharReplaceWithStrA((char *)v7 + 72, v21, v22, v23);
        }
        UrlPathToFilePathA((char *)v7 + 72, (char *)v7 + 72);
      }
      else
      {
        UrlGetAbstractPathFromPidl(p, 0, 0, (char *)v9 + 72, 0x104u);
        v24 = (_WORD *)v9 + lstrlenW((LPCWSTR)v9 + 36) + 35;
        if ( v24 >= (_WORD *)v9 + 36 && *v24 == 47 )
          *v24 = 0;
        if ( v9 != (_DWORD *)-72LL && *((_WORD *)v9 + 36) == 47 )
        {
          v26 = lstrlenW((LPCWSTR)v9 + 36);
          CharReplaceWithStrW((unsigned __int16 *)v9 + 36, v26, v27, v28);
        }
        UrlPathToFilePathW((const unsigned __int16 *)v9 + 36, (unsigned __int16 *)v9 + 36, v25);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800254f0  push    rbx
0x1800254f2  push    rbp
0x1800254f3  push    rsi
0x1800254f4  push    rdi
0x1800254f5  push    r14
0x1800254f7  push    r15
0x1800254f9  sub     rsp, 38h
0x1800254fd  mov     r9, [rdx]
0x180025500  xor     r15d, r15d
0x180025503  mov     r8, [rdx+8]
0x180025507  mov     rbp, rdx
0x18002550a  mov     rbx, rcx
0x18002550d  test    r9, r9
0x180025510  jz      short loc_18002552B
0x180025512  mov     ecx, [r9]
0x180025515  imul    rsi, rcx, 14Ch
0x18002551c  lea     eax, [rcx+1]
0x18002551f  add     rsi, 4
0x180025523  mov     [r9], eax
0x180025526  add     rsi, r9
0x180025529  jmp     short loc_18002552E
0x18002552b  mov     rsi, r15
0x18002552e  test    r8, r8
0x180025531  jz      short loc_18002554C
0x180025533  mov     ecx, [r8]
0x180025536  imul    r14, rcx, 250h
0x18002553d  lea     eax, [rcx+1]
0x180025540  add     r14, 4
0x180025544  mov     [r8], eax
0x180025547  add     r14, r8
0x18002554a  jmp     short loc_18002554F
0x18002554c  mov     r14, r15
0x18002554f  mov     rcx, rbx; pidl
0x180025552  call    cs:__imp_ILFindLastID
0x180025558  mov     edx, r15d
0x18002555b  mov     ecx, 0FFFCFFC2h
0x180025560  test    rsi, rsi
0x180025563  jz      short loc_1800255BE
0x180025565  mov     dword ptr [rsi], 407Ch
0x18002556b  cmp     word ptr [rax], 27h ; '''
0x18002556f  jb      short loc_180025579
0x180025571  test    [rax+6], ecx
0x180025574  jnz     short loc_180025579
0x180025576  mov     edx, [rax+0Ah]
0x180025579  mov     [rsi+24h], edx
0x18002557c  cmp     word ptr [rax], 27h ; '''
0x180025580  jb      short loc_18002558C
0x180025582  test    [rax+6], ecx
0x180025585  jnz     short loc_18002558C
0x180025587  mov     edx, [rax+0Eh]
0x18002558a  jmp     short loc_18002558F
0x18002558c  mov     edx, r15d
0x18002558f  mov     [rsi+44h], edx
0x180025592  cmp     word ptr [rax], 27h ; '''
0x180025596  jb      short loc_1800255A2
0x180025598  test    [rax+6], ecx
0x18002559b  jnz     short loc_1800255A2
0x18002559d  mov     ecx, [rax+12h]
0x1800255a0  jmp     short loc_1800255A5
0x1800255a2  mov     ecx, r15d
0x1800255a5  mov     [rsi+40h], ecx
0x1800255a8  mov     rcx, rax; struct _ITEMIDLIST *
0x1800255ab  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x1800255b0  mov     [rsi+28h], rax
0x1800255b4  mov     [rsi+38h], rax
0x1800255b8  mov     [rsi+30h], rax
0x1800255bc  jmp     short loc_180025619
0x1800255be  mov     dword ptr [r14], 407Ch
0x1800255c5  cmp     word ptr [rax], 27h ; '''
0x1800255c9  jb      short loc_1800255D3
0x1800255cb  test    [rax+6], ecx
0x1800255ce  jnz     short loc_1800255D3
0x1800255d0  mov     edx, [rax+0Ah]
0x1800255d3  mov     [r14+24h], edx
0x1800255d7  cmp     word ptr [rax], 27h ; '''
0x1800255db  jb      short loc_1800255E7
0x1800255dd  test    [rax+6], ecx
0x1800255e0  jnz     short loc_1800255E7
0x1800255e2  mov     edx, [rax+0Eh]
0x1800255e5  jmp     short loc_1800255EA
0x1800255e7  mov     edx, r15d
0x1800255ea  mov     [r14+44h], edx
0x1800255ee  cmp     word ptr [rax], 27h ; '''
0x1800255f2  jb      short loc_1800255FE
0x1800255f4  test    [rax+6], ecx
0x1800255f7  jnz     short loc_1800255FE
0x1800255f9  mov     ecx, [rax+12h]
0x1800255fc  jmp     short loc_180025601
0x1800255fe  mov     ecx, r15d
0x180025601  mov     [r14+40h], ecx
0x180025605  mov     rcx, rax; struct _ITEMIDLIST *
0x180025608  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x18002560d  mov     [r14+28h], rax
0x180025611  mov     [r14+38h], rax
0x180025615  mov     [r14+30h], rax
0x180025619  test    rbx, rbx
0x18002561c  jz      loc_180025761
0x180025622  mov     rbp, [rbp+10h]
0x180025626  mov     rcx, rbp; struct _ITEMIDLIST *
0x180025629  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18002562e  test    eax, eax
0x180025630  jz      short loc_18002563B
0x180025632  movzx   edi, word ptr [rbp+0]
0x180025636  add     rdi, rbp
0x180025639  jmp     short loc_18002563E
0x18002563b  mov     rdi, rbp
0x18002563e  mov     rcx, rbx; struct _ITEMIDLIST *
0x180025641  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180025646  test    eax, eax
0x180025648  jz      short loc_180025650
0x18002564a  movzx   eax, word ptr [rbx]
0x18002564d  add     rbx, rax
0x180025650  test    rdi, rdi
0x180025653  jz      short loc_18002568C
0x180025655  cmp     [rdi], r15w
0x180025659  jz      short loc_18002568C
0x18002565b  test    rbx, rbx
0x18002565e  jz      loc_180025761
0x180025664  cmp     [rbx], r15w
0x180025668  jz      short loc_180025695
0x18002566a  xor     r9d, r9d; unsigned int
0x18002566d  mov     r8, rbx; struct _ITEMIDLIST *
0x180025670  mov     rdx, rdi; struct _ITEMIDLIST *
0x180025673  xor     ecx, ecx; __int64
0x180025675  call    ?_FtpItemID_CompareOneID@@YAJ_JPEFBU_ITEMIDLIST@@1K@Z; _FtpItemID_CompareOneID(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *,ulong)
0x18002567a  test    eax, eax
0x18002567c  jnz     short loc_180025695
0x18002567e  movzx   eax, word ptr [rbx]
0x180025681  add     rbx, rax
0x180025684  movzx   eax, word ptr [rdi]
0x180025687  add     rdi, rax
0x18002568a  jnz     short loc_180025655
0x18002568c  test    rbx, rbx
0x18002568f  jz      loc_180025761
0x180025695  xor     edx, edx; int
0x180025697  mov     [rsp+68h+var_48], 104h; unsigned int
0x18002569f  mov     rcx, rbx; struct _ITEMIDLIST *
0x1800256a2  test    rsi, rsi
0x1800256a5  jz      short loc_180025704
0x1800256a7  lea     rdi, [rsi+48h]
0x1800256ab  mov     r9, rdi; void *
0x1800256ae  lea     r8d, [rdx+1]; int
0x1800256b2  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x1800256b7  mov     rcx, rdi; lpString
0x1800256ba  call    cs:__imp_lstrlenA
0x1800256c0  movsxd  rcx, eax
0x1800256c3  lea     rax, [rdi-1]
0x1800256c7  add     rax, rcx
0x1800256ca  mov     ecx, 2Fh ; '/'
0x1800256cf  cmp     rax, rdi
0x1800256d2  jb      short loc_1800256DB
0x1800256d4  cmp     [rax], cl
0x1800256d6  jnz     short loc_1800256DB
0x1800256d8  mov     [rax], r15b
0x1800256db  test    rdi, rdi
0x1800256de  jz      short loc_1800256F7
0x1800256e0  cmp     [rdi], cl
0x1800256e2  jnz     short loc_1800256F7
0x1800256e4  mov     rcx, rdi; lpString
0x1800256e7  call    cs:__imp_lstrlenA
0x1800256ed  mov     edx, eax; unsigned int
0x1800256ef  mov     rcx, rdi; char *
0x1800256f2  call    ?CharReplaceWithStrA@@YAJPEADKKPEBD@Z; CharReplaceWithStrA(char *,ulong,ulong,char const *)
0x1800256f7  mov     rdx, rdi; char *
0x1800256fa  mov     rcx, rdi; char *
0x1800256fd  call    ?UrlPathToFilePathA@@YAJPEBDPEADK@Z; UrlPathToFilePathA(char const *,char *,ulong)
0x180025702  jmp     short loc_180025761
0x180025704  lea     rdi, [r14+48h]
0x180025708  xor     r8d, r8d; int
0x18002570b  mov     r9, rdi; void *
0x18002570e  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x180025713  mov     rcx, rdi; lpString
0x180025716  call    cs:__imp_lstrlenW
0x18002571c  movsxd  rdx, eax
0x18002571f  mov     ecx, 2Fh ; '/'
0x180025724  dec     rdx
0x180025727  lea     rdx, [rdi+rdx*2]
0x18002572b  cmp     rdx, rdi
0x18002572e  jb      short loc_180025739
0x180025730  cmp     cx, [rdx]
0x180025733  jnz     short loc_180025739
0x180025735  mov     [rdx], r15w
0x180025739  test    rdi, rdi
0x18002573c  jz      short loc_180025756
0x18002573e  cmp     cx, [rdi]
0x180025741  jnz     short loc_180025756
0x180025743  mov     rcx, rdi; lpString
0x180025746  call    cs:__imp_lstrlenW
0x18002574c  mov     edx, eax; unsigned int
0x18002574e  mov     rcx, rdi; unsigned __int16 *
0x180025751  call    ?CharReplaceWithStrW@@YAJPEAGKKPEBG@Z; CharReplaceWithStrW(ushort *,ulong,ulong,ushort const *)
0x180025756  mov     rdx, rdi; unsigned __int16 *
0x180025759  mov     rcx, rdi; unsigned __int16 *
0x18002575c  call    ?UrlPathToFilePathW@@YAJPEBGPEAGK@Z; UrlPathToFilePathW(ushort const *,ushort *,ulong)
0x180025761  mov     eax, 1
0x180025766  add     rsp, 38h
0x18002576a  pop     r15
0x18002576c  pop     r14
0x18002576e  pop     rdi
0x18002576f  pop     rsi
0x180025770  pop     rbp
0x180025771  pop     rbx
0x180025772  retn
```
