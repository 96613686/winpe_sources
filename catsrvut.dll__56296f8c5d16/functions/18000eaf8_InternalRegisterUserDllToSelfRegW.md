# InternalRegisterUserDllToSelfRegW

- ea: `0x18000eaf8`
- end: `0x18000edab`
- name: `InternalRegisterUserDllToSelfRegW`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800133d4`

## callees

- `0x180005944`
- `0x18000e05c`
- `0x18000eaf8`
- `0x18000edb4`
- `0x1800160f4`
- `0x18004fc3c`
- `0x18004fdbc`
- `0x18004fed4`
- `0x1800504c0`
- `0x180050b6c`
- `0x1800514a0`
- `0x180052654`
- `0x180052750`
- `0x180052840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed7d`
- `ADVAPI32!RegCreateKeyW` at `0x18000eb63`
- `ADVAPI32!RegCreateKeyW` at `0x18000eb63`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ebdd`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ec35`
- `ADVAPI32!RegOverridePredefKey` at `0x18000eccd`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ed2b`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ed6e`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ebdd`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ec35`
- `ADVAPI32!RegOverridePredefKey` at `0x18000eccd`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ed2b`
- `ADVAPI32!RegOverridePredefKey` at `0x18000ed6e`

## string_xrefs

- `0x18000eb57`: `SOFTWARE\Microsoft\COM3\SelfReg`
- `0x18000ebc5`: `com\complus\src\comcat\catsrvut\catsrvut.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InternalRegisterUserDllToSelfRegW(unsigned __int16 *a1, __int64 a2, WCHAR *a3, const WCHAR *a4)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  int v8; // edi
  LSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rbx
  LSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  int v19; // [rsp+38h] [rbp-B1h] BYREF
  __int16 v20; // [rsp+3Ch] [rbp-ADh]
  __int64 v21; // [rsp+40h] [rbp-A9h]
  const unsigned __int16 *v22; // [rsp+48h] [rbp-A1h]
  __int64 v23; // [rsp+50h] [rbp-99h]
  __int64 v24; // [rsp+58h] [rbp-91h]
  int v25; // [rsp+60h] [rbp-89h]
  int v26; // [rsp+64h] [rbp-85h]
  _BYTE v27[96]; // [rsp+68h] [rbp-81h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-21h]
  unsigned __int16 *v29; // [rsp+148h] [rbp+5Fh] BYREF
  HKEY phkResult; // [rsp+150h] [rbp+67h] BYREF

  v29 = a1;
  phkResult = 0;
  RegScan::RegScan((RegScan *)v27, 0);
  v6 = PrepareSelfRegKey(z_fCleanup);
  if ( !v6 )
  {
    v7 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3\\SelfReg", &phkResult);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( !v6 )
    {
      v8 = 1;
      if ( !phkResult )
      {
        v19 = 0;
        v20 = 21;
        LODWORD(v21) = -1073605930;
        v22 = L"hKeySelfReg";
        v23 = 0;
        v24 = 0;
        v26 = 1;
        v25 = 1;
        CError::WriteToLog((CError *)&v19, L"com\\complus\\src\\comcat\\catsrvut\\catsrvut.cpp", 0x311u, L"hKeySelfReg");
      }
      while ( 1 )
      {
        v9 = RegOverridePredefKey(HKEY_CLASSES_ROOT, phkResult);
        v6 = v9;
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        if ( v6 )
          break;
        if ( v8 )
        {
          v8 = 0;
          RegScanUtil::BeginRegistryIsRedirected();
        }
        v29 = 0;
        RegScanUtil::GetSupportDll(&v29);
        v12 = v29;
        if ( !v29 )
        {
          v13 = RegOverridePredefKey(HKEY_CLASSES_ROOT, phkResult);
          v6 = v13;
          if ( v13 > 0 )
            v6 = (unsigned __int16)v13 | 0x80070000;
          if ( !v6 )
          {
            if ( (v15 = (unsigned int)z_fRefCountFile, *(_DWORD *)(v28 + 116) = z_fRefCountFile, !z_fCopyToRegistry)
              && !z_fDeleteOldKeys
              || (*(_DWORD *)(v28 + 112) = z_fIsBasePartition,
                  (v6 = RegScan::SetRegisteredFileName((RegScan *)v27, a3)) == 0)
              && (v6 = RegScan::ScanSourceKeys((RegScan *)v27, HKEY_CLASSES_ROOT)) == 0 )
            {
              v6 = RegisterUserDllW(v15, v14, a3, a4);
              if ( !v6 )
              {
                RegScanUtil::CheckRegistryIsRedirected(a3);
                v16 = RegOverridePredefKey(HKEY_CLASSES_ROOT, phkResult);
                v6 = v16;
                if ( v16 > 0 )
                  v6 = (unsigned __int16)v16 | 0x80070000;
                if ( !v6
                  && (!z_fCopyToRegistry && !z_fDeleteOldKeys
                   || (v6 = RegScan::ScanSourceKeys((RegScan *)v27, 0)) == 0
                   && (!z_fDeleteOldKeys || (v6 = RegScan::DeleteOldKeys((RegScan *)v27, 0)) == 0)) )
                {
                  v17 = RegOverridePredefKey(HKEY_CLASSES_ROOT, 0);
                  v6 = v17;
                  if ( v17 > 0 )
                    v6 = (unsigned __int16)v17 | 0x80070000;
                  if ( !v6 )
                  {
                    if ( z_fCopyToRegistry )
                    {
                      v6 = RegScan::ScanDestKeys((RegScan *)v27, HKEY_CLASSES_ROOT);
                      if ( !v6 )
                        v6 = RegScan::CopyKeys((RegScan *)v27);
                    }
                  }
                }
              }
            }
          }
          break;
        }
        RegisterUserDllW(v11, v10, v29, a4);
        RegScanUtil::CheckRegistryIsRedirected(v12);
      }
    }
  }
  RegOverridePredefKey(HKEY_CLASSES_ROOT, 0);
  if ( phkResult )
    RegCloseKey(phkResult);
  RegScan::~RegScan((RegScan *)v27);
  return v6;
}

```

## disassembly

```asm
0x18000eaf8  mov     rax, rsp
0x18000eafb  mov     [rax+18h], rbx
0x18000eaff  mov     [rax+10h], rdx
0x18000eb03  mov     [rax+8], rcx
0x18000eb07  push    rbp
0x18000eb08  push    rsi
0x18000eb09  push    rdi
0x18000eb0a  push    r12
0x18000eb0c  push    r13
0x18000eb0e  push    r14
0x18000eb10  push    r15
0x18000eb12  lea     rbp, [rax-57h]
0x18000eb16  sub     rsp, 100h
0x18000eb1d  mov     r14, r9
0x18000eb20  mov     rsi, r8
0x18000eb23  xor     r15d, r15d
0x18000eb26  mov     [rbp+4Fh+phkResult], r15
0x18000eb2a  xor     edx, edx; struct RegScan *
0x18000eb2c  lea     rcx, [rsp+130h+var_D0]; this
0x18000eb31  call    ??0RegScan@@QEAA@PEAV0@@Z; RegScan::RegScan(RegScan *)
0x18000eb36  nop
0x18000eb37  mov     ecx, cs:?z_fCleanup@@3HA; int z_fCleanup
0x18000eb3d  call    PrepareSelfRegKey
0x18000eb42  mov     ebx, eax
0x18000eb44  mov     r12, 0FFFFFFFF80000000h
0x18000eb4b  test    eax, eax
0x18000eb4d  jnz     loc_18000ED69
0x18000eb53  lea     r8, [rbp+4Fh+phkResult]; phkResult
0x18000eb57  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\COM3\\SelfReg"
0x18000eb5e  lea     rcx, [r12+2]; hKey
0x18000eb63  call    cs:__imp_RegCreateKeyW
0x18000eb69  mov     ebx, eax
0x18000eb6b  mov     r13d, 80070000h
0x18000eb71  test    eax, eax
0x18000eb73  jle     short loc_18000EB7B
0x18000eb75  movzx   ebx, ax
0x18000eb78  or      ebx, r13d
0x18000eb7b  test    ebx, ebx
0x18000eb7d  jnz     loc_18000ED69
0x18000eb83  lea     edi, [rbx+1]
0x18000eb86  cmp     [rbp+4Fh+phkResult], r15
0x18000eb8a  jnz     short loc_18000EBD6
0x18000eb8c  mov     [rsp+130h+var_100], r15d
0x18000eb91  lea     eax, [rbx+15h]
0x18000eb94  mov     [rsp+130h+var_FC], ax
0x18000eb99  mov     dword ptr [rsp+130h+var_F8], 0C00212D6h
0x18000eba1  lea     r9, aHkeyselfreg; "hKeySelfReg"
0x18000eba8  mov     [rsp+130h+var_F0], r9
0x18000ebad  mov     [rsp+130h+var_E8], r15
0x18000ebb2  mov     qword ptr [rsp+130h+var_E0], r15
0x18000ebb7  mov     [rsp+130h+var_D4], edi
0x18000ebbb  mov     [rsp+130h+var_D8], edi
0x18000ebbf  mov     r8d, 311h; unsigned int
0x18000ebc5  lea     rdx, aComComplusSrcC_1; "com\\complus\\src\\comcat\\catsrvut\\ca"...
0x18000ebcc  lea     rcx, [rsp+130h+var_100]; this
0x18000ebd1  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000ebd6  mov     rdx, [rbp+4Fh+phkResult]; hNewHKey
0x18000ebda  mov     rcx, r12; hKey
0x18000ebdd  call    cs:__imp_RegOverridePredefKey
0x18000ebe3  mov     ebx, eax
0x18000ebe5  test    eax, eax
0x18000ebe7  jle     short loc_18000EBEF
0x18000ebe9  movzx   ebx, ax
0x18000ebec  or      ebx, r13d
0x18000ebef  test    ebx, ebx
0x18000ebf1  jnz     loc_18000ED69
0x18000ebf7  test    edi, edi
0x18000ebf9  jz      short loc_18000EC03
0x18000ebfb  mov     edi, r15d
0x18000ebfe  call    ?BeginRegistryIsRedirected@RegScanUtil@@SAXXZ; RegScanUtil::BeginRegistryIsRedirected(void)
0x18000ec03  mov     [rbp+4Fh+arg_0], r15
0x18000ec07  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x18000ec0b  call    ?GetSupportDll@RegScanUtil@@SAJPEAPEAG@Z; RegScanUtil::GetSupportDll(ushort * *)
0x18000ec10  mov     rbx, [rbp+4Fh+arg_0]
0x18000ec14  test    rbx, rbx
0x18000ec17  jz      short loc_18000EC2E
0x18000ec19  mov     r9, r14
0x18000ec1c  mov     r8, rbx
0x18000ec1f  call    RegisterUserDllW
0x18000ec24  mov     rcx, rbx; unsigned __int16 *
0x18000ec27  call    ?CheckRegistryIsRedirected@RegScanUtil@@SAXPEAG@Z; RegScanUtil::CheckRegistryIsRedirected(ushort *)
0x18000ec2c  jmp     short loc_18000EBD6
0x18000ec2e  mov     rdx, [rbp+4Fh+phkResult]; hNewHKey
0x18000ec32  mov     rcx, r12; hKey
0x18000ec35  call    cs:__imp_RegOverridePredefKey
0x18000ec3b  mov     ebx, eax
0x18000ec3d  test    eax, eax
0x18000ec3f  jle     short loc_18000EC47
0x18000ec41  movzx   ebx, ax
0x18000ec44  or      ebx, r13d
0x18000ec47  test    ebx, ebx
0x18000ec49  jnz     loc_18000ED69
0x18000ec4f  mov     ecx, cs:?z_fRefCountFile@@3HA; int z_fRefCountFile
0x18000ec55  mov     rax, [rbp+4Fh+var_70]
0x18000ec59  mov     [rax+74h], ecx
0x18000ec5c  cmp     cs:?z_fCopyToRegistry@@3HA, r15d; int z_fCopyToRegistry
0x18000ec63  jnz     short loc_18000EC6E
0x18000ec65  cmp     cs:?z_fDeleteOldKeys@@3HA, r15d; int z_fDeleteOldKeys
0x18000ec6c  jz      short loc_18000ECA9
0x18000ec6e  mov     ecx, cs:?z_fIsBasePartition@@3HA; int z_fIsBasePartition
0x18000ec74  mov     rax, [rbp+4Fh+var_70]
0x18000ec78  mov     [rax+70h], ecx
0x18000ec7b  mov     rdx, rsi; unsigned __int16 *
0x18000ec7e  lea     rcx, [rsp+130h+var_D0]; this
0x18000ec83  call    ?SetRegisteredFileName@RegScan@@QEAAJPEAG@Z; RegScan::SetRegisteredFileName(ushort *)
0x18000ec88  mov     ebx, eax
0x18000ec8a  test    eax, eax
0x18000ec8c  jnz     loc_18000ED69
0x18000ec92  mov     rdx, r12; HKEY
0x18000ec95  lea     rcx, [rsp+130h+var_D0]; this
0x18000ec9a  call    ?ScanSourceKeys@RegScan@@QEAAJPEAUHKEY__@@@Z; RegScan::ScanSourceKeys(HKEY__ *)
0x18000ec9f  mov     ebx, eax
0x18000eca1  test    eax, eax
0x18000eca3  jnz     loc_18000ED69
0x18000eca9  mov     r9, r14
0x18000ecac  mov     r8, rsi
0x18000ecaf  call    RegisterUserDllW
0x18000ecb4  mov     ebx, eax
0x18000ecb6  test    eax, eax
0x18000ecb8  jnz     loc_18000ED69
0x18000ecbe  mov     rcx, rsi; unsigned __int16 *
0x18000ecc1  call    ?CheckRegistryIsRedirected@RegScanUtil@@SAXPEAG@Z; RegScanUtil::CheckRegistryIsRedirected(ushort *)
0x18000ecc6  mov     rdx, [rbp+4Fh+phkResult]; hNewHKey
0x18000ecca  mov     rcx, r12; hKey
0x18000eccd  call    cs:__imp_RegOverridePredefKey
0x18000ecd3  mov     ebx, eax
0x18000ecd5  test    eax, eax
0x18000ecd7  jle     short loc_18000ECDF
0x18000ecd9  movzx   ebx, ax
0x18000ecdc  or      ebx, r13d
0x18000ecdf  test    ebx, ebx
0x18000ece1  jnz     loc_18000ED69
0x18000ece7  cmp     cs:?z_fCopyToRegistry@@3HA, r15d; int z_fCopyToRegistry
0x18000ecee  jnz     short loc_18000ECF9
0x18000ecf0  cmp     cs:?z_fDeleteOldKeys@@3HA, r15d; int z_fDeleteOldKeys
0x18000ecf7  jz      short loc_18000ED26
0x18000ecf9  xor     edx, edx; HKEY
0x18000ecfb  lea     rcx, [rsp+130h+var_D0]; this
0x18000ed00  call    ?ScanSourceKeys@RegScan@@QEAAJPEAUHKEY__@@@Z; RegScan::ScanSourceKeys(HKEY__ *)
0x18000ed05  mov     ebx, eax
0x18000ed07  test    eax, eax
0x18000ed09  jnz     short loc_18000ED69
0x18000ed0b  cmp     cs:?z_fDeleteOldKeys@@3HA, r15d; int z_fDeleteOldKeys
0x18000ed12  jz      short loc_18000ED26
0x18000ed14  xor     edx, edx; int *
0x18000ed16  lea     rcx, [rsp+130h+var_D0]; this
0x18000ed1b  call    ?DeleteOldKeys@RegScan@@QEAAJPEAH@Z; RegScan::DeleteOldKeys(int *)
0x18000ed20  mov     ebx, eax
0x18000ed22  test    eax, eax
0x18000ed24  jnz     short loc_18000ED69
0x18000ed26  xor     edx, edx; hNewHKey
0x18000ed28  mov     rcx, r12; hKey
0x18000ed2b  call    cs:__imp_RegOverridePredefKey
0x18000ed31  mov     ebx, eax
0x18000ed33  test    eax, eax
0x18000ed35  jle     short loc_18000ED3D
0x18000ed37  movzx   ebx, ax
0x18000ed3a  or      ebx, r13d
0x18000ed3d  test    ebx, ebx
0x18000ed3f  jnz     short loc_18000ED69
0x18000ed41  cmp     cs:?z_fCopyToRegistry@@3HA, r15d; int z_fCopyToRegistry
0x18000ed48  jz      short loc_18000ED69
0x18000ed4a  mov     rdx, r12; HKEY
0x18000ed4d  lea     rcx, [rsp+130h+var_D0]; this
0x18000ed52  call    ?ScanDestKeys@RegScan@@QEAAJPEAUHKEY__@@@Z; RegScan::ScanDestKeys(HKEY__ *)
0x18000ed57  mov     ebx, eax
0x18000ed59  test    eax, eax
0x18000ed5b  jnz     short loc_18000ED69
0x18000ed5d  lea     rcx, [rsp+130h+var_D0]; this
0x18000ed62  call    ?CopyKeys@RegScan@@QEAAJXZ; RegScan::CopyKeys(void)
0x18000ed67  mov     ebx, eax
0x18000ed69  xor     edx, edx; hNewHKey
0x18000ed6b  mov     rcx, r12; hKey
0x18000ed6e  call    cs:__imp_RegOverridePredefKey
0x18000ed74  mov     rcx, [rbp+4Fh+phkResult]; hKey
0x18000ed78  test    rcx, rcx
0x18000ed7b  jz      short loc_18000ED84
0x18000ed7d  call    cs:__imp_RegCloseKey
0x18000ed83  nop
0x18000ed84  lea     rcx, [rsp+130h+var_D0]; this
0x18000ed89  call    ??1RegScan@@QEAA@XZ; RegScan::~RegScan(void)
0x18000ed8e  mov     eax, ebx
0x18000ed90  mov     rbx, [rsp+130h+arg_10]
0x18000ed98  add     rsp, 100h
0x18000ed9f  pop     r15
0x18000eda1  pop     r14
0x18000eda3  pop     r13
0x18000eda5  pop     r12
0x18000eda7  pop     rdi
0x18000eda8  pop     rsi
0x18000eda9  pop     rbp
0x18000edaa  retn
```
