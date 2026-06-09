# CMsmqVssWriter::BackupRegistryKeyInternal(void *,wchar_t const *,int)

- ea: `0x18008e93c`
- end: `0x18008eeba`
- name: `?BackupRegistryKeyInternal@CMsmqVssWriter@@AEAAJPEAXPEB_WH@Z`
- size: `1406`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, void *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e824`
- `0x18008e93c`

## callees

- `0x18000bb04`
- `0x18000cb80`
- `0x18002c61c`
- `0x18003c644`
- `0x18008e93c`
- `0x1800944c8`
- `0x180094550`
- `0x18009a4e8`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18008eb9a`
- `msvcrt!free` at `0x18008eba4`
- `msvcrt!free` at `0x18008ebc5`
- `msvcrt!free` at `0x18008ebcf`
- `msvcrt!free` at `0x18008ebff`
- `msvcrt!free` at `0x18008ec09`
- `msvcrt!free` at `0x18008ec44`
- `msvcrt!free` at `0x18008ec4e`
- `msvcrt!free` at `0x18008ed61`
- `msvcrt!free` at `0x18008ed8d`
- `msvcrt!free` at `0x18008edb4`
- `msvcrt!free` at `0x18008edbe`
- `msvcrt!free` at `0x18008edc8`
- `msvcrt!free` at `0x18008edd2`
- `msvcrt!free` at `0x18008edf3`
- `msvcrt!free` at `0x18008edfd`
- `msvcrt!free` at `0x18008ee07`
- `msvcrt!free` at `0x18008ee11`
- `msvcrt!free` at `0x18008ee45`
- `msvcrt!free` at `0x18008ee4f`
- `msvcrt!free` at `0x18008ee59`
- `msvcrt!free` at `0x18008ee68`
- `msvcrt!free` at `0x18008ee72`
- `msvcrt!free` at `0x18008ee7c`
- `msvcrt!free` at `0x18008eb9a`
- `msvcrt!free` at `0x18008eba4`
- `msvcrt!free` at `0x18008ebc5`
- `msvcrt!free` at `0x18008ebcf`
- `msvcrt!free` at `0x18008ebff`
- `msvcrt!free` at `0x18008ec09`
- `msvcrt!free` at `0x18008ec44`
- `msvcrt!free` at `0x18008ec4e`
- `msvcrt!free` at `0x18008ed61`
- `msvcrt!free` at `0x18008ed8d`
- `msvcrt!free` at `0x18008edb4`
- `msvcrt!free` at `0x18008edbe`
- `msvcrt!free` at `0x18008edc8`
- `msvcrt!free` at `0x18008edd2`
- `msvcrt!free` at `0x18008edf3`
- `msvcrt!free` at `0x18008edfd`
- `msvcrt!free` at `0x18008ee07`
- `msvcrt!free` at `0x18008ee11`
- `msvcrt!free` at `0x18008ee45`
- `msvcrt!free` at `0x18008ee4f`
- `msvcrt!free` at `0x18008ee59`
- `msvcrt!free` at `0x18008ee68`
- `msvcrt!free` at `0x18008ee72`
- `msvcrt!free` at `0x18008ee7c`
- `msvcrt!_wcsicmp` at `0x18008ed40`
- `msvcrt!_wcsicmp` at `0x18008ed54`
- `msvcrt!_wcsicmp` at `0x18008ed40`
- `msvcrt!_wcsicmp` at `0x18008ed54`
- `ADVAPI32!RegEnumValueW` at `0x18008eb32`
- `ADVAPI32!RegEnumValueW` at `0x18008eb32`
- `ADVAPI32!RegEnumKeyExW` at `0x18008ecbb`
- `ADVAPI32!RegEnumKeyExW` at `0x18008ecbb`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18008ea10`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18008ea10`

## string_xrefs

- `0x18008ea5f`: `writer/mqwriter`
- `0x18008eb88`: `writer/mqwriter`
- `0x18008ebb3`: `writer/mqwriter`
- `0x18008ebed`: `writer/mqwriter`
- `0x18008ec32`: `writer/mqwriter`
- `0x18008eda2`: `writer/mqwriter`
- `0x18008ede1`: `writer/mqwriter`
- `0x18008ee33`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMsmqVssWriter::BackupRegistryKeyInternal(CMsmqVssWriter *this, void *a2, wchar_t *a3)
{
  DWORD v5; // r13d
  HKEY v6; // r15
  LSTATUS v7; // eax
  signed int v8; // ebx
  unsigned __int16 v9; // r8
  int v10; // ecx
  int v11; // eax
  CMsmqVssWriter *v12; // rcx
  CMsmqVssWriter *v13; // rcx
  WCHAR *v14; // rbx
  CMsmqVssWriter *v15; // rcx
  BYTE *v16; // rdi
  DWORD i; // r14d
  LSTATUS v18; // eax
  CMsmqVssWriter *v19; // rcx
  signed int v20; // esi
  int v21; // eax
  CMsmqVssWriter *v22; // rcx
  int v23; // eax
  int v24; // eax
  void *v25; // r14
  LSTATUS v26; // eax
  unsigned int v27; // eax
  wchar_t *v28; // rsi
  int v29; // eax
  CMsmqVssWriter *v30; // rax
  int v31; // eax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  signed int v37; // [rsp+70h] [rbp-90h]
  DWORD cValues; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchValueName; // [rsp+84h] [rbp-7Ch] BYREF
  wchar_t *v43; // [rsp+88h] [rbp-78h]
  CMsmqVssWriter *v44; // [rsp+90h] [rbp-70h]
  HKEY v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h]
  int v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  WCHAR *v51; // [rsp+C8h] [rbp-38h]
  BYTE *v52; // [rsp+D0h] [rbp-30h]
  void *v53; // [rsp+D8h] [rbp-28h]
  wchar_t *v54; // [rsp+E0h] [rbp-20h]
  wchar_t v55[256]; // [rsp+F0h] [rbp-10h] BYREF

  v43 = a3;
  v44 = this;
  v46 = 1;
  v47 = a3;
  v5 = 0;
  v48 = 0;
  v49 = 0;
  v50 = -2147483646;
  v6 = CmOpenKey((const struct RegEntry *)&v46, 0x20019u);
  v45 = v6;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v7 = RegQueryInfoKeyW(v6, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_50;
    v9 = 3360;
    v10 = v8;
LABEL_9:
    LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", v9);
    goto LABEL_50;
  }
  v11 = StringCchPrintfW(v55, 0x100u, L"[%s]", a3);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 3380;
LABEL_8:
    v10 = v11;
    goto LABEL_9;
  }
  v11 = CMsmqVssWriter::WriteStringToFile(v12, a2, v55);
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 3400;
    goto LABEL_8;
  }
  v11 = CMsmqVssWriter::WriteStringToFile(v13, a2, L"\r\n");
  v8 = v11;
  if ( v11 < 0 )
  {
    v9 = 3420;
    goto LABEL_8;
  }
  v14 = (WCHAR *)MmAllocate(saturated_mul(++cbMaxValueNameLen, 2u));
  v51 = v14;
  v16 = (BYTE *)MmAllocate(cbMaxValueLen);
  v52 = v16;
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    Type = 0;
    v18 = RegEnumValueW(v6, i, v14, &cchValueName, 0, &Type, v16, &cbData);
    v20 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v20 = (unsigned __int16)v18 | 0x80070000;
      if ( v20 < 0 )
        LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0xD70u);
      free(v16);
      free(v14);
      goto LABEL_27;
    }
    v21 = CMsmqVssWriter::WriteValueToFile(v19, a2, v14, Type, v16, cbData);
    v20 = v21;
    if ( v21 < 0 )
    {
      LogMsgHR(v21, (wchar_t *)L"writer/mqwriter", 0xD84u);
      free(v16);
      free(v14);
      goto LABEL_27;
    }
    v23 = CMsmqVssWriter::WriteStringToFile(v22, a2, L"\r\n");
    v20 = v23;
    if ( v23 < 0 )
    {
      LogMsgHR(v23, (wchar_t *)L"writer/mqwriter", 0xD98u);
      free(v16);
      free(v14);
      goto LABEL_27;
    }
  }
  v24 = CMsmqVssWriter::WriteStringToFile(v15, a2, L"\r\n");
  v20 = v24;
  if ( v24 < 0 )
  {
    LogMsgHR(v24, (wchar_t *)L"writer/mqwriter", 0xDACu);
    free(v16);
    free(v14);
    goto LABEL_27;
  }
  v25 = MmAllocate(saturated_mul(++cbMaxSubKeyLen, 2u));
  v53 = v25;
  while ( 1 )
  {
    if ( v5 >= cSubKeys )
    {
      free(v25);
      free(v16);
      free(v14);
      v8 = 0;
      goto LABEL_50;
    }
    cchName = cbMaxSubKeyLen;
    v26 = RegEnumKeyExW(v6, v5, (LPWSTR)v25, &cchName, 0, 0, 0, 0);
    v20 = v26;
    if ( v26 )
      break;
    v27 = mqwcslen(v43);
    cchName += v27 + 2;
    v28 = (wchar_t *)MmAllocate(saturated_mul(cchName, 2u));
    v54 = v28;
    v29 = StringCchPrintfW(v28, cchName, L"%s\\%s", v43, v25);
    v37 = v29;
    if ( v29 < 0 )
    {
      LogMsgHR(v29, (wchar_t *)L"writer/mqwriter", 0xDD4u);
      free(v28);
      free(v25);
      free(v16);
      free(v14);
      goto LABEL_43;
    }
    v30 = v44;
    if ( !*((_QWORD *)v44 + 5) )
    {
      if ( !_wcsicmp(v28, L"Software\\Microsoft\\MSMQ\\Clustered QMs")
        || !_wcsicmp(v28, L"Software\\Microsoft\\MSMQ\\Triggers\\Clustered") )
      {
        goto LABEL_40;
      }
      v30 = v44;
    }
    v31 = CMsmqVssWriter::BackupRegistryKeyInternal(v30, a2, v28, 1);
    v37 = v31;
    if ( v31 < 0 )
    {
      LogMsgHR(v31, (wchar_t *)L"writer/mqwriter", 0xDE8u);
      free(v28);
      free(v25);
      free(v16);
      free(v14);
LABEL_43:
      v8 = v37;
      goto LABEL_50;
    }
LABEL_40:
    free(v28);
    ++v5;
  }
  if ( v26 > 0 )
    v20 = (unsigned __int16)v26 | 0x80070000;
  if ( v20 < 0 )
    LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0xDC0u);
  free(v25);
  free(v16);
  free(v14);
LABEL_27:
  v8 = v20;
LABEL_50:
  CRegHandle::~CRegHandle((CRegHandle *)&v45);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008e93c  mov     [rsp-8+arg_18], rbx
0x18008e941  push    rbp
0x18008e942  push    rsi
0x18008e943  push    rdi
0x18008e944  push    r12
0x18008e946  push    r13
0x18008e948  push    r14
0x18008e94a  push    r15
0x18008e94c  lea     rbp, [rsp-200h]
0x18008e954  sub     rsp, 300h
0x18008e95b  mov     rax, cs:__security_cookie
0x18008e962  xor     rax, rsp
0x18008e965  mov     [rbp+230h+var_40], rax
0x18008e96c  mov     rdi, r8
0x18008e96f  mov     [rbp+230h+var_2A8], r8
0x18008e973  mov     r12, rdx
0x18008e976  mov     [rbp+230h+var_2A0], rcx
0x18008e97a  mov     [rbp+230h+var_290], 1
0x18008e981  mov     [rbp+230h+var_288], r8
0x18008e985  xor     r13d, r13d
0x18008e988  mov     [rbp+230h+var_280], r13
0x18008e98c  mov     [rbp+230h+var_278], r13d
0x18008e990  mov     [rbp+230h+var_270], 0FFFFFFFF80000002h
0x18008e998  mov     edx, 20019h; samDesired
0x18008e99d  lea     rcx, [rbp+230h+var_290]; struct RegEntry *
0x18008e9a1  call    ?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmOpenKey(RegEntry const &,ulong)
0x18008e9a6  mov     r15, rax
0x18008e9a9  mov     [rbp+230h+var_298], rax
0x18008e9ad  mov     [rbp+230h+cSubKeys], r13d
0x18008e9b1  mov     [rsp+330h+cbMaxSubKeyLen], r13d
0x18008e9b6  mov     [rsp+330h+cValues], r13d
0x18008e9bb  mov     [rsp+330h+cbMaxValueNameLen], r13d
0x18008e9c0  mov     [rsp+330h+cbMaxValueLen], r13d
0x18008e9c5  mov     [rsp+330h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18008e9ca  mov     [rsp+330h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18008e9cf  lea     rax, [rsp+330h+cbMaxValueLen]
0x18008e9d4  mov     [rsp+330h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18008e9d9  lea     rax, [rsp+330h+cbMaxValueNameLen]
0x18008e9de  mov     [rsp+330h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18008e9e3  lea     rax, [rsp+330h+cValues]
0x18008e9e8  mov     [rsp+330h+lpcValues], rax; lpcValues
0x18008e9ed  mov     [rsp+330h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18008e9f2  lea     rax, [rsp+330h+cbMaxSubKeyLen]
0x18008e9f7  mov     [rsp+330h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18008e9fc  lea     rax, [rbp+230h+cSubKeys]
0x18008ea00  mov     [rsp+330h+lpcSubKeys], rax; lpcSubKeys
0x18008ea05  xor     r9d, r9d; lpReserved
0x18008ea08  xor     r8d, r8d; lpcchClass
0x18008ea0b  xor     edx, edx; lpClass
0x18008ea0d  mov     rcx, r15; hKey
0x18008ea10  call    cs:__imp_RegQueryInfoKeyW
0x18008ea16  mov     ebx, eax
0x18008ea18  test    eax, eax
0x18008ea1a  jz      short loc_18008EA39
0x18008ea1c  jle     short loc_18008EA27
0x18008ea1e  movzx   ebx, ax
0x18008ea21  or      ebx, 80070000h
0x18008ea27  test    ebx, ebx
0x18008ea29  jns     loc_18008EE85
0x18008ea2f  mov     r8d, 0D20h
0x18008ea35  mov     ecx, ebx
0x18008ea37  jmp     short loc_18008EA5F
0x18008ea39  mov     r9, rdi
0x18008ea3c  lea     r8, aS; "[%s]"
0x18008ea43  mov     edx, 100h; unsigned __int64
0x18008ea48  lea     rcx, [rbp+230h+var_240]; wchar_t *
0x18008ea4c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008ea51  mov     ebx, eax
0x18008ea53  test    eax, eax
0x18008ea55  jns     short loc_18008EA70
0x18008ea57  mov     r8d, 0D34h; unsigned __int16
0x18008ea5d  mov     ecx, eax; int
0x18008ea5f  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ea66  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ea6b  jmp     loc_18008EE85
0x18008ea70  lea     r8, [rbp+230h+var_240]; wchar_t *
0x18008ea74  mov     rdx, r12; void *
0x18008ea77  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008ea7c  mov     ebx, eax
0x18008ea7e  test    eax, eax
0x18008ea80  jns     short loc_18008EA8A
0x18008ea82  mov     r8d, 0D48h
0x18008ea88  jmp     short loc_18008EA5D
0x18008ea8a  lea     r8, asc_1801050C4; "\r\n"
0x18008ea91  mov     rdx, r12; void *
0x18008ea94  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008ea99  mov     ebx, eax
0x18008ea9b  test    eax, eax
0x18008ea9d  jns     short loc_18008EAA7
0x18008ea9f  mov     r8d, 0D5Ch
0x18008eaa5  jmp     short loc_18008EA5D
0x18008eaa7  mov     eax, [rsp+330h+cbMaxValueNameLen]
0x18008eaab  inc     eax
0x18008eaad  mov     [rsp+330h+cbMaxValueNameLen], eax
0x18008eab1  mov     ecx, eax
0x18008eab3  mov     eax, 2
0x18008eab8  mul     rcx
0x18008eabb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008eac2  cmovb   rax, rcx
0x18008eac6  mov     rcx, rax; unsigned __int64
0x18008eac9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008eace  mov     rbx, rax
0x18008ead1  mov     [rbp+230h+var_268], rax
0x18008ead5  mov     ecx, [rsp+330h+cbMaxValueLen]; unsigned __int64
0x18008ead9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008eade  mov     rdi, rax
0x18008eae1  mov     [rbp+230h+var_260], rax
0x18008eae5  mov     r14d, r13d
0x18008eae8  cmp     r14d, [rsp+330h+cValues]
0x18008eaed  jnb     loc_18008EC17
0x18008eaf3  mov     eax, [rsp+330h+cbMaxValueNameLen]
0x18008eaf7  mov     [rbp+230h+cchValueName], eax
0x18008eafa  mov     eax, [rsp+330h+cbMaxValueLen]
0x18008eafe  mov     [rsp+330h+cbData], eax
0x18008eb02  mov     [rsp+330h+Type], r13d
0x18008eb07  lea     rax, [rsp+330h+cbData]
0x18008eb0c  mov     [rsp+330h+lpcValues], rax; lpcbData
0x18008eb11  mov     [rsp+330h+lpcbMaxClassLen], rdi; lpData
0x18008eb16  lea     rax, [rsp+330h+Type]
0x18008eb1b  mov     [rsp+330h+lpcbMaxSubKeyLen], rax; lpType
0x18008eb20  mov     [rsp+330h+lpcSubKeys], r13; lpReserved
0x18008eb25  lea     r9, [rbp+230h+cchValueName]; lpcchValueName
0x18008eb29  mov     r8, rbx; lpValueName
0x18008eb2c  mov     edx, r14d; dwIndex
0x18008eb2f  mov     rcx, r15; hKey
0x18008eb32  call    cs:__imp_RegEnumValueW
0x18008eb38  mov     esi, eax
0x18008eb3a  test    eax, eax
0x18008eb3c  jnz     loc_18008EBD8
0x18008eb42  mov     eax, [rsp+330h+cbData]
0x18008eb46  mov     dword ptr [rsp+330h+lpcbMaxSubKeyLen], eax; unsigned int
0x18008eb4a  mov     [rsp+330h+lpcSubKeys], rdi; unsigned __int8 *
0x18008eb4f  mov     r9d, [rsp+330h+Type]; unsigned int
0x18008eb54  mov     r8, rbx; wchar_t *
0x18008eb57  mov     rdx, r12; void *
0x18008eb5a  call    ?WriteValueToFile@CMsmqVssWriter@@AEAAJPEAXPEB_WKPEAEK@Z; CMsmqVssWriter::WriteValueToFile(void *,wchar_t const *,ulong,uchar *,ulong)
0x18008eb5f  mov     esi, eax
0x18008eb61  test    eax, eax
0x18008eb63  js      short loc_18008EBAD
0x18008eb65  lea     r8, asc_1801050C4; "\r\n"
0x18008eb6c  mov     rdx, r12; void *
0x18008eb6f  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008eb74  mov     esi, eax
0x18008eb76  test    eax, eax
0x18008eb78  js      short loc_18008EB82
0x18008eb7a  inc     r14d
0x18008eb7d  jmp     loc_18008EAE8
0x18008eb82  mov     r8d, 0D98h; unsigned __int16
0x18008eb88  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008eb8f  mov     ecx, esi; int
0x18008eb91  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008eb96  nop
0x18008eb97  mov     rcx, rdi; Block
0x18008eb9a  call    cs:__imp_free
0x18008eba0  nop
0x18008eba1  mov     rcx, rbx; Block
0x18008eba4  call    cs:__imp_free
0x18008ebaa  nop
0x18008ebab  jmp     short loc_18008EC10
0x18008ebad  mov     r8d, 0D84h; unsigned __int16
0x18008ebb3  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ebba  mov     ecx, esi; int
0x18008ebbc  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ebc1  nop
0x18008ebc2  mov     rcx, rdi; Block
0x18008ebc5  call    cs:__imp_free
0x18008ebcb  nop
0x18008ebcc  mov     rcx, rbx; Block
0x18008ebcf  call    cs:__imp_free
0x18008ebd5  nop
0x18008ebd6  jmp     short loc_18008EC10
0x18008ebd8  jle     short loc_18008EBE3
0x18008ebda  movzx   esi, ax
0x18008ebdd  or      esi, 80070000h
0x18008ebe3  test    esi, esi
0x18008ebe5  jns     short loc_18008EBFC
0x18008ebe7  mov     r8d, 0D70h; unsigned __int16
0x18008ebed  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ebf4  mov     ecx, esi; int
0x18008ebf6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ebfb  nop
0x18008ebfc  mov     rcx, rdi; Block
0x18008ebff  call    cs:__imp_free
0x18008ec05  nop
0x18008ec06  mov     rcx, rbx; Block
0x18008ec09  call    cs:__imp_free
0x18008ec0f  nop
0x18008ec10  mov     ebx, esi
0x18008ec12  jmp     loc_18008EE85
0x18008ec17  lea     r8, asc_1801050C4; "\r\n"
0x18008ec1e  mov     rdx, r12; void *
0x18008ec21  call    ?WriteStringToFile@CMsmqVssWriter@@AEAAJPEAXPEB_W@Z; CMsmqVssWriter::WriteStringToFile(void *,wchar_t const *)
0x18008ec26  mov     esi, eax
0x18008ec28  test    eax, eax
0x18008ec2a  jns     short loc_18008EC57
0x18008ec2c  mov     r8d, 0DACh; unsigned __int16
0x18008ec32  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ec39  mov     ecx, eax; int
0x18008ec3b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ec40  nop
0x18008ec41  mov     rcx, rdi; Block
0x18008ec44  call    cs:__imp_free
0x18008ec4a  nop
0x18008ec4b  mov     rcx, rbx; Block
0x18008ec4e  call    cs:__imp_free
0x18008ec54  nop
0x18008ec55  jmp     short loc_18008EC10
0x18008ec57  mov     eax, [rsp+330h+cbMaxSubKeyLen]
0x18008ec5b  inc     eax
0x18008ec5d  mov     [rsp+330h+cbMaxSubKeyLen], eax
0x18008ec61  mov     ecx, eax
0x18008ec63  mov     eax, 2
0x18008ec68  mul     rcx
0x18008ec6b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008ec72  cmovb   rax, rcx
0x18008ec76  mov     rcx, rax; unsigned __int64
0x18008ec79  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008ec7e  mov     r14, rax
0x18008ec81  mov     [rbp+230h+var_258], rax
0x18008ec85  cmp     r13d, [rbp+230h+cSubKeys]
0x18008ec89  jnb     loc_18008EE65
0x18008ec8f  mov     eax, [rsp+330h+cbMaxSubKeyLen]
0x18008ec93  mov     [rsp+330h+cchName], eax
0x18008ec97  xor     eax, eax
0x18008ec99  mov     [rsp+330h+lpcValues], rax; lpftLastWriteTime
0x18008ec9e  mov     [rsp+330h+lpcbMaxClassLen], rax; lpcchClass
0x18008eca3  mov     [rsp+330h+lpcbMaxSubKeyLen], rax; lpClass
0x18008eca8  mov     [rsp+330h+lpcSubKeys], rax; lpReserved
0x18008ecad  lea     r9, [rsp+330h+cchName]; lpcchName
0x18008ecb2  mov     r8, r14; lpName
0x18008ecb5  mov     edx, r13d; dwIndex
0x18008ecb8  mov     rcx, r15; hKey
0x18008ecbb  call    cs:__imp_RegEnumKeyExW
0x18008ecc1  mov     esi, eax
0x18008ecc3  test    eax, eax
0x18008ecc5  jnz     loc_18008EE1E
0x18008eccb  mov     rcx, [rbp+230h+var_2A8]; wchar_t *
0x18008eccf  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18008ecd4  mov     edx, [rsp+330h+cchName]
0x18008ecd8  add     edx, 2
0x18008ecdb  add     edx, eax
0x18008ecdd  mov     [rsp+330h+cchName], edx
0x18008ece1  mov     ecx, edx
0x18008ece3  lea     eax, [rsi+2]
0x18008ece6  mul     rcx
0x18008ece9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008ecf0  cmovb   rax, rcx
0x18008ecf4  mov     rcx, rax; unsigned __int64
0x18008ecf7  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008ecfc  mov     rsi, rax
0x18008ecff  mov     [rbp+230h+var_250], rax
0x18008ed03  mov     edx, [rsp+330h+cchName]; unsigned __int64
0x18008ed07  mov     [rsp+330h+lpcSubKeys], r14
0x18008ed0c  mov     r9, [rbp+230h+var_2A8]
0x18008ed10  lea     r8, aSS_3; "%s\\%s"
0x18008ed17  mov     rcx, rax; wchar_t *
0x18008ed1a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008ed1f  mov     [rsp+330h+var_2C0], eax
0x18008ed23  test    eax, eax
0x18008ed25  js      loc_18008EDDB
0x18008ed2b  mov     rax, [rbp+230h+var_2A0]
0x18008ed2f  cmp     qword ptr [rax+28h], 0
0x18008ed34  jnz     short loc_18008ED6E
0x18008ed36  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\MSMQ\\Clustered QM"...
0x18008ed3d  mov     rcx, rsi; String1
0x18008ed40  call    cs:__imp__wcsicmp
0x18008ed46  test    eax, eax
0x18008ed48  jz      short loc_18008ED5E
0x18008ed4a  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\MSMQ\\Triggers\\Cl"...
0x18008ed51  mov     rcx, rsi; String1
0x18008ed54  call    cs:__imp__wcsicmp
0x18008ed5a  test    eax, eax
0x18008ed5c  jnz     short loc_18008ED6A
0x18008ed5e  mov     rcx, rsi; Block
0x18008ed61  call    cs:__imp_free
0x18008ed67  nop
0x18008ed68  jmp     short loc_18008ED94
0x18008ed6a  mov     rax, [rbp+230h+var_2A0]
0x18008ed6e  mov     r9d, 1; int
0x18008ed74  mov     r8, rsi; wchar_t *
0x18008ed77  mov     rdx, r12; void *
0x18008ed7a  mov     rcx, rax; this
0x18008ed7d  call    ?BackupRegistryKeyInternal@CMsmqVssWriter@@AEAAJPEAXPEB_WH@Z; CMsmqVssWriter::BackupRegistryKeyInternal(void *,wchar_t const *,int)
0x18008ed82  mov     [rsp+330h+var_2C0], eax
0x18008ed86  test    eax, eax
0x18008ed88  js      short loc_18008ED9C
0x18008ed8a  mov     rcx, rsi; Block
0x18008ed8d  call    cs:__imp_free
0x18008ed93  nop
0x18008ed94  inc     r13d
0x18008ed97  jmp     loc_18008EC85
0x18008ed9c  mov     r8d, 0DE8h; unsigned __int16
0x18008eda2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008eda9  mov     ecx, eax; int
0x18008edab  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008edb0  nop
0x18008edb1  mov     rcx, rsi; Block
0x18008edb4  call    cs:__imp_free
0x18008edba  nop
0x18008edbb  mov     rcx, r14; Block
  ... truncated ...
```
