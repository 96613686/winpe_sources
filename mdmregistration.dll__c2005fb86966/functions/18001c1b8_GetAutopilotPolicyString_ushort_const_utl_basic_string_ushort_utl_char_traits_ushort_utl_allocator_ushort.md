# GetAutopilotPolicyString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x18001c1b8`
- end: `0x18001c558`
- name: `?GetAutopilotPolicyString@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x18001a874`
- `0x18001a8f4`
- `0x18001aadc`
- `0x18001c1b8`
- `0x18001dc10`
- `0x18001e0b0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c2f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c359`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c3d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c2f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c359`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c3d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c4dd`

## string_xrefs

- `0x18001c1ff`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall GetAutopilotPolicyString(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  unsigned int v7; // ebx
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
  int v26; // [rsp+20h] [rbp-88h] BYREF
  __int64 v27; // [rsp+28h] [rbp-80h] BYREF
  _QWORD *v28; // [rsp+30h] [rbp-78h] BYREF
  HSTRING string; // [rsp+38h] [rbp-70h] BYREF
  __int64 v30; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER v31; // [rsp+48h] [rbp-60h] BYREF
  HSTRING v32; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v33[32]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v30 = a1;
  LOBYTE(v26) = 0;
  v28 = 0;
  v32 = 0;
  v3 = WindowsCreateStringReference(L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer", 0x3Cu, &v31, &v32);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18001C556LL);
  }
  v28 = 0;
  v6 = Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(v32, &v28);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v27 = 0;
    string = 0;
    v9 = v28;
    v10 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*v28 + 56LL);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &v30);
    v12 = v10(v9, *(_QWORD *)(v11 + 24), &v27);
    v15 = v12;
    if ( v12 >= 0 )
    {
      v17 = string;
      if ( string )
      {
        LastError = GetLastError();
        WindowsDeleteString(v17);
        SetLastError(LastError);
      }
      string = 0;
      v19 = v27;
      v20 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(v27, v13, v14, &v26);
      if ( v20 >= 0 )
        v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL))(v19, &string);
      if ( v20 >= 0 )
      {
        if ( (_BYTE)v26 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC27,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
            (const char *)0x800705B4LL,
            v26);
          if ( string )
            WindowsDeleteString(string);
          v22 = v27;
          if ( v27 )
          {
            v27 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v32 = 0;
          if ( v28 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
          return 2147943860LL;
        }
        else
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
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
          if ( string )
            WindowsDeleteString(string);
          v25 = v27;
          if ( v27 )
          {
            v27 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          v32 = 0;
          if ( v28 )
            (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
          return 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC26,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
          (const char *)(unsigned int)v20,
          v26);
        if ( string )
          WindowsDeleteString(string);
        v21 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v32 = 0;
        if ( v28 )
          (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
        return (unsigned int)v20;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC25,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
        (const char *)(unsigned int)v12,
        v26);
      if ( string )
        WindowsDeleteString(string);
      v16 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v32 = 0;
      if ( v28 )
        (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC20,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
      (const char *)(unsigned int)v6,
      v26);
    v32 = 0;
    if ( v28 )
      (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
    return v7;
  }
}

```

## disassembly

```asm
0x18001c1b8  mov     r11, rsp
0x18001c1bb  mov     [r11+18h], rbx
0x18001c1bf  push    rsi
0x18001c1c0  push    rdi
0x18001c1c1  push    r14
0x18001c1c3  sub     rsp, 90h
0x18001c1ca  mov     rax, cs:__security_cookie
0x18001c1d1  xor     rax, rsp
0x18001c1d4  mov     [rsp+0A8h+var_20], rax
0x18001c1dc  mov     rsi, rdx
0x18001c1df  mov     [r11-68h], rcx
0x18001c1e3  xor     r14d, r14d
0x18001c1e6  mov     byte ptr [rsp+0A8h+var_88], r14b; int
0x18001c1eb  mov     [r11-78h], r14
0x18001c1ef  mov     [r11-48h], r14
0x18001c1f3  lea     r9, [r11-48h]; string
0x18001c1f7  lea     r8, [r11-60h]; hstringHeader
0x18001c1fb  lea     edx, [r14+3Ch]; length
0x18001c1ff  lea     rcx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x18001c206  call    cs:__imp_WindowsCreateStringReference
0x18001c20d  nop     dword ptr [rax+rax+00h]
0x18001c212  test    eax, eax
0x18001c214  js      loc_18001C54F
0x18001c21a  mov     rcx, [rsp+0A8h+var_78]
0x18001c21f  mov     [rsp+0A8h+var_78], r14
0x18001c224  test    rcx, rcx
0x18001c227  jz      short loc_18001C236
0x18001c229  mov     rax, [rcx]
0x18001c22c  mov     rax, [rax+10h]
0x18001c230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c235  nop
0x18001c236  lea     rdx, [rsp+0A8h+var_78]
0x18001c23b  mov     rcx, [rsp+0A8h+var_48]
0x18001c240  call    ??$ActivateInstance@UIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(HSTRING__ *,EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil * *)
0x18001c245  mov     ebx, eax
0x18001c247  test    eax, eax
0x18001c249  jns     short loc_18001C28B
0x18001c24b  mov     rcx, [rsp+0A8h]; this
0x18001c253  mov     r9d, eax; char *
0x18001c256  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c25d  mov     edx, 0C20h; void *
0x18001c262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c267  nop
0x18001c268  mov     [rsp+0A8h+var_48], r14
0x18001c26d  mov     rcx, [rsp+0A8h+var_78]
0x18001c272  test    rcx, rcx
0x18001c275  jz      short loc_18001C284
0x18001c277  mov     rax, [rcx]
0x18001c27a  mov     rax, [rax+10h]
0x18001c27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c283  nop
0x18001c284  mov     eax, ebx
0x18001c286  jmp     loc_18001C52A
0x18001c28b  mov     [rsp+0A8h+var_80], r14
0x18001c290  mov     [rsp+0A8h+string], r14
0x18001c295  mov     rdi, [rsp+0A8h+var_78]
0x18001c29a  mov     rax, [rdi]
0x18001c29d  mov     rbx, [rax+38h]
0x18001c2a1  lea     rdx, [rsp+0A8h+var_68]
0x18001c2a6  lea     rcx, [rsp+0A8h+var_40]
0x18001c2ab  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c2b0  nop
0x18001c2b1  lea     r8, [rsp+0A8h+var_80]
0x18001c2b6  mov     rdx, [rax+18h]
0x18001c2ba  mov     rcx, rdi
0x18001c2bd  mov     rax, rbx
0x18001c2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c5  mov     ebx, eax
0x18001c2c7  test    eax, eax
0x18001c2c9  jns     short loc_18001C33E
0x18001c2cb  mov     rcx, [rsp+0A8h]; this
0x18001c2d3  mov     r9d, eax; char *
0x18001c2d6  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c2dd  mov     edx, 0C25h; void *
0x18001c2e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2e7  nop
0x18001c2e8  mov     rcx, [rsp+0A8h+string]; string
0x18001c2ed  test    rcx, rcx
0x18001c2f0  jz      short loc_18001C2FF
0x18001c2f2  call    cs:__imp_WindowsDeleteString
0x18001c2f9  nop     dword ptr [rax+rax+00h]
0x18001c2fe  nop
0x18001c2ff  mov     rcx, [rsp+0A8h+var_80]
0x18001c304  test    rcx, rcx
0x18001c307  jz      short loc_18001C31B
0x18001c309  mov     [rsp+0A8h+var_80], r14
0x18001c30e  mov     rax, [rcx]
0x18001c311  mov     rax, [rax+10h]
0x18001c315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c31a  nop
0x18001c31b  mov     [rsp+0A8h+var_48], r14
0x18001c320  mov     rcx, [rsp+0A8h+var_78]
0x18001c325  test    rcx, rcx
0x18001c328  jz      short loc_18001C337
0x18001c32a  mov     rax, [rcx]
0x18001c32d  mov     rax, [rax+10h]
0x18001c331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c336  nop
0x18001c337  mov     eax, ebx
0x18001c339  jmp     loc_18001C52A
0x18001c33e  mov     rdi, [rsp+0A8h+string]
0x18001c343  test    rdi, rdi
0x18001c346  jz      short loc_18001C373
0x18001c348  call    cs:__imp_GetLastError
0x18001c34f  nop     dword ptr [rax+rax+00h]
0x18001c354  mov     ebx, eax
0x18001c356  mov     rcx, rdi; string
0x18001c359  call    cs:__imp_WindowsDeleteString
0x18001c360  nop     dword ptr [rax+rax+00h]
0x18001c365  mov     ecx, ebx; dwErrCode
0x18001c367  call    cs:__imp_SetLastError
0x18001c36e  nop     dword ptr [rax+rax+00h]
0x18001c373  mov     [rsp+0A8h+string], r14
0x18001c378  mov     rdi, [rsp+0A8h+var_80]
0x18001c37d  lea     r9, [rsp+0A8h+var_88]
0x18001c382  mov     rcx, rdi
0x18001c385  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18001c38a  mov     ebx, eax
0x18001c38c  test    eax, eax
0x18001c38e  js      short loc_18001C3A6
0x18001c390  mov     rax, [rdi]
0x18001c393  lea     rdx, [rsp+0A8h+string]
0x18001c398  mov     rcx, rdi
0x18001c39b  mov     rax, [rax+40h]
0x18001c39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a4  mov     ebx, eax
0x18001c3a6  test    ebx, ebx
0x18001c3a8  jns     short loc_18001C41D
0x18001c3aa  mov     rcx, [rsp+0A8h]; this
0x18001c3b2  mov     r9d, ebx; char *
0x18001c3b5  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c3bc  mov     edx, 0C26h; void *
0x18001c3c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3c6  nop
0x18001c3c7  mov     rcx, [rsp+0A8h+string]; string
0x18001c3cc  test    rcx, rcx
0x18001c3cf  jz      short loc_18001C3DE
0x18001c3d1  call    cs:__imp_WindowsDeleteString
0x18001c3d8  nop     dword ptr [rax+rax+00h]
0x18001c3dd  nop
0x18001c3de  mov     rcx, [rsp+0A8h+var_80]
0x18001c3e3  test    rcx, rcx
0x18001c3e6  jz      short loc_18001C3FA
0x18001c3e8  mov     [rsp+0A8h+var_80], r14
0x18001c3ed  mov     rax, [rcx]
0x18001c3f0  mov     rax, [rax+10h]
0x18001c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f9  nop
0x18001c3fa  mov     [rsp+0A8h+var_48], r14
0x18001c3ff  mov     rcx, [rsp+0A8h+var_78]
0x18001c404  test    rcx, rcx
0x18001c407  jz      short loc_18001C416
0x18001c409  mov     rax, [rcx]
0x18001c40c  mov     rax, [rax+10h]
0x18001c410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c415  nop
0x18001c416  mov     eax, ebx
0x18001c418  jmp     loc_18001C52A
0x18001c41d  cmp     byte ptr [rsp+0A8h+var_88], r14b
0x18001c422  jz      short loc_18001C49C
0x18001c424  mov     rcx, [rsp+0A8h]; this
0x18001c42c  mov     ebx, 800705B4h
0x18001c431  mov     r9d, ebx; char *
0x18001c434  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c43b  mov     edx, 0C27h; void *
0x18001c440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c445  nop
0x18001c446  mov     rcx, [rsp+0A8h+string]; string
0x18001c44b  test    rcx, rcx
0x18001c44e  jz      short loc_18001C45D
0x18001c450  call    cs:__imp_WindowsDeleteString
0x18001c457  nop     dword ptr [rax+rax+00h]
0x18001c45c  nop
0x18001c45d  mov     rcx, [rsp+0A8h+var_80]
0x18001c462  test    rcx, rcx
0x18001c465  jz      short loc_18001C479
0x18001c467  mov     [rsp+0A8h+var_80], r14
0x18001c46c  mov     rax, [rcx]
0x18001c46f  mov     rax, [rax+10h]
0x18001c473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c478  nop
0x18001c479  mov     [rsp+0A8h+var_48], r14
0x18001c47e  mov     rcx, [rsp+0A8h+var_78]
0x18001c483  test    rcx, rcx
0x18001c486  jz      short loc_18001C495
0x18001c488  mov     rdx, [rcx]
0x18001c48b  mov     rax, [rdx+10h]
0x18001c48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c494  nop
0x18001c495  mov     eax, ebx
0x18001c497  jmp     loc_18001C52A
0x18001c49c  xor     edx, edx; length
0x18001c49e  mov     rcx, [rsp+0A8h+string]; string
0x18001c4a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c4aa  nop     dword ptr [rax+rax+00h]
0x18001c4af  test    rax, rax
0x18001c4b2  jz      short loc_18001C4C4
0x18001c4b4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c4b8  inc     r8
0x18001c4bb  cmp     [rax+r8*2], r14w
0x18001c4c0  jnz     short loc_18001C4B8
0x18001c4c2  jmp     short loc_18001C4C7
0x18001c4c4  mov     r8, r14
0x18001c4c7  mov     rdx, rax
0x18001c4ca  mov     rcx, rsi
0x18001c4cd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001c4d2  nop
0x18001c4d3  mov     rcx, [rsp+0A8h+string]; string
0x18001c4d8  test    rcx, rcx
0x18001c4db  jz      short loc_18001C4EA
0x18001c4dd  call    cs:__imp_WindowsDeleteString
0x18001c4e4  nop     dword ptr [rax+rax+00h]
0x18001c4e9  nop
0x18001c4ea  mov     rcx, [rsp+0A8h+var_80]
0x18001c4ef  test    rcx, rcx
0x18001c4f2  jz      short loc_18001C506
0x18001c4f4  mov     [rsp+0A8h+var_80], r14
0x18001c4f9  mov     rax, [rcx]
0x18001c4fc  mov     rax, [rax+10h]
0x18001c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c505  nop
0x18001c506  mov     [rsp+0A8h+var_48], r14
0x18001c50b  mov     rcx, [rsp+0A8h+var_78]
0x18001c510  test    rcx, rcx
0x18001c513  jz      short loc_18001C522
0x18001c515  mov     rax, [rcx]
0x18001c518  mov     rax, [rax+10h]
0x18001c51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c521  nop
0x18001c522  xor     eax, eax
0x18001c524  jmp     short loc_18001C52A
0x18001c526  mov     eax, dword ptr [rsp+0A8h+var_80]
0x18001c52a  mov     rcx, [rsp+0A8h+var_20]
0x18001c532  xor     rcx, rsp; StackCookie
0x18001c535  call    __security_check_cookie
0x18001c53a  mov     rbx, [rsp+0A8h+arg_10]
0x18001c542  add     rsp, 90h
0x18001c549  pop     r14
0x18001c54b  pop     rdi
0x18001c54c  pop     rsi
0x18001c54d  retn
0x18001c54f  mov     ecx, eax; this
0x18001c551  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
