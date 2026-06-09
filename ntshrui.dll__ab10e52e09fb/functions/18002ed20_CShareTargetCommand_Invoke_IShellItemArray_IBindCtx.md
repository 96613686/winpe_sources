# CShareTargetCommand::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x18002ed20`
- end: `0x18002f116`
- name: `?Invoke@CShareTargetCommand@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `1014`
- prototype: `int(CShareTargetCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008900`
- `0x1800214cc`
- `0x1800254e0`
- `0x180026388`
- `0x18002bf38`
- `0x18002c0ac`
- `0x18002c7a8`
- `0x18002ceac`
- `0x18002cee4`
- `0x18002d460`
- `0x18002e7b0`
- `0x18002ed20`
- `0x180030e10`
- `0x180030e44`
- `0x180031020`
- `0x18004ce34`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ef0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f0cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ef0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f0cb`
- `USER32!GetAncestor` at `0x18002edc7`
- `USER32!GetAncestor` at `0x18002edc7`

## string_xrefs

- `0x18002ee29`: `shell\osshell\lmui\ntshrui\dll\modernshareverbs.cpp`
- `0x18002ee6a`: `shell\osshell\lmui\ntshrui\dll\modernshareverbs.cpp`
- `0x18002eef8`: `shell\osshell\lmui\ntshrui\dll\modernshareverbs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CShareTargetCommand::Invoke(
        CShareTargetCommand *this,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  char *v5; // r14
  HWND Ancestor; // r13
  __int64 v7; // r15
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HWND, GUID *, __int64); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  const WCHAR *v17; // rax
  UINT32 v18; // edx
  HRESULT v19; // eax
  unsigned int v20; // ebx
  int v21; // esi
  __int64 v22; // rbx
  __int64 v23; // rbx
  char **v24; // rbx
  __int64 v25; // r8
  char *v26; // rdx
  HWND v27; // r9
  char *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rbx
  char **v31; // rbx
  __int64 v32; // r8
  char *v33; // rdx
  HWND v34; // r9
  char *v35; // rdi
  __int64 v36; // rbx
  int v37; // [rsp+20h] [rbp-C8h]
  HSTRING string; // [rsp+30h] [rbp-B8h] BYREF
  const unsigned __int16 *v39; // [rsp+38h] [rbp-B0h] BYREF
  HWND hwnd; // [rsp+40h] [rbp-A8h] BYREF
  char *v41; // [rsp+48h] [rbp-A0h]
  char *v42; // [rsp+50h] [rbp-98h]
  _BYTE v43[56]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v44; // [rsp+98h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v42 = (char *)this + 176;
  hwnd = (HWND)winrt::hstring::c_str((CShareTargetCommand *)((char *)this + 176));
  v5 = (char *)this + 168;
  v39 = winrt::hstring::c_str((CShareTargetCommand *)((char *)this + 168));
  ShareVerbTelemetry::ShareWithVerb_ShareTargetSelected<unsigned short const *,unsigned short const *>(&v39, &hwnd);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>>(v43);
  hwnd = 0;
  GetWindowFromSite(*((IUnknown **)this + 4), &hwnd);
  Ancestor = GetAncestor(hwnd, 2u);
  v7 = *((_QWORD *)this + 20);
  if ( *(_QWORD *)(v7 + 168)
    || (v8 = *((_QWORD *)this + 28),
        v9 = *(__int64 (__fastcall **)(__int64, HWND, GUID *, __int64))(*(_QWORD *)v8 + 24LL),
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v7 + 168),
        v10 = v9(v8, Ancestor, &GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c, v7 + 168),
        v11 = v10,
        v10 >= 0) )
  {
    v13 = CModernShareCommand::SetupDataTransferManager(*((CModernShareCommand **)this + 20), a2);
    v14 = v13;
    if ( v13 >= 0 )
    {
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      WindowsDeleteString(0);
      string = 0;
      v15 = winrt::hstring::c_str((CShareTargetCommand *)((char *)this + 168));
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v17 = winrt::hstring::c_str((CShareTargetCommand *)((char *)this + 168));
      v19 = WindowsCreateStringReference(v17, v18, &hstringHeader, &string);
      v20 = v19;
      if ( v19 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(_QWORD, HWND, HSTRING))(**((_QWORD **)this + 29) + 48LL))(
                *((_QWORD *)this + 29),
                Ancestor,
                string);
        v22 = v44;
        v39 = (const unsigned __int16 *)v44;
        if ( v21 < 0 )
        {
          if ( v44 )
            _InterlockedIncrement((volatile signed __int32 *)(v44 + 344));
          tip2::details::shared_data<0,0,0>::begin_update(v22 + 8);
          *(_BYTE *)(v22 + 274) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(&v39);
          v23 = v44;
          v39 = (const unsigned __int16 *)v44;
          if ( v44 )
            _InterlockedIncrement((volatile signed __int32 *)(v44 + 344));
          tip2::details::shared_data<0,0,0>::begin_update(v23 + 8);
          v24 = (char **)(v23 + 280);
          winrt::hstring::operator std::basic_string_view<unsigned short>(v5, &hwnd);
          v26 = v41;
          v27 = hwnd;
          if ( v41 > v24[3] )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v24,
              v41,
              v25,
              hwnd);
          }
          else
          {
            if ( (unsigned __int64)v24[3] <= 7 )
              v28 = (char *)v24;
            else
              v28 = *v24;
            v24[2] = v41;
            v29 = 2LL * (_QWORD)v26;
            memmove_0(v28, v27, 2LL * (_QWORD)v26);
            *(_WORD *)&v28[v29] = 0;
          }
          tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(&v39);
          v30 = v44;
          v39 = (const unsigned __int16 *)v44;
          if ( v44 )
            _InterlockedIncrement((volatile signed __int32 *)(v44 + 344));
          tip2::details::shared_data<0,0,0>::begin_update(v30 + 8);
          v31 = (char **)(v30 + 312);
          winrt::hstring::operator std::basic_string_view<unsigned short>(v42, &hwnd);
          v33 = v41;
          v34 = hwnd;
          if ( v41 > v31[3] )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              v31,
              v41,
              v32,
              hwnd);
          }
          else
          {
            if ( (unsigned __int64)v31[3] <= 7 )
              v35 = (char *)v31;
            else
              v35 = *v31;
            v31[2] = v41;
            v36 = 2LL * (_QWORD)v33;
            memmove_0(v35, v34, 2LL * (_QWORD)v33);
            *(_WORD *)&v35[v36] = 0;
          }
        }
        else
        {
          if ( v44 )
            _InterlockedIncrement((volatile signed __int32 *)(v44 + 344));
          tip2::details::shared_data<0,0,0>::begin_update(v22 + 8);
          *(_BYTE *)(v22 + 272) = 1;
        }
        tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(&v39);
        tip2::details::shared_data<0,0,0>::complete_without_lock(v44 + 8);
        WindowsDeleteString(string);
        string = 0;
        tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(v43);
        return (unsigned int)v21;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\modernshareverbs.cpp",
          (const char *)(unsigned int)v19,
          v37);
        WindowsDeleteString(string);
        string = 0;
        tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(v43);
        return v20;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\modernshareverbs.cpp",
        (const char *)(unsigned int)v13,
        v37);
      tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(v43);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\modernshareverbs.cpp",
      (const char *)(unsigned int)v10,
      v37);
    tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(v43);
    return v11;
  }
}

```

## disassembly

```asm
0x18002ed20  mov     [rsp+arg_10], rbx
0x18002ed25  mov     [rsp+arg_18], rsi
0x18002ed2a  push    rdi
0x18002ed2b  push    r12
0x18002ed2d  push    r13
0x18002ed2f  push    r14
0x18002ed31  push    r15
0x18002ed33  sub     rsp, 0C0h
0x18002ed3a  mov     rax, cs:__security_cookie
0x18002ed41  xor     rax, rsp
0x18002ed44  mov     [rsp+0E8h+var_30], rax
0x18002ed4c  mov     r12, rdx
0x18002ed4f  mov     rsi, rcx
0x18002ed52  lea     r8, [rcx+0C0h]
0x18002ed59  cmp     qword ptr [r8+18h], 0Fh
0x18002ed5e  jbe     short loc_18002ED63
0x18002ed60  mov     r8, [r8]
0x18002ed63  lea     rax, [rcx+0B0h]
0x18002ed6a  mov     [rsp+0E8h+var_98], rax
0x18002ed6f  mov     rcx, rax; this
0x18002ed72  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002ed77  mov     [rsp+0E8h+hwnd], rax
0x18002ed7c  lea     r14, [rsi+0A8h]
0x18002ed83  mov     rcx, r14; this
0x18002ed86  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002ed8b  mov     [rsp+0E8h+var_B0], rax
0x18002ed90  lea     rdx, [rsp+0E8h+hwnd]
0x18002ed95  lea     rcx, [rsp+0E8h+var_B0]
0x18002ed9a  call    ??$ShareWithVerb_ShareTargetSelected@PEBGPEBG@ShareVerbTelemetry@@SAX$$QEAPEBG0PEBD@Z; ShareVerbTelemetry::ShareWithVerb_ShareTargetSelected<ushort const *,ushort const *>(ushort const * &&,ushort const * &&,char const *)
0x18002ed9f  lea     rcx, [rsp+0E8h+var_88]
0x18002eda4  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18002eda9  nop
0x18002edaa  xor     edi, edi
0x18002edac  mov     [rsp+0E8h+hwnd], rdi
0x18002edb1  lea     rdx, [rsp+0E8h+hwnd]; phwnd
0x18002edb6  mov     rcx, [rsi+20h]; punk
0x18002edba  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x18002edbf  lea     edx, [rdi+2]; gaFlags
0x18002edc2  mov     rcx, [rsp+0E8h+hwnd]; hwnd
0x18002edc7  call    cs:__imp_GetAncestor
0x18002edcd  mov     r13, rax
0x18002edd0  mov     r15, [rsi+0A0h]
0x18002edd7  cmp     [r15+0A8h], rdi
0x18002edde  jnz     short loc_18002EE4A
0x18002ede0  mov     rdi, [rsi+0E0h]
0x18002ede7  mov     rdx, [rdi]
0x18002edea  mov     rbx, [rdx+18h]
0x18002edee  lea     rcx, [r15+0A8h]
0x18002edf5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002edfa  lea     r9, [r15+0A8h]
0x18002ee01  lea     r8, _GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c
0x18002ee08  mov     rdx, r13
0x18002ee0b  mov     rcx, rdi
0x18002ee0e  mov     rax, rbx
0x18002ee11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee16  mov     ebx, eax
0x18002ee18  xor     edi, edi
0x18002ee1a  test    eax, eax
0x18002ee1c  jns     short loc_18002EE4A
0x18002ee1e  mov     rcx, [rsp+0E8h]; this
0x18002ee26  mov     r9d, eax; char *
0x18002ee29  lea     r8, aShellOsshellLm_2; "shell\\osshell\\lmui\\ntshrui\\dll\\mod"...
0x18002ee30  lea     edx, [rdi+65h]; void *
0x18002ee33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee38  nop
0x18002ee39  lea     rcx, [rsp+0E8h+var_88]
0x18002ee3e  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002ee43  mov     eax, ebx
0x18002ee45  jmp     loc_18002F0E8
0x18002ee4a  mov     rdx, r12; struct IShellItemArray *
0x18002ee4d  mov     rcx, [rsi+0A0h]; this
0x18002ee54  call    ?SetupDataTransferManager@CModernShareCommand@@QEAAJPEAUIShellItemArray@@@Z; CModernShareCommand::SetupDataTransferManager(IShellItemArray *)
0x18002ee59  mov     ebx, eax
0x18002ee5b  test    eax, eax
0x18002ee5d  jns     short loc_18002EE8D
0x18002ee5f  mov     rcx, [rsp+0E8h]; this
0x18002ee67  mov     r9d, eax; char *
0x18002ee6a  lea     r8, aShellOsshellLm_2; "shell\\osshell\\lmui\\ntshrui\\dll\\mod"...
0x18002ee71  mov     edx, 68h ; 'h'; void *
0x18002ee76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee7b  nop
0x18002ee7c  lea     rcx, [rsp+0E8h+var_88]
0x18002ee81  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002ee86  mov     eax, ebx
0x18002ee88  jmp     loc_18002F0E8
0x18002ee8d  xorps   xmm0, xmm0
0x18002ee90  xor     eax, eax
0x18002ee92  movups  xmmword ptr [rsp+0E8h+hstringHeader.Reserved], xmm0
0x18002ee9a  mov     qword ptr [rsp+0E8h+hstringHeader.Reserved+10h], rax
0x18002eea2  mov     [rsp+0E8h+string], rdi
0x18002eea7  xor     ecx, ecx; string
0x18002eea9  call    cs:__imp_WindowsDeleteString
0x18002eeaf  mov     [rsp+0E8h+string], rdi
0x18002eeb4  mov     rcx, r14; this
0x18002eeb7  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002eebc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002eec0  inc     rdx
0x18002eec3  cmp     [rax+rdx*2], di
0x18002eec7  jnz     short loc_18002EEC0
0x18002eec9  mov     rcx, r14; this
0x18002eecc  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002eed1  lea     r9, [rsp+0E8h+string]; string
0x18002eed6  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x18002eede  mov     rcx, rax; sourceString
0x18002eee1  call    cs:__imp_WindowsCreateStringReference
0x18002eee7  mov     ebx, eax
0x18002eee9  test    eax, eax
0x18002eeeb  jns     short loc_18002EF2B
0x18002eeed  mov     rcx, [rsp+0E8h]; this
0x18002eef5  mov     r9d, eax; char *
0x18002eef8  lea     r8, aShellOsshellLm_2; "shell\\osshell\\lmui\\ntshrui\\dll\\mod"...
0x18002eeff  mov     edx, 6Dh ; 'm'; void *
0x18002ef04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef09  nop
0x18002ef0a  mov     rcx, [rsp+0E8h+string]; string
0x18002ef0f  call    cs:__imp_WindowsDeleteString
0x18002ef15  mov     [rsp+0E8h+string], rdi
0x18002ef1a  lea     rcx, [rsp+0E8h+var_88]
0x18002ef1f  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002ef24  mov     eax, ebx
0x18002ef26  jmp     loc_18002F0E8
0x18002ef2b  mov     rcx, [rsi+0E8h]
0x18002ef32  mov     rax, [rcx]
0x18002ef35  mov     r8, [rsp+0E8h+string]
0x18002ef3a  mov     rdx, r13
0x18002ef3d  mov     rax, [rax+30h]
0x18002ef41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef46  mov     esi, eax
0x18002ef48  mov     rbx, [rsp+0E8h+var_50]
0x18002ef50  mov     [rsp+0E8h+var_B0], rbx
0x18002ef55  test    eax, eax
0x18002ef57  js      short loc_18002EF7A
0x18002ef59  test    rbx, rbx
0x18002ef5c  jz      short loc_18002EF65
0x18002ef5e  lock inc dword ptr [rbx+158h]
0x18002ef65  lea     rcx, [rbx+8]
0x18002ef69  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002ef6e  mov     byte ptr [rbx+110h], 1
0x18002ef75  jmp     loc_18002F0AA
0x18002ef7a  test    rbx, rbx
0x18002ef7d  jz      short loc_18002EF86
0x18002ef7f  lock inc dword ptr [rbx+158h]
0x18002ef86  lea     rcx, [rbx+8]
0x18002ef8a  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002ef8f  mov     byte ptr [rbx+112h], 1
0x18002ef96  lea     rcx, [rsp+0E8h+var_B0]
0x18002ef9b  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002efa0  mov     rbx, [rsp+0E8h+var_50]
0x18002efa8  mov     [rsp+0E8h+var_B0], rbx
0x18002efad  test    rbx, rbx
0x18002efb0  jz      short loc_18002EFB9
0x18002efb2  lock inc dword ptr [rbx+158h]
0x18002efb9  lea     rcx, [rbx+8]
0x18002efbd  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002efc2  nop
0x18002efc3  add     rbx, 118h
0x18002efca  lea     rdx, [rsp+0E8h+hwnd]
0x18002efcf  mov     rcx, r14
0x18002efd2  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002efd7  mov     rdx, [rsp+0E8h+var_A0]
0x18002efdc  mov     r9, [rsp+0E8h+hwnd]
0x18002efe1  cmp     rdx, [rbx+18h]
0x18002efe5  ja      short loc_18002F016
0x18002efe7  cmp     qword ptr [rbx+18h], 7
0x18002efec  jbe     short loc_18002EFF3
0x18002efee  mov     rdi, [rbx]
0x18002eff1  jmp     short loc_18002EFF6
0x18002eff3  mov     rdi, rbx
0x18002eff6  mov     [rbx+10h], rdx
0x18002effa  lea     rbx, [rdx+rdx]
0x18002effe  mov     r8, rbx; Size
0x18002f001  mov     rdx, r9; Src
0x18002f004  mov     rcx, rdi; void *
0x18002f007  call    memmove_0
0x18002f00c  xor     eax, eax
0x18002f00e  mov     [rbx+rdi], ax
0x18002f012  xor     edi, edi
0x18002f014  jmp     short loc_18002F01F
0x18002f016  mov     rcx, rbx
0x18002f019  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002f01e  nop
0x18002f01f  lea     rcx, [rsp+0E8h+var_B0]
0x18002f024  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002f029  mov     rbx, [rsp+0E8h+var_50]
0x18002f031  mov     [rsp+0E8h+var_B0], rbx
0x18002f036  test    rbx, rbx
0x18002f039  jz      short loc_18002F042
0x18002f03b  lock inc dword ptr [rbx+158h]
0x18002f042  lea     rcx, [rbx+8]
0x18002f046  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18002f04b  nop
0x18002f04c  add     rbx, 138h
0x18002f053  lea     rdx, [rsp+0E8h+hwnd]
0x18002f058  mov     rcx, [rsp+0E8h+var_98]
0x18002f05d  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002f062  mov     rdx, [rsp+0E8h+var_A0]
0x18002f067  mov     r9, [rsp+0E8h+hwnd]
0x18002f06c  cmp     rdx, [rbx+18h]
0x18002f070  ja      short loc_18002F0A1
0x18002f072  cmp     qword ptr [rbx+18h], 7
0x18002f077  jbe     short loc_18002F07E
0x18002f079  mov     rdi, [rbx]
0x18002f07c  jmp     short loc_18002F081
0x18002f07e  mov     rdi, rbx
0x18002f081  mov     [rbx+10h], rdx
0x18002f085  lea     rbx, [rdx+rdx]
0x18002f089  mov     r8, rbx; Size
0x18002f08c  mov     rdx, r9; Src
0x18002f08f  mov     rcx, rdi; void *
0x18002f092  call    memmove_0
0x18002f097  xor     eax, eax
0x18002f099  mov     [rbx+rdi], ax
0x18002f09d  xor     edi, edi
0x18002f09f  jmp     short loc_18002F0AA
0x18002f0a1  mov     rcx, rbx
0x18002f0a4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002f0a9  nop
0x18002f0aa  lea     rcx, [rsp+0E8h+var_B0]
0x18002f0af  call    ??1?$test_data_control@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002f0b4  mov     rcx, [rsp+0E8h+var_50]
0x18002f0bc  add     rcx, 8
0x18002f0c0  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18002f0c5  nop
0x18002f0c6  mov     rcx, [rsp+0E8h+string]; string
0x18002f0cb  call    cs:__imp_WindowsDeleteString
0x18002f0d1  mov     [rsp+0E8h+string], rdi
0x18002f0d6  lea     rcx, [rsp+0E8h+var_88]
0x18002f0db  call    ??1?$test_watcher@V?$merged_data@U_tip_ShareWithVerbUserActionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>::~test_watcher<tip2::details::merged_data<_tip_ShareWithVerbUserActionTipTest,_tip_ShareWithVerbUserActionTipTest>>(void)
0x18002f0e0  mov     eax, esi
0x18002f0e2  jmp     short loc_18002F0E8
0x18002f0e4  mov     eax, dword ptr [rsp+0E8h+string]
0x18002f0e8  mov     rcx, [rsp+0E8h+var_30]
0x18002f0f0  xor     rcx, rsp; StackCookie
0x18002f0f3  call    __security_check_cookie
0x18002f0f8  lea     r11, [rsp+0E8h+var_28]
0x18002f100  mov     rbx, [r11+40h]
0x18002f104  mov     rsi, [r11+48h]
0x18002f108  mov     rsp, r11
0x18002f10b  pop     r15
0x18002f10d  pop     r14
0x18002f10f  pop     r13
0x18002f111  pop     r12
0x18002f113  pop     rdi
0x18002f114  retn
```
