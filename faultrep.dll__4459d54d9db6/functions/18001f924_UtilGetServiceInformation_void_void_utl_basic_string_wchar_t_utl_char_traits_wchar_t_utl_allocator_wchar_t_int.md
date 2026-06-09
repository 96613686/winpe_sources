# UtilGetServiceInformation(void *,void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001f924`
- end: `0x18001ffe2`
- name: `?UtilGetServiceInformation@@YAJPEAX0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1111@Z`
- size: `1726`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800190a0`

## callees

- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x18000bc54`
- `0x18000be60`
- `0x180016414`
- `0x18001f6c8`
- `0x18001f924`
- `0x18001ffe8`
- `0x1800204ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001faec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001faec`
- `ntdll!ZwQueryInformationThread` at `0x18001fa8c`
- `ntdll!ZwQueryInformationThread` at `0x18001fa8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ff5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fdaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fdaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb79`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001fb19`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001fb19`

## string_xrefs

- `0x18001fd0a`: `SYSTEM\CurrentControlSet\Services\`
- `0x18001fddb`: `ServiceDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetServiceInformation(
        void *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8)
{
  int ServiceInformationFromCommandLine; // eax
  __int64 v10; // r8
  unsigned __int64 v11; // r12
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edi
  _QWORD *v17; // rcx
  int ServiceDisplayName; // edi
  __int64 v19; // rdx
  __int64 v20; // r9
  DWORD ProcessId; // eax
  int v22; // eax
  HLOCAL v23; // rbx
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r8
  __int64 v26; // rcx
  char *v27; // rax
  unsigned __int64 v28; // rax
  _WORD *v29; // rcx
  HKEY *v30; // rax
  _WORD *v31; // rdx
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  unsigned __int64 v34; // rax
  __int64 v35; // r9
  DWORD v37; // [rsp+38h] [rbp-A9h]
  void *v38; // [rsp+48h] [rbp-99h] BYREF
  char *v39; // [rsp+50h] [rbp-91h]
  _WORD v40[8]; // [rsp+58h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-79h] BYREF
  __int128 ThreadInformation; // [rsp+70h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-61h]
  __int64 v44; // [rsp+88h] [rbp-59h] BYREF
  void *v45; // [rsp+90h] [rbp-51h] BYREF
  char *v46; // [rsp+98h] [rbp-49h]
  _WORD v47[8]; // [rsp+A0h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+B0h] [rbp-31h] BYREF
  _WORD v49[8]; // [rsp+C0h] [rbp-21h] BYREF
  void *v50[2]; // [rsp+D0h] [rbp-11h] BYREF
  _WORD v51[12]; // [rsp+E0h] [rbp-1h] BYREF

  v38 = v40;
  v39 = (char *)v40;
  v40[0] = 0;
  lpSubKey[0] = v49;
  lpSubKey[1] = v49;
  v49[0] = 0;
  v45 = v47;
  v46 = (char *)v47;
  v47[0] = 0;
  v50[0] = v51;
  v50[1] = v51;
  v51[0] = 0;
  hKey = 0;
  if ( !a1 || !a2 || !a3 || !a4 || !a5 || !a6 || !a7 || !a8 )
  {
    ServiceDisplayName = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    goto LABEL_108;
  }
  ServiceInformationFromCommandLine = UtilGetServiceInformationFromCommandLine(a1, a3, a4, a5);
  if ( ServiceInformationFromCommandLine < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
      (unsigned int)ServiceInformationFromCommandLine);
  }
  v10 = *(_QWORD *)(a5 + 8);
  v11 = -1;
  if ( *(_QWORD *)a5 != v10 )
  {
    if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
            (__int64)&v38,
            *(const void **)a5,
            (v10 - *(_QWORD *)a5) >> 1) )
    {
      ServiceDisplayName = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_108;
      v19 = 79;
      goto LABEL_43;
    }
    goto LABEL_45;
  }
  v12 = 0;
  v44 = 0;
  *(_QWORD *)&ThreadInformation = &v44;
  *((_QWORD *)&ThreadInformation + 1) = 0x800001720LL;
  v13 = ZwQueryInformationThread(a2, ThreadTebInformation, &ThreadInformation, 0x10u, 0);
  v16 = v13;
  if ( v13 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13);
      v17 = WPP_GLOBAL_Control;
    }
    ServiceDisplayName = v16 | 0x10000000;
    if ( ServiceDisplayName < 0 )
    {
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
      {
        v19 = 80;
LABEL_22:
        v20 = (unsigned int)ServiceDisplayName;
LABEL_44:
        WPP_SF_d(v17[2], v19, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v20);
        goto LABEL_108;
      }
      goto LABEL_108;
    }
  }
  else
  {
    v12 = v44;
  }
  ProcessId = GetProcessId(a1);
  v39 = (char *)v38;
  *(_WORD *)v38 = 0;
  hMem = 0;
  ThreadInformation = __PAIR64__(v12, ProcessId);
  v22 = I_QueryTagInformation(0, 1, &ThreadInformation);
  ServiceDisplayName = v22;
  if ( v22 )
  {
    if ( v22 > 0 )
      ServiceDisplayName = (unsigned __int16)v22 | 0x80070000;
  }
  else
  {
    v23 = hMem;
    ServiceDisplayName = 0;
    if ( !hMem )
      goto LABEL_45;
    if ( !*(_WORD *)hMem )
      goto LABEL_33;
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)hMem + v24) );
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((__int64)&v38, hMem, v24) )
    {
LABEL_33:
      if ( !v23 )
        goto LABEL_45;
    }
    else
    {
      ServiceDisplayName = -2147024882;
    }
    LocalFree(v23);
  }
  if ( ServiceDisplayName >= 0 )
  {
LABEL_45:
    if ( v38 == v39 )
      goto LABEL_59;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a6,
                             95) )
    {
LABEL_64:
      ServiceDisplayName = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_108;
      v19 = 82;
      goto LABEL_43;
    }
    v25 = (v39 - (_BYTE *)v38) >> 1;
    if ( !v25 )
    {
LABEL_56:
      if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append((__int64)a6, v38, v25) )
      {
        if ( (unsigned __int64)((__int64)(a6[1] - *a6) >> 1) > 0x40 )
        {
          v29 = (_WORD *)(*a6 + 128LL);
          a6[1] = v29;
          *v29 = 0;
        }
LABEL_59:
        ServiceDisplayName = UtilGetServiceDisplayName(v38, &v45);
        if ( (int)(ServiceDisplayName + 0x80000000) >= 0 && ServiceDisplayName != -2147024846 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 83;
            goto LABEL_22;
          }
          goto LABEL_108;
        }
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                (__int64)lpSubKey,
                L"SYSTEM\\CurrentControlSet\\Services\\",
                0x22u) )
        {
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_108;
          v19 = 84;
          goto LABEL_43;
        }
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                (__int64)lpSubKey,
                v38,
                (v39 - (_BYTE *)v38) >> 1) )
        {
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_108;
          v19 = 85;
          goto LABEL_43;
        }
        v30 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 1u, v30)
          || !hKey
          || (int)UtilRegGetString(hKey, L"Parameters", L"ServiceDll", 0, v50, 1, v37) < 0 )
        {
LABEL_94:
          if ( v45 == v46 )
          {
            if ( v38 != v39
              && !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                    a8,
                    v38,
                    (v39 - (_BYTE *)v38) >> 1) )
            {
              ServiceDisplayName = -2147024882;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_108;
              }
              v19 = 88;
              goto LABEL_43;
            }
LABEL_104:
            ServiceDisplayName = 0;
            goto LABEL_108;
          }
          if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                 a8,
                 v45,
                 (v46 - (_BYTE *)v45) >> 1) )
          {
            goto LABEL_104;
          }
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_108;
          v19 = 87;
LABEL_43:
          v20 = 2147942414LL;
          goto LABEL_44;
        }
        if ( v50[0] )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_WORD *)v50[0] + v32) );
          v33 = (unsigned __int16 *)((char *)v50[0] + 2 * v32);
          while ( 1 )
          {
            v31 = v33;
            if ( v33 <= v50[0] )
              break;
            v34 = *--v33;
            LOWORD(v34) = v34 - 47;
            if ( (unsigned __int16)v34 <= 0x2Du )
            {
              v35 = 0x200000000801LL;
              if ( _bittest64(&v35, v34) )
                break;
            }
          }
          if ( v31 )
          {
            do
              ++v11;
            while ( v31[v11] );
LABEL_81:
            if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a7, v31, v11) )
            {
              ServiceDisplayName = -2147024882;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_108;
              }
              v19 = 86;
              goto LABEL_43;
            }
            goto LABEL_94;
          }
        }
        else
        {
          v31 = 0;
        }
        v11 = 0;
        goto LABEL_81;
      }
      goto LABEL_64;
    }
    v26 = (v39 - (_BYTE *)v38) >> 1;
    v27 = (char *)v38;
    if ( *(_WORD *)v38 == 95 )
    {
LABEL_51:
      if ( v27 )
      {
        v28 = (v27 - (_BYTE *)v38) >> 1;
        goto LABEL_54;
      }
    }
    else
    {
      while ( v26 != 1 )
      {
        --v26;
        v27 += 2;
        if ( *(_WORD *)v27 == 95 )
          goto LABEL_51;
      }
    }
    v28 = -1;
LABEL_54:
    if ( v25 >= v28 )
      v25 = v28;
    goto LABEL_56;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v19 = 81;
    goto LABEL_22;
  }
LABEL_108:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v50[0] != v51 )
    operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v45 != v47 )
    operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpSubKey[0] != v49 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 != v40 )
    operator delete(v38, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ServiceDisplayName;
}

```

## disassembly

```asm
0x18001f924  mov     rax, rsp
0x18001f927  mov     [rax+10h], rbx
0x18001f92b  mov     [rax+18h], rdi
0x18001f92f  mov     [rax+8], rcx
0x18001f933  push    rbp
0x18001f934  push    r12
0x18001f936  push    r13
0x18001f938  push    r14
0x18001f93a  push    r15
0x18001f93c  lea     rbp, [rax-3Fh]
0x18001f940  sub     rsp, 0F0h
0x18001f947  mov     r10, r9
0x18001f94a  mov     r11, r8
0x18001f94d  mov     rdi, rdx
0x18001f950  lea     rax, [rsp+110h+var_C0]
0x18001f955  mov     [rsp+110h+var_D0], rax
0x18001f95a  lea     rax, [rsp+110h+var_C0]
0x18001f95f  mov     [rsp+110h+var_C8], rax
0x18001f964  xor     r14d, r14d
0x18001f967  mov     [rsp+110h+var_C0], r14w
0x18001f96d  lea     rax, [rbp+37h+var_58]
0x18001f971  mov     [rbp+37h+lpSubKey], rax
0x18001f975  lea     rax, [rbp+37h+var_58]
0x18001f979  mov     [rbp+37h+var_60], rax
0x18001f97d  mov     [rbp+37h+var_58], r14w
0x18001f982  lea     rax, [rbp+37h+var_78]
0x18001f986  mov     [rbp+37h+var_88], rax
0x18001f98a  lea     rax, [rbp+37h+var_78]
0x18001f98e  mov     [rbp+37h+var_80], rax
0x18001f992  mov     [rbp+37h+var_78], r14w
0x18001f997  lea     rax, [rbp+37h+var_38]
0x18001f99b  mov     [rbp+37h+var_48], rax
0x18001f99f  lea     rax, [rbp+37h+var_38]
0x18001f9a3  mov     [rbp+37h+var_40], rax
0x18001f9a7  mov     [rbp+37h+var_38], r14w
0x18001f9ac  mov     [rbp+37h+hKey], r14
0x18001f9b0  test    rcx, rcx
0x18001f9b3  jz      loc_18001FF1F
0x18001f9b9  test    rdx, rdx
0x18001f9bc  jz      loc_18001FF1F
0x18001f9c2  test    r8, r8
0x18001f9c5  jz      loc_18001FF1F
0x18001f9cb  test    r9, r9
0x18001f9ce  jz      loc_18001FF1F
0x18001f9d4  mov     rbx, [rbp+37h+arg_20]
0x18001f9d8  test    rbx, rbx
0x18001f9db  jz      loc_18001FF1F
0x18001f9e1  mov     r13, [rbp+37h+arg_28]
0x18001f9e5  test    r13, r13
0x18001f9e8  jz      loc_18001FF1F
0x18001f9ee  cmp     [rbp+37h+arg_30], r14
0x18001f9f2  jz      loc_18001FF1F
0x18001f9f8  cmp     [rbp+37h+arg_38], r14
0x18001f9fc  jz      loc_18001FF1F
0x18001fa02  mov     r9, rbx
0x18001fa05  mov     r8, r10
0x18001fa08  mov     rdx, r11
0x18001fa0b  call    ?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z; UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001fa10  lea     r15, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18001fa17  lea     r14, WPP_GLOBAL_Control
0x18001fa1e  test    eax, eax
0x18001fa20  jns     short loc_18001FA48
0x18001fa22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa29  cmp     rcx, r14
0x18001fa2c  jz      short loc_18001FA48
0x18001fa2e  test    byte ptr [rcx+1Ch], 2
0x18001fa32  jz      short loc_18001FA48
0x18001fa34  mov     edx, 4Eh ; 'N'
0x18001fa39  mov     r9d, eax
0x18001fa3c  mov     r8, r15
0x18001fa3f  mov     rcx, [rcx+10h]
0x18001fa43  call    WPP_SF_d
0x18001fa48  mov     r8, [rbx+8]
0x18001fa4c  mov     rdx, [rbx]
0x18001fa4f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001fa53  cmp     rdx, r8
0x18001fa56  jnz     loc_18001FBA9
0x18001fa5c  xor     ebx, ebx
0x18001fa5e  mov     [rbp+37h+var_90], rbx
0x18001fa62  lea     rax, [rbp+37h+var_90]
0x18001fa66  mov     qword ptr [rbp+37h+ThreadInformation], rax
0x18001fa6a  mov     dword ptr [rbp+37h+ThreadInformation+8], 1720h
0x18001fa71  mov     dword ptr [rbp+37h+ThreadInformation+0Ch], 8
0x18001fa78  mov     [rsp+110h+ReturnLength], rbx; ReturnLength
0x18001fa7d  lea     r9d, [r12+11h]; ThreadInformationLength
0x18001fa82  lea     r8, [rbp+37h+ThreadInformation]; ThreadInformation
0x18001fa86  lea     edx, [rbx+1Ah]; ThreadInformationClass
0x18001fa89  mov     rcx, rdi; ThreadHandle
0x18001fa8c  call    cs:__imp_ZwQueryInformationThread
0x18001fa92  mov     edi, eax
0x18001fa94  test    eax, eax
0x18001fa96  jz      short loc_18001FAE5
0x18001fa98  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa9f  cmp     rcx, r14
0x18001faa2  jz      short loc_18001FABD
0x18001faa4  test    byte ptr [rcx+1Ch], 1
0x18001faa8  jz      short loc_18001FABD
0x18001faaa  mov     r9d, eax
0x18001faad  mov     rcx, [rcx+10h]
0x18001fab1  call    WPP_SF_L
0x18001fab6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fabd  or      edi, 10000000h
0x18001fac3  jge     short loc_18001FAE8
0x18001fac5  cmp     rcx, r14
0x18001fac8  jz      loc_18001FF53
0x18001face  test    byte ptr [rcx+1Ch], 1
0x18001fad2  jz      loc_18001FF53
0x18001fad8  mov     edx, 50h ; 'P'
0x18001fadd  mov     r9d, edi
0x18001fae0  jmp     loc_18001FBE7
0x18001fae5  mov     ebx, dword ptr [rbp+37h+var_90]
0x18001fae8  mov     rcx, [rbp+37h+Process]; Process
0x18001faec  call    cs:__imp_GetProcessId
0x18001faf2  mov     rdx, [rsp+110h+var_D0]
0x18001faf7  mov     [rsp+110h+var_C8], rdx
0x18001fafc  xor     ecx, ecx
0x18001fafe  mov     [rdx], cx
0x18001fb01  xorps   xmm0, xmm0
0x18001fb04  movups  [rbp+37h+ThreadInformation], xmm0
0x18001fb08  mov     [rbp+37h+hMem], rcx
0x18001fb0c  mov     dword ptr [rbp+37h+ThreadInformation], eax
0x18001fb0f  mov     dword ptr [rbp+37h+ThreadInformation+4], ebx
0x18001fb12  lea     r8, [rbp+37h+ThreadInformation]
0x18001fb16  lea     edx, [rcx+1]
0x18001fb19  call    cs:__imp_I_QueryTagInformation
0x18001fb1f  mov     edi, eax
0x18001fb21  xor     ebx, ebx
0x18001fb23  test    eax, eax
0x18001fb25  jz      short loc_18001FB34
0x18001fb27  jle     short loc_18001FB81
0x18001fb29  movzx   edi, ax
0x18001fb2c  or      edi, 80070000h
0x18001fb32  jmp     short loc_18001FB81
0x18001fb34  mov     rbx, [rbp+37h+hMem]
0x18001fb38  xor     edi, edi
0x18001fb3a  test    rbx, rbx
0x18001fb3d  jz      loc_18001FBF8
0x18001fb43  cmp     [rbx], di
0x18001fb46  jz      short loc_18001FB6D
0x18001fb48  mov     r8, r12
0x18001fb4b  inc     r8
0x18001fb4e  cmp     [rbx+r8*2], di
0x18001fb53  jnz     short loc_18001FB4B
0x18001fb55  mov     rdx, rbx
0x18001fb58  lea     rcx, [rsp+110h+var_D0]
0x18001fb5d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001fb62  test    al, al
0x18001fb64  jnz     short loc_18001FB6D
0x18001fb66  mov     edi, 8007000Eh
0x18001fb6b  jmp     short loc_18001FB76
0x18001fb6d  test    rbx, rbx
0x18001fb70  jz      loc_18001FBF8
0x18001fb76  mov     rcx, rbx; hMem
0x18001fb79  call    cs:__imp_LocalFree
0x18001fb7f  xor     ebx, ebx
0x18001fb81  test    edi, edi
0x18001fb83  jns     short loc_18001FBFA
0x18001fb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb8c  cmp     rcx, r14
0x18001fb8f  jz      loc_18001FF53
0x18001fb95  test    byte ptr [rcx+1Ch], 1
0x18001fb99  jz      loc_18001FF53
0x18001fb9f  mov     edx, 51h ; 'Q'
0x18001fba4  jmp     loc_18001FADD
0x18001fba9  sub     r8, rdx
0x18001fbac  sar     r8, 1
0x18001fbaf  lea     rcx, [rsp+110h+var_D0]
0x18001fbb4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001fbb9  xor     ebx, ebx
0x18001fbbb  test    al, al
0x18001fbbd  jnz     short loc_18001FBFA
0x18001fbbf  mov     edi, 8007000Eh
0x18001fbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbcb  cmp     rcx, r14
0x18001fbce  jz      loc_18001FF53
0x18001fbd4  test    byte ptr [rcx+1Ch], 1
0x18001fbd8  jz      loc_18001FF53
0x18001fbde  lea     edx, [rbx+4Fh]
0x18001fbe1  mov     r9d, 8007000Eh
0x18001fbe7  mov     r8, r15
0x18001fbea  mov     rcx, [rcx+10h]
0x18001fbee  call    WPP_SF_d
0x18001fbf3  jmp     loc_18001FF53
0x18001fbf8  xor     ebx, ebx
0x18001fbfa  mov     rax, [rsp+110h+var_C8]
0x18001fbff  cmp     [rsp+110h+var_D0], rax
0x18001fc04  jz      loc_18001FC93
0x18001fc0a  mov     edi, 5Fh ; '_'
0x18001fc0f  mov     edx, edi
0x18001fc11  mov     rcx, r13
0x18001fc14  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18001fc19  test    al, al
0x18001fc1b  jz      loc_18001FCDB
0x18001fc21  mov     r8, [rsp+110h+var_C8]
0x18001fc26  mov     rdx, [rsp+110h+var_D0]
0x18001fc2b  sub     r8, rdx
0x18001fc2e  sar     r8, 1
0x18001fc31  jz      short loc_18001FC68
0x18001fc33  mov     rcx, r8
0x18001fc36  mov     rax, rdx
0x18001fc39  cmp     [rdx], di
0x18001fc3c  jz      short loc_18001FC50
0x18001fc3e  cmp     rcx, 1
0x18001fc42  jz      short loc_18001FC5D
0x18001fc44  dec     rcx
0x18001fc47  add     rax, 2
0x18001fc4b  cmp     [rax], di
0x18001fc4e  jnz     short loc_18001FC3E
0x18001fc50  test    rax, rax
0x18001fc53  jz      short loc_18001FC5D
0x18001fc55  sub     rax, rdx
0x18001fc58  sar     rax, 1
0x18001fc5b  jmp     short loc_18001FC60
0x18001fc5d  mov     rax, r12
0x18001fc60  cmp     r8, rax
0x18001fc63  jb      short loc_18001FC68
0x18001fc65  mov     r8, rax
0x18001fc68  mov     rcx, r13
0x18001fc6b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001fc70  test    al, al
0x18001fc72  jz      short loc_18001FCDB
0x18001fc74  mov     rcx, [r13+0]
0x18001fc78  mov     rax, [r13+8]
0x18001fc7c  sub     rax, rcx
0x18001fc7f  sar     rax, 1
0x18001fc82  cmp     rax, 40h ; '@'
0x18001fc86  jbe     short loc_18001FC93
0x18001fc88  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18001fc8c  mov     [r13+8], rcx
0x18001fc90  mov     [rcx], bx
0x18001fc93  lea     rdx, [rbp+37h+var_88]
0x18001fc97  mov     rcx, [rsp+110h+var_D0]
0x18001fc9c  call    ?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001fca1  mov     edi, eax
0x18001fca3  mov     eax, 80000000h
0x18001fca8  lea     ecx, [rdi+rax]
0x18001fcab  test    eax, ecx
0x18001fcad  jnz     short loc_18001FD04
0x18001fcaf  cmp     edi, 80070032h
0x18001fcb5  jz      short loc_18001FD04
0x18001fcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcbe  cmp     rcx, r14
0x18001fcc1  jz      loc_18001FF53
0x18001fcc7  test    byte ptr [rcx+1Ch], 1
0x18001fccb  jz      loc_18001FF53
0x18001fcd1  mov     edx, 53h ; 'S'
0x18001fcd6  jmp     loc_18001FADD
0x18001fcdb  mov     edi, 8007000Eh
0x18001fce0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fce7  cmp     rcx, r14
0x18001fcea  jz      loc_18001FF53
0x18001fcf0  test    byte ptr [rcx+1Ch], 1
0x18001fcf4  jz      loc_18001FF53
0x18001fcfa  mov     edx, 52h ; 'R'
0x18001fcff  jmp     loc_18001FBE1
0x18001fd04  mov     r8d, 22h ; '"'
0x18001fd0a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\"
0x18001fd11  lea     rcx, [rbp+37h+lpSubKey]
0x18001fd15  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001fd1a  test    al, al
0x18001fd1c  jnz     short loc_18001FD47
0x18001fd1e  mov     edi, 8007000Eh
0x18001fd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd2a  cmp     rcx, r14
0x18001fd2d  jz      loc_18001FF53
0x18001fd33  test    byte ptr [rcx+1Ch], 1
0x18001fd37  jz      loc_18001FF53
0x18001fd3d  mov     edx, 54h ; 'T'
0x18001fd42  jmp     loc_18001FBE1
0x18001fd47  mov     r8, [rsp+110h+var_C8]
0x18001fd4c  mov     rdx, [rsp+110h+var_D0]
0x18001fd51  sub     r8, rdx
0x18001fd54  sar     r8, 1
0x18001fd57  lea     rcx, [rbp+37h+lpSubKey]
0x18001fd5b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18001fd60  test    al, al
0x18001fd62  jnz     short loc_18001FD8D
0x18001fd64  mov     edi, 8007000Eh
0x18001fd69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd70  cmp     rcx, r14
0x18001fd73  jz      loc_18001FF53
0x18001fd79  test    byte ptr [rcx+1Ch], 1
0x18001fd7d  jz      loc_18001FF53
0x18001fd83  mov     edx, 55h ; 'U'
0x18001fd88  jmp     loc_18001FBE1
0x18001fd8d  lea     rcx, [rbp+37h+hKey]
0x18001fd91  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001fd96  mov     [rsp+110h+ReturnLength], rax; phkResult
0x18001fd9b  mov     r9d, 1; samDesired
0x18001fda1  xor     r8d, r8d; ulOptions
0x18001fda4  mov     rdx, [rbp+37h+lpSubKey]; lpSubKey
0x18001fda8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fdaf  call    cs:__imp_RegOpenKeyExW
0x18001fdb5  test    eax, eax
0x18001fdb7  jnz     loc_18001FE8E
0x18001fdbd  mov     rcx, [rbp+37h+hKey]; hKey
0x18001fdc1  test    rcx, rcx
0x18001fdc4  jz      loc_18001FE8E
0x18001fdca  mov     [rsp+110h+var_E8], 1; char
0x18001fdcf  lea     rax, [rbp+37h+var_48]
  ... truncated ...
```
