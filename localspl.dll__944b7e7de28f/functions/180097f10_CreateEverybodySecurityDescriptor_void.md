# CreateEverybodySecurityDescriptor(void)

- ea: `0x180097f10`
- end: `0x1800981fe`
- name: `?CreateEverybodySecurityDescriptor@@YAPEAXXZ`
- size: `750`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005000`
- `0x18007bd7c`

## callees

- `0x1800239a0`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x1800547e0`
- `0x180097f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009801d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009801d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980b8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097fb7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098013`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009805e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800980ae`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097fb7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098013`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009805e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800980ae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981a0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981b0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981d0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981a0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981b0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800981d0`

## string_xrefs

- `0x180097fd1`: `CreateEverybodySecurityDescriptor`
- `0x180098186`: `CreateEverybodySecurityDescriptor`
- `0x180098023`: `Couldn't allocate and initialize Creator-Owner SID.  Error %d`
- `0x180097fc7`: `Couldn't allocate and initialize User SID.  Error %d`
- `0x18009806e`: `Couldn't allocate and initialize Local System SID.  Error %d`
- `0x1800980be`: `Couldn't allocate and initialize Admin SID.  Error %d`

## pseudocode

```c
__int64 CreateEverybodySecurityDescriptor(void)
{
  DWORD v0; // eax
  DWORD v1; // eax
  DWORD v2; // eax
  DWORD LastError; // eax
  unsigned int v4; // ebx
  DWORD nSubAuthority5; // [rsp+38h] [rbp-C8h]
  PSID pSid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v8; // [rsp+68h] [rbp-98h] BYREF
  PSID v9; // [rsp+70h] [rbp-90h] BYREF
  PSID v10; // [rsp+78h] [rbp-88h] BYREF
  __int64 v11; // [rsp+80h] [rbp-80h] BYREF
  int v12; // [rsp+88h] [rbp-78h] BYREF
  char v13; // [rsp+8Ch] [rbp-74h]
  int v14; // [rsp+A0h] [rbp-60h] BYREF
  char v15; // [rsp+A4h] [rbp-5Ch]
  int v16[20]; // [rsp+C0h] [rbp-40h] BYREF
  int v17[2]; // [rsp+110h] [rbp+10h] BYREF
  PSID v18; // [rsp+118h] [rbp+18h]
  PSID v19; // [rsp+120h] [rbp+20h]
  PSID v20; // [rsp+128h] [rbp+28h]
  PSID v21[16]; // [rsp+130h] [rbp+30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+1B8h] [rbp+B8h] BYREF

  memset_0(v21, 0, sizeof(v21));
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 768;
  v8 = 0;
  pSid = 0;
  v10 = 0;
  v9 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( AllocateAndInitializeSid(&v23, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v9) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v10) )
      {
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v8) )
        {
          v4 = 4;
          *(_QWORD *)v17 = pSid;
          v18 = v9;
          v19 = v10;
          v20 = v8;
          v14 = 0;
          v16[0] = 1048718;
          v12 = 50529026;
          v16[1] = 2032095;
          v16[2] = 2032095;
          v16[3] = 2032095;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
          {
            v4 = 5;
            v21[0] = gRestrictedSpoolerServiceSid;
            v15 = 0;
            v16[4] = 2032095;
            v13 = 3;
          }
          v11 = 0;
          if ( !(unsigned int)BuildPrintObjectProtection(
                                (__int64)&v14,
                                v4,
                                (__int64)v17,
                                (__int64)v16,
                                (__int64)&v12,
                                0,
                                0,
                                nSubAuthority5,
                                &v11) )
          {
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "CreateEverybodySecurityDescriptor",
              L"Could not build Print Object protection");
            v11 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "CreateEverybodySecurityDescriptor",
            L"Couldn't allocate and initialize Admin SID.  Error %d",
            LastError);
        }
      }
      else
      {
        v2 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "CreateEverybodySecurityDescriptor",
          L"Couldn't allocate and initialize Local System SID.  Error %d",
          v2);
      }
    }
    else
    {
      v1 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateEverybodySecurityDescriptor",
        L"Couldn't allocate and initialize Creator-Owner SID.  Error %d",
        v1);
    }
  }
  else
  {
    v0 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateEverybodySecurityDescriptor",
      L"Couldn't allocate and initialize User SID.  Error %d",
      v0);
  }
  if ( pSid )
    FreeSid(pSid);
  if ( v8 )
    FreeSid(v8);
  if ( v9 )
    FreeSid(v9);
  if ( v10 )
    FreeSid(v10);
  return v11;
}

```

## disassembly

```asm
0x180097f10  mov     [rsp-8+arg_0], rbx
0x180097f15  mov     [rsp-8+arg_8], rdi
0x180097f1a  push    rbp
0x180097f1b  lea     rbp, [rsp-0D0h]
0x180097f23  sub     rsp, 1D0h
0x180097f2a  mov     rax, cs:__security_cookie
0x180097f31  xor     rax, rsp
0x180097f34  mov     [rbp+0D0h+var_10], rax
0x180097f3b  xor     edx, edx; Val
0x180097f3d  lea     rcx, [rbp+0D0h+var_A0]; void *
0x180097f41  mov     r8d, 80h; Size
0x180097f47  call    memset_0
0x180097f4c  xor     edi, edi
0x180097f4e  mov     word ptr [rbp+0D0h+pIdentifierAuthority.Value+4], 500h
0x180097f57  lea     rax, [rsp+1D0h+var_170]
0x180097f5c  mov     dword ptr [rbp+0D0h+pIdentifierAuthority.Value], edi
0x180097f62  mov     [rsp+1D0h+pSid], rax; pSid
0x180097f67  lea     rcx, [rbp+0D0h+pIdentifierAuthority]; pIdentifierAuthority
0x180097f6e  mov     [rsp+1D0h+nSubAuthority7], edi; nSubAuthority7
0x180097f72  mov     r9d, 221h; nSubAuthority1
0x180097f78  mov     [rsp+1D0h+nSubAuthority6], edi; nSubAuthority6
0x180097f7c  lea     ebx, [rdi+20h]
0x180097f7f  mov     [rsp+1D0h+nSubAuthority5], edi; nSubAuthority5
0x180097f83  mov     r8d, ebx; nSubAuthority0
0x180097f86  mov     [rsp+1D0h+nSubAuthority4], edi; nSubAuthority4
0x180097f8a  mov     dl, 2; nSubAuthorityCount
0x180097f8c  mov     [rsp+1D0h+nSubAuthority3], edi; nSubAuthority3
0x180097f90  mov     [rsp+1D0h+nSubAuthority2], edi; nSubAuthority2
0x180097f94  mov     dword ptr [rbp+0D0h+var_18.Value], edi
0x180097f9a  mov     word ptr [rbp+0D0h+var_18.Value+4], 300h
0x180097fa3  mov     [rsp+1D0h+var_168], rdi
0x180097fa8  mov     [rsp+1D0h+var_170], rdi
0x180097fad  mov     [rsp+1D0h+var_158], rdi
0x180097fb2  mov     [rsp+1D0h+var_160], rdi
0x180097fb7  call    cs:__imp_AllocateAndInitializeSid
0x180097fbd  test    eax, eax
0x180097fbf  jnz     short loc_180097FE2
0x180097fc1  call    cs:__imp_GetLastError
0x180097fc7  lea     rdx, aCouldnTAllocat_5; "Couldn't allocate and initialize User S"...
0x180097fce  mov     r8d, eax
0x180097fd1  lea     rcx, aCreateeverybod; "CreateEverybodySecurityDescriptor"
0x180097fd8  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180097fdd  jmp     loc_180098196
0x180097fe2  lea     rax, [rsp+1D0h+var_160]
0x180097fe7  xor     r9d, r9d; nSubAuthority1
0x180097fea  mov     [rsp+1D0h+pSid], rax; pSid
0x180097fef  lea     rcx, [rbp+0D0h+var_18]; pIdentifierAuthority
0x180097ff6  mov     [rsp+1D0h+nSubAuthority7], edi; nSubAuthority7
0x180097ffa  xor     r8d, r8d; nSubAuthority0
0x180097ffd  mov     [rsp+1D0h+nSubAuthority6], edi; nSubAuthority6
0x180098001  mov     dl, 1; nSubAuthorityCount
0x180098003  mov     [rsp+1D0h+nSubAuthority5], edi; nSubAuthority5
0x180098007  mov     [rsp+1D0h+nSubAuthority4], edi; nSubAuthority4
0x18009800b  mov     [rsp+1D0h+nSubAuthority3], edi; nSubAuthority3
0x18009800f  mov     [rsp+1D0h+nSubAuthority2], edi; nSubAuthority2
0x180098013  call    cs:__imp_AllocateAndInitializeSid
0x180098019  test    eax, eax
0x18009801b  jnz     short loc_18009802C
0x18009801d  call    cs:__imp_GetLastError
0x180098023  lea     rdx, aCouldnTAllocat_7; "Couldn't allocate and initialize Creato"...
0x18009802a  jmp     short loc_180097FCE
0x18009802c  lea     rax, [rsp+1D0h+var_158]
0x180098031  xor     r9d, r9d; nSubAuthority1
0x180098034  mov     [rsp+1D0h+pSid], rax; pSid
0x180098039  lea     rcx, [rbp+0D0h+pIdentifierAuthority]; pIdentifierAuthority
0x180098040  mov     [rsp+1D0h+nSubAuthority7], edi; nSubAuthority7
0x180098044  mov     dl, 1; nSubAuthorityCount
0x180098046  mov     [rsp+1D0h+nSubAuthority6], edi; nSubAuthority6
0x18009804a  mov     [rsp+1D0h+nSubAuthority5], edi; nSubAuthority5
0x18009804e  lea     r8d, [r9+12h]; nSubAuthority0
0x180098052  mov     [rsp+1D0h+nSubAuthority4], edi; nSubAuthority4
0x180098056  mov     [rsp+1D0h+nSubAuthority3], edi; nSubAuthority3
0x18009805a  mov     [rsp+1D0h+nSubAuthority2], edi; nSubAuthority2
0x18009805e  call    cs:__imp_AllocateAndInitializeSid
0x180098064  test    eax, eax
0x180098066  jnz     short loc_18009807A
0x180098068  call    cs:__imp_GetLastError
0x18009806e  lea     rdx, aCouldnTAllocat_3; "Couldn't allocate and initialize Local "...
0x180098075  jmp     loc_180097FCE
0x18009807a  lea     rax, [rsp+1D0h+var_168]
0x18009807f  mov     r9d, 220h; nSubAuthority1
0x180098085  mov     [rsp+1D0h+pSid], rax; pSid
0x18009808a  lea     rcx, [rbp+0D0h+pIdentifierAuthority]; pIdentifierAuthority
0x180098091  mov     [rsp+1D0h+nSubAuthority7], edi; nSubAuthority7
0x180098095  mov     r8d, ebx; nSubAuthority0
0x180098098  mov     [rsp+1D0h+nSubAuthority6], edi; nSubAuthority6
0x18009809c  mov     dl, 2; nSubAuthorityCount
0x18009809e  mov     [rsp+1D0h+nSubAuthority5], edi; dwBufferLength
0x1800980a2  mov     [rsp+1D0h+nSubAuthority4], edi; nSubAuthority4
0x1800980a6  mov     [rsp+1D0h+nSubAuthority3], edi; nSubAuthority3
0x1800980aa  mov     [rsp+1D0h+nSubAuthority2], edi; nSubAuthority2
0x1800980ae  call    cs:__imp_AllocateAndInitializeSid
0x1800980b4  test    eax, eax
0x1800980b6  jnz     short loc_1800980CA
0x1800980b8  call    cs:__imp_GetLastError
0x1800980be  lea     rdx, aCouldnTAllocat_6; "Couldn't allocate and initialize Admin "...
0x1800980c5  jmp     loc_180097FCE
0x1800980ca  mov     rax, [rsp+1D0h+var_170]
0x1800980cf  mov     ebx, 4
0x1800980d4  mov     qword ptr [rbp+0D0h+var_C0], rax
0x1800980d8  mov     rax, [rsp+1D0h+var_160]
0x1800980dd  mov     [rbp+0D0h+var_B8], rax
0x1800980e1  mov     rax, [rsp+1D0h+var_158]
0x1800980e6  mov     [rbp+0D0h+var_B0], rax
0x1800980ea  mov     rax, [rsp+1D0h+var_168]
0x1800980ef  mov     [rbp+0D0h+var_A8], rax
0x1800980f3  mov     [rbp+0D0h+var_130], edi
0x1800980f6  mov     [rbp+0D0h+var_110], 10008Eh
0x1800980fd  mov     dword ptr [rbp+0D0h+var_148], 3030302h
0x180098104  mov     [rbp+0D0h+var_10C], 1F01DFh
0x18009810b  mov     [rbp+0D0h+var_108], 1F01DFh
0x180098112  mov     [rbp+0D0h+var_104], 1F01DFh
0x180098119  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180098120  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180098125  test    al, al
0x180098127  jz      short loc_180098148
0x180098129  mov     rax, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; void * gRestrictedSpoolerServiceSid
0x180098130  mov     ebx, 5
0x180098135  mov     [rbp+0D0h+var_A0], rax
0x180098139  mov     [rbp+0D0h+var_12C], dil
0x18009813d  mov     [rbp+0D0h+var_100], 1F01DFh
0x180098144  mov     byte ptr [rbp+0D0h+var_148+4], 3
0x180098148  lea     rax, [rbp+0D0h+var_150]
0x18009814c  mov     [rbp+0D0h+var_150], rdi
0x180098150  mov     qword ptr [rsp+1D0h+nSubAuthority6], rax; __int64
0x180098155  lea     r9, [rbp+0D0h+var_110]; int
0x180098159  mov     qword ptr [rsp+1D0h+nSubAuthority4], rdi; pGroup
0x18009815e  lea     rax, [rbp+0D0h+var_148]
0x180098162  mov     qword ptr [rsp+1D0h+nSubAuthority3], rdi; pOwner
0x180098167  lea     r8, [rbp+0D0h+var_C0]; int
0x18009816b  mov     edx, ebx; int
0x18009816d  mov     qword ptr [rsp+1D0h+nSubAuthority2], rax; __int64
0x180098172  lea     rcx, [rbp+0D0h+var_130]; int
0x180098176  call    BuildPrintObjectProtection
0x18009817b  test    eax, eax
0x18009817d  jnz     short loc_180098196
0x18009817f  lea     rdx, aCouldNotBuildP; "Could not build Print Object protection"
0x180098186  lea     rcx, aCreateeverybod; "CreateEverybodySecurityDescriptor"
0x18009818d  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180098192  mov     [rbp+0D0h+var_150], rdi
0x180098196  mov     rcx, [rsp+1D0h+var_170]; pSid
0x18009819b  test    rcx, rcx
0x18009819e  jz      short loc_1800981A6
0x1800981a0  call    cs:__imp_FreeSid
0x1800981a6  mov     rcx, [rsp+1D0h+var_168]; pSid
0x1800981ab  test    rcx, rcx
0x1800981ae  jz      short loc_1800981B6
0x1800981b0  call    cs:__imp_FreeSid
0x1800981b6  mov     rcx, [rsp+1D0h+var_160]; pSid
0x1800981bb  test    rcx, rcx
0x1800981be  jz      short loc_1800981C6
0x1800981c0  call    cs:__imp_FreeSid
0x1800981c6  mov     rcx, [rsp+1D0h+var_158]; pSid
0x1800981cb  test    rcx, rcx
0x1800981ce  jz      short loc_1800981D6
0x1800981d0  call    cs:__imp_FreeSid
0x1800981d6  mov     rax, [rbp+0D0h+var_150]
0x1800981da  mov     rcx, [rbp+0D0h+var_10]
0x1800981e1  xor     rcx, rsp; StackCookie
0x1800981e4  call    __security_check_cookie
0x1800981e9  lea     r11, [rsp+1D0h+var_s0]
0x1800981f1  mov     rbx, [r11+10h]
0x1800981f5  mov     rdi, [r11+18h]
0x1800981f9  mov     rsp, r11
0x1800981fc  pop     rbp
0x1800981fd  retn
```
