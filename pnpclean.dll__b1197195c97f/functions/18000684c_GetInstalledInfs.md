# GetInstalledInfs

- ea: `0x18000684c`
- end: `0x180006c95`
- name: `GetInstalledInfs`
- size: `1097`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180006dc4`

## callees

- `0x18000684c`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180006b11`
- `msvcrt!wcsstr` at `0x180006b11`
- `KERNEL32!GetLastError` at `0x1800068c4`
- `KERNEL32!GetLastError` at `0x18000695a`
- `KERNEL32!GetLastError` at `0x1800069b0`
- `KERNEL32!GetLastError` at `0x180006c2e`
- `KERNEL32!GetLastError` at `0x1800068c4`
- `KERNEL32!GetLastError` at `0x18000695a`
- `KERNEL32!GetLastError` at `0x1800069b0`
- `KERNEL32!GetLastError` at `0x180006c2e`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180006c63`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180006c63`
- `SETUPAPI!pSetupFree` at `0x180006bf6`
- `SETUPAPI!pSetupFree` at `0x180006c0c`
- `SETUPAPI!pSetupFree` at `0x180006bf6`
- `SETUPAPI!pSetupFree` at `0x180006c0c`
- `SETUPAPI!pSetupMalloc` at `0x1800069da`
- `SETUPAPI!pSetupMalloc` at `0x1800069da`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x180006ac6`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x180006bcf`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x180006ac6`
- `SETUPAPI!pSetupStringTableAddStringEx` at `0x180006bcf`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180006b51`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180006b51`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000694c`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800069a2`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006a1c`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18000694c`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800069a2`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006a1c`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x1800068b5`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x1800068b5`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800068f9`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180006c1d`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800068f9`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180006c1d`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x180006a8f`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x180006b70`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x180006a8f`
- `SETUPAPI!pSetupStringTableLookUpStringEx` at `0x180006b70`

## string_xrefs

- `0x180006c45`: `Failed to retrieve installed INF names for all devices, Err = 0x%lx`

## pseudocode

```c
__int64 __fastcall GetInstalledInfs(__int64 a1)
{
  HDEVINFO ClassDevs; // rax
  void *v3; // r14
  unsigned int v4; // edi
  DWORD v5; // r12d
  int v6; // ebx
  const DEVPROPKEY *v7; // r8
  DWORD v8; // eax
  BYTE *v9; // rbx
  unsigned __int64 v10; // rax
  BYTE *v11; // rsi
  int v12; // eax
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rax
  wchar_t *v16; // rax
  int v17; // eax
  int v18; // ecx
  DWORD LastError; // eax
  HDEVINFO DeviceInfoSet; // [rsp+20h] [rbp-E0h]
  HDEVINFO DeviceInfoSeta; // [rsp+20h] [rbp-E0h]
  HDEVINFO DeviceInfoSetb; // [rsp+20h] [rbp-E0h]
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD RequiredSize; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t PropertyBuffer[264]; // [rsp+70h] [rbp-90h] BYREF

  PropertyType = 0;
  RequiredSize = 0;
  v27 = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  ClassDevs = SetupDiGetClassDevsExW(0, 0, 0, 4u, 0, 0, 0);
  v3 = ClassDevs;
  if ( ClassDevs == (HDEVINFO)-1LL )
    return GetLastError();
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  v4 = 0;
  v5 = 1;
  if ( !SetupDiEnumDeviceInfo(ClassDevs, 0, &DeviceInfoData) )
  {
LABEL_53:
    LastError = GetLastError();
    if ( LastError != 259 )
    {
      v4 = LastError;
      if ( LastError )
        goto LABEL_55;
    }
    goto LABEL_56;
  }
  while ( 2 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = &DEVPKEY_Device_DriverInfPath;
      if ( v6 )
        v7 = &DEVPKEY_Device_RollbackDriverNode;
      if ( !SetupDiGetDevicePropertyW(
              v3,
              &DeviceInfoData,
              v7,
              &PropertyType,
              (PBYTE)PropertyBuffer,
              0x208u,
              &RequiredSize,
              0) )
        break;
      if ( PropertyType == 18 )
      {
        if ( !v6 )
          goto LABEL_34;
        v16 = wcsstr(PropertyBuffer, L":");
        if ( v16 )
        {
          *v16 = 0;
LABEL_34:
          if ( *(_DWORD *)(a1 + 56) && *(_DWORD *)(a1 + 60) && v6 )
            SetupDiSetDevicePropertyW(v3, &DeviceInfoData, &DEVPKEY_Device_RollbackDriverNode, 0, 0, 0, 0);
          if ( (unsigned int)pSetupStringTableLookUpStringEx(*(_QWORD *)(a1 + 120), PropertyBuffer, 0, &v27, 8) == -1 )
          {
            v17 = 0;
            v18 = 0;
            v27 = 0;
          }
          else
          {
            v18 = HIDWORD(v27);
            v17 = v27;
          }
          if ( !v17 )
            LODWORD(v27) = v6 == 0;
          if ( !v18 )
            HIDWORD(v27) = v6 != 0;
          LODWORD(DeviceInfoSetb) = 8;
          if ( (unsigned int)pSetupStringTableAddStringEx(
                               *(_QWORD *)(a1 + 120),
                               PropertyBuffer,
                               4,
                               &v27,
                               DeviceInfoSetb) == -1 )
          {
            v4 = 8;
            goto LABEL_55;
          }
        }
      }
LABEL_46:
      if ( (unsigned int)++v6 >= 2 )
        goto LABEL_10;
    }
    v8 = GetLastError();
    if ( v8 == 1168 )
      goto LABEL_46;
    v4 = v8;
    if ( v8 )
      goto LABEL_55;
LABEL_10:
    if ( SetupDiGetDevicePropertyW(
           v3,
           &DeviceInfoData,
           &DEVPKEY_Device_DriverExtendedInfs,
           &PropertyType,
           0,
           0,
           &RequiredSize,
           0) )
    {
      goto LABEL_52;
    }
    if ( GetLastError() != 122 )
      goto LABEL_52;
    if ( PropertyType != 8210 )
      goto LABEL_52;
    if ( RequiredSize <= 2 )
      goto LABEL_52;
    v9 = (BYTE *)pSetupMalloc(RequiredSize);
    if ( !v9 )
      goto LABEL_52;
    if ( !SetupDiGetDevicePropertyW(
            v3,
            &DeviceInfoData,
            &DEVPKEY_Device_DriverExtendedInfs,
            &PropertyType,
            v9,
            RequiredSize,
            &RequiredSize,
            0)
      || PropertyType != 8210
      || (RequiredSize != 2 || *(_WORD *)v9)
      && (RequiredSize < 4
       || (v10 = (unsigned __int64)RequiredSize >> 1, *(_WORD *)&v9[2 * v10 - 2])
       || *(_WORD *)&v9[2 * v10 - 4]) )
    {
      pSetupFree(v9);
LABEL_52:
      if ( SetupDiEnumDeviceInfo(v3, v5++, &DeviceInfoData) )
        continue;
      goto LABEL_53;
    }
    break;
  }
  v11 = v9;
  if ( *(_WORD *)v9 )
  {
    while ( 1 )
    {
      v12 = pSetupStringTableLookUpStringEx(*(_QWORD *)(a1 + 120), v11, 0, &v27, 8);
      v13 = HIDWORD(v27);
      v14 = *(_QWORD *)(a1 + 120);
      LODWORD(v27) = 1;
      if ( v12 == -1 )
        v13 = 0;
      LODWORD(DeviceInfoSeta) = 8;
      HIDWORD(v27) = v13;
      if ( (unsigned int)pSetupStringTableAddStringEx(v14, v11, 4, &v27, DeviceInfoSeta) == -1 )
        break;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v11[2 * v15] );
      v11 += 2 * v15 + 2;
      if ( !*(_WORD *)v11 )
        goto LABEL_49;
    }
    v4 = 8;
  }
LABEL_49:
  pSetupFree(v9);
  if ( !v4 )
    goto LABEL_52;
LABEL_55:
  LODWORD(DeviceInfoSet) = v4;
  (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 40))(
    *(_QWORD *)(a1 + 48),
    1,
    0,
    "Failed to retrieve installed INF names for all devices, Err = 0x%lx",
    DeviceInfoSet);
LABEL_56:
  SetupDiDestroyDeviceInfoList(v3);
  return v4;
}

```

## disassembly

```asm
0x18000684c  push    rbp
0x18000684e  push    rbx
0x18000684f  push    rsi
0x180006850  push    rdi
0x180006851  push    r12
0x180006853  push    r13
0x180006855  push    r14
0x180006857  push    r15
0x180006859  lea     rbp, [rsp-198h]
0x180006861  sub     rsp, 298h
0x180006868  mov     rax, cs:__security_cookie
0x18000686f  xor     rax, rsp
0x180006872  mov     [rbp+1D0h+var_50], rax
0x180006879  xor     r13d, r13d
0x18000687c  xorps   xmm0, xmm0
0x18000687f  mov     r15, rcx
0x180006882  mov     [rsp+2D0h+Reserved], r13; Reserved
0x180006887  mov     [rsp+2D0h+MachineName], r13; MachineName
0x18000688c  xor     r8d, r8d; hwndParent
0x18000688f  xor     edx, edx; Enumerator
0x180006891  mov     [rsp+2D0h+PropertyType], r13d
0x180006896  lea     r9d, [r13+4]; Flags
0x18000689a  mov     [rsp+2D0h+RequiredSize], r13d
0x18000689f  xor     ecx, ecx; ClassGuid
0x1800068a1  mov     [rsp+2D0h+var_288], r13
0x1800068a6  movups  xmmword ptr [rsp+2D0h+DeviceInfoData.cbSize], xmm0
0x1800068ab  mov     [rsp+2D0h+DeviceInfoSet], r13; DeviceInfoSet
0x1800068b0  movups  xmmword ptr [rsp+2D0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800068b5  call    cs:__imp_SetupDiGetClassDevsExW
0x1800068bb  mov     r14, rax
0x1800068be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068c2  jnz     short loc_1800068D1
0x1800068c4  call    cs:__imp_GetLastError
0x1800068ca  mov     edi, eax
0x1800068cc  jmp     loc_180006C69
0x1800068d1  xorps   xmm0, xmm0
0x1800068d4  lea     r8, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x1800068d9  movups  xmmword ptr [rsp+2D0h+DeviceInfoData.cbSize], xmm0
0x1800068de  xor     edx, edx; MemberIndex
0x1800068e0  mov     [rsp+2D0h+DeviceInfoData.cbSize], 20h ; ' '
0x1800068e8  mov     rcx, r14; DeviceInfoSet
0x1800068eb  mov     edi, r13d
0x1800068ee  movups  xmmword ptr [rsp+2D0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800068f3  mov     r12d, 1
0x1800068f9  call    cs:__imp_SetupDiEnumDeviceInfo
0x1800068ff  test    eax, eax
0x180006901  jz      loc_180006C2E
0x180006907  lea     rsi, DEVPKEY_Device_RollbackDriverNode
0x18000690e  mov     ebx, r13d
0x180006911  mov     [rsp+2D0h+Flags], r13d; Flags
0x180006916  lea     rax, [rsp+2D0h+RequiredSize]
0x18000691b  mov     [rsp+2D0h+Reserved], rax; RequiredSize
0x180006920  lea     r8, DEVPKEY_Device_DriverInfPath
0x180006927  lea     rax, [rsp+2D0h+PropertyBuffer]
0x18000692c  mov     dword ptr [rsp+2D0h+MachineName], 208h; PropertyBufferSize
0x180006934  test    ebx, ebx
0x180006936  mov     [rsp+2D0h+DeviceInfoSet], rax; PropertyBuffer
0x18000693b  lea     r9, [rsp+2D0h+PropertyType]; PropertyType
0x180006940  mov     rcx, r14; DeviceInfoSet
0x180006943  cmovnz  r8, rsi; PropertyKey
0x180006947  lea     rdx, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x18000694c  call    cs:__imp_SetupDiGetDevicePropertyW
0x180006952  test    eax, eax
0x180006954  jnz     loc_180006AF6
0x18000695a  call    cs:__imp_GetLastError
0x180006960  cmp     eax, 490h
0x180006965  jz      loc_180006BDE
0x18000696b  mov     edi, eax
0x18000696d  test    eax, eax
0x18000696f  jnz     loc_180006C41
0x180006975  mov     [rsp+2D0h+Flags], r13d; Flags
0x18000697a  lea     rax, [rsp+2D0h+RequiredSize]
0x18000697f  mov     [rsp+2D0h+Reserved], rax; RequiredSize
0x180006984  lea     r9, [rsp+2D0h+PropertyType]; PropertyType
0x180006989  mov     dword ptr [rsp+2D0h+MachineName], r13d; PropertyBufferSize
0x18000698e  lea     r8, DEVPKEY_Device_DriverExtendedInfs; PropertyKey
0x180006995  lea     rdx, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x18000699a  mov     [rsp+2D0h+DeviceInfoSet], r13; PropertyBuffer
0x18000699f  mov     rcx, r14; DeviceInfoSet
0x1800069a2  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800069a8  test    eax, eax
0x1800069aa  jnz     loc_180006C12
0x1800069b0  call    cs:__imp_GetLastError
0x1800069b6  cmp     eax, 7Ah ; 'z'
0x1800069b9  jnz     loc_180006C12
0x1800069bf  cmp     [rsp+2D0h+PropertyType], 2012h
0x1800069c7  jnz     loc_180006C12
0x1800069cd  mov     ecx, [rsp+2D0h+RequiredSize]
0x1800069d1  cmp     ecx, 2
0x1800069d4  jbe     loc_180006C12
0x1800069da  call    cs:__imp_pSetupMalloc
0x1800069e0  mov     rbx, rax
0x1800069e3  test    rax, rax
0x1800069e6  jz      loc_180006C12
0x1800069ec  mov     ecx, [rsp+2D0h+RequiredSize]
0x1800069f0  lea     rax, [rsp+2D0h+RequiredSize]
0x1800069f5  mov     [rsp+2D0h+Flags], r13d; Flags
0x1800069fa  lea     r9, [rsp+2D0h+PropertyType]; PropertyType
0x1800069ff  mov     [rsp+2D0h+Reserved], rax; RequiredSize
0x180006a04  lea     r8, DEVPKEY_Device_DriverExtendedInfs; PropertyKey
0x180006a0b  mov     dword ptr [rsp+2D0h+MachineName], ecx; PropertyBufferSize
0x180006a0f  lea     rdx, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x180006a14  mov     rcx, r14; DeviceInfoSet
0x180006a17  mov     [rsp+2D0h+DeviceInfoSet], rbx; PropertyBuffer
0x180006a1c  call    cs:__imp_SetupDiGetDevicePropertyW
0x180006a22  test    eax, eax
0x180006a24  jz      loc_180006C09
0x180006a2a  cmp     [rsp+2D0h+PropertyType], 2012h
0x180006a32  jnz     loc_180006C09
0x180006a38  mov     eax, [rsp+2D0h+RequiredSize]
0x180006a3c  cmp     eax, 2
0x180006a3f  jnz     short loc_180006A47
0x180006a41  cmp     [rbx], r13w
0x180006a45  jz      short loc_180006A6B
0x180006a47  cmp     eax, 4
0x180006a4a  jb      loc_180006C09
0x180006a50  shr     rax, 1
0x180006a53  cmp     [rbx+rax*2-2], r13w
0x180006a59  jnz     loc_180006C09
0x180006a5f  cmp     [rbx+rax*2-4], r13w
0x180006a65  jnz     loc_180006C09
0x180006a6b  mov     rsi, rbx
0x180006a6e  cmp     [rbx], r13w
0x180006a72  jz      loc_180006BF3
0x180006a78  mov     rcx, [r15+78h]
0x180006a7c  lea     r9, [rsp+2D0h+var_288]
0x180006a81  xor     r8d, r8d
0x180006a84  mov     dword ptr [rsp+2D0h+DeviceInfoSet], 8
0x180006a8c  mov     rdx, rsi
0x180006a8f  call    cs:__imp_pSetupStringTableLookUpStringEx
0x180006a95  mov     edx, dword ptr [rsp+2D0h+var_288+4]
0x180006a99  lea     r9, [rsp+2D0h+var_288]
0x180006a9e  mov     rcx, [r15+78h]
0x180006aa2  cmp     eax, 0FFFFFFFFh
0x180006aa5  mov     r8d, 4
0x180006aab  mov     dword ptr [rsp+2D0h+var_288], 1
0x180006ab3  cmovz   edx, r13d
0x180006ab7  mov     dword ptr [rsp+2D0h+DeviceInfoSet], 8
0x180006abf  mov     dword ptr [rsp+2D0h+var_288+4], edx
0x180006ac3  mov     rdx, rsi
0x180006ac6  call    cs:__imp_pSetupStringTableAddStringEx
0x180006acc  cmp     eax, 0FFFFFFFFh
0x180006acf  jz      loc_180006BEE
0x180006ad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006ad9  inc     rax
0x180006adc  cmp     [rsi+rax*2], r13w
0x180006ae1  jnz     short loc_180006AD9
0x180006ae3  lea     rsi, [rsi+rax*2]
0x180006ae7  add     rsi, 2
0x180006aeb  cmp     [rsi], r13w
0x180006aef  jnz     short loc_180006A78
0x180006af1  jmp     loc_180006BF3
0x180006af6  cmp     [rsp+2D0h+PropertyType], 12h
0x180006afb  jnz     loc_180006BDE
0x180006b01  test    ebx, ebx
0x180006b03  jz      short loc_180006B24
0x180006b05  lea     rdx, asc_18000D154; ":"
0x180006b0c  lea     rcx, [rsp+2D0h+PropertyBuffer]; Str
0x180006b11  call    cs:__imp_wcsstr
0x180006b17  test    rax, rax
0x180006b1a  jz      loc_180006BDE
0x180006b20  mov     [rax], r13w
0x180006b24  cmp     [r15+38h], r13d
0x180006b28  jz      short loc_180006B57
0x180006b2a  cmp     [r15+3Ch], r13d
0x180006b2e  jz      short loc_180006B57
0x180006b30  test    ebx, ebx
0x180006b32  jz      short loc_180006B57
0x180006b34  mov     dword ptr [rsp+2D0h+Reserved], r13d; Flags
0x180006b39  lea     rdx, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x180006b3e  mov     dword ptr [rsp+2D0h+MachineName], r13d; PropertyBufferSize
0x180006b43  xor     r9d, r9d; PropertyType
0x180006b46  mov     r8, rsi; PropertyKey
0x180006b49  mov     [rsp+2D0h+DeviceInfoSet], r13; PropertyBuffer
0x180006b4e  mov     rcx, r14; DeviceInfoSet
0x180006b51  call    cs:__imp_SetupDiSetDevicePropertyW
0x180006b57  mov     rcx, [r15+78h]
0x180006b5b  lea     r9, [rsp+2D0h+var_288]
0x180006b60  xor     r8d, r8d
0x180006b63  mov     dword ptr [rsp+2D0h+DeviceInfoSet], 8
0x180006b6b  lea     rdx, [rsp+2D0h+PropertyBuffer]
0x180006b70  call    cs:__imp_pSetupStringTableLookUpStringEx
0x180006b76  cmp     eax, 0FFFFFFFFh
0x180006b79  jnz     short loc_180006B8B
0x180006b7b  mov     eax, r13d
0x180006b7e  mov     ecx, r13d
0x180006b81  mov     dword ptr [rsp+2D0h+var_288], eax
0x180006b85  mov     dword ptr [rsp+2D0h+var_288+4], ecx
0x180006b89  jmp     short loc_180006B93
0x180006b8b  mov     ecx, dword ptr [rsp+2D0h+var_288+4]
0x180006b8f  mov     eax, dword ptr [rsp+2D0h+var_288]
0x180006b93  test    eax, eax
0x180006b95  jnz     short loc_180006BA3
0x180006b97  mov     eax, r13d
0x180006b9a  test    ebx, ebx
0x180006b9c  setz    al
0x180006b9f  mov     dword ptr [rsp+2D0h+var_288], eax
0x180006ba3  test    ecx, ecx
0x180006ba5  jnz     short loc_180006BB3
0x180006ba7  mov     eax, r13d
0x180006baa  test    ebx, ebx
0x180006bac  setnz   al
0x180006baf  mov     dword ptr [rsp+2D0h+var_288+4], eax
0x180006bb3  mov     rcx, [r15+78h]
0x180006bb7  lea     r9, [rsp+2D0h+var_288]
0x180006bbc  mov     r8d, 4
0x180006bc2  mov     dword ptr [rsp+2D0h+DeviceInfoSet], 8
0x180006bca  lea     rdx, [rsp+2D0h+PropertyBuffer]
0x180006bcf  call    cs:__imp_pSetupStringTableAddStringEx
0x180006bd5  cmp     eax, 0FFFFFFFFh
0x180006bd8  jz      loc_180006C8E
0x180006bde  inc     ebx
0x180006be0  cmp     ebx, 2
0x180006be3  jb      loc_180006911
0x180006be9  jmp     loc_180006975
0x180006bee  mov     edi, 8
0x180006bf3  mov     rcx, rbx
0x180006bf6  call    cs:__imp_pSetupFree
0x180006bfc  test    edi, edi
0x180006bfe  jnz     short loc_180006C41
0x180006c00  lea     rsi, DEVPKEY_Device_RollbackDriverNode
0x180006c07  jmp     short loc_180006C12
0x180006c09  mov     rcx, rbx
0x180006c0c  call    cs:__imp_pSetupFree
0x180006c12  lea     r8, [rsp+2D0h+DeviceInfoData]; DeviceInfoData
0x180006c17  mov     edx, r12d; MemberIndex
0x180006c1a  mov     rcx, r14; DeviceInfoSet
0x180006c1d  call    cs:__imp_SetupDiEnumDeviceInfo
0x180006c23  inc     r12d
0x180006c26  test    eax, eax
0x180006c28  jnz     loc_18000690E
0x180006c2e  call    cs:__imp_GetLastError
0x180006c34  cmp     eax, 103h
0x180006c39  jz      short loc_180006C60
0x180006c3b  mov     edi, eax
0x180006c3d  test    eax, eax
0x180006c3f  jz      short loc_180006C60
0x180006c41  mov     rcx, [r15+30h]
0x180006c45  lea     r9, aFailedToRetrie; "Failed to retrieve installed INF names "...
0x180006c4c  mov     rax, [r15+28h]
0x180006c50  xor     r8d, r8d
0x180006c53  mov     dword ptr [rsp+2D0h+DeviceInfoSet], edi
0x180006c57  lea     edx, [r8+1]
0x180006c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c60  mov     rcx, r14; DeviceInfoSet
0x180006c63  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180006c69  mov     eax, edi
0x180006c6b  mov     rcx, [rbp+1D0h+var_50]
0x180006c72  xor     rcx, rsp; StackCookie
0x180006c75  call    __security_check_cookie
0x180006c7a  add     rsp, 298h
0x180006c81  pop     r15
0x180006c83  pop     r14
0x180006c85  pop     r13
0x180006c87  pop     r12
0x180006c89  pop     rdi
0x180006c8a  pop     rsi
0x180006c8b  pop     rbx
0x180006c8c  pop     rbp
0x180006c8d  retn
0x180006c8e  mov     edi, 8
0x180006c93  jmp     short loc_180006C41
```
