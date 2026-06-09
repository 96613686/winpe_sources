# LoadDeviceProviders(_REG_FAX_SERVICE *)

- ea: `0x140003d5c`
- end: `0x1400046d3`
- name: `?LoadDeviceProviders@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `2423`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x1400472a0`

## callees

- `0x140002c43`
- `0x1400034bc`
- `0x140003d5c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140065d14`
- `0x140065df8`
- `0x140066334`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400045c5`
- `KERNEL32!FreeLibrary` at `0x1400045c5`
- `KERNEL32!GetLastError` at `0x140003e58`
- `KERNEL32!GetLastError` at `0x140004256`
- `KERNEL32!GetLastError` at `0x1400043a5`
- `KERNEL32!GetLastError` at `0x140004481`
- `KERNEL32!GetLastError` at `0x14000460c`
- `KERNEL32!GetLastError` at `0x140003e58`
- `KERNEL32!GetLastError` at `0x140004256`
- `KERNEL32!GetLastError` at `0x1400043a5`
- `KERNEL32!GetLastError` at `0x140004481`
- `KERNEL32!GetLastError` at `0x14000460c`
- `KERNEL32!LoadLibraryW` at `0x140004242`
- `KERNEL32!LoadLibraryW` at `0x140004242`
- `KERNEL32!GetProcessHeap` at `0x14000445a`
- `KERNEL32!GetProcessHeap` at `0x14000445a`
- `KERNEL32!HeapCreate` at `0x14000446f`
- `KERNEL32!HeapCreate` at `0x14000446f`
- `KERNEL32!HeapDestroy` at `0x1400045e3`
- `KERNEL32!HeapDestroy` at `0x1400045e3`
- `msvcrt!_wcsicmp` at `0x14000414a`
- `msvcrt!_wcsicmp` at `0x140004162`
- `msvcrt!_wcsicmp` at `0x14000414a`
- `msvcrt!_wcsicmp` at `0x140004162`
- `msvcrt!_wsplitpath_s` at `0x1400040ec`
- `msvcrt!_wsplitpath_s` at `0x1400040ec`

## pseudocode

```c
__int64 __fastcall LoadDeviceProviders(struct _REG_FAX_SERVICE *a1)
{
  unsigned int v2; // r15d
  CMapDeviceId *v3; // rbx
  unsigned int v4; // r13d
  void *v5; // rax
  __int64 v6; // rbx
  char LastError; // al
  __int64 v8; // rsi
  HMODULE v9; // r12
  _WORD *v10; // r8
  __int64 v11; // rdx
  const WCHAR *v12; // rcx
  __int64 v13; // rax
  _WORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  _WORD *v17; // r8
  const WCHAR *v18; // rax
  __int64 v19; // rcx
  _WORD *v20; // rcx
  _WORD *v21; // r8
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  __int64 v24; // rcx
  _WORD *v25; // rcx
  _WORD *v26; // r8
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  __int64 v29; // rcx
  _WORD *v30; // rcx
  CMapDeviceId *v31; // rcx
  __int64 v32; // r9
  HMODULE LibraryW; // rax
  DWORD v34; // edi
  int FileVersion; // eax
  CMapDeviceId *v36; // rcx
  __int64 v37; // r9
  HANDLE ProcessHeap; // rax
  __int64 *v39; // rax
  void *v40; // rcx
  DWORD v41; // eax
  __int64 *v42; // rax
  unsigned __int16 v44[14]; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t String1[256]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Ext[256]; // [rsp+270h] [rbp+170h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_200271385d87382553faba38592a1280_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = 0;
  if ( *((_DWORD *)a1 + 2) )
  {
    while ( 1 )
    {
      memset_0(String1, 0, sizeof(String1));
      memset_0(Ext, 0, sizeof(Ext));
      if ( v3 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 && *((_BYTE *)v3 + 25) >= 5u )
        WPP_SF_d(*((_QWORD *)v3 + 2), 12, &WPP_200271385d87382553faba38592a1280_Traceguids, v4);
      v5 = (void *)pMemAlloc(0x8D0u);
      v6 = (__int64)v5;
      if ( v5 )
        break;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
          *(_QWORD *)(*(_QWORD *)a1 + 40LL * v4 + 8),
          LastError);
      }
      v8 = 40LL * v4;
      FaxLog(1, 1, 2, 3221257523LL);
      v2 = 0;
LABEL_118:
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_123;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_200271385d87382553faba38592a1280_Traceguids,
        *(_QWORD *)(*(_QWORD *)a1 + v8));
LABEL_122:
      v3 = WPP_GLOBAL_Control;
LABEL_123:
      if ( ++v4 >= *((_DWORD *)a1 + 2) )
        return v2;
    }
    v9 = 0;
    memset_0(v5, 0, 0x8D0u);
    v10 = (_WORD *)(v6 + 64);
    v11 = 260;
    v8 = 40LL * v4;
    v12 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1) )
      v12 = *(const WCHAR **)(v8 + *(_QWORD *)a1);
    v13 = 2147483646;
    do
    {
      if ( !v13 )
        break;
      if ( !*v12 )
        break;
      *v10++ = *v12++;
      --v13;
      --v11;
    }
    while ( v11 );
    v14 = v10 - 1;
    v15 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v14 = v10;
    *v14 = 0;
    if ( !v11 )
      goto LABEL_101;
    v16 = 260;
    v17 = (_WORD *)(v6 + 584);
    v18 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 8) )
      v18 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 8);
    v19 = 2147483646;
    do
    {
      if ( !v19 )
        break;
      if ( !*v18 )
        break;
      *v17++ = *v18++;
      --v19;
      --v16;
    }
    while ( v16 );
    v20 = v17 - 1;
    v15 = v16 == 0 ? 0x8007007A : 0;
    if ( v16 )
      v20 = v17;
    *v20 = 0;
    if ( !v16 )
      goto LABEL_101;
    v21 = (_WORD *)(v6 + 1104);
    v22 = 260;
    v23 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 16) )
      v23 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 16);
    v24 = 2147483646;
    do
    {
      if ( !v24 )
        break;
      if ( !*v23 )
        break;
      *v21++ = *v23++;
      --v24;
      --v22;
    }
    while ( v22 );
    v25 = v21 - 1;
    v15 = v22 == 0 ? 0x8007007A : 0;
    if ( v22 )
      v25 = v21;
    *v25 = 0;
    if ( !v22 )
      goto LABEL_101;
    v26 = (_WORD *)(v6 + 1624);
    v27 = 260;
    v28 = &Class;
    if ( *(_QWORD *)(v8 + *(_QWORD *)a1 + 32) )
      v28 = *(const WCHAR **)(v8 + *(_QWORD *)a1 + 32);
    v29 = 2147483646;
    do
    {
      if ( !v29 )
        break;
      if ( !*v28 )
        break;
      *v26++ = *v28++;
      --v29;
      --v27;
    }
    while ( v27 );
    v30 = v26 - 1;
    v15 = v27 == 0 ? 0x8007007A : 0;
    if ( v27 )
      v30 = v26;
    *v30 = 0;
    if ( !v27 )
    {
LABEL_101:
      v31 = WPP_GLOBAL_Control;
LABEL_102:
      if ( v31 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 4) != 0 && *((_BYTE *)v31 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v31 + 2), 15, &WPP_200271385d87382553faba38592a1280_Traceguids, v15);
      FaxLog(1, 1, 2, 3221257523LL);
      goto LABEL_107;
    }
    if ( _wsplitpath_s((const wchar_t *)(v6 + 584), 0, 0, 0, 0, String1, 0x100u, Ext, 0x100u) )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_200271385d87382553faba38592a1280_Traceguids);
        v31 = WPP_GLOBAL_Control;
      }
      v15 = 2147500037LL;
      goto LABEL_102;
    }
    if ( !_wcsicmp(String1, L"FXST30") && !_wcsicmp(Ext, L".DLL") )
      *(_DWORD *)(v6 + 2248) = 1;
    v32 = *(unsigned int *)(v8 + *(_QWORD *)a1 + 24);
    *(_DWORD *)(v6 + 2144) = v32;
    if ( (_DWORD)v32 != 0x10000 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_200271385d87382553faba38592a1280_Traceguids, v32);
      }
LABEL_66:
      v44[0] = 0;
      StringCchPrintfW(v44, 0xCu, L"0x%08X");
      FaxLog(1, 1, 3, 3221257531LL);
      *(_DWORD *)(v6 + 16) = 3;
      *(_DWORD *)(v6 + 20) = 31;
LABEL_107:
      v2 = 0;
      if ( *(_QWORD *)(v6 + 56) )
      {
        FreeLibrary(v9);
        *(_QWORD *)(v6 + 56) = 0;
      }
      v40 = *(void **)(v6 + 2152);
      if ( v40 && !*(_DWORD *)(v6 + 2248) )
      {
        if ( !HeapDestroy(v40)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_200271385d87382553faba38592a1280_Traceguids, v41);
        }
        *(_QWORD *)(v6 + 2152) = 0;
      }
      v42 = (__int64 *)qword_1400A1358;
      *(_QWORD *)v6 = &g_DeviceProvidersListHead;
      *(_QWORD *)(v6 + 8) = v42;
      *v42 = v6;
      qword_1400A1358 = v6;
      goto LABEL_118;
    }
    LibraryW = LoadLibraryW((LPCWSTR)(v6 + 584));
    v9 = LibraryW;
    if ( !LibraryW )
    {
      v34 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
          *(_QWORD *)(v8 + *(_QWORD *)a1 + 8),
          v34);
      }
      v44[0] = 0;
      StringCchPrintfW(v44, 0xCu, L"%ld", v34);
      FaxLog(1, 1, 3, 3221257522LL);
      *(_DWORD *)(v6 + 16) = 4;
      goto LABEL_73;
    }
    *(_QWORD *)(v6 + 56) = LibraryW;
    *(_DWORD *)(v6 + 24) = 20;
    FileVersion = GetFileVersion(*(LPCWSTR *)(v8 + *(_QWORD *)a1 + 8));
    if ( FileVersion )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_80;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_200271385d87382553faba38592a1280_Traceguids,
        *(_QWORD *)(v8 + *(_QWORD *)a1 + 8),
        FileVersion);
    }
    v36 = WPP_GLOBAL_Control;
LABEL_80:
    v37 = *(unsigned int *)(v6 + 2144);
    if ( (_DWORD)v37 != 0x10000 )
    {
      if ( v36 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 4) != 0 && *((_BYTE *)v36 + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)v36 + 2), 21, &WPP_200271385d87382553faba38592a1280_Traceguids, v37);
      goto LABEL_66;
    }
    if ( (unsigned int)GetLegacyProviderEntryPoints(v9) )
    {
      if ( *(_DWORD *)(v6 + 2248) )
        ProcessHeap = GetProcessHeap();
      else
        ProcessHeap = HeapCreate(0, 0x19000u, 0x200000u);
      *(_QWORD *)(v6 + 2152) = ProcessHeap;
      if ( ProcessHeap )
      {
        v39 = (__int64 *)qword_1400A1358;
        *(_QWORD *)v6 = &g_DeviceProvidersListHead;
        *(_QWORD *)(v6 + 8) = v39;
        *v39 = v6;
        qword_1400A1358 = v6;
        *(_QWORD *)(v6 + 16) = 0;
        goto LABEL_122;
      }
      v34 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_200271385d87382553faba38592a1280_Traceguids, v34);
      }
      FaxLog(1, 1, 2, 3221257523LL);
      *(_DWORD *)(v6 + 16) = 1;
    }
    else
    {
      v34 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_200271385d87382553faba38592a1280_Traceguids, v34);
      }
      v44[0] = 0;
      StringCchPrintfW(v44, 0xCu, L"%ld", v34);
      FaxLog(1, 1, 3, 3221257529LL);
      *(_DWORD *)(v6 + 16) = 5;
    }
LABEL_73:
    *(_DWORD *)(v6 + 20) = v34;
    goto LABEL_107;
  }
  return v2;
}

```

## disassembly

```asm
0x140003d5c  push    rbp
0x140003d5e  push    rbx
0x140003d5f  push    rsi
0x140003d60  push    rdi
0x140003d61  push    r12
0x140003d63  push    r13
0x140003d65  push    r14
0x140003d67  push    r15
0x140003d69  lea     rbp, [rsp-388h]
0x140003d71  sub     rsp, 488h
0x140003d78  mov     rax, cs:__security_cookie
0x140003d7f  xor     rax, rsp
0x140003d82  mov     [rbp+3C0h+var_50], rax
0x140003d89  mov     r14, rcx
0x140003d8c  mov     r15d, 1
0x140003d92  mov     rbx, cs:WPP_GLOBAL_Control
0x140003d99  lea     rsi, WPP_GLOBAL_Control
0x140003da0  cmp     rbx, rsi
0x140003da3  jz      short loc_140003DCC
0x140003da5  test    byte ptr [rbx+1Ch], 4
0x140003da9  jz      short loc_140003DCC
0x140003dab  cmp     byte ptr [rbx+19h], 5
0x140003daf  jb      short loc_140003DCC
0x140003db1  mov     rcx, [rbx+10h]
0x140003db5  lea     edx, [r15+0Ah]
0x140003db9  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003dc0  call    WPP_SF_
0x140003dc5  mov     rbx, cs:WPP_GLOBAL_Control
0x140003dcc  xor     edi, edi
0x140003dce  mov     r13d, edi
0x140003dd1  cmp     [r14+8], edi
0x140003dd5  jbe     loc_1400046AD
0x140003ddb  xor     edx, edx; Val
0x140003ddd  lea     rcx, [rsp+4C0h+String1]; void *
0x140003de2  mov     r8d, 200h; Size
0x140003de8  call    memset_0
0x140003ded  xor     edx, edx; Val
0x140003def  lea     rcx, [rbp+3C0h+var_250]; void *
0x140003df6  mov     r8d, 200h; Size
0x140003dfc  call    memset_0
0x140003e01  cmp     rbx, rsi
0x140003e04  jz      short loc_140003E2A
0x140003e06  test    byte ptr [rbx+1Ch], 4
0x140003e0a  jz      short loc_140003E2A
0x140003e0c  cmp     byte ptr [rbx+19h], 5
0x140003e10  jb      short loc_140003E2A
0x140003e12  mov     rcx, [rbx+10h]
0x140003e16  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003e1d  mov     edx, 0Ch
0x140003e22  mov     r9d, r13d
0x140003e25  call    WPP_SF_d
0x140003e2a  mov     ecx, 8D0h; dwBytes
0x140003e2f  call    pMemAlloc
0x140003e34  mov     rbx, rax
0x140003e37  test    rax, rax
0x140003e3a  jnz     loc_140003ED2
0x140003e40  mov     rax, cs:WPP_GLOBAL_Control
0x140003e47  cmp     rax, rsi
0x140003e4a  jz      short loc_140003E8F
0x140003e4c  test    byte ptr [rax+1Ch], 4
0x140003e50  jz      short loc_140003E8F
0x140003e52  cmp     byte ptr [rax+19h], 2
0x140003e56  jb      short loc_140003E8F
0x140003e58  call    cs:__imp_GetLastError
0x140003e5e  mov     r9, [r14]
0x140003e61  lea     edx, [rbx+0Dh]
0x140003e64  mov     r8d, eax
0x140003e67  mov     eax, r13d
0x140003e6a  mov     dword ptr [rsp+4C0h+DirCount], r8d
0x140003e6f  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140003e76  lea     rcx, [rax+rax*4]
0x140003e7a  mov     r9, [r9+rcx*8+8]
0x140003e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e86  mov     rcx, [rcx+10h]
0x140003e8a  call    WPP_SF_Sd
0x140003e8f  mov     edx, 1
0x140003e94  mov     eax, r13d
0x140003e97  mov     r9d, 0C0007D33h
0x140003e9d  lea     rcx, [rax+rax*4]
0x140003ea1  lea     rsi, ds:0[rcx*8]
0x140003ea9  mov     rcx, [r14]
0x140003eac  lea     r8d, [rdx+1]
0x140003eb0  mov     rax, [rcx+rsi+8]
0x140003eb5  mov     [rsp+4C0h+Filename], rax
0x140003eba  mov     rax, [rcx+rsi]
0x140003ebe  mov     ecx, edx
0x140003ec0  mov     [rsp+4C0h+DirCount], rax
0x140003ec5  call    FaxLog
0x140003eca  mov     r15d, edi
0x140003ecd  jmp     loc_140004657
0x140003ed2  xor     edx, edx; Val
0x140003ed4  mov     r8d, 8D0h; Size
0x140003eda  mov     rcx, rbx; void *
0x140003edd  mov     r12, rdi
0x140003ee0  call    memset_0
0x140003ee5  mov     eax, r13d
0x140003ee8  lea     r8, [rbx+40h]
0x140003eec  mov     r10d, 7FFFFFFEh
0x140003ef2  mov     edx, 104h
0x140003ef7  lea     rcx, [rax+rax*4]
0x140003efb  mov     rax, [r14]
0x140003efe  lea     rsi, ds:0[rcx*8]
0x140003f06  lea     rcx, Class
0x140003f0d  cmp     [rsi+rax], rdi
0x140003f11  cmovnz  rcx, [rsi+rax]
0x140003f16  mov     eax, r10d
0x140003f19  test    rax, rax
0x140003f1c  jz      short loc_140003F3D
0x140003f1e  movzx   r9d, word ptr [rcx]
0x140003f22  test    r9w, r9w
0x140003f26  jz      short loc_140003F3D
0x140003f28  mov     [r8], r9w
0x140003f2c  add     rcx, 2
0x140003f30  add     r8, 2
0x140003f34  dec     rax
0x140003f37  sub     rdx, 1
0x140003f3b  jnz     short loc_140003F19
0x140003f3d  mov     rax, rdx
0x140003f40  lea     rcx, [r8-2]
0x140003f44  neg     rax
0x140003f47  mov     r11d, 8007007Ah
0x140003f4d  sbb     r9d, r9d
0x140003f50  not     r9d
0x140003f53  and     r9d, r11d
0x140003f56  test    rdx, rdx
0x140003f59  cmovnz  rcx, r8
0x140003f5d  mov     [rcx], di
0x140003f60  jz      loc_140004559
0x140003f66  mov     rax, [r14]
0x140003f69  lea     rdi, [rbx+248h]
0x140003f70  mov     edx, 104h
0x140003f75  mov     r8, rdi
0x140003f78  mov     rcx, [rsi+rax+8]
0x140003f7d  lea     rax, Class
0x140003f84  test    rcx, rcx
0x140003f87  cmovnz  rax, rcx
0x140003f8b  mov     rcx, r10
0x140003f8e  xor     r10d, r10d
0x140003f91  test    rcx, rcx
0x140003f94  jz      short loc_140003FB5
0x140003f96  movzx   r9d, word ptr [rax]
0x140003f9a  test    r9w, r9w
0x140003f9e  jz      short loc_140003FB5
0x140003fa0  mov     [r8], r9w
0x140003fa4  add     rax, 2
0x140003fa8  add     r8, 2
0x140003fac  dec     rcx
0x140003faf  sub     rdx, 1
0x140003fb3  jnz     short loc_140003F91
0x140003fb5  mov     rax, rdx
0x140003fb8  lea     rcx, [r8-2]
0x140003fbc  neg     rax
0x140003fbf  sbb     r9d, r9d
0x140003fc2  not     r9d
0x140003fc5  and     r9d, r11d
0x140003fc8  test    rdx, rdx
0x140003fcb  cmovnz  rcx, r8
0x140003fcf  mov     [rcx], r10w
0x140003fd3  jz      loc_140004557
0x140003fd9  mov     rax, [r14]
0x140003fdc  lea     r8, [rbx+450h]
0x140003fe3  mov     edx, 104h
0x140003fe8  mov     rcx, [rsi+rax+10h]
0x140003fed  lea     rax, Class
0x140003ff4  test    rcx, rcx
0x140003ff7  cmovnz  rax, rcx
0x140003ffb  mov     ecx, 7FFFFFFEh
0x140004000  test    rcx, rcx
0x140004003  jz      short loc_140004024
0x140004005  movzx   r9d, word ptr [rax]
0x140004009  test    r9w, r9w
0x14000400d  jz      short loc_140004024
0x14000400f  mov     [r8], r9w
0x140004013  add     rax, 2
0x140004017  add     r8, 2
0x14000401b  dec     rcx
0x14000401e  sub     rdx, 1
0x140004022  jnz     short loc_140004000
0x140004024  mov     rax, rdx
0x140004027  lea     rcx, [r8-2]
0x14000402b  neg     rax
0x14000402e  sbb     r9d, r9d
0x140004031  not     r9d
0x140004034  and     r9d, r11d
0x140004037  test    rdx, rdx
0x14000403a  cmovnz  rcx, r8
0x14000403e  mov     [rcx], r10w
0x140004042  jz      loc_140004557
0x140004048  mov     rax, [r14]
0x14000404b  lea     r8, [rbx+658h]
0x140004052  mov     edx, 104h
0x140004057  mov     rcx, [rsi+rax+20h]
0x14000405c  lea     rax, Class
0x140004063  test    rcx, rcx
0x140004066  cmovnz  rax, rcx
0x14000406a  mov     ecx, 7FFFFFFEh
0x14000406f  test    rcx, rcx
0x140004072  jz      short loc_140004093
0x140004074  movzx   r9d, word ptr [rax]
0x140004078  test    r9w, r9w
0x14000407c  jz      short loc_140004093
0x14000407e  mov     [r8], r9w
0x140004082  add     rax, 2
0x140004086  add     r8, 2
0x14000408a  dec     rcx
0x14000408d  sub     rdx, 1
0x140004091  jnz     short loc_14000406F
0x140004093  mov     rax, rdx
0x140004096  lea     rcx, [r8-2]
0x14000409a  neg     rax
0x14000409d  sbb     r9d, r9d
0x1400040a0  not     r9d
0x1400040a3  and     r9d, r11d
0x1400040a6  test    rdx, rdx
0x1400040a9  cmovnz  rcx, r8
0x1400040ad  mov     [rcx], r10w
0x1400040b1  jz      loc_140004557
0x1400040b7  mov     ecx, 100h
0x1400040bc  lea     rax, [rbp+3C0h+var_250]
0x1400040c3  mov     [rsp+4C0h+ExtCount], rcx; ExtCount
0x1400040c8  xor     r9d, r9d; Dir
0x1400040cb  mov     [rsp+4C0h+Ext], rax; Ext
0x1400040d0  xor     r8d, r8d; DriveCount
0x1400040d3  mov     [rsp+4C0h+FilenameCount], rcx; FilenameCount
0x1400040d8  lea     rax, [rsp+4C0h+String1]
0x1400040dd  mov     [rsp+4C0h+Filename], rax; Filename
0x1400040e2  xor     edx, edx; Drive
0x1400040e4  mov     rcx, rdi; FullPath
0x1400040e7  mov     [rsp+4C0h+DirCount], r10; DirCount
0x1400040ec  call    cs:__imp__wsplitpath_s
0x1400040f2  test    eax, eax
0x1400040f4  jz      short loc_14000413E
0x1400040f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040fd  lea     rdx, WPP_GLOBAL_Control
0x140004104  cmp     rcx, rdx
0x140004107  jz      short loc_140004131
0x140004109  test    byte ptr [rcx+1Ch], 4
0x14000410d  jz      short loc_140004131
0x14000410f  cmp     byte ptr [rcx+19h], 2
0x140004113  jb      short loc_140004131
0x140004115  mov     rcx, [rcx+10h]
0x140004119  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x140004120  mov     edx, 0Eh
0x140004125  call    WPP_SF_
0x14000412a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004131  xor     edi, edi
0x140004133  mov     r9d, 80004005h
0x140004139  jmp     loc_140004560
0x14000413e  lea     rdx, aFxst30; "FXST30"
0x140004145  lea     rcx, [rsp+4C0h+String1]; String1
0x14000414a  call    cs:__imp__wcsicmp
0x140004150  test    eax, eax
0x140004152  jnz     short loc_140004176
0x140004154  lea     rdx, aDll; ".DLL"
0x14000415b  lea     rcx, [rbp+3C0h+var_250]; String1
0x140004162  call    cs:__imp__wcsicmp
0x140004168  test    eax, eax
0x14000416a  jnz     short loc_140004176
0x14000416c  mov     dword ptr [rbx+8C8h], 1
0x140004176  mov     rax, [r14]
0x140004179  mov     r9d, [rsi+rax+18h]
0x14000417e  mov     [rbx+860h], r9d
0x140004185  cmp     r9d, 10000h
0x14000418c  jz      loc_14000423F
0x140004192  mov     rcx, cs:WPP_GLOBAL_Control
0x140004199  lea     rax, WPP_GLOBAL_Control
0x1400041a0  cmp     rcx, rax
0x1400041a3  jz      short loc_1400041C6
0x1400041a5  test    byte ptr [rcx+1Ch], 4
0x1400041a9  jz      short loc_1400041C6
0x1400041ab  cmp     byte ptr [rcx+19h], 2
0x1400041af  jb      short loc_1400041C6
0x1400041b1  mov     rcx, [rcx+10h]
0x1400041b5  lea     r8, WPP_200271385d87382553faba38592a1280_Traceguids
0x1400041bc  mov     edx, 10h
0x1400041c1  call    WPP_SF_d
0x1400041c6  xor     edi, edi
0x1400041c8  mov     r9d, [rbx+860h]
0x1400041cf  lea     r8, a0x08x; "0x%08X"
0x1400041d6  mov     edx, 0Ch; unsigned __int64
0x1400041db  mov     [rsp+4C0h+var_470], r9d
0x1400041e0  lea     rcx, [rsp+4C0h+var_46C]; unsigned __int16 *
0x1400041e5  mov     [rsp+4C0h+var_46C], di
0x1400041ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400041ef  mov     rcx, [r14]
0x1400041f2  lea     rdx, [rsp+4C0h+var_46C]
0x1400041f7  test    eax, eax
0x1400041f9  mov     r15d, 3
0x1400041ff  mov     r9d, 0C0007D3Bh
0x140004205  mov     r8d, r15d
0x140004208  cmovs   rdx, rdi
0x14000420c  mov     rax, [rsi+rcx+8]
0x140004211  mov     [rsp+4C0h+FilenameCount], rdx
0x140004216  lea     edx, [r15-2]
0x14000421a  mov     [rsp+4C0h+Filename], rax
0x14000421f  mov     rax, [rsi+rcx]
0x140004223  mov     ecx, edx
0x140004225  mov     [rsp+4C0h+DirCount], rax
0x14000422a  call    FaxLog
0x14000422f  mov     [rbx+10h], r15d
  ... truncated ...
```
