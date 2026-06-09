# CBattery::GetNTBattery(MethodContext *,CHString &,CInstance *)

- ea: `0x1800520d0`
- end: `0x1800525a7`
- name: `?GetNTBattery@CBattery@@QEAAJPEAVMethodContext@@AEAVCHString@@PEAVCInstance@@@Z`
- size: `1239`
- prototype: `__int64 __fastcall(CBattery *__hidden this, struct MethodContext *, struct CHString *, struct CInstance *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180052080`
- `0x1800952f0`

## callees

- `0x180014c58`
- `0x180015c80`
- `0x1800520d0`
- `0x1800525b0`
- `0x18005262c`
- `0x1800526f4`
- `0x1800527a0`
- `0x18005283c`
- `0x18005297c`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800523ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800523ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052420`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800522a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800522a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800522fc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052359`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800523cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800522fc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180052359`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800523cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052228`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052228`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800523f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800523f5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180052375`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180052375`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180052469`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180052469`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18005245d`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18005245d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800524c3`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800524c3`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180052496`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180052496`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18005255f`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18005258f`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18005255f`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18005258f`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180052539`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180052539`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18005244e`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18005244e`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180052445`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x180052445`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800523e3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005247c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005259c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800523e3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005247c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18005259c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180052171`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180052171`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180052211`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005226b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180052211`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18005226b`
- `DEVOBJ!DevObjGetClassDevs` at `0x180052164`
- `DEVOBJ!DevObjGetClassDevs` at `0x180052164`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800521db`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800521db`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180052127`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180052127`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBattery::GetNTBattery(
        CBattery *this,
        struct MethodContext *a2,
        struct CHString *a3,
        struct CInstance *a4)
{
  CHString *v5; // rdi
  __int64 DeviceInfoList; // rax
  __int64 v8; // r14
  unsigned int BatteryProperties; // ebx
  int v11; // eax
  unsigned int v12; // ecx
  WCHAR *v13; // r15
  HANDLE FileW; // rsi
  __int64 v15; // rcx
  _BYTE *v16; // rax
  bool v17; // zf
  const unsigned __int16 *v18; // rax
  CInstance *NewInstance; // rax
  struct CInstance *v20; // rdi
  CBattery *v21; // rcx
  unsigned int v22; // r8d
  CBattery *v23; // rcx
  CBattery *v24; // rcx
  CBattery *v25; // rcx
  CInstance *v26; // rax
  int v27; // [rsp+40h] [rbp-C0h]
  unsigned int v28; // [rsp+44h] [rbp-BCh]
  SIZE_T uBytes; // [rsp+48h] [rbp-B8h] BYREF
  void *v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[8]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  int InBuffer; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v34; // [rsp+68h] [rbp-98h] BYREF
  CInstance *v35; // [rsp+70h] [rbp-90h] BYREF
  struct MethodContext *v36; // [rsp+78h] [rbp-88h]
  struct CHString *v37; // [rsp+80h] [rbp-80h]
  struct _BATTERY_QUERY_INFORMATION OutBuffer; // [rsp+88h] [rbp-78h] BYREF
  _BATTERY_INFORMATION v39; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v40[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[1040]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = a3;
  v37 = a3;
  v36 = a2;
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVICE_BATTERY, 0, 0, 0, 0);
  v8 = DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    BatteryProperties = -2147217406;
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVICE_BATTERY, 0, 18, 0, 0) )
    {
LABEL_3:
      DevObjDestroyDeviceInfoList(v8);
      return BatteryProperties;
    }
    v11 = 1;
    v27 = 1;
    memset(v40, 0, sizeof(v40));
    LODWORD(v40[0]) = 32;
    v12 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v11 )
          goto LABEL_3;
        v28 = v12 + 1;
        if ( (unsigned int)DevObjEnumDeviceInterfaces(v8, 0, &GUID_DEVICE_BATTERY, v12, v40) )
          break;
        if ( GetLastError() == 259 )
          BatteryProperties = 0;
        v11 = 0;
        v27 = 0;
LABEL_23:
        v12 = v28;
      }
      LODWORD(uBytes) = 0;
      if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v8, v40, 0, 0, &uBytes, 0) )
      {
        v17 = GetLastError() == 122;
        v11 = v27;
        v12 = v28;
        if ( !v17 )
          continue;
      }
      v13 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
      v11 = v27;
      v12 = v28;
      if ( v13 )
        break;
    }
    *(_DWORD *)v13 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v8, v40, v13, (unsigned int)uBytes, &uBytes, 0) )
    {
      FileW = CreateFileW(v13 + 2, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      v30 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        *(_QWORD *)&OutBuffer.InformationLevel = 0;
        InBuffer = 0;
        BytesReturned = 0;
        OutBuffer.BatteryTag = 0;
        if ( DeviceIoControl(FileW, 0x294040u, &InBuffer, 4u, &OutBuffer, 4u, &BytesReturned, 0) )
        {
          if ( OutBuffer.BatteryTag )
          {
            memset(&v39, 0, sizeof(v39));
            *(_QWORD *)&OutBuffer.InformationLevel = 0;
            if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, &v39, 0x24u, &BytesReturned, 0) )
            {
              if ( (v39.Capabilities & 0x80000000) != 0 )
              {
                CHString::CHString((CHString *)v31);
                v15 = 1040;
                v16 = v41;
                do
                {
                  *v16++ = 0;
                  --v15;
                }
                while ( v15 );
                v34 = 520;
                OutBuffer.InformationLevel = BatteryUniqueID;
                if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, v41, 0x410u, &v34, 0) )
                {
                  CHString::operator=(v31, v41);
                  if ( !CHString::IsEmpty(v5) )
                  {
                    v18 = (const unsigned __int16 *)CHString::operator unsigned short const *(v31);
                    if ( !CHString::CompareNoCase(v5, v18) )
                    {
                      BatteryProperties = CBattery::GetBatteryProperties(this, a4, &v39, &OutBuffer, &v30);
                      if ( !BatteryProperties )
                        BatteryProperties = CInstance::Commit(a4);
                      CHString::~CHString((CHString *)v31);
                      goto LABEL_3;
                    }
                    CHString::~CHString((CHString *)v31);
                    BatteryProperties = 0;
                    goto LABEL_22;
                  }
                  v35 = 0;
                  NewInstance = Provider::CreateNewInstance(this, v36);
                  v20 = NewInstance;
                  v35 = NewInstance;
                  if ( !NewInstance )
                    _com_issue_error(-2147467261);
                  CInstance::SetCHString(NewInstance, L"DeviceID", (const struct CHString *)v31);
                  BatteryProperties = CBattery::GetHardCodedInfo(this, v20);
                  if ( !BatteryProperties )
                  {
                    BatteryProperties = CBattery::SetPowerManagementCapabilities(v21, v20, v22);
                    if ( !BatteryProperties )
                    {
                      BatteryProperties = CBattery::SetChemistry(v23, v20, v39.Chemistry);
                      if ( !BatteryProperties )
                      {
                        BatteryProperties = CBattery::GetQueryBatteryInformation(v24, v20, &v30, &OutBuffer);
                        if ( !BatteryProperties )
                        {
                          BatteryProperties = CBattery::GetBatteryStatusInfo(v25, v20, &v30, &OutBuffer, &v39);
                          if ( !BatteryProperties )
                          {
                            v26 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v35);
                            BatteryProperties = CInstance::Commit(v26);
                          }
                        }
                        FileW = v30;
                      }
                    }
                  }
                  CInstance::Release(v20);
                  v5 = v37;
                }
                else
                {
                  BatteryProperties = -2147217407;
                }
                CHString::~CHString((CHString *)v31);
              }
            }
          }
        }
        CloseHandle(FileW);
      }
    }
    LocalFree(v13);
LABEL_22:
    v11 = v27;
    goto LABEL_23;
  }
  return 2147749890LL;
}

```

## disassembly

```asm
0x1800520d0  push    rbp
0x1800520d2  push    rbx
0x1800520d3  push    rsi
0x1800520d4  push    rdi
0x1800520d5  push    r12
0x1800520d7  push    r13
0x1800520d9  push    r14
0x1800520db  push    r15
0x1800520dd  lea     rbp, [rsp-408h]
0x1800520e5  sub     rsp, 508h
0x1800520ec  mov     rax, cs:__security_cookie
0x1800520f3  xor     rax, rsp
0x1800520f6  mov     [rbp+440h+var_50], rax
0x1800520fd  mov     r12, r9
0x180052100  mov     rdi, r8
0x180052103  mov     [rbp+440h+var_4C0], r8
0x180052107  mov     [rsp+540h+var_4C8], rdx
0x18005210c  mov     r13, rcx
0x18005210f  mov     qword ptr [rsp+540h+dwCreationDisposition], 0
0x180052118  xor     r9d, r9d
0x18005211b  xor     r8d, r8d
0x18005211e  xor     edx, edx
0x180052120  lea     rcx, GUID_DEVICE_BATTERY
0x180052127  call    cs:__imp_DevObjCreateDeviceInfoList
0x18005212d  mov     r14, rax
0x180052130  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052134  jz      loc_180052548
0x18005213a  mov     ebx, 80041002h
0x18005213f  mov     qword ptr [rsp+540h+dwFlagsAndAttributes], 0
0x180052148  mov     qword ptr [rsp+540h+dwCreationDisposition], 0
0x180052151  mov     r9d, 12h
0x180052157  xor     r8d, r8d
0x18005215a  lea     rdx, GUID_DEVICE_BATTERY
0x180052161  mov     rcx, rax
0x180052164  call    cs:__imp_DevObjGetClassDevs
0x18005216a  test    eax, eax
0x18005216c  jnz     short loc_18005219C
0x18005216e  mov     rcx, r14
0x180052171  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180052177  mov     eax, ebx
0x180052179  mov     rcx, [rbp+440h+var_50]
0x180052180  xor     rcx, rsp; StackCookie
0x180052183  call    __security_check_cookie
0x180052188  add     rsp, 508h
0x18005218f  pop     r15
0x180052191  pop     r14
0x180052193  pop     r13
0x180052195  pop     r12
0x180052197  pop     rdi
0x180052198  pop     rsi
0x180052199  pop     rbx
0x18005219a  pop     rbp
0x18005219b  retn
0x18005219c  mov     eax, 1
0x1800521a1  mov     [rsp+540h+var_500], eax
0x1800521a5  xorps   xmm0, xmm0
0x1800521a8  movups  [rbp+440h+var_480], xmm0
0x1800521ac  movups  [rbp+440h+var_470], xmm0
0x1800521b0  mov     dword ptr [rbp+440h+var_480], 20h ; ' '
0x1800521b7  xor     ecx, ecx
0x1800521b9  test    eax, eax
0x1800521bb  jz      short loc_18005216E
0x1800521bd  mov     r9d, ecx
0x1800521c0  inc     ecx
0x1800521c2  mov     [rsp+540h+var_4FC], ecx
0x1800521c6  lea     rax, [rbp+440h+var_480]
0x1800521ca  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x1800521cf  lea     r8, GUID_DEVICE_BATTERY
0x1800521d6  xor     edx, edx
0x1800521d8  mov     rcx, r14
0x1800521db  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800521e1  test    eax, eax
0x1800521e3  jz      loc_180052408
0x1800521e9  mov     dword ptr [rsp+540h+uBytes], 0
0x1800521f1  mov     qword ptr [rsp+540h+dwFlagsAndAttributes], 0
0x1800521fa  lea     rax, [rsp+540h+uBytes]
0x1800521ff  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x180052204  xor     r9d, r9d
0x180052207  xor     r8d, r8d
0x18005220a  lea     rdx, [rbp+440h+var_480]
0x18005220e  mov     rcx, r14
0x180052211  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180052217  test    eax, eax
0x180052219  jz      loc_180052420
0x18005221f  mov     edx, dword ptr [rsp+540h+uBytes]; uBytes
0x180052223  mov     ecx, 40h ; '@'; uFlags
0x180052228  call    cs:__imp_LocalAlloc
0x18005222e  mov     r15, rax
0x180052231  test    rax, rax
0x180052234  mov     eax, [rsp+540h+var_500]
0x180052238  mov     ecx, [rsp+540h+var_4FC]
0x18005223c  jz      loc_1800521B9
0x180052242  mov     dword ptr [r15], 8
0x180052249  mov     qword ptr [rsp+540h+dwFlagsAndAttributes], 0
0x180052252  lea     rax, [rsp+540h+uBytes]
0x180052257  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x18005225c  mov     r9d, dword ptr [rsp+540h+uBytes]
0x180052261  mov     r8, r15
0x180052264  lea     rdx, [rbp+440h+var_480]
0x180052268  mov     rcx, r14
0x18005226b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180052271  test    eax, eax
0x180052273  jz      loc_1800523F2
0x180052279  lea     rcx, [r15+4]; lpFileName
0x18005227d  mov     [rsp+540h+hTemplateFile], 0; hTemplateFile
0x180052286  mov     [rsp+540h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005228e  mov     [rsp+540h+dwCreationDisposition], 3; dwCreationDisposition
0x180052296  xor     r9d, r9d; lpSecurityAttributes
0x180052299  mov     edx, 0C0000000h; dwDesiredAccess
0x18005229e  lea     r8d, [r9+3]; dwShareMode
0x1800522a2  call    cs:__imp_CreateFileW
0x1800522a8  mov     rsi, rax
0x1800522ab  mov     [rsp+540h+var_4F0], rax
0x1800522b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800522b4  jz      loc_1800523F2
0x1800522ba  xor     eax, eax
0x1800522bc  mov     [rbp+440h+var_4B4], rax
0x1800522c0  mov     [rsp+540h+InBuffer], eax
0x1800522c4  mov     [rsp+540h+BytesReturned], eax
0x1800522c8  mov     [rbp+440h+OutBuffer], eax
0x1800522cb  mov     [rsp+540h+lpOverlapped], rax; lpOverlapped
0x1800522d0  lea     rax, [rsp+540h+BytesReturned]
0x1800522d5  mov     [rsp+540h+hTemplateFile], rax; lpBytesReturned
0x1800522da  mov     ecx, 4
0x1800522df  mov     [rsp+540h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1800522e3  lea     rax, [rbp+440h+OutBuffer]
0x1800522e7  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; lpOutBuffer
0x1800522ec  mov     r9d, ecx; nInBufferSize
0x1800522ef  lea     r8, [rsp+540h+InBuffer]; lpInBuffer
0x1800522f4  mov     edx, 294040h; dwIoControlCode
0x1800522f9  mov     rcx, rsi; hDevice
0x1800522fc  call    cs:__imp_DeviceIoControl
0x180052302  xor     ecx, ecx
0x180052304  test    eax, eax
0x180052306  jz      loc_1800523E9
0x18005230c  cmp     [rbp+440h+OutBuffer], ecx
0x18005230f  jz      loc_1800523E9
0x180052315  xorps   xmm0, xmm0
0x180052318  xor     eax, eax
0x18005231a  movups  xmmword ptr [rbp+440h+var_4A8.Capabilities], xmm0
0x18005231e  movups  xmmword ptr [rbp+440h+var_4A8.FullChargedCapacity], xmm0
0x180052322  mov     [rbp+440h+var_4A8.CycleCount], eax
0x180052325  mov     [rbp+440h+var_4B4], rcx
0x180052329  mov     [rsp+540h+lpOverlapped], rcx; lpOverlapped
0x18005232e  lea     rax, [rsp+540h+BytesReturned]
0x180052333  mov     [rsp+540h+hTemplateFile], rax; lpBytesReturned
0x180052338  mov     [rsp+540h+dwFlagsAndAttributes], 24h ; '$'; nOutBufferSize
0x180052340  lea     rax, [rbp+440h+var_4A8]
0x180052344  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; lpOutBuffer
0x180052349  lea     r9d, [rcx+0Ch]; nInBufferSize
0x18005234d  lea     r8, [rbp+440h+OutBuffer]; lpInBuffer
0x180052351  mov     edx, 294044h; dwIoControlCode
0x180052356  mov     rcx, rsi; hDevice
0x180052359  call    cs:__imp_DeviceIoControl
0x18005235f  test    eax, eax
0x180052361  jz      loc_1800523E9
0x180052367  test    [rbp+440h+var_4A8.Capabilities], 80000000h
0x18005236e  jz      short loc_1800523E9
0x180052370  lea     rcx, [rsp+540h+var_4E8]
0x180052375  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18005237b  nop
0x18005237c  mov     edx, 410h
0x180052381  mov     ecx, edx
0x180052383  lea     rax, [rbp+440h+var_460]
0x180052387  xor     ebx, ebx
0x180052389  mov     [rax], bl
0x18005238b  inc     rax
0x18005238e  sub     rcx, 1
0x180052392  jnz     short loc_180052389
0x180052394  mov     [rsp+540h+var_4D8], 208h
0x18005239c  mov     dword ptr [rbp+440h+var_4B4], 7
0x1800523a3  mov     [rsp+540h+lpOverlapped], rbx; lpOverlapped
0x1800523a8  lea     rax, [rsp+540h+var_4D8]
0x1800523ad  mov     [rsp+540h+hTemplateFile], rax; lpBytesReturned
0x1800523b2  mov     [rsp+540h+dwFlagsAndAttributes], edx; nOutBufferSize
0x1800523b6  lea     rax, [rbp+440h+var_460]
0x1800523ba  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; lpOutBuffer
0x1800523bf  lea     r9d, [rcx+0Ch]; nInBufferSize
0x1800523c3  lea     r8, [rbp+440h+OutBuffer]; lpInBuffer
0x1800523c7  mov     edx, 294044h; dwIoControlCode
0x1800523cc  mov     rcx, rsi; hDevice
0x1800523cf  call    cs:__imp_DeviceIoControl
0x1800523d5  test    eax, eax
0x1800523d7  jnz     short loc_18005243C
0x1800523d9  mov     ebx, 80041001h
0x1800523de  lea     rcx, [rsp+540h+var_4E8]
0x1800523e3  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800523e9  mov     rcx, rsi; hObject
0x1800523ec  call    cs:__imp_CloseHandle
0x1800523f2  mov     rcx, r15; hMem
0x1800523f5  call    cs:__imp_LocalFree
0x1800523fb  mov     eax, [rsp+540h+var_500]
0x1800523ff  mov     ecx, [rsp+540h+var_4FC]
0x180052403  jmp     loc_1800521B9
0x180052408  call    cs:__imp_GetLastError
0x18005240e  xor     ecx, ecx
0x180052410  cmp     eax, 103h
0x180052415  cmovz   ebx, ecx
0x180052418  xor     eax, eax
0x18005241a  mov     [rsp+540h+var_500], eax
0x18005241e  jmp     short loc_1800523FF
0x180052420  call    cs:__imp_GetLastError
0x180052426  cmp     eax, 7Ah ; 'z'
0x180052429  mov     eax, [rsp+540h+var_500]
0x18005242d  mov     ecx, [rsp+540h+var_4FC]
0x180052431  jz      loc_18005221F
0x180052437  jmp     loc_1800521B9
0x18005243c  lea     rdx, [rbp+440h+var_460]
0x180052440  lea     rcx, [rsp+540h+var_4E8]
0x180052445  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18005244b  mov     rcx, rdi
0x18005244e  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x180052454  test    eax, eax
0x180052456  jnz     short loc_180052489
0x180052458  lea     rcx, [rsp+540h+var_4E8]
0x18005245d  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180052463  mov     rdx, rax
0x180052466  mov     rcx, rdi
0x180052469  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x18005246f  test    eax, eax
0x180052471  jz      loc_180052569
0x180052477  lea     rcx, [rsp+540h+var_4E8]
0x18005247c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180052482  xor     ebx, ebx
0x180052484  jmp     loc_1800523FB
0x180052489  mov     [rsp+540h+var_4D0], rbx
0x18005248e  mov     rdx, [rsp+540h+var_4C8]
0x180052493  mov     rcx, r13
0x180052496  call    cs:__imp_?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z; Provider::CreateNewInstance(MethodContext *)
0x18005249c  mov     rdi, rax
0x18005249f  mov     [rsp+540h+var_4D0], rax
0x1800524a4  test    rax, rax
0x1800524a7  jnz     short loc_1800524B4
0x1800524a9  mov     ecx, 80004003h; int
0x1800524ae  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800524b4  lea     r8, [rsp+540h+var_4E8]
0x1800524b9  lea     rdx, aDeviceid; "DeviceID"
0x1800524c0  mov     rcx, rdi
0x1800524c3  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800524c9  mov     rdx, rdi; struct CInstance *
0x1800524cc  mov     rcx, r13; this
0x1800524cf  call    ?GetHardCodedInfo@CBattery@@QEAAJPEAVCInstance@@@Z; CBattery::GetHardCodedInfo(CInstance *)
0x1800524d4  mov     ebx, eax
0x1800524d6  test    eax, eax
0x1800524d8  jnz     short loc_180052536
0x1800524da  mov     rdx, rdi; struct CInstance *
0x1800524dd  call    ?SetPowerManagementCapabilities@CBattery@@QEAAJPEAVCInstance@@K@Z; CBattery::SetPowerManagementCapabilities(CInstance *,ulong)
0x1800524e2  mov     ebx, eax
0x1800524e4  test    eax, eax
0x1800524e6  jnz     short loc_180052536
0x1800524e8  lea     r8, [rbp+440h+var_4A8.Chemistry]; unsigned __int8 *
0x1800524ec  mov     rdx, rdi; struct CInstance *
0x1800524ef  call    ?SetChemistry@CBattery@@QEAAJPEAVCInstance@@PEAE@Z; CBattery::SetChemistry(CInstance *,uchar *)
0x1800524f4  mov     ebx, eax
0x1800524f6  test    eax, eax
0x1800524f8  jnz     short loc_180052536
0x1800524fa  lea     r9, [rbp+440h+OutBuffer]; struct _BATTERY_QUERY_INFORMATION *
0x1800524fe  lea     r8, [rsp+540h+var_4F0]; void **
0x180052503  mov     rdx, rdi; struct CInstance *
0x180052506  call    ?GetQueryBatteryInformation@CBattery@@QEAAJPEAVCInstance@@AEAPEAXAEAU_BATTERY_QUERY_INFORMATION@@@Z; CBattery::GetQueryBatteryInformation(CInstance *,void * &,_BATTERY_QUERY_INFORMATION &)
0x18005250b  mov     ebx, eax
0x18005250d  test    eax, eax
0x18005250f  jnz     short loc_180052531
0x180052511  lea     rax, [rbp+440h+var_4A8]
0x180052515  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; struct _BATTERY_INFORMATION *
0x18005251a  lea     r9, [rbp+440h+OutBuffer]; struct _BATTERY_QUERY_INFORMATION *
0x18005251e  lea     r8, [rsp+540h+var_4F0]; void **
0x180052523  mov     rdx, rdi; struct CInstance *
0x180052526  call    ?GetBatteryStatusInfo@CBattery@@QEAAJPEAVCInstance@@AEAPEAXAEAU_BATTERY_QUERY_INFORMATION@@AEAU_BATTERY_INFORMATION@@@Z; CBattery::GetBatteryStatusInfo(CInstance *,void * &,_BATTERY_QUERY_INFORMATION &,_BATTERY_INFORMATION &)
0x18005252b  mov     ebx, eax
0x18005252d  test    eax, eax
0x18005252f  jz      short loc_180052552
0x180052531  mov     rsi, [rsp+540h+var_4F0]
0x180052536  mov     rcx, rdi
0x180052539  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x18005253f  mov     rdi, [rbp+440h+var_4C0]
0x180052543  jmp     loc_1800523DE
0x180052548  mov     eax, 80041002h
0x18005254d  jmp     loc_180052179
0x180052552  lea     rcx, [rsp+540h+var_4D0]
0x180052557  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18005255c  mov     rcx, rax
0x18005255f  call    cs:__imp_?Commit@CInstance@@QEAAJXZ; CInstance::Commit(void)
0x180052565  mov     ebx, eax
0x180052567  jmp     short loc_180052531
0x180052569  lea     rax, [rsp+540h+var_4F0]
0x18005256e  mov     qword ptr [rsp+540h+dwCreationDisposition], rax; void **
0x180052573  lea     r9, [rbp+440h+OutBuffer]; struct _BATTERY_QUERY_INFORMATION *
0x180052577  lea     r8, [rbp+440h+var_4A8]; struct _BATTERY_INFORMATION *
0x18005257b  mov     rdx, r12; struct CInstance *
0x18005257e  mov     rcx, r13; this
0x180052581  call    ?GetBatteryProperties@CBattery@@QEAAJPEAVCInstance@@AEAU_BATTERY_INFORMATION@@AEAU_BATTERY_QUERY_INFORMATION@@AEAPEAX@Z; CBattery::GetBatteryProperties(CInstance *,_BATTERY_INFORMATION &,_BATTERY_QUERY_INFORMATION &,void * &)
0x180052586  mov     ebx, eax
0x180052588  test    eax, eax
0x18005258a  jnz     short loc_180052597
0x18005258c  mov     rcx, r12
0x18005258f  call    cs:__imp_?Commit@CInstance@@QEAAJXZ; CInstance::Commit(void)
0x180052595  mov     ebx, eax
0x180052597  lea     rcx, [rsp+540h+var_4E8]
0x18005259c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
  ... truncated ...
```
