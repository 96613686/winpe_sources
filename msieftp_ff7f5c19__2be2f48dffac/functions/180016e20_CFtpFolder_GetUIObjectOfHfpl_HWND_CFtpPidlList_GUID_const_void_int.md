# CFtpFolder::GetUIObjectOfHfpl(HWND__ *,CFtpPidlList *,_GUID const &,void * *,int)

- ea: `0x180016e20`
- end: `0x1800170b5`
- name: `?GetUIObjectOfHfpl@CFtpFolder@@QEAAJPEAUHWND__@@PEAVCFtpPidlList@@AEBU_GUID@@PEAPEAXH@Z`
- size: `661`
- prototype: `int(CFtpFolder *__hidden this, HWND, struct CFtpPidlList *, const struct _GUID *, void **, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f5b4`
- `0x18000fb64`
- `0x180018980`
- `0x180024fec`

## callees

- `0x18000d500`
- `0x1800161c0`
- `0x180016e20`
- `0x1800192b0`
- `0x1800199e0`
- `0x18001c4fc`
- `0x1800269f4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x18001708f`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x18001708f`
- `SHLWAPI!AssocCreate` at `0x180016fbe`
- `SHLWAPI!AssocCreate` at `0x180016fbe`

## pseudocode

```c
__int64 __fastcall CFtpFolder::GetUIObjectOfHfpl(
        CFtpFolder *this,
        HWND a2,
        struct CFtpPidlList *a3,
        const struct _GUID *a4,
        void **a5,
        int a6)
{
  int InfoTipFromItem2; // eax
  HRESULT v10; // esi
  void *v11; // rbx
  PVOID Ptr; // rax
  struct _DPA *v13; // rcx
  char Attributes; // al
  const wchar_t *v15; // r8
  PVOID v16; // rax
  struct _DPA *v17; // rcx
  void *ppv[2]; // [rsp+30h] [rbp-48h] BYREF
  CLSID clsid; // [rsp+40h] [rbp-38h] BYREF

  if ( *(_OWORD *)a4 == *(_OWORD *)&IID_IExtractIconA
    || *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1
    && *(_QWORD *)a4->Data4 == *(_QWORD *)IID_IExtractIconW.Data4 )
  {
    InfoTipFromItem2 = CFtpIcon_Create(this, a3, a4, a5);
    goto LABEL_35;
  }
  if ( *(_QWORD *)&a4->Data1 != *(_QWORD *)&IID_IContextMenu.Data1
    || *(_QWORD *)a4->Data4 != *(_QWORD *)IID_IContextMenu.Data4 )
  {
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IDataObject.Data1
      && *(_QWORD *)a4->Data4 == *(_QWORD *)IID_IDataObject.Data4 )
    {
      InfoTipFromItem2 = CFtpObj_Create(this, a3, a4, a5);
    }
    else
    {
      if ( *(_QWORD *)&a4->Data1 != *(_QWORD *)&IID_IDropTarget.Data1
        || *(_QWORD *)a4->Data4 != *(_QWORD *)IID_IDropTarget.Data4 )
      {
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IShellView.Data1
          && *(_QWORD *)a4->Data4 == *(_QWORD *)IID_IShellView.Data4 )
        {
          v10 = -2147024809;
        }
        else if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1
               && *(_QWORD *)a4->Data4 == *(_QWORD *)IID_IQueryAssociations.Data4 )
        {
          ppv[0] = 0;
          clsid = CLSID_QueryAssociations;
          v10 = AssocCreate(&clsid, &IID_IQueryAssociations, ppv);
          if ( v10 >= 0 )
          {
            Ptr = (PVOID)*((_QWORD *)a3 + 2);
            v13 = (struct _DPA *)*((_QWORD *)Ptr + 2);
            if ( *(_DWORD *)v13 != 1 )
              goto LABEL_25;
            if ( Ptr )
              Ptr = DPA_GetPtr(v13, 0);
            Attributes = FtpPidl_GetAttributes((const struct _ITEMIDLIST *)Ptr);
            v15 = L"Folder";
            if ( (Attributes & 0x10) == 0 )
LABEL_25:
              v15 = L"FTP";
            v10 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv[0] + 24LL))(
                    ppv[0],
                    0,
                    v15,
                    0,
                    0);
            if ( v10 >= 0 )
            {
              *a5 = ppv[0];
              return (unsigned int)v10;
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
          }
        }
        else
        {
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1
            && *(_QWORD *)a4->Data4 == *(_QWORD *)IID_IQueryInfo.Data4 )
          {
            v16 = (PVOID)*((_QWORD *)a3 + 2);
            v17 = (struct _DPA *)*((_QWORD *)v16 + 2);
            if ( *(_DWORD *)v17 == 1 )
            {
              if ( v16 )
                v16 = DPA_GetPtr(v17, 0);
              InfoTipFromItem2 = CreateInfoTipFromItem2(this, v16, &PKEY_PropList_QuickTip, 0, a4, a5);
              goto LABEL_35;
            }
          }
          v10 = -2147467262;
        }
LABEL_39:
        *a5 = 0;
        return (unsigned int)v10;
      }
      InfoTipFromItem2 = CFtpFolder::CreateSubViewObject(this, a2, a3, a4, a5);
    }
LABEL_35:
    v10 = InfoTipFromItem2;
    goto LABEL_36;
  }
  ppv[0] = 0;
  *a5 = 0;
  v10 = CFtpMenu_Create(this, a3, a2, a6, (struct CFtpMenu **)ppv);
  if ( v10 >= 0 )
  {
    v11 = ppv[0];
    v10 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv[0])(ppv[0], a4, a5);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
LABEL_36:
  if ( v10 < 0 )
    goto LABEL_39;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016e20  push    rbx
0x180016e22  push    rsi
0x180016e23  push    rdi
0x180016e24  push    r14
0x180016e26  sub     rsp, 58h
0x180016e2a  mov     rax, [r9]
0x180016e2d  mov     rdi, r9
0x180016e30  cmp     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180016e37  mov     rbx, r8
0x180016e3a  mov     r14, [rsp+78h+arg_20]
0x180016e42  mov     rsi, rcx
0x180016e45  jnz     short loc_180016E54
0x180016e47  mov     rax, [r9+8]
0x180016e4b  cmp     rax, qword ptr cs:IID_IExtractIconA.Data4
0x180016e52  jz      short loc_180016E6D
0x180016e54  mov     rax, [r9]
0x180016e57  cmp     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180016e5e  jnz     short loc_180016E80
0x180016e60  mov     rax, [r9+8]
0x180016e64  cmp     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180016e6b  jnz     short loc_180016E80
0x180016e6d  mov     r9, r14; void **
0x180016e70  mov     r8, rdi; struct _GUID *
0x180016e73  mov     rdx, rbx; struct CFtpPidlList *
0x180016e76  call    ?CFtpIcon_Create@@YAJPEAVCFtpFolder@@PEAVCFtpPidlList@@AEBU_GUID@@PEAPEAX@Z; CFtpIcon_Create(CFtpFolder *,CFtpPidlList *,_GUID const &,void * *)
0x180016e7b  jmp     loc_180017095
0x180016e80  mov     rax, [r9]
0x180016e83  cmp     rax, qword ptr cs:IID_IContextMenu.Data1
0x180016e8a  jnz     short loc_180016EFF
0x180016e8c  mov     rax, [r9+8]
0x180016e90  cmp     rax, qword ptr cs:IID_IContextMenu.Data4
0x180016e97  jnz     short loc_180016EFF
0x180016e99  mov     r9d, [rsp+78h+arg_28]; int
0x180016ea1  lea     rax, [rsp+78h+ppv]
0x180016ea6  mov     r8, rdx; HWND
0x180016ea9  mov     [rsp+78h+var_58], rax; struct CFtpMenu **
0x180016eae  mov     rdx, rbx; struct CFtpPidlList *
0x180016eb1  mov     [rsp+78h+ppv], 0
0x180016eba  mov     qword ptr [r14], 0
0x180016ec1  call    ?CFtpMenu_Create@@YAJPEAVCFtpFolder@@PEAVCFtpPidlList@@PEAUHWND__@@HPEAPEAVCFtpMenu@@@Z; CFtpMenu_Create(CFtpFolder *,CFtpPidlList *,HWND__ *,int,CFtpMenu * *)
0x180016ec6  mov     esi, eax
0x180016ec8  test    eax, eax
0x180016eca  js      loc_180017097
0x180016ed0  mov     rbx, [rsp+78h+ppv]
0x180016ed5  mov     r8, r14
0x180016ed8  mov     rdx, rdi
0x180016edb  mov     rcx, rbx
0x180016ede  mov     rax, [rbx]
0x180016ee1  mov     rax, [rax]
0x180016ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ee9  mov     esi, eax
0x180016eeb  mov     rcx, rbx
0x180016eee  mov     rax, [rbx]
0x180016ef1  mov     rax, [rax+10h]
0x180016ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016efa  jmp     loc_180017097
0x180016eff  mov     rax, [r9]
0x180016f02  cmp     rax, qword ptr cs:IID_IDataObject.Data1
0x180016f09  jnz     short loc_180016F2B
0x180016f0b  mov     rax, [r9+8]
0x180016f0f  cmp     rax, qword ptr cs:IID_IDataObject.Data4
0x180016f16  jnz     short loc_180016F2B
0x180016f18  mov     r9, r14; void **
0x180016f1b  mov     r8, rdi; struct _GUID *
0x180016f1e  mov     rdx, rbx; struct CFtpPidlList *
0x180016f21  call    ?CFtpObj_Create@@YAJPEAVCFtpFolder@@PEAVCFtpPidlList@@AEBU_GUID@@PEAPEAX@Z; CFtpObj_Create(CFtpFolder *,CFtpPidlList *,_GUID const &,void * *)
0x180016f26  jmp     loc_180017095
0x180016f2b  mov     rax, [r9]
0x180016f2e  cmp     rax, qword ptr cs:IID_IDropTarget.Data1
0x180016f35  jnz     short loc_180016F53
0x180016f37  mov     rax, [r9+8]
0x180016f3b  cmp     rax, qword ptr cs:IID_IDropTarget.Data4
0x180016f42  jnz     short loc_180016F53
0x180016f44  mov     [rsp+78h+var_58], r14; void **
0x180016f49  call    ?CreateSubViewObject@CFtpFolder@@QEAAJPEAUHWND__@@PEAVCFtpPidlList@@AEBU_GUID@@PEAPEAX@Z; CFtpFolder::CreateSubViewObject(HWND__ *,CFtpPidlList *,_GUID const &,void * *)
0x180016f4e  jmp     loc_180017095
0x180016f53  mov     rax, [r9]
0x180016f56  cmp     rax, qword ptr cs:IID_IShellView.Data1
0x180016f5d  jnz     short loc_180016F76
0x180016f5f  mov     rax, [r9+8]
0x180016f63  cmp     rax, qword ptr cs:IID_IShellView.Data4
0x180016f6a  jnz     short loc_180016F76
0x180016f6c  mov     esi, 80070057h
0x180016f71  jmp     loc_1800170A2
0x180016f76  mov     rax, [r9]
0x180016f79  cmp     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180016f80  jnz     loc_180017043
0x180016f86  mov     rax, [r9+8]
0x180016f8a  cmp     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180016f91  jnz     loc_180017043
0x180016f97  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180016f9e  lea     r8, [rsp+78h+ppv]; ppv
0x180016fa3  mov     [rsp+78h+ppv], 0
0x180016fac  lea     rdx, IID_IQueryAssociations; riid
0x180016fb3  lea     rcx, [rsp+78h+clsid]; clsid
0x180016fb8  movdqu  xmmword ptr [rsp+78h+clsid.Data1], xmm0
0x180016fbe  call    cs:__imp_AssocCreate
0x180016fc4  mov     esi, eax
0x180016fc6  test    eax, eax
0x180016fc8  js      loc_1800170A2
0x180016fce  mov     rax, [rbx+10h]
0x180016fd2  mov     rcx, [rax+10h]; hdpa
0x180016fd6  cmp     dword ptr [rcx], 1
0x180016fd9  jnz     short loc_180016FFA
0x180016fdb  test    rax, rax
0x180016fde  jz      short loc_180016FE7
0x180016fe0  xor     edx, edx; i
0x180016fe2  call    DPA_GetPtr
0x180016fe7  mov     rcx, rax; struct _ITEMIDLIST *
0x180016fea  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x180016fef  lea     r8, aFolder; "Folder"
0x180016ff6  test    al, 10h
0x180016ff8  jnz     short loc_180017001
0x180016ffa  lea     r8, aFtp_0; "FTP"
0x180017001  mov     rcx, [rsp+78h+ppv]
0x180017006  xor     r9d, r9d
0x180017009  xor     edx, edx
0x18001700b  mov     [rsp+78h+var_58], 0
0x180017014  mov     rax, [rcx]
0x180017017  mov     rax, [rax+18h]
0x18001701b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017020  mov     esi, eax
0x180017022  test    eax, eax
0x180017024  js      short loc_180017030
0x180017026  mov     rax, [rsp+78h+ppv]
0x18001702b  mov     [r14], rax
0x18001702e  jmp     short loc_1800170A9
0x180017030  mov     rcx, [rsp+78h+ppv]
0x180017035  mov     rax, [rcx]
0x180017038  mov     rax, [rax+10h]
0x18001703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017041  jmp     short loc_1800170A2
0x180017043  mov     rax, [r9]
0x180017046  cmp     rax, qword ptr cs:IID_IQueryInfo.Data1
0x18001704d  jnz     short loc_18001709D
0x18001704f  mov     rax, [r9+8]
0x180017053  cmp     rax, qword ptr cs:IID_IQueryInfo.Data4
0x18001705a  jnz     short loc_18001709D
0x18001705c  mov     rax, [r8+10h]
0x180017060  mov     rcx, [rax+10h]; hdpa
0x180017064  cmp     dword ptr [rcx], 1
0x180017067  jnz     short loc_18001709D
0x180017069  test    rax, rax
0x18001706c  jz      short loc_180017075
0x18001706e  xor     edx, edx; i
0x180017070  call    DPA_GetPtr
0x180017075  mov     [rsp+78h+var_50], r14
0x18001707a  lea     r8, PKEY_PropList_QuickTip
0x180017081  xor     r9d, r9d
0x180017084  mov     [rsp+78h+var_58], rdi
0x180017089  mov     rdx, rax
0x18001708c  mov     rcx, rsi
0x18001708f  call    cs:__imp_CreateInfoTipFromItem2
0x180017095  mov     esi, eax
0x180017097  test    esi, esi
0x180017099  jns     short loc_1800170A9
0x18001709b  jmp     short loc_1800170A2
0x18001709d  mov     esi, 80004002h
0x1800170a2  mov     qword ptr [r14], 0
0x1800170a9  mov     eax, esi
0x1800170ab  add     rsp, 58h
0x1800170af  pop     r14
0x1800170b1  pop     rdi
0x1800170b2  pop     rsi
0x1800170b3  pop     rbx
0x1800170b4  retn
```
