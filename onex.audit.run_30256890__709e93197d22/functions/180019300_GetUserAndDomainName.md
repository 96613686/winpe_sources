# GetUserAndDomainName

- ea: `0x180019300`
- end: `0x180019566`
- name: `GetUserAndDomainName`
- size: `614`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ac0`
- `0x180002020`
- `0x180011310`
- `0x180029668`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180019300`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001949c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001949c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001939a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180019492`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18001939a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180019492`
- `MobileNetworking!AllocateMemory` at `0x1800193d4`
- `MobileNetworking!AllocateMemory` at `0x180019436`
- `MobileNetworking!AllocateMemory` at `0x1800193d4`
- `MobileNetworking!AllocateMemory` at `0x180019436`
- `MobileNetworking!FreeMemory` at `0x18001950a`
- `MobileNetworking!FreeMemory` at `0x180019522`
- `MobileNetworking!FreeMemory` at `0x18001950a`
- `MobileNetworking!FreeMemory` at `0x180019522`

## pseudocode

```c
__int64 __fastcall GetUserAndDomainName(unsigned int a1, PSID *a2, LPWSTR *a3, _QWORD *a4)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPWSTR Name; // [rsp+30h] [rbp-48h] BYREF
  LPWSTR ReferencedDomainName[8]; // [rsp+38h] [rbp-40h] BYREF
  DWORD cchReferencedDomainName; // [rsp+88h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+90h] [rbp+18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+98h] [rbp+20h] BYREF

  peUse = SidTypeInvalid;
  v4 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  Name = 0;
  ReferencedDomainName[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids);
  *a3 = 0;
  *a4 = 0;
  if ( !LookupAccountSidLocalW(*a2, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 122 )
    {
      LastError = AllocateMemory(2 * cchName, &Name, "GetUserAndDomainName", 448);
      v4 = LastError;
      if ( LastError )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_25;
        v11 = 45;
        goto LABEL_10;
      }
      LastError = AllocateMemory(2 * cchReferencedDomainName, ReferencedDomainName, "GetUserAndDomainName", 451);
      v4 = LastError;
      if ( LastError )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_25;
        v11 = 46;
        goto LABEL_10;
      }
      if ( !LookupAccountSidLocalW(*a2, Name, &cchName, ReferencedDomainName[0], &cchReferencedDomainName, &peUse) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_25;
          v11 = 47;
          goto LABEL_10;
        }
      }
    }
    else if ( LastError )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_25;
      v11 = 48;
LABEL_10:
      WPP_SF_dd(v10[7], v11, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, a1, LastError);
LABEL_25:
      FreeMemory(&Name, "GetUserAndDomainName", 470);
      FreeMemory(ReferencedDomainName, "GetUserAndDomainName", 471);
      goto LABEL_26;
    }
  }
  *a3 = Name;
  *a4 = ReferencedDomainName[0];
  if ( v4 )
    goto LABEL_25;
LABEL_26:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180019300  mov     rax, rsp
0x180019303  push    rbx
0x180019304  push    rbp
0x180019305  push    rsi
0x180019306  push    rdi
0x180019307  push    r12
0x180019309  push    r14
0x18001930b  push    r15
0x18001930d  sub     rsp, 40h
0x180019311  xor     r15d, r15d
0x180019314  mov     dword ptr [rax+20h], 7
0x18001931b  mov     ebx, r15d
0x18001931e  mov     [rax+18h], r15d
0x180019322  mov     [rax+10h], r15d
0x180019326  mov     rdi, r9
0x180019329  mov     [rax-48h], r15
0x18001932d  mov     rsi, r8
0x180019330  mov     [rax-40h], r15
0x180019334  mov     r14, rdx
0x180019337  mov     ebp, ecx
0x180019339  mov     rcx, cs:WPP_GLOBAL_Control
0x180019340  lea     r12, WPP_GLOBAL_Control
0x180019347  cmp     rcx, r12
0x18001934a  jz      short loc_18001936A
0x18001934c  test    dword ptr [rcx+44h], 800h
0x180019353  jz      short loc_18001936A
0x180019355  mov     rcx, [rcx+38h]
0x180019359  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180019360  mov     edx, 2Ch ; ','
0x180019365  call    WPP_SF_
0x18001936a  mov     [rsi], r15
0x18001936d  lea     rax, [rsp+78h+arg_18]
0x180019375  mov     [rsp+78h+peUse], rax; peUse
0x18001937a  lea     r8, [rsp+78h+cchName]; cchName
0x180019382  lea     rax, [rsp+78h+arg_8]
0x18001938a  mov     [rdi], r15
0x18001938d  mov     rcx, [r14]; Sid
0x180019390  xor     r9d, r9d; ReferencedDomainName
0x180019393  xor     edx, edx; Name
0x180019395  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001939a  call    cs:__imp_LookupAccountSidLocalW
0x1800193a0  test    eax, eax
0x1800193a2  jnz     loc_1800194E4
0x1800193a8  call    cs:__imp_GetLastError
0x1800193ae  mov     ebx, eax
0x1800193b0  cmp     eax, 7Ah ; 'z'
0x1800193b3  jnz     loc_1800194C4
0x1800193b9  mov     ecx, [rsp+78h+cchName]
0x1800193c0  lea     r8, aGetuseranddoma; "GetUserAndDomainName"
0x1800193c7  add     ecx, ecx
0x1800193c9  lea     rdx, [rsp+78h+Name]
0x1800193ce  mov     r9d, 1C0h
0x1800193d4  call    cs:__imp_AllocateMemory
0x1800193da  mov     ebx, eax
0x1800193dc  test    eax, eax
0x1800193de  jz      short loc_18001941B
0x1800193e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193e7  cmp     rcx, r12
0x1800193ea  jz      loc_1800194F8
0x1800193f0  test    byte ptr [rcx+44h], 1
0x1800193f4  jz      loc_1800194F8
0x1800193fa  mov     edx, 2Dh ; '-'
0x1800193ff  mov     rcx, [rcx+38h]
0x180019403  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x18001940a  mov     r9d, ebp
0x18001940d  mov     dword ptr [rsp+78h+cchReferencedDomainName], eax
0x180019411  call    WPP_SF_dd
0x180019416  jmp     loc_1800194F8
0x18001941b  mov     ecx, [rsp+78h+arg_8]
0x180019422  lea     r8, aGetuseranddoma; "GetUserAndDomainName"
0x180019429  add     ecx, ecx
0x18001942b  lea     rdx, [rsp+78h+ReferencedDomainName]
0x180019430  mov     r9d, 1C3h
0x180019436  call    cs:__imp_AllocateMemory
0x18001943c  mov     ebx, eax
0x18001943e  test    eax, eax
0x180019440  jz      short loc_180019463
0x180019442  mov     rcx, cs:WPP_GLOBAL_Control
0x180019449  cmp     rcx, r12
0x18001944c  jz      loc_1800194F8
0x180019452  test    byte ptr [rcx+44h], 1
0x180019456  jz      loc_1800194F8
0x18001945c  mov     edx, 2Eh ; '.'
0x180019461  jmp     short loc_1800193FF
0x180019463  mov     r9, [rsp+78h+ReferencedDomainName]; ReferencedDomainName
0x180019468  lea     rax, [rsp+78h+arg_18]
0x180019470  mov     rdx, [rsp+78h+Name]; Name
0x180019475  lea     r8, [rsp+78h+cchName]; cchName
0x18001947d  mov     rcx, [r14]; Sid
0x180019480  mov     [rsp+78h+peUse], rax; peUse
0x180019485  lea     rax, [rsp+78h+arg_8]
0x18001948d  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180019492  call    cs:__imp_LookupAccountSidLocalW
0x180019498  test    eax, eax
0x18001949a  jnz     short loc_1800194E4
0x18001949c  call    cs:__imp_GetLastError
0x1800194a2  mov     ebx, eax
0x1800194a4  test    eax, eax
0x1800194a6  jz      short loc_1800194E4
0x1800194a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194af  cmp     rcx, r12
0x1800194b2  jz      short loc_1800194F8
0x1800194b4  test    byte ptr [rcx+44h], 1
0x1800194b8  jz      short loc_1800194F8
0x1800194ba  mov     edx, 2Fh ; '/'
0x1800194bf  jmp     loc_1800193FF
0x1800194c4  test    eax, eax
0x1800194c6  jz      short loc_1800194E4
0x1800194c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194cf  cmp     rcx, r12
0x1800194d2  jz      short loc_1800194F8
0x1800194d4  test    byte ptr [rcx+44h], 1
0x1800194d8  jz      short loc_1800194F8
0x1800194da  mov     edx, 30h ; '0'
0x1800194df  jmp     loc_1800193FF
0x1800194e4  mov     rax, [rsp+78h+Name]
0x1800194e9  mov     [rsi], rax
0x1800194ec  mov     rax, [rsp+78h+ReferencedDomainName]
0x1800194f1  mov     [rdi], rax
0x1800194f4  test    ebx, ebx
0x1800194f6  jz      short loc_180019528
0x1800194f8  mov     r8d, 1D6h
0x1800194fe  lea     rdx, aGetuseranddoma; "GetUserAndDomainName"
0x180019505  lea     rcx, [rsp+78h+Name]
0x18001950a  call    cs:__imp_FreeMemory
0x180019510  mov     r8d, 1D7h
0x180019516  lea     rdx, aGetuseranddoma; "GetUserAndDomainName"
0x18001951d  lea     rcx, [rsp+78h+ReferencedDomainName]
0x180019522  call    cs:__imp_FreeMemory
0x180019528  mov     rcx, cs:WPP_GLOBAL_Control
0x18001952f  cmp     rcx, r12
0x180019532  jz      short loc_180019555
0x180019534  test    dword ptr [rcx+44h], 800h
0x18001953b  jz      short loc_180019555
0x18001953d  mov     rcx, [rcx+38h]
0x180019541  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180019548  mov     edx, 31h ; '1'
0x18001954d  mov     r9d, ebx
0x180019550  call    WPP_SF_D
0x180019555  mov     eax, ebx
0x180019557  add     rsp, 40h
0x18001955b  pop     r15
0x18001955d  pop     r14
0x18001955f  pop     r12
0x180019561  pop     rdi
0x180019562  pop     rsi
0x180019563  pop     rbp
0x180019564  pop     rbx
0x180019565  retn
```
