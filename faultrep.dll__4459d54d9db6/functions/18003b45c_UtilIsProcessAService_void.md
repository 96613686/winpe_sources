# UtilIsProcessAService(void *)

- ea: `0x18003b45c`
- end: `0x18003b6e2`
- name: `?UtilIsProcessAService@@YAJPEAX@Z`
- size: `646`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d8b4`
- `0x180014c34`

## callees

- `0x180002890`
- `0x180009f00`
- `0x1800390e0`
- `0x18003b45c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b4cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003b4cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b6c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b6c2`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003b55e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003b55e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b63b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b63b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b671`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b671`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b65b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b687`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b65b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b687`

## pseudocode

```c
__int64 __fastcall UtilIsProcessAService(HANDLE ProcessHandle)
{
  void **v2; // rax
  BOOL v3; // ebx
  PSID v4; // rcx
  signed int v5; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void **v9; // rax
  BOOL v10; // ebx
  PSID v11; // rcx
  signed int LastError; // eax
  unsigned int i; // ebx
  DWORD v14; // r8d
  BOOL v15; // edi
  PSID v16; // rcx
  WINBOOL IsMember; // [rsp+60h] [rbp-29h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-21h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+70h] [rbp-19h] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp-11h] BYREF
  PSID pSid; // [rsp+80h] [rbp-9h] BYREF
  PSID *p_SidToCheck; // [rsp+88h] [rbp-1h]
  DWORD nSubAuthority0[6]; // [rsp+98h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  ExistingTokenHandle = 0;
  TokenHandle = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  nSubAuthority0[0] = 18;
  nSubAuthority0[1] = 19;
  nSubAuthority0[2] = 6;
  nSubAuthority0[3] = 90;
  nSubAuthority0[4] = 83;
  v2 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&pSid, &ExistingTokenHandle);
  v3 = OpenProcessToken(ProcessHandle, 2u, v2);
  if ( pSid )
  {
    v4 = *p_SidToCheck;
    *p_SidToCheck = pSid;
    if ( (unsigned __int64)v4 + 1 > 1 )
      CloseHandle(v4);
  }
  if ( v3 )
  {
    v9 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&pSid, &TokenHandle);
    v10 = DuplicateToken(ExistingTokenHandle, SecurityImpersonation, v9);
    if ( pSid )
    {
      v11 = *p_SidToCheck;
      *p_SidToCheck = pSid;
      if ( (unsigned __int64)v11 + 1 > 1 )
        CloseHandle(v11);
    }
    if ( v10 )
    {
      for ( i = 0; i < 5; ++i )
      {
        if ( IsMember )
          break;
        p_SidToCheck = &SidToCheck;
        pSid = 0;
        v14 = nSubAuthority0[i];
        SidToCheck = 0;
        v15 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, v14, 0, 0, 0, 0, 0, 0, 0, &pSid);
        if ( pSid )
        {
          v16 = *p_SidToCheck;
          *p_SidToCheck = pSid;
          if ( v16 )
            FreeSid(v16);
        }
        if ( v15 && !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
          IsMember = 0;
        if ( SidToCheck )
          FreeSid(SidToCheck);
      }
      v6 = IsMember == 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 42;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 41;
LABEL_23:
      WPP_SF_d(v7[2], v8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v6);
    }
  }
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  if ( (unsigned __int64)ExistingTokenHandle + 1 > 1 )
    CloseHandle(ExistingTokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b45c  push    rbp
0x18003b45e  push    rbx
0x18003b45f  push    rsi
0x18003b460  push    rdi
0x18003b461  lea     rbp, [rsp-3Fh]
0x18003b466  sub     rsp, 0C8h
0x18003b46d  mov     rax, cs:__security_cookie
0x18003b474  xor     rax, rsp
0x18003b477  mov     [rbp+57h+var_28], rax
0x18003b47b  xor     esi, esi
0x18003b47d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003b483  mov     rbx, rcx
0x18003b486  mov     [rbp+57h+IsMember], esi
0x18003b489  lea     rcx, [rbp+57h+var_60]
0x18003b48d  mov     [rbp+57h+ExistingTokenHandle], rsi
0x18003b491  lea     rdx, [rbp+57h+ExistingTokenHandle]
0x18003b495  mov     [rbp+57h+TokenHandle], rsi
0x18003b499  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18003b49c  mov     [rbp+57h+nSubAuthority0], 12h
0x18003b4a3  mov     [rbp+57h+var_44], 13h
0x18003b4aa  mov     [rbp+57h+var_40], 6
0x18003b4b1  mov     [rbp+57h+var_3C], 5Ah ; 'Z'
0x18003b4b8  mov     [rbp+57h+var_38], 53h ; 'S'
0x18003b4bf  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003b4c4  lea     edi, [rsi+2]
0x18003b4c7  mov     r8, rax; TokenHandle
0x18003b4ca  mov     edx, edi; DesiredAccess
0x18003b4cc  mov     rcx, rbx; ProcessHandle
0x18003b4cf  call    cs:__imp_OpenProcessToken
0x18003b4d5  mov     r8, [rbp+57h+var_60]
0x18003b4d9  mov     ebx, eax
0x18003b4db  test    r8, r8
0x18003b4de  jz      short loc_18003B4FA
0x18003b4e0  mov     rdx, [rbp+57h+var_58]
0x18003b4e4  mov     rcx, [rdx]; hObject
0x18003b4e7  mov     [rdx], r8
0x18003b4ea  lea     rdx, [rcx+1]
0x18003b4ee  cmp     rdx, 1
0x18003b4f2  jbe     short loc_18003B4FA
0x18003b4f4  call    cs:__imp_CloseHandle
0x18003b4fa  test    ebx, ebx
0x18003b4fc  jnz     short loc_18003B548
0x18003b4fe  call    cs:__imp_GetLastError
0x18003b504  mov     ebx, eax
0x18003b506  test    eax, eax
0x18003b508  jle     short loc_18003B513
0x18003b50a  movzx   ebx, ax
0x18003b50d  or      ebx, 80070000h
0x18003b513  test    ebx, ebx
0x18003b515  mov     eax, 80004005h
0x18003b51a  cmovns  ebx, eax
0x18003b51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b524  lea     rax, WPP_GLOBAL_Control
0x18003b52b  cmp     rcx, rax
0x18003b52e  jz      loc_18003B6A0
0x18003b534  test    byte ptr [rcx+1Ch], 1
0x18003b538  jz      loc_18003B5E1
0x18003b53e  mov     edx, 29h ; ')'
0x18003b543  jmp     loc_18003B5CE
0x18003b548  lea     rdx, [rbp+57h+TokenHandle]
0x18003b54c  lea     rcx, [rbp+57h+var_60]
0x18003b550  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003b555  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x18003b559  mov     r8, rax; DuplicateTokenHandle
0x18003b55c  mov     edx, edi; ImpersonationLevel
0x18003b55e  call    cs:__imp_DuplicateToken
0x18003b564  mov     r8, [rbp+57h+var_60]
0x18003b568  mov     ebx, eax
0x18003b56a  test    r8, r8
0x18003b56d  jz      short loc_18003B589
0x18003b56f  mov     rdx, [rbp+57h+var_58]
0x18003b573  mov     rcx, [rdx]; hObject
0x18003b576  mov     [rdx], r8
0x18003b579  lea     rdx, [rcx+1]
0x18003b57d  cmp     rdx, 1
0x18003b581  jbe     short loc_18003B589
0x18003b583  call    cs:__imp_CloseHandle
0x18003b589  test    ebx, ebx
0x18003b58b  jnz     short loc_18003B5EE
0x18003b58d  call    cs:__imp_GetLastError
0x18003b593  mov     ebx, eax
0x18003b595  test    eax, eax
0x18003b597  jle     short loc_18003B5A2
0x18003b599  movzx   ebx, ax
0x18003b59c  or      ebx, 80070000h
0x18003b5a2  test    ebx, ebx
0x18003b5a4  mov     eax, 80004005h
0x18003b5a9  cmovns  ebx, eax
0x18003b5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5b3  lea     rax, WPP_GLOBAL_Control
0x18003b5ba  cmp     rcx, rax
0x18003b5bd  jz      loc_18003B6A0
0x18003b5c3  test    byte ptr [rcx+1Ch], 1
0x18003b5c7  jz      short loc_18003B5E1
0x18003b5c9  mov     edx, 2Ah ; '*'
0x18003b5ce  mov     rcx, [rcx+10h]
0x18003b5d2  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b5d9  mov     r9d, ebx
0x18003b5dc  call    WPP_SF_d
0x18003b5e1  test    ebx, ebx
0x18003b5e3  jns     loc_18003B698
0x18003b5e9  jmp     loc_18003B6A0
0x18003b5ee  mov     ebx, esi
0x18003b5f0  cmp     [rbp+57h+IsMember], esi
0x18003b5f3  jnz     loc_18003B698
0x18003b5f9  lea     rax, [rbp+57h+SidToCheck]
0x18003b5fd  mov     r8d, ebx
0x18003b600  mov     [rbp+57h+var_58], rax
0x18003b604  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003b608  lea     rax, [rbp+57h+var_60]
0x18003b60c  mov     [rbp+57h+var_60], rsi
0x18003b610  mov     [rsp+0E0h+pSid], rax; pSid
0x18003b615  xor     r9d, r9d; nSubAuthority1
0x18003b618  mov     r8d, [rbp+r8*4+57h+nSubAuthority0]; nSubAuthority0
0x18003b61d  mov     dl, 1; nSubAuthorityCount
0x18003b61f  mov     [rsp+0E0h+nSubAuthority7], esi; nSubAuthority7
0x18003b623  mov     [rsp+0E0h+nSubAuthority6], esi; nSubAuthority6
0x18003b627  mov     [rsp+0E0h+nSubAuthority5], esi; nSubAuthority5
0x18003b62b  mov     [rsp+0E0h+nSubAuthority4], esi; nSubAuthority4
0x18003b62f  mov     [rsp+0E0h+nSubAuthority3], esi; nSubAuthority3
0x18003b633  mov     [rsp+0E0h+nSubAuthority2], esi; nSubAuthority2
0x18003b637  mov     [rbp+57h+SidToCheck], rsi
0x18003b63b  call    cs:__imp_AllocateAndInitializeSid
0x18003b641  mov     r8, [rbp+57h+var_60]
0x18003b645  mov     edi, eax
0x18003b647  test    r8, r8
0x18003b64a  jz      short loc_18003B661
0x18003b64c  mov     rdx, [rbp+57h+var_58]
0x18003b650  mov     rcx, [rdx]; pSid
0x18003b653  mov     [rdx], r8
0x18003b656  test    rcx, rcx
0x18003b659  jz      short loc_18003B661
0x18003b65b  call    cs:__imp_FreeSid
0x18003b661  test    edi, edi
0x18003b663  jz      short loc_18003B67E
0x18003b665  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003b669  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003b66d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003b671  call    cs:__imp_CheckTokenMembership
0x18003b677  test    eax, eax
0x18003b679  jnz     short loc_18003B67E
0x18003b67b  mov     [rbp+57h+IsMember], esi
0x18003b67e  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003b682  test    rcx, rcx
0x18003b685  jz      short loc_18003B68D
0x18003b687  call    cs:__imp_FreeSid
0x18003b68d  inc     ebx
0x18003b68f  cmp     ebx, 5
0x18003b692  jb      loc_18003B5F0
0x18003b698  cmp     [rbp+57h+IsMember], esi
0x18003b69b  mov     ebx, esi
0x18003b69d  setz    bl
0x18003b6a0  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18003b6a4  lea     rax, [rcx+1]
0x18003b6a8  cmp     rax, 1
0x18003b6ac  jbe     short loc_18003B6B4
0x18003b6ae  call    cs:__imp_CloseHandle
0x18003b6b4  mov     rcx, [rbp+57h+ExistingTokenHandle]; hObject
0x18003b6b8  lea     rdx, [rcx+1]
0x18003b6bc  cmp     rdx, 1
0x18003b6c0  jbe     short loc_18003B6C8
0x18003b6c2  call    cs:__imp_CloseHandle
0x18003b6c8  mov     eax, ebx
0x18003b6ca  mov     rcx, [rbp+57h+var_28]
0x18003b6ce  xor     rcx, rsp; StackCookie
0x18003b6d1  call    __security_check_cookie
0x18003b6d6  add     rsp, 0C8h
0x18003b6dd  pop     rdi
0x18003b6de  pop     rsi
0x18003b6df  pop     rbx
0x18003b6e0  pop     rbp
0x18003b6e1  retn
```
