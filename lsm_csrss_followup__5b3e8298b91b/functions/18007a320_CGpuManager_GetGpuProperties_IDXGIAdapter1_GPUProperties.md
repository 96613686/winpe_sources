# CGpuManager::GetGpuProperties(IDXGIAdapter1 *,_GPUProperties *)

- ea: `0x18007a320`
- end: `0x18007a61a`
- name: `?GetGpuProperties@CGpuManager@@AEAAJPEAUIDXGIAdapter1@@PEAU_GPUProperties@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(CGpuManager *__hidden this, struct IDXGIAdapter1 *, struct _GPUProperties *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007a85c`

## callees

- `0x1800074c0`
- `0x18001aa50`
- `0x18004b460`
- `0x18004bf44`
- `0x18007a320`
- `0x18007ab30`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a58a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a5cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a58a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007a5cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a4c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a4c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a4b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a57c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a5c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a4b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a57c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a5c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a563`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007a482`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007a502`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007a482`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18007a502`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18007a455`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18007a455`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007a5f6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007a5f6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007a39f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18007a39f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007a3f0`
- `DEVOBJ!DevObjGetClassDevs` at `0x18007a3f0`

## string_xrefs

- `0x18007a55a`: `StringCchCopy failed: 0x%x in %s`
- `0x18007a3ca`: `DevObjCreateDeviceInfoList failed: 0x%x in %s`

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
0x18007a320  push    rbp
0x18007a322  push    rbx
0x18007a323  push    rsi
0x18007a324  push    r12
0x18007a326  push    r13
0x18007a328  push    r14
0x18007a32a  push    r15
0x18007a32c  mov     rbp, rsp
0x18007a32f  sub     rsp, 70h
0x18007a333  mov     rax, cs:__security_cookie
0x18007a33a  xor     rax, rsp
0x18007a33d  mov     [rbp+var_10], rax
0x18007a341  mov     rax, [rdx]
0x18007a344  mov     r9, rdx
0x18007a347  xorps   xmm0, xmm0
0x18007a34a  mov     r12, rcx
0x18007a34d  mov     rdx, r8
0x18007a350  mov     rcx, r9
0x18007a353  mov     r13, r8
0x18007a356  mov     rax, [rax+50h]
0x18007a35a  movups  [rbp+var_30], xmm0
0x18007a35e  movups  [rbp+var_20], xmm0
0x18007a362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a367  xor     r14d, r14d
0x18007a36a  mov     ebx, eax
0x18007a36c  test    eax, eax
0x18007a36e  jns     short loc_18007A390
0x18007a370  mov     r8d, eax
0x18007a373  lea     rdx, aGetdesc1Failed; "GetDesc1 failed: 0x%x in %s"
0x18007a37a  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007a381  mov     ecx, 8; int
0x18007a386  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007a38b  jmp     loc_18007A5FC
0x18007a390  xor     r9d, r9d
0x18007a393  mov     [rsp+70h+var_50], r14
0x18007a398  xor     r8d, r8d
0x18007a39b  xor     edx, edx
0x18007a39d  xor     ecx, ecx
0x18007a39f  call    cs:__imp_DevObjCreateDeviceInfoList
0x18007a3a5  mov     rsi, rax
0x18007a3a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a3ac  jnz     short loc_18007A3D3
0x18007a3ae  call    cs:__imp_GetLastError
0x18007a3b4  mov     ebx, eax
0x18007a3b6  test    eax, eax
0x18007a3b8  jle     short loc_18007A3C3
0x18007a3ba  movzx   ebx, ax
0x18007a3bd  or      ebx, 80070000h
0x18007a3c3  test    ebx, ebx
0x18007a3c5  jns     short loc_18007A3D3
0x18007a3c7  mov     r8d, ebx
0x18007a3ca  lea     rdx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed: 0x%x"...
0x18007a3d1  jmp     short loc_18007A37A
0x18007a3d3  mov     [rsp+70h+var_48], r14
0x18007a3d8  lea     rdx, GUID_DISPLAY_DEVICE_ARRIVAL
0x18007a3df  mov     r9d, 12h
0x18007a3e5  mov     [rsp+70h+var_50], r14
0x18007a3ea  xor     r8d, r8d
0x18007a3ed  mov     rcx, rsi
0x18007a3f0  call    cs:__imp_DevObjGetClassDevs
0x18007a3f6  test    eax, eax
0x18007a3f8  jnz     short loc_18007A433
0x18007a3fa  call    cs:__imp_GetLastError
0x18007a400  mov     ebx, eax
0x18007a402  test    eax, eax
0x18007a404  jle     short loc_18007A40F
0x18007a406  movzx   ebx, ax
0x18007a409  or      ebx, 80070000h
0x18007a40f  test    ebx, ebx
0x18007a411  jns     short loc_18007A433
0x18007a413  lea     rdx, aDevobjgetclass_0; "DevObjGetClassDevs failed: 0x%x in %s"
0x18007a41a  mov     r8d, ebx
0x18007a41d  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007a424  mov     ecx, 8; int
0x18007a429  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007a42e  jmp     loc_18007A5ED
0x18007a433  mov     r15d, r14d
0x18007a436  lea     rax, [rbp+var_30]
0x18007a43a  mov     dword ptr [rbp+var_30], 20h ; ' '
0x18007a441  mov     r9d, r15d
0x18007a444  mov     [rsp+70h+var_50], rax
0x18007a449  lea     r8, GUID_DISPLAY_DEVICE_ARRIVAL
0x18007a450  xor     edx, edx
0x18007a452  mov     rcx, rsi
0x18007a455  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18007a45b  test    eax, eax
0x18007a45d  jz      loc_18007A5E8
0x18007a463  lea     rax, [rbp+dwBytes]
0x18007a467  mov     [rsp+70h+var_48], r14
0x18007a46c  xor     r9d, r9d
0x18007a46f  mov     [rsp+70h+var_50], rax
0x18007a474  xor     r8d, r8d
0x18007a477  mov     dword ptr [rbp+dwBytes], r14d
0x18007a47b  lea     rdx, [rbp+var_30]
0x18007a47f  mov     rcx, rsi
0x18007a482  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18007a488  call    cs:__imp_GetLastError
0x18007a48e  cmp     eax, 7Ah ; 'z'
0x18007a491  jz      short loc_18007A4B0
0x18007a493  call    cs:__imp_GetLastError
0x18007a499  mov     ebx, eax
0x18007a49b  test    eax, eax
0x18007a49d  jle     short loc_18007A4A8
0x18007a49f  movzx   ebx, ax
0x18007a4a2  or      ebx, 80070000h
0x18007a4a8  test    ebx, ebx
0x18007a4aa  js      loc_18007A5DC
0x18007a4b0  mov     ebx, dword ptr [rbp+dwBytes]
0x18007a4b3  call    cs:__imp_GetProcessHeap
0x18007a4b9  mov     r8d, ebx; dwBytes
0x18007a4bc  xor     edx, edx; dwFlags
0x18007a4be  mov     rcx, rax; hHeap
0x18007a4c1  call    cs:__imp_HeapAlloc
0x18007a4c7  xor     ebx, ebx
0x18007a4c9  mov     r14, rax
0x18007a4cc  test    rax, rax
0x18007a4cf  jz      loc_18007A5D7
0x18007a4d5  mov     r8d, dword ptr [rbp+dwBytes]; Size
0x18007a4d9  xor     edx, edx; Val
0x18007a4db  mov     rcx, rax; void *
0x18007a4de  call    memset_0
0x18007a4e3  mov     dword ptr [r14], 8
0x18007a4ea  lea     rdx, [rbp+var_30]
0x18007a4ee  mov     r9d, dword ptr [rbp+dwBytes]
0x18007a4f2  mov     r8, r14
0x18007a4f5  mov     rcx, rsi
0x18007a4f8  mov     [rsp+70h+var_48], rbx
0x18007a4fd  mov     [rsp+70h+var_50], rbx
0x18007a502  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18007a508  test    eax, eax
0x18007a50a  jz      short loc_18007A563
0x18007a50c  lea     r8, [rbp+var_38]; struct _LUID *
0x18007a510  mov     qword ptr [rbp+var_38.LowPart], rbx
0x18007a514  lea     rdx, [r14+4]; unsigned __int16 *
0x18007a518  mov     rcx, r12; this
0x18007a51b  call    ?QueryAdapterLuidByDeviceName@CGpuManager@@AEAAJPEBGPEAU_LUID@@@Z; CGpuManager::QueryAdapterLuidByDeviceName(ushort const *,_LUID *)
0x18007a520  test    eax, eax
0x18007a522  js      short loc_18007A57C
0x18007a524  mov     eax, [r13+12Ch]
0x18007a52b  cmp     [rbp+var_38.HighPart], eax
0x18007a52e  jnz     short loc_18007A57C
0x18007a530  mov     eax, [r13+128h]
0x18007a537  cmp     [rbp+var_38.LowPart], eax
0x18007a53a  jnz     short loc_18007A57C
0x18007a53c  lea     rcx, [r13+138h]; unsigned __int16 *
0x18007a543  mov     edx, 400h; unsigned __int64
0x18007a548  lea     r8, [r14+4]; unsigned __int16 *
0x18007a54c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007a551  mov     ebx, eax
0x18007a553  test    eax, eax
0x18007a555  jns     short loc_18007A5C1
0x18007a557  mov     r8d, eax
0x18007a55a  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18007a561  jmp     short loc_18007A5B0
0x18007a563  call    cs:__imp_GetLastError
0x18007a569  mov     ebx, eax
0x18007a56b  test    eax, eax
0x18007a56d  jle     short loc_18007A578
0x18007a56f  movzx   ebx, ax
0x18007a572  or      ebx, 80070000h
0x18007a578  test    ebx, ebx
0x18007a57a  js      short loc_18007A5A6
0x18007a57c  call    cs:__imp_GetProcessHeap
0x18007a582  mov     r8, r14; lpMem
0x18007a585  xor     edx, edx; dwFlags
0x18007a587  mov     rcx, rax; hHeap
0x18007a58a  call    cs:__imp_HeapFree
0x18007a590  xorps   xmm0, xmm0
0x18007a593  inc     r15d
0x18007a596  movups  [rbp+var_30], xmm0
0x18007a59a  xor     r14d, r14d
0x18007a59d  movups  [rbp+var_20], xmm0
0x18007a5a1  jmp     loc_18007A436
0x18007a5a6  mov     r8d, ebx
0x18007a5a9  lea     rdx, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed: "...
0x18007a5b0  lea     r9, aCgpumanagerGet; "CGpuManager::GetGpuProperties"
0x18007a5b7  mov     ecx, 8; int
0x18007a5bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007a5c1  call    cs:__imp_GetProcessHeap
0x18007a5c7  mov     r8, r14; lpMem
0x18007a5ca  xor     edx, edx; dwFlags
0x18007a5cc  mov     rcx, rax; hHeap
0x18007a5cf  call    cs:__imp_HeapFree
0x18007a5d5  jmp     short loc_18007A5ED
0x18007a5d7  mov     ebx, 8007000Eh
0x18007a5dc  lea     rdx, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail failed: "...
0x18007a5e3  jmp     loc_18007A41A
0x18007a5e8  mov     ebx, 80070002h
0x18007a5ed  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007a5f1  jz      short loc_18007A5FC
0x18007a5f3  mov     rcx, rsi
0x18007a5f6  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18007a5fc  mov     eax, ebx
0x18007a5fe  mov     rcx, [rbp+var_10]
0x18007a602  xor     rcx, rsp; StackCookie
0x18007a605  call    __security_check_cookie
0x18007a60a  add     rsp, 70h
0x18007a60e  pop     r15
0x18007a610  pop     r14
0x18007a612  pop     r13
0x18007a614  pop     r12
0x18007a616  pop     rsi
0x18007a617  pop     rbx
0x18007a618  pop     rbp
0x18007a619  retn
```
