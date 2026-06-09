# InitUserSidString(void)

- ea: `0x180022af0`
- end: `0x180022c42`
- name: `?InitUserSidString@@YAHXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022890`
- `0x1800229d8`

## callees

- `0x1800139a4`
- `0x180022af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022b2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022b2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022bdc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c37`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180022bb2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180022bb2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022b58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022b8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022b58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022b8d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180022bc0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180022bc0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022ba5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022ba5`

## pseudocode

```c
__int64 InitUserSidString(void)
{
  HANDLE CurrentProcess; // rax
  void **v2; // rbx
  void *v3; // rdi
  void *v4; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  LPWSTR v6; // r9
  unsigned __int16 near **v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  LPWSTR v10; // rcx
  unsigned __int16 near **v11; // rdx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+30h] BYREF

  TokenHandle = 0;
  if ( g_fIsUserSidStringInitialized )
    return 1;
  CurrentProcess = GetCurrentProcess();
  OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  if ( TokenHandle )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    v2 = (void **)LocalAlloc(0x40u, TokenInformationLength);
    if ( v2 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v3 = *v2;
        v4 = *v2;
        StringSid = 0;
        if ( ConvertSidToStringSidW(v4, &StringSid) )
        {
          v6 = StringSid;
          v7 = &g_szUserSidString;
          v8 = 2147483646;
          v9 = 260;
          do
          {
            if ( !v8 )
              break;
            if ( !*v6 )
              break;
            *(_WORD *)v7 = *v6++;
            v7 = (unsigned __int16 near **)((char *)v7 + 2);
            --v8;
            --v9;
          }
          while ( v9 );
          v10 = StringSid;
          v11 = (unsigned __int16 near **)((char *)v7 - 2);
          if ( v9 )
            v11 = v7;
          *(_WORD *)v11 = 0;
          LocalFree(v10);
        }
        SidSubAuthorityCount = GetSidSubAuthorityCount(v3);
        GetSidSubAuthority(v3, *SidSubAuthorityCount - 1);
        g_fIsUserSidStringInitialized = 1;
      }
      cicMemFree(v2);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)g_fIsUserSidStringInitialized;
}

```

## disassembly

```asm
0x180022af0  mov     [rsp-18h+arg_18], rbx
0x180022af5  push    rbp
0x180022af6  push    rsi
0x180022af7  push    rdi
0x180022af8  mov     rbp, rsp
0x180022afb  sub     rsp, 30h
0x180022aff  xor     esi, esi
0x180022b01  cmp     cs:?g_fIsUserSidStringInitialized@@3HA, esi; int g_fIsUserSidStringInitialized
0x180022b07  mov     [rbp+TokenHandle], rsi
0x180022b0b  jz      short loc_180022B1D
0x180022b0d  lea     eax, [rsi+1]
0x180022b10  mov     rbx, [rsp+30h+arg_18]
0x180022b15  add     rsp, 30h
0x180022b19  pop     rdi
0x180022b1a  pop     rsi
0x180022b1b  pop     rbp
0x180022b1c  retn
0x180022b1d  call    cs:__imp_GetCurrentProcess
0x180022b23  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180022b27  mov     edx, 8; DesiredAccess
0x180022b2c  mov     rcx, rax; ProcessHandle
0x180022b2f  call    cs:__imp_OpenProcessToken
0x180022b35  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022b39  test    rcx, rcx
0x180022b3c  jz      loc_180022BE2
0x180022b42  xor     r9d, r9d; TokenInformationLength
0x180022b45  mov     [rbp+TokenInformationLength], esi
0x180022b48  lea     rax, [rbp+TokenInformationLength]
0x180022b4c  xor     r8d, r8d; TokenInformation
0x180022b4f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022b54  lea     edx, [r9+1]; TokenInformationClass
0x180022b58  call    cs:__imp_GetTokenInformation
0x180022b5e  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180022b61  mov     ecx, 40h ; '@'; uFlags
0x180022b66  call    cs:__imp_LocalAlloc
0x180022b6c  mov     rbx, rax
0x180022b6f  test    rax, rax
0x180022b72  jz      short loc_180022BD8
0x180022b74  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180022b78  lea     rax, [rbp+TokenInformationLength]
0x180022b7c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180022b80  mov     r8, rbx; TokenInformation
0x180022b83  mov     edx, 1; TokenInformationClass
0x180022b88  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022b8d  call    cs:__imp_GetTokenInformation
0x180022b93  test    eax, eax
0x180022b95  jz      short loc_180022BD0
0x180022b97  mov     rdi, [rbx]
0x180022b9a  lea     rdx, [rbp+StringSid]; StringSid
0x180022b9e  mov     rcx, rdi; Sid
0x180022ba1  mov     [rbp+StringSid], rsi
0x180022ba5  call    cs:__imp_ConvertSidToStringSidW
0x180022bab  test    eax, eax
0x180022bad  jnz     short loc_180022BED
0x180022baf  mov     rcx, rdi; pSid
0x180022bb2  call    cs:__imp_GetSidSubAuthorityCount
0x180022bb8  mov     rcx, rdi; pSid
0x180022bbb  movzx   edx, byte ptr [rax]
0x180022bbe  dec     edx; nSubAuthority
0x180022bc0  call    cs:__imp_GetSidSubAuthority
0x180022bc6  mov     cs:?g_fIsUserSidStringInitialized@@3HA, 1; int g_fIsUserSidStringInitialized
0x180022bd0  mov     rcx, rbx
0x180022bd3  call    cicMemFree
0x180022bd8  mov     rcx, [rbp+TokenHandle]; hObject
0x180022bdc  call    cs:__imp_CloseHandle
0x180022be2  mov     eax, cs:?g_fIsUserSidStringInitialized@@3HA; int g_fIsUserSidStringInitialized
0x180022be8  jmp     loc_180022B10
0x180022bed  mov     r9, [rbp+StringSid]
0x180022bf1  lea     rax, ?g_szUserSidString@@3PAGA; ushort near * g_szUserSidString
0x180022bf8  mov     edx, 7FFFFFFEh
0x180022bfd  mov     r8d, 104h
0x180022c03  test    rdx, rdx
0x180022c06  jz      short loc_180022C25
0x180022c08  movzx   ecx, word ptr [r9]
0x180022c0c  test    cx, cx
0x180022c0f  jz      short loc_180022C25
0x180022c11  mov     [rax], cx
0x180022c14  add     r9, 2
0x180022c18  add     rax, 2
0x180022c1c  dec     rdx
0x180022c1f  sub     r8, 1
0x180022c23  jnz     short loc_180022C03
0x180022c25  mov     rcx, [rbp+StringSid]; hMem
0x180022c29  lea     rdx, [rax-2]
0x180022c2d  test    r8, r8
0x180022c30  cmovnz  rdx, rax
0x180022c34  mov     [rdx], si
0x180022c37  call    cs:__imp_LocalFree
0x180022c3d  jmp     loc_180022BAF
```
