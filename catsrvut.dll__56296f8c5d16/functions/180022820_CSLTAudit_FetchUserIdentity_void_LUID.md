# CSLTAudit::FetchUserIdentity(void * *,_LUID * *)

- ea: `0x180022820`
- end: `0x180022a63`
- name: `?FetchUserIdentity@CSLTAudit@@EEAAJPEAPEAXPEAPEAU_LUID@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, void **, struct _LUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180022820`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002296c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002296c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800228ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800229c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800228ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800229c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022a13`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180022848`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180022848`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180022a49`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180022a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022876`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022860`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800228bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022919`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002299c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800229f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800228bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022919`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002299c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800229f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002293a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002293a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::FetchUserIdentity(CSLTAudit *this, void **a2, struct _LUID **a3)
{
  int v5; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v8; // eax
  PSID *v9; // rsi
  signed int v10; // eax
  SIZE_T LengthSid; // rbx
  void *v12; // rax
  signed int v13; // eax
  _QWORD *v14; // rsi
  signed int v15; // eax
  struct _LUID *v16; // rcx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = CoImpersonateClient();
  if ( v5 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_33;
    }
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      goto LABEL_10;
    v8 = GetLastError();
    v5 = v8;
    if ( v8 == 122 )
      goto LABEL_10;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_10:
      v9 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
      if ( !v9 )
        goto LABEL_24;
      if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v9);
        v12 = CoTaskMemAlloc(LengthSid);
        *a2 = v12;
        if ( v12 )
        {
          memcpy_0(v12, *v9, LengthSid);
          v5 = 0;
        }
        else
        {
          v5 = -2147024882;
        }
      }
      else
      {
        v10 = GetLastError();
        v5 = v10;
        if ( v10 > 0 )
          v5 = (unsigned __int16)v10 | 0x80070000;
      }
      CoTaskMemFree(v9);
      if ( v5 < 0 )
        goto LABEL_32;
      TokenInformationLength = 0;
      if ( !GetTokenInformation(TokenHandle, TokenStatistics, 0, 0, &TokenInformationLength) )
      {
        v13 = GetLastError();
        v5 = v13;
        if ( v13 != 122 )
        {
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
          if ( v5 < 0 )
            goto LABEL_32;
        }
      }
      v14 = CoTaskMemAlloc(TokenInformationLength);
      if ( v14 )
      {
        if ( GetTokenInformation(TokenHandle, TokenStatistics, v14, TokenInformationLength, &TokenInformationLength) )
        {
          v16 = (struct _LUID *)CoTaskMemAlloc(8u);
          *a3 = v16;
          if ( v16 )
          {
            *v16 = (struct _LUID)v14[1];
            v5 = 0;
          }
          else
          {
            v5 = -2147024882;
          }
        }
        else
        {
          v15 = GetLastError();
          v5 = v15;
          if ( v15 > 0 )
            v5 = (unsigned __int16)v15 | 0x80070000;
        }
        CoTaskMemFree(v14);
      }
      else
      {
LABEL_24:
        v5 = -2147024882;
      }
    }
LABEL_32:
    CloseHandle(TokenHandle);
LABEL_33:
    CoRevertToSelf();
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022820  mov     [rsp-28h+arg_0], rbx
0x180022825  push    rbp
0x180022826  push    rsi
0x180022827  push    r12
0x180022829  push    r14
0x18002282b  push    r15
0x18002282d  mov     rbp, rsp
0x180022830  sub     rsp, 30h
0x180022834  mov     r12, r8
0x180022837  mov     r15, rdx
0x18002283a  mov     qword ptr [r8], 0
0x180022841  mov     qword ptr [rdx], 0
0x180022848  call    cs:__imp_CoImpersonateClient
0x18002284e  mov     ebx, eax
0x180022850  test    eax, eax
0x180022852  js      loc_180022A4F
0x180022858  mov     [rbp+TokenHandle], 0
0x180022860  call    cs:__imp_GetCurrentThread
0x180022866  mov     rcx, rax; ThreadHandle
0x180022869  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002286d  mov     edx, 8; DesiredAccess
0x180022872  lea     r8d, [rdx-7]; OpenAsSelf
0x180022876  call    cs:__imp_OpenThreadToken
0x18002287c  test    eax, eax
0x18002287e  jnz     short loc_18002289E
0x180022880  call    cs:__imp_GetLastError
0x180022886  mov     ebx, eax
0x180022888  test    eax, eax
0x18002288a  jle     loc_180022A49
0x180022890  movzx   ebx, ax
0x180022893  or      ebx, 80070000h
0x180022899  jmp     loc_180022A49
0x18002289e  mov     [rbp+TokenInformationLength], 0
0x1800228a5  lea     rax, [rbp+TokenInformationLength]
0x1800228a9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800228ae  xor     r9d, r9d; TokenInformationLength
0x1800228b1  xor     r8d, r8d; TokenInformation
0x1800228b4  lea     edx, [r9+1]; TokenInformationClass
0x1800228b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800228bc  call    cs:__imp_GetTokenInformation
0x1800228c2  mov     r14d, 80070000h
0x1800228c8  test    eax, eax
0x1800228ca  jnz     short loc_1800228EB
0x1800228cc  call    cs:__imp_GetLastError
0x1800228d2  mov     ebx, eax
0x1800228d4  cmp     eax, 7Ah ; 'z'
0x1800228d7  jz      short loc_1800228EB
0x1800228d9  test    eax, eax
0x1800228db  jle     short loc_1800228E3
0x1800228dd  movzx   ebx, ax
0x1800228e0  or      ebx, r14d
0x1800228e3  test    ebx, ebx
0x1800228e5  js      loc_180022A3F
0x1800228eb  mov     ecx, [rbp+TokenInformationLength]; cb
0x1800228ee  call    cs:__imp_CoTaskMemAlloc
0x1800228f4  mov     rsi, rax
0x1800228f7  test    rax, rax
0x1800228fa  jz      loc_1800229D2
0x180022900  lea     rax, [rbp+TokenInformationLength]
0x180022904  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022909  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002290d  mov     r8, rsi; TokenInformation
0x180022910  mov     edx, 1; TokenInformationClass
0x180022915  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022919  call    cs:__imp_GetTokenInformation
0x18002291f  test    eax, eax
0x180022921  jnz     short loc_180022937
0x180022923  call    cs:__imp_GetLastError
0x180022929  mov     ebx, eax
0x18002292b  test    eax, eax
0x18002292d  jle     short loc_180022969
0x18002292f  movzx   ebx, ax
0x180022932  or      ebx, r14d
0x180022935  jmp     short loc_180022969
0x180022937  mov     rcx, [rsi]; pSid
0x18002293a  call    cs:__imp_GetLengthSid
0x180022940  mov     ebx, eax
0x180022942  mov     ecx, eax; cb
0x180022944  call    cs:__imp_CoTaskMemAlloc
0x18002294a  mov     [r15], rax
0x18002294d  test    rax, rax
0x180022950  jnz     short loc_180022959
0x180022952  mov     ebx, 8007000Eh
0x180022957  jmp     short loc_180022969
0x180022959  mov     r8, rbx; Size
0x18002295c  mov     rdx, [rsi]; Src
0x18002295f  mov     rcx, rax; void *
0x180022962  call    memcpy_0
0x180022967  xor     ebx, ebx
0x180022969  mov     rcx, rsi; pv
0x18002296c  call    cs:__imp_CoTaskMemFree
0x180022972  nop
0x180022973  test    ebx, ebx
0x180022975  js      loc_180022A3F
0x18002297b  mov     [rbp+TokenInformationLength], 0
0x180022982  lea     rax, [rbp+TokenInformationLength]
0x180022986  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002298b  xor     r9d, r9d; TokenInformationLength
0x18002298e  xor     r8d, r8d; TokenInformation
0x180022991  lea     r15d, [r9+0Ah]
0x180022995  mov     edx, r15d; TokenInformationClass
0x180022998  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002299c  call    cs:__imp_GetTokenInformation
0x1800229a2  test    eax, eax
0x1800229a4  jnz     short loc_1800229C1
0x1800229a6  call    cs:__imp_GetLastError
0x1800229ac  mov     ebx, eax
0x1800229ae  cmp     eax, 7Ah ; 'z'
0x1800229b1  jz      short loc_1800229C1
0x1800229b3  test    eax, eax
0x1800229b5  jle     short loc_1800229BD
0x1800229b7  movzx   ebx, ax
0x1800229ba  or      ebx, r14d
0x1800229bd  test    ebx, ebx
0x1800229bf  js      short loc_180022A3F
0x1800229c1  mov     ecx, [rbp+TokenInformationLength]; cb
0x1800229c4  call    cs:__imp_CoTaskMemAlloc
0x1800229ca  mov     rsi, rax
0x1800229cd  test    rax, rax
0x1800229d0  jnz     short loc_1800229D9
0x1800229d2  mov     ebx, 8007000Eh
0x1800229d7  jmp     short loc_180022A3F
0x1800229d9  lea     rax, [rbp+TokenInformationLength]
0x1800229dd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800229e2  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800229e6  mov     r8, rsi; TokenInformation
0x1800229e9  mov     edx, r15d; TokenInformationClass
0x1800229ec  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800229f0  call    cs:__imp_GetTokenInformation
0x1800229f6  test    eax, eax
0x1800229f8  jnz     short loc_180022A0E
0x1800229fa  call    cs:__imp_GetLastError
0x180022a00  mov     ebx, eax
0x180022a02  test    eax, eax
0x180022a04  jle     short loc_180022A35
0x180022a06  movzx   ebx, ax
0x180022a09  or      ebx, r14d
0x180022a0c  jmp     short loc_180022A35
0x180022a0e  mov     ecx, 8; cb
0x180022a13  call    cs:__imp_CoTaskMemAlloc
0x180022a19  mov     rcx, rax
0x180022a1c  mov     [r12], rax
0x180022a20  test    rax, rax
0x180022a23  jnz     short loc_180022A2C
0x180022a25  mov     ebx, 8007000Eh
0x180022a2a  jmp     short loc_180022A35
0x180022a2c  mov     rax, [rsi+8]
0x180022a30  mov     [rcx], rax
0x180022a33  xor     ebx, ebx
0x180022a35  mov     rcx, rsi; pv
0x180022a38  call    cs:__imp_CoTaskMemFree
0x180022a3e  nop
0x180022a3f  mov     rcx, [rbp+TokenHandle]; hObject
0x180022a43  call    cs:__imp_CloseHandle
0x180022a49  call    cs:__imp_CoRevertToSelf
0x180022a4f  mov     eax, ebx
0x180022a51  mov     rbx, [rsp+30h+arg_0]
0x180022a56  add     rsp, 30h
0x180022a5a  pop     r15
0x180022a5c  pop     r14
0x180022a5e  pop     r12
0x180022a60  pop     rsi
0x180022a61  pop     rbp
0x180022a62  retn
```
