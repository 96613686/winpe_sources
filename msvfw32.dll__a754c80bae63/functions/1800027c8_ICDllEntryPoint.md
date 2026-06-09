# ICDllEntryPoint

- ea: `0x1800027c8`
- end: `0x1800029aa`
- name: `ICDllEntryPoint`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x1800027c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800027f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800027f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000295c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000295c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002943`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000283b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000283b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000287a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000287a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002977`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002977`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000296e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002984`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000296e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002984`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000298d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000298d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002900`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028ef`

## pseudocode

```c
__int64 __fastcall ICDllEntryPoint(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // ecx
  SIZE_T v4; // rbx
  HANDLE ProcessHeap; // rax
  HGLOBAL v6; // rax
  HGLOBAL v7; // rax
  __int64 Type; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  __int64 cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  cbData = a3;
  Type = a1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      InitializeCriticalSection(&ICOpenCritSec);
      if ( !giMaxConverters && !gfCheckedMaxConverters )
      {
        hKey = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\VFW", 0, 1u, &hKey) )
        {
          LODWORD(Type) = 0;
          LODWORD(cbData) = 0;
          Data = 75;
          if ( !RegQueryValueExW(hKey, L"MaxVFWConverters", 0, (LPDWORD)&Type, 0, (LPDWORD)&cbData)
            && (_DWORD)Type == 4
            && (_DWORD)cbData == 4
            && !RegQueryValueExW(hKey, L"MaxVFWConverters", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
          {
            v3 = Data;
            if ( Data > 0x258 )
            {
              v3 = 600;
              Data = 600;
            }
            if ( v3 - 76 <= 0x20C )
            {
              v4 = 48LL * v3;
              ProcessHeap = GetProcessHeap();
              paicConverters = (__int64 (*)[452])HeapAlloc(ProcessHeap, 8u, v4);
              if ( paicConverters )
              {
                g_max_converters = Data;
              }
              else
              {
                g_max_converters = 75;
                paicConverters = (__int64 (*)[452])aicConverters;
              }
              giMaxConverters = 0;
            }
          }
          RegCloseKey(hKey);
        }
        gfCheckedMaxConverters = 1;
      }
    }
  }
  else
  {
    DeleteCriticalSection(&ICOpenCritSec);
    if ( pMem )
    {
      v6 = GlobalHandle(pMem);
      GlobalUnlock(v6);
      v7 = GlobalHandle(pMem);
      GlobalFree(v7);
      pMem = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800027c8  mov     [rsp-10h+cbData], r8
0x1800027cd  mov     [rsp-10h+Type], rcx
0x1800027d2  push    rbp
0x1800027d3  push    rbx
0x1800027d4  mov     rbp, rsp
0x1800027d7  sub     rsp, 38h
0x1800027db  test    edx, edx
0x1800027dd  jz      loc_180002955
0x1800027e3  cmp     edx, 1
0x1800027e6  jnz     loc_18000299E
0x1800027ec  lea     rcx, ICOpenCritSec; lpCriticalSection
0x1800027f3  call    cs:__imp_InitializeCriticalSection
0x1800027f9  cmp     cs:giMaxConverters, 0
0x180002800  jnz     loc_18000299E
0x180002806  cmp     cs:gfCheckedMaxConverters, 0
0x18000280d  jnz     loc_18000299E
0x180002813  lea     rax, [rbp+hKey]
0x180002817  mov     [rbp+hKey], 0
0x18000281f  mov     r9d, 1; samDesired
0x180002825  mov     [rsp+38h+phkResult], rax; phkResult
0x18000282a  xor     r8d, r8d; ulOptions
0x18000282d  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002834  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000283b  call    cs:__imp_RegOpenKeyExW
0x180002841  test    eax, eax
0x180002843  jnz     loc_180002949
0x180002849  mov     rcx, [rbp+hKey]; hKey
0x18000284d  lea     r9, [rbp+Type]; lpType
0x180002851  mov     dword ptr [rbp+Type], eax
0x180002854  lea     rdx, ValueName; "MaxVFWConverters"
0x18000285b  mov     dword ptr [rbp+cbData], eax
0x18000285e  xor     r8d, r8d; lpReserved
0x180002861  lea     rax, [rbp+cbData]
0x180002865  mov     [rbp+Data], 4Bh ; 'K'
0x18000286c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180002871  mov     [rsp+38h+phkResult], 0; lpData
0x18000287a  call    cs:__imp_RegQueryValueExW
0x180002880  test    eax, eax
0x180002882  jnz     loc_18000293F
0x180002888  cmp     dword ptr [rbp+Type], 4
0x18000288c  jnz     loc_18000293F
0x180002892  cmp     dword ptr [rbp+cbData], 4
0x180002896  jnz     loc_18000293F
0x18000289c  mov     rcx, [rbp+hKey]; hKey
0x1800028a0  lea     rax, [rbp+cbData]
0x1800028a4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800028a9  lea     r9, [rbp+Type]; lpType
0x1800028ad  lea     rax, [rbp+Data]
0x1800028b1  xor     r8d, r8d; lpReserved
0x1800028b4  lea     rdx, ValueName; "MaxVFWConverters"
0x1800028bb  mov     [rsp+38h+phkResult], rax; lpData
0x1800028c0  call    cs:__imp_RegQueryValueExW
0x1800028c6  test    eax, eax
0x1800028c8  jnz     short loc_18000293F
0x1800028ca  mov     ecx, [rbp+Data]
0x1800028cd  mov     eax, 258h
0x1800028d2  cmp     ecx, eax
0x1800028d4  jbe     short loc_1800028DB
0x1800028d6  mov     ecx, eax
0x1800028d8  mov     [rbp+Data], eax
0x1800028db  lea     eax, [rcx-4Ch]
0x1800028de  cmp     eax, 20Ch
0x1800028e3  ja      short loc_18000293F
0x1800028e5  mov     eax, ecx
0x1800028e7  lea     rbx, [rax+rax*2]
0x1800028eb  shl     rbx, 4
0x1800028ef  call    cs:__imp_GetProcessHeap
0x1800028f5  mov     r8, rbx; dwBytes
0x1800028f8  mov     edx, 8; dwFlags
0x1800028fd  mov     rcx, rax; hHeap
0x180002900  call    cs:__imp_HeapAlloc
0x180002906  mov     cs:paicConverters, rax
0x18000290d  test    rax, rax
0x180002910  jnz     short loc_18000292C
0x180002912  lea     rax, aicConverters
0x180002919  mov     cs:g_max_converters, 4Bh ; 'K'
0x180002923  mov     cs:paicConverters, rax
0x18000292a  jmp     short loc_180002935
0x18000292c  mov     eax, [rbp+Data]
0x18000292f  mov     cs:g_max_converters, eax
0x180002935  mov     cs:giMaxConverters, 0
0x18000293f  mov     rcx, [rbp+hKey]; hKey
0x180002943  call    cs:__imp_RegCloseKey
0x180002949  mov     cs:gfCheckedMaxConverters, 1
0x180002953  jmp     short loc_18000299E
0x180002955  lea     rcx, ICOpenCritSec; lpCriticalSection
0x18000295c  call    cs:__imp_DeleteCriticalSection
0x180002962  mov     rcx, cs:pMem; pMem
0x180002969  test    rcx, rcx
0x18000296c  jz      short loc_18000299E
0x18000296e  call    cs:__imp_GlobalHandle
0x180002974  mov     rcx, rax; hMem
0x180002977  call    cs:__imp_GlobalUnlock
0x18000297d  mov     rcx, cs:pMem; pMem
0x180002984  call    cs:__imp_GlobalHandle
0x18000298a  mov     rcx, rax; hMem
0x18000298d  call    cs:__imp_GlobalFree
0x180002993  mov     cs:pMem, 0
0x18000299e  mov     eax, 1
0x1800029a3  add     rsp, 38h
0x1800029a7  pop     rbx
0x1800029a8  pop     rbp
0x1800029a9  retn
```
