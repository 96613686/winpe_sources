# UtilIsWriteRestrictedToken(void *)

- ea: `0x18003bbdc`
- end: `0x18003bd78`
- name: `?UtilIsWriteRestrictedToken@@YA_NPEAX@Z`
- size: `412`
- prototype: `bool __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bb10`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180009f00`
- `0x1800390e0`
- `0x18003bbdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bc52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd53`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003bc2d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003bc2d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bcee`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bcee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003bcb2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003bcb2`

## pseudocode

```c
bool __fastcall UtilIsWriteRestrictedToken(HANDLE ExistingTokenHandle)
{
  void **v2; // rax
  BOOL v3; // ebx
  void *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // rdx
  bool v8; // bl
  HANDLE TokenHandle; // [rsp+20h] [rbp-39h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+2Ch] [rbp-2Dh] BYREF
  void *v12; // [rsp+30h] [rbp-29h] BYREF
  void **v13; // [rsp+38h] [rbp-21h]
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  cbSid = 68;
  v2 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v12, &TokenHandle);
  v3 = DuplicateToken(ExistingTokenHandle, SecurityImpersonation, v2);
  if ( v12 )
  {
    v4 = *v13;
    *v13 = v12;
    if ( (unsigned __int64)v4 + 1 > 1 )
      CloseHandle(v4);
  }
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v6 = 43;
LABEL_8:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( !CreateWellKnownSid(WinWriteRestrictedCodeSid, 0, pSid, &cbSid) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v6 = 44;
      goto LABEL_8;
    }
LABEL_17:
    if ( (unsigned __int64)TokenHandle + 1 > 1 )
      CloseHandle(TokenHandle);
    return 0;
  }
  if ( !CheckTokenMembership(TokenHandle, pSid, &IsMember) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    goto LABEL_17;
  }
  v8 = IsMember != 0;
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x18003bbdc  mov     [rsp-8+arg_8], rbx
0x18003bbe1  push    rbp
0x18003bbe2  lea     rbp, [rsp-57h]
0x18003bbe7  sub     rsp, 0B0h
0x18003bbee  mov     rax, cs:__security_cookie
0x18003bbf5  xor     rax, rsp
0x18003bbf8  mov     [rbp+57h+var_10], rax
0x18003bbfc  mov     rbx, rcx
0x18003bbff  mov     [rbp+57h+TokenHandle], 0
0x18003bc07  lea     rcx, [rbp+57h+var_80]
0x18003bc0b  mov     [rbp+57h+IsMember], 0
0x18003bc12  lea     rdx, [rbp+57h+TokenHandle]
0x18003bc16  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18003bc1d  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003bc22  mov     r8, rax; DuplicateTokenHandle
0x18003bc25  mov     edx, 2; ImpersonationLevel
0x18003bc2a  mov     rcx, rbx; ExistingTokenHandle
0x18003bc2d  call    cs:__imp_DuplicateToken
0x18003bc33  mov     r8, [rbp+57h+var_80]
0x18003bc37  mov     ebx, eax
0x18003bc39  test    r8, r8
0x18003bc3c  jz      short loc_18003BC58
0x18003bc3e  mov     rdx, [rbp+57h+var_78]
0x18003bc42  mov     rcx, [rdx]; hObject
0x18003bc45  mov     [rdx], r8
0x18003bc48  lea     rdx, [rcx+1]
0x18003bc4c  cmp     rdx, 1
0x18003bc50  jbe     short loc_18003BC58
0x18003bc52  call    cs:__imp_CloseHandle
0x18003bc58  test    ebx, ebx
0x18003bc5a  jnz     short loc_18003BCA5
0x18003bc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc63  lea     rax, WPP_GLOBAL_Control
0x18003bc6a  cmp     rcx, rax
0x18003bc6d  jz      loc_18003BD26
0x18003bc73  test    byte ptr [rcx+1Ch], 1
0x18003bc77  jz      loc_18003BD26
0x18003bc7d  call    cs:__imp_GetLastError
0x18003bc83  lea     edx, [rbx+2Bh]
0x18003bc86  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc8d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003bc94  mov     r9d, eax
0x18003bc97  mov     rcx, [rcx+10h]
0x18003bc9b  call    WPP_SF_d
0x18003bca0  jmp     loc_18003BD26
0x18003bca5  xor     edx, edx; DomainSid
0x18003bca7  lea     r9, [rbp+57h+cbSid]; cbSid
0x18003bcab  lea     r8, [rbp+57h+pSid]; pSid
0x18003bcaf  lea     ecx, [rdx+46h]; WellKnownSidType
0x18003bcb2  call    cs:__imp_CreateWellKnownSid
0x18003bcb8  test    eax, eax
0x18003bcba  jnz     short loc_18003BCE2
0x18003bcbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcc3  lea     rax, WPP_GLOBAL_Control
0x18003bcca  cmp     rcx, rax
0x18003bccd  jz      short loc_18003BD26
0x18003bccf  test    byte ptr [rcx+1Ch], 1
0x18003bcd3  jz      short loc_18003BD26
0x18003bcd5  call    cs:__imp_GetLastError
0x18003bcdb  mov     edx, 2Ch ; ','
0x18003bce0  jmp     short loc_18003BC86
0x18003bce2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003bce6  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003bcea  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18003bcee  call    cs:__imp_CheckTokenMembership
0x18003bcf4  test    eax, eax
0x18003bcf6  jnz     short loc_18003BD3E
0x18003bcf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcff  lea     rax, WPP_GLOBAL_Control
0x18003bd06  cmp     rcx, rax
0x18003bd09  jz      short loc_18003BD26
0x18003bd0b  test    byte ptr [rcx+1Ch], 1
0x18003bd0f  jz      short loc_18003BD26
0x18003bd11  mov     rcx, [rcx+10h]
0x18003bd15  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003bd1c  mov     edx, 2Dh ; '-'
0x18003bd21  call    WPP_SF_
0x18003bd26  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18003bd2a  lea     rax, [rcx+1]
0x18003bd2e  cmp     rax, 1
0x18003bd32  jbe     short loc_18003BD3A
0x18003bd34  call    cs:__imp_CloseHandle
0x18003bd3a  xor     al, al
0x18003bd3c  jmp     short loc_18003BD5B
0x18003bd3e  cmp     [rbp+57h+IsMember], 0
0x18003bd42  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18003bd46  setnz   bl
0x18003bd49  lea     rdx, [rcx+1]
0x18003bd4d  cmp     rdx, 1
0x18003bd51  jbe     short loc_18003BD59
0x18003bd53  call    cs:__imp_CloseHandle
0x18003bd59  mov     al, bl
0x18003bd5b  mov     rcx, [rbp+57h+var_10]
0x18003bd5f  xor     rcx, rsp; StackCookie
0x18003bd62  call    __security_check_cookie
0x18003bd67  mov     rbx, [rsp+0B0h+arg_8]
0x18003bd6f  add     rsp, 0B0h
0x18003bd76  pop     rbp
0x18003bd77  retn
```
