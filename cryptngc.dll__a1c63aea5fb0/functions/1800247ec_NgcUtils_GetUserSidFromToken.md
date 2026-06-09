# NgcUtils::GetUserSidFromToken

- ea: `0x1800247ec`
- end: `0x180024943`
- name: `NgcUtils::GetUserSidFromToken`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009fd4`
- `0x18001df90`

## callees

- `0x180010700`
- `0x1800158e0`
- `0x1800159a0`
- `0x1800247ec`
- `0x18002cd5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248b4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024902`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024902`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024823`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800248aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024823`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800248aa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024920`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024920`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetUserSidFromToken(__int64 a1, PSID *a2)
{
  signed int v3; // ebx
  DWORD LastError; // eax
  __int64 LengthSid; // rbx
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+10h] BYREF
  int v9; // [rsp+64h] [rbp+14h]
  DWORD v10; // [rsp+70h] [rbp+20h] BYREF

  v9 = HIDWORD(a1);
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || (v3 = GetLastError(), v3 == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a2, LengthSid);
      CopySid(LengthSid, *a2, *(PSID *)TokenInformation[0]);
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v10 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)byte_180063689,
          0,
          0,
          (__int64)&v10);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    std::vector<unsigned char>::_Tidy(TokenInformation);
  }
  else
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v10 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (unsigned int)&word_18006365E,
        0,
        0,
        (__int64)&v10);
    }
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800247ec  mov     r11, rsp
0x1800247ef  mov     [r11+10h], rbx
0x1800247f3  mov     [r11+20h], rdi
0x1800247f7  mov     [r11+8], rcx
0x1800247fb  push    rbp
0x1800247fc  mov     rbp, rsp
0x1800247ff  sub     rsp, 50h
0x180024803  mov     rdi, rdx
0x180024806  mov     [rbp+TokenInformationLength], 0
0x18002480d  lea     rax, [rbp+TokenInformationLength]
0x180024811  mov     [r11-38h], rax
0x180024815  xor     r9d, r9d; TokenInformationLength
0x180024818  xor     r8d, r8d; TokenInformation
0x18002481b  lea     edx, [r9+1]; TokenInformationClass
0x18002481f  lea     rcx, [r9-6]; TokenHandle
0x180024823  call    cs:__imp_GetTokenInformation
0x180024829  test    eax, eax
0x18002482b  jnz     short loc_180024880
0x18002482d  call    cs:__imp_GetLastError
0x180024833  mov     ebx, eax
0x180024835  cmp     eax, 7Ah ; 'z'
0x180024838  jz      short loc_180024880
0x18002483a  mov     eax, cs:dword_18006E000
0x180024840  cmp     eax, 2
0x180024843  jbe     short loc_18002486A
0x180024845  mov     [rbp+arg_10], ebx
0x180024848  lea     rax, [rbp+arg_10]
0x18002484c  mov     [rsp+50h+ReturnLength], rax
0x180024851  xor     r9d, r9d
0x180024854  xor     r8d, r8d
0x180024857  lea     rdx, word_18006365E
0x18002485e  lea     rcx, dword_18006E000
0x180024865  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002486a  test    ebx, ebx
0x18002486c  jle     loc_180024931
0x180024872  movzx   ebx, bx
0x180024875  or      ebx, 80070000h
0x18002487b  jmp     loc_180024931
0x180024880  mov     edx, [rbp+TokenInformationLength]
0x180024883  lea     rcx, [rbp+TokenInformation]
0x180024887  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002488c  nop
0x18002488d  lea     rax, [rbp+TokenInformationLength]
0x180024891  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180024896  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002489a  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18002489e  mov     edx, 1; TokenInformationClass
0x1800248a3  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800248aa  call    cs:__imp_GetTokenInformation
0x1800248b0  test    eax, eax
0x1800248b2  jnz     short loc_1800248FB
0x1800248b4  call    cs:__imp_GetLastError
0x1800248ba  mov     ebx, eax
0x1800248bc  mov     ecx, cs:dword_18006E000
0x1800248c2  cmp     ecx, 2
0x1800248c5  jbe     short loc_1800248EC
0x1800248c7  mov     [rbp+arg_10], eax
0x1800248ca  lea     rax, [rbp+arg_10]
0x1800248ce  mov     [rsp+50h+ReturnLength], rax
0x1800248d3  xor     r9d, r9d
0x1800248d6  xor     r8d, r8d
0x1800248d9  lea     rdx, byte_180063689
0x1800248e0  lea     rcx, dword_18006E000
0x1800248e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800248ec  test    ebx, ebx
0x1800248ee  jle     short loc_180024928
0x1800248f0  movzx   ebx, bx
0x1800248f3  or      ebx, 80070000h
0x1800248f9  jmp     short loc_180024928
0x1800248fb  mov     rcx, [rbp+TokenInformation]
0x1800248ff  mov     rcx, [rcx]; pSid
0x180024902  call    cs:__imp_GetLengthSid
0x180024908  mov     ebx, eax
0x18002490a  mov     edx, eax
0x18002490c  mov     rcx, rdi
0x18002490f  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180024914  mov     r8, [rbp+TokenInformation]
0x180024918  mov     r8, [r8]; pSourceSid
0x18002491b  mov     rdx, [rdi]; pDestinationSid
0x18002491e  mov     ecx, ebx; nDestinationSidLength
0x180024920  call    cs:__imp_CopySid
0x180024926  xor     ebx, ebx
0x180024928  lea     rcx, [rbp+TokenInformation]
0x18002492c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180024931  mov     eax, ebx
0x180024933  mov     rbx, [rsp+50h+arg_8]
0x180024938  mov     rdi, [rsp+50h+arg_18]
0x18002493d  add     rsp, 50h
0x180024941  pop     rbp
0x180024942  retn
```
