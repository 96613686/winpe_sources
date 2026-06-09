# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x1400c8ac4`
- end: `0x1400c8e30`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1401bd918`

## callees

- `0x140020580`
- `0x14008a0b8`
- `0x1400c8ac4`
- `0x1400c8e38`
- `0x1401b6d28`
- `0x1401b6ee8`
- `0x1401b79d0`
- `0x1401b8bcc`
- `0x1401be288`
- `0x1401be3f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8bce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8c05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8c89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8d97`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8dd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8df1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8e05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8bce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8c05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8c89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8d97`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8dd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8df1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c8e05`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400c8c54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400c8c54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400c8d73`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400c8d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c8c68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c8c68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8d84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c8d84`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400c8cf7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400c8cf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c8cb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c8cb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c8d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c8d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c8d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c8d62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400c8d4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400c8d4f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400c8dc0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400c8dc0`

## string_xrefs

- `0x1400c8d44`: `SymbolicLinkValue`
- `0x1400c8c3f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`
- `0x1400c8b81`: `%s\ATConfig`
- `0x1400c8be8`: `%s\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  void *v2; // rbx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rdi
  int *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // r11d
  unsigned __int64 v8; // rbx
  LSTATUS v9; // r14d
  unsigned __int64 v10; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // r14
  void *v14; // rcx
  HANDLE EventW; // r15
  signed int LastError; // eax
  DWORD v17; // esi
  LSTATUS v18; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  v21 = 0;
  v22 = 0;
  v2 = 0;
  Block = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !CATUtils::IsInteractiveUser() )
  {
    v12 = -2147483647;
    v13 = SettingsCopier::_ATConfigKeyString;
    v4 = v26;
LABEL_17:
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError <= 0 )
      {
LABEL_21:
        free(v2);
        goto LABEL_37;
      }
      v9 = (unsigned __int16)LastError;
LABEL_20:
      v9 |= 0x80070000;
      goto LABEL_21;
    }
    v9 = RegOpenKeyExW((HKEY)v12, v13, 8u, 0x20019u, &hKey);
    if ( v9 )
    {
      CloseHandle(EventW);
LABEL_24:
      if ( v9 <= 0 )
        goto LABEL_21;
      v9 = (unsigned __int16)v9;
      goto LABEL_20;
    }
    v9 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
    if ( v9 )
    {
      CloseHandle(EventW);
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v9 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    v17 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v17 )
    {
      free(v2);
      v9 = -2147023590;
      goto LABEL_37;
    }
    if ( v9 )
    {
      if ( v9 != 2 )
        goto LABEL_24;
    }
    else if ( Type == 6 )
    {
      free(v2);
      v9 = -2147023432;
      goto LABEL_37;
    }
    v18 = RegDeleteTreeW(*a1, 0);
    v14 = v2;
    if ( !v18 )
    {
      free(v2);
      v9 = 0;
      goto LABEL_37;
    }
LABEL_33:
    free(v14);
    v9 = -2147467259;
    goto LABEL_37;
  }
  v3 = *(_QWORD *)CATUtils::SessionKeyString(&v23);
  v4 = v26;
  v5 = (int *)(v26 - 12);
  if ( (unsigned __int16 *)(v3 - 24) != v26 - 12 )
  {
    if ( v5[4] >= 0 && *(_QWORD *)(v3 - 24) == *(_QWORD *)v5 )
    {
      v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v5);
      v4 = (unsigned __int16 *)(v6 + 24);
      v26 = v4;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v3, *(unsigned int *)(v3 - 16));
      v4 = v26;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, &v21) < 0
    || (int)StringCchLengthW(v4, v7, &v22) < 0
    || (v8 = v21 + v22, v21 + v22 < v21) )
  {
    v14 = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v21 + v22) )
  {
    v10 = v8;
    v2 = Block;
    if ( (int)StringCchPrintfW((unsigned __int16 *)Block, v10, SettingsCopier::_ATSessionConfigKeyString, v4) < 0 )
    {
      free(v2);
      ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
      return 2147500037LL;
    }
    v12 = -2147483646;
    v13 = (const WCHAR *)v2;
    goto LABEL_17;
  }
  free(Block);
  v9 = -2147024882;
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400c8ac4  push    rbp
0x1400c8ac6  push    rbx
0x1400c8ac7  push    rsi
0x1400c8ac8  push    rdi
0x1400c8ac9  push    r12
0x1400c8acb  push    r14
0x1400c8acd  push    r15
0x1400c8acf  mov     rbp, rsp
0x1400c8ad2  sub     rsp, 60h
0x1400c8ad6  mov     r12, rcx
0x1400c8ad9  lea     rcx, [rbp+arg_18]
0x1400c8add  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400c8ae2  nop
0x1400c8ae3  mov     [rbp+var_20], 0
0x1400c8aeb  mov     [rbp+var_18], 0
0x1400c8af3  xor     ebx, ebx
0x1400c8af5  mov     [rbp+Block], rbx
0x1400c8af9  mov     [rbp+hKey], rbx
0x1400c8afd  mov     [rbp+Type], ebx
0x1400c8b00  mov     [rbp+cbData], ebx
0x1400c8b03  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1400c8b08  test    eax, eax
0x1400c8b0a  jz      loc_1400C8C38
0x1400c8b10  lea     rcx, [rbp+var_10]
0x1400c8b14  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1400c8b19  nop
0x1400c8b1a  mov     rdx, [rax]
0x1400c8b1d  lea     rcx, [rdx-18h]
0x1400c8b21  mov     rdi, [rbp+arg_18]
0x1400c8b25  lea     rbx, [rdi-18h]
0x1400c8b29  cmp     rcx, rbx
0x1400c8b2c  jz      short loc_1400C8B67
0x1400c8b2e  cmp     dword ptr [rbx+10h], 0
0x1400c8b32  jl      short loc_1400C8B56
0x1400c8b34  mov     rax, [rbx]
0x1400c8b37  cmp     [rcx], rax
0x1400c8b3a  jnz     short loc_1400C8B56
0x1400c8b3c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400c8b41  mov     rdi, rax
0x1400c8b44  mov     rcx, rbx; this
0x1400c8b47  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8b4c  add     rdi, 18h
0x1400c8b50  mov     [rbp+arg_18], rdi
0x1400c8b54  jmp     short loc_1400C8B67
0x1400c8b56  mov     r8d, [rdx-10h]
0x1400c8b5a  lea     rcx, [rbp+arg_18]
0x1400c8b5e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400c8b63  mov     rdi, [rbp+arg_18]
0x1400c8b67  mov     rcx, [rbp+var_10]
0x1400c8b6b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c8b6f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8b74  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1400c8b78  mov     r11d, 7FFFFFFFh
0x1400c8b7e  mov     edx, r11d; unsigned __int64
0x1400c8b81  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400c8b88  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400c8b8d  test    eax, eax
0x1400c8b8f  js      loc_1400C8C31
0x1400c8b95  lea     r8, [rbp+var_18]; unsigned __int64 *
0x1400c8b99  mov     edx, r11d; unsigned __int64
0x1400c8b9c  mov     rcx, rdi; unsigned __int16 *
0x1400c8b9f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400c8ba4  test    eax, eax
0x1400c8ba6  js      loc_1400C8C31
0x1400c8bac  mov     rbx, [rbp+var_18]
0x1400c8bb0  add     rbx, [rbp+var_20]
0x1400c8bb4  cmp     rbx, [rbp+var_20]
0x1400c8bb8  jb      short loc_1400C8C31
0x1400c8bba  mov     rdx, rbx
0x1400c8bbd  lea     rcx, [rbp+Block]
0x1400c8bc1  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1400c8bc6  test    al, al
0x1400c8bc8  jnz     short loc_1400C8BE5
0x1400c8bca  mov     rcx, [rbp+Block]; Block
0x1400c8bce  call    cs:__imp_free
0x1400c8bd5  nop     dword ptr [rax+rax+00h]
0x1400c8bda  mov     r14d, 8007000Eh
0x1400c8be0  jmp     loc_1400C8E14
0x1400c8be5  mov     r9, rdi
0x1400c8be8  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400c8bef  mov     rdx, rbx; unsigned __int64
0x1400c8bf2  mov     rbx, [rbp+Block]
0x1400c8bf6  mov     rcx, rbx; unsigned __int16 *
0x1400c8bf9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400c8bfe  test    eax, eax
0x1400c8c00  jns     short loc_1400C8C25
0x1400c8c02  mov     rcx, rbx; Block
0x1400c8c05  call    cs:__imp_free
0x1400c8c0c  nop     dword ptr [rax+rax+00h]
0x1400c8c11  nop
0x1400c8c12  lea     rcx, [rdi-18h]; this
0x1400c8c16  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8c1b  mov     eax, 80004005h
0x1400c8c20  jmp     loc_1400C8E20
0x1400c8c25  mov     rsi, 0FFFFFFFF80000002h
0x1400c8c2c  mov     r14, rbx
0x1400c8c2f  jmp     short loc_1400C8C4A
0x1400c8c31  xor     ecx, ecx
0x1400c8c33  jmp     loc_1400C8DD4
0x1400c8c38  mov     rsi, 0FFFFFFFF80000001h
0x1400c8c3f  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400c8c46  mov     rdi, [rbp+arg_18]
0x1400c8c4a  xor     r9d, r9d; lpName
0x1400c8c4d  xor     r8d, r8d; bInitialState
0x1400c8c50  xor     edx, edx; bManualReset
0x1400c8c52  xor     ecx, ecx; lpEventAttributes
0x1400c8c54  call    cs:__imp_CreateEventW
0x1400c8c5b  nop     dword ptr [rax+rax+00h]
0x1400c8c60  mov     r15, rax
0x1400c8c63  test    rax, rax
0x1400c8c66  jnz     short loc_1400C8C9A
0x1400c8c68  call    cs:__imp_GetLastError
0x1400c8c6f  nop     dword ptr [rax+rax+00h]
0x1400c8c74  mov     r14d, eax
0x1400c8c77  test    eax, eax
0x1400c8c79  jle     short loc_1400C8C86
0x1400c8c7b  movzx   r14d, ax
0x1400c8c7f  or      r14d, 80070000h
0x1400c8c86  mov     rcx, rbx; Block
0x1400c8c89  call    cs:__imp_free
0x1400c8c90  nop     dword ptr [rax+rax+00h]
0x1400c8c95  jmp     loc_1400C8E14
0x1400c8c9a  lea     rax, [rbp+hKey]
0x1400c8c9e  mov     [rsp+60h+phkResult], rax; phkResult
0x1400c8ca3  mov     r9d, 20019h; samDesired
0x1400c8ca9  mov     r8d, 8; ulOptions
0x1400c8caf  mov     rdx, r14; lpSubKey
0x1400c8cb2  mov     rcx, rsi; hKey
0x1400c8cb5  call    cs:__imp_RegOpenKeyExW
0x1400c8cbc  nop     dword ptr [rax+rax+00h]
0x1400c8cc1  mov     r14d, eax
0x1400c8cc4  test    eax, eax
0x1400c8cc6  jz      short loc_1400C8CE2
0x1400c8cc8  mov     rcx, r15; hObject
0x1400c8ccb  call    cs:__imp_CloseHandle
0x1400c8cd2  nop     dword ptr [rax+rax+00h]
0x1400c8cd7  test    r14d, r14d
0x1400c8cda  jle     short loc_1400C8C86
0x1400c8cdc  movzx   r14d, r14w
0x1400c8ce0  jmp     short loc_1400C8C7F
0x1400c8ce2  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x1400c8cea  mov     r9, r15; hEvent
0x1400c8ced  xor     edx, edx; bWatchSubtree
0x1400c8cef  lea     r8d, [rdx+5]; dwNotifyFilter
0x1400c8cf3  mov     rcx, [rbp+hKey]; hKey
0x1400c8cf7  call    cs:__imp_RegNotifyChangeKeyValue
0x1400c8cfe  nop     dword ptr [rax+rax+00h]
0x1400c8d03  mov     r14d, eax
0x1400c8d06  test    eax, eax
0x1400c8d08  jz      short loc_1400C8D2B
0x1400c8d0a  mov     rcx, r15; hObject
0x1400c8d0d  call    cs:__imp_CloseHandle
0x1400c8d14  nop     dword ptr [rax+rax+00h]
0x1400c8d19  mov     rcx, [rbp+hKey]; hKey
0x1400c8d1d  call    cs:__imp_RegCloseKey
0x1400c8d24  nop     dword ptr [rax+rax+00h]
0x1400c8d29  jmp     short loc_1400C8CD7
0x1400c8d2b  lea     rax, [rbp+cbData]
0x1400c8d2f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400c8d34  mov     [rsp+60h+phkResult], 0; lpData
0x1400c8d3d  lea     r9, [rbp+Type]; lpType
0x1400c8d41  xor     r8d, r8d; lpReserved
0x1400c8d44  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1400c8d4b  mov     rcx, [rbp+hKey]; hKey
0x1400c8d4f  call    cs:__imp_RegQueryValueExW
0x1400c8d56  nop     dword ptr [rax+rax+00h]
0x1400c8d5b  mov     r14d, eax
0x1400c8d5e  mov     rcx, [rbp+hKey]; hKey
0x1400c8d62  call    cs:__imp_RegCloseKey
0x1400c8d69  nop     dword ptr [rax+rax+00h]
0x1400c8d6e  xor     edx, edx; dwMilliseconds
0x1400c8d70  mov     rcx, r15; hHandle
0x1400c8d73  call    cs:__imp_WaitForSingleObject
0x1400c8d7a  nop     dword ptr [rax+rax+00h]
0x1400c8d7f  mov     esi, eax
0x1400c8d81  mov     rcx, r15; hObject
0x1400c8d84  call    cs:__imp_CloseHandle
0x1400c8d8b  nop     dword ptr [rax+rax+00h]
0x1400c8d90  test    esi, esi
0x1400c8d92  jnz     short loc_1400C8DAB
0x1400c8d94  mov     rcx, rbx; Block
0x1400c8d97  call    cs:__imp_free
0x1400c8d9e  nop     dword ptr [rax+rax+00h]
0x1400c8da3  mov     r14d, 8007051Ah
0x1400c8da9  jmp     short loc_1400C8E14
0x1400c8dab  test    r14d, r14d
0x1400c8dae  jz      short loc_1400C8DE8
0x1400c8db0  cmp     r14d, 2
0x1400c8db4  jnz     loc_1400C8CD7
0x1400c8dba  xor     edx, edx; lpSubKey
0x1400c8dbc  mov     rcx, [r12]; hKey
0x1400c8dc0  call    cs:__imp_RegDeleteTreeW
0x1400c8dc7  nop     dword ptr [rax+rax+00h]
0x1400c8dcc  nop
0x1400c8dcd  mov     rcx, rbx; Block
0x1400c8dd0  test    eax, eax
0x1400c8dd2  jz      short loc_1400C8E05
0x1400c8dd4  call    cs:__imp_free
0x1400c8ddb  nop     dword ptr [rax+rax+00h]
0x1400c8de0  mov     r14d, 80004005h
0x1400c8de6  jmp     short loc_1400C8E14
0x1400c8de8  cmp     [rbp+Type], 6
0x1400c8dec  jnz     short loc_1400C8DBA
0x1400c8dee  mov     rcx, rbx; Block
0x1400c8df1  call    cs:__imp_free
0x1400c8df8  nop     dword ptr [rax+rax+00h]
0x1400c8dfd  mov     r14d, 800705B8h
0x1400c8e03  jmp     short loc_1400C8E14
0x1400c8e05  call    cs:__imp_free
0x1400c8e0c  nop     dword ptr [rax+rax+00h]
0x1400c8e11  xor     r14d, r14d
0x1400c8e14  lea     rcx, [rdi-18h]; this
0x1400c8e18  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8e1d  mov     eax, r14d
0x1400c8e20  add     rsp, 60h
0x1400c8e24  pop     r15
0x1400c8e26  pop     r14
0x1400c8e28  pop     r12
0x1400c8e2a  pop     rdi
0x1400c8e2b  pop     rsi
0x1400c8e2c  pop     rbx
0x1400c8e2d  pop     rbp
0x1400c8e2e  retn
```
