# CSendToMyPhoneCommand::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x1800484e0`
- end: `0x1800487cd`
- name: `?Invoke@CSendToMyPhoneCommand@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `749`
- prototype: `int(CSendToMyPhoneCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800487e0`

## callees

- `0x180008900`
- `0x1800214cc`
- `0x1800254e0`
- `0x18002e7b0`
- `0x180030e10`
- `0x180031020`
- `0x18003a2c8`
- `0x18003a570`
- `0x18003a6a0`
- `0x1800484e0`
- `0x18004ce34`
- `0x18004cf7c`
- `0x1800532a4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800486f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800486f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800486d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800486d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048774`
- `USER32!GetAncestor` at `0x18004856a`
- `USER32!GetAncestor` at `0x18004856a`

## string_xrefs

- `0x180048600`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180048652`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004870f`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CSendToMyPhoneCommand::Invoke(
        CSendToMyPhoneCommand *this,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  HWND Ancestor; // r14
  HWND v6; // rbx
  __int64 v7; // r15
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HWND, GUID *, __int64); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  HWND v15; // rbx
  HRESULT v16; // eax
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-B8h]
  HSTRING string; // [rsp+30h] [rbp-A8h] BYREF
  HWND hwnd; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v21[56]; // [rsp+40h] [rbp-98h] BYREF
  HWND v22; // [rsp+78h] [rbp-60h]
  _BYTE *v23; // [rsp+80h] [rbp-58h]
  char v24; // [rsp+88h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  ShareVerbTelemetry::ShareVerb_InvokeSendToMyPhone();
  hwnd = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::start_and_watch_errors(
    &hwnd,
    v21);
  wil::com_ptr_t<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>,wil::err_returncode_policy>(&hwnd);
  v23 = v21;
  v24 = 1;
  hwnd = 0;
  GetWindowFromSite(*((IUnknown **)this + 5), &hwnd);
  Ancestor = GetAncestor(hwnd, 2u);
  v6 = v22;
  hwnd = v22;
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)v22 + 70);
  tip2::details::shared_data<0,0,0>::begin_update(v6 + 2);
  *((_BYTE *)v6 + 272) = Ancestor != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(&hwnd);
  v7 = *((_QWORD *)this + 21);
  if ( *(_QWORD *)(v7 + 168)
    || (v8 = *((_QWORD *)this + 22),
        v9 = *(__int64 (__fastcall **)(__int64, HWND, GUID *, __int64))(*(_QWORD *)v8 + 24LL),
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v7 + 168),
        v10 = v9(v8, Ancestor, &GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c, v7 + 168),
        v11 = v10,
        v10 >= 0) )
  {
    v13 = CModernShareCommand::SetupDataTransferManager(*((CModernShareCommand **)this + 21), a2);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v15 = v22;
      hwnd = v22;
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)v22 + 70);
      tip2::details::shared_data<0,0,0>::begin_update(v15 + 2);
      *((_BYTE *)v15 + 273) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(&hwnd);
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      WindowsDeleteString(0);
      string = 0;
      v16 = WindowsCreateStringReference(L"Microsoft.YourPhone_8wekyb3d8bbwe!App", 0x25u, &hstringHeader, &string);
      v17 = v16;
      if ( v16 >= 0 )
        v17 = (*(__int64 (__fastcall **)(_QWORD, HWND, HSTRING))(**((_QWORD **)this + 23) + 48LL))(
                *((_QWORD *)this + 23),
                Ancestor,
                string);
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC74,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v16,
          v18);
      WindowsDeleteString(string);
      string = 0;
      tip2::details::shared_data<0,0,0>::complete_without_lock(v22 + 2);
      tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(v21);
      return v17;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6F,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v13,
        v18);
      tip2::details::shared_data<0,0,0>::complete_without_lock(v22 + 2);
      tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(v21);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6C,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v10,
      v18);
    tip2::details::shared_data<0,0,0>::complete_without_lock(v22 + 2);
    tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(v21);
    return v11;
  }
}

```

## disassembly

```asm
0x1800484e0  mov     [rsp+arg_10], rbx
0x1800484e5  push    rsi
0x1800484e6  push    rdi
0x1800484e7  push    r12
0x1800484e9  push    r14
0x1800484eb  push    r15
0x1800484ed  sub     rsp, 0B0h
0x1800484f4  mov     rax, cs:__security_cookie
0x1800484fb  xor     rax, rsp
0x1800484fe  mov     [rsp+0D8h+var_30], rax
0x180048506  mov     r12, rdx
0x180048509  mov     rsi, rcx
0x18004850c  call    ?ShareVerb_InvokeSendToMyPhone@ShareVerbTelemetry@@SAXXZ; ShareVerbTelemetry::ShareVerb_InvokeSendToMyPhone(void)
0x180048511  mov     [rsp+0D8h+hwnd], 0
0x18004851a  lea     rdx, [rsp+0D8h+var_98]
0x18004851f  lea     rcx, [rsp+0D8h+hwnd]
0x180048524  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::start_and_watch_errors(void)
0x180048529  lea     rcx, [rsp+0D8h+hwnd]
0x18004852e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>,wil::err_returncode_policy>(void)
0x180048533  nop
0x180048534  lea     rax, [rsp+0D8h+var_98]
0x180048539  mov     [rsp+0D8h+var_58], rax
0x180048541  mov     [rsp+0D8h+var_50], 1
0x180048549  mov     [rsp+0D8h+hwnd], 0
0x180048552  lea     rdx, [rsp+0D8h+hwnd]; phwnd
0x180048557  mov     rcx, [rsi+28h]; punk
0x18004855b  call    ?GetWindowFromSite@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetWindowFromSite(IUnknown *,HWND__ * *)
0x180048560  mov     edx, 2; gaFlags
0x180048565  mov     rcx, [rsp+0D8h+hwnd]; hwnd
0x18004856a  call    cs:__imp_GetAncestor
0x180048570  mov     r14, rax
0x180048573  mov     rbx, [rsp+0D8h+var_60]
0x180048578  mov     [rsp+0D8h+hwnd], rbx
0x18004857d  test    rbx, rbx
0x180048580  jz      short loc_180048589
0x180048582  lock inc dword ptr [rbx+118h]
0x180048589  lea     rcx, [rbx+8]
0x18004858d  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180048592  test    r14, r14
0x180048595  setnz   cl
0x180048598  mov     [rbx+110h], cl
0x18004859e  lea     rcx, [rsp+0D8h+hwnd]
0x1800485a3  call    ??1?$test_data_control@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x1800485a8  mov     r15, [rsi+0A8h]
0x1800485af  cmp     qword ptr [r15+0A8h], 0
0x1800485b7  jnz     short loc_180048632
0x1800485b9  mov     rdi, [rsi+0B0h]
0x1800485c0  mov     rax, [rdi]
0x1800485c3  mov     rbx, [rax+18h]
0x1800485c7  lea     rcx, [r15+0A8h]
0x1800485ce  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800485d3  lea     r9, [r15+0A8h]
0x1800485da  lea     r8, _GUID_a5caee9b_8708_49d1_8d36_67d25a8da00c
0x1800485e1  mov     rdx, r14
0x1800485e4  mov     rcx, rdi
0x1800485e7  mov     rax, rbx
0x1800485ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485ef  mov     ebx, eax
0x1800485f1  test    eax, eax
0x1800485f3  jns     short loc_180048632
0x1800485f5  mov     rcx, [rsp+0D8h]; this
0x1800485fd  mov     r9d, eax; char *
0x180048600  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180048607  mov     edx, 0C6Ch; void *
0x18004860c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048611  nop
0x180048612  mov     rcx, [rsp+0D8h+var_60]
0x180048617  add     rcx, 8
0x18004861b  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180048620  nop
0x180048621  lea     rcx, [rsp+0D8h+var_98]
0x180048626  call    ??1?$test_watcher@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x18004862b  mov     eax, ebx
0x18004862d  jmp     loc_1800487A4
0x180048632  mov     rdx, r12; struct IShellItemArray *
0x180048635  mov     rcx, [rsi+0A8h]; this
0x18004863c  call    ?SetupDataTransferManager@CModernShareCommand@@QEAAJPEAUIShellItemArray@@@Z; CModernShareCommand::SetupDataTransferManager(IShellItemArray *)
0x180048641  mov     ebx, eax
0x180048643  test    eax, eax
0x180048645  jns     short loc_180048684
0x180048647  mov     rcx, [rsp+0D8h]; this
0x18004864f  mov     r9d, eax; char *
0x180048652  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180048659  mov     edx, 0C6Fh; void *
0x18004865e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048663  nop
0x180048664  mov     rcx, [rsp+0D8h+var_60]
0x180048669  add     rcx, 8
0x18004866d  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180048672  nop
0x180048673  lea     rcx, [rsp+0D8h+var_98]
0x180048678  call    ??1?$test_watcher@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x18004867d  mov     eax, ebx
0x18004867f  jmp     loc_1800487A4
0x180048684  mov     rbx, [rsp+0D8h+var_60]
0x180048689  mov     [rsp+0D8h+hwnd], rbx
0x18004868e  test    rbx, rbx
0x180048691  jz      short loc_18004869A
0x180048693  lock inc dword ptr [rbx+118h]
0x18004869a  lea     rcx, [rbx+8]
0x18004869e  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800486a3  mov     byte ptr [rbx+111h], 1
0x1800486aa  lea     rcx, [rsp+0D8h+hwnd]
0x1800486af  call    ??1?$test_data_control@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_data_control<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x1800486b4  xorps   xmm0, xmm0
0x1800486b7  xor     eax, eax
0x1800486b9  movups  xmmword ptr [rsp+0D8h+hstringHeader.Reserved], xmm0
0x1800486c1  mov     qword ptr [rsp+0D8h+hstringHeader.Reserved+10h], rax
0x1800486c9  mov     [rsp+0D8h+string], rax
0x1800486ce  xor     ecx, ecx; string
0x1800486d0  call    cs:__imp_WindowsDeleteString
0x1800486d6  mov     [rsp+0D8h+string], 0
0x1800486df  lea     r9, [rsp+0D8h+string]; string
0x1800486e4  lea     r8, [rsp+0D8h+hstringHeader]; hstringHeader
0x1800486ec  mov     edx, 25h ; '%'; length
0x1800486f1  lea     rcx, sourceString; "Microsoft.YourPhone_8wekyb3d8bbwe!App"
0x1800486f8  call    cs:__imp_WindowsCreateStringReference
0x1800486fe  mov     ebx, eax
0x180048700  test    eax, eax
0x180048702  jns     short loc_180048752
0x180048704  mov     rcx, [rsp+0D8h]; this
0x18004870c  mov     r9d, eax; char *
0x18004870f  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180048716  mov     edx, 0C74h; void *
0x18004871b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048720  nop
0x180048721  mov     rcx, [rsp+0D8h+string]; string
0x180048726  call    cs:__imp_WindowsDeleteString
0x18004872c  mov     [rsp+0D8h+string], 0
0x180048735  mov     rcx, [rsp+0D8h+var_60]
0x18004873a  add     rcx, 8
0x18004873e  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180048743  nop
0x180048744  lea     rcx, [rsp+0D8h+var_98]
0x180048749  call    ??1?$test_watcher@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x18004874e  mov     eax, ebx
0x180048750  jmp     short loc_1800487A4
0x180048752  mov     rcx, [rsi+0B8h]
0x180048759  mov     rax, [rcx]
0x18004875c  mov     r8, [rsp+0D8h+string]
0x180048761  mov     rdx, r14
0x180048764  mov     rax, [rax+30h]
0x180048768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004876d  mov     ebx, eax
0x18004876f  mov     rcx, [rsp+0D8h+string]; string
0x180048774  call    cs:__imp_WindowsDeleteString
0x18004877a  mov     [rsp+0D8h+string], 0
0x180048783  mov     rcx, [rsp+0D8h+var_60]
0x180048788  add     rcx, 8
0x18004878c  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180048791  nop
0x180048792  lea     rcx, [rsp+0D8h+var_98]
0x180048797  call    ??1?$test_watcher@V?$merged_data@U_tip_SendToMyPhoneVerbInvoked@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>::~test_watcher<tip2::details::merged_data<_tip_SendToMyPhoneVerbInvoked,_tip_SendToMyPhoneVerbInvoked>>(void)
0x18004879c  mov     eax, ebx
0x18004879e  jmp     short loc_1800487A4
0x1800487a0  mov     eax, dword ptr [rsp+0D8h+string]
0x1800487a4  mov     rcx, [rsp+0D8h+var_30]
0x1800487ac  xor     rcx, rsp; StackCookie
0x1800487af  call    __security_check_cookie
0x1800487b4  mov     rbx, [rsp+0D8h+arg_10]
0x1800487bc  add     rsp, 0B0h
0x1800487c3  pop     r15
0x1800487c5  pop     r14
0x1800487c7  pop     r12
0x1800487c9  pop     rdi
0x1800487ca  pop     rsi
0x1800487cb  retn
```
