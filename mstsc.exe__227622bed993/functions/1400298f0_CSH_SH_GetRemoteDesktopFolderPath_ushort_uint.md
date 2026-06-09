# CSH::SH_GetRemoteDesktopFolderPath(ushort *,uint)

- ea: `0x1400298f0`
- end: `0x140029d2b`
- name: `?SH_GetRemoteDesktopFolderPath@CSH@@SAHPEAGI@Z`
- size: `1083`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400278e8`
- `0x1400293c4`

## callees

- `0x140008940`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14001e210`
- `0x1400298f0`
- `0x14009d598`
- `0x14009d824`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140029cde`
- `KERNEL32!GetCurrentDirectoryW` at `0x140029cde`
- `KERNEL32!LocalFree` at `0x140029961`
- `KERNEL32!LocalFree` at `0x140029961`
- `KERNEL32!GetLastError` at `0x140029d10`
- `KERNEL32!GetLastError` at `0x140029d10`
- `SHELL32!SHGetPathFromIDListW` at `0x140029b82`
- `SHELL32!SHGetPathFromIDListW` at `0x140029b82`
- `SHELL32!SHGetMalloc` at `0x140029b92`
- `SHELL32!SHGetMalloc` at `0x140029b92`
- `SHELL32!SHGetSpecialFolderLocation` at `0x140029b5b`
- `SHELL32!SHGetSpecialFolderLocation` at `0x140029b5b`

## string_xrefs

- `0x140029cad`: `Root folder in current directory.`

## pseudocode

```c
__int64 __fastcall CSH::SH_GetRemoteDesktopFolderPath(unsigned __int16 *a1)
{
  int v2; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v4; // rdx
  __int64 v5; // rax
  unsigned int v6; // eax
  int v7; // edx
  __int64 v8; // rax
  HRESULT v10; // esi
  BOOL v11; // esi
  __int64 v12; // rax
  int v13; // edi
  unsigned int v14; // eax
  PVOID *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  DWORD LastError; // ebx
  unsigned int v19; // eax
  IMalloc *ppMalloc; // [rsp+30h] [rbp-10h] BYREF
  int v21; // [rsp+78h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+88h] [rbp+48h] BYREF

  *a1 = 0;
  hMem = 0;
  v21 = 260;
  CUT::UT_ReadRegistryExpandSZ(L"Default", L"RemoteDesktopFolder", &hMem, &v21, 2);
  if ( !hMem )
  {
    CUT::UT_ReadRegistryStringCb(L"Default", L"RemoteDesktopFolder", &pszPassword, a1, 516, 2);
    if ( *a1 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a1[v8] );
      if ( a1[(int)v8 - 1] != 92 )
      {
        v2 = StringCchCatW(a1, 0x104u, L"\\");
        if ( v2 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 0;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v4 = 20;
          goto LABEL_7;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 21;
        goto LABEL_33;
      }
      return 1;
    }
    ppidl = 0;
    v10 = SHGetSpecialFolderLocation(0, 5, &ppidl);
    if ( v10 >= 0 && ppidl )
    {
      ppMalloc = 0;
      v11 = SHGetPathFromIDListW(ppidl, a1);
      if ( SHGetMalloc(&ppMalloc) >= 0 )
      {
        ((void (__fastcall *)(IMalloc *, LPITEMIDLIST))ppMalloc->lpVtbl->Free)(ppMalloc, ppidl);
        ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      if ( v11 )
        goto LABEL_40;
    }
    else
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_59;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_55:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        {
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
            v17,
            (__int64)L"Root folder in current directory.");
        }
LABEL_59:
        if ( !GetCurrentDirectoryW(0x104u, a1) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
              v19,
              LastError);
          }
          return 0;
        }
LABEL_40:
        v12 = -1;
        do
          ++v12;
        while ( a1[v12] );
        if ( (int)v12 >= 1 && a1[(int)v12 - 1] != 92 )
        {
          v13 = StringCchCatW(a1, 0x104u, L"\\");
          if ( v13 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
                v14,
                v13);
            }
            return 0;
          }
        }
        return 1;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v16, v10);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  v2 = StringCchCopyW(a1, 0x102u, (const unsigned __int16 *)hMem);
  LocalFree(hMem);
  if ( v2 >= 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    if ( a1[(int)v5 - 1] != 92 )
    {
      v2 = StringCchCatW(a1, 0x104u, L"\\");
      if ( v2 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 0;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v4 = 18;
        goto LABEL_7;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 19;
LABEL_33:
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
        v6,
        (__int64)a1);
      return 1;
    }
    return 1;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return 0;
  }
  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
  v4 = 17;
LABEL_7:
  WPP_SF_Dd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v4,
    WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
    CurrentThreadActivityIdPrefix,
    v2);
  return 0;
}

```

## disassembly

```asm
0x1400298f0  mov     [rsp-28h+arg_0], rbx
0x1400298f5  mov     [rsp-28h+arg_8], edx
0x1400298f9  push    rbp
0x1400298fa  push    rsi
0x1400298fb  push    rdi
0x1400298fc  push    r13
0x1400298fe  push    r14
0x140029900  mov     rbp, rsp
0x140029903  sub     rsp, 40h
0x140029907  xor     r14d, r14d
0x14002990a  mov     dword ptr [rsp+40h+var_20], 2
0x140029912  mov     [rcx], r14w
0x140029916  lea     r9, [rbp+arg_8]
0x14002991a  mov     rdi, rcx
0x14002991d  mov     [rbp+hMem], r14
0x140029921  mov     r13d, 104h
0x140029927  lea     rcx, aDefault_0; "Default"
0x14002992e  lea     r8, [rbp+hMem]
0x140029932  mov     [rbp+arg_8], r13d
0x140029936  lea     rdx, aRemotedesktopf; "RemoteDesktopFolder"
0x14002993d  call    ?UT_ReadRegistryExpandSZ@CUT@@SAHPEBG0PEAPEAGPEAHW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryExpandSZ(ushort const *,ushort const *,ushort * *,int *,UT_REGREAD_LOCATION)
0x140029942  mov     r8, [rbp+hMem]; unsigned __int16 *
0x140029946  test    r8, r8
0x140029949  jz      loc_140029A4B
0x14002994f  lea     edx, [r13-2]; unsigned __int64
0x140029953  mov     rcx, rdi; unsigned __int16 *
0x140029956  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002995b  mov     rcx, [rbp+hMem]; hMem
0x14002995f  mov     esi, eax
0x140029961  call    cs:__imp_LocalFree
0x140029967  test    esi, esi
0x140029969  jns     short loc_1400299A8
0x14002996b  mov     rax, cs:WPP_GLOBAL_Control
0x140029972  lea     rbx, WPP_GLOBAL_Control
0x140029979  cmp     rax, rbx
0x14002997c  jz      loc_140029C49
0x140029982  test    byte ptr [rax+1Ch], 1
0x140029986  jz      loc_140029C49
0x14002998c  cmp     byte ptr [rax+19h], 2
0x140029990  jb      loc_140029C49
0x140029996  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002999b  lea     edx, [r14+11h]
0x14002999f  mov     dword ptr [rsp+40h+var_20], esi
0x1400299a3  jmp     loc_140029C2F
0x1400299a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400299ac  inc     rax
0x1400299af  cmp     [rdi+rax*2], r14w
0x1400299b4  jnz     short loc_1400299AC
0x1400299b6  dec     eax
0x1400299b8  movsxd  rcx, eax
0x1400299bb  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x1400299c0  jz      short loc_140029A11
0x1400299c2  lea     r8, SubBlock; "\\"
0x1400299c9  mov     rdx, r13; unsigned __int64
0x1400299cc  mov     rcx, rdi; unsigned __int16 *
0x1400299cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400299d4  mov     esi, eax
0x1400299d6  test    eax, eax
0x1400299d8  jns     short loc_140029A11
0x1400299da  mov     rax, cs:WPP_GLOBAL_Control
0x1400299e1  lea     rbx, WPP_GLOBAL_Control
0x1400299e8  cmp     rax, rbx
0x1400299eb  jz      loc_140029C49
0x1400299f1  test    byte ptr [rax+1Ch], 1
0x1400299f5  jz      loc_140029C49
0x1400299fb  cmp     byte ptr [rax+19h], 2
0x1400299ff  jb      loc_140029C49
0x140029a05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029a0a  mov     edx, 12h
0x140029a0f  jmp     short loc_14002999F
0x140029a11  mov     rax, cs:WPP_GLOBAL_Control
0x140029a18  lea     rbx, WPP_GLOBAL_Control
0x140029a1f  cmp     rax, rbx
0x140029a22  jz      loc_140029B36
0x140029a28  test    byte ptr [rax+1Ch], 1
0x140029a2c  jz      loc_140029B36
0x140029a32  cmp     byte ptr [rax+19h], 4
0x140029a36  jb      loc_140029B36
0x140029a3c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029a41  mov     edx, 13h
0x140029a46  jmp     loc_140029B17
0x140029a4b  mov     [rsp+40h+var_18], 2
0x140029a53  lea     r8, pszPassword
0x140029a5a  mov     r9, rdi
0x140029a5d  mov     dword ptr [rsp+40h+var_20], 204h
0x140029a65  lea     rdx, aRemotedesktopf; "RemoteDesktopFolder"
0x140029a6c  lea     rcx, aDefault_0; "Default"
0x140029a73  call    ?UT_ReadRegistryStringCb@CUT@@SAXPEBG00PEAGHW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryStringCb(ushort const *,ushort const *,ushort const *,ushort *,int,UT_REGREAD_LOCATION)
0x140029a78  cmp     [rdi], r14w
0x140029a7c  jz      loc_140029B4C
0x140029a82  or      rax, 0FFFFFFFFFFFFFFFFh
0x140029a86  inc     rax
0x140029a89  cmp     [rdi+rax*2], r14w
0x140029a8e  jnz     short loc_140029A86
0x140029a90  dec     eax
0x140029a92  movsxd  rcx, eax
0x140029a95  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x140029a9a  jz      short loc_140029AEE
0x140029a9c  lea     r8, SubBlock; "\\"
0x140029aa3  mov     rdx, r13; unsigned __int64
0x140029aa6  mov     rcx, rdi; unsigned __int16 *
0x140029aa9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140029aae  mov     esi, eax
0x140029ab0  test    eax, eax
0x140029ab2  jns     short loc_140029AEE
0x140029ab4  mov     rax, cs:WPP_GLOBAL_Control
0x140029abb  lea     rbx, WPP_GLOBAL_Control
0x140029ac2  cmp     rax, rbx
0x140029ac5  jz      loc_140029C49
0x140029acb  test    byte ptr [rax+1Ch], 1
0x140029acf  jz      loc_140029C49
0x140029ad5  cmp     byte ptr [rax+19h], 2
0x140029ad9  jb      loc_140029C49
0x140029adf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029ae4  mov     edx, 14h
0x140029ae9  jmp     loc_14002999F
0x140029aee  mov     rax, cs:WPP_GLOBAL_Control
0x140029af5  lea     rbx, WPP_GLOBAL_Control
0x140029afc  cmp     rax, rbx
0x140029aff  jz      short loc_140029B36
0x140029b01  test    byte ptr [rax+1Ch], 1
0x140029b05  jz      short loc_140029B36
0x140029b07  cmp     byte ptr [rax+19h], 4
0x140029b0b  jb      short loc_140029B36
0x140029b0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029b12  mov     edx, 15h
0x140029b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140029b1e  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140029b25  mov     r9d, eax
0x140029b28  mov     [rsp+40h+var_20], rdi
0x140029b2d  mov     rcx, [rcx+10h]
0x140029b31  call    WPP_SF_DS
0x140029b36  mov     eax, 1
0x140029b3b  mov     rbx, [rsp+40h+arg_0]
0x140029b40  add     rsp, 40h
0x140029b44  pop     r14
0x140029b46  pop     r13
0x140029b48  pop     rdi
0x140029b49  pop     rsi
0x140029b4a  pop     rbp
0x140029b4b  retn
0x140029b4c  lea     r8, [rbp+ppidl]; ppidl
0x140029b50  mov     [rbp+ppidl], r14
0x140029b54  mov     edx, 5; csidl
0x140029b59  xor     ecx, ecx; hwnd
0x140029b5b  call    cs:__imp_SHGetSpecialFolderLocation
0x140029b61  lea     rbx, WPP_GLOBAL_Control
0x140029b68  mov     esi, eax
0x140029b6a  test    eax, eax
0x140029b6c  js      loc_140029C50
0x140029b72  mov     rcx, [rbp+ppidl]; pidl
0x140029b76  test    rcx, rcx
0x140029b79  jz      loc_140029C50
0x140029b7f  mov     rdx, rdi; pszPath
0x140029b82  call    cs:__imp_SHGetPathFromIDListW
0x140029b88  lea     rcx, [rbp+ppMalloc]; ppMalloc
0x140029b8c  mov     [rbp+ppMalloc], r14
0x140029b90  mov     esi, eax
0x140029b92  call    cs:__imp_SHGetMalloc
0x140029b98  test    eax, eax
0x140029b9a  js      short loc_140029BC0
0x140029b9c  mov     rcx, [rbp+ppMalloc]
0x140029ba0  mov     rdx, [rbp+ppidl]
0x140029ba4  mov     rax, [rcx]
0x140029ba7  mov     rax, [rax+28h]
0x140029bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bb0  mov     rcx, [rbp+ppMalloc]
0x140029bb4  mov     rax, [rcx]
0x140029bb7  mov     rax, [rax+10h]
0x140029bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bc0  test    esi, esi
0x140029bc2  jz      loc_140029C90
0x140029bc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140029bcc  inc     rax
0x140029bcf  cmp     [rdi+rax*2], r14w
0x140029bd4  jnz     short loc_140029BCC
0x140029bd6  cmp     eax, 1
0x140029bd9  jl      loc_140029B36
0x140029bdf  cdqe
0x140029be1  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x140029be7  jz      loc_140029B36
0x140029bed  lea     r8, SubBlock; "\\"
0x140029bf4  mov     rdx, r13; unsigned __int64
0x140029bf7  mov     rcx, rdi; unsigned __int16 *
0x140029bfa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140029bff  mov     edi, eax
0x140029c01  test    eax, eax
0x140029c03  jns     loc_140029B36
0x140029c09  mov     rax, cs:WPP_GLOBAL_Control
0x140029c10  cmp     rax, rbx
0x140029c13  jz      short loc_140029C49
0x140029c15  test    byte ptr [rax+1Ch], 1
0x140029c19  jz      short loc_140029C49
0x140029c1b  cmp     byte ptr [rax+19h], 2
0x140029c1f  jb      short loc_140029C49
0x140029c21  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029c26  mov     edx, 19h
0x140029c2b  mov     dword ptr [rsp+40h+var_20], edi
0x140029c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c36  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140029c3d  mov     r9d, eax
0x140029c40  mov     rcx, [rcx+10h]
0x140029c44  call    WPP_SF_Dd
0x140029c49  xor     eax, eax
0x140029c4b  jmp     loc_140029B3B
0x140029c50  mov     rax, cs:WPP_GLOBAL_Control
0x140029c57  cmp     rax, rbx
0x140029c5a  jz      short loc_140029CD8
0x140029c5c  test    byte ptr [rax+1Ch], 1
0x140029c60  jz      short loc_140029C97
0x140029c62  cmp     byte ptr [rax+19h], 2
0x140029c66  jb      short loc_140029C97
0x140029c68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c74  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140029c7b  mov     edx, 16h
0x140029c80  mov     dword ptr [rsp+40h+var_20], esi
0x140029c84  mov     r9d, eax
0x140029c87  mov     rcx, [rcx+10h]
0x140029c8b  call    WPP_SF_Dd
0x140029c90  mov     rax, cs:WPP_GLOBAL_Control
0x140029c97  cmp     rax, rbx
0x140029c9a  jz      short loc_140029CD8
0x140029c9c  test    byte ptr [rax+1Ch], 1
0x140029ca0  jz      short loc_140029CD8
0x140029ca2  cmp     byte ptr [rax+19h], 2
0x140029ca6  jb      short loc_140029CD8
0x140029ca8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029cad  lea     rcx, aRootFolderInCu; "Root folder in current directory."
0x140029cb4  mov     edx, 17h
0x140029cb9  mov     [rsp+40h+var_20], rcx
0x140029cbe  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140029cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140029ccc  mov     r9d, eax
0x140029ccf  mov     rcx, [rcx+10h]
0x140029cd3  call    WPP_SF_DS
0x140029cd8  mov     rdx, rdi; lpBuffer
0x140029cdb  mov     ecx, r13d; nBufferLength
0x140029cde  call    cs:__imp_GetCurrentDirectoryW
0x140029ce4  test    eax, eax
0x140029ce6  jnz     loc_140029BC8
0x140029cec  mov     rax, cs:WPP_GLOBAL_Control
0x140029cf3  cmp     rax, rbx
0x140029cf6  jz      loc_140029C49
0x140029cfc  test    byte ptr [rax+1Ch], 1
0x140029d00  jz      loc_140029C49
0x140029d06  cmp     byte ptr [rax+19h], 2
0x140029d0a  jb      loc_140029C49
0x140029d10  call    cs:__imp_GetLastError
0x140029d16  mov     ebx, eax
0x140029d18  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029d1d  mov     edx, 18h
0x140029d22  mov     dword ptr [rsp+40h+var_20], ebx
0x140029d26  jmp     loc_140029C2F
```
