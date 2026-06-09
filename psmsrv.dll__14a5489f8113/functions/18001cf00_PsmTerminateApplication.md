# PsmTerminateApplication

- ea: `0x18001cf00`
- end: `0x18001d0d5`
- name: `PsmTerminateApplication`
- size: `469`
- prototype: `__int64 __fastcall(PSID Sid2, char, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callees

- `0x180001580`
- `0x18000171c`
- `0x180008cc0`
- `0x180009b40`
- `0x1800114d0`
- `0x18001b7e0`
- `0x18001cf00`
- `0x18001ea9c`
- `0x18001ee1c`
- `0x18001ef34`

## import_xrefs

- `ext-ms-win-core-psm-service-l1-1-2!PsmHamTerminateApplication` at `0x18001cf82`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHamTerminateApplication` at `0x18001cf82`

## pseudocode

```c
__int64 __fastcall PsmTerminateApplication(PSID Sid2, int a2, const unsigned __int16 *a3)
{
  int IsPackageFamilyNameEnabled; // ebx
  __int64 v7; // r9
  int ApplicationByManagerForUser; // eax
  __int64 v9; // r8
  __int64 v10; // rsi
  int v11; // eax
  int v12; // r8d
  PSID v14; // [rsp+28h] [rbp-F0h]
  __int64 v15; // [rsp+48h] [rbp-D0h] BYREF
  WCHAR ValueName[72]; // [rsp+50h] [rbp-C8h] BYREF

  v15 = 0;
  IsPackageFamilyNameEnabled = HamOptInPsmKeyToPackageFamilyName(a3, ValueName);
  if ( IsPackageFamilyNameEnabled || (IsPackageFamilyNameEnabled = HamOptInIsPackageFamilyNameEnabledEx(ValueName)) != 0 )
  {
    if ( IsPackageFamilyNameEnabled > 0 )
      return (unsigned __int16)IsPackageFamilyNameEnabled | 0xC0070000;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, a2, (__int64)a3, 2 * v7 + 2, 0, &v15);
    v10 = v15;
    IsPackageFamilyNameEnabled = ApplicationByManagerForUser;
    if ( ApplicationByManagerForUser >= 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_iS_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Cu, v9, *(_QWORD *)(v15 + 96), a3, Sid2, a2);
      v11 = PsmpChangeApplicationState(v10, 0, 0, 6u, 6, 0);
      IsPackageFamilyNameEnabled = v11;
      if ( v11 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_iSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v12, *(_QWORD *)(v10 + 96), (__int64)a3, v11);
    }
    else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(v14) = ApplicationByManagerForUser;
      WPP_SF_S_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Bu, v9, a3, (char *)Sid2, v14);
    }
    if ( v10 )
      PsmpDereferenceApplicationEx(v10, 0);
  }
  return (unsigned int)IsPackageFamilyNameEnabled;
}

```

## disassembly

```asm
0x18001cf00  mov     [rsp+arg_18], rbx
0x18001cf05  push    rbp
0x18001cf06  push    rsi
0x18001cf07  push    r12
0x18001cf09  push    r14
0x18001cf0b  push    r15
0x18001cf0d  sub     rsp, 0F0h
0x18001cf14  mov     rax, cs:__security_cookie
0x18001cf1b  xor     rax, rsp
0x18001cf1e  mov     [rsp+118h+var_38], rax
0x18001cf26  mov     r15d, edx
0x18001cf29  mov     r14, rcx
0x18001cf2c  xor     r12d, r12d
0x18001cf2f  lea     rdx, [rsp+118h+ValueName]; unsigned __int16 *
0x18001cf34  mov     rcx, r8; unsigned __int16 *
0x18001cf37  mov     [rsp+118h+var_D8], r12b
0x18001cf3c  mov     [rsp+118h+var_D0], r12
0x18001cf41  mov     rbp, r8
0x18001cf44  call    ?HamOptInPsmKeyToPackageFamilyName@@YAKPEBGPEAG@Z; HamOptInPsmKeyToPackageFamilyName(ushort const *,ushort *)
0x18001cf49  mov     ebx, eax
0x18001cf4b  test    eax, eax
0x18001cf4d  jnz     loc_18001D09E
0x18001cf53  lea     r8, [rsp+118h+var_D8]
0x18001cf58  lea     rcx, [rsp+118h+ValueName]; lpValueName
0x18001cf5d  call    HamOptInIsPackageFamilyNameEnabledEx
0x18001cf62  mov     ebx, eax
0x18001cf64  test    eax, eax
0x18001cf66  jnz     loc_18001D09E
0x18001cf6c  cmp     [rsp+118h+var_D8], r12b
0x18001cf71  jz      short loc_18001CF8F
0x18001cf73  mov     r9d, 400h
0x18001cf79  mov     r8, rbp
0x18001cf7c  mov     edx, r15d
0x18001cf7f  mov     rcx, r14
0x18001cf82  call    cs:__imp_PsmHamTerminateApplication
0x18001cf88  mov     ebx, eax
0x18001cf8a  jmp     loc_18001D0AB
0x18001cf8f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cf93  inc     r9
0x18001cf96  cmp     [rbp+r9*2+0], r12w
0x18001cf9c  jnz     short loc_18001CF93
0x18001cf9e  lea     rax, [rsp+118h+var_D0]
0x18001cfa3  mov     r8, rbp
0x18001cfa6  mov     [rsp+118h+var_F0], rax; __int64
0x18001cfab  lea     r9, ds:2[r9*2]
0x18001cfb3  mov     edx, r15d
0x18001cfb6  mov     dword ptr [rsp+118h+pSid], r12d; int
0x18001cfbb  mov     rcx, r14; Sid2
0x18001cfbe  call    PsmpFindApplicationByManagerForUser
0x18001cfc3  mov     rsi, [rsp+118h+var_D0]
0x18001cfc8  mov     ebx, eax
0x18001cfca  test    eax, eax
0x18001cfcc  jns     short loc_18001D008
0x18001cfce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfd5  test    byte ptr [rcx+1Ch], 2
0x18001cfd9  jz      loc_18001D08D
0x18001cfdf  cmp     byte ptr [rcx+19h], 2
0x18001cfe3  jb      loc_18001D08D
0x18001cfe9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cfed  mov     edx, 1Bh
0x18001cff2  mov     dword ptr [rsp+118h+var_F0], eax; char
0x18001cff6  mov     r9, rbp
0x18001cff9  mov     [rsp+118h+pSid], r14; pSid
0x18001cffe  call    WPP_SF_S_sid_d
0x18001d003  jmp     loc_18001D08D
0x18001d008  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d00f  test    byte ptr [rcx+1Ch], 2
0x18001d013  jz      short loc_18001D03C
0x18001d015  cmp     byte ptr [rcx+19h], 4
0x18001d019  jb      short loc_18001D03C
0x18001d01b  mov     r9, [rsi+60h]
0x18001d01f  mov     edx, 1Ch
0x18001d024  mov     rcx, [rcx+10h]; LoggerHandle
0x18001d028  mov     dword ptr [rsp+118h+var_E8], r15d; char
0x18001d02d  mov     [rsp+118h+var_F0], r14; pSid
0x18001d032  mov     [rsp+118h+pSid], rbp; __int64
0x18001d037  call    WPP_SF_iS_sid_d
0x18001d03c  mov     r9d, 6
0x18001d042  mov     [rsp+118h+var_F0], r12
0x18001d047  xor     r8d, r8d
0x18001d04a  mov     dword ptr [rsp+118h+pSid], r9d
0x18001d04f  xor     edx, edx
0x18001d051  mov     rcx, rsi
0x18001d054  call    PsmpChangeApplicationState
0x18001d059  mov     ebx, eax
0x18001d05b  test    eax, eax
0x18001d05d  jns     short loc_18001D08D
0x18001d05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d066  test    byte ptr [rcx+1Ch], 2
0x18001d06a  jz      short loc_18001D08D
0x18001d06c  cmp     byte ptr [rcx+19h], 2
0x18001d070  jb      short loc_18001D08D
0x18001d072  mov     r9, [rsi+60h]
0x18001d076  mov     edx, 1Dh
0x18001d07b  mov     rcx, [rcx+10h]
0x18001d07f  mov     dword ptr [rsp+118h+var_F0], eax
0x18001d083  mov     [rsp+118h+pSid], rbp
0x18001d088  call    WPP_SF_iSd
0x18001d08d  test    rsi, rsi
0x18001d090  jz      short loc_18001D0AB
0x18001d092  xor     edx, edx
0x18001d094  mov     rcx, rsi
0x18001d097  call    PsmpDereferenceApplicationEx
0x18001d09c  jmp     short loc_18001D0AB
0x18001d09e  test    ebx, ebx
0x18001d0a0  jle     short loc_18001D0AB
0x18001d0a2  movzx   ebx, bx
0x18001d0a5  or      ebx, 0C0070000h
0x18001d0ab  mov     eax, ebx
0x18001d0ad  mov     rcx, [rsp+118h+var_38]
0x18001d0b5  xor     rcx, rsp; StackCookie
0x18001d0b8  call    __security_check_cookie
0x18001d0bd  mov     rbx, [rsp+118h+arg_18]
0x18001d0c5  add     rsp, 0F0h
0x18001d0cc  pop     r15
0x18001d0ce  pop     r14
0x18001d0d0  pop     r12
0x18001d0d2  pop     rsi
0x18001d0d3  pop     rbp
0x18001d0d4  retn
```
