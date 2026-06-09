# ServiceUserTokenHelper::GetServiceNamesFromToken(void *,bool,std::vector<GenericStringHandle<ushort>,std::allocator<GenericStringHandle<ushort>>> *)

- ea: `0x18005aba0`
- end: `0x18005b1c8`
- name: `?GetServiceNamesFromToken@ServiceUserTokenHelper@@SAJPEAX_NPEAV?$vector@V?$GenericStringHandle@G@@V?$allocator@V?$GenericStringHandle@G@@@std@@@std@@@Z`
- size: `1576`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019690`
- `0x18005a2cc`
- `0x18005a720`
- `0x1800e0b60`

## callees

- `0x180006640`
- `0x180012c00`
- `0x1800543a0`
- `0x18005aba0`
- `0x18009bfcc`
- `0x18009cab8`
- `0x1800a2a0c`
- `0x1800a3444`
- `0x1800a3de8`
- `0x1800ab308`
- `0x1800f9948`
- `0x1800f996c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b05a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005b05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ac41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b070`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b070`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005afab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005afab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005af96`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18005af96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ac37`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ae07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ac37`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005ae07`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceUserTokenHelper::GetServiceNamesFromToken(HANDLE TokenHandle, char a2, __int64 a3)
{
  HANDLE v4; // r15
  void **v5; // rbx
  void **v6; // r14
  unsigned int v7; // edi
  BOOL TokenInformation; // eax
  __int64 v9; // r13
  _QWORD *v10; // r14
  SIZE_T v11; // rbx
  __int64 v12; // r15
  SIZE_T v13; // r12
  LPVOID v14; // rax
  __int64 v15; // r14
  signed __int64 v16; // r13
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  char *v19; // r15
  LPVOID v20; // rax
  unsigned __int64 v21; // rdx
  void *v22; // rcx
  int v23; // eax
  PSID *v24; // rbx
  int ServiceNameFromServiceSid; // eax
  volatile signed __int32 **v26; // rdx
  volatile signed __int32 *v27; // rcx
  unsigned __int64 v28; // rdx
  void *v29; // rcx
  __int64 result; // rax
  unsigned int LastError; // eax
  unsigned int v32; // eax
  const ComError *v33; // rbx
  void *Src[2]; // [rsp+30h] [rbp-1E8h]
  char *v35; // [rsp+40h] [rbp-1D8h]
  const ComError *v36; // [rsp+50h] [rbp-1C8h] BYREF
  _BYTE pExceptionObject[96]; // [rsp+60h] [rbp-1B8h] BYREF
  _BYTE v38[96]; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v39[96]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v40[152]; // [rsp+180h] [rbp-98h] BYREF
  DWORD TokenInformationLength; // [rsp+230h] [rbp+18h] BYREF
  void *v44; // [rsp+238h] [rbp+20h] BYREF

  v4 = TokenHandle;
  v5 = *(void ***)a3;
  v6 = *(void ***)(a3 + 8);
  v7 = 0;
  if ( *(void ***)a3 != v6 )
  {
    do
    {
      if ( *v5 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v5 + 2, 0xFFFFFFFF) == 1 )
          operator delete(*v5, 0x10u);
        *v5 = 0;
      }
      ++v5;
    }
    while ( v5 != v6 );
    *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  }
  *(_OWORD *)Src = 0;
  v35 = 0;
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(v4, TokenGroups, 0, 0, &TokenInformationLength);
  try
  {
    if ( !TokenInformation && GetLastError() != 122 )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      ComError::ComError((ComError *)pExceptionObject, LastError, 0x26u);
      throw (ComError *)pExceptionObject;
    }
    v9 = TokenInformationLength;
    v10 = 0;
    v44 = 0;
    if ( TokenInformationLength )
    {
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      v12 = TokenInformationLength;
      if ( TokenInformationLength < 0x1000uLL )
      {
        v10 = operator new(TokenInformationLength);
        v13 = 0x8000000000000026uLL;
      }
      else
      {
        if ( (unsigned __int64)TokenInformationLength + 39 < TokenInformationLength )
          std::_Throw_bad_array_new_length();
        v13 = 0x8000000000000026uLL;
        v14 = operator new(TokenInformationLength + 39LL);
        if ( !v14 )
          goto LABEL_36;
        v10 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v10 - 1) = v14;
      }
      memset_0((char *)v44 + (_QWORD)v10, 0, v9 - (_QWORD)v44);
      memmove_0(v10, 0, 0);
      Src[0] = v10;
      Src[1] = (char *)v10 + v9;
      v35 = (char *)v10 + v12;
      v4 = TokenHandle;
    }
    else
    {
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      v13 = 0x8000000000000026uLL;
    }
    if ( !GetTokenInformation(v4, TokenGroups, v10, TokenInformationLength, &TokenInformationLength) )
    {
      if ( (int)GetLastError() > 0 )
        v32 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v32 = GetLastError();
      ComError::ComError((ComError *)v38, v32, 0x33u);
      throw (ComError *)v38;
    }
    v15 = TokenInformationLength;
    v16 = (char *)Src[1] - (char *)Src[0];
    if ( (void *)TokenInformationLength <= (void *)((char *)Src[1] - (char *)Src[0]) )
      goto LABEL_41;
    v17 = v35 - (char *)Src[0];
    if ( TokenInformationLength <= (unsigned __int64)(v35 - (char *)Src[0]) )
    {
      memset_0(Src[1], 0, TokenInformationLength - v16);
      goto LABEL_41;
    }
    v18 = v17 >> 1;
    if ( v17 <= 0x7FFFFFFFFFFFFFFFLL - (v17 >> 1) )
    {
      v11 = v18 + v17;
      if ( v18 + v17 < TokenInformationLength )
        v11 = TokenInformationLength;
      if ( !v11 )
      {
        v19 = 0;
LABEL_32:
        memset_0(&v19[v16], 0, v15 - v16);
        memmove_0(v19, Src[0], (char *)Src[1] - (char *)Src[0]);
        if ( !Src[0] )
        {
LABEL_39:
          Src[0] = v19;
          v35 = &v19[v11];
LABEL_41:
          v23 = wil::impersonate_token_nothrow(0);
          if ( v23 < 0 )
          {
            ComError::ComError((ComError *)v39, v23, 0x3Cu);
            throw (ComError *)v39;
          }
          while ( v7 < *(_DWORD *)Src[0] )
          {
            v24 = (PSID *)((char *)Src[0] + 16 * v7);
            if ( *GetSidSubAuthorityCount(v24[1])
              && *GetSidSubAuthority(v24[1], 0) == 80
              && (!a2 || ((_BYTE)v24[2] & 4) != 0) )
            {
              _InterlockedIncrement(&dword_180145058);
              v44 = &GenericStringHandle<unsigned short>::s_EmptyString;
              ServiceNameFromServiceSid = ServiceUserTokenHelper::GetServiceNameFromServiceSid(v24[1], &v44);
              if ( ServiceNameFromServiceSid < 0 )
              {
                ComError::ComError((ComError *)v40, ServiceNameFromServiceSid, 0x49u);
                throw (ComError *)v40;
              }
              v26 = *(volatile signed __int32 ***)(a3 + 8);
              if ( v26 == *(volatile signed __int32 ***)(a3 + 16) )
              {
                std::vector<GenericStringHandle<unsigned short>>::_Emplace_reallocate<GenericStringHandle<unsigned short> const &>(
                  a3,
                  v26,
                  &v44);
                v27 = (volatile signed __int32 *)v44;
              }
              else
              {
                v27 = (volatile signed __int32 *)v44;
                _InterlockedIncrement((volatile signed __int32 *)v44 + 2);
                *v26 = v27;
                *(_QWORD *)(a3 + 8) += 8LL;
              }
              if ( v27 )
              {
                if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
                  operator delete((void *)v27, 0x10u);
              }
            }
            ++v7;
          }
          if ( Src[0] )
          {
            v28 = v35 - (char *)Src[0];
            if ( (unsigned __int64)(v35 - (char *)Src[0]) < 0x1000 )
            {
              v29 = Src[0];
            }
            else
            {
              v29 = (void *)*((_QWORD *)Src[0] - 1);
              if ( (unsigned __int64)((char *)Src[0] - (char *)v29 - 8) > 0x1F )
                __fastfail(5u);
              v28 += 39LL;
            }
            operator delete(v29, v28);
          }
          return 0;
        }
        v21 = v35 - (char *)Src[0];
        if ( (unsigned __int64)(v35 - (char *)Src[0]) < 0x1000 )
        {
          v22 = Src[0];
          goto LABEL_38;
        }
        v22 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v22 - 8) <= 0x1F )
        {
          v21 += 39LL;
LABEL_38:
          operator delete(v22, v21);
          goto LABEL_39;
        }
LABEL_36:
        __fastfail(5u);
      }
      if ( v11 < 0x1000 )
      {
        v19 = (char *)operator new(v11);
        goto LABEL_32;
      }
      v13 = v11 + 39;
      if ( v11 + 39 < v11 )
        std::_Throw_bad_array_new_length();
    }
    v20 = operator new(v13);
    if ( !v20 )
      goto LABEL_36;
    v19 = (char *)(((unsigned __int64)v20 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)v19 - 1) = v20;
    goto LABEL_32;
  }
  catch ( const ComError *v36 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v33 = v36;
    }
    else
    {
      v33 = v36;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids,
        *((unsigned int *)v36 + 6),
        *((_DWORD *)v36 + 7));
    }
    return (DWORD)*((_DWORD *)v33 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18005aba0  mov     [rsp+arg_8], dl
0x18005aba4  mov     [rsp+TokenHandle], rcx
0x18005aba9  push    rbx
0x18005abaa  push    rsi
0x18005abab  push    rdi
0x18005abac  push    r12
0x18005abae  push    r13
0x18005abb0  push    r14
0x18005abb2  push    r15
0x18005abb4  sub     rsp, 1E0h
0x18005abbb  mov     rsi, r8
0x18005abbe  mov     r15, rcx
0x18005abc1  mov     rbx, [r8]
0x18005abc4  mov     r14, [r8+8]
0x18005abc8  xor     edi, edi
0x18005abca  cmp     rbx, r14
0x18005abcd  jz      short loc_18005AC07
0x18005abcf  nop
0x18005abd0  mov     rcx, [rbx]
0x18005abd3  test    rcx, rcx
0x18005abd6  jz      short loc_18005ABF7
0x18005abd8  mov     eax, 0FFFFFFFFh
0x18005abdd  lock xadd [rcx+8], eax
0x18005abe2  cmp     eax, 1
0x18005abe5  jnz     short loc_18005ABF4
0x18005abe7  mov     edx, 10h; unsigned __int64
0x18005abec  mov     rcx, [rbx]; void *
0x18005abef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005abf4  mov     [rbx], rdi
0x18005abf7  add     rbx, 8
0x18005abfb  cmp     rbx, r14
0x18005abfe  jnz     short loc_18005ABD0
0x18005ac00  mov     rax, [rsi]
0x18005ac03  mov     [rsi+8], rax
0x18005ac07  xorps   xmm0, xmm0
0x18005ac0a  movdqu  xmmword ptr [rsp+218h+Src], xmm0
0x18005ac10  mov     [rsp+218h+var_1D8], rdi
0x18005ac15  mov     [rsp+218h+TokenInformationLength], edi
0x18005ac1c  lea     rax, [rsp+218h+TokenInformationLength]
0x18005ac24  mov     [rsp+218h+ReturnLength], rax; ReturnLength
0x18005ac29  xor     r9d, r9d; TokenInformationLength
0x18005ac2c  xor     r8d, r8d; TokenInformation
0x18005ac2f  mov     edx, 2; TokenInformationClass
0x18005ac34  mov     rcx, r15; TokenHandle
0x18005ac37  call    cs:__imp_GetTokenInformation
0x18005ac3d  test    eax, eax
0x18005ac3f  jnz     short loc_18005AC50
0x18005ac41  call    cs:__imp_GetLastError
0x18005ac47  cmp     eax, 7Ah ; 'z'
0x18005ac4a  jnz     loc_18005B0D6
0x18005ac50  mov     r13d, [rsp+218h+TokenInformationLength]
0x18005ac58  mov     rbx, [rsp+218h+Src+8]
0x18005ac5d  mov     rax, rbx
0x18005ac60  mov     r14, [rsp+218h+Src]
0x18005ac65  sub     rax, r14
0x18005ac68  mov     [rsp+218h+arg_18], rax
0x18005ac70  cmp     r13, rax
0x18005ac73  jnb     short loc_18005AC7E
0x18005ac75  lea     rax, [r14+r13]
0x18005ac79  jmp     loc_18005ADCE
0x18005ac7e  jbe     loc_18005ADD3
0x18005ac84  mov     rcx, [rsp+218h+var_1D8]
0x18005ac89  sub     rcx, r14
0x18005ac8c  cmp     r13, rcx
0x18005ac8f  jbe     loc_18005ADB5
0x18005ac95  mov     rdx, rcx
0x18005ac98  shr     rdx, 1
0x18005ac9b  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18005aca5  mov     rax, rbx
0x18005aca8  sub     rax, rdx
0x18005acab  cmp     rcx, rax
0x18005acae  jbe     short loc_18005ACC2
0x18005acb0  mov     r15, rbx
0x18005acb3  mov     r12, 8000000000000026h
0x18005acbd  mov     rcx, r12
0x18005acc0  jmp     short loc_18005ACF7
0x18005acc2  lea     r15, [rdx+rcx]
0x18005acc6  cmp     r15, r13
0x18005acc9  cmovb   r15, r13
0x18005accd  test    r15, r15
0x18005acd0  jnz     short loc_18005ACD7
0x18005acd2  mov     r14, rdi
0x18005acd5  jmp     short loc_18005AD1E
0x18005acd7  cmp     r15, 1000h
0x18005acde  jb      short loc_18005AD13
0x18005ace0  lea     rcx, [r15+27h]; dwBytes
0x18005ace4  cmp     rcx, r15
0x18005ace7  jbe     loc_18005B119
0x18005aced  mov     r12, 8000000000000026h
0x18005acf7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005acfc  test    rax, rax
0x18005acff  jz      loc_18005AF0B
0x18005ad05  lea     r14, [rax+27h]
0x18005ad09  and     r14, 0FFFFFFFFFFFFFFE0h
0x18005ad0d  mov     [r14-8], rax
0x18005ad11  jmp     short loc_18005AD28
0x18005ad13  mov     rcx, r15; dwBytes
0x18005ad16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ad1b  mov     r14, rax
0x18005ad1e  mov     r12, 8000000000000026h
0x18005ad28  mov     r8, r13
0x18005ad2b  mov     rax, [rsp+218h+arg_18]
0x18005ad33  sub     r8, rax; Size
0x18005ad36  lea     rcx, [r14+rax]; void *
0x18005ad3a  xor     edx, edx; Val
0x18005ad3c  call    memset_0
0x18005ad41  mov     r8, [rsp+218h+Src+8]
0x18005ad46  mov     rdx, [rsp+218h+Src]; Src
0x18005ad4b  sub     r8, rdx; Size
0x18005ad4e  mov     rcx, r14; void *
0x18005ad51  call    memmove_0
0x18005ad56  mov     rax, [rsp+218h+Src]
0x18005ad5b  test    rax, rax
0x18005ad5e  jz      short loc_18005AD94
0x18005ad60  mov     rdx, [rsp+218h+var_1D8]
0x18005ad65  sub     rdx, rax; unsigned __int64
0x18005ad68  cmp     rdx, 1000h
0x18005ad6f  jb      short loc_18005AD8C
0x18005ad71  mov     rcx, [rax-8]
0x18005ad75  sub     rax, rcx
0x18005ad78  sub     rax, 8
0x18005ad7c  cmp     rax, 1Fh
0x18005ad80  ja      loc_18005AF0B
0x18005ad86  add     rdx, 27h ; '''
0x18005ad8a  jmp     short loc_18005AD8F
0x18005ad8c  mov     rcx, rax; void *
0x18005ad8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005ad94  mov     [rsp+218h+Src], r14
0x18005ad99  lea     rax, [r14+r13]
0x18005ad9d  mov     [rsp+218h+Src+8], rax
0x18005ada2  lea     rax, [r14+r15]
0x18005ada6  mov     [rsp+218h+var_1D8], rax
0x18005adab  mov     r15, [rsp+218h+TokenHandle]
0x18005adb3  jmp     short loc_18005ADE7
0x18005adb5  sub     r13, rax
0x18005adb8  mov     r8, r13; Size
0x18005adbb  xor     edx, edx; Val
0x18005adbd  mov     rcx, rbx; void *
0x18005adc0  call    memset_0
0x18005adc5  lea     rax, [rbx+r13]
0x18005adc9  mov     r14, [rsp+218h+Src]
0x18005adce  mov     [rsp+218h+Src+8], rax
0x18005add3  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18005addd  mov     r12, 8000000000000026h
0x18005ade7  lea     rax, [rsp+218h+TokenInformationLength]
0x18005adef  mov     [rsp+218h+ReturnLength], rax; ReturnLength
0x18005adf4  mov     r9d, [rsp+218h+TokenInformationLength]; TokenInformationLength
0x18005adfc  mov     r8, r14; TokenInformation
0x18005adff  mov     edx, 2; TokenInformationClass
0x18005ae04  mov     rcx, r15; TokenHandle
0x18005ae07  call    cs:__imp_GetTokenInformation
0x18005ae0d  test    eax, eax
0x18005ae0f  jz      loc_18005B11E
0x18005ae15  mov     r14d, [rsp+218h+TokenInformationLength]
0x18005ae1d  mov     r15, [rsp+218h+Src+8]
0x18005ae22  mov     r13, r15
0x18005ae25  mov     rax, [rsp+218h+Src]
0x18005ae2a  sub     r13, rax
0x18005ae2d  cmp     r14, r13
0x18005ae30  jnb     short loc_18005AE3A
0x18005ae32  add     rax, r14
0x18005ae35  jmp     loc_18005AF47
0x18005ae3a  jbe     loc_18005AF4C
0x18005ae40  mov     rcx, [rsp+218h+var_1D8]
0x18005ae45  sub     rcx, rax
0x18005ae48  cmp     r14, rcx
0x18005ae4b  jbe     loc_18005AF33
0x18005ae51  mov     rdx, rcx
0x18005ae54  shr     rdx, 1
0x18005ae57  mov     rax, rbx
0x18005ae5a  sub     rax, rdx
0x18005ae5d  cmp     rcx, rax
0x18005ae60  ja      short loc_18005AE8D
0x18005ae62  lea     rbx, [rdx+rcx]
0x18005ae66  cmp     rbx, r14
0x18005ae69  cmovb   rbx, r14
0x18005ae6d  test    rbx, rbx
0x18005ae70  jnz     short loc_18005AE77
0x18005ae72  mov     r15, rdi
0x18005ae75  jmp     short loc_18005AEB3
0x18005ae77  cmp     rbx, 1000h
0x18005ae7e  jb      short loc_18005AEA8
0x18005ae80  lea     r12, [rbx+27h]
0x18005ae84  cmp     r12, rbx
0x18005ae87  jbe     loc_18005B167
0x18005ae8d  mov     rcx, r12; dwBytes
0x18005ae90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ae95  test    rax, rax
0x18005ae98  jz      short loc_18005AF0B
0x18005ae9a  lea     r15, [rax+27h]
0x18005ae9e  and     r15, 0FFFFFFFFFFFFFFE0h
0x18005aea2  mov     [r15-8], rax
0x18005aea6  jmp     short loc_18005AEB3
0x18005aea8  mov     rcx, rbx; dwBytes
0x18005aeab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005aeb0  mov     r15, rax
0x18005aeb3  mov     r8, r14
0x18005aeb6  sub     r8, r13; Size
0x18005aeb9  lea     rcx, [r15+r13]; void *
0x18005aebd  xor     edx, edx; Val
0x18005aebf  call    memset_0
0x18005aec4  mov     r8, [rsp+218h+Src+8]
0x18005aec9  mov     rdx, [rsp+218h+Src]; Src
0x18005aece  sub     r8, rdx; Size
0x18005aed1  mov     rcx, r15; void *
0x18005aed4  call    memmove_0
0x18005aed9  mov     rax, [rsp+218h+Src]
0x18005aede  test    rax, rax
0x18005aee1  jz      short loc_18005AF1A
0x18005aee3  mov     rdx, [rsp+218h+var_1D8]
0x18005aee8  sub     rdx, rax; unsigned __int64
0x18005aeeb  cmp     rdx, 1000h
0x18005aef2  jb      short loc_18005AF12
0x18005aef4  mov     rcx, [rax-8]
0x18005aef8  sub     rax, rcx
0x18005aefb  sub     rax, 8
0x18005aeff  cmp     rax, 1Fh
0x18005af03  ja      short loc_18005AF0B
0x18005af05  add     rdx, 27h ; '''
0x18005af09  jmp     short loc_18005AF15
0x18005af0b  mov     ecx, 5
0x18005af10  int     29h; Win8: RtlFailFast(ecx)
0x18005af12  mov     rcx, rax; void *
0x18005af15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005af1a  mov     [rsp+218h+Src], r15
0x18005af1f  lea     rax, [r14+r15]
0x18005af23  mov     [rsp+218h+Src+8], rax
0x18005af28  lea     rax, [r15+rbx]
0x18005af2c  mov     [rsp+218h+var_1D8], rax
0x18005af31  jmp     short loc_18005AF4C
0x18005af33  sub     r14, r13
0x18005af36  mov     r8, r14; Size
0x18005af39  xor     edx, edx; Val
0x18005af3b  mov     rcx, r15; void *
0x18005af3e  call    memset_0
0x18005af43  lea     rax, [r14+r15]
0x18005af47  mov     [rsp+218h+Src+8], rax
0x18005af4c  mov     [rsp+218h+Token], 0FFFFFFFFFFFFFFFFh
0x18005af55  lea     rdx, [rsp+218h+Token]
0x18005af5a  xor     ecx, ecx; Token
0x18005af5c  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18005af61  test    eax, eax
0x18005af63  js      loc_18005B16D
0x18005af69  mov     r14, [rsp+218h+Src]
0x18005af6e  lea     r12, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18005af75  movzx   r15d, [rsp+218h+arg_8]
0x18005af7e  xchg    ax, ax
0x18005af80  cmp     edi, [r14]
0x18005af83  jnb     loc_18005B04A
0x18005af89  mov     ebx, edi
0x18005af8b  shl     rbx, 4
0x18005af8f  add     rbx, r14
0x18005af92  mov     rcx, [rbx+8]; pSid
0x18005af96  call    cs:__imp_GetSidSubAuthorityCount
0x18005af9c  cmp     byte ptr [rax], 0
0x18005af9f  jz      loc_18005B043
0x18005afa5  xor     edx, edx; nSubAuthority
0x18005afa7  mov     rcx, [rbx+8]; pSid
0x18005afab  call    cs:__imp_GetSidSubAuthority
0x18005afb1  cmp     dword ptr [rax], 50h ; 'P'
0x18005afb4  jnz     loc_18005B043
0x18005afba  test    r15b, r15b
0x18005afbd  jz      short loc_18005AFC5
0x18005afbf  test    byte ptr [rbx+10h], 4
0x18005afc3  jz      short loc_18005B043
0x18005afc5  lock inc cs:dword_180145058
0x18005afcc  mov     [rsp+218h+arg_18], r12
0x18005afd4  lea     rdx, [rsp+218h+arg_18]
0x18005afdc  mov     rcx, [rbx+8]; Sid
0x18005afe0  call    ?GetServiceNameFromServiceSid@ServiceUserTokenHelper@@SAJPEAXPEAV?$GenericStringHandle@G@@@Z; ServiceUserTokenHelper::GetServiceNameFromServiceSid(void *,GenericStringHandle<ushort> *)
0x18005afe5  test    eax, eax
0x18005afe7  js      loc_18005B197
0x18005afed  mov     rdx, [rsi+8]
0x18005aff1  cmp     rdx, [rsi+10h]
0x18005aff5  jz      short loc_18005B00D
0x18005aff7  mov     rcx, [rsp+218h+arg_18]
0x18005afff  lock inc dword ptr [rcx+8]
0x18005b003  mov     [rdx], rcx
0x18005b006  add     qword ptr [rsi+8], 8
0x18005b00b  jmp     short loc_18005B025
0x18005b00d  lea     r8, [rsp+218h+arg_18]
0x18005b015  mov     rcx, rsi
0x18005b018  call    ??$_Emplace_reallocate@AEBV?$GenericStringHandle@G@@@?$vector@V?$GenericStringHandle@G@@V?$allocator@V?$GenericStringHandle@G@@@std@@@std@@AEAAPEAV?$GenericStringHandle@G@@QEAV2@AEBV2@@Z; std::vector<GenericStringHandle<ushort>>::_Emplace_reallocate<GenericStringHandle<ushort> const &>(GenericStringHandle<ushort> * const,GenericStringHandle<ushort> const &)
0x18005b01d  mov     rcx, [rsp+218h+arg_18]; void *
0x18005b025  test    rcx, rcx
0x18005b028  jz      short loc_18005B043
0x18005b02a  mov     eax, 0FFFFFFFFh
0x18005b02f  lock xadd [rcx+8], eax
0x18005b034  cmp     eax, 1
0x18005b037  jnz     short loc_18005B043
0x18005b039  mov     edx, 10h; unsigned __int64
0x18005b03e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b043  inc     edi
0x18005b045  jmp     loc_18005AF80
0x18005b04a  mov     rbx, [rsp+218h+Token]
0x18005b04f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005b053  jz      short loc_18005B077
0x18005b055  mov     rdx, rbx; Token
0x18005b058  xor     ecx, ecx; Thread
0x18005b05a  call    cs:__imp_SetThreadToken
  ... truncated ...
```
