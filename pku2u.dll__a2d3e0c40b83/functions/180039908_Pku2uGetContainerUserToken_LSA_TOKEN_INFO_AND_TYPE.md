# Pku2uGetContainerUserToken(_LSA_TOKEN_INFO_AND_TYPE * *)

- ea: `0x180039908`
- end: `0x180039da6`
- name: `?Pku2uGetContainerUserToken@@YAJPEAPEAU_LSA_TOKEN_INFO_AND_TYPE@@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(struct _LSA_TOKEN_INFO_AND_TYPE **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003bc0`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x180018c80`
- `0x1800210f0`
- `0x180021a54`
- `0x180039908`
- `0x180039dac`
- `0x18003a4d8`
- `0x18003b0a0`
- `0x18003b0e4`
- `0x180044f20`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039c86`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039c99`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039c86`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039c99`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039c73`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039d6e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180039d5d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180039d5d`
- `ntdll!NtQueryInformationToken` at `0x180039a11`
- `ntdll!NtQueryInformationToken` at `0x180039a5c`
- `ntdll!NtQueryInformationToken` at `0x180039b79`
- `ntdll!NtQueryInformationToken` at `0x180039a11`
- `ntdll!NtQueryInformationToken` at `0x180039a5c`
- `ntdll!NtQueryInformationToken` at `0x180039b79`
- `ntdll!RtlGetLastNtStatus` at `0x180039c04`
- `ntdll!RtlGetLastNtStatus` at `0x180039c04`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180039bfa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180039bfa`

## string_xrefs

- `0x1800399e3`: `Pku2uGetContainerUserToken`
- `0x180039baf`: `Pku2uGetContainerUserToken`
- `0x180039cd2`: `Pku2uGetContainerUserToken`

## pseudocode

```c
__int64 __fastcall Pku2uGetContainerUserToken(struct _LSA_TOKEN_INFO_AND_TYPE **a1)
{
  int HostUserToken; // ebx
  int v3; // r8d
  _QWORD *v4; // rcx
  int v5; // edx
  NTSTATUS v6; // eax
  unsigned __int64 v7; // rbx
  struct _TOKEN_GROUPS *p_TokenInformationLength; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  _DWORD *v13; // rax
  int v14; // r8d
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v17; // rbx
  void *v18; // rax
  void *v19; // rsi
  int v20; // r8d
  struct _LSA_TOKEN_INFO_AND_TYPE *v21; // rax
  struct _LSA_TOKEN_INFO_AND_TYPE *v22; // rcx
  struct _LSA_TOKEN_INFORMATION_V1 *v23; // rax
  __int64 v25; // [rsp+0h] [rbp-30h] BYREF
  ULONG TokenInformationLength; // [rsp+30h] [rbp+0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp+8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+44h] [rbp+14h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp+1Ch] BYREF
  struct _LSA_TOKEN_INFORMATION_V1 *v32; // [rsp+50h] [rbp+20h] BYREF
  PSID TokenInformation[11]; // [rsp+78h] [rbp+48h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+D0h] [rbp+A0h] BYREF
  WCHAR Name[264]; // [rsp+2D0h] [rbp+2A0h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x54u);
  ReturnLength = 0;
  TokenInformationLength = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  v32 = 0;
  if ( (unsigned __int16)Pku2uGetHostUserToken(&TokenHandle) )
    HostUserToken = (unsigned __int16)Pku2uGetHostUserToken(&TokenHandle) | 0xC0070000;
  else
    HostUserToken = (unsigned __int16)Pku2uGetHostUserToken(&TokenHandle);
  if ( HostUserToken < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 22;
LABEL_8:
      WPP_SF_sD(v4[2], v5, v3, (unsigned int)"Pku2uGetContainerUserToken", HostUserToken);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  HostUserToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength);
  if ( HostUserToken >= 0 )
  {
    v6 = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
    HostUserToken = v6;
    if ( v6 != -2147483643 && v6 != -1073741789 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 24;
        goto LABEL_8;
      }
      goto LABEL_57;
    }
    v7 = TokenInformationLength;
    p_TokenInformationLength = 0;
    if ( !TokenInformationLength
      || TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)TokenInformationLength + g_ulAdditionalProbeSize + 8 < TokenInformationLength
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_62;
    }
    v9 = v7 + 23;
    if ( v7 + 23 <= v7 + 8 )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
    v11 = alloca(v10);
    v12 = alloca(v10);
    p_TokenInformationLength = (struct _TOKEN_GROUPS *)&TokenInformationLength;
    if ( &v25 == (__int64 *)-48LL
      || (TokenInformationLength = 1801679955, (p_TokenInformationLength = (struct _TOKEN_GROUPS *)&TokenHandle) == 0) )
    {
LABEL_62:
      if ( v7 + 8 >= v7 )
      {
        v13 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_TokenInformationLength = (struct _TOKEN_GROUPS *)v13;
        if ( v13 )
        {
          *v13 = 1885431112;
          p_TokenInformationLength = (struct _TOKEN_GROUPS *)(v13 + 2);
        }
      }
    }
    if ( !p_TokenInformationLength )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2));
      HostUserToken = -1073741801;
      goto LABEL_57;
    }
    HostUserToken = NtQueryInformationToken(
                      TokenHandle,
                      TokenGroups,
                      p_TokenInformationLength,
                      TokenInformationLength,
                      &TokenInformationLength);
    if ( HostUserToken < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 26;
LABEL_38:
        WPP_SF_sD(v15[2], v16, v14, (unsigned int)"Pku2uGetContainerUserToken", HostUserToken);
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    cchName = 257;
    cchReferencedDomainName = 256;
    if ( !LookupAccountSidLocalW(
            TokenInformation[0],
            Name,
            &cchName,
            ReferencedDomainName,
            &cchReferencedDomainName,
            &peUse) )
    {
      HostUserToken = RtlGetLastNtStatus();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 27;
        goto LABEL_38;
      }
LABEL_55:
      if ( p_TokenInformationLength[-1].Groups[0].Attributes == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_57;
    }
    v17 = cchName + 2 + cchReferencedDomainName;
    v18 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 2 * v17);
    v19 = v18;
    if ( !v18 )
    {
      HostUserToken = -1073741801;
      goto LABEL_55;
    }
    _o_wcscpy_s(v18, v17, ReferencedDomainName);
    _o_wcscat_s(v19, v17, L"\\");
    _o_wcscat_s(v19, v17, Name);
    HostUserToken = Pku2uMakeTokenInformationV2Internal(TokenInformation[0], p_TokenInformationLength, &v32);
    if ( HostUserToken >= 0 )
    {
      v21 = (struct _LSA_TOKEN_INFO_AND_TYPE *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 0x18u);
      v22 = v21;
      if ( v21 )
      {
        *((_QWORD *)v21 + 1) = v32;
        v23 = 0;
        *(_DWORD *)v22 = 2;
        HostUserToken = 0;
        *((_QWORD *)v22 + 2) = v19;
        *a1 = v22;
LABEL_53:
        if ( v23 )
          Pku2uFree(v23);
        goto LABEL_55;
      }
      HostUserToken = -1073741801;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v20, (unsigned int)"Pku2uGetContainerUserToken", HostUserToken);
    }
    Pku2uFree(v19);
    v23 = v32;
    goto LABEL_53;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 23;
    goto LABEL_8;
  }
LABEL_57:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)HostUserToken;
}

```

## disassembly

```asm
0x180039908  push    rbp
0x18003990a  push    rdi
0x18003990b  push    r15
0x18003990d  sub     rsp, 500h
0x180039914  lea     rbp, [rsp+30h]
0x180039919  mov     [rbp+4E0h+arg_8], rbx
0x180039920  mov     [rbp+4E0h+arg_10], rsi
0x180039927  movaps  [rbp+4E0h+var_20], xmm6
0x18003992e  mov     rax, cs:__security_cookie
0x180039935  xor     rax, rbp
0x180039938  mov     [rbp+4E0h+var_30], rax
0x18003993f  mov     r15, rcx
0x180039942  mov     [rbp+4E0h+TokenHandle], 0
0x18003994a  mov     edi, 54h ; 'T'
0x18003994f  lea     rcx, [rbp+4E0h+TokenInformation]; void *
0x180039953  mov     r8d, edi; Size
0x180039956  xor     edx, edx; Val
0x180039958  xorps   xmm6, xmm6
0x18003995b  call    memset_0
0x180039960  lea     rcx, [rbp+4E0h+TokenHandle]; void **
0x180039964  mov     [rbp+4E0h+var_4C8], 0
0x18003996b  mov     [rbp+4E0h+TokenInformationLength], 0
0x180039972  mov     [rbp+4E0h+cchName], 0
0x180039979  mov     [rbp+4E0h+cchReferencedDomainName], 0
0x180039980  mov     [rbp+4E0h+var_4C4], 0
0x180039987  mov     [rbp+4E0h+var_4C0], 0
0x18003998f  call    ?Pku2uGetHostUserToken@@YAJPEAPEAX@Z; Pku2uGetHostUserToken(void * *)
0x180039994  lea     rcx, [rbp+4E0h+TokenHandle]; void **
0x180039998  test    ax, ax
0x18003999b  jnz     short loc_1800399A7
0x18003999d  call    ?Pku2uGetHostUserToken@@YAJPEAPEAX@Z; Pku2uGetHostUserToken(void * *)
0x1800399a2  movzx   ebx, ax
0x1800399a5  jmp     short loc_1800399B5
0x1800399a7  call    ?Pku2uGetHostUserToken@@YAJPEAPEAX@Z; Pku2uGetHostUserToken(void * *)
0x1800399ac  movzx   ebx, ax
0x1800399af  or      ebx, 0C0070000h
0x1800399b5  test    ebx, ebx
0x1800399b7  jns     short loc_1800399F8
0x1800399b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399c0  lea     rax, WPP_GLOBAL_Control
0x1800399c7  cmp     rcx, rax
0x1800399ca  jz      loc_180039D53
0x1800399d0  test    byte ptr [rcx+1Ch], 1
0x1800399d4  jz      loc_180039D53
0x1800399da  mov     edx, 16h
0x1800399df  mov     rcx, [rcx+10h]
0x1800399e3  lea     r9, aPku2ugetcontai; "Pku2uGetContainerUserToken"
0x1800399ea  mov     dword ptr [rsp+510h+ReturnLength], ebx
0x1800399ee  call    WPP_SF_sD
0x1800399f3  jmp     loc_180039D53
0x1800399f8  mov     rcx, [rbp+4E0h+TokenHandle]; TokenHandle
0x1800399fc  lea     rax, [rbp+4E0h+var_4C8]
0x180039a00  mov     r9d, edi; TokenInformationLength
0x180039a03  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x180039a08  lea     r8, [rbp+4E0h+TokenInformation]; TokenInformation
0x180039a0c  mov     edx, 1; TokenInformationClass
0x180039a11  call    cs:__imp_NtQueryInformationToken
0x180039a17  mov     ebx, eax
0x180039a19  test    eax, eax
0x180039a1b  jns     short loc_180039A45
0x180039a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a24  lea     rax, WPP_GLOBAL_Control
0x180039a2b  cmp     rcx, rax
0x180039a2e  jz      loc_180039D53
0x180039a34  test    byte ptr [rcx+1Ch], 1
0x180039a38  jz      loc_180039D53
0x180039a3e  mov     edx, 17h
0x180039a43  jmp     short loc_1800399DF
0x180039a45  mov     rcx, [rbp+4E0h+TokenHandle]; TokenHandle
0x180039a49  lea     rax, [rbp+4E0h+TokenInformationLength]
0x180039a4d  xor     r9d, r9d; TokenInformationLength
0x180039a50  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x180039a55  xor     r8d, r8d; TokenInformation
0x180039a58  lea     edx, [r9+2]; TokenInformationClass
0x180039a5c  call    cs:__imp_NtQueryInformationToken
0x180039a62  mov     ebx, eax
0x180039a64  cmp     eax, 80000005h
0x180039a69  jz      short loc_180039A9D
0x180039a6b  cmp     eax, 0C0000023h
0x180039a70  jz      short loc_180039A9D
0x180039a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a79  lea     rax, WPP_GLOBAL_Control
0x180039a80  cmp     rcx, rax
0x180039a83  jz      loc_180039D53
0x180039a89  test    byte ptr [rcx+1Ch], 1
0x180039a8d  jz      loc_180039D53
0x180039a93  mov     edx, 18h
0x180039a98  jmp     loc_1800399DF
0x180039a9d  mov     ebx, [rbp+4E0h+TokenInformationLength]
0x180039aa0  xor     edi, edi
0x180039aa2  test    rbx, rbx
0x180039aa5  jz      short loc_180039B08
0x180039aa7  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180039aae  ja      short loc_180039B08
0x180039ab0  mov     rcx, cs:g_ulAdditionalProbeSize
0x180039ab7  add     rcx, 8
0x180039abb  add     rcx, rbx
0x180039abe  cmp     rcx, rbx
0x180039ac1  jb      short loc_180039B08
0x180039ac3  call    VerifyStackAvailable
0x180039ac8  test    eax, eax
0x180039aca  jz      short loc_180039B08
0x180039acc  lea     rax, [rbx+8]
0x180039ad0  lea     rcx, [rax+0Fh]
0x180039ad4  cmp     rcx, rax
0x180039ad7  ja      short loc_180039AE3
0x180039ad9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180039ae3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180039ae7  mov     rax, rcx
0x180039aea  call    _alloca_probe
0x180039aef  sub     rsp, rcx
0x180039af2  lea     rdi, [rsp+510h+TokenInformationLength]
0x180039af7  test    rdi, rdi
0x180039afa  jz      short loc_180039B08
0x180039afc  mov     dword ptr [rdi], 6B637453h
0x180039b02  add     rdi, 8
0x180039b06  jnz     short loc_180039B2F
0x180039b08  lea     rcx, [rbx+8]
0x180039b0c  cmp     rcx, rbx
0x180039b0f  jb      short loc_180039B2F
0x180039b11  mov     rax, cs:g_pfnAllocate
0x180039b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b1d  mov     rdi, rax
0x180039b20  test    rax, rax
0x180039b23  jz      short loc_180039B2F
0x180039b25  mov     dword ptr [rax], 70616548h
0x180039b2b  add     rdi, 8
0x180039b2f  test    rdi, rdi
0x180039b32  jnz     short loc_180039B60
0x180039b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b3b  lea     rax, WPP_GLOBAL_Control
0x180039b42  cmp     rcx, rax
0x180039b45  jz      short loc_180039B56
0x180039b47  test    byte ptr [rcx+1Ch], 1
0x180039b4b  jz      short loc_180039B56
0x180039b4d  mov     rcx, [rcx+10h]
0x180039b51  call    WPP_SF_s
0x180039b56  mov     ebx, 0C0000017h
0x180039b5b  jmp     loc_180039D53
0x180039b60  mov     r9d, [rbp+4E0h+TokenInformationLength]; TokenInformationLength
0x180039b64  lea     rax, [rbp+4E0h+TokenInformationLength]
0x180039b68  mov     rcx, [rbp+4E0h+TokenHandle]; TokenHandle
0x180039b6c  mov     r8, rdi; TokenInformation
0x180039b6f  mov     edx, 2; TokenInformationClass
0x180039b74  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x180039b79  call    cs:__imp_NtQueryInformationToken
0x180039b7f  mov     ebx, eax
0x180039b81  test    eax, eax
0x180039b83  jns     short loc_180039BC4
0x180039b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b8c  lea     rax, WPP_GLOBAL_Control
0x180039b93  cmp     rcx, rax
0x180039b96  jz      loc_180039D3B
0x180039b9c  test    byte ptr [rcx+1Ch], 1
0x180039ba0  jz      loc_180039D3B
0x180039ba6  mov     edx, 1Ah
0x180039bab  mov     rcx, [rcx+10h]
0x180039baf  lea     r9, aPku2ugetcontai; "Pku2uGetContainerUserToken"
0x180039bb6  mov     dword ptr [rsp+510h+ReturnLength], ebx
0x180039bba  call    WPP_SF_sD
0x180039bbf  jmp     loc_180039D3B
0x180039bc4  mov     rcx, [rbp+4E0h+TokenInformation]; Sid
0x180039bc8  lea     rax, [rbp+4E0h+var_4C4]
0x180039bcc  mov     [rsp+510h+peUse], rax; peUse
0x180039bd1  lea     r9, [rbp+4E0h+ReferencedDomainName]; ReferencedDomainName
0x180039bd8  lea     rax, [rbp+4E0h+cchReferencedDomainName]
0x180039bdc  mov     [rbp+4E0h+cchName], 101h
0x180039be3  lea     r8, [rbp+4E0h+cchName]; cchName
0x180039be7  mov     [rsp+510h+ReturnLength], rax; cchReferencedDomainName
0x180039bec  lea     rdx, [rbp+4E0h+Name]; Name
0x180039bf3  mov     [rbp+4E0h+cchReferencedDomainName], 100h
0x180039bfa  call    cs:__imp_LookupAccountSidLocalW
0x180039c00  test    eax, eax
0x180039c02  jnz     short loc_180039C37
0x180039c04  call    cs:__imp_RtlGetLastNtStatus
0x180039c0a  mov     ebx, eax
0x180039c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c13  lea     rax, WPP_GLOBAL_Control
0x180039c1a  cmp     rcx, rax
0x180039c1d  jz      loc_180039D3B
0x180039c23  test    byte ptr [rcx+1Ch], 1
0x180039c27  jz      loc_180039D3B
0x180039c2d  mov     edx, 1Bh
0x180039c32  jmp     loc_180039BAB
0x180039c37  mov     ecx, [rbp+4E0h+cchReferencedDomainName]
0x180039c3a  mov     eax, [rbp+4E0h+cchName]
0x180039c3d  add     eax, 2
0x180039c40  add     ecx, eax
0x180039c42  mov     ebx, ecx
0x180039c44  lea     rdx, [rcx+rcx]; unsigned __int64
0x180039c48  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180039c4f  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180039c54  mov     rsi, rax
0x180039c57  test    rax, rax
0x180039c5a  jnz     short loc_180039C66
0x180039c5c  mov     ebx, 0C0000017h
0x180039c61  jmp     loc_180039D3B
0x180039c66  lea     r8, [rbp+4E0h+ReferencedDomainName]
0x180039c6d  mov     rdx, rbx
0x180039c70  mov     rcx, rsi
0x180039c73  call    cs:__imp__o_wcscpy_s
0x180039c79  lea     r8, asc_18004A4B8; "\\"
0x180039c80  mov     rdx, rbx
0x180039c83  mov     rcx, rsi
0x180039c86  call    cs:__imp__o_wcscat_s
0x180039c8c  lea     r8, [rbp+4E0h+Name]
0x180039c93  mov     rdx, rbx
0x180039c96  mov     rcx, rsi
0x180039c99  call    cs:__imp__o_wcscat_s
0x180039c9f  mov     rcx, [rbp+4E0h+TokenInformation]; SourceSid
0x180039ca3  lea     r8, [rbp+4E0h+var_4C0]; struct _LSA_TOKEN_INFORMATION_V1 **
0x180039ca7  mov     rdx, rdi; struct _TOKEN_GROUPS *
0x180039caa  call    ?Pku2uMakeTokenInformationV2Internal@@YAJPEAXPEAU_TOKEN_GROUPS@@PEAPEAU_LSA_TOKEN_INFORMATION_V1@@@Z; Pku2uMakeTokenInformationV2Internal(void *,_TOKEN_GROUPS *,_LSA_TOKEN_INFORMATION_V1 * *)
0x180039caf  mov     ebx, eax
0x180039cb1  test    eax, eax
0x180039cb3  jns     short loc_180039CE9
0x180039cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180039cbc  lea     rax, WPP_GLOBAL_Control
0x180039cc3  cmp     rcx, rax
0x180039cc6  jz      short loc_180039D07
0x180039cc8  test    byte ptr [rcx+1Ch], 1
0x180039ccc  jz      short loc_180039D07
0x180039cce  mov     rcx, [rcx+10h]
0x180039cd2  lea     r9, aPku2ugetcontai; "Pku2uGetContainerUserToken"
0x180039cd9  mov     edx, 1Ch
0x180039cde  mov     dword ptr [rsp+510h+ReturnLength], ebx
0x180039ce2  call    WPP_SF_sD
0x180039ce7  jmp     short loc_180039D07
0x180039ce9  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180039cf0  mov     edx, 18h; unsigned __int64
0x180039cf5  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180039cfa  mov     rcx, rax
0x180039cfd  test    rax, rax
0x180039d00  jnz     short loc_180039D15
0x180039d02  mov     ebx, 0C0000017h
0x180039d07  mov     rcx, rsi; void *
0x180039d0a  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180039d0f  mov     rax, [rbp+4E0h+var_4C0]
0x180039d13  jmp     short loc_180039D2E
0x180039d15  mov     rax, [rbp+4E0h+var_4C0]
0x180039d19  mov     [rcx+8], rax
0x180039d1d  xor     eax, eax
0x180039d1f  mov     dword ptr [rcx], 2
0x180039d25  xor     ebx, ebx
0x180039d27  mov     [rcx+10h], rsi
0x180039d2b  mov     [r15], rcx
0x180039d2e  test    rax, rax
0x180039d31  jz      short loc_180039D3B
0x180039d33  mov     rcx, rax; void *
0x180039d36  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180039d3b  lea     rcx, [rdi-8]
0x180039d3f  cmp     dword ptr [rcx], 70616548h
0x180039d45  jnz     short loc_180039D53
0x180039d47  mov     rax, cs:g_pfnFree
0x180039d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d53  movq    rcx, xmm6; pSid
0x180039d58  test    rcx, rcx
0x180039d5b  jz      short loc_180039D63
0x180039d5d  call    cs:__imp_FreeSid
0x180039d63  cmp     [rbp+4E0h+TokenHandle], 0
0x180039d68  jz      short loc_180039D74
0x180039d6a  mov     rcx, [rbp+4E0h+TokenHandle]; hObject
0x180039d6e  call    cs:__imp_CloseHandle
0x180039d74  mov     eax, ebx
0x180039d76  mov     rcx, [rbp+4E0h+var_30]
0x180039d7d  xor     rcx, rbp; StackCookie
0x180039d80  call    __security_check_cookie
0x180039d85  mov     rbx, [rbp+4E0h+arg_8]
0x180039d8c  mov     rsi, [rbp+4E0h+arg_10]
0x180039d93  movaps  xmm6, [rbp+4E0h+var_20]
0x180039d9a  lea     rsp, [rbp+4D0h]
0x180039da1  pop     r15
0x180039da3  pop     rdi
0x180039da4  pop     rbp
0x180039da5  retn
```
