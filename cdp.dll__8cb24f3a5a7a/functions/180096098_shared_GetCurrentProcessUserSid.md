# shared::GetCurrentProcessUserSid

- ea: `0x180096098`
- end: `0x180096415`
- name: `shared::GetCurrentProcessUserSid`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180096004`

## callees

- `0x18000d02c`
- `0x18000d350`
- `0x180010fb4`
- `0x180011058`
- `0x1800624cc`
- `0x180095a00`
- `0x180095a34`
- `0x180096098`
- `0x180114c58`
- `0x180199618`
- `0x1801f7974`
- `0x1801fc5e8`
- `0x1801fcb5a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800960f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800962ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800960f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800962ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096378`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800960e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800961d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800960e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800961d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180096262`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180096262`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800961e5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800961e5`

## string_xrefs

- `0x180096394`: `CopySid Failed`
- `0x180096353`: `GetTokenInformation Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall shared::GetCurrentProcessUserSid(__int64 a1)
{
  __int64 v2; // rbx
  char *v3; // rdi
  signed __int64 v4; // r15
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // r14
  PSID *v8; // r15
  DWORD LengthSid; // eax
  DWORD v10; // r14d
  __int64 v11; // rdi
  void *v12; // rbx
  void *v13; // rcx
  const struct std::nothrow_t *v14; // rdx
  __int64 v16; // rax
  char *v17; // rax
  signed int LastError; // eax
  __int64 v19; // rax
  signed int v20; // eax
  __int64 v21; // rax
  signed int v22; // eax
  __int64 v23; // rax
  size_t v24; // rbx
  const char *v25; // [rsp+38h] [rbp-41h] BYREF
  int v26; // [rsp+40h] [rbp-39h]
  void *Src[2]; // [rsp+48h] [rbp-31h]
  char *v28; // [rsp+58h] [rbp-21h]
  _BYTE v29[112]; // [rsp+60h] [rbp-19h] BYREF
  DWORD TokenInformationLength; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int64 v31; // [rsp+F0h] [rbp+77h] BYREF
  void *v32; // [rsp+F8h] [rbp+7Fh] BYREF

  TokenInformationLength = 0;
  *(_OWORD *)Src = 0;
  v28 = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v25 = ".\\statechangenotifier.cpp";
    v26 = 28;
    v16 = cdp::MakeException<cdp::HResultException<-2147418113>,>(v29, &v25, "Expected ERROR_INSUFFICIENT_BUFFER");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v25, v16);
  }
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v25 = ".\\statechangenotifier.cpp";
    v26 = 31;
    v19 = cdp::MakeException<cdp::hresult_exception,>(
            v29,
            &v25,
            (unsigned int)LastError,
            "Expected ERROR_INSUFFICIENT_BUFFER");
    cdp::CdpThrow<cdp::hresult_exception>(&v25, v19);
  }
  v2 = TokenInformationLength;
  v3 = (char *)Src[0];
  v4 = (char *)Src[1] - (char *)Src[0];
  if ( (void *)TokenInformationLength < (void *)((char *)Src[1] - (char *)Src[0]) )
  {
    v17 = (char *)Src[0] + TokenInformationLength;
LABEL_23:
    Src[1] = v17;
    goto LABEL_12;
  }
  if ( (void *)TokenInformationLength <= (void *)((char *)Src[1] - (char *)Src[0]) )
    goto LABEL_12;
  v5 = v28 - (char *)Src[0];
  if ( TokenInformationLength <= (unsigned __int64)(v28 - (char *)Src[0]) )
  {
    v24 = TokenInformationLength - v4;
    memset_0(Src[1], 0, v24);
    v17 = (char *)Src[1] + v24;
    v3 = (char *)Src[0];
    goto LABEL_23;
  }
  v6 = v5 >> 1;
  v7 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v5 <= 0x7FFFFFFFFFFFFFFFLL - (v5 >> 1) )
  {
    v7 = v6 + v5;
    if ( v6 + v5 < TokenInformationLength )
      v7 = TokenInformationLength;
  }
  v3 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v7);
  memset_0(&v3[v4], 0, v2 - v4);
  memmove_0(v3, Src[0], (char *)Src[1] - (char *)Src[0]);
  if ( Src[0] )
    std::_Deallocate<16>(Src[0], v28 - (char *)Src[0]);
  Src[0] = v3;
  Src[1] = &v3[v2];
  v28 = &v3[v7];
LABEL_12:
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFCLL,
          TokenUser,
          v3,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    v25 = ".\\statechangenotifier.cpp";
    v26 = 36;
    v21 = cdp::MakeException<cdp::hresult_exception,>(v29, &v25, (unsigned int)v20, "GetTokenInformation Failed");
    cdp::CdpThrow<cdp::hresult_exception>(&v25, v21);
  }
  v8 = (PSID *)Src[0];
  LengthSid = GetLengthSid(*(PSID *)Src[0]);
  v10 = LengthSid;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( LengthSid )
  {
    v11 = std::vector<unsigned char>::_Calculate_growth(a1, LengthSid);
    v12 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v11);
    memset_0(v12, 0, v10);
    memmove_0(v12, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
    std::vector<unsigned char>::_Change_array(a1, v12, v10, v11);
  }
  if ( !CopySid(v10, *(PSID *)a1, *v8) )
  {
    v22 = GetLastError();
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    v25 = ".\\statechangenotifier.cpp";
    v26 = 45;
    v23 = cdp::MakeException<cdp::hresult_exception,>(v29, &v25, (unsigned int)v22, "CopySid Failed");
    cdp::CdpThrow<cdp::hresult_exception>(&v25, v23);
  }
  v13 = Src[0];
  if ( Src[0] )
  {
    v14 = (const struct std::nothrow_t *)(v28 - (char *)Src[0]);
    v31 = v28 - (char *)Src[0];
    v32 = Src[0];
    if ( (unsigned __int64)(v28 - (char *)Src[0]) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v32, &v31);
      v14 = (const struct std::nothrow_t *)v31;
      v13 = v32;
    }
    operator delete(v13, v14);
  }
  return a1;
}

```

## disassembly

```asm
0x180096098  mov     [rsp-8+arg_0], rcx
0x18009609d  push    rbp
0x18009609e  push    rbx
0x18009609f  push    rsi
0x1800960a0  push    rdi
0x1800960a1  push    r14
0x1800960a3  push    r15
0x1800960a5  lea     rbp, [rsp-2Fh]
0x1800960aa  sub     rsp, 0A8h
0x1800960b1  mov     rsi, rcx
0x1800960b4  mov     [rbp+57h+var_A0], 0
0x1800960bb  mov     [rbp+57h+TokenInformationLength], 0
0x1800960c2  xorps   xmm0, xmm0
0x1800960c5  movdqu  xmmword ptr [rbp+57h+Src], xmm0
0x1800960ca  mov     [rbp+57h+var_78], 0
0x1800960d2  lea     rax, [rbp+57h+TokenInformationLength]
0x1800960d6  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800960db  xor     r9d, r9d; TokenInformationLength
0x1800960de  xor     r8d, r8d; TokenInformation
0x1800960e1  lea     edx, [r9+1]; TokenInformationClass
0x1800960e5  lea     rcx, [r9-4]; TokenHandle
0x1800960e9  call    cs:__imp_GetTokenInformation
0x1800960ef  test    eax, eax
0x1800960f1  jnz     loc_1800962AD
0x1800960f7  call    cs:__imp_GetLastError
0x1800960fd  cmp     eax, 7Ah ; 'z'
0x180096100  jnz     loc_1800962EE
0x180096106  mov     ebx, [rbp+57h+TokenInformationLength]
0x180096109  mov     rdi, [rbp+57h+Src]
0x18009610d  mov     r14, [rbp+57h+Src+8]
0x180096111  mov     r15, r14
0x180096114  sub     r15, rdi
0x180096117  cmp     rbx, r15
0x18009611a  jb      loc_1800962E1
0x180096120  jbe     loc_1800961B4
0x180096126  mov     rcx, [rbp+57h+var_78]
0x18009612a  sub     rcx, rdi
0x18009612d  cmp     rbx, rcx
0x180096130  jbe     loc_1800963C6
0x180096136  mov     rdx, rcx
0x180096139  shr     rdx, 1
0x18009613c  mov     r14, 7FFFFFFFFFFFFFFFh
0x180096146  mov     rax, r14
0x180096149  sub     rax, rdx
0x18009614c  cmp     rcx, rax
0x18009614f  ja      short loc_18009615C
0x180096151  lea     r14, [rdx+rcx]
0x180096155  cmp     r14, rbx
0x180096158  cmovb   r14, rbx
0x18009615c  mov     rcx, r14
0x18009615f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180096164  mov     rdi, rax
0x180096167  mov     r8, rbx
0x18009616a  sub     r8, r15; Size
0x18009616d  lea     rcx, [rax+r15]; void *
0x180096171  xor     edx, edx; Val
0x180096173  call    memset_0
0x180096178  mov     rdx, [rbp+57h+Src]; Src
0x18009617c  mov     r8, [rbp+57h+Src+8]
0x180096180  sub     r8, rdx; Size
0x180096183  mov     rcx, rdi; void *
0x180096186  call    memmove_0
0x18009618b  mov     rcx, [rbp+57h+Src]
0x18009618f  test    rcx, rcx
0x180096192  jz      short loc_1800961A0
0x180096194  mov     rdx, [rbp+57h+var_78]
0x180096198  sub     rdx, rcx
0x18009619b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800961a0  mov     [rbp+57h+Src], rdi
0x1800961a4  lea     rax, [rdi+rbx]
0x1800961a8  mov     [rbp+57h+Src+8], rax
0x1800961ac  lea     rax, [r14+rdi]
0x1800961b0  mov     [rbp+57h+var_78], rax
0x1800961b4  lea     rax, [rbp+57h+TokenInformationLength]
0x1800961b8  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800961bd  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800961c1  mov     r8, rdi; TokenInformation
0x1800961c4  mov     edx, 1; TokenInformationClass
0x1800961c9  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800961d0  call    cs:__imp_GetTokenInformation
0x1800961d6  test    eax, eax
0x1800961d8  jz      loc_180096333
0x1800961de  mov     r15, [rbp+57h+Src]
0x1800961e2  mov     rcx, [r15]; pSid
0x1800961e5  call    cs:__imp_GetLengthSid
0x1800961eb  mov     r14d, eax
0x1800961ee  mov     qword ptr [rsi], 0
0x1800961f5  mov     qword ptr [rsi+8], 0
0x1800961fd  mov     qword ptr [rsi+10h], 0
0x180096205  mov     [rbp+57h+var_A0], 1
0x18009620c  test    eax, eax
0x18009620e  jz      short loc_180096259
0x180096210  mov     edx, r14d
0x180096213  mov     rcx, rsi
0x180096216  call    ?_Calculate_growth@?$vector@EV?$allocator@E@std@@@std@@AEBA_K_K@Z; std::vector<uchar>::_Calculate_growth(unsigned __int64)
0x18009621b  mov     rdi, rax
0x18009621e  mov     rcx, rax
0x180096221  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180096226  mov     rbx, rax
0x180096229  mov     r8d, r14d; Size
0x18009622c  xor     edx, edx; Val
0x18009622e  mov     rcx, rax; void *
0x180096231  call    memset_0
0x180096236  mov     r8, [rsi+8]
0x18009623a  sub     r8, [rsi]; Size
0x18009623d  mov     rdx, [rsi]; Src
0x180096240  mov     rcx, rbx; void *
0x180096243  call    memmove_0
0x180096248  mov     r9, rdi
0x18009624b  mov     r8d, r14d
0x18009624e  mov     rdx, rbx
0x180096251  mov     rcx, rsi
0x180096254  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x180096259  mov     r8, [r15]; pSourceSid
0x18009625c  mov     rdx, [rsi]; pDestinationSid
0x18009625f  mov     ecx, r14d; nDestinationSidLength
0x180096262  call    cs:__imp_CopySid
0x180096268  test    eax, eax
0x18009626a  jz      loc_180096378
0x180096270  mov     rcx, [rbp+57h+Src]; void *
0x180096274  test    rcx, rcx
0x180096277  jz      short loc_18009629A
0x180096279  mov     rdx, [rbp+57h+var_78]
0x18009627d  sub     rdx, rcx; struct std::nothrow_t *
0x180096280  mov     [rbp+57h+arg_10], rdx
0x180096284  mov     [rbp+57h+arg_18], rcx
0x180096288  cmp     rdx, 1000h
0x18009628f  jnb     loc_1800963FA
0x180096295  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009629a  mov     rax, rsi
0x18009629d  add     rsp, 0A8h
0x1800962a4  pop     r15
0x1800962a6  pop     r14
0x1800962a8  pop     rdi
0x1800962a9  pop     rsi
0x1800962aa  pop     rbx
0x1800962ab  pop     rbp
0x1800962ac  retn
0x1800962ad  lea     rcx, aStatechangenot; ".\\statechangenotifier.cpp"
0x1800962b4  mov     [rbp+57h+var_98], rcx
0x1800962b8  mov     [rbp+57h+var_90], 1Ch
0x1800962bf  lea     r8, aExpectedErrorI; "Expected ERROR_INSUFFICIENT_BUFFER"
0x1800962c6  lea     rdx, [rbp+57h+var_98]
0x1800962ca  lea     rcx, [rbp+57h+var_70]
0x1800962ce  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1800962d3  nop
0x1800962d4  mov     rdx, rax
0x1800962d7  lea     rcx, [rbp+57h+var_98]
0x1800962db  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800962e1  lea     rax, [rdi+rbx]
0x1800962e5  mov     [rbp+57h+Src+8], rax
0x1800962e9  jmp     loc_1800961B4
0x1800962ee  call    cs:__imp_GetLastError
0x1800962f4  test    eax, eax
0x1800962f6  jg      loc_1800963B9
0x1800962fc  lea     rcx, aStatechangenot; ".\\statechangenotifier.cpp"
0x180096303  mov     [rbp+57h+var_98], rcx
0x180096307  mov     [rbp+57h+var_90], 1Fh
0x18009630e  lea     r9, aExpectedErrorI; "Expected ERROR_INSUFFICIENT_BUFFER"
0x180096315  mov     r8d, eax
0x180096318  lea     rdx, [rbp+57h+var_98]
0x18009631c  lea     rcx, [rbp+57h+var_70]
0x180096320  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180096325  nop
0x180096326  mov     rdx, rax
0x180096329  lea     rcx, [rbp+57h+var_98]
0x18009632d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180096333  call    cs:__imp_GetLastError
0x180096339  test    eax, eax
0x18009633b  jg      loc_1800963E3
0x180096341  lea     rcx, aStatechangenot; ".\\statechangenotifier.cpp"
0x180096348  mov     [rbp+57h+var_98], rcx
0x18009634c  mov     [rbp+57h+var_90], 24h ; '$'
0x180096353  lea     r9, aGettokeninform; "GetTokenInformation Failed"
0x18009635a  mov     r8d, eax
0x18009635d  lea     rdx, [rbp+57h+var_98]
0x180096361  lea     rcx, [rbp+57h+var_70]
0x180096365  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18009636a  nop
0x18009636b  mov     rdx, rax
0x18009636e  lea     rcx, [rbp+57h+var_98]
0x180096372  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180096378  call    cs:__imp_GetLastError
0x18009637e  test    eax, eax
0x180096380  jg      short loc_1800963F0
0x180096382  lea     rcx, aStatechangenot; ".\\statechangenotifier.cpp"
0x180096389  mov     [rbp+57h+var_98], rcx
0x18009638d  mov     [rbp+57h+var_90], 2Dh ; '-'
0x180096394  lea     r9, aCopysidFailed; "CopySid Failed"
0x18009639b  mov     r8d, eax
0x18009639e  lea     rdx, [rbp+57h+var_98]
0x1800963a2  lea     rcx, [rbp+57h+var_70]
0x1800963a6  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800963ab  nop
0x1800963ac  mov     rdx, rax
0x1800963af  lea     rcx, [rbp+57h+var_98]
0x1800963b3  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800963b9  movzx   eax, ax
0x1800963bc  or      eax, 80070000h
0x1800963c1  jmp     loc_1800962FC
0x1800963c6  sub     rbx, r15
0x1800963c9  mov     r8, rbx; Size
0x1800963cc  xor     edx, edx; Val
0x1800963ce  mov     rcx, r14; void *
0x1800963d1  call    memset_0
0x1800963d6  lea     rax, [r14+rbx]
0x1800963da  mov     rdi, [rbp+57h+Src]
0x1800963de  jmp     loc_1800962E5
0x1800963e3  movzx   eax, ax
0x1800963e6  or      eax, 80070000h
0x1800963eb  jmp     loc_180096341
0x1800963f0  movzx   eax, ax
0x1800963f3  or      eax, 80070000h
0x1800963f8  jmp     short loc_180096382
0x1800963fa  lea     rdx, [rbp+57h+arg_10]; unsigned __int64 *
0x1800963fe  lea     rcx, [rbp+57h+arg_18]; void **
0x180096402  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180096407  mov     rdx, [rbp+57h+arg_10]
0x18009640b  mov     rcx, [rbp+57h+arg_18]
0x18009640f  jmp     loc_180096295
```
