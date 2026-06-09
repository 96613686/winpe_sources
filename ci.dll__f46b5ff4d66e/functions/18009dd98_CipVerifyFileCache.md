# CipVerifyFileCache

- ea: `0x18009dd98`
- end: `0x18009e20b`
- name: `CipVerifyFileCache`
- size: `1139`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009d178`

## callees

- `0x18000ead4`
- `0x18002c860`
- `0x180057fb0`
- `0x18005802c`
- `0x18009dd98`
- `0x18009e670`
- `0x1800a0b64`
- `0x1800e77b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009deaf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009deaf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18009deee`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18009deee`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18009dec4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18009dec4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009defa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009defa`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009de8c`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009de8c`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18009e0cb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e02b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e175`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e193`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e02b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e175`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009e193`
- `ntoskrnl!KdDebuggerEnabled` at `0x18009e0bf`

## pseudocode

```c
__int64 __fastcall CipVerifyFileCache(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _DWORD *ActiveState,
        _DWORD *a7,
        _QWORD *a8)
{
  __int64 v8; // rbx
  _DWORD *v9; // r14
  _QWORD *v10; // r13
  _DWORD *v11; // r15
  int v13; // ecx
  unsigned int v14; // esi
  __int64 v15; // rax
  _QWORD *v16; // rdi
  int v17; // ebx
  char v19; // r15
  __int64 v20; // rcx
  int v21; // ebx
  int FoundSecureSetting; // eax
  int v23; // ebx
  _QWORD *v24; // rax
  char v25; // cl
  int v26; // [rsp+60h] [rbp-49h] BYREF
  int v27; // [rsp+64h] [rbp-45h] BYREF
  int v28; // [rsp+68h] [rbp-41h] BYREF
  __int64 v29; // [rsp+70h] [rbp-39h]
  UNICODE_STRING String1; // [rsp+78h] [rbp-31h] BYREF
  UNICODE_STRING v31; // [rsp+88h] [rbp-21h] BYREF
  UNICODE_STRING v32; // [rsp+98h] [rbp-11h] BYREF
  char v33; // [rsp+F0h] [rbp+47h] BYREF
  int v34; // [rsp+108h] [rbp+5Fh]

  v34 = a4;
  v8 = *a1;
  v9 = a7;
  v10 = a8;
  v11 = ActiveState;
  v32.Buffer = L"Microsoft";
  v31.Buffer = L"WindowsLockdownPolicySettings";
  String1.Buffer = L"VerifiedAndReputableAllowUnknown";
  v28 = 0;
  *(_QWORD *)&v32.Length = 1310738;
  *(_QWORD *)&v31.Length = 3932218;
  *(_QWORD *)&String1.Length = 4325440;
  v13 = *(_DWORD *)(v8 + 24);
  v29 = v8;
  v26 = 0;
  v33 = 0;
  v27 = 1;
  *a7 = 1;
  *v10 = 0;
  *v11 = 0;
  if ( (v13 & 0x20) != 0
    && (g_CiDeveloperMode & 0x100) == 0
    && (g_CiDeveloperMode & 0x4000) == 0
    && (g_CiOptions & 8) == 0
    && (!(_BYTE)KdDebuggerEnabled || (_BYTE)KdDebuggerNotPresent == 1) )
  {
    *v9 = 21;
    return (unsigned int)-1073741275;
  }
  v14 = 0;
  if ( (v13 & 0x200) != 0 )
    return v14;
  if ( (v13 & 0x1000) != 0 && (g_CiDeveloperMode & 0x80000) != 0 )
  {
    v25 = *(_BYTE *)(v8 + 7);
    if ( ((v25 - 5) & 0xFC) == 0 && v25 != 7 )
      return v14;
  }
  v15 = *(_QWORD *)(v8 + 16);
  if ( v15 != g_CiBlocklistUpdateTime )
  {
    *v9 = 17;
LABEL_13:
    *v10 = v15;
    return (unsigned int)-1073741275;
  }
  v16 = (_QWORD *)(a2 + 464);
  v14 = FsRtlKernelFsControlFile(a3, 590068, 0, 0, a2 + 464, 64, &v28);
  if ( (v14 & 0x80000000) != 0 )
  {
    *v9 = 19;
    return v14;
  }
  v15 = *(_QWORD *)(v8 + 8);
  if ( v15 != *v16 )
  {
    *v9 = 20;
    goto LABEL_13;
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyHashLock, 0);
  v17 = g_CiPolicyState;
  if ( (g_CiPolicyState & 2) != 0 || (g_CiPolicyState & 0x20) != 0 )
  {
    v19 = *((_BYTE *)a1 + 52);
    if ( (v19 != 32 || memcmp((const void *)a1[7], &g_SiPolicyHash, 0x20u))
      && ((v17 & 0x40000) == 0 || (*(_DWORD *)(v29 + 24) & 0x8000) == 0 || v19 != 32) )
    {
      v14 = -1073741275;
      *v9 = v19 != 0 ? 22 : 29;
    }
    v11 = ActiveState;
  }
  ExReleasePushLockSharedEx(&g_CipPolicyHashLock, 0);
  KeLeaveCriticalRegion();
  if ( (g_CiPolicyState & 0x4000) != 0
    && (v34 & 0x10) != 0
    && a5
    && (unsigned int)CipSmartlockerHasDangerousOrInstallerExtension(a5) )
  {
    *v9 = 31;
    v14 = -1073741275;
  }
  if ( a1[8] && ((g_CiPolicyState & 0x4000) != 0 || (g_CiPolicyState & 0x20000) != 0) )
  {
    v20 = a1[8];
    if ( MEMORY[0xFFFFF78000000014] <= *(_QWORD *)v20 )
    {
      if ( *(_DWORD *)(v20 + 8) != 1 )
      {
        *v11 |= 0x4000u;
        return v14;
      }
      *v9 = 12;
      *v10 = 1;
      return (unsigned int)-1073741275;
    }
    ActiveState = (_DWORD *)SIPolicyGetActiveState();
    v21 = (int)ActiveState;
    if ( RtlEqualUnicodeString(&String1, &stru_18002EF18, 1u) )
    {
      FoundSecureSetting = SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup(
                             v21,
                             (unsigned int)&v32,
                             (unsigned int)&v31,
                             (unsigned int)&String1,
                             (__int64)&v26,
                             (__int64)&v33,
                             (__int64)&v27);
    }
    else if ( RtlEqualUnicodeString(&v32, &stru_180030DA8, 1u) && RtlEqualUnicodeString(&v31, &stru_180030DB8, 1u) )
    {
      FoundSecureSetting = SIPolicyInternalBooleanSecureSettingRollup(
                             v21,
                             (unsigned int)&v32,
                             (unsigned int)&v31,
                             (unsigned int)&String1,
                             (__int64)&v26,
                             (__int64)&v33,
                             (__int64)&v27);
    }
    else
    {
      FoundSecureSetting = SIPolicyInternalReturnFirstFoundSecureSetting(
                             v21,
                             (unsigned int)&v32,
                             (unsigned int)&v31,
                             (unsigned int)&String1,
                             (__int64)&v26,
                             (__int64)&v33,
                             (__int64)&v27);
    }
    v23 = FoundSecureSetting;
    SIPolicyReleaseState(&ActiveState);
    if ( v23 < 0 || v26 || !v33 )
    {
      v24 = (_QWORD *)a1[8];
      *v9 = 15;
      *v10 = *v24;
      return (unsigned int)-1073741275;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18009dd98  mov     [rsp-8+arg_8], rbx
0x18009dd9d  mov     [rsp-8+arg_18], r9d
0x18009dda2  push    rbp
0x18009dda3  push    rsi
0x18009dda4  push    rdi
0x18009dda5  push    r12
0x18009dda7  push    r13
0x18009dda9  push    r14
0x18009ddab  push    r15
0x18009ddad  lea     rbp, [rsp-7]
0x18009ddb2  sub     rsp, 0B0h
0x18009ddb9  mov     rbx, [rcx]
0x18009ddbc  lea     rax, aMicrosoft; "Microsoft"
0x18009ddc3  mov     r14, [rbp+37h+arg_30]
0x18009ddc7  mov     r10, r8
0x18009ddca  mov     r13, [rbp+37h+arg_38]
0x18009ddce  xor     r8d, r8d
0x18009ddd1  mov     r15, [rbp+37h+arg_28]
0x18009ddd5  mov     r12, rcx
0x18009ddd8  mov     [rbp+37h+var_48.Buffer], rax
0x18009dddc  lea     rax, aWindowslockdow; "WindowsLockdownPolicySettings"
0x18009dde3  mov     [rbp+37h+var_58.Buffer], rax
0x18009dde7  lea     rax, aVerifiedandrep; "VerifiedAndReputableAllowUnknown"
0x18009ddee  mov     [rbp+37h+String1.Buffer], rax
0x18009ddf2  lea     r9d, [r8+40h]
0x18009ddf6  mov     [rbp+37h+var_78], r8d
0x18009ddfa  mov     qword ptr [rbp+37h+var_48.Length], 140012h
0x18009de02  mov     qword ptr [rbp+37h+var_58.Length], 3C003Ah
0x18009de0a  mov     qword ptr [rbp+37h+String1.Length], 420040h
0x18009de12  mov     ecx, [rbx+18h]
0x18009de15  mov     [rbp+37h+var_70], rbx
0x18009de19  mov     [rbp+37h+var_80], r8d
0x18009de1d  mov     [rbp+37h+arg_0], r8b
0x18009de21  mov     [rbp+37h+var_7C], 1
0x18009de28  mov     dword ptr [r14], 1
0x18009de2f  mov     [r13+0], r8
0x18009de33  mov     [r15], r8d
0x18009de36  test    cl, 20h
0x18009de39  jnz     loc_18009E097
0x18009de3f  mov     esi, r8d
0x18009de42  bt      ecx, 9
0x18009de46  jb      loc_18009DF1E
0x18009de4c  bt      ecx, 0Ch
0x18009de50  jb      loc_18009E12C
0x18009de56  mov     rax, [rbx+10h]
0x18009de5a  cmp     rax, cs:g_CiBlocklistUpdateTime
0x18009de61  jnz     loc_18009DF3C
0x18009de67  lea     rdi, [rdx+1D0h]
0x18009de6e  mov     rcx, r10
0x18009de71  lea     rax, [rbp+37h+var_78]
0x18009de75  mov     edx, 900F4h
0x18009de7a  mov     [rsp+0E0h+var_B0], rax
0x18009de7f  mov     dword ptr [rsp+0E0h+var_B8], r9d
0x18009de84  xor     r9d, r9d
0x18009de87  mov     [rsp+0E0h+var_C0], rdi
0x18009de8c  call    cs:__imp_FsRtlKernelFsControlFile
0x18009de93  nop     dword ptr [rax+rax+00h]
0x18009de98  mov     esi, eax
0x18009de9a  test    eax, eax
0x18009de9c  js      loc_18009DF4E
0x18009dea2  mov     rax, [rbx+8]
0x18009dea6  cmp     rax, [rdi]
0x18009dea9  jnz     loc_18009DFB4
0x18009deaf  call    cs:__imp_KeEnterCriticalRegion
0x18009deb6  nop     dword ptr [rax+rax+00h]
0x18009debb  xor     edx, edx
0x18009debd  lea     rcx, g_CipPolicyHashLock
0x18009dec4  call    cs:__imp_ExAcquirePushLockSharedEx
0x18009decb  nop     dword ptr [rax+rax+00h]
0x18009ded0  mov     ebx, cs:g_CiPolicyState
0x18009ded6  mov     edi, 0C0000225h
0x18009dedb  test    bl, 2
0x18009dede  jnz     short loc_18009DF57
0x18009dee0  test    bl, 20h
0x18009dee3  jnz     short loc_18009DF57
0x18009dee5  xor     edx, edx
0x18009dee7  lea     rcx, g_CipPolicyHashLock
0x18009deee  call    cs:__imp_ExReleasePushLockSharedEx
0x18009def5  nop     dword ptr [rax+rax+00h]
0x18009defa  call    cs:__imp_KeLeaveCriticalRegion
0x18009df01  nop     dword ptr [rax+rax+00h]
0x18009df06  test    cs:g_CiPolicyState, 4000h
0x18009df10  jnz     short loc_18009DF86
0x18009df12  cmp     qword ptr [r12+40h], 0
0x18009df18  jnz     loc_18009DFE6
0x18009df1e  mov     rbx, [rsp+0E0h+arg_8]
0x18009df26  mov     eax, esi
0x18009df28  add     rsp, 0B0h
0x18009df2f  pop     r15
0x18009df31  pop     r14
0x18009df33  pop     r13
0x18009df35  pop     r12
0x18009df37  pop     rdi
0x18009df38  pop     rsi
0x18009df39  pop     rbp
0x18009df3a  retn
0x18009df3c  mov     dword ptr [r14], 11h
0x18009df43  mov     [r13+0], rax
0x18009df47  mov     esi, 0C0000225h
0x18009df4c  jmp     short loc_18009DF1E
0x18009df4e  mov     dword ptr [r14], 13h
0x18009df55  jmp     short loc_18009DF1E
0x18009df57  mov     r15b, [r12+34h]
0x18009df5c  cmp     r15b, 20h ; ' '
0x18009df60  jnz     short loc_18009DFBD
0x18009df62  mov     rcx, [r12+38h]; Buf1
0x18009df67  lea     rdx, g_SiPolicyHash; Buf2
0x18009df6e  mov     r8d, 20h ; ' '; Size
0x18009df74  call    memcmp
0x18009df79  test    eax, eax
0x18009df7b  jnz     short loc_18009DFBD
0x18009df7d  mov     r15, [rbp+37h+arg_28]
0x18009df81  jmp     loc_18009DEE5
0x18009df86  test    byte ptr [rbp+37h+arg_18], 10h
0x18009df8a  jz      short loc_18009DF12
0x18009df8c  mov     rcx, [rbp+37h+arg_20]
0x18009df90  test    rcx, rcx
0x18009df93  jz      loc_18009DF12
0x18009df99  call    CipSmartlockerHasDangerousOrInstallerExtension
0x18009df9e  test    eax, eax
0x18009dfa0  jz      loc_18009DF12
0x18009dfa6  mov     dword ptr [r14], 1Fh
0x18009dfad  mov     esi, edi
0x18009dfaf  jmp     loc_18009DF12
0x18009dfb4  mov     dword ptr [r14], 14h
0x18009dfbb  jmp     short loc_18009DF43
0x18009dfbd  bt      ebx, 12h
0x18009dfc1  jnb     short loc_18009DFD4
0x18009dfc3  mov     rax, [rbp+37h+var_70]
0x18009dfc7  test    dword ptr [rax+18h], 8000h
0x18009dfce  jnz     loc_18009E0F9
0x18009dfd4  neg     r15b
0x18009dfd7  mov     esi, edi
0x18009dfd9  sbb     eax, eax
0x18009dfdb  and     eax, 0FFFFFFF9h
0x18009dfde  add     eax, 1Dh
0x18009dfe1  mov     [r14], eax
0x18009dfe4  jmp     short loc_18009DF7D
0x18009dfe6  mov     eax, cs:g_CiPolicyState
0x18009dfec  bt      eax, 0Eh
0x18009dff0  jnb     loc_18009E158
0x18009dff6  mov     rax, 0FFFFF78000000014h
0x18009e000  mov     rax, [rax]
0x18009e003  mov     rcx, [r12+40h]
0x18009e008  cmp     rax, [rcx]
0x18009e00b  jle     loc_18009E108
0x18009e011  call    SIPolicyGetActiveState
0x18009e016  mov     r8b, 1; CaseInSensitive
0x18009e019  mov     [rbp+37h+arg_28], rax
0x18009e01d  lea     rdx, stru_18002EF18; String2
0x18009e024  mov     rbx, rax
0x18009e027  lea     rcx, [rbp+37h+String1]; String1
0x18009e02b  call    cs:__imp_RtlEqualUnicodeString
0x18009e032  nop     dword ptr [rax+rax+00h]
0x18009e037  test    al, al
0x18009e039  jz      loc_18009E167
0x18009e03f  lea     rax, [rbp+37h+var_7C]
0x18009e043  mov     rcx, rbx
0x18009e046  mov     [rsp+0E0h+var_B0], rax
0x18009e04b  lea     r9, [rbp+37h+String1]
0x18009e04f  lea     rax, [rbp+37h+arg_0]
0x18009e053  mov     [rsp+0E0h+var_B8], rax
0x18009e058  lea     r8, [rbp+37h+var_58]
0x18009e05c  lea     rax, [rbp+37h+var_80]
0x18009e060  lea     rdx, [rbp+37h+var_48]
0x18009e064  mov     [rsp+0E0h+var_C0], rax
0x18009e069  call    SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup
0x18009e06e  mov     ebx, eax
0x18009e070  lea     rcx, [rbp+37h+arg_28]
0x18009e074  call    SIPolicyReleaseState
0x18009e079  test    ebx, ebx
0x18009e07b  jns     short loc_18009E0E7
0x18009e07d  mov     rax, [r12+40h]
0x18009e082  mov     dword ptr [r14], 0Fh
0x18009e089  mov     rcx, [rax]
0x18009e08c  mov     [r13+0], rcx
0x18009e090  mov     esi, edi
0x18009e092  jmp     loc_18009DF1E
0x18009e097  mov     eax, cs:g_CiDeveloperMode
0x18009e09d  bt      eax, 8
0x18009e0a1  jb      loc_18009DE3F
0x18009e0a7  bt      eax, 0Eh
0x18009e0ab  jb      loc_18009DE3F
0x18009e0b1  mov     eax, cs:g_CiOptions
0x18009e0b7  test    al, 8
0x18009e0b9  jnz     loc_18009DE3F
0x18009e0bf  mov     rax, cs:KdDebuggerEnabled
0x18009e0c6  cmp     [rax], r8b
0x18009e0c9  jz      short loc_18009E0DB
0x18009e0cb  mov     rax, cs:KdDebuggerNotPresent
0x18009e0d2  cmp     byte ptr [rax], 1
0x18009e0d5  jnz     loc_18009DE3F
0x18009e0db  mov     dword ptr [r14], 15h
0x18009e0e2  jmp     loc_18009DF47
0x18009e0e7  cmp     [rbp+37h+var_80], 0
0x18009e0eb  jnz     short loc_18009E07D
0x18009e0ed  cmp     [rbp+37h+arg_0], 0
0x18009e0f1  jnz     loc_18009DF1E
0x18009e0f7  jmp     short loc_18009E07D
0x18009e0f9  cmp     r15b, 20h ; ' '
0x18009e0fd  jz      loc_18009DF7D
0x18009e103  jmp     loc_18009DFD4
0x18009e108  cmp     dword ptr [rcx+8], 1
0x18009e10c  jnz     short loc_18009E122
0x18009e10e  mov     dword ptr [r14], 0Ch
0x18009e115  mov     qword ptr [r13+0], 1
0x18009e11d  jmp     loc_18009E090
0x18009e122  bts     dword ptr [r15], 0Eh
0x18009e127  jmp     loc_18009DF1E
0x18009e12c  test    cs:g_CiDeveloperMode, 80000h
0x18009e136  jz      loc_18009DE56
0x18009e13c  mov     cl, [rbx+7]
0x18009e13f  lea     eax, [rcx-5]
0x18009e142  test    al, 0FCh
0x18009e144  jnz     loc_18009DE56
0x18009e14a  cmp     cl, 7
0x18009e14d  jnz     loc_18009DF1E
0x18009e153  jmp     loc_18009DE56
0x18009e158  bt      eax, 11h
0x18009e15c  jnb     loc_18009DF1E
0x18009e162  jmp     loc_18009DFF6
0x18009e167  mov     r8b, 1; CaseInSensitive
0x18009e16a  lea     rdx, stru_180030DA8; String2
0x18009e171  lea     rcx, [rbp+37h+var_48]; String1
0x18009e175  call    cs:__imp_RtlEqualUnicodeString
0x18009e17c  nop     dword ptr [rax+rax+00h]
0x18009e181  test    al, al
0x18009e183  jz      short loc_18009E1D7
0x18009e185  mov     r8b, 1; CaseInSensitive
0x18009e188  lea     rdx, stru_180030DB8; String2
0x18009e18f  lea     rcx, [rbp+37h+var_58]; String1
0x18009e193  call    cs:__imp_RtlEqualUnicodeString
0x18009e19a  nop     dword ptr [rax+rax+00h]
0x18009e19f  test    al, al
0x18009e1a1  jz      short loc_18009E1D7
0x18009e1a3  lea     rax, [rbp+37h+var_7C]
0x18009e1a7  mov     rcx, rbx
0x18009e1aa  mov     [rsp+0E0h+var_B0], rax
0x18009e1af  lea     r9, [rbp+37h+String1]
0x18009e1b3  lea     rax, [rbp+37h+arg_0]
0x18009e1b7  mov     [rsp+0E0h+var_B8], rax
0x18009e1bc  lea     r8, [rbp+37h+var_58]
0x18009e1c0  lea     rax, [rbp+37h+var_80]
0x18009e1c4  lea     rdx, [rbp+37h+var_48]
0x18009e1c8  mov     [rsp+0E0h+var_C0], rax
0x18009e1cd  call    SIPolicyInternalBooleanSecureSettingRollup
0x18009e1d2  jmp     loc_18009E06E
0x18009e1d7  lea     rax, [rbp+37h+var_7C]
0x18009e1db  mov     rcx, rbx
0x18009e1de  mov     [rsp+0E0h+var_B0], rax
0x18009e1e3  lea     r9, [rbp+37h+String1]
0x18009e1e7  lea     rax, [rbp+37h+arg_0]
0x18009e1eb  mov     [rsp+0E0h+var_B8], rax
0x18009e1f0  lea     r8, [rbp+37h+var_58]
0x18009e1f4  lea     rax, [rbp+37h+var_80]
0x18009e1f8  lea     rdx, [rbp+37h+var_48]
0x18009e1fc  mov     [rsp+0E0h+var_C0], rax
0x18009e201  call    SIPolicyInternalReturnFirstFoundSecureSetting
0x18009e206  jmp     loc_18009E06E
```
