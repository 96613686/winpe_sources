# CAddProgram::AddProgramsToList(IShellFolder *)

- ea: `0x180027438`
- end: `0x1800277bc`
- name: `?AddProgramsToList@CAddProgram@@AEAAJPEAUIShellFolder@@@Z`
- size: `900`
- prototype: `__int64 __fastcall(CAddProgram *__hidden this, IShellFolder *pshf)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800278b8`
- `0x180028110`

## callees

- `0x180008178`
- `0x180027438`
- `0x180027ab4`
- `0x180027b6c`
- `0x180028930`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800276a6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800276d5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800276a6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800276d5`
- `SHCORE!__imp_StrRetToBufW` at `0x18002764d`
- `SHCORE!__imp_StrRetToBufW` at `0x18002764d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800276f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002771b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800276f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002771b`
- `OLEAUT32!__imp_SysFreeString` at `0x180027758`
- `OLEAUT32!__imp_SysFreeString` at `0x180027758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800276e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800276e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027774`
- `SHELL32!__imp_SHMapPIDLToSystemImageListIndex` at `0x180027678`
- `SHELL32!__imp_SHMapPIDLToSystemImageListIndex` at `0x180027678`

## pseudocode

```c
__int64 __fastcall CAddProgram::AddProgramsToList(CAddProgram *this, IShellFolder *pshf)
{
  struct IShellFolderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *EnumObjects)(IShellFolder *, HWND, SHCONTF, IEnumIDList **); // rax
  int v6; // ebx
  struct IShellFolderVtbl *v7; // rax
  __int64 v8; // rdx
  HRESULT (__stdcall *GetUIObjectOf)(IShellFolder *, HWND, UINT, LPCITEMIDLIST *, const IID *const, UINT *, void **); // rax
  __int64 v10; // rax
  CAddProgram *v11; // rcx
  int v12; // r14d
  DWORD v13; // ebx
  DWORD v14; // ebx
  WCHAR *v15; // rax
  WCHAR *v16; // rdi
  unsigned __int16 *v17; // rbx
  WCHAR *v18; // rcx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IShellLinkW *v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  STRRET pstr; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[592]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Src[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  WCHAR Dst[264]; // [rsp+5D0h] [rbp+4D0h] BYREF
  WCHAR pszBuf[264]; // [rsp+7E0h] [rbp+6E0h] BYREF

  lpVtbl = pshf->lpVtbl;
  v24 = 0;
  pidl = 0;
  EnumObjects = lpVtbl->EnumObjects;
  v21 = 0;
  v6 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))EnumObjects)(pshf, 0, 64, &v24);
  if ( v6 >= 0 )
  {
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)v24 + 24LL))(
             v24,
             1,
             &pidl,
             &v21);
      if ( v6 || v21 != 1 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        return (unsigned int)v6;
      }
      v7 = pshf->lpVtbl;
      v22 = 1074266112;
      if ( ((int (__fastcall *)(IShellFolder *, _QWORD, LPCITEMIDLIST *, int *))v7->GetAttributesOf)(
             pshf,
             (unsigned int)(v6 + 1),
             &pidl,
             &v22) >= 0
        && (v22 & 0x80000) == 0 )
      {
        v8 = *((_QWORD *)this + 11);
        GetUIObjectOf = pshf->lpVtbl->GetUIObjectOf;
        v23 = 0;
        if ( ((int (__fastcall *)(IShellFolder *, __int64, _QWORD, LPCITEMIDLIST *, GUID *, _QWORD, struct IShellLinkW **))GetUIObjectOf)(
               pshf,
               v8,
               (unsigned int)(v6 + 1),
               &pidl,
               &IID_IShellLinkW,
               0,
               &v23) >= 0 )
          break;
      }
LABEL_29:
      CoTaskMemFree((LPVOID)pidl);
    }
    memset_0(Src, 0, 0x208u);
    if ( ((int (__fastcall *)(struct IShellLinkW *, WCHAR *, __int64))v23->lpVtbl->GetArguments)(v23, Src, 260) < 0 )
      goto LABEL_28;
    v10 = -1;
    do
      ++v10;
    while ( Src[v10] );
    if ( v10
      || (memset_0(v26, 0, sizeof(v26)),
          ((void (__fastcall *)(struct IShellLinkW *, WCHAR *, __int64, _BYTE *, int))v23->lpVtbl->GetPath)(
            v23,
            Src,
            260,
            v26,
            4),
          CAddProgram::ShouldIgnoreProgram(v11, v23, Src)) )
    {
LABEL_28:
      ((void (__fastcall *)(struct IShellLinkW *))v23->lpVtbl->Release)(v23);
      goto LABEL_29;
    }
    memset_0(&pstr, 0, sizeof(pstr));
    if ( ((unsigned int (__fastcall *)(IShellFolder *, LPCITEMIDLIST, __int64, STRRET *))pshf->lpVtbl->GetDisplayNameOf)(
           pshf,
           pidl,
           1,
           &pstr)
      || StrRetToBufW(&pstr, pidl, pszBuf, 0x104u) )
    {
      StringCchCopyW(pszBuf, 0x104u, Src);
    }
    v12 = SHMapPIDLToSystemImageListIndex(pshf, pidl, 0);
    memset_0(Dst, 0, 0x208u);
    v13 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( v13 >= 0x104 )
    {
      v14 = v13 + 1;
      v15 = (WCHAR *)CoTaskMemAlloc(2LL * v14);
      v16 = v15;
      if ( !v15 )
        goto LABEL_22;
      v13 = ExpandEnvironmentStringsW(Src, v15, v14);
      if ( !v13 )
      {
        CoTaskMemFree(v16);
        v16 = 0;
      }
      if ( v13 >= 0x104 )
      {
        v17 = SysAllocString(v16);
        CoTaskMemFree(v16);
        goto LABEL_24;
      }
    }
    v18 = Dst;
    if ( v13 )
    {
LABEL_23:
      v17 = SysAllocString(v18);
LABEL_24:
      if ( v17 )
      {
        if ( CAddProgram::IsAlreadyListed(this, v17) == -1 )
          CAddProgram::InsertItem(this, pszBuf, v17, v12, 0);
        else
          SysFreeString(v17);
      }
      goto LABEL_28;
    }
LABEL_22:
    v18 = Src;
    goto LABEL_23;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180027438  mov     [rsp-8+arg_10], rbx
0x18002743d  push    rbp
0x18002743e  push    rsi
0x18002743f  push    rdi
0x180027440  push    r12
0x180027442  push    r13
0x180027444  push    r14
0x180027446  push    r15
0x180027448  lea     rbp, [rsp-900h]
0x180027450  sub     rsp, 0A00h
0x180027457  mov     rax, cs:__security_cookie
0x18002745e  xor     rax, rsp
0x180027461  mov     [rbp+930h+var_40], rax
0x180027468  mov     rax, [rdx]
0x18002746b  lea     r9, [rsp+0A30h+var_9D8]
0x180027470  xor     r12d, r12d
0x180027473  mov     rsi, rdx
0x180027476  mov     r15, rcx
0x180027479  mov     [rsp+0A30h+var_9D8], r12
0x18002747e  xor     edx, edx
0x180027480  mov     [rsp+0A30h+pidl], r12
0x180027485  mov     rax, [rax+20h]
0x180027489  mov     rcx, rsi
0x18002748c  lea     r8d, [r12+40h]
0x180027491  mov     [rsp+0A30h+var_9E8], r12d
0x180027496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002749b  mov     ebx, eax
0x18002749d  test    eax, eax
0x18002749f  js      loc_180027790
0x1800274a5  mov     r13d, 104h
0x1800274ab  mov     rcx, [rsp+0A30h+var_9D8]
0x1800274b0  lea     r9, [rsp+0A30h+var_9E8]
0x1800274b5  lea     r8, [rsp+0A30h+pidl]
0x1800274ba  mov     edx, 1
0x1800274bf  mov     rax, [rcx]
0x1800274c2  mov     rax, [rax+18h]
0x1800274c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274cb  mov     ebx, eax
0x1800274cd  test    eax, eax
0x1800274cf  jnz     loc_18002777F
0x1800274d5  cmp     [rsp+0A30h+var_9E8], 1
0x1800274da  jnz     loc_18002777F
0x1800274e0  mov     rax, [rsi]
0x1800274e3  lea     r9, [rsp+0A30h+var_9E4]
0x1800274e8  lea     r8, [rsp+0A30h+pidl]
0x1800274ed  mov     [rsp+0A30h+var_9E4], 40080000h
0x1800274f5  lea     edx, [rbx+1]
0x1800274f8  mov     rcx, rsi
0x1800274fb  mov     rax, [rax+48h]
0x1800274ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027504  test    eax, eax
0x180027506  js      loc_18002776F
0x18002750c  test    [rsp+0A30h+var_9E4], 80000h
0x180027514  jnz     loc_18002776F
0x18002751a  mov     rax, [rsi]
0x18002751d  lea     rcx, [rsp+0A30h+var_9E0]
0x180027522  mov     rdx, [r15+58h]
0x180027526  lea     r9, [rsp+0A30h+pidl]
0x18002752b  mov     [rsp+0A30h+var_A00], rcx
0x180027530  lea     r8d, [rbx+1]
0x180027534  lea     rcx, IID_IShellLinkW
0x18002753b  mov     [rsp+0A30h+var_A08], r12
0x180027540  mov     rax, [rax+50h]
0x180027544  mov     qword ptr [rsp+0A30h+var_A10], rcx
0x180027549  mov     rcx, rsi
0x18002754c  mov     [rsp+0A30h+var_9E0], r12
0x180027551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027556  test    eax, eax
0x180027558  js      loc_18002776F
0x18002755e  xor     edx, edx; Val
0x180027560  lea     rcx, [rbp+930h+Src]; void *
0x180027567  mov     r8d, 208h; Size
0x18002756d  call    memset_0
0x180027572  mov     rcx, [rsp+0A30h+var_9E0]
0x180027577  lea     rdx, [rbp+930h+Src]
0x18002757e  mov     r8d, r13d
0x180027581  mov     rax, [rcx]
0x180027584  mov     rax, [rax+50h]
0x180027588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002758d  test    eax, eax
0x18002758f  js      loc_18002775E
0x180027595  lea     rcx, [rbp+930h+Src]
0x18002759c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800275a0  inc     rax
0x1800275a3  cmp     [rcx+rax*2], r12w
0x1800275a8  jnz     short loc_1800275A0
0x1800275aa  test    rax, rax
0x1800275ad  jnz     loc_18002775E
0x1800275b3  xor     edx, edx; Val
0x1800275b5  lea     rcx, [rbp+930h+var_8C0]; void *
0x1800275b9  mov     r8d, 250h; Size
0x1800275bf  call    memset_0
0x1800275c4  mov     rcx, [rsp+0A30h+var_9E0]
0x1800275c9  lea     r9, [rbp+930h+var_8C0]
0x1800275cd  mov     r8d, r13d
0x1800275d0  mov     [rsp+0A30h+var_A10], 4
0x1800275d8  lea     rdx, [rbp+930h+Src]
0x1800275df  mov     rax, [rcx]
0x1800275e2  mov     rax, [rax+18h]
0x1800275e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275eb  mov     rdx, [rsp+0A30h+var_9E0]; struct IShellLinkW *
0x1800275f0  lea     r8, [rbp+930h+Src]; unsigned __int16 *
0x1800275f7  call    ?ShouldIgnoreProgram@CAddProgram@@AEAAHPEAUIShellLinkW@@PEBG@Z; CAddProgram::ShouldIgnoreProgram(IShellLinkW *,ushort const *)
0x1800275fc  test    eax, eax
0x1800275fe  jnz     loc_18002775E
0x180027604  xor     edx, edx; Val
0x180027606  lea     rcx, [rsp+0A30h+pstr]; void *
0x18002760b  mov     r8d, 110h; Size
0x180027611  call    memset_0
0x180027616  mov     rax, [rsi]
0x180027619  lea     r9, [rsp+0A30h+pstr]
0x18002761e  mov     rdx, [rsp+0A30h+pidl]
0x180027623  mov     r8d, 1
0x180027629  mov     rcx, rsi
0x18002762c  mov     rax, [rax+58h]
0x180027630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027635  test    eax, eax
0x180027637  jnz     short loc_180027657
0x180027639  mov     rdx, [rsp+0A30h+pidl]; pidl
0x18002763e  lea     r8, [rbp+930h+pszBuf]; pszBuf
0x180027645  mov     r9d, r13d; cchBuf
0x180027648  lea     rcx, [rsp+0A30h+pstr]; pstr
0x18002764d  call    cs:__imp_StrRetToBufW
0x180027653  test    eax, eax
0x180027655  jz      short loc_18002766D
0x180027657  lea     r8, [rbp+930h+Src]; unsigned __int16 *
0x18002765e  mov     rdx, r13; unsigned __int64
0x180027661  lea     rcx, [rbp+930h+pszBuf]; unsigned __int16 *
0x180027668  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002766d  mov     rdx, [rsp+0A30h+pidl]; pidl
0x180027672  xor     r8d, r8d; piIndexSel
0x180027675  mov     rcx, rsi; pshf
0x180027678  call    cs:__imp_SHMapPIDLToSystemImageListIndex
0x18002767e  xor     edx, edx; Val
0x180027680  lea     rcx, [rbp+930h+Dst]; void *
0x180027687  mov     r8d, 208h; Size
0x18002768d  mov     r14d, eax
0x180027690  call    memset_0
0x180027695  mov     r8d, r13d; nSize
0x180027698  lea     rdx, [rbp+930h+Dst]; lpDst
0x18002769f  lea     rcx, [rbp+930h+Src]; lpSrc
0x1800276a6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800276ac  mov     ebx, eax
0x1800276ae  cmp     eax, r13d
0x1800276b1  jb      short loc_180027709
0x1800276b3  inc     ebx
0x1800276b5  mov     ecx, ebx
0x1800276b7  add     rcx, rcx; cb
0x1800276ba  call    cs:__imp_CoTaskMemAlloc
0x1800276c0  mov     rdi, rax
0x1800276c3  test    rax, rax
0x1800276c6  jz      short loc_180027714
0x1800276c8  mov     r8d, ebx; nSize
0x1800276cb  lea     rcx, [rbp+930h+Src]; lpSrc
0x1800276d2  mov     rdx, rax; lpDst
0x1800276d5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800276db  mov     ebx, eax
0x1800276dd  test    eax, eax
0x1800276df  jnz     short loc_1800276ED
0x1800276e1  mov     rcx, rdi; pv
0x1800276e4  call    cs:__imp_CoTaskMemFree
0x1800276ea  mov     rdi, r12
0x1800276ed  cmp     ebx, r13d
0x1800276f0  jb      short loc_180027709
0x1800276f2  mov     rcx, rdi; psz
0x1800276f5  call    cs:__imp_SysAllocString
0x1800276fb  mov     rcx, rdi; pv
0x1800276fe  mov     rbx, rax
0x180027701  call    cs:__imp_CoTaskMemFree
0x180027707  jmp     short loc_180027724
0x180027709  lea     rcx, [rbp+930h+Dst]
0x180027710  test    ebx, ebx
0x180027712  jnz     short loc_18002771B
0x180027714  lea     rcx, [rbp+930h+Src]; psz
0x18002771b  call    cs:__imp_SysAllocString
0x180027721  mov     rbx, rax
0x180027724  test    rbx, rbx
0x180027727  jz      short loc_18002775E
0x180027729  mov     rdx, rbx; unsigned __int16 *
0x18002772c  mov     rcx, r15; this
0x18002772f  call    ?IsAlreadyListed@CAddProgram@@AEAAHPEAG@Z; CAddProgram::IsAlreadyListed(ushort *)
0x180027734  cmp     eax, 0FFFFFFFFh
0x180027737  jnz     short loc_180027755
0x180027739  mov     r9d, r14d; int
0x18002773c  mov     [rsp+0A30h+var_A10], r12d; int
0x180027741  mov     r8, rbx; unsigned __int16 *
0x180027744  lea     rdx, [rbp+930h+pszBuf]; unsigned __int16 *
0x18002774b  mov     rcx, r15; this
0x18002774e  call    ?InsertItem@CAddProgram@@AEAAHPEAG0HH@Z; CAddProgram::InsertItem(ushort *,ushort *,int,int)
0x180027753  jmp     short loc_18002775E
0x180027755  mov     rcx, rbx; bstrString
0x180027758  call    cs:__imp_SysFreeString
0x18002775e  mov     rcx, [rsp+0A30h+var_9E0]
0x180027763  mov     rax, [rcx]
0x180027766  mov     rax, [rax+10h]
0x18002776a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776f  mov     rcx, [rsp+0A30h+pidl]; pv
0x180027774  call    cs:__imp_CoTaskMemFree
0x18002777a  jmp     loc_1800274AB
0x18002777f  mov     rcx, [rsp+0A30h+var_9D8]
0x180027784  mov     rax, [rcx]
0x180027787  mov     rax, [rax+10h]
0x18002778b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027790  mov     eax, ebx
0x180027792  mov     rcx, [rbp+930h+var_40]
0x180027799  xor     rcx, rsp; StackCookie
0x18002779c  call    __security_check_cookie
0x1800277a1  mov     rbx, [rsp+0A30h+arg_10]
0x1800277a9  add     rsp, 0A00h
0x1800277b0  pop     r15
0x1800277b2  pop     r14
0x1800277b4  pop     r13
0x1800277b6  pop     r12
0x1800277b8  pop     rdi
0x1800277b9  pop     rsi
0x1800277ba  pop     rbp
0x1800277bb  retn
```
