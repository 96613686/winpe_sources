# CMessageContextMenu::SearchByProperty(HWND__ *,_tagpropertykey const &,_tagpropertykey const &)

- ea: `0x18001dac4`
- end: `0x18001deed`
- name: `?SearchByProperty@CMessageContextMenu@@IEAAJPEAUHWND__@@AEBU_tagpropertykey@@1@Z`
- size: `1065`
- prototype: `__int64 __fastcall(CMessageContextMenu *this, HWND, const struct _tagpropertykey *, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c020`

## callees

- `0x180005210`
- `0x180006dcc`
- `0x180008730`
- `0x18001968c`
- `0x18001b3d4`
- `0x18001dac4`
- `0x18001e808`
- `0x18001e974`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de3c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dead`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001dead`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dcc6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dcc6`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18001dba6`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18001dba6`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001de60`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18001de60`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18001ddbd`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18001ddbd`
- `PROPSYS!PSGetPropertyDescription` at `0x18001dc3a`
- `PROPSYS!PSGetPropertyDescription` at `0x18001dc3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMessageContextMenu::SearchByProperty(
        CMessageContextMenu *this,
        HWND a2,
        const struct _tagpropertykey *a3,
        const struct _tagpropertykey *a4)
{
  int v4; // esi
  int DateRangeForDay; // ebx
  CMessageContextMenu *v8; // rcx
  const struct _GUID *v9; // r9
  int v10; // r8d
  signed int LastError; // eax
  int v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v15; // [rsp+48h] [rbp-B8h] BYREF
  void *v16; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertyStore *v17; // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST v18; // [rsp+60h] [rbp-A0h] BYREF
  void *v19; // [rsp+68h] [rbp-98h] BYREF
  void *ppv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  void *v22; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT v23[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+98h] [rbp-68h]
  PROPVARIANT v25[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPCITEMIDLIST pidl; // [rsp+B0h] [rbp-50h]
  struct tagPROPVARIANT pvar; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPROPVARIANT v28; // [rsp+D0h] [rbp-30h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v30; // [rsp+180h] [rbp+80h] BYREF

  v4 = (int)a4;
  v22 = 0;
  DateRangeForDay = SHCreateItemWithParentHelper(
                      *((const struct _ITEMIDLIST_ABSOLUTE **)this + 12),
                      0,
                      **((const struct _ITEMID_CHILD ***)this + 13),
                      &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                      &v22);
  if ( DateRangeForDay >= 0 )
  {
    v21 = 0;
    DateRangeForDay = (*(__int64 (__fastcall **)(void *, __int64, GUID *, __int64 *))(*(_QWORD *)v22 + 64LL))(
                        v22,
                        96,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        &v21);
    if ( DateRangeForDay < 0 )
    {
LABEL_39:
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v21);
      goto LABEL_40;
    }
    ppv = 0;
    *(_OWORD *)v25 = 0;
    pidl = 0;
    DateRangeForDay = (*(__int64 (__fastcall **)(__int64, struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v21 + 40LL))(
                        v21,
                        &stru_180053F38,
                        v25);
    if ( DateRangeForDay < 0
      || LOWORD(v25[0]) == 65
      && (DateRangeForDay = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv),
          DateRangeForDay < 0) )
    {
LABEL_38:
      PropVariantClear(v25);
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
      goto LABEL_39;
    }
    v17 = 0;
    DateRangeForDay = (*(__int64 (__fastcall **)(void *, __int64, GUID *, struct IPropertyStore **))(*(_QWORD *)ppv + 64LL))(
                        ppv,
                        96,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        &v17);
    if ( DateRangeForDay < 0 )
    {
LABEL_37:
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v17);
      goto LABEL_38;
    }
    *(_OWORD *)v23 = 0;
    v24 = 0;
    DateRangeForDay = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))v17->lpVtbl->GetValue)(
                        v17,
                        a3,
                        v23);
    if ( DateRangeForDay < 0 || !LOWORD(v23[0]) )
    {
LABEL_36:
      PropVariantClear(v23);
      goto LABEL_37;
    }
    v19 = 0;
    DateRangeForDay = PSGetPropertyDescription(a3, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &v19);
    if ( DateRangeForDay < 0
      || (v30 = 0,
          DateRangeForDay = (*(__int64 (__fastcall **)(void *, unsigned __int16 *))(*(_QWORD *)v19 + 40LL))(v19, &v30),
          DateRangeForDay < 0) )
    {
LABEL_35:
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v19);
      goto LABEL_36;
    }
    v16 = 0;
    DateRangeForDay = CMessageContextMenu::CreateSearchFolderItemFactory(v8, a3, v17, v9, &v16);
    if ( DateRangeForDay < 0 )
    {
LABEL_34:
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v16);
      goto LABEL_35;
    }
    v15 = 0;
    DateRangeForDay = CoCreateInstance(
                        &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                        0,
                        0x17u,
                        &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                        &v15);
    if ( DateRangeForDay < 0 )
    {
LABEL_33:
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v15);
      goto LABEL_34;
    }
    v14 = 0;
    if ( v30 != 8 && v30 != 31 )
    {
      if ( v30 == 64 )
      {
        memset(&v28, 0, sizeof(v28));
        memset(&pvar, 0, sizeof(pvar));
        DateRangeForDay = CMessageContextMenu::GetDateRangeForDay(
                            (CMessageContextMenu *)((unsigned int)v30 - 64),
                            (struct _FILETIME)v23[1],
                            &v28,
                            &pvar);
        if ( DateRangeForDay >= 0 )
          DateRangeForDay = CreateConditionRange((_DWORD)v15, v4, v10, (unsigned int)&v28, v13, (__int64)&pvar);
        PropVariantClear((PROPVARIANT *)&pvar);
        PropVariantClear((PROPVARIANT *)&v28);
LABEL_19:
        if ( DateRangeForDay < 0 )
        {
LABEL_32:
          ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v14);
          goto LABEL_33;
        }
LABEL_20:
        DateRangeForDay = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v16 + 96LL))(v16);
        if ( DateRangeForDay >= 0 )
        {
          v18 = 0;
          DateRangeForDay = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST *))(*(_QWORD *)v16 + 112LL))(v16, &v18);
          if ( DateRangeForDay >= 0 )
          {
            pExecInfo.cbSize = 112;
            memset_0(&pExecInfo.fMask, 0, 0x6Cu);
            pExecInfo.fMask = 12;
            pExecInfo.hwnd = a2;
            pExecInfo.nShow = 1;
            pExecInfo.lpIDList = v18;
            pExecInfo.lpVerb = 0;
            if ( ShellExecuteExW(&pExecInfo) )
            {
              DateRangeForDay = 0;
            }
            else
            {
              LastError = GetLastError();
              DateRangeForDay = LastError;
              if ( LastError > 0 )
                DateRangeForDay = (unsigned __int16)LastError | 0x80070000;
              if ( DateRangeForDay >= 0 )
                DateRangeForDay = -2147467259;
            }
            ILFree(v18);
          }
        }
        goto LABEL_32;
      }
      if ( v30 != 4104 && v30 != 4127 )
        goto LABEL_20;
    }
    DateRangeForDay = CreateLeafCondition((_DWORD)v15, v4, 13, (unsigned int)v23, v13, 4);
    goto LABEL_19;
  }
LABEL_40:
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v22);
  return (unsigned int)DateRangeForDay;
}

```

## disassembly

```asm
0x18001dac4  mov     [rsp-8+arg_8], rbx
0x18001dac9  mov     [rsp-8+arg_10], rsi
0x18001dace  push    rbp
0x18001dacf  push    rdi
0x18001dad0  push    r14
0x18001dad2  lea     rbp, [rsp-60h]
0x18001dad7  sub     rsp, 160h
0x18001dade  mov     rsi, r9
0x18001dae1  mov     rdi, r8
0x18001dae4  mov     r14, rdx
0x18001dae7  mov     [rbp+70h+var_F0], 0
0x18001daef  mov     r8, [rcx+68h]
0x18001daf3  lea     rax, [rbp+70h+var_F0]
0x18001daf7  mov     [rsp+170h+var_150], rax; void **
0x18001dafc  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; struct _GUID *
0x18001db03  mov     r8, [r8]; struct _ITEMID_CHILD *
0x18001db06  xor     edx, edx; struct IShellFolder *
0x18001db08  mov     rcx, [rcx+60h]; struct _ITEMIDLIST_ABSOLUTE *
0x18001db0c  call    ?SHCreateItemWithParentHelper@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; SHCreateItemWithParentHelper(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)
0x18001db11  mov     ebx, eax
0x18001db13  test    eax, eax
0x18001db15  js      loc_18001DECA
0x18001db1b  mov     [rsp+170h+var_F8], 0
0x18001db24  mov     rcx, [rbp+70h+var_F0]
0x18001db28  mov     rax, [rcx]
0x18001db2b  lea     r9, [rsp+170h+var_F8]
0x18001db30  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001db37  mov     edx, 60h ; '`'
0x18001db3c  mov     rax, [rax+40h]
0x18001db40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db45  mov     ebx, eax
0x18001db47  test    eax, eax
0x18001db49  js      loc_18001DEBF
0x18001db4f  mov     [rsp+170h+ppv], 0
0x18001db58  xorps   xmm0, xmm0
0x18001db5b  xor     eax, eax
0x18001db5d  movups  xmmword ptr [rbp+70h+var_D0], xmm0
0x18001db61  mov     [rbp+70h+pidl], rax
0x18001db65  mov     rcx, [rsp+170h+var_F8]
0x18001db6a  mov     rax, [rcx]
0x18001db6d  lea     r8, [rbp+70h+var_D0]
0x18001db71  lea     rdx, stru_180053F38
0x18001db78  mov     rax, [rax+28h]
0x18001db7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db81  mov     ebx, eax
0x18001db83  test    eax, eax
0x18001db85  js      loc_18001DEA9
0x18001db8b  mov     eax, 41h ; 'A'
0x18001db90  cmp     ax, word ptr [rbp+70h+var_D0]
0x18001db94  jnz     short loc_18001DBB6
0x18001db96  lea     r8, [rsp+170h+ppv]; ppv
0x18001db9b  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18001dba2  mov     rcx, [rbp+70h+pidl]; pidl
0x18001dba6  call    cs:__imp_SHCreateItemFromIDList
0x18001dbac  mov     ebx, eax
0x18001dbae  test    eax, eax
0x18001dbb0  js      loc_18001DEA9
0x18001dbb6  mov     [rsp+170h+var_118], 0
0x18001dbbf  mov     rcx, [rsp+170h+ppv]
0x18001dbc4  mov     rax, [rcx]
0x18001dbc7  lea     r9, [rsp+170h+var_118]
0x18001dbcc  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001dbd3  mov     edx, 60h ; '`'
0x18001dbd8  mov     rax, [rax+40h]
0x18001dbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe1  mov     ebx, eax
0x18001dbe3  test    eax, eax
0x18001dbe5  js      loc_18001DE9E
0x18001dbeb  xorps   xmm0, xmm0
0x18001dbee  xor     eax, eax
0x18001dbf0  movups  xmmword ptr [rbp+70h+var_E8], xmm0
0x18001dbf4  mov     [rbp+70h+var_D8], rax
0x18001dbf8  mov     rcx, [rsp+170h+var_118]
0x18001dbfd  mov     rax, [rcx]
0x18001dc00  lea     r8, [rbp+70h+var_E8]
0x18001dc04  mov     rdx, rdi
0x18001dc07  mov     rax, [rax+28h]
0x18001dc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc10  mov     ebx, eax
0x18001dc12  test    eax, eax
0x18001dc14  js      loc_18001DE93
0x18001dc1a  xor     eax, eax
0x18001dc1c  cmp     ax, word ptr [rbp+70h+var_E8]
0x18001dc20  jz      loc_18001DE93
0x18001dc26  mov     [rsp+170h+var_108], rax
0x18001dc2b  lea     r8, [rsp+170h+var_108]; ppv
0x18001dc30  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18001dc37  mov     rcx, rdi; propkey
0x18001dc3a  call    cs:__imp_PSGetPropertyDescription
0x18001dc40  mov     ebx, eax
0x18001dc42  test    eax, eax
0x18001dc44  js      loc_18001DE88
0x18001dc4a  xor     eax, eax
0x18001dc4c  mov     [rbp+70h+arg_0], ax
0x18001dc53  mov     rcx, [rsp+170h+var_108]
0x18001dc58  mov     rax, [rcx]
0x18001dc5b  lea     rdx, [rbp+70h+arg_0]
0x18001dc62  mov     rax, [rax+28h]
0x18001dc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc6b  mov     ebx, eax
0x18001dc6d  test    eax, eax
0x18001dc6f  js      loc_18001DE88
0x18001dc75  mov     [rsp+170h+var_120], 0
0x18001dc7e  lea     rax, [rsp+170h+var_120]
0x18001dc83  mov     [rsp+170h+var_150], rax; void **
0x18001dc88  mov     r8, [rsp+170h+var_118]; struct IPropertyStore *
0x18001dc8d  mov     rdx, rdi; struct _tagpropertykey *
0x18001dc90  call    ?CreateSearchFolderItemFactory@CMessageContextMenu@@IEAAJAEBU_tagpropertykey@@PEAUIPropertyStore@@AEBU_GUID@@PEAPEAX@Z; CMessageContextMenu::CreateSearchFolderItemFactory(_tagpropertykey const &,IPropertyStore *,_GUID const &,void * *)
0x18001dc95  mov     ebx, eax
0x18001dc97  test    eax, eax
0x18001dc99  js      loc_18001DE7D
0x18001dc9f  mov     [rsp+170h+var_128], 0
0x18001dca8  lea     rax, [rsp+170h+var_128]
0x18001dcad  mov     [rsp+170h+var_150], rax; ppv
0x18001dcb2  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x18001dcb9  xor     edx, edx; pUnkOuter
0x18001dcbb  lea     r8d, [rdx+17h]; dwClsContext
0x18001dcbf  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x18001dcc6  call    cs:__imp_CoCreateInstance
0x18001dccc  mov     ebx, eax
0x18001dcce  test    eax, eax
0x18001dcd0  js      loc_18001DE72
0x18001dcd6  xor     edx, edx
0x18001dcd8  mov     [rsp+170h+var_130], rdx
0x18001dcdd  movzx   ecx, [rbp+70h+arg_0]
0x18001dce4  sub     ecx, 8
0x18001dce7  jz      short loc_18001DD04
0x18001dce9  sub     ecx, 17h
0x18001dcec  jz      short loc_18001DD04
0x18001dcee  sub     ecx, 21h ; '!'; this
0x18001dcf1  jz      loc_18001DDCE
0x18001dcf7  sub     ecx, 0FC8h
0x18001dcfd  jz      short loc_18001DD04
0x18001dcff  cmp     ecx, 17h
0x18001dd02  jnz     short loc_18001DD3C
0x18001dd04  lea     rax, [rsp+170h+var_130]
0x18001dd09  mov     [rsp+170h+var_138], rax
0x18001dd0e  mov     dword ptr [rsp+170h+var_148], 4
0x18001dd16  lea     r9, [rbp+70h+var_E8]
0x18001dd1a  mov     r8d, 0Dh
0x18001dd20  mov     rdx, rsi
0x18001dd23  mov     rcx, [rsp+170h+var_128]
0x18001dd28  call    _CreateLeafCondition
0x18001dd2d  mov     ebx, eax
0x18001dd2f  test    ebx, ebx
0x18001dd31  js      loc_18001DE67
0x18001dd37  mov     rdx, [rsp+170h+var_130]
0x18001dd3c  mov     rcx, [rsp+170h+var_120]
0x18001dd41  mov     rax, [rcx]
0x18001dd44  mov     rax, [rax+60h]
0x18001dd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd4d  mov     ebx, eax
0x18001dd4f  test    eax, eax
0x18001dd51  js      loc_18001DE67
0x18001dd57  mov     [rsp+170h+var_110], 0
0x18001dd60  mov     rcx, [rsp+170h+var_120]
0x18001dd65  mov     rax, [rcx]
0x18001dd68  lea     rdx, [rsp+170h+var_110]
0x18001dd6d  mov     rax, [rax+70h]
0x18001dd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd76  mov     ebx, eax
0x18001dd78  test    eax, eax
0x18001dd7a  js      loc_18001DE67
0x18001dd80  mov     [rbp+70h+pExecInfo.cbSize], 70h ; 'p'
0x18001dd87  xor     edx, edx; Val
0x18001dd89  lea     r8d, [rdx+6Ch]; Size
0x18001dd8d  lea     rcx, [rbp+70h+pExecInfo.fMask]; void *
0x18001dd91  call    memset_0
0x18001dd96  mov     [rbp+70h+pExecInfo.fMask], 0Ch
0x18001dd9d  mov     [rbp+70h+pExecInfo.hwnd], r14
0x18001dda1  mov     [rbp+70h+pExecInfo.nShow], 1
0x18001dda8  mov     rax, [rsp+170h+var_110]
0x18001ddad  mov     [rbp+70h+pExecInfo.lpIDList], rax
0x18001ddb1  mov     [rbp+70h+pExecInfo.lpVerb], 0
0x18001ddb9  lea     rcx, [rbp+70h+pExecInfo]; pExecInfo
0x18001ddbd  call    cs:__imp_ShellExecuteExW
0x18001ddc3  test    eax, eax
0x18001ddc5  jz      short loc_18001DE3C
0x18001ddc7  xor     ebx, ebx
0x18001ddc9  jmp     loc_18001DE5B
0x18001ddce  xorps   xmm0, xmm0
0x18001ddd1  xor     eax, eax
0x18001ddd3  movups  xmmword ptr [rbp+70h+var_A0], xmm0
0x18001ddd7  mov     [rbp+70h+var_90], rax
0x18001dddb  xorps   xmm1, xmm1
0x18001ddde  movups  xmmword ptr [rbp+70h+pvar], xmm1
0x18001dde2  mov     [rbp+70h+var_A8], rax
0x18001dde6  lea     r9, [rbp+70h+pvar]; struct tagPROPVARIANT *
0x18001ddea  lea     r8, [rbp+70h+var_A0]; struct tagPROPVARIANT *
0x18001ddee  mov     rdx, [rbp+70h+var_E8+8]; struct _FILETIME
0x18001ddf2  call    ?GetDateRangeForDay@CMessageContextMenu@@IEAAJU_FILETIME@@PEAUtagPROPVARIANT@@1@Z; CMessageContextMenu::GetDateRangeForDay(_FILETIME,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001ddf7  mov     ebx, eax
0x18001ddf9  test    eax, eax
0x18001ddfb  js      short loc_18001DE23
0x18001ddfd  lea     rax, [rsp+170h+var_130]
0x18001de02  mov     [rsp+170h+var_138], rax
0x18001de07  lea     rax, [rbp+70h+pvar]
0x18001de0b  mov     [rsp+170h+var_148], rax
0x18001de10  lea     r9, [rbp+70h+var_A0]
0x18001de14  mov     rdx, rsi
0x18001de17  mov     rcx, [rsp+170h+var_128]
0x18001de1c  call    _CreateConditionRange
0x18001de21  mov     ebx, eax
0x18001de23  lea     rcx, [rbp+70h+pvar]; pvar
0x18001de27  call    cs:__imp_PropVariantClear
0x18001de2d  lea     rcx, [rbp+70h+var_A0]; pvar
0x18001de31  call    cs:__imp_PropVariantClear
0x18001de37  jmp     loc_18001DD2F
0x18001de3c  call    cs:__imp_GetLastError
0x18001de42  mov     ebx, eax
0x18001de44  test    eax, eax
0x18001de46  jle     short loc_18001DE51
0x18001de48  movzx   ebx, ax
0x18001de4b  or      ebx, 80070000h
0x18001de51  mov     eax, 80004005h
0x18001de56  test    ebx, ebx
0x18001de58  cmovns  ebx, eax
0x18001de5b  mov     rcx, [rsp+170h+var_110]; pidl
0x18001de60  call    cs:__imp_ILFree
0x18001de66  nop
0x18001de67  lea     rcx, [rsp+170h+var_130]
0x18001de6c  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001de71  nop
0x18001de72  lea     rcx, [rsp+170h+var_128]
0x18001de77  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001de7c  nop
0x18001de7d  lea     rcx, [rsp+170h+var_120]
0x18001de82  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001de87  nop
0x18001de88  lea     rcx, [rsp+170h+var_108]
0x18001de8d  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001de92  nop
0x18001de93  lea     rcx, [rbp+70h+var_E8]; pvar
0x18001de97  call    cs:__imp_PropVariantClear
0x18001de9d  nop
0x18001de9e  lea     rcx, [rsp+170h+var_118]
0x18001dea3  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001dea8  nop
0x18001dea9  lea     rcx, [rbp+70h+var_D0]; pvar
0x18001dead  call    cs:__imp_PropVariantClear
0x18001deb3  nop
0x18001deb4  lea     rcx, [rsp+170h+ppv]
0x18001deb9  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001debe  nop
0x18001debf  lea     rcx, [rsp+170h+var_F8]
0x18001dec4  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001dec9  nop
0x18001deca  lea     rcx, [rbp+70h+var_F0]
0x18001dece  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18001ded3  mov     eax, ebx
0x18001ded5  lea     r11, [rsp+170h+var_10]
0x18001dedd  mov     rbx, [r11+28h]
0x18001dee1  mov     rsi, [r11+30h]
0x18001dee5  mov     rsp, r11
0x18001dee8  pop     r14
0x18001deea  pop     rdi
0x18001deeb  pop     rbp
0x18001deec  retn
```
