# GetUser(void *,ulong *,ushort *)

- ea: `0x18008eeac`
- end: `0x18008f148`
- name: `?GetUser@@YAJPEAXPEAKPEAG@Z`
- size: `668`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f150`
- `0x18008f260`

## callees

- `0x180034cf8`
- `0x180037120`
- `0x18008eeac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f0b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f0b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ef06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ef45`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ef06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ef45`
- `wbemcomn!GetMemLogObject` at `0x18008f0e6`
- `wbemcomn!GetMemLogObject` at `0x18008f0e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f0f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008f0f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f085`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f095`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f0c4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f085`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f095`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18008f0c4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008ef26`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008efc6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008efe8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008ef26`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008efc6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18008efe8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008ef83`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008f019`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008ef83`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008f019`

## pseudocode

```c
__int64 __fastcall GetUser(HANDLE TokenHandle, unsigned int *a2, unsigned __int16 *a3)
{
  PSID *v6; // rdi
  PSID v7; // rcx
  DWORD LastError; // eax
  int v9; // ebx
  __int64 v10; // rbx
  WCHAR *v11; // r15
  WCHAR *v12; // r14
  __int64 v13; // rax
  unsigned int v14; // esi
  CMemoryLog *MemLogObject; // rax
  DWORD cchName; // [rsp+30h] [rbp-10h] BYREF
  enum _SID_NAME_USE peUse[3]; // [rsp+34h] [rbp-Ch] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+58h] BYREF

  if ( !TokenHandle )
  {
    v9 = -2147024890;
LABEL_35:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    goto LABEL_36;
  }
  if ( a2 && a3 )
  {
    TokenInformationLength = 0;
    v6 = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
      && GetLastError() == 122
      && (v6 = (PSID *)CWin32DefaultArena::WbemMemAlloc(TokenInformationLength),
          GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength))
      && v6 )
    {
      v7 = *v6;
      peUse[0] = 0;
      cchReferencedDomainName = 0;
      cchName = 0;
      if ( LookupAccountSidLocalW(v7, 0, &cchName, 0, &cchReferencedDomainName, peUse) )
      {
        v9 = -2147217379;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 122 )
        {
          v10 = -1;
          v11 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchName, 2u));
          if ( v11 )
          {
            v12 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchReferencedDomainName, 2u));
            if ( v12 )
            {
              if ( LookupAccountSidLocalW(*v6, v11, &cchName, v12, &cchReferencedDomainName, peUse) )
              {
                v13 = -1;
                do
                  ++v13;
                while ( v12[v13] );
                do
                  ++v10;
                while ( v11[v10] );
                v14 = v13 + v10 + 2;
                if ( *a2 < v14 )
                {
                  v9 = -2147217348;
                }
                else
                {
                  v9 = 0;
                  StringCchPrintfW(a3, v14, L"%s\\%s", v12, v11);
                }
                *a2 = v14;
              }
              else
              {
                v9 = -(GetLastError() != 1332) - 2147217406;
              }
              CWin32DefaultArena::WbemMemFree(v12);
            }
            else
            {
              v9 = -2147217402;
            }
            CWin32DefaultArena::WbemMemFree(v11);
          }
          else
          {
            v9 = -2147217402;
          }
        }
        else
        {
          v9 = -2147217406 - (LastError != 1332);
        }
      }
    }
    else
    {
      GetLastError();
      v9 = -2147217407;
      if ( !v6 )
        goto LABEL_30;
    }
    CWin32DefaultArena::WbemMemFree(v6);
  }
  else
  {
    v9 = -2147217400;
  }
LABEL_30:
  if ( v9 == -2147217406 )
    return 2147749890LL;
  if ( v9 < 0 )
    goto LABEL_35;
LABEL_36:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008eeac  mov     [rsp-38h+arg_8], rbx
0x18008eeb1  push    rbp
0x18008eeb2  push    rsi
0x18008eeb3  push    rdi
0x18008eeb4  push    r12
0x18008eeb6  push    r13
0x18008eeb8  push    r14
0x18008eeba  push    r15
0x18008eebc  mov     rbp, rsp
0x18008eebf  sub     rsp, 40h
0x18008eec3  xor     esi, esi
0x18008eec5  mov     r13, r8
0x18008eec8  mov     r12, rdx
0x18008eecb  mov     rbx, rcx
0x18008eece  test    rcx, rcx
0x18008eed1  jz      loc_18008F0E1
0x18008eed7  mov     r14d, 80041002h
0x18008eedd  test    rdx, rdx
0x18008eee0  jz      loc_18008F0CC
0x18008eee6  test    r8, r8
0x18008eee9  jz      loc_18008F0CC
0x18008eeef  lea     rax, [rbp+TokenInformationLength]
0x18008eef3  mov     [rbp+TokenInformationLength], esi
0x18008eef6  xor     r9d, r9d; TokenInformationLength
0x18008eef9  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18008eefe  xor     r8d, r8d; TokenInformation
0x18008ef01  lea     edx, [rsi+1]; TokenInformationClass
0x18008ef04  mov     edi, esi
0x18008ef06  call    cs:__imp_GetTokenInformation
0x18008ef0c  test    eax, eax
0x18008ef0e  jnz     loc_18008F0B1
0x18008ef14  call    cs:__imp_GetLastError
0x18008ef1a  cmp     eax, 7Ah ; 'z'
0x18008ef1d  jnz     loc_18008F0B1
0x18008ef23  mov     ecx, [rbp+TokenInformationLength]
0x18008ef26  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008ef2c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18008ef30  lea     edx, [rsi+1]; TokenInformationClass
0x18008ef33  mov     rdi, rax
0x18008ef36  mov     rcx, rbx; TokenHandle
0x18008ef39  lea     rax, [rbp+TokenInformationLength]
0x18008ef3d  mov     r8, rdi; TokenInformation
0x18008ef40  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18008ef45  call    cs:__imp_GetTokenInformation
0x18008ef4b  test    eax, eax
0x18008ef4d  jz      loc_18008F0B1
0x18008ef53  test    rdi, rdi
0x18008ef56  jz      loc_18008F0B1
0x18008ef5c  mov     rcx, [rdi]; Sid
0x18008ef5f  lea     rax, [rbp+var_C]
0x18008ef63  mov     [rsp+40h+peUse], rax; peUse
0x18008ef68  lea     r8, [rbp+cchName]; cchName
0x18008ef6c  lea     rax, [rbp+cchReferencedDomainName]
0x18008ef70  mov     [rbp+var_C], esi
0x18008ef73  xor     r9d, r9d; ReferencedDomainName
0x18008ef76  mov     [rsp+40h+ReturnLength], rax; cchReferencedDomainName
0x18008ef7b  xor     edx, edx; Name
0x18008ef7d  mov     [rbp+cchReferencedDomainName], esi
0x18008ef80  mov     [rbp+cchName], esi
0x18008ef83  call    cs:__imp_LookupAccountSidLocalW
0x18008ef89  test    eax, eax
0x18008ef8b  jnz     loc_18008F0AA
0x18008ef91  call    cs:__imp_GetLastError
0x18008ef97  cmp     eax, 7Ah ; 'z'
0x18008ef9a  jz      short loc_18008EFAD
0x18008ef9c  sub     eax, 534h
0x18008efa1  neg     eax
0x18008efa3  sbb     ebx, ebx
0x18008efa5  add     ebx, r14d
0x18008efa8  jmp     loc_18008F0C1
0x18008efad  mov     ecx, [rbp+cchName]
0x18008efb0  mov     eax, 2
0x18008efb5  mul     rcx
0x18008efb8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008efbf  cmovb   rax, rbx
0x18008efc3  mov     rcx, rax
0x18008efc6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008efcc  mov     r15, rax
0x18008efcf  test    rax, rax
0x18008efd2  jz      loc_18008F0A3
0x18008efd8  mov     ecx, [rbp+cchReferencedDomainName]
0x18008efdb  lea     eax, [rbx+3]
0x18008efde  mul     rcx
0x18008efe1  cmovb   rax, rbx
0x18008efe5  mov     rcx, rax
0x18008efe8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008efee  mov     r14, rax
0x18008eff1  test    rax, rax
0x18008eff4  jz      loc_18008F08D
0x18008effa  mov     rcx, [rdi]; Sid
0x18008effd  lea     rax, [rbp+var_C]
0x18008f001  mov     [rsp+40h+peUse], rax; peUse
0x18008f006  lea     r8, [rbp+cchName]; cchName
0x18008f00a  lea     rax, [rbp+cchReferencedDomainName]
0x18008f00e  mov     r9, r14; ReferencedDomainName
0x18008f011  mov     rdx, r15; Name
0x18008f014  mov     [rsp+40h+ReturnLength], rax; cchReferencedDomainName
0x18008f019  call    cs:__imp_LookupAccountSidLocalW
0x18008f01f  test    eax, eax
0x18008f021  jz      short loc_18008F06D
0x18008f023  mov     rax, rbx
0x18008f026  inc     rax
0x18008f029  cmp     [r14+rax*2], si
0x18008f02e  jnz     short loc_18008F026
0x18008f030  inc     rbx
0x18008f033  cmp     [r15+rbx*2], si
0x18008f038  jnz     short loc_18008F030
0x18008f03a  lea     esi, [rbx+2]
0x18008f03d  add     esi, eax
0x18008f03f  cmp     [r12], esi
0x18008f043  jb      short loc_18008F062
0x18008f045  xor     ebx, ebx
0x18008f047  mov     edx, esi; unsigned __int64
0x18008f049  mov     r9, r14
0x18008f04c  mov     [rsp+40h+ReturnLength], r15
0x18008f051  lea     r8, aSS; "%s\\%s"
0x18008f058  mov     rcx, r13; unsigned __int16 *
0x18008f05b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008f060  jmp     short loc_18008F067
0x18008f062  mov     ebx, 8004103Ch
0x18008f067  mov     [r12], esi
0x18008f06b  jmp     short loc_18008F082
0x18008f06d  call    cs:__imp_GetLastError
0x18008f073  sub     eax, 534h
0x18008f078  neg     eax
0x18008f07a  sbb     ebx, ebx
0x18008f07c  add     ebx, 80041002h
0x18008f082  mov     rcx, r14
0x18008f085  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18008f08b  jmp     short loc_18008F092
0x18008f08d  mov     ebx, 80041006h
0x18008f092  mov     rcx, r15
0x18008f095  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18008f09b  mov     r14d, 80041002h
0x18008f0a1  jmp     short loc_18008F0C1
0x18008f0a3  mov     ebx, 80041006h
0x18008f0a8  jmp     short loc_18008F0C1
0x18008f0aa  mov     ebx, 8004101Dh
0x18008f0af  jmp     short loc_18008F0C1
0x18008f0b1  call    cs:__imp_GetLastError
0x18008f0b7  mov     ebx, 80041001h
0x18008f0bc  test    rdi, rdi
0x18008f0bf  jz      short loc_18008F0D1
0x18008f0c1  mov     rcx, rdi
0x18008f0c4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18008f0ca  jmp     short loc_18008F0D1
0x18008f0cc  mov     ebx, 80041008h
0x18008f0d1  cmp     ebx, r14d
0x18008f0d4  jnz     short loc_18008F0DB
0x18008f0d6  mov     eax, r14d
0x18008f0d9  jmp     short loc_18008F130
0x18008f0db  test    ebx, ebx
0x18008f0dd  jns     short loc_18008F0F7
0x18008f0df  jmp     short loc_18008F0E6
0x18008f0e1  mov     ebx, 80070006h
0x18008f0e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008f0ec  mov     rcx, rax
0x18008f0ef  mov     edx, ebx
0x18008f0f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008f0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f0fe  lea     rax, WPP_GLOBAL_Control
0x18008f105  cmp     rcx, rax
0x18008f108  jz      short loc_18008F12E
0x18008f10a  test    byte ptr [rcx+1Ch], 1
0x18008f10e  jz      short loc_18008F12E
0x18008f110  cmp     byte ptr [rcx+19h], 2
0x18008f114  jb      short loc_18008F12E
0x18008f116  mov     rcx, [rcx+10h]
0x18008f11a  lea     r8, WPP_a3414c62bfc43c14b650084b64f85981_Traceguids
0x18008f121  mov     edx, 0Dh
0x18008f126  mov     r9d, ebx
0x18008f129  call    WPP_SF_d
0x18008f12e  mov     eax, ebx
0x18008f130  mov     rbx, [rsp+40h+arg_8]
0x18008f138  add     rsp, 40h
0x18008f13c  pop     r15
0x18008f13e  pop     r14
0x18008f140  pop     r13
0x18008f142  pop     r12
0x18008f144  pop     rdi
0x18008f145  pop     rsi
0x18008f146  pop     rbp
0x18008f147  retn
```
