# Windows::Compat::Ids::IdsOneSettings::ParseModule(void *)

- ea: `0x1800d5ac8`
- end: `0x1800d5f9b`
- name: `?ParseModule@IdsOneSettings@Ids@Compat@Windows@@AEAAJPEAX@Z`
- size: `1235`
- prototype: `__int64 __fastcall(Windows::Compat::Ids::IdsOneSettings *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5fa4`

## callees

- `0x180012920`
- `0x18008cd3c`
- `0x180096f34`
- `0x1800bc074`
- `0x1800d5208`
- `0x1800d5898`
- `0x1800d5ac8`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800d5d50`
- `msvcrt!_wtoi` at `0x1800d5d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5c12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5f6c`

## string_xrefs

- `0x1800d5b70`: `Windows::Compat::Ids::IdsOneSettings::ParseModule`
- `0x1800d5b9a`: `Windows::Compat::Ids::IdsOneSettings::ParseModule`
- `0x1800d5e7f`: `Failed to get the json array size [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Compat::Ids::IdsOneSettings::ParseModule(Windows::Compat::Ids::IdsEngine **this, void *a2)
{
  __int64 (__fastcall *v4)(void *, __int64, HSTRING *); // rbx
  int JsonArraySize; // ebx
  const char *v6; // r9
  int v7; // r8d
  __int64 (__fastcall *v8)(void *, __int64, HSTRING *); // rbx
  __int64 (__fastcall *v9)(void *, __int64, __int64 *); // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int (__fastcall *v11)(void *, __int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  Windows::Compat::Ids::IdsEngine *v13; // rsi
  unsigned __int16 *v14; // rdi
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rax
  __int64 (__fastcall *v17)(void *, __int64, __int64 *); // rbx
  unsigned int v18; // esi
  __int64 v19; // rdi
  int (__fastcall *v20)(__int64, _QWORD, struct Windows::Compat::Ids::IdsModel **); // rbx
  HSTRING v22; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v23; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  HSTRING string; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::Compat::Ids::IdsModel *v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v31; // [rsp+88h] [rbp+Fh]

  string = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v29 = 0;
  v25 = 0;
  v4 = *(__int64 (__fastcall **)(void *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Name", 5u, 4u);
  JsonArraySize = v4(a2, v31, &string);
  if ( JsonArraySize < 0 )
  {
    v6 = "Failed to get the object name [%x]";
    v7 = 116;
LABEL_15:
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule", v7, (_DWORD)v6);
    goto LABEL_26;
  }
  WindowsGetStringRawBuffer(string, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
    119,
    (unsigned int)"Got name of the object [%ws]");
  v8 = *(__int64 (__fastcall **)(void *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(v23);
  v23 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Type", 5u, 4u);
  JsonArraySize = v8(a2, v31, &v23);
  if ( JsonArraySize < 0 )
  {
    v6 = "Failed to get the object type [%x]";
    v7 = 124;
    goto LABEL_15;
  }
  WindowsGetStringRawBuffer(v23, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
    127,
    (unsigned int)"Got type of the object [%ws]");
  v9 = *(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)a2 + 48LL);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DATA", 5u, 4u);
  JsonArraySize = v9(a2, v31, &v29);
  if ( JsonArraySize < 0 )
  {
    v6 = "Failed to get the model parameter [%x]";
    v7 = 132;
    goto LABEL_15;
  }
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 56LL);
  WindowsDeleteString(v22);
  v22 = 0;
  JsonArraySize = v10(v29, &v22);
  if ( JsonArraySize < 0 )
  {
    v6 = "Failed to stringify the model parameter [%x]";
    v7 = 139;
    goto LABEL_15;
  }
  WindowsGetStringRawBuffer(v22, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
    142,
    (unsigned int)"Got model parameter [%ws]");
  v11 = *(int (__fastcall **)(void *, __int64, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(v24);
  v24 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"STATE", 6u, 5u);
  if ( v11(a2, v31, &v24) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v24, 0);
    _wtoi(StringRawBuffer);
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
    150,
    (unsigned int)"Got model state [%x]");
  v13 = *this;
  v14 = (unsigned __int16 *)WindowsGetStringRawBuffer(v22, 0);
  v15 = (unsigned __int16 *)WindowsGetStringRawBuffer(v23, 0);
  v16 = WindowsGetStringRawBuffer(string, 0);
  if ( Windows::Compat::Ids::IdsEngine::GetModel(v13, v16, v15, v14, &v28) )
  {
    WindowsGetStringRawBuffer(v22, 0);
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
      158,
      (unsigned int)"Failed to get model for [%ws] [%d]");
    JsonArraySize = -2147467259;
  }
  else
  {
    v17 = *(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)a2 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v25);
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"EVENTLIST", 0xAu, 9u);
    JsonArraySize = v17(a2, v31, &v25);
    if ( JsonArraySize < 0 )
    {
      v6 = "Failed to get the event list [%x]";
      v7 = 165;
      goto LABEL_15;
    }
    v27 = 0;
    JsonArraySize = GetJsonArraySize(&v25, &v27);
    if ( JsonArraySize < 0 )
    {
      v6 = "Failed to get the json array size [%x]";
      v7 = 173;
      goto LABEL_15;
    }
    v18 = 0;
    if ( v27 )
    {
      while ( 1 )
      {
        v28 = 0;
        v19 = v25;
        v20 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::Compat::Ids::IdsModel **))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v28);
        if ( v20(v19, v18, &v28) < 0 )
          break;
        if ( (int)Windows::Compat::Ids::IdsOneSettings::ParseEvent((Windows::Compat::Ids::IdsOneSettings *)this, v28) < 0 )
          AslLogCallPrintf(
            1,
            (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
            189,
            (unsigned int)"Failed to parse event [%x]");
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v28);
        if ( ++v18 >= v27 )
          goto LABEL_25;
      }
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Ids::IdsOneSettings::ParseModule",
        183,
        (unsigned int)"Failed to get event at [%d]");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v28);
    }
LABEL_25:
    JsonArraySize = 0;
  }
LABEL_26:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v25);
  WindowsDeleteString(v24);
  v24 = 0;
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(v23);
  v23 = 0;
  WindowsDeleteString(string);
  return (unsigned int)JsonArraySize;
}

```

## disassembly

```asm
0x1800d5ac8  mov     [rsp-8+arg_10], rbx
0x1800d5acd  push    rbp
0x1800d5ace  push    rsi
0x1800d5acf  push    rdi
0x1800d5ad0  push    r12
0x1800d5ad2  push    r13
0x1800d5ad4  push    r14
0x1800d5ad6  push    r15
0x1800d5ad8  lea     rbp, [rsp-27h]
0x1800d5add  sub     rsp, 0A0h
0x1800d5ae4  mov     rax, cs:__security_cookie
0x1800d5aeb  xor     rax, rsp
0x1800d5aee  mov     [rbp+57h+var_40], rax
0x1800d5af2  mov     r15, rdx
0x1800d5af5  mov     r12, rcx
0x1800d5af8  xor     r13d, r13d
0x1800d5afb  mov     [rbp+57h+string], r13
0x1800d5aff  mov     [rbp+57h+var_98], r13
0x1800d5b03  mov     [rbp+57h+var_A0], r13
0x1800d5b07  mov     [rbp+57h+var_90], r13
0x1800d5b0b  mov     [rbp+57h+var_68], r13
0x1800d5b0f  mov     [rbp+57h+var_88], r13
0x1800d5b13  mov     rax, [rdx]
0x1800d5b16  mov     rbx, [rax+50h]
0x1800d5b1a  xor     ecx, ecx; string
0x1800d5b1c  call    cs:__imp_WindowsDeleteString
0x1800d5b22  mov     [rbp+57h+string], r13
0x1800d5b26  mov     [rbp+57h+var_48], r13
0x1800d5b2a  lea     edi, [r13+4]
0x1800d5b2e  mov     r9d, edi; unsigned int
0x1800d5b31  lea     esi, [rdi+1]
0x1800d5b34  mov     r8d, esi; unsigned int
0x1800d5b37  lea     rdx, aName; "Name"
0x1800d5b3e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5b42  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5b47  nop
0x1800d5b48  lea     r8, [rbp+57h+string]
0x1800d5b4c  mov     rdx, [rbp+57h+var_48]
0x1800d5b50  mov     rcx, r15
0x1800d5b53  mov     rax, rbx
0x1800d5b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5b5b  mov     ebx, eax
0x1800d5b5d  test    eax, eax
0x1800d5b5f  jns     short loc_1800D5B7C
0x1800d5b61  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800d5b65  lea     r9, aFailedToGetThe_24; "Failed to get the object name [%x]"
0x1800d5b6c  lea     r8d, [r13+74h]
0x1800d5b70  lea     rdx, aWindowsCompatI_62; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d5b77  jmp     loc_1800D5E59
0x1800d5b7c  xor     edx, edx; length
0x1800d5b7e  mov     rcx, [rbp+57h+string]; string
0x1800d5b82  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5b88  mov     [rsp+0D0h+var_B0], rax
0x1800d5b8d  lea     r9, aGotNameOfTheOb; "Got name of the object [%ws]"
0x1800d5b94  mov     r8d, 77h ; 'w'
0x1800d5b9a  lea     r14, aWindowsCompatI_62; "Windows::Compat::Ids::IdsOneSettings::P"...
0x1800d5ba1  mov     rdx, r14
0x1800d5ba4  lea     ecx, [r8-74h]
0x1800d5ba8  call    AslLogCallPrintf
0x1800d5bad  mov     rax, [r15]
0x1800d5bb0  mov     rbx, [rax+50h]
0x1800d5bb4  mov     rcx, [rbp+57h+var_98]; string
0x1800d5bb8  call    cs:__imp_WindowsDeleteString
0x1800d5bbe  mov     [rbp+57h+var_98], r13
0x1800d5bc2  mov     [rbp+57h+var_48], r13
0x1800d5bc6  mov     r9d, edi; unsigned int
0x1800d5bc9  mov     r8d, esi; unsigned int
0x1800d5bcc  lea     rdx, aType_0; "Type"
0x1800d5bd3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5bd7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5bdc  nop
0x1800d5bdd  lea     r8, [rbp+57h+var_98]
0x1800d5be1  mov     rdx, [rbp+57h+var_48]
0x1800d5be5  mov     rcx, r15
0x1800d5be8  mov     rax, rbx
0x1800d5beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5bf0  mov     ebx, eax
0x1800d5bf2  test    eax, eax
0x1800d5bf4  jns     short loc_1800D5C0C
0x1800d5bf6  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800d5bfa  lea     r9, aFailedToGetThe_39; "Failed to get the object type [%x]"
0x1800d5c01  mov     r8d, 7Ch ; '|'
0x1800d5c07  jmp     loc_1800D5E56
0x1800d5c0c  xor     edx, edx; length
0x1800d5c0e  mov     rcx, [rbp+57h+var_98]; string
0x1800d5c12  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5c18  mov     [rsp+0D0h+var_B0], rax
0x1800d5c1d  lea     r9, aGotTypeOfTheOb; "Got type of the object [%ws]"
0x1800d5c24  mov     r8d, 7Fh
0x1800d5c2a  mov     rdx, r14
0x1800d5c2d  lea     ecx, [r8-7Ch]
0x1800d5c31  call    AslLogCallPrintf
0x1800d5c36  mov     rax, [r15]
0x1800d5c39  mov     rbx, [rax+30h]
0x1800d5c3d  mov     [rbp+57h+var_48], r13
0x1800d5c41  mov     r9d, edi; unsigned int
0x1800d5c44  mov     r8d, esi; unsigned int
0x1800d5c47  lea     rdx, aData; "DATA"
0x1800d5c4e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5c52  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5c57  nop
0x1800d5c58  lea     r8, [rbp+57h+var_68]
0x1800d5c5c  mov     rdx, [rbp+57h+var_48]
0x1800d5c60  mov     rcx, r15
0x1800d5c63  mov     rax, rbx
0x1800d5c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5c6b  mov     ebx, eax
0x1800d5c6d  test    eax, eax
0x1800d5c6f  jns     short loc_1800D5C87
0x1800d5c71  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800d5c75  lea     r9, aFailedToGetThe_6; "Failed to get the model parameter [%x]"
0x1800d5c7c  mov     r8d, 84h
0x1800d5c82  jmp     loc_1800D5E56
0x1800d5c87  mov     rax, [rbp+57h+var_68]
0x1800d5c8b  mov     rcx, [rax]
0x1800d5c8e  mov     rbx, [rcx+38h]
0x1800d5c92  mov     rcx, [rbp+57h+var_A0]; string
0x1800d5c96  call    cs:__imp_WindowsDeleteString
0x1800d5c9c  mov     [rbp+57h+var_A0], r13
0x1800d5ca0  lea     rdx, [rbp+57h+var_A0]
0x1800d5ca4  mov     rcx, [rbp+57h+var_68]
0x1800d5ca8  mov     rax, rbx
0x1800d5cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5cb0  mov     ebx, eax
0x1800d5cb2  test    eax, eax
0x1800d5cb4  jns     short loc_1800D5CC8
0x1800d5cb6  lea     r9, aFailedToString; "Failed to stringify the model parameter"...
0x1800d5cbd  mov     r8d, 8Bh
0x1800d5cc3  jmp     loc_1800D5E52
0x1800d5cc8  xor     edx, edx; length
0x1800d5cca  mov     rcx, [rbp+57h+var_A0]; string
0x1800d5cce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5cd4  mov     [rsp+0D0h+var_B0], rax
0x1800d5cd9  lea     r9, aGotModelParame; "Got model parameter [%ws]"
0x1800d5ce0  mov     r8d, 8Eh
0x1800d5ce6  mov     rdx, r14
0x1800d5ce9  mov     ecx, 3
0x1800d5cee  call    AslLogCallPrintf
0x1800d5cf3  mov     edi, r13d
0x1800d5cf6  mov     rax, [r15]
0x1800d5cf9  mov     rbx, [rax+50h]
0x1800d5cfd  mov     rcx, [rbp+57h+var_90]; string
0x1800d5d01  call    cs:__imp_WindowsDeleteString
0x1800d5d07  mov     [rbp+57h+var_90], r13
0x1800d5d0b  mov     [rbp+57h+var_48], r13
0x1800d5d0f  mov     r9d, esi; unsigned int
0x1800d5d12  mov     r8d, 6; unsigned int
0x1800d5d18  lea     rdx, aState; "STATE"
0x1800d5d1f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5d23  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5d28  nop
0x1800d5d29  lea     r8, [rbp+57h+var_90]
0x1800d5d2d  mov     rdx, [rbp+57h+var_48]
0x1800d5d31  mov     rcx, r15
0x1800d5d34  mov     rax, rbx
0x1800d5d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5d3c  nop
0x1800d5d3d  test    eax, eax
0x1800d5d3f  js      short loc_1800D5D58
0x1800d5d41  xor     edx, edx; length
0x1800d5d43  mov     rcx, [rbp+57h+var_90]; string
0x1800d5d47  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5d4d  mov     rcx, rax; String
0x1800d5d50  call    cs:__imp__wtoi
0x1800d5d56  mov     edi, eax
0x1800d5d58  mov     dword ptr [rsp+0D0h+var_B0], edi
0x1800d5d5c  lea     r9, aGotModelStateX; "Got model state [%x]"
0x1800d5d63  mov     r8d, 96h
0x1800d5d69  mov     rdx, r14
0x1800d5d6c  mov     ecx, 3
0x1800d5d71  call    AslLogCallPrintf
0x1800d5d76  mov     rsi, [r12]
0x1800d5d7a  xor     edx, edx; length
0x1800d5d7c  mov     rcx, [rbp+57h+var_A0]; string
0x1800d5d80  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5d86  mov     rdi, rax
0x1800d5d89  xor     edx, edx; length
0x1800d5d8b  mov     rcx, [rbp+57h+var_98]; string
0x1800d5d8f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5d95  mov     rbx, rax
0x1800d5d98  xor     edx, edx; length
0x1800d5d9a  mov     rcx, [rbp+57h+string]; string
0x1800d5d9e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5da4  lea     rcx, [rbp+57h+var_70]
0x1800d5da8  mov     [rsp+0D0h+var_B0], rcx; struct Windows::Compat::Ids::IdsModel **
0x1800d5dad  mov     r9, rdi; unsigned __int16 *
0x1800d5db0  mov     r8, rbx; unsigned __int16 *
0x1800d5db3  mov     rdx, rax; unsigned __int16 *
0x1800d5db6  mov     rcx, rsi; this
0x1800d5db9  call    ?GetModel@IdsEngine@Ids@Compat@Windows@@QEAAKPEBGPEAG1PEAPEAVIdsModel@234@@Z; Windows::Compat::Ids::IdsEngine::GetModel(ushort const *,ushort *,ushort *,Windows::Compat::Ids::IdsModel * *)
0x1800d5dbe  mov     ebx, eax
0x1800d5dc0  test    eax, eax
0x1800d5dc2  jz      short loc_1800D5DFD
0x1800d5dc4  xor     edx, edx; length
0x1800d5dc6  mov     rcx, [rbp+57h+var_A0]; string
0x1800d5dca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5dd0  mov     [rsp+0D0h+var_A8], ebx
0x1800d5dd4  mov     [rsp+0D0h+var_B0], rax
0x1800d5dd9  lea     r9, aFailedToGetMod_0; "Failed to get model for [%ws] [%d]"
0x1800d5de0  mov     r8d, 9Eh
0x1800d5de6  mov     rdx, r14
0x1800d5de9  mov     ecx, 1
0x1800d5dee  call    AslLogCallPrintf
0x1800d5df3  mov     ebx, 80004005h
0x1800d5df8  jmp     loc_1800D5F34
0x1800d5dfd  mov     rax, [r15]
0x1800d5e00  mov     rbx, [rax+48h]
0x1800d5e04  lea     rcx, [rbp+57h+var_88]
0x1800d5e08  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d5e0d  mov     [rbp+57h+var_48], r13
0x1800d5e11  mov     r9d, 9; unsigned int
0x1800d5e17  lea     r8d, [r9+1]; unsigned int
0x1800d5e1b  lea     rdx, aEventlist_2; "EVENTLIST"
0x1800d5e22  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d5e26  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5e2b  nop
0x1800d5e2c  lea     r8, [rbp+57h+var_88]
0x1800d5e30  mov     rdx, [rbp+57h+var_48]
0x1800d5e34  mov     rcx, r15
0x1800d5e37  mov     rax, rbx
0x1800d5e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5e3f  mov     ebx, eax
0x1800d5e41  test    eax, eax
0x1800d5e43  jns     short loc_1800D5E68
0x1800d5e45  lea     r9, aFailedToGetThe_27; "Failed to get the event list [%x]"
0x1800d5e4c  mov     r8d, 0A5h
0x1800d5e52  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800d5e56  mov     rdx, r14
0x1800d5e59  mov     ecx, 1
0x1800d5e5e  call    AslLogCallPrintf
0x1800d5e63  jmp     loc_1800D5F34
0x1800d5e68  mov     [rbp+57h+var_78], r13d
0x1800d5e6c  lea     rdx, [rbp+57h+var_78]
0x1800d5e70  lea     rcx, [rbp+57h+var_88]
0x1800d5e74  call    ?GetJsonArraySize@@YAJAEBV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAI@Z; GetJsonArraySize(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> const &,uint *)
0x1800d5e79  mov     ebx, eax
0x1800d5e7b  test    eax, eax
0x1800d5e7d  jns     short loc_1800D5E8E
0x1800d5e7f  lea     r9, aFailedToGetThe_1; "Failed to get the json array size [%x]"
0x1800d5e86  mov     r8d, 0ADh
0x1800d5e8c  jmp     short loc_1800D5E52
0x1800d5e8e  mov     esi, r13d
0x1800d5e91  cmp     [rbp+57h+var_78], r13d
0x1800d5e95  jbe     loc_1800D5F31
0x1800d5e9b  mov     [rbp+57h+var_70], r13
0x1800d5e9f  mov     rdi, [rbp+57h+var_88]
0x1800d5ea3  mov     rax, [rdi]
0x1800d5ea6  mov     rbx, [rax+30h]
0x1800d5eaa  lea     rcx, [rbp+57h+var_70]
0x1800d5eae  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d5eb3  lea     r8, [rbp+57h+var_70]
0x1800d5eb7  mov     edx, esi
0x1800d5eb9  mov     rcx, rdi
0x1800d5ebc  mov     rax, rbx
0x1800d5ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5ec4  test    eax, eax
0x1800d5ec6  js      short loc_1800D5F09
0x1800d5ec8  mov     rdx, [rbp+57h+var_70]; void *
0x1800d5ecc  mov     rcx, r12; this
0x1800d5ecf  call    ?ParseEvent@IdsOneSettings@Ids@Compat@Windows@@AEAAJPEAX@Z; Windows::Compat::Ids::IdsOneSettings::ParseEvent(void *)
0x1800d5ed4  test    eax, eax
0x1800d5ed6  jns     short loc_1800D5EF7
0x1800d5ed8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800d5edc  lea     r9, aFailedToParseE; "Failed to parse event [%x]"
0x1800d5ee3  mov     r8d, 0BDh
0x1800d5ee9  mov     rdx, r14
0x1800d5eec  mov     ecx, 1
0x1800d5ef1  call    AslLogCallPrintf
0x1800d5ef6  nop
0x1800d5ef7  lea     rcx, [rbp+57h+var_70]
0x1800d5efb  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d5f00  inc     esi
0x1800d5f02  cmp     esi, [rbp+57h+var_78]
0x1800d5f05  jb      short loc_1800D5E9B
0x1800d5f07  jmp     short loc_1800D5F31
0x1800d5f09  mov     dword ptr [rsp+0D0h+var_B0], esi
0x1800d5f0d  lea     r9, aFailedToGetEve_7; "Failed to get event at [%d]"
0x1800d5f14  mov     r8d, 0B7h
0x1800d5f1a  mov     rdx, r14
0x1800d5f1d  mov     ecx, 1
0x1800d5f22  call    AslLogCallPrintf
0x1800d5f27  nop
0x1800d5f28  lea     rcx, [rbp+57h+var_70]
0x1800d5f2c  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d5f31  mov     ebx, r13d
0x1800d5f34  lea     rcx, [rbp+57h+var_88]
0x1800d5f38  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d5f3d  nop
0x1800d5f3e  mov     rcx, [rbp+57h+var_90]; string
0x1800d5f42  call    cs:__imp_WindowsDeleteString
0x1800d5f48  mov     [rbp+57h+var_90], r13
0x1800d5f4c  mov     rcx, [rbp+57h+var_A0]; string
0x1800d5f50  call    cs:__imp_WindowsDeleteString
0x1800d5f56  mov     [rbp+57h+var_A0], r13
0x1800d5f5a  mov     rcx, [rbp+57h+var_98]; string
0x1800d5f5e  call    cs:__imp_WindowsDeleteString
0x1800d5f64  mov     [rbp+57h+var_98], r13
0x1800d5f68  mov     rcx, [rbp+57h+string]; string
0x1800d5f6c  call    cs:__imp_WindowsDeleteString
0x1800d5f72  mov     eax, ebx
  ... truncated ...
```
