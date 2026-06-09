# CheckDeviceInterface(DRIVE_TARGET *,void *,HKEY__ *,_DO_DEVINFO_DATA *)

- ea: `0x14000abe4`
- end: `0x14000b1fd`
- name: `?CheckDeviceInterface@@YAJPEAUDRIVE_TARGET@@PEAXPEAUHKEY__@@PEAU_DO_DEVINFO_DATA@@@Z`
- size: `1561`
- prototype: `int(struct DRIVE_TARGET *, void *, HKEY, struct _DO_DEVINFO_DATA *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14000b77c`
- `0x14000bb78`

## callees

- `0x1400028f4`
- `0x140004b1c`
- `0x140005750`
- `0x140008c9c`
- `0x14000a640`
- `0x14000a6c0`
- `0x14000abe4`
- `0x14000b2f0`
- `0x14000b528`
- `0x14000c864`
- `0x14000c944`
- `0x14000ca2c`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b161`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14000b081`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x14000b081`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000b157`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000b157`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ae7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ae7b`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x14000ac70`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x14000ac70`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x14000acd6`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x14000acd6`

## pseudocode

```c
__int64 __fastcall CheckDeviceInterface(struct DRIVE_TARGET *a1, void *a2, HKEY a3, struct _DO_DEVINFO_DATA *a4)
{
  WCHAR *v7; // r14
  signed int v8; // eax
  unsigned int VolumeUniqueId; // edi
  int VolumeDeviceName; // eax
  void *v11; // r15
  unsigned int CurrentThreadActivityIdPrefix; // eax
  PVOID *v13; // rdx
  char v14; // bl
  unsigned int v15; // eax
  LSTATUS v16; // eax
  unsigned __int16 v17; // bx
  int v18; // r10d
  unsigned __int16 i; // cx
  unsigned __int64 v20; // rdi
  int *v21; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // eax
  signed int v25; // eax
  __int64 v26; // r11
  signed int LastError; // eax
  char v28; // bl
  unsigned int v29; // eax
  int v30; // edx
  int v31; // r8d
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  char v35[4]; // [rsp+44h] [rbp-BCh] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCWSTR lpValueName; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD Type[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SourceString[264]; // [rsp+70h] [rbp-90h] BYREF

  *(_DWORD *)Data = 23;
  v37 = 0;
  lpValueName = 0;
  v40 = 0;
  *(_DWORD *)v35 = 0;
  *(_QWORD *)Type = 0;
  cbData = 0;
  v7 = 0;
  if ( (unsigned int)DevObjGetDeviceRegistryProperty(a2, a4, 14, 0, SourceString, 520, &v37) )
  {
    v39 = 7;
    *(_DWORD *)v35 = 0;
    if ( (unsigned int)DevObjGetDeviceProperty(a2, a4, &DEVPKEY_Device_SessionId, &v39, v35, 4, &v37, 0) )
    {
      VolumeDeviceName = GetVolumeDeviceName(SourceString, (unsigned __int16 **)Type, (int *)&cbData);
      v11 = *(void **)Type;
      VolumeUniqueId = VolumeDeviceName;
      if ( VolumeDeviceName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpcbData) = VolumeUniqueId;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"GetVolumeDeviceName",
            lpcbData);
        }
LABEL_73:
        if ( v11 )
          operator delete(v11);
        return VolumeUniqueId;
      }
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v14 = v35[0];
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)SourceString, (__int64)v11, v14);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( a3 )
      {
        VolumeUniqueId = GetVolumeUniqueId(SourceString, (unsigned __int16 **)&lpValueName, &v40);
        if ( (VolumeUniqueId & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(lpcbData) = VolumeUniqueId;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
              v15,
              (__int64)"GetVolumeUniqueId",
              lpcbData);
          }
          v7 = (WCHAR *)lpValueName;
LABEL_71:
          if ( v7 )
            operator delete(v7);
          goto LABEL_73;
        }
        v7 = (WCHAR *)lpValueName;
        Type[0] = 4;
        *(_DWORD *)Data = 23;
        cbData = 4;
        v16 = RegQueryValueExW(a3, lpValueName, 0, Type, Data, &cbData);
        VolumeUniqueId = v16;
        if ( (v16 & 0xFFFFFFFD) != 0 )
        {
          if ( v16 > 0 )
            VolumeUniqueId = (unsigned __int16)v16 | 0x80070000;
          goto LABEL_71;
        }
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      v17 = 23;
      v18 = 0;
      for ( i = 0; i < 0x17u; ++i )
      {
        v20 = 524LL * i;
        v21 = &dword_140088AA4[v20 / 4];
        do
        {
          v22 = *(unsigned __int16 *)((char *)v21 + (_BYTE *)v11 - (_BYTE *)&dword_140088AA4[v20 / 4]);
          v23 = *(unsigned __int16 *)v21 - v22;
          if ( v23 )
            break;
          v21 = (int *)((char *)v21 + 2);
        }
        while ( v22 );
        if ( !v23 )
        {
          *(DWORD *)((char *)Type + 2) = 58;
          LOWORD(Type[0]) = i + 68;
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          {
            RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11, (__int64)Type);
          }
          if ( !*(_DWORD *)((char *)&g_Targets + v20) )
            *(_DWORD *)((char *)&g_Targets + v20) = *(_DWORD *)v35;
LABEL_47:
          VolumeUniqueId = -2147023728;
          goto LABEL_71;
        }
        if ( !v18 && !*(_WORD *)((char *)&g_Targets + v20 + 4) )
        {
          v17 = i;
          v18 = 1;
        }
      }
      VolumeUniqueId = 0;
      if ( !v18 )
      {
        if ( i == 23 && v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
            v24,
            (__int64)&dword_140088AA4[131 * v17]);
        }
        goto LABEL_47;
      }
      if ( !*((_WORD *)&g_Targets + 262 * v17 + 2) )
      {
        if ( *(_DWORD *)Data < 0x17u && !*((_WORD *)&g_Targets + 262 * *(unsigned int *)Data + 2) )
          v17 = *(_WORD *)Data;
        *(DWORD *)((char *)Type + 2) = 58;
        LOWORD(Type[0]) = v17 + 68;
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11, (__int64)Type);
        }
        if ( DefineDosDeviceW(1u, (LPCWSTR)Type, (LPCWSTR)v11) )
        {
          StringCchCopyW((unsigned __int16 *)&dword_140088AA4[131 * v17], 0x104u, (const unsigned __int16 *)v11);
          *(_DWORD *)((char *)&g_Targets + v26) = *(_DWORD *)v35;
          if ( a3 )
          {
            cbData = v17;
            if ( RegSetValueExW(a3, v7, 0, 4u, (const BYTE *)&cbData, 4u) )
            {
              LastError = GetLastError();
              VolumeUniqueId = LastError;
              if ( LastError > 0 )
                VolumeUniqueId = (unsigned __int16)LastError | 0x80070000;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v28 = cbData;
                v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DSdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v29, (__int64)v7, v28, VolumeUniqueId);
              }
            }
          }
        }
        else
        {
          v25 = GetLastError();
          VolumeUniqueId = v25;
          if ( v25 > 0 )
            VolumeUniqueId = (unsigned __int16)v25 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)Type, (__int64)v11, VolumeUniqueId);
          }
        }
      }
      goto LABEL_71;
    }
  }
  v8 = GetLastError();
  VolumeUniqueId = v8;
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return VolumeUniqueId;
}

```

## disassembly

```asm
0x14000abe4  mov     [rsp-8+arg_0], rbx
0x14000abe9  push    rbp
0x14000abea  push    rsi
0x14000abeb  push    rdi
0x14000abec  push    r12
0x14000abee  push    r13
0x14000abf0  push    r14
0x14000abf2  push    r15
0x14000abf4  lea     rbp, [rsp-190h]
0x14000abfc  sub     rsp, 290h
0x14000ac03  mov     rax, cs:__security_cookie
0x14000ac0a  xor     rax, rsp
0x14000ac0d  mov     [rbp+1C0h+var_40], rax
0x14000ac14  xor     esi, esi
0x14000ac16  mov     dword ptr [rsp+2C0h+Data], 17h
0x14000ac1e  mov     rdi, r9
0x14000ac21  mov     [rsp+2C0h+var_274], esi
0x14000ac25  mov     rbx, rdx
0x14000ac28  mov     [rsp+2C0h+lpValueName], rsi
0x14000ac2d  lea     rax, [rsp+2C0h+var_274]
0x14000ac32  mov     [rsp+2C0h+var_264], esi
0x14000ac36  mov     qword ptr [rsp+2C0h+var_290], rax
0x14000ac3b  lea     r12d, [rsi+0Eh]
0x14000ac3f  mov     r13, r8
0x14000ac42  mov     dword ptr [rsp+2C0h+lpcbData], 208h
0x14000ac4a  lea     rax, [rsp+2C0h+SourceString]
0x14000ac4f  mov     dword ptr [rsp+2C0h+var_27C], esi
0x14000ac53  mov     r8d, r12d
0x14000ac56  mov     qword ptr [rsp+2C0h+Type], rsi
0x14000ac5b  xor     r9d, r9d
0x14000ac5e  mov     [rsp+2C0h+cbData], esi
0x14000ac62  mov     rdx, rdi
0x14000ac65  mov     [rsp+2C0h+lpData], rax
0x14000ac6a  mov     rcx, rbx
0x14000ac6d  mov     r14d, esi
0x14000ac70  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x14000ac76  test    eax, eax
0x14000ac78  jnz     short loc_14000AC98
0x14000ac7a  call    cs:__imp_GetLastError
0x14000ac80  mov     edi, eax
0x14000ac82  test    eax, eax
0x14000ac84  jle     loc_14000B1D1
0x14000ac8a  movzx   edi, ax
0x14000ac8d  or      edi, 80070000h
0x14000ac93  jmp     loc_14000B1D1
0x14000ac98  mov     [rsp+2C0h+var_288], esi
0x14000ac9c  lea     rax, [rsp+2C0h+var_274]
0x14000aca1  mov     qword ptr [rsp+2C0h+var_290], rax
0x14000aca6  lea     r9, [rsp+2C0h+var_268]
0x14000acab  lea     rax, [rsp+2C0h+var_27C]
0x14000acb0  mov     dword ptr [rsp+2C0h+lpcbData], 4
0x14000acb8  lea     r8, DEVPKEY_Device_SessionId
0x14000acbf  mov     [rsp+2C0h+lpData], rax
0x14000acc4  mov     rdx, rdi
0x14000acc7  mov     [rsp+2C0h+var_268], 7
0x14000accf  mov     rcx, rbx
0x14000acd2  mov     dword ptr [rsp+2C0h+var_27C], esi
0x14000acd6  call    cs:__imp_DevObjGetDeviceProperty
0x14000acdc  test    eax, eax
0x14000acde  jz      short loc_14000AC7A
0x14000ace0  lea     r8, [rsp+2C0h+cbData]; int *
0x14000ace5  lea     rdx, [rsp+2C0h+Type]; unsigned __int16 **
0x14000acea  lea     rcx, [rsp+2C0h+SourceString]; SourceString
0x14000acef  call    ?GetVolumeDeviceName@@YAJPEBGPEAPEAGPEAJ@Z; GetVolumeDeviceName(ushort const *,ushort * *,long *)
0x14000acf4  mov     r15, qword ptr [rsp+2C0h+Type]
0x14000acf9  mov     edi, eax
0x14000acfb  test    eax, eax
0x14000acfd  jns     short loc_14000AD61
0x14000acff  mov     rax, cs:WPP_GLOBAL_Control
0x14000ad06  lea     rsi, WPP_GLOBAL_Control
0x14000ad0d  cmp     rax, rsi
0x14000ad10  jz      loc_14000B1C4
0x14000ad16  test    byte ptr [rax+1Ch], 8
0x14000ad1a  jz      loc_14000B1C4
0x14000ad20  cmp     byte ptr [rax+19h], 2
0x14000ad24  jb      loc_14000B1C4
0x14000ad2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ad2f  lea     rcx, aGetvolumedevic; "GetVolumeDeviceName"
0x14000ad36  mov     dword ptr [rsp+2C0h+lpcbData], edi
0x14000ad3a  mov     [rsp+2C0h+lpData], rcx
0x14000ad3f  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000ad46  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad4d  mov     edx, r12d
0x14000ad50  mov     r9d, eax
0x14000ad53  mov     rcx, [rcx+10h]
0x14000ad57  call    WPP_SF_DsD
0x14000ad5c  jmp     loc_14000B1C4
0x14000ad61  mov     rdx, cs:WPP_GLOBAL_Control
0x14000ad68  lea     rsi, WPP_GLOBAL_Control
0x14000ad6f  lea     r12, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000ad76  cmp     rdx, rsi
0x14000ad79  jz      short loc_14000ADC5
0x14000ad7b  test    byte ptr [rdx+1Ch], 1
0x14000ad7f  jz      short loc_14000ADC5
0x14000ad81  cmp     byte ptr [rdx+19h], 4
0x14000ad85  jb      short loc_14000ADC5
0x14000ad87  mov     ebx, dword ptr [rsp+2C0h+var_27C]
0x14000ad8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ad90  lea     rcx, [rsp+2C0h+SourceString]
0x14000ad95  mov     dword ptr [rsp+2C0h+var_290], ebx; char
0x14000ad99  mov     [rsp+2C0h+lpcbData], r15; __int64
0x14000ad9e  mov     edx, 0Fh
0x14000ada3  mov     [rsp+2C0h+lpData], rcx; __int64
0x14000ada8  mov     r9d, eax
0x14000adab  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adb2  mov     r8, r12
0x14000adb5  mov     rcx, [rcx+10h]; LoggerHandle
0x14000adb9  call    WPP_SF_DSSd
0x14000adbe  mov     rdx, cs:WPP_GLOBAL_Control
0x14000adc5  xor     edi, edi
0x14000adc7  test    r13, r13
0x14000adca  jz      loc_14000AEA9
0x14000add0  lea     r8, [rsp+2C0h+var_264]; unsigned int *
0x14000add5  lea     rdx, [rsp+2C0h+lpValueName]; unsigned __int16 **
0x14000adda  lea     rcx, [rsp+2C0h+SourceString]; SourceString
0x14000addf  call    ?GetVolumeUniqueId@@YAJPEBGPEAPEAGPEAK@Z; GetVolumeUniqueId(ushort const *,ushort * *,ulong *)
0x14000ade4  mov     edi, eax
0x14000ade6  test    eax, eax
0x14000ade8  jns     short loc_14000AE3C
0x14000adea  mov     rax, cs:WPP_GLOBAL_Control
0x14000adf1  cmp     rax, rsi
0x14000adf4  jz      short loc_14000AE32
0x14000adf6  test    byte ptr [rax+1Ch], 8
0x14000adfa  jz      short loc_14000AE32
0x14000adfc  cmp     byte ptr [rax+19h], 2
0x14000ae00  jb      short loc_14000AE32
0x14000ae02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ae07  lea     rcx, aGetvolumeuniqu; "GetVolumeUniqueId"
0x14000ae0e  mov     dword ptr [rsp+2C0h+lpcbData], edi
0x14000ae12  mov     [rsp+2C0h+lpData], rcx
0x14000ae17  mov     edx, 10h
0x14000ae1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae23  mov     r9d, eax
0x14000ae26  mov     r8, r12
0x14000ae29  mov     rcx, [rcx+10h]
0x14000ae2d  call    WPP_SF_DsD
0x14000ae32  mov     r14, [rsp+2C0h+lpValueName]
0x14000ae37  jmp     loc_14000B1B7
0x14000ae3c  mov     r14, [rsp+2C0h+lpValueName]
0x14000ae41  lea     rax, [rsp+2C0h+cbData]
0x14000ae46  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x14000ae4b  lea     r9, [rsp+2C0h+Type]; lpType
0x14000ae50  lea     rax, [rsp+2C0h+Data]
0x14000ae55  mov     [rsp+2C0h+Type], 4
0x14000ae5d  xor     r8d, r8d; lpReserved
0x14000ae60  mov     [rsp+2C0h+lpData], rax; lpData
0x14000ae65  mov     rdx, r14; lpValueName
0x14000ae68  mov     dword ptr [rsp+2C0h+Data], 17h
0x14000ae70  mov     rcx, r13; hKey
0x14000ae73  mov     [rsp+2C0h+cbData], 4
0x14000ae7b  call    cs:__imp_RegQueryValueExW
0x14000ae81  mov     edi, eax
0x14000ae83  test    eax, 0FFFFFFFDh
0x14000ae88  jz      short loc_14000AEA0
0x14000ae8a  test    eax, eax
0x14000ae8c  jle     loc_14000B1B7
0x14000ae92  movzx   edi, ax
0x14000ae95  or      edi, 80070000h
0x14000ae9b  jmp     loc_14000B1B7
0x14000aea0  mov     rdx, cs:WPP_GLOBAL_Control
0x14000aea7  xor     edi, edi
0x14000aea9  mov     eax, 17h
0x14000aeae  lea     r11, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000aeb5  movzx   ebx, ax
0x14000aeb8  mov     r10d, edi
0x14000aebb  mov     ecx, edi
0x14000aebd  lea     r9d, [rax-16h]
0x14000aec1  cmp     cx, ax
0x14000aec4  jnb     loc_14000AF8F
0x14000aeca  movzx   eax, cx
0x14000aecd  imul    rdi, rax, 20Ch
0x14000aed4  lea     rax, [r11+4]
0x14000aed8  mov     r11, r15
0x14000aedb  add     rax, rdi
0x14000aede  sub     r11, rax
0x14000aee1  movzx   r9d, word ptr [rax]
0x14000aee5  movzx   r8d, word ptr [rax+r11]
0x14000aeea  sub     r9d, r8d
0x14000aeed  jnz     short loc_14000AEF8
0x14000aeef  add     rax, 2
0x14000aef3  test    r8d, r8d
0x14000aef6  jnz     short loc_14000AEE1
0x14000aef8  xor     eax, eax
0x14000aefa  test    r9d, r9d
0x14000aefd  jz      short loc_14000AF28
0x14000aeff  lea     r11, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000af06  lea     r9d, [rax+1]
0x14000af0a  test    r10d, r10d
0x14000af0d  jnz     short loc_14000AF1D
0x14000af0f  cmp     [rdi+r11+4], ax
0x14000af15  jnz     short loc_14000AF1D
0x14000af17  movzx   ebx, cx
0x14000af1a  mov     r10d, r9d
0x14000af1d  add     cx, r9w
0x14000af21  mov     eax, 17h
0x14000af26  jmp     short loc_14000AEC1
0x14000af28  add     cx, 44h ; 'D'
0x14000af2c  mov     [rsp+2C0h+Type+2], 3Ah ; ':'
0x14000af34  mov     word ptr [rsp+2C0h+Type], cx
0x14000af39  cmp     rdx, rsi
0x14000af3c  jz      short loc_14000AF79
0x14000af3e  test    byte ptr [rdx+1Ch], 1
0x14000af42  jz      short loc_14000AF79
0x14000af44  cmp     byte ptr [rdx+19h], 4
0x14000af48  jb      short loc_14000AF79
0x14000af4a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000af4f  lea     rcx, [rsp+2C0h+Type]
0x14000af54  mov     edx, 11h
0x14000af59  mov     [rsp+2C0h+lpcbData], rcx; __int64
0x14000af5e  mov     r9d, eax
0x14000af61  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af68  mov     r8, r12
0x14000af6b  mov     [rsp+2C0h+lpData], r15; __int64
0x14000af70  mov     rcx, [rcx+10h]; LoggerHandle
0x14000af74  call    WPP_SF_DSS
0x14000af79  lea     rcx, ?g_Targets@@3PAUDRIVE_TARGET@@A; DRIVE_TARGET near * g_Targets
0x14000af80  cmp     dword ptr [rdi+rcx], 0
0x14000af84  jnz     short loc_14000AFE3
0x14000af86  mov     eax, dword ptr [rsp+2C0h+var_27C]
0x14000af8a  mov     [rdi+rcx], eax
0x14000af8d  jmp     short loc_14000AFE3
0x14000af8f  xor     edi, edi
0x14000af91  test    r10d, r10d
0x14000af94  jnz     short loc_14000AFED
0x14000af96  cmp     cx, ax
0x14000af99  jnz     short loc_14000AFE3
0x14000af9b  cmp     rdx, rsi
0x14000af9e  jz      short loc_14000AFE3
0x14000afa0  test    [rdx+1Ch], r9b
0x14000afa4  jz      short loc_14000AFE3
0x14000afa6  cmp     byte ptr [rdx+19h], 2
0x14000afaa  jb      short loc_14000AFE3
0x14000afac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000afb1  movzx   ecx, bx
0x14000afb4  lea     edx, [rdi+12h]
0x14000afb7  imul    r8, rcx, 20Ch
0x14000afbe  lea     rcx, dword_140088AA4
0x14000afc5  mov     r9d, eax
0x14000afc8  add     r8, rcx
0x14000afcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afd2  mov     [rsp+2C0h+lpData], r8
0x14000afd7  mov     r8, r12
0x14000afda  mov     rcx, [rcx+10h]
0x14000afde  call    WPP_SF_DS
0x14000afe3  mov     edi, 80070490h
0x14000afe8  jmp     loc_14000B1B7
0x14000afed  movzx   eax, bx
0x14000aff0  imul    rcx, rax, 20Ch
0x14000aff7  cmp     [rcx+r11+4], di
0x14000affd  jnz     loc_14000B1B7
0x14000b003  mov     r8d, dword ptr [rsp+2C0h+Data]
0x14000b008  cmp     r8d, 17h
0x14000b00c  jnb     short loc_14000B020
0x14000b00e  imul    rcx, r8, 20Ch
0x14000b015  cmp     [rcx+r11+4], di
0x14000b01b  cmovz   bx, r8w
0x14000b020  lea     eax, [rbx+44h]
0x14000b023  mov     [rsp+2C0h+Type+2], 3Ah ; ':'
0x14000b02b  mov     word ptr [rsp+2C0h+Type], ax
0x14000b030  cmp     rdx, rsi
0x14000b033  jz      short loc_14000B070
0x14000b035  test    [rdx+1Ch], r9b
0x14000b039  jz      short loc_14000B070
0x14000b03b  cmp     byte ptr [rdx+19h], 4
0x14000b03f  jb      short loc_14000B070
0x14000b041  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000b046  lea     rcx, [rsp+2C0h+Type]
0x14000b04b  mov     edx, 13h
0x14000b050  mov     [rsp+2C0h+lpcbData], rcx; __int64
0x14000b055  mov     r9d, eax
0x14000b058  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b05f  mov     r8, r12
0x14000b062  mov     [rsp+2C0h+lpData], r15; __int64
0x14000b067  mov     rcx, [rcx+10h]; LoggerHandle
0x14000b06b  call    WPP_SF_DSS
0x14000b070  mov     r12d, 1
0x14000b076  lea     rdx, [rsp+2C0h+Type]; lpDeviceName
0x14000b07b  mov     ecx, r12d; dwFlags
0x14000b07e  mov     r8, r15; lpTargetPath
0x14000b081  call    cs:__imp_DefineDosDeviceW
0x14000b087  test    eax, eax
0x14000b089  jnz     short loc_14000B0F4
0x14000b08b  call    cs:__imp_GetLastError
0x14000b091  mov     edi, eax
0x14000b093  test    eax, eax
0x14000b095  jle     short loc_14000B0A0
0x14000b097  movzx   edi, ax
0x14000b09a  or      edi, 80070000h
0x14000b0a0  mov     rax, cs:WPP_GLOBAL_Control
0x14000b0a7  cmp     rax, rsi
0x14000b0aa  jz      loc_14000B1B7
0x14000b0b0  test    [rax+1Ch], r12b
0x14000b0b4  jz      loc_14000B1B7
0x14000b0ba  cmp     byte ptr [rax+19h], 2
0x14000b0be  jb      loc_14000B1B7
0x14000b0c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000b0c9  lea     rcx, [rsp+2C0h+Type]
0x14000b0ce  mov     dword ptr [rsp+2C0h+var_290], edi; char
0x14000b0d2  mov     [rsp+2C0h+lpcbData], r15; __int64
0x14000b0d7  mov     r9d, eax
  ... truncated ...
```
