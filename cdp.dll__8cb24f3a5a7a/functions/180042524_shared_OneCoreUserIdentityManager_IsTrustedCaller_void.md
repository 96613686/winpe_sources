# shared::OneCoreUserIdentityManager::IsTrustedCaller(void)

- ea: `0x180042524`
- end: `0x1800426f3`
- name: `?IsTrustedCaller@OneCoreUserIdentityManager@shared@@AEAA_NXZ`
- size: `463`
- prototype: `bool __fastcall(shared::OneCoreUserIdentityManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180041880`
- `0x1800ec200`

## callees

- `0x18001ee70`
- `0x180042524`
- `0x180042914`
- `0x18014946c`
- `0x1801f6fb0`
- `0x180223200`
- `0x1802398a8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426e8`
- `ntdll!RtlSidDominates` at `0x1800425d0`
- `ntdll!RtlSidDominates` at `0x1800425d0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180042586`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180042586`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800425b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800425b4`

## string_xrefs

- `0x180042686`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failed to get user token from calling context"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall shared::OneCoreUserIdentityManager::IsTrustedCaller(
        shared::OneCoreUserIdentityManager *this,
        void **a2)
{
  int v2; // ecx
  int v3; // r9d
  bool v4; // bl
  HANDLE v5; // rdi
  const char *v6; // r9
  int v7; // eax
  __int64 v8; // rdx
  signed int LastError; // eax
  int v10; // ecx
  int v11; // r9d
  const char *v12; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  _BYTE v15[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbSid[2]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD TokenInformation[12]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  TokenHandle = 0;
  cbSid[0] = shared::GetCurrentUserToken(&TokenHandle, a2);
  if ( (cbSid[0] & 0x80000000) != 0 )
  {
    v16 = 390;
    Log<long &,char const (&)[33],int>(
      v2,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failed to get user token from calling context\"}",
      (unsigned int)cbSid,
      v3,
      (__int64)&v16);
    v4 = 0;
    goto LABEL_10;
  }
  v4 = 0;
  v5 = TokenHandle;
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinMediumLabelSid, 0, pSid, cbSid) )
  {
    v16 = 84;
    if ( GetTokenInformation(v5, TokenIntegrityLevel, TokenInformation, 0x54u, &v16) )
    {
      v15[0] = 0;
      v7 = RtlSidDominates(TokenInformation[0], pSid, v15);
      if ( v7 >= 0 )
      {
        v4 = v15[0] == 1;
        goto LABEL_10;
      }
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x34D,
                    (unsigned int)".\\platformshared.cpp",
                    (const char *)(unsigned int)v7,
                    ReturnLength);
      goto LABEL_8;
    }
    v8 = 842;
  }
  else
  {
    v8 = 834;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v8,
                (unsigned int)".\\platformshared.cpp",
                v6);
LABEL_8:
  v16 = LastError;
  if ( LastError < 0 )
  {
    cbSid[0] = 397;
    Log<long &,char const (&)[33],int>(
      v10,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failed to check if caller is Medium IL or higher\"}",
      (unsigned int)&v16,
      v11,
      (__int64)cbSid);
  }
LABEL_10:
  v12 = qword_1803986E0;
  if ( !v4 )
    v12 = "not";
  *(_QWORD *)cbSid = v12;
  Log<unsigned __int64 &>(4, "{\"text\":\"Calling context is %s Medium IL or higher\"}", (const char *)cbSid);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180042524  mov     [rsp-8+arg_0], rbx
0x180042529  mov     [rsp-8+arg_8], rdi
0x18004252e  push    rbp
0x18004252f  lea     rbp, [rsp-10h]
0x180042534  sub     rsp, 110h
0x18004253b  mov     rax, cs:__security_cookie
0x180042542  xor     rax, rsp
0x180042545  mov     [rbp+10h+var_10], rax
0x180042549  mov     [rsp+110h+TokenHandle], 0
0x180042552  lea     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x180042557  call    ?GetCurrentUserToken@shared@@YAJPEAPEAX@Z; shared::GetCurrentUserToken(void * *)
0x18004255c  mov     [rsp+110h+cbSid], eax
0x180042560  test    eax, eax
0x180042562  js      loc_18004266F
0x180042568  xor     bl, bl
0x18004256a  mov     rdi, [rsp+110h+TokenHandle]
0x18004256f  mov     [rsp+110h+cbSid], 44h ; 'D'
0x180042577  lea     r9, [rsp+110h+cbSid]; cbSid
0x18004257c  lea     r8, [rsp+110h+pSid]; pSid
0x180042581  xor     edx, edx; DomainSid
0x180042583  lea     ecx, [rdx+43h]; WellKnownSidType
0x180042586  call    cs:__imp_CreateWellKnownSid
0x18004258c  test    eax, eax
0x18004258e  jz      loc_180042699
0x180042594  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18004259a  mov     [rsp+110h+var_DC], r9d
0x18004259f  lea     rax, [rsp+110h+var_DC]
0x1800425a4  mov     qword ptr [rsp+110h+ReturnLength], rax; int
0x1800425a9  lea     r8, [rbp+10h+TokenInformation]; TokenInformation
0x1800425ad  lea     edx, [r9-3Bh]; TokenInformationClass
0x1800425b1  mov     rcx, rdi; TokenHandle
0x1800425b4  call    cs:__imp_GetTokenInformation
0x1800425ba  test    eax, eax
0x1800425bc  jz      short loc_1800425E8
0x1800425be  mov     [rsp+110h+var_E0], bl
0x1800425c2  lea     r8, [rsp+110h+var_E0]
0x1800425c7  lea     rdx, [rsp+110h+pSid]
0x1800425cc  mov     rcx, [rbp+10h+TokenInformation]
0x1800425d0  call    cs:__imp_RtlSidDominates
0x1800425d6  test    eax, eax
0x1800425d8  js      loc_1800426A3
0x1800425de  cmp     [rsp+110h+var_E0], 1
0x1800425e3  setz    bl
0x1800425e6  jmp     short loc_180042609
0x1800425e8  mov     edx, 34Ah; void *
0x1800425ed  lea     r8, aPlatformshared; ".\\platformshared.cpp"
0x1800425f4  mov     rcx, [rbp+18h]; this
0x1800425f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800425fd  mov     [rsp+110h+var_DC], eax
0x180042601  test    eax, eax
0x180042603  js      loc_1800426C0
0x180042609  lea     rcx, aNot; "not"
0x180042610  lea     rax, qword_1803986E0
0x180042617  test    bl, bl
0x180042619  cmovz   rax, rcx
0x18004261d  mov     qword ptr [rsp+110h+cbSid], rax
0x180042622  lea     r8, [rsp+110h+cbSid]
0x180042627  lea     rdx, aTextCallingCon; "{\"text\":\"Calling context is %s Mediu"...
0x18004262e  mov     ecx, 4
0x180042633  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x180042638  nop
0x180042639  mov     rcx, [rsp+110h+TokenHandle]; hObject
0x18004263e  lea     rdx, [rcx-1]
0x180042642  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180042646  jbe     loc_1800426E8
0x18004264c  mov     al, bl
0x18004264e  mov     rcx, [rbp+10h+var_10]
0x180042652  xor     rcx, rsp; StackCookie
0x180042655  call    __security_check_cookie
0x18004265a  lea     r11, [rsp+110h+var_s0]
0x180042662  mov     rbx, [r11+10h]
0x180042666  mov     rdi, [r11+18h]
0x18004266a  mov     rsp, r11
0x18004266d  pop     rbp
0x18004266e  retn
0x18004266f  mov     [rsp+110h+var_DC], 186h
0x180042677  lea     rax, [rsp+110h+var_DC]
0x18004267c  mov     qword ptr [rsp+110h+ReturnLength], rax
0x180042681  lea     r8, [rsp+110h+cbSid]
0x180042686  lea     rdx, aHr0x08xFileSLi_25; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004268d  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x180042692  xor     bl, bl
0x180042694  jmp     loc_180042609
0x180042699  mov     edx, 342h
0x18004269e  jmp     loc_1800425ED
0x1800426a3  mov     rcx, [rbp+18h]; this
0x1800426a7  mov     r9d, eax; char *
0x1800426aa  lea     r8, aPlatformshared; ".\\platformshared.cpp"
0x1800426b1  mov     edx, 34Dh; void *
0x1800426b6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800426bb  jmp     loc_1800425FD
0x1800426c0  mov     [rsp+110h+cbSid], 18Dh
0x1800426c8  lea     rax, [rsp+110h+cbSid]
0x1800426cd  mov     qword ptr [rsp+110h+ReturnLength], rax
0x1800426d2  lea     r8, [rsp+110h+var_DC]
0x1800426d7  lea     rdx, aHr0x08xFileSLi_12; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800426de  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x1800426e3  jmp     loc_180042609
0x1800426e8  call    cs:__imp_CloseHandle
0x1800426ee  jmp     loc_18004264C
```
