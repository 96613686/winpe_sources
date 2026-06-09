# RasEapGetMethodProperties

- ea: `0x18000f300`
- end: `0x18000f852`
- name: `RasEapGetMethodProperties`
- size: `1362`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180003bd0`
- `0x180004690`
- `0x180006a20`
- `0x18000f300`
- `0x180017bc4`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000f41c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000f41c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f7f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f457`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f4e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f563`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f457`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f4e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f82c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f82c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f528`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f78a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f528`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f536`

## string_xrefs

- `0x18000f40e`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\26`

## pseudocode

```c
__int64 __fastcall RasEapGetMethodProperties(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  int v9; // r15d
  _QWORD *v11; // rcx
  __int64 v12; // rsi
  DWORD v13; // edi
  __int64 v14; // rdx
  DWORD LastError; // eax
  LSTATUS v16; // eax
  __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // ebx
  unsigned int v21; // r14d
  HKEY v22; // rcx
  unsigned int v23; // eax
  BYTE *v24; // r12
  __int64 v25; // rax
  HLOCAL v26; // rax
  __int64 v27; // r13
  __int64 v28; // r8
  __int64 v29; // rdx
  unsigned __int8 v30; // cf
  __int64 v31; // rcx
  __int64 v32; // r9
  int v33; // ecx
  __int64 v34; // rdx
  __int64 v35; // r8
  bool v36; // zf
  bool v37; // zf
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  __int64 v42; // rbx
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 i; // rbx
  __int64 v46; // rax
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-24h] BYREF
  __int64 v50; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+58h] BYREF

  v9 = 0;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  DebuggingInit(1);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v12 = a9;
  if ( a3 != 26 )
  {
    v13 = 87;
    if ( v11 != &WPP_GLOBAL_Control )
      WPP_SF_d(v11[2], 195, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, a3);
    goto LABEL_81;
  }
  if ( !a9 )
  {
    v13 = 87;
    if ( v11 == &WPP_GLOBAL_Control )
      goto LABEL_81;
    v14 = 196;
    goto LABEL_9;
  }
  if ( a5 && !a6 )
  {
    v13 = 87;
    if ( v11 == &WPP_GLOBAL_Control )
      goto LABEL_81;
    v14 = 197;
    goto LABEL_9;
  }
  if ( a7 && !a8 )
  {
    v13 = 87;
    if ( v11 == &WPP_GLOBAL_Control )
      goto LABEL_81;
    v14 = 198;
LABEL_9:
    WPP_SF_(v11[2], v14, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    goto LABEL_81;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\26",
                0,
                0x20019u,
                &hKey);
  v13 = LastError;
  if ( LastError )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_81;
    v19 = 205;
    goto LABEL_79;
  }
  cbData = 4;
  v16 = RegQueryValueExA(hKey, "Properties", 0, &Type, Data, &cbData);
  if ( v16 )
  {
    if ( v16 == 2 )
    {
      v20 = 0;
      v21 = 0;
      goto LABEL_28;
    }
    LastError = GetLastError();
    v13 = LastError;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_81;
    v19 = 200;
LABEL_79:
    v17 = LastError;
    goto LABEL_80;
  }
  if ( Type != 4 )
  {
    v17 = 1629;
    v13 = 1629;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_81;
    v19 = 199;
    goto LABEL_80;
  }
  v20 = *(_DWORD *)Data;
  v21 = 30;
LABEL_28:
  v22 = hKey;
  *(_OWORD *)v12 = 0;
  v23 = RegQueryValueExA(v22, "ExtendedProperties", 0, &Type, 0, &cbData);
  v13 = v23;
  if ( v23 )
  {
    v24 = 0;
    if ( v23 != 2 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_81;
      v19 = 204;
      goto LABEL_37;
    }
    goto LABEL_43;
  }
  if ( Type != 3 )
  {
    v17 = 1629;
    v13 = 1629;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_81;
    v19 = 201;
    goto LABEL_80;
  }
  v24 = (BYTE *)LocalAlloc(0x40u, cbData);
  if ( !v24 )
  {
LABEL_33:
    v13 = GetLastError();
    goto LABEL_81;
  }
  v23 = RegQueryValueExA(hKey, "ExtendedProperties", 0, &Type, v24, &cbData);
  v13 = v23;
  if ( v23 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_81;
    v19 = 202;
LABEL_37:
    v17 = v23;
LABEL_80:
    WPP_SF_d(v18[2], v19, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v17);
    goto LABEL_81;
  }
  LODWORD(v50) = v21;
  if ( (unsigned int)ValidateExtendedMethodProperties(&v50, v24, cbData) == 1 )
  {
    v9 = v50;
LABEL_43:
    v25 = v9 + v21;
    v13 = 0;
    *(_DWORD *)v12 = v25;
    if ( !(_DWORD)v25 )
      goto LABEL_81;
    v26 = LocalAlloc(0x40u, 24 * v25);
    *(_QWORD *)(v12 + 8) = v26;
    if ( !v26 )
      goto LABEL_33;
    v27 = 0;
    if ( v21 )
    {
      v28 = 0;
      do
      {
        v29 = 3 * v28;
        v30 = _bittest(&v20, v28);
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v29) = v28;
        v28 = (unsigned int)(v28 + 1);
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v29 + 4) = 0;
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v29 + 8) = 4;
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v29 + 12) = v30;
      }
      while ( (unsigned int)v28 < v21 - 1 );
      v31 = 3 * v28;
      *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v31) = 31;
      *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v31 + 4) = 1;
      *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v31 + 8) = 4;
      *(_DWORD *)(*(_QWORD *)(v12 + 8) + 8 * v31 + 12) = v20;
    }
    while ( 1 )
    {
      if ( v21 >= *(_DWORD *)v12 )
        goto LABEL_81;
      *(_DWORD *)(*(_QWORD *)(v12 + 8) + 24LL * v21) = *(_DWORD *)&v24[v27];
      v32 = *(_QWORD *)(v12 + 8);
      v33 = *(_DWORD *)(v32 + 24LL * v21);
      if ( v33 > 255 )
        goto LABEL_81;
      v34 = (unsigned int)(v27 + 4);
      v50 = v34;
      v35 = (unsigned int)(v27 + 8);
      v27 = v35;
      if ( v33 != 255 )
        break;
      *(_DWORD *)(v32 + 24LL * v21 + 4) = 2;
      v42 = *(_QWORD *)(v12 + 8);
      *(_QWORD *)(v42 + 24LL * v21 + 16) = LocalAlloc(0x40u, *(unsigned int *)&v24[v34]);
      v43 = *(_QWORD *)(v12 + 8);
      if ( !*(_QWORD *)(v43 + 24LL * v21 + 16) )
        goto LABEL_33;
      v44 = v50;
      *(_DWORD *)(v43 + 24LL * v21 + 8) = *(_DWORD *)&v24[v50];
      memcpy_0(*(void **)(*(_QWORD *)(v12 + 8) + 24LL * v21 + 16), &v24[v27], *(unsigned int *)&v24[v44]);
LABEL_76:
      ++v21;
    }
    if ( v33 > 14 )
    {
      if ( v33 > 22 )
      {
        v38 = v33 - 23;
        v37 = v38 == 0;
        goto LABEL_67;
      }
      if ( v33 == 22 )
        goto LABEL_72;
      v33 -= 15;
      v36 = v33 == 0;
    }
    else
    {
      if ( v33 == 14 )
        goto LABEL_72;
      if ( v33 > 7 )
      {
        v38 = v33 - 8;
        v37 = v38 == 0;
        goto LABEL_67;
      }
      if ( v33 == 7 )
      {
LABEL_72:
        *(_DWORD *)(v32 + 24LL * v21 + 4) = 0;
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 24LL * v21 + 8) = *(_DWORD *)&v24[v34];
        if ( *(_DWORD *)&v24[v35] > 1u )
          goto LABEL_81;
        v27 = (unsigned int)(v35 + 4);
        *(_DWORD *)(*(_QWORD *)(v12 + 8) + 24LL * v21 + 12) = *(_DWORD *)&v24[v35] != 0;
        goto LABEL_76;
      }
      v36 = v33 == 0;
    }
    if ( !v36 )
    {
      v38 = v33 - 1;
      v37 = v38 == 0;
LABEL_67:
      if ( !v37 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            v41 = v40 - 1;
            if ( v41 )
            {
              if ( (unsigned int)(v41 - 1) > 1 )
                goto LABEL_81;
            }
          }
        }
      }
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  v13 = 13;
LABEL_81:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)v12; i = (unsigned int)(i + 1) )
    {
      v46 = *(_QWORD *)(v12 + 8);
      if ( *(_DWORD *)(v46 + 24 * i + 4) == 2 )
        LocalFree(*(HLOCAL *)(v46 + 24 * i + 16));
    }
    LocalFree(*(HLOCAL *)(v12 + 8));
    *(_OWORD *)v12 = 0;
  }
  DebuggingInit(0);
  return v13;
}

```

## disassembly

```asm
0x18000f300  push    rbp
0x18000f302  push    rbx
0x18000f303  push    rsi
0x18000f304  push    rdi
0x18000f305  push    r12
0x18000f307  push    r13
0x18000f309  push    r14
0x18000f30b  push    r15
0x18000f30d  mov     rbp, rsp
0x18000f310  sub     rsp, 58h
0x18000f314  xor     r15d, r15d
0x18000f317  mov     ebx, r8d
0x18000f31a  mov     [rbp+hKey], r15
0x18000f31e  mov     [rbp+Type], r15d
0x18000f322  mov     dword ptr [rbp+Data], r15d
0x18000f326  lea     ecx, [r15+1]
0x18000f32a  mov     [rbp+cbData], r15d
0x18000f32e  call    DebuggingInit
0x18000f333  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f33a  lea     r13, WPP_GLOBAL_Control
0x18000f341  lea     r12, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000f348  cmp     rcx, r13
0x18000f34b  jz      short loc_18000F365
0x18000f34d  mov     rcx, [rcx+10h]
0x18000f351  mov     edx, 0C2h
0x18000f356  mov     r8, r12
0x18000f359  call    WPP_SF_
0x18000f35e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f365  mov     rsi, [rbp+arg_40]
0x18000f36c  cmp     ebx, 1Ah
0x18000f36f  jz      short loc_18000F396
0x18000f371  mov     edi, 57h ; 'W'
0x18000f376  cmp     rcx, r13
0x18000f379  jz      loc_18000F7EF
0x18000f37f  mov     rcx, [rcx+10h]
0x18000f383  lea     edx, [rdi+6Ch]
0x18000f386  mov     r9d, ebx
0x18000f389  mov     r8, r12
0x18000f38c  call    WPP_SF_d
0x18000f391  jmp     loc_18000F7EF
0x18000f396  test    rsi, rsi
0x18000f399  jnz     short loc_18000F3BB
0x18000f39b  lea     edi, [rsi+57h]
0x18000f39e  cmp     rcx, r13
0x18000f3a1  jz      loc_18000F7EF
0x18000f3a7  lea     edx, [rdi+6Dh]
0x18000f3aa  mov     rcx, [rcx+10h]
0x18000f3ae  mov     r8, r12
0x18000f3b1  call    WPP_SF_
0x18000f3b6  jmp     loc_18000F7EF
0x18000f3bb  cmp     [rbp+arg_20], r15d
0x18000f3bf  jz      short loc_18000F3DA
0x18000f3c1  cmp     [rbp+arg_28], r15
0x18000f3c5  jnz     short loc_18000F3DA
0x18000f3c7  mov     edi, 57h ; 'W'
0x18000f3cc  cmp     rcx, r13
0x18000f3cf  jz      loc_18000F7EF
0x18000f3d5  lea     edx, [rdi+6Eh]
0x18000f3d8  jmp     short loc_18000F3AA
0x18000f3da  cmp     [rbp+arg_30], r15d
0x18000f3de  jz      short loc_18000F3FC
0x18000f3e0  cmp     [rbp+arg_38], r15
0x18000f3e7  jnz     short loc_18000F3FC
0x18000f3e9  mov     edi, 57h ; 'W'
0x18000f3ee  cmp     rcx, r13
0x18000f3f1  jz      loc_18000F7EF
0x18000f3f7  lea     edx, [rdi+6Fh]
0x18000f3fa  jmp     short loc_18000F3AA
0x18000f3fc  lea     rax, [rbp+hKey]
0x18000f400  mov     r9d, 20019h; samDesired
0x18000f406  xor     r8d, r8d; ulOptions
0x18000f409  mov     [rsp+58h+phkResult], rax; phkResult
0x18000f40e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x18000f415  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f41c  call    cs:__imp_RegOpenKeyExA
0x18000f422  mov     edi, eax
0x18000f424  test    eax, eax
0x18000f426  jnz     loc_18000F7CF
0x18000f42c  mov     rcx, [rbp+hKey]; hKey
0x18000f430  lea     rax, [rbp+cbData]
0x18000f434  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000f439  lea     r9, [rbp+Type]; lpType
0x18000f43d  lea     rax, [rbp+Data]
0x18000f441  mov     [rbp+cbData], 4
0x18000f448  xor     r8d, r8d; lpReserved
0x18000f44b  mov     [rsp+58h+phkResult], rax; lpData
0x18000f450  lea     rdx, aProperties; "Properties"
0x18000f457  call    cs:__imp_RegQueryValueExA
0x18000f45d  test    eax, eax
0x18000f45f  jnz     short loc_18000F495
0x18000f461  cmp     [rbp+Type], 4
0x18000f465  jz      short loc_18000F48A
0x18000f467  mov     r9d, 65Dh
0x18000f46d  mov     edi, r9d
0x18000f470  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f477  cmp     rcx, r13
0x18000f47a  jz      loc_18000F7EF
0x18000f480  mov     edx, 0C7h
0x18000f485  jmp     loc_18000F7E3
0x18000f48a  mov     ebx, dword ptr [rbp+Data]
0x18000f48d  mov     r14d, 1Eh
0x18000f493  jmp     short loc_18000F4C1
0x18000f495  cmp     eax, 2
0x18000f498  jz      short loc_18000F4BC
0x18000f49a  call    cs:__imp_GetLastError
0x18000f4a0  mov     edi, eax
0x18000f4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a9  cmp     rcx, r13
0x18000f4ac  jz      loc_18000F7EF
0x18000f4b2  mov     edx, 0C8h
0x18000f4b7  jmp     loc_18000F7E0
0x18000f4bc  xor     ebx, ebx
0x18000f4be  xor     r14d, r14d
0x18000f4c1  mov     rcx, [rbp+hKey]; hKey
0x18000f4c5  lea     rax, [rbp+cbData]
0x18000f4c9  xorps   xmm0, xmm0
0x18000f4cc  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000f4d1  lea     r9, [rbp+Type]; lpType
0x18000f4d5  mov     [rsp+58h+phkResult], r15; lpData
0x18000f4da  xor     r8d, r8d; lpReserved
0x18000f4dd  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18000f4e4  movups  xmmword ptr [rsi], xmm0
0x18000f4e7  call    cs:__imp_RegQueryValueExA
0x18000f4ed  mov     edi, eax
0x18000f4ef  test    eax, eax
0x18000f4f1  jnz     loc_18000F6E6
0x18000f4f7  cmp     [rbp+Type], 3
0x18000f4fb  jz      short loc_18000F520
0x18000f4fd  mov     r9d, 65Dh
0x18000f503  mov     edi, r9d
0x18000f506  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f50d  cmp     rcx, r13
0x18000f510  jz      loc_18000F7EF
0x18000f516  mov     edx, 0C9h
0x18000f51b  jmp     loc_18000F7E3
0x18000f520  mov     edx, [rbp+cbData]; uBytes
0x18000f523  mov     ecx, 40h ; '@'; uFlags
0x18000f528  call    cs:__imp_LocalAlloc
0x18000f52e  mov     r12, rax
0x18000f531  test    rax, rax
0x18000f534  jnz     short loc_18000F543
0x18000f536  call    cs:__imp_GetLastError
0x18000f53c  mov     edi, eax
0x18000f53e  jmp     loc_18000F7EF
0x18000f543  mov     rcx, [rbp+hKey]; hKey
0x18000f547  lea     rax, [rbp+cbData]
0x18000f54b  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000f550  lea     r9, [rbp+Type]; lpType
0x18000f554  xor     r8d, r8d; lpReserved
0x18000f557  mov     [rsp+58h+phkResult], r12; lpData
0x18000f55c  lea     rdx, aExtendedproper; "ExtendedProperties"
0x18000f563  call    cs:__imp_RegQueryValueExA
0x18000f569  mov     edi, eax
0x18000f56b  test    eax, eax
0x18000f56d  jz      short loc_18000F593
0x18000f56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f576  cmp     rcx, r13
0x18000f579  jz      loc_18000F7EF
0x18000f57f  mov     edx, 0CAh
0x18000f584  mov     r9d, eax
0x18000f587  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000f58e  jmp     loc_18000F7E6
0x18000f593  mov     r8d, [rbp+cbData]
0x18000f597  lea     rcx, [rbp+var_20]
0x18000f59b  mov     rdx, r12
0x18000f59e  mov     dword ptr [rbp+var_20], r14d
0x18000f5a2  call    ValidateExtendedMethodProperties
0x18000f5a7  cmp     eax, 1
0x18000f5aa  jz      short loc_18000F5D7
0x18000f5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5b3  cmp     rcx, r13
0x18000f5b6  jz      short loc_18000F5CD
0x18000f5b8  mov     rcx, [rcx+10h]
0x18000f5bc  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000f5c3  mov     edx, 0CBh
0x18000f5c8  call    WPP_SF_
0x18000f5cd  mov     edi, 0Dh
0x18000f5d2  jmp     loc_18000F7EF
0x18000f5d7  mov     r15d, dword ptr [rbp+var_20]
0x18000f5db  lea     eax, [r15+r14]
0x18000f5df  xor     edi, edi
0x18000f5e1  mov     [rsi], eax
0x18000f5e3  test    eax, eax
0x18000f5e5  jz      loc_18000F7EF
0x18000f5eb  lea     rdx, [rax+rax*2]
0x18000f5ef  shl     rdx, 3; uBytes
0x18000f5f3  lea     ecx, [rdi+40h]; uFlags
0x18000f5f6  call    cs:__imp_LocalAlloc
0x18000f5fc  mov     [rsi+8], rax
0x18000f600  test    rax, rax
0x18000f603  jz      loc_18000F536
0x18000f609  xor     r13d, r13d
0x18000f60c  test    r14d, r14d
0x18000f60f  jz      short loc_18000F680
0x18000f611  xor     r8d, r8d
0x18000f614  lea     r9d, [r14-1]
0x18000f618  mov     rax, [rsi+8]
0x18000f61c  lea     rdx, [r8+r8*2]
0x18000f620  xor     ecx, ecx
0x18000f622  bt      ebx, r8d
0x18000f626  mov     [rax+rdx*8], r8d
0x18000f62a  setb    cl
0x18000f62d  mov     rax, [rsi+8]
0x18000f631  inc     r8d
0x18000f634  mov     [rax+rdx*8+4], edi
0x18000f638  mov     rax, [rsi+8]
0x18000f63c  mov     dword ptr [rax+rdx*8+8], 4
0x18000f644  mov     rax, [rsi+8]
0x18000f648  mov     [rax+rdx*8+0Ch], ecx
0x18000f64c  cmp     r8d, r9d
0x18000f64f  jb      short loc_18000F618
0x18000f651  mov     rax, [rsi+8]
0x18000f655  lea     rcx, [r8+r8*2]
0x18000f659  mov     dword ptr [rax+rcx*8], 1Fh
0x18000f660  mov     rax, [rsi+8]
0x18000f664  mov     dword ptr [rax+rcx*8+4], 1
0x18000f66c  mov     rax, [rsi+8]
0x18000f670  mov     dword ptr [rax+rcx*8+8], 4
0x18000f678  mov     rax, [rsi+8]
0x18000f67c  mov     [rax+rcx*8+0Ch], ebx
0x18000f680  cmp     r14d, [rsi]
0x18000f683  jnb     loc_18000F7EF
0x18000f689  mov     rcx, [rsi+8]
0x18000f68d  mov     eax, r14d
0x18000f690  lea     r15, [rax+rax*2]
0x18000f694  mov     eax, [r13+r12+0]
0x18000f699  mov     [rcx+r15*8], eax
0x18000f69d  mov     r9, [rsi+8]
0x18000f6a1  mov     ecx, [r9+r15*8]
0x18000f6a5  cmp     ecx, 0FFh
0x18000f6ab  jg      loc_18000F7EF
0x18000f6b1  add     r13d, 4
0x18000f6b5  mov     edx, r13d
0x18000f6b8  mov     [rbp+var_20], rdx
0x18000f6bc  lea     r8d, [r13+4]
0x18000f6c0  mov     r13d, r8d
0x18000f6c3  cmp     ecx, 0FFh
0x18000f6c9  jz      loc_18000F774
0x18000f6cf  cmp     ecx, 0Eh
0x18000f6d2  jg      short loc_18000F711
0x18000f6d4  jz      short loc_18000F73F
0x18000f6d6  cmp     ecx, 7
0x18000f6d9  jg      short loc_18000F70C
0x18000f6db  jz      short loc_18000F73F
0x18000f6dd  test    ecx, ecx
0x18000f6df  jz      short loc_18000F73F
0x18000f6e1  sub     ecx, 1
0x18000f6e4  jmp     short loc_18000F720
0x18000f6e6  xor     r12d, r12d
0x18000f6e9  cmp     eax, 2
0x18000f6ec  jz      loc_18000F5DB
0x18000f6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6f9  cmp     rcx, r13
0x18000f6fc  jz      loc_18000F7EF
0x18000f702  mov     edx, 0CCh
0x18000f707  jmp     loc_18000F584
0x18000f70c  sub     ecx, 8
0x18000f70f  jmp     short loc_18000F720
0x18000f711  cmp     ecx, 16h
0x18000f714  jg      short loc_18000F71D
0x18000f716  jz      short loc_18000F73F
0x18000f718  sub     ecx, 0Fh
0x18000f71b  jmp     short loc_18000F6DF
0x18000f71d  sub     ecx, 17h
0x18000f720  jz      short loc_18000F73F
0x18000f722  sub     ecx, 1
0x18000f725  jz      short loc_18000F73F
0x18000f727  sub     ecx, 1
0x18000f72a  jz      short loc_18000F73F
0x18000f72c  sub     ecx, 1
0x18000f72f  jz      short loc_18000F73F
0x18000f731  sub     ecx, 1
0x18000f734  jz      short loc_18000F73F
0x18000f736  cmp     ecx, 1
0x18000f739  jnz     loc_18000F7EF
0x18000f73f  mov     [r9+r15*8+4], edi
0x18000f744  mov     rcx, [rsi+8]
0x18000f748  mov     eax, [rdx+r12]
0x18000f74c  mov     [rcx+r15*8+8], eax
0x18000f751  cmp     dword ptr [r8+r12], 1
0x18000f756  ja      loc_18000F7EF
0x18000f75c  mov     rax, [rsi+8]
0x18000f760  xor     ecx, ecx
0x18000f762  add     r13d, 4
0x18000f766  cmp     [r8+r12], ecx
0x18000f76a  setnz   cl
0x18000f76d  mov     [rax+r15*8+0Ch], ecx
0x18000f772  jmp     short loc_18000F7C7
0x18000f774  mov     dword ptr [r9+r15*8+4], 2
0x18000f77d  mov     ecx, 40h ; '@'; uFlags
0x18000f782  mov     edx, [rdx+r12]; uBytes
0x18000f786  mov     rbx, [rsi+8]
0x18000f78a  call    cs:__imp_LocalAlloc
0x18000f790  mov     [rbx+r15*8+10h], rax
0x18000f795  mov     rcx, [rsi+8]
0x18000f799  cmp     [rcx+r15*8+10h], rdi
0x18000f79e  jz      loc_18000F536
0x18000f7a4  mov     rdx, [rbp+var_20]
0x18000f7a8  mov     eax, [rdx+r12]
0x18000f7ac  mov     [rcx+r15*8+8], eax
  ... truncated ...
```
