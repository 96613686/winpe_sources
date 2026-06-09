# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x1401bf4b8`
- end: `0x1401bf794`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x1401bf1f0`

## callees

- `0x1401bf1a4`
- `0x1401bf4b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf516`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf6b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf71d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf754`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf516`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf6b0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf71d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bf754`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1401bf6f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1401bf6f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401bf529`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401bf529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bf537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bf537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf57c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf5bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf57c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf5bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bf700`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1401bf5ac`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1401bf5ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf5c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf64d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf6a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf6ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf5c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf64d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf6a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401bf6ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bf56d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401bf56d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bf6de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401bf6de`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bf606`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bf68e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bf606`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1401bf68e`

## string_xrefs

- `0x1401bf6d7`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-30h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 == 259 )
      goto LABEL_17;
    if ( v19 && v19 != 234 )
    {
LABEL_10:
      CloseHandle(EventW);
      RegCloseKey(hKeya);
      goto LABEL_6;
    }
    if ( cbData )
    {
      if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v11, cbData) )
      {
        v18 = -2147024882;
LABEL_17:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        return v18;
      }
      lpData = (BYTE *)*v11;
      cchValueName = 260;
      v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
      if ( v17 )
      {
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        free(*v11);
        *v11 = 0;
LABEL_6:
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return v17;
      }
    }
    v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
    RegCloseKey(hKeya);
    v20 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v20 )
    {
      v17 = -2147023590;
LABEL_29:
      free(*v11);
      *v11 = 0;
      *a4 = 0;
      return v17;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        free(*v11);
        *v11 = 0;
        *a4 = 0;
        if ( v18 > 0 )
          return (unsigned __int16)v18 | 0x80070000;
        return v18;
      }
    }
    else if ( v23 == 6 )
    {
      v17 = -2147023432;
      goto LABEL_29;
    }
    *v8 = Type;
    *v9 = cbData;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1401bf4b8  mov     [rsp-38h+arg_0], rbx
0x1401bf4bd  mov     [rsp-38h+dwIndex], r8d
0x1401bf4c2  push    rbp
0x1401bf4c3  push    rsi
0x1401bf4c4  push    rdi
0x1401bf4c5  push    r12
0x1401bf4c7  push    r13
0x1401bf4c9  push    r14
0x1401bf4cb  push    r15
0x1401bf4cd  mov     rbp, rsp
0x1401bf4d0  sub     rsp, 60h
0x1401bf4d4  mov     r12, [rbp+arg_28]
0x1401bf4d8  xor     r14d, r14d
0x1401bf4db  mov     r13, [rbp+arg_38]
0x1401bf4df  mov     rdi, rcx
0x1401bf4e2  mov     rsi, [rbp+arg_30]
0x1401bf4e6  mov     r15, r9
0x1401bf4e9  mov     [r9], r14w
0x1401bf4ed  mov     rbx, rdx
0x1401bf4f0  mov     [r12], r14d
0x1401bf4f4  mov     [r13+0], r14d
0x1401bf4f8  mov     rcx, [rsi]; Block
0x1401bf4fb  mov     [rbp+hKey], r14
0x1401bf4ff  mov     [rbp+cchValueName], 104h
0x1401bf506  mov     [rbp+Type], r14d
0x1401bf50a  mov     [rbp+cbData], r14d
0x1401bf50e  mov     [rbp+var_1C], r14d
0x1401bf512  mov     [rbp+var_18], r14d
0x1401bf516  call    cs:__imp_free
0x1401bf51c  xor     r9d, r9d; lpName
0x1401bf51f  mov     [rsi], r14
0x1401bf522  xor     r8d, r8d; bInitialState
0x1401bf525  xor     edx, edx; bManualReset
0x1401bf527  xor     ecx, ecx; lpEventAttributes
0x1401bf529  call    cs:__imp_CreateEventW
0x1401bf52f  mov     r14, rax
0x1401bf532  test    rax, rax
0x1401bf535  jnz     short loc_1401BF552
0x1401bf537  call    cs:__imp_GetLastError
0x1401bf53d  test    eax, eax
0x1401bf53f  jle     loc_1401BF77C
0x1401bf545  movzx   eax, ax
0x1401bf548  or      eax, 80070000h
0x1401bf54d  jmp     loc_1401BF77C
0x1401bf552  lea     rax, [rbp+hKey]
0x1401bf556  mov     r9d, 20019h; samDesired
0x1401bf55c  mov     r8d, 8; ulOptions
0x1401bf562  mov     [rsp+60h+phkResult], rax; phkResult
0x1401bf567  mov     rdx, rbx; lpSubKey
0x1401bf56a  mov     rcx, rdi; hKey
0x1401bf56d  call    cs:__imp_RegOpenKeyExW
0x1401bf573  mov     ebx, eax
0x1401bf575  test    eax, eax
0x1401bf577  jz      short loc_1401BF596
0x1401bf579  mov     rcx, r14; hObject
0x1401bf57c  call    cs:__imp_CloseHandle
0x1401bf582  test    ebx, ebx
0x1401bf584  jle     short loc_1401BF58F
0x1401bf586  movzx   ebx, bx
0x1401bf589  or      ebx, 80070000h
0x1401bf58f  mov     eax, ebx
0x1401bf591  jmp     loc_1401BF77C
0x1401bf596  mov     rcx, [rbp+hKey]; hKey
0x1401bf59a  mov     edi, 1
0x1401bf59f  mov     r9, r14; hEvent
0x1401bf5a2  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x1401bf5a6  xor     edx, edx; bWatchSubtree
0x1401bf5a8  lea     r8d, [rdi+4]; dwNotifyFilter
0x1401bf5ac  call    cs:__imp_RegNotifyChangeKeyValue
0x1401bf5b2  mov     ebx, eax
0x1401bf5b4  test    eax, eax
0x1401bf5b6  jz      short loc_1401BF5CD
0x1401bf5b8  mov     rcx, r14; hObject
0x1401bf5bb  call    cs:__imp_CloseHandle
0x1401bf5c1  mov     rcx, [rbp+hKey]; hKey
0x1401bf5c5  call    cs:__imp_RegCloseKey
0x1401bf5cb  jmp     short loc_1401BF582
0x1401bf5cd  mov     edx, [rbp+dwIndex]; dwIndex
0x1401bf5d0  lea     rax, [rbp+cbData]
0x1401bf5d4  mov     rcx, [rbp+hKey]; hKey
0x1401bf5d8  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1401bf5dc  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1401bf5e1  mov     r8, r15; lpValueName
0x1401bf5e4  lea     rax, [rbp+Type]
0x1401bf5e8  mov     [rsp+60h+lpData], 0; lpData
0x1401bf5f1  mov     [rsp+60h+lpType], rax; lpType
0x1401bf5f6  mov     [rsp+60h+phkResult], 0; lpReserved
0x1401bf5ff  mov     [rbp+cchValueName], 104h
0x1401bf606  call    cs:__imp_RegEnumValueW
0x1401bf60c  mov     ebx, eax
0x1401bf60e  cmp     eax, 103h
0x1401bf613  jz      short loc_1401BF640
0x1401bf615  xor     edi, edi
0x1401bf617  test    eax, eax
0x1401bf619  jz      short loc_1401BF622
0x1401bf61b  cmp     eax, 0EAh
0x1401bf620  jnz     short loc_1401BF5B8
0x1401bf622  mov     eax, [rbp+cbData]
0x1401bf625  test    eax, eax
0x1401bf627  jz      loc_1401BF6BE
0x1401bf62d  mov     edx, eax
0x1401bf62f  mov     rcx, rsi
0x1401bf632  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401bf637  test    al, al
0x1401bf639  jnz     short loc_1401BF65A
0x1401bf63b  mov     edi, 8007000Eh
0x1401bf640  mov     rcx, r14; hObject
0x1401bf643  call    cs:__imp_CloseHandle
0x1401bf649  mov     rcx, [rbp+hKey]; hKey
0x1401bf64d  call    cs:__imp_RegCloseKey
0x1401bf653  mov     eax, edi
0x1401bf655  jmp     loc_1401BF77C
0x1401bf65a  mov     edx, [rbp+dwIndex]; dwIndex
0x1401bf65d  lea     rax, [rbp+cbData]
0x1401bf661  mov     rcx, [rbp+hKey]; hKey
0x1401bf665  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1401bf669  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1401bf66e  mov     r8, r15; lpValueName
0x1401bf671  mov     rax, [rsi]
0x1401bf674  mov     [rsp+60h+lpData], rax; lpData
0x1401bf679  lea     rax, [rbp+Type]
0x1401bf67d  mov     [rsp+60h+lpType], rax; lpType
0x1401bf682  mov     [rsp+60h+phkResult], rdi; lpReserved
0x1401bf687  mov     [rbp+cchValueName], 104h
0x1401bf68e  call    cs:__imp_RegEnumValueW
0x1401bf694  mov     ebx, eax
0x1401bf696  test    eax, eax
0x1401bf698  jz      short loc_1401BF6BE
0x1401bf69a  mov     rcx, r14; hObject
0x1401bf69d  call    cs:__imp_CloseHandle
0x1401bf6a3  mov     rcx, [rbp+hKey]; hKey
0x1401bf6a7  call    cs:__imp_RegCloseKey
0x1401bf6ad  mov     rcx, [rsi]; Block
0x1401bf6b0  call    cs:__imp_free
0x1401bf6b6  mov     [rsi], rdi
0x1401bf6b9  jmp     loc_1401BF582
0x1401bf6be  mov     rcx, [rbp+hKey]; hKey
0x1401bf6c2  lea     rax, [rbp+var_18]
0x1401bf6c6  mov     [rsp+60h+lpType], rax; lpcbData
0x1401bf6cb  lea     r9, [rbp+var_1C]; lpType
0x1401bf6cf  xor     r8d, r8d; lpReserved
0x1401bf6d2  mov     [rsp+60h+phkResult], rdi; lpData
0x1401bf6d7  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1401bf6de  call    cs:__imp_RegQueryValueExW
0x1401bf6e4  mov     rcx, [rbp+hKey]; hKey
0x1401bf6e8  mov     edi, eax
0x1401bf6ea  call    cs:__imp_RegCloseKey
0x1401bf6f0  xor     edx, edx; dwMilliseconds
0x1401bf6f2  mov     rcx, r14; hHandle
0x1401bf6f5  call    cs:__imp_WaitForSingleObject
0x1401bf6fb  mov     rcx, r14; hObject
0x1401bf6fe  mov     ebx, eax
0x1401bf700  call    cs:__imp_CloseHandle
0x1401bf706  test    ebx, ebx
0x1401bf708  jnz     short loc_1401BF711
0x1401bf70a  mov     ebx, 8007051Ah
0x1401bf70f  jmp     short loc_1401BF751
0x1401bf711  test    edi, edi
0x1401bf713  jz      short loc_1401BF746
0x1401bf715  cmp     edi, 2
0x1401bf718  jz      short loc_1401BF76C
0x1401bf71a  mov     rcx, [rsi]; Block
0x1401bf71d  call    cs:__imp_free
0x1401bf723  xor     eax, eax
0x1401bf725  mov     qword ptr [rsi], 0
0x1401bf72c  mov     [r15], ax
0x1401bf730  test    edi, edi
0x1401bf732  jle     loc_1401BF653
0x1401bf738  movzx   edi, di
0x1401bf73b  or      edi, 80070000h
0x1401bf741  jmp     loc_1401BF653
0x1401bf746  cmp     [rbp+var_1C], 6
0x1401bf74a  jnz     short loc_1401BF76C
0x1401bf74c  mov     ebx, 800705B8h
0x1401bf751  mov     rcx, [rsi]; Block
0x1401bf754  call    cs:__imp_free
0x1401bf75a  xor     ecx, ecx
0x1401bf75c  mov     qword ptr [rsi], 0
0x1401bf763  mov     [r15], cx
0x1401bf767  jmp     loc_1401BF58F
0x1401bf76c  mov     eax, [rbp+Type]
0x1401bf76f  mov     [r12], eax
0x1401bf773  mov     eax, [rbp+cbData]
0x1401bf776  mov     [r13+0], eax
0x1401bf77a  xor     eax, eax
0x1401bf77c  mov     rbx, [rsp+60h+arg_0]
0x1401bf784  add     rsp, 60h
0x1401bf788  pop     r15
0x1401bf78a  pop     r14
0x1401bf78c  pop     r13
0x1401bf78e  pop     r12
0x1401bf790  pop     rdi
0x1401bf791  pop     rsi
0x1401bf792  pop     rbp
0x1401bf793  retn
```
