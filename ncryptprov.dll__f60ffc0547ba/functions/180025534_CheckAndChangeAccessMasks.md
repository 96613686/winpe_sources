# CheckAndChangeAccessMasks

- ea: `0x180025534`
- end: `0x180025691`
- name: `CheckAndChangeAccessMasks`
- size: `349`
- prototype: `__int64 __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004f8c`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180025534`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025649`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800255f2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800255f2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025570`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025570`

## string_xrefs

- `0x1800255b3`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18002565b`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall CheckAndChangeAccessMasks(PACL pAcl)
{
  int v2; // edx
  DWORD LastError; // ebx
  DWORD i; // ebx
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // eax
  LPVOID pAce; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h] BYREF
  int v11; // [rsp+50h] [rbp-18h]

  pAce = 0;
  v10 = 0;
  v11 = 0;
  if ( GetAclInformation(pAcl, &v10, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)v10; ++i )
    {
      if ( !GetAce(pAcl, i, &pAce) )
      {
        LastError = GetLastError();
        DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4611);
        return LastError;
      }
      v5 = pAce;
      v6 = *((_DWORD *)pAce + 1);
      if ( (v6 & 1) != 0 )
      {
        *((_DWORD *)pAce + 1) = v6 | 0x80000000;
        v5 = pAce;
      }
      v7 = v5[1];
      if ( (v7 & 2) != 0 )
      {
        v5[1] = v7 | 0x40000000;
        v5 = pAce;
      }
      if ( (v5[1] & 0x1F01FF) == 0x1F01FF )
        v5[1] |= 0x10000000u;
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        (unsigned int)"dwReturn",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        249);
  }
  return LastError;
}

```

## disassembly

```asm
0x180025534  mov     r11, rsp
0x180025537  mov     [r11+10h], rbx
0x18002553b  push    rdi
0x18002553c  sub     rsp, 60h
0x180025540  mov     rax, cs:__security_cookie
0x180025547  xor     rax, rsp
0x18002554a  mov     [rsp+68h+var_10], rax
0x18002554f  xor     eax, eax
0x180025551  mov     qword ptr [r11-28h], 0
0x180025559  mov     [r11-20h], rax
0x18002555d  lea     rdx, [r11-20h]; pAclInformation
0x180025561  mov     rdi, rcx
0x180025564  mov     [rsp+68h+var_18], eax
0x180025568  lea     r9d, [rax+2]; dwAclInformationClass
0x18002556c  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180025570  call    cs:__imp_GetAclInformation
0x180025577  nop     dword ptr [rax+rax+00h]
0x18002557c  test    eax, eax
0x18002557e  jnz     short loc_1800255DC
0x180025580  call    cs:__imp_GetLastError
0x180025587  nop     dword ptr [rax+rax+00h]
0x18002558c  mov     ebx, eax
0x18002558e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025595  lea     rax, WPP_GLOBAL_Control
0x18002559c  cmp     rcx, rax
0x18002559f  jz      loc_180025676
0x1800255a5  test    byte ptr [rcx+1Ch], 1
0x1800255a9  jz      loc_180025676
0x1800255af  mov     rcx, [rcx+10h]
0x1800255b3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800255ba  mov     [rsp+68h+var_38], 11F9h
0x1800255c2  lea     r9, aDwreturn; "dwReturn"
0x1800255c9  mov     [rsp+68h+var_40], r8
0x1800255ce  mov     [rsp+68h+var_48], ebx
0x1800255d2  call    WPP_SF_sDsd
0x1800255d7  jmp     loc_180025676
0x1800255dc  xor     ebx, ebx
0x1800255de  cmp     ebx, dword ptr [rsp+68h+var_20]
0x1800255e2  jnb     loc_180025674
0x1800255e8  lea     r8, [rsp+68h+pAce]; pAce
0x1800255ed  mov     edx, ebx; dwAceIndex
0x1800255ef  mov     rcx, rdi; pAcl
0x1800255f2  call    cs:__imp_GetAce
0x1800255f9  nop     dword ptr [rax+rax+00h]
0x1800255fe  test    eax, eax
0x180025600  jz      short loc_180025649
0x180025602  mov     rcx, [rsp+68h+pAce]
0x180025607  mov     eax, [rcx+4]
0x18002560a  test    al, 1
0x18002560c  jz      short loc_18002561A
0x18002560e  bts     eax, 1Fh
0x180025612  mov     [rcx+4], eax
0x180025615  mov     rcx, [rsp+68h+pAce]
0x18002561a  mov     eax, [rcx+4]
0x18002561d  test    al, 2
0x18002561f  jz      short loc_18002562D
0x180025621  bts     eax, 1Eh
0x180025625  mov     [rcx+4], eax
0x180025628  mov     rcx, [rsp+68h+pAce]
0x18002562d  mov     edx, [rcx+4]
0x180025630  mov     eax, edx
0x180025632  and     eax, 1F01FFh
0x180025637  cmp     eax, 1F01FFh
0x18002563c  jnz     short loc_180025645
0x18002563e  bts     edx, 1Ch
0x180025642  mov     [rcx+4], edx
0x180025645  inc     ebx
0x180025647  jmp     short loc_1800255DE
0x180025649  call    cs:__imp_GetLastError
0x180025650  nop     dword ptr [rax+rax+00h]
0x180025655  mov     r9d, 1203h
0x18002565b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180025662  mov     ecx, eax
0x180025664  lea     rdx, aDwreturn; "dwReturn"
0x18002566b  mov     ebx, eax
0x18002566d  call    DebugTraceError
0x180025672  jmp     short loc_180025676
0x180025674  xor     ebx, ebx
0x180025676  mov     eax, ebx
0x180025678  mov     rcx, [rsp+68h+var_10]
0x18002567d  xor     rcx, rsp; StackCookie
0x180025680  call    __security_check_cookie
0x180025685  mov     rbx, [rsp+68h+arg_8]
0x18002568a  add     rsp, 60h
0x18002568e  pop     rdi
0x18002568f  retn
```
