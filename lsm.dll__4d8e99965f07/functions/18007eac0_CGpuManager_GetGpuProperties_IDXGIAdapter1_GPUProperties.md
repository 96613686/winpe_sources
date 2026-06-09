# CGpuManager::GetGpuProperties(IDXGIAdapter1 *,_GPUProperties *)

- ea: `0x18007eac0`
- end: `0x18007ee21`
- name: `?GetGpuProperties@CGpuManager@@AEAAJPEAUIDXGIAdapter1@@PEAU_GPUProperties@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(CGpuManager *__hidden this, struct IDXGIAdapter1 *, struct _GPUProperties *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007f064`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18004e850`
- `0x18004f354`
- `0x18007eac0`
- `0x18007f348`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007ed78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007edc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007ed78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007edc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ec97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ec97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ec83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ed64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007edb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ec83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ed64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007edb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ebac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ed45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007eb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ebac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ec5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ed45`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007ec40`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007ecde`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007ec40`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007ecde`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18007ec0d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18007ec0d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007edf6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007edf6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007eb3f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007eb3f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007eb9c`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007eb9c`

## string_xrefs

- `0x18007ed3c`: `StringCchCopy failed: 0x%x in %s`
- `0x18007eb76`: `DevObjCreateDeviceInfoList failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CGpuManager::GetGpuProperties(
        CGpuManager *this,
        struct IDXGIAdapter1 *a2,
        struct _GPUProperties *a3)
{
  HRESULT (__stdcall *GetDesc1)(IDXGIAdapter1 *, DXGI_ADAPTER_DESC1 *); // rax
  int v6; // eax
  signed int v7; // ebx
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  signed int v10; // eax
  unsigned int i; // r15d
  signed int v12; // eax
  unsigned int v13; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r14
  int v17; // eax
  signed int v18; // eax
  HANDLE v19; // rax
  HANDLE v20; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-40h] BYREF
  struct _LUID v23; // [rsp+38h] [rbp-38h] BYREF
  __int128 v24; // [rsp+40h] [rbp-30h] BYREF
  __int128 v25; // [rsp+50h] [rbp-20h]

  GetDesc1 = a2->lpVtbl->GetDesc1;
  v24 = 0;
  v25 = 0;
  v6 = ((__int64 (__fastcall *)(struct IDXGIAdapter1 *, struct _GPUProperties *))GetDesc1)(a2, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    if ( DeviceInfoList != -1 )
      goto LABEL_12;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      _DbgPrintMessage(
        8,
        "DevObjCreateDeviceInfoList failed: 0x%x in %s",
        (unsigned int)v7,
        "CGpuManager::GetGpuProperties");
    }
    else
    {
LABEL_12:
      if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DISPLAY_DEVICE_ARRIVAL, 0, 18, 0, 0) )
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 < 0 )
        {
          _DbgPrintMessage(
            8,
            "DevObjGetClassDevs failed: 0x%x in %s",
            (unsigned int)v7,
            "CGpuManager::GetGpuProperties");
          goto LABEL_37;
        }
      }
      for ( i = 0; ; ++i )
      {
        LODWORD(v24) = 32;
        if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DISPLAY_DEVICE_ARRIVAL, i, &v24) )
        {
          v7 = -2147024894;
          goto LABEL_37;
        }
        LODWORD(dwBytes) = 0;
        DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v24, 0, 0, &dwBytes, 0);
        if ( GetLastError() != 122 )
        {
          v12 = GetLastError();
          v7 = v12;
          if ( v12 > 0 )
            v7 = (unsigned __int16)v12 | 0x80070000;
          if ( v7 < 0 )
            goto LABEL_35;
        }
        v13 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v13);
        v16 = v15;
        if ( !v15 )
          break;
        memset_0(v15, 0, (unsigned int)dwBytes);
        *(_DWORD *)v16 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v24, v16, (unsigned int)dwBytes, 0, 0) )
        {
          v23 = 0;
          if ( (int)CGpuManager::QueryAdapterLuidByDeviceName(this, v16 + 2, &v23) >= 0
            && v23.HighPart == *((_DWORD *)a3 + 75)
            && v23.LowPart == *((_DWORD *)a3 + 74) )
          {
            v17 = StringCchCopyW((unsigned __int16 *)a3 + 156, 0x400u, v16 + 2);
            v7 = v17;
            if ( v17 < 0 )
              _DbgPrintMessage(
                8,
                "StringCchCopy failed: 0x%x in %s",
                (unsigned int)v17,
                "CGpuManager::GetGpuProperties");
            goto LABEL_33;
          }
        }
        else
        {
          v18 = GetLastError();
          v7 = v18;
          if ( v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
          if ( v7 < 0 )
          {
            _DbgPrintMessage(
              8,
              "DevObjGetDeviceInterfaceDetail failed: 0x%x in %s",
              (unsigned int)v7,
              "CGpuManager::GetGpuProperties");
LABEL_33:
            v20 = GetProcessHeap();
            HeapFree(v20, 0, v16);
            goto LABEL_37;
          }
        }
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v16);
        v24 = 0;
        v25 = 0;
      }
      v7 = -2147024882;
LABEL_35:
      _DbgPrintMessage(
        8,
        "DevObjGetDeviceInterfaceDetail failed: 0x%x in %s",
        (unsigned int)v7,
        "CGpuManager::GetGpuProperties");
LABEL_37:
      if ( DeviceInfoList != -1 )
        DevObjDestroyDeviceInfoList(DeviceInfoList);
    }
  }
  else
  {
    _DbgPrintMessage(8, "GetDesc1 failed: 0x%x in %s", (unsigned int)v6, "CGpuManager::GetGpuProperties");
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007eac0  push    rbp
0x18007eac2  push    rbx
0x18007eac3  push    rsi
0x18007eac4  push    r12
0x18007eac6  push    r13
0x18007eac8  push    r14
0x18007eaca  push    r15
0x18007eacc  mov     rbp, rsp
0x18007eacf  sub     rsp, 70h
0x18007ead3  mov     rax, cs:__security_cookie
0x18007eada  xor     rax, rsp
0x18007eadd  mov     [rbp+var_10], rax
0x18007eae1  mov     rax, [rdx]
0x18007eae4  mov     r9, rdx
0x18007eae7  xorps   xmm0, xmm0
0x18007eaea  mov     r12, rcx
0x18007eaed  mov     rdx, r8
0x18007eaf0  mov     rcx, r9
0x18007eaf3  mov     r13, r8
0x18007eaf6  mov     rax, [rax+50h]
0x18007eafa  movups  [rbp+var_30], xmm0
0x18007eafe  movups  [rbp+var_20], xmm0
0x18007eb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb07  xor     r14d, r14d
0x18007eb0a  mov     ebx, eax
0x18007eb0c  test    eax, eax
0x18007eb0e  jns     short loc_18007EB30
0x18007eb10  mov     r8d, eax
0x18007eb13  lea     rdx, aGetdesc1Failed; "GetDesc1 failed: 0x%x in %s"
0x18007eb1a  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007eb21  mov     ecx, 8; int
0x18007eb26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007eb2b  jmp     loc_18007EE02
0x18007eb30  xor     r9d, r9d
0x18007eb33  mov     [rsp+70h+var_50], r14
0x18007eb38  xor     r8d, r8d
0x18007eb3b  xor     edx, edx
0x18007eb3d  xor     ecx, ecx
0x18007eb3f  call    cs:__imp_DevObjCreateDeviceInfoList
0x18007eb46  nop     dword ptr [rax+rax+00h]
0x18007eb4b  mov     rsi, rax
0x18007eb4e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007eb52  jnz     short loc_18007EB7F
0x18007eb54  call    cs:__imp_GetLastError
0x18007eb5b  nop     dword ptr [rax+rax+00h]
0x18007eb60  mov     ebx, eax
0x18007eb62  test    eax, eax
0x18007eb64  jle     short loc_18007EB6F
0x18007eb66  movzx   ebx, ax
0x18007eb69  or      ebx, 80070000h
0x18007eb6f  test    ebx, ebx
0x18007eb71  jns     short loc_18007EB7F
0x18007eb73  mov     r8d, ebx
0x18007eb76  lea     rdx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed: 0x%x"...
0x18007eb7d  jmp     short loc_18007EB1A
0x18007eb7f  mov     [rsp+70h+var_48], r14
0x18007eb84  lea     rdx, GUID_DISPLAY_DEVICE_ARRIVAL
0x18007eb8b  mov     r9d, 12h
0x18007eb91  mov     [rsp+70h+var_50], r14
0x18007eb96  xor     r8d, r8d
0x18007eb99  mov     rcx, rsi
0x18007eb9c  call    cs:__imp_DevObjGetClassDevs
0x18007eba3  nop     dword ptr [rax+rax+00h]
0x18007eba8  test    eax, eax
0x18007ebaa  jnz     short loc_18007EBEB
0x18007ebac  call    cs:__imp_GetLastError
0x18007ebb3  nop     dword ptr [rax+rax+00h]
0x18007ebb8  mov     ebx, eax
0x18007ebba  test    eax, eax
0x18007ebbc  jle     short loc_18007EBC7
0x18007ebbe  movzx   ebx, ax
0x18007ebc1  or      ebx, 80070000h
0x18007ebc7  test    ebx, ebx
0x18007ebc9  jns     short loc_18007EBEB
0x18007ebcb  lea     rdx, aDevobjgetclass_0; "DevObjGetClassDevs failed: 0x%x in %s"
0x18007ebd2  mov     r8d, ebx
0x18007ebd5  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007ebdc  mov     ecx, 8; int
0x18007ebe1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007ebe6  jmp     loc_18007EDED
0x18007ebeb  mov     r15d, r14d
0x18007ebee  lea     rax, [rbp+var_30]
0x18007ebf2  mov     dword ptr [rbp+var_30], 20h ; ' '
0x18007ebf9  mov     r9d, r15d
0x18007ebfc  mov     [rsp+70h+var_50], rax
0x18007ec01  lea     r8, GUID_DISPLAY_DEVICE_ARRIVAL
0x18007ec08  xor     edx, edx
0x18007ec0a  mov     rcx, rsi
0x18007ec0d  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18007ec14  nop     dword ptr [rax+rax+00h]
0x18007ec19  test    eax, eax
0x18007ec1b  jz      loc_18007EDE8
0x18007ec21  lea     rax, [rbp+dwBytes]
0x18007ec25  mov     [rsp+70h+var_48], r14
0x18007ec2a  xor     r9d, r9d
0x18007ec2d  mov     [rsp+70h+var_50], rax
0x18007ec32  xor     r8d, r8d
0x18007ec35  mov     dword ptr [rbp+dwBytes], r14d
0x18007ec39  lea     rdx, [rbp+var_30]
0x18007ec3d  mov     rcx, rsi
0x18007ec40  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18007ec47  nop     dword ptr [rax+rax+00h]
0x18007ec4c  call    cs:__imp_GetLastError
0x18007ec53  nop     dword ptr [rax+rax+00h]
0x18007ec58  cmp     eax, 7Ah ; 'z'
0x18007ec5b  jz      short loc_18007EC80
0x18007ec5d  call    cs:__imp_GetLastError
0x18007ec64  nop     dword ptr [rax+rax+00h]
0x18007ec69  mov     ebx, eax
0x18007ec6b  test    eax, eax
0x18007ec6d  jle     short loc_18007EC78
0x18007ec6f  movzx   ebx, ax
0x18007ec72  or      ebx, 80070000h
0x18007ec78  test    ebx, ebx
0x18007ec7a  js      loc_18007EDDC
0x18007ec80  mov     ebx, dword ptr [rbp+dwBytes]
0x18007ec83  call    cs:__imp_GetProcessHeap
0x18007ec8a  nop     dword ptr [rax+rax+00h]
0x18007ec8f  mov     r8d, ebx; dwBytes
0x18007ec92  xor     edx, edx; dwFlags
0x18007ec94  mov     rcx, rax; hHeap
0x18007ec97  call    cs:__imp_HeapAlloc
0x18007ec9e  nop     dword ptr [rax+rax+00h]
0x18007eca3  xor     ebx, ebx
0x18007eca5  mov     r14, rax
0x18007eca8  test    rax, rax
0x18007ecab  jz      loc_18007EDD7
0x18007ecb1  mov     r8d, dword ptr [rbp+dwBytes]; Size
0x18007ecb5  xor     edx, edx; Val
0x18007ecb7  mov     rcx, rax; void *
0x18007ecba  call    memset_0
0x18007ecbf  mov     dword ptr [r14], 8
0x18007ecc6  lea     rdx, [rbp+var_30]
0x18007ecca  mov     r9d, dword ptr [rbp+dwBytes]
0x18007ecce  mov     r8, r14
0x18007ecd1  mov     rcx, rsi
0x18007ecd4  mov     [rsp+70h+var_48], rbx
0x18007ecd9  mov     [rsp+70h+var_50], rbx
0x18007ecde  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18007ece5  nop     dword ptr [rax+rax+00h]
0x18007ecea  test    eax, eax
0x18007ecec  jz      short loc_18007ED45
0x18007ecee  lea     r8, [rbp+var_38]; struct _LUID *
0x18007ecf2  mov     qword ptr [rbp+var_38.LowPart], rbx
0x18007ecf6  lea     rdx, [r14+4]; unsigned __int16 *
0x18007ecfa  mov     rcx, r12; this
0x18007ecfd  call    ?QueryAdapterLuidByDeviceName@CGpuManager@@AEAAJPEBGPEAU_LUID@@@Z; CGpuManager::QueryAdapterLuidByDeviceName(ushort const *,_LUID *)
0x18007ed02  test    eax, eax
0x18007ed04  js      short loc_18007ED64
0x18007ed06  mov     eax, [r13+12Ch]
0x18007ed0d  cmp     [rbp+var_38.HighPart], eax
0x18007ed10  jnz     short loc_18007ED64
0x18007ed12  mov     eax, [r13+128h]
0x18007ed19  cmp     [rbp+var_38.LowPart], eax
0x18007ed1c  jnz     short loc_18007ED64
0x18007ed1e  lea     rcx, [r13+138h]; unsigned __int16 *
0x18007ed25  mov     edx, 400h; unsigned __int64
0x18007ed2a  lea     r8, [r14+4]; unsigned __int16 *
0x18007ed2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007ed33  mov     ebx, eax
0x18007ed35  test    eax, eax
0x18007ed37  jns     short loc_18007EDB5
0x18007ed39  mov     r8d, eax
0x18007ed3c  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18007ed43  jmp     short loc_18007EDA4
0x18007ed45  call    cs:__imp_GetLastError
0x18007ed4c  nop     dword ptr [rax+rax+00h]
0x18007ed51  mov     ebx, eax
0x18007ed53  test    eax, eax
0x18007ed55  jle     short loc_18007ED60
0x18007ed57  movzx   ebx, ax
0x18007ed5a  or      ebx, 80070000h
0x18007ed60  test    ebx, ebx
0x18007ed62  js      short loc_18007ED9A
0x18007ed64  call    cs:__imp_GetProcessHeap
0x18007ed6b  nop     dword ptr [rax+rax+00h]
0x18007ed70  mov     r8, r14; lpMem
0x18007ed73  xor     edx, edx; dwFlags
0x18007ed75  mov     rcx, rax; hHeap
0x18007ed78  call    cs:__imp_HeapFree
0x18007ed7f  nop     dword ptr [rax+rax+00h]
0x18007ed84  xorps   xmm0, xmm0
0x18007ed87  inc     r15d
0x18007ed8a  movups  [rbp+var_30], xmm0
0x18007ed8e  xor     r14d, r14d
0x18007ed91  movups  [rbp+var_20], xmm0
0x18007ed95  jmp     loc_18007EBEE
0x18007ed9a  mov     r8d, ebx
0x18007ed9d  lea     rdx, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed: "...
0x18007eda4  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007edab  mov     ecx, 8; int
0x18007edb0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007edb5  call    cs:__imp_GetProcessHeap
0x18007edbc  nop     dword ptr [rax+rax+00h]
0x18007edc1  mov     r8, r14; lpMem
0x18007edc4  xor     edx, edx; dwFlags
0x18007edc6  mov     rcx, rax; hHeap
0x18007edc9  call    cs:__imp_HeapFree
0x18007edd0  nop     dword ptr [rax+rax+00h]
0x18007edd5  jmp     short loc_18007EDED
0x18007edd7  mov     ebx, 8007000Eh
0x18007eddc  lea     rdx, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed: "...
0x18007ede3  jmp     loc_18007EBD2
0x18007ede8  mov     ebx, 80070002h
0x18007eded  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007edf1  jz      short loc_18007EE02
0x18007edf3  mov     rcx, rsi
0x18007edf6  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18007edfd  nop     dword ptr [rax+rax+00h]
0x18007ee02  mov     eax, ebx
0x18007ee04  mov     rcx, [rbp+var_10]
0x18007ee08  xor     rcx, rsp; StackCookie
0x18007ee0b  call    __security_check_cookie
0x18007ee10  add     rsp, 70h
0x18007ee14  pop     r15
0x18007ee16  pop     r14
0x18007ee18  pop     r13
0x18007ee1a  pop     r12
0x18007ee1c  pop     rsi
0x18007ee1d  pop     rbx
0x18007ee1e  pop     rbp
0x18007ee1f  retn
```
