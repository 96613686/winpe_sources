# IsAttrStrValid(int,ushort const *,unsigned __int64)

- ea: `0x1004e8cc8`
- end: `0x1004e90a4`
- name: `?IsAttrStrValid@@YAHHPEBG_K@Z`
- size: `988`
- prototype: `int(int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1004e9708`
- `0x1005172d0`

## callees

- `0x1004076ac`
- `0x1004e8cc8`
- `0x1004e90ac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x1004e8e93`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x1004e8e93`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d40`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d5e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d7c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d9a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8dd4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8dec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8e04`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8e4d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8f3e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8fbc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8ffb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9019`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9033`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e904d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9067`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9081`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d40`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d5e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d7c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8d9a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8dd4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8dec`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8e04`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8e4d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8f3e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8fbc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e8ffb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9019`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9033`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e904d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9067`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e9081`

## string_xrefs

- `0x1004e8ff1`: `ActiveDirectoryIntegrated`
- `0x1004e900f`: `ActiveDirectoryPassword`
- `0x1004e9029`: `ActiveDirectoryInteractive`
- `0x1004e905d`: `ActiveDirectoryMSI`
- `0x1004e9077`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall IsAttrStrValid(int a1, wchar_t *a2, size_t a3)
{
  wint_t *v4; // rsi
  unsigned int v5; // ebp
  bool v6; // zf
  const wchar_t *v7; // rdx
  __int64 v8; // rcx
  unsigned int v10; // [rsp+20h] [rbp-18h]
  unsigned int v11; // [rsp+28h] [rbp-10h]

  v4 = a2;
  v5 = 1;
  if ( a1 <= 26 )
  {
    if ( a1 != 26 )
    {
      if ( a1 > 17 )
      {
        switch ( a1 )
        {
          case 19:
          case 20:
            goto LABEL_31;
          case 22:
            if ( a3 <= 5 )
            {
              while ( *v4 )
              {
                if ( !iswdigit(*v4) )
                  return 0;
                ++v4;
              }
              return v5;
            }
            return 0;
          case 23:
            goto LABEL_31;
        }
        v6 = a1 == 25;
LABEL_30:
        if ( v6 )
          goto LABEL_31;
LABEL_61:
        v8 = 88LL * a1;
        if ( *(_DWORD *)&x_rgLookup[v8 + 68] && a3 > *(unsigned int *)&x_rgLookup[v8 + 68] )
          return 0;
        return v5;
      }
      if ( a1 != 17 )
      {
        if ( a1 == 4 )
          return v5;
        if ( a1 != 8 )
        {
          if ( a1 == 13 )
          {
            if ( a3 == 8 )
            {
              if ( !_wcsicmp(a2, L"DBNMPNTW") || !_wcsicmp(v4, L"DBMSSOCN") || !_wcsicmp(v4, L"DBMSLPCN") )
                return v5;
              v7 = L"DBNETLIB";
              goto LABEL_81;
            }
            return 0;
          }
          if ( a1 == 15 )
          {
            if ( a3 == 3 && !_wcsicmp(a2, L"Yes")
              || a3 == 9 && !_wcsicmp(v4, L"Mandatory")
              || a3 == 2 && !_wcsicmp(v4, L"No")
              || a3 == 8 && !_wcsicmp(v4, L"Optional") )
            {
              return v5;
            }
            if ( a3 == 6 )
            {
              v7 = L"Strict";
              goto LABEL_81;
            }
            return 0;
          }
          v6 = a1 == 16;
          goto LABEL_30;
        }
      }
    }
LABEL_31:
    if ( a3 == 3 && !_wcsicmp(a2, L"Yes") )
      return v5;
    if ( a3 == 2 )
    {
      v7 = L"No";
      goto LABEL_81;
    }
    return 0;
  }
  if ( a1 > 37 )
  {
    switch ( a1 )
    {
      case '&':
        if ( !a3
          || a3 == 25 && !_wcsicmp(a2, L"ActiveDirectoryIntegrated")
          || a3 == 23 && !_wcsicmp(v4, L"ActiveDirectoryPassword")
          || a3 == 26 && !_wcsicmp(v4, L"ActiveDirectoryInteractive")
          || a3 == 11 && !_wcsicmp(v4, L"SqlPassword")
          || a3 == 18 && !_wcsicmp(v4, L"ActiveDirectoryMSI") )
        {
          return v5;
        }
        if ( a3 != 31 )
          return 0;
        v7 = L"ActiveDirectoryServicePrincipal";
        break;
      case '+':
      case '6':
        goto LABEL_31;
      case '8':
        if ( a3 == 3 && !_wcsicmp(a2, L"off") )
          return v5;
        if ( a3 != 2 )
          return 0;
        v7 = L"v1";
        break;
      default:
        goto LABEL_61;
    }
  }
  else
  {
    if ( a1 != 37 )
    {
      if ( a1 != 27 )
      {
        if ( a1 == 31 )
        {
          if ( !(unsigned int)FIsValidApplicationIntentString(a2, a3) )
            return 0;
          return v5;
        }
        if ( a1 != 32 )
        {
          if ( a1 == 33 )
          {
            v11 = 255;
            v10 = 0;
          }
          else
          {
            if ( a1 != 34 )
              goto LABEL_61;
            v11 = 60;
            v10 = 1;
          }
          _mm_lfence();
          return (unsigned int)IsValidNumericKey(a1, a2, a3, 1, v10, v11);
        }
      }
      goto LABEL_31;
    }
    if ( a3 == 7 && !_wcsicmp(a2, L"Enabled") )
      return v5;
    if ( a3 != 8 )
      return 0;
    v7 = L"Disabled";
  }
LABEL_81:
  if ( _wcsicmp(v4, v7) )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x1004e8cc8  mov     [rsp+arg_0], rbx
0x1004e8ccd  mov     [rsp+arg_8], rbp
0x1004e8cd2  mov     [rsp+arg_10], rsi
0x1004e8cd7  push    rdi
0x1004e8cd8  sub     rsp, 30h
0x1004e8cdc  mov     rdi, r8
0x1004e8cdf  mov     rsi, rdx
0x1004e8ce2  mov     ebp, 1
0x1004e8ce7  cmp     ecx, 1Ah
0x1004e8cea  jg      loc_1004E8EB2
0x1004e8cf0  jz      loc_1004E8E3B
0x1004e8cf6  cmp     ecx, 11h
0x1004e8cf9  jg      loc_1004E8E1E
0x1004e8cff  jz      loc_1004E8E3B
0x1004e8d05  mov     edx, ecx
0x1004e8d07  sub     edx, 4
0x1004e8d0a  jz      loc_1004E908D
0x1004e8d10  sub     edx, 4
0x1004e8d13  jz      loc_1004E8E3B
0x1004e8d19  sub     edx, 5
0x1004e8d1c  jz      loc_1004E8DBE
0x1004e8d22  sub     edx, 2
0x1004e8d25  jz      short loc_1004E8D2E
0x1004e8d27  cmp     edx, ebp
0x1004e8d29  jmp     loc_1004E8E35
0x1004e8d2e  xor     ebx, ebx
0x1004e8d30  cmp     rdi, 3
0x1004e8d34  jnz     short loc_1004E8D4E
0x1004e8d36  lea     rdx, aYes_1; "Yes"
0x1004e8d3d  mov     rcx, rsi; String1
0x1004e8d40  call    cs:__imp__wcsicmp
0x1004e8d46  test    eax, eax
0x1004e8d48  jz      loc_1004E908D
0x1004e8d4e  cmp     rdi, 9
0x1004e8d52  jnz     short loc_1004E8D6C
0x1004e8d54  lea     rdx, aMandatory; "Mandatory"
0x1004e8d5b  mov     rcx, rsi; String1
0x1004e8d5e  call    cs:__imp__wcsicmp
0x1004e8d64  test    eax, eax
0x1004e8d66  jz      loc_1004E908D
0x1004e8d6c  cmp     rdi, 2
0x1004e8d70  jnz     short loc_1004E8D8A
0x1004e8d72  lea     rdx, aNo; "No"
0x1004e8d79  mov     rcx, rsi; String1
0x1004e8d7c  call    cs:__imp__wcsicmp
0x1004e8d82  test    eax, eax
0x1004e8d84  jz      loc_1004E908D
0x1004e8d8a  cmp     rdi, 8
0x1004e8d8e  jnz     short loc_1004E8DA8
0x1004e8d90  lea     rdx, aOptional; "Optional"
0x1004e8d97  mov     rcx, rsi; String1
0x1004e8d9a  call    cs:__imp__wcsicmp
0x1004e8da0  test    eax, eax
0x1004e8da2  jz      loc_1004E908D
0x1004e8da8  cmp     rdi, 6
0x1004e8dac  jnz     loc_1004E908B
0x1004e8db2  lea     rdx, aStrict; "Strict"
0x1004e8db9  jmp     loc_1004E907E
0x1004e8dbe  xor     ebx, ebx
0x1004e8dc0  cmp     rdi, 8
0x1004e8dc4  jnz     loc_1004E908B
0x1004e8dca  lea     rdx, aDbnmpntw; "DBNMPNTW"
0x1004e8dd1  mov     rcx, rsi; String1
0x1004e8dd4  call    cs:__imp__wcsicmp
0x1004e8dda  test    eax, eax
0x1004e8ddc  jz      loc_1004E908D
0x1004e8de2  lea     rdx, aDbmssocn; "DBMSSOCN"
0x1004e8de9  mov     rcx, rsi; String1
0x1004e8dec  call    cs:__imp__wcsicmp
0x1004e8df2  test    eax, eax
0x1004e8df4  jz      loc_1004E908D
0x1004e8dfa  lea     rdx, aDbmslpcn; "DBMSLPCN"
0x1004e8e01  mov     rcx, rsi; String1
0x1004e8e04  call    cs:__imp__wcsicmp
0x1004e8e0a  test    eax, eax
0x1004e8e0c  jz      loc_1004E908D
0x1004e8e12  lea     rdx, aDbnetlib; "DBNETLIB"
0x1004e8e19  jmp     loc_1004E907E
0x1004e8e1e  mov     edx, ecx
0x1004e8e20  sub     edx, 13h
0x1004e8e23  jz      short loc_1004E8E3B
0x1004e8e25  sub     edx, ebp
0x1004e8e27  jz      short loc_1004E8E3B
0x1004e8e29  sub     edx, 2
0x1004e8e2c  jz      short loc_1004E8E71
0x1004e8e2e  sub     edx, ebp
0x1004e8e30  jz      short loc_1004E8E3B
0x1004e8e32  cmp     edx, 2
0x1004e8e35  jnz     loc_1004E8F7E
0x1004e8e3b  xor     ebx, ebx
0x1004e8e3d  cmp     rdi, 3
0x1004e8e41  jnz     short loc_1004E8E5B
0x1004e8e43  lea     rdx, aYes_1; "Yes"
0x1004e8e4a  mov     rcx, rsi; String1
0x1004e8e4d  call    cs:__imp__wcsicmp
0x1004e8e53  test    eax, eax
0x1004e8e55  jz      loc_1004E908D
0x1004e8e5b  cmp     rdi, 2
0x1004e8e5f  jnz     loc_1004E908B
0x1004e8e65  lea     rdx, aNo; "No"
0x1004e8e6c  jmp     loc_1004E907E
0x1004e8e71  movsxd  rax, ecx
0x1004e8e74  xor     ebx, ebx
0x1004e8e76  imul    rcx, rax, 58h ; 'X'
0x1004e8e7a  lea     rax, ?x_rgLookup@@3QBU_KeyLookUp@@B; "SaveFile"
0x1004e8e81  mov     eax, [rcx+rax+44h]
0x1004e8e85  cmp     rdi, rax
0x1004e8e88  ja      loc_1004E908B
0x1004e8e8e  jmp     short loc_1004E8EA5
0x1004e8e90  movzx   ecx, ax; C
0x1004e8e93  call    cs:__imp_iswdigit
0x1004e8e99  test    eax, eax
0x1004e8e9b  jz      loc_1004E908B
0x1004e8ea1  add     rsi, 2
0x1004e8ea5  movzx   eax, word ptr [rsi]
0x1004e8ea8  test    ax, ax
0x1004e8eab  jnz     short loc_1004E8E90
0x1004e8ead  jmp     loc_1004E908D
0x1004e8eb2  cmp     ecx, 25h ; '%'
0x1004e8eb5  jg      loc_1004E8F62
0x1004e8ebb  jz      short loc_1004E8F2C
0x1004e8ebd  mov     edx, ecx
0x1004e8ebf  sub     edx, 1Bh
0x1004e8ec2  jz      loc_1004E8E3B
0x1004e8ec8  sub     edx, 4
0x1004e8ecb  jz      short loc_1004E8F12
0x1004e8ecd  sub     edx, ebp
0x1004e8ecf  jz      loc_1004E8E3B
0x1004e8ed5  sub     edx, ebp
0x1004e8ed7  jz      short loc_1004E8EEF
0x1004e8ed9  cmp     edx, ebp
0x1004e8edb  jnz     loc_1004E8F7E
0x1004e8ee1  mov     [rsp+38h+var_10], 3Ch ; '<'
0x1004e8ee9  mov     [rsp+38h+var_18], ebp
0x1004e8eed  jmp     short loc_1004E8EFD
0x1004e8eef  xor     ebx, ebx
0x1004e8ef1  mov     [rsp+38h+var_10], 0FFh; unsigned int
0x1004e8ef9  mov     [rsp+38h+var_18], ebx; unsigned int
0x1004e8efd  lfence
0x1004e8f00  mov     r9d, ebp; int
0x1004e8f03  mov     rdx, rsi; unsigned __int16 *
0x1004e8f06  call    ?IsValidNumericKey@@YAHHPEBG_KHII@Z; IsValidNumericKey(int,ushort const *,unsigned __int64,int,uint,uint)
0x1004e8f0b  mov     ebp, eax
0x1004e8f0d  jmp     loc_1004E908D
0x1004e8f12  mov     rdx, rdi; MaxCount
0x1004e8f15  mov     rcx, rsi; String1
0x1004e8f18  call    FIsValidApplicationIntentString
0x1004e8f1d  xor     ebx, ebx
0x1004e8f1f  test    eax, eax
0x1004e8f21  jnz     loc_1004E908D
0x1004e8f27  jmp     loc_1004E908B
0x1004e8f2c  xor     ebx, ebx
0x1004e8f2e  cmp     rdi, 7
0x1004e8f32  jnz     short loc_1004E8F4C
0x1004e8f34  lea     rdx, aEnabled; "Enabled"
0x1004e8f3b  mov     rcx, rsi; String1
0x1004e8f3e  call    cs:__imp__wcsicmp
0x1004e8f44  test    eax, eax
0x1004e8f46  jz      loc_1004E908D
0x1004e8f4c  cmp     rdi, 8
0x1004e8f50  jnz     loc_1004E908B
0x1004e8f56  lea     rdx, aDisabled; "Disabled"
0x1004e8f5d  jmp     loc_1004E907E
0x1004e8f62  cmp     ecx, 26h ; '&'
0x1004e8f65  jz      short loc_1004E8FE0
0x1004e8f67  cmp     ecx, 2Bh ; '+'
0x1004e8f6a  jz      loc_1004E8E3B
0x1004e8f70  cmp     ecx, 36h ; '6'
0x1004e8f73  jz      loc_1004E8E3B
0x1004e8f79  cmp     ecx, 38h ; '8'
0x1004e8f7c  jz      short loc_1004E8FAA
0x1004e8f7e  movsxd  rax, ecx
0x1004e8f81  xor     ebx, ebx
0x1004e8f83  imul    rcx, rax, 58h ; 'X'
0x1004e8f87  lea     rax, ?x_rgLookup@@3QBU_KeyLookUp@@B; "SaveFile"
0x1004e8f8e  cmp     [rcx+rax+44h], ebx
0x1004e8f92  jz      loc_1004E908D
0x1004e8f98  mov     eax, [rcx+rax+44h]
0x1004e8f9c  cmp     rdi, rax
0x1004e8f9f  jbe     loc_1004E908D
0x1004e8fa5  jmp     loc_1004E908B
0x1004e8faa  xor     ebx, ebx
0x1004e8fac  cmp     rdi, 3
0x1004e8fb0  jnz     short loc_1004E8FCA
0x1004e8fb2  lea     rdx, aOff_0; "off"
0x1004e8fb9  mov     rcx, rsi; String1
0x1004e8fbc  call    cs:__imp__wcsicmp
0x1004e8fc2  test    eax, eax
0x1004e8fc4  jz      loc_1004E908D
0x1004e8fca  cmp     rdi, 2
0x1004e8fce  jnz     loc_1004E908B
0x1004e8fd4  lea     rdx, aV1; "v1"
0x1004e8fdb  jmp     loc_1004E907E
0x1004e8fe0  xor     ebx, ebx
0x1004e8fe2  test    rdi, rdi
0x1004e8fe5  jz      loc_1004E908D
0x1004e8feb  cmp     rdi, 19h
0x1004e8fef  jnz     short loc_1004E9009
0x1004e8ff1  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x1004e8ff8  mov     rcx, rsi; String1
0x1004e8ffb  call    cs:__imp__wcsicmp
0x1004e9001  test    eax, eax
0x1004e9003  jz      loc_1004E908D
0x1004e9009  cmp     rdi, 17h
0x1004e900d  jnz     short loc_1004E9023
0x1004e900f  lea     rdx, aActivedirector_2; "ActiveDirectoryPassword"
0x1004e9016  mov     rcx, rsi; String1
0x1004e9019  call    cs:__imp__wcsicmp
0x1004e901f  test    eax, eax
0x1004e9021  jz      short loc_1004E908D
0x1004e9023  cmp     rdi, 1Ah
0x1004e9027  jnz     short loc_1004E903D
0x1004e9029  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x1004e9030  mov     rcx, rsi; String1
0x1004e9033  call    cs:__imp__wcsicmp
0x1004e9039  test    eax, eax
0x1004e903b  jz      short loc_1004E908D
0x1004e903d  cmp     rdi, 0Bh
0x1004e9041  jnz     short loc_1004E9057
0x1004e9043  lea     rdx, aSqlpassword; "SqlPassword"
0x1004e904a  mov     rcx, rsi; String1
0x1004e904d  call    cs:__imp__wcsicmp
0x1004e9053  test    eax, eax
0x1004e9055  jz      short loc_1004E908D
0x1004e9057  cmp     rdi, 12h
0x1004e905b  jnz     short loc_1004E9071
0x1004e905d  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x1004e9064  mov     rcx, rsi; String1
0x1004e9067  call    cs:__imp__wcsicmp
0x1004e906d  test    eax, eax
0x1004e906f  jz      short loc_1004E908D
0x1004e9071  cmp     rdi, 1Fh
0x1004e9075  jnz     short loc_1004E908B
0x1004e9077  lea     rdx, aActivedirector_0; "ActiveDirectoryServicePrincipal"
0x1004e907e  mov     rcx, rsi; String1
0x1004e9081  call    cs:__imp__wcsicmp
0x1004e9087  test    eax, eax
0x1004e9089  jz      short loc_1004E908D
0x1004e908b  mov     ebp, ebx
0x1004e908d  mov     rbx, [rsp+38h+arg_0]
0x1004e9092  mov     eax, ebp
0x1004e9094  mov     rbp, [rsp+38h+arg_8]
0x1004e9099  mov     rsi, [rsp+38h+arg_10]
0x1004e909e  add     rsp, 30h
0x1004e90a2  pop     rdi
0x1004e90a3  retn
```
