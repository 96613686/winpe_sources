# Int_FwValidateAndMigrateSecurityDescriptor

- ea: `0x18000cdf0`
- end: `0x18000d2c6`
- name: `Int_FwValidateAndMigrateSecurityDescriptor`
- size: `1238`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cd30`
- `0x18000d490`

## callees

- `0x18000ccd4`
- `0x18000cdf0`
- `0x180011d38`
- `0x180017d1c`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d269`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ceef`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ceef`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000ce90`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000ce90`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000ceae`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000ceae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf4e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ce75`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ce75`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000d25b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000d25b`

## pseudocode

```c
__int64 __fastcall Int_FwValidateAndMigrateSecurityDescriptor(LPCWSTR StringSecurityDescriptor, int a2, LPWSTR *a3)
{
  PACL v6; // rcx
  DWORD v7; // ebx
  int v8; // esi
  DWORD i; // r14d
  char v10; // al
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-20h] BYREF
  WINBOOL bDaclPresent; // [rsp+48h] [rbp-18h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+4Ch] [rbp-14h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  SecurityDescriptor = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAce = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    v14 = 280;
LABEL_29:
    v15 = LastError;
    goto LABEL_65;
  }
  if ( !SecurityDescriptor )
  {
    v7 = 1450;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v14 = 293;
    v15 = 1450;
LABEL_65:
    WPP_SF_d(v13[2], v14, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v15);
    goto LABEL_21;
  }
  if ( !IsValidSecurityDescriptor(SecurityDescriptor) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    v14 = 281;
    goto LABEL_29;
  }
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    v14 = 282;
    goto LABEL_29;
  }
  if ( !bDaclPresent )
  {
    v15 = 87;
    v7 = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    v14 = 283;
    goto LABEL_65;
  }
  v6 = pDacl;
  if ( !a3 && !pDacl )
  {
    v15 = 87;
    v7 = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    v14 = 284;
    goto LABEL_65;
  }
  v7 = 0;
  v8 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v6->AceCount )
    {
      if ( a3 )
      {
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(SecurityDescriptor, 1u, 0xFu, a3, 0) )
          goto LABEL_21;
        v7 = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_21;
        v14 = 292;
        goto LABEL_66;
      }
      if ( v8 )
      {
        if ( a2 )
          goto LABEL_21;
      }
      else if ( !a2 )
      {
        goto LABEL_21;
      }
      v15 = 87;
      v7 = 87;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v14 = 291;
      goto LABEL_65;
    }
    if ( !GetAce(v6, i, &pAce) )
    {
      v7 = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v14 = 285;
      goto LABEL_66;
    }
    v10 = *(_BYTE *)pAce;
    if ( !*(_BYTE *)pAce )
      break;
    if ( v10 != 1 )
    {
      if ( v10 == 9 )
      {
        v7 = Int_FwValidateAndMigateAccessMask(a3 != 0, (unsigned int *)pAce + 1);
        if ( v7 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_21;
          v14 = 288;
          goto LABEL_66;
        }
      }
      else
      {
        if ( v10 != 10 )
        {
          if ( !a3 )
          {
            v15 = 87;
            v7 = 87;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v14 = 290;
              goto LABEL_65;
            }
            goto LABEL_21;
          }
          goto LABEL_16;
        }
        v7 = Int_FwValidateAndMigateAccessMask(a3 != 0, (unsigned int *)pAce + 1);
        if ( v7 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_21;
          v14 = 289;
          goto LABEL_66;
        }
      }
      v8 = 1;
      goto LABEL_16;
    }
    v7 = Int_FwValidateAndMigateAccessMask(a3 != 0, (unsigned int *)pAce + 1);
    if ( v7 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v14 = 287;
LABEL_66:
      v15 = v7;
      goto LABEL_65;
    }
LABEL_16:
    v6 = pDacl;
  }
  if ( a3 )
  {
    *((_DWORD *)pAce + 1) = 1;
    goto LABEL_15;
  }
  if ( *((_DWORD *)pAce + 1) == 1 )
  {
LABEL_15:
    v7 = 0;
    goto LABEL_16;
  }
  v15 = 87;
  v7 = 87;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 286;
    goto LABEL_65;
  }
LABEL_21:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x18000cdf0  mov     [rsp-28h+arg_8], rbx
0x18000cdf5  mov     [rsp-28h+arg_18], rsi
0x18000cdfa  push    rbp
0x18000cdfb  push    rdi
0x18000cdfc  push    r13
0x18000cdfe  push    r14
0x18000ce00  push    r15
0x18000ce02  mov     rbp, rsp
0x18000ce05  sub     rsp, 60h
0x18000ce09  mov     rax, cs:__security_cookie
0x18000ce10  xor     rax, rsp
0x18000ce13  mov     [rbp+var_10], rax
0x18000ce17  mov     rdi, r8
0x18000ce1a  mov     r15d, edx
0x18000ce1d  mov     rbx, rcx
0x18000ce20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce27  lea     rsi, WPP_GLOBAL_Control
0x18000ce2e  lea     r14, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000ce35  cmp     rcx, rsi
0x18000ce38  jnz     loc_18000CF7B
0x18000ce3e  xor     r9d, r9d; SecurityDescriptorSize
0x18000ce41  mov     [rbp+SecurityDescriptor], 0
0x18000ce49  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000ce4d  mov     [rbp+pDacl], 0
0x18000ce55  mov     rcx, rbx; StringSecurityDescriptor
0x18000ce58  mov     [rbp+bDaclPresent], 0
0x18000ce5f  mov     [rbp+bDaclDefaulted], 0
0x18000ce66  lea     r13d, [r9+1]
0x18000ce6a  mov     [rbp+pAce], 0
0x18000ce72  mov     edx, r13d; StringSDRevision
0x18000ce75  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000ce7b  test    eax, eax
0x18000ce7d  jz      loc_18000CFEB
0x18000ce83  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18000ce87  test    rcx, rcx
0x18000ce8a  jz      loc_18000D297
0x18000ce90  call    cs:__imp_IsValidSecurityDescriptor
0x18000ce96  test    eax, eax
0x18000ce98  jz      loc_18000CFC2
0x18000ce9e  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18000cea2  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000cea6  lea     r8, [rbp+pDacl]; pDacl
0x18000ceaa  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000ceae  call    cs:__imp_GetSecurityDescriptorDacl
0x18000ceb4  test    eax, eax
0x18000ceb6  jz      loc_18000CF9B
0x18000cebc  cmp     [rbp+bDaclPresent], 0
0x18000cec0  jz      loc_18000D014
0x18000cec6  mov     rcx, [rbp+pDacl]; pAcl
0x18000ceca  test    rdi, rdi
0x18000cecd  jnz     short loc_18000CED8
0x18000cecf  test    rcx, rcx
0x18000ced2  jz      loc_18000D041
0x18000ced8  xor     ebx, ebx
0x18000ceda  xor     esi, esi
0x18000cedc  xor     r14d, r14d
0x18000cedf  movzx   eax, word ptr [rcx+4]
0x18000cee3  cmp     r14d, eax
0x18000cee6  jnb     short loc_18000CF2B
0x18000cee8  lea     r8, [rbp+pAce]; pAce
0x18000ceec  mov     edx, r14d; dwAceIndex
0x18000ceef  call    cs:__imp_GetAce
0x18000cef5  test    eax, eax
0x18000cef7  jz      loc_18000D1DA
0x18000cefd  mov     rdx, [rbp+pAce]
0x18000cf01  mov     al, [rdx]
0x18000cf03  test    al, al
0x18000cf05  jnz     loc_18000D06E
0x18000cf0b  test    rdi, rdi
0x18000cf0e  jnz     short loc_18000CF25
0x18000cf10  cmp     [rdx+4], r13d
0x18000cf14  jnz     loc_18000D185
0x18000cf1a  xor     ebx, ebx
0x18000cf1c  mov     rcx, [rbp+pDacl]
0x18000cf20  add     r14d, r13d
0x18000cf23  jmp     short loc_18000CEDF
0x18000cf25  mov     [rdx+4], r13d
0x18000cf29  jmp     short loc_18000CF1A
0x18000cf2b  test    rdi, rdi
0x18000cf2e  jnz     loc_18000D242
0x18000cf34  test    esi, esi
0x18000cf36  jnz     loc_18000D20A
0x18000cf3c  test    r15d, r15d
0x18000cf3f  jnz     loc_18000D213
0x18000cf45  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000cf49  test    rcx, rcx
0x18000cf4c  jz      short loc_18000CF54
0x18000cf4e  call    cs:__imp_LocalFree
0x18000cf54  mov     eax, ebx
0x18000cf56  mov     rcx, [rbp+var_10]
0x18000cf5a  xor     rcx, rsp; StackCookie
0x18000cf5d  call    __security_check_cookie
0x18000cf62  lea     r11, [rsp+60h+var_s0]
0x18000cf67  mov     rbx, [r11+38h]
0x18000cf6b  mov     rsi, [r11+48h]
0x18000cf6f  mov     rsp, r11
0x18000cf72  pop     r15
0x18000cf74  pop     r14
0x18000cf76  pop     r13
0x18000cf78  pop     rdi
0x18000cf79  pop     rbp
0x18000cf7a  retn
0x18000cf7b  test    byte ptr [rcx+1Ch], 8
0x18000cf7f  jz      loc_18000CE3E
0x18000cf85  mov     rcx, [rcx+10h]
0x18000cf89  mov     edx, 117h
0x18000cf8e  mov     r8, r14
0x18000cf91  call    WPP_SF_
0x18000cf96  jmp     loc_18000CE3E
0x18000cf9b  call    cs:__imp_GetLastError
0x18000cfa1  mov     ebx, eax
0x18000cfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfaa  cmp     rcx, rsi
0x18000cfad  jz      short loc_18000CF45
0x18000cfaf  test    [rcx+1Ch], r13b
0x18000cfb3  jz      short loc_18000CF45
0x18000cfb5  mov     edx, 11Ah
0x18000cfba  mov     r9d, eax
0x18000cfbd  jmp     loc_18000D2BE
0x18000cfc2  call    cs:__imp_GetLastError
0x18000cfc8  mov     ebx, eax
0x18000cfca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd1  cmp     rcx, rsi
0x18000cfd4  jz      loc_18000CF45
0x18000cfda  test    [rcx+1Ch], r13b
0x18000cfde  jz      loc_18000CF45
0x18000cfe4  mov     edx, 119h
0x18000cfe9  jmp     short loc_18000CFBA
0x18000cfeb  call    cs:__imp_GetLastError
0x18000cff1  mov     ebx, eax
0x18000cff3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cffa  cmp     rcx, rsi
0x18000cffd  jz      loc_18000CF45
0x18000d003  test    [rcx+1Ch], r13b
0x18000d007  jz      loc_18000CF45
0x18000d00d  mov     edx, 118h
0x18000d012  jmp     short loc_18000CFBA
0x18000d014  mov     r9d, 57h ; 'W'
0x18000d01a  mov     ebx, r9d
0x18000d01d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d024  cmp     rcx, rsi
0x18000d027  jz      loc_18000CF45
0x18000d02d  test    [rcx+1Ch], r13b
0x18000d031  jz      loc_18000CF45
0x18000d037  mov     edx, 11Bh
0x18000d03c  jmp     loc_18000D2BE
0x18000d041  mov     r9d, 57h ; 'W'
0x18000d047  mov     ebx, r9d
0x18000d04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d051  cmp     rcx, rsi
0x18000d054  jz      loc_18000CF45
0x18000d05a  test    [rcx+1Ch], r13b
0x18000d05e  jz      loc_18000CF45
0x18000d064  mov     edx, 11Ch
0x18000d069  jmp     loc_18000D2BE
0x18000d06e  cmp     al, r13b
0x18000d071  jnz     short loc_18000D0B9
0x18000d073  xor     ecx, ecx
0x18000d075  add     rdx, 4; unsigned int *
0x18000d079  test    rdi, rdi
0x18000d07c  setnz   cl; int
0x18000d07f  call    ?Int_FwValidateAndMigateAccessMask@@YAKHPEAK@Z; Int_FwValidateAndMigateAccessMask(int,ulong *)
0x18000d084  mov     ebx, eax
0x18000d086  test    eax, eax
0x18000d088  jz      loc_18000CF1C
0x18000d08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d095  lea     rax, WPP_GLOBAL_Control
0x18000d09c  cmp     rcx, rax
0x18000d09f  jz      loc_18000CF45
0x18000d0a5  test    [rcx+1Ch], r13b
0x18000d0a9  jz      loc_18000CF45
0x18000d0af  mov     edx, 11Fh
0x18000d0b4  jmp     loc_18000D1D5
0x18000d0b9  cmp     al, 9
0x18000d0bb  jnz     short loc_18000D0FF
0x18000d0bd  xor     ecx, ecx
0x18000d0bf  add     rdx, 4; unsigned int *
0x18000d0c3  test    rdi, rdi
0x18000d0c6  setnz   cl; int
0x18000d0c9  call    ?Int_FwValidateAndMigateAccessMask@@YAKHPEAK@Z; Int_FwValidateAndMigateAccessMask(int,ulong *)
0x18000d0ce  mov     ebx, eax
0x18000d0d0  test    eax, eax
0x18000d0d2  jz      short loc_18000D145
0x18000d0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0db  lea     rax, WPP_GLOBAL_Control
0x18000d0e2  cmp     rcx, rax
0x18000d0e5  jz      loc_18000CF45
0x18000d0eb  test    [rcx+1Ch], r13b
0x18000d0ef  jz      loc_18000CF45
0x18000d0f5  mov     edx, 120h
0x18000d0fa  jmp     loc_18000D1D5
0x18000d0ff  cmp     al, 0Ah
0x18000d101  jnz     short loc_18000D14D
0x18000d103  xor     ecx, ecx
0x18000d105  add     rdx, 4; unsigned int *
0x18000d109  test    rdi, rdi
0x18000d10c  setnz   cl; int
0x18000d10f  call    ?Int_FwValidateAndMigateAccessMask@@YAKHPEAK@Z; Int_FwValidateAndMigateAccessMask(int,ulong *)
0x18000d114  mov     ebx, eax
0x18000d116  test    eax, eax
0x18000d118  jz      short loc_18000D145
0x18000d11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d121  lea     rax, WPP_GLOBAL_Control
0x18000d128  cmp     rcx, rax
0x18000d12b  jz      loc_18000CF45
0x18000d131  test    [rcx+1Ch], r13b
0x18000d135  jz      loc_18000CF45
0x18000d13b  mov     edx, 121h
0x18000d140  jmp     loc_18000D1D5
0x18000d145  mov     esi, r13d
0x18000d148  jmp     loc_18000CF1C
0x18000d14d  test    rdi, rdi
0x18000d150  jnz     loc_18000CF1C
0x18000d156  lea     r9d, [rdi+57h]
0x18000d15a  mov     ebx, r9d
0x18000d15d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d164  lea     rax, WPP_GLOBAL_Control
0x18000d16b  cmp     rcx, rax
0x18000d16e  jz      loc_18000CF45
0x18000d174  test    [rcx+1Ch], r13b
0x18000d178  jz      loc_18000CF45
0x18000d17e  mov     edx, 122h
0x18000d183  jmp     short loc_18000D1BB
0x18000d185  mov     r9d, 57h ; 'W'
0x18000d18b  mov     ebx, r9d
0x18000d18e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d195  lea     rax, WPP_GLOBAL_Control
0x18000d19c  cmp     rcx, rax
0x18000d19f  jz      loc_18000CF45
0x18000d1a5  test    [rcx+1Ch], r13b
0x18000d1a9  jz      loc_18000CF45
0x18000d1af  mov     edx, 11Eh
0x18000d1b4  jmp     short loc_18000D1BB
0x18000d1b6  mov     edx, 123h
0x18000d1bb  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000d1c2  mov     rcx, [rcx+10h]
0x18000d1c6  call    WPP_SF_d
0x18000d1cb  jmp     loc_18000CF45
0x18000d1d0  mov     edx, 124h
0x18000d1d5  mov     r9d, ebx
0x18000d1d8  jmp     short loc_18000D1BB
0x18000d1da  call    cs:__imp_GetLastError
0x18000d1e0  mov     ebx, eax
0x18000d1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1e9  lea     rax, WPP_GLOBAL_Control
0x18000d1f0  cmp     rcx, rax
0x18000d1f3  jz      loc_18000CF45
0x18000d1f9  test    [rcx+1Ch], r13b
0x18000d1fd  jz      loc_18000CF45
0x18000d203  mov     edx, 11Dh
0x18000d208  jmp     short loc_18000D1D5
0x18000d20a  test    r15d, r15d
0x18000d20d  jnz     loc_18000CF45
0x18000d213  mov     r9d, 57h ; 'W'
0x18000d219  mov     ebx, r9d
0x18000d21c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d223  lea     rax, WPP_GLOBAL_Control
0x18000d22a  cmp     rcx, rax
0x18000d22d  jz      loc_18000CF45
0x18000d233  test    [rcx+1Ch], r13b
0x18000d237  jz      loc_18000CF45
0x18000d23d  jmp     loc_18000D1B6
0x18000d242  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000d246  mov     r9, rdi; StringSecurityDescriptor
0x18000d249  mov     r8d, 0Fh; SecurityInformation
0x18000d24f  mov     [rsp+60h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x18000d258  mov     edx, r13d; RequestedStringSDRevision
0x18000d25b  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000d261  test    eax, eax
0x18000d263  jnz     loc_18000CF45
0x18000d269  call    cs:__imp_GetLastError
0x18000d26f  mov     ebx, eax
0x18000d271  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d278  lea     rax, WPP_GLOBAL_Control
0x18000d27f  cmp     rcx, rax
0x18000d282  jz      loc_18000CF45
0x18000d288  test    [rcx+1Ch], r13b
0x18000d28c  jz      loc_18000CF45
0x18000d292  jmp     loc_18000D1D0
0x18000d297  mov     ebx, 5AAh
0x18000d29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a3  cmp     rcx, rsi
0x18000d2a6  jz      loc_18000CF54
0x18000d2ac  test    [rcx+1Ch], r13b
0x18000d2b0  jz      loc_18000CF54
0x18000d2b6  mov     edx, 125h
0x18000d2bb  mov     r9d, ebx
0x18000d2be  mov     r8, r14
0x18000d2c1  jmp     loc_18000D1C2
```
