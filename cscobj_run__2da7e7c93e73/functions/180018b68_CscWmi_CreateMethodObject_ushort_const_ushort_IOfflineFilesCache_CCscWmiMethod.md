# CscWmi_CreateMethodObject(ushort const *,ushort *,IOfflineFilesCache *,CCscWmiMethod * *)

- ea: `0x180018b68`
- end: `0x18001907d`
- name: `?CscWmi_CreateMethodObject@@YAJPEBGPEAGPEAUIOfflineFilesCache@@PEAPEAVCCscWmiMethod@@@Z`
- size: `1301`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH, struct IOfflineFilesCache *, struct CCscWmiMethod **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024650`

## callees

- `0x18000b390`
- `0x180014140`
- `0x1800141ec`
- `0x180018350`
- `0x180018480`
- `0x180018b68`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018bea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018c15`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018c7f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018cd2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018d17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018d79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018ddb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018e3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018e9f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018fc2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018bea`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018c15`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018c7f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018cd2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018d17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018d79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018ddb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018e3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018e9f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018f63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180018fc2`

## string_xrefs

- `0x180018bc6`: `Win32_OfflineFilesCache`
- `0x180018feb`: `Win32_OfflineFilesCache`
- `0x180018d5d`: `RenameItem`
- `0x180018da4`: `RenameItem`
- `0x180018dbf`: `RenameItemEx`
- `0x180018e06`: `RenameItemEx`
- `0x180018cfb`: `DeleteItems`
- `0x180018d42`: `DeleteItems`

## pseudocode

```c
__int64 __fastcall CscWmi_CreateMethodObject(
        PCNZWCH lpString1,
        PCNZWCH a2,
        struct IOfflineFilesCache *a3,
        struct CCscWmiMethod **a4)
{
  unsigned int v8; // ebx
  CCscWmiCacheMethod *v9; // rax
  CCscWmiPinMethod *v10; // rdi
  void **v11; // rax
  CCscWmiPinMethod *v12; // rax
  int v13; // edx
  CCscWmiCacheMethod *v14; // rax
  CCscWmiCacheMethod *v15; // rax
  CCscWmiCacheMethod *v16; // rax
  CCscWmiCacheMethod *v17; // rax
  CCscWmiCacheMethod *v18; // rax
  CCscWmiCacheMethod *v19; // rax
  CCscWmiCacheMethod *v20; // rax
  CCscWmiPinMethod *v21; // rax

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      113,
      (unsigned int)WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (_DWORD)lpString1,
      (__int64)a2);
  }
  *a4 = 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Win32_OfflineFilesCache", -1) != 2 )
    goto LABEL_55;
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Synchronize", -1) == 2 )
  {
    if ( !a3 )
    {
LABEL_7:
      v8 = -2147217372;
      goto LABEL_56;
    }
    v9 = (CCscWmiCacheMethod *)operator new(0x40u);
    v10 = v9;
    if ( v9 )
    {
      CCscWmiCacheMethod::CCscWmiCacheMethod(v9, L"Synchronize", a3);
      v11 = &CCscWmiSyncMethod::`vftable';
LABEL_50:
      *(_QWORD *)v10 = v11;
      goto LABEL_52;
    }
    goto LABEL_51;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Pin", -1) == 2 )
  {
    if ( !a3 )
      goto LABEL_7;
    v12 = (CCscWmiPinMethod *)operator new(0x48u);
    if ( !v12 )
      goto LABEL_51;
    v13 = 1;
    goto LABEL_14;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Unpin", -1) == 2 )
  {
    if ( !a3 )
      goto LABEL_7;
    v12 = (CCscWmiPinMethod *)operator new(0x48u);
    if ( !v12 )
      goto LABEL_51;
    v13 = 0;
LABEL_14:
    v10 = CCscWmiPinMethod::CCscWmiPinMethod(v12, v13, a3);
    goto LABEL_52;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"DeleteItems", -1) != 2 )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"RenameItem", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v15 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v15;
      if ( v15 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v15, L"RenameItem", a3);
        v11 = &CCscWmiRenameMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"RenameItemEx", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v16 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v16;
      if ( v16 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v16, L"RenameItemEx", a3);
        v11 = &CCscWmiRenameExMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Encrypt", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v17 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v17;
      if ( v17 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v17, L"Encrypt", a3);
        v11 = &CCscWmiEncryptMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"SuspendRoot", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v18 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v18;
      if ( v18 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v18, L"SuspendRoot", a3);
        v11 = &CCscWmiSuspendRootMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"TransitionOffline", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v19 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v19;
      if ( v19 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v19, L"TransitionOffline", a3);
        v11 = &CCscWmiTransitionOfflineMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"TransitionOnline", -1) == 2 )
    {
      if ( !a3 )
        goto LABEL_7;
      v20 = (CCscWmiCacheMethod *)operator new(0x40u);
      v10 = v20;
      if ( v20 )
      {
        CCscWmiCacheMethod::CCscWmiCacheMethod(v20, L"TransitionOnline", a3);
        v11 = &CCscWmiTransitionOnlineMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Enable", -1) == 2 )
    {
      v21 = (CCscWmiPinMethod *)operator new(0x28u);
      v10 = v21;
      if ( v21 )
      {
        *((_DWORD *)v21 + 2) = 1;
        *(_QWORD *)v21 = &CCscWmiMethod::`vftable';
        *((_QWORD *)v21 + 2) = L"Win32_OfflineFilesCache";
        *((_QWORD *)v21 + 3) = L"Enable";
        *((_QWORD *)v21 + 4) = 0;
        _InterlockedAdd(&g_cRefDll, 1u);
        v11 = &CCscWmiEnableMethod::`vftable';
        goto LABEL_50;
      }
      goto LABEL_51;
    }
LABEL_55:
    v8 = -2147217396;
    goto LABEL_56;
  }
  if ( !a3 )
    goto LABEL_7;
  v14 = (CCscWmiCacheMethod *)operator new(0x40u);
  v10 = v14;
  if ( v14 )
  {
    CCscWmiCacheMethod::CCscWmiCacheMethod(v14, L"DeleteItems", a3);
    v11 = &CCscWmiDeleteMethod::`vftable';
    goto LABEL_50;
  }
LABEL_51:
  v10 = 0;
LABEL_52:
  v8 = 0;
  *a4 = v10;
  if ( !v10 )
    v8 = -2147024882;
LABEL_56:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SSD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      114,
      (unsigned int)WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (_DWORD)lpString1,
      (__int64)a2,
      v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180018b68  push    rbx
0x180018b6a  push    rbp
0x180018b6b  push    rsi
0x180018b6c  push    rdi
0x180018b6d  push    r12
0x180018b6f  push    r14
0x180018b71  push    r15
0x180018b73  sub     rsp, 30h
0x180018b77  mov     rsi, r9
0x180018b7a  mov     rbx, r8
0x180018b7d  mov     rbp, rdx
0x180018b80  mov     r14, rcx
0x180018b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b8a  lea     rax, WPP_GLOBAL_Control
0x180018b91  cmp     rcx, rax
0x180018b94  jz      short loc_180018BBC
0x180018b96  test    dword ptr [rcx+1Ch], 4000000h
0x180018b9d  jz      short loc_180018BBC
0x180018b9f  mov     rcx, [rcx+10h]
0x180018ba3  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180018baa  mov     edx, 71h ; 'q'
0x180018baf  mov     [rsp+68h+lpString2], rbp
0x180018bb4  mov     r9, r14
0x180018bb7  call    WPP_SF_SS
0x180018bbc  or      edi, 0FFFFFFFFh
0x180018bbf  mov     qword ptr [rsi], 0
0x180018bc6  lea     rax, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x180018bcd  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018bd1  mov     r9d, edi; cchCount1
0x180018bd4  mov     [rsp+68h+lpString2], rax; lpString2
0x180018bd9  mov     r8, r14; lpString1
0x180018bdc  lea     r15d, [rdi+2]
0x180018be0  lea     r12d, [r15+7Eh]
0x180018be4  mov     edx, r15d; dwCmpFlags
0x180018be7  mov     ecx, r12d; Locale
0x180018bea  call    cs:__imp_CompareStringW
0x180018bf0  cmp     eax, 2
0x180018bf3  jnz     loc_18001902A
0x180018bf9  lea     rax, CSCWMI_STR_METHOD_SYNCHRONIZE; "Synchronize"
0x180018c00  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018c04  mov     r9d, edi; cchCount1
0x180018c07  mov     [rsp+68h+lpString2], rax; lpString2
0x180018c0c  mov     r8, rbp; lpString1
0x180018c0f  mov     edx, r15d; dwCmpFlags
0x180018c12  mov     ecx, r12d; Locale
0x180018c15  call    cs:__imp_CompareStringW
0x180018c1b  cmp     eax, 2
0x180018c1e  jnz     short loc_180018C63
0x180018c20  test    rbx, rbx
0x180018c23  jnz     short loc_180018C2F
0x180018c25  mov     ebx, 80041024h
0x180018c2a  jmp     loc_18001902F
0x180018c2f  mov     ecx, 40h ; '@'; Size
0x180018c34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018c39  mov     rdi, rax
0x180018c3c  test    rax, rax
0x180018c3f  jz      loc_180019016
0x180018c45  mov     r8, rbx; struct IOfflineFilesCache *
0x180018c48  lea     rdx, CSCWMI_STR_METHOD_SYNCHRONIZE; "Synchronize"
0x180018c4f  mov     rcx, rax; this
0x180018c52  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018c57  lea     rax, ??_7CCscWmiSyncMethod@@6B@; const CCscWmiSyncMethod::`vftable'
0x180018c5e  jmp     loc_180019011
0x180018c63  lea     rax, CSCWMI_STR_METHOD_PIN; "Pin"
0x180018c6a  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018c6e  mov     r9d, edi; cchCount1
0x180018c71  mov     [rsp+68h+lpString2], rax; lpString2
0x180018c76  mov     r8, rbp; lpString1
0x180018c79  mov     edx, r15d; dwCmpFlags
0x180018c7c  mov     ecx, r12d; Locale
0x180018c7f  call    cs:__imp_CompareStringW
0x180018c85  cmp     eax, 2
0x180018c88  jnz     short loc_180018CB6
0x180018c8a  test    rbx, rbx
0x180018c8d  jz      short loc_180018C25
0x180018c8f  lea     ecx, [rax+46h]; Size
0x180018c92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018c97  test    rax, rax
0x180018c9a  jz      loc_180019016
0x180018ca0  mov     edx, r15d; int
0x180018ca3  mov     r8, rbx; struct IOfflineFilesCache *
0x180018ca6  mov     rcx, rax; this
0x180018ca9  call    ??0CCscWmiPinMethod@@QEAA@HPEAUIOfflineFilesCache@@@Z; CCscWmiPinMethod::CCscWmiPinMethod(int,IOfflineFilesCache *)
0x180018cae  mov     rdi, rax
0x180018cb1  jmp     loc_180019018
0x180018cb6  lea     rax, CSCWMI_STR_METHOD_UNPIN; "Unpin"
0x180018cbd  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018cc1  mov     r9d, edi; cchCount1
0x180018cc4  mov     [rsp+68h+lpString2], rax; lpString2
0x180018cc9  mov     r8, rbp; lpString1
0x180018ccc  mov     edx, r15d; dwCmpFlags
0x180018ccf  mov     ecx, r12d; Locale
0x180018cd2  call    cs:__imp_CompareStringW
0x180018cd8  cmp     eax, 2
0x180018cdb  jnz     short loc_180018CFB
0x180018cdd  test    rbx, rbx
0x180018ce0  jz      loc_180018C25
0x180018ce6  lea     ecx, [rax+46h]; Size
0x180018ce9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018cee  test    rax, rax
0x180018cf1  jz      loc_180019016
0x180018cf7  xor     edx, edx
0x180018cf9  jmp     short loc_180018CA3
0x180018cfb  lea     rax, CSCWMI_STR_METHOD_DELETEITEMS; "DeleteItems"
0x180018d02  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018d06  mov     r9d, edi; cchCount1
0x180018d09  mov     [rsp+68h+lpString2], rax; lpString2
0x180018d0e  mov     r8, rbp; lpString1
0x180018d11  mov     edx, r15d; dwCmpFlags
0x180018d14  mov     ecx, r12d; Locale
0x180018d17  call    cs:__imp_CompareStringW
0x180018d1d  cmp     eax, 2
0x180018d20  jnz     short loc_180018D5D
0x180018d22  test    rbx, rbx
0x180018d25  jz      loc_180018C25
0x180018d2b  lea     ecx, [rax+3Eh]; Size
0x180018d2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d33  mov     rdi, rax
0x180018d36  test    rax, rax
0x180018d39  jz      loc_180019016
0x180018d3f  mov     r8, rbx; struct IOfflineFilesCache *
0x180018d42  lea     rdx, CSCWMI_STR_METHOD_DELETEITEMS; "DeleteItems"
0x180018d49  mov     rcx, rax; this
0x180018d4c  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018d51  lea     rax, ??_7CCscWmiDeleteMethod@@6B@; const CCscWmiDeleteMethod::`vftable'
0x180018d58  jmp     loc_180019011
0x180018d5d  lea     rax, CSCWMI_STR_METHOD_RENAMEITEM; "RenameItem"
0x180018d64  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018d68  mov     r9d, edi; cchCount1
0x180018d6b  mov     [rsp+68h+lpString2], rax; lpString2
0x180018d70  mov     r8, rbp; lpString1
0x180018d73  mov     edx, r15d; dwCmpFlags
0x180018d76  mov     ecx, r12d; Locale
0x180018d79  call    cs:__imp_CompareStringW
0x180018d7f  cmp     eax, 2
0x180018d82  jnz     short loc_180018DBF
0x180018d84  test    rbx, rbx
0x180018d87  jz      loc_180018C25
0x180018d8d  lea     ecx, [rax+3Eh]; Size
0x180018d90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d95  mov     rdi, rax
0x180018d98  test    rax, rax
0x180018d9b  jz      loc_180019016
0x180018da1  mov     r8, rbx; struct IOfflineFilesCache *
0x180018da4  lea     rdx, CSCWMI_STR_METHOD_RENAMEITEM; "RenameItem"
0x180018dab  mov     rcx, rax; this
0x180018dae  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018db3  lea     rax, ??_7CCscWmiRenameMethod@@6B@; const CCscWmiRenameMethod::`vftable'
0x180018dba  jmp     loc_180019011
0x180018dbf  lea     rax, CSCWMI_STR_METHOD_RENAMEITEMEX; "RenameItemEx"
0x180018dc6  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018dca  mov     r9d, edi; cchCount1
0x180018dcd  mov     [rsp+68h+lpString2], rax; lpString2
0x180018dd2  mov     r8, rbp; lpString1
0x180018dd5  mov     edx, r15d; dwCmpFlags
0x180018dd8  mov     ecx, r12d; Locale
0x180018ddb  call    cs:__imp_CompareStringW
0x180018de1  cmp     eax, 2
0x180018de4  jnz     short loc_180018E21
0x180018de6  test    rbx, rbx
0x180018de9  jz      loc_180018C25
0x180018def  lea     ecx, [rax+3Eh]; Size
0x180018df2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018df7  mov     rdi, rax
0x180018dfa  test    rax, rax
0x180018dfd  jz      loc_180019016
0x180018e03  mov     r8, rbx; struct IOfflineFilesCache *
0x180018e06  lea     rdx, CSCWMI_STR_METHOD_RENAMEITEMEX; "RenameItemEx"
0x180018e0d  mov     rcx, rax; this
0x180018e10  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018e15  lea     rax, ??_7CCscWmiRenameExMethod@@6B@; const CCscWmiRenameExMethod::`vftable'
0x180018e1c  jmp     loc_180019011
0x180018e21  lea     rax, CSCWMI_STR_METHOD_ENCRYPT; "Encrypt"
0x180018e28  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018e2c  mov     r9d, edi; cchCount1
0x180018e2f  mov     [rsp+68h+lpString2], rax; lpString2
0x180018e34  mov     r8, rbp; lpString1
0x180018e37  mov     edx, r15d; dwCmpFlags
0x180018e3a  mov     ecx, r12d; Locale
0x180018e3d  call    cs:__imp_CompareStringW
0x180018e43  cmp     eax, 2
0x180018e46  jnz     short loc_180018E83
0x180018e48  test    rbx, rbx
0x180018e4b  jz      loc_180018C25
0x180018e51  lea     ecx, [rax+3Eh]; Size
0x180018e54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018e59  mov     rdi, rax
0x180018e5c  test    rax, rax
0x180018e5f  jz      loc_180019016
0x180018e65  mov     r8, rbx; struct IOfflineFilesCache *
0x180018e68  lea     rdx, CSCWMI_STR_METHOD_ENCRYPT; "Encrypt"
0x180018e6f  mov     rcx, rax; this
0x180018e72  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018e77  lea     rax, ??_7CCscWmiEncryptMethod@@6B@; const CCscWmiEncryptMethod::`vftable'
0x180018e7e  jmp     loc_180019011
0x180018e83  lea     rax, CSCWMI_STR_METHOD_SUSPENDROOT; "SuspendRoot"
0x180018e8a  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018e8e  mov     r9d, edi; cchCount1
0x180018e91  mov     [rsp+68h+lpString2], rax; lpString2
0x180018e96  mov     r8, rbp; lpString1
0x180018e99  mov     edx, r15d; dwCmpFlags
0x180018e9c  mov     ecx, r12d; Locale
0x180018e9f  call    cs:__imp_CompareStringW
0x180018ea5  cmp     eax, 2
0x180018ea8  jnz     short loc_180018EE5
0x180018eaa  test    rbx, rbx
0x180018ead  jz      loc_180018C25
0x180018eb3  lea     ecx, [rax+3Eh]; Size
0x180018eb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ebb  mov     rdi, rax
0x180018ebe  test    rax, rax
0x180018ec1  jz      loc_180019016
0x180018ec7  mov     r8, rbx; struct IOfflineFilesCache *
0x180018eca  lea     rdx, CSCWMI_STR_METHOD_SUSPENDROOT; "SuspendRoot"
0x180018ed1  mov     rcx, rax; this
0x180018ed4  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018ed9  lea     rax, ??_7CCscWmiSuspendRootMethod@@6B@; const CCscWmiSuspendRootMethod::`vftable'
0x180018ee0  jmp     loc_180019011
0x180018ee5  lea     rax, CSCWMI_STR_METHOD_TRANSITIONOFFLINE; "TransitionOffline"
0x180018eec  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018ef0  mov     r9d, edi; cchCount1
0x180018ef3  mov     [rsp+68h+lpString2], rax; lpString2
0x180018ef8  mov     r8, rbp; lpString1
0x180018efb  mov     edx, r15d; dwCmpFlags
0x180018efe  mov     ecx, r12d; Locale
0x180018f01  call    cs:__imp_CompareStringW
0x180018f07  cmp     eax, 2
0x180018f0a  jnz     short loc_180018F47
0x180018f0c  test    rbx, rbx
0x180018f0f  jz      loc_180018C25
0x180018f15  lea     ecx, [rax+3Eh]; Size
0x180018f18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018f1d  mov     rdi, rax
0x180018f20  test    rax, rax
0x180018f23  jz      loc_180019016
0x180018f29  mov     r8, rbx; struct IOfflineFilesCache *
0x180018f2c  lea     rdx, CSCWMI_STR_METHOD_TRANSITIONOFFLINE; "TransitionOffline"
0x180018f33  mov     rcx, rax; this
0x180018f36  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018f3b  lea     rax, ??_7CCscWmiTransitionOfflineMethod@@6B@; const CCscWmiTransitionOfflineMethod::`vftable'
0x180018f42  jmp     loc_180019011
0x180018f47  lea     rax, CSCWMI_STR_METHOD_TRANSITIONONLINE; "TransitionOnline"
0x180018f4e  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018f52  mov     r9d, edi; cchCount1
0x180018f55  mov     [rsp+68h+lpString2], rax; lpString2
0x180018f5a  mov     r8, rbp; lpString1
0x180018f5d  mov     edx, r15d; dwCmpFlags
0x180018f60  mov     ecx, r12d; Locale
0x180018f63  call    cs:__imp_CompareStringW
0x180018f69  cmp     eax, 2
0x180018f6c  jnz     short loc_180018FA6
0x180018f6e  test    rbx, rbx
0x180018f71  jz      loc_180018C25
0x180018f77  lea     ecx, [rax+3Eh]; Size
0x180018f7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018f7f  mov     rdi, rax
0x180018f82  test    rax, rax
0x180018f85  jz      loc_180019016
0x180018f8b  mov     r8, rbx; struct IOfflineFilesCache *
0x180018f8e  lea     rdx, CSCWMI_STR_METHOD_TRANSITIONONLINE; "TransitionOnline"
0x180018f95  mov     rcx, rax; this
0x180018f98  call    ??0CCscWmiCacheMethod@@QEAA@PEBGPEAUIOfflineFilesCache@@@Z; CCscWmiCacheMethod::CCscWmiCacheMethod(ushort const *,IOfflineFilesCache *)
0x180018f9d  lea     rax, ??_7CCscWmiTransitionOnlineMethod@@6B@; const CCscWmiTransitionOnlineMethod::`vftable'
0x180018fa4  jmp     short loc_180019011
0x180018fa6  lea     rbx, CSCWMI_STR_METHOD_ENABLE; "Enable"
0x180018fad  mov     [rsp+68h+cchCount2], edi; cchCount2
0x180018fb1  mov     r9d, edi; cchCount1
0x180018fb4  mov     [rsp+68h+lpString2], rbx; lpString2
0x180018fb9  mov     r8, rbp; lpString1
0x180018fbc  mov     edx, r15d; dwCmpFlags
0x180018fbf  mov     ecx, r12d; Locale
0x180018fc2  call    cs:__imp_CompareStringW
0x180018fc8  cmp     eax, 2
0x180018fcb  jnz     short loc_18001902A
0x180018fcd  lea     ecx, [rax+26h]; Size
0x180018fd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018fd5  mov     rdi, rax
0x180018fd8  test    rax, rax
0x180018fdb  jz      short loc_180019016
0x180018fdd  mov     [rax+8], r15d
0x180018fe1  lea     rax, ??_7CCscWmiMethod@@6B@; const CCscWmiMethod::`vftable'
0x180018fe8  mov     [rdi], rax
0x180018feb  lea     rax, CSCWMI_STR_OFFLINEFILESCACHE; "Win32_OfflineFilesCache"
0x180018ff2  mov     [rdi+10h], rax
0x180018ff6  mov     [rdi+18h], rbx
0x180018ffa  mov     qword ptr [rdi+20h], 0
0x180019002  lock add cs:?g_cRefDll@@3JA, r15d; long g_cRefDll
0x18001900a  lea     rax, ??_7CCscWmiEnableMethod@@6B@; const CCscWmiEnableMethod::`vftable'
0x180019011  mov     [rdi], rax
0x180019014  jmp     short loc_180019018
0x180019016  xor     edi, edi
0x180019018  xor     ebx, ebx
0x18001901a  mov     [rsi], rdi
0x18001901d  test    rdi, rdi
0x180019020  mov     eax, 8007000Eh
0x180019025  cmovz   ebx, eax
0x180019028  jmp     short loc_18001902F
0x18001902a  mov     ebx, 8004100Ch
0x18001902f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019036  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
