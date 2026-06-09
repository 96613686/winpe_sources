# ObtainLatestVersionFromDriverStore(void *,PLATFORM,_SP_DRVINFO_DATA_V2_W *,ulong,ushort *)

- ea: `0x18000c870`
- end: `0x18000ca30`
- name: `?ObtainLatestVersionFromDriverStore@@YAJPEAXW4PLATFORM@@PEAU_SP_DRVINFO_DATA_V2_W@@KPEAG@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009724`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x18000c870`
- `0x180012b28`
- `0x1800272bc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c9ae`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000c9ae`
- `KERNEL32!lstrcmpiW` at `0x18000c93c`
- `KERNEL32!lstrcmpiW` at `0x18000c93c`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000c925`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000c925`

## pseudocode

```c
__int64 __fastcall ObtainLatestVersionFromDriverStore(
        char *a1,
        unsigned int a2,
        __int64 a3,
        DWORD a4,
        unsigned __int16 *a5)
{
  int LastErrorAsFailHR; // ebx
  DWORDLONG DriverVersion; // rsi
  int v11; // edx
  NCoreLibrary *v12; // rcx
  LONG v13; // eax
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-C8h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+660h] [rbp+560h] BYREF

  memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && (unsigned int)ValidPlatform(a2) && a3 && a5 )
  {
    LastErrorAsFailHR = 0;
    DriverVersion = *(_QWORD *)(a3 + 1560);
    FileTime1 = *(FILETIME *)(a3 + 1552);
    DriverInfoData.cbSize = 1568;
    while ( 1 )
    {
      if ( !SetupDiEnumDriverInfoW(a1, 0, 1u, a4, &DriverInfoData) )
        return (unsigned int)LastErrorAsFailHR;
      if ( !lstrcmpiW((LPCWSTR)(a3 + 16), DriverInfoData.Description) )
      {
        LODWORD(v15) = 0;
        memset_0(ReturnBuffer, 0, 0x208u);
        if ( (unsigned int)GetDriverStorePathFromDeviceInfo(
                             (int)a1,
                             v11,
                             (int)&DriverInfoData,
                             a2,
                             (__int64)&v15,
                             ReturnBuffer) )
        {
          LastErrorAsFailHR = 0;
        }
        else
        {
          LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12);
          if ( LastErrorAsFailHR < 0 )
            goto LABEL_17;
        }
        if ( (_DWORD)v15 )
        {
          v13 = CompareFileTime(&FileTime1, &DriverInfoData.DriverDate);
          if ( v13 == -1 )
          {
            FileTime1 = DriverInfoData.DriverDate;
          }
          else if ( v13 || DriverInfoData.DriverVersion <= DriverVersion )
          {
            goto LABEL_17;
          }
          DriverVersion = DriverInfoData.DriverVersion;
          LastErrorAsFailHR = StringCchCopyW(a5, 0x104u, ReturnBuffer);
        }
      }
LABEL_17:
      ++a4;
      DriverInfoData.cbSize = 1568;
      if ( LastErrorAsFailHR < 0 )
        return (unsigned int)LastErrorAsFailHR;
    }
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18000c870  push    rbp
0x18000c872  push    rbx
0x18000c873  push    rsi
0x18000c874  push    rdi
0x18000c875  push    r12
0x18000c877  push    r13
0x18000c879  push    r14
0x18000c87b  push    r15
0x18000c87d  lea     rbp, [rsp-788h]
0x18000c885  sub     rsp, 888h
0x18000c88c  mov     rax, cs:__security_cookie
0x18000c893  xor     rax, rsp
0x18000c896  mov     [rbp+7C0h+var_50], rax
0x18000c89d  mov     r15, [rbp+7C0h+arg_20]
0x18000c8a4  mov     rdi, r8
0x18000c8a7  mov     r12d, edx
0x18000c8aa  mov     r13, rcx
0x18000c8ad  xor     edx, edx; Val
0x18000c8af  lea     rcx, [rsp+8C0h+var_880.DriverType]; void *
0x18000c8b4  mov     r8d, 61Ch; Size
0x18000c8ba  mov     r14d, r9d
0x18000c8bd  call    memset_0
0x18000c8c2  lea     rax, [r13-1]
0x18000c8c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c8ca  ja      loc_18000CA06
0x18000c8d0  mov     ecx, r12d
0x18000c8d3  call    ValidPlatform
0x18000c8d8  test    eax, eax
0x18000c8da  jz      loc_18000CA06
0x18000c8e0  test    rdi, rdi
0x18000c8e3  jz      loc_18000CA06
0x18000c8e9  test    r15, r15
0x18000c8ec  jz      loc_18000CA06
0x18000c8f2  mov     rax, [rdi+610h]
0x18000c8f9  xor     ebx, ebx
0x18000c8fb  mov     rsi, [rdi+618h]
0x18000c902  mov     qword ptr [rsp+8C0h+FileTime1.dwLowDateTime], rax
0x18000c907  mov     [rsp+8C0h+var_880.cbSize], 620h
0x18000c90f  xor     edx, edx; DeviceInfoData
0x18000c911  lea     rax, [rsp+8C0h+var_880]
0x18000c916  mov     r9d, r14d; MemberIndex
0x18000c919  mov     [rsp+8C0h+DriverInfoData], rax; DriverInfoData
0x18000c91e  mov     rcx, r13; DeviceInfoSet
0x18000c921  lea     r8d, [rdx+1]; DriverType
0x18000c925  call    cs:__imp_SetupDiEnumDriverInfoW
0x18000c92b  test    eax, eax
0x18000c92d  jz      loc_18000CA0B
0x18000c933  lea     rcx, [rdi+10h]; lpString1
0x18000c937  lea     rdx, [rsp+8C0h+var_880.Description]; lpString2
0x18000c93c  call    cs:__imp_lstrcmpiW
0x18000c942  test    eax, eax
0x18000c944  jnz     loc_18000C9F1
0x18000c94a  xor     edx, edx; Val
0x18000c94c  mov     dword ptr [rsp+8C0h+var_890], eax
0x18000c950  mov     r8d, 208h; Size
0x18000c956  lea     rcx, [rbp+7C0h+var_260]; void *
0x18000c95d  call    memset_0
0x18000c962  lea     rax, [rbp+7C0h+var_260]
0x18000c969  mov     r9d, r12d; int
0x18000c96c  mov     [rsp+8C0h+ReturnBuffer], rax; ReturnBuffer
0x18000c971  lea     r8, [rsp+8C0h+var_880]; int
0x18000c976  lea     rax, [rsp+8C0h+var_890]
0x18000c97b  mov     rcx, r13; int
0x18000c97e  mov     [rsp+8C0h+DriverInfoData], rax; __int64
0x18000c983  call    GetDriverStorePathFromDeviceInfo
0x18000c988  test    eax, eax
0x18000c98a  jz      short loc_18000C990
0x18000c98c  xor     ebx, ebx
0x18000c98e  jmp     short loc_18000C99B
0x18000c990  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18000c995  mov     ebx, eax
0x18000c997  test    eax, eax
0x18000c999  js      short loc_18000C9F1
0x18000c99b  cmp     dword ptr [rsp+8C0h+var_890], 0
0x18000c9a0  jz      short loc_18000C9F1
0x18000c9a2  lea     rdx, [rbp+7C0h+var_880.DriverDate]; lpFileTime2
0x18000c9a9  lea     rcx, [rsp+8C0h+FileTime1]; lpFileTime1
0x18000c9ae  call    cs:__imp_CompareFileTime
0x18000c9b4  cmp     eax, 0FFFFFFFFh
0x18000c9b7  jnz     short loc_18000C9C7
0x18000c9b9  mov     rax, qword ptr [rbp+7C0h+var_880.DriverDate.dwLowDateTime]
0x18000c9c0  mov     qword ptr [rsp+8C0h+FileTime1.dwLowDateTime], rax
0x18000c9c5  jmp     short loc_18000C9D4
0x18000c9c7  test    eax, eax
0x18000c9c9  jnz     short loc_18000C9F1
0x18000c9cb  cmp     [rbp+7C0h+var_880.DriverVersion], rsi
0x18000c9d2  jbe     short loc_18000C9F1
0x18000c9d4  mov     rsi, [rbp+7C0h+var_880.DriverVersion]
0x18000c9db  lea     r8, [rbp+7C0h+var_260]; unsigned __int16 *
0x18000c9e2  mov     edx, 104h; unsigned __int64
0x18000c9e7  mov     rcx, r15; unsigned __int16 *
0x18000c9ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c9ef  mov     ebx, eax
0x18000c9f1  inc     r14d
0x18000c9f4  mov     [rsp+8C0h+var_880.cbSize], 620h
0x18000c9fc  test    ebx, ebx
0x18000c9fe  jns     loc_18000C90F
0x18000ca04  jmp     short loc_18000CA0B
0x18000ca06  mov     ebx, 80070057h
0x18000ca0b  mov     eax, ebx
0x18000ca0d  mov     rcx, [rbp+7C0h+var_50]
0x18000ca14  xor     rcx, rsp; StackCookie
0x18000ca17  call    __security_check_cookie
0x18000ca1c  add     rsp, 888h
0x18000ca23  pop     r15
0x18000ca25  pop     r14
0x18000ca27  pop     r13
0x18000ca29  pop     r12
0x18000ca2b  pop     rdi
0x18000ca2c  pop     rsi
0x18000ca2d  pop     rbx
0x18000ca2e  pop     rbp
0x18000ca2f  retn
```
