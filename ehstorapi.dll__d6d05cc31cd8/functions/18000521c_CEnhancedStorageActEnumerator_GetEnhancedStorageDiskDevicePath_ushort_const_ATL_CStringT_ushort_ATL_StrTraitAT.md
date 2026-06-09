# CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18000521c`
- end: `0x180005954`
- name: `?GetEnhancedStorageDiskDevicePath@CEnhancedStorageActEnumerator@@AEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1848`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x180005960`

## callees

- `0x18000124c`
- `0x180001258`
- `0x180003864`
- `0x18000394c`
- `0x180003bdc`
- `0x180003c54`
- `0x180003c94`
- `0x180003ce0`
- `0x180003df0`
- `0x180003e58`
- `0x180003ed0`
- `0x180003ff4`
- `0x180004194`
- `0x1800046b4`
- `0x18000521c`
- `0x18000604c`
- `0x1800060e8`
- `0x180006148`
- `0x18000c4f0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000548e`
- `KERNEL32!CreateFileW` at `0x18000548e`
- `KERNEL32!GetLastError` at `0x1800052e7`
- `KERNEL32!GetLastError` at `0x18000534c`
- `KERNEL32!GetLastError` at `0x1800053ca`
- `KERNEL32!GetLastError` at `0x1800054d4`
- `KERNEL32!GetLastError` at `0x1800055d0`
- `KERNEL32!GetLastError` at `0x1800056ff`
- `KERNEL32!GetLastError` at `0x1800057c8`
- `KERNEL32!GetLastError` at `0x180005897`
- `KERNEL32!GetLastError` at `0x1800052e7`
- `KERNEL32!GetLastError` at `0x18000534c`
- `KERNEL32!GetLastError` at `0x1800053ca`
- `KERNEL32!GetLastError` at `0x1800054d4`
- `KERNEL32!GetLastError` at `0x1800055d0`
- `KERNEL32!GetLastError` at `0x1800056ff`
- `KERNEL32!GetLastError` at `0x1800057c8`
- `KERNEL32!GetLastError` at `0x180005897`
- `KERNEL32!DeviceIoControl` at `0x1800054cc`
- `KERNEL32!DeviceIoControl` at `0x18000554f`
- `KERNEL32!DeviceIoControl` at `0x1800054cc`
- `KERNEL32!DeviceIoControl` at `0x18000554f`
- `KERNEL32!CloseHandle` at `0x1800054ef`
- `KERNEL32!CloseHandle` at `0x1800055fd`
- `KERNEL32!CloseHandle` at `0x18000588f`
- `KERNEL32!CloseHandle` at `0x1800054ef`
- `KERNEL32!CloseHandle` at `0x1800055fd`
- `KERNEL32!CloseHandle` at `0x18000588f`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800053c2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800055c8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800053c2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800055c8`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000590a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000590a`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800052d8`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800052d8`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005342`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005591`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005342`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005591`

## string_xrefs

- `0x1800052b4`: `CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3)
{
  HDEVINFO DeviceInfoList; // rax
  void *v6; // r13
  signed int LastError; // eax
  signed int v8; // eax
  BOOL DeviceInterfaceDetailW; // ebx
  DWORD v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  signed int DeviceList; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  unsigned int i; // esi
  __int64 v18; // r15
  LPCWSTR *v19; // rax
  HANDLE FileW; // r12
  BOOL v21; // ebx
  DWORD v22; // eax
  __int64 v23; // r8
  WCHAR *v24; // rdi
  BOOL v25; // ebx
  DWORD v26; // eax
  __int64 v27; // r8
  __int64 v28; // rdx
  int *v29; // rsi
  __int64 v30; // rbx
  _QWORD *v31; // rax
  signed int v32; // eax
  signed int v33; // eax
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // ebx
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  DWORD RequiredSize; // [rsp+48h] [rbp-B8h] BYREF
  int InBuffer; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  int v45; // [rsp+68h] [rbp-98h]
  unsigned __int64 v46; // [rsp+70h] [rbp-90h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+78h] [rbp-88h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+98h] [rbp-68h] BYREF
  struct _SP_DEVINFO_DATA v49; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v50[272]; // [rsp+E0h] [rbp-20h] BYREF

  v38 = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, (_DWORD)a3, (_DWORD)a2, (char)a3);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v50, "CEnhancedStorageActEnumerator::GetEnhancedStorageDiskDevicePath", &v38);
  DeviceInfoData.cbSize = 32;
  DeviceInterfaceData.cbSize = 32;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  v6 = DeviceInfoList;
  if ( DeviceInfoList == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v38 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
        (unsigned int)LastError);
  }
  else
  {
    if ( SetupDiOpenDeviceInterfaceW(DeviceInfoList, a2, 0, &DeviceInterfaceData) )
    {
      RequiredSize = 0;
      DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW(
                                 v6,
                                 &DeviceInterfaceData,
                                 0,
                                 0,
                                 &RequiredSize,
                                 &DeviceInfoData);
      v10 = GetLastError();
      if ( DeviceInterfaceDetailW || v10 != 122 )
      {
        v38 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v12, v10, -2147418113);
      }
      else
      {
        DeviceList = CEnhancedStorageActEnumerator::GetDeviceList(v11, &v42);
        v38 = DeviceList;
        if ( DeviceList >= 0 )
        {
          v16 = v43;
          v46 = v43;
          for ( i = 0; ; ++i )
          {
            v18 = i;
            if ( i >= v16 )
            {
              v38 = -2147023728;
              goto LABEL_85;
            }
            InBuffer = 1;
            BytesReturned = 0;
            memset(&v49, 0, sizeof(v49));
            v49.cbSize = 32;
            v19 = (LPCWSTR *)ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](&v42, i);
            FileW = CreateFileW(*v19, 0x80000000, 3u, 0, 3u, 0, 0);
            if ( FileW == (HANDLE)-1LL )
              break;
            v21 = DeviceIoControl(FileW, 0x2D1410u, &InBuffer, 4u, 0, 0, &BytesReturned, 0);
            v22 = GetLastError();
            if ( v21 )
              goto LABEL_72;
            if ( v22 == 1168 )
            {
              CloseHandle(FileW);
            }
            else
            {
              if ( v22 != 234 )
              {
LABEL_72:
                v38 = -2147418113;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v23, v22, -2147418113);
                goto LABEL_75;
              }
              v24 = (WCHAR *)operator new[](BytesReturned);
              if ( !v24 )
              {
                v38 = -2147024882;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    57,
                    &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
                    "pbBuffer");
                goto LABEL_75;
              }
              if ( !DeviceIoControl(FileW, 0x2D1410u, &InBuffer, 4u, v24, BytesReturned, &BytesReturned, 0) )
              {
                v33 = GetLastError();
                if ( v33 > 0 )
                  v33 = (unsigned __int16)v33 | 0x80070000;
                v38 = v33;
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v35 = 58;
                  goto LABEL_67;
                }
LABEL_68:
                operator delete[](v24);
LABEL_75:
                CloseHandle(FileW);
                goto LABEL_85;
              }
              if ( *(_DWORD *)v24 != 1 )
              {
                v38 = -2147024883;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    59,
                    &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
                    *(unsigned int *)v24,
                    -2147024883);
                goto LABEL_68;
              }
              if ( *((_BYTE *)v24 + 4) != 1 )
              {
                v33 = -2147024883;
                v38 = -2147024883;
                v34 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_68;
                v35 = 60;
LABEL_67:
                WPP_SF_d(v34[2], v35, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, (unsigned int)v33);
                goto LABEL_68;
              }
              v24[9] = v24[8];
              DeviceInterfaceData.cbSize = 32;
              if ( !SetupDiOpenDeviceInterfaceW(v6, v24 + 8, 0, &DeviceInterfaceData) )
              {
                v32 = GetLastError();
                if ( v32 > 0 )
                  v32 = (unsigned __int16)v32 | 0x80070000;
                v38 = v32;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    61,
                    (unsigned int)&WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
                    (_DWORD)v24 + 16,
                    v32);
                goto LABEL_68;
              }
              RequiredSize = 0;
              v25 = SetupDiGetDeviceInterfaceDetailW(v6, &DeviceInterfaceData, 0, 0, &RequiredSize, &v49);
              v26 = GetLastError();
              if ( v25 || v26 != 122 )
              {
                v38 = -2147418113;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, v27, v26, -2147418113);
                goto LABEL_68;
              }
              if ( v49.DevInst == DeviceInfoData.DevInst )
              {
                v38 = 0;
                v28 = *(_QWORD *)ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](&v42, i);
                v29 = (int *)(*a3 - 24LL);
                if ( (int *)(v28 - 24) != v29 )
                {
                  if ( v29[4] >= 0 && *(_QWORD *)(v28 - 24) == *(_QWORD *)v29 )
                  {
                    v30 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                    ATL::CStringData::Release((ATL::CStringData *)v29);
                    *a3 = v30 + 24;
                  }
                  else
                  {
                    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v28, *(unsigned int *)(v28 - 16));
                  }
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                {
                  v31 = (_QWORD *)ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](&v42, v18);
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    63,
                    &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
                    *v31);
                }
                goto LABEL_68;
              }
              operator delete[](v24);
              CloseHandle(FileW);
            }
            v16 = v46;
          }
          DeviceList = GetLastError();
          if ( DeviceList > 0 )
            DeviceList = (unsigned __int16)DeviceList | 0x80070000;
          v38 = DeviceList;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v15 = 55;
            goto LABEL_22;
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v15 = 54;
LABEL_22:
            WPP_SF_d(v14[2], v15, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, (unsigned int)DeviceList);
          }
        }
      }
    }
    else
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v38 = v8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)&WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
          (_DWORD)a2,
          v8);
    }
LABEL_85:
    SetupDiDestroyDeviceInfoList(v6);
  }
  v36 = v38;
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v50);
  ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(&v42);
  return v36;
}

```

## disassembly

```asm
0x18000521c  mov     [rsp-8+arg_0], rbx
0x180005221  push    rbp
0x180005222  push    rsi
0x180005223  push    rdi
0x180005224  push    r12
0x180005226  push    r13
0x180005228  push    r14
0x18000522a  push    r15
0x18000522c  lea     rbp, [rsp-100h]
0x180005234  sub     rsp, 200h
0x18000523b  mov     rax, cs:__security_cookie
0x180005242  xor     rax, rsp
0x180005245  mov     [rbp+130h+var_40], rax
0x18000524c  mov     r14, r8
0x18000524f  mov     rbx, rdx
0x180005252  xor     edi, edi
0x180005254  mov     [rsp+230h+var_1F0], edi
0x180005258  xorps   xmm0, xmm0
0x18000525b  movups  xmmword ptr [rbp+130h+var_198.cbSize], xmm0
0x18000525f  movups  xmmword ptr [rbp+130h+var_198.ClassGuid.Data4+4], xmm0
0x180005263  xorps   xmm1, xmm1
0x180005266  movups  xmmword ptr [rsp+230h+DeviceInterfaceData.cbSize], xmm1
0x18000526b  movups  xmmword ptr [rbp+130h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm1
0x18000526f  mov     [rsp+230h+var_1E0], rdi
0x180005274  mov     [rsp+230h+var_1D8], rdi
0x180005279  mov     [rsp+230h+var_1D0], rdi
0x18000527e  mov     [rsp+230h+var_1C8], edi
0x180005282  lea     rsi, WPP_GLOBAL_Control
0x180005289  mov     rcx, cs:WPP_GLOBAL_Control
0x180005290  cmp     rcx, rsi
0x180005293  jz      short loc_1800052AF
0x180005295  test    byte ptr [rcx+1Ch], 10h
0x180005299  jz      short loc_1800052AF
0x18000529b  lea     edx, [rdi+32h]
0x18000529e  mov     [rsp+230h+RequiredSize], r8
0x1800052a3  mov     r9, rbx
0x1800052a6  mov     rcx, [rcx+10h]
0x1800052aa  call    WPP_SF_Sq
0x1800052af  lea     r8, [rsp+230h+var_1F0]; int *
0x1800052b4  lea     rdx, aCenhancedstora_3; "CEnhancedStorageActEnumerator::GetEnhan"...
0x1800052bb  lea     rcx, [rbp+130h+var_150]; this
0x1800052bf  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x1800052c4  nop
0x1800052c5  mov     [rbp+130h+var_198.cbSize], 20h ; ' '
0x1800052cc  mov     [rsp+230h+DeviceInterfaceData.cbSize], 20h ; ' '
0x1800052d4  xor     edx, edx; hwndParent
0x1800052d6  xor     ecx, ecx; ClassGuid
0x1800052d8  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800052de  mov     r13, rax
0x1800052e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800052e5  jnz     short loc_180005334
0x1800052e7  call    cs:__imp_GetLastError
0x1800052ed  test    eax, eax
0x1800052ef  jle     short loc_1800052F9
0x1800052f1  movzx   eax, ax
0x1800052f4  or      eax, 80070000h
0x1800052f9  mov     [rsp+230h+var_1F0], eax
0x1800052fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005304  cmp     rcx, rsi
0x180005307  jz      loc_180005910
0x18000530d  test    byte ptr [rcx+1Ch], 2
0x180005311  jz      loc_180005910
0x180005317  mov     edx, 33h ; '3'
0x18000531c  mov     r9d, eax
0x18000531f  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180005326  mov     rcx, [rcx+10h]
0x18000532a  call    WPP_SF_d
0x18000532f  jmp     loc_180005910
0x180005334  lea     r9, [rsp+230h+DeviceInterfaceData]; DeviceInterfaceData
0x180005339  xor     r8d, r8d; OpenFlags
0x18000533c  mov     rdx, rbx; DevicePath
0x18000533f  mov     rcx, r13; DeviceInfoSet
0x180005342  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x180005348  test    eax, eax
0x18000534a  jnz     short loc_18000539D
0x18000534c  call    cs:__imp_GetLastError
0x180005352  test    eax, eax
0x180005354  jle     short loc_18000535E
0x180005356  movzx   eax, ax
0x180005359  or      eax, 80070000h
0x18000535e  mov     [rsp+230h+var_1F0], eax
0x180005362  mov     rcx, cs:WPP_GLOBAL_Control
0x180005369  cmp     rcx, rsi
0x18000536c  jz      loc_180005907
0x180005372  test    byte ptr [rcx+1Ch], 2
0x180005376  jz      loc_180005907
0x18000537c  mov     edx, 34h ; '4'
0x180005381  mov     dword ptr [rsp+230h+RequiredSize], eax
0x180005385  mov     r9, rbx
0x180005388  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x18000538f  mov     rcx, [rcx+10h]
0x180005393  call    WPP_SF_Sd
0x180005398  jmp     loc_180005907
0x18000539d  mov     [rsp+230h+var_1E8], edi
0x1800053a1  lea     rax, [rbp+130h+var_198]
0x1800053a5  mov     [rsp+230h+DeviceInfoData], rax; DeviceInfoData
0x1800053aa  lea     rax, [rsp+230h+var_1E8]
0x1800053af  mov     [rsp+230h+RequiredSize], rax; RequiredSize
0x1800053b4  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1800053b7  xor     r8d, r8d; DeviceInterfaceDetailData
0x1800053ba  lea     rdx, [rsp+230h+DeviceInterfaceData]; DeviceInterfaceData
0x1800053bf  mov     rcx, r13; DeviceInfoSet
0x1800053c2  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800053c8  mov     ebx, eax
0x1800053ca  call    cs:__imp_GetLastError
0x1800053d0  mov     r9d, eax
0x1800053d3  test    ebx, ebx
0x1800053d5  jnz     loc_1800058DA
0x1800053db  cmp     eax, 7Ah ; 'z'
0x1800053de  jnz     loc_1800058DA
0x1800053e4  lea     rdx, [rsp+230h+var_1E0]
0x1800053e9  call    ?GetDeviceList@CEnhancedStorageActEnumerator@@AEAAJAEAV?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@@Z; CEnhancedStorageActEnumerator::GetDeviceList(ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>> &)
0x1800053ee  mov     [rsp+230h+var_1F0], eax
0x1800053f2  test    eax, eax
0x1800053f4  jns     short loc_18000542B
0x1800053f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053fd  cmp     rcx, rsi
0x180005400  jz      loc_180005907
0x180005406  test    byte ptr [rcx+1Ch], 2
0x18000540a  jz      loc_180005907
0x180005410  lea     edx, [rbx+36h]
0x180005413  mov     r9d, eax
0x180005416  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x18000541d  mov     rcx, [rcx+10h]
0x180005421  call    WPP_SF_d
0x180005426  jmp     loc_180005907
0x18000542b  mov     rax, [rsp+230h+var_1D8]
0x180005430  mov     [rsp+230h+var_1C0], rax
0x180005435  mov     esi, edi
0x180005437  mov     r15d, esi
0x18000543a  cmp     r15, rax
0x18000543d  jnb     loc_1800058D0
0x180005443  mov     [rsp+230h+InBuffer], 1
0x18000544b  mov     [rsp+230h+BytesReturned], edi
0x18000544f  xorps   xmm0, xmm0
0x180005452  movups  xmmword ptr [rbp+130h+var_178.cbSize], xmm0
0x180005456  movups  xmmword ptr [rbp+130h+var_178.ClassGuid.Data4+4], xmm0
0x18000545a  mov     [rbp+130h+var_178.cbSize], 20h ; ' '
0x180005461  mov     edx, r15d
0x180005464  lea     rcx, [rsp+230h+var_1E0]
0x180005469  call    ??A?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAAAEAVDeviceData@@_K@Z; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](unsigned __int64)
0x18000546e  mov     [rsp+230h+hTemplateFile], rdi; hTemplateFile
0x180005473  mov     dword ptr [rsp+230h+DeviceInfoData], edi; dwFlagsAndAttributes
0x180005477  mov     dword ptr [rsp+230h+RequiredSize], 3; dwCreationDisposition
0x18000547f  xor     r9d, r9d; lpSecurityAttributes
0x180005482  mov     edx, 80000000h; dwDesiredAccess
0x180005487  lea     r8d, [r9+3]; dwShareMode
0x18000548b  mov     rcx, [rax]; lpFileName
0x18000548e  call    cs:__imp_CreateFileW
0x180005494  mov     r12, rax
0x180005497  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000549b  jz      loc_180005897
0x1800054a1  mov     [rsp+230h+lpOverlapped], rdi; lpOverlapped
0x1800054a6  lea     rax, [rsp+230h+BytesReturned]
0x1800054ab  mov     [rsp+230h+hTemplateFile], rax; lpBytesReturned
0x1800054b0  mov     dword ptr [rsp+230h+DeviceInfoData], edi; nOutBufferSize
0x1800054b4  mov     [rsp+230h+RequiredSize], rdi; lpOutBuffer
0x1800054b9  mov     r9d, 4; nInBufferSize
0x1800054bf  lea     r8, [rsp+230h+InBuffer]; lpInBuffer
0x1800054c4  mov     edx, 2D1410h; dwIoControlCode
0x1800054c9  mov     rcx, r12; hDevice
0x1800054cc  call    cs:__imp_DeviceIoControl
0x1800054d2  mov     ebx, eax
0x1800054d4  call    cs:__imp_GetLastError
0x1800054da  mov     r9d, eax
0x1800054dd  test    ebx, ebx
0x1800054df  jnz     loc_180005858
0x1800054e5  cmp     eax, 490h
0x1800054ea  jnz     short loc_1800054FA
0x1800054ec  mov     rcx, r12; hObject
0x1800054ef  call    cs:__imp_CloseHandle
0x1800054f5  jmp     loc_180005605
0x1800054fa  cmp     r9d, 0EAh
0x180005501  jnz     loc_180005858
0x180005507  mov     ecx, [rsp+230h+BytesReturned]; unsigned __int64
0x18000550b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005510  mov     rdi, rax
0x180005513  test    rax, rax
0x180005516  jz      loc_180005819
0x18000551c  mov     [rsp+230h+lpOverlapped], 0; lpOverlapped
0x180005525  lea     rax, [rsp+230h+BytesReturned]
0x18000552a  mov     [rsp+230h+hTemplateFile], rax; lpBytesReturned
0x18000552f  mov     eax, [rsp+230h+BytesReturned]
0x180005533  mov     dword ptr [rsp+230h+DeviceInfoData], eax; nOutBufferSize
0x180005537  mov     [rsp+230h+RequiredSize], rdi; lpOutBuffer
0x18000553c  mov     r9d, 4; nInBufferSize
0x180005542  lea     r8, [rsp+230h+InBuffer]; lpInBuffer
0x180005547  mov     edx, 2D1410h; dwIoControlCode
0x18000554c  mov     rcx, r12; hDevice
0x18000554f  call    cs:__imp_DeviceIoControl
0x180005555  test    eax, eax
0x180005557  jz      loc_1800057C8
0x18000555d  cmp     dword ptr [rdi], 1
0x180005560  jnz     loc_180005788
0x180005566  cmp     byte ptr [rdi+4], 1
0x18000556a  jnz     loc_180005757
0x180005570  lea     rbx, [rdi+10h]
0x180005574  movzx   eax, word ptr [rbx]
0x180005577  mov     [rdi+12h], ax
0x18000557b  mov     [rsp+230h+DeviceInterfaceData.cbSize], 20h ; ' '
0x180005583  lea     r9, [rsp+230h+DeviceInterfaceData]; DeviceInterfaceData
0x180005588  xor     r8d, r8d; OpenFlags
0x18000558b  mov     rdx, rbx; DevicePath
0x18000558e  mov     rcx, r13; DeviceInfoSet
0x180005591  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x180005597  test    eax, eax
0x180005599  jz      loc_1800056FF
0x18000559f  mov     [rsp+230h+var_1E8], 0
0x1800055a7  lea     rax, [rbp+130h+var_178]
0x1800055ab  mov     [rsp+230h+DeviceInfoData], rax; DeviceInfoData
0x1800055b0  lea     rax, [rsp+230h+var_1E8]
0x1800055b5  mov     [rsp+230h+RequiredSize], rax; RequiredSize
0x1800055ba  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1800055bd  xor     r8d, r8d; DeviceInterfaceDetailData
0x1800055c0  lea     rdx, [rsp+230h+DeviceInterfaceData]; DeviceInterfaceData
0x1800055c5  mov     rcx, r13; DeviceInfoSet
0x1800055c8  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800055ce  mov     ebx, eax
0x1800055d0  call    cs:__imp_GetLastError
0x1800055d6  mov     r9d, eax
0x1800055d9  test    ebx, ebx
0x1800055db  jnz     loc_1800056BE
0x1800055e1  cmp     eax, 7Ah ; 'z'
0x1800055e4  jnz     loc_1800056BE
0x1800055ea  mov     eax, [rbp+130h+var_198.DevInst]
0x1800055ed  cmp     [rbp+130h+var_178.DevInst], eax
0x1800055f0  jz      short loc_180005611
0x1800055f2  mov     rcx, rdi; Block
0x1800055f5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800055fa  mov     rcx, r12; hObject
0x1800055fd  call    cs:__imp_CloseHandle
0x180005603  xor     edi, edi
0x180005605  inc     esi
0x180005607  mov     rax, [rsp+230h+var_1C0]
0x18000560c  jmp     loc_180005437
0x180005611  mov     [rsp+230h+var_1F0], 0
0x180005619  mov     rdx, r15
0x18000561c  lea     rcx, [rsp+230h+var_1E0]
0x180005621  call    ??A?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAAAEAVDeviceData@@_K@Z; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](unsigned __int64)
0x180005626  mov     rdx, [rax]
0x180005629  lea     rcx, [rdx-18h]
0x18000562d  mov     rsi, [r14]
0x180005630  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180005634  cmp     rcx, rsi
0x180005637  jz      short loc_18000566C
0x180005639  cmp     dword ptr [rsi+10h], 0
0x18000563d  jl      short loc_180005660
0x18000563f  mov     rax, [rsi]
0x180005642  cmp     [rcx], rax
0x180005645  jnz     short loc_180005660
0x180005647  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000564c  mov     rbx, rax
0x18000564f  mov     rcx, rsi; this
0x180005652  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005657  lea     rax, [rbx+18h]
0x18000565b  mov     [r14], rax
0x18000565e  jmp     short loc_18000566C
0x180005660  mov     r8d, [rdx-10h]
0x180005664  mov     rcx, r14
0x180005667  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000566c  mov     rax, cs:WPP_GLOBAL_Control
0x180005673  lea     rdx, WPP_GLOBAL_Control
0x18000567a  cmp     rax, rdx
0x18000567d  jz      loc_18000580F
0x180005683  test    byte ptr [rax+1Ch], 20h
0x180005687  jz      loc_18000580F
0x18000568d  mov     rdx, r15
0x180005690  lea     rcx, [rsp+230h+var_1E0]
0x180005695  call    ??A?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAAAEAVDeviceData@@_K@Z; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](unsigned __int64)
0x18000569a  mov     edx, 3Fh ; '?'
0x18000569f  mov     r9, [rax]
0x1800056a2  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x1800056a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056b0  mov     rcx, [rcx+10h]
0x1800056b4  call    WPP_SF_S
0x1800056b9  jmp     loc_18000580F
0x1800056be  mov     eax, 8000FFFFh
0x1800056c3  mov     [rsp+230h+var_1F0], eax
0x1800056c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056ce  lea     rdx, WPP_GLOBAL_Control
0x1800056d5  cmp     rcx, rdx
0x1800056d8  jz      loc_18000580F
0x1800056de  test    byte ptr [rcx+1Ch], 2
0x1800056e2  jz      loc_18000580F
0x1800056e8  mov     edx, 3Eh ; '>'
0x1800056ed  mov     dword ptr [rsp+230h+RequiredSize], eax
0x1800056f1  mov     rcx, [rcx+10h]
0x1800056f5  call    WPP_SF_Dd
0x1800056fa  jmp     loc_18000580F
0x1800056ff  call    cs:__imp_GetLastError
0x180005705  test    eax, eax
0x180005707  jle     short loc_180005711
0x180005709  movzx   eax, ax
0x18000570c  or      eax, 80070000h
0x180005711  mov     [rsp+230h+var_1F0], eax
0x180005715  mov     rcx, cs:WPP_GLOBAL_Control
0x18000571c  lea     rdx, WPP_GLOBAL_Control
0x180005723  cmp     rcx, rdx
0x180005726  jz      loc_18000580F
0x18000572c  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
