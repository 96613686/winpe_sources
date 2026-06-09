# Rdp::Avenc::Umrdp::CRdpSharedMemoryClient::CRdpSharedMemoryClient(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x18001b164`
- end: `0x18001b57e`
- name: `??0CRdpSharedMemoryClient@Umrdp@Avenc@Rdp@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_K@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001737c`

## callees

- `0x180002058`
- `0x180006580`
- `0x18000d0ac`
- `0x180010c10`
- `0x18001155c`
- `0x180017b98`
- `0x180019998`
- `0x180019bf0`
- `0x18001b164`
- `0x180082e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b48f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b48f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4ef`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b3ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b3ca`
- `ntdll!NtOpenSection` at `0x18001b413`
- `ntdll!NtOpenSection` at `0x18001b413`
- `ntdll!RtlInitUnicodeString` at `0x18001b3e2`
- `ntdll!RtlInitUnicodeString` at `0x18001b3e2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b4bd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b4db`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b4bd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001b4db`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b44f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001b44f`

## string_xrefs

- `0x18001b2cb`: `Opening shared memory`
- `0x18001b569`: `Failed to open file mapping %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpSharedMemoryClient::CRdpSharedMemoryClient(
        __int64 a1,
        _QWORD *a2,
        void **a3,
        __int64 a4)
{
  void **v4; // r15
  const void **v6; // r13
  void **v7; // rsi
  void **v8; // rdi
  unsigned __int64 v9; // rax
  char *v10; // r12
  __int64 v11; // rbx
  unsigned __int64 v12; // rdx
  char *v13; // r12
  __int64 v14; // rbx
  void *v15; // rax
  void *v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  const WCHAR *v19; // rdx
  NTSTATUS v20; // ecx
  DWORD v21; // eax
  char *v22; // rdi
  NTSTATUS v23; // eax
  const void *v24; // rsi
  void *v25; // r15
  DWORD LastError; // ebx
  const void *v27; // r15
  DWORD v28; // ebx
  const char *v30; // rax
  const char *v31; // rax
  void *SectionHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  char *v34; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  void *v36; // [rsp+88h] [rbp-78h] BYREF
  void *v37; // [rsp+90h] [rbp-70h] BYREF
  const char *v38; // [rsp+98h] [rbp-68h] BYREF
  const char *v39; // [rsp+A0h] [rbp-60h] BYREF
  const void *v40; // [rsp+A8h] [rbp-58h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  PCWSTR SourceString[4]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v33 = a4;
  v4 = a3;
  v42 = a1;
  *(_QWORD *)a1 = 0;
  v6 = (const void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  v7 = (void **)(a1 + 16);
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 7;
  *(_WORD *)(a1 + 16) = 0;
  v8 = (void **)(a1 + 48);
  *(_OWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 7;
  *(_WORD *)(a1 + 48) = 0;
  if ( (_QWORD *)(a1 + 16) != a2 )
  {
    v9 = a2[2];
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    if ( v9 > *(_QWORD *)(a1 + 40) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        a1 + 16,
        v9,
        a3,
        a2);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 40) <= 7u )
        v10 = (char *)(a1 + 16);
      else
        v10 = (char *)*v7;
      *(_QWORD *)(a1 + 32) = v9;
      v11 = 2 * v9;
      memmove_0(v10, a2, 2 * v9);
      *(_WORD *)&v10[v11] = 0;
    }
  }
  if ( v8 != v4 )
  {
    v12 = (unsigned __int64)v4[2];
    if ( (unsigned __int64)v4[3] > 7 )
      v4 = (void **)*v4;
    if ( v12 > *(_QWORD *)(a1 + 72) )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        a1 + 48,
        v12,
        a3,
        v4);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 72) <= 7u )
        v13 = (char *)(a1 + 48);
      else
        v13 = (char *)*v8;
      *(_QWORD *)(a1 + 64) = v12;
      v14 = 2 * v12;
      memmove_0(v13, v4, 2 * v12);
      *(_WORD *)&v13[v14] = 0;
    }
  }
  *(_QWORD *)(a1 + 80) = v33;
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v33 = *(_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 72) <= 7u )
      v15 = (void *)(a1 + 48);
    else
      v15 = *v8;
    v36 = v15;
    if ( *(_QWORD *)(a1 + 40) <= 7u )
      v16 = (void *)(a1 + 16);
    else
      v16 = *v7;
    v37 = v16;
    v38 = "Opening shared memory";
    v39 = "Rdp::Avenc::Umrdp::CRdpSharedMemoryClient::CRdpSharedMemoryClient";
    LODWORD(SectionHandle) = 60;
    *(_QWORD *)&DestinationString.Length = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800ACDB6,
      (_DWORD)a3,
      a4,
      (__int64)&DestinationString,
      (__int64)&SectionHandle,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v33);
  }
  v17 = *(_QWORD *)(a1 + 32);
  v18 = *(_QWORD *)(a1 + 64);
  if ( 0x7FFFFFFFFFFFFFFELL - v17 < v18 )
    std::_Xlen_string();
  if ( *(_QWORD *)(a1 + 40) > 7u )
    v7 = (void **)*v7;
  if ( *(_QWORD *)(a1 + 72) > 7u )
    v8 = (void **)*v8;
  std::wstring::wstring(SourceString, v18, a3, v7, v17, v8, v18);
  v19 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v19 = SourceString[0];
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  SectionHandle = 0;
  if ( !v19 )
  {
    v20 = -1073741811;
LABEL_36:
    v21 = RtlNtStatusToDosErrorNoTeb(v20);
    SetLastError(v21);
    v22 = 0;
    goto LABEL_40;
  }
  RtlInitUnicodeString(&DestinationString, v19);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v23 = NtOpenSection(&SectionHandle, 6u, &ObjectAttributes);
  if ( v23 < 0 )
  {
    v20 = v23;
    goto LABEL_36;
  }
  v22 = (char *)SectionHandle;
LABEL_40:
  v34 = v22;
  if ( ((unsigned __int64)(v22 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v31 = (const char *)std::wstring::c_str(SourceString);
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp",
      "Failed to open file mapping %ls",
      v31);
  }
  v24 = MapViewOfFile(v22, 6u, 0, 0, *(_QWORD *)(a1 + 80));
  v40 = v24;
  if ( !v24 )
  {
    v30 = (const char *)std::wstring::c_str(SourceString);
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\sharedmemory.cpp",
      "Could not map view of file %ls",
      v30);
  }
  if ( (char **)a1 != &v34 )
  {
    v25 = *(void **)a1;
    if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v25);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v22;
    v22 = 0;
    v34 = 0;
  }
  if ( v6 != &v40 )
  {
    v27 = *v6;
    if ( *v6 )
    {
      v28 = GetLastError();
      UnmapViewOfFile(v27);
      SetLastError(v28);
    }
    *v6 = v24;
    v24 = 0;
  }
  if ( v24 )
    UnmapViewOfFile(v24);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v22);
  std::wstring::~wstring(SourceString);
  return a1;
}

```

## disassembly

```asm
0x18001b164  mov     [rsp-8+arg_18], rbx
0x18001b169  push    rbp
0x18001b16a  push    rsi
0x18001b16b  push    rdi
0x18001b16c  push    r12
0x18001b16e  push    r13
0x18001b170  push    r14
0x18001b172  push    r15
0x18001b174  lea     rbp, [rsp-10h]
0x18001b179  sub     rsp, 110h
0x18001b180  mov     rax, cs:__security_cookie
0x18001b187  xor     rax, rsp
0x18001b18a  mov     [rbp+40h+var_38], rax
0x18001b18e  mov     [rsp+140h+var_D8], r9
0x18001b193  mov     r15, r8
0x18001b196  mov     r14, rcx
0x18001b199  mov     [rbp+40h+var_60], rcx
0x18001b19d  xor     ecx, ecx
0x18001b19f  mov     [r14], rcx
0x18001b1a2  lea     r13, [r14+8]
0x18001b1a6  mov     [r13+0], rcx
0x18001b1aa  lea     rsi, [r14+10h]
0x18001b1ae  xorps   xmm0, xmm0
0x18001b1b1  movups  xmmword ptr [rsi], xmm0
0x18001b1b4  mov     [rsi+10h], rcx
0x18001b1b8  mov     qword ptr [rsi+18h], 7
0x18001b1c0  mov     [rsi], cx
0x18001b1c3  lea     rdi, [r14+30h]
0x18001b1c7  movups  xmmword ptr [rdi], xmm0
0x18001b1ca  mov     [rdi+10h], rcx
0x18001b1ce  mov     qword ptr [rdi+18h], 7
0x18001b1d6  mov     [rdi], cx
0x18001b1d9  cmp     rsi, rdx
0x18001b1dc  jz      short loc_18001B22B
0x18001b1de  mov     rax, [rdx+10h]
0x18001b1e2  cmp     qword ptr [rdx+18h], 7
0x18001b1e7  jbe     short loc_18001B1EC
0x18001b1e9  mov     rdx, [rdx]; Src
0x18001b1ec  cmp     rax, [rsi+18h]
0x18001b1f0  ja      short loc_18001B21D
0x18001b1f2  cmp     qword ptr [rsi+18h], 7
0x18001b1f7  jbe     short loc_18001B1FE
0x18001b1f9  mov     r12, [rsi]
0x18001b1fc  jmp     short loc_18001B201
0x18001b1fe  mov     r12, rsi
0x18001b201  mov     [rsi+10h], rax
0x18001b205  lea     rbx, [rax+rax]
0x18001b209  mov     r8, rbx; Size
0x18001b20c  mov     rcx, r12; void *
0x18001b20f  call    memmove_0
0x18001b214  xor     eax, eax
0x18001b216  mov     [r12+rbx], ax
0x18001b21b  jmp     short loc_18001B22B
0x18001b21d  mov     r9, rdx
0x18001b220  mov     rdx, rax
0x18001b223  mov     rcx, rsi
0x18001b226  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001b22b  cmp     rdi, r15
0x18001b22e  jz      short loc_18001B27D
0x18001b230  mov     rdx, [r15+10h]
0x18001b234  cmp     qword ptr [r15+18h], 7
0x18001b239  jbe     short loc_18001B23E
0x18001b23b  mov     r15, [r15]
0x18001b23e  cmp     rdx, [rdi+18h]
0x18001b242  ja      short loc_18001B272
0x18001b244  cmp     qword ptr [rdi+18h], 7
0x18001b249  jbe     short loc_18001B250
0x18001b24b  mov     r12, [rdi]
0x18001b24e  jmp     short loc_18001B253
0x18001b250  mov     r12, rdi
0x18001b253  mov     [rdi+10h], rdx
0x18001b257  lea     rbx, [rdx+rdx]
0x18001b25b  mov     r8, rbx; Size
0x18001b25e  mov     rdx, r15; Src
0x18001b261  mov     rcx, r12; void *
0x18001b264  call    memmove_0
0x18001b269  xor     eax, eax
0x18001b26b  mov     [r12+rbx], ax
0x18001b270  jmp     short loc_18001B27D
0x18001b272  mov     r9, r15
0x18001b275  mov     rcx, rdi
0x18001b278  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18001b27d  mov     rax, [rsp+140h+var_D8]
0x18001b282  mov     [r14+50h], rax
0x18001b286  mov     eax, cs:dword_1800C1058
0x18001b28c  lea     rbx, aOnecoreuapTerm_55; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001b293  cmp     eax, 4
0x18001b296  jbe     loc_18001B343
0x18001b29c  mov     rax, [r14+50h]
0x18001b2a0  mov     [rsp+140h+var_D8], rax
0x18001b2a5  cmp     qword ptr [rdi+18h], 7
0x18001b2aa  jbe     short loc_18001B2B1
0x18001b2ac  mov     rax, [rdi]
0x18001b2af  jmp     short loc_18001B2B4
0x18001b2b1  mov     rax, rdi
0x18001b2b4  mov     [rbp+40h+var_B8], rax
0x18001b2b8  cmp     qword ptr [rsi+18h], 7
0x18001b2bd  jbe     short loc_18001B2C4
0x18001b2bf  mov     rax, [rsi]
0x18001b2c2  jmp     short loc_18001B2C7
0x18001b2c4  mov     rax, rsi
0x18001b2c7  mov     [rbp+40h+var_B0], rax
0x18001b2cb  lea     rax, aOpeningSharedM; "Opening shared memory"
0x18001b2d2  mov     [rbp+40h+var_A8], rax
0x18001b2d6  lea     rax, aRdpAvencUmrdpC_1; "Rdp::Avenc::Umrdp::CRdpSharedMemoryClie"...
0x18001b2dd  mov     [rbp+40h+var_A0], rax
0x18001b2e1  mov     dword ptr [rsp+140h+SectionHandle], 3Ch ; '<'
0x18001b2e9  mov     qword ptr [rsp+140h+DestinationString.Length], rbx
0x18001b2ee  lea     rax, [rsp+140h+var_D8]
0x18001b2f3  mov     [rsp+140h+var_F0], rax
0x18001b2f8  lea     rax, [rbp+40h+var_B8]
0x18001b2fc  mov     [rsp+140h+var_F8], rax
0x18001b301  lea     rax, [rbp+40h+var_B0]
0x18001b305  mov     [rsp+140h+var_100], rax
0x18001b30a  lea     rax, [rbp+40h+var_A8]
0x18001b30e  mov     [rsp+140h+var_108], rax
0x18001b313  lea     rax, [rbp+40h+var_A0]
0x18001b317  mov     [rsp+140h+var_110], rax
0x18001b31c  lea     rax, [rsp+140h+SectionHandle]
0x18001b321  mov     [rsp+140h+var_118], rax
0x18001b326  lea     rax, [rsp+140h+DestinationString]
0x18001b32b  mov     [rsp+140h+dwNumberOfBytesToMap], rax
0x18001b330  lea     rdx, word_1800ACDB6
0x18001b337  lea     rcx, dword_1800C1058
0x18001b33e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18001b343  mov     rcx, [rsi+10h]
0x18001b347  mov     rdx, [rdi+10h]
0x18001b34b  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001b355  sub     rax, rcx
0x18001b358  cmp     rax, rdx
0x18001b35b  jb      loc_18001B551
0x18001b361  cmp     qword ptr [rsi+18h], 7
0x18001b366  jbe     short loc_18001B36B
0x18001b368  mov     rsi, [rsi]
0x18001b36b  cmp     qword ptr [rdi+18h], 7
0x18001b370  jbe     short loc_18001B375
0x18001b372  mov     rdi, [rdi]
0x18001b375  mov     [rsp+140h+var_110], rdx
0x18001b37a  mov     [rsp+140h+var_118], rdi
0x18001b37f  mov     [rsp+140h+dwNumberOfBytesToMap], rcx
0x18001b384  mov     r9, rsi
0x18001b387  lea     rcx, [rbp+40h+SourceString]
0x18001b38b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001b390  nop
0x18001b391  lea     rdx, [rbp+40h+SourceString]
0x18001b395  cmp     [rbp+40h+var_40], 7
0x18001b39a  cmova   rdx, [rbp+40h+SourceString]; SourceString
0x18001b39f  xorps   xmm0, xmm0
0x18001b3a2  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18001b3a6  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18001b3aa  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b3ae  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x18001b3b3  xor     r12d, r12d
0x18001b3b6  mov     [rsp+140h+SectionHandle], r12
0x18001b3bb  lea     esi, [r12+6]
0x18001b3c0  test    rdx, rdx
0x18001b3c3  jnz     short loc_18001B3DD
0x18001b3c5  mov     ecx, 0C000000Dh; Status
0x18001b3ca  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001b3d0  mov     ecx, eax; dwErrCode
0x18001b3d2  call    cs:__imp_SetLastError
0x18001b3d8  mov     rdi, r12
0x18001b3db  jmp     short loc_18001B426
0x18001b3dd  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x18001b3e2  call    cs:__imp_RtlInitUnicodeString
0x18001b3e8  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18001b3ef  mov     [rbp+40h+ObjectAttributes.RootDirectory], r12
0x18001b3f3  mov     [rbp+40h+ObjectAttributes.Attributes], r12d
0x18001b3f7  lea     rax, [rsp+140h+DestinationString]
0x18001b3fc  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18001b400  xorps   xmm0, xmm0
0x18001b403  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b408  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18001b40c  mov     edx, esi; DesiredAccess
0x18001b40e  lea     rcx, [rsp+140h+SectionHandle]; SectionHandle
0x18001b413  call    cs:__imp_NtOpenSection
0x18001b419  test    eax, eax
0x18001b41b  jns     short loc_18001B421
0x18001b41d  mov     ecx, eax
0x18001b41f  jmp     short loc_18001B3CA
0x18001b421  mov     rdi, [rsp+140h+SectionHandle]
0x18001b426  mov     [rsp+140h+var_D0], rdi
0x18001b42b  lea     rax, [rdi+1]
0x18001b42f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b435  jz      loc_18001B557
0x18001b43b  mov     rax, [r14+50h]
0x18001b43f  mov     [rsp+140h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x18001b444  xor     r9d, r9d; dwFileOffsetLow
0x18001b447  xor     r8d, r8d; dwFileOffsetHigh
0x18001b44a  mov     edx, esi; dwDesiredAccess
0x18001b44c  mov     rcx, rdi; hFileMappingObject
0x18001b44f  call    cs:__imp_MapViewOfFile
0x18001b455  mov     rsi, rax
0x18001b458  mov     [rbp+40h+var_98], rax
0x18001b45c  test    rax, rax
0x18001b45f  jz      loc_18001B52A
0x18001b465  lea     rax, [rsp+140h+var_D0]
0x18001b46a  cmp     r14, rax
0x18001b46d  jz      short loc_18001B4A0
0x18001b46f  mov     r15, [r14]
0x18001b472  lea     rax, [r15-1]
0x18001b476  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b47a  ja      short loc_18001B495
0x18001b47c  call    cs:__imp_GetLastError
0x18001b482  mov     ebx, eax
0x18001b484  mov     rcx, r15; hObject
0x18001b487  call    cs:__imp_CloseHandle
0x18001b48d  mov     ecx, ebx; dwErrCode
0x18001b48f  call    cs:__imp_SetLastError
0x18001b495  mov     [r14], rdi
0x18001b498  mov     rdi, r12
0x18001b49b  mov     [rsp+140h+var_D0], r12
0x18001b4a0  lea     rax, [rbp+40h+var_98]
0x18001b4a4  cmp     r13, rax
0x18001b4a7  jz      short loc_18001B4D3
0x18001b4a9  mov     r15, [r13+0]
0x18001b4ad  test    r15, r15
0x18001b4b0  jz      short loc_18001B4CC
0x18001b4b2  call    cs:__imp_GetLastError
0x18001b4b8  mov     ebx, eax
0x18001b4ba  mov     rcx, r15; lpBaseAddress
0x18001b4bd  call    cs:__imp_UnmapViewOfFile
0x18001b4c3  mov     ecx, ebx; dwErrCode
0x18001b4c5  call    cs:__imp_SetLastError
0x18001b4cb  nop
0x18001b4cc  mov     [r13+0], rsi
0x18001b4d0  mov     rsi, r12
0x18001b4d3  test    rsi, rsi
0x18001b4d6  jz      short loc_18001B4E2
0x18001b4d8  mov     rcx, rsi; lpBaseAddress
0x18001b4db  call    cs:__imp_UnmapViewOfFile
0x18001b4e1  nop
0x18001b4e2  lea     rdx, [rdi-1]
0x18001b4e6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001b4ea  ja      short loc_18001B4F6
0x18001b4ec  mov     rcx, rdi; hObject
0x18001b4ef  call    cs:__imp_CloseHandle
0x18001b4f5  nop
0x18001b4f6  lea     rcx, [rbp+40h+SourceString]
0x18001b4fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b4ff  nop
0x18001b500  mov     rax, r14
0x18001b503  mov     rcx, [rbp+40h+var_38]
0x18001b507  xor     rcx, rsp; StackCookie
0x18001b50a  call    __security_check_cookie
0x18001b50f  mov     rbx, [rsp+140h+arg_18]
0x18001b517  add     rsp, 110h
0x18001b51e  pop     r15
0x18001b520  pop     r14
0x18001b522  pop     r13
0x18001b524  pop     r12
0x18001b526  pop     rdi
0x18001b527  pop     rsi
0x18001b528  pop     rbp
0x18001b529  retn
0x18001b52a  lea     rcx, [rbp+40h+SourceString]
0x18001b52e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18001b533  mov     rcx, [rbp+48h]; this
0x18001b537  mov     [rsp+140h+dwNumberOfBytesToMap], rax; char *
0x18001b53c  lea     r9, aCouldNotMapVie; "Could not map view of file %ls"
0x18001b543  mov     r8, rbx; unsigned int
0x18001b546  mov     edx, 5Bh ; '['; void *
0x18001b54b  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001b551  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001b557  lea     rcx, [rbp+40h+SourceString]
0x18001b55b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18001b560  mov     rcx, [rbp+48h]; this
0x18001b564  mov     [rsp+140h+dwNumberOfBytesToMap], rax; char *
0x18001b569  lea     r9, aFailedToOpenFi; "Failed to open file mapping %ls"
0x18001b570  mov     r8, rbx; unsigned int
0x18001b573  mov     edx, 4Bh ; 'K'; void *
0x18001b578  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
