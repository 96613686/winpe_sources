# CInplaceShareEngine::_s_RemoveParentAce(ushort const *,void *)

- ea: `0x180024014`
- end: `0x18002423e`
- name: `?_s_RemoveParentAce@CInplaceShareEngine@@CAJPEBGPEAX@Z`
- size: `554`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, PSID pSid2)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059214`
- `0x18005c4a4`

## callees

- `0x18000f4b0`
- `0x18000f4f0`
- `0x180019d98`
- `0x180024014`
- `0x180024244`
- `0x1800254e0`
- `0x18005e108`
- `0x18005e1c8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800240ee`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800240ee`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024136`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024136`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800240b7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800240b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002420e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002420e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002417b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002417b`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180024081`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180024081`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_s_RemoveParentAce(LPCWSTR lpFileName, PSID pSid2)
{
  signed int NamedSecurityInfoW; // eax
  signed int Instance; // ebx
  int v6; // r14d
  DWORD v7; // edi
  PSID *v8; // rsi
  unsigned int v9; // edx
  signed int v10; // eax
  int v11; // r8d
  LPWSTR StringSid; // [rsp+40h] [rbp-40h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+50h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v18; // [rsp+68h] [rbp-18h]

  pAcl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem);
  Instance = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    Instance = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( Instance >= 0 )
  {
    pAclInformation = 0;
    v18 = 0;
    if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      v6 = 0;
      v7 = 0;
      do
      {
        if ( v6 || v7 >= (unsigned int)pAclInformation )
          break;
        pAce = 0;
        if ( GetAce(pAcl, v7, &pAce) )
        {
          StringSid = 0;
          Instance = CAce::CreateInstance((struct _ACE_HEADER *)pAce, (struct CAce **)&StringSid);
          if ( Instance >= 0 )
          {
            v8 = (PSID *)StringSid;
            if ( (unsigned int)CAce::IsTraverse((CAce *)StringSid) && EqualSid(v8[1], pSid2) )
            {
              v6 = 1;
              v10 = FaRemoveAce(lpFileName, v7);
              Instance = v10;
              if ( v10 > 0 )
                Instance = (unsigned __int16)v10 | 0x80070000;
              if ( Instance < 0 )
              {
                StringSid = 0;
                if ( ConvertSidToStringSidW(v8[1], &StringSid) )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    WPP_SF_SSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      25,
                      v11,
                      (_DWORD)StringSid,
                      (__int64)lpFileName,
                      Instance);
                  }
                  LocalFree(StringSid);
                }
                else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, (_DWORD)lpFileName, Instance);
                }
              }
            }
            if ( v8 )
              CAce::`scalar deleting destructor'((CAce *)v8, v9);
          }
        }
        ++v7;
      }
      while ( Instance >= 0 );
    }
    LocalFree(hMem);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180024014  mov     r11, rsp
0x180024017  mov     [r11+18h], rbx
0x18002401b  mov     [r11+20h], rsi
0x18002401f  push    rbp
0x180024020  push    rdi
0x180024021  push    r12
0x180024023  push    r14
0x180024025  push    r15
0x180024027  mov     rbp, rsp
0x18002402a  sub     rsp, 80h
0x180024031  mov     rax, cs:__security_cookie
0x180024038  xor     rax, rsp
0x18002403b  mov     [rbp+var_10], rax
0x18002403f  xor     r9d, r9d; ppsidOwner
0x180024042  mov     [rbp+pAcl], 0
0x18002404a  lea     rax, [rbp+hMem]
0x18002404e  mov     [rbp+hMem], 0
0x180024056  mov     [r11-70h], rax
0x18002405a  mov     r12, rdx
0x18002405d  mov     qword ptr [r11-78h], 0
0x180024065  lea     rax, [rbp+pAcl]
0x180024069  mov     [r11-80h], rax
0x18002406d  lea     edx, [r9+1]; ObjectType
0x180024071  lea     r8d, [r9+4]; SecurityInfo
0x180024075  mov     [rsp+80h+ppsidGroup], 0; ppsidGroup
0x18002407e  mov     r15, rcx
0x180024081  call    cs:__imp_GetNamedSecurityInfoW
0x180024087  mov     ebx, eax
0x180024089  test    eax, eax
0x18002408b  jle     short loc_180024096
0x18002408d  movzx   ebx, ax
0x180024090  or      ebx, 80070000h
0x180024096  test    ebx, ebx
0x180024098  js      loc_180024214
0x18002409e  mov     rcx, [rbp+pAcl]; pAcl
0x1800240a2  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1800240a6  xor     eax, eax
0x1800240a8  mov     [rbp+pAclInformation], rax
0x1800240ac  mov     [rbp+var_18], eax
0x1800240af  lea     r9d, [rax+2]; dwAclInformationClass
0x1800240b3  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800240b7  call    cs:__imp_GetAclInformation
0x1800240bd  test    eax, eax
0x1800240bf  jz      loc_18002420A
0x1800240c5  xor     r14d, r14d
0x1800240c8  xor     edi, edi
0x1800240ca  test    r14d, r14d
0x1800240cd  jnz     loc_18002420A
0x1800240d3  cmp     edi, dword ptr [rbp+pAclInformation]
0x1800240d6  jnb     loc_18002420A
0x1800240dc  mov     rcx, [rbp+pAcl]; pAcl
0x1800240e0  lea     r8, [rbp+pAce]; pAce
0x1800240e4  mov     edx, edi; dwAceIndex
0x1800240e6  mov     [rbp+pAce], 0
0x1800240ee  call    cs:__imp_GetAce
0x1800240f4  test    eax, eax
0x1800240f6  jz      loc_180024200
0x1800240fc  mov     rcx, [rbp+pAce]; struct _ACE_HEADER *
0x180024100  lea     rdx, [rbp+StringSid]; struct CAce **
0x180024104  mov     [rbp+StringSid], 0
0x18002410c  call    ?CreateInstance@CAce@@SAJPEAU_ACE_HEADER@@PEAPEAV1@@Z; CAce::CreateInstance(_ACE_HEADER *,CAce * *)
0x180024111  mov     ebx, eax
0x180024113  test    eax, eax
0x180024115  js      loc_180024200
0x18002411b  mov     rsi, [rbp+StringSid]
0x18002411f  mov     rcx, rsi; this
0x180024122  call    ?IsTraverse@CAce@@QEBAHXZ; CAce::IsTraverse(void)
0x180024127  test    eax, eax
0x180024129  jz      loc_1800241F3
0x18002412f  mov     rcx, [rsi+8]; pSid1
0x180024133  mov     rdx, r12; pSid2
0x180024136  call    cs:__imp_EqualSid
0x18002413c  test    eax, eax
0x18002413e  jz      loc_1800241F3
0x180024144  mov     edx, edi; dwAceIndex
0x180024146  mov     rcx, r15; lpFileName
0x180024149  mov     r14d, 1
0x18002414f  call    FaRemoveAce
0x180024154  mov     ebx, eax
0x180024156  test    eax, eax
0x180024158  jle     short loc_180024163
0x18002415a  movzx   ebx, ax
0x18002415d  or      ebx, 80070000h
0x180024163  test    ebx, ebx
0x180024165  jns     loc_1800241F3
0x18002416b  mov     [rbp+StringSid], 0
0x180024173  lea     rdx, [rbp+StringSid]; StringSid
0x180024177  mov     rcx, [rsi+8]; Sid
0x18002417b  call    cs:__imp_ConvertSidToStringSidW
0x180024181  test    eax, eax
0x180024183  jz      short loc_1800241C5
0x180024185  mov     rcx, cs:WPP_GLOBAL_Control
0x18002418c  lea     rax, WPP_GLOBAL_Control
0x180024193  cmp     rcx, rax
0x180024196  jz      short loc_1800241B9
0x180024198  test    byte ptr [rcx+1Ch], 4
0x18002419c  jz      short loc_1800241B9
0x18002419e  mov     r9, [rbp+StringSid]
0x1800241a2  mov     edx, 19h
0x1800241a7  mov     rcx, [rcx+10h]
0x1800241ab  mov     [rsp+80h+var_58], ebx
0x1800241af  mov     [rsp+80h+ppsidGroup], r15
0x1800241b4  call    WPP_SF_SSd
0x1800241b9  mov     rcx, [rbp+StringSid]; hMem
0x1800241bd  call    cs:__imp_LocalFree
0x1800241c3  jmp     short loc_1800241F3
0x1800241c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241cc  lea     rax, WPP_GLOBAL_Control
0x1800241d3  cmp     rcx, rax
0x1800241d6  jz      short loc_1800241F3
0x1800241d8  test    byte ptr [rcx+1Ch], 4
0x1800241dc  jz      short loc_1800241F3
0x1800241de  mov     rcx, [rcx+10h]
0x1800241e2  mov     edx, 1Ah
0x1800241e7  mov     r9, r15
0x1800241ea  mov     dword ptr [rsp+80h+ppsidGroup], ebx
0x1800241ee  call    WPP_SF_Sd
0x1800241f3  test    rsi, rsi
0x1800241f6  jz      short loc_180024200
0x1800241f8  mov     rcx, rsi; this
0x1800241fb  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x180024200  inc     edi
0x180024202  test    ebx, ebx
0x180024204  jns     loc_1800240CA
0x18002420a  mov     rcx, [rbp+hMem]; hMem
0x18002420e  call    cs:__imp_LocalFree
0x180024214  mov     eax, ebx
0x180024216  mov     rcx, [rbp+var_10]
0x18002421a  xor     rcx, rsp; StackCookie
0x18002421d  call    __security_check_cookie
0x180024222  lea     r11, [rsp+80h+var_s0]
0x18002422a  mov     rbx, [r11+40h]
0x18002422e  mov     rsi, [r11+48h]
0x180024232  mov     rsp, r11
0x180024235  pop     r15
0x180024237  pop     r14
0x180024239  pop     r12
0x18002423b  pop     rdi
0x18002423c  pop     rbp
0x18002423d  retn
```
