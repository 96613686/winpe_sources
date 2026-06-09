# GetAutopilotSettingValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001c560`
- end: `0x18001c93c`
- name: `?GetAutopilotSettingValue@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x18001a874`
- `0x18001a8f4`
- `0x18001aadc`
- `0x18001c560`
- `0x18001dc10`
- `0x18001df00`
- `0x18001e0b0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c733`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c752`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c6dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c83b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c8c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c6dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c83b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c8c8`

## string_xrefs

- `0x18001c5e7`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall GetAutopilotSettingValue(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rdi
  __int64 (__fastcall *v10)(_QWORD *, _QWORD, __int64 *); // rbx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // ebx
  __int64 v16; // rcx
  HSTRING v17; // rdi
  DWORD LastError; // ebx
  __int64 v19; // rdi
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+28h] [rbp-A0h] BYREF
  _QWORD *v28; // [rsp+30h] [rbp-98h] BYREF
  HSTRING v29; // [rsp+38h] [rbp-90h] BYREF
  const wchar_t *v30; // [rsp+40h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-78h] BYREF
  HSTRING string; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v33[32]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v30 = L"CloudAssignedDeviceAssociationTag";
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v26) = 0;
    v28 = 0;
    string = 0;
    v4 = WindowsCreateStringReference(
           L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer",
           0x3Cu,
           &hstringHeader,
           &string);
    if ( v4 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
      JUMPOUT(0x18001C93ALL);
    }
    v28 = 0;
    v7 = Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(
           string,
           &v28);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v27 = 0;
      v29 = 0;
      v9 = v28;
      v10 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*v28 + 336LL);
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &v30);
      v12 = v10(v9, *(_QWORD *)(v11 + 24), &v27);
      v15 = v12;
      if ( v12 >= 0 )
      {
        v17 = v29;
        if ( v29 )
        {
          LastError = GetLastError();
          WindowsDeleteString(v17);
          SetLastError(LastError);
        }
        v29 = 0;
        v19 = v27;
        v20 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(v27, v13, v14, &v26);
        if ( v20 >= 0 )
          v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL))(v19, &v29);
        if ( v20 >= 0 )
        {
          if ( (_BYTE)v26 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC43,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
              (const char *)0x800705B4LL,
              v26);
            if ( v29 )
              WindowsDeleteString(v29);
            v22 = v27;
            if ( v27 )
            {
              v27 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            string = 0;
            if ( v28 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
            return 2147943860LL;
          }
          else
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
            if ( StringRawBuffer )
            {
              v24 = -1;
              do
                ++v24;
              while ( StringRawBuffer[v24] );
            }
            else
            {
              v24 = 0;
            }
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              a2,
              StringRawBuffer,
              v24);
            if ( v29 )
              WindowsDeleteString(v29);
            v25 = v27;
            if ( v27 )
            {
              v27 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
            string = 0;
            if ( v28 )
              (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
            return 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC41,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
            (const char *)(unsigned int)v20,
            v26);
          if ( v29 )
            WindowsDeleteString(v29);
          v21 = v27;
          if ( v27 )
          {
            v27 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          string = 0;
          if ( v28 )
            (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
          return (unsigned int)v20;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
          (const char *)(unsigned int)v12,
          v26);
        if ( v29 )
          WindowsDeleteString(v29);
        v16 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        string = 0;
        if ( v28 )
          (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
        (const char *)(unsigned int)v7,
        v26);
      string = 0;
      if ( v28 )
        (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC31,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
      (const char *)0x80004001LL,
      v26);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18001c560  push    rbx
0x18001c562  push    rsi
0x18001c563  push    rdi
0x18001c564  push    r14
0x18001c566  sub     rsp, 0A8h
0x18001c56d  mov     rax, cs:__security_cookie
0x18001c574  xor     rax, rsp
0x18001c577  mov     [rsp+0C8h+var_38], rax
0x18001c57f  mov     rsi, rdx
0x18001c582  lea     rax, aCloudassignedd; "CloudAssignedDeviceAssociationTag"
0x18001c589  mov     [rsp+0C8h+var_88], rax
0x18001c58e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18001c595  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18001c59a  xor     r14d, r14d
0x18001c59d  test    al, al
0x18001c59f  jnz     short loc_18001C5C9
0x18001c5a1  mov     rcx, [rsp+0C8h]; this
0x18001c5a9  mov     ebx, 80004001h
0x18001c5ae  mov     r9d, ebx; char *
0x18001c5b1  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c5b8  mov     edx, 0C31h; void *
0x18001c5bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5c2  mov     eax, ebx
0x18001c5c4  jmp     loc_18001C915
0x18001c5c9  mov     byte ptr [rsp+0C8h+var_A8], r14b; int
0x18001c5ce  mov     [rsp+0C8h+var_98], r14
0x18001c5d3  mov     [rsp+0C8h+string], r14
0x18001c5d8  lea     r9, [rsp+0C8h+string]; string
0x18001c5dd  lea     r8, [rsp+0C8h+hstringHeader]; hstringHeader
0x18001c5e2  mov     edx, 3Ch ; '<'; length
0x18001c5e7  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x18001c5ee  call    cs:__imp_WindowsCreateStringReference
0x18001c5f5  nop     dword ptr [rax+rax+00h]
0x18001c5fa  test    eax, eax
0x18001c5fc  js      loc_18001C933
0x18001c602  mov     rcx, [rsp+0C8h+var_98]
0x18001c607  mov     [rsp+0C8h+var_98], r14
0x18001c60c  test    rcx, rcx
0x18001c60f  jz      short loc_18001C61E
0x18001c611  mov     rax, [rcx]
0x18001c614  mov     rax, [rax+10h]
0x18001c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c61d  nop
0x18001c61e  lea     rdx, [rsp+0C8h+var_98]
0x18001c623  mov     rcx, [rsp+0C8h+string]
0x18001c628  call    ??$ActivateInstance@UIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(HSTRING__ *,EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil * *)
0x18001c62d  mov     ebx, eax
0x18001c62f  test    eax, eax
0x18001c631  jns     short loc_18001C673
0x18001c633  mov     rcx, [rsp+0C8h]; this
0x18001c63b  mov     r9d, eax; char *
0x18001c63e  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c645  mov     edx, 0C38h; void *
0x18001c64a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c64f  nop
0x18001c650  mov     [rsp+0C8h+string], r14
0x18001c655  mov     rcx, [rsp+0C8h+var_98]
0x18001c65a  test    rcx, rcx
0x18001c65d  jz      short loc_18001C66C
0x18001c65f  mov     rax, [rcx]
0x18001c662  mov     rax, [rax+10h]
0x18001c666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c66b  nop
0x18001c66c  mov     eax, ebx
0x18001c66e  jmp     loc_18001C915
0x18001c673  mov     [rsp+0C8h+var_A0], r14
0x18001c678  mov     [rsp+0C8h+var_90], r14
0x18001c67d  mov     rdi, [rsp+0C8h+var_98]
0x18001c682  mov     rax, [rdi]
0x18001c685  mov     rbx, [rax+150h]
0x18001c68c  lea     rdx, [rsp+0C8h+var_88]
0x18001c691  lea     rcx, [rsp+0C8h+var_58]
0x18001c696  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c69b  nop
0x18001c69c  lea     r8, [rsp+0C8h+var_A0]
0x18001c6a1  mov     rdx, [rax+18h]
0x18001c6a5  mov     rcx, rdi
0x18001c6a8  mov     rax, rbx
0x18001c6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b0  mov     ebx, eax
0x18001c6b2  test    eax, eax
0x18001c6b4  jns     short loc_18001C729
0x18001c6b6  mov     rcx, [rsp+0C8h]; this
0x18001c6be  mov     r9d, eax; char *
0x18001c6c1  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c6c8  mov     edx, 0C3Fh; void *
0x18001c6cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6d2  nop
0x18001c6d3  mov     rcx, [rsp+0C8h+var_90]; string
0x18001c6d8  test    rcx, rcx
0x18001c6db  jz      short loc_18001C6EA
0x18001c6dd  call    cs:__imp_WindowsDeleteString
0x18001c6e4  nop     dword ptr [rax+rax+00h]
0x18001c6e9  nop
0x18001c6ea  mov     rcx, [rsp+0C8h+var_A0]
0x18001c6ef  test    rcx, rcx
0x18001c6f2  jz      short loc_18001C706
0x18001c6f4  mov     [rsp+0C8h+var_A0], r14
0x18001c6f9  mov     rax, [rcx]
0x18001c6fc  mov     rax, [rax+10h]
0x18001c700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c705  nop
0x18001c706  mov     [rsp+0C8h+string], r14
0x18001c70b  mov     rcx, [rsp+0C8h+var_98]
0x18001c710  test    rcx, rcx
0x18001c713  jz      short loc_18001C722
0x18001c715  mov     rax, [rcx]
0x18001c718  mov     rax, [rax+10h]
0x18001c71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c721  nop
0x18001c722  mov     eax, ebx
0x18001c724  jmp     loc_18001C915
0x18001c729  mov     rdi, [rsp+0C8h+var_90]
0x18001c72e  test    rdi, rdi
0x18001c731  jz      short loc_18001C75E
0x18001c733  call    cs:__imp_GetLastError
0x18001c73a  nop     dword ptr [rax+rax+00h]
0x18001c73f  mov     ebx, eax
0x18001c741  mov     rcx, rdi; string
0x18001c744  call    cs:__imp_WindowsDeleteString
0x18001c74b  nop     dword ptr [rax+rax+00h]
0x18001c750  mov     ecx, ebx; dwErrCode
0x18001c752  call    cs:__imp_SetLastError
0x18001c759  nop     dword ptr [rax+rax+00h]
0x18001c75e  mov     [rsp+0C8h+var_90], r14
0x18001c763  mov     rdi, [rsp+0C8h+var_A0]
0x18001c768  lea     r9, [rsp+0C8h+var_A8]
0x18001c76d  mov     rcx, rdi
0x18001c770  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18001c775  mov     ebx, eax
0x18001c777  test    eax, eax
0x18001c779  js      short loc_18001C791
0x18001c77b  mov     rax, [rdi]
0x18001c77e  lea     rdx, [rsp+0C8h+var_90]
0x18001c783  mov     rcx, rdi
0x18001c786  mov     rax, [rax+40h]
0x18001c78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c78f  mov     ebx, eax
0x18001c791  test    ebx, ebx
0x18001c793  jns     short loc_18001C808
0x18001c795  mov     rcx, [rsp+0C8h]; this
0x18001c79d  mov     r9d, ebx; char *
0x18001c7a0  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c7a7  mov     edx, 0C41h; void *
0x18001c7ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7b1  nop
0x18001c7b2  mov     rcx, [rsp+0C8h+var_90]; string
0x18001c7b7  test    rcx, rcx
0x18001c7ba  jz      short loc_18001C7C9
0x18001c7bc  call    cs:__imp_WindowsDeleteString
0x18001c7c3  nop     dword ptr [rax+rax+00h]
0x18001c7c8  nop
0x18001c7c9  mov     rcx, [rsp+0C8h+var_A0]
0x18001c7ce  test    rcx, rcx
0x18001c7d1  jz      short loc_18001C7E5
0x18001c7d3  mov     [rsp+0C8h+var_A0], r14
0x18001c7d8  mov     rax, [rcx]
0x18001c7db  mov     rax, [rax+10h]
0x18001c7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e4  nop
0x18001c7e5  mov     [rsp+0C8h+string], r14
0x18001c7ea  mov     rcx, [rsp+0C8h+var_98]
0x18001c7ef  test    rcx, rcx
0x18001c7f2  jz      short loc_18001C801
0x18001c7f4  mov     rax, [rcx]
0x18001c7f7  mov     rax, [rax+10h]
0x18001c7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c800  nop
0x18001c801  mov     eax, ebx
0x18001c803  jmp     loc_18001C915
0x18001c808  cmp     byte ptr [rsp+0C8h+var_A8], r14b
0x18001c80d  jz      short loc_18001C887
0x18001c80f  mov     rcx, [rsp+0C8h]; this
0x18001c817  mov     ebx, 800705B4h
0x18001c81c  mov     r9d, ebx; char *
0x18001c81f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c826  mov     edx, 0C43h; void *
0x18001c82b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c830  nop
0x18001c831  mov     rcx, [rsp+0C8h+var_90]; string
0x18001c836  test    rcx, rcx
0x18001c839  jz      short loc_18001C848
0x18001c83b  call    cs:__imp_WindowsDeleteString
0x18001c842  nop     dword ptr [rax+rax+00h]
0x18001c847  nop
0x18001c848  mov     rcx, [rsp+0C8h+var_A0]
0x18001c84d  test    rcx, rcx
0x18001c850  jz      short loc_18001C864
0x18001c852  mov     [rsp+0C8h+var_A0], r14
0x18001c857  mov     rax, [rcx]
0x18001c85a  mov     rax, [rax+10h]
0x18001c85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c863  nop
0x18001c864  mov     [rsp+0C8h+string], r14
0x18001c869  mov     rcx, [rsp+0C8h+var_98]
0x18001c86e  test    rcx, rcx
0x18001c871  jz      short loc_18001C880
0x18001c873  mov     rdx, [rcx]
0x18001c876  mov     rax, [rdx+10h]
0x18001c87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c87f  nop
0x18001c880  mov     eax, ebx
0x18001c882  jmp     loc_18001C915
0x18001c887  xor     edx, edx; length
0x18001c889  mov     rcx, [rsp+0C8h+var_90]; string
0x18001c88e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c895  nop     dword ptr [rax+rax+00h]
0x18001c89a  test    rax, rax
0x18001c89d  jz      short loc_18001C8AF
0x18001c89f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c8a3  inc     r8
0x18001c8a6  cmp     [rax+r8*2], r14w
0x18001c8ab  jnz     short loc_18001C8A3
0x18001c8ad  jmp     short loc_18001C8B2
0x18001c8af  mov     r8, r14
0x18001c8b2  mov     rdx, rax
0x18001c8b5  mov     rcx, rsi
0x18001c8b8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001c8bd  nop
0x18001c8be  mov     rcx, [rsp+0C8h+var_90]; string
0x18001c8c3  test    rcx, rcx
0x18001c8c6  jz      short loc_18001C8D5
0x18001c8c8  call    cs:__imp_WindowsDeleteString
0x18001c8cf  nop     dword ptr [rax+rax+00h]
0x18001c8d4  nop
0x18001c8d5  mov     rcx, [rsp+0C8h+var_A0]
0x18001c8da  test    rcx, rcx
0x18001c8dd  jz      short loc_18001C8F1
0x18001c8df  mov     [rsp+0C8h+var_A0], r14
0x18001c8e4  mov     rax, [rcx]
0x18001c8e7  mov     rax, [rax+10h]
0x18001c8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8f0  nop
0x18001c8f1  mov     [rsp+0C8h+string], r14
0x18001c8f6  mov     rcx, [rsp+0C8h+var_98]
0x18001c8fb  test    rcx, rcx
0x18001c8fe  jz      short loc_18001C90D
0x18001c900  mov     rax, [rcx]
0x18001c903  mov     rax, [rax+10h]
0x18001c907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90c  nop
0x18001c90d  xor     eax, eax
0x18001c90f  jmp     short loc_18001C915
0x18001c911  mov     eax, dword ptr [rsp+0C8h+var_A0]
0x18001c915  mov     rcx, [rsp+0C8h+var_38]
0x18001c91d  xor     rcx, rsp; StackCookie
0x18001c920  call    __security_check_cookie
0x18001c925  add     rsp, 0A8h
0x18001c92c  pop     r14
0x18001c92e  pop     rdi
0x18001c92f  pop     rsi
0x18001c930  pop     rbx
0x18001c931  retn
0x18001c933  mov     ecx, eax; this
0x18001c935  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
