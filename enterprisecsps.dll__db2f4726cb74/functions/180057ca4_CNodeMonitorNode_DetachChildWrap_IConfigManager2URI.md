# CNodeMonitorNode::DetachChildWrap(IConfigManager2URI *)

- ea: `0x180057ca4`
- end: `0x180058019`
- name: `?DetachChildWrap@CNodeMonitorNode@@IEAAJPEAUIConfigManager2URI@@@Z`
- size: `885`
- prototype: `__int64 __fastcall(CNodeMonitorNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057c80`

## callees

- `0x18000d4d4`
- `0x180057ca4`
- `0x18006046c`
- `0x180060554`
- `0x1800605e0`
- `0x18006102c`
- `0x18006125c`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057d98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057d98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180057ec1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180057fac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180057ec1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180057fac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180057f45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180057f45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057fd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057f6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057fd3`

## string_xrefs

- `0x180057cf3`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180057d4a`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180057ffc`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemonnode.cpp`
- `0x180057f3b`: `CacheVersion`

## pseudocode

```c
__int64 __fastcall CNodeMonitorNode::DetachChildWrap(CNodeMonitorNode *this, struct IConfigManager2URI *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 v15; // rcx
  CNodeCacheManager *v16; // rcx
  CNodeCacheManager *v17; // rcx
  CNodeCacheManager *v18; // rcx
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  HKEY v22; // rdi
  LSTATUS v23; // eax
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // rdx
  int ProviderIdKey; // eax
  HKEY v27; // rdi
  LSTATUS v28; // eax
  const unsigned __int16 *v29; // r8
  const WCHAR *v30; // rsi
  int NodeMonitorKey; // eax
  HKEY v32; // rdi
  LSTATUS v33; // eax
  int v34; // [rsp+20h] [rbp-30h]
  __int64 v35; // [rsp+30h] [rbp-20h] BYREF
  __int64 v36; // [rsp+38h] [rbp-18h]
  LPCWSTR v37; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v39; // [rsp+88h] [rbp+38h] BYREF
  LPCWSTR lpSubKey; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 830;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)v4,
      v34);
    return (unsigned int)v4;
  }
  v6 = *(_QWORD *)a2;
  v39 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(v6 + 136))(a2, &v39);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x341,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)v7,
      v34);
    return v8;
  }
  if ( v39 != 1 )
  {
    v4 = -2147024809;
    v5 = 834;
    goto LABEL_58;
  }
  v10 = *(_QWORD *)a2;
  lpSubKey = 0;
  v11 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, LPCWSTR *))(v10 + 88))(a2, 0, &lpSubKey);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x345,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemonnode.cpp",
      (const char *)(unsigned int)v11,
      v34);
    return v12;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xB )
    {
      v4 = -2046820350;
      v5 = 863;
      goto LABEL_58;
    }
    v14 = 32LL * i;
    if ( *(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14) == *(_DWORD *)(*((_QWORD *)this + 7) + 4LL) )
    {
      v15 = *(__int64 *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 16);
      if ( !v15 || !(unsigned int)_o__wcsicmp(v15, lpSubKey) )
        break;
    }
  }
  v16 = (CNodeCacheManager *)(unsigned int)(*(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) - 1);
  if ( *(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) == 1 )
  {
    v29 = (const unsigned __int16 *)*((_QWORD *)this + 5);
    v30 = lpSubKey;
    hKey = 0;
    NodeMonitorKey = CNodeCacheManager::GetNodeMonitorKey(v16, &hKey, v29);
    v32 = hKey;
    v4 = NodeMonitorKey;
    if ( NodeMonitorKey >= 0 )
    {
      v33 = RegDeleteTreeW(hKey, v30);
      if ( v33 )
      {
        if ( v33 > 0 )
          v4 = (unsigned __int16)v33 | 0x80070000;
        else
          v4 = v33;
      }
    }
    if ( v32 )
      RegCloseKey(v32);
    if ( v4 >= 0 )
      return 0;
    v5 = 870;
    goto LABEL_58;
  }
  v17 = (CNodeCacheManager *)(unsigned int)(*(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) - 2);
  if ( *(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) == 2 )
  {
    v24 = (const unsigned __int16 *)*((_QWORD *)this + 4);
    v25 = (const unsigned __int16 *)*((_QWORD *)this + 5);
    hKey = 0;
    ProviderIdKey = CNodeCacheManager::GetProviderIdKey(v17, v25, v24, &hKey, 0);
    v27 = hKey;
    v4 = ProviderIdKey;
    if ( ProviderIdKey >= 0 )
    {
      v28 = RegDeleteValueW(hKey, L"CacheVersion");
      if ( v28 )
      {
        if ( v28 > 0 )
          v4 = (unsigned __int16)v28 | 0x80070000;
        else
          v4 = v28;
      }
    }
    if ( v27 )
      RegCloseKey(v27);
    if ( v4 >= 0 )
      return 0;
    v5 = 877;
    goto LABEL_58;
  }
  if ( *(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) == 3 )
    return 2248146961LL;
  v18 = (CNodeCacheManager *)(unsigned int)(*(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) - 4);
  switch ( *(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) )
  {
    case 4:
      v19 = (const unsigned __int16 *)*((_QWORD *)this + 4);
      v20 = (const unsigned __int16 *)*((_QWORD *)this + 5);
      hKey = 0;
      v21 = CNodeCacheManager::GetProviderIdKey(v18, v20, v19, &hKey, 0);
      v22 = hKey;
      v4 = v21;
      if ( v21 >= 0 )
      {
        v23 = RegDeleteTreeW(hKey, L"Nodes");
        if ( v23 )
        {
          if ( v23 > 0 )
            v4 = (unsigned __int16)v23 | 0x80070000;
          else
            v4 = v23;
        }
      }
      if ( v22 )
        RegCloseKey(v22);
      if ( v4 < 0 )
      {
        v5 = 892;
        goto LABEL_58;
      }
      break;
    case 5:
      v35 = *((_QWORD *)this + 5);
      v36 = *((_QWORD *)this + 4);
      v37 = lpSubKey;
      v4 = CNodeCacheManager::DeleteNodeId((CNodeCacheManager *)&v35);
      if ( v4 < 0 )
      {
        v5 = 899;
        goto LABEL_58;
      }
      break;
    case 6:
      v35 = *((_QWORD *)this + 5);
      v36 = *((_QWORD *)this + 4);
      v37 = (LPCWSTR)*((_QWORD *)this + 6);
      v4 = CNodeCacheManager::DeleteNodeUri((CNodeCacheManager *)&v35);
      if ( v4 < 0 )
      {
        v5 = 906;
        goto LABEL_58;
      }
      break;
    default:
      if ( (unsigned int)(*(_DWORD *)((char *)&c_rgNODEMONITORNODEINFOTable + v14 + 4) - 7) <= 1 )
      {
        v35 = *((_QWORD *)this + 5);
        v36 = *((_QWORD *)this + 4);
        v37 = (LPCWSTR)*((_QWORD *)this + 6);
        v4 = CNodeCacheManager::DeleteExpectedValue((CNodeCacheManager *)&v35);
        if ( v4 < 0 )
        {
          v5 = 914;
          goto LABEL_58;
        }
        return 0;
      }
      return 2248146961LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180057ca4  push    rbp
0x180057ca6  push    rbx
0x180057ca7  push    rsi
0x180057ca8  push    rdi
0x180057ca9  push    r15
0x180057cab  mov     rbp, rsp
0x180057cae  sub     rsp, 50h
0x180057cb2  mov     rdi, rdx
0x180057cb5  mov     rbx, rcx
0x180057cb8  test    rdx, rdx
0x180057cbb  jnz     short loc_180057CCC
0x180057cbd  mov     ebx, 80070057h
0x180057cc2  mov     edx, 33Eh
0x180057cc7  jmp     loc_180057FF8
0x180057ccc  mov     rax, [rdx]
0x180057ccf  mov     rcx, rdi
0x180057cd2  lea     rdx, [rbp+arg_8]
0x180057cd6  mov     [rbp+arg_8], 0
0x180057cdd  mov     rax, [rax+88h]
0x180057ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ce9  mov     esi, eax
0x180057ceb  test    eax, eax
0x180057ced  jns     short loc_180057D0E
0x180057cef  mov     rcx, [rbp+28h]; this
0x180057cf3  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180057cfa  mov     r9d, eax; char *
0x180057cfd  mov     edx, 341h; void *
0x180057d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d07  mov     eax, esi
0x180057d09  jmp     loc_18005800D
0x180057d0e  cmp     [rbp+arg_8], 1
0x180057d12  jz      short loc_180057D23
0x180057d14  mov     ebx, 80070057h
0x180057d19  mov     edx, 342h
0x180057d1e  jmp     loc_180057FF8
0x180057d23  mov     rax, [rdi]
0x180057d26  lea     r8, [rbp+lpSubKey]
0x180057d2a  xor     edx, edx
0x180057d2c  mov     [rbp+lpSubKey], 0
0x180057d34  mov     rcx, rdi
0x180057d37  mov     rax, [rax+58h]
0x180057d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d40  mov     edi, eax
0x180057d42  test    eax, eax
0x180057d44  jns     short loc_180057D65
0x180057d46  mov     rcx, [rbp+28h]; this
0x180057d4a  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180057d51  mov     r9d, eax; char *
0x180057d54  mov     edx, 345h; void *
0x180057d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d5e  mov     eax, edi
0x180057d60  jmp     loc_18005800D
0x180057d65  xor     esi, esi
0x180057d67  cmp     esi, 0Bh
0x180057d6a  jnb     loc_180057FEE
0x180057d70  mov     rax, [rbx+38h]
0x180057d74  lea     r15, ?c_rgNODEMONITORNODEINFOTable@@3QBUNODEMONITORNODEINFO@@B; NODEMONITORNODEINFO const near * const c_rgNODEMONITORNODEINFOTable
0x180057d7b  mov     edi, esi
0x180057d7d  shl     rdi, 5
0x180057d81  mov     ecx, [rax+4]
0x180057d84  cmp     [rdi+r15], ecx
0x180057d88  jnz     short loc_180057DA8
0x180057d8a  mov     rcx, [rdi+r15+10h]
0x180057d8f  test    rcx, rcx
0x180057d92  jz      short loc_180057DAC
0x180057d94  mov     rdx, [rbp+lpSubKey]
0x180057d98  call    cs:__imp__o__wcsicmp
0x180057d9f  nop     dword ptr [rax+rax+00h]
0x180057da4  test    eax, eax
0x180057da6  jz      short loc_180057DAC
0x180057da8  inc     esi
0x180057daa  jmp     short loc_180057D67
0x180057dac  mov     ecx, [rdi+r15+4]
0x180057db1  sub     ecx, 1; this
0x180057db4  jz      loc_180057F83
0x180057dba  sub     ecx, 1; this
0x180057dbd  jz      loc_180057F10
0x180057dc3  sub     ecx, 1
0x180057dc6  jz      loc_180057F06
0x180057dcc  sub     ecx, 1; this
0x180057dcf  jz      loc_180057E8C
0x180057dd5  sub     ecx, 1
0x180057dd8  jz      short loc_180057E57
0x180057dda  sub     ecx, 1
0x180057ddd  jz      short loc_180057E22
0x180057ddf  sub     ecx, 1
0x180057de2  jz      short loc_180057DED
0x180057de4  cmp     ecx, 1
0x180057de7  jnz     loc_180057F06
0x180057ded  mov     rax, [rbx+28h]
0x180057df1  lea     rcx, [rbp+var_20]; this
0x180057df5  mov     [rbp+var_20], rax
0x180057df9  mov     rax, [rbx+20h]
0x180057dfd  mov     [rbp+var_18], rax
0x180057e01  mov     rax, [rbx+30h]
0x180057e05  mov     [rbp+var_10], rax
0x180057e09  call    ?DeleteExpectedValue@CNodeCacheManager@@QEAAJXZ; CNodeCacheManager::DeleteExpectedValue(void)
0x180057e0e  mov     ebx, eax
0x180057e10  test    eax, eax
0x180057e12  jns     loc_180057FEA
0x180057e18  mov     edx, 392h
0x180057e1d  jmp     loc_180057FF8
0x180057e22  mov     rax, [rbx+28h]
0x180057e26  lea     rcx, [rbp+var_20]; this
0x180057e2a  mov     [rbp+var_20], rax
0x180057e2e  mov     rax, [rbx+20h]
0x180057e32  mov     [rbp+var_18], rax
0x180057e36  mov     rax, [rbx+30h]
0x180057e3a  mov     [rbp+var_10], rax
0x180057e3e  call    ?DeleteNodeUri@CNodeCacheManager@@QEAAJXZ; CNodeCacheManager::DeleteNodeUri(void)
0x180057e43  mov     ebx, eax
0x180057e45  test    eax, eax
0x180057e47  jns     loc_180057FEA
0x180057e4d  mov     edx, 38Ah
0x180057e52  jmp     loc_180057FF8
0x180057e57  mov     rax, [rbx+28h]
0x180057e5b  lea     rcx, [rbp+var_20]; this
0x180057e5f  mov     [rbp+var_20], rax
0x180057e63  mov     rax, [rbx+20h]
0x180057e67  mov     [rbp+var_18], rax
0x180057e6b  mov     rax, [rbp+lpSubKey]
0x180057e6f  mov     [rbp+var_10], rax
0x180057e73  call    ?DeleteNodeId@CNodeCacheManager@@QEAAJXZ; CNodeCacheManager::DeleteNodeId(void)
0x180057e78  mov     ebx, eax
0x180057e7a  test    eax, eax
0x180057e7c  jns     loc_180057FEA
0x180057e82  mov     edx, 383h
0x180057e87  jmp     loc_180057FF8
0x180057e8c  mov     r8, [rbx+20h]; unsigned __int16 *
0x180057e90  lea     r9, [rbp+hKey]; HKEY *
0x180057e94  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180057e98  mov     [rbp+hKey], 0
0x180057ea0  mov     [rsp+50h+var_30], 0; int
0x180057ea8  call    ?GetProviderIdKey@CNodeCacheManager@@AEAAJPEBG0PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetProviderIdKey(ushort const *,ushort const *,HKEY__ * *,int)
0x180057ead  mov     rdi, [rbp+hKey]
0x180057eb1  mov     ebx, eax
0x180057eb3  test    eax, eax
0x180057eb5  js      short loc_180057EE0
0x180057eb7  lea     rdx, aNodes_1; "Nodes"
0x180057ebe  mov     rcx, rdi; hKey
0x180057ec1  call    cs:__imp_RegDeleteTreeW
0x180057ec8  nop     dword ptr [rax+rax+00h]
0x180057ecd  test    eax, eax
0x180057ecf  jz      short loc_180057EE0
0x180057ed1  jg      short loc_180057ED7
0x180057ed3  mov     ebx, eax
0x180057ed5  jmp     short loc_180057EE0
0x180057ed7  movzx   ebx, ax
0x180057eda  or      ebx, 80070000h
0x180057ee0  test    rdi, rdi
0x180057ee3  jz      short loc_180057EF4
0x180057ee5  mov     rcx, rdi; hKey
0x180057ee8  call    cs:__imp_RegCloseKey
0x180057eef  nop     dword ptr [rax+rax+00h]
0x180057ef4  test    ebx, ebx
0x180057ef6  jns     loc_180057FEA
0x180057efc  mov     edx, 37Ch
0x180057f01  jmp     loc_180057FF8
0x180057f06  mov     eax, 86000011h
0x180057f0b  jmp     loc_18005800D
0x180057f10  mov     r8, [rbx+20h]; unsigned __int16 *
0x180057f14  lea     r9, [rbp+hKey]; HKEY *
0x180057f18  mov     rdx, [rbx+28h]; unsigned __int16 *
0x180057f1c  mov     [rbp+hKey], 0
0x180057f24  mov     [rsp+50h+var_30], 0; int
0x180057f2c  call    ?GetProviderIdKey@CNodeCacheManager@@AEAAJPEBG0PEAPEAUHKEY__@@H@Z; CNodeCacheManager::GetProviderIdKey(ushort const *,ushort const *,HKEY__ * *,int)
0x180057f31  mov     rdi, [rbp+hKey]
0x180057f35  mov     ebx, eax
0x180057f37  test    eax, eax
0x180057f39  js      short loc_180057F64
0x180057f3b  lea     rdx, aCacheversion; "CacheVersion"
0x180057f42  mov     rcx, rdi; hKey
0x180057f45  call    cs:__imp_RegDeleteValueW
0x180057f4c  nop     dword ptr [rax+rax+00h]
0x180057f51  test    eax, eax
0x180057f53  jz      short loc_180057F64
0x180057f55  jg      short loc_180057F5B
0x180057f57  mov     ebx, eax
0x180057f59  jmp     short loc_180057F64
0x180057f5b  movzx   ebx, ax
0x180057f5e  or      ebx, 80070000h
0x180057f64  test    rdi, rdi
0x180057f67  jz      short loc_180057F78
0x180057f69  mov     rcx, rdi; hKey
0x180057f6c  call    cs:__imp_RegCloseKey
0x180057f73  nop     dword ptr [rax+rax+00h]
0x180057f78  test    ebx, ebx
0x180057f7a  jns     short loc_180057FEA
0x180057f7c  mov     edx, 36Dh
0x180057f81  jmp     short loc_180057FF8
0x180057f83  mov     r8, [rbx+28h]; unsigned __int16 *
0x180057f87  lea     rdx, [rbp+hKey]; HKEY *
0x180057f8b  mov     rsi, [rbp+lpSubKey]
0x180057f8f  mov     [rbp+hKey], 0
0x180057f97  call    ?GetNodeMonitorKey@CNodeCacheManager@@AEAAJPEAPEAUHKEY__@@PEBG@Z; CNodeCacheManager::GetNodeMonitorKey(HKEY__ * *,ushort const *)
0x180057f9c  mov     rdi, [rbp+hKey]
0x180057fa0  mov     ebx, eax
0x180057fa2  test    eax, eax
0x180057fa4  js      short loc_180057FCB
0x180057fa6  mov     rdx, rsi; lpSubKey
0x180057fa9  mov     rcx, rdi; hKey
0x180057fac  call    cs:__imp_RegDeleteTreeW
0x180057fb3  nop     dword ptr [rax+rax+00h]
0x180057fb8  test    eax, eax
0x180057fba  jz      short loc_180057FCB
0x180057fbc  jg      short loc_180057FC2
0x180057fbe  mov     ebx, eax
0x180057fc0  jmp     short loc_180057FCB
0x180057fc2  movzx   ebx, ax
0x180057fc5  or      ebx, 80070000h
0x180057fcb  test    rdi, rdi
0x180057fce  jz      short loc_180057FDF
0x180057fd0  mov     rcx, rdi; hKey
0x180057fd3  call    cs:__imp_RegCloseKey
0x180057fda  nop     dword ptr [rax+rax+00h]
0x180057fdf  test    ebx, ebx
0x180057fe1  jns     short loc_180057FEA
0x180057fe3  mov     edx, 366h
0x180057fe8  jmp     short loc_180057FF8
0x180057fea  xor     eax, eax
0x180057fec  jmp     short loc_18005800D
0x180057fee  mov     ebx, 86000002h
0x180057ff3  mov     edx, 35Fh; void *
0x180057ff8  mov     rcx, [rbp+28h]; this
0x180057ffc  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180058003  mov     r9d, ebx; char *
0x180058006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005800b  mov     eax, ebx
0x18005800d  add     rsp, 50h
0x180058011  pop     r15
0x180058013  pop     rdi
0x180058014  pop     rsi
0x180058015  pop     rbx
0x180058016  pop     rbp
0x180058017  retn
```
