# CredpElevateIfLowToken(void * *)

- ea: `0x1800438f4`
- end: `0x180043e6d`
- name: `?CredpElevateIfLowToken@@YAJPEAPEAX@Z`
- size: `1401`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180041fd0`
- `0x18008a6ac`
- `0x180099bf4`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x1800438f4`
- `0x180097568`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043dfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043e5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043dfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043e5c`
- `ntdll!NtSetInformationToken` at `0x180043d0d`
- `ntdll!NtSetInformationToken` at `0x180043d0d`
- `ntdll!NtDuplicateToken` at `0x180043c99`
- `ntdll!NtDuplicateToken` at `0x180043c99`
- `ntdll!NtSetInformationThread` at `0x180043c0a`
- `ntdll!NtSetInformationThread` at `0x180043d55`
- `ntdll!NtSetInformationThread` at `0x180043dbf`
- `ntdll!NtSetInformationThread` at `0x180043c0a`
- `ntdll!NtSetInformationThread` at `0x180043d55`
- `ntdll!NtSetInformationThread` at `0x180043dbf`
- `ntdll!RtlSidDominates` at `0x1800439f7`
- `ntdll!RtlSidDominates` at `0x1800439f7`
- `ntdll!NtQueryInformationToken` at `0x1800439cb`
- `ntdll!NtQueryInformationToken` at `0x180043bb3`
- `ntdll!NtQueryInformationToken` at `0x1800439cb`
- `ntdll!NtQueryInformationToken` at `0x180043bb3`
- `ntdll!NtOpenThreadToken` at `0x180043996`
- `ntdll!NtOpenThreadToken` at `0x180043996`

## pseudocode

```c
__int64 __fastcall CredpElevateIfLowToken(void **a1)
{
  char v2; // r15
  struct _RTL_BALANCED_NODE *v3; // rsi
  void *v4; // rdx
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  LsaHandleCache *v7; // rcx
  __int64 v8; // rdx
  struct _RTL_BALANCED_NODE *v10; // rax
  char v11[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE TokenInformation[128]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  hObject = 0;
  ThreadInformation = 0;
  TokenInformationLength = 128;
  v11[0] = 0;
  v2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = (struct _RTL_BALANCED_NODE *)TokenInformation;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  if ( !a1 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
    {
LABEL_60:
      *a1 = 0;
      goto LABEL_12;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, 0);
    goto LABEL_53;
  }
  v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xEu, 1u, &TokenHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v8 = 18;
      goto LABEL_52;
    }
LABEL_53:
    if ( TokenHandle )
    {
      if ( v2
        && NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u) < 0
        && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v6);
      }
      CloseHandle(TokenHandle);
    }
    goto LABEL_60;
  }
  v5 = NtQueryInformationToken(
         TokenHandle,
         TokenIntegrityLevel,
         TokenInformation,
         TokenInformationLength,
         &TokenInformationLength);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -1073741789 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 19;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
    v10 = (struct _RTL_BALANCED_NODE *)LsapAllocate(TokenInformationLength);
    v3 = v10;
    if ( !v10 )
    {
      v6 = -1073741670;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
      }
      goto LABEL_53;
    }
    v5 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, v10, TokenInformationLength, &TokenInformationLength);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 21;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
  }
  v5 = RtlSidDominates(*((_QWORD *)WellKnownSids + 222), v3->Children[0], v11);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v8 = 22;
LABEL_52:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, (unsigned int)v5);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  if ( v11[0] )
  {
    v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 23;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    v2 = 1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = NtDuplicateToken(TokenHandle, 0x8Eu, &ObjectAttributes, 0, TokenImpersonation, &hObject);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 24;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
    memset_0(v3, 0, TokenInformationLength);
    v3->Children[0] = (struct _RTL_BALANCED_NODE *)*((_QWORD *)WellKnownSids + 228);
    LODWORD(v3->Right) = 96;
    v5 = NtSetInformationToken(hObject, TokenIntegrityLevel, v3, 0x80u);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 25;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
    v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v8 = 26;
        goto LABEL_52;
      }
      goto LABEL_53;
    }
    *a1 = TokenHandle;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
    }
  }
  else
  {
    v6 = 0;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    *a1 = 0;
  }
LABEL_12:
  if ( hObject )
    CloseHandle(hObject);
  if ( v3 && v3 != (struct _RTL_BALANCED_NODE *)TokenInformation )
    LsapSubProv_FreeRoutine(v3, v4);
  return v6;
}

```

## disassembly

```asm
0x1800438f4  mov     [rsp-8+arg_8], rbx
0x1800438f9  mov     [rsp-8+arg_10], rsi
0x1800438fe  push    rbp
0x1800438ff  push    rdi
0x180043900  push    r13
0x180043902  push    r14
0x180043904  push    r15
0x180043906  lea     rbp, [rsp-10h]
0x18004390b  sub     rsp, 110h
0x180043912  mov     rax, cs:__security_cookie
0x180043919  xor     rax, rsp
0x18004391c  mov     [rbp+30h+var_30], rax
0x180043920  xorps   xmm0, xmm0
0x180043923  mov     [rsp+130h+TokenHandle], 0
0x18004392c  mov     eax, 80h
0x180043931  mov     [rsp+130h+hObject], 0
0x18004393a  mov     r14, rcx
0x18004393d  mov     [rsp+130h+ThreadInformation], 0
0x180043946  mov     r8d, eax; Size
0x180043949  mov     [rsp+130h+TokenInformationLength], eax
0x18004394d  xor     edx, edx; Val
0x18004394f  mov     [rsp+130h+var_100], 0
0x180043954  lea     rcx, [rbp+30h+TokenInformation]; void *
0x180043958  xor     r15b, r15b
0x18004395b  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x180043960  lea     rsi, [rbp+30h+TokenInformation]
0x180043964  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x180043969  movups  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004396e  call    memset_0
0x180043973  mov     r13d, 200h
0x180043979  test    r14, r14
0x18004397c  jz      loc_180043AD6
0x180043982  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x180043987  mov     r8b, 1; OpenAsSelf
0x18004398a  mov     edx, 0Eh; DesiredAccess
0x18004398f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180043996  call    cs:__imp_NtOpenThreadToken
0x18004399d  nop     dword ptr [rax+rax+00h]
0x1800439a2  mov     edi, eax
0x1800439a4  test    eax, eax
0x1800439a6  js      loc_180043AAB
0x1800439ac  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x1800439b1  lea     rax, [rsp+130h+TokenInformationLength]
0x1800439b6  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x1800439bb  lea     r8, [rbp+30h+TokenInformation]; TokenInformation
0x1800439bf  mov     ebx, 19h
0x1800439c4  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x1800439c9  mov     edx, ebx; TokenInformationClass
0x1800439cb  call    cs:__imp_NtQueryInformationToken
0x1800439d2  nop     dword ptr [rax+rax+00h]
0x1800439d7  mov     edi, eax
0x1800439d9  test    eax, eax
0x1800439db  js      loc_180043B19
0x1800439e1  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800439e8  lea     r8, [rsp+130h+var_100]
0x1800439ed  mov     rdx, [rsi]
0x1800439f0  mov     rcx, [rcx+6F0h]
0x1800439f7  call    cs:__imp_RtlSidDominates
0x1800439fe  nop     dword ptr [rax+rax+00h]
0x180043a03  mov     edi, eax
0x180043a05  test    eax, eax
0x180043a07  jns     short loc_180043A34
0x180043a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a10  lea     rbx, WPP_GLOBAL_Control
0x180043a17  cmp     rcx, rbx
0x180043a1a  jz      loc_180043D9C
0x180043a20  test    [rcx+1Ch], r13d
0x180043a24  jz      loc_180043D9C
0x180043a2a  mov     edx, 16h
0x180043a2f  jmp     loc_180043D89
0x180043a34  cmp     [rsp+130h+var_100], r15b
0x180043a39  jnz     loc_180043BF4
0x180043a3f  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180043a44  xor     edi, edi
0x180043a46  test    rcx, rcx
0x180043a49  jz      short loc_180043A57
0x180043a4b  call    cs:__imp_CloseHandle
0x180043a52  nop     dword ptr [rax+rax+00h]
0x180043a57  mov     [r14], rdi
0x180043a5a  mov     rcx, [rsp+130h+hObject]; hObject
0x180043a5f  test    rcx, rcx
0x180043a62  jnz     loc_180043E5C
0x180043a68  test    rsi, rsi
0x180043a6b  jnz     short loc_180043A98
0x180043a6d  mov     eax, edi
0x180043a6f  mov     rcx, [rbp+30h+var_30]
0x180043a73  xor     rcx, rsp; StackCookie
0x180043a76  call    __security_check_cookie
0x180043a7b  lea     r11, [rsp+130h+var_20]
0x180043a83  mov     rbx, [r11+38h]
0x180043a87  mov     rsi, [r11+40h]
0x180043a8b  mov     rsp, r11
0x180043a8e  pop     r15
0x180043a90  pop     r14
0x180043a92  pop     r13
0x180043a94  pop     rdi
0x180043a95  pop     rbp
0x180043a96  retn
0x180043a98  lea     rax, [rbp+30h+TokenInformation]
0x180043a9c  cmp     rsi, rax
0x180043a9f  jz      short loc_180043A6D
0x180043aa1  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x180043aa4  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180043aa9  jmp     short loc_180043A6D
0x180043aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ab2  lea     rbx, WPP_GLOBAL_Control
0x180043ab9  cmp     rcx, rbx
0x180043abc  jz      loc_180043D9C
0x180043ac2  test    [rcx+1Ch], r13d
0x180043ac6  jz      loc_180043D9C
0x180043acc  mov     edx, 12h
0x180043ad1  jmp     loc_180043D89
0x180043ad6  mov     edi, 0C000000Dh
0x180043adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ae2  lea     rbx, WPP_GLOBAL_Control
0x180043ae9  cmp     rcx, rbx
0x180043aec  jz      loc_180043E0A
0x180043af2  test    [rcx+1Ch], r13d
0x180043af6  jz      loc_180043E0A
0x180043afc  mov     rcx, [rcx+10h]
0x180043b00  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180043b07  mov     edx, 11h
0x180043b0c  xor     r9d, r9d
0x180043b0f  call    WPP_SF_q
0x180043b14  jmp     loc_180043D9C
0x180043b19  cmp     eax, 0C0000023h
0x180043b1e  jz      short loc_180043B4B
0x180043b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b27  lea     rbx, WPP_GLOBAL_Control
0x180043b2e  cmp     rcx, rbx
0x180043b31  jz      loc_180043D9C
0x180043b37  test    [rcx+1Ch], r13d
0x180043b3b  jz      loc_180043D9C
0x180043b41  mov     edx, 13h
0x180043b46  jmp     loc_180043D89
0x180043b4b  mov     ecx, [rsp+130h+TokenInformationLength]
0x180043b4f  call    LsapAllocate
0x180043b54  mov     rsi, rax
0x180043b57  test    rax, rax
0x180043b5a  jnz     short loc_180043B9A
0x180043b5c  mov     edi, 0C000009Ah
0x180043b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b68  lea     rbx, WPP_GLOBAL_Control
0x180043b6f  cmp     rcx, rbx
0x180043b72  jz      loc_180043D9C
0x180043b78  test    [rcx+1Ch], r13d
0x180043b7c  jz      loc_180043D9C
0x180043b82  mov     rcx, [rcx+10h]
0x180043b86  lea     edx, [rax+14h]
0x180043b89  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180043b90  call    WPP_SF_
0x180043b95  jmp     loc_180043D9C
0x180043b9a  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x180043b9f  lea     rax, [rsp+130h+TokenInformationLength]
0x180043ba4  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180043ba9  mov     r8, rsi; TokenInformation
0x180043bac  mov     edx, ebx; TokenInformationClass
0x180043bae  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180043bb3  call    cs:__imp_NtQueryInformationToken
0x180043bba  nop     dword ptr [rax+rax+00h]
0x180043bbf  mov     edi, eax
0x180043bc1  test    eax, eax
0x180043bc3  jns     loc_1800439E1
0x180043bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bd0  lea     rbx, WPP_GLOBAL_Control
0x180043bd7  cmp     rcx, rbx
0x180043bda  jz      loc_180043D9C
0x180043be0  test    [rcx+1Ch], r13d
0x180043be4  jz      loc_180043D9C
0x180043bea  mov     edx, 15h
0x180043bef  jmp     loc_180043D89
0x180043bf4  mov     r9d, 8; ThreadInformationLength
0x180043bfa  lea     r8, [rsp+130h+ThreadInformation]; ThreadInformation
0x180043bff  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180043c06  lea     edx, [r9-3]; ThreadInformationClass
0x180043c0a  call    cs:__imp_NtSetInformationThread
0x180043c11  nop     dword ptr [rax+rax+00h]
0x180043c16  mov     edi, eax
0x180043c18  test    eax, eax
0x180043c1a  jns     short loc_180043C47
0x180043c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c23  lea     rbx, WPP_GLOBAL_Control
0x180043c2a  cmp     rcx, rbx
0x180043c2d  jz      loc_180043D9C
0x180043c33  test    [rcx+1Ch], r13d
0x180043c37  jz      loc_180043D9C
0x180043c3d  mov     edx, 17h
0x180043c42  jmp     loc_180043D89
0x180043c47  mov     rcx, [rsp+130h+TokenHandle]; ExistingTokenHandle
0x180043c4c  lea     rax, [rsp+130h+hObject]
0x180043c51  xorps   xmm0, xmm0
0x180043c54  mov     [rsp+130h+NewTokenHandle], rax; NewTokenHandle
0x180043c59  xor     r9d, r9d; EffectiveOnly
0x180043c5c  mov     dword ptr [rsp+130h+ReturnLength], 2; TokenType
0x180043c64  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180043c69  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180043c71  mov     edx, 8Eh; DesiredAccess
0x180043c76  mov     [rsp+130h+ObjectAttributes.RootDirectory], 0
0x180043c7f  mov     r15b, 1
0x180043c82  mov     [rsp+130h+ObjectAttributes.Attributes], 0
0x180043c8a  mov     [rsp+130h+ObjectAttributes.ObjectName], 0
0x180043c93  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x180043c99  call    cs:__imp_NtDuplicateToken
0x180043ca0  nop     dword ptr [rax+rax+00h]
0x180043ca5  mov     edi, eax
0x180043ca7  test    eax, eax
0x180043ca9  jns     short loc_180043CD6
0x180043cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180043cb2  lea     rbx, WPP_GLOBAL_Control
0x180043cb9  cmp     rcx, rbx
0x180043cbc  jz      loc_180043D9C
0x180043cc2  test    [rcx+1Ch], r13d
0x180043cc6  jz      loc_180043D9C
0x180043ccc  mov     edx, 18h
0x180043cd1  jmp     loc_180043D89
0x180043cd6  mov     r8d, [rsp+130h+TokenInformationLength]; Size
0x180043cdb  xor     edx, edx; Val
0x180043cdd  mov     rcx, rsi; void *
0x180043ce0  call    memset_0
0x180043ce5  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180043cec  mov     r9d, 80h; TokenInformationLength
0x180043cf2  mov     r8, rsi; TokenInformation
0x180043cf5  mov     edx, ebx; TokenInformationClass
0x180043cf7  mov     rcx, [rax+720h]
0x180043cfe  mov     [rsi], rcx
0x180043d01  mov     dword ptr [rsi+8], 60h ; '`'
0x180043d08  mov     rcx, [rsp+130h+hObject]; TokenHandle
0x180043d0d  call    cs:__imp_NtSetInformationToken
0x180043d14  nop     dword ptr [rax+rax+00h]
0x180043d19  mov     edi, eax
0x180043d1b  test    eax, eax
0x180043d1d  jns     short loc_180043D3F
0x180043d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d26  lea     rbx, WPP_GLOBAL_Control
0x180043d2d  cmp     rcx, rbx
0x180043d30  jz      short loc_180043D9C
0x180043d32  test    [rcx+1Ch], r13d
0x180043d36  jz      short loc_180043D9C
0x180043d38  mov     edx, 19h
0x180043d3d  jmp     short loc_180043D89
0x180043d3f  mov     r9d, 8; ThreadInformationLength
0x180043d45  lea     r8, [rsp+130h+hObject]; ThreadInformation
0x180043d4a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180043d51  lea     edx, [r9-3]; ThreadInformationClass
0x180043d55  call    cs:__imp_NtSetInformationThread
0x180043d5c  nop     dword ptr [rax+rax+00h]
0x180043d61  mov     edi, eax
0x180043d63  test    eax, eax
0x180043d65  jns     loc_180043E16
0x180043d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d72  lea     rbx, WPP_GLOBAL_Control
0x180043d79  cmp     rcx, rbx
0x180043d7c  jz      short loc_180043D9C
0x180043d7e  test    [rcx+1Ch], r13d
0x180043d82  jz      short loc_180043D9C
0x180043d84  mov     edx, 1Ah
0x180043d89  mov     rcx, [rcx+10h]
0x180043d8d  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180043d94  mov     r9d, eax
0x180043d97  call    WPP_SF_d
0x180043d9c  cmp     [rsp+130h+TokenHandle], 0
0x180043da2  jz      short loc_180043E0A
0x180043da4  test    r15b, r15b
0x180043da7  jz      short loc_180043DF9
0x180043da9  mov     r9d, 8; ThreadInformationLength
0x180043daf  lea     r8, [rsp+130h+TokenHandle]; ThreadInformation
0x180043db4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180043dbb  lea     edx, [r9-3]; ThreadInformationClass
0x180043dbf  call    cs:__imp_NtSetInformationThread
0x180043dc6  nop     dword ptr [rax+rax+00h]
0x180043dcb  test    eax, eax
0x180043dcd  jns     short loc_180043DF9
0x180043dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180043dd6  cmp     rcx, rbx
0x180043dd9  jz      short loc_180043DF9
0x180043ddb  test    [rcx+1Ch], r13d
0x180043ddf  jz      short loc_180043DF9
0x180043de1  mov     rcx, [rcx+10h]
0x180043de5  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180043dec  mov     edx, 1Ch
0x180043df1  mov     r9d, edi
0x180043df4  call    WPP_SF_d
0x180043df9  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180043dfe  call    cs:__imp_CloseHandle
0x180043e05  nop     dword ptr [rax+rax+00h]
0x180043e0a  mov     qword ptr [r14], 0
0x180043e11  jmp     loc_180043A5A
0x180043e16  mov     rax, [rsp+130h+TokenHandle]
0x180043e1b  mov     [r14], rax
0x180043e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043e25  lea     rbx, WPP_GLOBAL_Control
0x180043e2c  cmp     rcx, rbx
0x180043e2f  jz      loc_180043A5A
0x180043e35  test    dword ptr [rcx+1Ch], 400000h
0x180043e3c  jz      loc_180043A5A
0x180043e42  mov     rcx, [rcx+10h]
0x180043e46  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x180043e4d  mov     edx, 1Bh
0x180043e52  call    WPP_SF_
0x180043e57  jmp     loc_180043A5A
  ... truncated ...
```
