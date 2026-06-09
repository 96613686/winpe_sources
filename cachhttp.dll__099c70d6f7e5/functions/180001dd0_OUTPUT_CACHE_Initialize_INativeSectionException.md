# OUTPUT_CACHE::Initialize(INativeSectionException * *)

- ea: `0x180001dd0`
- end: `0x1800020be`
- name: `?Initialize@OUTPUT_CACHE@@QEAAJPEAPEAVINativeSectionException@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(OUTPUT_CACHE *__hidden this, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180001280`

## callees

- `0x180001dd0`
- `0x180008bbe`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001f97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001f97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001fc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002006`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001fc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000205a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000205a`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180001f2b`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180001f2b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002050`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002050`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180001e55`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180001e55`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180002072`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180002072`

## string_xrefs

- `0x180001ee1`: `maxCacheSize`
- `0x180001f84`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x180001fbd`: `OutputCacheTTL`

## pseudocode

```c
__int64 __fastcall OUTPUT_CACHE::Initialize(OUTPUT_CACHE *this, struct INativeSectionException **a2)
{
  PVOID v2; // rbx
  signed int v5; // esi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  __int64 v7; // rcx
  DWORDLONG ullAvailVirtual; // rcx
  int v9; // edi
  signed int LastError; // eax
  DWORD Type; // [rsp+40h] [rbp-39h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-35h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-31h] BYREF
  int v14; // [rsp+4Ch] [rbp-2Dh] BYREF
  __int64 v15; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+70h] [rbp-9h] BYREF

  v2 = g_pOutputCache;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  hKey = 0;
  v17 = 0;
  v15 = 0;
  v14 = 0;
  if ( *((_DWORD *)g_pOutputCache + 20) )
    return 0;
  v5 = 0;
  CLKRHashTable::WriteLock((CLKRHashTable *)g_pOutputCache);
  if ( !*((_DWORD *)v2 + 20) )
  {
    v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
    v5 = (**v6)(v6, &IID_INativeConfigurationSystem, &v17);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v17 + 24LL))(
             v17,
             L"system.webServer/caching",
             L"MACHINE/WEBROOT/APPHOST",
             &v15,
             a2,
             0);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
               v15,
               L"maxCacheSize",
               &v14,
               0,
               0);
        if ( v5 >= 0 )
        {
          v7 = (__int64)v14 << 20;
          *((_QWORD *)v2 + 12) = v7;
          if ( !v7 )
          {
            memset_0(&Buffer, 0, sizeof(Buffer));
            Buffer.dwLength = 64;
            GlobalMemoryStatusEx(&Buffer);
            ullAvailVirtual = Buffer.ullAvailVirtual;
            if ( Buffer.ullAvailPhys < Buffer.ullAvailVirtual )
              ullAvailVirtual = Buffer.ullAvailPhys;
            v7 = ullAvailVirtual >> 1;
          }
          *((_QWORD *)v2 + 11) = v7;
          v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 48LL))(
                 v15,
                 L"maxResponseSize",
                 (__int64)v2 + 84,
                 0,
                 0);
          if ( v5 >= 0 )
          {
            v9 = 30;
            if ( !RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
                    0,
                    0x20019u,
                    &hKey) )
            {
              if ( !RegQueryValueExW(hKey, L"OutputCacheTTL", 0, &Type, Data, &cbData) && Type == 4 )
                v9 = *(_DWORD *)Data;
              cbData = 4;
              if ( !RegQueryValueExW(hKey, L"FileAttributeCheckThreshold", 0, &Type, Data, &cbData) && Type == 4 )
                *((_DWORD *)v2 + 28) = 1000 * *(_DWORD *)Data;
              RegCloseKey(hKey);
            }
            if ( CreateTimerQueueTimer(
                   (PHANDLE)v2 + 9,
                   0,
                   OUTPUT_CACHE::ScavengerCallback,
                   v2,
                   1000 * v9,
                   1000 * v9,
                   0x10u) )
            {
              *((_DWORD *)v2 + 20) = 1;
            }
            else
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  CLKRHashTable::WriteUnlock((CLKRHashTable *)v2);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001dd0  mov     [rsp-8+arg_10], rbx
0x180001dd5  push    rbp
0x180001dd6  push    rdi
0x180001dd7  push    r14
0x180001dd9  lea     rbp, [rsp-47h]
0x180001dde  sub     rsp, 0C0h
0x180001de5  mov     rax, cs:__security_cookie
0x180001dec  xor     rax, rsp
0x180001def  mov     [rbp+57h+var_20], rax
0x180001df3  mov     rbx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180001dfa  xor     r14d, r14d
0x180001dfd  mov     rdi, rdx
0x180001e00  mov     dword ptr [rbp+57h+Data], r14d
0x180001e04  mov     [rbp+57h+Type], r14d
0x180001e08  mov     [rbp+57h+cbData], 4
0x180001e0f  mov     [rbp+57h+hKey], r14
0x180001e13  mov     [rbp+57h+var_70], r14
0x180001e17  mov     [rbp+57h+var_80], r14
0x180001e1b  mov     [rbp+57h+var_84], r14d
0x180001e1f  cmp     [rbx+50h], r14d
0x180001e23  jz      short loc_180001E47
0x180001e25  xor     eax, eax
0x180001e27  mov     rcx, [rbp+57h+var_20]
0x180001e2b  xor     rcx, rsp; StackCookie
0x180001e2e  call    __security_check_cookie
0x180001e33  mov     rbx, [rsp+0D0h+arg_10]
0x180001e3b  add     rsp, 0C0h
0x180001e42  pop     r14
0x180001e44  pop     rdi
0x180001e45  pop     rbp
0x180001e46  retn
0x180001e47  mov     [rsp+0D0h+arg_0], rsi
0x180001e4f  mov     rcx, rbx
0x180001e52  mov     esi, r14d
0x180001e55  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x180001e5b  cmp     [rbx+50h], r14d
0x180001e5f  jnz     loc_18000206F
0x180001e65  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001e6c  mov     rax, [rcx]
0x180001e6f  mov     rax, [rax+38h]
0x180001e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e78  mov     rcx, rax
0x180001e7b  lea     r8, [rbp+57h+var_70]
0x180001e7f  lea     rdx, IID_INativeConfigurationSystem
0x180001e86  mov     rax, [rax]
0x180001e89  mov     rax, [rax]
0x180001e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e91  mov     esi, eax
0x180001e93  test    eax, eax
0x180001e95  js      loc_18000206F
0x180001e9b  mov     rcx, [rbp+57h+var_70]
0x180001e9f  lea     r9, [rbp+57h+var_80]
0x180001ea3  mov     [rsp+0D0h+lpcbData], r14
0x180001ea8  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001eaf  lea     rdx, aSystemWebserve; "system.webServer/caching"
0x180001eb6  mov     [rsp+0D0h+phkResult], rdi
0x180001ebb  mov     rax, [rcx]
0x180001ebe  mov     rax, [rax+18h]
0x180001ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec7  mov     esi, eax
0x180001ec9  test    eax, eax
0x180001ecb  js      loc_18000206F
0x180001ed1  mov     rcx, [rbp+57h+var_80]
0x180001ed5  lea     r8, [rbp+57h+var_84]
0x180001ed9  xor     r9d, r9d
0x180001edc  mov     [rsp+0D0h+phkResult], r14
0x180001ee1  lea     rdx, aMaxcachesize; "maxCacheSize"
0x180001ee8  mov     rax, [rcx]
0x180001eeb  mov     rax, [rax+30h]
0x180001eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef4  mov     esi, eax
0x180001ef6  test    eax, eax
0x180001ef8  js      loc_18000206F
0x180001efe  movsxd  rcx, [rbp+57h+var_84]
0x180001f02  shl     rcx, 14h
0x180001f06  mov     [rbx+60h], rcx
0x180001f0a  test    rcx, rcx
0x180001f0d  jnz     short loc_180001F41
0x180001f0f  xor     edx, edx; Val
0x180001f11  lea     rcx, [rbp+57h+Buffer]; void *
0x180001f15  mov     r8d, 40h ; '@'; Size
0x180001f1b  call    memset_0
0x180001f20  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x180001f24  mov     [rbp+57h+Buffer.dwLength], 40h ; '@'
0x180001f2b  call    cs:__imp_GlobalMemoryStatusEx
0x180001f31  mov     rcx, [rbp+57h+Buffer.ullAvailVirtual]
0x180001f35  cmp     [rbp+57h+Buffer.ullAvailPhys], rcx
0x180001f39  cmovb   rcx, [rbp+57h+Buffer.ullAvailPhys]
0x180001f3e  shr     rcx, 1
0x180001f41  mov     [rbx+58h], rcx
0x180001f45  lea     r8, [rbx+54h]
0x180001f49  mov     rcx, [rbp+57h+var_80]
0x180001f4d  lea     rdx, aMaxresponsesiz; "maxResponseSize"
0x180001f54  xor     r9d, r9d
0x180001f57  mov     [rsp+0D0h+phkResult], r14
0x180001f5c  mov     rax, [rcx]
0x180001f5f  mov     rax, [rax+30h]
0x180001f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f68  mov     esi, eax
0x180001f6a  test    eax, eax
0x180001f6c  js      loc_18000206F
0x180001f72  lea     rax, [rbp+57h+hKey]
0x180001f76  mov     r9d, 20019h; samDesired
0x180001f7c  xor     r8d, r8d; ulOptions
0x180001f7f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180001f84  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x180001f8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001f92  mov     edi, 1Eh
0x180001f97  call    cs:__imp_RegOpenKeyExW
0x180001f9d  test    eax, eax
0x180001f9f  jnz     loc_18000202A
0x180001fa5  mov     rcx, [rbp+57h+hKey]; hKey
0x180001fa9  lea     rax, [rbp+57h+cbData]
0x180001fad  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180001fb2  lea     r9, [rbp+57h+Type]; lpType
0x180001fb6  lea     rax, [rbp+57h+Data]
0x180001fba  xor     r8d, r8d; lpReserved
0x180001fbd  lea     rdx, ValueName; "OutputCacheTTL"
0x180001fc4  mov     [rsp+0D0h+phkResult], rax; lpData
0x180001fc9  call    cs:__imp_RegQueryValueExW
0x180001fcf  test    eax, eax
0x180001fd1  jnz     short loc_180001FDB
0x180001fd3  cmp     [rbp+57h+Type], 4
0x180001fd7  cmovz   edi, dword ptr [rbp+57h+Data]
0x180001fdb  mov     rcx, [rbp+57h+hKey]; hKey
0x180001fdf  lea     rax, [rbp+57h+cbData]
0x180001fe3  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180001fe8  lea     r9, [rbp+57h+Type]; lpType
0x180001fec  lea     rax, [rbp+57h+Data]
0x180001ff0  mov     [rbp+57h+cbData], 4
0x180001ff7  xor     r8d, r8d; lpReserved
0x180001ffa  mov     [rsp+0D0h+phkResult], rax; lpData
0x180001fff  lea     rdx, aFileattributec; "FileAttributeCheckThreshold"
0x180002006  call    cs:__imp_RegQueryValueExW
0x18000200c  test    eax, eax
0x18000200e  jnz     short loc_180002020
0x180002010  cmp     [rbp+57h+Type], 4
0x180002014  jnz     short loc_180002020
0x180002016  imul    eax, dword ptr [rbp+57h+Data], 3E8h
0x18000201d  mov     [rbx+70h], eax
0x180002020  mov     rcx, [rbp+57h+hKey]; hKey
0x180002024  call    cs:__imp_RegCloseKey
0x18000202a  imul    eax, edi, 3E8h
0x180002030  lea     rcx, [rbx+48h]; phNewTimer
0x180002034  mov     [rsp+0D0h+Flags], 10h; Flags
0x18000203c  lea     r8, ?ScavengerCallback@OUTPUT_CACHE@@CAXPEAXE@Z; Callback
0x180002043  mov     r9, rbx; Parameter
0x180002046  xor     edx, edx; TimerQueue
0x180002048  mov     dword ptr [rsp+0D0h+lpcbData], eax; Period
0x18000204c  mov     dword ptr [rsp+0D0h+phkResult], eax; DueTime
0x180002050  call    cs:__imp_CreateTimerQueueTimer
0x180002056  test    eax, eax
0x180002058  jnz     short loc_1800020B5
0x18000205a  call    cs:__imp_GetLastError
0x180002060  mov     esi, eax
0x180002062  test    eax, eax
0x180002064  jle     short loc_18000206F
0x180002066  movzx   esi, ax
0x180002069  or      esi, 80070000h
0x18000206f  mov     rcx, rbx
0x180002072  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x180002078  mov     rcx, [rbp+57h+var_80]
0x18000207c  test    rcx, rcx
0x18000207f  jz      short loc_180002091
0x180002081  mov     rax, [rcx]
0x180002084  mov     rax, [rax+10h]
0x180002088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000208d  mov     [rbp+57h+var_80], r14
0x180002091  mov     rcx, [rbp+57h+var_70]
0x180002095  test    rcx, rcx
0x180002098  jz      short loc_1800020A6
0x18000209a  mov     rax, [rcx]
0x18000209d  mov     rax, [rax+10h]
0x1800020a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020a6  mov     eax, esi
0x1800020a8  mov     rsi, [rsp+0D0h+arg_0]
0x1800020b0  jmp     loc_180001E27
0x1800020b5  mov     dword ptr [rbx+50h], 1
0x1800020bc  jmp     short loc_18000206F
```
