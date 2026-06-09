# Windows::Compat::Inventory::GetMoreData::AddHwReqChk(_iobuf *)

- ea: `0x14000d7bc`
- end: `0x14000dbc2`
- name: `?AddHwReqChk@GetMoreData@Inventory@Compat@Windows@@CAJPEAU_iobuf@@@Z`
- size: `1030`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000dbdc`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400026d8`
- `0x14000d7bc`
- `0x1400151b0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d8c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d8de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d8c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000d8de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000d83f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000d83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d84d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000db93`

## string_xrefs

- `0x14000d832`: `hwreqchk.dll`
- `0x14000d912`: `Windows::Compat::Inventory::GetMoreData::AddHwReqChk`
- `0x14000d92e`: `Windows::Compat::Inventory::GetMoreData::AddHwReqChk`
- `0x14000d9a9`: `Windows::Compat::Inventory::GetMoreData::AddHwReqChk`
- `0x14000d9de`: `	SSE2ProcessorSupport      :	%d\n	NXProcessorSupport        :	%d\n	CompareExchange128Support :	%d\n	LahfSahfSupport           :	%d\n	PrefetchWSupport          :	%d\n	CpuCoreCount              :	%d\n	SecureBootCapable         :	%d\n	TpmVersion                :	%d\n	CpuMhz                    :	%d\n	RamMB                     :	%d\n	SystemDiskSizeMB          :	%d\n	ArmV81ProcessorSupport    :	%d\n	Architecture              :	%d\n	CpuFamily                 :	%d\n	CpuModel                  :	%d\n	CpuS`

## pseudocode

```c
signed int __fastcall Windows::Compat::Inventory::GetMoreData::AddHwReqChk(FILE *Stream)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  signed int result; // eax
  FARPROC ProcAddress; // rax
  __int64 v6; // rdi
  const char *v7; // r9
  __int64 v8; // r8
  FARPROC v9; // rdi
  FARPROC v10; // rax
  int v11; // eax
  const wchar_t *v12; // rax
  unsigned int i; // r14d
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-130h]
  __int64 v17; // [rsp+28h] [rbp-128h]
  unsigned int v18; // [rsp+D0h] [rbp-80h] BYREF
  int v19; // [rsp+D4h] [rbp-7Ch] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-78h] BYREF
  _OWORD v21[8]; // [rsp+E0h] [rbp-70h] BYREF
  unsigned int v23; // [rsp+170h] [rbp+20h] BYREF
  unsigned int v24; // [rsp+174h] [rbp+24h]
  _DWORD v25[18]; // [rsp+200h] [rbp+B0h] BYREF
  _BYTE v26[512]; // [rsp+248h] [rbp+F8h] BYREF
  int v27; // [rsp+448h] [rbp+2F8h]
  int v28; // [rsp+44Ch] [rbp+2FCh]
  int v29; // [rsp+450h] [rbp+300h]
  _BYTE v30[524]; // [rsp+454h] [rbp+304h] BYREF

  memset_0(v25, 0, 0x454u);
  pv = 0;
  memset_0(&v23, 0, 0x90u);
  v18 = 0;
  fwprintf(Stream, L"Adding HwReqChk information\n");
  Library = LoadLibraryExW(L"hwreqchk.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetHardwareRequirementSystemInfo");
    if ( ProcAddress )
    {
      v6 = ((unsigned int (__fastcall *)(_DWORD *))ProcAddress)(v25);
      fwprintf(Stream, L"GetHardwareRequirementSystemInfo returned [%#x]\n", v6);
      if ( (int)v6 < 0 )
      {
        v7 = "GetHardwareRequirementSystemInfo failed [%#x]";
        v8 = 198;
        goto LABEL_13;
      }
      v9 = GetProcAddress(v3, "EvaluateHardwareRequirement");
      if ( v9 )
      {
        v10 = GetProcAddress(v3, "GetLatestHardwareRequirement");
        if ( v10 )
        {
          v11 = ((__int64 (__fastcall *)(__int64, unsigned int *))v10)(1, &v23);
          if ( v11 < 0 )
            AslLogCallPrintf(
              1,
              "Windows::Compat::Inventory::GetMoreData::AddHwReqChk",
              217,
              "GetLatestHardwareRequirement failed [%#x]",
              v11);
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::GetMoreData::AddHwReqChk",
            220,
            "Calling EvaluateHardwareRequirement with target-release: %d product-type: %d",
            v23,
            v24);
          fwprintf(
            Stream,
            L"\nCalling EvaluateHardwareRequirement with target-release: %d, product-type: %d\n",
            v23,
            v24);
          v19 = 0;
          v6 = ((unsigned int (__fastcall *)(unsigned int *, int *, LPVOID *, unsigned int *))v9)(&v23, &v19, &pv, &v18);
          fwprintf(Stream, L"EvaluateHardwareRequirement returned [%#x]\n", v6);
          if ( (int)v6 >= 0 )
          {
            v12 = L"Passed";
            if ( !v19 )
              v12 = L"Failed";
            LODWORD(v17) = v25[3];
            LODWORD(v16) = v25[2];
            fwprintf(
              Stream,
              L"\tSSE2ProcessorSupport      :\t%d\n"
               "\tNXProcessorSupport        :\t%d\n"
               "\tCompareExchange128Support :\t%d\n"
               "\tLahfSahfSupport           :\t%d\n"
               "\tPrefetchWSupport          :\t%d\n"
               "\tCpuCoreCount              :\t%d\n"
               "\tSecureBootCapable         :\t%d\n"
               "\tTpmVersion                :\t%d\n"
               "\tCpuMhz                    :\t%d\n"
               "\tRamMB                     :\t%d\n"
               "\tSystemDiskSizeMB          :\t%d\n"
               "\tArmV81ProcessorSupport    :\t%d\n"
               "\tArchitecture              :\t%d\n"
               "\tCpuFamily                 :\t%d\n"
               "\tCpuModel                  :\t%d\n"
               "\tCpuStepping               :\t%d\n"
               "\tPlatform                  :\t%d\n"
               "\tCpuVendor                 :\t%d\n"
               "\tIsServer                  :\t%d\n"
               "\tLockdownMode              :\t%d\n"
               "\tProductOS                 :\t%d\n"
               "\tProductName               :\t%ls\n"
               "\tProcessorName             :\t%ls\n"
               "\tRequirement Evaluation    :\t%ls\n",
              v25[0],
              v25[1],
              v16,
              v17,
              v25[4],
              v25[11],
              v25[6],
              v25[7],
              v25[10],
              v25[8],
              v25[9],
              v25[5],
              v25[17],
              v25[12],
              v25[13],
              v25[14],
              v25[15],
              v25[16],
              v27,
              v28,
              v29,
              v30,
              v26,
              v12);
            for ( i = 0; i < v18; ++i )
            {
              v14 = L"TRUE";
              v15 = 132LL * i;
              v21[0] = *(_OWORD *)((char *)pv + v15);
              v21[1] = *(_OWORD *)((char *)pv + v15 + 16);
              v21[2] = *(_OWORD *)((char *)pv + v15 + 32);
              v21[3] = *(_OWORD *)((char *)pv + v15 + 48);
              v21[4] = *(_OWORD *)((char *)pv + v15 + 64);
              v21[5] = *(_OWORD *)((char *)pv + v15 + 80);
              v21[6] = *(_OWORD *)((char *)pv + v15 + 96);
              v21[7] = *(_OWORD *)((char *)pv + v15 + 112);
              if ( !*(_DWORD *)((char *)pv + v15 + 128) )
                v14 = L"FALSE";
              fwprintf(Stream, L"%32ls\tSucceeded:%ls\n", v21, v14);
            }
            if ( pv )
              CoTaskMemFree(pv);
            return v6;
          }
          v7 = "EvaluateHardwareRequirement failed [%#x]";
          v8 = 229;
LABEL_13:
          LODWORD(v16) = v6;
          AslLogCallPrintf(1, "Windows::Compat::Inventory::GetMoreData::AddHwReqChk", v8, v7, v16);
          return v6;
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000d7bc  mov     [rsp-8+arg_8], rbx
0x14000d7c1  mov     [rsp-8+arg_10], rsi
0x14000d7c6  push    rbp
0x14000d7c7  push    rdi
0x14000d7c8  push    r14
0x14000d7ca  lea     rbp, [rsp-520h]
0x14000d7d2  sub     rsp, 670h
0x14000d7d9  mov     rax, cs:__security_cookie
0x14000d7e0  xor     rax, rsp
0x14000d7e3  mov     [rbp+530h+var_20], rax
0x14000d7ea  mov     rsi, rcx
0x14000d7ed  xor     edx, edx; Val
0x14000d7ef  lea     rcx, [rbp+530h+var_480]; void *
0x14000d7f6  mov     r8d, 454h; Size
0x14000d7fc  call    memset_0
0x14000d801  xor     edx, edx; Val
0x14000d803  mov     [rbp+530h+pv], 0
0x14000d80b  mov     r8d, 90h; Size
0x14000d811  lea     rcx, [rbp+530h+var_510]; void *
0x14000d815  call    memset_0
0x14000d81a  lea     rdx, aAddingHwreqchk; "Adding HwReqChk information\n"
0x14000d821  mov     [rbp+530h+var_5B0], 0
0x14000d828  mov     rcx, rsi; Stream
0x14000d82b  call    fwprintf
0x14000d830  xor     edx, edx; hFile
0x14000d832  lea     rcx, LibFileName; "hwreqchk.dll"
0x14000d839  mov     r8d, 800h; dwFlags
0x14000d83f  call    cs:__imp_LoadLibraryExW
0x14000d845  mov     rbx, rax
0x14000d848  test    rax, rax
0x14000d84b  jnz     short loc_14000D868
0x14000d84d  call    cs:__imp_GetLastError
0x14000d853  test    eax, eax
0x14000d855  jle     loc_14000DB9B
0x14000d85b  movzx   eax, ax
0x14000d85e  or      eax, 80070000h
0x14000d863  jmp     loc_14000DB9B
0x14000d868  lea     rdx, aGethardwarereq; "GetHardwareRequirementSystemInfo"
0x14000d86f  mov     rcx, rbx; hModule
0x14000d872  call    cs:__imp_GetProcAddress
0x14000d878  test    rax, rax
0x14000d87b  jz      short loc_14000D84D
0x14000d87d  lea     rcx, [rbp+530h+var_480]
0x14000d884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d889  mov     r8d, eax
0x14000d88c  lea     rdx, aGethardwarereq_1; "GetHardwareRequirementSystemInfo return"...
0x14000d893  mov     rcx, rsi; Stream
0x14000d896  mov     edi, eax
0x14000d898  call    fwprintf
0x14000d89d  test    edi, edi
0x14000d89f  jns     short loc_14000D8B8
0x14000d8a1  lea     r9, aGethardwarereq_0; "GetHardwareRequirementSystemInfo failed"...
0x14000d8a8  mov     r8d, 0C6h
0x14000d8ae  mov     ecx, 1
0x14000d8b3  jmp     loc_14000D9A9
0x14000d8b8  lea     rdx, aEvaluatehardwa; "EvaluateHardwareRequirement"
0x14000d8bf  mov     rcx, rbx; hModule
0x14000d8c2  call    cs:__imp_GetProcAddress
0x14000d8c8  mov     rdi, rax
0x14000d8cb  test    rax, rax
0x14000d8ce  jz      loc_14000D84D
0x14000d8d4  lea     rdx, aGetlatesthardw; "GetLatestHardwareRequirement"
0x14000d8db  mov     rcx, rbx; hModule
0x14000d8de  call    cs:__imp_GetProcAddress
0x14000d8e4  test    rax, rax
0x14000d8e7  jz      loc_14000D84D
0x14000d8ed  mov     ebx, 1
0x14000d8f2  lea     rdx, [rbp+530h+var_510]
0x14000d8f6  mov     ecx, ebx
0x14000d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8fd  test    eax, eax
0x14000d8ff  jns     short loc_14000D920
0x14000d901  lea     r9, aGetlatesthardw_0; "GetLatestHardwareRequirement failed [%#"...
0x14000d908  mov     dword ptr [rsp+680h+var_660], eax
0x14000d90c  mov     r8d, 0D9h
0x14000d912  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::GetMoreData"...
0x14000d919  mov     ecx, ebx
0x14000d91b  call    AslLogCallPrintf
0x14000d920  mov     eax, [rbp+530h+var_50C]
0x14000d923  lea     r9, aCallingEvaluat_0; "Calling EvaluateHardwareRequirement wit"...
0x14000d92a  mov     dword ptr [rsp+680h+var_658], eax
0x14000d92e  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::GetMoreData"...
0x14000d935  mov     eax, [rbp+530h+var_510]
0x14000d938  mov     r8d, 0DCh
0x14000d93e  mov     ecx, 3
0x14000d943  mov     dword ptr [rsp+680h+var_660], eax
0x14000d947  call    AslLogCallPrintf
0x14000d94c  mov     r9d, [rbp+530h+var_50C]
0x14000d950  lea     rdx, aCallingEvaluat; "\nCalling EvaluateHardwareRequirement w"...
0x14000d957  mov     r8d, [rbp+530h+var_510]
0x14000d95b  mov     rcx, rsi; Stream
0x14000d95e  call    fwprintf
0x14000d963  lea     r9, [rbp+530h+var_5B0]
0x14000d967  mov     [rbp+530h+var_5AC], 0
0x14000d96e  lea     r8, [rbp+530h+pv]
0x14000d972  mov     rax, rdi
0x14000d975  lea     rdx, [rbp+530h+var_5AC]
0x14000d979  lea     rcx, [rbp+530h+var_510]
0x14000d97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d982  mov     r8d, eax
0x14000d985  lea     rdx, aEvaluatehardwa_1; "EvaluateHardwareRequirement returned [%"...
0x14000d98c  mov     rcx, rsi; Stream
0x14000d98f  mov     edi, eax
0x14000d991  call    fwprintf
0x14000d996  test    edi, edi
0x14000d998  jns     short loc_14000D9BE
0x14000d99a  lea     r9, aEvaluatehardwa_0; "EvaluateHardwareRequirement failed [%#x"...
0x14000d9a1  mov     r8d, 0E5h
0x14000d9a7  mov     ecx, ebx
0x14000d9a9  lea     rdx, aWindowsCompatI_4; "Windows::Compat::Inventory::GetMoreData"...
0x14000d9b0  mov     dword ptr [rsp+680h+var_660], edi
0x14000d9b4  call    AslLogCallPrintf
0x14000d9b9  jmp     loc_14000DB99
0x14000d9be  cmp     [rbp+530h+var_5AC], 0
0x14000d9c2  lea     rcx, aFailed; "Failed"
0x14000d9c9  mov     r9d, [rbp+530h+var_47C]
0x14000d9d0  lea     rax, aPassed; "Passed"
0x14000d9d7  mov     r8d, [rbp+530h+var_480]
0x14000d9de  lea     rdx, aSse2processors; "\tSSE2ProcessorSupport      :\t%d\n\tNX"...
0x14000d9e5  cmovz   rax, rcx
0x14000d9e9  mov     rcx, rsi; Stream
0x14000d9ec  mov     [rsp+680h+var_5B8], rax
0x14000d9f4  lea     rax, [rbp+530h+var_438]
0x14000d9fb  mov     [rsp+680h+var_5C0], rax
0x14000da03  lea     rax, [rbp+530h+var_22C]
0x14000da0a  mov     [rsp+680h+var_5C8], rax
0x14000da12  mov     eax, [rbp+530h+var_230]
0x14000da18  mov     [rsp+680h+var_5D0], eax
0x14000da1f  mov     eax, [rbp+530h+var_234]
0x14000da25  mov     [rsp+680h+var_5D8], eax
0x14000da2c  mov     eax, [rbp+530h+var_238]
0x14000da32  mov     [rsp+680h+var_5E0], eax
0x14000da39  mov     eax, [rbp+530h+var_440]
0x14000da3f  mov     [rsp+680h+var_5E8], eax
0x14000da46  mov     eax, [rbp+530h+var_444]
0x14000da4c  mov     [rsp+680h+var_5F0], eax
0x14000da53  mov     eax, [rbp+530h+var_448]
0x14000da59  mov     [rsp+680h+var_5F8], eax
0x14000da60  mov     eax, [rbp+530h+var_44C]
0x14000da66  mov     [rsp+680h+var_600], eax
0x14000da6d  mov     eax, [rbp+530h+var_450]
0x14000da73  mov     [rsp+680h+var_608], eax
0x14000da77  mov     eax, [rbp+530h+var_43C]
0x14000da7d  mov     [rsp+680h+var_610], eax
0x14000da81  mov     eax, [rbp+530h+var_46C]
0x14000da87  mov     [rsp+680h+var_618], eax
0x14000da8b  mov     eax, [rbp+530h+var_45C]
0x14000da91  mov     [rsp+680h+var_620], eax
0x14000da95  mov     eax, [rbp+530h+var_460]
0x14000da9b  mov     [rsp+680h+var_628], eax
0x14000da9f  mov     eax, [rbp+530h+var_458]
0x14000daa5  mov     [rsp+680h+var_630], eax
0x14000daa9  mov     eax, [rbp+530h+var_464]
0x14000daaf  mov     [rsp+680h+var_638], eax
0x14000dab3  mov     eax, [rbp+530h+var_468]
0x14000dab9  mov     [rsp+680h+var_640], eax
0x14000dabd  mov     eax, [rbp+530h+var_454]
0x14000dac3  mov     [rsp+680h+var_648], eax
0x14000dac7  mov     eax, [rbp+530h+var_470]
0x14000dacd  mov     [rsp+680h+var_650], eax
0x14000dad1  mov     eax, [rbp+530h+var_474]
0x14000dad7  mov     dword ptr [rsp+680h+var_658], eax
0x14000dadb  mov     eax, [rbp+530h+var_478]
0x14000dae1  mov     dword ptr [rsp+680h+var_660], eax
0x14000dae5  call    fwprintf
0x14000daea  xor     r14d, r14d
0x14000daed  cmp     [rbp+530h+var_5B0], r14d
0x14000daf1  jbe     loc_14000DB8A
0x14000daf7  mov     eax, r14d
0x14000dafa  lea     r9, aTrue_0; "TRUE"
0x14000db01  imul    rcx, rax, 84h
0x14000db08  mov     rax, [rbp+530h+pv]
0x14000db0c  lea     r8, [rbp+530h+var_5A0]
0x14000db10  lea     rdx, a32lsSucceededL; "%32ls\tSucceeded:%ls\n"
0x14000db17  movups  xmm0, xmmword ptr [rcx+rax]
0x14000db1b  movups  [rbp+530h+var_5A0], xmm0
0x14000db1f  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x14000db24  movups  [rbp+530h+var_590], xmm1
0x14000db28  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x14000db2d  movups  [rbp+530h+var_580], xmm0
0x14000db31  movups  xmm1, xmmword ptr [rcx+rax+30h]
0x14000db36  movups  [rbp+530h+var_570], xmm1
0x14000db3a  movups  xmm0, xmmword ptr [rcx+rax+40h]
0x14000db3f  movups  [rbp+530h+var_560], xmm0
0x14000db43  movups  xmm1, xmmword ptr [rcx+rax+50h]
0x14000db48  movups  [rbp+530h+var_550], xmm1
0x14000db4c  movups  xmm0, xmmword ptr [rcx+rax+60h]
0x14000db51  movups  [rbp+530h+var_540], xmm0
0x14000db55  movups  xmm1, xmmword ptr [rcx+rax+70h]
0x14000db5a  movups  [rbp+530h+var_530], xmm1
0x14000db5e  mov     eax, [rcx+rax+80h]
0x14000db65  test    eax, eax
0x14000db67  lea     rcx, aFalse_0; "FALSE"
0x14000db6e  mov     [rbp+530h+var_520], eax
0x14000db71  cmovz   r9, rcx
0x14000db75  mov     rcx, rsi; Stream
0x14000db78  call    fwprintf
0x14000db7d  add     r14d, ebx
0x14000db80  cmp     r14d, [rbp+530h+var_5B0]
0x14000db84  jb      loc_14000DAF7
0x14000db8a  mov     rcx, [rbp+530h+pv]; pv
0x14000db8e  test    rcx, rcx
0x14000db91  jz      short loc_14000DB99
0x14000db93  call    cs:__imp_CoTaskMemFree
0x14000db99  mov     eax, edi
0x14000db9b  mov     rcx, [rbp+530h+var_20]
0x14000dba2  xor     rcx, rsp; StackCookie
0x14000dba5  call    __security_check_cookie
0x14000dbaa  lea     r11, [rsp+680h+var_10]
0x14000dbb2  mov     rbx, [r11+28h]
0x14000dbb6  mov     rsi, [r11+30h]
0x14000dbba  mov     rsp, r11
0x14000dbbd  pop     r14
0x14000dbbf  pop     rdi
0x14000dbc0  pop     rbp
0x14000dbc1  retn
```
