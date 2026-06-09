# AllInboxCoreDriversInLocalDriverStore

- ea: `0x18001b648`
- end: `0x18001b9d1`
- name: `AllInboxCoreDriversInLocalDriverStore`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000b7ec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180012b28`
- `0x1800180f0`
- `0x18001b320`
- `0x18001b648`
- `0x18001bc44`
- `0x18001bf74`
- `0x180020330`
- `0x180026c04`
- `0x180026ed4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b98a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b98a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b712`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b730`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b712`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b730`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001b7b3`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b960`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001b75a`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001b75a`

## pseudocode

```c
__int64 __fastcall AllInboxCoreDriversInLocalDriverStore(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        FILETIME a4,
        DWORDLONG a5,
        const WCHAR *a6,
        int *a7,
        __int64 *a8)
{
  __int64 v10; // r13
  int v12; // esi
  LPOLESTR *v13; // r12
  __int64 v14; // r14
  HRESULT v15; // eax
  signed int v16; // edi
  DWORD v17; // r14d
  __int64 i; // r14
  _DWORD *v19; // r13
  PCWSTR v20; // r14
  int v21; // eax
  __int64 *v22; // r14
  __int64 v23; // rax
  __int64 v24; // rbx
  LPOLESTR v25; // rcx
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-ACh]
  HDEVINFO DeviceInfoSet; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  int v32[2]; // [rsp+68h] [rbp-98h]
  __int64 *v33; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h]
  PCWSTR Section; // [rsp+80h] [rbp-80h]
  int *v36; // [rsp+88h] [rbp-78h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v38[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v10 = -1;
  *(_QWORD *)v32 = a3;
  v28 = a1;
  Section = a6;
  v36 = a7;
  v33 = a8;
  DeviceInfoSet = (HDEVINFO)-1LL;
  memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
  v12 = 0;
  if ( !(unsigned int)ValidPlatform(v28) || !a2 || !a3 || !a7 )
    return (unsigned int)-2147024809;
  DriverInfoData.cbSize = 1568;
  *a7 = 0;
  if ( a8 )
    *a8 = 0;
  hMem = LocalAlloc(0x40u, 4 * a2);
  if ( !hMem )
    return (unsigned int)-2147024882;
  v13 = (LPOLESTR *)LocalAlloc(0x40u, 8 * a2);
  if ( !v13 )
  {
    v16 = -2147024882;
    goto LABEL_45;
  }
  v14 = 0;
  while ( (unsigned int)v14 < a2 )
  {
    v15 = StringFromIID((const IID *const)(*(_QWORD *)v32 + 16LL * (unsigned int)v14), &v13[v14]);
    v14 = (unsigned int)(v14 + 1);
    v16 = v15;
    if ( v15 < 0 )
      goto LABEL_39;
  }
  v17 = 0;
  v31 = 0;
  v16 = CreateAndBuildDriverList(v28, (__int64 *)&DeviceInfoSet);
  if ( v16 < 0 )
    goto LABEL_38;
  do
  {
    if ( v12 )
      goto LABEL_37;
    v10 = (__int64)DeviceInfoSet;
    if ( !SetupDiEnumDriverInfoW(DeviceInfoSet, 0, 1u, v17, &DriverInfoData) )
      goto LABEL_36;
    memset_0(v38, 0, 0x208u);
    v12 = 1;
    v27 = 1;
    for ( i = 0; ; i = (unsigned int)(v30 + 1) )
    {
      v30 = i;
      if ( v16 < 0 || (unsigned int)i >= a2 )
        break;
      v19 = (char *)hMem + 4 * i;
      if ( !*v19 )
      {
        if ( (unsigned int)IsInboxCorePrinterDriver(v13[i]) )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))DriverFoundInDriverStore)(
                  DeviceInfoSet,
                  v13[i],
                  v28,
                  a4,
                  a5,
                  &DriverInfoData,
                  v38,
                  260,
                  v19);
          if ( v16 >= 0 )
          {
            if ( *v19 )
            {
              v20 = Section;
              if ( Section )
              {
                v12 = VerifyLegacyNeedsDependencies(Section, v38);
                v27 = v12;
              }
              else
              {
                v21 = CheckCoreDriversInInf((__int64)v38, v28, a2, *(__int64 *)v32, a4, a5, &v27);
                v12 = v27;
                v16 = v21;
                if ( v21 < 0 )
                  continue;
              }
              if ( v12 )
              {
                v22 = v33;
                if ( v33 )
                {
                  v23 = AllocStr(v38);
                  *v22 = v23;
                  v16 = v23 == 0 ? 0x8007000E : 0;
                }
                break;
              }
              if ( v20 || v33 )
              {
                *v19 = 0;
                break;
              }
            }
            else
            {
              v12 = 0;
              v27 = 0;
            }
          }
        }
      }
    }
    v17 = v31 + 1;
    DriverInfoData.cbSize = 1568;
    ++v31;
  }
  while ( v16 >= 0 );
  v10 = (__int64)DeviceInfoSet;
LABEL_36:
  if ( v16 >= 0 )
  {
LABEL_37:
    *v36 = v12;
LABEL_38:
    v10 = (__int64)DeviceInfoSet;
  }
LABEL_39:
  v24 = 0;
  do
  {
    v25 = v13[v24];
    if ( v25 )
    {
      CoTaskMemFree(v25);
      v13[v24] = 0;
    }
    v24 = (unsigned int)(v24 + 1);
  }
  while ( (unsigned int)v24 < a2 );
  LocalFree(v13);
LABEL_45:
  LocalFree(hMem);
  if ( v10 != -1 )
    DestroyOnlyPrinterDeviceInfoList(v10);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001b648  push    rbp
0x18001b64a  push    rbx
0x18001b64b  push    rsi
0x18001b64c  push    rdi
0x18001b64d  push    r12
0x18001b64f  push    r13
0x18001b651  push    r14
0x18001b653  push    r15
0x18001b655  lea     rbp, [rsp-7D8h]
0x18001b65d  sub     rsp, 8D8h
0x18001b664  mov     rax, cs:__security_cookie
0x18001b66b  xor     rax, rsp
0x18001b66e  mov     [rbp+810h+var_50], rax
0x18001b675  mov     rax, [rbp+810h+arg_28]
0x18001b67c  mov     r12, r8
0x18001b67f  mov     r14, [rbp+810h+arg_30]
0x18001b686  mov     r15d, edx
0x18001b689  mov     rdi, [rbp+810h+arg_38]
0x18001b690  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001b694  mov     qword ptr [rsp+910h+var_8A8], r8
0x18001b699  xor     edx, edx; Val
0x18001b69b  mov     dword ptr [rsp+910h+var_8C0+4], ecx
0x18001b69f  mov     r8d, 61Ch; Size
0x18001b6a5  lea     rcx, [rbp+810h+var_880.DriverType]; void *
0x18001b6a9  mov     [rbp+810h+Section], rax
0x18001b6ad  mov     [rbp+810h+var_888], r14
0x18001b6b1  mov     rbx, r9
0x18001b6b4  mov     [rsp+910h+var_8A0], rdi
0x18001b6b9  mov     [rsp+910h+DeviceInfoSet], r13
0x18001b6be  call    memset_0
0x18001b6c3  mov     ecx, dword ptr [rsp+910h+var_8C0+4]
0x18001b6c7  xor     esi, esi
0x18001b6c9  call    ValidPlatform
0x18001b6ce  test    eax, eax
0x18001b6d0  jz      loc_18001B9A7
0x18001b6d6  test    r15d, r15d
0x18001b6d9  jz      loc_18001B9A7
0x18001b6df  test    r12, r12
0x18001b6e2  jz      loc_18001B9A7
0x18001b6e8  test    r14, r14
0x18001b6eb  jz      loc_18001B9A7
0x18001b6f1  mov     [rbp+810h+var_880.cbSize], 620h
0x18001b6f8  mov     [r14], esi
0x18001b6fb  test    rdi, rdi
0x18001b6fe  jz      short loc_18001B703
0x18001b700  mov     [rdi], rsi
0x18001b703  mov     edi, 40h ; '@'
0x18001b708  lea     edx, ds:0[r15*4]; uBytes
0x18001b710  mov     ecx, edi; uFlags
0x18001b712  call    cs:__imp_LocalAlloc
0x18001b718  mov     [rsp+910h+hMem], rax
0x18001b71d  test    rax, rax
0x18001b720  jz      loc_18001B9A0
0x18001b726  lea     edx, ds:0[r15*8]; uBytes
0x18001b72e  mov     ecx, edi; uFlags
0x18001b730  call    cs:__imp_LocalAlloc
0x18001b736  mov     r12, rax
0x18001b739  test    rax, rax
0x18001b73c  jz      loc_18001B980
0x18001b742  xor     r14d, r14d
0x18001b745  cmp     r14d, r15d
0x18001b748  jnb     short loc_18001B76E
0x18001b74a  mov     ecx, r14d
0x18001b74d  lea     rdx, [r12+r14*8]; lplpsz
0x18001b751  shl     rcx, 4
0x18001b755  add     rcx, qword ptr [rsp+910h+var_8A8]; rclsid
0x18001b75a  call    cs:__imp_StringFromIID
0x18001b760  inc     r14d
0x18001b763  mov     edi, eax
0x18001b765  test    eax, eax
0x18001b767  jns     short loc_18001B745
0x18001b769  jmp     loc_18001B950
0x18001b76e  mov     ecx, dword ptr [rsp+910h+var_8C0+4]
0x18001b772  lea     rdx, [rsp+910h+DeviceInfoSet]
0x18001b777  xor     r14d, r14d
0x18001b77a  mov     [rsp+910h+var_8AC], r14d
0x18001b77f  call    CreateAndBuildDriverList
0x18001b784  mov     edi, eax
0x18001b786  test    eax, eax
0x18001b788  js      loc_18001B94B
0x18001b78e  test    esi, esi
0x18001b790  jnz     loc_18001B945
0x18001b796  mov     r13, [rsp+910h+DeviceInfoSet]
0x18001b79b  lea     rax, [rbp+810h+var_880]
0x18001b79f  mov     r9d, r14d; MemberIndex
0x18001b7a2  mov     [rsp+910h+DriverInfoData], rax; DriverInfoData
0x18001b7a7  lea     r14d, [rsi+1]
0x18001b7ab  xor     edx, edx; DeviceInfoData
0x18001b7ad  mov     r8d, r14d; DriverType
0x18001b7b0  mov     rcx, r13; DeviceInfoSet
0x18001b7b3  call    cs:__imp_SetupDiEnumDriverInfoW
0x18001b7b9  test    eax, eax
0x18001b7bb  jz      loc_18001B941
0x18001b7c1  xor     edx, edx; Val
0x18001b7c3  lea     rcx, [rbp+810h+var_260]; void *
0x18001b7ca  mov     r8d, 208h; Size
0x18001b7d0  call    memset_0
0x18001b7d5  mov     esi, r14d
0x18001b7d8  mov     dword ptr [rsp+910h+var_8C0], r14d
0x18001b7dd  xor     r14d, r14d
0x18001b7e0  mov     [rsp+910h+var_8B0], r14d
0x18001b7e5  test    edi, edi
0x18001b7e7  js      loc_18001B920
0x18001b7ed  cmp     r14d, r15d
0x18001b7f0  jnb     loc_18001B920
0x18001b7f6  mov     rax, [rsp+910h+hMem]
0x18001b7fb  lea     r13, [rax+r14*4]
0x18001b7ff  cmp     dword ptr [r13+0], 0
0x18001b804  jnz     loc_18001B8ED
0x18001b80a  mov     rcx, [r12+r14*8]; lpString1
0x18001b80e  call    IsInboxCorePrinterDriver
0x18001b813  test    eax, eax
0x18001b815  jz      loc_18001B8ED
0x18001b81b  mov     r8d, dword ptr [rsp+910h+var_8C0+4]
0x18001b820  lea     rax, [rbp+810h+var_260]
0x18001b827  mov     rdx, [r12+r14*8]
0x18001b82b  mov     r9, rbx
0x18001b82e  mov     rcx, [rsp+910h+DeviceInfoSet]
0x18001b833  mov     [rsp+910h+var_8D0], r13
0x18001b838  mov     [rsp+910h+var_8D8], 104h
0x18001b840  mov     [rsp+910h+var_8E0], rax
0x18001b845  lea     rax, [rbp+810h+var_880]
0x18001b849  mov     [rsp+910h+var_8E8], rax
0x18001b84e  mov     rax, [rbp+810h+arg_20]
0x18001b855  mov     [rsp+910h+DriverInfoData], rax
0x18001b85a  call    ?DriverFoundInDriverStore@@YAJPEAXPEAGW4PLATFORM@@U_FILETIME@@_KPEAU_SP_DRVINFO_DATA_V2_W@@1KPEAH@Z; DriverFoundInDriverStore(void *,ushort *,PLATFORM,_FILETIME,unsigned __int64,_SP_DRVINFO_DATA_V2_W *,ushort *,ulong,int *)
0x18001b85f  mov     edi, eax
0x18001b861  test    eax, eax
0x18001b863  js      loc_18001B8ED
0x18001b869  cmp     dword ptr [r13+0], 0
0x18001b86e  jz      short loc_18001B8E7
0x18001b870  mov     r14, [rbp+810h+Section]
0x18001b874  test    r14, r14
0x18001b877  jz      short loc_18001B890
0x18001b879  lea     rdx, [rbp+810h+var_260]; unsigned __int16 *
0x18001b880  mov     rcx, r14; Section
0x18001b883  call    ?VerifyLegacyNeedsDependencies@@YAHPEBG0@Z; VerifyLegacyNeedsDependencies(ushort const *,ushort const *)
0x18001b888  mov     esi, eax
0x18001b88a  mov     dword ptr [rsp+910h+var_8C0], eax
0x18001b88e  jmp     short loc_18001B8CD
0x18001b890  mov     r9, qword ptr [rsp+910h+var_8A8]; int
0x18001b895  lea     rax, [rsp+910h+var_8C0]
0x18001b89a  mov     edx, dword ptr [rsp+910h+var_8C0+4]; int
0x18001b89e  lea     rcx, [rbp+810h+var_260]; int
0x18001b8a5  mov     [rsp+910h+var_8E0], rax; __int64
0x18001b8aa  mov     r8d, r15d; int
0x18001b8ad  mov     rax, [rbp+810h+arg_20]
0x18001b8b4  mov     [rsp+910h+var_8E8], rax; __int64
0x18001b8b9  mov     [rsp+910h+DriverInfoData], rbx; FileTime1
0x18001b8be  call    CheckCoreDriversInInf
0x18001b8c3  mov     esi, dword ptr [rsp+910h+var_8C0]
0x18001b8c7  mov     edi, eax
0x18001b8c9  test    eax, eax
0x18001b8cb  js      short loc_18001B8ED
0x18001b8cd  test    esi, esi
0x18001b8cf  jnz     short loc_18001B8FA
0x18001b8d1  test    r14, r14
0x18001b8d4  jnz     short loc_18001B8DD
0x18001b8d6  cmp     [rsp+910h+var_8A0], r14
0x18001b8db  jz      short loc_18001B8ED
0x18001b8dd  mov     dword ptr [r13+0], 0
0x18001b8e5  jmp     short loc_18001B920
0x18001b8e7  xor     esi, esi
0x18001b8e9  mov     dword ptr [rsp+910h+var_8C0], esi
0x18001b8ed  mov     r14d, [rsp+910h+var_8B0]
0x18001b8f2  inc     r14d
0x18001b8f5  jmp     loc_18001B7E0
0x18001b8fa  mov     r14, [rsp+910h+var_8A0]
0x18001b8ff  test    r14, r14
0x18001b902  jz      short loc_18001B920
0x18001b904  lea     rcx, [rbp+810h+var_260]; unsigned __int16 *
0x18001b90b  call    AllocStr
0x18001b910  mov     [r14], rax
0x18001b913  neg     rax
0x18001b916  sbb     edi, edi
0x18001b918  not     edi
0x18001b91a  and     edi, 8007000Eh
0x18001b920  mov     r14d, [rsp+910h+var_8AC]
0x18001b925  inc     r14d
0x18001b928  mov     [rbp+810h+var_880.cbSize], 620h
0x18001b92f  mov     [rsp+910h+var_8AC], r14d
0x18001b934  test    edi, edi
0x18001b936  jns     loc_18001B78E
0x18001b93c  mov     r13, [rsp+910h+DeviceInfoSet]
0x18001b941  test    edi, edi
0x18001b943  js      short loc_18001B950
0x18001b945  mov     rax, [rbp+810h+var_888]
0x18001b949  mov     [rax], esi
0x18001b94b  mov     r13, [rsp+910h+DeviceInfoSet]
0x18001b950  xor     ebx, ebx
0x18001b952  test    r15d, r15d
0x18001b955  jz      short loc_18001B975
0x18001b957  mov     rcx, [r12+rbx*8]; pv
0x18001b95b  test    rcx, rcx
0x18001b95e  jz      short loc_18001B96E
0x18001b960  call    cs:__imp_CoTaskMemFree
0x18001b966  mov     qword ptr [r12+rbx*8], 0
0x18001b96e  inc     ebx
0x18001b970  cmp     ebx, r15d
0x18001b973  jb      short loc_18001B957
0x18001b975  mov     rcx, r12; hMem
0x18001b978  call    cs:__imp_LocalFree
0x18001b97e  jmp     short loc_18001B985
0x18001b980  mov     edi, 8007000Eh
0x18001b985  mov     rcx, [rsp+910h+hMem]; hMem
0x18001b98a  call    cs:__imp_LocalFree
0x18001b990  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18001b994  jz      short loc_18001B9AC
0x18001b996  mov     rcx, r13
0x18001b999  call    DestroyOnlyPrinterDeviceInfoList
0x18001b99e  jmp     short loc_18001B9AC
0x18001b9a0  mov     edi, 8007000Eh
0x18001b9a5  jmp     short loc_18001B9AC
0x18001b9a7  mov     edi, 80070057h
0x18001b9ac  mov     eax, edi
0x18001b9ae  mov     rcx, [rbp+810h+var_50]
0x18001b9b5  xor     rcx, rsp; StackCookie
0x18001b9b8  call    __security_check_cookie
0x18001b9bd  add     rsp, 8D8h
0x18001b9c4  pop     r15
0x18001b9c6  pop     r14
0x18001b9c8  pop     r13
0x18001b9ca  pop     r12
0x18001b9cc  pop     rdi
0x18001b9cd  pop     rsi
0x18001b9ce  pop     rbx
0x18001b9cf  pop     rbp
0x18001b9d0  retn
```
