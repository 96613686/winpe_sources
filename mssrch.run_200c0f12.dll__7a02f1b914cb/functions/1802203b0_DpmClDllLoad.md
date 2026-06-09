# DpmClDllLoad

- ea: `0x1802203b0`
- end: `0x180220797`
- name: `DpmClDllLoad`
- size: `999`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180220904`
- `0x180220968`

## callees

- `0x1800cae14`
- `0x1802203b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18022059e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18022059e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180220759`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180220759`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802205be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802205e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220606`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18022062a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18022064e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220692`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802206b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802206d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802205be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802205e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220606`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18022062a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18022064e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180220692`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802206b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802206d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18022076d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18022076d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802203c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802203c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180220786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180220786`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022053c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022053c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022052b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180220778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022052b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180220778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802206e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802206e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802204ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180220583`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802204ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180220583`

## string_xrefs

- `0x180220623`: `EdpCredentialDelete`
- `0x18022066b`: `EdpQueryCredServiceInfo`
- `0x1802205b4`: `EdpCredentialCreate`
- `0x18022068b`: `EdpSetCredServiceInfo`
- `0x1802204a7`: `SYSTEM\CurrentControlSet\Services\EFS\Parameters`
- `0x180220570`: `SYSTEM\CurrentControlSet\Services\EFS\Parameters`

## pseudocode

```c
__int64 DpmClDllLoad()
{
  void *pvData; // rdi
  int v1; // esi
  signed int v2; // ebx
  LSTATUS ValueW; // ecx
  int v4; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  bool v8; // cc
  HMODULE Library; // rax
  HANDLE v10; // rax
  DWORD pcbData; // [rsp+70h] [rbp+8h] BYREF

  pcbData = 0;
  pvData = 0;
  EnterCriticalSection(&stru_1802DBCF8);
  v1 = dword_1802D9360;
  v2 = 1;
  if ( dword_1802D9360 == -1 )
  {
    dword_1802D9360 = 2;
  }
  else
  {
    ++dword_1802D9360;
    if ( v1 + 1 > 1 )
      goto LABEL_53;
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( hLibModule )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC638 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC5F8 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC600 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC630 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC608 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC618 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC5F0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC610 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( qword_1802DC628 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  hLibModule = 0;
  qword_1802DC638 = 0;
  qword_1802DC5F8 = 0;
  qword_1802DC600 = 0;
  qword_1802DC630 = 0;
  qword_1802DC608 = 0;
  qword_1802DC618 = 0;
  qword_1802DC5F0 = 0;
  qword_1802DC610 = 0;
  qword_1802DC628 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\EFS\\Parameters",
             L"EdpCredLibProxy",
             0x10000002u,
             0,
             0,
             &pcbData);
  if ( (unsigned int)(ValueW - 2) <= 1 )
  {
    v2 = -2147467263;
  }
  else
  {
    if ( ValueW )
    {
      if ( ValueW <= 0 )
      {
        v2 = ValueW;
        goto LABEL_47;
      }
      v4 = (unsigned __int16)ValueW;
LABEL_46:
      v2 = v4 | 0x80070000;
LABEL_47:
      if ( v2 >= 0 )
        goto LABEL_53;
      goto LABEL_51;
    }
    v5 = pcbData;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 8u, v5);
    if ( pvData )
    {
      LastError = RegGetValueW(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\CurrentControlSet\\Services\\EFS\\Parameters",
                    L"EdpCredLibProxy",
                    0x10000002u,
                    0,
                    pvData,
                    &pcbData);
      v2 = LastError;
      v8 = LastError <= 0;
      if ( !LastError )
      {
        Library = LoadLibraryExW((LPCWSTR)pvData, 0, 0x800u);
        hLibModule = Library;
        if ( Library )
        {
          qword_1802DC638 = (__int64)GetProcAddress(Library, "EdpCredentialCreate");
          if ( qword_1802DC638 )
          {
            qword_1802DC5F8 = (__int64)GetProcAddress(hLibModule, "EdpCredentialQuery");
            if ( qword_1802DC5F8 )
            {
              qword_1802DC600 = (__int64)GetProcAddress(hLibModule, "EdpCredentialExists");
              if ( qword_1802DC600 )
              {
                qword_1802DC630 = (__int64)GetProcAddress(hLibModule, "EdpCredentialDelete");
                if ( qword_1802DC630 )
                {
                  qword_1802DC608 = (__int64)GetProcAddress(hLibModule, "EdpFree");
                  if ( qword_1802DC608 )
                  {
                    qword_1802DC618 = (__int64)GetProcAddress(hLibModule, "EdpQueryCredServiceInfo");
                    if ( qword_1802DC618 )
                    {
                      qword_1802DC5F0 = (__int64)GetProcAddress(hLibModule, "EdpSetCredServiceInfo");
                      if ( qword_1802DC5F0 )
                      {
                        qword_1802DC610 = (__int64)GetProcAddress(hLibModule, "EdpIsConsumerDataProtectionSupported");
                        if ( qword_1802DC610 )
                        {
                          qword_1802DC628 = (__int64)GetProcAddress(hLibModule, "EdpIsConsumerDataProtectionEnforced");
                          if ( qword_1802DC628 )
                          {
                            v2 = 0;
                            goto LABEL_53;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        LastError = GetLastError();
        v8 = LastError <= 0;
        v2 = LastError;
      }
      if ( v8 )
        goto LABEL_47;
      v4 = (unsigned __int16)LastError;
      goto LABEL_46;
    }
    v2 = -2147024882;
  }
LABEL_51:
  dword_1802D9360 = v1;
  qword_1802DC638 = 0;
  qword_1802DC5F8 = 0;
  qword_1802DC600 = 0;
  qword_1802DC630 = 0;
  qword_1802DC608 = 0;
  qword_1802DC618 = 0;
  qword_1802DC5F0 = 0;
  qword_1802DC610 = 0;
  qword_1802DC628 = 0;
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
LABEL_53:
  LeaveCriticalSection(&stru_1802DBCF8);
  if ( pvData )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, pvData);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1802203b0  push    rbx
0x1802203b2  push    rbp
0x1802203b3  push    rsi
0x1802203b4  push    rdi
0x1802203b5  sub     rsp, 48h
0x1802203b9  xor     ebp, ebp
0x1802203bb  lea     rcx, stru_1802DBCF8; lpCriticalSection
0x1802203c2  mov     [rsp+68h+arg_0], ebp
0x1802203c6  mov     edi, ebp
0x1802203c8  call    cs:__imp_EnterCriticalSection
0x1802203ce  mov     esi, cs:dword_1802D9360
0x1802203d4  lea     ebx, [rbp+1]
0x1802203d7  cmp     esi, 0FFFFFFFFh
0x1802203da  jnz     short loc_1802203E8
0x1802203dc  mov     cs:dword_1802D9360, 2
0x1802203e6  jmp     short loc_1802203FE
0x1802203e8  lea     eax, [rsi+1]
0x1802203eb  mov     cs:dword_1802D9360, eax
0x1802203f1  cmp     eax, ebx
0x1802203f3  jg      loc_180220766
0x1802203f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1802203fe  cmp     cs:hLibModule, rbp
0x180220405  jz      short loc_18022040C
0x180220407  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18022040c  cmp     cs:qword_1802DC638, rbp
0x180220413  jz      short loc_18022041A
0x180220415  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18022041a  cmp     cs:qword_1802DC5F8, rbp
0x180220421  jz      short loc_180220428
0x180220423  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180220428  cmp     cs:qword_1802DC600, rbp
0x18022042f  jz      short loc_180220436
0x180220431  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180220436  cmp     cs:qword_1802DC630, rbp
0x18022043d  jz      short loc_180220444
0x18022043f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180220444  cmp     cs:qword_1802DC608, rbp
0x18022044b  jz      short loc_180220452
0x18022044d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180220452  cmp     cs:qword_1802DC618, rbp
0x180220459  jz      short loc_180220460
0x18022045b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180220460  cmp     cs:qword_1802DC5F0, rbp
0x180220467  jz      short loc_18022046E
0x180220469  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18022046e  cmp     cs:qword_1802DC610, rbp
0x180220475  jz      short loc_18022047C
0x180220477  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18022047c  cmp     cs:qword_1802DC628, rbp
0x180220483  jz      short loc_18022048A
0x180220485  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18022048a  lea     rax, [rsp+68h+arg_0]
0x18022048f  mov     cs:hLibModule, rbp
0x180220496  mov     [rsp+68h+pcbData], rax; pcbData
0x18022049b  lea     r8, aEdpcredlibprox; "EdpCredLibProxy"
0x1802204a2  mov     [rsp+68h+pvData], rbp; pvData
0x1802204a7  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\EF"...
0x1802204ae  mov     r9d, 10000002h; dwFlags
0x1802204b4  mov     [rsp+68h+pdwType], rbp; pdwType
0x1802204b9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1802204c0  mov     cs:qword_1802DC638, rbp
0x1802204c7  mov     cs:qword_1802DC5F8, rbp
0x1802204ce  mov     cs:qword_1802DC600, rbp
0x1802204d5  mov     cs:qword_1802DC630, rbp
0x1802204dc  mov     cs:qword_1802DC608, rbp
0x1802204e3  mov     cs:qword_1802DC618, rbp
0x1802204ea  mov     cs:qword_1802DC5F0, rbp
0x1802204f1  mov     cs:qword_1802DC610, rbp
0x1802204f8  mov     cs:qword_1802DC628, rbp
0x1802204ff  call    cs:__imp_RegGetValueW
0x180220505  mov     ecx, eax
0x180220507  add     eax, 0FFFFFFFEh
0x18022050a  cmp     eax, ebx
0x18022050c  jbe     loc_180220703
0x180220512  test    ecx, ecx
0x180220514  jz      short loc_180220527
0x180220516  jg      short loc_18022051F
0x180220518  mov     ebx, ecx
0x18022051a  jmp     loc_1802206F9
0x18022051f  movzx   ebx, cx
0x180220522  jmp     loc_1802206F3
0x180220527  mov     ebx, [rsp+68h+arg_0]
0x18022052b  call    cs:__imp_GetProcessHeap
0x180220531  mov     r8d, ebx; dwBytes
0x180220534  mov     edx, 8; dwFlags
0x180220539  mov     rcx, rax; hHeap
0x18022053c  call    cs:__imp_HeapAlloc
0x180220542  mov     rdi, rax
0x180220545  test    rax, rax
0x180220548  jnz     short loc_180220554
0x18022054a  mov     ebx, 8007000Eh
0x18022054f  jmp     loc_180220708
0x180220554  lea     rax, [rsp+68h+arg_0]
0x180220559  mov     r9d, 10000002h; dwFlags
0x18022055f  mov     [rsp+68h+pcbData], rax; pcbData
0x180220564  lea     r8, aEdpcredlibprox; "EdpCredLibProxy"
0x18022056b  mov     [rsp+68h+pvData], rdi; pvData
0x180220570  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\EF"...
0x180220577  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18022057e  mov     [rsp+68h+pdwType], rbp; pdwType
0x180220583  call    cs:__imp_RegGetValueW
0x180220589  mov     ebx, eax
0x18022058b  test    eax, eax
0x18022058d  jnz     loc_1802206EE
0x180220593  xor     edx, edx; hFile
0x180220595  mov     r8d, 800h; dwFlags
0x18022059b  mov     rcx, rdi; lpLibFileName
0x18022059e  call    cs:__imp_LoadLibraryExW
0x1802205a4  mov     cs:hLibModule, rax
0x1802205ab  test    rax, rax
0x1802205ae  jz      loc_1802206E4
0x1802205b4  lea     rdx, aEdpcredentialc; "EdpCredentialCreate"
0x1802205bb  mov     rcx, rax; hModule
0x1802205be  call    cs:__imp_GetProcAddress
0x1802205c4  mov     cs:qword_1802DC638, rax
0x1802205cb  test    rax, rax
0x1802205ce  jz      loc_1802206E4
0x1802205d4  mov     rcx, cs:hLibModule; hModule
0x1802205db  lea     rdx, aEdpcredentialq; "EdpCredentialQuery"
0x1802205e2  call    cs:__imp_GetProcAddress
0x1802205e8  mov     cs:qword_1802DC5F8, rax
0x1802205ef  test    rax, rax
0x1802205f2  jz      loc_1802206E4
0x1802205f8  mov     rcx, cs:hLibModule; hModule
0x1802205ff  lea     rdx, aEdpcredentiale; "EdpCredentialExists"
0x180220606  call    cs:__imp_GetProcAddress
0x18022060c  mov     cs:qword_1802DC600, rax
0x180220613  test    rax, rax
0x180220616  jz      loc_1802206E4
0x18022061c  mov     rcx, cs:hLibModule; hModule
0x180220623  lea     rdx, aEdpcredentiald; "EdpCredentialDelete"
0x18022062a  call    cs:__imp_GetProcAddress
0x180220630  mov     cs:qword_1802DC630, rax
0x180220637  test    rax, rax
0x18022063a  jz      loc_1802206E4
0x180220640  mov     rcx, cs:hLibModule; hModule
0x180220647  lea     rdx, aEdpfree; "EdpFree"
0x18022064e  call    cs:__imp_GetProcAddress
0x180220654  mov     cs:qword_1802DC608, rax
0x18022065b  test    rax, rax
0x18022065e  jz      loc_1802206E4
0x180220664  mov     rcx, cs:hLibModule; hModule
0x18022066b  lea     rdx, aEdpquerycredse; "EdpQueryCredServiceInfo"
0x180220672  call    cs:__imp_GetProcAddress
0x180220678  mov     cs:qword_1802DC618, rax
0x18022067f  test    rax, rax
0x180220682  jz      short loc_1802206E4
0x180220684  mov     rcx, cs:hLibModule; hModule
0x18022068b  lea     rdx, aEdpsetcredserv; "EdpSetCredServiceInfo"
0x180220692  call    cs:__imp_GetProcAddress
0x180220698  mov     cs:qword_1802DC5F0, rax
0x18022069f  test    rax, rax
0x1802206a2  jz      short loc_1802206E4
0x1802206a4  mov     rcx, cs:hLibModule; hModule
0x1802206ab  lea     rdx, aEdpisconsumerd; "EdpIsConsumerDataProtectionSupported"
0x1802206b2  call    cs:__imp_GetProcAddress
0x1802206b8  mov     cs:qword_1802DC610, rax
0x1802206bf  test    rax, rax
0x1802206c2  jz      short loc_1802206E4
0x1802206c4  mov     rcx, cs:hLibModule; hModule
0x1802206cb  lea     rdx, aEdpisconsumerd_0; "EdpIsConsumerDataProtectionEnforced"
0x1802206d2  call    cs:__imp_GetProcAddress
0x1802206d8  mov     cs:qword_1802DC628, rax
0x1802206df  test    rax, rax
0x1802206e2  jnz     short loc_1802206FF
0x1802206e4  call    cs:__imp_GetLastError
0x1802206ea  test    eax, eax
0x1802206ec  mov     ebx, eax
0x1802206ee  jle     short loc_1802206F9
0x1802206f0  movzx   ebx, ax
0x1802206f3  or      ebx, 80070000h
0x1802206f9  test    ebx, ebx
0x1802206fb  jns     short loc_180220766
0x1802206fd  jmp     short loc_180220708
0x1802206ff  mov     ebx, ebp
0x180220701  jmp     short loc_180220766
0x180220703  mov     ebx, 80004001h
0x180220708  mov     rcx, cs:hLibModule; hLibModule
0x18022070f  mov     cs:dword_1802D9360, esi
0x180220715  mov     cs:qword_1802DC638, rbp
0x18022071c  mov     cs:qword_1802DC5F8, rbp
0x180220723  mov     cs:qword_1802DC600, rbp
0x18022072a  mov     cs:qword_1802DC630, rbp
0x180220731  mov     cs:qword_1802DC608, rbp
0x180220738  mov     cs:qword_1802DC618, rbp
0x18022073f  mov     cs:qword_1802DC5F0, rbp
0x180220746  mov     cs:qword_1802DC610, rbp
0x18022074d  mov     cs:qword_1802DC628, rbp
0x180220754  test    rcx, rcx
0x180220757  jz      short loc_180220766
0x180220759  call    cs:__imp_FreeLibrary
0x18022075f  mov     cs:hLibModule, rbp
0x180220766  lea     rcx, stru_1802DBCF8; lpCriticalSection
0x18022076d  call    cs:__imp_LeaveCriticalSection
0x180220773  test    rdi, rdi
0x180220776  jz      short loc_18022078C
0x180220778  call    cs:__imp_GetProcessHeap
0x18022077e  mov     r8, rdi; lpMem
0x180220781  xor     edx, edx; dwFlags
0x180220783  mov     rcx, rax; hHeap
0x180220786  call    cs:__imp_HeapFree
0x18022078c  mov     eax, ebx
0x18022078e  add     rsp, 48h
0x180220792  pop     rdi
0x180220793  pop     rsi
0x180220794  pop     rbp
0x180220795  pop     rbx
0x180220796  retn
```
