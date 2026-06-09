# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x140024ba4`
- end: `0x140024e99`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14002491c`

## callees

- `0x140004700`
- `0x140005c04`
- `0x140009524`
- `0x140009cd8`
- `0x140009f28`
- `0x140013a34`
- `0x14001c494`
- `0x14001c768`
- `0x14001caa4`
- `0x140024ba4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140024d73`
- `ADVAPI32!RegOpenKeyExW` at `0x140024d73`
- `ADVAPI32!RegCloseKey` at `0x140024dc3`
- `ADVAPI32!RegCloseKey` at `0x140024dfc`
- `ADVAPI32!RegCloseKey` at `0x140024dc3`
- `ADVAPI32!RegCloseKey` at `0x140024dfc`
- `ADVAPI32!RegQueryValueExW` at `0x140024def`
- `ADVAPI32!RegQueryValueExW` at `0x140024def`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140024da9`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140024da9`
- `ADVAPI32!RegDeleteTreeW` at `0x140024e42`
- `ADVAPI32!RegDeleteTreeW` at `0x140024e42`
- `KERNEL32!WaitForSingleObject` at `0x140024e07`
- `KERNEL32!WaitForSingleObject` at `0x140024e07`
- `KERNEL32!GetLastError` at `0x140024d32`
- `KERNEL32!GetLastError` at `0x140024d32`
- `KERNEL32!CloseHandle` at `0x140024d83`
- `KERNEL32!CloseHandle` at `0x140024db9`
- `KERNEL32!CloseHandle` at `0x140024e12`
- `KERNEL32!CloseHandle` at `0x140024d83`
- `KERNEL32!CloseHandle` at `0x140024db9`
- `KERNEL32!CloseHandle` at `0x140024e12`
- `KERNEL32!CreateEventW` at `0x140024d24`
- `KERNEL32!CreateEventW` at `0x140024d24`
- `msvcrt!free` at `0x140024caa`
- `msvcrt!free` at `0x140024cdb`
- `msvcrt!free` at `0x140024d4d`
- `msvcrt!free` at `0x140024e1f`
- `msvcrt!free` at `0x140024e50`
- `msvcrt!free` at `0x140024e67`
- `msvcrt!free` at `0x140024e75`
- `msvcrt!free` at `0x140024caa`
- `msvcrt!free` at `0x140024cdb`
- `msvcrt!free` at `0x140024d4d`
- `msvcrt!free` at `0x140024e1f`
- `msvcrt!free` at `0x140024e50`
- `msvcrt!free` at `0x140024e67`
- `msvcrt!free` at `0x140024e75`

## string_xrefs

- `0x140024de4`: `SymbolicLinkValue`
- `0x140024c61`: `%s\ATConfig`
- `0x140024cbe`: `%s\ATConfig`
- `0x140024d0f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

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
0x140024ba4  push    rbp
0x140024ba6  push    rbx
0x140024ba7  push    rsi
0x140024ba8  push    rdi
0x140024ba9  push    r12
0x140024bab  push    r14
0x140024bad  push    r15
0x140024baf  mov     rbp, rsp
0x140024bb2  sub     rsp, 60h
0x140024bb6  mov     r12, rcx
0x140024bb9  lea     rcx, [rbp+arg_18]
0x140024bbd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140024bc2  nop
0x140024bc3  mov     [rbp+var_20], 0
0x140024bcb  mov     [rbp+var_18], 0
0x140024bd3  xor     ebx, ebx
0x140024bd5  mov     [rbp+Block], rbx
0x140024bd9  mov     [rbp+hKey], rbx
0x140024bdd  mov     [rbp+Type], ebx
0x140024be0  mov     [rbp+cbData], ebx
0x140024be3  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140024be8  test    eax, eax
0x140024bea  jz      loc_140024D08
0x140024bf0  lea     rcx, [rbp+var_10]
0x140024bf4  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140024bf9  nop
0x140024bfa  mov     rdx, [rax]
0x140024bfd  lea     rcx, [rdx-18h]
0x140024c01  mov     rdi, [rbp+arg_18]
0x140024c05  lea     rbx, [rdi-18h]
0x140024c09  cmp     rcx, rbx
0x140024c0c  jz      short loc_140024C47
0x140024c0e  cmp     dword ptr [rbx+10h], 0
0x140024c12  jl      short loc_140024C36
0x140024c14  mov     rax, [rbx]
0x140024c17  cmp     [rcx], rax
0x140024c1a  jnz     short loc_140024C36
0x140024c1c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140024c21  mov     rdi, rax
0x140024c24  mov     rcx, rbx; this
0x140024c27  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140024c2c  add     rdi, 18h
0x140024c30  mov     [rbp+arg_18], rdi
0x140024c34  jmp     short loc_140024C47
0x140024c36  mov     r8d, [rdx-10h]
0x140024c3a  lea     rcx, [rbp+arg_18]
0x140024c3e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140024c43  mov     rdi, [rbp+arg_18]
0x140024c47  mov     rcx, [rbp+var_10]
0x140024c4b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140024c4f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140024c54  lea     r8, [rbp+var_20]; unsigned __int64 *
0x140024c58  mov     r11d, 7FFFFFFFh
0x140024c5e  mov     edx, r11d; unsigned __int64
0x140024c61  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140024c68  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140024c6d  test    eax, eax
0x140024c6f  js      loc_140024D01
0x140024c75  lea     r8, [rbp+var_18]; unsigned __int64 *
0x140024c79  mov     edx, r11d; unsigned __int64
0x140024c7c  mov     rcx, rdi; unsigned __int16 *
0x140024c7f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140024c84  test    eax, eax
0x140024c86  js      short loc_140024D01
0x140024c88  mov     rbx, [rbp+var_18]
0x140024c8c  add     rbx, [rbp+var_20]
0x140024c90  cmp     rbx, [rbp+var_20]
0x140024c94  jb      short loc_140024D01
0x140024c96  mov     rdx, rbx
0x140024c99  lea     rcx, [rbp+Block]
0x140024c9d  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x140024ca2  test    al, al
0x140024ca4  jnz     short loc_140024CBB
0x140024ca6  mov     rcx, [rbp+Block]; Block
0x140024caa  call    cs:__imp_free
0x140024cb0  mov     r14d, 8007000Eh
0x140024cb6  jmp     loc_140024E7E
0x140024cbb  mov     r9, rdi
0x140024cbe  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140024cc5  mov     rdx, rbx; unsigned __int64
0x140024cc8  mov     rbx, [rbp+Block]
0x140024ccc  mov     rcx, rbx; unsigned __int16 *
0x140024ccf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140024cd4  test    eax, eax
0x140024cd6  jns     short loc_140024CF5
0x140024cd8  mov     rcx, rbx; Block
0x140024cdb  call    cs:__imp_free
0x140024ce1  nop
0x140024ce2  lea     rcx, [rdi-18h]; this
0x140024ce6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140024ceb  mov     eax, 80004005h
0x140024cf0  jmp     loc_140024E8A
0x140024cf5  mov     rsi, 0FFFFFFFF80000002h
0x140024cfc  mov     r14, rbx
0x140024cff  jmp     short loc_140024D1A
0x140024d01  xor     ecx, ecx
0x140024d03  jmp     loc_140024E50
0x140024d08  mov     rsi, 0FFFFFFFF80000001h
0x140024d0f  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140024d16  mov     rdi, [rbp+arg_18]
0x140024d1a  xor     r9d, r9d; lpName
0x140024d1d  xor     r8d, r8d; bInitialState
0x140024d20  xor     edx, edx; bManualReset
0x140024d22  xor     ecx, ecx; lpEventAttributes
0x140024d24  call    cs:__imp_CreateEventW
0x140024d2a  mov     r15, rax
0x140024d2d  test    rax, rax
0x140024d30  jnz     short loc_140024D58
0x140024d32  call    cs:__imp_GetLastError
0x140024d38  mov     r14d, eax
0x140024d3b  test    eax, eax
0x140024d3d  jle     short loc_140024D4A
0x140024d3f  movzx   r14d, ax
0x140024d43  or      r14d, 80070000h
0x140024d4a  mov     rcx, rbx; Block
0x140024d4d  call    cs:__imp_free
0x140024d53  jmp     loc_140024E7E
0x140024d58  lea     rax, [rbp+hKey]
0x140024d5c  mov     [rsp+60h+phkResult], rax; phkResult
0x140024d61  mov     r9d, 20019h; samDesired
0x140024d67  mov     r8d, 8; ulOptions
0x140024d6d  mov     rdx, r14; lpSubKey
0x140024d70  mov     rcx, rsi; hKey
0x140024d73  call    cs:__imp_RegOpenKeyExW
0x140024d79  mov     r14d, eax
0x140024d7c  test    eax, eax
0x140024d7e  jz      short loc_140024D94
0x140024d80  mov     rcx, r15; hObject
0x140024d83  call    cs:__imp_CloseHandle
0x140024d89  test    r14d, r14d
0x140024d8c  jle     short loc_140024D4A
0x140024d8e  movzx   r14d, r14w
0x140024d92  jmp     short loc_140024D43
0x140024d94  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x140024d9c  mov     r9, r15; hEvent
0x140024d9f  xor     edx, edx; bWatchSubtree
0x140024da1  lea     r8d, [rdx+5]; dwNotifyFilter
0x140024da5  mov     rcx, [rbp+hKey]; hKey
0x140024da9  call    cs:__imp_RegNotifyChangeKeyValue
0x140024daf  mov     r14d, eax
0x140024db2  test    eax, eax
0x140024db4  jz      short loc_140024DCB
0x140024db6  mov     rcx, r15; hObject
0x140024db9  call    cs:__imp_CloseHandle
0x140024dbf  mov     rcx, [rbp+hKey]; hKey
0x140024dc3  call    cs:__imp_RegCloseKey
0x140024dc9  jmp     short loc_140024D89
0x140024dcb  lea     rax, [rbp+cbData]
0x140024dcf  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140024dd4  mov     [rsp+60h+phkResult], 0; lpData
0x140024ddd  lea     r9, [rbp+Type]; lpType
0x140024de1  xor     r8d, r8d; lpReserved
0x140024de4  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140024deb  mov     rcx, [rbp+hKey]; hKey
0x140024def  call    cs:__imp_RegQueryValueExW
0x140024df5  mov     r14d, eax
0x140024df8  mov     rcx, [rbp+hKey]; hKey
0x140024dfc  call    cs:__imp_RegCloseKey
0x140024e02  xor     edx, edx; dwMilliseconds
0x140024e04  mov     rcx, r15; hHandle
0x140024e07  call    cs:__imp_WaitForSingleObject
0x140024e0d  mov     esi, eax
0x140024e0f  mov     rcx, r15; hObject
0x140024e12  call    cs:__imp_CloseHandle
0x140024e18  test    esi, esi
0x140024e1a  jnz     short loc_140024E2D
0x140024e1c  mov     rcx, rbx; Block
0x140024e1f  call    cs:__imp_free
0x140024e25  mov     r14d, 8007051Ah
0x140024e2b  jmp     short loc_140024E7E
0x140024e2d  test    r14d, r14d
0x140024e30  jz      short loc_140024E5E
0x140024e32  cmp     r14d, 2
0x140024e36  jnz     loc_140024D89
0x140024e3c  xor     edx, edx; lpSubKey
0x140024e3e  mov     rcx, [r12]; hKey
0x140024e42  call    cs:__imp_RegDeleteTreeW
0x140024e48  nop
0x140024e49  mov     rcx, rbx; Block
0x140024e4c  test    eax, eax
0x140024e4e  jz      short loc_140024E75
0x140024e50  call    cs:__imp_free
0x140024e56  mov     r14d, 80004005h
0x140024e5c  jmp     short loc_140024E7E
0x140024e5e  cmp     [rbp+Type], 6
0x140024e62  jnz     short loc_140024E3C
0x140024e64  mov     rcx, rbx; Block
0x140024e67  call    cs:__imp_free
0x140024e6d  mov     r14d, 800705B8h
0x140024e73  jmp     short loc_140024E7E
0x140024e75  call    cs:__imp_free
0x140024e7b  xor     r14d, r14d
0x140024e7e  lea     rcx, [rdi-18h]; this
0x140024e82  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140024e87  mov     eax, r14d
0x140024e8a  add     rsp, 60h
0x140024e8e  pop     r15
0x140024e90  pop     r14
0x140024e92  pop     r12
0x140024e94  pop     rdi
0x140024e95  pop     rsi
0x140024e96  pop     rbx
0x140024e97  pop     rbp
0x140024e98  retn
```
