# CDeviceProfile::_SetOptionsUnderLock(void)

- ea: `0x1800dda08`
- end: `0x1800ddee7`
- name: `?_SetOptionsUnderLock@CDeviceProfile@@AEAAXXZ`
- size: `1247`
- prototype: `void __fastcall(CDeviceProfile *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dd968`

## callees

- `0x180008618`
- `0x18000933c`
- `0x1800095a0`
- `0x18009b290`
- `0x18009b300`
- `0x1800a49c4`
- `0x1800a4a9c`
- `0x1800ac938`
- `0x1800dda08`
- `0x1800ddf10`
- `0x1800de250`
- `0x1800e0f58`
- `0x1800eeedc`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ddc7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ddcc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ddcc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ddbfc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ddbfc`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExA` at `0x1800ddabe`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExA` at `0x1800ddabe`
- `netutils!NetApiBufferFree` at `0x1800ddc5c`
- `netutils!NetApiBufferFree` at `0x1800ddc5c`

## string_xrefs

- `0x1800ddbf5`: `Netapi32.dll`
- `0x1800ddb57`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x1800dddef`: `CommercialId`
- `0x1800dde14`: `CommercialId`
- `0x1800dda90`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\DeviceProfile.cpp`
- `0x1800ddacc`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\DeviceProfile.cpp`
- `0x1800ddd29`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\PolicyProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CDeviceProfile::_SetOptionsUnderLock(CDeviceProfile *this)
{
  __int16 v2; // bx
  int CachePath; // eax
  int v4; // edi
  const CHAR *v5; // rcx
  const char *v6; // r9
  int LastError; // eax
  const char *v8; // rcx
  __int16 v9; // si
  __int16 v10; // di
  __int128 *v11; // rax
  struct CPersistenceLocation *v12; // rax
  const char *v13; // rbx
  struct CPersistenceLocation *v14; // rax
  HMODULE Library; // rax
  HMODULE v16; // rbx
  bool v17; // r12
  FARPROC ProcAddress; // rax
  FARPROC v19; // r15
  FARPROC v20; // rax
  void (__fastcall *v21)(LPVOID); // rsi
  int v22; // esi
  char *v23; // rcx
  int v24; // eax
  union _ULARGE_INTEGER v25; // rcx
  signed int v26; // ebx
  union _ULARGE_INTEGER v27; // rcx
  int v28; // eax
  int v29; // ecx
  bool v30; // bl
  LPCSTR *v31; // rax
  __int64 v32; // [rsp+28h] [rbp-39h] BYREF
  LPVOID Buffer; // [rsp+30h] [rbp-31h] BYREF
  bool v34; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v35[7]; // [rsp+39h] [rbp-28h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+40h] [rbp-21h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-19h] BYREF
  unsigned int v38; // [rsp+4Ch] [rbp-15h] BYREF
  LPCSTR lpDirectoryName[2]; // [rsp+50h] [rbp-11h] BYREF
  __m128i si128; // [rsp+60h] [rbp-1h]
  __int128 v41; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+80h] [rbp+1Fh]
  unsigned __int64 v43; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v2 = *((_WORD *)this + 1) & 0xD;
  if ( !*((_BYTE *)this + 4) && CDeviceProfile::_IsOnVirtualMachine() )
    v2 |= 1u;
  *(_OWORD *)lpDirectoryName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(lpDirectoryName[0]) = 0;
  CachePath = CPersistenceLocation::GetCachePath(lpDirectoryName, 0);
  v4 = CachePath;
  if ( CachePath >= 0 )
  {
    TotalNumberOfBytes.QuadPart = 0;
    v5 = (const CHAR *)lpDirectoryName;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v5 = lpDirectoryName[0];
    if ( GetDiskFreeSpaceExA(v5, 0, &TotalNumberOfBytes, 0) )
    {
      if ( TotalNumberOfBytes.QuadPart > 0x800000000LL )
      {
        v4 = -2147023728;
        goto LABEL_16;
      }
      v32 = 0;
      Buffer = 0;
      v8 = (const char *)lpDirectoryName;
      if ( si128.m128i_i64[1] > 0xFuLL )
        v8 = lpDirectoryName[0];
      LastError = QuerySoftReserve(v8, &v32, (unsigned __int64 *)&Buffer);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1D3,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\DeviceProfile.cpp",
                    v6);
    }
    v4 = LastError;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D0,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\DeviceProfile.cpp",
    (const char *)(unsigned int)CachePath,
    v32);
LABEL_16:
  std::string::~string(lpDirectoryName);
  v9 = v2 | 0x80;
  if ( v4 < 0 )
    v9 = v2;
  v41 = 0;
  v42 = 0;
  v43 = 15;
  LOBYTE(v41) = 0;
  v10 = v9;
  if ( (int)RegQueryStringValue(
              -2147483646,
              "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
              "ActivePolicyCode",
              &v41) >= 0 )
  {
    v11 = &v41;
    if ( v43 > 0xF )
      v11 = (__int128 *)v41;
    if ( v42 == 2 && *(_WORD *)v11 == 26746 )
      v10 = v9 | 0x200;
  }
  v37 = 0;
  v12 = CPersistenceLocation::Instance();
  v13 = (char *)v12 + 32;
  if ( *((_QWORD *)v12 + 7) > 0xFu )
    v13 = *(const char **)v13;
  v14 = CPersistenceLocation::Instance();
  if ( (int)RegQueryDwordValue((HKEY)(-(__int64)(*((_BYTE *)v14 + 160) != 0) - 2147483645), v13, "Profile_RDX", &v37) >= 0
    && v37 )
  {
    v10 |= 2u;
  }
  if ( !*((_BYTE *)this + 4) )
  {
    Library = LoadLibraryExA("Netapi32.dll", 0, 0x800u);
    v16 = Library;
    v32 = (__int64)Library;
    v17 = Library != 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "NetGetJoinInformation");
      if ( ProcAddress )
      {
        TotalNumberOfBytes.LowPart = 0;
        Buffer = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, LPVOID *, union _ULARGE_INTEGER *))ProcAddress)(
                0,
                &Buffer,
                &TotalNumberOfBytes)
          && TotalNumberOfBytes.LowPart == 3 )
        {
          v10 |= 4u;
        }
        if ( Buffer )
          NetApiBufferFree(Buffer);
      }
      v19 = GetProcAddress(v16, "NetGetAadJoinInformation");
      v20 = GetProcAddress(v16, "NetFreeAadJoinInformation");
      v21 = (void (__fastcall *)(LPVOID))v20;
      if ( v19 )
      {
        if ( v20 )
        {
          Buffer = 0;
          if ( ((int (__fastcall *)(_QWORD, LPVOID *))v19)(0, &Buffer) >= 0 )
          {
            if ( Buffer )
            {
              v10 |= 8u;
              v21(Buffer);
            }
          }
        }
      }
    }
    if ( v17 )
      FreeLibrary(v16);
  }
  v22 = 0;
  while ( 1 )
  {
    v23 = (&off_180124FD8)[10 * v22];
    if ( v23 )
      break;
LABEL_55:
    if ( (unsigned int)++v22 >= 0xC3 )
      goto LABEL_58;
  }
  TotalNumberOfBytes.QuadPart = 0;
  if ( (int)GetNamedPolicy(v23, &TotalNumberOfBytes) < 0 )
  {
LABEL_49:
    v25 = TotalNumberOfBytes;
    if ( TotalNumberOfBytes.QuadPart )
    {
      TotalNumberOfBytes.QuadPart = 0;
      (*(void (__fastcall **)(union _ULARGE_INTEGER))(*(_QWORD *)v25.QuadPart + 16LL))(v25);
    }
    goto LABEL_55;
  }
  v35[0] = 0;
  v24 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER, _BYTE *))(*(_QWORD *)TotalNumberOfBytes.QuadPart + 72LL))(
          TotalNumberOfBytes,
          v35);
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\PolicyProvider.cpp",
      (const char *)(unsigned int)v24,
      v32);
    goto LABEL_49;
  }
  v26 = v35[0] == 0 ? 0x80070490 : 0;
  v27 = TotalNumberOfBytes;
  if ( TotalNumberOfBytes.QuadPart )
  {
    TotalNumberOfBytes.QuadPart = 0;
    (*(void (__fastcall **)(union _ULARGE_INTEGER))(*(_QWORD *)v27.QuadPart + 16LL))(v27);
  }
  if ( v26 < 0 )
    goto LABEL_55;
  v10 |= 0x20u;
LABEL_58:
  v34 = 0;
  if ( !CGlobalObjects::_pPlatformHost )
    goto LABEL_63;
  v28 = (*(__int64 (__fastcall **)(struct IDOPlatformHost *, bool *))(*(_QWORD *)CGlobalObjects::_pPlatformHost + 56LL))(
          CGlobalObjects::_pPlatformHost,
          &v34);
  v29 = 0;
  if ( v28 < 0 )
    v29 = v28;
  if ( v29 >= 0 )
  {
    v30 = v34;
  }
  else
  {
LABEL_63:
    *(_OWORD *)lpDirectoryName = 0;
    si128.m128i_i64[0] = 0;
    si128.m128i_i64[1] = 15;
    LOBYTE(lpDirectoryName[0]) = 0;
    if ( (int)RegQueryStringValue(
                -2147483646,
                "SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
                "CommercialId",
                lpDirectoryName) < 0
      && (int)RegQueryStringValue(
                -2147483646,
                "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
                "CommercialId",
                lpDirectoryName) < 0 )
    {
      si128.m128i_i64[0] = 0;
      v31 = lpDirectoryName;
      if ( si128.m128i_i64[1] > 0xFuLL )
        v31 = (LPCSTR *)lpDirectoryName[0];
      *(_BYTE *)v31 = 0;
    }
    v30 = si128.m128i_i64[0] != 0;
    std::string::~string(lpDirectoryName);
    v34 = v30;
  }
  if ( v30 )
    v10 |= 0x10u;
  v38 = 0;
  if ( (int)RegQueryDwordValue(
              HKEY_LOCAL_MACHINE,
              "Software\\Microsoft\\Windows\\CurrentVersion\\SharedPC",
              "EduSharedPCMode",
              &v38) >= 0
    && v38 )
  {
    v10 |= 0x40u;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit>::GetImpl'::`2'::impl)
    && CDeviceProfile::_IsWindowsInsider() )
  {
    v10 |= 0x400u;
  }
  *((_WORD *)this + 1) = v10;
  *((_BYTE *)this + 4) = 1;
  std::string::~string(&v41);
}

```

## disassembly

```asm
0x1800dda08  mov     rax, rsp
0x1800dda0b  mov     [rax+10h], rbx
0x1800dda0f  mov     [rax+18h], rsi
0x1800dda13  mov     [rax+20h], rdi
0x1800dda17  push    rbp
0x1800dda18  push    r12
0x1800dda1a  push    r13
0x1800dda1c  push    r14
0x1800dda1e  push    r15
0x1800dda20  lea     rbp, [rax-5Fh]
0x1800dda24  sub     rsp, 90h
0x1800dda2b  mov     rax, cs:__security_cookie
0x1800dda32  xor     rax, rsp
0x1800dda35  mov     [rbp+57h+var_28], rax
0x1800dda39  mov     r14, rcx
0x1800dda3c  movzx   ebx, word ptr [rcx+2]
0x1800dda40  and     bx, 0Dh
0x1800dda44  mov     r12d, 1
0x1800dda4a  xor     r13d, r13d
0x1800dda4d  cmp     [rcx+4], r13b
0x1800dda51  jnz     short loc_1800DDA60
0x1800dda53  call    ?_IsOnVirtualMachine@CDeviceProfile@@CA_NXZ; CDeviceProfile::_IsOnVirtualMachine(void)
0x1800dda58  test    al, al
0x1800dda5a  jz      short loc_1800DDA60
0x1800dda5c  or      bx, r12w
0x1800dda60  xorps   xmm0, xmm0
0x1800dda63  movups  xmmword ptr [rbp+57h+lpDirectoryName], xmm0
0x1800dda67  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800dda6f  movdqu  [rbp+57h+var_58], xmm1
0x1800dda74  mov     byte ptr [rbp+57h+lpDirectoryName], r13b
0x1800dda78  xor     edx, edx
0x1800dda7a  lea     rcx, [rbp+57h+lpDirectoryName]
0x1800dda7e  call    ?GetCachePath@CPersistenceLocation@@SAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; CPersistenceLocation::GetCachePath(std::string &,char const *)
0x1800dda83  mov     edi, eax
0x1800dda85  test    eax, eax
0x1800dda87  jns     short loc_1800DDAA3
0x1800dda89  mov     rcx, [rbp+5Fh]; this
0x1800dda8d  mov     r9d, eax; char *
0x1800dda90  lea     r8, aCW1SSrcDeliver_34; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800dda97  mov     edx, 1D0h; void *
0x1800dda9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddaa1  jmp     short loc_1800DDB1B
0x1800ddaa3  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r13
0x1800ddaa7  lea     rcx, [rbp+57h+lpDirectoryName]
0x1800ddaab  cmp     qword ptr [rbp+57h+var_58+8], 0Fh
0x1800ddab0  cmova   rcx, [rbp+57h+lpDirectoryName]; lpDirectoryName
0x1800ddab5  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x1800ddab8  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800ddabc  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1800ddabe  call    cs:__imp_GetDiskFreeSpaceExA
0x1800ddac4  test    eax, eax
0x1800ddac6  jnz     short loc_1800DDADF
0x1800ddac8  mov     rcx, [rbp+5Fh]; this
0x1800ddacc  lea     r8, aCW1SSrcDeliver_34; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ddad3  mov     edx, 1D3h; void *
0x1800ddad8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ddadd  jmp     short loc_1800DDB19
0x1800ddadf  mov     rax, 800000000h
0x1800ddae9  cmp     qword ptr [rbp+57h+TotalNumberOfBytes], rax
0x1800ddaed  jbe     short loc_1800DDAF6
0x1800ddaef  mov     edi, 80070490h
0x1800ddaf4  jmp     short loc_1800DDB1B
0x1800ddaf6  mov     [rbp+57h+var_90], r13
0x1800ddafa  mov     [rbp+57h+Buffer], r13
0x1800ddafe  lea     rcx, [rbp+57h+lpDirectoryName]
0x1800ddb02  cmp     qword ptr [rbp+57h+var_58+8], 0Fh
0x1800ddb07  cmova   rcx, [rbp+57h+lpDirectoryName]; char *
0x1800ddb0c  lea     r8, [rbp+57h+Buffer]; unsigned __int64 *
0x1800ddb10  lea     rdx, [rbp+57h+var_90]; __int64 *
0x1800ddb14  call    ?QuerySoftReserve@@YAJPEBDAEA_JAEA_K@Z; QuerySoftReserve(char const *,__int64 &,unsigned __int64 &)
0x1800ddb19  mov     edi, eax
0x1800ddb1b  lea     rcx, [rbp+57h+lpDirectoryName]; void *
0x1800ddb1f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800ddb24  movzx   esi, bx
0x1800ddb27  or      si, 80h
0x1800ddb2c  test    edi, edi
0x1800ddb2e  cmovs   si, bx
0x1800ddb32  xorps   xmm0, xmm0
0x1800ddb35  movups  [rbp+57h+var_48], xmm0
0x1800ddb39  mov     [rbp+57h+var_38], r13
0x1800ddb3d  mov     [rbp+57h+var_30], 0Fh
0x1800ddb45  mov     byte ptr [rbp+57h+var_48], r13b
0x1800ddb49  movzx   edi, si
0x1800ddb4c  lea     r9, [rbp+57h+var_48]
0x1800ddb50  lea     r8, aActivepolicyco; "ActivePolicyCode"
0x1800ddb57  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800ddb5e  mov     rcx, 0FFFFFFFF80000002h
0x1800ddb65  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEBD1AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RegQueryStringValue(HKEY__ *,char const *,char const *,std::string &)
0x1800ddb6a  mov     r15d, 2
0x1800ddb70  test    eax, eax
0x1800ddb72  js      short loc_1800DDB94
0x1800ddb74  lea     rax, [rbp+57h+var_48]
0x1800ddb78  cmp     [rbp+57h+var_30], 0Fh
0x1800ddb7d  cmova   rax, qword ptr [rbp+57h+var_48]
0x1800ddb82  cmp     [rbp+57h+var_38], r15
0x1800ddb86  jnz     short loc_1800DDB94
0x1800ddb88  cmp     word ptr [rax], 687Ah
0x1800ddb8d  jnz     short loc_1800DDB94
0x1800ddb8f  or      di, 200h
0x1800ddb94  mov     [rbp+57h+var_70], r13d
0x1800ddb98  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800ddb9d  lea     rbx, [rax+20h]
0x1800ddba1  cmp     qword ptr [rbx+18h], 0Fh
0x1800ddba6  jbe     short loc_1800DDBAB
0x1800ddba8  mov     rbx, [rbx]
0x1800ddbab  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800ddbb0  mov     cl, [rax+0A0h]
0x1800ddbb6  neg     cl
0x1800ddbb8  sbb     rcx, rcx
0x1800ddbbb  add     rcx, 0FFFFFFFF80000003h; HKEY
0x1800ddbc2  lea     r9, [rbp+57h+var_70]; unsigned int *
0x1800ddbc6  lea     r8, aProfileRdx; "Profile_RDX"
0x1800ddbcd  mov     rdx, rbx; char *
0x1800ddbd0  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEBD1PEAI@Z; RegQueryDwordValue(HKEY__ *,char const *,char const *,uint *)
0x1800ddbd5  test    eax, eax
0x1800ddbd7  js      short loc_1800DDBE3
0x1800ddbd9  cmp     [rbp+57h+var_70], r13d
0x1800ddbdd  jz      short loc_1800DDBE3
0x1800ddbdf  or      di, r15w
0x1800ddbe3  cmp     [r14+4], r13b
0x1800ddbe7  jnz     loc_1800DDCD2
0x1800ddbed  xor     edx, edx; hFile
0x1800ddbef  mov     r8d, 800h; dwFlags
0x1800ddbf5  lea     rcx, aNetapi32Dll; "Netapi32.dll"
0x1800ddbfc  call    cs:__imp_LoadLibraryExA
0x1800ddc02  mov     rbx, rax
0x1800ddc05  mov     [rbp+57h+var_90], rax
0x1800ddc09  test    rax, rax
0x1800ddc0c  setnz   r12b
0x1800ddc10  test    rax, rax
0x1800ddc13  jz      loc_1800DDCBE
0x1800ddc19  lea     rdx, aNetgetjoininfo; "NetGetJoinInformation"
0x1800ddc20  mov     rcx, rax; hModule
0x1800ddc23  call    cs:__imp_GetProcAddress
0x1800ddc29  test    rax, rax
0x1800ddc2c  jz      short loc_1800DDC62
0x1800ddc2e  mov     dword ptr [rbp+57h+TotalNumberOfBytes], r13d
0x1800ddc32  mov     [rbp+57h+Buffer], r13
0x1800ddc36  lea     r8, [rbp+57h+TotalNumberOfBytes]
0x1800ddc3a  lea     rdx, [rbp+57h+Buffer]
0x1800ddc3e  xor     ecx, ecx
0x1800ddc40  call    _guard_dispatch_icall
0x1800ddc45  test    eax, eax
0x1800ddc47  jnz     short loc_1800DDC53
0x1800ddc49  cmp     dword ptr [rbp+57h+TotalNumberOfBytes], 3
0x1800ddc4d  jnz     short loc_1800DDC53
0x1800ddc4f  or      di, 4
0x1800ddc53  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800ddc57  test    rcx, rcx
0x1800ddc5a  jz      short loc_1800DDC62
0x1800ddc5c  call    cs:__imp_NetApiBufferFree
0x1800ddc62  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x1800ddc69  mov     rcx, rbx; hModule
0x1800ddc6c  call    cs:__imp_GetProcAddress
0x1800ddc72  mov     r15, rax
0x1800ddc75  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x1800ddc7c  mov     rcx, rbx; hModule
0x1800ddc7f  call    cs:__imp_GetProcAddress
0x1800ddc85  mov     rsi, rax
0x1800ddc88  test    r15, r15
0x1800ddc8b  jz      short loc_1800DDCBE
0x1800ddc8d  test    rax, rax
0x1800ddc90  jz      short loc_1800DDCBE
0x1800ddc92  mov     [rbp+57h+Buffer], r13
0x1800ddc96  lea     rdx, [rbp+57h+Buffer]
0x1800ddc9a  xor     ecx, ecx
0x1800ddc9c  mov     rax, r15
0x1800ddc9f  call    _guard_dispatch_icall
0x1800ddca4  test    eax, eax
0x1800ddca6  js      short loc_1800DDCBE
0x1800ddca8  mov     rcx, [rbp+57h+Buffer]
0x1800ddcac  test    rcx, rcx
0x1800ddcaf  jz      short loc_1800DDCBE
0x1800ddcb1  or      di, 8
0x1800ddcb5  mov     rax, rsi
0x1800ddcb8  call    _guard_dispatch_icall
0x1800ddcbd  nop
0x1800ddcbe  test    r12b, r12b
0x1800ddcc1  jz      short loc_1800DDCCC
0x1800ddcc3  mov     rcx, rbx; hLibModule
0x1800ddcc6  call    cs:__imp_FreeLibrary
0x1800ddccc  mov     r12d, 1
0x1800ddcd2  mov     esi, r13d
0x1800ddcd5  movsxd  rax, esi
0x1800ddcd8  lea     rcx, [rax+rax*4]
0x1800ddcdc  add     rcx, rcx
0x1800ddcdf  lea     rax, off_180124FD8; "DOAbsoluteMaxCacheSize"
0x1800ddce6  mov     rcx, [rax+rcx*8]
0x1800ddcea  test    rcx, rcx
0x1800ddced  jz      loc_1800DDD84
0x1800ddcf3  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r13
0x1800ddcf7  lea     rdx, [rbp+57h+TotalNumberOfBytes]
0x1800ddcfb  call    _GetNamedPolicy
0x1800ddd00  test    eax, eax
0x1800ddd02  jns     short loc_1800DDD06
0x1800ddd04  jmp     short loc_1800DDD3B
0x1800ddd06  mov     [rbp+57h+var_7F], r13b
0x1800ddd0a  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x1800ddd0e  mov     rax, [rcx]
0x1800ddd11  lea     rdx, [rbp+57h+var_7F]
0x1800ddd15  mov     rax, [rax+48h]
0x1800ddd19  call    _guard_dispatch_icall
0x1800ddd1e  test    eax, eax
0x1800ddd20  jns     short loc_1800DDD57
0x1800ddd22  mov     rcx, [rbp+5Fh]; this
0x1800ddd26  mov     r9d, eax; char *
0x1800ddd29  lea     r8, aCW1SSrcDeliver_31; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ddd30  mov     edx, 64h ; 'd'; void *
0x1800ddd35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddd3a  nop
0x1800ddd3b  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x1800ddd3f  test    rcx, rcx
0x1800ddd42  jz      short loc_1800DDD55
0x1800ddd44  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r13
0x1800ddd48  mov     rax, [rcx]
0x1800ddd4b  mov     rax, [rax+10h]
0x1800ddd4f  call    _guard_dispatch_icall
0x1800ddd54  nop
0x1800ddd55  jmp     short loc_1800DDD84
0x1800ddd57  mov     al, [rbp+57h+var_7F]
0x1800ddd5a  neg     al
0x1800ddd5c  sbb     ebx, ebx
0x1800ddd5e  not     ebx
0x1800ddd60  and     ebx, 80070490h
0x1800ddd66  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x1800ddd6a  test    rcx, rcx
0x1800ddd6d  jz      short loc_1800DDD80
0x1800ddd6f  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r13
0x1800ddd73  mov     rax, [rcx]
0x1800ddd76  mov     rax, [rax+10h]
0x1800ddd7a  call    _guard_dispatch_icall
0x1800ddd7f  nop
0x1800ddd80  test    ebx, ebx
0x1800ddd82  jns     short loc_1800DDD95
0x1800ddd84  add     esi, r12d
0x1800ddd87  cmp     esi, 0C3h
0x1800ddd8d  jb      loc_1800DDCD5
0x1800ddd93  jmp     short loc_1800DDD99
0x1800ddd95  or      di, 20h
0x1800ddd99  mov     [rbp+57h+var_80], r13b
0x1800ddd9d  mov     rcx, cs:?_pPlatformHost@CGlobalObjects@@0PEAVIDOPlatformHost@@EA; IDOPlatformHost * CGlobalObjects::_pPlatformHost
0x1800ddda4  test    rcx, rcx
0x1800ddda7  jz      short loc_1800DDDD4
0x1800ddda9  mov     rax, [rcx]
0x1800dddac  lea     rdx, [rbp+57h+var_80]
0x1800dddb0  mov     rax, [rax+38h]
0x1800dddb4  call    _guard_dispatch_icall
0x1800dddb9  mov     ecx, r13d
0x1800dddbc  test    eax, eax
0x1800dddbe  cmovs   ecx, eax
0x1800dddc1  test    ecx, ecx
0x1800dddc3  js      short loc_1800DDDD4
0x1800dddc5  mov     bl, [rbp+57h+var_80]
0x1800dddc8  mov     rsi, 0FFFFFFFF80000002h
0x1800dddcf  jmp     loc_1800DDE56
0x1800dddd4  xorps   xmm0, xmm0
0x1800dddd7  movups  xmmword ptr [rbp+57h+lpDirectoryName], xmm0
0x1800ddddb  mov     qword ptr [rbp+57h+var_58], r13
0x1800ddddf  mov     qword ptr [rbp+57h+var_58+8], 0Fh
0x1800ddde7  mov     byte ptr [rbp+57h+lpDirectoryName], r13b
0x1800dddeb  lea     r9, [rbp+57h+lpDirectoryName]
0x1800dddef  lea     r8, aCommercialid; "CommercialId"
0x1800dddf6  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800dddfd  mov     rsi, 0FFFFFFFF80000002h
0x1800dde04  mov     rcx, rsi
0x1800dde07  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEBD1AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RegQueryStringValue(HKEY__ *,char const *,char const *,std::string &)
0x1800dde0c  test    eax, eax
0x1800dde0e  jns     short loc_1800DDE43
0x1800dde10  lea     r9, [rbp+57h+lpDirectoryName]
0x1800dde14  lea     r8, aCommercialid; "CommercialId"
0x1800dde1b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800dde22  mov     rcx, rsi
0x1800dde25  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEBD1AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RegQueryStringValue(HKEY__ *,char const *,char const *,std::string &)
0x1800dde2a  test    eax, eax
0x1800dde2c  jns     short loc_1800DDE43
0x1800dde2e  mov     qword ptr [rbp+57h+var_58], r13
0x1800dde32  lea     rax, [rbp+57h+lpDirectoryName]
0x1800dde36  cmp     qword ptr [rbp+57h+var_58+8], 0Fh
0x1800dde3b  cmova   rax, [rbp+57h+lpDirectoryName]
0x1800dde40  mov     [rax], r13b
0x1800dde43  cmp     qword ptr [rbp+57h+var_58], r13
0x1800dde47  setnz   bl
0x1800dde4a  lea     rcx, [rbp+57h+lpDirectoryName]; void *
0x1800dde4e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800dde53  mov     [rbp+57h+var_80], bl
0x1800dde56  test    bl, bl
0x1800dde58  jz      short loc_1800DDE5E
0x1800dde5a  or      di, 10h
0x1800dde5e  mov     [rbp+57h+var_6C], r13d
0x1800dde62  lea     r9, [rbp+57h+var_6C]; unsigned int *
0x1800dde66  lea     r8, aEdusharedpcmod; "EduSharedPCMode"
0x1800dde6d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800dde74  mov     rcx, rsi; HKEY
0x1800dde77  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEBD1PEAI@Z; RegQueryDwordValue(HKEY__ *,char const *,char const *,uint *)
0x1800dde7c  test    eax, eax
0x1800dde7e  js      short loc_1800DDE8A
0x1800dde80  cmp     [rbp+57h+var_6C], r13d
0x1800dde84  jz      short loc_1800DDE8A
0x1800dde86  or      di, 40h
0x1800dde8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_41232331_WindowsInsiderBit>::GetImpl(void)'::`2'::impl
  ... truncated ...
```
