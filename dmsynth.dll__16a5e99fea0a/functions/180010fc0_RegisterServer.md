# RegisterServer

- ea: `0x180010fc0`
- end: `0x180011296`
- name: `RegisterServer`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ede0`

## callees

- `0x1800014f0`
- `0x180010da0`
- `0x180010fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180011023`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180011023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011198`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011198`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001118d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001118d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001113e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001113e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800110fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800110fd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011005`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001102e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001102e`

## string_xrefs

- `0x18001103a`: `CLSID\`
- `0x18001122b`: `CLSID`
- `0x180011267`: `CLSID`
- `0x1800111c4`: `ThreadingModel`

## pseudocode

```c
HRESULT __fastcall RegisterServer(__int64 a1, const IID *a2, const BYTE *a3, const CHAR *a4, const CHAR *lpSubKey)
{
  HMODULE v5; // rdi
  HRESULT result; // eax
  __int64 v9; // r9
  const char *v10; // r10
  CHAR *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  CHAR *v14; // rcx
  __int64 v15; // rdx
  CHAR *v16; // rcx
  __int64 v17; // rax
  CHAR *v18; // rcx
  CHAR *v19; // r8
  CHAR *v20; // rdx
  const BYTE *v21; // rax
  __int64 v22; // rcx
  LPOLESTR lpsz; // [rsp+50h] [rbp-368h] BYREF
  CHAR v24[40]; // [rsp+58h] [rbp-360h] BYREF
  CHAR SubKey[256]; // [rsp+80h] [rbp-338h] BYREF
  CHAR Filename[512]; // [rsp+180h] [rbp-238h] BYREF

  v5 = g_hModule;
  lpsz = 0;
  result = StringFromCLSID(a2, &lpsz);
  if ( result >= 0 )
  {
    _o_wcstombs(v24, lpsz, 39);
    CoTaskMemFree(lpsz);
    v9 = 2147483646;
    v10 = "CLSID\\";
    v11 = SubKey;
    v12 = 2147483646;
    v13 = 256;
    do
    {
      if ( !v12 )
        break;
      if ( !*v10 )
        break;
      *v11++ = *v10++;
      --v12;
      --v13;
    }
    while ( v13 );
    v14 = v11 - 1;
    if ( v13 )
      v14 = v11;
    v15 = 256;
    *v14 = 0;
    v16 = SubKey;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    if ( v15 )
    {
      v17 = v15;
      v18 = v24;
      v19 = &SubKey[256 - v15];
      do
      {
        if ( !v9 )
          break;
        if ( !*v18 )
          break;
        *v19++ = *v18++;
        --v9;
        --v17;
      }
      while ( v17 );
      v20 = v19 - 1;
      if ( v17 )
        v20 = v19;
      *v20 = 0;
    }
    GetModuleFileNameA(v5, Filename, 0x200u);
    lpsz = 0;
    if ( !RegCreateKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0xF003Fu, 0, (PHKEY)&lpsz, 0) && a3 )
    {
      v21 = a3;
      v22 = 0x7FFFFFFF;
      do
      {
        if ( !*v21 )
          break;
        ++v21;
        --v22;
      }
      while ( v22 );
      if ( v22 )
      {
        RegSetValueExA((HKEY)lpsz, 0, 0, 1u, a3, 0x7FFFFFFF - v22 + 1);
        RegCloseKey((HKEY)lpsz);
      }
    }
    RegSetDefValue(SubKey);
    RegSetDefValue(SubKey);
    RegSetDefValue(SubKey);
    RegSetDefValue(SubKey);
    RegSetDefValue(a4);
    RegSetDefValue(a4);
    RegSetDefValue(a4);
    RegSetDefValue(lpSubKey);
    RegSetDefValue(lpSubKey);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010fc0  push    rbx
0x180010fc2  push    rbp
0x180010fc3  push    rsi
0x180010fc4  push    rdi
0x180010fc5  push    r14
0x180010fc7  sub     rsp, 390h
0x180010fce  mov     rax, cs:__security_cookie
0x180010fd5  xor     rax, rsp
0x180010fd8  mov     [rsp+3B8h+var_38], rax
0x180010fe0  mov     rbp, [rsp+3B8h+lpSubKey]
0x180010fe8  mov     rcx, rdx; rclsid
0x180010feb  mov     rdi, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x180010ff2  lea     rdx, [rsp+3B8h+lpsz]; lplpsz
0x180010ff7  xor     r14d, r14d
0x180010ffa  mov     rsi, r9
0x180010ffd  mov     [rsp+3B8h+lpsz], r14
0x180011002  mov     rbx, r8
0x180011005  call    cs:__imp_StringFromCLSID
0x18001100b  test    eax, eax
0x18001100d  js      loc_180011278
0x180011013  mov     rdx, [rsp+3B8h+lpsz]
0x180011018  lea     rcx, [rsp+3B8h+var_360]
0x18001101d  mov     r8d, 27h ; '''
0x180011023  call    cs:__imp__o_wcstombs
0x180011029  mov     rcx, [rsp+3B8h+lpsz]; pv
0x18001102e  call    cs:__imp_CoTaskMemFree
0x180011034  mov     r9d, 7FFFFFFEh
0x18001103a  lea     r10, aClsid; "CLSID\\"
0x180011041  mov     eax, 100h
0x180011046  lea     rdx, [rsp+3B8h+SubKey]
0x18001104e  mov     ecx, r9d
0x180011051  mov     r8d, eax
0x180011054  test    rcx, rcx
0x180011057  jz      short loc_180011074
0x180011059  movzx   r11d, byte ptr [r10]
0x18001105d  test    r11b, r11b
0x180011060  jz      short loc_180011074
0x180011062  mov     [rdx], r11b
0x180011065  inc     r10
0x180011068  inc     rdx
0x18001106b  dec     rcx
0x18001106e  sub     r8, 1
0x180011072  jnz     short loc_180011054
0x180011074  lea     rcx, [rdx-1]
0x180011078  test    r8, r8
0x18001107b  cmovnz  rcx, rdx
0x18001107f  mov     rdx, rax
0x180011082  mov     [rcx], r14b
0x180011085  lea     rcx, [rsp+3B8h+SubKey]
0x18001108d  nop     dword ptr [rax]
0x180011090  cmp     [rcx], r14b
0x180011093  jz      short loc_18001109E
0x180011095  inc     rcx
0x180011098  sub     rdx, 1
0x18001109c  jnz     short loc_180011090
0x18001109e  mov     r8, rax
0x1800110a1  sub     r8, rdx
0x1800110a4  test    rdx, rdx
0x1800110a7  cmovz   r8, r14
0x1800110ab  jz      short loc_1800110EC
0x1800110ad  sub     rax, r8
0x1800110b0  lea     rcx, [rsp+3B8h+var_360]
0x1800110b5  lea     r8, [rsp+r8+3B8h+SubKey]
0x1800110bd  jz      short loc_1800110DE
0x1800110bf  nop
0x1800110c0  test    r9, r9
0x1800110c3  jz      short loc_1800110DE
0x1800110c5  movzx   edx, byte ptr [rcx]
0x1800110c8  test    dl, dl
0x1800110ca  jz      short loc_1800110DE
0x1800110cc  mov     [r8], dl
0x1800110cf  inc     rcx
0x1800110d2  inc     r8
0x1800110d5  dec     r9
0x1800110d8  sub     rax, 1
0x1800110dc  jnz     short loc_1800110C0
0x1800110de  test    rax, rax
0x1800110e1  lea     rdx, [r8-1]
0x1800110e5  cmovnz  rdx, r8
0x1800110e9  mov     [rdx], r14b
0x1800110ec  mov     r8d, 200h; nSize
0x1800110f2  lea     rdx, [rsp+3B8h+Filename]; lpFilename
0x1800110fa  mov     rcx, rdi; hModule
0x1800110fd  call    cs:__imp_GetModuleFileNameA
0x180011103  mov     [rsp+3B8h+lpdwDisposition], r14; lpdwDisposition
0x180011108  lea     rax, [rsp+3B8h+lpsz]
0x18001110d  mov     [rsp+3B8h+phkResult], rax; phkResult
0x180011112  lea     rdx, [rsp+3B8h+SubKey]; lpSubKey
0x18001111a  mov     [rsp+3B8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001111f  xor     r9d, r9d; lpClass
0x180011122  mov     [rsp+3B8h+samDesired], 0F003Fh; samDesired
0x18001112a  xor     r8d, r8d; Reserved
0x18001112d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180011134  mov     [rsp+3B8h+dwOptions], r14d; dwOptions
0x180011139  mov     [rsp+3B8h+lpsz], r14
0x18001113e  call    cs:__imp_RegCreateKeyExA
0x180011144  test    eax, eax
0x180011146  jnz     short loc_18001119E
0x180011148  test    rbx, rbx
0x18001114b  jz      short loc_18001119E
0x18001114d  mov     edx, 7FFFFFFFh
0x180011152  mov     rax, rbx
0x180011155  mov     ecx, edx
0x180011157  cmp     [rax], r14b
0x18001115a  jz      short loc_180011165
0x18001115c  inc     rax
0x18001115f  sub     rcx, 1
0x180011163  jnz     short loc_180011157
0x180011165  sub     rdx, rcx
0x180011168  test    rcx, rcx
0x18001116b  cmovz   rdx, r14
0x18001116f  jz      short loc_18001119E
0x180011171  mov     rcx, [rsp+3B8h+lpsz]; hKey
0x180011176  lea     eax, [rdx+1]
0x180011179  mov     [rsp+3B8h+samDesired], eax; cbData
0x18001117d  mov     r9d, 1; dwType
0x180011183  xor     r8d, r8d; Reserved
0x180011186  mov     qword ptr [rsp+3B8h+dwOptions], rbx; lpData
0x18001118b  xor     edx, edx; lpValueName
0x18001118d  call    cs:__imp_RegSetValueExA
0x180011193  mov     rcx, [rsp+3B8h+lpsz]; hKey
0x180011198  call    cs:__imp_RegCloseKey
0x18001119e  lea     r9, [rsp+3B8h+Filename]
0x1800111a6  xor     r8d, r8d
0x1800111a9  lea     rdx, aInprocserver32; "InProcServer32"
0x1800111b0  lea     rcx, [rsp+3B8h+SubKey]; lpSubKey
0x1800111b8  call    RegSetDefValue
0x1800111bd  lea     r9, aBoth; "Both"
0x1800111c4  lea     r8, aThreadingmodel; "ThreadingModel"
0x1800111cb  lea     rdx, aInprocserver32; "InProcServer32"
0x1800111d2  lea     rcx, [rsp+3B8h+SubKey]; lpSubKey
0x1800111da  call    RegSetDefValue
0x1800111df  mov     r9, rbp
0x1800111e2  lea     rdx, aProgid; "ProgID"
0x1800111e9  xor     r8d, r8d
0x1800111ec  lea     rcx, [rsp+3B8h+SubKey]; lpSubKey
0x1800111f4  call    RegSetDefValue
0x1800111f9  mov     r9, rsi
0x1800111fc  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x180011203  xor     r8d, r8d
0x180011206  lea     rcx, [rsp+3B8h+SubKey]; lpSubKey
0x18001120e  call    RegSetDefValue
0x180011213  mov     r9, rbx
0x180011216  xor     r8d, r8d
0x180011219  xor     edx, edx
0x18001121b  mov     rcx, rsi; lpSubKey
0x18001121e  call    RegSetDefValue
0x180011223  lea     r9, [rsp+3B8h+var_360]
0x180011228  xor     r8d, r8d
0x18001122b  lea     rdx, aClsid_0; "CLSID"
0x180011232  mov     rcx, rsi; lpSubKey
0x180011235  call    RegSetDefValue
0x18001123a  mov     r9, rbp
0x18001123d  lea     rdx, aCurver; "CurVer"
0x180011244  xor     r8d, r8d
0x180011247  mov     rcx, rsi; lpSubKey
0x18001124a  call    RegSetDefValue
0x18001124f  mov     r9, rbx
0x180011252  xor     r8d, r8d
0x180011255  xor     edx, edx
0x180011257  mov     rcx, rbp; lpSubKey
0x18001125a  call    RegSetDefValue
0x18001125f  lea     r9, [rsp+3B8h+var_360]
0x180011264  xor     r8d, r8d
0x180011267  lea     rdx, aClsid_0; "CLSID"
0x18001126e  mov     rcx, rbp; lpSubKey
0x180011271  call    RegSetDefValue
0x180011276  xor     eax, eax
0x180011278  mov     rcx, [rsp+3B8h+var_38]
0x180011280  xor     rcx, rsp; StackCookie
0x180011283  call    __security_check_cookie
0x180011288  add     rsp, 390h
0x18001128f  pop     r14
0x180011291  pop     rdi
0x180011292  pop     rsi
0x180011293  pop     rbp
0x180011294  pop     rbx
0x180011295  retn
```
