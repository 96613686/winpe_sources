# RegisterComClass(ushort const *,ushort const *,ushort const *,_GUID)

- ea: `0x180041960`
- end: `0x180041e78`
- name: `?RegisterComClass@@YAJPEBG00U_GUID@@@Z`
- size: `1304`
- prototype: `__int64 __fastcall(BYTE *lpData, BYTE *, BYTE *, UUID *Uuid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001fae0`

## callees

- `0x180041960`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041af2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041b6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041c27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041c99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041ccd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041db3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041af2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041b6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041c27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041c99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041ccd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041db3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041b98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041e10`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041a9d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041bef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041c64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041d78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041a9d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041bef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041c64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041d78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180041e4d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180041e4d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041b4e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041bba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041d97`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041b4e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041bba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180041d97`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800419dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800419dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041a28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041d09`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041a28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180041d09`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041a41`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041a5c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041d22`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041d3d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041a41`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041a5c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041d22`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180041d3d`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180041b41`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180041d8a`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180041b41`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180041d8a`
- `RPCRT4!UuidToStringW` at `0x180041a0d`
- `RPCRT4!UuidToStringW` at `0x180041cf0`
- `RPCRT4!UuidToStringW` at `0x180041a0d`
- `RPCRT4!UuidToStringW` at `0x180041cf0`
- `RPCRT4!RpcStringFreeW` at `0x180041e27`
- `RPCRT4!RpcStringFreeW` at `0x180041e3e`
- `RPCRT4!RpcStringFreeW` at `0x180041e27`
- `RPCRT4!RpcStringFreeW` at `0x180041e3e`

## string_xrefs

- `0x180041b0b`: `CLSID`
- `0x180041b8a`: `CLSID`
- `0x180041cbb`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall RegisterComClass(const WCHAR *lpData, BYTE *a2, BYTE *a3, UUID *Uuid)
{
  int v8; // edi
  LSTATUS v9; // eax
  bool v10; // cc
  __int64 v11; // rsi
  __int64 v12; // rax
  DWORD v13; // ebx
  const BYTE *Str; // rax
  const WCHAR *v15; // rax
  __int64 v16; // rax
  DWORD v17; // ebx
  const BYTE *v18; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v21; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR StringUuid; // [rsp+68h] [rbp-98h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp-90h] BYREF
  HKEY v25; // [rsp+78h] [rbp-88h] BYREF
  HKEY v26; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[56]; // [rsp+88h] [rbp-78h] BYREF
  UUID Uuida; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v29[256]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  phkResult = 0;
  v26 = 0;
  v21 = 0;
  v25 = 0;
  StringUuid = 0;
  String = 0;
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v27, v29, 0x100u);
  Uuida = 0;
  if ( lpData && a2 && a3 )
  {
    v8 = UuidToStringW(Uuid, &StringUuid);
    if ( !v8 )
    {
      v8 = STRU::Copy((STRU *)v27, L"{");
      if ( v8 >= 0 )
      {
        v8 = STRU::Append((STRU *)v27, StringUuid);
        if ( v8 >= 0 )
        {
          v8 = STRU::Append((STRU *)v27, L"}");
          if ( v8 >= 0 )
          {
            v9 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpData, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v11 = -1;
            v12 = -1;
            do
              ++v12;
            while ( *(_WORD *)&a2[2 * v12] );
            v9 = RegSetValueExW(hKey, 0, 0, 1u, a2, 2 * v12 + 2);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v9 = RegCreateKeyExW(hKey, L"CLSID", 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v13 = STRU::QueryCB((STRU *)v27) + 2;
            Str = (const BYTE *)STRU::QueryStr((STRU *)v27);
            v9 = RegSetValueExW(phkResult, 0, 0, 1u, Str, v13);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &v26);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            RegCloseKey(phkResult);
            phkResult = 0;
            v15 = STRU::QueryStr((STRU *)v27);
            v9 = RegCreateKeyExW(v26, v15, 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v16 = -1;
            do
              ++v16;
            while ( lpData[v16] );
            v9 = RegSetValueExW(phkResult, 0, 0, 1u, (const BYTE *)lpData, 2 * v16 + 2);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v9 = RegCreateKeyExW(phkResult, L"InProcServer32", 0, 0, 0, 0x2000000u, 0, &v21, 0);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            do
              ++v11;
            while ( *(_WORD *)&a3[2 * v11] );
            v9 = RegSetValueExW(v21, 0, 0, 1u, a3, 2 * v11 + 2);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            v9 = RegSetValueExW(v21, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
            v10 = v9 <= 0;
            if ( v9 )
              goto LABEL_9;
            Uuida = LIBID_AppHostAdminLibrary;
            if ( !UuidToStringW(&Uuida, &String) )
            {
              v8 = STRU::Copy((STRU *)v27, L"{");
              if ( v8 >= 0 )
              {
                v8 = STRU::Append((STRU *)v27, String);
                if ( v8 >= 0 )
                {
                  v8 = STRU::Append((STRU *)v27, L"}");
                  if ( v8 >= 0 )
                  {
                    v9 = RegCreateKeyExW(phkResult, L"TypeLib", 0, 0, 0, 0x2000000u, 0, &v25, 0);
                    v10 = v9 <= 0;
                    if ( v9
                      || (v17 = STRU::QueryCB((STRU *)v27) + 2,
                          v18 = (const BYTE *)STRU::QueryStr((STRU *)v27),
                          v9 = RegSetValueExW(v25, 0, 0, 1u, v18, v17),
                          v10 = v9 <= 0,
                          v9) )
                    {
LABEL_9:
                      if ( v10 )
                        v8 = v9;
                      else
                        v8 = (unsigned __int16)v9 | 0x80070000;
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
  else
  {
    v8 = -2147024809;
  }
  if ( v21 )
  {
    RegCloseKey(v21);
    v21 = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v25 )
  {
    RegCloseKey(v25);
    v25 = 0;
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( String )
  {
    RpcStringFreeW(&String);
    String = 0;
  }
  STRU::~STRU((STRU *)v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180041960  push    rbp
0x180041962  push    rbx
0x180041963  push    rsi
0x180041964  push    rdi
0x180041965  push    r12
0x180041967  push    r13
0x180041969  push    r14
0x18004196b  push    r15
0x18004196d  lea     rbp, [rsp-1E8h]
0x180041975  sub     rsp, 2E8h
0x18004197c  mov     rax, cs:__security_cookie
0x180041983  xor     rax, rsp
0x180041986  mov     [rbp+220h+var_50], rax
0x18004198d  xor     r12d, r12d
0x180041990  mov     r15, r8
0x180041993  mov     rbx, rdx
0x180041996  mov     [rsp+320h+hKey], r12
0x18004199b  mov     r14, rcx
0x18004199e  mov     [rsp+320h+var_2D0], r12
0x1800419a3  xor     edx, edx; Val
0x1800419a5  mov     [rbp+220h+var_2A0], r12
0x1800419a9  mov     r8d, 200h; Size
0x1800419af  mov     [rsp+320h+var_2C8], r12
0x1800419b4  lea     rcx, [rbp+220h+var_250]; void *
0x1800419b8  mov     [rsp+320h+var_2A8], r12
0x1800419bd  mov     [rsp+320h+StringUuid], r12
0x1800419c2  mov     rdi, r9
0x1800419c5  mov     [rsp+320h+String], r12
0x1800419ca  call    memset_0
0x1800419cf  mov     r8d, 100h
0x1800419d5  lea     rdx, [rbp+220h+var_250]
0x1800419d9  lea     rcx, [rbp+220h+var_298]
0x1800419dd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800419e3  xorps   xmm0, xmm0
0x1800419e6  movups  xmmword ptr [rbp+220h+Uuid.Data1], xmm0
0x1800419ea  test    r14, r14
0x1800419ed  jz      loc_180041DC2
0x1800419f3  test    rbx, rbx
0x1800419f6  jz      loc_180041DC2
0x1800419fc  test    r15, r15
0x1800419ff  jz      loc_180041DC2
0x180041a05  lea     rdx, [rsp+320h+StringUuid]; StringUuid
0x180041a0a  mov     rcx, rdi; Uuid
0x180041a0d  call    cs:__imp_UuidToStringW
0x180041a13  mov     edi, eax
0x180041a15  test    eax, eax
0x180041a17  jnz     loc_180041DC7
0x180041a1d  lea     rdx, asc_180062380; "{"
0x180041a24  lea     rcx, [rbp+220h+var_298]
0x180041a28  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180041a2e  mov     edi, eax
0x180041a30  test    eax, eax
0x180041a32  js      loc_180041DC7
0x180041a38  mov     rdx, [rsp+320h+StringUuid]
0x180041a3d  lea     rcx, [rbp+220h+var_298]
0x180041a41  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041a47  mov     edi, eax
0x180041a49  test    eax, eax
0x180041a4b  js      loc_180041DC7
0x180041a51  lea     rdx, asc_180062384; "}"
0x180041a58  lea     rcx, [rbp+220h+var_298]
0x180041a5c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041a62  mov     edi, eax
0x180041a64  test    eax, eax
0x180041a66  js      loc_180041DC7
0x180041a6c  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180041a71  lea     rax, [rsp+320h+hKey]
0x180041a76  mov     [rsp+320h+phkResult], rax; phkResult
0x180041a7b  xor     r9d, r9d; lpClass
0x180041a7e  mov     [rsp+320h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180041a83  xor     r8d, r8d; Reserved
0x180041a86  mov     [rsp+320h+samDesired], 2000000h; samDesired
0x180041a8e  mov     rdx, r14; lpSubKey
0x180041a91  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180041a98  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x180041a9d  call    cs:__imp_RegCreateKeyExW
0x180041aa3  test    eax, eax
0x180041aa5  jz      short loc_180041ABE
0x180041aa7  jg      short loc_180041AB0
0x180041aa9  mov     edi, eax
0x180041aab  jmp     loc_180041DC7
0x180041ab0  movzx   edi, ax
0x180041ab3  or      edi, 80070000h
0x180041ab9  jmp     loc_180041DC7
0x180041abe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180041ac2  mov     rax, rsi
0x180041ac5  inc     rax
0x180041ac8  cmp     [rbx+rax*2], r12w
0x180041acd  jnz     short loc_180041AC5
0x180041acf  mov     rcx, [rsp+320h+hKey]; hKey
0x180041ad4  lea     eax, ds:2[rax*2]
0x180041adb  mov     [rsp+320h+samDesired], eax; cbData
0x180041adf  mov     r13d, 1
0x180041ae5  mov     r9d, r13d; dwType
0x180041ae8  mov     qword ptr [rsp+320h+dwOptions], rbx; lpData
0x180041aed  xor     r8d, r8d; Reserved
0x180041af0  xor     edx, edx; lpValueName
0x180041af2  call    cs:__imp_RegSetValueExW
0x180041af8  test    eax, eax
0x180041afa  jnz     short loc_180041AA7
0x180041afc  mov     rcx, [rsp+320h+hKey]; hKey
0x180041b01  lea     rax, [rsp+320h+var_2D0]
0x180041b06  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180041b0b  lea     rdx, aClsid; "CLSID"
0x180041b12  mov     [rsp+320h+phkResult], rax; phkResult
0x180041b17  xor     r9d, r9d; lpClass
0x180041b1a  mov     [rsp+320h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180041b1f  xor     r8d, r8d; Reserved
0x180041b22  mov     [rsp+320h+samDesired], 2000000h; samDesired
0x180041b2a  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x180041b2f  call    cs:__imp_RegCreateKeyExW
0x180041b35  test    eax, eax
0x180041b37  jnz     loc_180041AA7
0x180041b3d  lea     rcx, [rbp+220h+var_298]
0x180041b41  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x180041b47  lea     rcx, [rbp+220h+var_298]
0x180041b4b  lea     ebx, [rax+2]
0x180041b4e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180041b54  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041b59  mov     r9d, r13d; dwType
0x180041b5c  xor     r8d, r8d; Reserved
0x180041b5f  mov     [rsp+320h+samDesired], ebx; cbData
0x180041b63  xor     edx, edx; lpValueName
0x180041b65  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180041b6a  call    cs:__imp_RegSetValueExW
0x180041b70  test    eax, eax
0x180041b72  jnz     loc_180041AA7
0x180041b78  lea     rax, [rbp+220h+var_2A0]
0x180041b7c  mov     r9d, 0F003Fh; samDesired
0x180041b82  xor     r8d, r8d; ulOptions
0x180041b85  mov     qword ptr [rsp+320h+dwOptions], rax; phkResult
0x180041b8a  lea     rdx, aClsid; "CLSID"
0x180041b91  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180041b98  call    cs:__imp_RegOpenKeyExW
0x180041b9e  test    eax, eax
0x180041ba0  jnz     loc_180041AA7
0x180041ba6  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041bab  call    cs:__imp_RegCloseKey
0x180041bb1  lea     rcx, [rbp+220h+var_298]
0x180041bb5  mov     [rsp+320h+var_2D0], r12
0x180041bba  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180041bc0  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180041bc5  lea     rcx, [rsp+320h+var_2D0]
0x180041bca  mov     [rsp+320h+phkResult], rcx; phkResult
0x180041bcf  mov     ebx, 2000000h
0x180041bd4  mov     rcx, [rbp+220h+var_2A0]; hKey
0x180041bd8  xor     r9d, r9d; lpClass
0x180041bdb  mov     [rsp+320h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180041be0  xor     r8d, r8d; Reserved
0x180041be3  mov     [rsp+320h+samDesired], ebx; samDesired
0x180041be7  mov     rdx, rax; lpSubKey
0x180041bea  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x180041bef  call    cs:__imp_RegCreateKeyExW
0x180041bf5  test    eax, eax
0x180041bf7  jnz     loc_180041AA7
0x180041bfd  mov     rax, rsi
0x180041c00  inc     rax
0x180041c03  cmp     [r14+rax*2], r12w
0x180041c08  jnz     short loc_180041C00
0x180041c0a  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041c0f  lea     eax, ds:2[rax*2]
0x180041c16  mov     [rsp+320h+samDesired], eax; cbData
0x180041c1a  mov     r9d, r13d; dwType
0x180041c1d  xor     r8d, r8d; Reserved
0x180041c20  mov     qword ptr [rsp+320h+dwOptions], r14; lpData
0x180041c25  xor     edx, edx; lpValueName
0x180041c27  call    cs:__imp_RegSetValueExW
0x180041c2d  test    eax, eax
0x180041c2f  jnz     loc_180041AA7
0x180041c35  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041c3a  lea     rax, [rsp+320h+var_2C8]
0x180041c3f  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180041c44  lea     rdx, aInprocserver32; "InProcServer32"
0x180041c4b  mov     [rsp+320h+phkResult], rax; phkResult
0x180041c50  xor     r9d, r9d; lpClass
0x180041c53  mov     [rsp+320h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180041c58  xor     r8d, r8d; Reserved
0x180041c5b  mov     [rsp+320h+samDesired], ebx; samDesired
0x180041c5f  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x180041c64  call    cs:__imp_RegCreateKeyExW
0x180041c6a  test    eax, eax
0x180041c6c  jnz     loc_180041AA7
0x180041c72  inc     rsi
0x180041c75  cmp     [r15+rsi*2], r12w
0x180041c7a  jnz     short loc_180041C72
0x180041c7c  mov     rcx, [rsp+320h+var_2C8]; hKey
0x180041c81  lea     eax, ds:2[rsi*2]
0x180041c88  mov     [rsp+320h+samDesired], eax; cbData
0x180041c8c  mov     r9d, r13d; dwType
0x180041c8f  xor     r8d, r8d; Reserved
0x180041c92  mov     qword ptr [rsp+320h+dwOptions], r15; lpData
0x180041c97  xor     edx, edx; lpValueName
0x180041c99  call    cs:__imp_RegSetValueExW
0x180041c9f  test    eax, eax
0x180041ca1  jnz     loc_180041AA7
0x180041ca7  mov     rcx, [rsp+320h+var_2C8]; hKey
0x180041cac  lea     rax, Data; "Both"
0x180041cb3  mov     [rsp+320h+samDesired], 0Ah; cbData
0x180041cbb  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180041cc2  mov     r9d, r13d; dwType
0x180041cc5  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180041cca  xor     r8d, r8d; Reserved
0x180041ccd  call    cs:__imp_RegSetValueExW
0x180041cd3  test    eax, eax
0x180041cd5  jnz     loc_180041AA7
0x180041cdb  movups  xmm0, xmmword ptr cs:LIBID_AppHostAdminLibrary.Data1
0x180041ce2  lea     rdx, [rsp+320h+String]; StringUuid
0x180041ce7  lea     rcx, [rbp+220h+Uuid]; Uuid
0x180041ceb  movdqu  xmmword ptr [rbp+220h+Uuid.Data1], xmm0
0x180041cf0  call    cs:__imp_UuidToStringW
0x180041cf6  test    eax, eax
0x180041cf8  jnz     loc_180041DC7
0x180041cfe  lea     rdx, asc_180062380; "{"
0x180041d05  lea     rcx, [rbp+220h+var_298]
0x180041d09  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180041d0f  mov     edi, eax
0x180041d11  test    eax, eax
0x180041d13  js      loc_180041DC7
0x180041d19  mov     rdx, [rsp+320h+String]
0x180041d1e  lea     rcx, [rbp+220h+var_298]
0x180041d22  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041d28  mov     edi, eax
0x180041d2a  test    eax, eax
0x180041d2c  js      loc_180041DC7
0x180041d32  lea     rdx, asc_180062384; "}"
0x180041d39  lea     rcx, [rbp+220h+var_298]
0x180041d3d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180041d43  mov     edi, eax
0x180041d45  test    eax, eax
0x180041d47  js      short loc_180041DC7
0x180041d49  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041d4e  lea     rax, [rsp+320h+var_2A8]
0x180041d53  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180041d58  lea     rdx, aTypelib; "TypeLib"
0x180041d5f  mov     [rsp+320h+phkResult], rax; phkResult
0x180041d64  xor     r9d, r9d; lpClass
0x180041d67  mov     [rsp+320h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180041d6c  xor     r8d, r8d; Reserved
0x180041d6f  mov     [rsp+320h+samDesired], ebx; samDesired
0x180041d73  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x180041d78  call    cs:__imp_RegCreateKeyExW
0x180041d7e  test    eax, eax
0x180041d80  jnz     loc_180041AA7
0x180041d86  lea     rcx, [rbp+220h+var_298]
0x180041d8a  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x180041d90  lea     rcx, [rbp+220h+var_298]
0x180041d94  lea     ebx, [rax+2]
0x180041d97  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180041d9d  mov     rcx, [rsp+320h+var_2A8]; hKey
0x180041da2  mov     r9d, r13d; dwType
0x180041da5  xor     r8d, r8d; Reserved
0x180041da8  mov     [rsp+320h+samDesired], ebx; cbData
0x180041dac  xor     edx, edx; lpValueName
0x180041dae  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x180041db3  call    cs:__imp_RegSetValueExW
0x180041db9  test    eax, eax
0x180041dbb  jz      short loc_180041DC7
0x180041dbd  jmp     loc_180041AA7
0x180041dc2  mov     edi, 80070057h
0x180041dc7  mov     rcx, [rsp+320h+var_2C8]; hKey
0x180041dcc  test    rcx, rcx
0x180041dcf  jz      short loc_180041DDC
0x180041dd1  call    cs:__imp_RegCloseKey
0x180041dd7  mov     [rsp+320h+var_2C8], r12
0x180041ddc  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180041de1  test    rcx, rcx
0x180041de4  jz      short loc_180041DF1
0x180041de6  call    cs:__imp_RegCloseKey
0x180041dec  mov     [rsp+320h+var_2D0], r12
0x180041df1  mov     rcx, [rsp+320h+hKey]; hKey
0x180041df6  test    rcx, rcx
0x180041df9  jz      short loc_180041E06
0x180041dfb  call    cs:__imp_RegCloseKey
0x180041e01  mov     [rsp+320h+hKey], r12
0x180041e06  mov     rcx, [rsp+320h+var_2A8]; hKey
0x180041e0b  test    rcx, rcx
0x180041e0e  jz      short loc_180041E1B
0x180041e10  call    cs:__imp_RegCloseKey
0x180041e16  mov     [rsp+320h+var_2A8], r12
0x180041e1b  cmp     [rsp+320h+StringUuid], r12
0x180041e20  jz      short loc_180041E32
0x180041e22  lea     rcx, [rsp+320h+StringUuid]; String
0x180041e27  call    cs:__imp_RpcStringFreeW
0x180041e2d  mov     [rsp+320h+StringUuid], r12
0x180041e32  cmp     [rsp+320h+String], r12
0x180041e37  jz      short loc_180041E49
0x180041e39  lea     rcx, [rsp+320h+String]; String
0x180041e3e  call    cs:__imp_RpcStringFreeW
0x180041e44  mov     [rsp+320h+String], r12
0x180041e49  lea     rcx, [rbp+220h+var_298]
0x180041e4d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180041e53  mov     eax, edi
0x180041e55  mov     rcx, [rbp+220h+var_50]
0x180041e5c  xor     rcx, rsp; StackCookie
0x180041e5f  call    __security_check_cookie
0x180041e64  add     rsp, 2E8h
0x180041e6b  pop     r15
0x180041e6d  pop     r14
0x180041e6f  pop     r13
0x180041e71  pop     r12
  ... truncated ...
```
