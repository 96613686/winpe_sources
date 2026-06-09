# GetFileLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b6a64`
- end: `0x1800b7177`
- name: `?GetFileLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1811`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800b6398`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x18000e234`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x18002b240`
- `0x180087bf0`
- `0x1800b17ac`
- `0x1800b3c14`
- `0x1800b52fc`
- `0x1800b5f44`
- `0x1800b6a64`
- `0x1800b9c4c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6fe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b6fe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b6cbd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6e1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6e34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6fb1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6fca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6e1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6e34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6fb1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b6fca`

## string_xrefs

- `0x1800b6f4b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b70ac`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b70c1`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b70d6`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b70eb`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7100`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7115`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b712a`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7150`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7165`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
bool __fastcall GetFileLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rdi
  int v20; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // rax
  _QWORD *v23; // rdi
  const unsigned __int16 *v24; // rbx
  char *v25; // r8
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 length; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  int v44; // [rsp+80h] [rbp-80h] BYREF
  __int128 v45; // [rsp+88h] [rbp-78h]
  __int128 v46; // [rsp+98h] [rbp-68h]
  __int128 v47; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  _OWORD v49[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v50[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v38 = 0;
  v37 = 0;
  if ( (**(int (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_96f79d71_c461_4b3d_8428_4a095a986272,
         &v38) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v37) >= 0 )
  {
    v8 = v37;
    if ( v37 )
      goto LABEL_42;
  }
  v39 = 0;
  v9 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496,
         &v39);
  if ( v9 == -2147467262 )
  {
    v10 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_43;
  }
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C0,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v9,
      v35);
  v40 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, &v40);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v12,
      v35);
  v44 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 56LL))(v40, &v44);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v13,
      v35);
  if ( !v44 )
  {
    v14 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_43;
  }
  v43 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, 0, &v43);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v17,
      v35);
  string = 0;
  v18 = v43;
  v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 88LL);
  WindowsDeleteString(0);
  string = 0;
  v20 = v19(v18, &string);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v20,
      v35);
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v47 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v47, StringRawBuffer, length);
  v49[0] = v47;
  v49[1] = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v47) = 0;
  std::wstring::~wstring(&v47);
  v22 = std::filesystem::path::extension(v49, v50);
  std::wstring::wstring(&v47, v22);
  v23 = (_QWORD *)((char *)a4 + 328);
  std::wstring::operator=((char *)a4 + 328, &v47);
  std::wstring::~wstring(&v47);
  std::wstring::~wstring(v50);
  std::wstring::wstring(&v47, v49);
  std::wstring::operator=((char *)a4 + 360, &v47);
  std::wstring::~wstring(&v47);
  LOBYTE(v36) = 0;
  v45 = 0;
  v46 = 0;
  if ( *((_QWORD *)a4 + 44) > 7u )
    v23 = (_QWORD *)*v23;
  v24 = (const unsigned __int16 *)((char *)a4 + 64);
  v25 = (char *)a4 + 64;
  if ( *((_QWORD *)a4 + 11) > 7u )
    v25 = *(char **)v24;
  v26 = StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(
          a2,
          a3,
          v25,
          v23);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v26,
      3);
  if ( *((_QWORD *)a4 + 11) > 7u )
    v24 = *(const unsigned __int16 **)v24;
  if ( !IsRuntimeBehaviorUniversal(a2, a3, v24) )
  {
    v34 = wil::verify_hresult(2147943568LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)v34,
      3);
  }
  v27 = *((_QWORD *)&v46 + 1);
  *((_QWORD *)&v46 + 1) = 0;
  if ( v27 )
    SRCache_Free();
  v28 = v46;
  *(_QWORD *)&v46 = 0;
  if ( v28 )
    SRCache_Free();
  std::wstring::~wstring(v49);
  WindowsDeleteString(string);
  string = 0;
  v29 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v8 = v37;
  if ( v37 )
  {
LABEL_42:
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_43:
  v32 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b6a64  push    rbp
0x1800b6a66  push    rbx
0x1800b6a67  push    rsi
0x1800b6a68  push    rdi
0x1800b6a69  push    r12
0x1800b6a6b  push    r13
0x1800b6a6d  push    r14
0x1800b6a6f  push    r15
0x1800b6a71  lea     rbp, [rsp-78h]
0x1800b6a76  sub     rsp, 178h
0x1800b6a7d  mov     rax, cs:__security_cookie
0x1800b6a84  xor     rax, rsp
0x1800b6a87  mov     [rbp+0B0h+var_50], rax
0x1800b6a8b  mov     r15, r9
0x1800b6a8e  mov     r14, r8
0x1800b6a91  mov     rsi, rdx
0x1800b6a94  mov     rdi, rcx
0x1800b6a97  xor     r13d, r13d
0x1800b6a9a  mov     [rsp+1B0h+var_160], r13
0x1800b6a9f  mov     [rsp+1B0h+var_168], r13
0x1800b6aa4  mov     rax, [rcx]
0x1800b6aa7  lea     r8, [rsp+1B0h+var_160]
0x1800b6aac  lea     rdx, _GUID_96f79d71_c461_4b3d_8428_4a095a986272
0x1800b6ab3  mov     rax, [rax]
0x1800b6ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6abb  test    eax, eax
0x1800b6abd  js      short loc_1800B6B1C
0x1800b6abf  mov     rbx, [rsp+1B0h+var_160]
0x1800b6ac4  mov     rax, [rbx]
0x1800b6ac7  mov     r12, [rax+30h]
0x1800b6acb  mov     rcx, [rsp+1B0h+var_168]
0x1800b6ad0  test    rcx, rcx
0x1800b6ad3  jz      short loc_1800B6AE7
0x1800b6ad5  mov     [rsp+1B0h+var_168], r13
0x1800b6ada  mov     rdx, [rcx]
0x1800b6add  mov     rax, [rdx+10h]
0x1800b6ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ae6  nop
0x1800b6ae7  lea     rdx, [rsp+1B0h+var_168]
0x1800b6aec  mov     rcx, rbx
0x1800b6aef  mov     rax, r12
0x1800b6af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6af7  test    eax, eax
0x1800b6af9  js      short loc_1800B6B1C
0x1800b6afb  mov     rcx, [rsp+1B0h+var_168]
0x1800b6b00  test    rcx, rcx
0x1800b6b03  jz      short loc_1800B6B1C
0x1800b6b05  mov     [rsp+1B0h+var_168], r13
0x1800b6b0a  mov     rax, [rcx]
0x1800b6b0d  mov     rax, [rax+10h]
0x1800b6b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b16  nop
0x1800b6b17  jmp     loc_1800B6ED1
0x1800b6b1c  mov     [rsp+1B0h+var_158], r13
0x1800b6b21  mov     rax, [rdi]
0x1800b6b24  lea     r8, [rsp+1B0h+var_158]
0x1800b6b29  lea     rdx, _GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496
0x1800b6b30  mov     rcx, rdi
0x1800b6b33  mov     rax, [rax]
0x1800b6b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b3b  cmp     eax, 80004002h
0x1800b6b40  jnz     short loc_1800B6B7F
0x1800b6b42  mov     rcx, [rsp+1B0h+var_158]
0x1800b6b47  test    rcx, rcx
0x1800b6b4a  jz      short loc_1800B6B5E
0x1800b6b4c  mov     [rsp+1B0h+var_158], r13
0x1800b6b51  mov     rax, [rcx]
0x1800b6b54  mov     rax, [rax+10h]
0x1800b6b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b5d  nop
0x1800b6b5e  mov     rcx, [rsp+1B0h+var_168]
0x1800b6b63  test    rcx, rcx
0x1800b6b66  jz      short loc_1800B6B7A
0x1800b6b68  mov     [rsp+1B0h+var_168], r13
0x1800b6b6d  mov     rax, [rcx]
0x1800b6b70  mov     rax, [rax+10h]
0x1800b6b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b79  nop
0x1800b6b7a  jmp     loc_1800B6ED1
0x1800b6b7f  mov     rcx, [rbp+0B8h]; this
0x1800b6b86  test    eax, eax
0x1800b6b88  js      loc_1800B70BE
0x1800b6b8e  mov     [rsp+1B0h+var_150], r13
0x1800b6b93  mov     rcx, [rsp+1B0h+var_158]
0x1800b6b98  mov     rax, [rcx]
0x1800b6b9b  lea     rdx, [rsp+1B0h+var_150]
0x1800b6ba0  mov     rax, [rax+30h]
0x1800b6ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ba9  mov     rcx, [rbp+0B8h]; this
0x1800b6bb0  test    eax, eax
0x1800b6bb2  js      loc_1800B70D3
0x1800b6bb8  mov     [rbp+0B0h+var_130], r13d
0x1800b6bbc  mov     rcx, [rsp+1B0h+var_150]
0x1800b6bc1  mov     rax, [rcx]
0x1800b6bc4  lea     rdx, [rbp+0B0h+var_130]
0x1800b6bc8  mov     rax, [rax+38h]
0x1800b6bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6bd1  mov     rcx, [rbp+0B8h]; this
0x1800b6bd8  test    eax, eax
0x1800b6bda  js      loc_1800B70E8
0x1800b6be0  cmp     [rbp+0B0h+var_130], 1
0x1800b6be4  jnb     short loc_1800B6C3F
0x1800b6be6  mov     rcx, [rsp+1B0h+var_150]
0x1800b6beb  test    rcx, rcx
0x1800b6bee  jz      short loc_1800B6C02
0x1800b6bf0  mov     [rsp+1B0h+var_150], r13
0x1800b6bf5  mov     rax, [rcx]
0x1800b6bf8  mov     rax, [rax+10h]
0x1800b6bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c01  nop
0x1800b6c02  mov     rcx, [rsp+1B0h+var_158]
0x1800b6c07  test    rcx, rcx
0x1800b6c0a  jz      short loc_1800B6C1E
0x1800b6c0c  mov     [rsp+1B0h+var_158], r13
0x1800b6c11  mov     rax, [rcx]
0x1800b6c14  mov     rax, [rax+10h]
0x1800b6c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c1d  nop
0x1800b6c1e  mov     rcx, [rsp+1B0h+var_168]
0x1800b6c23  test    rcx, rcx
0x1800b6c26  jz      short loc_1800B6C3A
0x1800b6c28  mov     [rsp+1B0h+var_168], r13
0x1800b6c2d  mov     rax, [rcx]
0x1800b6c30  mov     rax, [rax+10h]
0x1800b6c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c39  nop
0x1800b6c3a  jmp     loc_1800B6ED1
0x1800b6c3f  mov     [rsp+1B0h+var_138], r13
0x1800b6c44  mov     rcx, [rsp+1B0h+var_150]
0x1800b6c49  mov     rax, [rcx]
0x1800b6c4c  lea     r8, [rsp+1B0h+var_138]
0x1800b6c51  xor     edx, edx
0x1800b6c53  mov     rax, [rax+30h]
0x1800b6c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c5c  mov     rcx, [rbp+0B8h]; this
0x1800b6c63  test    eax, eax
0x1800b6c65  js      loc_1800B70FD
0x1800b6c6b  mov     [rsp+1B0h+string], r13
0x1800b6c70  mov     rbx, [rsp+1B0h+var_138]
0x1800b6c75  mov     rax, [rbx]
0x1800b6c78  mov     rdi, [rax+58h]
0x1800b6c7c  xor     ecx, ecx; string
0x1800b6c7e  call    cs:__imp_WindowsDeleteString
0x1800b6c85  nop     dword ptr [rax+rax+00h]
0x1800b6c8a  mov     [rsp+1B0h+string], r13
0x1800b6c8f  lea     rdx, [rsp+1B0h+string]
0x1800b6c94  mov     rcx, rbx
0x1800b6c97  mov     rax, rdi
0x1800b6c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c9f  mov     rcx, [rbp+0B8h]; this
0x1800b6ca6  test    eax, eax
0x1800b6ca8  js      loc_1800B7112
0x1800b6cae  mov     [rsp+1B0h+length], r13d
0x1800b6cb3  lea     rdx, [rsp+1B0h+length]; length
0x1800b6cb8  mov     rcx, [rsp+1B0h+string]; string
0x1800b6cbd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b6cc4  nop     dword ptr [rax+rax+00h]
0x1800b6cc9  mov     r8d, [rsp+1B0h+length]
0x1800b6cce  xorps   xmm0, xmm0
0x1800b6cd1  movups  [rbp+0B0h+var_B0], xmm0
0x1800b6cd5  xorps   xmm1, xmm1
0x1800b6cd8  movdqu  [rbp+0B0h+var_A0], xmm1
0x1800b6cdd  mov     rdx, rax
0x1800b6ce0  lea     rcx, [rbp+0B0h+var_B0]
0x1800b6ce4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b6ce9  movups  xmm0, [rbp+0B0h+var_B0]
0x1800b6ced  movups  [rbp+0B0h+var_90], xmm0
0x1800b6cf1  movups  xmm1, [rbp+0B0h+var_A0]
0x1800b6cf5  movups  [rbp+0B0h+var_80], xmm1
0x1800b6cf9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800b6d01  movdqu  [rbp+0B0h+var_A0], xmm0
0x1800b6d06  mov     word ptr [rbp+0B0h+var_B0], r13w
0x1800b6d0b  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b6d0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6d14  lea     rdx, [rbp+0B0h+var_70]
0x1800b6d18  lea     rcx, [rbp+0B0h+var_90]
0x1800b6d1c  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x1800b6d21  nop
0x1800b6d22  mov     rdx, rax
0x1800b6d25  lea     rcx, [rbp+0B0h+var_B0]
0x1800b6d29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b6d2e  lea     rdi, [r15+148h]
0x1800b6d35  lea     rdx, [rbp+0B0h+var_B0]
0x1800b6d39  mov     rcx, rdi
0x1800b6d3c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b6d41  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b6d45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6d4a  nop
0x1800b6d4b  lea     rcx, [rbp+0B0h+var_70]; void *
0x1800b6d4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6d54  lea     rdx, [rbp+0B0h+var_90]
0x1800b6d58  lea     rcx, [rbp+0B0h+var_B0]
0x1800b6d5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b6d61  lea     rcx, [r15+168h]
0x1800b6d68  lea     rdx, [rbp+0B0h+var_B0]
0x1800b6d6c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b6d71  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b6d75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6d7a  mov     byte ptr [rsp+1B0h+var_170], r13b
0x1800b6d7f  xorps   xmm0, xmm0
0x1800b6d82  movdqu  [rbp+0B0h+var_128], xmm0
0x1800b6d87  xorps   xmm1, xmm1
0x1800b6d8a  movdqu  [rbp+0B0h+var_118], xmm1
0x1800b6d8f  cmp     qword ptr [rdi+18h], 7
0x1800b6d94  jbe     short loc_1800B6D99
0x1800b6d96  mov     rdi, [rdi]
0x1800b6d99  lea     rbx, [r15+40h]
0x1800b6d9d  mov     r8, rbx
0x1800b6da0  cmp     qword ptr [rbx+18h], 7
0x1800b6da5  jbe     short loc_1800B6DAA
0x1800b6da7  mov     r8, [rbx]
0x1800b6daa  lea     rax, [rsp+1B0h+var_170]
0x1800b6daf  mov     [rsp+1B0h+var_180], rax
0x1800b6db4  lea     rax, [rbp+0B0h+var_128]
0x1800b6db8  mov     [rsp+1B0h+var_188], rax
0x1800b6dbd  mov     qword ptr [rsp+1B0h+var_190], 3; int
0x1800b6dc6  mov     r9, rdi
0x1800b6dc9  mov     rdx, r14
0x1800b6dcc  mov     rcx, rsi
0x1800b6dcf  call    ?GetByUserAndApplicationUserModelIdAndFileType@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b6dd4  mov     rcx, [rbp+0B8h]; this
0x1800b6ddb  test    eax, eax
0x1800b6ddd  js      loc_1800B7127
0x1800b6de3  cmp     byte ptr [rsp+1B0h+var_170], r13b
0x1800b6de8  jnz     loc_1800B6EF4
0x1800b6dee  cmp     qword ptr [rbx+18h], 7
0x1800b6df3  jbe     short loc_1800B6DF8
0x1800b6df5  mov     rbx, [rbx]
0x1800b6df8  mov     r8, rbx; unsigned __int16 *
0x1800b6dfb  mov     rdx, r14; __int64
0x1800b6dfe  mov     rcx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800b6e01  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b6e06  test    al, al
0x1800b6e08  jz      loc_1800B713C
0x1800b6e0e  mov     rcx, qword ptr [rbp+0B0h+var_118+8]
0x1800b6e12  mov     qword ptr [rbp+0B0h+var_118+8], r13
0x1800b6e16  test    rcx, rcx
0x1800b6e19  jz      short loc_1800B6E27
0x1800b6e1b  call    cs:__imp_SRCache_Free
0x1800b6e22  nop     dword ptr [rax+rax+00h]
0x1800b6e27  mov     rcx, qword ptr [rbp+0B0h+var_118]
0x1800b6e2b  mov     qword ptr [rbp+0B0h+var_118], r13
0x1800b6e2f  test    rcx, rcx
0x1800b6e32  jz      short loc_1800B6E41
0x1800b6e34  call    cs:__imp_SRCache_Free
0x1800b6e3b  nop     dword ptr [rax+rax+00h]
0x1800b6e40  nop
0x1800b6e41  lea     rcx, [rbp+0B0h+var_90]; void *
0x1800b6e45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6e4a  nop
0x1800b6e4b  mov     rcx, [rsp+1B0h+string]; string
0x1800b6e50  call    cs:__imp_WindowsDeleteString
0x1800b6e57  nop     dword ptr [rax+rax+00h]
0x1800b6e5c  mov     [rsp+1B0h+string], r13
0x1800b6e61  mov     rcx, [rsp+1B0h+var_138]
0x1800b6e66  test    rcx, rcx
0x1800b6e69  jz      short loc_1800B6E7D
0x1800b6e6b  mov     [rsp+1B0h+var_138], r13
0x1800b6e70  mov     rax, [rcx]
0x1800b6e73  mov     rax, [rax+10h]
0x1800b6e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e7c  nop
0x1800b6e7d  mov     rcx, [rsp+1B0h+var_150]
0x1800b6e82  test    rcx, rcx
0x1800b6e85  jz      short loc_1800B6E99
0x1800b6e87  mov     [rsp+1B0h+var_150], r13
0x1800b6e8c  mov     rax, [rcx]
0x1800b6e8f  mov     rax, [rax+10h]
0x1800b6e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6e98  nop
0x1800b6e99  mov     rcx, [rsp+1B0h+var_158]
0x1800b6e9e  test    rcx, rcx
0x1800b6ea1  jz      short loc_1800B6EB5
0x1800b6ea3  mov     [rsp+1B0h+var_158], r13
0x1800b6ea8  mov     rax, [rcx]
0x1800b6eab  mov     rax, [rax+10h]
0x1800b6eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6eb4  nop
0x1800b6eb5  mov     rcx, [rsp+1B0h+var_168]
0x1800b6eba  test    rcx, rcx
0x1800b6ebd  jz      short loc_1800B6ED1
0x1800b6ebf  mov     [rsp+1B0h+var_168], r13
0x1800b6ec4  mov     rax, [rcx]
0x1800b6ec7  mov     rax, [rax+10h]
0x1800b6ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ed0  nop
0x1800b6ed1  mov     rcx, [rsp+1B0h+var_160]
0x1800b6ed6  test    rcx, rcx
0x1800b6ed9  jz      short loc_1800B6EED
0x1800b6edb  mov     [rsp+1B0h+var_160], r13
0x1800b6ee0  mov     rax, [rcx]
0x1800b6ee3  mov     rax, [rax+10h]
0x1800b6ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6eec  nop
0x1800b6eed  xor     al, al
0x1800b6eef  jmp     loc_1800B7085
0x1800b6ef4  mov     byte ptr [rsp+1B0h+var_170], r13b
0x1800b6ef9  xorps   xmm0, xmm0
0x1800b6efc  movdqa  [rbp+0B0h+var_100], xmm0
0x1800b6f01  mov     [rbp+0B0h+var_F0], r13
  ... truncated ...
```
