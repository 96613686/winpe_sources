# DRR_ForceDownload

- ea: `0x180005c00`
- end: `0x180006228`
- name: `DRR_ForceDownload`
- size: `1576`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002f60`

## callees

- `0x1800035cc`
- `0x1800035f4`
- `0x180003d84`
- `0x180003e70`
- `0x180004224`
- `0x1800052ac`
- `0x18000542c`
- `0x180005a30`
- `0x180005c00`
- `0x18000702c`
- `0x18000d384`
- `0x18000d89e`
- `0x18000d8d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005cfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005cfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005d3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005d3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800061a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005cb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005cb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005de4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005de4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006147`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005d82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005d82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005d00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005d00`
- `ntdll!EtwEventWrite` at `0x180005f2b`
- `ntdll!EtwEventWrite` at `0x18000613e`
- `ntdll!EtwEventWrite` at `0x180005f2b`
- `ntdll!EtwEventWrite` at `0x18000613e`

## pseudocode

```c
__int64 __fastcall DRR_ForceDownload(__int64 a1, __int64 *a2)
{
  HKEY v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _OWORD *v8; // rax
  __int64 v9; // r9
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, __int64, int *, __int64 *); // rax
  unsigned int v14; // eax
  int v15; // eax
  __int64 *v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  __int64 *v22; // rbx
  __int64 v23; // rax
  int v24; // eax
  DWORD updated; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-98h] BYREF
  BYTE v30[4]; // [rsp+6Ch] [rbp-94h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36[3]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v37[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[16]; // [rsp+B8h] [rbp-48h] BYREF
  struct _FILETIME v39; // [rsp+C8h] [rbp-38h]
  struct _FILETIME v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 v42; // [rsp+F0h] [rbp-10h]
  __int128 v43; // [rsp+F8h] [rbp-8h]
  __int128 v44; // [rsp+120h] [rbp+20h] BYREF
  DWORD *p_updated; // [rsp+130h] [rbp+30h] BYREF
  __int64 v46; // [rsp+138h] [rbp+38h]
  __int64 *v47; // [rsp+140h] [rbp+40h]
  int v48; // [rsp+148h] [rbp+48h]
  int v49; // [rsp+14Ch] [rbp+4Ch]

  v34 = 0;
  memset_0(v37, 0, 0x80u);
  SystemTimeAsFileTime = 0;
  *(_DWORD *)v30 = 0;
  v33 = 0;
  v32 = 0;
  updated = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  *(_OWORD *)v36 = 0;
  v35 = 0;
  if ( RegCreateKeyExW(::hKey, L"Software\\Microsoft\\Cryptography\\DIMS\\KeyRoaming", 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    v4 = 0;
    hKey = 0;
  }
  else
  {
    v4 = hKey;
  }
  if ( v4 )
  {
    cbData[0] = 4;
    RegQueryValueExW(v4, L"LastTick", 0, 0, Data, cbData);
  }
  *(_DWORD *)v30 = GetTickCount();
  if ( (unsigned int)(*(_DWORD *)v30 - *(_DWORD *)Data) >= 0xEA60 )
  {
    if ( hKey )
      RegSetValueExW(hKey, L"LastTick", 0, 4u, v30, 4u);
    v34 = 0;
    memset_0(v37, 0, 0x70u);
    v40 = FileTime;
    v44 = 0;
    v37[0] = 1414746699;
    updated = 0;
    v37[1] = 0x10000;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v5 = LocalAlloc(0, 0x20u);
    if ( !v5 )
      goto LABEL_69;
    v6 = LocalAlloc(0, 8u);
    *v5 = v6;
    if ( !v6
      || (*v6 = 0, v7 = LocalAlloc(0, 8u), (v5[1] = v7) == 0)
      || (*v7 = 0, v8 = LocalAlloc(0, 0x10u), (v5[2] = v8) == 0) )
    {
LABEL_69:
      updated = 14;
      goto LABEL_70;
    }
    *v8 = 0;
    (*(void (__fastcall **)(__int64 *, _QWORD *, int *))(*a2 + 56))(a2, v5, &v32);
    v9 = updated;
    if ( updated )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v11 = 27;
      goto LABEL_17;
    }
    v12 = *a2;
    v41 = 0;
    v42 = 0;
    v13 = *(__int64 (__fastcall **)(__int64 *, __int64, int *, __int64 *))(v12 + 48);
    v43 = 0;
    v14 = v13(a2, 0x3FFFFFFF, &v33, &v34);
    v9 = v14;
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v14;
    updated = v9;
    if ( (_DWORD)v9 )
    {
      if ( (unsigned int)g_dwLoglevel > 1 )
      {
        *(_QWORD *)cbData = 0;
        p_updated = &updated;
        v46 = 4;
        v15 = LogErrorCodeAndText(v9, (wchar_t **)cbData);
        v16 = *(__int64 **)cbData;
        if ( v15 && *(_QWORD *)cbData )
        {
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)(*(_QWORD *)cbData + 2 * v17) );
          v47 = *(__int64 **)cbData;
          v18 = 2 * v17 + 2;
        }
        else
        {
          v47 = &qword_18000FCA0;
          v18 = 2;
        }
        v48 = v18;
        v49 = 0;
        if ( qword_1800138C8 )
          EtwEventWrite(qword_1800138C8, DRR_LOG_ERROR_NETSTOREREAD, 2, &p_updated);
        LocalFree(v16);
        v9 = updated;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v11 = 28;
      goto LABEL_17;
    }
    updated = drr_BuildChangeSet((__int64)&v35, v34, (__int64)&v44, 1, 1, &SystemTimeAsFileTime);
    v9 = updated;
    if ( updated )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v11 = 29;
      goto LABEL_17;
    }
    if ( DWORD2(v35) )
    {
      if ( !drr_UpdateLocStoreWithRetries(a1, v36, (__int64 *)&v35) )
      {
        updated = 29;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_70;
        v20 = 30;
        goto LABEL_43;
      }
      v40 = SystemTimeAsFileTime;
    }
    updated = drr_UpdateState((__int64)v37, v36, (__int64 *)&v35, &SystemTimeAsFileTime);
    v9 = updated;
    if ( updated )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v11 = 31;
      goto LABEL_17;
    }
    v39 = SystemTimeAsFileTime;
    updated = DRR_HashState(v37, v38);
    if ( updated )
      goto LABEL_70;
    updated = DRR_WriteState();
    v9 = updated;
    if ( updated )
    {
      if ( (unsigned int)g_dwLoglevel > 1 )
      {
        *(_QWORD *)cbData = 0;
        p_updated = &updated;
        v46 = 4;
        v21 = LogErrorCodeAndText(updated, (wchar_t **)cbData);
        v22 = *(__int64 **)cbData;
        if ( v21 && *(_QWORD *)cbData )
        {
          v23 = -1;
          do
            ++v23;
          while ( *(_WORD *)(*(_QWORD *)cbData + 2 * v23) );
          v47 = *(__int64 **)cbData;
          v24 = 2 * v23 + 2;
        }
        else
        {
          v47 = &qword_18000FCA0;
          v24 = 2;
        }
        v48 = v24;
        v49 = 0;
        if ( qword_1800138C8 )
          EtwEventWrite(qword_1800138C8, DRR_LOG_ERROR_STATEFILEWRITE, 2, &p_updated);
        LocalFree(v22);
        v9 = updated;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_70;
      v11 = 32;
LABEL_17:
      WPP_SF_D(v10[2], v11, WPP_0d35500083bf3b199c9126c7ab80908a_Traceguids, v9);
LABEL_70:
      DRR_UninitRoamingTokenSet(&v44);
      goto LABEL_71;
    }
    if ( hKey )
    {
      cbData[0] = 0;
      RegSetValueExW(hKey, L"Disabled", 0, 4u, (const BYTE *)cbData, 4u);
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_70;
    v20 = 33;
LABEL_43:
    WPP_SF_(v19[2], v20, WPP_0d35500083bf3b199c9126c7ab80908a_Traceguids);
    goto LABEL_70;
  }
LABEL_71:
  if ( hKey )
    RegCloseKey(hKey);
  _drr_UninitChangeSet((struct DRR_CHANGE_SET *)&v35);
  _drr_UninitChangeSet((struct DRR_CHANGE_SET *)v36);
  return updated;
}

```

## disassembly

```asm
0x180005c00  mov     rax, rsp
0x180005c03  mov     [rax+18h], rbx
0x180005c07  push    rbp
0x180005c08  push    rsi
0x180005c09  push    rdi
0x180005c0a  push    r14
0x180005c0c  push    r15
0x180005c0e  lea     rbp, [rsp-70h]
0x180005c13  sub     rsp, 170h
0x180005c1a  movaps  xmmword ptr [rax-38h], xmm6
0x180005c1e  mov     rax, cs:__security_cookie
0x180005c25  xor     rax, rsp
0x180005c28  mov     [rbp+90h+var_40], rax
0x180005c2c  mov     rdi, rdx
0x180005c2f  mov     rsi, rcx
0x180005c32  xor     r14d, r14d
0x180005c35  lea     rcx, [rbp+90h+var_E0]; void *
0x180005c39  xor     edx, edx; Val
0x180005c3b  mov     [rbp+90h+var_110], r14
0x180005c3f  mov     r8d, 80h; Size
0x180005c45  call    memset_0
0x180005c4a  mov     rcx, cs:hKey; hKey
0x180005c51  lea     rax, [rsp+190h+hKey]
0x180005c56  mov     [rsp+190h+lpdwDisposition], r14; lpdwDisposition
0x180005c5b  lea     rdx, DRR_REG_SUBKEY; "Software\\Microsoft\\Cryptography\\DIMS"...
0x180005c62  mov     [rsp+190h+phkResult], rax; phkResult
0x180005c67  xorps   xmm0, xmm0
0x180005c6a  mov     [rsp+190h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005c6f  xorps   xmm1, xmm1
0x180005c72  mov     [rsp+190h+samDesired], 0F003Fh; samDesired
0x180005c7a  xor     r9d, r9d; lpClass
0x180005c7d  xor     r8d, r8d; Reserved
0x180005c80  mov     [rsp+190h+dwOptions], r14d; dwOptions
0x180005c85  mov     qword ptr [rsp+190h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180005c8a  mov     dword ptr [rsp+190h+var_124], r14d
0x180005c8f  mov     [rsp+190h+var_114], r14d
0x180005c94  mov     [rsp+190h+var_118], r14d
0x180005c99  mov     [rsp+190h+var_140], r14d
0x180005c9e  mov     [rsp+190h+hKey], r14
0x180005ca3  mov     dword ptr [rsp+190h+Data], r14d
0x180005ca8  movups  xmmword ptr [rbp+90h+var_F8], xmm0
0x180005cac  movups  [rbp+90h+var_108], xmm1
0x180005cb0  call    cs:__imp_RegCreateKeyExW
0x180005cb6  test    eax, eax
0x180005cb8  jz      short loc_180005CC4
0x180005cba  mov     ecx, r14d
0x180005cbd  mov     [rsp+190h+hKey], rcx
0x180005cc2  jmp     short loc_180005CC9
0x180005cc4  mov     rcx, [rsp+190h+hKey]; hKey
0x180005cc9  mov     r15d, 4
0x180005ccf  test    rcx, rcx
0x180005cd2  jz      short loc_180005D00
0x180005cd4  lea     rax, [rsp+190h+cbData]
0x180005cd9  mov     [rsp+190h+cbData], r15d
0x180005cde  mov     qword ptr [rsp+190h+samDesired], rax; lpcbData
0x180005ce3  lea     rdx, aLasttick; "LastTick"
0x180005cea  lea     rax, [rsp+190h+Data]
0x180005cef  xor     r9d, r9d; lpType
0x180005cf2  xor     r8d, r8d; lpReserved
0x180005cf5  mov     qword ptr [rsp+190h+dwOptions], rax; lpData
0x180005cfa  call    cs:__imp_RegQueryValueExW
0x180005d00  call    cs:__imp_GetTickCount
0x180005d06  mov     dword ptr [rsp+190h+var_124], eax
0x180005d0a  sub     eax, dword ptr [rsp+190h+Data]
0x180005d0e  cmp     eax, 0EA60h
0x180005d13  jb      loc_1800061DA
0x180005d19  mov     rcx, [rsp+190h+hKey]; hKey
0x180005d1e  test    rcx, rcx
0x180005d21  jz      short loc_180005D45
0x180005d23  lea     rax, [rsp+190h+var_124]
0x180005d28  mov     [rsp+190h+samDesired], r15d; cbData
0x180005d2d  mov     r9d, r15d; dwType
0x180005d30  mov     qword ptr [rsp+190h+dwOptions], rax; lpData
0x180005d35  xor     r8d, r8d; Reserved
0x180005d38  lea     rdx, aLasttick; "LastTick"
0x180005d3f  call    cs:__imp_RegSetValueExW
0x180005d45  xor     edx, edx; Val
0x180005d47  mov     [rbp+90h+var_110], r14
0x180005d4b  lea     rcx, [rbp+90h+var_E0]; void *
0x180005d4f  lea     r8d, [rdx+70h]; Size
0x180005d53  call    memset_0
0x180005d58  mov     rax, qword ptr cs:FileTime.dwLowDateTime
0x180005d5f  lea     rcx, [rsp+190h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005d64  xorps   xmm0, xmm0
0x180005d67  mov     [rbp+90h+var_C0], rax
0x180005d6b  movups  [rbp+90h+var_70], xmm0
0x180005d6f  mov     [rbp+90h+var_E0], 5453524Bh
0x180005d76  mov     [rsp+190h+var_140], r14d
0x180005d7b  mov     [rbp+90h+var_DC], 10000h
0x180005d82  call    cs:__imp_GetSystemTimeAsFileTime
0x180005d88  mov     edx, 20h ; ' '; uBytes
0x180005d8d  xor     ecx, ecx; uFlags
0x180005d8f  xorps   xmm6, xmm6
0x180005d92  call    cs:__imp_LocalAlloc
0x180005d98  mov     rbx, rax
0x180005d9b  test    rax, rax
0x180005d9e  jz      loc_1800061C9
0x180005da4  mov     edx, 8; uBytes
0x180005da9  xor     ecx, ecx; uFlags
0x180005dab  call    cs:__imp_LocalAlloc
0x180005db1  mov     [rbx], rax
0x180005db4  test    rax, rax
0x180005db7  jz      loc_1800061C9
0x180005dbd  mov     edx, 8; uBytes
0x180005dc2  mov     [rax], r14
0x180005dc5  xor     ecx, ecx; uFlags
0x180005dc7  call    cs:__imp_LocalAlloc
0x180005dcd  mov     [rbx+8], rax
0x180005dd1  test    rax, rax
0x180005dd4  jz      loc_1800061C9
0x180005dda  mov     edx, 10h; uBytes
0x180005ddf  mov     [rax], r14
0x180005de2  xor     ecx, ecx; uFlags
0x180005de4  call    cs:__imp_LocalAlloc
0x180005dea  mov     [rbx+10h], rax
0x180005dee  test    rax, rax
0x180005df1  jz      loc_1800061C9
0x180005df7  movdqu  xmmword ptr [rax], xmm6
0x180005dfb  mov     rax, [rdi]
0x180005dfe  lea     r8, [rsp+190h+var_118]
0x180005e03  mov     rdx, rbx
0x180005e06  mov     rcx, rdi
0x180005e09  mov     rax, [rax+38h]
0x180005e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e12  mov     r9d, [rsp+190h+var_140]
0x180005e17  test    r9d, r9d
0x180005e1a  jz      short loc_180005E57
0x180005e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e23  lea     rax, WPP_GLOBAL_Control
0x180005e2a  cmp     rcx, rax
0x180005e2d  jz      loc_1800061D1
0x180005e33  test    byte ptr [rcx+1Ch], 2
0x180005e37  jz      loc_1800061D1
0x180005e3d  mov     edx, 1Bh
0x180005e42  mov     rcx, [rcx+10h]
0x180005e46  lea     r8, WPP_0d35500083bf3b199c9126c7ab80908a_Traceguids
0x180005e4d  call    WPP_SF_D
0x180005e52  jmp     loc_1800061D1
0x180005e57  mov     rax, [rdi]
0x180005e5a  lea     r9, [rbp+90h+var_110]
0x180005e5e  lea     r8, [rsp+190h+var_114]
0x180005e63  mov     [rbp+90h+var_A8], r14
0x180005e67  mov     edx, 3FFFFFFFh
0x180005e6c  mov     [rbp+90h+var_A0], r14
0x180005e70  mov     rcx, rdi
0x180005e73  mov     rax, [rax+30h]
0x180005e77  movdqu  [rbp+90h+var_98], xmm6
0x180005e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e81  mov     r9d, eax
0x180005e84  and     eax, 1FFF0000h
0x180005e89  cmp     eax, 70000h
0x180005e8e  jnz     short loc_180005E94
0x180005e90  movzx   r9d, r9w
0x180005e94  mov     [rsp+190h+var_140], r9d
0x180005e99  test    r9d, r9d
0x180005e9c  jz      loc_180005F6A
0x180005ea2  cmp     cs:g_dwLoglevel, 1
0x180005ea9  jbe     loc_180005F3F
0x180005eaf  lea     rax, [rsp+190h+var_140]
0x180005eb4  mov     qword ptr [rsp+190h+cbData], r14
0x180005eb9  lea     rdx, [rsp+190h+cbData]
0x180005ebe  mov     [rbp+90h+var_60], rax
0x180005ec2  mov     ecx, r9d; dwMessageId
0x180005ec5  mov     [rbp+90h+var_58], r15
0x180005ec9  call    _LogErrorCodeAndText
0x180005ece  mov     rbx, qword ptr [rsp+190h+cbData]
0x180005ed3  test    eax, eax
0x180005ed5  jz      short loc_180005EF7
0x180005ed7  test    rbx, rbx
0x180005eda  jz      short loc_180005EF7
0x180005edc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ee0  inc     rax
0x180005ee3  cmp     [rbx+rax*2], r14w
0x180005ee8  jnz     short loc_180005EE0
0x180005eea  mov     [rbp+90h+var_50], rbx
0x180005eee  lea     eax, ds:2[rax*2]
0x180005ef5  jmp     short loc_180005F07
0x180005ef7  lea     rax, qword_18000FCA0
0x180005efe  mov     [rbp+90h+var_50], rax
0x180005f02  mov     eax, 2
0x180005f07  mov     rcx, cs:qword_1800138C8
0x180005f0e  mov     [rbp+90h+var_48], eax
0x180005f11  mov     [rbp+90h+var_44], r14d
0x180005f15  test    rcx, rcx
0x180005f18  jz      short loc_180005F31
0x180005f1a  lea     r9, [rbp+90h+var_60]
0x180005f1e  mov     r8d, 2
0x180005f24  lea     rdx, DRR_LOG_ERROR_NETSTOREREAD
0x180005f2b  call    cs:__imp_EtwEventWrite
0x180005f31  mov     rcx, rbx; hMem
0x180005f34  call    cs:__imp_LocalFree
0x180005f3a  mov     r9d, [rsp+190h+var_140]
0x180005f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f46  lea     rax, WPP_GLOBAL_Control
0x180005f4d  cmp     rcx, rax
0x180005f50  jz      loc_1800061D1
0x180005f56  test    byte ptr [rcx+1Ch], 2
0x180005f5a  jz      loc_1800061D1
0x180005f60  mov     edx, 1Ch
0x180005f65  jmp     loc_180005E42
0x180005f6a  mov     rdx, [rbp+90h+var_110]
0x180005f6e  lea     rax, [rsp+190h+SystemTimeAsFileTime]
0x180005f73  mov     qword ptr [rsp+190h+samDesired], rax
0x180005f78  lea     r8, [rbp+90h+var_70]
0x180005f7c  mov     r9d, 1
0x180005f82  mov     [rsp+190h+dwOptions], 1
0x180005f8a  lea     rcx, [rbp+90h+var_108]
0x180005f8e  call    _drr_BuildChangeSet
0x180005f93  mov     [rsp+190h+var_140], eax
0x180005f97  mov     r9d, eax
0x180005f9a  test    eax, eax
0x180005f9c  jz      short loc_180005FC9
0x180005f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fa5  lea     rax, WPP_GLOBAL_Control
0x180005fac  cmp     rcx, rax
0x180005faf  jz      loc_1800061D1
0x180005fb5  test    byte ptr [rcx+1Ch], 2
0x180005fb9  jz      loc_1800061D1
0x180005fbf  mov     edx, 1Dh
0x180005fc4  jmp     loc_180005E42
0x180005fc9  cmp     dword ptr [rbp+90h+var_108+8], r14d
0x180005fcd  jz      short loc_18000602F
0x180005fcf  lea     r8, [rbp+90h+var_108]
0x180005fd3  mov     rcx, rsi
0x180005fd6  lea     rdx, [rbp+90h+var_F8]
0x180005fda  call    _drr_UpdateLocStoreWithRetries
0x180005fdf  test    eax, eax
0x180005fe1  jnz     short loc_180006026
0x180005fe3  mov     [rsp+190h+var_140], 1Dh
0x180005feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ff2  lea     rax, WPP_GLOBAL_Control
0x180005ff9  cmp     rcx, rax
0x180005ffc  jz      loc_1800061D1
0x180006002  test    byte ptr [rcx+1Ch], 2
0x180006006  jz      loc_1800061D1
0x18000600c  mov     edx, 1Eh
0x180006011  mov     rcx, [rcx+10h]
0x180006015  lea     r8, WPP_0d35500083bf3b199c9126c7ab80908a_Traceguids
0x18000601c  call    WPP_SF_
0x180006021  jmp     loc_1800061D1
0x180006026  mov     rax, qword ptr [rsp+190h+SystemTimeAsFileTime.dwLowDateTime]
0x18000602b  mov     [rbp+90h+var_C0], rax
0x18000602f  lea     r9, [rsp+190h+SystemTimeAsFileTime]
0x180006034  lea     r8, [rbp+90h+var_108]
0x180006038  lea     rdx, [rbp+90h+var_F8]
0x18000603c  lea     rcx, [rbp+90h+var_E0]
0x180006040  call    _drr_UpdateState
0x180006045  mov     [rsp+190h+var_140], eax
0x180006049  mov     r9d, eax
0x18000604c  test    eax, eax
0x18000604e  jz      short loc_18000607B
0x180006050  mov     rcx, cs:WPP_GLOBAL_Control
0x180006057  lea     rax, WPP_GLOBAL_Control
0x18000605e  cmp     rcx, rax
0x180006061  jz      loc_1800061D1
0x180006067  test    byte ptr [rcx+1Ch], 2
0x18000606b  jz      loc_1800061D1
0x180006071  mov     edx, 1Fh
0x180006076  jmp     loc_180005E42
0x18000607b  mov     rax, qword ptr [rsp+190h+SystemTimeAsFileTime.dwLowDateTime]
0x180006080  lea     rdx, [rbp+90h+var_D8]
0x180006084  lea     rcx, [rbp+90h+var_E0]
0x180006088  mov     [rbp+90h+var_C8], rax
0x18000608c  call    DRR_HashState
0x180006091  mov     [rsp+190h+var_140], eax
0x180006095  test    eax, eax
0x180006097  jnz     loc_1800061D1
0x18000609d  lea     rcx, [rbp+90h+var_E0]
0x1800060a1  call    DRR_WriteState
0x1800060a6  mov     [rsp+190h+var_140], eax
0x1800060aa  mov     r9d, eax
0x1800060ad  test    eax, eax
0x1800060af  jz      loc_180006175
0x1800060b5  cmp     cs:g_dwLoglevel, 1
0x1800060bc  jbe     loc_180006152
0x1800060c2  lea     rax, [rsp+190h+var_140]
0x1800060c7  mov     qword ptr [rsp+190h+cbData], r14
0x1800060cc  lea     rdx, [rsp+190h+cbData]
0x1800060d1  mov     [rbp+90h+var_60], rax
0x1800060d5  mov     ecx, r9d; dwMessageId
0x1800060d8  mov     [rbp+90h+var_58], r15
0x1800060dc  call    _LogErrorCodeAndText
0x1800060e1  mov     rbx, qword ptr [rsp+190h+cbData]
0x1800060e6  test    eax, eax
0x1800060e8  jz      short loc_18000610A
0x1800060ea  test    rbx, rbx
0x1800060ed  jz      short loc_18000610A
0x1800060ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800060f3  inc     rax
0x1800060f6  cmp     [rbx+rax*2], r14w
0x1800060fb  jnz     short loc_1800060F3
0x1800060fd  mov     [rbp+90h+var_50], rbx
0x180006101  lea     eax, ds:2[rax*2]
0x180006108  jmp     short loc_18000611A
0x18000610a  lea     rax, qword_18000FCA0
0x180006111  mov     [rbp+90h+var_50], rax
0x180006115  mov     eax, 2
0x18000611a  mov     rcx, cs:qword_1800138C8
0x180006121  mov     [rbp+90h+var_48], eax
0x180006124  mov     [rbp+90h+var_44], r14d
  ... truncated ...
```
