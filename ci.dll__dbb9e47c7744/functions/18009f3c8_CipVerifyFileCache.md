# CipVerifyFileCache

- ea: `0x18009f3c8`
- end: `0x18009f83b`
- name: `CipVerifyFileCache`
- size: `1139`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009e7a8`

## callees

- `0x18000ead4`
- `0x18002c8a0`
- `0x180058cc8`
- `0x180058d44`
- `0x18009f3c8`
- `0x18009fca0`
- `0x1800a2194`
- `0x1800e8d5c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009f4df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009f4df`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18009f51e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18009f51e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18009f4f4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18009f4f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f52a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009f52a`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009f4bc`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009f4bc`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18009f6fb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f65b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f7a5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f7c3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f65b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f7a5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18009f7c3`
- `ntoskrnl!KdDebuggerEnabled` at `0x18009f6ef`

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
    else if ( RtlEqualUnicodeString(&v32, &stru_180030E58, 1u) && RtlEqualUnicodeString(&v31, &stru_180030E68, 1u) )
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
0x18009f3c8  mov     [rsp-8+arg_8], rbx
0x18009f3cd  mov     [rsp-8+arg_18], r9d
0x18009f3d2  push    rbp
0x18009f3d3  push    rsi
0x18009f3d4  push    rdi
0x18009f3d5  push    r12
0x18009f3d7  push    r13
0x18009f3d9  push    r14
0x18009f3db  push    r15
0x18009f3dd  lea     rbp, [rsp-7]
0x18009f3e2  sub     rsp, 0B0h
0x18009f3e9  mov     rbx, [rcx]
0x18009f3ec  lea     rax, aMicrosoft; "Microsoft"
0x18009f3f3  mov     r14, [rbp+37h+arg_30]
0x18009f3f7  mov     r10, r8
0x18009f3fa  mov     r13, [rbp+37h+arg_38]
0x18009f3fe  xor     r8d, r8d
0x18009f401  mov     r15, [rbp+37h+arg_28]
0x18009f405  mov     r12, rcx
0x18009f408  mov     [rbp+37h+var_48.Buffer], rax
0x18009f40c  lea     rax, aWindowslockdow; "WindowsLockdownPolicySettings"
0x18009f413  mov     [rbp+37h+var_58.Buffer], rax
0x18009f417  lea     rax, aVerifiedandrep; "VerifiedAndReputableAllowUnknown"
0x18009f41e  mov     [rbp+37h+String1.Buffer], rax
0x18009f422  lea     r9d, [r8+40h]
0x18009f426  mov     [rbp+37h+var_78], r8d
0x18009f42a  mov     qword ptr [rbp+37h+var_48.Length], 140012h
0x18009f432  mov     qword ptr [rbp+37h+var_58.Length], 3C003Ah
0x18009f43a  mov     qword ptr [rbp+37h+String1.Length], 420040h
0x18009f442  mov     ecx, [rbx+18h]
0x18009f445  mov     [rbp+37h+var_70], rbx
0x18009f449  mov     [rbp+37h+var_80], r8d
0x18009f44d  mov     [rbp+37h+arg_0], r8b
0x18009f451  mov     [rbp+37h+var_7C], 1
0x18009f458  mov     dword ptr [r14], 1
0x18009f45f  mov     [r13+0], r8
0x18009f463  mov     [r15], r8d
0x18009f466  test    cl, 20h
0x18009f469  jnz     loc_18009F6C7
0x18009f46f  mov     esi, r8d
0x18009f472  bt      ecx, 9
0x18009f476  jb      loc_18009F54E
0x18009f47c  bt      ecx, 0Ch
0x18009f480  jb      loc_18009F75C
0x18009f486  mov     rax, [rbx+10h]
0x18009f48a  cmp     rax, cs:g_CiBlocklistUpdateTime
0x18009f491  jnz     loc_18009F56C
0x18009f497  lea     rdi, [rdx+1D0h]
0x18009f49e  mov     rcx, r10
0x18009f4a1  lea     rax, [rbp+37h+var_78]
0x18009f4a5  mov     edx, 900F4h
0x18009f4aa  mov     [rsp+0E0h+var_B0], rax
0x18009f4af  mov     dword ptr [rsp+0E0h+var_B8], r9d
0x18009f4b4  xor     r9d, r9d
0x18009f4b7  mov     [rsp+0E0h+var_C0], rdi
0x18009f4bc  call    cs:__imp_FsRtlKernelFsControlFile
0x18009f4c3  nop     dword ptr [rax+rax+00h]
0x18009f4c8  mov     esi, eax
0x18009f4ca  test    eax, eax
0x18009f4cc  js      loc_18009F57E
0x18009f4d2  mov     rax, [rbx+8]
0x18009f4d6  cmp     rax, [rdi]
0x18009f4d9  jnz     loc_18009F5E4
0x18009f4df  call    cs:__imp_KeEnterCriticalRegion
0x18009f4e6  nop     dword ptr [rax+rax+00h]
0x18009f4eb  xor     edx, edx
0x18009f4ed  lea     rcx, g_CipPolicyHashLock
0x18009f4f4  call    cs:__imp_ExAcquirePushLockSharedEx
0x18009f4fb  nop     dword ptr [rax+rax+00h]
0x18009f500  mov     ebx, cs:g_CiPolicyState
0x18009f506  mov     edi, 0C0000225h
0x18009f50b  test    bl, 2
0x18009f50e  jnz     short loc_18009F587
0x18009f510  test    bl, 20h
0x18009f513  jnz     short loc_18009F587
0x18009f515  xor     edx, edx
0x18009f517  lea     rcx, g_CipPolicyHashLock
0x18009f51e  call    cs:__imp_ExReleasePushLockSharedEx
0x18009f525  nop     dword ptr [rax+rax+00h]
0x18009f52a  call    cs:__imp_KeLeaveCriticalRegion
0x18009f531  nop     dword ptr [rax+rax+00h]
0x18009f536  test    cs:g_CiPolicyState, 4000h
0x18009f540  jnz     short loc_18009F5B6
0x18009f542  cmp     qword ptr [r12+40h], 0
0x18009f548  jnz     loc_18009F616
0x18009f54e  mov     rbx, [rsp+0E0h+arg_8]
0x18009f556  mov     eax, esi
0x18009f558  add     rsp, 0B0h
0x18009f55f  pop     r15
0x18009f561  pop     r14
0x18009f563  pop     r13
0x18009f565  pop     r12
0x18009f567  pop     rdi
0x18009f568  pop     rsi
0x18009f569  pop     rbp
0x18009f56a  retn
0x18009f56c  mov     dword ptr [r14], 11h
0x18009f573  mov     [r13+0], rax
0x18009f577  mov     esi, 0C0000225h
0x18009f57c  jmp     short loc_18009F54E
0x18009f57e  mov     dword ptr [r14], 13h
0x18009f585  jmp     short loc_18009F54E
0x18009f587  mov     r15b, [r12+34h]
0x18009f58c  cmp     r15b, 20h ; ' '
0x18009f590  jnz     short loc_18009F5ED
0x18009f592  mov     rcx, [r12+38h]; Buf1
0x18009f597  lea     rdx, g_SiPolicyHash; Buf2
0x18009f59e  mov     r8d, 20h ; ' '; Size
0x18009f5a4  call    memcmp
0x18009f5a9  test    eax, eax
0x18009f5ab  jnz     short loc_18009F5ED
0x18009f5ad  mov     r15, [rbp+37h+arg_28]
0x18009f5b1  jmp     loc_18009F515
0x18009f5b6  test    byte ptr [rbp+37h+arg_18], 10h
0x18009f5ba  jz      short loc_18009F542
0x18009f5bc  mov     rcx, [rbp+37h+arg_20]
0x18009f5c0  test    rcx, rcx
0x18009f5c3  jz      loc_18009F542
0x18009f5c9  call    CipSmartlockerHasDangerousOrInstallerExtension
0x18009f5ce  test    eax, eax
0x18009f5d0  jz      loc_18009F542
0x18009f5d6  mov     dword ptr [r14], 1Fh
0x18009f5dd  mov     esi, edi
0x18009f5df  jmp     loc_18009F542
0x18009f5e4  mov     dword ptr [r14], 14h
0x18009f5eb  jmp     short loc_18009F573
0x18009f5ed  bt      ebx, 12h
0x18009f5f1  jnb     short loc_18009F604
0x18009f5f3  mov     rax, [rbp+37h+var_70]
0x18009f5f7  test    dword ptr [rax+18h], 8000h
0x18009f5fe  jnz     loc_18009F729
0x18009f604  neg     r15b
0x18009f607  mov     esi, edi
0x18009f609  sbb     eax, eax
0x18009f60b  and     eax, 0FFFFFFF9h
0x18009f60e  add     eax, 1Dh
0x18009f611  mov     [r14], eax
0x18009f614  jmp     short loc_18009F5AD
0x18009f616  mov     eax, cs:g_CiPolicyState
0x18009f61c  bt      eax, 0Eh
0x18009f620  jnb     loc_18009F788
0x18009f626  mov     rax, 0FFFFF78000000014h
0x18009f630  mov     rax, [rax]
0x18009f633  mov     rcx, [r12+40h]
0x18009f638  cmp     rax, [rcx]
0x18009f63b  jle     loc_18009F738
0x18009f641  call    SIPolicyGetActiveState
0x18009f646  mov     r8b, 1; CaseInSensitive
0x18009f649  mov     [rbp+37h+arg_28], rax
0x18009f64d  lea     rdx, stru_18002EF18; String2
0x18009f654  mov     rbx, rax
0x18009f657  lea     rcx, [rbp+37h+String1]; String1
0x18009f65b  call    cs:__imp_RtlEqualUnicodeString
0x18009f662  nop     dword ptr [rax+rax+00h]
0x18009f667  test    al, al
0x18009f669  jz      loc_18009F797
0x18009f66f  lea     rax, [rbp+37h+var_7C]
0x18009f673  mov     rcx, rbx
0x18009f676  mov     [rsp+0E0h+var_B0], rax
0x18009f67b  lea     r9, [rbp+37h+String1]
0x18009f67f  lea     rax, [rbp+37h+arg_0]
0x18009f683  mov     [rsp+0E0h+var_B8], rax
0x18009f688  lea     r8, [rbp+37h+var_58]
0x18009f68c  lea     rax, [rbp+37h+var_80]
0x18009f690  lea     rdx, [rbp+37h+var_48]
0x18009f694  mov     [rsp+0E0h+var_C0], rax
0x18009f699  call    SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup
0x18009f69e  mov     ebx, eax
0x18009f6a0  lea     rcx, [rbp+37h+arg_28]
0x18009f6a4  call    SIPolicyReleaseState
0x18009f6a9  test    ebx, ebx
0x18009f6ab  jns     short loc_18009F717
0x18009f6ad  mov     rax, [r12+40h]
0x18009f6b2  mov     dword ptr [r14], 0Fh
0x18009f6b9  mov     rcx, [rax]
0x18009f6bc  mov     [r13+0], rcx
0x18009f6c0  mov     esi, edi
0x18009f6c2  jmp     loc_18009F54E
0x18009f6c7  mov     eax, cs:g_CiDeveloperMode
0x18009f6cd  bt      eax, 8
0x18009f6d1  jb      loc_18009F46F
0x18009f6d7  bt      eax, 0Eh
0x18009f6db  jb      loc_18009F46F
0x18009f6e1  mov     eax, cs:g_CiOptions
0x18009f6e7  test    al, 8
0x18009f6e9  jnz     loc_18009F46F
0x18009f6ef  mov     rax, cs:KdDebuggerEnabled
0x18009f6f6  cmp     [rax], r8b
0x18009f6f9  jz      short loc_18009F70B
0x18009f6fb  mov     rax, cs:KdDebuggerNotPresent
0x18009f702  cmp     byte ptr [rax], 1
0x18009f705  jnz     loc_18009F46F
0x18009f70b  mov     dword ptr [r14], 15h
0x18009f712  jmp     loc_18009F577
0x18009f717  cmp     [rbp+37h+var_80], 0
0x18009f71b  jnz     short loc_18009F6AD
0x18009f71d  cmp     [rbp+37h+arg_0], 0
0x18009f721  jnz     loc_18009F54E
0x18009f727  jmp     short loc_18009F6AD
0x18009f729  cmp     r15b, 20h ; ' '
0x18009f72d  jz      loc_18009F5AD
0x18009f733  jmp     loc_18009F604
0x18009f738  cmp     dword ptr [rcx+8], 1
0x18009f73c  jnz     short loc_18009F752
0x18009f73e  mov     dword ptr [r14], 0Ch
0x18009f745  mov     qword ptr [r13+0], 1
0x18009f74d  jmp     loc_18009F6C0
0x18009f752  bts     dword ptr [r15], 0Eh
0x18009f757  jmp     loc_18009F54E
0x18009f75c  test    cs:g_CiDeveloperMode, 80000h
0x18009f766  jz      loc_18009F486
0x18009f76c  mov     cl, [rbx+7]
0x18009f76f  lea     eax, [rcx-5]
0x18009f772  test    al, 0FCh
0x18009f774  jnz     loc_18009F486
0x18009f77a  cmp     cl, 7
0x18009f77d  jnz     loc_18009F54E
0x18009f783  jmp     loc_18009F486
0x18009f788  bt      eax, 11h
0x18009f78c  jnb     loc_18009F54E
0x18009f792  jmp     loc_18009F626
0x18009f797  mov     r8b, 1; CaseInSensitive
0x18009f79a  lea     rdx, stru_180030E58; String2
0x18009f7a1  lea     rcx, [rbp+37h+var_48]; String1
0x18009f7a5  call    cs:__imp_RtlEqualUnicodeString
0x18009f7ac  nop     dword ptr [rax+rax+00h]
0x18009f7b1  test    al, al
0x18009f7b3  jz      short loc_18009F807
0x18009f7b5  mov     r8b, 1; CaseInSensitive
0x18009f7b8  lea     rdx, stru_180030E68; String2
0x18009f7bf  lea     rcx, [rbp+37h+var_58]; String1
0x18009f7c3  call    cs:__imp_RtlEqualUnicodeString
0x18009f7ca  nop     dword ptr [rax+rax+00h]
0x18009f7cf  test    al, al
0x18009f7d1  jz      short loc_18009F807
0x18009f7d3  lea     rax, [rbp+37h+var_7C]
0x18009f7d7  mov     rcx, rbx
0x18009f7da  mov     [rsp+0E0h+var_B0], rax
0x18009f7df  lea     r9, [rbp+37h+String1]
0x18009f7e3  lea     rax, [rbp+37h+arg_0]
0x18009f7e7  mov     [rsp+0E0h+var_B8], rax
0x18009f7ec  lea     r8, [rbp+37h+var_58]
0x18009f7f0  lea     rax, [rbp+37h+var_80]
0x18009f7f4  lea     rdx, [rbp+37h+var_48]
0x18009f7f8  mov     [rsp+0E0h+var_C0], rax
0x18009f7fd  call    SIPolicyInternalBooleanSecureSettingRollup
0x18009f802  jmp     loc_18009F69E
0x18009f807  lea     rax, [rbp+37h+var_7C]
0x18009f80b  mov     rcx, rbx
0x18009f80e  mov     [rsp+0E0h+var_B0], rax
0x18009f813  lea     r9, [rbp+37h+String1]
0x18009f817  lea     rax, [rbp+37h+arg_0]
0x18009f81b  mov     [rsp+0E0h+var_B8], rax
0x18009f820  lea     r8, [rbp+37h+var_58]
0x18009f824  lea     rax, [rbp+37h+var_80]
0x18009f828  lea     rdx, [rbp+37h+var_48]
0x18009f82c  mov     [rsp+0E0h+var_C0], rax
0x18009f831  call    SIPolicyInternalReturnFirstFoundSecureSetting
0x18009f836  jmp     loc_18009F69E
```
