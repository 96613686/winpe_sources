# Rdp::Avenc::Umrdp::CRdpSharedMemoryServer::TryCreate(_SECURITY_ATTRIBUTES *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x18001b584`
- end: `0x18001b99a`
- name: `?TryCreate@CRdpSharedMemoryServer@Umrdp@Avenc@Rdp@@IEAA_NPEAU_SECURITY_ATTRIBUTES@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018194`

## callees

- `0x180002058`
- `0x180006580`
- `0x18000d0ac`
- `0x180010c10`
- `0x18001155c`
- `0x180017b98`
- `0x180019998`
- `0x180019bf0`
- `0x18001b584`
- `0x180082e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b7a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b808`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b7a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b808`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b8e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b89a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b89a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b840`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b90e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b840`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b90e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b7f0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b7f0`
- `ntdll!NtCreateSection` at `0x18001b7e4`
- `ntdll!NtCreateSection` at `0x18001b7e4`
- `ntdll!RtlInitUnicodeString` at `0x18001b757`
- `ntdll!RtlInitUnicodeString` at `0x18001b757`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b8dd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b8fa`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b8dd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b8fa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b86d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b86d`

## string_xrefs

- `0x18001b65b`: `Rdp::Avenc::Umrdp::CRdpSharedMemoryServer::TryCreate`
- `0x18001b981`: `Failed to create mapping %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Rdp::Avenc::Umrdp::CRdpSharedMemoryServer::TryCreate(
        __int64 a1,
        __int64 a2,
        const void **a3,
        union _LARGE_INTEGER a4)
{
  const void *v5; // r9
  char *v8; // rdi
  unsigned __int64 v9; // rdx
  char *v10; // r14
  __int64 v11; // rbx
  char *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // r9
  __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  const WCHAR *v17; // rdx
  DWORD v18; // ecx
  char *v19; // rdi
  int v20; // eax
  DWORD v21; // ecx
  const void *v23; // r14
  char *v24; // r15
  DWORD LastError; // ebx
  const void **v26; // rsi
  const void *v27; // r15
  DWORD v28; // ebx
  const char *v29; // rax
  const char *v30; // rax
  union _LARGE_INTEGER MaximumSize; // [rsp+60h] [rbp-A0h] BYREF
  void *SectionHandle; // [rsp+68h] [rbp-98h] BYREF
  char *v33; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  char *v35; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v36; // [rsp+90h] [rbp-70h] BYREF
  const char *v37; // [rsp+98h] [rbp-68h] BYREF
  const char *v38; // [rsp+A0h] [rbp-60h] BYREF
  const void *v39; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  PCWSTR SourceString[4]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v5 = a3;
  v8 = (char *)(a1 + 48);
  if ( (const void **)(a1 + 48) != a3 )
  {
    v9 = (unsigned __int64)a3[2];
    if ( (unsigned __int64)a3[3] > 7 )
      v5 = *a3;
    if ( v9 > *(_QWORD *)(a1 + 72) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        a1 + 48,
        v9,
        a3,
        v5);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 72) <= 7u )
        v10 = (char *)(a1 + 48);
      else
        v10 = *(char **)v8;
      *(_QWORD *)(a1 + 64) = v9;
      v11 = 2 * v9;
      memmove_0(v10, v5, 2 * v9);
      *(_WORD *)&v10[v11] = 0;
    }
  }
  *(union _LARGE_INTEGER *)(a1 + 80) = a4;
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    SectionHandle = *(void **)(a1 + 80);
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v12 = v8;
    else
      v12 = *(char **)v8;
    v35 = v12;
    v13 = (_QWORD *)(a1 + 16);
    if ( *(_QWORD *)(a1 + 40) > 7u )
      v13 = (_QWORD *)*v13;
    v36 = v13;
    v37 = "Creating shared memory";
    v38 = "Rdp::Avenc::Umrdp::CRdpSharedMemoryServer::TryCreate";
    MaximumSize.LowPart = 133;
    *(_QWORD *)&DestinationString.Length = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800ACD66,
      (_DWORD)a3,
      (_DWORD)v5,
      (__int64)&DestinationString,
      (__int64)&MaximumSize,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&SectionHandle);
  }
  v14 = (_QWORD *)(a1 + 16);
  v15 = *(_QWORD *)(a1 + 32);
  v16 = *((_QWORD *)v8 + 2);
  if ( 0x7FFFFFFFFFFFFFFELL - v15 < v16 )
    std::_Xlen_string();
  if ( *(_QWORD *)(a1 + 40) > 7u )
    v14 = (_QWORD *)*v14;
  if ( *((_QWORD *)v8 + 3) > 7u )
    v8 = *(char **)v8;
  std::wstring::wstring(SourceString, v16, a3, v14, v15, v8, v16);
  v17 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v17 = SourceString[0];
  SectionHandle = 0;
  MaximumSize.QuadPart = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v17);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = *(_DWORD *)(a2 + 16) != 0 ? 2 : 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = *(PVOID *)(a2 + 8);
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( !a4.QuadPart )
  {
    v18 = 87;
LABEL_26:
    SetLastError(v18);
    v19 = 0;
    goto LABEL_33;
  }
  MaximumSize = a4;
  v20 = NtCreateSection(&SectionHandle, 0xF0007u, &ObjectAttributes, &MaximumSize, 4u, 0x8000000u, 0);
  if ( v20 < 0 )
  {
    v18 = RtlNtStatusToDosErrorNoTeb(v20);
    goto LABEL_26;
  }
  if ( v20 == 0x40000000 )
    v21 = 183;
  else
    v21 = 0;
  SetLastError(v21);
  v19 = (char *)SectionHandle;
LABEL_33:
  v33 = v19;
  if ( ((unsigned __int64)(v19 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v23 = MapViewOfFile(v19, 6u, 0, 0, *(_QWORD *)(a1 + 80));
    v39 = v23;
    if ( !v23 )
    {
      v29 = (const char *)std::wstring::c_str(SourceString);
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp",
        "Could not map view of file %ls",
        v29);
    }
    if ( (char **)a1 != &v33 )
    {
      v24 = *(char **)a1;
      if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v24);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v19;
      v19 = 0;
      v33 = 0;
    }
    v26 = (const void **)(a1 + 8);
    if ( v26 != &v39 )
    {
      v27 = *v26;
      if ( *v26 )
      {
        v28 = GetLastError();
        UnmapViewOfFile(v27);
        SetLastError(v28);
      }
      *v26 = v23;
      v23 = 0;
    }
    if ( v23 )
      UnmapViewOfFile(v23);
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v19);
    std::wstring::~wstring(SourceString);
    return 1;
  }
  else
  {
    if ( GetLastError() != 183 )
    {
      v30 = (const char *)std::wstring::c_str(SourceString);
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp",
        "Failed to create mapping %ls",
        v30);
    }
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v19);
    std::wstring::~wstring(SourceString);
    return 0;
  }
}

```

## disassembly

```asm
0x18001b584  push    rbp
0x18001b586  push    rbx
0x18001b587  push    rsi
0x18001b588  push    rdi
0x18001b589  push    r13
0x18001b58b  push    r14
0x18001b58d  push    r15
0x18001b58f  lea     rbp, [rsp-10h]
0x18001b594  sub     rsp, 110h
0x18001b59b  mov     rax, cs:__security_cookie
0x18001b5a2  xor     rax, rsp
0x18001b5a5  mov     [rbp+40h+var_40], rax
0x18001b5a9  mov     r15, r9
0x18001b5ac  mov     r9, r8
0x18001b5af  mov     r13, rdx
0x18001b5b2  mov     rsi, rcx
0x18001b5b5  lea     rdi, [rcx+30h]
0x18001b5b9  cmp     rdi, r8
0x18001b5bc  jz      short loc_18001B608
0x18001b5be  mov     rdx, [r8+10h]
0x18001b5c2  cmp     qword ptr [r8+18h], 7
0x18001b5c7  jbe     short loc_18001B5CC
0x18001b5c9  mov     r9, [r8]
0x18001b5cc  cmp     rdx, [rdi+18h]
0x18001b5d0  ja      short loc_18001B600
0x18001b5d2  cmp     qword ptr [rdi+18h], 7
0x18001b5d7  jbe     short loc_18001B5DE
0x18001b5d9  mov     r14, [rdi]
0x18001b5dc  jmp     short loc_18001B5E1
0x18001b5de  mov     r14, rdi
0x18001b5e1  mov     [rdi+10h], rdx
0x18001b5e5  lea     rbx, [rdx+rdx]
0x18001b5e9  mov     r8, rbx; Size
0x18001b5ec  mov     rdx, r9; Src
0x18001b5ef  mov     rcx, r14; void *
0x18001b5f2  call    memmove_0
0x18001b5f7  xor     eax, eax
0x18001b5f9  mov     [rbx+r14], ax
0x18001b5fe  jmp     short loc_18001B608
0x18001b600  mov     rcx, rdi
0x18001b603  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001b608  mov     [rsi+50h], r15
0x18001b60c  mov     eax, cs:dword_1800C1058
0x18001b612  lea     rcx, aOnecoreuapTerm_55; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001b619  cmp     eax, 4
0x18001b61c  jbe     loc_18001B6C8
0x18001b622  mov     rax, [rsi+50h]
0x18001b626  mov     [rsp+140h+SectionHandle], rax
0x18001b62b  cmp     qword ptr [rdi+18h], 7
0x18001b630  jbe     short loc_18001B637
0x18001b632  mov     rax, [rdi]
0x18001b635  jmp     short loc_18001B63A
0x18001b637  mov     rax, rdi
0x18001b63a  mov     [rbp+40h+var_B8], rax
0x18001b63e  lea     rax, [rsi+10h]
0x18001b642  cmp     qword ptr [rax+18h], 7
0x18001b647  jbe     short loc_18001B64C
0x18001b649  mov     rax, [rax]
0x18001b64c  mov     [rbp+40h+var_B0], rax
0x18001b650  lea     rax, aCreatingShared; "Creating shared memory"
0x18001b657  mov     [rbp+40h+var_A8], rax
0x18001b65b  lea     rax, aRdpAvencUmrdpC_36; "Rdp::Avenc::Umrdp::CRdpSharedMemoryServ"...
0x18001b662  mov     [rbp+40h+var_A0], rax
0x18001b666  mov     dword ptr [rsp+140h+MaximumSize], 85h
0x18001b66e  mov     qword ptr [rsp+140h+DestinationString.Length], rcx
0x18001b673  lea     rax, [rsp+140h+SectionHandle]
0x18001b678  mov     [rsp+140h+var_F0], rax
0x18001b67d  lea     rax, [rbp+40h+var_B8]
0x18001b681  mov     [rsp+140h+var_F8], rax
0x18001b686  lea     rax, [rbp+40h+var_B0]
0x18001b68a  mov     [rsp+140h+var_100], rax
0x18001b68f  lea     rax, [rbp+40h+var_A8]
0x18001b693  mov     [rsp+140h+var_108], rax
0x18001b698  lea     rax, [rbp+40h+var_A0]
0x18001b69c  mov     [rsp+140h+FileHandle], rax
0x18001b6a1  lea     rax, [rsp+140h+MaximumSize]
0x18001b6a6  mov     qword ptr [rsp+140h+AllocationAttributes], rax
0x18001b6ab  lea     rax, [rsp+140h+DestinationString]
0x18001b6b0  mov     qword ptr [rsp+140h+SectionPageProtection], rax
0x18001b6b5  lea     rdx, word_1800ACD66
0x18001b6bc  lea     rcx, dword_1800C1058
0x18001b6c3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18001b6c8  lea     r9, [rsi+10h]
0x18001b6cc  mov     rcx, [r9+10h]
0x18001b6d0  mov     rdx, [rdi+10h]
0x18001b6d4  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001b6de  sub     rax, rcx
0x18001b6e1  cmp     rax, rdx
0x18001b6e4  jb      loc_18001B969
0x18001b6ea  cmp     qword ptr [r9+18h], 7
0x18001b6ef  jbe     short loc_18001B6F4
0x18001b6f1  mov     r9, [r9]
0x18001b6f4  cmp     qword ptr [rdi+18h], 7
0x18001b6f9  jbe     short loc_18001B6FE
0x18001b6fb  mov     rdi, [rdi]
0x18001b6fe  mov     [rsp+140h+FileHandle], rdx
0x18001b703  mov     qword ptr [rsp+140h+AllocationAttributes], rdi
0x18001b708  mov     qword ptr [rsp+140h+SectionPageProtection], rcx
0x18001b70d  lea     rcx, [rbp+40h+SourceString]
0x18001b711  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001b716  nop
0x18001b717  lea     rdx, [rbp+40h+SourceString]
0x18001b71b  cmp     [rbp+40h+var_48], 7
0x18001b720  cmova   rdx, [rbp+40h+SourceString]; SourceString
0x18001b725  mov     [rsp+140h+SectionHandle], 0
0x18001b72e  mov     qword ptr [rsp+140h+MaximumSize], 0
0x18001b737  xorps   xmm0, xmm0
0x18001b73a  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18001b73e  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18001b742  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b746  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x18001b74b  mov     rbx, r15
0x18001b74e  shr     rbx, 20h
0x18001b752  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x18001b757  call    cs:__imp_RtlInitUnicodeString
0x18001b75d  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18001b764  mov     [rbp+40h+ObjectAttributes.RootDirectory], 0
0x18001b76c  mov     eax, [r13+10h]
0x18001b770  neg     eax
0x18001b772  sbb     ecx, ecx
0x18001b774  and     ecx, 2
0x18001b777  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x18001b77a  lea     rax, [rsp+140h+DestinationString]
0x18001b77f  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18001b783  mov     rax, [r13+8]
0x18001b787  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rax
0x18001b78b  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], 0
0x18001b793  mov     r14d, 0B7h
0x18001b799  test    r15d, r15d
0x18001b79c  jnz     short loc_18001B7AF
0x18001b79e  test    ebx, ebx
0x18001b7a0  jnz     short loc_18001B7AF
0x18001b7a2  lea     ecx, [rbx+57h]; dwErrCode
0x18001b7a5  call    cs:__imp_SetLastError
0x18001b7ab  xor     edi, edi
0x18001b7ad  jmp     short loc_18001B813
0x18001b7af  lea     r9, [rsp+140h+MaximumSize]; MaximumSize
0x18001b7b4  mov     dword ptr [rsp+140h+MaximumSize], r15d
0x18001b7b9  mov     dword ptr [rsp+140h+MaximumSize+4], ebx
0x18001b7bd  mov     [rsp+140h+FileHandle], 0; FileHandle
0x18001b7c6  mov     [rsp+140h+AllocationAttributes], 8000000h; AllocationAttributes
0x18001b7ce  mov     [rsp+140h+SectionPageProtection], 4; SectionPageProtection
0x18001b7d6  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18001b7da  mov     edx, 0F0007h; DesiredAccess
0x18001b7df  lea     rcx, [rsp+140h+SectionHandle]; SectionHandle
0x18001b7e4  call    cs:__imp_NtCreateSection
0x18001b7ea  test    eax, eax
0x18001b7ec  jns     short loc_18001B7FA
0x18001b7ee  mov     ecx, eax; Status
0x18001b7f0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001b7f6  mov     ecx, eax
0x18001b7f8  jmp     short loc_18001B7A5
0x18001b7fa  cmp     eax, 40000000h
0x18001b7ff  jnz     short loc_18001B806
0x18001b801  mov     ecx, r14d
0x18001b804  jmp     short loc_18001B808
0x18001b806  xor     ecx, ecx; dwErrCode
0x18001b808  call    cs:__imp_SetLastError
0x18001b80e  mov     rdi, [rsp+140h+SectionHandle]
0x18001b813  mov     [rsp+140h+var_D0], rdi
0x18001b818  lea     rax, [rdi+1]
0x18001b81c  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b822  jnz     short loc_18001B857
0x18001b824  call    cs:__imp_GetLastError
0x18001b82a  cmp     eax, r14d
0x18001b82d  jnz     loc_18001B96F
0x18001b833  lea     rax, [rdi-1]
0x18001b837  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b83b  ja      short loc_18001B847
0x18001b83d  mov     rcx, rdi; hObject
0x18001b840  call    cs:__imp_CloseHandle
0x18001b846  nop
0x18001b847  lea     rcx, [rbp+40h+SourceString]
0x18001b84b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b850  xor     al, al
0x18001b852  jmp     loc_18001B920
0x18001b857  mov     rax, [rsi+50h]
0x18001b85b  mov     qword ptr [rsp+140h+SectionPageProtection], rax; dwNumberOfBytesToMap
0x18001b860  xor     r9d, r9d; dwFileOffsetLow
0x18001b863  xor     r8d, r8d; dwFileOffsetHigh
0x18001b866  lea     edx, [r9+6]; dwDesiredAccess
0x18001b86a  mov     rcx, rdi; hFileMappingObject
0x18001b86d  call    cs:__imp_MapViewOfFile
0x18001b873  mov     r14, rax
0x18001b876  mov     [rbp+40h+var_98], rax
0x18001b87a  test    rax, rax
0x18001b87d  jz      loc_18001B93E
0x18001b883  lea     rax, [rsp+140h+var_D0]
0x18001b888  cmp     rsi, rax
0x18001b88b  jz      short loc_18001B8BD
0x18001b88d  mov     r15, [rsi]
0x18001b890  lea     rax, [r15-1]
0x18001b894  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b898  ja      short loc_18001B8B3
0x18001b89a  call    cs:__imp_GetLastError
0x18001b8a0  mov     ebx, eax
0x18001b8a2  mov     rcx, r15; hObject
0x18001b8a5  call    cs:__imp_CloseHandle
0x18001b8ab  mov     ecx, ebx; dwErrCode
0x18001b8ad  call    cs:__imp_SetLastError
0x18001b8b3  mov     [rsi], rdi
0x18001b8b6  xor     edi, edi
0x18001b8b8  mov     [rsp+140h+var_D0], rdi
0x18001b8bd  add     rsi, 8
0x18001b8c1  lea     rax, [rbp+40h+var_98]
0x18001b8c5  cmp     rsi, rax
0x18001b8c8  jz      short loc_18001B8F2
0x18001b8ca  mov     r15, [rsi]
0x18001b8cd  test    r15, r15
0x18001b8d0  jz      short loc_18001B8EC
0x18001b8d2  call    cs:__imp_GetLastError
0x18001b8d8  mov     ebx, eax
0x18001b8da  mov     rcx, r15; lpBaseAddress
0x18001b8dd  call    cs:__imp_UnmapViewOfFile
0x18001b8e3  mov     ecx, ebx; dwErrCode
0x18001b8e5  call    cs:__imp_SetLastError
0x18001b8eb  nop
0x18001b8ec  mov     [rsi], r14
0x18001b8ef  xor     r14d, r14d
0x18001b8f2  test    r14, r14
0x18001b8f5  jz      short loc_18001B901
0x18001b8f7  mov     rcx, r14; lpBaseAddress
0x18001b8fa  call    cs:__imp_UnmapViewOfFile
0x18001b900  nop
0x18001b901  lea     rax, [rdi-1]
0x18001b905  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b909  ja      short loc_18001B915
0x18001b90b  mov     rcx, rdi; hObject
0x18001b90e  call    cs:__imp_CloseHandle
0x18001b914  nop
0x18001b915  lea     rcx, [rbp+40h+SourceString]
0x18001b919  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b91e  mov     al, 1
0x18001b920  mov     rcx, [rbp+40h+var_40]
0x18001b924  xor     rcx, rsp; StackCookie
0x18001b927  call    __security_check_cookie
0x18001b92c  add     rsp, 110h
0x18001b933  pop     r15
0x18001b935  pop     r14
0x18001b937  pop     r13
0x18001b939  pop     rdi
0x18001b93a  pop     rsi
0x18001b93b  pop     rbx
0x18001b93c  pop     rbp
0x18001b93d  retn
0x18001b93e  lea     rcx, [rbp+40h+SourceString]
0x18001b942  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18001b947  mov     rcx, [rbp+48h]; this
0x18001b94b  mov     qword ptr [rsp+140h+SectionPageProtection], rax; char *
0x18001b950  lea     r9, aCouldNotMapVie; "Could not map view of file %ls"
0x18001b957  lea     r8, aOnecoreuapTerm_55; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001b95e  mov     edx, 0B2h; void *
0x18001b963  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001b969  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001b96f  lea     rcx, [rbp+40h+SourceString]
0x18001b973  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18001b978  mov     rcx, [rbp+48h]; this
0x18001b97c  mov     qword ptr [rsp+140h+SectionPageProtection], rax; char *
0x18001b981  lea     r9, aFailedToCreate_2; "Failed to create mapping %ls"
0x18001b988  lea     r8, aOnecoreuapTerm_55; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001b98f  mov     edx, 0A2h; void *
0x18001b994  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
