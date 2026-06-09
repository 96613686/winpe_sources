# CSH::SH_GetMyDocumentsDisplayName(ushort *,uint)

- ea: `0x140028ea0`
- end: `0x1400292e7`
- name: `?SH_GetMyDocumentsDisplayName@CSH@@SAHPEAGI@Z`
- size: `1095`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1400278e8`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140028ea0`
- `0x14002a720`
- `0x140112010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140028ff3`
- `ole32!CoTaskMemFree` at `0x140029191`
- `ole32!CoTaskMemFree` at `0x140028ff3`
- `ole32!CoTaskMemFree` at `0x140029191`
- `SHELL32!SHGetSpecialFolderLocation` at `0x140029106`
- `SHELL32!SHGetSpecialFolderLocation` at `0x140029106`
- `SHELL32!SHGetDesktopFolder` at `0x140028f0c`
- `SHELL32!SHGetDesktopFolder` at `0x140028f0c`

## pseudocode

```c
__int64 __fastcall CSH::SH_GetMyDocumentsDisplayName(unsigned __int16 *a1)
{
  int v2; // edi
  int v3; // edi
  int v4; // ebx
  PVOID *v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rdx
  void (*Release)(void); // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  HRESULT v14; // edi
  unsigned int v15; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _STRRET v18; // [rsp+50h] [rbp-B0h] BYREF
  IShellFolder *ppshf; // [rsp+1A0h] [rbp+A0h] BYREF
  int v20; // [rsp+1A8h] [rbp+A8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+1B0h] [rbp+B0h] BYREF
  LPVOID pv; // [rsp+1B8h] [rbp+B8h] BYREF

  ppshf = 0;
  ppidl = 0;
  v17 = 0;
  v20 = 0;
  memset_0(&v18, 0, sizeof(v18));
  if ( a1 )
  {
    *a1 = 0;
    if ( SHGetDesktopFolder(&ppshf) < 0 )
    {
LABEL_52:
      v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_53:
      if ( !ppshf )
      {
LABEL_56:
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        return 0;
      }
      ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
      ppshf = 0;
LABEL_55:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    if ( !ppshf )
      goto LABEL_55;
    v2 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, _QWORD, const wchar_t *, int *, __int64 *, _QWORD))ppshf->lpVtbl->ParseDisplayName)(
           ppshf,
           0,
           0,
           L"::{450d8fba-ad25-11d0-98a8-0800361b1103}",
           &v20,
           &v17,
           0);
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 40;
        goto LABEL_29;
      }
    }
    else
    {
      v2 = ((__int64 (__fastcall *)(IShellFolder *, __int64, __int64, _STRRET *))ppshf->lpVtbl->GetDisplayNameOf)(
             ppshf,
             v17,
             1,
             &v18);
      if ( v2 >= 0 )
      {
        pv = 0;
        v3 = XStrRetToStrW(&v18, ppidl, (unsigned __int16 **)&pv);
        if ( v3 >= 0 )
        {
          v4 = StringCchCopyW(a1, 0x104u, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
          if ( v4 < 0 )
          {
            v5 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_53;
            }
            v6 = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 37;
            goto LABEL_12;
          }
          Release = (void (*)(void))ppshf->lpVtbl->Release;
          goto LABEL_15;
        }
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 38;
LABEL_20:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v10, v3);
        goto LABEL_52;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 39;
LABEL_29:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v12, v2);
      }
    }
    v14 = SHGetSpecialFolderLocation(0, 5, &ppidl);
    if ( v14 < 0 || !ppidl )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v15, v14);
      goto LABEL_52;
    }
    v3 = ((__int64 (__fastcall *)(IShellFolder *, LPITEMIDLIST, __int64, _STRRET *))ppshf->lpVtbl->GetDisplayNameOf)(
           ppshf,
           ppidl,
           1,
           &v18);
    if ( v3 < 0 )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 43;
    }
    else
    {
      pv = 0;
      v3 = XStrRetToStrW(&v18, ppidl, (unsigned __int16 **)&pv);
      if ( v3 >= 0 )
      {
        v4 = StringCchCopyW(a1, 0x104u, (const unsigned __int16 *)pv);
        CoTaskMemFree(pv);
        if ( v4 < 0 )
        {
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 41;
LABEL_12:
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v6, v4);
          goto LABEL_52;
        }
        Release = (void (*)(void))ppshf->lpVtbl->Release;
LABEL_15:
        Release();
        return 1;
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 42;
    }
    goto LABEL_20;
  }
  return 0;
}

```

## disassembly

```asm
0x140028ea0  mov     [rsp-8+arg_8], edx
0x140028ea4  push    rbp
0x140028ea5  push    rbx
0x140028ea6  push    rdi
0x140028ea7  push    r12
0x140028ea9  push    r13
0x140028eab  push    r14
0x140028ead  lea     rbp, [rsp-68h]
0x140028eb2  sub     rsp, 168h
0x140028eb9  mov     rbx, rcx
0x140028ebc  mov     [rbp+90h+ppshf], 0
0x140028ec7  lea     rcx, [rsp+190h+var_140]; void *
0x140028ecc  mov     [rbp+90h+ppidl], 0
0x140028ed7  xor     edx, edx; Val
0x140028ed9  mov     [rsp+190h+var_150], 0
0x140028ee2  mov     r8d, 110h; Size
0x140028ee8  mov     [rbp+90h+arg_8], 0
0x140028ef2  call    memset_0
0x140028ef7  test    rbx, rbx
0x140028efa  jz      loc_1400292D4
0x140028f00  xor     eax, eax
0x140028f02  lea     rcx, [rbp+90h+ppshf]; ppshf
0x140028f09  mov     [rbx], ax
0x140028f0c  call    cs:__imp_SHGetDesktopFolder
0x140028f12  mov     r14d, 1
0x140028f18  lea     r12, WPP_GLOBAL_Control
0x140028f1f  lea     r13, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140028f26  test    eax, eax
0x140028f28  js      loc_14002926F
0x140028f2e  mov     rcx, [rbp+90h+ppshf]
0x140028f35  test    rcx, rcx
0x140028f38  jz      loc_14002929C
0x140028f3e  mov     rax, [rcx]
0x140028f41  lea     rdx, [rsp+190h+var_150]
0x140028f46  mov     [rsp+190h+var_160], 0
0x140028f4f  lea     r9, a450d8fbaAd2511; "::{450d8fba-ad25-11d0-98a8-0800361b1103"...
0x140028f56  mov     [rsp+190h+var_168], rdx
0x140028f5b  xor     r8d, r8d
0x140028f5e  lea     rdx, [rbp+90h+arg_8]
0x140028f65  mov     rax, [rax+18h]
0x140028f69  mov     [rsp+190h+var_170], rdx
0x140028f6e  xor     edx, edx
0x140028f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028f75  mov     edi, eax
0x140028f77  test    eax, eax
0x140028f79  js      loc_1400290BC
0x140028f7f  mov     rcx, [rbp+90h+ppshf]
0x140028f86  lea     r9, [rsp+190h+var_140]
0x140028f8b  mov     rdx, [rsp+190h+var_150]
0x140028f90  mov     r8d, r14d
0x140028f93  mov     rax, [rcx]
0x140028f96  mov     rax, [rax+58h]
0x140028f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028f9f  mov     edi, eax
0x140028fa1  test    eax, eax
0x140028fa3  js      loc_140029098
0x140028fa9  mov     rdx, [rbp+90h+ppidl]; struct _ITEMIDLIST *
0x140028fb0  lea     r8, [rbp+90h+pv]; unsigned __int16 **
0x140028fb7  lea     rcx, [rsp+190h+var_140]; struct _STRRET *
0x140028fbc  mov     [rbp+90h+pv], 0
0x140028fc7  call    ?XStrRetToStrW@@YAJPEAU_STRRET@@PEFBU_ITEMIDLIST@@PEAPEAG@Z; XStrRetToStrW(_STRRET *,_ITEMIDLIST const *,ushort * *)
0x140028fcc  mov     edi, eax
0x140028fce  test    eax, eax
0x140028fd0  js      loc_140029064
0x140028fd6  mov     r8, [rbp+90h+pv]; unsigned __int16 *
0x140028fdd  mov     edx, 104h; unsigned __int64
0x140028fe2  mov     rcx, rbx; unsigned __int16 *
0x140028fe5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140028fea  mov     rcx, [rbp+90h+pv]; pv
0x140028ff1  mov     ebx, eax
0x140028ff3  call    cs:__imp_CoTaskMemFree
0x140028ff9  test    ebx, ebx
0x140028ffb  jns     short loc_140029049
0x140028ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140029004  cmp     rcx, r12
0x140029007  jz      loc_140029276
0x14002900d  test    [rcx+1Ch], r14b
0x140029011  jz      loc_140029276
0x140029017  cmp     byte ptr [rcx+19h], 2
0x14002901b  jb      loc_140029276
0x140029021  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029026  lea     edx, [r14+24h]
0x14002902a  mov     dword ptr [rsp+190h+var_170], ebx
0x14002902e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029035  mov     r9d, eax
0x140029038  mov     r8, r13
0x14002903b  mov     rcx, [rcx+10h]
0x14002903f  call    WPP_SF_Dd
0x140029044  jmp     loc_14002926F
0x140029049  mov     rcx, [rbp+90h+ppshf]
0x140029050  mov     rdx, [rcx]
0x140029053  mov     rax, [rdx+10h]
0x140029057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002905c  mov     eax, r14d
0x14002905f  jmp     loc_1400292D6
0x140029064  mov     rcx, cs:WPP_GLOBAL_Control
0x14002906b  cmp     rcx, r12
0x14002906e  jz      loc_140029276
0x140029074  test    [rcx+1Ch], r14b
0x140029078  jz      loc_140029276
0x14002907e  cmp     byte ptr [rcx+19h], 2
0x140029082  jb      loc_140029276
0x140029088  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002908d  mov     edx, 26h ; '&'
0x140029092  mov     dword ptr [rsp+190h+var_170], edi
0x140029096  jmp     short loc_14002902E
0x140029098  mov     rax, cs:WPP_GLOBAL_Control
0x14002909f  cmp     rax, r12
0x1400290a2  jz      short loc_1400290F8
0x1400290a4  test    [rax+1Ch], r14b
0x1400290a8  jz      short loc_1400290F8
0x1400290aa  cmp     byte ptr [rax+19h], 2
0x1400290ae  jb      short loc_1400290F8
0x1400290b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400290b5  mov     edx, 27h ; '''
0x1400290ba  jmp     short loc_1400290DE
0x1400290bc  mov     rax, cs:WPP_GLOBAL_Control
0x1400290c3  cmp     rax, r12
0x1400290c6  jz      short loc_1400290F8
0x1400290c8  test    [rax+1Ch], r14b
0x1400290cc  jz      short loc_1400290F8
0x1400290ce  cmp     byte ptr [rax+19h], 2
0x1400290d2  jb      short loc_1400290F8
0x1400290d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400290d9  mov     edx, 28h ; '('
0x1400290de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400290e5  mov     r9d, eax
0x1400290e8  mov     r8, r13
0x1400290eb  mov     dword ptr [rsp+190h+var_170], edi
0x1400290ef  mov     rcx, [rcx+10h]
0x1400290f3  call    WPP_SF_Dd
0x1400290f8  lea     r8, [rbp+90h+ppidl]; ppidl
0x1400290ff  mov     edx, 5; csidl
0x140029104  xor     ecx, ecx; hwnd
0x140029106  call    cs:__imp_SHGetSpecialFolderLocation
0x14002910c  mov     edi, eax
0x14002910e  test    eax, eax
0x140029110  js      loc_140029233
0x140029116  mov     rdx, [rbp+90h+ppidl]
0x14002911d  test    rdx, rdx
0x140029120  jz      loc_140029233
0x140029126  mov     rcx, [rbp+90h+ppshf]
0x14002912d  lea     r9, [rsp+190h+var_140]
0x140029132  mov     r8d, r14d
0x140029135  mov     rax, [rcx]
0x140029138  mov     rax, [rax+58h]
0x14002913c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029141  mov     edi, eax
0x140029143  test    eax, eax
0x140029145  js      loc_14002920C
0x14002914b  mov     rdx, [rbp+90h+ppidl]; struct _ITEMIDLIST *
0x140029152  lea     r8, [rbp+90h+pv]; unsigned __int16 **
0x140029159  lea     rcx, [rsp+190h+var_140]; struct _STRRET *
0x14002915e  mov     [rbp+90h+pv], 0
0x140029169  call    ?XStrRetToStrW@@YAJPEAU_STRRET@@PEFBU_ITEMIDLIST@@PEAPEAG@Z; XStrRetToStrW(_STRRET *,_ITEMIDLIST const *,ushort * *)
0x14002916e  mov     edi, eax
0x140029170  test    eax, eax
0x140029172  js      short loc_1400291E1
0x140029174  mov     r8, [rbp+90h+pv]; unsigned __int16 *
0x14002917b  mov     edx, 104h; unsigned __int64
0x140029180  mov     rcx, rbx; unsigned __int16 *
0x140029183  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140029188  mov     rcx, [rbp+90h+pv]; pv
0x14002918f  mov     ebx, eax
0x140029191  call    cs:__imp_CoTaskMemFree
0x140029197  test    ebx, ebx
0x140029199  jns     short loc_1400291CE
0x14002919b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291a2  cmp     rcx, r12
0x1400291a5  jz      loc_140029276
0x1400291ab  test    [rcx+1Ch], r14b
0x1400291af  jz      loc_140029276
0x1400291b5  cmp     byte ptr [rcx+19h], 2
0x1400291b9  jb      loc_140029276
0x1400291bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400291c4  mov     edx, 29h ; ')'
0x1400291c9  jmp     loc_14002902A
0x1400291ce  mov     rcx, [rbp+90h+ppshf]
0x1400291d5  mov     rax, [rcx]
0x1400291d8  mov     rax, [rax+10h]
0x1400291dc  jmp     loc_140029057
0x1400291e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291e8  cmp     rcx, r12
0x1400291eb  jz      loc_140029276
0x1400291f1  test    [rcx+1Ch], r14b
0x1400291f5  jz      short loc_140029276
0x1400291f7  cmp     byte ptr [rcx+19h], 2
0x1400291fb  jb      short loc_140029276
0x1400291fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029202  mov     edx, 2Ah ; '*'
0x140029207  jmp     loc_140029092
0x14002920c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029213  cmp     rcx, r12
0x140029216  jz      short loc_140029276
0x140029218  test    [rcx+1Ch], r14b
0x14002921c  jz      short loc_140029276
0x14002921e  cmp     byte ptr [rcx+19h], 2
0x140029222  jb      short loc_140029276
0x140029224  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029229  mov     edx, 2Bh ; '+'
0x14002922e  jmp     loc_140029092
0x140029233  mov     rcx, cs:WPP_GLOBAL_Control
0x14002923a  cmp     rcx, r12
0x14002923d  jz      short loc_140029276
0x14002923f  test    [rcx+1Ch], r14b
0x140029243  jz      short loc_140029276
0x140029245  cmp     byte ptr [rcx+19h], 2
0x140029249  jb      short loc_140029276
0x14002924b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140029250  mov     rcx, cs:WPP_GLOBAL_Control
0x140029257  mov     edx, 2Ch ; ','
0x14002925c  mov     r9d, eax
0x14002925f  mov     dword ptr [rsp+190h+var_170], edi
0x140029263  mov     r8, r13
0x140029266  mov     rcx, [rcx+10h]
0x14002926a  call    WPP_SF_Dd
0x14002926f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029276  mov     rdx, [rbp+90h+ppshf]
0x14002927d  test    rdx, rdx
0x140029280  jz      short loc_1400292A3
0x140029282  mov     rax, [rdx]
0x140029285  mov     rcx, rdx
0x140029288  mov     rax, [rax+10h]
0x14002928c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029291  mov     [rbp+90h+ppshf], 0
0x14002929c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292a3  cmp     rcx, r12
0x1400292a6  jz      short loc_1400292D4
0x1400292a8  test    [rcx+1Ch], r14b
0x1400292ac  jz      short loc_1400292D4
0x1400292ae  cmp     byte ptr [rcx+19h], 2
0x1400292b2  jb      short loc_1400292D4
0x1400292b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400292b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292c0  mov     edx, 2Dh ; '-'
0x1400292c5  mov     r9d, eax
0x1400292c8  mov     r8, r13
0x1400292cb  mov     rcx, [rcx+10h]
0x1400292cf  call    WPP_SF_d
0x1400292d4  xor     eax, eax
0x1400292d6  add     rsp, 168h
0x1400292dd  pop     r14
0x1400292df  pop     r13
0x1400292e1  pop     r12
0x1400292e3  pop     rdi
0x1400292e4  pop     rbx
0x1400292e5  pop     rbp
0x1400292e6  retn
```
