# GetFileLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b8910`
- end: `0x1800b9028`
- name: `?GetFileLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1816`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800b8250`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x18000ff24`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x1800136dc`
- `0x18002bab4`
- `0x180089318`
- `0x1800b3980`
- `0x1800b5828`
- `0x1800b7104`
- `0x1800b7d2c`
- `0x1800b8910`
- `0x1800bba18`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8e97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8e97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8b6c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ce5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8e62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8e7b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8ce5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8e62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8e7b`

## string_xrefs

- `0x1800b8dfc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-FileTypeAssociation.hpp`
- `0x1800b8f5d`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8f72`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8f87`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8f9c`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8fb1`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8fc6`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8fdb`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9001`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9016`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

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
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
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
      goto LABEL_43;
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
    goto LABEL_44;
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
    goto LABEL_44;
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
  if ( *((_QWORD *)a4 + 11) <= 7u )
    v25 = (char *)a4 + 64;
  else
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
LABEL_43:
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_44:
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
0x1800b8910  push    rbp
0x1800b8912  push    rbx
0x1800b8913  push    rsi
0x1800b8914  push    rdi
0x1800b8915  push    r12
0x1800b8917  push    r13
0x1800b8919  push    r14
0x1800b891b  push    r15
0x1800b891d  lea     rbp, [rsp-78h]
0x1800b8922  sub     rsp, 178h
0x1800b8929  mov     rax, cs:__security_cookie
0x1800b8930  xor     rax, rsp
0x1800b8933  mov     [rbp+0B0h+var_50], rax
0x1800b8937  mov     r15, r9
0x1800b893a  mov     r14, r8
0x1800b893d  mov     rsi, rdx
0x1800b8940  mov     rbx, rcx
0x1800b8943  xor     r13d, r13d
0x1800b8946  mov     [rsp+1B0h+var_160], r13
0x1800b894b  mov     [rsp+1B0h+var_168], r13
0x1800b8950  mov     rax, [rcx]
0x1800b8953  lea     r8, [rsp+1B0h+var_160]
0x1800b8958  lea     rdx, _GUID_96f79d71_c461_4b3d_8428_4a095a986272
0x1800b895f  mov     rax, [rax]
0x1800b8962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8967  test    eax, eax
0x1800b8969  js      short loc_1800B89CB
0x1800b896b  mov     rdi, [rsp+1B0h+var_160]
0x1800b8970  mov     rax, [rdi]
0x1800b8973  mov     r12, [rax+30h]
0x1800b8977  mov     rdx, [rsp+1B0h+var_168]
0x1800b897c  test    rdx, rdx
0x1800b897f  jz      short loc_1800B8996
0x1800b8981  mov     [rsp+1B0h+var_168], r13
0x1800b8986  mov     rcx, [rdx]
0x1800b8989  mov     rax, [rcx+10h]
0x1800b898d  mov     rcx, rdx
0x1800b8990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8995  nop
0x1800b8996  lea     rdx, [rsp+1B0h+var_168]
0x1800b899b  mov     rcx, rdi
0x1800b899e  mov     rax, r12
0x1800b89a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b89a6  test    eax, eax
0x1800b89a8  js      short loc_1800B89CB
0x1800b89aa  mov     rcx, [rsp+1B0h+var_168]
0x1800b89af  test    rcx, rcx
0x1800b89b2  jz      short loc_1800B89CB
0x1800b89b4  mov     [rsp+1B0h+var_168], r13
0x1800b89b9  mov     rax, [rcx]
0x1800b89bc  mov     rax, [rax+10h]
0x1800b89c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b89c5  nop
0x1800b89c6  jmp     loc_1800B8D82
0x1800b89cb  mov     [rsp+1B0h+var_158], r13
0x1800b89d0  mov     rax, [rbx]
0x1800b89d3  lea     r8, [rsp+1B0h+var_158]
0x1800b89d8  lea     rdx, _GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496
0x1800b89df  mov     rcx, rbx
0x1800b89e2  mov     rax, [rax]
0x1800b89e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b89ea  cmp     eax, 80004002h
0x1800b89ef  jnz     short loc_1800B8A2E
0x1800b89f1  mov     rcx, [rsp+1B0h+var_158]
0x1800b89f6  test    rcx, rcx
0x1800b89f9  jz      short loc_1800B8A0D
0x1800b89fb  mov     [rsp+1B0h+var_158], r13
0x1800b8a00  mov     rax, [rcx]
0x1800b8a03  mov     rax, [rax+10h]
0x1800b8a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8a0c  nop
0x1800b8a0d  mov     rcx, [rsp+1B0h+var_168]
0x1800b8a12  test    rcx, rcx
0x1800b8a15  jz      short loc_1800B8A29
0x1800b8a17  mov     [rsp+1B0h+var_168], r13
0x1800b8a1c  mov     rax, [rcx]
0x1800b8a1f  mov     rax, [rax+10h]
0x1800b8a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8a28  nop
0x1800b8a29  jmp     loc_1800B8D82
0x1800b8a2e  mov     rcx, [rbp+0B8h]; this
0x1800b8a35  test    eax, eax
0x1800b8a37  js      loc_1800B8F6F
0x1800b8a3d  mov     [rsp+1B0h+var_150], r13
0x1800b8a42  mov     rcx, [rsp+1B0h+var_158]
0x1800b8a47  mov     rax, [rcx]
0x1800b8a4a  lea     rdx, [rsp+1B0h+var_150]
0x1800b8a4f  mov     rax, [rax+30h]
0x1800b8a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8a58  mov     rcx, [rbp+0B8h]; this
0x1800b8a5f  test    eax, eax
0x1800b8a61  js      loc_1800B8F84
0x1800b8a67  mov     [rbp+0B0h+var_130], r13d
0x1800b8a6b  mov     rcx, [rsp+1B0h+var_150]
0x1800b8a70  mov     rax, [rcx]
0x1800b8a73  lea     rdx, [rbp+0B0h+var_130]
0x1800b8a77  mov     rax, [rax+38h]
0x1800b8a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8a80  mov     rcx, [rbp+0B8h]; this
0x1800b8a87  test    eax, eax
0x1800b8a89  js      loc_1800B8F99
0x1800b8a8f  cmp     [rbp+0B0h+var_130], 1
0x1800b8a93  jnb     short loc_1800B8AEE
0x1800b8a95  mov     rcx, [rsp+1B0h+var_150]
0x1800b8a9a  test    rcx, rcx
0x1800b8a9d  jz      short loc_1800B8AB1
0x1800b8a9f  mov     [rsp+1B0h+var_150], r13
0x1800b8aa4  mov     rax, [rcx]
0x1800b8aa7  mov     rax, [rax+10h]
0x1800b8aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8ab0  nop
0x1800b8ab1  mov     rcx, [rsp+1B0h+var_158]
0x1800b8ab6  test    rcx, rcx
0x1800b8ab9  jz      short loc_1800B8ACD
0x1800b8abb  mov     [rsp+1B0h+var_158], r13
0x1800b8ac0  mov     rax, [rcx]
0x1800b8ac3  mov     rax, [rax+10h]
0x1800b8ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8acc  nop
0x1800b8acd  mov     rcx, [rsp+1B0h+var_168]
0x1800b8ad2  test    rcx, rcx
0x1800b8ad5  jz      short loc_1800B8AE9
0x1800b8ad7  mov     [rsp+1B0h+var_168], r13
0x1800b8adc  mov     rax, [rcx]
0x1800b8adf  mov     rax, [rax+10h]
0x1800b8ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8ae8  nop
0x1800b8ae9  jmp     loc_1800B8D82
0x1800b8aee  mov     [rsp+1B0h+var_138], r13
0x1800b8af3  mov     rcx, [rsp+1B0h+var_150]
0x1800b8af8  mov     rax, [rcx]
0x1800b8afb  lea     r8, [rsp+1B0h+var_138]
0x1800b8b00  xor     edx, edx
0x1800b8b02  mov     rax, [rax+30h]
0x1800b8b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8b0b  mov     rcx, [rbp+0B8h]; this
0x1800b8b12  test    eax, eax
0x1800b8b14  js      loc_1800B8FAE
0x1800b8b1a  mov     [rsp+1B0h+string], r13
0x1800b8b1f  mov     rdi, [rsp+1B0h+var_138]
0x1800b8b24  mov     rax, [rdi]
0x1800b8b27  mov     rbx, [rax+58h]
0x1800b8b2b  xor     ecx, ecx; string
0x1800b8b2d  call    cs:__imp_WindowsDeleteString
0x1800b8b34  nop     dword ptr [rax+rax+00h]
0x1800b8b39  mov     [rsp+1B0h+string], r13
0x1800b8b3e  lea     rdx, [rsp+1B0h+string]
0x1800b8b43  mov     rcx, rdi
0x1800b8b46  mov     rax, rbx
0x1800b8b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8b4e  mov     rcx, [rbp+0B8h]; this
0x1800b8b55  test    eax, eax
0x1800b8b57  js      loc_1800B8FC3
0x1800b8b5d  mov     [rsp+1B0h+length], r13d
0x1800b8b62  lea     rdx, [rsp+1B0h+length]; length
0x1800b8b67  mov     rcx, [rsp+1B0h+string]; string
0x1800b8b6c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b8b73  nop     dword ptr [rax+rax+00h]
0x1800b8b78  xorps   xmm0, xmm0
0x1800b8b7b  movups  [rbp+0B0h+var_B0], xmm0
0x1800b8b7f  xorps   xmm1, xmm1
0x1800b8b82  movdqu  [rbp+0B0h+var_A0], xmm1
0x1800b8b87  mov     r8d, [rsp+1B0h+length]
0x1800b8b8c  mov     rdx, rax
0x1800b8b8f  lea     rcx, [rbp+0B0h+var_B0]
0x1800b8b93  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b8b98  movups  xmm0, [rbp+0B0h+var_B0]
0x1800b8b9c  movups  [rbp+0B0h+var_90], xmm0
0x1800b8ba0  movups  xmm1, [rbp+0B0h+var_A0]
0x1800b8ba4  movups  [rbp+0B0h+var_80], xmm1
0x1800b8ba8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800b8bb0  movdqu  [rbp+0B0h+var_A0], xmm0
0x1800b8bb5  mov     word ptr [rbp+0B0h+var_B0], r13w
0x1800b8bba  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b8bbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8bc3  lea     rdx, [rbp+0B0h+var_70]
0x1800b8bc7  lea     rcx, [rbp+0B0h+var_90]
0x1800b8bcb  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x1800b8bd0  nop
0x1800b8bd1  mov     rdx, rax
0x1800b8bd4  lea     rcx, [rbp+0B0h+var_B0]
0x1800b8bd8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b8bdd  lea     rdi, [r15+148h]
0x1800b8be4  lea     rdx, [rbp+0B0h+var_B0]
0x1800b8be8  mov     rcx, rdi
0x1800b8beb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b8bf0  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b8bf4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8bf9  nop
0x1800b8bfa  lea     rcx, [rbp+0B0h+var_70]; void *
0x1800b8bfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8c03  lea     rdx, [rbp+0B0h+var_90]
0x1800b8c07  lea     rcx, [rbp+0B0h+var_B0]
0x1800b8c0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b8c10  lea     rcx, [r15+168h]
0x1800b8c17  lea     rdx, [rbp+0B0h+var_B0]
0x1800b8c1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b8c20  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800b8c24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8c29  mov     byte ptr [rsp+1B0h+var_170], r13b
0x1800b8c2e  xorps   xmm0, xmm0
0x1800b8c31  movdqu  [rbp+0B0h+var_128], xmm0
0x1800b8c36  xorps   xmm1, xmm1
0x1800b8c39  movdqu  [rbp+0B0h+var_118], xmm1
0x1800b8c3e  cmp     qword ptr [rdi+18h], 7
0x1800b8c43  jbe     short loc_1800B8C48
0x1800b8c45  mov     rdi, [rdi]
0x1800b8c48  lea     rbx, [r15+40h]
0x1800b8c4c  cmp     qword ptr [rbx+18h], 7
0x1800b8c51  jbe     short loc_1800B8C58
0x1800b8c53  mov     r8, [rbx]
0x1800b8c56  jmp     short loc_1800B8C5B
0x1800b8c58  mov     r8, rbx
0x1800b8c5b  lea     rax, [rsp+1B0h+var_170]
0x1800b8c60  mov     [rsp+1B0h+var_180], rax
0x1800b8c65  lea     rax, [rbp+0B0h+var_128]
0x1800b8c69  mov     [rsp+1B0h+var_188], rax
0x1800b8c6e  mov     qword ptr [rsp+1B0h+var_190], 3; int
0x1800b8c77  mov     r9, rdi
0x1800b8c7a  mov     rdx, r14
0x1800b8c7d  mov     rcx, rsi
0x1800b8c80  call    ?GetByUserAndApplicationUserModelIdAndFileType@FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::GetByUserAndApplicationUserModelIdAndFileType(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::CacheFlags,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &,bool &)
0x1800b8c85  mov     rcx, [rbp+0B8h]; this
0x1800b8c8c  test    eax, eax
0x1800b8c8e  js      loc_1800B8FD8
0x1800b8c94  cmp     byte ptr [rsp+1B0h+var_170], r13b
0x1800b8c99  jnz     loc_1800B8DA5
0x1800b8c9f  cmp     qword ptr [rbx+18h], 7
0x1800b8ca4  jbe     short loc_1800B8CA9
0x1800b8ca6  mov     rbx, [rbx]
0x1800b8ca9  mov     r8, rbx; unsigned __int16 *
0x1800b8cac  mov     rdx, r14; __int64
0x1800b8caf  mov     rcx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8cb2  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b8cb7  test    al, al
0x1800b8cb9  jz      loc_1800B8FED
0x1800b8cbf  mov     rcx, qword ptr [rbp+0B0h+var_118+8]
0x1800b8cc3  mov     qword ptr [rbp+0B0h+var_118+8], r13
0x1800b8cc7  test    rcx, rcx
0x1800b8cca  jz      short loc_1800B8CD8
0x1800b8ccc  call    cs:__imp_SRCache_Free
0x1800b8cd3  nop     dword ptr [rax+rax+00h]
0x1800b8cd8  mov     rcx, qword ptr [rbp+0B0h+var_118]
0x1800b8cdc  mov     qword ptr [rbp+0B0h+var_118], r13
0x1800b8ce0  test    rcx, rcx
0x1800b8ce3  jz      short loc_1800B8CF2
0x1800b8ce5  call    cs:__imp_SRCache_Free
0x1800b8cec  nop     dword ptr [rax+rax+00h]
0x1800b8cf1  nop
0x1800b8cf2  lea     rcx, [rbp+0B0h+var_90]; void *
0x1800b8cf6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8cfb  nop
0x1800b8cfc  mov     rcx, [rsp+1B0h+string]; string
0x1800b8d01  call    cs:__imp_WindowsDeleteString
0x1800b8d08  nop     dword ptr [rax+rax+00h]
0x1800b8d0d  mov     [rsp+1B0h+string], r13
0x1800b8d12  mov     rcx, [rsp+1B0h+var_138]
0x1800b8d17  test    rcx, rcx
0x1800b8d1a  jz      short loc_1800B8D2E
0x1800b8d1c  mov     [rsp+1B0h+var_138], r13
0x1800b8d21  mov     rax, [rcx]
0x1800b8d24  mov     rax, [rax+10h]
0x1800b8d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8d2d  nop
0x1800b8d2e  mov     rcx, [rsp+1B0h+var_150]
0x1800b8d33  test    rcx, rcx
0x1800b8d36  jz      short loc_1800B8D4A
0x1800b8d38  mov     [rsp+1B0h+var_150], r13
0x1800b8d3d  mov     rax, [rcx]
0x1800b8d40  mov     rax, [rax+10h]
0x1800b8d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8d49  nop
0x1800b8d4a  mov     rcx, [rsp+1B0h+var_158]
0x1800b8d4f  test    rcx, rcx
0x1800b8d52  jz      short loc_1800B8D66
0x1800b8d54  mov     [rsp+1B0h+var_158], r13
0x1800b8d59  mov     rax, [rcx]
0x1800b8d5c  mov     rax, [rax+10h]
0x1800b8d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8d65  nop
0x1800b8d66  mov     rcx, [rsp+1B0h+var_168]
0x1800b8d6b  test    rcx, rcx
0x1800b8d6e  jz      short loc_1800B8D82
0x1800b8d70  mov     [rsp+1B0h+var_168], r13
0x1800b8d75  mov     rax, [rcx]
0x1800b8d78  mov     rax, [rax+10h]
0x1800b8d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8d81  nop
0x1800b8d82  mov     rcx, [rsp+1B0h+var_160]
0x1800b8d87  test    rcx, rcx
0x1800b8d8a  jz      short loc_1800B8D9E
0x1800b8d8c  mov     [rsp+1B0h+var_160], r13
0x1800b8d91  mov     rax, [rcx]
0x1800b8d94  mov     rax, [rax+10h]
0x1800b8d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8d9d  nop
0x1800b8d9e  xor     al, al
0x1800b8da0  jmp     loc_1800B8F36
0x1800b8da5  mov     byte ptr [rsp+1B0h+var_170], r13b
0x1800b8daa  xorps   xmm0, xmm0
  ... truncated ...
```
