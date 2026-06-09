# MakeRegKeySecure(void *,HKEY__ *,ushort const *,int,int,int)

- ea: `0x1800336a0`
- end: `0x180034867`
- name: `?MakeRegKeySecure@@YAHPEAXPEAUHKEY__@@PEBGHHH@Z`
- size: `4551`
- prototype: `int(void *, HKEY, const unsigned __int16 *, int, int, int)`
- caller_count: `14`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002243c`
- `0x1800247b4`
- `0x18002e5a0`
- `0x180033430`
- `0x180034870`
- `0x180034c34`
- `0x1800483b0`
- `0x180048bb0`
- `0x180053870`
- `0x180058f20`
- `0x18005ce5c`
- `0x180065240`
- `0x180065928`
- `0x180066138`

## callees

- `0x180033140`
- `0x1800336a0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003402c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003411b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003414a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003426f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003429f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003433c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003453d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003457c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003463f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003467e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003473e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003476e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003402c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003411b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003414a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003426f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003429f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003430c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003433c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800343e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003453d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003457c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003463f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003467e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800346ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003473e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003476e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b19`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180033ae6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180033ae6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180033856`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180033856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033a59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033a59`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180033a74`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180033a74`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800339fe`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800339fe`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180033873`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180033873`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033805`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033811`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003382a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033e0d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003419d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033805`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033811`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003382a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033e0d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003419d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033a1b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033a1b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800337ac`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800337f3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033c58`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033ce1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033dc3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800337ac`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800337f3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033c58`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033ce1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180033dc3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003393c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003398d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800339d0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033b54`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033f10`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033f53`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003393c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003398d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800339d0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033b54`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033f10`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180033f53`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033ac9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033ad8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033b21`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033d81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003485c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033ac9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033ad8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033b21`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180033d81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003485c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033893`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800338b3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800338e0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033922`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033973`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800339b6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033b3a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033c02`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033ef6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033f39`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033f80`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033fa0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033893`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800338b3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800338e0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033922`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033973`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800339b6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033b3a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033c02`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033ef6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033f39`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033f80`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033fa0`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180033cfb`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180033cfb`

## string_xrefs

- `0x1800336e3`: `registryRead`
- `0x180033fcc`: `MakeRegKeySecure:  Failed to get user sid`
- `0x180033ffc`: `MakeRegKeySecure:  Failed to get user sid`
- `0x180033c89`: `MakeRegKeySecure: Failed to initialize authenticated users sid.  Error = %d`
- `0x180034032`: `MakeRegKeySecure: Failed to initialize authenticated users sid.  Error = %d`
- `0x180033df4`: `MakeRegKeySecure: Failed to initialize network service sid.  Error = %d`
- `0x18003405e`: `MakeRegKeySecure: Failed to initialize network service sid.  Error = %d`
- `0x180034089`: `MakeRegKeySecure: Failed to initialize Lowbox sid.  Error = %d`
- `0x1800340c5`: `MakeRegKeySecure: Failed to initialize Lowbox sid.  Error = %d`
- `0x180033d29`: `MakeRegKeySecure: Failed to derive registryRead capability SID.  Status = %d`
- `0x1800340e8`: `MakeRegKeySecure: Failed to derive registryRead capability SID.  Status = %d`
- `0x180033e8d`: `MakeRegKeySecure: Failed to initialize system sid.  Error = %d`
- `0x180034121`: `MakeRegKeySecure: Failed to initialize system sid.  Error = %d`
- `0x180034150`: `MakeRegKeySecure: Failed to initialize admin sid.  Error = %d`
- `0x18003418c`: `MakeRegKeySecure: Failed to initialize admin sid.  Error = %d`
- `0x1800341cd`: `MakeRegKeySecure: Failed to initialize acl.  Error = %d`
- `0x180034209`: `MakeRegKeySecure: Failed to initialize acl.  Error = %d`
- `0x180034342`: `MakeRegKeySecure: Failed to add ace for network service.  Error = %d`
- `0x18003437e`: `MakeRegKeySecure: Failed to add ace for network service.  Error = %d`
- `0x180034543`: `MakeRegKeySecure: Failed to add ace for network service.  Error = %d`
- `0x180033ecc`: `MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d`
- `0x180034744`: `MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d`
- `0x180034774`: `MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d`
- `0x1800347b0`: `MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d`
- `0x1800347dd`: `MakeRegKeySecure: Failed to set security, error = %d`
- `0x180034813`: `MakeRegKeySecure: Failed to set security, error = %d`
- `0x180033e3e`: `MakeRegKeySecure: Failed to open registry key, error = %d`
- `0x180034843`: `MakeRegKeySecure: Failed to open registry key, error = %d`

## pseudocode

```c
__int64 __fastcall MakeRegKeySecure(void *a1, HKEY a2, const unsigned __int16 *a3, __int64 a4, int a5, int a6)
{
  struct _ACL *v9; // rbx
  unsigned int v10; // r14d
  DWORD LengthSid; // ebx
  DWORD v12; // edi
  struct _ACL *v13; // rax
  PSID v14; // r9
  unsigned int v15; // edi
  PSID v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v21; // eax
  void (*v22)(unsigned int, const unsigned __int16 *, ...); // rsi
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  int v25; // eax
  void (*v26)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v27; // eax
  void (*v28)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v29; // eax
  void (*v30)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v31; // eax
  void (*v32)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v33; // eax
  DWORD v34; // eax
  DWORD v35; // eax
  void (*v36)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v37; // eax
  DWORD v38; // eax
  DWORD v39; // eax
  void (*v40)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v41; // eax
  DWORD v42; // eax
  void (*v43)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v44; // eax
  DWORD v45; // eax
  void (*v46)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v47; // eax
  DWORD v48; // eax
  void (*v49)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v50; // eax
  DWORD v51; // eax
  DWORD v52; // eax
  void (*v53)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v54; // eax
  DWORD v55; // eax
  void (*v56)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v57; // eax
  DWORD v58; // eax
  void (*v59)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v60; // eax
  DWORD v61; // eax
  DWORD v62; // eax
  void (*v63)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v64; // eax
  void (*v65)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v66; // eax
  void (*v67)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v68; // eax
  DWORD v69; // eax
  DWORD v70; // eax
  void (*v71)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v72; // eax
  DWORD v73; // eax
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  PSID hMem; // [rsp+68h] [rbp-98h] BYREF
  PSID v76; // [rsp+70h] [rbp-90h] BYREF
  PSID v77; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  PSID v79; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp-70h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v82[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-30h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D8h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v86; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v87[48]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v88[48]; // [rsp+118h] [rbp+18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  dwDisposition = 0;
  v84 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v86.Value = 0;
  v82[1] = L"registryRead";
  phkResult = 0;
  *(_WORD *)&v86.Value[4] = 3840;
  hMem = 0;
  pSid = 0;
  v79 = 0;
  v76 = 0;
  v77 = 0;
  v82[0] = 1703960;
  pAce = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( a1 )
  {
    hMem = GetUserSid(a1);
    if ( !hMem )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"MakeRegKeySecure:  Failed to get user sid");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"MakeRegKeySecure:  Failed to get user sid");
        }
      }
      return 0;
    }
  }
  else if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v23 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v23(2u, L"MakeRegKeySecure: Failed to initialize authenticated users sid.  Error = %d", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v34 = GetLastError();
        RedirectDebugMsg(2u, L"MakeRegKeySecure: Failed to initialize authenticated users sid.  Error = %d", v34);
      }
    }
    return 0;
  }
  if ( a5 && !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v76) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v28 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v29 = GetLastError();
        v28(2u, L"MakeRegKeySecure: Failed to initialize network service sid.  Error = %d", v29);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v35 = GetLastError();
        RedirectDebugMsg(2u, L"MakeRegKeySecure: Failed to initialize network service sid.  Error = %d", v35);
      }
    }
    return 0;
  }
  if ( a6 )
  {
    if ( !AllocateAndInitializeSid(&v86, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v77) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v36 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v37 = GetLastError();
          v36(2u, L"MakeRegKeySecure: Failed to initialize Lowbox sid.  Error = %d", v37);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v38 = GetLastError();
          RedirectDebugMsg(2u, L"MakeRegKeySecure: Failed to initialize Lowbox sid.  Error = %d", v38);
        }
      }
      return 0;
    }
    v25 = RtlDeriveCapabilitySidsFromName(v82, v88, v87);
    if ( v25 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"MakeRegKeySecure: Failed to derive registryRead capability SID.  Status = %d",
            (unsigned int)v25);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"MakeRegKeySecure: Failed to derive registryRead capability SID.  Status = %d",
            (unsigned int)v25);
        }
      }
      return 0;
    }
  }
  v9 = 0;
  v10 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v30 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v31 = GetLastError();
        v30(4u, L"MakeRegKeySecure: Failed to initialize system sid.  Error = %d", v31);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v39 = GetLastError();
        RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to initialize system sid.  Error = %d", v39);
      }
    }
    goto LABEL_38;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v79) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v40 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v41 = GetLastError();
        v40(4u, L"MakeRegKeySecure: Failed to initialize admin sid.  Error = %d", v41);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v42 = GetLastError();
        RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to initialize admin sid.  Error = %d", v42);
      }
    }
    goto LABEL_38;
  }
  LengthSid = GetLengthSid(v79);
  v12 = 2 * (GetLengthSid(pSid) + LengthSid) + 40;
  if ( hMem )
    v12 += 2 * GetLengthSid(hMem) + 16;
  if ( v76 )
    v12 += 2 * GetLengthSid(v76) + 16;
  if ( v77 )
    v12 += 2 * GetLengthSid(v77) + 128;
  v13 = (struct _ACL *)GlobalAlloc(0, v12);
  v9 = v13;
  if ( !v13 )
    goto LABEL_38;
  if ( !InitializeAcl(v13, v12, 2u) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v43 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v44 = GetLastError();
        v43(4u, L"MakeRegKeySecure: Failed to initialize acl.  Error = %d", v44);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v45 = GetLastError();
        RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to initialize acl.  Error = %d", v45);
      }
    }
    goto LABEL_38;
  }
  if ( !AddAccessAllowedAce(v9, 2u, 0xF003Fu, pSid) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v46 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v47 = GetLastError();
      v46(4u, L"MakeRegKeySecure: Failed to add ace for system.  Error = %d", v47);
      goto LABEL_38;
    }
    goto LABEL_137;
  }
  if ( !AddAccessAllowedAce(v9, 2u, 0xF003Fu, v79) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v49 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v50 = GetLastError();
      v49(4u, L"MakeRegKeySecure: Failed to add ace for admin.  Error = %d", v50);
      goto LABEL_38;
    }
LABEL_143:
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v51 = GetLastError();
      RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add ace for admin.  Error = %d", v51);
    }
    goto LABEL_38;
  }
  v14 = hMem;
  v15 = 1;
  if ( hMem )
  {
    v15 = 2;
    if ( !AddAccessAllowedAce(v9, 2u, 0x20019u, hMem) )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_38;
      v26 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
        goto LABEL_75;
      goto LABEL_146;
    }
    v14 = hMem;
  }
  v16 = v76;
  if ( v76 )
  {
    if ( !AddAccessAllowedAce(v9, 2u, 0x20019u, v76) )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_38;
      v53 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v54 = GetLastError();
        v53(4u, L"MakeRegKeySecure: Failed to add ace for network service.  Error = %d", v54);
        goto LABEL_38;
      }
LABEL_152:
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v55 = GetLastError();
        RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add ace for network service.  Error = %d", v55);
      }
      goto LABEL_38;
    }
    v14 = hMem;
    ++v15;
    v16 = v76;
  }
  if ( v77 )
  {
    if ( !AddAccessAllowedAce(v9, 2u, 0x20019u, v77) )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_38;
      v56 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v57 = GetLastError();
        v56(4u, L"MakeRegKeySecure: Failed to add ace for Lowbox.  Error = %d", v57);
        goto LABEL_38;
      }
      goto LABEL_158;
    }
    if ( !AddAccessAllowedAce(v9, 2u, 0x20019u, v87) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v59 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v60 = GetLastError();
          v59(4u, L"MakeRegKeySecure: Failed to add capability ace for Lowbox.  Error = %d", v60);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v61 = GetLastError();
          RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add capability ace for Lowbox.  Error = %d", v61);
        }
      }
      goto LABEL_38;
    }
    v14 = hMem;
    v15 += 2;
    v16 = v76;
  }
  if ( v14 )
  {
    if ( AddAccessAllowedAce(v9, 2u, 0x80000000, v14) )
    {
      if ( !GetAce(v9, ++v15, &pAce) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v22 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
            goto LABEL_198;
          goto LABEL_172;
        }
        goto LABEL_38;
      }
      *((_BYTE *)pAce + 1) |= 0xBu;
      v16 = v76;
      goto LABEL_26;
    }
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v26 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
LABEL_75:
      v27 = GetLastError();
      v26(4u, L"MakeRegKeySecure: Failed to add ace for user.  Error = %d", v27);
      goto LABEL_38;
    }
LABEL_146:
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v52 = GetLastError();
      RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add ace for user.  Error = %d", v52);
    }
    goto LABEL_38;
  }
LABEL_26:
  if ( !v16 )
    goto LABEL_27;
  if ( !AddAccessAllowedAce(v9, 2u, 0x80000000, v16) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v63 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v64 = GetLastError();
      v63(4u, L"MakeRegKeySecure: Failed to add ace for network service.  Error = %d", v64);
      goto LABEL_38;
    }
    goto LABEL_152;
  }
  if ( !GetAce(v9, ++v15, &pAce) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v22 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
        goto LABEL_198;
      goto LABEL_172;
    }
    goto LABEL_38;
  }
  *((_BYTE *)pAce + 1) |= 0xBu;
LABEL_27:
  if ( !AddAccessAllowedAce(v9, 2u, 0x10000000u, pSid) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v20 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v21 = GetLastError();
      v20(4u, L"MakeRegKeySecure: Failed to add ace for system.  Error = %d", v21);
      goto LABEL_38;
    }
LABEL_137:
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v48 = GetLastError();
      RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add ace for system.  Error = %d", v48);
    }
    goto LABEL_38;
  }
  if ( !GetAce(v9, ++v15, &pAce) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v22 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
        goto LABEL_198;
      goto LABEL_172;
    }
    goto LABEL_38;
  }
  *((_BYTE *)pAce + 1) |= 0xBu;
  if ( !AddAccessAllowedAce(v9, 2u, 0x10000000u, v79) )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_38;
    v65 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v66 = GetLastError();
      v65(4u, L"MakeRegKeySecure: Failed to add ace for admin.  Error = %d", v66);
      goto LABEL_38;
    }
    goto LABEL_143;
  }
  if ( GetAce(v9, ++v15, &pAce) )
  {
    *((_BYTE *)pAce + 1) |= 0xBu;
    if ( !v77 )
      goto LABEL_32;
    if ( AddAccessAllowedAce(v9, 2u, 0x80000000, v77) )
    {
      if ( !GetAce(v9, ++v15, &pAce) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v22 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
            goto LABEL_198;
          goto LABEL_172;
        }
        goto LABEL_38;
      }
      *((_BYTE *)pAce + 1) |= 0xBu;
      if ( AddAccessAllowedAce(v9, 2u, 0x80000000, v87) )
      {
        if ( GetAce(v9, ++v15, &pAce) )
        {
          *((_BYTE *)pAce + 1) |= 0xBu;
LABEL_32:
          if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0) )
            {
              v17 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x40000u, 0, &phkResult, &dwDisposition);
              if ( v17 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"MakeRegKeySecure: Failed to open registry key, error = %d", v17);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"MakeRegKeySecure: Failed to open registry key, error = %d", v17);
                  }
                }
              }
              else
              {
                v18 = RegSetKeySecurity(phkResult, 4u, pSecurityDescriptor);
                if ( v18 )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"MakeRegKeySecure: Failed to set security, error = %d", v18);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"MakeRegKeySecure: Failed to set security, error = %d", v18);
                    }
                  }
                }
                else
                {
                  v10 = 1;
                }
                RegCloseKey(phkResult);
              }
            }
            else if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v71 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v72 = GetLastError();
                v71(4u, L"MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d", v72);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v73 = GetLastError();
                RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to set security descriptor dacl.  Error = %d", v73);
              }
            }
          }
          else if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v32 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v33 = GetLastError();
              v32(4u, L"MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d", v33);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v70 = GetLastError();
              RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to initialize security descriptor.  Error = %d", v70);
            }
          }
          goto LABEL_38;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v22 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
LABEL_198:
            v69 = GetLastError();
            v22(4u, L"MakeRegKeySecure: Failed to get ace (%d).  Error = %d", v15, v69);
            goto LABEL_38;
          }
LABEL_172:
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v62 = GetLastError();
            RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to get ace (%d).  Error = %d", v15, v62);
          }
          goto LABEL_38;
        }
        goto LABEL_38;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_38;
      v67 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
LABEL_189:
        v68 = GetLastError();
        v67(4u, L"MakeRegKeySecure: Failed to add ace for Lowbox.  Error = %d", v68);
        goto LABEL_38;
      }
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_38;
      v67 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
        goto LABEL_189;
    }
LABEL_158:
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v58 = GetLastError();
      RedirectDebugMsg(4u, L"MakeRegKeySecure: Failed to add ace for Lowbox.  Error = %d", v58);
    }
    goto LABEL_38;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v22 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
      goto LABEL_198;
    goto LABEL_172;
  }
LABEL_38:
  if ( v77 )
    FreeSid(v77);
  if ( hMem )
  {
    if ( a1 )
      LocalFree(hMem);
    else
      FreeSid(hMem);
  }
  if ( v76 )
    FreeSid(v76);
  if ( pSid )
    FreeSid(pSid);
  if ( v79 )
    FreeSid(v79);
  if ( v9 )
    GlobalFree(v9);
  return v10;
}

```

## disassembly

```asm
0x1800336a0  push    rbp
0x1800336a2  push    rbx
0x1800336a3  push    rsi
0x1800336a4  push    r12
0x1800336a6  push    r13
0x1800336a8  push    r15
0x1800336aa  lea     rbp, [rsp-58h]
0x1800336af  sub     rsp, 158h
0x1800336b6  mov     rax, cs:__security_cookie
0x1800336bd  xor     rax, rsp
0x1800336c0  mov     [rbp+80h+var_38], rax
0x1800336c4  xor     r13d, r13d
0x1800336c7  mov     word ptr [rbp+80h+pIdentifierAuthority.Value+4], 500h
0x1800336cd  xor     eax, eax
0x1800336cf  mov     [rbp+80h+dwDisposition], r13d
0x1800336d3  mov     [rbp+80h+var_B0], rax
0x1800336d7  xorps   xmm0, xmm0
0x1800336da  mov     dword ptr [rbp+80h+pIdentifierAuthority.Value], eax
0x1800336dd  mov     r12, r8
0x1800336e0  mov     dword ptr [rbp+80h+var_A0.Value], eax
0x1800336e3  lea     rax, aRegistryread; "registryRead"
0x1800336ea  mov     [rbp+80h+var_D8], rax
0x1800336ee  mov     rsi, rdx
0x1800336f1  mov     [rbp+80h+phkResult], r13
0x1800336f5  mov     r15, rcx
0x1800336f8  mov     word ptr [rbp+80h+var_A0.Value+4], 0F00h
0x1800336fe  mov     [rsp+180h+hMem], r13
0x180033703  mov     [rbp+80h+var_100], r13
0x180033707  mov     [rbp+80h+var_F8], r13
0x18003370b  mov     [rsp+180h+var_110], r13
0x180033710  mov     [rsp+180h+var_108], r13
0x180033715  mov     [rbp+80h+var_E0], 1A0018h
0x18003371d  mov     [rsp+180h+pAce], r13
0x180033722  movups  [rbp+80h+pSecurityDescriptor], xmm0
0x180033726  movups  [rbp+80h+var_C0], xmm0
0x18003372a  test    rcx, rcx
0x18003372d  jz      loc_180033C21
0x180033733  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x180033738  mov     [rsp+180h+hMem], rax
0x18003373d  test    rax, rax
0x180033740  jz      loc_180033E57
0x180033746  cmp     [rbp+80h+arg_20], r13d
0x18003374d  jnz     loc_180033D8C
0x180033753  cmp     [rbp+80h+arg_28], r13d
0x18003375a  jnz     loc_180033CA5
0x180033760  lea     rax, [rbp+80h+var_100]
0x180033764  mov     [rsp+180h+arg_18], rdi
0x18003376c  mov     [rsp+180h+pSid], rax; pSid
0x180033771  lea     rcx, [rbp+80h+pIdentifierAuthority]; pIdentifierAuthority
0x180033775  mov     [rsp+180h+nSubAuthority7], r13d; nSubAuthority7
0x18003377a  xor     r9d, r9d; nSubAuthority1
0x18003377d  mov     [rsp+180h+nSubAuthority6], r13d; nSubAuthority6
0x180033782  mov     r8d, 12h; nSubAuthority0
0x180033788  mov     [rsp+180h+nSubAuthority5], r13d; nSubAuthority5
0x18003378d  mov     dl, 1; nSubAuthorityCount
0x18003378f  mov     [rsp+180h+nSubAuthority4], r13d; nSubAuthority4
0x180033794  mov     rbx, r13
0x180033797  mov     [rsp+180h+nSubAuthority3], r13d; nSubAuthority3
0x18003379c  mov     [rsp+180h+var_30], r14
0x1800337a4  mov     r14d, r13d
0x1800337a7  mov     [rsp+180h+nSubAuthority2], r13d; nSubAuthority2
0x1800337ac  call    cs:__imp_AllocateAndInitializeSid
0x1800337b2  test    eax, eax
0x1800337b4  jz      loc_180033E6B
0x1800337ba  lea     rax, [rbp+80h+var_F8]
0x1800337be  mov     r9d, 220h; nSubAuthority1
0x1800337c4  mov     [rsp+180h+pSid], rax; pSid
0x1800337c9  lea     rcx, [rbp+80h+pIdentifierAuthority]; pIdentifierAuthority
0x1800337cd  mov     [rsp+180h+nSubAuthority7], r13d; nSubAuthority7
0x1800337d2  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800337d8  mov     [rsp+180h+nSubAuthority6], r13d; nSubAuthority6
0x1800337dd  mov     dl, 2; nSubAuthorityCount
0x1800337df  mov     [rsp+180h+nSubAuthority5], r13d; nSubAuthority5
0x1800337e4  mov     [rsp+180h+nSubAuthority4], r13d; nSubAuthority4
0x1800337e9  mov     [rsp+180h+nSubAuthority3], r13d; nSubAuthority3
0x1800337ee  mov     [rsp+180h+nSubAuthority2], r13d; nSubAuthority2
0x1800337f3  call    cs:__imp_AllocateAndInitializeSid
0x1800337f9  test    eax, eax
0x1800337fb  jz      loc_180034132
0x180033801  mov     rcx, [rbp+80h+var_F8]; pSid
0x180033805  call    cs:__imp_GetLengthSid
0x18003380b  mov     rcx, [rbp+80h+var_100]; pSid
0x18003380f  mov     ebx, eax
0x180033811  call    cs:__imp_GetLengthSid
0x180033817  mov     rcx, [rsp+180h+hMem]; pSid
0x18003381c  add     ebx, eax
0x18003381e  lea     edi, ds:28h[rbx*2]
0x180033825  test    rcx, rcx
0x180033828  jz      short loc_180033836
0x18003382a  call    cs:__imp_GetLengthSid
0x180033830  lea     edi, [rdi+rax*2]
0x180033833  add     edi, 10h
0x180033836  mov     rcx, [rsp+180h+var_110]; pSid
0x18003383b  test    rcx, rcx
0x18003383e  jnz     loc_180033E0D
0x180033844  mov     rcx, [rsp+180h+var_108]; pSid
0x180033849  test    rcx, rcx
0x18003384c  jnz     loc_18003419D
0x180033852  mov     edx, edi; dwBytes
0x180033854  xor     ecx, ecx; uFlags
0x180033856  call    cs:__imp_GlobalAlloc
0x18003385c  mov     rbx, rax
0x18003385f  test    rax, rax
0x180033862  jz      loc_180033A92
0x180033868  mov     r8d, 2; dwAclRevision
0x18003386e  mov     edx, edi; nAclLength
0x180033870  mov     rcx, rax; pAcl
0x180033873  call    cs:__imp_InitializeAcl
0x180033879  test    eax, eax
0x18003387b  jz      loc_1800341AE
0x180033881  mov     r9, [rbp+80h+var_100]; pSid
0x180033885  mov     edx, 2; dwAceRevision
0x18003388a  mov     r8d, 0F003Fh; AccessMask
0x180033890  mov     rcx, rbx; pAcl
0x180033893  call    cs:__imp_AddAccessAllowedAce
0x180033899  test    eax, eax
0x18003389b  jz      loc_18003421A
0x1800338a1  mov     r9, [rbp+80h+var_F8]; pSid
0x1800338a5  mov     edx, 2; dwAceRevision
0x1800338aa  mov     r8d, 0F003Fh; AccessMask
0x1800338b0  mov     rcx, rbx; pAcl
0x1800338b3  call    cs:__imp_AddAccessAllowedAce
0x1800338b9  test    eax, eax
0x1800338bb  jz      loc_180034286
0x1800338c1  mov     r9, [rsp+180h+hMem]; pSid
0x1800338c6  mov     edi, 1
0x1800338cb  test    r9, r9
0x1800338ce  jz      short loc_1800338F3
0x1800338d0  mov     edi, 2
0x1800338d5  mov     r8d, 20019h; AccessMask
0x1800338db  mov     edx, edi; dwAceRevision
0x1800338dd  mov     rcx, rbx; pAcl
0x1800338e0  call    cs:__imp_AddAccessAllowedAce
0x1800338e6  test    eax, eax
0x1800338e8  jz      loc_180033D42
0x1800338ee  mov     r9, [rsp+180h+hMem]; pSid
0x1800338f3  mov     rax, [rsp+180h+var_110]
0x1800338f8  test    rax, rax
0x1800338fb  jnz     loc_180033BF1
0x180033901  mov     rcx, [rsp+180h+var_108]
0x180033906  test    rcx, rcx
0x180033909  jnz     loc_180033F6F
0x18003390f  test    r9, r9
0x180033912  jz      short loc_180033958
0x180033914  mov     edx, 2; dwAceRevision
0x180033919  mov     r8d, 80000000h; AccessMask
0x18003391f  mov     rcx, rbx; pAcl
0x180033922  call    cs:__imp_AddAccessAllowedAce
0x180033928  test    eax, eax
0x18003392a  jz      loc_180034467
0x180033930  inc     edi
0x180033932  lea     r8, [rsp+180h+pAce]; pAce
0x180033937  mov     edx, edi; dwAceIndex
0x180033939  mov     rcx, rbx; pAcl
0x18003393c  call    cs:__imp_GetAce
0x180033942  test    eax, eax
0x180033944  jz      loc_1800344A6
0x18003394a  mov     rax, [rsp+180h+pAce]
0x18003394f  or      byte ptr [rax+1], 0Bh
0x180033953  mov     rax, [rsp+180h+var_110]
0x180033958  test    rax, rax
0x18003395b  jnz     loc_180033B29
0x180033961  mov     r9, [rbp+80h+var_100]; pSid
0x180033965  mov     edx, 2; dwAceRevision
0x18003396a  mov     r8d, 10000000h; AccessMask
0x180033970  mov     rcx, rbx; pAcl
0x180033973  call    cs:__imp_AddAccessAllowedAce
0x180033979  test    eax, eax
0x18003397b  jz      loc_180033B70
0x180033981  inc     edi
0x180033983  lea     r8, [rsp+180h+pAce]; pAce
0x180033988  mov     edx, edi; dwAceIndex
0x18003398a  mov     rcx, rbx; pAcl
0x18003398d  call    cs:__imp_GetAce
0x180033993  test    eax, eax
0x180033995  jz      loc_1800345A1
0x18003399b  mov     rax, [rsp+180h+pAce]
0x1800339a0  mov     edx, 2; dwAceRevision
0x1800339a5  mov     r8d, 10000000h; AccessMask
0x1800339ab  mov     rcx, rbx; pAcl
0x1800339ae  or      byte ptr [rax+1], 0Bh
0x1800339b2  mov     r9, [rbp+80h+var_F8]; pSid
0x1800339b6  call    cs:__imp_AddAccessAllowedAce
0x1800339bc  test    eax, eax
0x1800339be  jz      loc_1800345E3
0x1800339c4  inc     edi
0x1800339c6  lea     r8, [rsp+180h+pAce]; pAce
0x1800339cb  mov     edx, edi; dwAceIndex
0x1800339cd  mov     rcx, rbx; pAcl
0x1800339d0  call    cs:__imp_GetAce
0x1800339d6  test    eax, eax
0x1800339d8  jz      loc_180033BAF
0x1800339de  mov     rax, [rsp+180h+pAce]
0x1800339e3  or      byte ptr [rax+1], 0Bh
0x1800339e7  mov     r9, [rsp+180h+var_108]; pSid
0x1800339ec  test    r9, r9
0x1800339ef  jnz     loc_180033EE8
0x1800339f5  mov     edx, 1; dwRevision
0x1800339fa  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x1800339fe  call    cs:__imp_InitializeSecurityDescriptor
0x180033a04  test    eax, eax
0x180033a06  jz      loc_180033EA9
0x180033a0c  xor     r9d, r9d; bDaclDefaulted
0x180033a0f  lea     rcx, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x180033a13  mov     r8, rbx; pDacl
0x180033a16  mov     edx, 1; bDaclPresent
0x180033a1b  call    cs:__imp_SetSecurityDescriptorDacl
0x180033a21  test    eax, eax
0x180033a23  jz      loc_180034755
0x180033a29  lea     rax, [rbp+80h+dwDisposition]
0x180033a2d  xor     r9d, r9d; lpClass
0x180033a30  mov     qword ptr [rsp+180h+nSubAuthority6], rax; lpdwDisposition
0x180033a35  xor     r8d, r8d; Reserved
0x180033a38  lea     rax, [rbp+80h+phkResult]
0x180033a3c  mov     rdx, r12; lpSubKey
0x180033a3f  mov     qword ptr [rsp+180h+nSubAuthority5], rax; phkResult
0x180033a44  mov     rcx, rsi; hKey
0x180033a47  mov     qword ptr [rsp+180h+nSubAuthority4], r13; lpSecurityAttributes
0x180033a4c  mov     [rsp+180h+nSubAuthority3], 40000h; samDesired
0x180033a54  mov     [rsp+180h+nSubAuthority2], r13d; dwOptions
0x180033a59  call    cs:__imp_RegCreateKeyExW
0x180033a5f  test    eax, eax
0x180033a61  jnz     loc_180033E1E
0x180033a67  mov     rcx, [rbp+80h+phkResult]; hKey
0x180033a6b  lea     r8, [rbp+80h+pSecurityDescriptor]; pSecurityDescriptor
0x180033a6f  mov     edx, 4; SecurityInformation
0x180033a74  call    cs:__imp_RegSetKeySecurity
0x180033a7a  test    eax, eax
0x180033a7c  jnz     loc_1800347C1
0x180033a82  mov     r14d, 1
0x180033a88  mov     rcx, [rbp+80h+phkResult]; hKey
0x180033a8c  call    cs:__imp_RegCloseKey
0x180033a92  mov     rcx, [rsp+180h+var_108]; pSid
0x180033a97  mov     rdi, [rsp+180h+arg_18]
0x180033a9f  test    rcx, rcx
0x180033aa2  jnz     loc_18003485C
0x180033aa8  mov     rcx, [rsp+180h+hMem]; pSid
0x180033aad  test    rcx, rcx
0x180033ab0  jnz     short loc_180033B14
0x180033ab2  mov     rcx, [rsp+180h+var_110]; pSid
0x180033ab7  test    rcx, rcx
0x180033aba  jnz     loc_180033D81
0x180033ac0  mov     rcx, [rbp+80h+var_100]; pSid
0x180033ac4  test    rcx, rcx
0x180033ac7  jz      short loc_180033ACF
0x180033ac9  call    cs:__imp_FreeSid
0x180033acf  mov     rcx, [rbp+80h+var_F8]; pSid
0x180033ad3  test    rcx, rcx
0x180033ad6  jz      short loc_180033ADE
0x180033ad8  call    cs:__imp_FreeSid
0x180033ade  test    rbx, rbx
0x180033ae1  jz      short loc_180033AEC
0x180033ae3  mov     rcx, rbx; hMem
0x180033ae6  call    cs:__imp_GlobalFree
0x180033aec  mov     eax, r14d
0x180033aef  mov     r14, [rsp+180h+var_30]
0x180033af7  mov     rcx, [rbp+80h+var_38]
0x180033afb  xor     rcx, rsp; StackCookie
0x180033afe  call    __security_check_cookie
0x180033b03  add     rsp, 158h
0x180033b0a  pop     r15
0x180033b0c  pop     r13
0x180033b0e  pop     r12
0x180033b10  pop     rsi
0x180033b11  pop     rbx
0x180033b12  pop     rbp
0x180033b13  retn
0x180033b14  test    r15, r15
0x180033b17  jz      short loc_180033B21
0x180033b19  call    cs:__imp_LocalFree
0x180033b1f  jmp     short loc_180033AB2
0x180033b21  call    cs:__imp_FreeSid
0x180033b27  jmp     short loc_180033AB2
0x180033b29  mov     r9, rax; pSid
0x180033b2c  mov     edx, 2; dwAceRevision
0x180033b31  mov     r8d, 80000000h; AccessMask
0x180033b37  mov     rcx, rbx; pAcl
0x180033b3a  call    cs:__imp_AddAccessAllowedAce
0x180033b40  test    eax, eax
0x180033b42  jz      loc_180034520
0x180033b48  inc     edi
0x180033b4a  lea     r8, [rsp+180h+pAce]; pAce
0x180033b4f  mov     edx, edi; dwAceIndex
0x180033b51  mov     rcx, rbx; pAcl
0x180033b54  call    cs:__imp_GetAce
0x180033b5a  test    eax, eax
0x180033b5c  jz      loc_18003455F
0x180033b62  mov     rax, [rsp+180h+pAce]
0x180033b67  or      byte ptr [rax+1], 0Bh
0x180033b6b  jmp     loc_180033961
0x180033b70  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180033b77  jz      loc_180033A92
0x180033b7d  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180033b84  test    rdi, rdi
0x180033b87  jz      loc_180034255
0x180033b8d  call    cs:__imp_GetLastError
0x180033b93  lea     rdx, aMakeregkeysecu_5; "MakeRegKeySecure: Failed to add ace for"...
0x180033b9a  mov     ecx, 4
0x180033b9f  mov     r8d, eax
0x180033ba2  mov     rax, rdi
  ... truncated ...
```
