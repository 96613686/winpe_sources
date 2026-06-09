# SERVICES_MANAGER::Kill(void)

- ea: `0x140003674`
- end: `0x140003cd2`
- name: `?Kill@SERVICES_MANAGER@@QEAAJXZ`
- size: `1630`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140002ec0`

## callees

- `0x140001014`
- `0x140001054`
- `0x140003674`
- `0x140003cd8`
- `0x140003d1c`
- `0x140005074`
- `0x14000548e`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003a05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003a05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003a84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400039c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400039c8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140003ba6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140003ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003b25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003b25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bdb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003904`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003920`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003bf0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c5b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003904`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003920`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003bf0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c48`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140003c5b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400036dc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140003a92`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400036dc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140003a92`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003822`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003b15`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003822`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003b15`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x14000387a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1400038bf`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x14000387a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1400038bf`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1400038f7`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140003bd1`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1400038f7`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x140003bd1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000384d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140003b88`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000384d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140003b88`

## string_xrefs

- `0x140003926`: `iisw3adm.dll`
- `0x140003962`: `wam.dll`
- `0x140003969`: `DLLHOST`
- `0x1400039ba`: `system\CurrentControlSet\services\IISAdmin`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::Kill(SERVICES_MANAGER *this)
{
  SC_HANDLE v1; // rsi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  signed int LastError; // eax
  signed int v6; // ebx
  unsigned int v7; // r13d
  _QWORD *v8; // r15
  void *v9; // rax
  _QWORD *v10; // rax
  unsigned int v11; // edi
  BYTE *v12; // rax
  signed int v13; // eax
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  BYTE *v19; // rdi
  int v20; // eax
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  HKEY v24; // r14
  signed int v25; // edi
  unsigned int v26; // ecx
  unsigned int v27; // eax
  __int64 v28; // r13
  SERVICES_MANAGER *v29; // rbx
  signed int v30; // eax
  __int64 v31; // rax
  _DWORD *v32; // rax
  _DWORD *v33; // r14
  unsigned int v34; // r12d
  signed int v35; // eax
  unsigned int i; // edi
  void *v37; // rcx
  int v39; // [rsp+30h] [rbp-D0h]
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v41; // [rsp+38h] [rbp-C8h]
  DWORD cbBufSize; // [rsp+3Ch] [rbp-C4h] BYREF
  int v43; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbBytesNeeded; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h]
  SERVICES_MANAGER *v48; // [rsp+60h] [rbp-A0h]
  __int128 Info; // [rsp+68h] [rbp-98h] BYREF
  __int128 v50; // [rsp+78h] [rbp-88h]
  _QWORD *v51; // [rsp+88h] [rbp-78h]
  BYTE Buffer[16]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v53; // [rsp+A0h] [rbp-60h]
  int v54; // [rsp+B0h] [rbp-50h]
  _QWORD v55[3]; // [rsp+B8h] [rbp-48h] BYREF
  BYTE v56[64]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[2044]; // [rsp+110h] [rbp+10h] BYREF
  int v58; // [rsp+90Ch] [rbp+80Ch]

  v1 = 0;
  v48 = this;
  cbBufSize = 0;
  pcbBytesNeeded = 0;
  v51 = 0;
  v54 = 0;
  Info = 0;
  v50 = 0;
  *(_OWORD *)Buffer = 0;
  v53 = 0;
  v3 = OpenSCManagerW(0, 0, 4u);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_91;
  }
  Block = 0;
  *(_QWORD *)&v50 = &qword_140007B18;
  *((_QWORD *)&Info + 1) = &qword_140007B18;
  LODWORD(Info) = -1;
  v51 = v55;
  v7 = 0;
  v8 = 0;
  DWORD2(v50) = 3;
  memset(v55, 0, sizeof(v55));
  v39 = SERVICES_MANAGER::ResolveDependencies(this, v3);
  v6 = v39;
  if ( v39 >= 0 )
  {
    v41 = *((_DWORD *)this + 2);
    v7 = v41;
    v9 = operator new(saturated_mul(v41, 4u));
    Block = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 4LL * v41);
      v10 = operator new(saturated_mul(v41, 8u));
      v8 = v10;
      if ( v10 )
      {
        v43 = 0;
        memset_0(v10, 0, 8LL * v41);
        v11 = 0;
        if ( v41 )
        {
          while ( 1 )
          {
            if ( v11 > *((_DWORD *)v48 + 2) - 1 )
            {
              v1 = 0;
              v6 = -2147023483;
              goto LABEL_47;
            }
            v1 = OpenServiceW(v4, *(LPCWSTR *)(*((_QWORD *)v48 + 6) + 8LL * v11), 7u);
            if ( !v1 || !QueryServiceStatusEx(v1, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
              break;
            *((_DWORD *)Block + v11) = HIDWORD(v53);
            if ( !QueryServiceConfig2W(v1, 2u, v56, 0, &cbBufSize) )
            {
              if ( GetLastError() != 122 )
                break;
              v12 = (BYTE *)operator new(cbBufSize);
              v8[v11] = v12;
              if ( !v12 )
              {
                v6 = -2147024888;
                goto LABEL_47;
              }
              if ( !QueryServiceConfig2W(v1, 2u, v12, cbBufSize, &cbBufSize) )
                break;
            }
            if ( !ChangeServiceConfig2W(v1, 2u, &Info) )
              break;
            CloseServiceHandle(v1);
            if ( ++v11 >= v7 )
            {
              v1 = 0;
              v6 = 0;
              v39 = 0;
              goto LABEL_21;
            }
          }
          v13 = GetLastError();
          v39 = v13;
          v6 = v13;
          if ( v13 <= 0 )
            goto LABEL_43;
          v6 = (unsigned __int16)v13 | 0x80070000;
LABEL_47:
          v39 = v6;
        }
        else
        {
LABEL_21:
          CloseServiceHandle(v4);
          v14 = KillTaskByName(L"SVCHOST", "iisw3adm.dll");
          v15 = KillTaskByName(L"W3WP", 0);
          if ( v14 >= 0 )
            v14 = v15;
          v16 = KillTaskByName(L"INETINFO", 0);
          if ( v14 >= 0 )
            v14 = v16;
          v17 = KillTaskByName(L"DLLHOST", "wam.dll");
          if ( v14 >= 0 )
            v14 = v17;
          v18 = KillTaskByName(L"ASPNET_WP", 0);
          phkResult = 0;
          Type = 0;
          if ( v14 >= 0 )
            v14 = v18;
          cbData = 0;
          v43 = v14;
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"system\\CurrentControlSet\\services\\IISAdmin",
                  0,
                  0x20019u,
                  &phkResult) )
          {
            cbData = 2048;
            v1 = 0;
            if ( !RegQueryValueExW(phkResult, L"KillProcsOnFailure", 0, &Type, Data, &cbData) && Type == 7 && cbData > 2 )
            {
              v19 = Data;
              v58 = 0;
              if ( *(_WORD *)Data )
              {
                do
                {
                  v20 = KillTaskByName(v19, 0);
                  if ( v14 >= 0 )
                    v14 = v20;
                  v21 = -1;
                  do
                    ++v21;
                  while ( *(_WORD *)&v19[2 * v21] );
                  v22 = -2 - 2 * v21;
                  v23 = -1;
                  cbData += v22;
                  do
                    ++v23;
                  while ( *(_WORD *)&v19[2 * v23] );
                  v19 += 2 * v23 + 2;
                }
                while ( *(_WORD *)v19 );
                v6 = v39;
                v43 = v14;
              }
            }
            RegCloseKey(phkResult);
          }
        }
LABEL_43:
        phkResult = (HKEY)OpenSCManagerW(0, 0, 4u);
        v24 = phkResult;
        if ( phkResult )
        {
          cbData = 0;
          v25 = 0;
          v26 = 0;
          if ( v7 )
          {
            v27 = v41;
            v28 = 0;
            v29 = v48;
            do
            {
              if ( v8[v28] )
              {
                if ( v26 <= *((_DWORD *)v29 + 2) - 1 )
                {
                  v1 = OpenServiceW((SC_HANDLE)v24, *(LPCWSTR *)(*((_QWORD *)v29 + 6) + 8 * v28), 0x17u);
                  if ( v1 )
                  {
                    v31 = v8[v28];
                    if ( *(_DWORD *)(v31 + 24) != 3
                      || (v32 = *(_DWORD **)(v31 + 32)) == 0
                      || *v32
                      || v32[2]
                      || (v25 = 0, v32[4]) )
                    {
                      v33 = Block;
                      v34 = 0;
                      v25 = 0;
                      do
                      {
                        if ( !QueryServiceStatusEx(v1, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
                          break;
                        if ( HIDWORD(v53) != v33[v28] )
                          break;
                        if ( *(_DWORD *)&Buffer[4] == 1 )
                          break;
                        Sleep(0x64u);
                        ++v34;
                      }
                      while ( v34 < 0xA );
                      v24 = phkResult;
                      v29 = v48;
                    }
                    if ( !ChangeServiceConfig2W(v1, 2u, (LPVOID)v8[v28]) )
                    {
                      v35 = GetLastError();
                      v25 = v35;
                      if ( v35 > 0 )
                        v25 = (unsigned __int16)v35 | 0x80070000;
                    }
                    CloseServiceHandle(v1);
                    v1 = 0;
                  }
                  else
                  {
                    v30 = GetLastError();
                    v25 = v30;
                    if ( v30 > 0 )
                      v25 = (unsigned __int16)v30 | 0x80070000;
                  }
                  v26 = cbData;
                }
                else
                {
                  v25 = -2147023483;
                }
                v27 = v41;
              }
              ++v26;
              ++v28;
              cbData = v26;
            }
            while ( v26 < v27 );
            v6 = v39;
            v7 = v41;
          }
          CloseServiceHandle((SC_HANDLE)v24);
          if ( v6 >= 0 )
          {
            if ( v43 >= 0 )
            {
              if ( v25 < 0 )
                v6 = v25;
            }
            else
            {
              v6 = v43;
            }
          }
        }
        else
        {
          GetLastError();
        }
        if ( v1 )
          CloseServiceHandle(v1);
        goto LABEL_83;
      }
    }
    v6 = -2147024888;
  }
  CloseServiceHandle(v4);
LABEL_83:
  if ( v8 )
  {
    for ( i = 0; i < v7; ++i )
    {
      v37 = (void *)v8[i];
      if ( v37 )
      {
        operator delete(v37);
        v8[i] = 0;
      }
    }
    operator delete(v8);
  }
  if ( Block )
    operator delete(Block);
LABEL_91:
  SERVICES_MANAGER::ResetDependencies(v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003674  push    rbp
0x140003676  push    rbx
0x140003677  push    rsi
0x140003678  push    rdi
0x140003679  push    r12
0x14000367b  push    r13
0x14000367d  push    r14
0x14000367f  push    r15
0x140003681  lea     rbp, [rsp-828h]
0x140003689  sub     rsp, 928h
0x140003690  mov     rax, cs:__security_cookie
0x140003697  xor     rax, rsp
0x14000369a  mov     [rbp+860h+var_50], rax
0x1400036a1  xor     esi, esi
0x1400036a3  mov     [rsp+960h+var_900], rcx
0x1400036a8  xorps   xmm0, xmm0
0x1400036ab  mov     [rsp+960h+cbBufSize], esi
0x1400036af  xor     eax, eax
0x1400036b1  mov     [rsp+960h+var_918], esi
0x1400036b5  xorps   xmm1, xmm1
0x1400036b8  mov     [rbp+860h+var_8D8], rax
0x1400036bc  mov     r12, rcx
0x1400036bf  mov     [rbp+860h+var_8B0], eax
0x1400036c2  lea     r8d, [rsi+4]; dwDesiredAccess
0x1400036c6  xor     edx, edx; lpDatabaseName
0x1400036c8  xor     ecx, ecx; lpMachineName
0x1400036ca  movups  [rsp+960h+Info], xmm0
0x1400036cf  movups  [rsp+960h+var_8E8], xmm0
0x1400036d4  movups  xmmword ptr [rbp+860h+Buffer], xmm1
0x1400036d8  movups  [rbp+860h+var_8C0], xmm1
0x1400036dc  call    cs:__imp_OpenSCManagerW
0x1400036e2  mov     r14, rax
0x1400036e5  test    rax, rax
0x1400036e8  jnz     short loc_140003708
0x1400036ea  call    cs:__imp_GetLastError
0x1400036f0  mov     ebx, eax
0x1400036f2  test    eax, eax
0x1400036f4  jle     loc_140003CA3
0x1400036fa  movzx   ebx, ax
0x1400036fd  or      ebx, 80070000h
0x140003703  jmp     loc_140003CA3
0x140003708  lea     rax, qword_140007B18
0x14000370f  mov     [rsp+960h+Block], rsi
0x140003714  mov     qword ptr [rsp+960h+var_8E8], rax
0x140003719  mov     rdx, r14; struct SC_HANDLE__ *
0x14000371c  mov     qword ptr [rsp+960h+Info+8], rax
0x140003721  mov     rcx, r12; this
0x140003724  lea     rax, [rbp+860h+var_8A8]
0x140003728  mov     dword ptr [rsp+960h+Info], 0FFFFFFFFh
0x140003730  mov     [rbp+860h+var_8D8], rax
0x140003734  mov     r13d, esi
0x140003737  mov     r15, rsi
0x14000373a  mov     dword ptr [rbp+860h+var_8E8+8], 3
0x140003741  mov     [rbp+860h+var_8A8], rsi
0x140003745  mov     [rbp+860h+var_8A0], rsi
0x140003749  mov     [rbp+860h+var_898], rsi
0x14000374d  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x140003752  mov     [rsp+960h+var_930], eax
0x140003756  mov     ebx, eax
0x140003758  test    eax, eax
0x14000375a  js      loc_140003C55
0x140003760  mov     r13d, [r12+8]
0x140003765  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000376c  mov     eax, 4
0x140003771  mov     [rsp+960h+var_928], r13d
0x140003776  mul     r13
0x140003779  mov     edi, r13d
0x14000377c  cmovb   rax, rcx
0x140003780  mov     rcx, rax; Size
0x140003783  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003788  xor     r12d, r12d
0x14000378b  mov     [rsp+960h+Block], rax
0x140003790  test    rax, rax
0x140003793  jnz     short loc_14000379F
0x140003795  mov     ebx, 80070008h
0x14000379a  jmp     loc_140003C58
0x14000379f  lea     r8, ds:0[r13*4]; Size
0x1400037a7  xor     edx, edx; Val
0x1400037a9  mov     rcx, rax; void *
0x1400037ac  call    memset_0
0x1400037b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400037b8  mov     eax, 8
0x1400037bd  mul     rdi
0x1400037c0  cmovb   rax, rcx
0x1400037c4  mov     rcx, rax; Size
0x1400037c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400037cc  mov     r15, rax
0x1400037cf  test    rax, rax
0x1400037d2  jz      short loc_140003795
0x1400037d4  lea     r8, ds:0[r13*8]; Size
0x1400037dc  mov     [rsp+960h+var_920], esi
0x1400037e0  xor     edx, edx; Val
0x1400037e2  mov     rcx, rax; void *
0x1400037e5  call    memset_0
0x1400037ea  mov     edi, esi
0x1400037ec  mov     r12d, 80070000h
0x1400037f2  test    r13d, r13d
0x1400037f5  jz      loc_14000391D
0x1400037fb  xor     ebx, ebx
0x1400037fd  mov     rcx, [rsp+960h+var_900]
0x140003802  mov     eax, [rcx+8]
0x140003805  dec     eax
0x140003807  cmp     edi, eax
0x140003809  ja      loc_140003ABC
0x14000380f  mov     rdx, [rcx+30h]
0x140003813  mov     r8d, 7; dwDesiredAccess
0x140003819  mov     ebx, edi
0x14000381b  mov     rcx, r14; hSCManager
0x14000381e  mov     rdx, [rdx+rbx*8]; lpServiceName
0x140003822  call    cs:__imp_OpenServiceW
0x140003828  mov     rsi, rax
0x14000382b  test    rax, rax
0x14000382e  jz      loc_1400038C9
0x140003834  lea     rax, [rsp+960h+var_918]
0x140003839  mov     r9d, 24h ; '$'; cbBufSize
0x14000383f  lea     r8, [rbp+860h+Buffer]; lpBuffer
0x140003843  mov     [rsp+960h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140003848  xor     edx, edx; InfoLevel
0x14000384a  mov     rcx, rsi; hService
0x14000384d  call    cs:__imp_QueryServiceStatusEx
0x140003853  test    eax, eax
0x140003855  jz      short loc_1400038C9
0x140003857  mov     eax, dword ptr [rbp+860h+var_8C0+0Ch]
0x14000385a  lea     r8, [rbp+860h+var_890]; lpBuffer
0x14000385e  mov     rcx, [rsp+960h+Block]
0x140003863  xor     r9d, r9d; cbBufSize
0x140003866  mov     [rcx+rbx*4], eax
0x140003869  lea     edx, [r9+2]; dwInfoLevel
0x14000386d  lea     rax, [rsp+960h+cbBufSize]
0x140003872  mov     rcx, rsi; hService
0x140003875  mov     [rsp+960h+pcbBytesNeeded], rax; pcbBytesNeeded
0x14000387a  call    cs:__imp_QueryServiceConfig2W
0x140003880  test    eax, eax
0x140003882  jnz     short loc_1400038E8
0x140003884  call    cs:__imp_GetLastError
0x14000388a  cmp     eax, 7Ah ; 'z'
0x14000388d  jnz     short loc_1400038C9
0x14000388f  mov     ecx, [rsp+960h+cbBufSize]; Size
0x140003893  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003898  mov     [r15+rbx*8], rax
0x14000389c  xor     ebx, ebx
0x14000389e  test    rax, rax
0x1400038a1  jz      loc_140003AB5
0x1400038a7  mov     r9d, [rsp+960h+cbBufSize]; cbBufSize
0x1400038ac  lea     rcx, [rsp+960h+cbBufSize]
0x1400038b1  mov     [rsp+960h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x1400038b6  lea     edx, [rbx+2]; dwInfoLevel
0x1400038b9  mov     rcx, rsi; hService
0x1400038bc  mov     r8, rax; lpBuffer
0x1400038bf  call    cs:__imp_QueryServiceConfig2W
0x1400038c5  test    eax, eax
0x1400038c7  jnz     short loc_1400038EA
0x1400038c9  call    cs:__imp_GetLastError
0x1400038cf  mov     [rsp+960h+var_930], eax
0x1400038d3  mov     ebx, eax
0x1400038d5  test    eax, eax
0x1400038d7  jle     loc_140003A8A
0x1400038dd  movzx   ebx, ax
0x1400038e0  or      ebx, r12d
0x1400038e3  jmp     loc_140003AC4
0x1400038e8  xor     ebx, ebx
0x1400038ea  lea     r8, [rsp+960h+Info]; lpInfo
0x1400038ef  mov     edx, 2; dwInfoLevel
0x1400038f4  mov     rcx, rsi; hService
0x1400038f7  call    cs:__imp_ChangeServiceConfig2W
0x1400038fd  test    eax, eax
0x1400038ff  jz      short loc_1400038C9
0x140003901  mov     rcx, rsi; hSCObject
0x140003904  call    cs:__imp_CloseServiceHandle
0x14000390a  inc     edi
0x14000390c  cmp     edi, r13d
0x14000390f  jb      loc_1400037FD
0x140003915  xor     esi, esi
0x140003917  mov     ebx, esi
0x140003919  mov     [rsp+960h+var_930], ebx
0x14000391d  mov     rcx, r14; hSCObject
0x140003920  call    cs:__imp_CloseServiceHandle
0x140003926  lea     rdx, aIisw3admDll; "iisw3adm.dll"
0x14000392d  lea     rcx, aSvchost; "SVCHOST"
0x140003934  call    KillTaskByName
0x140003939  xor     edx, edx
0x14000393b  lea     rcx, aW3wp; "W3WP"
0x140003942  mov     r14d, eax
0x140003945  call    KillTaskByName
0x14000394a  test    r14d, r14d
0x14000394d  lea     rcx, aInetinfo; "INETINFO"
0x140003954  cmovns  r14d, eax
0x140003958  xor     edx, edx
0x14000395a  call    KillTaskByName
0x14000395f  test    r14d, r14d
0x140003962  lea     rdx, aWamDll; "wam.dll"
0x140003969  lea     rcx, aDllhost; "DLLHOST"
0x140003970  cmovns  r14d, eax
0x140003974  call    KillTaskByName
0x140003979  test    r14d, r14d
0x14000397c  lea     rcx, aAspnetWp; "ASPNET_WP"
0x140003983  cmovns  r14d, eax
0x140003987  xor     edx, edx
0x140003989  call    KillTaskByName
0x14000398e  test    r14d, r14d
0x140003991  mov     [rsp+960h+phkResult], rsi
0x140003996  mov     r9d, 20019h; samDesired
0x14000399c  mov     [rsp+960h+Type], esi
0x1400039a0  cmovns  r14d, eax
0x1400039a4  mov     [rsp+960h+cbData], esi
0x1400039a8  lea     rax, [rsp+960h+phkResult]
0x1400039ad  mov     [rsp+960h+var_920], r14d
0x1400039b2  xor     r8d, r8d; ulOptions
0x1400039b5  mov     [rsp+960h+pcbBytesNeeded], rax; phkResult
0x1400039ba  lea     rdx, aSystemCurrentc; "system\\CurrentControlSet\\services\\II"...
0x1400039c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400039c8  call    cs:__imp_RegOpenKeyExW
0x1400039ce  test    eax, eax
0x1400039d0  jnz     loc_140003A8A
0x1400039d6  mov     rcx, [rsp+960h+phkResult]; hKey
0x1400039db  lea     rax, [rsp+960h+cbData]
0x1400039e0  mov     [rsp+960h+lpcbData], rax; lpcbData
0x1400039e5  lea     r9, [rsp+960h+Type]; lpType
0x1400039ea  lea     rax, [rbp+860h+Data]
0x1400039ee  mov     [rsp+960h+cbData], 800h
0x1400039f6  xor     r8d, r8d; lpReserved
0x1400039f9  mov     [rsp+960h+pcbBytesNeeded], rax; lpData
0x1400039fe  lea     rdx, aKillprocsonfai; "KillProcsOnFailure"
0x140003a05  call    cs:__imp_RegQueryValueExW
0x140003a0b  xor     esi, esi
0x140003a0d  test    eax, eax
0x140003a0f  jnz     short loc_140003A7F
0x140003a11  cmp     [rsp+960h+Type], 7
0x140003a16  jnz     short loc_140003A7F
0x140003a18  cmp     [rsp+960h+cbData], 2
0x140003a1d  jbe     short loc_140003A7F
0x140003a1f  lea     rdi, [rbp+860h+Data]
0x140003a23  mov     [rbp+860h+var_54], esi
0x140003a29  cmp     word ptr [rbp+860h+Data], si
0x140003a2d  jz      short loc_140003A7F
0x140003a2f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140003a33  xor     edx, edx
0x140003a35  mov     rcx, rdi
0x140003a38  call    KillTaskByName
0x140003a3d  test    r14d, r14d
0x140003a40  cmovns  r14d, eax
0x140003a44  mov     rax, rbx
0x140003a47  inc     rax
0x140003a4a  cmp     [rdi+rax*2], si
0x140003a4e  jnz     short loc_140003A47
0x140003a50  add     eax, eax
0x140003a52  mov     ecx, 0FFFFFFFEh
0x140003a57  sub     ecx, eax
0x140003a59  mov     rax, rbx
0x140003a5c  add     [rsp+960h+cbData], ecx
0x140003a60  inc     rax
0x140003a63  cmp     [rdi+rax*2], si
0x140003a67  jnz     short loc_140003A60
0x140003a69  lea     rdi, [rdi+rax*2]
0x140003a6d  add     rdi, 2
0x140003a71  cmp     [rdi], si
0x140003a74  jnz     short loc_140003A33
0x140003a76  mov     ebx, [rsp+960h+var_930]
0x140003a7a  mov     [rsp+960h+var_920], r14d
0x140003a7f  mov     rcx, [rsp+960h+phkResult]; hKey
0x140003a84  call    cs:__imp_RegCloseKey
0x140003a8a  xor     edx, edx; lpDatabaseName
0x140003a8c  xor     ecx, ecx; lpMachineName
0x140003a8e  lea     r8d, [rdx+4]; dwDesiredAccess
0x140003a92  call    cs:__imp_OpenSCManagerW
0x140003a98  xor     edx, edx
0x140003a9a  mov     [rsp+960h+phkResult], rax
0x140003a9f  mov     r14, rax
0x140003aa2  test    rax, rax
0x140003aa5  jnz     short loc_140003ACA
0x140003aa7  call    cs:__imp_GetLastError
0x140003aad  xor     r12d, r12d
0x140003ab0  jmp     loc_140003C40
0x140003ab5  mov     ebx, 80070008h
0x140003aba  jmp     short loc_140003AC4
0x140003abc  mov     rsi, rbx
0x140003abf  mov     ebx, 80070585h
0x140003ac4  mov     [rsp+960h+var_930], ebx
0x140003ac8  jmp     short loc_140003A8A
0x140003aca  mov     [rsp+960h+cbData], edx
0x140003ace  mov     edi, edx
0x140003ad0  mov     ecx, edx
0x140003ad2  test    r13d, r13d
0x140003ad5  jz      loc_140003C1C
0x140003adb  mov     eax, [rsp+960h+var_928]
0x140003adf  mov     r13, rdx
0x140003ae2  mov     rbx, [rsp+960h+var_900]
0x140003ae7  cmp     [r15+r13*8], rdx
0x140003aeb  jz      loc_140003C02
0x140003af1  mov     eax, [rbx+8]
0x140003af4  dec     eax
0x140003af6  cmp     ecx, eax
0x140003af8  jbe     short loc_140003B04
0x140003afa  mov     edi, 80070585h
0x140003aff  jmp     loc_140003BFE
0x140003b04  mov     rdx, [rbx+30h]
0x140003b08  mov     r8d, 17h; dwDesiredAccess
0x140003b0e  mov     rcx, r14; hSCManager
0x140003b11  mov     rdx, [rdx+r13*8]; lpServiceName
0x140003b15  call    cs:__imp_OpenServiceW
  ... truncated ...
```
