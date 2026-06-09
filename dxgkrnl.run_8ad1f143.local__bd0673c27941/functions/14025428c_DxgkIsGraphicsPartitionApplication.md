# DxgkIsGraphicsPartitionApplication

- ea: `0x14025428c`
- end: `0x1402546cf`
- name: `DxgkIsGraphicsPartitionApplication`
- size: `1091`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1403b6044`

## callees

- `0x140012380`
- `0x14001b890`
- `0x1400a0100`
- `0x1400a0240`
- `0x14025428c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14025467a`
- `ntoskrnl!ZwClose` at `0x14025468b`
- `ntoskrnl!ZwClose` at `0x14025467a`
- `ntoskrnl!ZwClose` at `0x14025468b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402545e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402545e0`
- `ntoskrnl!ZwOpenKey` at `0x140254622`
- `ntoskrnl!ZwOpenKey` at `0x140254661`
- `ntoskrnl!ZwOpenKey` at `0x140254622`
- `ntoskrnl!ZwOpenKey` at `0x140254661`
- `ntoskrnl!ExGetPreviousMode` at `0x1402542bc`
- `ntoskrnl!ExGetPreviousMode` at `0x1402542bc`
- `ntoskrnl!RtlCapabilityCheck` at `0x140254441`
- `ntoskrnl!RtlCapabilityCheck` at `0x140254461`
- `ntoskrnl!RtlCapabilityCheck` at `0x140254441`
- `ntoskrnl!RtlCapabilityCheck` at `0x140254461`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140254325`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1402544ae`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140254325`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1402544ae`
- `ntoskrnl!SeQueryInformationToken` at `0x140254341`
- `ntoskrnl!SeQueryInformationToken` at `0x140254341`
- `ntoskrnl!SeSecurityAttributePresent` at `0x140254369`
- `ntoskrnl!SeSecurityAttributePresent` at `0x140254369`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1402543a1`
- `ntoskrnl!RtlQueryPackageClaims` at `0x1402543a1`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1402543b9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1402544eb`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1402543b9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1402544eb`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1402544da`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1402544da`
- `watchdog!WdLogSingleEntry0` at `0x1402542d6`
- `watchdog!WdLogSingleEntry0` at `0x1402542d6`
- `watchdog!WdLogSingleEntry1` at `0x1402543d1`
- `watchdog!WdLogSingleEntry1` at `0x1402543d1`

## string_xrefs

- `0x1402545cf`: `\REGISTRY\MACHINE\OSDATA\Software\Microsoft\Durango\LiveSettings\HevcOverride`

## pseudocode

```c
char __fastcall DxgkIsGraphicsPartitionApplication(PEPROCESS Process)
{
  char v2; // si
  PACCESS_TOKEN v3; // rdi
  NTSTATUS v4; // eax
  int v5; // ebx
  char v6; // r12
  int v7; // r15d
  PACCESS_TOKEN v9; // rdi
  int v10; // ebx
  __int16 v11; // ax
  unsigned int v12; // r15d
  __int16 *v13; // rcx
  unsigned int v14; // r14d
  _WORD *i; // rdi
  char v16; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+51h] [rbp-AFh] BYREF
  _BYTE v18[6]; // [rsp+52h] [rbp-AEh] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v21; // [rsp+68h] [rbp-98h]
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  PVOID TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v26[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v28[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _WORD Src[128]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v32[144]; // [rsp+200h] [rbp+100h] BYREF

  v2 = 1;
  if ( ExGetPreviousMode() != 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1558;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"ExGetPreviousMode() == UserMode", 1558, 0, 0, 0, 0);
  }
  TokenInformation = 0;
  v3 = PsReferencePrimaryToken(Process);
  v4 = SeQueryInformationToken(v3, TokenIsAppContainer, &TokenInformation);
  v26[0] = 1441812;
  v5 = v4;
  v26[1] = L"WIN://BGKD";
  v6 = SeSecurityAttributePresent(v3, v26);
  v22 = 0;
  RtlQueryPackageClaims(v3, 0, 0, 0, 0, 0, &v22, 0);
  v7 = v22 & 5;
  PsDereferencePrimaryToken(v3);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 1582;
    return 0;
  }
  if ( !TokenInformation && v7 != 5 || v6 == 1 )
    return 0;
  v27[0] = 1703960;
  v27[1] = L"hevcPlayback";
  v28[1] = L"expandedResources";
  v28[0] = 2359330;
  v16 = 0;
  v17 = 0;
  if ( v7 != 5 )
  {
    if ( (int)RtlCapabilityCheck(0, v27, &v16) < 0 )
      v16 = 0;
    if ( (int)RtlCapabilityCheck(0, v28, &v17) < 0 )
      v17 = 0;
  }
  if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 304896) )
  {
    if ( v16 )
      goto LABEL_33;
    if ( v17 )
      return 0;
    v24 = 256;
    v18[0] = 0;
    v9 = PsReferencePrimaryToken(Process);
    v10 = RtlQueryPackageIdentity(v9, Src, &v24, 0, 0, v18);
    PsDereferencePrimaryToken(v9);
    if ( v10 >= 0 && v18[0] )
    {
      v20 = 8519680;
      v21 = v32;
      v11 = Src[0];
      v12 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      if ( Src[0] != 95 )
      {
        v13 = Src;
        do
        {
          if ( !v11 )
            break;
          ++v13;
          v12 += 2;
          v11 = *v13;
        }
        while ( *v13 != 95 );
      }
      v14 = 0;
      for ( i = (_WORD *)((char *)&DestinationString.Buffer + v24 + 6); *i != 95 && i != Src; --i )
        v14 += 2;
      if ( (unsigned __int64)(v14 + v12) + 2 <= 0x82 )
      {
        KeyHandle = 0;
        DestinationString = 0;
        memmove(v32, Src, v12);
        memmove(&v21[v12], i, v14 + 2LL);
        LOWORD(v20) = v12 + v14;
        RtlInitUnicodeString(
          &DestinationString,
          L"\\REGISTRY\\MACHINE\\OSDATA\\Software\\Microsoft\\Durango\\LiveSettings\\HevcOverride");
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          ObjectAttributes.RootDirectory = KeyHandle;
          Handle = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
          {
            v16 = 1;
            ZwClose(Handle);
          }
          ZwClose(KeyHandle);
        }
      }
    }
  }
  if ( !v16 )
    return 0;
LABEL_33:
  if ( v17 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x14025428c  push    rbp
0x14025428e  push    rbx
0x14025428f  push    rsi
0x140254290  push    rdi
0x140254291  push    r12
0x140254293  push    r13
0x140254295  push    r14
0x140254297  push    r15
0x140254299  lea     rbp, [rsp-1A8h]
0x1402542a1  sub     rsp, 2A8h
0x1402542a8  mov     rax, cs:__security_cookie
0x1402542af  xor     rax, rsp
0x1402542b2  mov     [rbp+1E0h+var_50], rax
0x1402542b9  mov     r14, rcx
0x1402542bc  call    cs:__imp_ExGetPreviousMode
0x1402542c3  nop     dword ptr [rax+rax+00h]
0x1402542c8  xor     r13d, r13d
0x1402542cb  lea     esi, [r13+1]
0x1402542cf  cmp     al, sil
0x1402542d2  jz      short loc_14025431D
0x1402542d4  mov     ecx, esi
0x1402542d6  call    cs:__imp_WdLogSingleEntry0
0x1402542dd  nop     dword ptr [rax+rax+00h]
0x1402542e2  mov     [rsp+2E0h+var_2A0], r13
0x1402542e7  lea     r9, aExgetpreviousm; "ExGetPreviousMode() == UserMode"
0x1402542ee  mov     [rsp+2E0h+var_2A8], r13
0x1402542f3  mov     eax, 616h
0x1402542f8  mov     [rsp+2E0h+var_2B0], r13
0x1402542fd  or      r8d, 0FFFFFFFFh
0x140254301  mov     [rsp+2E0h+var_2B8], r13
0x140254306  mov     edx, 40002h
0x14025430b  xor     ecx, ecx
0x14025430d  mov     [rsp+2E0h+var_2C0], rax
0x140254312  mov     cs:WdLogGlobalForLineNumber, eax
0x140254318  call    DxgkLogInternalTriageEvent
0x14025431d  mov     rcx, r14; Process
0x140254320  mov     [rsp+2E0h+TokenInformation], r13
0x140254325  call    cs:__imp_PsReferencePrimaryToken
0x14025432c  nop     dword ptr [rax+rax+00h]
0x140254331  lea     r8, [rsp+2E0h+TokenInformation]; TokenInformation
0x140254336  mov     edx, 1Dh; TokenInformationClass
0x14025433b  mov     rcx, rax; Token
0x14025433e  mov     rdi, rax
0x140254341  call    cs:__imp_SeQueryInformationToken
0x140254348  nop     dword ptr [rax+rax+00h]
0x14025434d  lea     rdx, [rbp+1E0h+var_250]
0x140254351  mov     [rbp+1E0h+var_250], 160014h
0x140254359  mov     ebx, eax
0x14025435b  mov     rcx, rdi
0x14025435e  lea     rax, aWinBgkd; "WIN://BGKD"
0x140254365  mov     [rbp+1E0h+var_248], rax
0x140254369  call    cs:__imp_SeSecurityAttributePresent
0x140254370  nop     dword ptr [rax+rax+00h]
0x140254375  mov     [rsp+2E0h+var_2A8], r13
0x14025437a  xor     r9d, r9d
0x14025437d  mov     r12b, al
0x140254380  mov     [rsp+2E0h+var_270], r13
0x140254385  lea     rax, [rsp+2E0h+var_270]
0x14025438a  xor     r8d, r8d
0x14025438d  mov     [rsp+2E0h+var_2B0], rax
0x140254392  xor     edx, edx
0x140254394  mov     [rsp+2E0h+var_2B8], r13
0x140254399  mov     rcx, rdi
0x14025439c  mov     [rsp+2E0h+var_2C0], r13
0x1402543a1  call    cs:__imp_RtlQueryPackageClaims
0x1402543a8  nop     dword ptr [rax+rax+00h]
0x1402543ad  mov     r15d, dword ptr [rsp+2E0h+var_270]
0x1402543b2  mov     rcx, rdi; PrimaryToken
0x1402543b5  and     r15d, 5
0x1402543b9  call    cs:__imp_PsDereferencePrimaryToken
0x1402543c0  nop     dword ptr [rax+rax+00h]
0x1402543c5  test    ebx, ebx
0x1402543c7  jns     short loc_1402543EE
0x1402543c9  mov     rdx, r14
0x1402543cc  mov     ecx, 3
0x1402543d1  call    cs:__imp_WdLogSingleEntry1
0x1402543d8  nop     dword ptr [rax+rax+00h]
0x1402543dd  mov     cs:WdLogGlobalForLineNumber, 62Eh
0x1402543e7  xor     al, al
0x1402543e9  jmp     loc_1402546AB
0x1402543ee  cmp     [rsp+2E0h+TokenInformation], r13
0x1402543f3  jnz     short loc_1402543FB
0x1402543f5  cmp     r15d, 5
0x1402543f9  jnz     short loc_1402543E7
0x1402543fb  cmp     r12b, sil
0x1402543fe  jz      short loc_1402543E7
0x140254400  mov     [rbp+1E0h+var_240], 1A0018h
0x140254408  lea     rax, aHevcplayback; "hevcPlayback"
0x14025440f  mov     [rbp+1E0h+var_238], rax
0x140254413  lea     rax, aExpandedresour; "expandedResources"
0x14025441a  mov     [rbp+1E0h+var_228], rax
0x14025441e  mov     [rbp+1E0h+var_230], 240022h
0x140254426  mov     [rsp+2E0h+var_290], r13b
0x14025442b  mov     [rsp+2E0h+var_28F], r13b
0x140254430  cmp     r15d, 5
0x140254434  jz      short loc_140254476
0x140254436  lea     r8, [rsp+2E0h+var_290]
0x14025443b  xor     ecx, ecx
0x14025443d  lea     rdx, [rbp+1E0h+var_240]
0x140254441  call    cs:__imp_RtlCapabilityCheck
0x140254448  nop     dword ptr [rax+rax+00h]
0x14025444d  test    eax, eax
0x14025444f  jns     short loc_140254456
0x140254451  mov     [rsp+2E0h+var_290], r13b
0x140254456  lea     r8, [rsp+2E0h+var_28F]
0x14025445b  xor     ecx, ecx
0x14025445d  lea     rdx, [rbp+1E0h+var_230]
0x140254461  call    cs:__imp_RtlCapabilityCheck
0x140254468  nop     dword ptr [rax+rax+00h]
0x14025446d  test    eax, eax
0x14025446f  jns     short loc_140254476
0x140254471  mov     [rsp+2E0h+var_28F], r13b
0x140254476  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14025447b  cmp     [rax+4A700h], r13b
0x140254482  jz      loc_140254697
0x140254488  cmp     [rsp+2E0h+var_290], r13b
0x14025448d  jnz     loc_14025469E
0x140254493  cmp     [rsp+2E0h+var_28F], r13b
0x140254498  jnz     loc_1402546A5
0x14025449e  mov     rcx, r14; Process
0x1402544a1  mov     [rbp+1E0h+var_260], 100h
0x1402544a9  mov     [rsp+2E0h+var_28E], r13b
0x1402544ae  call    cs:__imp_PsReferencePrimaryToken
0x1402544b5  nop     dword ptr [rax+rax+00h]
0x1402544ba  xor     r9d, r9d
0x1402544bd  lea     r8, [rbp+1E0h+var_260]
0x1402544c1  mov     rdi, rax
0x1402544c4  lea     rdx, [rbp+1E0h+Src]
0x1402544c8  lea     rax, [rsp+2E0h+var_28E]
0x1402544cd  mov     rcx, rdi
0x1402544d0  mov     [rsp+2E0h+var_2B8], rax
0x1402544d5  mov     [rsp+2E0h+var_2C0], r13
0x1402544da  call    cs:__imp_RtlQueryPackageIdentity
0x1402544e1  nop     dword ptr [rax+rax+00h]
0x1402544e6  mov     rcx, rdi; PrimaryToken
0x1402544e9  mov     ebx, eax
0x1402544eb  call    cs:__imp_PsDereferencePrimaryToken
0x1402544f2  nop     dword ptr [rax+rax+00h]
0x1402544f7  test    ebx, ebx
0x1402544f9  js      loc_140254697
0x1402544ff  cmp     [rsp+2E0h+var_28E], r13b
0x140254504  jz      loc_140254697
0x14025450a  xorps   xmm0, xmm0
0x14025450d  mov     [rsp+2E0h+var_280], 820000h
0x140254516  lea     rax, [rbp+1E0h+var_E0]
0x14025451d  mov     dx, 5Fh ; '_'
0x140254521  mov     [rsp+2E0h+var_278], rax
0x140254526  mov     r8d, 82h
0x14025452c  movzx   eax, [rbp+1E0h+Src]
0x140254530  mov     r15d, r13d
0x140254533  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.Length], xmm0
0x140254537  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x14025453b  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14025453f  cmp     ax, dx
0x140254542  jz      short loc_14025455D
0x140254544  lea     rcx, [rbp+1E0h+Src]
0x140254548  test    ax, ax
0x14025454b  jz      short loc_14025455D
0x14025454d  add     rcx, 2
0x140254551  add     r15d, 2
0x140254555  movzx   eax, word ptr [rcx]
0x140254558  cmp     ax, dx
0x14025455b  jnz     short loc_140254548
0x14025455d  mov     rax, [rbp+1E0h+var_260]
0x140254561  mov     r14d, r13d
0x140254564  lea     rdi, [rbp+rax+1E0h+DestinationString.Buffer+6]
0x140254569  jmp     short loc_14025457C
0x14025456b  lea     rax, [rbp+1E0h+Src]
0x14025456f  cmp     rdi, rax
0x140254572  jz      short loc_140254581
0x140254574  add     r14d, 2
0x140254578  sub     rdi, 2
0x14025457c  cmp     [rdi], dx
0x14025457f  jnz     short loc_14025456B
0x140254581  lea     ecx, [r14+r15]
0x140254585  add     rcx, 2
0x140254589  cmp     rcx, r8
0x14025458c  ja      loc_140254697
0x140254592  xorps   xmm0, xmm0
0x140254595  mov     r8d, r15d; Size
0x140254598  lea     rdx, [rbp+1E0h+Src]; Src
0x14025459c  mov     [rsp+2E0h+KeyHandle], r13
0x1402545a1  lea     rcx, [rbp+1E0h+var_E0]; void *
0x1402545a8  mov     ebx, r15d
0x1402545ab  movups  xmmword ptr [rbp-10h], xmm0
0x1402545af  call    memmove
0x1402545b4  mov     rcx, [rsp+2E0h+var_278]
0x1402545b9  mov     rdx, rdi; Src
0x1402545bc  mov     r8d, r14d
0x1402545bf  add     rcx, rbx; void *
0x1402545c2  add     r8, 2; Size
0x1402545c6  call    memmove
0x1402545cb  add     r14w, r15w
0x1402545cf  lea     rdx, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\OSDATA\\Software\\"...
0x1402545d6  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x1402545da  mov     word ptr [rsp+2E0h+var_280], r14w
0x1402545e0  call    cs:__imp_RtlInitUnicodeString
0x1402545e7  nop     dword ptr [rax+rax+00h]
0x1402545ec  lea     rax, [rbp+1E0h+DestinationString]
0x1402545f0  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], r13
0x1402545f4  xorps   xmm0, xmm0
0x1402545f7  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x1402545fb  mov     r14d, 20019h
0x140254601  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x140254605  mov     ebx, 30h ; '0'
0x14025460a  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x14025460f  mov     edi, 240h
0x140254614  mov     [rbp+1E0h+ObjectAttributes.Length], ebx
0x140254617  mov     edx, r14d; DesiredAccess
0x14025461a  mov     [rbp+1E0h+ObjectAttributes.Attributes], edi
0x14025461d  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140254622  call    cs:__imp_ZwOpenKey
0x140254629  nop     dword ptr [rax+rax+00h]
0x14025462e  test    eax, eax
0x140254630  js      short loc_140254697
0x140254632  mov     rax, [rsp+2E0h+KeyHandle]
0x140254637  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x14025463b  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], rax
0x14025463f  lea     rcx, [rbp+1E0h+Handle]; KeyHandle
0x140254643  lea     rax, [rsp+2E0h+var_280]
0x140254648  mov     [rbp+1E0h+Handle], r13
0x14025464c  xorps   xmm0, xmm0
0x14025464f  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x140254653  mov     edx, r14d; DesiredAccess
0x140254656  mov     [rbp+1E0h+ObjectAttributes.Length], ebx
0x140254659  mov     [rbp+1E0h+ObjectAttributes.Attributes], edi
0x14025465c  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140254661  call    cs:__imp_ZwOpenKey
0x140254668  nop     dword ptr [rax+rax+00h]
0x14025466d  test    eax, eax
0x14025466f  js      short loc_140254686
0x140254671  mov     rcx, [rbp+1E0h+Handle]; Handle
0x140254675  mov     [rsp+2E0h+var_290], sil
0x14025467a  call    cs:__imp_ZwClose
0x140254681  nop     dword ptr [rax+rax+00h]
0x140254686  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x14025468b  call    cs:__imp_ZwClose
0x140254692  nop     dword ptr [rax+rax+00h]
0x140254697  cmp     [rsp+2E0h+var_290], r13b
0x14025469c  jz      short loc_1402546A5
0x14025469e  cmp     [rsp+2E0h+var_28F], r13b
0x1402546a3  jz      short loc_1402546A8
0x1402546a5  mov     sil, r13b
0x1402546a8  mov     al, sil
0x1402546ab  mov     rcx, [rbp+1E0h+var_50]
0x1402546b2  xor     rcx, rsp; StackCookie
0x1402546b5  call    __security_check_cookie
0x1402546ba  add     rsp, 2A8h
0x1402546c1  pop     r15
0x1402546c3  pop     r14
0x1402546c5  pop     r13
0x1402546c7  pop     r12
0x1402546c9  pop     rdi
0x1402546ca  pop     rsi
0x1402546cb  pop     rbx
0x1402546cc  pop     rbp
0x1402546cd  retn
```
