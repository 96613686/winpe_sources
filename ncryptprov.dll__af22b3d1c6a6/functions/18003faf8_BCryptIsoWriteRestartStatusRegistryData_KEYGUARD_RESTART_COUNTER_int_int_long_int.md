# BCryptIsoWriteRestartStatusRegistryData(_KEYGUARD_RESTART_COUNTER *,int,int,long,int)

- ea: `0x18003faf8`
- end: `0x18003fc59`
- name: `?BCryptIsoWriteRestartStatusRegistryData@@YAXPEAU_KEYGUARD_RESTART_COUNTER@@HHJH@Z`
- size: `353`
- prototype: `void __fastcall(struct _KEYGUARD_RESTART_COUNTER *, int, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180035a04`

## callees

- `0x18003faf8`
- `0x18003fc60`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003fba3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003fba3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc35`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003fbeb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003fbeb`

## string_xrefs

- `0x18003fb28`: `LsaIsoLaunchAttempted`
- `0x18003fb16`: `IsTestConfig`
- `0x18003fb4d`: `ExecSystemProcessesError`
- `0x18003fb58`: `NumAttemptedRestarts`

## pseudocode

```c
void __fastcall BCryptIsoWriteRestartStatusRegistryData(
        struct _KEYGUARD_RESTART_COUNTER *a1,
        int a2,
        int a3,
        int a4,
        int a5)
{
  int i; // edi
  int v6; // edx
  int v7; // r8d
  LSTATUS v8; // r9d
  LPCWSTR lpValueName; // [rsp+30h] [rbp-51h]
  _DWORD v10[2]; // [rsp+38h] [rbp-49h] BYREF
  const WCHAR *v11; // [rsp+40h] [rbp-41h]
  int v12; // [rsp+48h] [rbp-39h]
  const WCHAR *v13; // [rsp+50h] [rbp-31h]
  int v14; // [rsp+58h] [rbp-29h]
  const wchar_t *v15; // [rsp+60h] [rbp-21h]
  int v16; // [rsp+68h] [rbp-19h]
  const wchar_t *v17; // [rsp+70h] [rbp-11h]
  int v18; // [rsp+78h] [rbp-9h]
  const wchar_t *v19; // [rsp+80h] [rbp-1h]
  int v20; // [rsp+88h] [rbp+7h]
  const WCHAR *v21; // [rsp+90h] [rbp+Fh]
  int v22; // [rsp+98h] [rbp+17h]
  const wchar_t *v23; // [rsp+A0h] [rbp+1Fh]
  int v24; // [rsp+A8h] [rbp+27h]

  v12 = a3;
  lpValueName = L"IsTestConfig";
  v10[0] = a2;
  v11 = L"LsaIsoLaunchAttempted";
  v13 = L"LsaIsoLaunchError";
  v16 = a4;
  v14 = a3 != 0 ? a4 : 0;
  v15 = L"ExecSystemProcessesError";
  v17 = L"NumAttemptedRestarts";
  v18 = *(_DWORD *)a1;
  v19 = L"NumSuccessfulRestarts";
  v20 = *((_DWORD *)a1 + 1);
  v21 = L"KeyGuardEnabled";
  v22 = a5;
  v23 = L"CredGuardEnabled";
  v24 = 0;
  AcquireSRWLockExclusive(&SRWLock);
  for ( i = 0; (unsigned __int64)i < 8; ++i )
  {
    v8 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard\\Status",
           *(LPCWSTR *)&v10[4 * i - 2],
           4u,
           &v10[4 * i],
           4u);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v8, *(_QWORD *)&v10[4 * i - 2]);
      break;
    }
  }
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x18003faf8  push    rbp
0x18003fafa  push    rbx
0x18003fafb  push    rdi
0x18003fafc  lea     rbp, [rsp-3Fh]
0x18003fb01  sub     rsp, 0C0h
0x18003fb08  mov     rax, cs:__security_cookie
0x18003fb0f  xor     rax, rsp
0x18003fb12  mov     [rbp+4Fh+var_20], rax
0x18003fb16  lea     rax, aIstestconfig; "IsTestConfig"
0x18003fb1d  mov     [rbp+4Fh+var_88], r8d
0x18003fb21  mov     [rbp+4Fh+lpValueName], rax
0x18003fb25  neg     r8d
0x18003fb28  lea     rax, aLsaisolaunchat; "LsaIsoLaunchAttempted"
0x18003fb2f  mov     [rbp+4Fh+var_98], edx
0x18003fb32  mov     [rbp+4Fh+var_90], rax
0x18003fb36  lea     rax, aLsaisolauncher; "LsaIsoLaunchError"
0x18003fb3d  mov     [rbp+4Fh+var_80], rax
0x18003fb41  sbb     eax, eax
0x18003fb43  and     eax, r9d
0x18003fb46  mov     [rbp+4Fh+var_68], r9d
0x18003fb4a  mov     [rbp+4Fh+var_78], eax
0x18003fb4d  lea     rax, aExecsystemproc; "ExecSystemProcessesError"
0x18003fb54  mov     [rbp+4Fh+var_70], rax
0x18003fb58  lea     rax, aNumattemptedre; "NumAttemptedRestarts"
0x18003fb5f  mov     [rbp+4Fh+var_60], rax
0x18003fb63  mov     eax, [rcx]
0x18003fb65  mov     [rbp+4Fh+var_58], eax
0x18003fb68  lea     rax, aNumsuccessfulr; "NumSuccessfulRestarts"
0x18003fb6f  mov     [rbp+4Fh+var_50], rax
0x18003fb73  mov     eax, [rcx+4]
0x18003fb76  lea     rcx, SRWLock; SRWLock
0x18003fb7d  mov     [rbp+4Fh+var_48], eax
0x18003fb80  lea     rax, aKeyguardenable; "KeyGuardEnabled"
0x18003fb87  mov     [rbp+4Fh+var_40], rax
0x18003fb8b  mov     eax, [rbp+4Fh+arg_20]
0x18003fb8e  mov     [rbp+4Fh+var_38], eax
0x18003fb91  lea     rax, aCredguardenabl; "CredGuardEnabled"
0x18003fb98  mov     [rbp+4Fh+var_30], rax
0x18003fb9c  mov     [rbp+4Fh+var_28], 0
0x18003fba3  call    cs:__imp_AcquireSRWLockExclusive
0x18003fbaa  nop     dword ptr [rax+rax+00h]
0x18003fbaf  xor     edi, edi
0x18003fbb1  movsxd  rbx, edi
0x18003fbb4  cmp     rbx, 8
0x18003fbb8  jnb     short loc_18003FC2E
0x18003fbba  shl     rbx, 4
0x18003fbbe  lea     rax, [rbp+4Fh+var_98]
0x18003fbc2  add     rax, rbx
0x18003fbc5  mov     [rsp+0D0h+cbData], 4; cbData
0x18003fbcd  mov     r9d, 4; dwType
0x18003fbd3  mov     [rsp+0D0h+lpData], rax; lpData
0x18003fbd8  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18003fbdf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fbe6  mov     r8, [rbp+rbx+4Fh+lpValueName]; lpValueName
0x18003fbeb  call    cs:__imp_RegSetKeyValueW
0x18003fbf2  nop     dword ptr [rax+rax+00h]
0x18003fbf7  mov     r9d, eax
0x18003fbfa  test    eax, eax
0x18003fbfc  jnz     short loc_18003FC02
0x18003fbfe  inc     edi
0x18003fc00  jmp     short loc_18003FBB1
0x18003fc02  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc09  lea     rax, WPP_GLOBAL_Control
0x18003fc10  cmp     rcx, rax
0x18003fc13  jz      short loc_18003FC2E
0x18003fc15  test    byte ptr [rcx+1Ch], 1
0x18003fc19  jz      short loc_18003FC2E
0x18003fc1b  mov     rax, [rbp+rbx+4Fh+lpValueName]
0x18003fc20  mov     rcx, [rcx+10h]
0x18003fc24  mov     [rsp+0D0h+lpData], rax
0x18003fc29  call    WPP_SF_DSS
0x18003fc2e  lea     rcx, SRWLock; SRWLock
0x18003fc35  call    cs:__imp_ReleaseSRWLockExclusive
0x18003fc3c  nop     dword ptr [rax+rax+00h]
0x18003fc41  mov     rcx, [rbp+4Fh+var_20]
0x18003fc45  xor     rcx, rsp; StackCookie
0x18003fc48  call    __security_check_cookie
0x18003fc4d  add     rsp, 0C0h
0x18003fc54  pop     rdi
0x18003fc55  pop     rbx
0x18003fc56  pop     rbp
0x18003fc57  retn
```
