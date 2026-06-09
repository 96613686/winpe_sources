# _DeleteSubKeyTree

- ea: `0x180144988`
- end: `0x180144c4c`
- name: `_DeleteSubKeyTree`
- size: `708`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180143f8c`
- `0x180144988`

## callees

- `0x180119140`
- `0x1801244c0`
- `0x180144818`
- `0x180144988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144bb0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180144a11`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180144a11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144b1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801449cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801449cc`
- `WDSCORE!CurrentIP` at `0x180144a3a`
- `WDSCORE!CurrentIP` at `0x180144aa5`
- `WDSCORE!CurrentIP` at `0x180144b4a`
- `WDSCORE!CurrentIP` at `0x180144bb8`
- `WDSCORE!CurrentIP` at `0x180144a3a`
- `WDSCORE!CurrentIP` at `0x180144aa5`
- `WDSCORE!CurrentIP` at `0x180144b4a`
- `WDSCORE!CurrentIP` at `0x180144bb8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144b0a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144c1d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144b0a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144c1d`

## string_xrefs

- `0x180144a7f`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144ae4`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144b89`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144bf7`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144a51`: `MSS: _DeleteSubKeyTree call failed to delete reg key tree %ls under %ls - error 0x%X.`
- `0x180144a65`: `_DeleteSubKeyTree`
- `0x180144aca`: `_DeleteSubKeyTree`
- `0x180144b6f`: `_DeleteSubKeyTree`
- `0x180144bdd`: `_DeleteSubKeyTree`
- `0x180144b53`: `MSS: _DeleteSubKeyTree call failed to open reg key %ls - error 0x%X.`
- `0x180144aae`: `MSS: _DeleteSubKeyTree call failed to enumerate reg subkeys for %ls - error 0x%X.`
- `0x180144bc1`: `MSS: _DeleteSubKeyTree call failed to delete reg key %ls - error 0x%X.`

## pseudocode

```c
__int64 __fastcall DeleteSubKeyTree(HKEY a1, const WCHAR *a2)
{
  LSTATUS v4; // eax
  unsigned int v5; // esi
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // ecx
  bool v14; // cf
  DWORD LastError; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  HKEY hKey; // [rsp+60h] [rbp-258h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-250h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-248h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 8u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( (unsigned int)(v4 - 2) > 1 )
    {
      LastError = GetLastError();
      v16 = CurrentIP();
      v17 = ConstructPartialMsgW(
              0x2000000u,
              "MSS: _DeleteSubKeyTree call failed to open reg key %ls - error 0x%X.",
              a2,
              v5);
      WdsSetupLogMessageW(
        v17,
        983040,
        L"D",
        0,
        177,
        L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
        L"_DeleteSubKeyTree",
        v16,
        LastError,
        0,
        0);
      return v5;
    }
  }
  else
  {
    while ( !v5 )
    {
      cchName = 260;
      v5 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v5 )
      {
        if ( v5 == 259 )
        {
          v5 = 0;
          break;
        }
        v9 = GetLastError();
        v10 = CurrentIP();
        v11 = ConstructPartialMsgW(
                0x2000000u,
                "MSS: _DeleteSubKeyTree call failed to enumerate reg subkeys for %ls - error 0x%X.",
                a2,
                v5);
        WdsSetupLogMessageW(
          v11,
          983040,
          L"D",
          0,
          166,
          L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
          L"_DeleteSubKeyTree",
          v10,
          v9,
          0,
          0);
      }
      else
      {
        v5 = DeleteSubKeyTree(hKey, Name);
        if ( v5 )
        {
          v6 = GetLastError();
          v7 = CurrentIP();
          v8 = ConstructPartialMsgW(
                 0x2000000u,
                 "MSS: _DeleteSubKeyTree call failed to delete reg key tree %ls under %ls - error 0x%X.",
                 Name,
                 a2,
                 v5);
          WdsSetupLogMessageW(
            v8,
            983040,
            L"D",
            0,
            153,
            L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
            L"_DeleteSubKeyTree",
            v7,
            v6,
            0,
            0);
        }
      }
    }
    RegCloseKey(hKey);
    if ( v5 )
    {
      v12 = v5 - 2;
      v13 = v5;
      v14 = v5 == 2;
      v5 = 0;
      if ( !v14 && v12 != 1 )
        return v13;
      return v5;
    }
  }
  v5 = DeleteKey(a1, a2);
  if ( v5 )
  {
    v18 = GetLastError();
    v19 = CurrentIP();
    v20 = ConstructPartialMsgW(
            0x2000000u,
            "MSS: _DeleteSubKeyTree call failed to delete reg key %ls - error 0x%X.",
            a2,
            v5);
    WdsSetupLogMessageW(
      v20,
      983040,
      L"D",
      0,
      185,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"_DeleteSubKeyTree",
      v19,
      v18,
      0,
      0);
  }
  return v5;
}

```

## disassembly

```asm
0x180144988  mov     [rsp+arg_10], rbx
0x18014498d  push    rbp
0x18014498e  push    rsi
0x18014498f  push    rdi
0x180144990  push    r14
0x180144992  push    r15
0x180144994  sub     rsp, 290h
0x18014499b  mov     rax, cs:__security_cookie
0x1801449a2  xor     rax, rsp
0x1801449a5  mov     [rsp+2B8h+var_38], rax
0x1801449ad  xor     r15d, r15d
0x1801449b0  lea     rax, [rsp+2B8h+hKey]
0x1801449b5  xor     r8d, r8d; ulOptions
0x1801449b8  mov     [rsp+2B8h+hKey], r15
0x1801449bd  mov     rbp, rdx
0x1801449c0  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1801449c5  mov     r14, rcx
0x1801449c8  lea     r9d, [r15+8]; samDesired
0x1801449cc  call    cs:__imp_RegOpenKeyExW
0x1801449d2  mov     esi, eax
0x1801449d4  test    eax, eax
0x1801449d6  jnz     loc_180144B3A
0x1801449dc  test    esi, esi
0x1801449de  jnz     loc_180144B18
0x1801449e4  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1801449e9  lea     r9, [rsp+2B8h+cchName]; lpcchName
0x1801449ee  mov     [rsp+2B8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1801449f3  lea     r8, [rsp+2B8h+Name]; lpName
0x1801449f8  mov     [rsp+2B8h+lpcchClass], r15; lpcchClass
0x1801449fd  xor     edx, edx; dwIndex
0x1801449ff  mov     [rsp+2B8h+lpClass], r15; lpClass
0x180144a04  mov     [rsp+2B8h+phkResult], r15; lpReserved
0x180144a09  mov     [rsp+2B8h+cchName], 104h
0x180144a11  call    cs:__imp_RegEnumKeyExW
0x180144a17  mov     esi, eax
0x180144a19  test    eax, eax
0x180144a1b  jnz     short loc_180144A95
0x180144a1d  mov     rcx, [rsp+2B8h+hKey]
0x180144a22  lea     rdx, [rsp+2B8h+Name]
0x180144a27  call    _DeleteSubKeyTree
0x180144a2c  mov     esi, eax
0x180144a2e  test    eax, eax
0x180144a30  jz      short loc_1801449DC
0x180144a32  call    cs:__imp_GetLastError
0x180144a38  mov     edi, eax
0x180144a3a  call    cs:__imp_CurrentIP
0x180144a40  mov     r9, rbp
0x180144a43  mov     dword ptr [rsp+2B8h+phkResult], esi
0x180144a47  lea     r8, [rsp+2B8h+Name]
0x180144a4c  mov     ecx, 2000000h; unsigned int
0x180144a51  lea     rdx, aMssDeletesubke_1; "MSS: _DeleteSubKeyTree call failed to d"...
0x180144a58  mov     rbx, rax
0x180144a5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144a60  mov     [rsp+2B8h+var_268], r15d
0x180144a65  lea     rcx, aDeletesubkeytr; "_DeleteSubKeyTree"
0x180144a6c  mov     [rsp+2B8h+var_270], r15
0x180144a71  mov     [rsp+2B8h+var_278], edi
0x180144a75  mov     [rsp+2B8h+lpftLastWriteTime], rbx
0x180144a7a  mov     [rsp+2B8h+lpcchClass], rcx
0x180144a7f  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144a86  mov     [rsp+2B8h+lpClass], rcx
0x180144a8b  mov     dword ptr [rsp+2B8h+phkResult], 99h
0x180144a93  jmp     short loc_180144AF8
0x180144a95  cmp     esi, 103h
0x180144a9b  jz      short loc_180144B15
0x180144a9d  call    cs:__imp_GetLastError
0x180144aa3  mov     edi, eax
0x180144aa5  call    cs:__imp_CurrentIP
0x180144aab  mov     r9d, esi
0x180144aae  lea     rdx, aMssDeletesubke; "MSS: _DeleteSubKeyTree call failed to e"...
0x180144ab5  mov     r8, rbp
0x180144ab8  mov     ecx, 2000000h; unsigned int
0x180144abd  mov     rbx, rax
0x180144ac0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144ac5  mov     [rsp+2B8h+var_268], r15d
0x180144aca  lea     rcx, aDeletesubkeytr; "_DeleteSubKeyTree"
0x180144ad1  mov     [rsp+2B8h+var_270], r15
0x180144ad6  mov     [rsp+2B8h+var_278], edi
0x180144ada  mov     [rsp+2B8h+lpftLastWriteTime], rbx
0x180144adf  mov     [rsp+2B8h+lpcchClass], rcx
0x180144ae4  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144aeb  mov     [rsp+2B8h+lpClass], rcx
0x180144af0  mov     dword ptr [rsp+2B8h+phkResult], 0A6h
0x180144af8  xor     r9d, r9d
0x180144afb  lea     r8, aD_2; "D"
0x180144b02  mov     edx, 0F0000h
0x180144b07  mov     rcx, rax
0x180144b0a  call    cs:__imp_WdsSetupLogMessageW
0x180144b10  jmp     loc_1801449DC
0x180144b15  mov     esi, r15d
0x180144b18  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180144b1d  call    cs:__imp_RegCloseKey
0x180144b23  test    esi, esi
0x180144b25  jz      short loc_180144B9F
0x180144b27  lea     eax, [rsi-2]
0x180144b2a  mov     ecx, esi
0x180144b2c  cmp     eax, 1
0x180144b2f  mov     esi, r15d
0x180144b32  cmova   esi, ecx
0x180144b35  jmp     loc_180144C23
0x180144b3a  add     eax, 0FFFFFFFEh
0x180144b3d  cmp     eax, 1
0x180144b40  jbe     short loc_180144B9F
0x180144b42  call    cs:__imp_GetLastError
0x180144b48  mov     edi, eax
0x180144b4a  call    cs:__imp_CurrentIP
0x180144b50  mov     r9d, esi
0x180144b53  lea     rdx, aMssDeletesubke_0; "MSS: _DeleteSubKeyTree call failed to o"...
0x180144b5a  mov     r8, rbp
0x180144b5d  mov     ecx, 2000000h; unsigned int
0x180144b62  mov     rbx, rax
0x180144b65  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144b6a  mov     [rsp+2B8h+var_268], r15d
0x180144b6f  lea     rcx, aDeletesubkeytr; "_DeleteSubKeyTree"
0x180144b76  mov     [rsp+2B8h+var_270], r15
0x180144b7b  mov     [rsp+2B8h+var_278], edi
0x180144b7f  mov     [rsp+2B8h+lpftLastWriteTime], rbx
0x180144b84  mov     [rsp+2B8h+lpcchClass], rcx
0x180144b89  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144b90  mov     [rsp+2B8h+lpClass], rcx
0x180144b95  mov     dword ptr [rsp+2B8h+phkResult], 0B1h
0x180144b9d  jmp     short loc_180144C0B
0x180144b9f  mov     rdx, rbp
0x180144ba2  mov     rcx, r14
0x180144ba5  call    _DeleteKey
0x180144baa  mov     esi, eax
0x180144bac  test    eax, eax
0x180144bae  jz      short loc_180144C23
0x180144bb0  call    cs:__imp_GetLastError
0x180144bb6  mov     edi, eax
0x180144bb8  call    cs:__imp_CurrentIP
0x180144bbe  mov     r9d, esi
0x180144bc1  lea     rdx, aMssDeletesubke_2; "MSS: _DeleteSubKeyTree call failed to d"...
0x180144bc8  mov     r8, rbp
0x180144bcb  mov     ecx, 2000000h; unsigned int
0x180144bd0  mov     rbx, rax
0x180144bd3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144bd8  mov     [rsp+2B8h+var_268], r15d
0x180144bdd  lea     rcx, aDeletesubkeytr; "_DeleteSubKeyTree"
0x180144be4  mov     [rsp+2B8h+var_270], r15
0x180144be9  mov     [rsp+2B8h+var_278], edi
0x180144bed  mov     [rsp+2B8h+lpftLastWriteTime], rbx
0x180144bf2  mov     [rsp+2B8h+lpcchClass], rcx
0x180144bf7  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144bfe  mov     [rsp+2B8h+lpClass], rcx
0x180144c03  mov     dword ptr [rsp+2B8h+phkResult], 0B9h
0x180144c0b  xor     r9d, r9d
0x180144c0e  lea     r8, aD_2; "D"
0x180144c15  mov     edx, 0F0000h
0x180144c1a  mov     rcx, rax
0x180144c1d  call    cs:__imp_WdsSetupLogMessageW
0x180144c23  mov     eax, esi
0x180144c25  mov     rcx, [rsp+2B8h+var_38]
0x180144c2d  xor     rcx, rsp; StackCookie
0x180144c30  call    __security_check_cookie
0x180144c35  mov     rbx, [rsp+2B8h+arg_10]
0x180144c3d  add     rsp, 290h
0x180144c44  pop     r15
0x180144c46  pop     r14
0x180144c48  pop     rdi
0x180144c49  pop     rsi
0x180144c4a  pop     rbp
0x180144c4b  retn
```
