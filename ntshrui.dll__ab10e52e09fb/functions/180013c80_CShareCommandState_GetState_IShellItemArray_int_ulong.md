# CShareCommandState::GetState(IShellItemArray *,int,ulong *)

- ea: `0x180013c80`
- end: `0x180013f0c`
- name: `?GetState@CShareCommandState@@UEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `652`
- prototype: `int(CShareCommandState *__hidden this, struct IShellItemArray *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180008900`
- `0x18001376c`
- `0x180013c80`
- `0x180013f20`
- `0x1800143ec`
- `0x180046b04`
- `0x1800509c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013cdb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e7f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ea9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013cdb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013dc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e7f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013ea9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShareCommandState::GetState(
        CShareCommandState *this,
        struct IShellItemArray *a2,
        int a3,
        unsigned int *a4)
{
  const WCHAR *v8; // rcx
  char v9; // r15
  unsigned int SyncRootItemTypes; // ebx
  HRESULT (__stdcall *GetItemAt)(IShellItemArray *, DWORD, IShellItem **); // rbx
  bool v12; // zf
  const unsigned __int16 *v13; // rcx
  int v15[4]; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+80h] [rbp+40h] BYREF
  struct IShellItem *v17; // [rsp+98h] [rbp+58h] BYREF

  *a4 = 1;
  v8 = (const WCHAR *)*((_QWORD *)this + 4);
  v9 = 0;
  if ( !v8 )
    return (unsigned int)-2147418113;
  if ( a2 && CompareStringOrdinal(v8, -1, L"Windows.ShareWithSyncEngine", -1, 1) == 2 )
  {
    v16 = 0;
    SyncRootItemTypes = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))a2->lpVtbl->GetCount)(a2, &v16);
    if ( (SyncRootItemTypes & 0x80000000) == 0 && v16 == 1 )
    {
      v17 = 0;
      GetItemAt = a2->lpVtbl->GetItemAt;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
      SyncRootItemTypes = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))GetItemAt)(
                            a2,
                            0,
                            &v17);
      if ( (SyncRootItemTypes & 0x80000000) == 0 && !IShellItem_GetItemOfflineStatus(v17) )
        *a4 = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v17);
    }
    return SyncRootItemTypes;
  }
  LODWORD(v17) = 0;
  v16 = 0;
  SyncRootItemTypes = _GetSyncRootItemTypes(
                        *((IUnknown **)this - 1),
                        a2,
                        (unsigned int *)&v17,
                        (enum SyncRootItemType *)&v16);
  if ( (SyncRootItemTypes & 0x80000000) != 0 )
    return SyncRootItemTypes;
  v12 = (v16 & 1) == 0;
  *((_BYTE *)this + 41) = v16 & 1;
  if ( !v12 )
  {
    if ( *((_BYTE *)this + 40) && (_DWORD)v17 == 1 && (v16 & 2) == 0 )
      *a4 = 0;
    return SyncRootItemTypes;
  }
  if ( CompareStringOrdinal(*((LPCWCH *)this + 4), -1, L"Windows.RibbonShare", -1, 1) == 2 )
  {
    v9 = 1;
    goto LABEL_19;
  }
  if ( CompareStringOrdinal(*((LPCWCH *)this + 4), -1, L"Windows.SharePrivate", -1, 1) == 2
    || CompareStringOrdinal(*((LPCWCH *)this + 4), -1, L"Windows.ShareWithUserRO", -1, 1) == 2 )
  {
LABEL_19:
    if ( IsServiceRunningOrStartPending(v13) )
    {
      LODWORD(v17) = 0;
      v16 = 0;
      v15[0] = 0;
      SyncRootItemTypes = _GetShareStateFromSite(
                            *((struct IUnknown **)this - 1),
                            a2,
                            (enum SHARING_MENU_SHARE_STATE *)&v16,
                            0,
                            (enum SHARE_MODE *)&v17,
                            v15);
      if ( (SyncRootItemTypes & 0x80000000) != 0 )
        return SyncRootItemTypes;
      if ( v9 )
      {
        if ( v16 == 1 )
          return SyncRootItemTypes;
        goto LABEL_31;
      }
      if ( v16 != 1 )
      {
        if ( (_DWORD)v17 == 3 )
          goto LABEL_34;
        if ( !v15[0] )
        {
LABEL_31:
          *a4 = 0;
          return SyncRootItemTypes;
        }
      }
      if ( (_DWORD)v17 != 3 && !v15[0] )
        return SyncRootItemTypes;
    }
LABEL_34:
    *a4 = 2;
    return SyncRootItemTypes;
  }
  if ( CompareStringOrdinal(*((LPCWCH *)this + 4), -1, L"Windows.Share", -1, 1) == 2 )
    return (unsigned int)CShareCommandState::_GetShareCommandState(
                           (CShareCommandState *)((char *)this - 16),
                           a2,
                           a3,
                           a4);
  return SyncRootItemTypes;
}

```

## disassembly

```asm
0x180013c80  mov     [rsp-38h+arg_8], rbx
0x180013c85  push    rbp
0x180013c86  push    rsi
0x180013c87  push    rdi
0x180013c88  push    r12
0x180013c8a  push    r13
0x180013c8c  push    r14
0x180013c8e  push    r15
0x180013c90  mov     rbp, rsp
0x180013c93  sub     rsp, 40h
0x180013c97  mov     rdi, r9
0x180013c9a  mov     r12d, r8d
0x180013c9d  mov     r14, rdx
0x180013ca0  mov     rsi, rcx
0x180013ca3  mov     eax, 1
0x180013ca8  mov     [r9], eax
0x180013cab  mov     rcx, [rcx+20h]; lpString1
0x180013caf  xor     r15d, r15d
0x180013cb2  test    rcx, rcx
0x180013cb5  jnz     short loc_180013CC1
0x180013cb7  mov     ebx, 8000FFFFh
0x180013cbc  jmp     loc_180013EF2
0x180013cc1  or      edx, 0FFFFFFFFh; cchCount1
0x180013cc4  test    r14, r14
0x180013cc7  jz      loc_180013D5A
0x180013ccd  mov     [rsp+40h+bIgnoreCase], eax; bIgnoreCase
0x180013cd1  mov     r9d, edx; cchCount2
0x180013cd4  lea     r8, String2; "Windows.ShareWithSyncEngine"
0x180013cdb  call    cs:__imp_CompareStringOrdinal
0x180013ce1  cmp     eax, 2
0x180013ce4  jnz     short loc_180013D5A
0x180013ce6  mov     [rbp+arg_0], r15d
0x180013cea  mov     rax, [r14]
0x180013ced  lea     rdx, [rbp+arg_0]
0x180013cf1  mov     rcx, r14
0x180013cf4  mov     rax, [rax+38h]
0x180013cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cfd  mov     ebx, eax
0x180013cff  test    eax, eax
0x180013d01  js      loc_180013EF2
0x180013d07  cmp     [rbp+arg_0], 1
0x180013d0b  jnz     loc_180013EF2
0x180013d11  mov     [rbp+arg_18], r15
0x180013d15  mov     rax, [r14]
0x180013d18  mov     rbx, [rax+40h]
0x180013d1c  lea     rcx, [rbp+arg_18]
0x180013d20  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013d25  lea     r8, [rbp+arg_18]
0x180013d29  xor     edx, edx
0x180013d2b  mov     rcx, r14
0x180013d2e  mov     rax, rbx
0x180013d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d36  mov     ebx, eax
0x180013d38  test    eax, eax
0x180013d3a  js      short loc_180013D4C
0x180013d3c  mov     rcx, [rbp+arg_18]; struct IShellItem *
0x180013d40  call    ?IShellItem_GetItemOfflineStatus@@YAKPEAUIShellItem@@@Z; IShellItem_GetItemOfflineStatus(IShellItem *)
0x180013d45  test    eax, eax
0x180013d47  jnz     short loc_180013D4C
0x180013d49  mov     [rdi], r15d
0x180013d4c  lea     rcx, [rbp+arg_18]
0x180013d50  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180013d55  jmp     loc_180013EF2
0x180013d5a  mov     dword ptr [rbp+arg_18], r15d
0x180013d5e  mov     [rbp+arg_0], r15d
0x180013d62  lea     r9, [rbp+arg_0]; enum SyncRootItemType *
0x180013d66  lea     r8, [rbp+arg_18]; unsigned int *
0x180013d6a  mov     rdx, r14; struct IShellItemArray *
0x180013d6d  mov     rcx, [rsi-8]; punk
0x180013d71  call    ?_GetSyncRootItemTypes@@YAJPEAUIUnknown@@PEAUIShellItemArray@@PEAKPEAW4SyncRootItemType@@@Z; _GetSyncRootItemTypes(IUnknown *,IShellItemArray *,ulong *,SyncRootItemType *)
0x180013d76  mov     ebx, eax
0x180013d78  test    eax, eax
0x180013d7a  js      loc_180013EF2
0x180013d80  mov     eax, [rbp+arg_0]
0x180013d83  and     al, 1
0x180013d85  mov     [rsi+29h], al
0x180013d88  jz      short loc_180013DB0
0x180013d8a  cmp     [rsi+28h], r15b
0x180013d8e  jz      loc_180013EF2
0x180013d94  cmp     dword ptr [rbp+arg_18], 1
0x180013d98  jnz     loc_180013EF2
0x180013d9e  test    byte ptr [rbp+arg_0], 2
0x180013da2  jnz     loc_180013EF2
0x180013da8  mov     [rdi], r15d
0x180013dab  jmp     loc_180013EF2
0x180013db0  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180013db8  or      edx, 0FFFFFFFFh; cchCount1
0x180013dbb  mov     r9d, edx; cchCount2
0x180013dbe  lea     r8, aWindowsRibbons; "Windows.RibbonShare"
0x180013dc5  mov     rcx, [rsi+20h]; lpString1
0x180013dc9  call    cs:__imp_CompareStringOrdinal
0x180013dcf  cmp     eax, 2
0x180013dd2  jnz     short loc_180013E3A
0x180013dd4  mov     r15b, 1
0x180013dd7  call    ?IsServiceRunningOrStartPending@@YA_NPEBG@Z; IsServiceRunningOrStartPending(ushort const *)
0x180013ddc  xor     r12d, r12d
0x180013ddf  test    al, al
0x180013de1  jz      loc_180013EEC
0x180013de7  mov     dword ptr [rbp+arg_18], r12d
0x180013deb  mov     [rbp+arg_0], r12d
0x180013def  mov     [rbp+var_10], r12d
0x180013df3  lea     rax, [rbp+var_10]
0x180013df7  mov     [rsp+40h+var_18], rax; int *
0x180013dfc  lea     rax, [rbp+arg_18]
0x180013e00  mov     qword ptr [rsp+40h+bIgnoreCase], rax; enum SHARE_MODE *
0x180013e05  xor     r9d, r9d; enum SHARING_MENU_PRESENTATION_STATE *
0x180013e08  lea     r8, [rbp+arg_0]; enum SHARING_MENU_SHARE_STATE *
0x180013e0c  mov     rdx, r14; struct IShellItemArray *
0x180013e0f  mov     rcx, [rsi-8]; struct IUnknown *
0x180013e13  call    ?_GetShareStateFromSite@@YAJPEAUIUnknown@@PEAUIShellItemArray@@PEAW4SHARING_MENU_SHARE_STATE@@PEAW4SHARING_MENU_PRESENTATION_STATE@@PEAW4SHARE_MODE@@PEAH@Z; _GetShareStateFromSite(IUnknown *,IShellItemArray *,SHARING_MENU_SHARE_STATE *,SHARING_MENU_PRESENTATION_STATE *,SHARE_MODE *,int *)
0x180013e18  mov     ebx, eax
0x180013e1a  test    eax, eax
0x180013e1c  js      loc_180013EF2
0x180013e22  test    r15b, r15b
0x180013e25  jz      loc_180013ECA
0x180013e2b  cmp     [rbp+arg_0], 1
0x180013e2f  jnz     loc_180013EDD
0x180013e35  jmp     loc_180013EF2
0x180013e3a  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180013e42  or      eax, 0FFFFFFFFh
0x180013e45  mov     r9d, eax; cchCount2
0x180013e48  lea     r8, aWindowsSharepr; "Windows.SharePrivate"
0x180013e4f  mov     edx, eax; cchCount1
0x180013e51  mov     rcx, [rsi+20h]; lpString1
0x180013e55  call    cs:__imp_CompareStringOrdinal
0x180013e5b  cmp     eax, 2
0x180013e5e  jz      loc_180013DD7
0x180013e64  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180013e6c  or      eax, 0FFFFFFFFh
0x180013e6f  mov     r9d, eax; cchCount2
0x180013e72  lea     r8, aWindowsSharewi_0; "Windows.ShareWithUserRO"
0x180013e79  mov     edx, eax; cchCount1
0x180013e7b  mov     rcx, [rsi+20h]; lpString1
0x180013e7f  call    cs:__imp_CompareStringOrdinal
0x180013e85  cmp     eax, 2
0x180013e88  jz      loc_180013DD7
0x180013e8e  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180013e96  or      eax, 0FFFFFFFFh
0x180013e99  mov     r9d, eax; cchCount2
0x180013e9c  lea     r8, aWindowsShare; "Windows.Share"
0x180013ea3  mov     edx, eax; cchCount1
0x180013ea5  mov     rcx, [rsi+20h]; lpString1
0x180013ea9  call    cs:__imp_CompareStringOrdinal
0x180013eaf  cmp     eax, 2
0x180013eb2  jnz     short loc_180013EF2
0x180013eb4  mov     r9, rdi; unsigned int *
0x180013eb7  mov     r8d, r12d; int
0x180013eba  mov     rdx, r14; struct IShellItemArray *
0x180013ebd  lea     rcx, [rsi-10h]; this
0x180013ec1  call    ?_GetShareCommandState@CShareCommandState@@AEAAJPEAUIShellItemArray@@HPEAK@Z; CShareCommandState::_GetShareCommandState(IShellItemArray *,int,ulong *)
0x180013ec6  mov     ebx, eax
0x180013ec8  jmp     short loc_180013EF2
0x180013eca  mov     eax, [rbp+var_10]
0x180013ecd  cmp     [rbp+arg_0], 1
0x180013ed1  jz      short loc_180013EE2
0x180013ed3  cmp     dword ptr [rbp+arg_18], 3
0x180013ed7  jz      short loc_180013EEC
0x180013ed9  test    eax, eax
0x180013edb  jnz     short loc_180013EE2
0x180013edd  mov     [rdi], r12d
0x180013ee0  jmp     short loc_180013EF2
0x180013ee2  cmp     dword ptr [rbp+arg_18], 3
0x180013ee6  jz      short loc_180013EEC
0x180013ee8  test    eax, eax
0x180013eea  jz      short loc_180013EF2
0x180013eec  mov     dword ptr [rdi], 2
0x180013ef2  mov     eax, ebx
0x180013ef4  mov     rbx, [rsp+40h+arg_8]
0x180013efc  add     rsp, 40h
0x180013f00  pop     r15
0x180013f02  pop     r14
0x180013f04  pop     r13
0x180013f06  pop     r12
0x180013f08  pop     rdi
0x180013f09  pop     rsi
0x180013f0a  pop     rbp
0x180013f0b  retn
```
