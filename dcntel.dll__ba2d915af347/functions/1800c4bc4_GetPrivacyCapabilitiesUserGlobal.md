# GetPrivacyCapabilitiesUserGlobal

- ea: `0x1800c4bc4`
- end: `0x1800c4eb9`
- name: `GetPrivacyCapabilitiesUserGlobal`
- size: `757`
- prototype: `__int64 __fastcall(struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008f360`
- `0x1800cff70`

## callees

- `0x180008da4`
- `0x180008dc0`
- `0x180011cc4`
- `0x18009f918`
- `0x1800c3870`
- `0x1800c3af8`
- `0x1800c4bc4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c4d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c4d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4d19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4d24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4d86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4d24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4d86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4e47`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4c4b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4cab`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4da8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4e69`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4e7f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4c4b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4cab`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4da8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4e69`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800c4e7f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800c4c27`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800c4c27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c4c84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c4c84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c4cf6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c4cf6`

## string_xrefs

- `0x1800c4d50`: `onecore\base\appcompat\programs\devicecensus\dlls\privacysettingspriv.cpp`
- `0x1800c4c61`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetPrivacyCapabilitiesUserGlobal(
        struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4)
{
  _WORD *v4; // r14
  __int64 v6; // rdx
  _WORD *v7; // rax
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  Delayed::HStringReference *v14; // rax
  __int64 v15; // rdx
  int ActivationFactory; // edi
  wil *v17; // rcx
  BOOL v18; // eax
  const char *v19; // r9
  LPWSTR v20; // r13
  _QWORD *v21; // r14
  HLOCAL v22; // r15
  DWORD LastError; // edi
  __int64 v24; // rdx
  unsigned int v25; // edi
  void *v26; // rcx
  __int64 v27; // rdx
  unsigned __int64 i; // rdi
  _WORD *v29; // r14
  void *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // [rsp+20h] [rbp-A8h]
  BOOL v34; // [rsp+24h] [rbp-A4h]
  unsigned int v35; // [rsp+24h] [rbp-A4h]
  void *Block; // [rsp+28h] [rbp-A0h] BYREF
  wil *v37; // [rsp+30h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-90h] BYREF
  _WORD *v39; // [rsp+40h] [rbp-88h]
  HLOCAL *p_hMem; // [rsp+48h] [rbp-80h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-78h] BYREF
  wchar_t *v42; // [rsp+58h] [rbp-70h]
  _WORD *v43; // [rsp+60h] [rbp-68h]
  struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *v44; // [rsp+68h] [rbp-60h]
  _BYTE v45[32]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a4;
  v39 = a4;
  v6 = 31;
  v7 = a4;
  do
  {
    *v7++ = -1;
    --v6;
  }
  while ( v6 );
  if ( !*((_QWORD *)a1 + 2) )
    return 2147500033LL;
  v8 = -2147221008;
  v33 = -2147221008;
  v9 = RoInitialize(1);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -2147417850 )
      goto LABEL_51;
  }
  else
  {
    v8 = v9;
    v33 = v9;
  }
  if ( v9 < 0 )
  {
    if ( v8 >= 0 )
      RoUninitialize(v11, v10);
    return v12;
  }
LABEL_51:
  try
  {
    v37 = 0;
    v14 = Delayed::HStringReference::HStringReference(
            (Delayed::HStringReference *)&p_hMem,
            a1,
            L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager");
    ActivationFactory = RoGetActivationFactory(*(_QWORD *)v14, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v37);
    if ( ActivationFactory >= 0 )
    {
      hMem = 0;
      wil::GetTokenInformation<_TOKEN_USER>(&Block, v15);
      p_hMem = &hMem;
      StringSid = 0;
      LOBYTE(v42) = 1;
      v18 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
      v34 = v18;
      if ( (_BYTE)v42 )
      {
        v20 = StringSid;
        v21 = p_hMem;
        v22 = *p_hMem;
        if ( *p_hMem )
        {
          LastError = GetLastError();
          LocalFree(v22);
          SetLastError(LastError);
          v18 = v34;
        }
        *v21 = v20;
        v4 = v39;
      }
      if ( v18 )
      {
        Delayed::HStringReference::HStringReference(
          (Delayed::HStringReference *)v45,
          a1,
          (const unsigned __int16 *)hMem);
        for ( i = 0; i < 0x1F; ++i )
        {
          v29 = &v4[i];
          p_hMem = (HLOCAL *)&v37;
          StringSid = (LPWSTR)v45;
          v42 = off_1801A3260[i];
          v43 = v29;
          v44 = a1;
          if ( (int)lambda_6812e73b48d3fd891febadada26db3e6_::operator()(&p_hMem) < 0 )
            *v29 = -1;
          v4 = v39;
        }
        v30 = Block;
        Block = 0;
        if ( v30 )
          operator delete(v30);
        if ( hMem )
          LocalFree(hMem);
        v17 = v37;
        if ( v37 )
          (*(void (__fastcall **)(wil *))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v8 >= 0 )
        {
          RoUninitialize(v17, v27);
          v33 = -2147221008;
        }
        result = 0;
      }
      else
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1D7,
                (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\privacysettingspriv.cpp",
                v19);
        v26 = Block;
        Block = 0;
        if ( v26 )
          operator delete(v26);
        if ( hMem )
          LocalFree(hMem);
        v17 = v37;
        if ( v37 )
          (*(void (__fastcall **)(wil *))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v8 >= 0 )
        {
          RoUninitialize(v17, v24);
          v33 = -2147221008;
        }
        result = v25;
      }
    }
    else
    {
      v17 = v37;
      if ( v37 )
        (*(void (__fastcall **)(wil *, _QWORD))(*(_QWORD *)v37 + 16LL))(v37, *(_QWORD *)v37);
      if ( v8 >= 0 )
      {
        RoUninitialize(v17, v15);
        v33 = -2147221008;
      }
      result = (unsigned int)ActivationFactory;
    }
  }
  catch ( ... )
  {
    v35 = wil::ResultFromCaughtException(v17);
    if ( v33 >= 0 )
      RoUninitialize(v32, v31);
    return v35;
  }
  return result;
}

```

## disassembly

```asm
0x1800c4bc4  mov     [rsp+arg_8], rbx
0x1800c4bc9  push    rdi
0x1800c4bca  push    r12
0x1800c4bcc  push    r13
0x1800c4bce  push    r14
0x1800c4bd0  push    r15
0x1800c4bd2  sub     rsp, 0A0h
0x1800c4bd9  mov     rax, cs:__security_cookie
0x1800c4be0  xor     rax, rsp
0x1800c4be3  mov     [rsp+0C8h+var_38], rax
0x1800c4beb  mov     r14, r9
0x1800c4bee  mov     [rsp+0C8h+var_88], r9
0x1800c4bf3  mov     r12, rcx
0x1800c4bf6  mov     edx, 1Fh
0x1800c4bfb  mov     rax, r9
0x1800c4bfe  mov     word ptr [rax], 0FFFFh
0x1800c4c03  lea     rax, [rax+2]
0x1800c4c07  sub     rdx, 1
0x1800c4c0b  jnz     short loc_1800C4BFE
0x1800c4c0d  cmp     [rcx+10h], rdx
0x1800c4c11  jz      loc_1800C4E8B
0x1800c4c17  mov     r15d, 800401F0h
0x1800c4c1d  mov     ebx, r15d
0x1800c4c20  mov     [rsp+0C8h+var_A8], ebx
0x1800c4c24  lea     ecx, [rdx+1]
0x1800c4c27  call    cs:__imp_RoInitialize
0x1800c4c2d  mov     edi, eax
0x1800c4c2f  test    eax, eax
0x1800c4c31  js      short loc_1800C4C3B
0x1800c4c33  mov     ebx, eax
0x1800c4c35  mov     [rsp+0C8h+var_A8], eax
0x1800c4c39  jmp     short loc_1800C4C43
0x1800c4c3b  cmp     edi, 80010106h
0x1800c4c41  jz      short loc_1800C4C58
0x1800c4c43  test    edi, edi
0x1800c4c45  jns     short loc_1800C4C58
0x1800c4c47  test    ebx, ebx
0x1800c4c49  js      short loc_1800C4C51
0x1800c4c4b  call    cs:__imp_RoUninitialize
0x1800c4c51  mov     eax, edi
0x1800c4c53  jmp     loc_1800C4E90
0x1800c4c58  mov     [rsp+0C8h+var_98], 0
0x1800c4c61  lea     r8, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x1800c4c68  mov     rdx, r12; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800c4c6b  lea     rcx, [rsp+0C8h+var_80]; this
0x1800c4c70  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800c4c75  lea     r8, [rsp+0C8h+var_98]
0x1800c4c7a  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x1800c4c81  mov     rcx, [rax]
0x1800c4c84  call    cs:__imp_RoGetActivationFactory
0x1800c4c8a  mov     edi, eax
0x1800c4c8c  test    eax, eax
0x1800c4c8e  jns     short loc_1800C4CBD
0x1800c4c90  mov     rcx, [rsp+0C8h+var_98]
0x1800c4c95  test    rcx, rcx
0x1800c4c98  jz      short loc_1800C4CA7
0x1800c4c9a  mov     rdx, [rcx]
0x1800c4c9d  mov     rax, [rdx+10h]
0x1800c4ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ca6  nop
0x1800c4ca7  test    ebx, ebx
0x1800c4ca9  js      short loc_1800C4CB6
0x1800c4cab  call    cs:__imp_RoUninitialize
0x1800c4cb1  mov     [rsp+0C8h+var_A8], r15d
0x1800c4cb6  mov     eax, edi
0x1800c4cb8  jmp     loc_1800C4E90
0x1800c4cbd  mov     [rsp+0C8h+hMem], 0
0x1800c4cc6  lea     rcx, [rsp+0C8h+Block]
0x1800c4ccb  call    ??$GetTokenInformation@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x1800c4cd0  nop
0x1800c4cd1  lea     rax, [rsp+0C8h+hMem]
0x1800c4cd6  mov     [rsp+0C8h+var_80], rax
0x1800c4cdb  mov     [rsp+0C8h+StringSid], 0
0x1800c4ce4  mov     byte ptr [rsp+0C8h+var_70], 1
0x1800c4ce9  lea     rdx, [rsp+0C8h+StringSid]; StringSid
0x1800c4cee  mov     rcx, [rsp+0C8h+Block]
0x1800c4cf3  mov     rcx, [rcx]; Sid
0x1800c4cf6  call    cs:__imp_ConvertSidToStringSidW
0x1800c4cfc  mov     [rsp+0C8h+var_A4], eax
0x1800c4d00  cmp     byte ptr [rsp+0C8h+var_70], 0
0x1800c4d05  jz      short loc_1800C4D44
0x1800c4d07  mov     r13, [rsp+0C8h+StringSid]
0x1800c4d0c  mov     r14, [rsp+0C8h+var_80]
0x1800c4d11  mov     r15, [r14]
0x1800c4d14  test    r15, r15
0x1800c4d17  jz      short loc_1800C4D36
0x1800c4d19  call    cs:__imp_GetLastError
0x1800c4d1f  mov     edi, eax
0x1800c4d21  mov     rcx, r15; hMem
0x1800c4d24  call    cs:__imp_LocalFree
0x1800c4d2a  mov     ecx, edi; dwErrCode
0x1800c4d2c  call    cs:__imp_SetLastError
0x1800c4d32  mov     eax, [rsp+0C8h+var_A4]
0x1800c4d36  mov     [r14], r13
0x1800c4d39  mov     r14, [rsp+0C8h+var_88]
0x1800c4d3e  mov     r15d, 800401F0h
0x1800c4d44  test    eax, eax
0x1800c4d46  jnz     short loc_1800C4DBA
0x1800c4d48  mov     rcx, [rsp+0C8h]; this
0x1800c4d50  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appcompat\\programs\\dev"...
0x1800c4d57  mov     edx, 1D7h; void *
0x1800c4d5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c4d61  mov     edi, eax
0x1800c4d63  mov     rcx, [rsp+0C8h+Block]; Block
0x1800c4d68  mov     [rsp+0C8h+Block], 0
0x1800c4d71  test    rcx, rcx
0x1800c4d74  jz      short loc_1800C4D7C
0x1800c4d76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c4d7b  nop
0x1800c4d7c  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800c4d81  test    rcx, rcx
0x1800c4d84  jz      short loc_1800C4D8D
0x1800c4d86  call    cs:__imp_LocalFree
0x1800c4d8c  nop
0x1800c4d8d  mov     rcx, [rsp+0C8h+var_98]
0x1800c4d92  test    rcx, rcx
0x1800c4d95  jz      short loc_1800C4DA4
0x1800c4d97  mov     rax, [rcx]
0x1800c4d9a  mov     rax, [rax+10h]
0x1800c4d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4da3  nop
0x1800c4da4  test    ebx, ebx
0x1800c4da6  js      short loc_1800C4DB3
0x1800c4da8  call    cs:__imp_RoUninitialize
0x1800c4dae  mov     [rsp+0C8h+var_A8], r15d
0x1800c4db3  mov     eax, edi
0x1800c4db5  jmp     loc_1800C4E90
0x1800c4dba  mov     r8, [rsp+0C8h+hMem]; unsigned __int16 *
0x1800c4dbf  mov     rdx, r12; struct Delayed::api_ms_win_core_winrt_string_l1_1_0 *
0x1800c4dc2  lea     rcx, [rsp+0C8h+var_58]; this
0x1800c4dc7  call    ??0HStringReference@Delayed@@QEAA@AEBVapi_ms_win_core_winrt_string_l1_1_0@1@PEBG@Z; Delayed::HStringReference::HStringReference(Delayed::api_ms_win_core_winrt_string_l1_1_0 const &,ushort const *)
0x1800c4dcc  xor     edi, edi
0x1800c4dce  cmp     rdi, 1Fh
0x1800c4dd2  jnb     short loc_1800C4E24
0x1800c4dd4  lea     r14, [r14+rdi*2]
0x1800c4dd8  lea     rax, [rsp+0C8h+var_98]
0x1800c4ddd  mov     [rsp+0C8h+var_80], rax
0x1800c4de2  lea     rax, [rsp+0C8h+var_58]
0x1800c4de7  mov     [rsp+0C8h+StringSid], rax
0x1800c4dec  lea     rax, off_1801A3260; "activity"
0x1800c4df3  mov     rax, [rax+rdi*8]
0x1800c4df7  mov     [rsp+0C8h+var_70], rax
0x1800c4dfc  mov     [rsp+0C8h+var_68], r14
0x1800c4e01  mov     [rsp+0C8h+var_60], r12
0x1800c4e06  lea     rcx, [rsp+0C8h+var_80]
0x1800c4e0b  call    _lambda_6812e73b48d3fd891febadada26db3e6___operator__
0x1800c4e10  test    eax, eax
0x1800c4e12  jns     short loc_1800C4E1A
0x1800c4e14  mov     word ptr [r14], 0FFFFh
0x1800c4e1a  inc     rdi
0x1800c4e1d  mov     r14, [rsp+0C8h+var_88]
0x1800c4e22  jmp     short loc_1800C4DCE
0x1800c4e24  mov     rcx, [rsp+0C8h+Block]; Block
0x1800c4e29  mov     [rsp+0C8h+Block], 0
0x1800c4e32  test    rcx, rcx
0x1800c4e35  jz      short loc_1800C4E3D
0x1800c4e37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c4e3c  nop
0x1800c4e3d  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800c4e42  test    rcx, rcx
0x1800c4e45  jz      short loc_1800C4E4E
0x1800c4e47  call    cs:__imp_LocalFree
0x1800c4e4d  nop
0x1800c4e4e  mov     rcx, [rsp+0C8h+var_98]
0x1800c4e53  test    rcx, rcx
0x1800c4e56  jz      short loc_1800C4E65
0x1800c4e58  mov     rax, [rcx]
0x1800c4e5b  mov     rax, [rax+10h]
0x1800c4e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e64  nop
0x1800c4e65  test    ebx, ebx
0x1800c4e67  js      short loc_1800C4E74
0x1800c4e69  call    cs:__imp_RoUninitialize
0x1800c4e6f  mov     [rsp+0C8h+var_A8], r15d
0x1800c4e74  xor     eax, eax
0x1800c4e76  jmp     short loc_1800C4E90
0x1800c4e78  cmp     [rsp+0C8h+var_A8], 0
0x1800c4e7d  jl      short loc_1800C4E85
0x1800c4e7f  call    cs:__imp_RoUninitialize
0x1800c4e85  mov     eax, [rsp+0C8h+var_A4]
0x1800c4e89  jmp     short loc_1800C4E90
0x1800c4e8b  mov     eax, 80004001h
0x1800c4e90  mov     rcx, [rsp+0C8h+var_38]
0x1800c4e98  xor     rcx, rsp; StackCookie
0x1800c4e9b  call    __security_check_cookie
0x1800c4ea0  mov     rbx, [rsp+0C8h+arg_8]
0x1800c4ea8  add     rsp, 0A0h
0x1800c4eaf  pop     r15
0x1800c4eb1  pop     r14
0x1800c4eb3  pop     r13
0x1800c4eb5  pop     r12
0x1800c4eb7  pop     rdi
0x1800c4eb8  retn
```
