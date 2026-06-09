# _lambda_2a5d63626e09ba70a6122ff7784e5fcf_::operator()

- ea: `0x180072ef0`
- end: `0x180073213`
- name: `_lambda_2a5d63626e09ba70a6122ff7784e5fcf_::operator()`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180075d34`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18000ac48`
- `0x180019140`
- `0x18001aa9c`
- `0x180026b68`
- `0x180056480`
- `0x180056b28`
- `0x180072ef0`
- `0x180073adc`
- `0x180075780`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072f7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072f7c`

## string_xrefs

- `0x180072f57`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180072fa2`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180072fff`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180073101`: `Feature update scan not complete after %d seconds; abandoning`
- `0x1800730df`: `ExpeditedUpdateWUTask unexpected waitResult.`
- `0x180073151`: `ExpeditedUpdateWUTask update Found.`
- `0x180073186`: `ExpeditedUpdateWUTask update not Found.`
- `0x180072fe6`: `ExpeditedUpdateWUTask begin scan HResult code [hr=0x%08X]`
- `0x18007304d`: `TestFeatureUpdateScanTimeoutSeconds`
- `0x180073074`: `Using test hook feature update scan timeout value (%d seconds)`
- `0x1800730b7`: `Wait result from WU feature update search: %#X`
- `0x1800731a6`: `ExpeditedUpdateWUTask scan canceled`
- `0x1800731b4`: `ExpeditedUpdateWUTask scan failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_2a5d63626e09ba70a6122ff7784e5fcf_::operator()(__int64 **a1)
{
  bool v2; // r14
  __int64 v3; // rdi
  int v4; // eax
  unsigned __int64 updated; // rbx
  ExpeditedUpdateWUTask *v6; // rbx
  __int64 v7; // r8
  unsigned int v8; // edi
  __int64 v9; // rbx
  __int64 v10; // rcx
  unsigned int v12; // [rsp+20h] [rbp-39h]
  unsigned int v13; // [rsp+28h] [rbp-31h]
  bool v14; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-25h] BYREF
  struct ISearchJob *v16; // [rsp+38h] [rbp-21h] BYREF
  struct IUpdateSearcher *v17; // [rsp+40h] [rbp-19h] BYREF
  void **v18; // [rsp+48h] [rbp-11h] BYREF
  void *EventW; // [rsp+50h] [rbp-9h]
  void *v20[2]; // [rsp+58h] [rbp-1h] BYREF
  unsigned int v21[4]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = 0;
  v14 = 0;
  v17 = 0;
  v3 = **a1;
  updated = *(_QWORD *)(*(_QWORD *)v3 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  v4 = ((__int64 (__fastcall *)(__int64, struct IUpdateSearcher **))updated)(v3, &v17);
  LODWORD(updated) = v4;
  if ( v4 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !EventW )
    {
      LODWORD(updated) = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)0x8000FFFFLL,
        v12);
LABEL_32:
      v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v18);
      goto LABEL_33;
    }
    v16 = 0;
    v6 = (ExpeditedUpdateWUTask *)a1[1];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    updated = (unsigned int)ExpeditedUpdateWUTask::BeginAsyncExpeditedUpdateSearch(v6, v17, EventW, &v16);
    UnattendLogW(0, L"ExpeditedUpdateWUTask begin scan HResult code [hr=0x%08X]", updated);
    if ( (updated & 0x80000000) != 0LL )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)updated,
        v12);
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
      goto LABEL_32;
    }
    if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_OOBE_Machine_Plugins_Context,
        ExpeditedUpdateScan_Start,
        v7,
        1,
        v21);
    v8 = 120;
    v15 = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
                L"TestFeatureUpdateScanTimeoutSeconds",
                &v15) >= 0
      && v15 )
    {
      UnattendLogW(0, L"Using test hook feature update scan timeout value (%d seconds)");
      v8 = v15;
    }
    v20[0] = (void *)a1[1][76];
    v20[1] = EventW;
    v9 = SHProcessMessagesUntilEventsEx((HWND)v20[0], v20, 2u, 1000 * v8, v12, v13);
    UnattendLogW(0, L"Wait result from WU feature update search: %#X", v9);
    if ( (_DWORD)v9 )
    {
      if ( (_DWORD)v9 == 1 )
      {
        LODWORD(updated) = ExpeditedUpdateWUTask::OnExpeditedUpdateSearchCompleted(
                             (ExpeditedUpdateWUTask *)a1[1],
                             v17,
                             v16,
                             &v14);
        v2 = v14;
        goto LABEL_20;
      }
      if ( (_DWORD)v9 != 258 )
      {
        if ( (_DWORD)v9 == -1 )
        {
          LODWORD(updated) = ResultFromKnownLastError();
        }
        else
        {
          UnattendLogW(1, L"ExpeditedUpdateWUTask unexpected waitResult.");
          LODWORD(updated) = -2147418113;
        }
        goto LABEL_20;
      }
      UnattendLogW(2, L"Feature update scan not complete after %d seconds; abandoning", v8);
    }
    ((void (__fastcall *)(struct ISearchJob *))v16->lpVtbl->RequestAbort)(v16);
    LODWORD(updated) = -2147467260;
LABEL_20:
    if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
      McTemplateU0q_EventWriteTransfer(v10, ExpeditedUpdateScan_Stop, v2);
    if ( (updated & 0x80000000) != 0LL )
    {
      if ( (_DWORD)updated == -2147467260 )
        UnattendLogW(2, L"ExpeditedUpdateWUTask scan canceled");
      else
        UnattendLogW(1, L"ExpeditedUpdateWUTask scan failed.");
      *(_DWORD *)a1[2] = 5;
    }
    else if ( v2 )
    {
      UnattendLogW(0, L"ExpeditedUpdateWUTask update Found.");
      *(_DWORD *)a1[2] = 2;
    }
    else
    {
      UnattendLogW(0, L"ExpeditedUpdateWUTask update not Found.");
      *(_DWORD *)a1[2] = 3;
    }
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB0,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v4,
    v12);
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180072ef0  push    rbp
0x180072ef2  push    rbx
0x180072ef3  push    rsi
0x180072ef4  push    rdi
0x180072ef5  push    r12
0x180072ef7  push    r14
0x180072ef9  lea     rbp, [rsp-2Fh]
0x180072efe  sub     rsp, 88h
0x180072f05  mov     rax, cs:__security_cookie
0x180072f0c  xor     rax, rsp
0x180072f0f  mov     [rbp+57h+var_38], rax
0x180072f13  mov     rsi, rcx
0x180072f16  xor     r14b, r14b
0x180072f19  mov     [rbp+57h+var_80], r14b
0x180072f1d  mov     [rbp+57h+var_70], 0
0x180072f25  mov     rax, [rcx]
0x180072f28  mov     rdi, [rax]
0x180072f2b  mov     rax, [rdi]
0x180072f2e  mov     rbx, [rax+60h]
0x180072f32  lea     rcx, [rbp+57h+var_70]
0x180072f36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072f3b  lea     rdx, [rbp+57h+var_70]
0x180072f3f  mov     rcx, rdi
0x180072f42  mov     rax, rbx
0x180072f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f4a  mov     ebx, eax
0x180072f4c  test    eax, eax
0x180072f4e  jns     short loc_180072F6D
0x180072f50  mov     rcx, [rbp+5Fh]; this
0x180072f54  mov     r9d, eax; char *
0x180072f57  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180072f5e  mov     edx, 0B0h; void *
0x180072f63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f68  jmp     loc_1800731EC
0x180072f6d  xor     r9d, r9d; lpName
0x180072f70  xor     r8d, r8d; bInitialState
0x180072f73  lea     r12d, [r9+1]
0x180072f77  mov     edx, r12d; bManualReset
0x180072f7a  xor     ecx, ecx; lpEventAttributes
0x180072f7c  call    cs:__imp_CreateEventW
0x180072f82  mov     [rbp+57h+var_60], rax
0x180072f86  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180072f8d  mov     [rbp+57h+var_68], rcx
0x180072f91  test    rax, rax
0x180072f94  jnz     short loc_180072FB8
0x180072f96  mov     rcx, [rbp+5Fh]; this
0x180072f9a  mov     ebx, 8000FFFFh
0x180072f9f  mov     r9d, ebx; char *
0x180072fa2  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180072fa9  mov     edx, 0B3h; void *
0x180072fae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072fb3  jmp     loc_1800731D7
0x180072fb8  mov     [rbp+57h+var_78], 0
0x180072fc0  mov     rbx, [rsi+8]
0x180072fc4  lea     rcx, [rbp+57h+var_78]
0x180072fc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072fcd  lea     r9, [rbp+57h+var_78]; struct ISearchJob **
0x180072fd1  mov     r8, [rbp+57h+var_60]; void *
0x180072fd5  mov     rdx, [rbp+57h+var_70]; struct IUpdateSearcher *
0x180072fd9  mov     rcx, rbx; this
0x180072fdc  call    ?BeginAsyncExpeditedUpdateSearch@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdateSearcher@@PEAXPEAPEAUISearchJob@@@Z; ExpeditedUpdateWUTask::BeginAsyncExpeditedUpdateSearch(IUpdateSearcher *,void *,ISearchJob * *)
0x180072fe1  mov     ebx, eax
0x180072fe3  mov     r8d, eax
0x180072fe6  lea     rdx, aExpeditedupdat_65; "ExpeditedUpdateWUTask begin scan HResul"...
0x180072fed  xor     ecx, ecx
0x180072fef  call    UnattendLogW
0x180072ff4  test    ebx, ebx
0x180072ff6  jns     short loc_180073015
0x180072ff8  mov     rcx, [rbp+5Fh]; this
0x180072ffc  mov     r9d, ebx; char *
0x180072fff  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180073006  mov     edx, 0B8h; void *
0x18007300b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073010  jmp     loc_1800731CD
0x180073015  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, r12b
0x18007301c  jz      short loc_18007303D
0x18007301e  lea     rax, [rbp+57h+var_48]
0x180073022  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x180073027  mov     r9d, r12d
0x18007302a  lea     rdx, ExpeditedUpdateScan_Start
0x180073031  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x180073038  call    McGenEventWrite_EventWriteTransfer
0x18007303d  mov     edi, 78h ; 'x'
0x180073042  mov     [rbp+57h+var_7C], 0
0x180073049  lea     r9, [rbp+57h+var_7C]; unsigned int *
0x18007304d  lea     r8, aTestfeatureupd; "TestFeatureUpdateScanTimeoutSeconds"
0x180073054  lea     rdx, aSoftwareMicros_39; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007305b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180073062  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180073067  test    eax, eax
0x180073069  js      short loc_180073085
0x18007306b  mov     r8d, [rbp+57h+var_7C]
0x18007306f  test    r8d, r8d
0x180073072  jz      short loc_180073085
0x180073074  lea     rdx, aUsingTestHookF; "Using test hook feature update scan tim"...
0x18007307b  xor     ecx, ecx
0x18007307d  call    UnattendLogW
0x180073082  mov     edi, [rbp+57h+var_7C]
0x180073085  mov     rax, [rsi+8]
0x180073089  mov     rcx, [rax+260h]; HWND
0x180073090  mov     [rbp+57h+var_58], rcx
0x180073094  mov     rax, [rbp+57h+var_60]
0x180073098  mov     [rbp+57h+var_50], rax
0x18007309c  imul    r9d, edi, 3E8h; unsigned int
0x1800730a3  mov     r8d, 2; unsigned int
0x1800730a9  lea     rdx, [rbp+57h+var_58]; void **
0x1800730ad  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x1800730b2  mov     ebx, eax
0x1800730b4  mov     r8d, eax
0x1800730b7  lea     rdx, aWaitResultFrom_2; "Wait result from WU feature update sear"...
0x1800730be  xor     ecx, ecx
0x1800730c0  call    UnattendLogW
0x1800730c5  test    ebx, ebx
0x1800730c7  jz      short loc_180073112
0x1800730c9  cmp     ebx, r12d
0x1800730cc  jz      loc_180073169
0x1800730d2  cmp     ebx, 102h
0x1800730d8  jz      short loc_1800730FE
0x1800730da  cmp     ebx, 0FFFFFFFFh
0x1800730dd  jz      short loc_1800730F5
0x1800730df  lea     rdx, aExpeditedupdat_3; "ExpeditedUpdateWUTask unexpected waitRe"...
0x1800730e6  mov     ecx, r12d
0x1800730e9  call    UnattendLogW
0x1800730ee  mov     ebx, 8000FFFFh
0x1800730f3  jmp     short loc_180073127
0x1800730f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800730fa  mov     ebx, eax
0x1800730fc  jmp     short loc_180073127
0x1800730fe  mov     r8d, edi
0x180073101  lea     rdx, aFeatureUpdateS; "Feature update scan not complete after "...
0x180073108  mov     ecx, 2
0x18007310d  call    UnattendLogW
0x180073112  mov     rcx, [rbp+57h+var_78]
0x180073116  mov     rax, [rcx]
0x180073119  mov     rax, [rax+50h]
0x18007311d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073122  mov     ebx, 80004004h
0x180073127  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, r12b
0x18007312e  jz      short loc_180073146
0x180073130  xor     r8d, r8d
0x180073133  test    r14b, r14b
0x180073136  setnz   r8b
0x18007313a  lea     rdx, ExpeditedUpdateScan_Stop
0x180073141  call    McTemplateU0q_EventWriteTransfer
0x180073146  test    ebx, ebx
0x180073148  js      short loc_18007319E
0x18007314a  xor     ecx, ecx
0x18007314c  test    r14b, r14b
0x18007314f  jz      short loc_180073186
0x180073151  lea     rdx, aExpeditedupdat_22; "ExpeditedUpdateWUTask update Found."
0x180073158  call    UnattendLogW
0x18007315d  mov     rax, [rsi+10h]
0x180073161  mov     dword ptr [rax], 2
0x180073167  jmp     short loc_1800731CD
0x180073169  lea     r9, [rbp+57h+var_80]; bool *
0x18007316d  mov     r8, [rbp+57h+var_78]; struct ISearchJob *
0x180073171  mov     rdx, [rbp+57h+var_70]; struct IUpdateSearcher *
0x180073175  mov     rcx, [rsi+8]; this
0x180073179  call    ?OnExpeditedUpdateSearchCompleted@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdateSearcher@@PEAUISearchJob@@PEA_N@Z; ExpeditedUpdateWUTask::OnExpeditedUpdateSearchCompleted(IUpdateSearcher *,ISearchJob *,bool *)
0x18007317e  mov     ebx, eax
0x180073180  mov     r14b, [rbp+57h+var_80]
0x180073184  jmp     short loc_180073127
0x180073186  lea     rdx, aExpeditedupdat_2; "ExpeditedUpdateWUTask update not Found."
0x18007318d  call    UnattendLogW
0x180073192  mov     rax, [rsi+10h]
0x180073196  mov     dword ptr [rax], 3
0x18007319c  jmp     short loc_1800731CD
0x18007319e  cmp     ebx, 80004004h
0x1800731a4  jnz     short loc_1800731B4
0x1800731a6  lea     rdx, aExpeditedupdat_30; "ExpeditedUpdateWUTask scan canceled"
0x1800731ad  mov     ecx, 2
0x1800731b2  jmp     short loc_1800731BE
0x1800731b4  lea     rdx, aExpeditedupdat_45; "ExpeditedUpdateWUTask scan failed."
0x1800731bb  mov     ecx, r12d
0x1800731be  call    UnattendLogW
0x1800731c3  mov     rax, [rsi+10h]
0x1800731c7  mov     dword ptr [rax], 5
0x1800731cd  lea     rcx, [rbp+57h+var_78]
0x1800731d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800731d6  nop
0x1800731d7  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800731de  mov     [rbp+57h+var_68], rax
0x1800731e2  lea     rcx, [rbp+57h+var_68]
0x1800731e6  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x1800731eb  nop
0x1800731ec  lea     rcx, [rbp+57h+var_70]
0x1800731f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800731f5  mov     eax, ebx
0x1800731f7  mov     rcx, [rbp+57h+var_38]
0x1800731fb  xor     rcx, rsp; StackCookie
0x1800731fe  call    __security_check_cookie
0x180073203  add     rsp, 88h
0x18007320a  pop     r14
0x18007320c  pop     r12
0x18007320e  pop     rdi
0x18007320f  pop     rsi
0x180073210  pop     rbx
0x180073211  pop     rbp
0x180073212  retn
```
