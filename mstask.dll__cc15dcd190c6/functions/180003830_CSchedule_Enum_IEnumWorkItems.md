# CSchedule::Enum(IEnumWorkItems * *)

- ea: `0x180003830`
- end: `0x180003cd7`
- name: `?Enum@CSchedule@@UEAAJPEAPEAUIEnumWorkItems@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, struct IEnumWorkItems **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003830`
- `0x180003ce0`
- `0x180009a04`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003996`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800039e6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003996`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800039e6`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180003937`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180003937`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003a5d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003a5d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003a76`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000391a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000391a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000390c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000395d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000390c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000395d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800038f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003945`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800038f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a85`

## pseudocode

```c
__int64 __fastcall CSchedule::Enum(CSchedule *this, struct IEnumWorkItems **a2)
{
  const WCHAR **v3; // rbx
  char *v4; // r14
  __int64 result; // rax
  const WCHAR *v6; // r14
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v9; // edi
  HANDLE v10; // rax
  void *v11; // r15
  signed int v12; // eax
  void *v13; // rsi
  signed int v14; // eax
  unsigned __int64 v15; // rsi
  _WORD *v16; // rax
  _WORD *v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // rcx
  const WCHAR *v20; // rbx
  _WORD *v21; // rcx
  _WORD *v22; // rax
  _WORD *v23; // r8
  const unsigned __int16 *v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  _WORD *v27; // rcx
  _WORD *v28; // rdx
  __int64 v29; // r8
  const unsigned __int16 *v30; // rcx
  _WORD *v31; // rcx
  unsigned int v32; // ebx
  __int64 v33; // rsi
  DWORD nLengthNeeded; // [rsp+48h] [rbp-29h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-19h] BYREF
  DWORD PrivilegeSetLength; // [rsp+60h] [rbp-11h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-9h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+7h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v3 = (const WCHAR **)((char *)this + 64);
  if ( !*((_QWORD *)this + 7) )
  {
    v6 = *v3;
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v9 = FolderAccessCheck(v6, TokenHandle, 1u);
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError != 1008 )
      {
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_21:
        if ( v9 < 0 )
          return (unsigned int)v9;
        goto LABEL_3;
      }
      v9 = -2147024891;
      if ( ImpersonateSelf(SecurityImpersonation) )
      {
        v10 = GetCurrentThread();
        if ( OpenThreadToken(v10, 8u, 1, &TokenHandle) && v6 )
        {
          v11 = TokenHandle;
          nLengthNeeded = 0;
          if ( GetFileSecurityW(v6, 7u, 0, 0, &nLengthNeeded) || (v12 = GetLastError(), v12 == 122) )
          {
            if ( nLengthNeeded )
            {
              v13 = operator new(nLengthNeeded + 1);
              if ( v13 )
              {
                if ( GetFileSecurityW(v6, 7u, v13, nLengthNeeded, &nLengthNeeded) )
                {
                  GenericMapping.GenericRead = 1179785;
                  AccessStatus = 0;
                  GrantedAccess = 0;
                  GenericMapping.GenericWrite = 1179926;
                  GenericMapping.GenericExecute = 1179808;
                  GenericMapping.GenericAll = 2032127;
                  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
                  PrivilegeSetLength = 20;
                  if ( AccessCheck(
                         v13,
                         v11,
                         1u,
                         &GenericMapping,
                         &PrivilegeSet,
                         &PrivilegeSetLength,
                         &GrantedAccess,
                         &AccessStatus)
                    && AccessStatus
                    && (GrantedAccess & 1) != 0 )
                  {
                    v9 = 0;
                  }
                }
                else
                {
                  v14 = GetLastError();
                  v9 = v14;
                  if ( v14 > 0 )
                    v9 = (unsigned __int16)v14 | 0x80070000;
                }
                operator delete(v13);
              }
            }
          }
          else if ( v12 > 0 )
          {
            v9 = (unsigned __int16)v12 | 0x80070000;
          }
          else
          {
            v9 = v12;
          }
        }
        RevertToSelf();
      }
    }
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    goto LABEL_21;
  }
LABEL_3:
  v4 = (char *)operator new(0x260u);
  if ( !v4 )
  {
    result = 2147942414LL;
LABEL_5:
    *a2 = 0;
    return result;
  }
  *((_QWORD *)v4 + 1) = -1;
  *(_QWORD *)v4 = &CEnumJobs::`vftable';
  *((_QWORD *)v4 + 2) = 0;
  *((_QWORD *)v4 + 3) = 0;
  *(_QWORD *)(v4 + 588) = 0;
  *((_DWORD *)v4 + 149) = 0;
  *((_DWORD *)v4 + 150) = 1;
  _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
  *((_WORD *)v4 + 16) = 0;
  v20 = *v3;
  if ( !v20 )
  {
    v32 = -2147467259;
    goto LABEL_52;
  }
  v33 = -1;
  do
    ++v33;
  while ( v20[v33] );
  v15 = v33 + 1;
  v16 = operator new(saturated_mul(v15, 2u));
  *((_QWORD *)v4 + 3) = v16;
  v17 = v16;
  if ( !v16 )
  {
LABEL_51:
    v32 = -2147024882;
LABEL_52:
    CEnumJobs::~CEnumJobs((CEnumJobs *)v4);
    operator delete(v4);
    result = v32;
    goto LABEL_5;
  }
  v18 = 2147483646;
  if ( v15 )
  {
    if ( v15 > 0x7FFFFFFF )
    {
      *v16 = 0;
    }
    else
    {
      v19 = 2147483646;
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v17++ = *v20++;
        --v19;
        --v15;
      }
      while ( v15 );
      v21 = v17 - 1;
      if ( v15 )
        v21 = v17;
      *v21 = 0;
    }
  }
  v22 = operator new(0x218u);
  v23 = v22;
  if ( !v22 )
  {
    *((_QWORD *)v4 + 2) = 0;
    goto LABEL_51;
  }
  *((_QWORD *)v22 + 66) = 0;
  v24 = L".";
  *((_QWORD *)v4 + 2) = v22;
  v25 = 2147483646;
  v26 = 261;
  do
  {
    if ( !v25 )
      break;
    if ( !*v24 )
      break;
    *v23++ = *v24++;
    --v25;
    --v26;
  }
  while ( v26 );
  v27 = v23 - 1;
  v28 = v4 + 554;
  if ( v26 )
    v27 = v23;
  v29 = 16;
  *v27 = 0;
  v30 = L".job";
  do
  {
    if ( !v18 )
      break;
    if ( !*v30 )
      break;
    *v28++ = *v30++;
    --v18;
    --v29;
  }
  while ( v29 );
  v31 = v28 - 1;
  result = 0;
  if ( v29 )
    v31 = v28;
  *v31 = 0;
  *((_DWORD *)v4 + 148) = 1;
  *a2 = (struct IEnumWorkItems *)v4;
  return result;
}

```

## disassembly

```asm
0x180003830  mov     r11, rsp
0x180003833  push    rbp
0x180003834  push    r12
0x180003836  lea     rbp, [r11-5Fh]
0x18000383a  sub     rsp, 0B8h
0x180003841  mov     rax, cs:__security_cookie
0x180003848  xor     rax, rsp
0x18000384b  mov     [rbp+57h+var_38], rax
0x18000384f  mov     r12, rdx
0x180003852  test    rdx, rdx
0x180003855  jz      loc_180003C9F
0x18000385b  mov     [r11+18h], rbx
0x18000385f  lea     rbx, [rcx+40h]
0x180003863  mov     [r11-18h], rsi
0x180003867  mov     [r11-20h], rdi
0x18000386b  mov     [r11-28h], r13
0x18000386f  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180003876  mov     [r11-30h], r14
0x18000387a  mov     [r11-38h], r15
0x18000387e  xor     r15d, r15d
0x180003881  cmp     [rcx+38h], r15
0x180003885  jz      short loc_1800038ED
0x180003887  mov     ecx, 260h; Size
0x18000388c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003891  mov     r14, rax
0x180003894  test    rax, rax
0x180003897  jnz     loc_180003C17
0x18000389d  mov     eax, 8007000Eh
0x1800038a2  mov     [r12], r15
0x1800038a6  mov     r14, [rsp+0C0h+var_28]
0x1800038ae  mov     r13, [rsp+0C0h+var_20]
0x1800038b6  mov     rdi, [rsp+0C0h+var_18]
0x1800038be  mov     rsi, [rsp+0B0h]
0x1800038c6  mov     rbx, [rsp+0C0h+arg_10]
0x1800038ce  mov     r15, [rsp+0C0h+var_30]
0x1800038d6  mov     rcx, [rbp+57h+var_38]
0x1800038da  xor     rcx, rsp; StackCookie
0x1800038dd  call    __security_check_cookie
0x1800038e2  add     rsp, 0B8h
0x1800038e9  pop     r12
0x1800038eb  pop     rbp
0x1800038ec  retn
0x1800038ed  mov     r14, [rbx]
0x1800038f0  mov     [rbp+57h+TokenHandle], r13
0x1800038f4  call    cs:__imp_GetCurrentThread
0x1800038fa  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800038fe  mov     edx, 8; DesiredAccess
0x180003903  mov     rcx, rax; ThreadHandle
0x180003906  mov     r8d, 1; OpenAsSelf
0x18000390c  call    cs:__imp_OpenThreadToken
0x180003912  test    eax, eax
0x180003914  jnz     loc_180003A9A
0x18000391a  call    cs:__imp_GetLastError
0x180003920  mov     edi, eax
0x180003922  cmp     eax, 3F0h
0x180003927  jnz     loc_180003C70
0x18000392d  mov     ecx, 2; ImpersonationLevel
0x180003932  mov     edi, 80070005h
0x180003937  call    cs:__imp_ImpersonateSelf
0x18000393d  test    eax, eax
0x18000393f  jz      loc_180003A7C
0x180003945  call    cs:__imp_GetCurrentThread
0x18000394b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000394f  mov     edx, 8; DesiredAccess
0x180003954  mov     rcx, rax; ThreadHandle
0x180003957  mov     r8d, 1; OpenAsSelf
0x18000395d  call    cs:__imp_OpenThreadToken
0x180003963  test    eax, eax
0x180003965  jz      loc_180003A76
0x18000396b  test    r14, r14
0x18000396e  jz      loc_180003A76
0x180003974  mov     r15, [rbp+57h+TokenHandle]
0x180003978  lea     rax, [rbp+57h+nLengthNeeded]
0x18000397c  xor     r9d, r9d; nLength
0x18000397f  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180003984  xor     r8d, r8d; pSecurityDescriptor
0x180003987  mov     [rbp+57h+nLengthNeeded], 0
0x18000398e  mov     edx, 7; RequestedInformation
0x180003993  mov     rcx, r14; lpFileName
0x180003996  call    cs:__imp_GetFileSecurityW
0x18000399c  test    eax, eax
0x18000399e  jnz     short loc_1800039AF
0x1800039a0  call    cs:__imp_GetLastError
0x1800039a6  cmp     eax, 7Ah ; 'z'
0x1800039a9  jnz     loc_180003C86
0x1800039af  mov     eax, [rbp+57h+nLengthNeeded]
0x1800039b2  test    eax, eax
0x1800039b4  jz      loc_180003A73
0x1800039ba  lea     ecx, [rax+1]; Size
0x1800039bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039c2  mov     rsi, rax
0x1800039c5  test    rax, rax
0x1800039c8  jz      loc_180003A73
0x1800039ce  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1800039d2  lea     rax, [rbp+57h+nLengthNeeded]
0x1800039d6  mov     r8, rsi; pSecurityDescriptor
0x1800039d9  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800039de  mov     edx, 7; RequestedInformation
0x1800039e3  mov     rcx, r14; lpFileName
0x1800039e6  call    cs:__imp_GetFileSecurityW
0x1800039ec  test    eax, eax
0x1800039ee  jz      loc_180003AB0
0x1800039f4  xor     eax, eax
0x1800039f6  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1800039fd  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180003a00  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180003a04  mov     [rbp+57h+AccessStatus], eax
0x180003a07  xorps   xmm0, xmm0
0x180003a0a  mov     [rbp+57h+var_78], eax
0x180003a0d  mov     r8d, 1; DesiredAccess
0x180003a13  lea     rax, [rbp+57h+AccessStatus]
0x180003a17  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x180003a1e  mov     [rsp+38h], rax; AccessStatus
0x180003a23  mov     rdx, r15; ClientToken
0x180003a26  lea     rax, [rbp+57h+var_78]
0x180003a2a  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x180003a31  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180003a36  mov     rcx, rsi; pSecurityDescriptor
0x180003a39  lea     rax, [rbp+57h+var_68]
0x180003a3d  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x180003a44  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180003a49  lea     rax, [rbp+57h+PrivilegeSet]
0x180003a4d  mov     [rsp+0C0h+lpnLengthNeeded], rax; PrivilegeSet
0x180003a52  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180003a56  mov     [rbp+57h+var_68], 14h
0x180003a5d  call    cs:__imp_AccessCheck
0x180003a63  test    eax, eax
0x180003a65  jnz     loc_180003CA9
0x180003a6b  mov     rcx, rsi; Block
0x180003a6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a73  xor     r15d, r15d
0x180003a76  call    cs:__imp_RevertToSelf
0x180003a7c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180003a80  cmp     rcx, r13
0x180003a83  jz      short loc_180003A8B
0x180003a85  call    cs:__imp_CloseHandle
0x180003a8b  test    edi, edi
0x180003a8d  jns     loc_180003887
0x180003a93  mov     eax, edi
0x180003a95  jmp     loc_1800038A6
0x180003a9a  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180003a9e  mov     r8d, 1; DesiredAccess
0x180003aa4  mov     rcx, r14; lpFileName
0x180003aa7  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x180003aac  mov     edi, eax
0x180003aae  jmp     short loc_180003A7C
0x180003ab0  call    cs:__imp_GetLastError
0x180003ab6  mov     edi, eax
0x180003ab8  test    eax, eax
0x180003aba  jle     short loc_180003A6B
0x180003abc  movzx   edi, ax
0x180003abf  or      edi, 80070000h
0x180003ac5  jmp     short loc_180003A6B
0x180003ac7  inc     rsi
0x180003aca  mov     eax, 2
0x180003acf  mul     rsi
0x180003ad2  cmovb   rax, r13
0x180003ad6  mov     rcx, rax; Size
0x180003ad9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ade  mov     [r14+18h], rax
0x180003ae2  mov     rdx, rax
0x180003ae5  test    rax, rax
0x180003ae8  jz      loc_180003BFB
0x180003aee  mov     edi, 7FFFFFFEh
0x180003af3  test    rsi, rsi
0x180003af6  jz      short loc_180003B37
0x180003af8  cmp     rsi, 7FFFFFFFh
0x180003aff  ja      loc_180003CCE
0x180003b05  mov     ecx, edi
0x180003b07  test    rcx, rcx
0x180003b0a  jz      short loc_180003B28
0x180003b0c  movzx   eax, word ptr [rbx]
0x180003b0f  test    ax, ax
0x180003b12  jz      short loc_180003B28
0x180003b14  mov     [rdx], ax
0x180003b17  add     rbx, 2
0x180003b1b  add     rdx, 2
0x180003b1f  dec     rcx
0x180003b22  sub     rsi, 1
0x180003b26  jnz     short loc_180003B07
0x180003b28  test    rsi, rsi
0x180003b2b  lea     rcx, [rdx-2]
0x180003b2f  cmovnz  rcx, rdx
0x180003b33  mov     [rcx], r15w
0x180003b37  mov     ecx, 218h; Size
0x180003b3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b41  mov     r8, rax
0x180003b44  test    rax, rax
0x180003b47  jz      loc_180003BF7
0x180003b4d  mov     [rax+210h], r15
0x180003b54  lea     rdx, asc_18001D95C; "."
0x180003b5b  mov     [r14+10h], rax
0x180003b5f  mov     rcx, rdi
0x180003b62  mov     r9d, 105h
0x180003b68  test    rcx, rcx
0x180003b6b  jz      short loc_180003B8A
0x180003b6d  movzx   eax, word ptr [rdx]
0x180003b70  test    ax, ax
0x180003b73  jz      short loc_180003B8A
0x180003b75  mov     [r8], ax
0x180003b79  add     rdx, 2
0x180003b7d  add     r8, 2
0x180003b81  dec     rcx
0x180003b84  sub     r9, 1
0x180003b88  jnz     short loc_180003B68
0x180003b8a  lea     rcx, [r8-2]
0x180003b8e  test    r9, r9
0x180003b91  lea     rdx, [r14+22Ah]
0x180003b98  cmovnz  rcx, r8
0x180003b9c  mov     r8d, 10h
0x180003ba2  mov     [rcx], r15w
0x180003ba6  lea     rcx, aJob; ".job"
0x180003bad  nop     dword ptr [rax]
0x180003bb0  test    rdi, rdi
0x180003bb3  jz      short loc_180003BD1
0x180003bb5  movzx   eax, word ptr [rcx]
0x180003bb8  test    ax, ax
0x180003bbb  jz      short loc_180003BD1
0x180003bbd  mov     [rdx], ax
0x180003bc0  add     rcx, 2
0x180003bc4  add     rdx, 2
0x180003bc8  dec     rdi
0x180003bcb  sub     r8, 1
0x180003bcf  jnz     short loc_180003BB0
0x180003bd1  test    r8, r8
0x180003bd4  lea     rcx, [rdx-2]
0x180003bd8  mov     eax, r15d
0x180003bdb  cmovnz  rcx, rdx
0x180003bdf  mov     [rcx], r15w
0x180003be3  mov     dword ptr [r14+250h], 1
0x180003bee  mov     [r12], r14
0x180003bf2  jmp     loc_1800038A6
0x180003bf7  mov     [r14+10h], r15
0x180003bfb  mov     ebx, 8007000Eh
0x180003c00  mov     rcx, r14; this
0x180003c03  call    ??1CEnumJobs@@QEAA@XZ; CEnumJobs::~CEnumJobs(void)
0x180003c08  mov     rcx, r14; Block
0x180003c0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003c10  mov     eax, ebx
0x180003c12  jmp     loc_1800038A2
0x180003c17  lea     rax, ??_7CEnumJobs@@6B@; const CEnumJobs::`vftable'
0x180003c1e  mov     [r14+8], r13
0x180003c22  mov     [r14], rax
0x180003c25  mov     [r14+10h], r15
0x180003c29  mov     [r14+18h], r15
0x180003c2d  mov     qword ptr [r14+24Ch], 0
0x180003c38  mov     [r14+254h], r15d
0x180003c3f  mov     dword ptr [r14+258h], 1
0x180003c4a  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180003c51  mov     [r14+20h], r15w
0x180003c56  mov     rbx, [rbx]
0x180003c59  test    rbx, rbx
0x180003c5c  jz      short loc_180003CC4
0x180003c5e  mov     rsi, r13
0x180003c61  inc     rsi
0x180003c64  cmp     word ptr [rbx+rsi*2], 0
0x180003c69  jnz     short loc_180003C61
0x180003c6b  jmp     loc_180003AC7
0x180003c70  test    eax, eax
0x180003c72  jle     loc_180003A8B
0x180003c78  movzx   edi, ax
0x180003c7b  or      edi, 80070000h
0x180003c81  jmp     loc_180003A8B
0x180003c86  test    eax, eax
0x180003c88  jg      short loc_180003C91
0x180003c8a  mov     edi, eax
0x180003c8c  jmp     loc_180003A73
0x180003c91  movzx   edi, ax
0x180003c94  or      edi, 80070000h
0x180003c9a  jmp     loc_180003A73
0x180003c9f  mov     eax, 80070057h
0x180003ca4  jmp     loc_1800038D6
0x180003ca9  cmp     [rbp+57h+AccessStatus], 0
0x180003cad  jz      loc_180003A6B
0x180003cb3  test    byte ptr [rbp+57h+var_78], 1
0x180003cb7  jz      loc_180003A6B
0x180003cbd  xor     edi, edi
0x180003cbf  jmp     loc_180003A6B
0x180003cc4  mov     ebx, 80004005h
0x180003cc9  jmp     loc_180003C00
0x180003cce  mov     [rax], r15w
0x180003cd2  jmp     loc_180003B37
```
