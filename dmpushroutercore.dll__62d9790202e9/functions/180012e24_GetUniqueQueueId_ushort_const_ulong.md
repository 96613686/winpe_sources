# GetUniqueQueueId(ushort const *,ulong *)

- ea: `0x180012e24`
- end: `0x18001321b`
- name: `?GetUniqueQueueId@@YAJPEBGPEAK@Z`
- size: `1015`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012860`
- `0x180016110`

## callees

- `0x1800043a8`
- `0x180012738`
- `0x180012e24`
- `0x180013458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800130ff`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800130ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013060`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012eec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013176`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012eec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013176`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e97`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012e6b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180012e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012fcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013000`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180012f10`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001308b`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180012f10`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001308b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetUniqueQueueId(const unsigned __int16 *a1, unsigned int *a2)
{
  DWORD v2; // r15d
  WCHAR *v4; // r12
  unsigned int *v5; // r13
  char IsStateSeparationEnabled; // r14
  LSTATUS v7; // eax
  signed int DWORD; // ebx
  bool v9; // cc
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HKEY v12; // rcx
  unsigned int v13; // eax
  signed int v14; // ecx
  unsigned __int64 v15; // rax
  DWORD v16; // ebx
  DWORD v17; // ecx
  HKEY v18; // rcx
  const unsigned __int16 *v19; // r8
  HKEY v20; // rcx
  __int64 v21; // rcx
  const unsigned __int16 *v22; // r8
  unsigned int v23; // ecx
  DWORD i; // edx
  const unsigned __int16 *v25; // rdx
  HKEY v26; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  HKEY v32; // [rsp+70h] [rbp-10h] BYREF
  HKEY v33; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v35; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  hKey = 0;
  v4 = 0;
  cSubKeys = 0;
  v5 = 0;
  cchName = 0;
  cbMaxSubKeyLen = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\PushRouter\\Registrations\\ByGenericId",
         0,
         0x20019u,
         &hKey);
  DWORD = v7;
  v9 = v7 <= 0;
  if ( v7 )
  {
LABEL_2:
    if ( !v9 )
      DWORD = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_45;
  }
  if ( IsStateSeparationEnabled )
  {
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, c_szAppRegistrationByGenIdStateSep, 0, 0, 0, 0x2001Fu, 0, &v32, 0);
    DWORD = v7;
    v9 = v7 <= 0;
    if ( v7 )
      goto LABEL_2;
    v10 = v32;
  }
  else
  {
    v10 = hKey;
  }
  DWORD = OmaDmRegistryGetDWORD(v10, a1, L"QueueId", &v35);
  if ( DWORD != -2147023267 )
  {
    if ( ((DWORD + 0x80000000) & 0x80000000) == 0 && DWORD != -2147024894 )
      goto LABEL_45;
LABEL_15:
    v13 = v35;
    if ( v35 )
      goto LABEL_44;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    DWORD = v7;
    v9 = v7 <= 0;
    if ( v7 )
      goto LABEL_2;
    v14 = cbMaxSubKeyLen + 1;
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
    }
    else
    {
      ++cbMaxSubKeyLen;
      if ( v14 >= 0 )
      {
        v4 = (WCHAR *)LocalAlloc(0, (unsigned int)(2 * v14));
        if ( !v4 )
        {
          DWORD = -2147024882;
          goto LABEL_45;
        }
        v15 = 4LL * cSubKeys;
        if ( v15 <= 0xFFFFFFFF )
        {
          v16 = 4 * cSubKeys;
          v5 = (unsigned int *)LocalAlloc(0, (unsigned int)v15);
          memset_0(v5, 0, v16);
          v17 = cSubKeys;
          if ( cSubKeys )
          {
            do
            {
              v35 = 0;
              cchName = cbMaxSubKeyLen;
              v7 = RegEnumKeyExW(hKey, v2, v4, &cchName, 0, 0, 0, 0);
              DWORD = v7;
              v9 = v7 <= 0;
              if ( v7 )
                goto LABEL_2;
              v18 = v32;
              if ( !IsStateSeparationEnabled )
                v18 = hKey;
              DWORD = OmaDmRegistryGetDWORD(v18, v4, L"QueueId", &v35);
              if ( DWORD == -2147023267 )
              {
                v20 = v32;
                if ( !IsStateSeparationEnabled )
                  v20 = hKey;
                DWORD = DeleteValue(v20, a1, v19);
                if ( DWORD < 0 )
                  goto LABEL_45;
              }
              else if ( (int)(DWORD + 0x80000000) >= 0 && DWORD != -2147024894 )
              {
                goto LABEL_45;
              }
              v21 = v2++;
              v5[v21] = v35;
              v17 = cSubKeys;
            }
            while ( v2 < cSubKeys );
          }
          qsort(v5, v17, 4u, SortQueueId);
          v35 = 0;
          v23 = 0;
          for ( i = 0; i < cSubKeys; v23 = (unsigned int)v22 )
          {
            v22 = (const unsigned __int16 *)v5[i];
            if ( v5[i] - v23 > 1 )
              break;
            ++i;
          }
          if ( v23 + 1 >= v23 )
          {
            v35 = v23 + 1;
            v25 = a1;
            if ( IsStateSeparationEnabled )
            {
              v7 = RegCreateKeyExW(v32, a1, 0, 0, 0, 0x2001Fu, 0, &v33, 0);
              DWORD = v7;
              v9 = v7 <= 0;
              if ( v7 )
                goto LABEL_2;
              v26 = v32;
              v25 = a1;
            }
            else
            {
              v26 = hKey;
            }
            DWORD = SetValue(v26, v25, v22, (unsigned __int8 *const)&v35, phkResult);
            if ( DWORD < 0 )
              goto LABEL_45;
            v13 = v35;
LABEL_44:
            *a2 = v13;
            goto LABEL_45;
          }
          v35 = -1;
        }
      }
    }
    DWORD = -2147024362;
    goto LABEL_45;
  }
  v12 = v32;
  if ( !IsStateSeparationEnabled )
    v12 = hKey;
  DWORD = DeleteValue(v12, a1, v11);
  if ( DWORD >= 0 )
    goto LABEL_15;
LABEL_45:
  LocalFree(v4);
  LocalFree(v5);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v32 )
    RegCloseKey(v32);
  if ( v33 )
    RegCloseKey(v33);
  return (unsigned int)DWORD;
}

```

## disassembly

```asm
0x180012e24  mov     [rsp-38h+arg_0], rbx
0x180012e29  mov     [rsp-38h+arg_8], rdx
0x180012e2e  push    rbp
0x180012e2f  push    rsi
0x180012e30  push    rdi
0x180012e31  push    r12
0x180012e33  push    r13
0x180012e35  push    r14
0x180012e37  push    r15
0x180012e39  mov     rbp, rsp
0x180012e3c  sub     rsp, 80h
0x180012e43  xor     r15d, r15d
0x180012e46  mov     rdi, rcx
0x180012e49  mov     [rbp+hKey], r15
0x180012e4d  mov     r12d, r15d
0x180012e50  mov     [rbp+cSubKeys], r15d
0x180012e54  mov     r13d, r15d
0x180012e57  mov     [rbp+cchName], r15d
0x180012e5b  mov     [rbp+cbMaxSubKeyLen], r15d
0x180012e5f  mov     [rbp+arg_10], r15d
0x180012e63  mov     [rbp+var_10], r15
0x180012e67  mov     [rbp+var_8], r15
0x180012e6b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180012e71  mov     rsi, 0FFFFFFFF80000002h
0x180012e78  lea     rdx, ?c_szAppRegistrationByGenId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x180012e7f  mov     r14b, al
0x180012e82  mov     r9d, 20019h; samDesired
0x180012e88  lea     rax, [rbp+hKey]
0x180012e8c  xor     r8d, r8d; ulOptions
0x180012e8f  mov     rcx, rsi; hKey
0x180012e92  mov     [rsp+80h+phkResult], rax; phkResult
0x180012e97  call    cs:__imp_RegOpenKeyExW
0x180012e9d  mov     ebx, eax
0x180012e9f  test    eax, eax
0x180012ea1  jz      short loc_180012EB7
0x180012ea3  jle     loc_1800131AB
0x180012ea9  movzx   ebx, ax
0x180012eac  or      ebx, 80070000h
0x180012eb2  jmp     loc_1800131AB
0x180012eb7  test    r14b, r14b
0x180012eba  jz      short loc_180012EFE
0x180012ebc  mov     rdx, cs:?c_szAppRegistrationByGenIdStateSep@@3QEAGEA; lpSubKey
0x180012ec3  lea     rax, [rbp+var_10]
0x180012ec7  mov     [rsp+80h+lpdwDisposition], r15; lpdwDisposition
0x180012ecc  xor     r9d, r9d; lpClass
0x180012ecf  mov     [rsp+80h+var_48], rax; phkResult
0x180012ed4  xor     r8d, r8d; Reserved
0x180012ed7  mov     [rsp+80h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180012edc  mov     rcx, rsi; hKey
0x180012edf  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x180012ee7  mov     dword ptr [rsp+80h+phkResult], r15d; dwOptions
0x180012eec  call    cs:__imp_RegCreateKeyExW
0x180012ef2  mov     ebx, eax
0x180012ef4  test    eax, eax
0x180012ef6  jnz     short loc_180012EA3
0x180012ef8  mov     rcx, [rbp+var_10]
0x180012efc  jmp     short loc_180012F02
0x180012efe  mov     rcx, [rbp+hKey]
0x180012f02  lea     r9, [rbp+arg_10]
0x180012f06  mov     rdx, rdi
0x180012f09  lea     r8, ?c_szQueueId@@3QBGB; "QueueId"
0x180012f10  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180012f16  mov     ebx, eax
0x180012f18  mov     ecx, 80000000h
0x180012f1d  cmp     eax, 8007065Dh
0x180012f22  jnz     short loc_180012F45
0x180012f24  mov     rcx, [rbp+var_10]
0x180012f28  mov     rdx, rdi; unsigned __int16 *
0x180012f2b  test    r14b, r14b
0x180012f2e  jnz     short loc_180012F34
0x180012f30  mov     rcx, [rbp+hKey]; HKEY
0x180012f34  call    ?DeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; DeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180012f39  mov     ebx, eax
0x180012f3b  test    eax, eax
0x180012f3d  js      loc_1800131AB
0x180012f43  jmp     short loc_180012F58
0x180012f45  lea     eax, [rbx+rcx]
0x180012f48  test    ecx, eax
0x180012f4a  jnz     short loc_180012F58
0x180012f4c  cmp     ebx, 80070002h
0x180012f52  jnz     loc_1800131AB
0x180012f58  mov     eax, [rbp+arg_10]
0x180012f5b  test    eax, eax
0x180012f5d  jnz     loc_1800131A5
0x180012f63  mov     rcx, [rbp+hKey]; hKey
0x180012f67  lea     rax, [rbp+cbMaxSubKeyLen]
0x180012f6b  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180012f70  xor     r9d, r9d; lpReserved
0x180012f73  mov     [rsp+80h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180012f78  xor     r8d, r8d; lpcchClass
0x180012f7b  mov     [rsp+80h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180012f80  xor     edx, edx; lpClass
0x180012f82  mov     [rsp+80h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x180012f87  mov     [rsp+80h+var_48], r15; lpcValues
0x180012f8c  mov     [rsp+80h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x180012f91  mov     qword ptr [rsp+80h+samDesired], rax; lpcbMaxSubKeyLen
0x180012f96  lea     rax, [rbp+cSubKeys]
0x180012f9a  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x180012f9f  call    cs:__imp_RegQueryInfoKeyW
0x180012fa5  mov     ebx, eax
0x180012fa7  test    eax, eax
0x180012fa9  jnz     loc_180012EA3
0x180012faf  mov     eax, [rbp+cbMaxSubKeyLen]
0x180012fb2  lea     ecx, [rax+1]
0x180012fb5  cmp     ecx, eax
0x180012fb7  jb      loc_180013211
0x180012fbd  mov     [rbp+cbMaxSubKeyLen], ecx
0x180012fc0  test    ecx, ecx
0x180012fc2  js      loc_18001320A
0x180012fc8  lea     edx, [rcx+rcx]; uBytes
0x180012fcb  xor     ecx, ecx; uFlags
0x180012fcd  call    cs:__imp_LocalAlloc
0x180012fd3  mov     r12, rax
0x180012fd6  test    rax, rax
0x180012fd9  jnz     short loc_180012FE5
0x180012fdb  mov     ebx, 8007000Eh
0x180012fe0  jmp     loc_1800131AB
0x180012fe5  mov     eax, [rbp+cSubKeys]
0x180012fe8  mov     esi, 0FFFFFFFFh
0x180012fed  shl     rax, 2
0x180012ff1  cmp     rax, rsi
0x180012ff4  ja      loc_18001320A
0x180012ffa  mov     edx, eax; uBytes
0x180012ffc  xor     ecx, ecx; uFlags
0x180012ffe  mov     ebx, eax
0x180013000  call    cs:__imp_LocalAlloc
0x180013006  mov     r8d, ebx; Size
0x180013009  xor     edx, edx; Val
0x18001300b  mov     rcx, rax; void *
0x18001300e  mov     r13, rax
0x180013011  call    memset_0
0x180013016  mov     ecx, [rbp+cSubKeys]
0x180013019  test    ecx, ecx
0x18001301b  jz      loc_1800130ED
0x180013021  mov     eax, [rbp+cbMaxSubKeyLen]
0x180013024  lea     r9, [rbp+cchName]; lpcchName
0x180013028  mov     rcx, [rbp+hKey]; hKey
0x18001302c  mov     r8, r12; lpName
0x18001302f  mov     [rsp+80h+var_48], 0; lpftLastWriteTime
0x180013038  mov     edx, r15d; dwIndex
0x18001303b  mov     [rsp+80h+lpSecurityAttributes], 0; lpcchClass
0x180013044  mov     qword ptr [rsp+80h+samDesired], 0; lpClass
0x18001304d  mov     [rsp+80h+phkResult], 0; unsigned int
0x180013056  mov     [rbp+arg_10], 0
0x18001305d  mov     [rbp+cchName], eax
0x180013060  call    cs:__imp_RegEnumKeyExW
0x180013066  mov     ebx, eax
0x180013068  test    eax, eax
0x18001306a  jnz     loc_180012EA3
0x180013070  mov     rcx, [rbp+var_10]
0x180013074  lea     r9, [rbp+arg_10]
0x180013078  lea     r8, ?c_szQueueId@@3QBGB; "QueueId"
0x18001307f  mov     rdx, r12
0x180013082  test    r14b, r14b
0x180013085  jnz     short loc_18001308B
0x180013087  mov     rcx, [rbp+hKey]
0x18001308b  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180013091  mov     ebx, eax
0x180013093  cmp     eax, 8007065Dh
0x180013098  jnz     short loc_1800130BB
0x18001309a  mov     rcx, [rbp+var_10]
0x18001309e  mov     rdx, rdi; unsigned __int16 *
0x1800130a1  test    r14b, r14b
0x1800130a4  jnz     short loc_1800130AA
0x1800130a6  mov     rcx, [rbp+hKey]; HKEY
0x1800130aa  call    ?DeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; DeleteValue(HKEY__ *,ushort const *,ushort const *)
0x1800130af  mov     ebx, eax
0x1800130b1  test    eax, eax
0x1800130b3  js      loc_1800131AB
0x1800130b9  jmp     short loc_1800130D3
0x1800130bb  mov     ecx, 80000000h
0x1800130c0  lea     eax, [rbx+rcx]
0x1800130c3  test    ecx, eax
0x1800130c5  jnz     short loc_1800130D3
0x1800130c7  cmp     ebx, 80070002h
0x1800130cd  jnz     loc_1800131AB
0x1800130d3  mov     eax, [rbp+arg_10]
0x1800130d6  mov     ecx, r15d
0x1800130d9  inc     r15d
0x1800130dc  mov     [r13+rcx*4+0], eax
0x1800130e1  mov     ecx, [rbp+cSubKeys]
0x1800130e4  cmp     r15d, ecx
0x1800130e7  jb      loc_180013021
0x1800130ed  mov     edx, ecx; NumOfElements
0x1800130ef  lea     r9, SortQueueId; CompareFunction
0x1800130f6  mov     rcx, r13; Base
0x1800130f9  mov     r8d, 4; SizeOfElements
0x1800130ff  call    cs:__imp_qsort
0x180013105  mov     r9d, [rbp+cSubKeys]
0x180013109  xor     r15d, r15d
0x18001310c  mov     [rbp+arg_10], r15d
0x180013110  mov     ecx, r15d
0x180013113  mov     edx, r15d
0x180013116  test    r9d, r9d
0x180013119  jz      short loc_180013136
0x18001311b  mov     eax, edx
0x18001311d  mov     r8d, [r13+rax*4+0]; unsigned __int16 *
0x180013122  mov     eax, r8d
0x180013125  sub     eax, ecx
0x180013127  cmp     eax, 1
0x18001312a  ja      short loc_180013136
0x18001312c  inc     edx
0x18001312e  mov     ecx, r8d
0x180013131  cmp     edx, r9d
0x180013134  jb      short loc_18001311B
0x180013136  lea     eax, [rcx+1]
0x180013139  cmp     eax, ecx
0x18001313b  jb      loc_180013207
0x180013141  mov     [rbp+arg_10], eax
0x180013144  mov     rdx, rdi; unsigned __int16 *
0x180013147  test    r14b, r14b
0x18001314a  jz      short loc_18001318F
0x18001314c  mov     rcx, [rbp+var_10]; hKey
0x180013150  lea     rax, [rbp+var_8]
0x180013154  mov     [rsp+80h+lpdwDisposition], r15; lpdwDisposition
0x180013159  xor     r9d, r9d; lpClass
0x18001315c  mov     [rsp+80h+var_48], rax; phkResult
0x180013161  xor     r8d, r8d; Reserved
0x180013164  mov     [rsp+80h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180013169  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x180013171  mov     dword ptr [rsp+80h+phkResult], r15d; dwOptions
0x180013176  call    cs:__imp_RegCreateKeyExW
0x18001317c  mov     ebx, eax
0x18001317e  test    eax, eax
0x180013180  jnz     loc_180012EA3
0x180013186  mov     rcx, [rbp+var_10]
0x18001318a  mov     rdx, rdi
0x18001318d  jmp     short loc_180013193
0x18001318f  mov     rcx, [rbp+hKey]; HKEY
0x180013193  lea     r9, [rbp+arg_10]; unsigned __int8 *
0x180013197  call    ?SetValue@@YAJPEAUHKEY__@@PEBG1QEAEK@Z; SetValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong)
0x18001319c  mov     ebx, eax
0x18001319e  test    eax, eax
0x1800131a0  js      short loc_1800131AB
0x1800131a2  mov     eax, [rbp+arg_10]
0x1800131a5  mov     rcx, [rbp+arg_8]
0x1800131a9  mov     [rcx], eax
0x1800131ab  mov     rcx, r12; hMem
0x1800131ae  call    cs:__imp_LocalFree
0x1800131b4  mov     rcx, r13; hMem
0x1800131b7  call    cs:__imp_LocalFree
0x1800131bd  mov     rcx, [rbp+hKey]; hKey
0x1800131c1  test    rcx, rcx
0x1800131c4  jz      short loc_1800131CC
0x1800131c6  call    cs:__imp_RegCloseKey
0x1800131cc  mov     rcx, [rbp+var_10]; hKey
0x1800131d0  test    rcx, rcx
0x1800131d3  jz      short loc_1800131DB
0x1800131d5  call    cs:__imp_RegCloseKey
0x1800131db  mov     rcx, [rbp+var_8]; hKey
0x1800131df  test    rcx, rcx
0x1800131e2  jz      short loc_1800131EA
0x1800131e4  call    cs:__imp_RegCloseKey
0x1800131ea  mov     eax, ebx
0x1800131ec  mov     rbx, [rsp+80h+arg_0]
0x1800131f4  add     rsp, 80h
0x1800131fb  pop     r15
0x1800131fd  pop     r14
0x1800131ff  pop     r13
0x180013201  pop     r12
0x180013203  pop     rdi
0x180013204  pop     rsi
0x180013205  pop     rbp
0x180013206  retn
0x180013207  mov     [rbp+arg_10], esi
0x18001320a  mov     ebx, 80070216h
0x18001320f  jmp     short loc_1800131AB
0x180013211  mov     esi, 0FFFFFFFFh
0x180013216  mov     [rbp+cbMaxSubKeyLen], esi
0x180013219  jmp     short loc_18001320A
```
