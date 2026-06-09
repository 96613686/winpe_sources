# CWin32VideoController::SetServiceProperties(CInstance *,ushort const *,HKEY__ * &)

- ea: `0x18004fc8c`
- end: `0x18004fff5`
- name: `?SetServiceProperties@CWin32VideoController@@IEAAXPEAVCInstance@@PEBGAEAPEAUHKEY__@@@Z`
- size: `873`
- prototype: `void __fastcall(CWin32VideoController *__hidden this, struct CInstance *, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180072614`

## callees

- `0x18004fc8c`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004fef8`
- `framedynos!?SetAt@CHString@@QEAAXHG@Z` at `0x18004fd5d`
- `framedynos!?SetAt@CHString@@QEAAXHG@Z` at `0x18004fd5d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004fd01`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004feb1`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004fd01`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004feb1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004fdd3`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004fdd3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004fd96`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffb3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffc8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffdd`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004fd96`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffb3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffc8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18004ffdd`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18004fd28`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18004fd28`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18004fcc2`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18004fcc2`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18004fe82`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18004fe82`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18004fcee`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18004fcee`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x18004fde3`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x18004fde3`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18004fecd`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18004fecd`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18004fd7d`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18004ff62`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18004fd7d`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18004ff62`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18004ff57`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18004ff9e`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18004ff57`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x18004ff9e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004fe2d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004fe6a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004fe2d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004fe6a`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18004fd3a`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18004fd6d`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18004fd3a`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18004fd6d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18004fd19`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18004ff1a`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18004fd19`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18004ff1a`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fdba`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fe12`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fe4f`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004ff45`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004ff88`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fdba`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fe12`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004fe4f`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004ff45`
- `framedynos!?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z` at `0x18004ff88`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004fe76`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004ffe9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004fe76`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004ffe9`

## string_xrefs

- `0x18004fd8c`: `InstalledDisplayDrivers`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWin32VideoController::SetServiceProperties(
        CWin32VideoController *this,
        struct CInstance *a2,
        const unsigned __int16 *a3,
        HKEY *a4)
{
  int Length; // ebx
  int v7; // eax
  int v8; // ebx
  HKEY v9; // rax
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[608]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[256]; // [rsp+2C0h] [rbp+1C0h] BYREF

  CRegistry::CRegistry((CRegistry *)v16);
  v14 = 0;
  v10 = 0;
  if ( !CRegistry::Open((CRegistry *)v16, *a4, (const unsigned __int16 *)&Data, 0x20019u) )
  {
    CHString::CHString((CHString *)v12);
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"UserModeDriverName", (struct CHString *)v12) )
    {
      Length = CHString::GetLength((CHString *)v12);
      v7 = CHString::Find((CHString *)v12, 0xAu);
      if ( v7 != -1 )
      {
        v8 = Length - 1;
        do
        {
          CHString::SetAt((CHString *)v12, v7, v8 != v7 ? 0x2C : 0);
          v7 = CHString::Find((CHString *)v12, 0xAu);
        }
        while ( v7 != -1 );
      }
    }
    if ( !CHString::IsEmpty((CHString *)v12) )
      CInstance::SetCHString(a2, L"InstalledDisplayDrivers", (const struct CHString *)v12);
    v10 = 4;
    if ( !CRegistry::GetCurrentBinaryKeyValue(
            (CRegistry *)v16,
            L"HardwareInformation.MemorySize",
            (unsigned __int8 *)&v14,
            &v10) )
      CInstance::SetDWORD(a2, L"AdapterRAM", v14);
    if ( CInstance::IsNull(a2, L"Description") )
    {
      CHString::CHString((CHString *)v11);
      Type = 0;
      cbData[0] = 0;
      v9 = CRegistry::GethKey((CRegistry *)v16);
      if ( !RegQueryValueExW(v9, L"Device Description", 0, &Type, 0, cbData) )
      {
        if ( Type == 1 )
        {
          CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"Device Description", (struct CHString *)v11);
        }
        else if ( Type == 3 )
        {
          v10 = 512;
          CRegistry::GetCurrentBinaryKeyValue((CRegistry *)v16, L"Device Description", (unsigned __int8 *)v17, &v10);
          CHString::operator=(v11, v17);
        }
      }
      if ( CHString::IsEmpty((CHString *)v11) )
      {
        v10 = 512;
        if ( !CRegistry::GetCurrentBinaryKeyValue(
                (CRegistry *)v16,
                L"HardwareInformation.AdapterString",
                (unsigned __int8 *)v17,
                &v10) )
          CHString::operator=(v11, v17);
      }
      CInstance::SetCHString(a2, L"Description", (const struct CHString *)v11);
      CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v11);
      CInstance::SetCHString(a2, L"Name", (const struct CHString *)v11);
      CHString::~CHString((CHString *)v11);
    }
    v10 = 512;
    if ( !CRegistry::GetCurrentBinaryKeyValue(
            (CRegistry *)v16,
            L"HardwareInformation.ChipType",
            (unsigned __int8 *)v17,
            &v10) )
      CInstance::SetCHString(a2, L"VideoProcessor", v17);
    v10 = 512;
    if ( !CRegistry::GetCurrentBinaryKeyValue(
            (CRegistry *)v16,
            L"HardwareInformation.DACType",
            (unsigned __int8 *)v17,
            &v10) )
      CInstance::SetCHString(a2, L"AdapterDACType", v17);
    CHString::~CHString((CHString *)v12);
  }
  CRegistry::~CRegistry((CRegistry *)v16);
}

```

## disassembly

```asm
0x18004fc8c  mov     [rsp-8+arg_0], rbx
0x18004fc91  mov     [rsp-8+arg_10], rdi
0x18004fc96  push    rbp
0x18004fc97  lea     rbp, [rsp-3D0h]
0x18004fc9f  sub     rsp, 4D0h
0x18004fca6  mov     rax, cs:__security_cookie
0x18004fcad  xor     rax, rsp
0x18004fcb0  mov     [rbp+3D0h+var_10], rax
0x18004fcb7  mov     rbx, r9
0x18004fcba  mov     rdi, rdx
0x18004fcbd  lea     rcx, [rsp+4D0h+var_470]
0x18004fcc2  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18004fcc8  nop
0x18004fcc9  mov     [rsp+4D0h+var_484], 0
0x18004fcd1  mov     [rsp+4D0h+var_4A0], 0
0x18004fcd9  mov     r9d, 20019h
0x18004fcdf  lea     r8, Data
0x18004fce6  mov     rdx, [rbx]
0x18004fce9  lea     rcx, [rsp+4D0h+var_470]
0x18004fcee  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18004fcf4  test    eax, eax
0x18004fcf6  jnz     loc_18004FE7D
0x18004fcfc  lea     rcx, [rsp+4D0h+var_490]
0x18004fd01  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18004fd07  nop
0x18004fd08  lea     r8, [rsp+4D0h+var_490]
0x18004fd0d  lea     rdx, aUsermodedriver; "UserModeDriverName"
0x18004fd14  lea     rcx, [rsp+4D0h+var_470]
0x18004fd19  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18004fd1f  test    eax, eax
0x18004fd21  jnz     short loc_18004FD78
0x18004fd23  lea     rcx, [rsp+4D0h+var_490]
0x18004fd28  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x18004fd2e  mov     ebx, eax
0x18004fd30  mov     edx, 0Ah
0x18004fd35  lea     rcx, [rsp+4D0h+var_490]
0x18004fd3a  call    cs:__imp_?Find@CHString@@QEBAHG@Z; CHString::Find(ushort)
0x18004fd40  cmp     eax, 0FFFFFFFFh
0x18004fd43  jz      short loc_18004FD78
0x18004fd45  dec     ebx
0x18004fd47  mov     ecx, eax
0x18004fd49  sub     ecx, ebx
0x18004fd4b  neg     ecx
0x18004fd4d  sbb     r8w, r8w
0x18004fd51  and     r8w, 2Ch
0x18004fd56  mov     edx, eax
0x18004fd58  lea     rcx, [rsp+4D0h+var_490]
0x18004fd5d  call    cs:__imp_?SetAt@CHString@@QEAAXHG@Z; CHString::SetAt(int,ushort)
0x18004fd63  mov     edx, 0Ah
0x18004fd68  lea     rcx, [rsp+4D0h+var_490]
0x18004fd6d  call    cs:__imp_?Find@CHString@@QEBAHG@Z; CHString::Find(ushort)
0x18004fd73  cmp     eax, 0FFFFFFFFh
0x18004fd76  jnz     short loc_18004FD47
0x18004fd78  lea     rcx, [rsp+4D0h+var_490]
0x18004fd7d  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18004fd83  test    eax, eax
0x18004fd85  jnz     short loc_18004FD9C
0x18004fd87  lea     r8, [rsp+4D0h+var_490]
0x18004fd8c  lea     rdx, aInstalleddispl; "InstalledDisplayDrivers"
0x18004fd93  mov     rcx, rdi
0x18004fd96  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18004fd9c  mov     [rsp+4D0h+var_4A0], 4
0x18004fda4  lea     r9, [rsp+4D0h+var_4A0]
0x18004fda9  lea     r8, [rsp+4D0h+var_484]
0x18004fdae  lea     rdx, aHardwareinform_1; "HardwareInformation.MemorySize"
0x18004fdb5  lea     rcx, [rsp+4D0h+var_470]
0x18004fdba  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18004fdc0  test    eax, eax
0x18004fdc2  jnz     short loc_18004FDD9
0x18004fdc4  mov     r8d, [rsp+4D0h+var_484]
0x18004fdc9  lea     rdx, aAdapterram; "AdapterRAM"
0x18004fdd0  mov     rcx, rdi
0x18004fdd3  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18004fdd9  lea     rdx, aDescription; "Description"
0x18004fde0  mov     rcx, rdi
0x18004fde3  call    cs:__imp_?IsNull@CInstance@@QEBA_NPEBG@Z; CInstance::IsNull(ushort const *)
0x18004fde9  mov     ebx, 200h
0x18004fdee  test    al, al
0x18004fdf0  jnz     loc_18004FEAC
0x18004fdf6  mov     [rsp+4D0h+var_4A0], ebx
0x18004fdfa  lea     r9, [rsp+4D0h+var_4A0]
0x18004fdff  lea     r8, [rbp+3D0h+var_210]
0x18004fe06  lea     rdx, aHardwareinform_2; "HardwareInformation.ChipType"
0x18004fe0d  lea     rcx, [rsp+4D0h+var_470]
0x18004fe12  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18004fe18  test    eax, eax
0x18004fe1a  jnz     short loc_18004FE33
0x18004fe1c  lea     r8, [rbp+3D0h+var_210]
0x18004fe23  lea     rdx, aVideoprocessor; "VideoProcessor"
0x18004fe2a  mov     rcx, rdi
0x18004fe2d  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x18004fe33  mov     [rsp+4D0h+var_4A0], ebx
0x18004fe37  lea     r9, [rsp+4D0h+var_4A0]
0x18004fe3c  lea     r8, [rbp+3D0h+var_210]
0x18004fe43  lea     rdx, aHardwareinform; "HardwareInformation.DACType"
0x18004fe4a  lea     rcx, [rsp+4D0h+var_470]
0x18004fe4f  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18004fe55  test    eax, eax
0x18004fe57  jnz     short loc_18004FE71
0x18004fe59  lea     r8, [rbp+3D0h+var_210]
0x18004fe60  lea     rdx, aAdapterdactype; "AdapterDACType"
0x18004fe67  mov     rcx, rdi
0x18004fe6a  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x18004fe70  nop
0x18004fe71  lea     rcx, [rsp+4D0h+var_490]
0x18004fe76  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18004fe7c  nop
0x18004fe7d  lea     rcx, [rsp+4D0h+var_470]
0x18004fe82  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18004fe88  mov     rcx, [rbp+3D0h+var_10]
0x18004fe8f  xor     rcx, rsp; StackCookie
0x18004fe92  call    __security_check_cookie
0x18004fe97  lea     r11, [rsp+4D0h+var_s0]
0x18004fe9f  mov     rbx, [r11+10h]
0x18004fea3  mov     rdi, [r11+20h]
0x18004fea7  mov     rsp, r11
0x18004feaa  pop     rbp
0x18004feab  retn
0x18004feac  lea     rcx, [rsp+4D0h+var_498]
0x18004feb1  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18004feb7  nop
0x18004feb8  mov     [rsp+4D0h+Type], 0
0x18004fec0  mov     [rsp+4D0h+cbData], 0
0x18004fec8  lea     rcx, [rsp+4D0h+var_470]
0x18004fecd  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x18004fed3  mov     rcx, rax; hKey
0x18004fed6  lea     rax, [rsp+4D0h+cbData]
0x18004fedb  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x18004fee0  mov     [rsp+4D0h+lpData], 0; lpData
0x18004fee9  lea     r9, [rsp+4D0h+Type]; lpType
0x18004feee  xor     r8d, r8d; lpReserved
0x18004fef1  lea     rdx, aDeviceDescript; "Device Description"
0x18004fef8  call    cs:__imp_RegQueryValueExW
0x18004fefe  test    eax, eax
0x18004ff00  jnz     short loc_18004FF5D
0x18004ff02  cmp     [rsp+4D0h+Type], 1
0x18004ff07  jnz     short loc_18004FF22
0x18004ff09  lea     r8, [rsp+4D0h+var_498]
0x18004ff0e  lea     rdx, aDeviceDescript; "Device Description"
0x18004ff15  lea     rcx, [rsp+4D0h+var_470]
0x18004ff1a  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18004ff20  jmp     short loc_18004FF5D
0x18004ff22  cmp     [rsp+4D0h+Type], 3
0x18004ff27  jnz     short loc_18004FF5D
0x18004ff29  mov     [rsp+4D0h+var_4A0], ebx
0x18004ff2d  lea     r9, [rsp+4D0h+var_4A0]
0x18004ff32  lea     r8, [rbp+3D0h+var_210]
0x18004ff39  lea     rdx, aDeviceDescript; "Device Description"
0x18004ff40  lea     rcx, [rsp+4D0h+var_470]
0x18004ff45  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18004ff4b  lea     rdx, [rbp+3D0h+var_210]
0x18004ff52  lea     rcx, [rsp+4D0h+var_498]
0x18004ff57  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18004ff5d  lea     rcx, [rsp+4D0h+var_498]
0x18004ff62  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18004ff68  test    eax, eax
0x18004ff6a  jz      short loc_18004FFA4
0x18004ff6c  mov     [rsp+4D0h+var_4A0], ebx
0x18004ff70  lea     r9, [rsp+4D0h+var_4A0]
0x18004ff75  lea     r8, [rbp+3D0h+var_210]
0x18004ff7c  lea     rdx, aHardwareinform_0; "HardwareInformation.AdapterString"
0x18004ff83  lea     rcx, [rsp+4D0h+var_470]
0x18004ff88  call    cs:__imp_?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGPEAEPEAK@Z; CRegistry::GetCurrentBinaryKeyValue(ushort const *,uchar *,ulong *)
0x18004ff8e  test    eax, eax
0x18004ff90  jnz     short loc_18004FFA4
0x18004ff92  lea     rdx, [rbp+3D0h+var_210]
0x18004ff99  lea     rcx, [rsp+4D0h+var_498]
0x18004ff9e  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18004ffa4  lea     r8, [rsp+4D0h+var_498]
0x18004ffa9  lea     rdx, aDescription; "Description"
0x18004ffb0  mov     rcx, rdi
0x18004ffb3  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18004ffb9  lea     r8, [rsp+4D0h+var_498]
0x18004ffbe  lea     rdx, aCaption; "Caption"
0x18004ffc5  mov     rcx, rdi
0x18004ffc8  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18004ffce  lea     r8, [rsp+4D0h+var_498]
0x18004ffd3  lea     rdx, aName; "Name"
0x18004ffda  mov     rcx, rdi
0x18004ffdd  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18004ffe3  nop
0x18004ffe4  lea     rcx, [rsp+4D0h+var_498]
0x18004ffe9  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18004ffef  jmp     loc_18004FDF6
```
