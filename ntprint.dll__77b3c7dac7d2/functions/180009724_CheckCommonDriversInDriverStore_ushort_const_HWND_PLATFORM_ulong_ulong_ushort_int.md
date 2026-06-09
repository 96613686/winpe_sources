# CheckCommonDriversInDriverStore(ushort const *,HWND__ *,PLATFORM,ulong,ulong,ushort * *,int *)

- ea: `0x180009724`
- end: `0x180009a07`
- name: `?CheckCommonDriversInDriverStore@@YAJPEBGPEAUHWND__@@W4PLATFORM@@KKPEAPEAGPEAH@Z`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800093a4`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180009724`
- `0x180009a10`
- `0x18000b11c`
- `0x18000b200`
- `0x18000c870`
- `0x18000d314`
- `0x180012b28`
- `0x180026c04`
- `0x180026ed4`
- `0x1800272bc`
- `0x180036248`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000983d`
- `KERNEL32!lstrcmpiW` at `0x18000983d`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000980e`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000980e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009951`

## pseudocode

```c
__int64 __fastcall CheckCommonDriversInDriverStore(
        const WCHAR *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned __int16 **a6,
        _DWORD *a7)
{
  DWORD v8; // r14d
  int LastErrorAsFailHR; // ebx
  __int64 v10; // r14
  const WCHAR *v11; // rcx
  int v12; // edx
  NCoreLibrary *v13; // rcx
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  int v17; // [rsp+48h] [rbp-B8h]
  HDEVINFO DeviceInfoSet; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpString1; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v24[528]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v21 = a2;
  lpString1 = a1;
  v19 = a4;
  DeviceInfoSet = (HDEVINFO)-1LL;
  memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
  if ( !(unsigned int)ValidPlatform(a3) || !a5 || !a6 || !a7 || *a7 )
    return (unsigned int)-2147024809;
  v8 = 0;
  DriverInfoData.cbSize = 1568;
  v17 = 0;
  LastErrorAsFailHR = CreateAndBuildDriverList(a3, (__int64 *)&DeviceInfoSet);
  if ( LastErrorAsFailHR < 0 )
    goto LABEL_27;
  do
  {
    if ( *a7 || !SetupDiEnumDriverInfoW(DeviceInfoSet, 0, 1u, v8, &DriverInfoData) )
      break;
    v10 = 0;
    while ( (unsigned int)v10 < a5 )
    {
      v11 = a6[v10];
      if ( !v11 || lstrcmpiW(v11, DriverInfoData.Description) )
        goto LABEL_22;
      v16 = 0;
      memset_0(ReturnBuffer, 0, 0x208u);
      if ( (unsigned int)GetDriverStorePathFromDeviceInfo(
                           (int)DeviceInfoSet,
                           v12,
                           (int)&DriverInfoData,
                           a3,
                           (__int64)&v16,
                           ReturnBuffer) )
      {
        LastErrorAsFailHR = 0;
      }
      else
      {
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
        if ( LastErrorAsFailHR < 0 )
          goto LABEL_22;
      }
      if ( v16 )
      {
        if ( (unsigned int)IsLocalMachine(lpString1) )
          goto LABEL_20;
        LastErrorAsFailHR = ObtainLatestVersionFromDriverStore(
                              DeviceInfoSet,
                              a3,
                              &DriverInfoData,
                              (unsigned int)(v17 + 1),
                              ReturnBuffer);
        if ( LastErrorAsFailHR >= 0 )
        {
          memset_0(v24, 0, 0x208u);
          v16 = 260;
          LastErrorAsFailHR = UploadPrinterDriverHelper(ReturnBuffer, lpString1, v21, a3, v19, v24, &v16);
LABEL_20:
          if ( LastErrorAsFailHR >= 0 )
          {
            CoTaskMemFree(a6[v10]);
            a6[v10] = 0;
            *a7 = 0;
            LastErrorAsFailHR = CheckCommonDriversInInf(ReturnBuffer, a3, a5, a6, a7);
          }
        }
      }
LABEL_22:
      v10 = (unsigned int)(v10 + 1);
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_26;
    }
    if ( !*a7 )
      *a7 = FoundAllCommonDrivers(a5, a6);
LABEL_26:
    v8 = v17 + 1;
    DriverInfoData.cbSize = 1568;
    ++v17;
  }
  while ( LastErrorAsFailHR >= 0 );
LABEL_27:
  if ( DeviceInfoSet != (HDEVINFO)-1LL )
    DestroyOnlyPrinterDeviceInfoList(DeviceInfoSet);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180009724  mov     [rsp-8+arg_18], rbx
0x180009729  push    rbp
0x18000972a  push    rdi
0x18000972b  push    r13
0x18000972d  push    r14
0x18000972f  push    r15
0x180009731  lea     rbp, [rsp-9C0h]
0x180009739  sub     rsp, 0AC0h
0x180009740  mov     rax, cs:__security_cookie
0x180009747  xor     rax, rsp
0x18000974a  mov     [rbp+9E0h+var_30], rax
0x180009751  mov     r15, [rbp+9E0h+arg_28]
0x180009758  mov     ebx, r8d
0x18000975b  mov     rdi, [rbp+9E0h+arg_30]
0x180009762  mov     r8d, 61Ch; Size
0x180009768  mov     [rsp+0AE0h+var_A78], rdx
0x18000976d  xor     edx, edx; Val
0x18000976f  mov     [rsp+0AE0h+lpString1], rcx
0x180009774  lea     rcx, [rsp+0AE0h+var_A70.DriverType]; void *
0x180009779  mov     [rsp+0AE0h+var_AA0], ebx
0x18000977d  mov     [rsp+0AE0h+var_A88], r9d
0x180009782  mov     [rsp+0AE0h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x18000978b  call    memset_0
0x180009790  mov     ecx, ebx
0x180009792  call    ValidPlatform
0x180009797  test    eax, eax
0x180009799  jz      loc_1800099D9
0x18000979f  cmp     [rbp+9E0h+arg_20], 0
0x1800097a6  jz      loc_1800099D9
0x1800097ac  test    r15, r15
0x1800097af  jz      loc_1800099D9
0x1800097b5  test    rdi, rdi
0x1800097b8  jz      loc_1800099D9
0x1800097be  cmp     dword ptr [rdi], 0
0x1800097c1  jnz     loc_1800099D9
0x1800097c7  xor     r14d, r14d
0x1800097ca  mov     [rsp+0AE0h+var_A70.cbSize], 620h
0x1800097d2  lea     rdx, [rsp+0AE0h+DeviceInfoSet]
0x1800097d7  mov     dword ptr [rsp+0AE0h+var_A9C+4], r14d
0x1800097dc  mov     ecx, ebx
0x1800097de  call    CreateAndBuildDriverList
0x1800097e3  mov     ebx, eax
0x1800097e5  test    eax, eax
0x1800097e7  js      loc_1800099C5
0x1800097ed  cmp     dword ptr [rdi], 0
0x1800097f0  jnz     loc_1800099C5
0x1800097f6  mov     rcx, [rsp+0AE0h+DeviceInfoSet]; DeviceInfoSet
0x1800097fb  lea     rax, [rsp+0AE0h+var_A70]
0x180009800  xor     edx, edx; DeviceInfoData
0x180009802  mov     [rsp+0AE0h+DriverInfoData], rax; DriverInfoData
0x180009807  mov     r9d, r14d; MemberIndex
0x18000980a  lea     r8d, [rdx+1]; DriverType
0x18000980e  call    cs:__imp_SetupDiEnumDriverInfoW
0x180009814  test    eax, eax
0x180009816  jz      loc_1800099C5
0x18000981c  xor     r14d, r14d
0x18000981f  cmp     r14d, [rbp+9E0h+arg_20]
0x180009826  jnb     loc_180009993
0x18000982c  mov     rcx, [r15+r14*8]; lpString1
0x180009830  test    rcx, rcx
0x180009833  jz      loc_180009986
0x180009839  lea     rdx, [rbp+9E0h+var_A70.Description]; lpString2
0x18000983d  call    cs:__imp_lstrcmpiW
0x180009843  test    eax, eax
0x180009845  jnz     loc_180009986
0x18000984b  xor     edx, edx; Val
0x18000984d  mov     dword ptr [rsp+0AE0h+var_A9C], eax
0x180009851  mov     r8d, 208h; Size
0x180009857  lea     rcx, [rbp+9E0h+var_450]; void *
0x18000985e  call    memset_0
0x180009863  mov     r9d, [rsp+0AE0h+var_AA0]; int
0x180009868  lea     rax, [rbp+9E0h+var_450]
0x18000986f  mov     rcx, [rsp+0AE0h+DeviceInfoSet]; int
0x180009874  lea     r8, [rsp+0AE0h+var_A70]; int
0x180009879  mov     [rsp+0AE0h+ReturnBuffer], rax; ReturnBuffer
0x18000987e  lea     rax, [rsp+0AE0h+var_A9C]
0x180009883  mov     [rsp+0AE0h+DriverInfoData], rax; __int64
0x180009888  call    GetDriverStorePathFromDeviceInfo
0x18000988d  test    eax, eax
0x18000988f  jz      short loc_180009895
0x180009891  xor     ebx, ebx
0x180009893  jmp     short loc_1800098A4
0x180009895  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18000989a  mov     ebx, eax
0x18000989c  test    eax, eax
0x18000989e  js      loc_180009986
0x1800098a4  cmp     dword ptr [rsp+0AE0h+var_A9C], 0
0x1800098a9  jz      loc_180009986
0x1800098af  mov     rcx, [rsp+0AE0h+lpString1]; lpString1
0x1800098b4  call    IsLocalMachine
0x1800098b9  test    eax, eax
0x1800098bb  jnz     loc_180009949
0x1800098c1  mov     r9d, dword ptr [rsp+0AE0h+var_A9C+4]
0x1800098c6  lea     rax, [rbp+9E0h+var_450]
0x1800098cd  mov     edx, [rsp+0AE0h+var_AA0]
0x1800098d1  lea     r8, [rsp+0AE0h+var_A70]
0x1800098d6  mov     rcx, [rsp+0AE0h+DeviceInfoSet]
0x1800098db  inc     r9d
0x1800098de  mov     [rsp+0AE0h+DriverInfoData], rax
0x1800098e3  call    ?ObtainLatestVersionFromDriverStore@@YAJPEAXW4PLATFORM@@PEAU_SP_DRVINFO_DATA_V2_W@@KPEAG@Z; ObtainLatestVersionFromDriverStore(void *,PLATFORM,_SP_DRVINFO_DATA_V2_W *,ulong,ushort *)
0x1800098e8  mov     ebx, eax
0x1800098ea  test    eax, eax
0x1800098ec  js      loc_180009986
0x1800098f2  xor     edx, edx; Val
0x1800098f4  lea     rcx, [rbp+9E0h+var_240]; void *
0x1800098fb  mov     r8d, 208h; Size
0x180009901  call    memset_0
0x180009906  mov     r9d, [rsp+0AE0h+var_AA0]
0x18000990b  lea     rax, [rsp+0AE0h+var_A9C]
0x180009910  mov     r8, [rsp+0AE0h+var_A78]
0x180009915  lea     rcx, [rbp+9E0h+var_450]
0x18000991c  mov     rdx, [rsp+0AE0h+lpString1]
0x180009921  mov     [rsp+0AE0h+var_AB0], rax
0x180009926  lea     rax, [rbp+9E0h+var_240]
0x18000992d  mov     [rsp+0AE0h+ReturnBuffer], rax
0x180009932  mov     eax, [rsp+0AE0h+var_A88]
0x180009936  mov     dword ptr [rsp+0AE0h+DriverInfoData], eax
0x18000993a  mov     dword ptr [rsp+0AE0h+var_A9C], 104h
0x180009942  call    ?UploadPrinterDriverHelper@@YAJPEAGPEBGPEAUHWND__@@W4PLATFORM@@K0PEAK@Z; UploadPrinterDriverHelper(ushort *,ushort const *,HWND__ *,PLATFORM,ulong,ushort *,ulong *)
0x180009947  mov     ebx, eax
0x180009949  test    ebx, ebx
0x18000994b  js      short loc_180009986
0x18000994d  mov     rcx, [r15+r14*8]; pv
0x180009951  call    cs:__imp_CoTaskMemFree
0x180009957  mov     r8d, [rbp+9E0h+arg_20]
0x18000995e  lea     rcx, [rbp+9E0h+var_450]
0x180009965  mov     edx, [rsp+0AE0h+var_AA0]
0x180009969  mov     r9, r15
0x18000996c  mov     qword ptr [r15+r14*8], 0
0x180009974  mov     dword ptr [rdi], 0
0x18000997a  mov     [rsp+0AE0h+DriverInfoData], rdi
0x18000997f  call    ?CheckCommonDriversInInf@@YAJPEBGW4PLATFORM@@KPEAPEAGPEAH@Z; CheckCommonDriversInInf(ushort const *,PLATFORM,ulong,ushort * *,int *)
0x180009984  mov     ebx, eax
0x180009986  inc     r14d
0x180009989  test    ebx, ebx
0x18000998b  jns     loc_18000981F
0x180009991  jmp     short loc_1800099A8
0x180009993  cmp     dword ptr [rdi], 0
0x180009996  jnz     short loc_1800099A8
0x180009998  mov     ecx, [rbp+9E0h+arg_20]; unsigned int
0x18000999e  mov     rdx, r15; unsigned __int16 **
0x1800099a1  call    ?FoundAllCommonDrivers@@YAHKPEAPEAG@Z; FoundAllCommonDrivers(ulong,ushort * *)
0x1800099a6  mov     [rdi], eax
0x1800099a8  mov     r14d, dword ptr [rsp+0AE0h+var_A9C+4]
0x1800099ad  inc     r14d
0x1800099b0  mov     [rsp+0AE0h+var_A70.cbSize], 620h
0x1800099b8  mov     dword ptr [rsp+0AE0h+var_A9C+4], r14d
0x1800099bd  test    ebx, ebx
0x1800099bf  jns     loc_1800097ED
0x1800099c5  cmp     [rsp+0AE0h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x1800099cb  jz      short loc_1800099DE
0x1800099cd  mov     rcx, [rsp+0AE0h+DeviceInfoSet]
0x1800099d2  call    DestroyOnlyPrinterDeviceInfoList
0x1800099d7  jmp     short loc_1800099DE
0x1800099d9  mov     ebx, 80070057h
0x1800099de  mov     eax, ebx
0x1800099e0  mov     rcx, [rbp+9E0h+var_30]
0x1800099e7  xor     rcx, rsp; StackCookie
0x1800099ea  call    __security_check_cookie
0x1800099ef  mov     rbx, [rsp+0AE0h+arg_18]
0x1800099f7  add     rsp, 0AC0h
0x1800099fe  pop     r15
0x180009a00  pop     r14
0x180009a02  pop     r13
0x180009a04  pop     rdi
0x180009a05  pop     rbp
0x180009a06  retn
```
