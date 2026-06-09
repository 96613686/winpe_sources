# CEnhancedStorageSilo::GetRegistryProperty(ushort const *,uchar * *,ulong *,ulong)

- ea: `0x180007430`
- end: `0x180007839`
- name: `?GetRegistryProperty@CEnhancedStorageSilo@@AEAAJPEBGPEAPEAEPEAKK@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *this, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180002d68`
- `0x180006af0`
- `0x180007f00`

## callees

- `0x18000124c`
- `0x180001258`
- `0x180003bdc`
- `0x180003c54`
- `0x180003c94`
- `0x180003df0`
- `0x180003ed0`
- `0x180007430`
- `0x180008924`
- `0x18000c4f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800074f6`
- `KERNEL32!GetLastError` at `0x18000756f`
- `KERNEL32!GetLastError` at `0x1800075ff`
- `KERNEL32!GetLastError` at `0x180007685`
- `KERNEL32!GetLastError` at `0x180007766`
- `KERNEL32!GetLastError` at `0x1800074f6`
- `KERNEL32!GetLastError` at `0x18000756f`
- `KERNEL32!GetLastError` at `0x1800075ff`
- `KERNEL32!GetLastError` at `0x180007685`
- `KERNEL32!GetLastError` at `0x180007766`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800075f5`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800075f5`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007801`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007801`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800074e7`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800074e7`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180007565`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180007565`
- `SETUPAPI!SetupDiGetCustomDevicePropertyW` at `0x18000767b`
- `SETUPAPI!SetupDiGetCustomDevicePropertyW` at `0x18000775c`
- `SETUPAPI!SetupDiGetCustomDevicePropertyW` at `0x18000767b`
- `SETUPAPI!SetupDiGetCustomDevicePropertyW` at `0x18000775c`

## string_xrefs

- `0x1800074d2`: `CEnhancedStorageSilo::GetRegistryProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnhancedStorageSilo::GetRegistryProperty(
        CEnhancedStorageSilo *this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned int a5)
{
  unsigned __int8 *v9; // rbx
  HDEVINFO DeviceInfoList; // rdi
  signed int LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v17; // r9
  BYTE *v18; // rax
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // ebx
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  DWORD PropertyBufferSize; // [rsp+44h] [rbp-BCh] BYREF
  DWORD PropertyRegDataType; // [rsp+48h] [rbp-B8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+50h] [rbp-B0h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[272]; // [rsp+90h] [rbp-70h] BYREF

  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  PropertyBufferSize = 0;
  v9 = 0;
  PropertyRegDataType = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, (char)a3, (char)a4, a5);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v30, "CEnhancedStorageSilo::GetRegistryProperty", &v25);
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v25 = LastError;
    if ( LastError < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 15;
LABEL_11:
        WPP_SF_d(v12[2], v13, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, (unsigned int)LastError);
        goto LABEL_54;
      }
      goto LABEL_54;
    }
  }
  DeviceInterfaceData.cbSize = 32;
  if ( !SetupDiOpenDeviceInterfaceW(DeviceInfoList, *((PCWSTR *)this + 8), 0, &DeviceInterfaceData) )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v25 = v14;
    if ( v14 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_54;
      v16 = 16;
      v17 = *((_QWORD *)this + 8);
LABEL_19:
      WPP_SF_Sd(v15[2], v16, (unsigned int)&WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v17, v14);
      goto LABEL_54;
    }
  }
  DeviceInfoData.cbSize = 32;
  if ( SetupDiGetDeviceInterfaceDetailW(DeviceInfoList, &DeviceInterfaceData, 0, 0, 0, &DeviceInfoData) )
    goto LABEL_62;
  LastError = GetLastError();
  if ( LastError == 122 )
    goto LABEL_62;
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v25 = LastError;
  if ( LastError >= 0 )
  {
LABEL_62:
    if ( !SetupDiGetCustomDevicePropertyW(DeviceInfoList, &DeviceInfoData, a2, 0, 0, 0, 0, &PropertyBufferSize) )
    {
      v14 = GetLastError();
      if ( v14 != 122 )
      {
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        v25 = v14;
        if ( v14 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_54;
          v16 = 18;
LABEL_36:
          LODWORD(v17) = (_DWORD)a2;
          goto LABEL_19;
        }
      }
    }
    v18 = (BYTE *)operator new[](PropertyBufferSize);
    v9 = v18;
    if ( v18 )
    {
      if ( !SetupDiGetCustomDevicePropertyW(
              DeviceInfoList,
              &DeviceInfoData,
              a2,
              0,
              &PropertyRegDataType,
              v18,
              PropertyBufferSize,
              0) )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        v25 = v14;
        if ( v14 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_54;
          v16 = 20;
          goto LABEL_36;
        }
      }
      v22 = PropertyRegDataType;
      if ( PropertyRegDataType == a5 )
      {
        *a3 = v9;
        *a4 = PropertyBufferSize;
        goto LABEL_54;
      }
      v19 = -2147418113;
      v25 = -2147418113;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_56;
      v21 = 21;
    }
    else
    {
      v19 = -2147024882;
      v25 = -2147024882;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_57;
      v21 = 19;
      v22 = PropertyBufferSize;
    }
    WPP_SF_dd(v20[2], v21, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v22, v19);
    goto LABEL_54;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v13 = 17;
    goto LABEL_11;
  }
LABEL_54:
  if ( v25 < 0 && v9 )
LABEL_56:
    operator delete[](v9);
LABEL_57:
  if ( DeviceInfoList != (HDEVINFO)-1LL )
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
  v23 = v25;
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v30);
  return v23;
}

```

## disassembly

```asm
0x180007430  push    rbp
0x180007432  push    rbx
0x180007433  push    rsi
0x180007434  push    rdi
0x180007435  push    r12
0x180007437  push    r13
0x180007439  push    r14
0x18000743b  push    r15
0x18000743d  lea     rbp, [rsp-0B8h]
0x180007445  sub     rsp, 1B8h
0x18000744c  mov     rax, cs:__security_cookie
0x180007453  xor     rax, rsp
0x180007456  mov     [rbp+0F0h+var_50], rax
0x18000745d  mov     r12, r9
0x180007460  mov     r15, r8
0x180007463  mov     rsi, rdx
0x180007466  mov     r14, rcx
0x180007469  xorps   xmm0, xmm0
0x18000746c  movups  xmmword ptr [rsp+1F0h+var_1A0.cbSize], xmm0
0x180007471  movups  xmmword ptr [rsp+1F0h+var_1A0.ClassGuid.Data4+4], xmm0
0x180007476  xorps   xmm1, xmm1
0x180007479  movups  xmmword ptr [rsp+1F0h+DeviceInterfaceData.cbSize], xmm1
0x18000747e  movups  xmmword ptr [rbp+0F0h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm1
0x180007482  xor     eax, eax
0x180007484  mov     [rsp+1F0h+var_1AC], eax
0x180007488  mov     ebx, eax
0x18000748a  mov     [rsp+1F0h+PropertyRegDataType], eax
0x18000748e  mov     [rsp+1F0h+var_1B0], eax
0x180007492  lea     rax, WPP_GLOBAL_Control
0x180007499  mov     r13d, [rbp+0F0h+arg_20]
0x1800074a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074a7  cmp     rcx, rax
0x1800074aa  jz      short loc_1800074CD
0x1800074ac  test    byte ptr [rcx+1Ch], 10h
0x1800074b0  jz      short loc_1800074CD
0x1800074b2  mov     [rsp+1F0h+PropertyBufferSize], r13d
0x1800074b7  mov     [rsp+1F0h+DeviceInfoData], r9
0x1800074bc  mov     [rsp+1F0h+RequiredSize], r8
0x1800074c1  mov     r9, rdx
0x1800074c4  mov     rcx, [rcx+10h]
0x1800074c8  call    WPP_SF_SqqD
0x1800074cd  lea     r8, [rsp+1F0h+var_1B0]; int *
0x1800074d2  lea     rdx, aCenhancedstora_9; "CEnhancedStorageSilo::GetRegistryProper"...
0x1800074d9  lea     rcx, [rbp+0F0h+var_160]; this
0x1800074dd  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x1800074e2  nop
0x1800074e3  xor     edx, edx; hwndParent
0x1800074e5  xor     ecx, ecx; ClassGuid
0x1800074e7  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800074ed  mov     rdi, rax
0x1800074f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800074f4  jnz     short loc_18000754E
0x1800074f6  call    cs:__imp_GetLastError
0x1800074fc  test    eax, eax
0x1800074fe  jle     short loc_180007508
0x180007500  movzx   eax, ax
0x180007503  or      eax, 80070000h
0x180007508  mov     [rsp+1F0h+var_1B0], eax
0x18000750c  test    eax, eax
0x18000750e  jns     short loc_18000754E
0x180007510  mov     rcx, cs:WPP_GLOBAL_Control
0x180007517  lea     rdx, WPP_GLOBAL_Control
0x18000751e  cmp     rcx, rdx
0x180007521  jz      loc_1800077E4
0x180007527  test    byte ptr [rcx+1Ch], 2
0x18000752b  jz      loc_1800077E4
0x180007531  mov     edx, 0Fh
0x180007536  mov     r9d, eax
0x180007539  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007540  mov     rcx, [rcx+10h]
0x180007544  call    WPP_SF_d
0x180007549  jmp     loc_1800077E4
0x18000754e  mov     [rsp+1F0h+DeviceInterfaceData.cbSize], 20h ; ' '
0x180007556  lea     r9, [rsp+1F0h+DeviceInterfaceData]; DeviceInterfaceData
0x18000755b  xor     r8d, r8d; OpenFlags
0x18000755e  mov     rdx, [r14+40h]; DevicePath
0x180007562  mov     rcx, rdi; DeviceInfoSet
0x180007565  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x18000756b  test    eax, eax
0x18000756d  jnz     short loc_1800075CC
0x18000756f  call    cs:__imp_GetLastError
0x180007575  test    eax, eax
0x180007577  jle     short loc_180007581
0x180007579  movzx   eax, ax
0x18000757c  or      eax, 80070000h
0x180007581  mov     [rsp+1F0h+var_1B0], eax
0x180007585  test    eax, eax
0x180007587  jns     short loc_1800075CC
0x180007589  mov     rcx, cs:WPP_GLOBAL_Control
0x180007590  lea     rdx, WPP_GLOBAL_Control
0x180007597  cmp     rcx, rdx
0x18000759a  jz      loc_1800077E4
0x1800075a0  test    byte ptr [rcx+1Ch], 2
0x1800075a4  jz      loc_1800077E4
0x1800075aa  mov     edx, 10h
0x1800075af  mov     r9, [r14+40h]
0x1800075b3  mov     dword ptr [rsp+1F0h+RequiredSize], eax
0x1800075b7  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800075be  mov     rcx, [rcx+10h]
0x1800075c2  call    WPP_SF_Sd
0x1800075c7  jmp     loc_1800077E4
0x1800075cc  mov     [rsp+1F0h+var_1A0.cbSize], 20h ; ' '
0x1800075d4  lea     rax, [rsp+1F0h+var_1A0]
0x1800075d9  mov     [rsp+1F0h+DeviceInfoData], rax; DeviceInfoData
0x1800075de  mov     [rsp+1F0h+RequiredSize], 0; RequiredSize
0x1800075e7  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1800075ea  xor     r8d, r8d; DeviceInterfaceDetailData
0x1800075ed  lea     rdx, [rsp+1F0h+DeviceInterfaceData]; DeviceInterfaceData
0x1800075f2  mov     rcx, rdi; DeviceInfoSet
0x1800075f5  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800075fb  test    eax, eax
0x1800075fd  jnz     short loc_180007649
0x1800075ff  call    cs:__imp_GetLastError
0x180007605  cmp     eax, 7Ah ; 'z'
0x180007608  jz      short loc_180007649
0x18000760a  test    eax, eax
0x18000760c  jle     short loc_180007616
0x18000760e  movzx   eax, ax
0x180007611  or      eax, 80070000h
0x180007616  mov     [rsp+1F0h+var_1B0], eax
0x18000761a  test    eax, eax
0x18000761c  jns     short loc_180007649
0x18000761e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007625  lea     rdx, WPP_GLOBAL_Control
0x18000762c  cmp     rcx, rdx
0x18000762f  jz      loc_1800077E4
0x180007635  test    byte ptr [rcx+1Ch], 2
0x180007639  jz      loc_1800077E4
0x18000763f  mov     edx, 11h
0x180007644  jmp     loc_180007536
0x180007649  lea     rax, [rsp+1F0h+var_1AC]
0x18000764e  mov     [rsp+1F0h+var_1B8], rax; RequiredSize
0x180007653  mov     [rsp+1F0h+PropertyBufferSize], 0; PropertyBufferSize
0x18000765b  mov     [rsp+1F0h+DeviceInfoData], 0; PropertyBuffer
0x180007664  mov     [rsp+1F0h+RequiredSize], 0; PropertyRegDataType
0x18000766d  xor     r9d, r9d; Flags
0x180007670  mov     r8, rsi; CustomPropertyName
0x180007673  lea     rdx, [rsp+1F0h+var_1A0]; DeviceInfoData
0x180007678  mov     rcx, rdi; DeviceInfoSet
0x18000767b  call    cs:__imp_SetupDiGetCustomDevicePropertyW
0x180007681  test    eax, eax
0x180007683  jnz     short loc_1800076D2
0x180007685  call    cs:__imp_GetLastError
0x18000768b  cmp     eax, 7Ah ; 'z'
0x18000768e  jz      short loc_1800076D2
0x180007690  test    eax, eax
0x180007692  jle     short loc_18000769C
0x180007694  movzx   eax, ax
0x180007697  or      eax, 80070000h
0x18000769c  mov     [rsp+1F0h+var_1B0], eax
0x1800076a0  test    eax, eax
0x1800076a2  jns     short loc_1800076D2
0x1800076a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ab  lea     rdx, WPP_GLOBAL_Control
0x1800076b2  cmp     rcx, rdx
0x1800076b5  jz      loc_1800077E4
0x1800076bb  test    byte ptr [rcx+1Ch], 2
0x1800076bf  jz      loc_1800077E4
0x1800076c5  mov     edx, 12h
0x1800076ca  mov     r9, rsi
0x1800076cd  jmp     loc_1800075B3
0x1800076d2  mov     ecx, [rsp+1F0h+var_1AC]; unsigned __int64
0x1800076d6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800076db  mov     rbx, rax
0x1800076de  test    rax, rax
0x1800076e1  jnz     short loc_18000772E
0x1800076e3  mov     eax, 8007000Eh
0x1800076e8  mov     [rsp+1F0h+var_1B0], eax
0x1800076ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076f3  lea     rdx, WPP_GLOBAL_Control
0x1800076fa  cmp     rcx, rdx
0x1800076fd  jz      loc_1800077F8
0x180007703  test    byte ptr [rcx+1Ch], 2
0x180007707  jz      loc_1800077F8
0x18000770d  lea     edx, [rbx+13h]
0x180007710  mov     r9d, [rsp+1F0h+var_1AC]
0x180007715  mov     dword ptr [rsp+1F0h+RequiredSize], eax
0x180007719  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007720  mov     rcx, [rcx+10h]
0x180007724  call    WPP_SF_dd
0x180007729  jmp     loc_1800077E4
0x18000772e  mov     [rsp+1F0h+var_1B8], 0; RequiredSize
0x180007737  mov     eax, [rsp+1F0h+var_1AC]
0x18000773b  mov     [rsp+1F0h+PropertyBufferSize], eax; PropertyBufferSize
0x18000773f  mov     [rsp+1F0h+DeviceInfoData], rbx; PropertyBuffer
0x180007744  lea     rax, [rsp+1F0h+PropertyRegDataType]
0x180007749  mov     [rsp+1F0h+RequiredSize], rax; PropertyRegDataType
0x18000774e  xor     r9d, r9d; Flags
0x180007751  mov     r8, rsi; CustomPropertyName
0x180007754  lea     rdx, [rsp+1F0h+var_1A0]; DeviceInfoData
0x180007759  mov     rcx, rdi; DeviceInfoSet
0x18000775c  call    cs:__imp_SetupDiGetCustomDevicePropertyW
0x180007762  test    eax, eax
0x180007764  jnz     short loc_1800077A3
0x180007766  call    cs:__imp_GetLastError
0x18000776c  test    eax, eax
0x18000776e  jle     short loc_180007778
0x180007770  movzx   eax, ax
0x180007773  or      eax, 80070000h
0x180007778  mov     [rsp+1F0h+var_1B0], eax
0x18000777c  test    eax, eax
0x18000777e  jns     short loc_1800077A3
0x180007780  mov     rcx, cs:WPP_GLOBAL_Control
0x180007787  lea     rdx, WPP_GLOBAL_Control
0x18000778e  cmp     rcx, rdx
0x180007791  jz      short loc_1800077E4
0x180007793  test    byte ptr [rcx+1Ch], 2
0x180007797  jz      short loc_1800077E4
0x180007799  mov     edx, 14h
0x18000779e  jmp     loc_1800076CA
0x1800077a3  mov     r9d, [rsp+1F0h+PropertyRegDataType]
0x1800077a8  cmp     r9d, r13d
0x1800077ab  jz      short loc_1800077D9
0x1800077ad  mov     eax, 8000FFFFh
0x1800077b2  mov     [rsp+1F0h+var_1B0], eax
0x1800077b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077bd  lea     rdx, WPP_GLOBAL_Control
0x1800077c4  cmp     rcx, rdx
0x1800077c7  jz      short loc_1800077F0
0x1800077c9  test    byte ptr [rcx+1Ch], 2
0x1800077cd  jz      short loc_1800077F0
0x1800077cf  mov     edx, 15h
0x1800077d4  jmp     loc_180007715
0x1800077d9  mov     [r15], rbx
0x1800077dc  mov     eax, [rsp+1F0h+var_1AC]
0x1800077e0  mov     [r12], eax
0x1800077e4  cmp     [rsp+1F0h+var_1B0], 0
0x1800077e9  jge     short loc_1800077F8
0x1800077eb  test    rbx, rbx
0x1800077ee  jz      short loc_1800077F8
0x1800077f0  mov     rcx, rbx; Block
0x1800077f3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800077f8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800077fc  jz      short loc_180007807
0x1800077fe  mov     rcx, rdi; DeviceInfoSet
0x180007801  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180007807  mov     ebx, [rsp+1F0h+var_1B0]
0x18000780b  lea     rcx, [rbp+0F0h+var_160]; this
0x18000780f  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180007814  mov     eax, ebx
0x180007816  mov     rcx, [rbp+0F0h+var_50]
0x18000781d  xor     rcx, rsp; StackCookie
0x180007820  call    __security_check_cookie
0x180007825  add     rsp, 1B8h
0x18000782c  pop     r15
0x18000782e  pop     r14
0x180007830  pop     r13
0x180007832  pop     r12
0x180007834  pop     rdi
0x180007835  pop     rsi
0x180007836  pop     rbx
0x180007837  pop     rbp
0x180007838  retn
```
