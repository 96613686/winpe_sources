# SspLogNTLMServerBlockedChallenge

- ea: `0x180051a98`
- end: `0x180051d4a`
- name: `SspLogNTLMServerBlockedChallenge`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800157b0`
- `0x18002ba90`

## callees

- `0x18002e3e8`
- `0x18002fb50`
- `0x180051104`
- `0x180051a98`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cf2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051b4c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051b4c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180051b68`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180051b68`
- `ntdll!EtwEventEnabled` at `0x180051b1f`
- `ntdll!EtwEventEnabled` at `0x180051b1f`
- `ntdll!EtwEventWrite` at `0x180051ce4`
- `ntdll!EtwEventWrite` at `0x180051ce4`
- `SspiCli!LsaGetLogonSessionData` at `0x180051bbe`
- `SspiCli!LsaGetLogonSessionData` at `0x180051bbe`
- `SspiCli!LsaFreeReturnBuffer` at `0x180051d02`
- `SspiCli!LsaFreeReturnBuffer` at `0x180051d02`

## pseudocode

```c
NTSTATUS __fastcall SspLogNTLMServerBlockedChallenge(DWORD a1, struct _LUID *a2, int a3)
{
  unsigned __int16 *v3; // rsi
  NTSTATUS result; // eax
  __int64 *v7; // rdx
  HANDLE v8; // rax
  void *v9; // r14
  int Length; // r8d
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rax
  __int64 *v14; // rdx
  DWORD dwProcessId; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v17; // [rsp+30h] [rbp-D0h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  struct ASN1objectidentifier_s *v20; // [rsp+50h] [rbp-B0h]
  DWORD *p_dwProcessId; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  WCHAR *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  struct _LUID *v25; // [rsp+80h] [rbp-80h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  PWSTR Buffer; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  PWSTR v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  WCHAR ExeName[264]; // [rsp+E0h] [rbp-20h] BYREF

  dwProcessId = a1;
  v17 = 0;
  ppLogonSessionData = 0;
  v19 = 0;
  v20 = 0;
  v3 = 0;
  dwSize = 261;
  result = SspInitEtwLogHandle();
  if ( result < 0 )
  {
LABEL_33:
    if ( ppLogonSessionData )
      result = LsaFreeReturnBuffer(ppLogonSessionData);
    if ( v3 )
      return ((__int64 (__fastcall *)(unsigned __int16 *))LsaFunctions->FreePrivateHeap)(v3);
    return result;
  }
  v7 = (__int64 *)&NTLMClientBlocked;
  if ( !a3 )
    v7 = NTLMClientBlockedAudit;
  result = EtwEventEnabled(MsvEtwLogHandle, v7);
  if ( (_BYTE)result )
  {
    p_dwProcessId = &dwProcessId;
    v22 = 4;
    v8 = OpenProcess(0x1000u, 0, dwProcessId);
    v9 = v8;
    if ( v8 && QueryFullProcessImageNameW(v8, 0, ExeName, &dwSize) && dwSize )
    {
      v23 = ExeName;
      v24 = 2 * dwSize + 2;
    }
    else
    {
      v24 = 4;
      v23 = L"-";
    }
    v25 = a2;
    v26 = 8;
    if ( LsaGetLogonSessionData(a2, &ppLogonSessionData) >= 0 && ppLogonSessionData )
    {
      if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-16LL
        && ppLogonSessionData->UserName.Buffer
        && (Length = ppLogonSessionData->UserName.Length, (_WORD)Length) )
      {
        Buffer = ppLogonSessionData->UserName.Buffer;
        v28 = (unsigned int)(Length + 2);
      }
      else
      {
        Buffer = L"(NULL)";
        v28 = 14;
      }
      if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-32LL )
      {
        if ( ppLogonSessionData->LogonDomain.Buffer )
        {
          v11 = ppLogonSessionData->LogonDomain.Length;
          if ( (_WORD)v11 )
          {
            v29 = ppLogonSessionData->LogonDomain.Buffer;
            v30 = (unsigned int)(v11 + 2);
            goto LABEL_23;
          }
        }
      }
    }
    else
    {
      v28 = 14;
      Buffer = L"(NULL)";
    }
    v30 = 14;
    v29 = L"(NULL)";
LABEL_23:
    if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v19)
      && (v12 = SspOIDToString(v20, &v17), v3 = v17, v12) )
    {
      v13 = -1;
      do
        ++v13;
      while ( v17[v13] );
      v31 = v17;
      v32 = (unsigned int)(2 * v13 + 2);
    }
    else
    {
      v31 = L"(NULL)";
      v32 = 14;
    }
    v14 = NTLMServerBlockedChallenge;
    if ( !a3 )
      v14 = NTLMServerBlockedChallengeAudit;
    result = EtwEventWrite(MsvEtwLogHandle, v14, 6);
    if ( v9 )
      result = CloseHandle(v9);
    goto LABEL_33;
  }
  return result;
}

```

## disassembly

```asm
0x180051a98  mov     [rsp-8+arg_10], rbx
0x180051a9d  push    rbp
0x180051a9e  push    rsi
0x180051a9f  push    r12
0x180051aa1  push    r14
0x180051aa3  push    r15
0x180051aa5  lea     rbp, [rsp-200h]
0x180051aad  sub     rsp, 300h
0x180051ab4  mov     rax, cs:__security_cookie
0x180051abb  xor     rax, rsp
0x180051abe  mov     [rbp+220h+var_30], rax
0x180051ac5  xor     r12d, r12d
0x180051ac8  mov     [rsp+320h+dwProcessId], ecx
0x180051acc  xorps   xmm0, xmm0
0x180051acf  mov     [rsp+320h+var_2F0], r12
0x180051ad4  xor     eax, eax
0x180051ad6  mov     [rsp+320h+ppLogonSessionData], r12
0x180051adb  movups  [rsp+320h+var_2E0], xmm0
0x180051ae0  mov     [rsp+320h+var_2D0], rax
0x180051ae5  mov     esi, r12d
0x180051ae8  mov     r15d, r8d
0x180051aeb  mov     [rsp+320h+dwSize], 105h
0x180051af3  mov     rbx, rdx
0x180051af6  call    SspInitEtwLogHandle
0x180051afb  test    eax, eax
0x180051afd  js      loc_180051CF8
0x180051b03  mov     rcx, cs:MsvEtwLogHandle
0x180051b0a  lea     rax, NTLMClientBlockedAudit
0x180051b11  test    r15d, r15d
0x180051b14  lea     rdx, NTLMClientBlocked
0x180051b1b  cmovz   rdx, rax
0x180051b1f  call    cs:__imp_EtwEventEnabled
0x180051b25  test    al, al
0x180051b27  jz      loc_180051D23
0x180051b2d  mov     r8d, [rsp+320h+dwProcessId]; dwProcessId
0x180051b32  lea     rax, [rsp+320h+dwProcessId]
0x180051b37  xor     edx, edx; bInheritHandle
0x180051b39  mov     [rsp+320h+var_2C0], rax
0x180051b3e  mov     ecx, 1000h; dwDesiredAccess
0x180051b43  mov     [rsp+320h+var_2B8], 4
0x180051b4c  call    cs:__imp_OpenProcess
0x180051b52  mov     r14, rax
0x180051b55  test    rax, rax
0x180051b58  jz      short loc_180051B95
0x180051b5a  lea     r9, [rsp+320h+dwSize]; lpdwSize
0x180051b5f  xor     edx, edx; dwFlags
0x180051b61  lea     r8, [rbp+220h+ExeName]; lpExeName
0x180051b65  mov     rcx, rax; hProcess
0x180051b68  call    cs:__imp_QueryFullProcessImageNameW
0x180051b6e  test    eax, eax
0x180051b70  jz      short loc_180051B95
0x180051b72  mov     eax, [rsp+320h+dwSize]
0x180051b76  test    eax, eax
0x180051b78  jz      short loc_180051B95
0x180051b7a  lea     rcx, [rbp+220h+ExeName]
0x180051b7e  mov     dword ptr [rsp+320h+var_2A8+4], r12d
0x180051b83  lea     eax, ds:2[rax*2]
0x180051b8a  mov     [rsp+320h+var_2B0], rcx
0x180051b8f  mov     dword ptr [rsp+320h+var_2A8], eax
0x180051b93  jmp     short loc_180051BAA
0x180051b95  lea     rax, asc_1800745A0; "-"
0x180051b9c  mov     [rsp+320h+var_2A8], 4
0x180051ba5  mov     [rsp+320h+var_2B0], rax
0x180051baa  lea     rdx, [rsp+320h+ppLogonSessionData]; ppLogonSessionData
0x180051baf  mov     [rbp+220h+var_2A0], rbx
0x180051bb3  mov     rcx, rbx; LogonId
0x180051bb6  mov     [rbp+220h+var_298], 8
0x180051bbe  call    cs:__imp_LsaGetLogonSessionData
0x180051bc4  test    eax, eax
0x180051bc6  js      short loc_180051C3C
0x180051bc8  mov     rcx, [rsp+320h+ppLogonSessionData]
0x180051bcd  test    rcx, rcx
0x180051bd0  jz      short loc_180051C3C
0x180051bd2  lea     rax, [rcx+10h]
0x180051bd6  lea     rbx, aNull; "(NULL)"
0x180051bdd  test    rax, rax
0x180051be0  jz      short loc_180051C06
0x180051be2  mov     rdx, [rcx+18h]
0x180051be6  test    rdx, rdx
0x180051be9  jz      short loc_180051C06
0x180051beb  movzx   r8d, word ptr [rax]
0x180051bef  test    r8w, r8w
0x180051bf3  jz      short loc_180051C06
0x180051bf5  lea     eax, [r8+2]
0x180051bf9  mov     [rbp+220h+var_290], rdx
0x180051bfd  mov     dword ptr [rbp+220h+var_288], eax
0x180051c00  mov     dword ptr [rbp+220h+var_288+4], r12d
0x180051c04  jmp     short loc_180051C12
0x180051c06  mov     [rbp+220h+var_290], rbx
0x180051c0a  mov     [rbp+220h+var_288], 0Eh
0x180051c12  lea     rax, [rcx+20h]
0x180051c16  test    rax, rax
0x180051c19  jz      short loc_180051C4F
0x180051c1b  mov     rdx, [rcx+28h]
0x180051c1f  test    rdx, rdx
0x180051c22  jz      short loc_180051C4F
0x180051c24  movzx   ecx, word ptr [rax]
0x180051c27  test    cx, cx
0x180051c2a  jz      short loc_180051C4F
0x180051c2c  lea     eax, [rcx+2]
0x180051c2f  mov     [rbp+220h+var_280], rdx
0x180051c33  mov     dword ptr [rbp+220h+var_278], eax
0x180051c36  mov     dword ptr [rbp+220h+var_278+4], r12d
0x180051c3a  jmp     short loc_180051C5B
0x180051c3c  lea     rbx, aNull; "(NULL)"
0x180051c43  mov     [rbp+220h+var_288], 0Eh
0x180051c4b  mov     [rbp+220h+var_290], rbx
0x180051c4f  mov     [rbp+220h+var_278], 0Eh
0x180051c57  mov     [rbp+220h+var_280], rbx
0x180051c5b  mov     rax, cs:LsaFunctions
0x180051c62  lea     rcx, [rsp+320h+var_2E0]
0x180051c67  mov     rax, [rax+0C0h]
0x180051c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c73  test    al, al
0x180051c75  jz      short loc_180051CB1
0x180051c77  mov     rcx, [rsp+320h+var_2D0]; struct ASN1objectidentifier_s *
0x180051c7c  lea     rdx, [rsp+320h+var_2F0]; unsigned __int16 **
0x180051c81  call    ?SspOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; SspOIDToString(ASN1objectidentifier_s *,ushort * *)
0x180051c86  mov     rsi, [rsp+320h+var_2F0]
0x180051c8b  test    eax, eax
0x180051c8d  jz      short loc_180051CB1
0x180051c8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051c93  inc     rax
0x180051c96  cmp     [rsi+rax*2], r12w
0x180051c9b  jnz     short loc_180051C93
0x180051c9d  lea     eax, ds:2[rax*2]
0x180051ca4  mov     [rbp+220h+var_270], rsi
0x180051ca8  mov     dword ptr [rbp+220h+var_268], eax
0x180051cab  mov     dword ptr [rbp+220h+var_268+4], r12d
0x180051caf  jmp     short loc_180051CBD
0x180051cb1  mov     [rbp+220h+var_270], rbx
0x180051cb5  mov     [rbp+220h+var_268], 0Eh
0x180051cbd  mov     rcx, cs:MsvEtwLogHandle
0x180051cc4  lea     rax, NTLMServerBlockedChallengeAudit
0x180051ccb  test    r15d, r15d
0x180051cce  lea     rdx, NTLMServerBlockedChallenge
0x180051cd5  lea     r9, [rsp+320h+var_2C0]
0x180051cda  mov     r8d, 6
0x180051ce0  cmovz   rdx, rax
0x180051ce4  call    cs:__imp_EtwEventWrite
0x180051cea  test    r14, r14
0x180051ced  jz      short loc_180051CF8
0x180051cef  mov     rcx, r14; hObject
0x180051cf2  call    cs:__imp_CloseHandle
0x180051cf8  mov     rcx, [rsp+320h+ppLogonSessionData]; Buffer
0x180051cfd  test    rcx, rcx
0x180051d00  jz      short loc_180051D08
0x180051d02  call    cs:__imp_LsaFreeReturnBuffer
0x180051d08  test    rsi, rsi
0x180051d0b  jz      short loc_180051D23
0x180051d0d  mov     rax, cs:LsaFunctions
0x180051d14  mov     rcx, rsi
0x180051d17  mov     rax, [rax+188h]
0x180051d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d23  mov     rcx, [rbp+220h+var_30]
0x180051d2a  xor     rcx, rsp; StackCookie
0x180051d2d  call    __security_check_cookie
0x180051d32  mov     rbx, [rsp+320h+arg_10]
0x180051d3a  add     rsp, 300h
0x180051d41  pop     r15
0x180051d43  pop     r14
0x180051d45  pop     r12
0x180051d47  pop     rsi
0x180051d48  pop     rbp
0x180051d49  retn
```
