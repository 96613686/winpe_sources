# CAutomateContent::OnBeforeNavigate(char const *,long,char const *,tagVARIANT *,char const *,int *)

- ea: `0x18000c484`
- end: `0x18000cba2`
- name: `?OnBeforeNavigate@CAutomateContent@@QEAAXPEBDJ0PEAUtagVARIANT@@0PEAH@Z`
- size: `1822`
- prototype: `void __fastcall(CAutomateContent *__hidden this, const char *, int, const char *, struct tagVARIANT *, const char *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000c0c0`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x180006708`
- `0x1800095c8`
- `0x18000bec0`
- `0x18000c484`
- `0x1800269d0`
- `0x1800340b0`
- `0x18004e6a8`
- `0x180051e98`
- `0x18005fbe0`
- `0x18005fce8`
- `0x1800628e8`
- `0x180063488`
- `0x180063bd8`
- `0x180065e50`
- `0x180066cc0`
- `0x1800678a0`
- `0x18006a284`
- `0x18006bdc0`
- `0x18006e4b8`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x18000c6b2`
- `KERNEL32!lstrcmpiA` at `0x18000c6b2`
- `KERNEL32!GetFileAttributesA` at `0x18000c77e`
- `KERNEL32!GetFileAttributesA` at `0x18000c77e`
- `KERNEL32!LocalAlloc` at `0x18000c824`
- `KERNEL32!LocalAlloc` at `0x18000c864`
- `KERNEL32!LocalAlloc` at `0x18000c9a8`
- `KERNEL32!LocalAlloc` at `0x18000c824`
- `KERNEL32!LocalAlloc` at `0x18000c864`
- `KERNEL32!LocalAlloc` at `0x18000c9a8`
- `USER32!GetMenu` at `0x18000cac1`
- `USER32!GetMenu` at `0x18000cac1`
- `USER32!SendMessageA` at `0x18000cab2`
- `USER32!SendMessageA` at `0x18000cab2`
- `USER32!EnableMenuItem` at `0x18000cade`
- `USER32!EnableMenuItem` at `0x18000cade`
- `USER32!PostMessageA` at `0x18000c897`
- `USER32!PostMessageA` at `0x18000c9d3`
- `USER32!PostMessageA` at `0x18000c897`
- `USER32!PostMessageA` at `0x18000c9d3`

## string_xrefs

- `0x18000c588`: `mk:@MSITStore:`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CAutomateContent::OnBeforeNavigate(
        CAutomateContent *this,
        const char *a2,
        __int64 a3,
        const char *a4,
        struct tagVARIANT *a5,
        const char *a6,
        int *a7)
{
  const char *v7; // rdi
  unsigned int URLType; // r9d
  unsigned int v10; // r12d
  CExCollection *v11; // rbx
  struct CExTitle *v12; // r14
  struct CHHWinType *HHWindowIndex; // rax
  HWND v14; // rcx
  int v15; // r9d
  int v16; // r10d
  int v17; // r11d
  struct CHHWinType *v18; // rsi
  const char *v19; // r8
  unsigned int v20; // r10d
  __int64 v21; // r15
  int v22; // r12d
  CExCollection *CurrentCollection; // rax
  CExCollection *v24; // rax
  char *v25; // r9
  __int64 v26; // rdx
  CHAR *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  char *v30; // rax
  WPARAM v31; // r10
  CExCollection *v32; // rax
  int v33; // eax
  char *v34; // r9
  char *v35; // rax
  WPARAM v36; // r10
  unsigned int v37; // r14d
  CExTitle *v38; // r15
  HWND v39; // rcx
  HMENU Menu; // rax
  unsigned int v41; // eax
  int v42; // ecx
  int v43; // edx
  char v44[4]; // [rsp+30h] [rbp-D0h] BYREF
  char *v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-C0h] BYREF
  CExTitle *v47; // [rsp+48h] [rbp-B8h] BYREF
  PCSTR pszStart; // [rsp+50h] [rbp-B0h] BYREF
  LPCSTR lpString1; // [rsp+58h] [rbp-A8h] BYREF
  LPCSTR lpString2; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v51; // [rsp+68h] [rbp-98h]
  CHAR FileName[272]; // [rsp+70h] [rbp-90h] BYREF
  char v53[256]; // [rsp+180h] [rbp+80h] BYREF
  char v54[256]; // [rsp+280h] [rbp+180h] BYREF
  char v55[2096]; // [rsp+380h] [rbp+280h] BYREF
  char v56[2096]; // [rsp+BB0h] [rbp+AB0h] BYREF
  char v57[2096]; // [rsp+13E0h] [rbp+12E0h] BYREF

  v7 = a2;
  v45 = 0;
  URLType = GetURLType(a2);
  *a7 = 0;
  pszStart = 0;
  if ( URLType == -2 )
  {
    COleDispatchDriver::InvokeHelper(*(COleDispatchDriver **)(*((_QWORD *)this + 7) + 152LL), 211, 2u, 8u, &pszStart, 0);
    v7 = pszStart;
    if ( !pszStart || !*pszStart )
      goto LABEL_86;
    v46 = 0;
    URLType = GetURLType(pszStart);
  }
  else
  {
    v46 = 1;
  }
  v10 = URLType;
  v51 = URLType;
  v11 = 0;
  v12 = 0;
  v47 = 0;
  HHWindowIndex = FindHHWindowIndex(*((struct CContainer **)this + 7));
  v18 = HHWindowIndex;
  if ( HHWindowIndex )
    *((_DWORD *)HHWindowIndex + 142) = v16;
  if ( v15 == v16 )
  {
    v19 = "ms-its:";
    if ( !g_bMsItsMonikerSupport )
      v19 = "mk:@MSITStore:";
    StringCchCopyA(v56, 0x824u, v19);
    StringCchCatA(v56, v20, v7);
    v7 = v56;
    v17 = 2;
    v15 = 2;
  }
  v21 = -1;
  if ( v18 )
  {
    if ( v15 == 3 )
    {
      v22 = 0;
      CurrentCollection = GetCurrentCollection(v14, v7);
      v11 = CurrentCollection;
      if ( CurrentCollection )
      {
        CExCollection::URL2ExTitle(CurrentCollection, v7, &v47);
        v12 = v47;
        if ( !v47 )
        {
          GetCompiledName(v7, (PCSTR *)&v45);
          v22 = 1;
        }
      }
      goto LABEL_33;
    }
    if ( v15 != v17 )
    {
      v22 = 0;
LABEL_33:
      *(_DWORD *)v44 = v22;
      goto LABEL_34;
    }
    v24 = GetCurrentCollection(v14, v7);
    v11 = v24;
    if ( v24 )
    {
      CExCollection::URL2ExTitle(v24, v7, &v47);
      v12 = v47;
      v22 = 0;
      if ( v47 )
        CExTitle::ConvertURL(v47, v7, v57, v25);
      lpString1 = 0;
      lpString2 = 0;
      if ( v12 )
      {
        ConvertSpacesToEscapes(v57, (struct CStr *)&lpString1);
        ConvertSpacesToEscapes(v7, (struct CStr *)&lpString2);
        if ( !lstrcmpiA(lpString1, lpString2) )
        {
          *(_DWORD *)v44 = 0;
LABEL_29:
          CWStr::~CWStr((CWStr *)&lpString2);
          CWStr::~CWStr((CWStr *)&lpString1);
LABEL_34:
          lpString1 = 0;
          if ( v22 )
          {
            v26 = -1;
            do
              ++v26;
            while ( v45[v26] );
            v27 = (CHAR *)LocalAlloc(0, v26 + 1);
            lpString1 = v27;
            v28 = -1;
            do
              ++v28;
            while ( v45[v28] );
            StringCchCopyA(v27, v28 + 1, v45);
          }
          if ( *(_DWORD *)v44 )
          {
            v29 = -1;
            do
              ++v29;
            while ( v7[v29] );
            v30 = (char *)LocalAlloc(0, v29 + 1);
            do
              ++v21;
            while ( v7[v21] );
            StringCchCopyA(v30, v21 + 1, v7);
            PostMessageA(*((HWND *)v18 + 8), 0x615u, v31, (LPARAM)lpString1);
            *a7 = 1;
            goto LABEL_86;
          }
          v10 = v51;
          goto LABEL_47;
        }
        v7 = v57;
      }
      else
      {
        GetCompiledName(v7, (PCSTR *)&v45);
        SplitPath(v45, 0, 0, v53, v54);
        StringCchCatA(v53, 0x100u, v54);
        SplitPath(*((const char **)v11 + 134), v44, v55, 0, 0);
        StringCchCopyA(FileName, 0x104u, v44);
        CatPath(FileName, v55, 0x104u);
        CatPath(FileName, v53, 0x104u);
        if ( GetFileAttributesA(FileName) == -1 )
        {
          if ( !(unsigned int)FindThisFile(0, v53, (struct CStr *)&v45, 0) )
          {
            *a7 = 1;
            CWStr::~CWStr((CWStr *)&lpString2);
            CWStr::~CWStr((CWStr *)&lpString1);
            goto LABEL_86;
          }
        }
        else
        {
          CStr::operator=(&v45);
        }
        v22 = 1;
      }
      *(_DWORD *)v44 = 1;
      goto LABEL_29;
    }
  }
LABEL_47:
  if ( v10 != -1 )
  {
    v32 = GetCurrentCollection(v14, v7);
    v11 = v32;
    if ( v32 && !v12 )
    {
      CExCollection::URL2ExTitle(v32, v7, &v47);
      v12 = v47;
    }
    if ( v18 && v11 && !*((_DWORD *)v11 + 274) )
    {
      if ( !v12 )
      {
        CExCollection::URL2ExTitle(v11, v7, &v47);
        v12 = v47;
      }
      v33 = EnsureStorageAvailability(v12, 0, 1, 1, 0);
      if ( v33 < 0 )
      {
        if ( v33 == -2147221403 )
        {
          MsgBox(1108, 0);
        }
        else if ( v33 == -2147467259 )
        {
LABEL_61:
          *((_DWORD *)v18 + 141) = 0;
          goto LABEL_86;
        }
        *a7 = 1;
        goto LABEL_61;
      }
      if ( v33 == 262244 )
      {
        CExTitle::ConvertURL(v12, v7, v55, v34);
        *a7 = 1;
        do
          ++v21;
        while ( v55[v21] );
        v35 = (char *)LocalAlloc(0, v21 + 1);
        StringCchCopyA(v35, v21 + 1, v55);
        PostMessageA(*((HWND *)v18 + 8), 0x615u, v36, 0);
        goto LABEL_86;
      }
    }
  }
  if ( !v46 )
    goto LABEL_86;
  if ( v10 != -1 && v12 && !(unsigned int)CExTitle::EnsureChmChiMatch(v12, 0) )
  {
    *a7 = 1;
    *((_DWORD *)v18 + 141) = 0;
    goto LABEL_86;
  }
  if ( !v18 )
    goto LABEL_84;
  v37 = 0;
  if ( v11 && CExCollection::IsBinaryTOC(v11, *((const char **)v18 + 17)) )
  {
    if ( CExCollection::URL2ExTitle(v11, v7, &v47) >= 0 )
    {
      v38 = v47;
    }
    else
    {
      v38 = (CExTitle *)*((_QWORD *)v11 + 166);
      if ( !v38 )
        goto LABEL_76;
    }
    v46 = 0;
    *(_DWORD *)v44 = 0;
    if ( CExTitle::GetUrlTocSlot(v38, v7, &v46, (unsigned int *)v44) >= 0 )
    {
      v41 = v46;
      v42 = *(_DWORD *)v44;
    }
    else
    {
      v41 = 0;
      v42 = 0;
    }
    v43 = *((_DWORD *)v11 + 329);
    if ( !v43 || v41 == v43 || v42 != *((_DWORD *)v11 + 330) )
    {
      *((_DWORD *)v11 + 329) = v41;
      *((_DWORD *)v11 + 330) = v42;
      *((_QWORD *)v11 + 166) = v38;
    }
    if ( v41 )
      v37 = 1;
  }
LABEL_76:
  if ( (unsigned int)IsValidWindow(*((HWND *)v18 + 11)) && (*((_DWORD *)v18 + 42) & 0x800) != 0 )
  {
    if ( v11 && !CExCollection::IsBinaryTOC(v11, *((const char **)v18 + 17)) )
      v37 = 1;
    SendMessageA(*((HWND *)v18 + 11), 0x401u, 0xCEu, v37);
    v39 = (HWND)*((_QWORD *)v18 + 8);
    if ( v39 )
    {
      Menu = GetMenu(v39);
      if ( Menu )
        EnableMenuItem(Menu, 0x1775u, v37 == 0);
    }
  }
LABEL_84:
  if ( !*a7 )
    *((_DWORD *)v18 + 142) = 0;
LABEL_86:
  CWStr::~CWStr((CWStr *)&pszStart);
  CWStr::~CWStr((CWStr *)&v45);
}

```

## disassembly

```asm
0x18000c484  mov     [rsp-8+arg_10], rbx
0x18000c489  push    rbp
0x18000c48a  push    rsi
0x18000c48b  push    rdi
0x18000c48c  push    r12
0x18000c48e  push    r13
0x18000c490  push    r14
0x18000c492  push    r15
0x18000c494  lea     rbp, [rsp-1B20h]
0x18000c49c  mov     eax, 1C20h
0x18000c4a1  call    _alloca_probe
0x18000c4a6  sub     rsp, rax
0x18000c4a9  mov     rax, cs:__security_cookie
0x18000c4b0  xor     rax, rsp
0x18000c4b3  mov     [rbp+1B50h+var_40], rax
0x18000c4ba  mov     rdi, rdx
0x18000c4bd  mov     rsi, rcx
0x18000c4c0  mov     r13, [rbp+1B50h+arg_30]
0x18000c4c7  xor     r15d, r15d
0x18000c4ca  mov     [rsp+1C50h+var_1C18], r15
0x18000c4cf  mov     rcx, rdx; pszStart
0x18000c4d2  call    ?GetURLType@@YAIPEBD@Z; GetURLType(char const *)
0x18000c4d7  mov     r9d, eax
0x18000c4da  mov     [r13+0], r15d
0x18000c4de  mov     [rsp+1C50h+pszStart], r15
0x18000c4e3  lea     r10d, [r15+1]
0x18000c4e7  lea     r11d, [r15+2]
0x18000c4eb  cmp     eax, 0FFFFFFFEh
0x18000c4ee  jnz     short loc_18000C54C
0x18000c4f0  lea     r9d, [r15+8]; unsigned __int16
0x18000c4f4  mov     rcx, [rsi+38h]
0x18000c4f8  mov     [rsp+1C50h+var_1C28], r15; unsigned __int8 *
0x18000c4fd  lea     rax, [rsp+1C50h+pszStart]
0x18000c502  mov     [rsp+1C50h+var_1C30], rax; void *
0x18000c507  mov     r8d, r11d; unsigned __int16
0x18000c50a  mov     edx, 0D3h; int
0x18000c50f  mov     rcx, [rcx+98h]; this
0x18000c516  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x18000c51b  mov     rdi, [rsp+1C50h+pszStart]
0x18000c520  test    rdi, rdi
0x18000c523  jz      loc_18000CAF1
0x18000c529  cmp     [rdi], r15b
0x18000c52c  jz      loc_18000CAF1
0x18000c532  mov     [rsp+1C50h+var_1C10], r15d
0x18000c537  mov     rcx, rdi; pszStart
0x18000c53a  call    ?GetURLType@@YAIPEBD@Z; GetURLType(char const *)
0x18000c53f  mov     r9d, eax
0x18000c542  lea     r10d, [r15+1]
0x18000c546  lea     r11d, [r15+2]
0x18000c54a  jmp     short loc_18000C551
0x18000c54c  mov     [rsp+1C50h+var_1C10], r10d
0x18000c551  mov     r12d, r9d
0x18000c554  mov     [rsp+1C50h+var_1BE8], r9d
0x18000c559  mov     rbx, r15
0x18000c55c  mov     r14, r15
0x18000c55f  mov     [rsp+1C50h+var_1C08], r15
0x18000c564  mov     rcx, [rsi+38h]; struct CContainer *
0x18000c568  call    ?FindHHWindowIndex@@YAPEAVCHHWinType@@PEAVCContainer@@@Z; FindHHWindowIndex(CContainer *)
0x18000c56d  mov     rsi, rax
0x18000c570  test    rax, rax
0x18000c573  jz      short loc_18000C57C
0x18000c575  mov     [rax+238h], r10d
0x18000c57c  cmp     r9d, r10d
0x18000c57f  jnz     short loc_18000C5D1
0x18000c581  lea     r8, ?txtMsItsMoniker@@3QBDB; "ms-its:"
0x18000c588  lea     rax, ?txtMkStore@@3QBDB; "mk:@MSITStore:"
0x18000c58f  cmp     cs:?g_bMsItsMonikerSupport@@3HA, r15d; int g_bMsItsMonikerSupport
0x18000c596  cmovz   r8, rax; char *
0x18000c59a  mov     r10d, 824h
0x18000c5a0  mov     edx, r10d; unsigned __int64
0x18000c5a3  lea     rcx, [rbp+1B50h+var_10A0]; char *
0x18000c5aa  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000c5af  mov     r8, rdi; char *
0x18000c5b2  mov     edx, r10d; unsigned __int64
0x18000c5b5  lea     rcx, [rbp+1B50h+var_10A0]; char *
0x18000c5bc  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000c5c1  lea     rdi, [rbp+1B50h+var_10A0]
0x18000c5c8  mov     r11d, 2
0x18000c5ce  mov     r9d, r11d
0x18000c5d1  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c5d5  test    rsi, rsi
0x18000c5d8  jz      loc_18000C8AF
0x18000c5de  cmp     r9d, 3
0x18000c5e2  jnz     short loc_18000C62F
0x18000c5e4  xor     r12d, r12d
0x18000c5e7  mov     rdx, rdi; char *
0x18000c5ea  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x18000c5ef  mov     rbx, rax
0x18000c5f2  test    rax, rax
0x18000c5f5  jz      loc_18000C7FC
0x18000c5fb  lea     r8, [rsp+1C50h+var_1C08]; struct CExTitle **
0x18000c600  mov     rdx, rdi; char *
0x18000c603  mov     rcx, rax; this
0x18000c606  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x18000c60b  mov     r14, [rsp+1C50h+var_1C08]
0x18000c610  test    r14, r14
0x18000c613  jnz     loc_18000C7FC
0x18000c619  lea     rdx, [rsp+1C50h+var_1C18]; struct CStr *
0x18000c61e  mov     rcx, rdi; pszFirst
0x18000c621  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x18000c626  lea     r12d, [r15+2]
0x18000c62a  jmp     loc_18000C7FC
0x18000c62f  cmp     r9d, r11d
0x18000c632  jnz     loc_18000C7F9
0x18000c638  mov     rdx, rdi; char *
0x18000c63b  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x18000c640  mov     rbx, rax
0x18000c643  test    rax, rax
0x18000c646  jz      loc_18000C8AF
0x18000c64c  lea     r8, [rsp+1C50h+var_1C08]; struct CExTitle **
0x18000c651  mov     rdx, rdi; char *
0x18000c654  mov     rcx, rax; this
0x18000c657  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x18000c65c  mov     r14, [rsp+1C50h+var_1C08]
0x18000c661  xor     r12d, r12d
0x18000c664  test    r14, r14
0x18000c667  jz      short loc_18000C67B
0x18000c669  lea     r8, [rbp+1B50h+var_870]; char *
0x18000c670  mov     rdx, rdi; char *
0x18000c673  mov     rcx, r14; this
0x18000c676  call    ?ConvertURL@CExTitle@@QEAAJPEBDPEAD_K@Z; CExTitle::ConvertURL(char const *,char *,unsigned __int64)
0x18000c67b  mov     [rsp+1C50h+lpString1], r12
0x18000c680  mov     [rsp+1C50h+lpString2], r12
0x18000c685  test    r14, r14
0x18000c688  jz      short loc_18000C6D2
0x18000c68a  lea     rdx, [rsp+1C50h+lpString1]; struct CStr *
0x18000c68f  lea     rcx, [rbp+1B50h+var_870]; char *
0x18000c696  call    ?ConvertSpacesToEscapes@@YAXPEBDPEAVCStr@@@Z; ConvertSpacesToEscapes(char const *,CStr *)
0x18000c69b  lea     rdx, [rsp+1C50h+lpString2]; struct CStr *
0x18000c6a0  mov     rcx, rdi; char *
0x18000c6a3  call    ?ConvertSpacesToEscapes@@YAXPEBDPEAVCStr@@@Z; ConvertSpacesToEscapes(char const *,CStr *)
0x18000c6a8  mov     rdx, [rsp+1C50h+lpString2]; lpString2
0x18000c6ad  mov     rcx, [rsp+1C50h+lpString1]; lpString1
0x18000c6b2  call    cs:__imp_lstrcmpiA
0x18000c6b8  test    eax, eax
0x18000c6ba  jz      short loc_18000C6C8
0x18000c6bc  lea     rdi, [rbp+1B50h+var_870]
0x18000c6c3  jmp     loc_18000C79E
0x18000c6c8  mov     dword ptr [rsp+1C50h+var_1C20], r12d
0x18000c6cd  jmp     loc_18000C7A6
0x18000c6d2  lea     rdx, [rsp+1C50h+var_1C18]; struct CStr *
0x18000c6d7  mov     rcx, rdi; pszFirst
0x18000c6da  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x18000c6df  lea     rax, [rbp+1B50h+var_19D0]
0x18000c6e6  mov     [rsp+1C50h+var_1C30], rax; char *
0x18000c6eb  lea     r9, [rbp+1B50h+var_1AD0]; char *
0x18000c6f2  xor     r8d, r8d; char *
0x18000c6f5  xor     edx, edx; char *
0x18000c6f7  mov     rcx, [rsp+1C50h+var_1C18]; char *
0x18000c6fc  call    ?SplitPath@@YAXPEBDPEAD111@Z; SplitPath(char const *,char *,char *,char *,char *)
0x18000c701  lea     r8, [rbp+1B50h+var_19D0]; char *
0x18000c708  mov     edx, 100h; unsigned __int64
0x18000c70d  lea     rcx, [rbp+1B50h+var_1AD0]; char *
0x18000c714  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000c719  mov     [rsp+1C50h+var_1C30], r12; char *
0x18000c71e  xor     r9d, r9d; char *
0x18000c721  lea     r8, [rbp+1B50h+var_18D0]; char *
0x18000c728  lea     rdx, [rsp+1C50h+var_1C20]; char *
0x18000c72d  mov     rcx, [rbx+430h]; char *
0x18000c734  call    ?SplitPath@@YAXPEBDPEAD111@Z; SplitPath(char const *,char *,char *,char *,char *)
0x18000c739  lea     r8, [rsp+1C50h+var_1C20]; char *
0x18000c73e  mov     r12d, 104h
0x18000c744  mov     edx, r12d; unsigned __int64
0x18000c747  lea     rcx, [rsp+1C50h+FileName]; char *
0x18000c74c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000c751  mov     r8d, r12d; unsigned __int64
0x18000c754  lea     rdx, [rbp+1B50h+var_18D0]; char *
0x18000c75b  lea     rcx, [rsp+1C50h+FileName]; char *
0x18000c760  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x18000c765  mov     r8d, r12d; unsigned __int64
0x18000c768  lea     rdx, [rbp+1B50h+var_1AD0]; char *
0x18000c76f  lea     rcx, [rsp+1C50h+FileName]; char *
0x18000c774  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x18000c779  lea     rcx, [rsp+1C50h+FileName]; lpFileName
0x18000c77e  call    cs:__imp_GetFileAttributesA
0x18000c784  cmp     eax, 0FFFFFFFFh
0x18000c787  jz      short loc_18000C7BD
0x18000c789  lea     rdx, [rsp+1C50h+FileName]
0x18000c78e  lea     rcx, [rsp+1C50h+var_1C18]
0x18000c793  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18000c798  mov     r12d, 1
0x18000c79e  mov     dword ptr [rsp+1C50h+var_1C20], 1
0x18000c7a6  lea     rcx, [rsp+1C50h+lpString2]; this
0x18000c7ab  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18000c7b0  nop
0x18000c7b1  lea     rcx, [rsp+1C50h+lpString1]; this
0x18000c7b6  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18000c7bb  jmp     short loc_18000C801
0x18000c7bd  xor     r9d, r9d; int
0x18000c7c0  lea     r8, [rsp+1C50h+var_1C18]; struct CStr *
0x18000c7c5  lea     rdx, [rbp+1B50h+var_1AD0]; char *
0x18000c7cc  xor     ecx, ecx; HWND
0x18000c7ce  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x18000c7d3  test    eax, eax
0x18000c7d5  jnz     short loc_18000C798
0x18000c7d7  mov     dword ptr [r13+0], 1
0x18000c7df  lea     rcx, [rsp+1C50h+lpString2]; this
0x18000c7e4  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18000c7e9  nop
0x18000c7ea  lea     rcx, [rsp+1C50h+lpString1]; this
0x18000c7ef  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18000c7f4  jmp     loc_18000CAF1
0x18000c7f9  xor     r12d, r12d
0x18000c7fc  mov     dword ptr [rsp+1C50h+var_1C20], r12d
0x18000c801  xor     r10d, r10d
0x18000c804  mov     [rsp+1C50h+lpString1], r10
0x18000c809  test    r12d, r12d
0x18000c80c  jz      short loc_18000C84C
0x18000c80e  mov     rax, [rsp+1C50h+var_1C18]
0x18000c813  mov     rdx, r15
0x18000c816  inc     rdx
0x18000c819  cmp     [rax+rdx], r10b
0x18000c81d  jnz     short loc_18000C816
0x18000c81f  inc     rdx; uBytes
0x18000c822  xor     ecx, ecx; uFlags
0x18000c824  call    cs:__imp_LocalAlloc
0x18000c82a  mov     [rsp+1C50h+lpString1], rax
0x18000c82f  mov     r8, [rsp+1C50h+var_1C18]; char *
0x18000c834  mov     rdx, r15
0x18000c837  inc     rdx
0x18000c83a  cmp     byte ptr [r8+rdx], 0
0x18000c83f  jnz     short loc_18000C837
0x18000c841  inc     rdx; unsigned __int64
0x18000c844  mov     rcx, rax; char *
0x18000c847  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000c84c  cmp     dword ptr [rsp+1C50h+var_1C20], 0
0x18000c851  jz      short loc_18000C8AA
0x18000c853  mov     rdx, r15
0x18000c856  inc     rdx
0x18000c859  cmp     byte ptr [rdi+rdx], 0
0x18000c85d  jnz     short loc_18000C856
0x18000c85f  inc     rdx; uBytes
0x18000c862  xor     ecx, ecx; uFlags
0x18000c864  call    cs:__imp_LocalAlloc
0x18000c86a  mov     r10, rax
0x18000c86d  inc     r15
0x18000c870  cmp     byte ptr [rdi+r15], 0
0x18000c875  jnz     short loc_18000C86D
0x18000c877  lea     rdx, [r15+1]; unsigned __int64
0x18000c87b  mov     r8, rdi; char *
0x18000c87e  mov     rcx, r10; char *
0x18000c881  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000c886  mov     r9, [rsp+1C50h+lpString1]; lParam
0x18000c88b  mov     r8, r10; wParam
0x18000c88e  mov     edx, 615h; Msg
0x18000c893  mov     rcx, [rsi+40h]; hWnd
0x18000c897  call    cs:__imp_PostMessageA
0x18000c89d  mov     dword ptr [r13+0], 1
0x18000c8a5  jmp     loc_18000CAF1
0x18000c8aa  mov     r12d, [rsp+1C50h+var_1BE8]
0x18000c8af  cmp     r12d, 0FFFFFFFFh
0x18000c8b3  jz      loc_18000C9DE
0x18000c8b9  mov     rdx, rdi; char *
0x18000c8bc  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x18000c8c1  mov     rbx, rax
0x18000c8c4  test    rax, rax
0x18000c8c7  jz      short loc_18000C8E3
0x18000c8c9  test    r14, r14
0x18000c8cc  jnz     short loc_18000C8E3
0x18000c8ce  lea     r8, [rsp+1C50h+var_1C08]; struct CExTitle **
0x18000c8d3  mov     rdx, rdi; char *
0x18000c8d6  mov     rcx, rax; this
0x18000c8d9  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x18000c8de  mov     r14, [rsp+1C50h+var_1C08]
0x18000c8e3  test    rsi, rsi
0x18000c8e6  jz      loc_18000C9DE
0x18000c8ec  test    rbx, rbx
0x18000c8ef  jz      loc_18000C9DE
0x18000c8f5  cmp     dword ptr [rbx+448h], 0
0x18000c8fc  jnz     loc_18000C9DE
0x18000c902  test    r14, r14
0x18000c905  jnz     short loc_18000C91C
0x18000c907  lea     r8, [rsp+1C50h+var_1C08]; struct CExTitle **
0x18000c90c  mov     rdx, rdi; char *
0x18000c90f  mov     rcx, rbx; this
0x18000c912  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x18000c917  mov     r14, [rsp+1C50h+var_1C08]
0x18000c91c  mov     dword ptr [rsp+1C50h+var_1C30], 0; int
0x18000c924  mov     eax, 1
0x18000c929  mov     r9d, eax; int
0x18000c92c  mov     r8d, eax; int
0x18000c92f  xor     edx, edx; unsigned int
0x18000c931  mov     rcx, r14; struct CExTitle *
0x18000c934  call    ?EnsureStorageAvailability@@YAJPEAVCExTitle@@IHHH@Z; EnsureStorageAvailability(CExTitle *,uint,int,int,int)
0x18000c939  test    eax, eax
0x18000c93b  jns     short loc_18000C970
0x18000c93d  cmp     eax, 80040065h
0x18000c942  jnz     short loc_18000C952
0x18000c944  xor     edx, edx; unsigned int
0x18000c946  mov     ecx, 454h; int
0x18000c94b  call    ?MsgBox@@YAHHI@Z; MsgBox(int,uint)
0x18000c950  jmp     short loc_18000C959
0x18000c952  cmp     eax, 80004005h
0x18000c957  jz      short loc_18000C961
0x18000c959  mov     dword ptr [r13+0], 1
0x18000c961  mov     dword ptr [rsi+234h], 0
0x18000c96b  jmp     loc_18000CAF1
0x18000c970  cmp     eax, 40064h
0x18000c975  jnz     short loc_18000C9DE
0x18000c977  lea     r8, [rbp+1B50h+var_18D0]; char *
  ... truncated ...
```
