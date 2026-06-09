# CipVerifyFileCache

- ea: `0x180090654`
- end: `0x180090ac7`
- name: `CipVerifyFileCache`
- size: `1139`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008fa34`

## callees

- `0x18000eae4`
- `0x18002ca20`
- `0x180058bf0`
- `0x180058c6c`
- `0x180090654`
- `0x180090f2c`
- `0x1800ad228`
- `0x1800e9414`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009076b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009076b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800907aa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800907aa`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180090780`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180090780`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800907b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800907b6`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x180090748`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x180090748`
- `ntoskrnl!KdDebuggerNotPresent` at `0x180090987`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800908e7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180090a31`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180090a4f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800908e7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180090a31`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180090a4f`
- `ntoskrnl!KdDebuggerEnabled` at `0x18009097b`

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
    if ( RtlEqualUnicodeString(&String1, &stru_18002E4C0, 1u) )
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
    else if ( RtlEqualUnicodeString(&v32, &stru_180030E38, 1u) && RtlEqualUnicodeString(&v31, &stru_180030E48, 1u) )
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
0x180090654  mov     [rsp-8+arg_8], rbx
0x180090659  mov     [rsp-8+arg_18], r9d
0x18009065e  push    rbp
0x18009065f  push    rsi
0x180090660  push    rdi
0x180090661  push    r12
0x180090663  push    r13
0x180090665  push    r14
0x180090667  push    r15
0x180090669  lea     rbp, [rsp-7]
0x18009066e  sub     rsp, 0B0h
0x180090675  mov     rbx, [rcx]
0x180090678  lea     rax, aMicrosoft; "Microsoft"
0x18009067f  mov     r14, [rbp+37h+arg_30]
0x180090683  mov     r10, r8
0x180090686  mov     r13, [rbp+37h+arg_38]
0x18009068a  xor     r8d, r8d
0x18009068d  mov     r15, [rbp+37h+arg_28]
0x180090691  mov     r12, rcx
0x180090694  mov     [rbp+37h+var_48.Buffer], rax
0x180090698  lea     rax, aWindowslockdow; "WindowsLockdownPolicySettings"
0x18009069f  mov     [rbp+37h+var_58.Buffer], rax
0x1800906a3  lea     rax, aVerifiedandrep; "VerifiedAndReputableAllowUnknown"
0x1800906aa  mov     [rbp+37h+String1.Buffer], rax
0x1800906ae  lea     r9d, [r8+40h]
0x1800906b2  mov     [rbp+37h+var_78], r8d
0x1800906b6  mov     qword ptr [rbp+37h+var_48.Length], 140012h
0x1800906be  mov     qword ptr [rbp+37h+var_58.Length], 3C003Ah
0x1800906c6  mov     qword ptr [rbp+37h+String1.Length], 420040h
0x1800906ce  mov     ecx, [rbx+18h]
0x1800906d1  mov     [rbp+37h+var_70], rbx
0x1800906d5  mov     [rbp+37h+var_80], r8d
0x1800906d9  mov     [rbp+37h+arg_0], r8b
0x1800906dd  mov     [rbp+37h+var_7C], 1
0x1800906e4  mov     dword ptr [r14], 1
0x1800906eb  mov     [r13+0], r8
0x1800906ef  mov     [r15], r8d
0x1800906f2  test    cl, 20h
0x1800906f5  jnz     loc_180090953
0x1800906fb  mov     esi, r8d
0x1800906fe  bt      ecx, 9
0x180090702  jb      loc_1800907DA
0x180090708  bt      ecx, 0Ch
0x18009070c  jb      loc_1800909E8
0x180090712  mov     rax, [rbx+10h]
0x180090716  cmp     rax, cs:g_CiBlocklistUpdateTime
0x18009071d  jnz     loc_1800907F8
0x180090723  lea     rdi, [rdx+1D0h]
0x18009072a  mov     rcx, r10
0x18009072d  lea     rax, [rbp+37h+var_78]
0x180090731  mov     edx, 900F4h
0x180090736  mov     [rsp+0E0h+var_B0], rax
0x18009073b  mov     dword ptr [rsp+0E0h+var_B8], r9d
0x180090740  xor     r9d, r9d
0x180090743  mov     [rsp+0E0h+var_C0], rdi
0x180090748  call    cs:__imp_FsRtlKernelFsControlFile
0x18009074f  nop     dword ptr [rax+rax+00h]
0x180090754  mov     esi, eax
0x180090756  test    eax, eax
0x180090758  js      loc_18009080A
0x18009075e  mov     rax, [rbx+8]
0x180090762  cmp     rax, [rdi]
0x180090765  jnz     loc_180090870
0x18009076b  call    cs:__imp_KeEnterCriticalRegion
0x180090772  nop     dword ptr [rax+rax+00h]
0x180090777  xor     edx, edx
0x180090779  lea     rcx, g_CipPolicyHashLock
0x180090780  call    cs:__imp_ExAcquirePushLockSharedEx
0x180090787  nop     dword ptr [rax+rax+00h]
0x18009078c  mov     ebx, cs:g_CiPolicyState
0x180090792  mov     edi, 0C0000225h
0x180090797  test    bl, 2
0x18009079a  jnz     short loc_180090813
0x18009079c  test    bl, 20h
0x18009079f  jnz     short loc_180090813
0x1800907a1  xor     edx, edx
0x1800907a3  lea     rcx, g_CipPolicyHashLock
0x1800907aa  call    cs:__imp_ExReleasePushLockSharedEx
0x1800907b1  nop     dword ptr [rax+rax+00h]
0x1800907b6  call    cs:__imp_KeLeaveCriticalRegion
0x1800907bd  nop     dword ptr [rax+rax+00h]
0x1800907c2  test    cs:g_CiPolicyState, 4000h
0x1800907cc  jnz     short loc_180090842
0x1800907ce  cmp     qword ptr [r12+40h], 0
0x1800907d4  jnz     loc_1800908A2
0x1800907da  mov     rbx, [rsp+0E0h+arg_8]
0x1800907e2  mov     eax, esi
0x1800907e4  add     rsp, 0B0h
0x1800907eb  pop     r15
0x1800907ed  pop     r14
0x1800907ef  pop     r13
0x1800907f1  pop     r12
0x1800907f3  pop     rdi
0x1800907f4  pop     rsi
0x1800907f5  pop     rbp
0x1800907f6  retn
0x1800907f8  mov     dword ptr [r14], 11h
0x1800907ff  mov     [r13+0], rax
0x180090803  mov     esi, 0C0000225h
0x180090808  jmp     short loc_1800907DA
0x18009080a  mov     dword ptr [r14], 13h
0x180090811  jmp     short loc_1800907DA
0x180090813  mov     r15b, [r12+34h]
0x180090818  cmp     r15b, 20h ; ' '
0x18009081c  jnz     short loc_180090879
0x18009081e  mov     rcx, [r12+38h]; Buf1
0x180090823  lea     rdx, g_SiPolicyHash; Buf2
0x18009082a  mov     r8d, 20h ; ' '; Size
0x180090830  call    memcmp
0x180090835  test    eax, eax
0x180090837  jnz     short loc_180090879
0x180090839  mov     r15, [rbp+37h+arg_28]
0x18009083d  jmp     loc_1800907A1
0x180090842  test    byte ptr [rbp+37h+arg_18], 10h
0x180090846  jz      short loc_1800907CE
0x180090848  mov     rcx, [rbp+37h+arg_20]
0x18009084c  test    rcx, rcx
0x18009084f  jz      loc_1800907CE
0x180090855  call    CipSmartlockerHasDangerousOrInstallerExtension
0x18009085a  test    eax, eax
0x18009085c  jz      loc_1800907CE
0x180090862  mov     dword ptr [r14], 1Fh
0x180090869  mov     esi, edi
0x18009086b  jmp     loc_1800907CE
0x180090870  mov     dword ptr [r14], 14h
0x180090877  jmp     short loc_1800907FF
0x180090879  bt      ebx, 12h
0x18009087d  jnb     short loc_180090890
0x18009087f  mov     rax, [rbp+37h+var_70]
0x180090883  test    dword ptr [rax+18h], 8000h
0x18009088a  jnz     loc_1800909B5
0x180090890  neg     r15b
0x180090893  mov     esi, edi
0x180090895  sbb     eax, eax
0x180090897  and     eax, 0FFFFFFF9h
0x18009089a  add     eax, 1Dh
0x18009089d  mov     [r14], eax
0x1800908a0  jmp     short loc_180090839
0x1800908a2  mov     eax, cs:g_CiPolicyState
0x1800908a8  bt      eax, 0Eh
0x1800908ac  jnb     loc_180090A14
0x1800908b2  mov     rax, 0FFFFF78000000014h
0x1800908bc  mov     rax, [rax]
0x1800908bf  mov     rcx, [r12+40h]
0x1800908c4  cmp     rax, [rcx]
0x1800908c7  jle     loc_1800909C4
0x1800908cd  call    SIPolicyGetActiveState
0x1800908d2  mov     r8b, 1; CaseInSensitive
0x1800908d5  mov     [rbp+37h+arg_28], rax
0x1800908d9  lea     rdx, stru_18002E4C0; String2
0x1800908e0  mov     rbx, rax
0x1800908e3  lea     rcx, [rbp+37h+String1]; String1
0x1800908e7  call    cs:__imp_RtlEqualUnicodeString
0x1800908ee  nop     dword ptr [rax+rax+00h]
0x1800908f3  test    al, al
0x1800908f5  jz      loc_180090A23
0x1800908fb  lea     rax, [rbp+37h+var_7C]
0x1800908ff  mov     rcx, rbx
0x180090902  mov     [rsp+0E0h+var_B0], rax
0x180090907  lea     r9, [rbp+37h+String1]
0x18009090b  lea     rax, [rbp+37h+arg_0]
0x18009090f  mov     [rsp+0E0h+var_B8], rax
0x180090914  lea     r8, [rbp+37h+var_58]
0x180090918  lea     rax, [rbp+37h+var_80]
0x18009091c  lea     rdx, [rbp+37h+var_48]
0x180090920  mov     [rsp+0E0h+var_C0], rax
0x180090925  call    SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup
0x18009092a  mov     ebx, eax
0x18009092c  lea     rcx, [rbp+37h+arg_28]
0x180090930  call    SIPolicyReleaseState
0x180090935  test    ebx, ebx
0x180090937  jns     short loc_1800909A3
0x180090939  mov     rax, [r12+40h]
0x18009093e  mov     dword ptr [r14], 0Fh
0x180090945  mov     rcx, [rax]
0x180090948  mov     [r13+0], rcx
0x18009094c  mov     esi, edi
0x18009094e  jmp     loc_1800907DA
0x180090953  mov     eax, cs:g_CiDeveloperMode
0x180090959  bt      eax, 8
0x18009095d  jb      loc_1800906FB
0x180090963  bt      eax, 0Eh
0x180090967  jb      loc_1800906FB
0x18009096d  mov     eax, cs:g_CiOptions
0x180090973  test    al, 8
0x180090975  jnz     loc_1800906FB
0x18009097b  mov     rax, cs:KdDebuggerEnabled
0x180090982  cmp     [rax], r8b
0x180090985  jz      short loc_180090997
0x180090987  mov     rax, cs:KdDebuggerNotPresent
0x18009098e  cmp     byte ptr [rax], 1
0x180090991  jnz     loc_1800906FB
0x180090997  mov     dword ptr [r14], 15h
0x18009099e  jmp     loc_180090803
0x1800909a3  cmp     [rbp+37h+var_80], 0
0x1800909a7  jnz     short loc_180090939
0x1800909a9  cmp     [rbp+37h+arg_0], 0
0x1800909ad  jnz     loc_1800907DA
0x1800909b3  jmp     short loc_180090939
0x1800909b5  cmp     r15b, 20h ; ' '
0x1800909b9  jz      loc_180090839
0x1800909bf  jmp     loc_180090890
0x1800909c4  cmp     dword ptr [rcx+8], 1
0x1800909c8  jnz     short loc_1800909DE
0x1800909ca  mov     dword ptr [r14], 0Ch
0x1800909d1  mov     qword ptr [r13+0], 1
0x1800909d9  jmp     loc_18009094C
0x1800909de  bts     dword ptr [r15], 0Eh
0x1800909e3  jmp     loc_1800907DA
0x1800909e8  test    cs:g_CiDeveloperMode, 80000h
0x1800909f2  jz      loc_180090712
0x1800909f8  mov     cl, [rbx+7]
0x1800909fb  lea     eax, [rcx-5]
0x1800909fe  test    al, 0FCh
0x180090a00  jnz     loc_180090712
0x180090a06  cmp     cl, 7
0x180090a09  jnz     loc_1800907DA
0x180090a0f  jmp     loc_180090712
0x180090a14  bt      eax, 11h
0x180090a18  jnb     loc_1800907DA
0x180090a1e  jmp     loc_1800908B2
0x180090a23  mov     r8b, 1; CaseInSensitive
0x180090a26  lea     rdx, stru_180030E38; String2
0x180090a2d  lea     rcx, [rbp+37h+var_48]; String1
0x180090a31  call    cs:__imp_RtlEqualUnicodeString
0x180090a38  nop     dword ptr [rax+rax+00h]
0x180090a3d  test    al, al
0x180090a3f  jz      short loc_180090A93
0x180090a41  mov     r8b, 1; CaseInSensitive
0x180090a44  lea     rdx, stru_180030E48; String2
0x180090a4b  lea     rcx, [rbp+37h+var_58]; String1
0x180090a4f  call    cs:__imp_RtlEqualUnicodeString
0x180090a56  nop     dword ptr [rax+rax+00h]
0x180090a5b  test    al, al
0x180090a5d  jz      short loc_180090A93
0x180090a5f  lea     rax, [rbp+37h+var_7C]
0x180090a63  mov     rcx, rbx
0x180090a66  mov     [rsp+0E0h+var_B0], rax
0x180090a6b  lea     r9, [rbp+37h+String1]
0x180090a6f  lea     rax, [rbp+37h+arg_0]
0x180090a73  mov     [rsp+0E0h+var_B8], rax
0x180090a78  lea     r8, [rbp+37h+var_58]
0x180090a7c  lea     rax, [rbp+37h+var_80]
0x180090a80  lea     rdx, [rbp+37h+var_48]
0x180090a84  mov     [rsp+0E0h+var_C0], rax
0x180090a89  call    SIPolicyInternalBooleanSecureSettingRollup
0x180090a8e  jmp     loc_18009092A
0x180090a93  lea     rax, [rbp+37h+var_7C]
0x180090a97  mov     rcx, rbx
0x180090a9a  mov     [rsp+0E0h+var_B0], rax
0x180090a9f  lea     r9, [rbp+37h+String1]
0x180090aa3  lea     rax, [rbp+37h+arg_0]
0x180090aa7  mov     [rsp+0E0h+var_B8], rax
0x180090aac  lea     r8, [rbp+37h+var_58]
0x180090ab0  lea     rax, [rbp+37h+var_80]
0x180090ab4  lea     rdx, [rbp+37h+var_48]
0x180090ab8  mov     [rsp+0E0h+var_C0], rax
0x180090abd  call    SIPolicyInternalReturnFirstFoundSecureSetting
0x180090ac2  jmp     loc_18009092A
```
