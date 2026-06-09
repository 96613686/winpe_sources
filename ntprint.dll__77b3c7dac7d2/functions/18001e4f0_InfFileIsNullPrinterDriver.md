# InfFileIsNullPrinterDriver

- ea: `0x18001e4f0`
- end: `0x18001e8a9`
- name: `InfFileIsNullPrinterDriver`
- size: `953`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000b7ec`
- `0x180013804`
- `0x180013e68`

## callees

- `0x180002300`
- `0x180012b28`
- `0x180018d18`
- `0x180019c1c`
- `0x18001a454`
- `0x18001e4f0`
- `0x180034f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e821`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e5f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e5f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e700`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e700`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001e692`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001e79c`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001e692`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001e79c`
- `SETUPAPI!SetupCloseInfFile` at `0x18001e5e3`
- `SETUPAPI!SetupCloseInfFile` at `0x18001e5e3`

## string_xrefs

- `0x18001e58e`: `OpenPrinterInf Failed`
- `0x18001e6a3`: `SetupDiGetActualSectionToInstallEx failed`
- `0x18001e7c3`: `SetupDiGetActualSectionToInstallEx failed`
- `0x18001e717`: `For pszInstallSection`

## pseudocode

```c
__int64 __fastcall InfFileIsNullPrinterDriver(const unsigned __int16 **a1, unsigned int a2, int *a3)
{
  __int64 v3; // r12
  __int64 v5; // r8
  WCHAR *v6; // rsi
  signed int v7; // eax
  signed int LastErrorAsHResult; // ebx
  const unsigned __int16 **v9; // r14
  const WCHAR *v10; // rdx
  const unsigned __int16 *v11; // rax
  DWORD LastError; // eax
  DWORD RequiredSize; // [rsp+50h] [rbp-9h] BYREF
  HINF InfHandle; // [rsp+58h] [rbp-1h] BYREF
  int *v16; // [rsp+60h] [rbp+7h]
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+68h] [rbp+Fh] BYREF

  v16 = a3;
  v3 = (int)a2;
  InfHandle = (HINF)-1LL;
  RequiredSize = 0;
  memset(&AlternatePlatformInfo, 0, sizeof(AlternatePlatformInfo));
  if ( a1 && (unsigned int)ValidPlatform(a2) && v5 )
  {
    v6 = 0;
    v7 = OpenPrinterInf(a1, (unsigned int)v3, &InfHandle);
    LastErrorAsHResult = v7;
    v9 = (const unsigned __int16 **)&PlatformEnv[v3];
    if ( v7 >= 0 )
    {
      AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * v3);
      v10 = a1[2];
      AlternatePlatformInfo.ProcessorArchitecture = word_180047CE4[4 * v3];
      AlternatePlatformInfo.cbSize = 28;
      if ( SetupDiGetActualSectionToInstallExW(InfHandle, v10, &AlternatePlatformInfo, 0, 0, &RequiredSize, 0, 0)
        || (LastErrorAsHResult = GetLastErrorAsHResult(),
            SplLogPrinterSetupEvent(
              &SETUP_PARSEINF_FAILED,
              L"InfFileIsNullPrinterDriver",
              L"SetupDiGetActualSectionToInstallEx failed",
              0,
              *a1,
              a1[1],
              a1[2],
              *v9,
              (unsigned __int16)LastErrorAsHResult,
              LastErrorAsHResult),
            LastErrorAsHResult >= 0) )
      {
        v6 = (WCHAR *)LocalAlloc(0x40u, 2 * RequiredSize);
        if ( v6
          || (LastErrorAsHResult = GetLastErrorAsHResult(),
              SplLogPrinterSetupEvent(
                &SETUP_PARSEINF_FAILED,
                L"InfFileIsNullPrinterDriver",
                L"LocalAllocMem failed",
                L"For pszInstallSection",
                *a1,
                a1[1],
                a1[2],
                *v9,
                (unsigned __int16)LastErrorAsHResult,
                LastErrorAsHResult),
              LastErrorAsHResult >= 0) )
        {
          if ( SetupDiGetActualSectionToInstallExW(InfHandle, a1[2], &AlternatePlatformInfo, v6, RequiredSize, 0, 0, 0) )
            goto LABEL_20;
          LastErrorAsHResult = GetLastErrorAsHResult();
          v11 = v6;
          if ( !v6 )
            v11 = a1[2];
          SplLogPrinterSetupEvent(
            &SETUP_PARSEINF_FAILED,
            L"InfFileIsNullPrinterDriver",
            L"SetupDiGetActualSectionToInstallEx failed",
            0,
            *a1,
            a1[1],
            v11,
            *v9,
            (unsigned __int16)LastErrorAsHResult,
            LastErrorAsHResult);
          if ( LastErrorAsHResult >= 0 )
          {
LABEL_20:
            LastErrorAsHResult = IsNullPrinterDriver(InfHandle, v6, v16);
            if ( LastErrorAsHResult < 0 )
            {
              LastError = GetLastError();
              SplLogPrinterSetupEvent(
                &SETUP_PARSEINF_FAILED,
                L"InfFileIsNullPrinterDriver",
                L"IsNullPrinterDriver failed",
                0,
                *a1,
                0,
                0,
                (const unsigned __int16 *)PlatformEnv[v3],
                LastError,
                LastErrorAsHResult);
            }
          }
        }
      }
    }
    else
    {
      SplLogPrinterSetupEvent(
        &SETUP_PARSEINF_FAILED,
        L"InfFileIsNullPrinterDriver",
        L"OpenPrinterInf Failed",
        0,
        *a1,
        a1[1],
        a1[2],
        *v9,
        (unsigned __int16)v7,
        v7);
    }
    if ( InfHandle != (HINF)-1LL )
      SetupCloseInfFile(InfHandle);
    if ( v6 )
      LocalFree(v6);
    if ( LastErrorAsHResult >= 0 )
      SplLogPrinterSetupEvent(
        &SETUP_PARSEINF_SUCCEEDED,
        L"InfFileIsNullPrinterDriver",
        0,
        0,
        *a1,
        0,
        0,
        (const unsigned __int16 *)PlatformEnv[v3],
        0,
        LastErrorAsHResult);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x18001e4f0  mov     [rsp-8+arg_18], rbx
0x18001e4f5  push    rbp
0x18001e4f6  push    rsi
0x18001e4f7  push    rdi
0x18001e4f8  push    r12
0x18001e4fa  push    r14
0x18001e4fc  lea     rbp, [rsp-37h]
0x18001e501  sub     rsp, 90h
0x18001e508  mov     rax, cs:__security_cookie
0x18001e50f  xor     rax, rsp
0x18001e512  mov     [rbp+57h+var_28], rax
0x18001e516  xorps   xmm0, xmm0
0x18001e519  mov     [rbp+57h+var_50], r8
0x18001e51d  xor     eax, eax
0x18001e51f  movsxd  r12, edx
0x18001e522  mov     [rbp+57h+InfHandle], 0FFFFFFFFFFFFFFFFh
0x18001e52a  mov     rdi, rcx
0x18001e52d  mov     [rbp+57h+var_60], eax
0x18001e530  movups  xmmword ptr [rbp+57h+AlternatePlatformInfo.cbSize], xmm0
0x18001e534  movups  xmmword ptr [rbp+57h+AlternatePlatformInfo.MinorVersion], xmm0
0x18001e538  test    rcx, rcx
0x18001e53b  jz      loc_18001E87F
0x18001e541  mov     ecx, r12d
0x18001e544  call    ValidPlatform
0x18001e549  test    eax, eax
0x18001e54b  jz      loc_18001E87F
0x18001e551  test    r8, r8
0x18001e554  jz      loc_18001E87F
0x18001e55a  lea     r8, [rbp+57h+InfHandle]
0x18001e55e  mov     edx, r12d
0x18001e561  mov     rcx, rdi
0x18001e564  xor     esi, esi
0x18001e566  call    ?OpenPrinterInf@@YAJPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEAPEAX@Z; OpenPrinterInf(_PSETUP_LOCAL_DATA *,PLATFORM,void * *)
0x18001e56b  lea     rdx, __ImageBase
0x18001e572  xor     r9d, r9d; unsigned __int16 *
0x18001e575  lea     r14, rva PlatformEnv[rdx]
0x18001e57c  mov     ebx, eax
0x18001e57e  lea     r14, [r14+r12*8]
0x18001e582  test    eax, eax
0x18001e584  jns     loc_18001E650
0x18001e58a  mov     [rsp+0B0h+var_68], eax; unsigned int
0x18001e58e  lea     r8, aOpenprinterinf; "OpenPrinterInf Failed"
0x18001e595  movzx   ecx, ax
0x18001e598  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e59f  mov     rax, [r14]
0x18001e5a2  mov     [rsp+0B0h+var_70], ecx; unsigned int
0x18001e5a6  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001e5ad  mov     [rsp+0B0h+Reserved], rax; unsigned __int16 *
0x18001e5b2  mov     rax, [rdi+10h]
0x18001e5b6  mov     [rsp+0B0h+Extension], rax; unsigned __int16 *
0x18001e5bb  mov     rax, [rdi+8]
0x18001e5bf  mov     [rsp+0B0h+RequiredSize], rax; unsigned __int16 *
0x18001e5c4  mov     rax, [rdi]
0x18001e5c7  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e5cc  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e5d1  lea     r14, __ImageBase
0x18001e5d8  cmp     [rbp+57h+InfHandle], 0FFFFFFFFFFFFFFFFh
0x18001e5dd  jz      short loc_18001E5E9
0x18001e5df  mov     rcx, [rbp+57h+InfHandle]; InfHandle
0x18001e5e3  call    cs:__imp_SetupCloseInfFile
0x18001e5e9  test    rsi, rsi
0x18001e5ec  jz      short loc_18001E5F7
0x18001e5ee  mov     rcx, rsi; hMem
0x18001e5f1  call    cs:__imp_LocalFree
0x18001e5f7  test    ebx, ebx
0x18001e5f9  js      loc_18001E884
0x18001e5ff  mov     rax, rva PlatformEnv[r14+r12*8]
0x18001e607  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e60e  mov     [rsp+0B0h+var_68], ebx; unsigned int
0x18001e612  lea     rcx, SETUP_PARSEINF_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18001e619  mov     [rsp+0B0h+var_70], 0; unsigned int
0x18001e621  xor     r9d, r9d; unsigned __int16 *
0x18001e624  mov     [rsp+0B0h+Reserved], rax; unsigned __int16 *
0x18001e629  xor     r8d, r8d; unsigned __int16 *
0x18001e62c  mov     rax, [rdi]
0x18001e62f  mov     [rsp+0B0h+Extension], 0; unsigned __int16 *
0x18001e638  mov     [rsp+0B0h+RequiredSize], 0; unsigned __int16 *
0x18001e641  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e646  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e64b  jmp     loc_18001E884
0x18001e650  mov     eax, ds:rva PlatformArch[rdx+r12*8]
0x18001e658  lea     r8, [rbp+57h+AlternatePlatformInfo]; AlternatePlatformInfo
0x18001e65c  mov     rcx, [rbp+57h+InfHandle]; InfHandle
0x18001e660  mov     [rbp+57h+AlternatePlatformInfo.Platform], eax
0x18001e663  movzx   eax, ds:rva word_180047CE4[rdx+r12*8]
0x18001e66c  mov     rdx, [rdi+10h]; InfSectionName
0x18001e670  mov     [rsp+0B0h+Reserved], rsi; Reserved
0x18001e675  mov     [rbp+57h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x18001e679  lea     rax, [rbp+57h+var_60]
0x18001e67d  mov     [rsp+0B0h+Extension], rsi; Extension
0x18001e682  mov     [rsp+0B0h+RequiredSize], rax; RequiredSize
0x18001e687  mov     [rsp+0B0h+InfSectionWithExtSize], esi; InfSectionWithExtSize
0x18001e68b  mov     [rbp+57h+AlternatePlatformInfo.cbSize], 1Ch
0x18001e692  call    cs:__imp_SetupDiGetActualSectionToInstallExW
0x18001e698  test    eax, eax
0x18001e69a  jnz     short loc_18001E6F5
0x18001e69c  call    GetLastErrorAsHResult
0x18001e6a1  mov     ebx, eax
0x18001e6a3  lea     r8, aSetupdigetactu; "SetupDiGetActualSectionToInstallEx fail"...
0x18001e6aa  movzx   eax, ax
0x18001e6ad  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e6b4  mov     [rsp+0B0h+var_68], ebx; unsigned int
0x18001e6b8  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001e6bf  mov     [rsp+0B0h+var_70], eax; unsigned int
0x18001e6c3  xor     r9d, r9d; unsigned __int16 *
0x18001e6c6  mov     rax, [r14]
0x18001e6c9  mov     [rsp+0B0h+Reserved], rax; unsigned __int16 *
0x18001e6ce  mov     rax, [rdi+10h]
0x18001e6d2  mov     [rsp+0B0h+Extension], rax; unsigned __int16 *
0x18001e6d7  mov     rax, [rdi+8]
0x18001e6db  mov     [rsp+0B0h+RequiredSize], rax; unsigned __int16 *
0x18001e6e0  mov     rax, [rdi]
0x18001e6e3  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e6e8  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e6ed  test    ebx, ebx
0x18001e6ef  js      loc_18001E5D1
0x18001e6f5  mov     eax, [rbp+57h+var_60]
0x18001e6f8  mov     ecx, 40h ; '@'; uFlags
0x18001e6fd  lea     edx, [rax+rax]; uBytes
0x18001e700  call    cs:__imp_LocalAlloc
0x18001e706  mov     rsi, rax
0x18001e709  test    rax, rax
0x18001e70c  jnz     short loc_18001E76B
0x18001e70e  call    GetLastErrorAsHResult
0x18001e713  mov     [rsp+0B0h+var_68], eax; unsigned int
0x18001e717  lea     r9, aForPszinstalls; "For pszInstallSection"
0x18001e71e  movzx   ecx, ax
0x18001e721  lea     r8, aLocalallocmemF; "LocalAllocMem failed"
0x18001e728  mov     [rsp+0B0h+var_70], ecx; unsigned int
0x18001e72c  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e733  mov     rcx, [r14]
0x18001e736  mov     ebx, eax
0x18001e738  mov     rax, [rdi]
0x18001e73b  mov     [rsp+0B0h+Reserved], rcx; unsigned __int16 *
0x18001e740  mov     rcx, [rdi+10h]
0x18001e744  mov     [rsp+0B0h+Extension], rcx; unsigned __int16 *
0x18001e749  mov     rcx, [rdi+8]
0x18001e74d  mov     [rsp+0B0h+RequiredSize], rcx; unsigned __int16 *
0x18001e752  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001e759  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e75e  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e763  test    ebx, ebx
0x18001e765  js      loc_18001E5D1
0x18001e76b  mov     eax, [rbp+57h+var_60]
0x18001e76e  lea     r8, [rbp+57h+AlternatePlatformInfo]; AlternatePlatformInfo
0x18001e772  mov     rdx, [rdi+10h]; InfSectionName
0x18001e776  mov     r9, rsi; InfSectionWithExt
0x18001e779  mov     rcx, [rbp+57h+InfHandle]; InfHandle
0x18001e77d  mov     [rsp+0B0h+Reserved], 0; Reserved
0x18001e786  mov     [rsp+0B0h+Extension], 0; Extension
0x18001e78f  mov     [rsp+0B0h+RequiredSize], 0; RequiredSize
0x18001e798  mov     [rsp+0B0h+InfSectionWithExtSize], eax; InfSectionWithExtSize
0x18001e79c  call    cs:__imp_SetupDiGetActualSectionToInstallExW
0x18001e7a2  test    eax, eax
0x18001e7a4  jnz     short loc_18001E807
0x18001e7a6  call    GetLastErrorAsHResult
0x18001e7ab  mov     rdx, [r14]
0x18001e7ae  mov     ebx, eax
0x18001e7b0  movzx   ecx, ax
0x18001e7b3  mov     rax, rsi
0x18001e7b6  test    rsi, rsi
0x18001e7b9  jnz     short loc_18001E7BF
0x18001e7bb  mov     rax, [rdi+10h]
0x18001e7bf  mov     [rsp+0B0h+var_68], ebx; unsigned int
0x18001e7c3  lea     r8, aSetupdigetactu; "SetupDiGetActualSectionToInstallEx fail"...
0x18001e7ca  mov     [rsp+0B0h+var_70], ecx; unsigned int
0x18001e7ce  xor     r9d, r9d; unsigned __int16 *
0x18001e7d1  mov     [rsp+0B0h+Reserved], rdx; unsigned __int16 *
0x18001e7d6  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001e7dd  mov     [rsp+0B0h+Extension], rax; unsigned __int16 *
0x18001e7e2  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e7e9  mov     rax, [rdi+8]
0x18001e7ed  mov     [rsp+0B0h+RequiredSize], rax; unsigned __int16 *
0x18001e7f2  mov     rax, [rdi]
0x18001e7f5  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e7fa  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e7ff  test    ebx, ebx
0x18001e801  js      loc_18001E5D1
0x18001e807  mov     r8, [rbp+57h+var_50]; int *
0x18001e80b  mov     rdx, rsi; unsigned __int16 *
0x18001e80e  mov     rcx, [rbp+57h+InfHandle]; void *
0x18001e812  call    ?IsNullPrinterDriver@@YAJPEAXPEBGPEAH@Z; IsNullPrinterDriver(void *,ushort const *,int *)
0x18001e817  mov     ebx, eax
0x18001e819  test    eax, eax
0x18001e81b  jns     loc_18001E5D1
0x18001e821  call    cs:__imp_GetLastError
0x18001e827  mov     [rsp+0B0h+var_68], ebx; unsigned int
0x18001e82b  lea     r14, __ImageBase
0x18001e832  mov     [rsp+0B0h+var_70], eax; unsigned int
0x18001e836  lea     r8, aIsnullprinterd_1; "IsNullPrinterDriver failed"
0x18001e83d  mov     rax, rva PlatformEnv[r14+r12*8]
0x18001e845  lea     rdx, aInffileisnullp; "InfFileIsNullPrinterDriver"
0x18001e84c  mov     [rsp+0B0h+Reserved], rax; unsigned __int16 *
0x18001e851  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x18001e858  mov     rax, [rdi]
0x18001e85b  xor     r9d, r9d; unsigned __int16 *
0x18001e85e  mov     [rsp+0B0h+Extension], 0; unsigned __int16 *
0x18001e867  mov     [rsp+0B0h+RequiredSize], 0; unsigned __int16 *
0x18001e870  mov     qword ptr [rsp+0B0h+InfSectionWithExtSize], rax; unsigned __int16 *
0x18001e875  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18001e87a  jmp     loc_18001E5D8
0x18001e87f  mov     ebx, 80070057h
0x18001e884  mov     eax, ebx
0x18001e886  mov     rcx, [rbp+57h+var_28]
0x18001e88a  xor     rcx, rsp; StackCookie
0x18001e88d  call    __security_check_cookie
0x18001e892  mov     rbx, [rsp+0B0h+arg_18]
0x18001e89a  add     rsp, 90h
0x18001e8a1  pop     r14
0x18001e8a3  pop     r12
0x18001e8a5  pop     rdi
0x18001e8a6  pop     rsi
0x18001e8a7  pop     rbp
0x18001e8a8  retn
```
