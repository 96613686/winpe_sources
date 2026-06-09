# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(IInspectable *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004db98`
- end: `0x18004dfd6`
- name: `?Match@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CA_NPEAUIInspectable@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@@Z`
- size: `1086`
- prototype: `char __fastcall(__int64, HSTRING, char **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004e200`

## callees

- `0x180004f70`
- `0x18000b132`
- `0x1800125f4`
- `0x1800130e4`
- `0x180039d1c`
- `0x18003fd60`
- `0x18004c898`
- `0x18004db98`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dc41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dd52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dc41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dd52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004de45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004de59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004debe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004de45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004de59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004debe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004dde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004dde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004dd05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004dd05`

## pseudocode

```c
char __fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::Match(
        __int64 a1,
        HSTRING a2,
        char **a3)
{
  int v6; // eax
  _QWORD *v7; // rbx
  __int64 v8; // r15
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // r12
  int v15; // r15d
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rax
  HRESULT v19; // eax
  _QWORD *v20; // rsi
  __int64 v21; // r15
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // r15
  int v28; // esi
  HSTRING v29; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  char *v33; // rsi
  __int64 v34; // rbx
  _QWORD *v35; // rcx
  _QWORD *v37; // rcx
  HSTRING string1; // [rsp+20h] [rbp-69h] BYREF
  _QWORD *v39; // [rsp+28h] [rbp-61h] BYREF
  INT32 result; // [rsp+30h] [rbp-59h] BYREF
  HSTRING v41; // [rsp+38h] [rbp-51h] BYREF
  __int64 v42; // [rsp+40h] [rbp-49h] BYREF
  __int64 v43; // [rsp+48h] [rbp-41h] BYREF
  char *v44; // [rsp+50h] [rbp-39h]
  __int64 v45; // [rsp+58h] [rbp-31h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-29h] BYREF
  HSTRING string; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER v48; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v49; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v45 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v39 = 0;
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))a1)(
         a1,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v39);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v6,
      (int)string1);
  v43 = 0;
  LODWORD(v44) = 0;
  v7 = v39;
  v8 = *v39;
  v41 = (HSTRING)&v43;
  v42 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"@GroupId", 8u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
LABEL_47:
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0x160,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v12,
      (int)string1);
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v8 + 48))(v7, string, &v42);
  v13 = retaddr;
  if ( v12 < 0 )
    goto LABEL_47;
  string = 0;
  RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v41);
  v14 = v43;
  v15 = (int)v44;
  WindowsDeleteString(0);
  string1 = 0;
  v16 = -2147316576;
  if ( v15 == 7 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 152LL))(v14, &string1);
  }
  else
  {
    v17 = -2147316576;
    if ( v15 < 0 )
      v17 = v15;
  }
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v17,
      (int)string1);
  result = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(HSTRING *)a2;
  v41 = a2;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v48, &v41);
  v19 = WindowsCompareStringOrdinal(string1, *(HSTRING *)(v18 + 24), &result);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v19,
      (int)string1);
  if ( !result )
  {
    v20 = v39;
    v21 = *v39;
    hstringHeader.Reserved.Reserved1 = &v43;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    v49 = 0;
    v22 = WindowsCreateStringReference(L"@Parameters", 0xBu, &v48, &v49);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    }
    else
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, char *))(v21 + 48))(
              v20,
              v49,
              &hstringHeader.Reserved.Reserved2[8]);
      v26 = retaddr;
      if ( v25 >= 0 )
      {
        v49 = 0;
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&hstringHeader);
        v41 = 0;
        v27 = v43;
        v28 = (int)v44;
        WindowsDeleteString(0);
        v29 = 0;
        v41 = 0;
        if ( v28 == 7 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 152LL))(v27, &v41);
          v29 = v41;
        }
        else if ( v28 < 0 )
        {
          v16 = v28;
        }
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x170,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
            (const char *)(unsigned int)v16,
            (int)string1);
        StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
        v32 = -1;
        do
          ++v32;
        while ( StringRawBuffer[v32] );
        if ( v32 > (unsigned __int64)a3[3] )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            a3,
            v32,
            v31,
            StringRawBuffer);
        }
        else
        {
          if ( (unsigned __int64)a3[3] <= 7 )
            v33 = (char *)a3;
          else
            v33 = *a3;
          a3[2] = (char *)v32;
          v34 = 2 * v32;
          memmove_0(v33, StringRawBuffer, 2 * v32);
          *(_WORD *)&v33[v34] = 0;
        }
        WindowsDeleteString(v41);
        v41 = 0;
        WindowsDeleteString(string1);
        string1 = 0;
        if ( v43 && (((_DWORD)v44 - 3) & 0xFFFFFFFB) == 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v35 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
        return 1;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v26,
      (void *)0x16D,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v25,
      (int)string1);
  }
  WindowsDeleteString(string1);
  string1 = 0;
  if ( v43 && (((_DWORD)v44 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v37 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18004db98  mov     [rsp-8+arg_0], rbx
0x18004db9d  push    rbp
0x18004db9e  push    rsi
0x18004db9f  push    rdi
0x18004dba0  push    r12
0x18004dba2  push    r13
0x18004dba4  push    r14
0x18004dba6  push    r15
0x18004dba8  lea     rbp, [rsp-27h]
0x18004dbad  sub     rsp, 0B0h
0x18004dbb4  mov     rax, cs:__security_cookie
0x18004dbbb  xor     rax, rsp
0x18004dbbe  mov     [rbp+57h+var_40], rax
0x18004dbc2  mov     r14, r8
0x18004dbc5  mov     rsi, rdx
0x18004dbc8  mov     rdi, rcx
0x18004dbcb  mov     [rbp+57h+var_88], rcx
0x18004dbcf  xor     r13d, r13d
0x18004dbd2  test    rcx, rcx
0x18004dbd5  jz      short loc_18004DBE4
0x18004dbd7  mov     rax, [rcx]
0x18004dbda  mov     rax, [rax+8]
0x18004dbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbe3  nop
0x18004dbe4  mov     [rbp+57h+var_B8], r13
0x18004dbe8  mov     rax, [rdi]
0x18004dbeb  lea     r8, [rbp+57h+var_B8]
0x18004dbef  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004dbf6  mov     rcx, rdi
0x18004dbf9  mov     rax, [rax]
0x18004dbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc01  nop
0x18004dc02  mov     rcx, [rbp+5Fh]; this
0x18004dc06  test    eax, eax
0x18004dc08  js      loc_18004DF5D
0x18004dc0e  mov     [rbp+57h+var_98], r13
0x18004dc12  mov     dword ptr [rbp+57h+var_90], r13d
0x18004dc16  mov     rbx, [rbp+57h+var_B8]
0x18004dc1a  mov     r15, [rbx]
0x18004dc1d  lea     rax, [rbp+57h+var_98]
0x18004dc21  mov     [rbp+57h+var_A8], rax
0x18004dc25  mov     [rbp+57h+var_A0], r13
0x18004dc29  mov     [rbp+57h+string], r13
0x18004dc2d  lea     r9, [rbp+57h+string]; string
0x18004dc31  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004dc35  mov     edx, 8; length
0x18004dc3a  lea     rcx, aGroupid; "@GroupId"
0x18004dc41  call    cs:__imp_WindowsCreateStringReference
0x18004dc48  nop     dword ptr [rax+rax+00h]
0x18004dc4d  test    eax, eax
0x18004dc4f  js      loc_18004DF72
0x18004dc55  lea     r8, [rbp+57h+var_A0]
0x18004dc59  mov     rdx, [rbp+57h+string]
0x18004dc5d  mov     rcx, rbx
0x18004dc60  mov     rax, [r15+30h]
0x18004dc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc69  mov     rcx, [rbp+5Fh]
0x18004dc6d  test    eax, eax
0x18004dc6f  js      loc_18004DF7A
0x18004dc75  mov     [rbp+57h+string], r13
0x18004dc79  lea     rcx, [rbp+57h+var_A8]; this
0x18004dc7d  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18004dc82  mov     [rbp+57h+string1], r13
0x18004dc86  mov     r12, [rbp+57h+var_98]
0x18004dc8a  mov     r15d, dword ptr [rbp+57h+var_90]
0x18004dc8e  xor     ecx, ecx; string
0x18004dc90  call    cs:__imp_WindowsDeleteString
0x18004dc97  nop     dword ptr [rax+rax+00h]
0x18004dc9c  mov     [rbp+57h+string1], r13
0x18004dca0  mov     ebx, 80028CA0h
0x18004dca5  cmp     r15d, 7
0x18004dca9  jz      short loc_18004DCB6
0x18004dcab  mov     eax, ebx
0x18004dcad  test    r15d, r15d
0x18004dcb0  cmovs   eax, r15d
0x18004dcb4  jmp     short loc_18004DCCD
0x18004dcb6  mov     rax, [r12]
0x18004dcba  lea     rdx, [rbp+57h+string1]
0x18004dcbe  mov     rcx, r12
0x18004dcc1  mov     rax, [rax+98h]
0x18004dcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dccd  mov     rcx, [rbp+5Fh]; this
0x18004dcd1  test    eax, eax
0x18004dcd3  js      loc_18004DF8F
0x18004dcd9  mov     [rbp+57h+result], r13d
0x18004dcdd  cmp     qword ptr [rsi+18h], 7
0x18004dce2  jbe     short loc_18004DCE7
0x18004dce4  mov     rsi, [rsi]
0x18004dce7  mov     [rbp+57h+var_A8], rsi
0x18004dceb  lea     rdx, [rbp+57h+var_A8]
0x18004dcef  lea     rcx, [rbp+57h+var_60]
0x18004dcf3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004dcf8  nop
0x18004dcf9  lea     r8, [rbp+57h+result]; result
0x18004dcfd  mov     rdx, [rax+18h]; string2
0x18004dd01  mov     rcx, [rbp+57h+string1]; string1
0x18004dd05  call    cs:__imp_WindowsCompareStringOrdinal
0x18004dd0c  nop     dword ptr [rax+rax+00h]
0x18004dd11  mov     rcx, [rbp+5Fh]; this
0x18004dd15  test    eax, eax
0x18004dd17  js      loc_18004DFA4
0x18004dd1d  cmp     [rbp+57h+result], r13d
0x18004dd21  jnz     loc_18004DEBA
0x18004dd27  mov     rsi, [rbp+57h+var_B8]
0x18004dd2b  mov     r15, [rsi]
0x18004dd2e  lea     rax, [rbp+57h+var_98]
0x18004dd32  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18004dd36  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x18004dd3a  mov     [rbp+57h+var_48], r13
0x18004dd3e  lea     r9, [rbp+57h+var_48]; string
0x18004dd42  lea     r8, [rbp+57h+var_60]; hstringHeader
0x18004dd46  mov     edx, 0Bh; length
0x18004dd4b  lea     rcx, aParameters_0; "@Parameters"
0x18004dd52  call    cs:__imp_WindowsCreateStringReference
0x18004dd59  nop     dword ptr [rax+rax+00h]
0x18004dd5e  test    eax, eax
0x18004dd60  js      loc_18004DFB9
0x18004dd66  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x18004dd6a  mov     rdx, [rbp+57h+var_48]
0x18004dd6e  mov     rcx, rsi
0x18004dd71  mov     rax, [r15+30h]
0x18004dd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd7a  mov     rcx, [rbp+5Fh]
0x18004dd7e  test    eax, eax
0x18004dd80  js      loc_18004DFC1
0x18004dd86  mov     [rbp+57h+var_48], r13
0x18004dd8a  lea     rcx, [rbp+57h+hstringHeader]; this
0x18004dd8e  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18004dd93  mov     [rbp+57h+var_A8], r13
0x18004dd97  mov     r15, [rbp+57h+var_98]
0x18004dd9b  mov     esi, dword ptr [rbp+57h+var_90]
0x18004dd9e  xor     ecx, ecx; string
0x18004dda0  call    cs:__imp_WindowsDeleteString
0x18004dda7  nop     dword ptr [rax+rax+00h]
0x18004ddac  mov     rcx, r13
0x18004ddaf  mov     [rbp+57h+var_A8], rcx
0x18004ddb3  cmp     esi, 7
0x18004ddb6  jz      short loc_18004DDBF
0x18004ddb8  test    esi, esi
0x18004ddba  cmovs   ebx, esi
0x18004ddbd  jmp     short loc_18004DDDB
0x18004ddbf  mov     rax, [r15]
0x18004ddc2  lea     rdx, [rbp+57h+var_A8]
0x18004ddc6  mov     rcx, r15
0x18004ddc9  mov     rax, [rax+98h]
0x18004ddd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddd5  mov     ebx, eax
0x18004ddd7  mov     rcx, [rbp+57h+var_A8]; string
0x18004dddb  mov     rax, [rbp+5Fh]
0x18004dddf  test    ebx, ebx
0x18004dde1  js      loc_18004DF45
0x18004dde7  xor     edx, edx; length
0x18004dde9  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ddf0  nop     dword ptr [rax+rax+00h]
0x18004ddf5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ddf9  inc     rdx
0x18004ddfc  cmp     [rax+rdx*2], r13w
0x18004de01  jnz     short loc_18004DDF9
0x18004de03  cmp     rdx, [r14+18h]
0x18004de07  ja      short loc_18004DE35
0x18004de09  cmp     qword ptr [r14+18h], 7
0x18004de0e  jbe     short loc_18004DE15
0x18004de10  mov     rsi, [r14]
0x18004de13  jmp     short loc_18004DE18
0x18004de15  mov     rsi, r14
0x18004de18  mov     [r14+10h], rdx
0x18004de1c  lea     rbx, [rdx+rdx]
0x18004de20  mov     r8, rbx; Size
0x18004de23  mov     rdx, rax; Src
0x18004de26  mov     rcx, rsi; void *
0x18004de29  call    memmove_0
0x18004de2e  mov     [rbx+rsi], r13w
0x18004de33  jmp     short loc_18004DE41
0x18004de35  mov     r9, rax
0x18004de38  mov     rcx, r14
0x18004de3b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18004de40  nop
0x18004de41  mov     rcx, [rbp+57h+var_A8]; string
0x18004de45  call    cs:__imp_WindowsDeleteString
0x18004de4c  nop     dword ptr [rax+rax+00h]
0x18004de51  mov     [rbp+57h+var_A8], r13
0x18004de55  mov     rcx, [rbp+57h+string1]; string
0x18004de59  call    cs:__imp_WindowsDeleteString
0x18004de60  nop     dword ptr [rax+rax+00h]
0x18004de65  mov     [rbp+57h+string1], r13
0x18004de69  mov     rcx, [rbp+57h+var_98]
0x18004de6d  test    rcx, rcx
0x18004de70  jz      short loc_18004DE8C
0x18004de72  mov     eax, dword ptr [rbp+57h+var_90]
0x18004de75  add     eax, 0FFFFFFFDh
0x18004de78  test    eax, 0FFFFFFFBh
0x18004de7d  jnz     short loc_18004DE8C
0x18004de7f  mov     rax, [rcx]
0x18004de82  mov     rax, [rax+10h]
0x18004de86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de8b  nop
0x18004de8c  mov     rcx, [rbp+57h+var_B8]
0x18004de90  test    rcx, rcx
0x18004de93  jz      short loc_18004DEA6
0x18004de95  mov     [rbp+57h+var_B8], r13
0x18004de99  mov     rax, [rcx]
0x18004de9c  mov     rax, [rax+10h]
0x18004dea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dea5  nop
0x18004dea6  mov     rax, [rdi]
0x18004dea9  mov     rcx, rdi
0x18004deac  mov     rax, [rax+10h]
0x18004deb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004deb5  nop
0x18004deb6  mov     al, 1
0x18004deb8  jmp     short loc_18004DF1D
0x18004deba  mov     rcx, [rbp+57h+string1]; string
0x18004debe  call    cs:__imp_WindowsDeleteString
0x18004dec5  nop     dword ptr [rax+rax+00h]
0x18004deca  mov     [rbp+57h+string1], r13
0x18004dece  mov     rcx, [rbp+57h+var_98]
0x18004ded2  test    rcx, rcx
0x18004ded5  jz      short loc_18004DEF1
0x18004ded7  mov     eax, dword ptr [rbp+57h+var_90]
0x18004deda  add     eax, 0FFFFFFFDh
0x18004dedd  test    eax, 0FFFFFFFBh
0x18004dee2  jnz     short loc_18004DEF1
0x18004dee4  mov     rax, [rcx]
0x18004dee7  mov     rax, [rax+10h]
0x18004deeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004def0  nop
0x18004def1  mov     rcx, [rbp+57h+var_B8]
0x18004def5  test    rcx, rcx
0x18004def8  jz      short loc_18004DF0B
0x18004defa  mov     [rbp+57h+var_B8], r13
0x18004defe  mov     rax, [rcx]
0x18004df01  mov     rax, [rax+10h]
0x18004df05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df0a  nop
0x18004df0b  mov     rax, [rdi]
0x18004df0e  mov     rcx, rdi
0x18004df11  mov     rax, [rax+10h]
0x18004df15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df1a  nop
0x18004df1b  xor     al, al
0x18004df1d  mov     rcx, [rbp+57h+var_40]
0x18004df21  xor     rcx, rsp; StackCookie
0x18004df24  call    __security_check_cookie
0x18004df29  mov     rbx, [rsp+0E0h+arg_0]
0x18004df31  add     rsp, 0B0h
0x18004df38  pop     r15
0x18004df3a  pop     r14
0x18004df3c  pop     r13
0x18004df3e  pop     r12
0x18004df40  pop     rdi
0x18004df41  pop     rsi
0x18004df42  pop     rbp
0x18004df43  retn
0x18004df45  mov     r9d, ebx; char *
0x18004df48  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004df4f  mov     edx, 170h; void *
0x18004df54  mov     rcx, rax; this
0x18004df57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004df5d  mov     r9d, eax; char *
0x18004df60  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004df67  mov     edx, 15Dh; void *
0x18004df6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004df72  mov     ecx, eax; this
0x18004df74  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004df79  nop
0x18004df7a  mov     r9d, eax; char *
0x18004df7d  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004df84  mov     edx, 160h; void *
0x18004df89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004df8f  mov     r9d, eax; char *
0x18004df92  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004df99  mov     edx, 163h; void *
0x18004df9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dfa4  mov     r9d, eax; char *
0x18004dfa7  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004dfae  mov     edx, 169h; void *
0x18004dfb3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dfb9  mov     ecx, eax; this
0x18004dfbb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004dfc0  nop
0x18004dfc1  mov     r9d, eax; char *
0x18004dfc4  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004dfcb  mov     edx, 16Dh; void *
0x18004dfd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
