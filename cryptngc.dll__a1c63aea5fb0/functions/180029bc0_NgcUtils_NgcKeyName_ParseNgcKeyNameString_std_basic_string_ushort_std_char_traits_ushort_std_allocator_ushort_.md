# NgcUtils::NgcKeyName::ParseNgcKeyNameString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> *,_GUID *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180029bc0`
- end: `0x18002a226`
- name: `?ParseNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@EV?$allocator@E@std@@@4@PEAU_GUID@@PEAV34@33@Z`
- size: `1638`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800295f0`
- `0x1800332c0`

## callees

- `0x18000edb0`
- `0x1800158e0`
- `0x180018430`
- `0x18001bb24`
- `0x180029aec`
- `0x180029bc0`
- `0x18002d4d0`
- `0x180042354`
- `0x1800426c4`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029d6d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029d6d`
- `RPCRT4!UuidFromStringW` at `0x180029e87`
- `RPCRT4!UuidFromStringW` at `0x180029e87`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029cfb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029cfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcUtils::NgcKeyName::ParseNgcKeyNameString(
        _QWORD *a1,
        __int64 a2,
        UUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD *v8; // rdi
  unsigned __int64 v9; // rdx
  int *v10; // rdx
  __int64 v11; // rsi
  DWORD LengthSid; // r15d
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  BOOL v16; // ebx
  signed int LastError; // eax
  unsigned int v18; // ebx
  PSID v19; // rcx
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rdx
  PSID v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // r14
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  RPC_STATUS v27; // eax
  __int64 v28; // rbx
  unsigned __int64 v29; // rdx
  char *v30; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rbx
  unsigned __int64 v35; // rdx
  __int16 *v36; // rdx
  _QWORD *v37; // rcx
  __int64 v38; // rsi
  __int64 v39; // rax
  unsigned __int64 v40; // rsi
  _QWORD *v41; // rcx
  __int64 v42; // rax
  PSID v43; // rcx
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  PSID pSid; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-C0h]
  __int64 v47; // [rsp+48h] [rbp-B8h]
  PSID *p_pSid; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  char v50; // [rsp+60h] [rbp-A0h]
  RPC_WSTR StringUuid[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v52[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v53[32]; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR StringSid[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v56[32]; // [rsp+100h] [rbp+0h] BYREF

  v44 = a4;
  v8 = a1;
  v46 = a5;
  v47 = a6;
  v9 = a1[2];
  if ( v9 > 0x433 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v10 = &dword_180063624;
LABEL_9:
      LODWORD(v44) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (_DWORD)v10,
        0,
        0,
        (__int64)&v44);
      return 2147942487LL;
    }
    return 2147942487LL;
  }
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v11 = std::_Traits_find_ch<std::char_traits<unsigned short>>(a1, v9, 0, 47);
  if ( v11 == -1 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v10 = &dword_1800635F4;
      goto LABEL_9;
    }
    return 2147942487LL;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(StringSid);
  pSid = 0;
  LengthSid = 0;
  if ( !v11 )
  {
LABEL_21:
    v20 = v11 + 1;
    v21 = v8[2];
    if ( v20 >= v21 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        LODWORD(v44) = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)byte_180063585,
          0,
          0,
          (__int64)&v44);
      }
      v22 = pSid;
      pSid = 0;
      goto LABEL_76;
    }
    if ( v8[3] <= 7u )
      v23 = v8;
    else
      v23 = (_QWORD *)*v8;
    v24 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v23, v21, v20, 47);
    if ( v24 == -1 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        LODWORD(v44) = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)byte_18006354D,
          0,
          0,
          (__int64)&v44);
      }
      goto LABEL_75;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(StringUuid);
    Uuid = 0;
    if ( v24 != v20 )
    {
      v25 = std::wstring::substr(v8, v52, v20, v24 - v20);
      std::wstring::operator=(StringUuid, v25);
      std::wstring::~wstring(v52);
      v26 = (unsigned __int16 *)StringUuid;
      if ( StringUuid[3] > (RPC_WSTR)7 )
        v26 = StringUuid[0];
      v27 = UuidFromStringW(v26, &Uuid);
      v18 = v27;
      if ( v27 )
      {
        if ( v27 > 0 )
          v18 = (unsigned __int16)v27 | 0x80070000;
        if ( (unsigned int)dword_18006E000 > 2 )
        {
          LODWORD(v44) = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18006E000,
            (unsigned int)&word_18006350E,
            0,
            0,
            (__int64)&v44);
        }
        std::wstring::~wstring(StringUuid);
        v19 = pSid;
        pSid = 0;
        goto LABEL_40;
      }
    }
    v28 = v24 + 1;
    v29 = v8[2];
    if ( v24 + 1 >= v29 )
    {
      if ( (unsigned int)dword_18006E000 <= 2 )
      {
LABEL_74:
        std::wstring::~wstring(StringUuid);
LABEL_75:
        v22 = pSid;
        pSid = 0;
LABEL_76:
        if ( v22 )
          LocalFree(v22);
        v18 = -2147024809;
        goto LABEL_84;
      }
      v30 = byte_1800634DB;
LABEL_45:
      LODWORD(v44) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (_DWORD)v30,
        0,
        0,
        (__int64)&v44);
      goto LABEL_74;
    }
    if ( v8[3] <= 7u )
      v31 = v8;
    else
      v31 = (_QWORD *)*v8;
    v32 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v31, v29, v24 + 1, 47);
    if ( v32 == -1 )
    {
      if ( (unsigned int)dword_18006E000 <= 2 )
        goto LABEL_74;
      v30 = (char *)&unk_1800634A8;
      goto LABEL_45;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&p_pSid);
    if ( v32 != v28 )
    {
      v33 = std::wstring::substr(v8, v52, v28, v32 - v28);
      std::wstring::operator=(&p_pSid, v33);
      std::wstring::~wstring(v52);
    }
    v34 = v32 + 1;
    v35 = v8[2];
    if ( v32 + 1 < v35 )
    {
      if ( v8[3] <= 7u )
        v37 = v8;
      else
        v37 = (_QWORD *)*v8;
      v38 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v37, v35, v32 + 1, 47);
      if ( v38 != -1 )
      {
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v52);
        if ( v38 != v34 )
        {
          v39 = std::wstring::substr(v8, v53, v34, v38 - v34);
          std::wstring::operator=(v52, v39);
          std::wstring::~wstring(v53);
        }
        v40 = v38 + 1;
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v53);
        if ( v8[3] <= 7u )
          v41 = v8;
        else
          v41 = (_QWORD *)*v8;
        if ( std::_Traits_find_ch<std::char_traits<unsigned short>>(v41, v8[2], v40, 47) == -1 )
        {
          if ( v40 < v8[2] )
          {
            v42 = std::wstring::substr(v8, v56, v40, -1);
            std::wstring::operator=(v53, v42);
            std::wstring::~wstring(v56);
          }
          std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(a2, pSid, LengthSid);
          *a3 = Uuid;
          std::wstring::operator=(v44, &p_pSid);
          std::wstring::operator=(v46, v52);
          std::wstring::operator=(v47, v53);
          std::wstring::~wstring(v53);
          std::wstring::~wstring(v52);
          std::wstring::~wstring(&p_pSid);
          std::wstring::~wstring(StringUuid);
          v43 = pSid;
          pSid = 0;
          if ( v43 )
            LocalFree(v43);
          v18 = 0;
          goto LABEL_84;
        }
        if ( (unsigned int)dword_18006E000 > 2 )
        {
          LODWORD(v44) = -2147024809;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18006E000,
            (unsigned int)&dword_18006340C,
            0,
            0,
            (__int64)&v44);
        }
        std::wstring::~wstring(v53);
        std::wstring::~wstring(v52);
        goto LABEL_73;
      }
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v36 = word_180063442;
        goto LABEL_57;
      }
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v36 = (__int16 *)byte_180063475;
LABEL_57:
      LODWORD(v44) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (_DWORD)v36,
        0,
        0,
        (__int64)&v44);
    }
LABEL_73:
    std::wstring::~wstring(&p_pSid);
    goto LABEL_74;
  }
  v14 = std::wstring::substr(v8, v52, 0, v11);
  std::wstring::operator=(StringSid, v14);
  std::wstring::~wstring(v52);
  p_pSid = &pSid;
  Sid = 0;
  v50 = 1;
  v15 = (const WCHAR *)StringSid;
  if ( StringSid[3] > (LPCWSTR)7 )
    v15 = StringSid[0];
  v16 = ConvertStringSidToSidW(v15, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pSid);
  if ( v16 )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_21;
  }
  LastError = GetLastError();
  v18 = LastError;
  if ( LastError > 0 )
    v18 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    LODWORD(v44) = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)byte_1800635BD,
      0,
      0,
      (__int64)&v44);
  }
  v19 = pSid;
  pSid = 0;
LABEL_40:
  if ( v19 )
    LocalFree(v19);
LABEL_84:
  std::wstring::~wstring(StringSid);
  return v18;
}

```

## disassembly

```asm
0x180029bc0  push    rbp
0x180029bc2  push    rbx
0x180029bc3  push    rsi
0x180029bc4  push    rdi
0x180029bc5  push    r12
0x180029bc7  push    r13
0x180029bc9  push    r14
0x180029bcb  push    r15
0x180029bcd  lea     rbp, [rsp-38h]
0x180029bd2  sub     rsp, 138h
0x180029bd9  mov     rax, cs:__security_cookie
0x180029be0  xor     rax, rsp
0x180029be3  mov     [rbp+70h+var_50], rax
0x180029be7  mov     [rsp+170h+var_140], r9
0x180029bec  mov     r13, r8
0x180029bef  mov     r12, rdx
0x180029bf2  mov     rdi, rcx
0x180029bf5  mov     rax, [rbp+70h+arg_20]
0x180029bfc  mov     [rsp+170h+var_130], rax
0x180029c01  mov     rax, [rbp+70h+arg_28]
0x180029c08  mov     [rsp+170h+var_128], rax
0x180029c0d  mov     rdx, [rcx+10h]
0x180029c11  cmp     rdx, 433h
0x180029c18  jbe     short loc_180029C2E
0x180029c1a  mov     eax, cs:dword_18006E000
0x180029c20  cmp     eax, 2
0x180029c23  jbe     short loc_180029C85
0x180029c25  lea     rdx, dword_180063624
0x180029c2c  jmp     short loc_180029C61
0x180029c2e  cmp     qword ptr [rcx+18h], 7
0x180029c33  jbe     short loc_180029C38
0x180029c35  mov     rcx, [rcx]
0x180029c38  mov     r9d, 2Fh ; '/'
0x180029c3e  xor     r8d, r8d
0x180029c41  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180029c46  mov     rsi, rax
0x180029c49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029c4d  jnz     short loc_180029C8F
0x180029c4f  mov     eax, cs:dword_18006E000
0x180029c55  cmp     eax, 2
0x180029c58  jbe     short loc_180029C85
0x180029c5a  lea     rdx, dword_1800635F4
0x180029c61  lea     rax, [rsp+170h+var_140]
0x180029c66  mov     [rsp+170h+var_150], rax
0x180029c6b  mov     dword ptr [rsp+170h+var_140], 80070057h
0x180029c73  xor     r9d, r9d
0x180029c76  xor     r8d, r8d
0x180029c79  lea     rcx, dword_18006E000
0x180029c80  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029c85  mov     eax, 80070057h
0x180029c8a  jmp     loc_18002A206
0x180029c8f  lea     rcx, [rbp+70h+StringSid]
0x180029c93  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180029c98  nop
0x180029c99  xor     r14d, r14d
0x180029c9c  mov     [rsp+170h+pSid], r14
0x180029ca1  mov     r15d, r14d
0x180029ca4  test    rsi, rsi
0x180029ca7  jz      loc_180029D76
0x180029cad  mov     r9, rsi
0x180029cb0  xor     r8d, r8d
0x180029cb3  lea     rdx, [rbp+70h+var_E0]
0x180029cb7  mov     rcx, rdi
0x180029cba  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180029cbf  mov     rdx, rax
0x180029cc2  lea     rcx, [rbp+70h+StringSid]
0x180029cc6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029ccb  lea     rcx, [rbp+70h+var_E0]
0x180029ccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029cd4  lea     rax, [rsp+170h+pSid]
0x180029cd9  mov     [rsp+170h+var_120], rax
0x180029cde  mov     [rsp+170h+Sid], r14
0x180029ce3  mov     [rsp+170h+var_110], 1
0x180029ce8  lea     rcx, [rbp+70h+StringSid]
0x180029cec  cmp     [rbp+70h+var_78], 7
0x180029cf1  cmova   rcx, [rbp+70h+StringSid]; StringSid
0x180029cf6  lea     rdx, [rsp+170h+Sid]; Sid
0x180029cfb  call    cs:__imp_ConvertStringSidToSidW
0x180029d01  mov     ebx, eax
0x180029d03  lea     rcx, [rsp+170h+var_120]
0x180029d08  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180029d0d  test    ebx, ebx
0x180029d0f  jnz     short loc_180029D68
0x180029d11  call    cs:__imp_GetLastError
0x180029d17  mov     ebx, eax
0x180029d19  test    eax, eax
0x180029d1b  jle     short loc_180029D26
0x180029d1d  movzx   ebx, ax
0x180029d20  or      ebx, 80070000h
0x180029d26  mov     eax, cs:dword_18006E000
0x180029d2c  cmp     eax, 2
0x180029d2f  jbe     short loc_180029D59
0x180029d31  mov     dword ptr [rsp+170h+var_140], ebx
0x180029d35  lea     rax, [rsp+170h+var_140]
0x180029d3a  mov     [rsp+170h+var_150], rax
0x180029d3f  xor     r9d, r9d
0x180029d42  xor     r8d, r8d
0x180029d45  lea     rdx, byte_1800635BD
0x180029d4c  lea     rcx, dword_18006E000
0x180029d53  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029d58  nop
0x180029d59  mov     rcx, [rsp+170h+pSid]
0x180029d5e  mov     [rsp+170h+pSid], r14
0x180029d63  jmp     loc_180029EEA
0x180029d68  mov     rcx, [rsp+170h+pSid]; pSid
0x180029d6d  call    cs:__imp_GetLengthSid
0x180029d73  mov     r15d, eax
0x180029d76  inc     rsi
0x180029d79  mov     rdx, [rdi+10h]
0x180029d7d  cmp     rsi, rdx
0x180029d80  jb      short loc_180029DC8
0x180029d82  mov     eax, cs:dword_18006E000
0x180029d88  cmp     eax, 2
0x180029d8b  jbe     short loc_180029DB9
0x180029d8d  mov     dword ptr [rsp+170h+var_140], 80070057h
0x180029d95  lea     rax, [rsp+170h+var_140]
0x180029d9a  mov     [rsp+170h+var_150], rax
0x180029d9f  xor     r9d, r9d
0x180029da2  xor     r8d, r8d
0x180029da5  lea     rdx, byte_180063585
0x180029dac  lea     rcx, dword_18006E000
0x180029db3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029db8  nop
0x180029db9  mov     rcx, [rsp+170h+pSid]
0x180029dbe  mov     [rsp+170h+pSid], r14
0x180029dc3  jmp     loc_18002A12E
0x180029dc8  cmp     qword ptr [rdi+18h], 7
0x180029dcd  jbe     short loc_180029DD4
0x180029dcf  mov     rcx, [rdi]
0x180029dd2  jmp     short loc_180029DD7
0x180029dd4  mov     rcx, rdi
0x180029dd7  mov     r9d, 2Fh ; '/'
0x180029ddd  mov     r8, rsi
0x180029de0  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180029de5  mov     r14, rax
0x180029de8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029dec  jnz     short loc_180029E2D
0x180029dee  mov     eax, cs:dword_18006E000
0x180029df4  cmp     eax, 2
0x180029df7  jbe     loc_18002A120
0x180029dfd  mov     dword ptr [rsp+170h+var_140], 80070057h
0x180029e05  lea     rax, [rsp+170h+var_140]
0x180029e0a  mov     [rsp+170h+var_150], rax
0x180029e0f  xor     r9d, r9d
0x180029e12  xor     r8d, r8d
0x180029e15  lea     rdx, byte_18006354D
0x180029e1c  lea     rcx, dword_18006E000
0x180029e23  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029e28  jmp     loc_18002A120
0x180029e2d  lea     rcx, [rsp+170h+StringUuid]
0x180029e32  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180029e37  nop
0x180029e38  xorps   xmm1, xmm1
0x180029e3b  movups  xmmword ptr [rbp+70h+Uuid.Data1], xmm1
0x180029e3f  cmp     r14, rsi
0x180029e42  jz      loc_180029EFE
0x180029e48  mov     r9, r14
0x180029e4b  sub     r9, rsi
0x180029e4e  mov     r8, rsi
0x180029e51  lea     rdx, [rbp+70h+var_E0]
0x180029e55  mov     rcx, rdi
0x180029e58  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180029e5d  mov     rdx, rax
0x180029e60  lea     rcx, [rsp+170h+StringUuid]
0x180029e65  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029e6a  lea     rcx, [rbp+70h+var_E0]
0x180029e6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029e73  lea     rcx, [rsp+170h+StringUuid]
0x180029e78  cmp     [rbp+70h+var_E8], 7
0x180029e7d  cmova   rcx, [rsp+170h+StringUuid]; StringUuid
0x180029e83  lea     rdx, [rbp+70h+Uuid]; Uuid
0x180029e87  call    cs:__imp_UuidFromStringW
0x180029e8d  mov     ebx, eax
0x180029e8f  test    eax, eax
0x180029e91  jz      short loc_180029EFE
0x180029e93  jle     short loc_180029E9E
0x180029e95  movzx   ebx, ax
0x180029e98  or      ebx, 80070000h
0x180029e9e  mov     eax, cs:dword_18006E000
0x180029ea4  cmp     eax, 2
0x180029ea7  jbe     short loc_180029ED1
0x180029ea9  mov     dword ptr [rsp+170h+var_140], ebx
0x180029ead  lea     rax, [rsp+170h+var_140]
0x180029eb2  mov     [rsp+170h+var_150], rax
0x180029eb7  xor     r9d, r9d
0x180029eba  xor     r8d, r8d
0x180029ebd  lea     rdx, word_18006350E
0x180029ec4  lea     rcx, dword_18006E000
0x180029ecb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029ed0  nop
0x180029ed1  lea     rcx, [rsp+170h+StringUuid]
0x180029ed6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029edb  nop
0x180029edc  mov     rcx, [rsp+170h+pSid]; hMem
0x180029ee1  mov     [rsp+170h+pSid], 0
0x180029eea  test    rcx, rcx
0x180029eed  jz      loc_18002A1FB
0x180029ef3  call    cs:__imp_LocalFree
0x180029ef9  jmp     loc_18002A1FB
0x180029efe  lea     rbx, [r14+1]
0x180029f02  mov     rdx, [rdi+10h]
0x180029f06  cmp     rbx, rdx
0x180029f09  jb      short loc_180029F4A
0x180029f0b  mov     eax, cs:dword_18006E000
0x180029f11  cmp     eax, 2
0x180029f14  jbe     loc_18002A115
0x180029f1a  lea     rdx, byte_1800634DB
0x180029f21  xor     r9d, r9d
0x180029f24  lea     rax, [rsp+170h+var_140]
0x180029f29  xor     r8d, r8d
0x180029f2c  mov     [rsp+170h+var_150], rax
0x180029f31  mov     dword ptr [rsp+170h+var_140], 80070057h
0x180029f39  lea     rcx, dword_18006E000
0x180029f40  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029f45  jmp     loc_18002A115
0x180029f4a  cmp     qword ptr [rdi+18h], 7
0x180029f4f  jbe     short loc_180029F56
0x180029f51  mov     rcx, [rdi]
0x180029f54  jmp     short loc_180029F59
0x180029f56  mov     rcx, rdi
0x180029f59  mov     r9d, 2Fh ; '/'
0x180029f5f  mov     r8, rbx
0x180029f62  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180029f67  mov     rsi, rax
0x180029f6a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180029f6e  cmp     rax, r14
0x180029f71  jnz     short loc_180029F8B
0x180029f73  mov     eax, cs:dword_18006E000
0x180029f79  cmp     eax, 2
0x180029f7c  jbe     loc_18002A115
0x180029f82  lea     rdx, unk_1800634A8
0x180029f89  jmp     short loc_180029F21
0x180029f8b  lea     rcx, [rsp+170h+var_120]
0x180029f90  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180029f95  nop
0x180029f96  cmp     rsi, rbx
0x180029f99  jz      short loc_180029FC6
0x180029f9b  mov     r9, rsi
0x180029f9e  sub     r9, rbx
0x180029fa1  mov     r8, rbx
0x180029fa4  lea     rdx, [rbp+70h+var_E0]
0x180029fa8  mov     rcx, rdi
0x180029fab  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180029fb0  mov     rdx, rax
0x180029fb3  lea     rcx, [rsp+170h+var_120]
0x180029fb8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029fbd  lea     rcx, [rbp+70h+var_E0]
0x180029fc1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029fc6  lea     rbx, [rsi+1]
0x180029fca  mov     rdx, [rdi+10h]
0x180029fce  cmp     rbx, rdx
0x180029fd1  jb      short loc_18002A012
0x180029fd3  mov     eax, cs:dword_18006E000
0x180029fd9  cmp     eax, 2
0x180029fdc  jbe     loc_18002A10A
0x180029fe2  lea     rdx, byte_180063475
0x180029fe9  xor     r9d, r9d
0x180029fec  lea     rax, [rsp+170h+var_140]
0x180029ff1  xor     r8d, r8d
0x180029ff4  mov     [rsp+170h+var_150], rax
0x180029ff9  mov     dword ptr [rsp+170h+var_140], 80070057h
0x18002a001  lea     rcx, dword_18006E000
0x18002a008  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002a00d  jmp     loc_18002A10A
0x18002a012  cmp     qword ptr [rdi+18h], 7
0x18002a017  jbe     short loc_18002A01E
0x18002a019  mov     rcx, [rdi]
0x18002a01c  jmp     short loc_18002A021
0x18002a01e  mov     rcx, rdi
0x18002a021  mov     r9d, 2Fh ; '/'
0x18002a027  mov     r8, rbx
0x18002a02a  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18002a02f  mov     rsi, rax
0x18002a032  cmp     rax, r14
0x18002a035  jnz     short loc_18002A04F
0x18002a037  mov     eax, cs:dword_18006E000
0x18002a03d  cmp     eax, 2
0x18002a040  jbe     loc_18002A10A
0x18002a046  lea     rdx, word_180063442
0x18002a04d  jmp     short loc_180029FE9
0x18002a04f  lea     rcx, [rbp+70h+var_E0]
0x18002a053  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002a058  nop
0x18002a059  cmp     rsi, rbx
0x18002a05c  jz      short loc_18002A088
0x18002a05e  mov     r9, rsi
0x18002a061  sub     r9, rbx
0x18002a064  mov     r8, rbx
0x18002a067  lea     rdx, [rbp+70h+var_C0]
0x18002a06b  mov     rcx, rdi
0x18002a06e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18002a073  mov     rdx, rax
0x18002a076  lea     rcx, [rbp+70h+var_E0]
0x18002a07a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a07f  lea     rcx, [rbp+70h+var_C0]
0x18002a083  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a088  inc     rsi
0x18002a08b  lea     rcx, [rbp+70h+var_C0]
0x18002a08f  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002a094  nop
  ... truncated ...
```
