# NetworkCompliance::_VerifyAppCapability

- ea: `0x1800c5fd8`
- end: `0x1800c637a`
- name: `NetworkCompliance::_VerifyAppCapability`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c6380`

## callees

- `0x180008b1c`
- `0x18000933c`
- `0x18009c2f0`
- `0x18009c368`
- `0x1800c5fd8`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c61d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c61d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6335`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c6135`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800c6135`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800c601d`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800c601d`
- `RPCRT4!I_RpcGetCurrentCallHandle` at `0x1800c600a`
- `RPCRT4!I_RpcGetCurrentCallHandle` at `0x1800c600a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c6080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c6080`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c60be`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c60be`

## string_xrefs

- `0x1800c6032`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c60d5`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c617c`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c620e`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c628b`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c6079`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall NetworkCompliance::_VerifyAppCapability(const WCHAR *a1)
{
  RPC_BINDING_HANDLE v1; // rax
  unsigned int v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rbx
  __int64 v9; // rcx
  int ActivationFactory; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, PVOID, _QWORD); // rsi
  DWORD ProcessId; // edi
  unsigned int v16; // r8d
  HSTRING_HEADER *v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // [rsp+20h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+48h] [rbp-40h] BYREF
  const WCHAR *v33; // [rsp+50h] [rbp-38h] BYREF
  __int64 v34; // [rsp+58h] [rbp-30h] BYREF
  int v35[2]; // [rsp+60h] [rbp-28h] BYREF
  int v36; // [rsp+68h] [rbp-20h] BYREF
  void *ClientProcess; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v33 = a1;
  ClientProcess = 0;
  v1 = I_RpcGetCurrentCallHandle();
  v2 = I_RpcOpenClientProcess(v1, 0x1000u, &ClientProcess);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x48,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
           (const char *)v2,
           v30);
    if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ClientProcess);
    return v3;
  }
  else
  {
    v34 = 0;
    string = 0;
    v5 = WindowsCreateStringReference(
           L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability",
           0x40u,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
      JUMPOUT(0x1800C6378LL);
    }
    v8 = string;
    v9 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    ActivationFactory = RoGetActivationFactory(v8, &GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22, &v34);
    v11 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      *(_QWORD *)v35 = 0;
      v13 = v34;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, PVOID, _QWORD))(*(_QWORD *)v34 + 72LL);
      ProcessId = GetProcessId(ClientProcess);
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v33, v16);
      v18 = v14(v13, 0, v17[1].Reserved.Reserved1, ProcessId);
      v19 = v18;
      if ( v18 >= 0 )
      {
        v36 = 0;
        v22 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v35 + 72LL))(*(_QWORD *)v35, &v36);
        v23 = v22;
        if ( v22 >= 0 )
        {
          if ( v36 == 4 )
          {
            v28 = *(_QWORD *)v35;
            if ( *(_QWORD *)v35 )
            {
              *(_QWORD *)v35 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            v29 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(ClientProcess);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x57,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
              (const char *)0x80D0201ELL,
              (int)v35);
            v26 = *(_QWORD *)v35;
            if ( *(_QWORD *)v35 )
            {
              *(_QWORD *)v35 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            }
            v27 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(ClientProcess);
            return 2161123358LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
            (const char *)(unsigned int)v22,
            (int)v35);
          v24 = *(_QWORD *)v35;
          if ( *(_QWORD *)v35 )
          {
            *(_QWORD *)v35 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          v25 = v34;
          if ( v34 )
          {
            v34 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(ClientProcess);
          return v23;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
          (const char *)(unsigned int)v18,
          (int)v35);
        v20 = *(_QWORD *)v35;
        if ( *(_QWORD *)v35 )
        {
          *(_QWORD *)v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(ClientProcess);
        return v19;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v30);
      v12 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      if ( (char *)ClientProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(ClientProcess);
      return v11;
    }
  }
}

```

## disassembly

```asm
0x1800c5fd8  mov     r11, rsp
0x1800c5fdb  mov     [r11+10h], rbx
0x1800c5fdf  mov     [r11+18h], rsi
0x1800c5fe3  mov     [r11+20h], rdi
0x1800c5fe7  push    r14
0x1800c5fe9  sub     rsp, 80h
0x1800c5ff0  mov     rax, cs:__security_cookie
0x1800c5ff7  xor     rax, rsp
0x1800c5ffa  mov     [rsp+88h+var_10], rax
0x1800c5fff  mov     [r11-38h], rcx
0x1800c6003  xor     r14d, r14d
0x1800c6006  mov     [r11-18h], r14
0x1800c600a  call    cs:__imp_I_RpcGetCurrentCallHandle
0x1800c6010  lea     r8, [rsp+88h+ClientProcess]; ClientProcess
0x1800c6015  mov     edx, 1000h; DesiredAccess
0x1800c601a  mov     rcx, rax; Binding
0x1800c601d  call    cs:__imp_I_RpcOpenClientProcess
0x1800c6023  test    eax, eax
0x1800c6025  jz      short loc_1800C6060
0x1800c6027  mov     rcx, [rsp+88h]; this
0x1800c602f  mov     r9d, eax; char *
0x1800c6032  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6039  lea     edx, [r14+48h]; void *
0x1800c603d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c6042  mov     ebx, eax
0x1800c6044  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c6049  lea     rdx, [rcx-1]
0x1800c604d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800c6051  ja      short loc_1800C6059
0x1800c6053  call    cs:__imp_CloseHandle
0x1800c6059  mov     eax, ebx
0x1800c605b  jmp     loc_1800C634A
0x1800c6060  mov     [rsp+88h+var_30], r14
0x1800c6065  mov     [rsp+88h+string], r14
0x1800c606a  lea     r9, [rsp+88h+string]; string
0x1800c606f  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x1800c6074  mov     edx, 40h ; '@'; length
0x1800c6079  lea     rcx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QB_WB; "Windows.Security.Authorization.AppCapab"...
0x1800c6080  call    cs:__imp_WindowsCreateStringReference
0x1800c6086  test    eax, eax
0x1800c6088  js      loc_1800C6371
0x1800c608e  mov     rbx, [rsp+88h+string]
0x1800c6093  mov     rcx, [rsp+88h+var_30]
0x1800c6098  test    rcx, rcx
0x1800c609b  jz      short loc_1800C60AF
0x1800c609d  mov     [rsp+88h+var_30], r14
0x1800c60a2  mov     rax, [rcx]
0x1800c60a5  mov     rax, [rax+10h]
0x1800c60a9  call    _guard_dispatch_icall
0x1800c60ae  nop
0x1800c60af  lea     r8, [rsp+88h+var_30]
0x1800c60b4  lea     rdx, _GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x1800c60bb  mov     rcx, rbx
0x1800c60be  call    cs:__imp_RoGetActivationFactory
0x1800c60c4  mov     ebx, eax
0x1800c60c6  test    eax, eax
0x1800c60c8  jns     short loc_1800C611F
0x1800c60ca  mov     rcx, [rsp+88h]; this
0x1800c60d2  mov     r9d, eax; char *
0x1800c60d5  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c60dc  mov     edx, 4Dh ; 'M'; void *
0x1800c60e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c60e6  nop
0x1800c60e7  mov     rcx, [rsp+88h+var_30]
0x1800c60ec  test    rcx, rcx
0x1800c60ef  jz      short loc_1800C6103
0x1800c60f1  mov     [rsp+88h+var_30], r14
0x1800c60f6  mov     rax, [rcx]
0x1800c60f9  mov     rax, [rax+10h]
0x1800c60fd  call    _guard_dispatch_icall
0x1800c6102  nop
0x1800c6103  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c6108  lea     rax, [rcx-1]
0x1800c610c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c6110  ja      short loc_1800C6118
0x1800c6112  call    cs:__imp_CloseHandle
0x1800c6118  mov     eax, ebx
0x1800c611a  jmp     loc_1800C634A
0x1800c611f  mov     qword ptr [rsp+88h+var_28], r14
0x1800c6124  mov     rbx, [rsp+88h+var_30]
0x1800c6129  mov     rax, [rbx]
0x1800c612c  mov     rsi, [rax+48h]
0x1800c6130  mov     rcx, [rsp+88h+ClientProcess]; Process
0x1800c6135  call    cs:__imp_GetProcessId
0x1800c613b  mov     edi, eax
0x1800c613d  lea     rdx, [rsp+88h+var_38]
0x1800c6142  lea     rcx, [rsp+88h+hstringHeader]
0x1800c6147  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800c614c  nop
0x1800c614d  lea     rcx, [rsp+88h+var_28]
0x1800c6152  mov     qword ptr [rsp+88h+var_68], rcx; int
0x1800c6157  mov     r9d, edi
0x1800c615a  mov     r8, [rax+18h]
0x1800c615e  xor     edx, edx
0x1800c6160  mov     rcx, rbx
0x1800c6163  mov     rax, rsi
0x1800c6166  call    _guard_dispatch_icall
0x1800c616b  mov     ebx, eax
0x1800c616d  test    eax, eax
0x1800c616f  jns     short loc_1800C61E2
0x1800c6171  mov     rcx, [rsp+88h]; this
0x1800c6179  mov     r9d, eax; char *
0x1800c617c  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6183  mov     edx, 51h ; 'Q'; void *
0x1800c6188  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c618d  nop
0x1800c618e  mov     rcx, qword ptr [rsp+88h+var_28]
0x1800c6193  test    rcx, rcx
0x1800c6196  jz      short loc_1800C61AA
0x1800c6198  mov     qword ptr [rsp+88h+var_28], r14
0x1800c619d  mov     rax, [rcx]
0x1800c61a0  mov     rax, [rax+10h]
0x1800c61a4  call    _guard_dispatch_icall
0x1800c61a9  nop
0x1800c61aa  mov     rcx, [rsp+88h+var_30]
0x1800c61af  test    rcx, rcx
0x1800c61b2  jz      short loc_1800C61C6
0x1800c61b4  mov     [rsp+88h+var_30], r14
0x1800c61b9  mov     rax, [rcx]
0x1800c61bc  mov     rax, [rax+10h]
0x1800c61c0  call    _guard_dispatch_icall
0x1800c61c5  nop
0x1800c61c6  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c61cb  lea     rax, [rcx-1]
0x1800c61cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c61d3  ja      short loc_1800C61DB
0x1800c61d5  call    cs:__imp_CloseHandle
0x1800c61db  mov     eax, ebx
0x1800c61dd  jmp     loc_1800C634A
0x1800c61e2  mov     [rsp+88h+var_20], r14d
0x1800c61e7  mov     rcx, qword ptr [rsp+88h+var_28]
0x1800c61ec  mov     rax, [rcx]
0x1800c61ef  lea     rdx, [rsp+88h+var_20]
0x1800c61f4  mov     rax, [rax+48h]
0x1800c61f8  call    _guard_dispatch_icall
0x1800c61fd  mov     ebx, eax
0x1800c61ff  test    eax, eax
0x1800c6201  jns     short loc_1800C6274
0x1800c6203  mov     rcx, [rsp+88h]; this
0x1800c620b  mov     r9d, eax; char *
0x1800c620e  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6215  mov     edx, 54h ; 'T'; void *
0x1800c621a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c621f  nop
0x1800c6220  mov     rcx, qword ptr [rsp+88h+var_28]
0x1800c6225  test    rcx, rcx
0x1800c6228  jz      short loc_1800C623C
0x1800c622a  mov     qword ptr [rsp+88h+var_28], r14
0x1800c622f  mov     rax, [rcx]
0x1800c6232  mov     rax, [rax+10h]
0x1800c6236  call    _guard_dispatch_icall
0x1800c623b  nop
0x1800c623c  mov     rcx, [rsp+88h+var_30]
0x1800c6241  test    rcx, rcx
0x1800c6244  jz      short loc_1800C6258
0x1800c6246  mov     [rsp+88h+var_30], r14
0x1800c624b  mov     rax, [rcx]
0x1800c624e  mov     rax, [rax+10h]
0x1800c6252  call    _guard_dispatch_icall
0x1800c6257  nop
0x1800c6258  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c625d  lea     rax, [rcx-1]
0x1800c6261  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c6265  ja      short loc_1800C626D
0x1800c6267  call    cs:__imp_CloseHandle
0x1800c626d  mov     eax, ebx
0x1800c626f  jmp     loc_1800C634A
0x1800c6274  cmp     [rsp+88h+var_20], 4
0x1800c6279  jz      short loc_1800C62EE
0x1800c627b  mov     rcx, [rsp+88h]; this
0x1800c6283  mov     ebx, 80D0201Eh
0x1800c6288  mov     r9d, ebx; char *
0x1800c628b  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6292  mov     edx, 57h ; 'W'; void *
0x1800c6297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c629c  nop
0x1800c629d  mov     rcx, qword ptr [rsp+88h+var_28]
0x1800c62a2  test    rcx, rcx
0x1800c62a5  jz      short loc_1800C62B9
0x1800c62a7  mov     qword ptr [rsp+88h+var_28], r14
0x1800c62ac  mov     rax, [rcx]
0x1800c62af  mov     rax, [rax+10h]
0x1800c62b3  call    _guard_dispatch_icall
0x1800c62b8  nop
0x1800c62b9  mov     rcx, [rsp+88h+var_30]
0x1800c62be  test    rcx, rcx
0x1800c62c1  jz      short loc_1800C62D5
0x1800c62c3  mov     [rsp+88h+var_30], r14
0x1800c62c8  mov     rax, [rcx]
0x1800c62cb  mov     rax, [rax+10h]
0x1800c62cf  call    _guard_dispatch_icall
0x1800c62d4  nop
0x1800c62d5  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c62da  lea     rdx, [rcx-1]
0x1800c62de  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800c62e2  ja      short loc_1800C62EA
0x1800c62e4  call    cs:__imp_CloseHandle
0x1800c62ea  mov     eax, ebx
0x1800c62ec  jmp     short loc_1800C634A
0x1800c62ee  mov     rcx, qword ptr [rsp+88h+var_28]
0x1800c62f3  test    rcx, rcx
0x1800c62f6  jz      short loc_1800C630A
0x1800c62f8  mov     qword ptr [rsp+88h+var_28], r14
0x1800c62fd  mov     rax, [rcx]
0x1800c6300  mov     rax, [rax+10h]
0x1800c6304  call    _guard_dispatch_icall
0x1800c6309  nop
0x1800c630a  mov     rcx, [rsp+88h+var_30]
0x1800c630f  test    rcx, rcx
0x1800c6312  jz      short loc_1800C6326
0x1800c6314  mov     [rsp+88h+var_30], r14
0x1800c6319  mov     rax, [rcx]
0x1800c631c  mov     rax, [rax+10h]
0x1800c6320  call    _guard_dispatch_icall
0x1800c6325  nop
0x1800c6326  mov     rcx, [rsp+88h+ClientProcess]; hObject
0x1800c632b  lea     rax, [rcx-1]
0x1800c632f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c6333  ja      short loc_1800C633B
0x1800c6335  call    cs:__imp_CloseHandle
0x1800c633b  xor     eax, eax
0x1800c633d  jmp     short loc_1800C634A
0x1800c633f  mov     eax, 8007000Eh
0x1800c6344  jmp     short loc_1800C634A
0x1800c6346  mov     eax, [rsp+88h+var_20]
0x1800c634a  mov     rcx, [rsp+88h+var_10]
0x1800c634f  xor     rcx, rsp; StackCookie
0x1800c6352  call    __security_check_cookie
0x1800c6357  lea     r11, [rsp+88h+var_8]
0x1800c635f  mov     rbx, [r11+18h]
0x1800c6363  mov     rsi, [r11+20h]
0x1800c6367  mov     rdi, [r11+28h]
0x1800c636b  mov     rsp, r11
0x1800c636e  pop     r14
0x1800c6370  retn
0x1800c6371  mov     ecx, eax; this
0x1800c6373  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
