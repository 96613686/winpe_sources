# CFilterProcess::Init(_GUID const &,wchar_t const *,unsigned __int64)

- ea: `0x18019ea80`
- end: `0x18019ed9a`
- name: `?Init@CFilterProcess@@QEAAJAEBU_GUID@@PEB_W_K@Z`
- size: `794`
- prototype: `__int64 __fastcall(CFilterProcess *this, const struct _GUID *, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a238`

## callees

- `0x18000e628`
- `0x18000ee18`
- `0x18000f880`
- `0x18004b638`
- `0x180067220`
- `0x18008fde0`
- `0x18009b43c`
- `0x1800a8b90`
- `0x1800be1c8`
- `0x1800faee8`
- `0x180109038`
- `0x18019e1e8`
- `0x18019ea80`
- `0x18020a8ac`

## import_xrefs

- `ntdll!NtCreateCrossVmEvent` at `0x18019eb96`
- `ntdll!NtCreateCrossVmEvent` at `0x18019ec06`
- `ntdll!NtCreateCrossVmEvent` at `0x18019ec5b`
- `ntdll!NtCreateCrossVmEvent` at `0x18019eb96`
- `ntdll!NtCreateCrossVmEvent` at `0x18019ec06`
- `ntdll!NtCreateCrossVmEvent` at `0x18019ec5b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019eb46`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019ebc9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019ec21`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019eb46`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019ebc9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019ec21`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18019eaee`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18019eaee`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CFilterProcess::Init(CFilterProcess *this, const struct _GUID *a2, const wchar_t *a3, __int64 a4)
{
  const struct _GUID *v6; // r14
  HRESULT v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  _QWORD *v10; // rbx
  HRESULT Guid; // eax
  __int64 v12; // rax
  int CrossVmEvent; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  struct IUnknown *v17; // rbx
  int v18; // eax
  unsigned int v19; // esi
  int v20; // eax
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-30h]
  int v24; // [rsp+20h] [rbp-30h]
  __int64 *v25; // [rsp+30h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-18h] BYREF
  char v27; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct IUnknown *v29; // [rsp+80h] [rbp+30h] BYREF
  __int64 v30; // [rsp+88h] [rbp+38h] BYREF

  *((_BYTE *)this + 264) = 1;
  v6 = (const struct _GUID *)((char *)this + 268);
  *(struct _GUID *)((char *)this + 268) = *a2;
  std::wstring::assign((char *)this + 320, a3);
  *((_QWORD *)this + 44) = a4;
  v30 = 0;
  v25 = &v30;
  lpsz = 0;
  v27 = 1;
  v7 = StringFromCLSID(v6, &lpsz);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v25);
  if ( v7 >= 0 )
  {
    v10 = (_QWORD *)((char *)this + 288);
    std::wstring::assign((char *)this + 288, v30 + 2);
    --*((_QWORD *)this + 38);
    if ( *((_QWORD *)this + 39) > 7u )
      v10 = (_QWORD *)*v10;
    *((_WORD *)v10 + *((_QWORD *)this + 38)) = 0;
    Guid = CoCreateGuid((GUID *)((char *)this + 360));
    v7 = Guid;
    if ( Guid < 0 )
    {
      v9 = 1437;
LABEL_7:
      v8 = (unsigned int)Guid;
      goto LABEL_8;
    }
    v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 208);
    v23 = (_DWORD)this + 360;
    CrossVmEvent = NtCreateCrossVmEvent(v12, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v14 = 1439;
LABEL_11:
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v14,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
             (const char *)(unsigned int)CrossVmEvent,
             v23);
      goto LABEL_32;
    }
    Guid = CoCreateGuid((GUID *)this + 24);
    v7 = Guid;
    if ( Guid < 0 )
    {
      v9 = 1441;
      goto LABEL_7;
    }
    v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 376);
    v23 = (_DWORD)this + 384;
    CrossVmEvent = NtCreateCrossVmEvent(v15, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v14 = 1443;
      goto LABEL_11;
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 408));
    v7 = Guid;
    if ( Guid < 0 )
    {
      v9 = 1445;
      goto LABEL_7;
    }
    v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 400);
    v23 = (_DWORD)this + 408;
    CrossVmEvent = NtCreateCrossVmEvent(v16, 2031619, 0, 0);
    if ( CrossVmEvent < 0 )
    {
      v14 = 1447;
      goto LABEL_11;
    }
    v29 = 0;
    Guid = ATL::CComObject<CFilterPipe>::CreateInstance(&v29);
    v7 = Guid;
    if ( Guid < 0 )
    {
      v9 = 1453;
      goto LABEL_7;
    }
    TComNoUnkPointer<CUMap>::TComNoUnkPointer<CUMap>(&v29, v29);
    v17 = v29;
    LOBYTE(v29[54].lpVtbl) = 1;
    TComNoUnkPointer<CPlugin>::operator=(&v17[49], this);
    v18 = CShMPipe::CreateForContainer((CShMPipe *)&v17[1], v6);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)(unsigned int)v18,
        v23);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)v19,
        v24);
      TComPointer<CGatherStore>::~TComPointer<CGatherStore>(&v29);
      v7 = v19;
      goto LABEL_32;
    }
    v17[4].lpVtbl = *(struct IUnknownVtbl **)((char *)this + 376);
    v17[3].lpVtbl = *(struct IUnknownVtbl **)((char *)this + 208);
    *((_DWORD *)this + 13) = 1;
    v20 = CUnkSList::Append((CFilterProcess *)((char *)this + 72), v17);
    v7 = v20;
    if ( v20 )
    {
      if ( v20 >= 0 )
      {
LABEL_28:
        TComPointer<CGatherStore>::~TComPointer<CGatherStore>(&v29);
        goto LABEL_32;
      }
      v21 = 1463;
    }
    else
    {
      v20 = CFilterProcess::SpawnInContainer(this);
      v7 = v20;
      if ( v20 >= 0 )
      {
        TComPointer<CGatherStore>::~TComPointer<CGatherStore>(&v29);
        v7 = 0;
        goto LABEL_32;
      }
      v21 = 1465;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
      (const char *)(unsigned int)v20,
      v23);
    goto LABEL_28;
  }
  v8 = (unsigned int)v7;
  v9 = 1433;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
    (const char *)v8,
    v23);
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18019ea80  mov     [rsp-28h+arg_10], rbx
0x18019ea85  mov     [rsp-28h+arg_18], rsi
0x18019ea8a  push    rbp
0x18019ea8b  push    rdi
0x18019ea8c  push    r12
0x18019ea8e  push    r14
0x18019ea90  push    r15
0x18019ea92  mov     rbp, rsp
0x18019ea95  sub     rsp, 50h
0x18019ea99  mov     rbx, r9
0x18019ea9c  mov     rdi, rcx
0x18019ea9f  mov     byte ptr [rcx+108h], 1
0x18019eaa6  lea     r14, [rcx+10Ch]
0x18019eaad  movups  xmm0, xmmword ptr [rdx]
0x18019eab0  movdqu  xmmword ptr [r14], xmm0
0x18019eab5  add     rcx, 140h
0x18019eabc  mov     rdx, r8
0x18019eabf  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18019eac4  mov     [rdi+160h], rbx
0x18019eacb  mov     [rbp+arg_8], 0
0x18019ead3  lea     rax, [rbp+arg_8]
0x18019ead7  mov     [rbp+var_20], rax
0x18019eadb  mov     [rbp+lpsz], 0
0x18019eae3  mov     [rbp+var_10], 1
0x18019eae7  lea     rdx, [rbp+lpsz]; lplpsz
0x18019eaeb  mov     rcx, r14; rclsid
0x18019eaee  call    cs:__imp_StringFromCLSID
0x18019eaf4  mov     ebx, eax
0x18019eaf6  lea     rcx, [rbp+var_20]
0x18019eafa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x18019eaff  test    ebx, ebx
0x18019eb01  jns     short loc_18019EB0D
0x18019eb03  mov     r9d, ebx
0x18019eb06  mov     edx, 599h
0x18019eb0b  jmp     short loc_18019EB5A
0x18019eb0d  lea     rbx, [rdi+120h]
0x18019eb14  mov     rdx, [rbp+arg_8]
0x18019eb18  add     rdx, 2
0x18019eb1c  mov     rcx, rbx
0x18019eb1f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18019eb24  dec     qword ptr [rbx+10h]
0x18019eb28  mov     rcx, [rbx+10h]
0x18019eb2c  cmp     qword ptr [rbx+18h], 7
0x18019eb31  jbe     short loc_18019EB36
0x18019eb33  mov     rbx, [rbx]
0x18019eb36  xor     eax, eax
0x18019eb38  mov     [rbx+rcx*2], ax
0x18019eb3c  lea     rsi, [rdi+168h]
0x18019eb43  mov     rcx, rsi; pguid
0x18019eb46  call    cs:__imp_CoCreateGuid
0x18019eb4c  mov     ebx, eax
0x18019eb4e  test    eax, eax
0x18019eb50  jns     short loc_18019EB6F
0x18019eb52  mov     edx, 59Dh; void *
0x18019eb57  mov     r9d, eax; char *
0x18019eb5a  mov     rcx, [rbp+28h]; this
0x18019eb5e  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019eb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019eb6a  jmp     loc_18019ED76
0x18019eb6f  lea     r12, [rdi+0D0h]
0x18019eb76  mov     rcx, r12
0x18019eb79  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18019eb7e  mov     [rsp+50h+var_28], r14
0x18019eb83  mov     qword ptr [rsp+50h+var_30], rsi; int
0x18019eb88  xor     r9d, r9d
0x18019eb8b  xor     r8d, r8d
0x18019eb8e  mov     edx, 1F0003h
0x18019eb93  mov     rcx, rax
0x18019eb96  call    cs:__imp_NtCreateCrossVmEvent
0x18019eb9c  test    eax, eax
0x18019eb9e  jns     short loc_18019EBBF
0x18019eba0  mov     edx, 59Fh; void *
0x18019eba5  mov     rcx, [rbp+28h]; this
0x18019eba9  mov     r9d, eax; char *
0x18019ebac  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019ebb3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18019ebb8  mov     ebx, eax
0x18019ebba  jmp     loc_18019ED76
0x18019ebbf  lea     rsi, [rdi+180h]
0x18019ebc6  mov     rcx, rsi; pguid
0x18019ebc9  call    cs:__imp_CoCreateGuid
0x18019ebcf  mov     ebx, eax
0x18019ebd1  test    eax, eax
0x18019ebd3  jns     short loc_18019EBDF
0x18019ebd5  mov     edx, 5A1h
0x18019ebda  jmp     loc_18019EB57
0x18019ebdf  lea     r15, [rdi+178h]
0x18019ebe6  mov     rcx, r15
0x18019ebe9  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18019ebee  mov     [rsp+50h+var_28], r14
0x18019ebf3  mov     qword ptr [rsp+50h+var_30], rsi
0x18019ebf8  xor     r9d, r9d
0x18019ebfb  xor     r8d, r8d
0x18019ebfe  mov     edx, 1F0003h
0x18019ec03  mov     rcx, rax
0x18019ec06  call    cs:__imp_NtCreateCrossVmEvent
0x18019ec0c  test    eax, eax
0x18019ec0e  jns     short loc_18019EC17
0x18019ec10  mov     edx, 5A3h
0x18019ec15  jmp     short loc_18019EBA5
0x18019ec17  lea     rsi, [rdi+198h]
0x18019ec1e  mov     rcx, rsi; pguid
0x18019ec21  call    cs:__imp_CoCreateGuid
0x18019ec27  mov     ebx, eax
0x18019ec29  test    eax, eax
0x18019ec2b  jns     short loc_18019EC37
0x18019ec2d  mov     edx, 5A5h
0x18019ec32  jmp     loc_18019EB57
0x18019ec37  lea     rcx, [rdi+190h]
0x18019ec3e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18019ec43  mov     [rsp+50h+var_28], r14
0x18019ec48  mov     qword ptr [rsp+50h+var_30], rsi; int
0x18019ec4d  xor     r9d, r9d
0x18019ec50  xor     r8d, r8d
0x18019ec53  mov     edx, 1F0003h
0x18019ec58  mov     rcx, rax
0x18019ec5b  call    cs:__imp_NtCreateCrossVmEvent
0x18019ec61  test    eax, eax
0x18019ec63  jns     short loc_18019EC6F
0x18019ec65  mov     edx, 5A7h
0x18019ec6a  jmp     loc_18019EBA5
0x18019ec6f  mov     [rbp+arg_0], 0
0x18019ec77  lea     rcx, [rbp+arg_0]
0x18019ec7b  call    ?CreateInstance@?$CComObject@VCFilterPipe@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterPipe>::CreateInstance(ATL::CComObject<CFilterPipe> * *)
0x18019ec80  mov     ebx, eax
0x18019ec82  test    eax, eax
0x18019ec84  jns     short loc_18019EC90
0x18019ec86  mov     edx, 5ADh
0x18019ec8b  jmp     loc_18019EB57
0x18019ec90  mov     rdx, [rbp+arg_0]
0x18019ec94  lea     rcx, [rbp+arg_0]
0x18019ec98  call    ??0?$TComNoUnkPointer@VCUMap@@@@QEAA@PEAVCUMap@@@Z; TComNoUnkPointer<CUMap>::TComNoUnkPointer<CUMap>(CUMap *)
0x18019ec9d  nop
0x18019ec9e  mov     rbx, [rbp+arg_0]
0x18019eca2  mov     byte ptr [rbx+1B0h], 1
0x18019eca9  lea     rcx, [rbx+188h]
0x18019ecb0  mov     rdx, rdi
0x18019ecb3  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x18019ecb8  lea     rcx, [rbx+8]; this
0x18019ecbc  mov     rdx, r14; struct _GUID *
0x18019ecbf  call    ?CreateForContainer@CShMPipe@@QEAAJAEBU_GUID@@@Z; CShMPipe::CreateForContainer(_GUID const &)
0x18019ecc4  mov     esi, eax
0x18019ecc6  test    eax, eax
0x18019ecc8  jns     short loc_18019ED08
0x18019ecca  mov     rcx, [rbp+28h]; this
0x18019ecce  mov     r9d, eax; char *
0x18019ecd1  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019ecd8  mov     edx, 1C2h; void *
0x18019ecdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ece2  mov     rcx, [rbp+28h]; this
0x18019ece6  mov     r9d, esi; char *
0x18019ece9  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019ecf0  mov     edx, 5B0h; void *
0x18019ecf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ecfa  nop
0x18019ecfb  lea     rcx, [rbp+arg_0]
0x18019ecff  call    ??1?$TComPointer@VCGatherStore@@@@QEAA@XZ; TComPointer<CGatherStore>::~TComPointer<CGatherStore>(void)
0x18019ed04  mov     ebx, esi
0x18019ed06  jmp     short loc_18019ED76
0x18019ed08  mov     rax, [r15]
0x18019ed0b  mov     [rbx+20h], rax
0x18019ed0f  mov     rax, [r12]
0x18019ed13  mov     [rbx+18h], rax
0x18019ed17  mov     dword ptr [rdi+34h], 1
0x18019ed1e  lea     rcx, [rdi+48h]; this
0x18019ed22  mov     rdx, rbx; struct IUnknown *
0x18019ed25  call    ?Append@CUnkSList@@QEAAJPEAUIUnknown@@@Z; CUnkSList::Append(IUnknown *)
0x18019ed2a  mov     ebx, eax
0x18019ed2c  test    eax, eax
0x18019ed2e  jz      short loc_18019ED56
0x18019ed30  jns     short loc_18019ED4B
0x18019ed32  mov     edx, 5B7h; void *
0x18019ed37  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019ed3e  mov     r9d, eax; char *
0x18019ed41  mov     rcx, [rbp+28h]; this
0x18019ed45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ed4a  nop
0x18019ed4b  lea     rcx, [rbp+arg_0]
0x18019ed4f  call    ??1?$TComPointer@VCGatherStore@@@@QEAA@XZ; TComPointer<CGatherStore>::~TComPointer<CGatherStore>(void)
0x18019ed54  jmp     short loc_18019ED76
0x18019ed56  mov     rcx, rdi; this
0x18019ed59  call    ?SpawnInContainer@CFilterProcess@@QEAAJXZ; CFilterProcess::SpawnInContainer(void)
0x18019ed5e  mov     ebx, eax
0x18019ed60  test    eax, eax
0x18019ed62  jns     short loc_18019ED6B
0x18019ed64  mov     edx, 5B9h
0x18019ed69  jmp     short loc_18019ED37
0x18019ed6b  lea     rcx, [rbp+arg_0]
0x18019ed6f  call    ??1?$TComPointer@VCGatherStore@@@@QEAA@XZ; TComPointer<CGatherStore>::~TComPointer<CGatherStore>(void)
0x18019ed74  xor     ebx, ebx
0x18019ed76  lea     rcx, [rbp+arg_8]
0x18019ed7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019ed7f  mov     eax, ebx
0x18019ed81  lea     r11, [rsp+50h+var_s0]
0x18019ed86  mov     rbx, [r11+40h]
0x18019ed8a  mov     rsi, [r11+48h]
0x18019ed8e  mov     rsp, r11
0x18019ed91  pop     r15
0x18019ed93  pop     r14
0x18019ed95  pop     r12
0x18019ed97  pop     rdi
0x18019ed98  pop     rbp
0x18019ed99  retn
```
