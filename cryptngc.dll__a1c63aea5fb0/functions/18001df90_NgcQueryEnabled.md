# NgcQueryEnabled

- ea: `0x18001df90`
- end: `0x18001e35e`
- name: `NgcQueryEnabled`
- size: `974`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009fd4`
- `0x18001de44`

## callees

- `0x180006560`
- `0x1800105c0`
- `0x1800158e0`
- `0x1800159a0`
- `0x180018790`
- `0x18001a36c`
- `0x18001df90`
- `0x1800247ec`
- `0x180035120`
- `0x18003673c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e1ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e1ca`

## pseudocode

```c
__int64 __fastcall NgcQueryEnabled(__int64 a1, const WCHAR *a2, int *a3, _DWORD *a4, _DWORD *a5, _DWORD *a6)
{
  _DWORD *v6; // rbx
  signed int LastError; // ebx
  int v10; // edx
  int v12; // [rsp+38h] [rbp-D0h] BYREF
  int v13; // [rsp+3Ch] [rbp-CCh] BYREF
  int UserSidFromToken; // [rsp+40h] [rbp-C8h] BYREF
  int v15; // [rsp+44h] [rbp-C4h] BYREF
  int v16; // [rsp+48h] [rbp-C0h] BYREF
  int v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  __m256i StringSid; // [rsp+58h] [rbp-B0h] BYREF
  const WCHAR *v20; // [rsp+78h] [rbp-90h] BYREF
  char v21; // [rsp+80h] [rbp-88h] BYREF
  int v22; // [rsp+84h] [rbp-84h]
  __int64 v23; // [rsp+88h] [rbp-80h]
  char v24; // [rsp+90h] [rbp-78h]
  int v25; // [rsp+94h] [rbp-74h]
  int v26; // [rsp+98h] [rbp-70h]
  __int128 v27; // [rsp+9Ch] [rbp-6Ch]
  int v28; // [rsp+ACh] [rbp-5Ch]
  __int64 v29; // [rsp+B0h] [rbp-58h]
  int v30; // [rsp+B8h] [rbp-50h]
  _QWORD v31[14]; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v32; // [rsp+138h] [rbp+30h]
  _QWORD v33[16]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v34; // [rsp+1E8h] [rbp+E0h] BYREF
  const WCHAR *v35; // [rsp+1F0h] [rbp+E8h] BYREF

  v35 = a2;
  v34 = a1;
  v6 = a5;
  v31[0] = &UserSidFromToken;
  UserSidFromToken = 0;
  v31[1] = &v34;
  v31[2] = &v35;
  v31[3] = &v15;
  v31[4] = &v16;
  v31[5] = &v17;
  v31[6] = &v13;
  v31[7] = (char *)&v13 + 1;
  v31[8] = (char *)&v12 + 3;
  v31[9] = (char *)&v13 + 2;
  v31[10] = (char *)&v13 + 3;
  v31[11] = &v18;
  v31[12] = &v12;
  v15 = 2;
  v16 = 0;
  v31[13] = (char *)&v12 + 1;
  v17 = 0;
  v21 = 0;
  v22 = 1;
  v23 = 1;
  v24 = 0;
  v25 = 8;
  v26 = 127;
  v28 = 2;
  v29 = 1;
  v30 = 0;
  StringSid.m256i_i64[0] = 0;
  LODWORD(v18) = 1;
  v13 = 0;
  v12 = 0;
  v32 = 256;
  v27 = 0;
  if ( a5 )
    BYTE2(v12) = (*a5 & 0x20) != 0;
  if ( a2 && !*a2 )
  {
    UserSidFromToken = -2146893819;
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v20 = v35;
      LODWORD(a5) = UserSidFromToken;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        a1,
        (unsigned __int8 *)word_18006047A,
        1,
        (__int64)a4,
        (__int64)&a5,
        &v20);
    }
    LastError = UserSidFromToken;
    goto LABEL_29;
  }
  if ( !a1 )
  {
    memset(&StringSid.m256i_u64[1], 0, 24);
    UserSidFromToken = NgcUtils::GetUserSidFromToken(0, (PSID *)&StringSid.m256i_i64[1]);
    if ( UserSidFromToken < 0 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        LODWORD(a5) = UserSidFromToken;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)&word_180060456,
          0,
          0,
          (__int64)&a5);
      }
      LastError = UserSidFromToken;
LABEL_13:
      std::vector<unsigned char>::_Tidy(&StringSid.m256i_u64[1]);
      goto LABEL_29;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW((PSID)StringSid.m256i_i64[1], (LPWSTR *)&StringSid) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        LODWORD(a5) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)&unk_180060428,
          0,
          0,
          (__int64)&a5);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      UserSidFromToken = LastError;
      goto LABEL_13;
    }
    v34 = StringSid.m256i_i64[0];
    std::vector<unsigned char>::_Tidy(&StringSid.m256i_u64[1]);
  }
  v33[0] = &UserSidFromToken;
  v33[1] = &v34;
  v33[2] = &v35;
  v33[3] = &v15;
  v33[4] = &v16;
  v33[5] = &v17;
  v33[6] = &v12;
  v33[7] = (char *)&v12 + 1;
  v33[8] = (char *)&v12 + 2;
  v33[9] = &v18;
  v33[10] = &v21;
  v33[11] = (char *)&v12 + 3;
  v33[12] = &v13;
  v33[13] = (char *)&v13 + 1;
  v33[14] = (char *)&v13 + 2;
  v33[15] = (char *)&v13 + 3;
  v10 = HResultErrorContract__lambda_2231b4a0d8078d5c81bf8fecd1a6e66f_(v33);
  if ( v10 >= 0 )
  {
    *a3 = v15;
    if ( a4 )
      *a4 = v16;
    if ( v6 )
      *v6 = v17;
    if ( a6 )
      *a6 = v18;
  }
  UserSidFromToken = HResultToSecurityStatus(v10);
  LastError = UserSidFromToken;
LABEL_29:
  wil::details::ScopeExitFnGuard__lambda_6e7f68c3e81740690bdce835b631320c___::operator()(v31);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001df90  mov     rax, rsp
0x18001df93  mov     [rax+18h], rbx
0x18001df97  mov     [rax+20h], rsi
0x18001df9b  mov     [rax+10h], rdx
0x18001df9f  mov     [rax+8], rcx
0x18001dfa3  push    rbp
0x18001dfa4  push    rdi
0x18001dfa5  push    r14
0x18001dfa7  lea     rbp, [rax-0D8h]
0x18001dfae  sub     rsp, 1C0h
0x18001dfb5  mov     rbx, [rbp+0D0h+arg_20]
0x18001dfbc  lea     rax, [rsp+1D0h+var_198]
0x18001dfc1  xor     r14d, r14d
0x18001dfc4  mov     [rbp+0D0h+var_110], rax
0x18001dfc8  mov     [rsp+1D0h+var_198], r14d
0x18001dfcd  lea     rax, [rbp+0D0h+arg_0]
0x18001dfd4  mov     [rbp+0D0h+var_108], rax
0x18001dfd8  lea     rax, [rbp+0D0h+arg_8]
0x18001dfdf  mov     [rbp+0D0h+var_100], rax
0x18001dfe3  lea     rax, [rsp+1D0h+var_194]
0x18001dfe8  mov     [rbp+0D0h+var_F8], rax
0x18001dfec  lea     rax, [rsp+1D0h+var_190]
0x18001dff1  mov     [rbp+0D0h+var_F0], rax
0x18001dff5  lea     rax, [rsp+1D0h+var_18C]
0x18001dffa  mov     [rbp+0D0h+var_E8], rax
0x18001dffe  lea     rax, [rsp+1D0h+var_19C]
0x18001e003  mov     [rbp+0D0h+var_E0], rax
0x18001e007  lea     rax, [rsp+1D0h+var_19C+1]
0x18001e00c  mov     [rbp+0D0h+var_D8], rax
0x18001e010  lea     rax, [rsp+1D0h+var_1A0+3]
0x18001e015  mov     [rbp+0D0h+var_D0], rax
0x18001e019  lea     rax, [rsp+1D0h+var_19C+2]
0x18001e01e  mov     [rbp+0D0h+var_C8], rax
0x18001e022  lea     rax, [rsp+1D0h+var_19C+3]
0x18001e027  mov     [rbp+0D0h+var_C0], rax
0x18001e02b  lea     rax, [rsp+1D0h+var_188]
0x18001e030  mov     [rbp+0D0h+var_B8], rax
0x18001e034  lea     rax, [rsp+1D0h+var_1A0]
0x18001e039  mov     [rbp+0D0h+var_B0], rax
0x18001e03d  mov     rsi, r8
0x18001e040  mov     [rsp+1D0h+var_194], 2
0x18001e048  lea     r8d, [r14+1]
0x18001e04c  mov     [rsp+1D0h+var_190], r14d
0x18001e051  lea     rax, [rsp+1D0h+var_1A0+1]
0x18001e056  mov     [rbp+0D0h+var_A8], rax
0x18001e05a  xorps   xmm0, xmm0
0x18001e05d  mov     [rsp+1D0h+var_18C], r14d
0x18001e062  mov     rdi, r9
0x18001e065  mov     [rsp+1D0h+var_158], r14b
0x18001e06a  mov     [rsp+1D0h+var_154], r8d
0x18001e06f  mov     [rbp+0D0h+var_150], r8
0x18001e073  mov     [rbp+0D0h+var_148], r14b
0x18001e077  mov     [rbp+0D0h+var_144], 8
0x18001e07e  mov     [rbp+0D0h+var_140], 7Fh
0x18001e085  mov     [rbp+0D0h+var_12C], 2
0x18001e08c  mov     [rbp+0D0h+var_128], r8
0x18001e090  mov     [rbp+0D0h+var_120], r14d
0x18001e094  mov     qword ptr [rsp+1D0h+StringSid], r14
0x18001e099  mov     dword ptr [rsp+1D0h+var_188], r8d
0x18001e09e  mov     byte ptr [rsp+1D0h+var_19C], r14b
0x18001e0a3  mov     byte ptr [rsp+1D0h+var_19C+1], r14b
0x18001e0a8  mov     byte ptr [rsp+1D0h+var_1A0+3], r14b
0x18001e0ad  mov     byte ptr [rsp+1D0h+var_19C+2], r14b
0x18001e0b2  mov     byte ptr [rsp+1D0h+var_19C+3], r14b
0x18001e0b7  mov     byte ptr [rsp+1D0h+var_1A0], r14b
0x18001e0bc  mov     byte ptr [rsp+1D0h+var_1A0+1], r14b
0x18001e0c1  mov     byte ptr [rsp+1D0h+var_1A0+2], r14b
0x18001e0c6  mov     [rbp+0D0h+var_A0], 100h
0x18001e0cc  movdqu  [rbp+0D0h+var_13C], xmm0
0x18001e0d1  test    rbx, rbx
0x18001e0d4  jz      short loc_18001E0E2
0x18001e0d6  mov     eax, [rbx]
0x18001e0d8  shr     eax, 5
0x18001e0db  and     al, r8b
0x18001e0de  mov     byte ptr [rsp+1D0h+var_1A0+2], al
0x18001e0e2  test    rdx, rdx
0x18001e0e5  jz      short loc_18001E141
0x18001e0e7  cmp     [rdx], r14w
0x18001e0eb  jnz     short loc_18001E141
0x18001e0ed  mov     eax, cs:dword_18006E000
0x18001e0f3  mov     [rsp+1D0h+var_198], 80090005h
0x18001e0fb  cmp     eax, 2
0x18001e0fe  jbe     short loc_18001E138
0x18001e100  mov     rax, [rbp+0D0h+arg_8]
0x18001e107  lea     rdx, word_18006047A
0x18001e10e  mov     [rsp+1D0h+var_160], rax
0x18001e113  mov     eax, [rsp+1D0h+var_198]
0x18001e117  mov     dword ptr [rbp+0D0h+arg_20], eax
0x18001e11d  lea     rax, [rsp+1D0h+var_160]
0x18001e122  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x18001e127  lea     rax, [rbp+0D0h+arg_20]
0x18001e12e  mov     [rsp+1D0h+var_1B0], rax
0x18001e133  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001e138  mov     ebx, [rsp+1D0h+var_198]
0x18001e13c  jmp     loc_18001E331
0x18001e141  test    rcx, rcx
0x18001e144  jnz     loc_18001E23B
0x18001e14a  lea     rdx, [rsp+1D0h+StringSid+8]
0x18001e14f  mov     [rsp+1D0h+var_168], r14
0x18001e154  movdqu  xmmword ptr [rsp+1D0h+StringSid+8], xmm0
0x18001e15a  call    NgcUtils__GetUserSidFromToken
0x18001e15f  mov     [rsp+1D0h+var_198], eax
0x18001e163  test    eax, eax
0x18001e165  jns     short loc_18001E1B4
0x18001e167  mov     eax, cs:dword_18006E000
0x18001e16d  cmp     eax, 2
0x18001e170  jbe     short loc_18001E1A1
0x18001e172  mov     eax, [rsp+1D0h+var_198]
0x18001e176  lea     rdx, word_180060456
0x18001e17d  mov     dword ptr [rbp+0D0h+arg_20], eax
0x18001e183  lea     rcx, dword_18006E000
0x18001e18a  lea     rax, [rbp+0D0h+arg_20]
0x18001e191  xor     r9d, r9d
0x18001e194  xor     r8d, r8d
0x18001e197  mov     [rsp+1D0h+var_1B0], rax
0x18001e19c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e1a1  mov     ebx, [rsp+1D0h+var_198]
0x18001e1a5  lea     rcx, [rsp+1D0h+StringSid+8]
0x18001e1aa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e1af  jmp     loc_18001E331
0x18001e1b4  xor     edx, edx
0x18001e1b6  lea     rcx, [rsp+1D0h+StringSid]
0x18001e1bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e1c0  mov     rcx, qword ptr [rsp+1D0h+StringSid+8]; Sid
0x18001e1c5  lea     rdx, [rsp+1D0h+StringSid]; StringSid
0x18001e1ca  call    cs:__imp_ConvertSidToStringSidW
0x18001e1d0  test    eax, eax
0x18001e1d2  jnz     short loc_18001E225
0x18001e1d4  call    cs:__imp_GetLastError
0x18001e1da  mov     ebx, eax
0x18001e1dc  mov     eax, cs:dword_18006E000
0x18001e1e2  cmp     eax, 2
0x18001e1e5  jbe     short loc_18001E212
0x18001e1e7  lea     rax, [rbp+0D0h+arg_20]
0x18001e1ee  mov     dword ptr [rbp+0D0h+arg_20], ebx
0x18001e1f4  xor     r9d, r9d
0x18001e1f7  mov     [rsp+1D0h+var_1B0], rax
0x18001e1fc  xor     r8d, r8d
0x18001e1ff  lea     rdx, unk_180060428
0x18001e206  lea     rcx, dword_18006E000
0x18001e20d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e212  test    ebx, ebx
0x18001e214  jle     short loc_18001E21F
0x18001e216  movzx   ebx, bx
0x18001e219  or      ebx, 80070000h
0x18001e21f  mov     [rsp+1D0h+var_198], ebx
0x18001e223  jmp     short loc_18001E1A5
0x18001e225  mov     rax, qword ptr [rsp+1D0h+StringSid]
0x18001e22a  lea     rcx, [rsp+1D0h+StringSid+8]
0x18001e22f  mov     [rbp+0D0h+arg_0], rax
0x18001e236  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001e23b  lea     rax, [rsp+1D0h+var_198]
0x18001e240  mov     [rbp+0D0h+var_90], rax
0x18001e244  lea     rcx, [rbp+0D0h+var_90]
0x18001e248  lea     rax, [rbp+0D0h+arg_0]
0x18001e24f  mov     [rbp+0D0h+var_88], rax
0x18001e253  lea     rax, [rbp+0D0h+arg_8]
0x18001e25a  mov     [rbp+0D0h+var_80], rax
0x18001e25e  lea     rax, [rsp+1D0h+var_194]
0x18001e263  mov     [rbp+0D0h+var_78], rax
0x18001e267  lea     rax, [rsp+1D0h+var_190]
0x18001e26c  mov     [rbp+0D0h+var_70], rax
0x18001e270  lea     rax, [rsp+1D0h+var_18C]
0x18001e275  mov     [rbp+0D0h+var_68], rax
0x18001e279  lea     rax, [rsp+1D0h+var_1A0]
0x18001e27e  mov     [rbp+0D0h+var_60], rax
0x18001e282  lea     rax, [rsp+1D0h+var_1A0+1]
0x18001e287  mov     [rbp+0D0h+var_58], rax
0x18001e28b  lea     rax, [rsp+1D0h+var_1A0+2]
0x18001e290  mov     [rbp+0D0h+var_50], rax
0x18001e297  lea     rax, [rsp+1D0h+var_188]
0x18001e29c  mov     [rbp+0D0h+var_48], rax
0x18001e2a3  lea     rax, [rsp+1D0h+var_158]
0x18001e2a8  mov     [rbp+0D0h+var_40], rax
0x18001e2af  lea     rax, [rsp+1D0h+var_1A0+3]
0x18001e2b4  mov     [rbp+0D0h+var_38], rax
0x18001e2bb  lea     rax, [rsp+1D0h+var_19C]
0x18001e2c0  mov     [rbp+0D0h+var_30], rax
0x18001e2c7  lea     rax, [rsp+1D0h+var_19C+1]
0x18001e2cc  mov     [rbp+0D0h+var_28], rax
0x18001e2d3  lea     rax, [rsp+1D0h+var_19C+2]
0x18001e2d8  mov     [rbp+0D0h+var_20], rax
0x18001e2df  lea     rax, [rsp+1D0h+var_19C+3]
0x18001e2e4  mov     [rbp+0D0h+var_18], rax
0x18001e2eb  call    HResultErrorContract__lambda_2231b4a0d8078d5c81bf8fecd1a6e66f___; HResultErrorContract__lambda_2231b4a0d8078d5c81bf8fecd1a6e66f_
0x18001e2f0  mov     edx, eax
0x18001e2f2  test    eax, eax
0x18001e2f4  js      short loc_18001E324
0x18001e2f6  mov     eax, [rsp+1D0h+var_194]
0x18001e2fa  mov     [rsi], eax
0x18001e2fc  test    rdi, rdi
0x18001e2ff  jz      short loc_18001E307
0x18001e301  mov     eax, [rsp+1D0h+var_190]
0x18001e305  mov     [rdi], eax
0x18001e307  test    rbx, rbx
0x18001e30a  jz      short loc_18001E312
0x18001e30c  mov     eax, [rsp+1D0h+var_18C]
0x18001e310  mov     [rbx], eax
0x18001e312  mov     rcx, [rbp+0D0h+arg_28]
0x18001e319  test    rcx, rcx
0x18001e31c  jz      short loc_18001E324
0x18001e31e  mov     eax, dword ptr [rsp+1D0h+var_188]
0x18001e322  mov     [rcx], eax
0x18001e324  mov     ecx, edx; int
0x18001e326  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18001e32b  mov     [rsp+1D0h+var_198], eax
0x18001e32f  mov     ebx, eax
0x18001e331  lea     rcx, [rbp+0D0h+var_110]
0x18001e335  call    wil__details__ScopeExitFnGuard__lambda_6e7f68c3e81740690bdce835b631320c_____operator__
0x18001e33a  lea     rcx, [rsp+1D0h+StringSid]; void *
0x18001e33f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001e344  lea     r11, [rsp+1D0h+var_10]
0x18001e34c  mov     eax, ebx
0x18001e34e  mov     rbx, [r11+30h]
0x18001e352  mov     rsi, [r11+38h]
0x18001e356  mov     rsp, r11
0x18001e359  pop     r14
0x18001e35b  pop     rdi
0x18001e35c  pop     rbp
0x18001e35d  retn
```
