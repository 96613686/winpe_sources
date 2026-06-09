# GetLocationInfo(ushort const *,ushort *,ulong)

- ea: `0x180033580`
- end: `0x180033742`
- name: `?GetLocationInfo@@YAXPEBGPEAGK@Z`
- size: `450`
- prototype: `void __fastcall(PCWSTR DeviceInstanceId, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800333cc`

## callees

- `0x1800086f0`
- `0x18001e1e0`
- `0x1800228e8`
- `0x180033580`
- `0x180034ba0`
- `0x180040370`
- `0x1800403ec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180033696`
- `ADVAPI32!RegCloseKey` at `0x180033696`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800335be`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800335be`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180033603`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180033603`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18003365d`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18003365d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180033719`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180033719`

## pseudocode

```c
void __fastcall GetLocationInfo(PCWSTR DeviceInstanceId, unsigned __int16 *a2)
{
  HDEVINFO DeviceInfoList; // rsi
  unsigned int v5; // r8d
  unsigned int *v6; // r9
  int DeviceRegistryProperty; // r14d
  HKEY v8; // rdi
  BOOL v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // edi
  const unsigned __int16 *v12; // rax
  unsigned int v13; // ebx
  unsigned int v14; // edx
  const unsigned __int16 *v15; // rax
  PSP_DEVINFO_DATA DeviceInfoData; // [rsp+20h] [rbp-60h]
  REGSAM samDesired; // [rsp+28h] [rbp-58h]
  unsigned int *v18; // [rsp+30h] [rbp-50h]
  int v19; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int8 v20[4]; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v21; // [rsp+48h] [rbp-38h] BYREF
  struct _SP_DEVINFO_DATA v22; // [rsp+50h] [rbp-30h] BYREF

  memset(&v22, 0, sizeof(v22));
  DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0);
  if ( DeviceInfoList != (HDEVINFO)-1LL || (DeviceInfoList = 0, !(unsigned int)HrFromLastWin32Error()) )
  {
    memset(&v22, 0, sizeof(v22));
    v22.cbSize = 32;
    if ( !SetupDiOpenDeviceInfoW(DeviceInfoList, DeviceInstanceId, 0, 0, &v22) && (unsigned int)HrFromLastWin32Error() )
      goto LABEL_15;
    *(_DWORD *)v20 = 0;
    v21 = 0;
    DeviceRegistryProperty = HrSetupDiGetDeviceRegistryProperty(DeviceInfoList, &v22, v5, v6, v20, samDesired, v18);
    v8 = SetupDiOpenDevRegKey(DeviceInfoList, &v22, 1u, 0, 1u, 0x20019u);
    if ( v8 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL || (v9 = 0, v8 = 0, !(unsigned int)HrFromLastWin32Error()) )
    {
      v9 = HrRegQueryDword(v8, L"Port", &v21) == 0;
      RegCloseKey(v8);
    }
    if ( DeviceRegistryProperty )
    {
      if ( !v9 )
        goto LABEL_15;
      v13 = v21;
      v19 = 0;
      v14 = 16052;
    }
    else
    {
      v19 = 0;
      if ( v9 )
      {
        v10 = v21;
        v11 = *(_DWORD *)v20;
        v12 = SzLoadStringPcch(hInst, 0x3EB2u, &v19);
        LODWORD(DeviceInfoData) = v10;
        StringCchPrintfW(a2, 0x104u, v12, v11, DeviceInfoData);
LABEL_15:
        SetupDiDestroyDeviceInfoList(DeviceInfoList);
        return;
      }
      v13 = *(_DWORD *)v20;
      v14 = 16051;
    }
    v15 = SzLoadStringPcch(hInst, v14, &v19);
    StringCchPrintfW(a2, 0x104u, v15, v13);
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x180033580  mov     [rsp-28h+arg_10], rbx
0x180033585  push    rbp
0x180033586  push    rsi
0x180033587  push    rdi
0x180033588  push    r14
0x18003358a  push    r15
0x18003358c  mov     rbp, rsp
0x18003358f  sub     rsp, 80h
0x180033596  mov     rax, cs:__security_cookie
0x18003359d  xor     rax, rsp
0x1800335a0  mov     [rbp+var_10], rax
0x1800335a4  xorps   xmm0, xmm0
0x1800335a7  mov     r15, rdx
0x1800335aa  mov     rbx, rcx
0x1800335ad  xor     edx, edx; hwndParent
0x1800335af  lea     rcx, GUID_DEVCLASS_NET; ClassGuid
0x1800335b6  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x1800335ba  movups  xmmword ptr [rbp+var_30.ClassGuid.Data4+4], xmm0
0x1800335be  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800335c4  mov     rsi, rax
0x1800335c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800335cb  jnz     short loc_1800335DC
0x1800335cd  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800335d2  xor     esi, esi
0x1800335d4  test    eax, eax
0x1800335d6  jnz     loc_18003371F
0x1800335dc  xorps   xmm0, xmm0
0x1800335df  lea     rax, [rbp+var_30]
0x1800335e3  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x1800335e7  xor     r9d, r9d; OpenFlags
0x1800335ea  mov     [rbp+var_30.cbSize], 20h ; ' '
0x1800335f1  xor     r8d, r8d; hwndParent
0x1800335f4  mov     [rsp+80h+DeviceInfoData], rax; DeviceInfoData
0x1800335f9  mov     rdx, rbx; DeviceInstanceId
0x1800335fc  mov     rcx, rsi; DeviceInfoSet
0x1800335ff  movups  xmmword ptr [rbp+var_30.ClassGuid.Data4+4], xmm0
0x180033603  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180033609  test    eax, eax
0x18003360b  jnz     short loc_18003361A
0x18003360d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033612  test    eax, eax
0x180033614  jnz     loc_180033716
0x18003361a  lea     rax, [rbp+var_3C]
0x18003361e  mov     dword ptr [rbp+var_3C], 0
0x180033625  lea     rdx, [rbp+var_30]; struct _SP_DEVINFO_DATA *
0x180033629  mov     [rsp+80h+DeviceInfoData], rax; unsigned __int8 *
0x18003362e  mov     rcx, rsi; void *
0x180033631  mov     [rbp+var_38], 0
0x180033638  call    ?HrSetupDiGetDeviceRegistryProperty@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KPEAKPEAEK2@Z; HrSetupDiGetDeviceRegistryProperty(void *,_SP_DEVINFO_DATA *,ulong,ulong *,uchar *,ulong,ulong *)
0x18003363d  mov     r8d, 1; Scope
0x180033643  mov     [rsp+80h+samDesired], 20019h; samDesired
0x18003364b  xor     r9d, r9d; HwProfile
0x18003364e  mov     dword ptr [rsp+80h+DeviceInfoData], r8d; KeyType
0x180033653  lea     rdx, [rbp+var_30]; DeviceInfoData
0x180033657  mov     rcx, rsi; DeviceInfoSet
0x18003365a  mov     r14d, eax
0x18003365d  call    cs:__imp_SetupDiOpenDevRegKey
0x180033663  mov     rdi, rax
0x180033666  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003366a  jnz     short loc_180033679
0x18003366c  xor     ebx, ebx
0x18003366e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033673  xor     edi, edi
0x180033675  test    eax, eax
0x180033677  jnz     short loc_18003369C
0x180033679  lea     r8, [rbp+var_38]; unsigned int *
0x18003367d  mov     rcx, rdi; HKEY
0x180033680  lea     rdx, aPort; "Port"
0x180033687  call    ?HrRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; HrRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18003368c  xor     ebx, ebx
0x18003368e  mov     rcx, rdi; hKey
0x180033691  test    eax, eax
0x180033693  setz    bl
0x180033696  call    cs:__imp_RegCloseKey
0x18003369c  mov     rcx, cs:hInst; hModule
0x1800336a3  test    r14d, r14d
0x1800336a6  jnz     short loc_1800336E7
0x1800336a8  mov     [rbp+var_40], r14d
0x1800336ac  lea     r8, [rbp+var_40]; int *
0x1800336b0  test    ebx, ebx
0x1800336b2  jz      short loc_1800336DD
0x1800336b4  mov     ebx, [rbp+var_38]
0x1800336b7  mov     edx, 3EB2h; unsigned int
0x1800336bc  mov     edi, dword ptr [rbp+var_3C]
0x1800336bf  call    ?SzLoadStringPcch@@YAPEBGPEAUHINSTANCE__@@IPEAH@Z; SzLoadStringPcch(HINSTANCE__ *,uint,int *)
0x1800336c4  mov     r9d, edi
0x1800336c7  mov     dword ptr [rsp+80h+DeviceInfoData], ebx
0x1800336cb  mov     r8, rax; unsigned __int16 *
0x1800336ce  mov     edx, 104h; unsigned __int64
0x1800336d3  mov     rcx, r15; unsigned __int16 *
0x1800336d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800336db  jmp     short loc_180033716
0x1800336dd  mov     ebx, dword ptr [rbp+var_3C]
0x1800336e0  mov     edx, 3EB3h
0x1800336e5  jmp     short loc_1800336FE
0x1800336e7  test    ebx, ebx
0x1800336e9  jz      short loc_180033716
0x1800336eb  mov     ebx, [rbp+var_38]
0x1800336ee  lea     r8, [rbp+var_40]; int *
0x1800336f2  mov     [rbp+var_40], 0
0x1800336f9  mov     edx, 3EB4h; unsigned int
0x1800336fe  call    ?SzLoadStringPcch@@YAPEBGPEAUHINSTANCE__@@IPEAH@Z; SzLoadStringPcch(HINSTANCE__ *,uint,int *)
0x180033703  mov     r9d, ebx
0x180033706  mov     r8, rax; unsigned __int16 *
0x180033709  mov     edx, 104h; unsigned __int64
0x18003370e  mov     rcx, r15; unsigned __int16 *
0x180033711  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033716  mov     rcx, rsi; DeviceInfoSet
0x180033719  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18003371f  mov     rcx, [rbp+var_10]
0x180033723  xor     rcx, rsp; StackCookie
0x180033726  call    __security_check_cookie
0x18003372b  mov     rbx, [rsp+80h+arg_10]
0x180033733  add     rsp, 80h
0x18003373a  pop     r15
0x18003373c  pop     r14
0x18003373e  pop     rdi
0x18003373f  pop     rsi
0x180033740  pop     rbp
0x180033741  retn
```
