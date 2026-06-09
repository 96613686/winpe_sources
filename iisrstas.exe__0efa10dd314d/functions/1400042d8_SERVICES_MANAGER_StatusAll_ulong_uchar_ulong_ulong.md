# SERVICES_MANAGER::StatusAll(ulong,uchar *,ulong *,ulong *)

- ea: `0x1400042d8`
- end: `0x140004620`
- name: `?StatusAll@SERVICES_MANAGER@@QEAAJKPEAEPEAK1@Z`
- size: `840`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, unsigned int, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1400031d0`

## callees

- `0x140003cd8`
- `0x140003d1c`
- `0x1400042d8`
- `0x140005482`
- `0x14000548e`
- `0x1400054c0`
- `0x140005550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004597`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400045c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400045c9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400045c0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400045c9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140004389`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140004389`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000440b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000440b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1400045dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1400045eb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1400045dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1400045eb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140004461`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x140004461`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14000443f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140004481`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x14000443f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140004481`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140004424`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140004424`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::StatusAll(
        SERVICES_MANAGER *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r15
  unsigned int *v8; // rdi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // r12
  signed int v11; // eax
  signed int v12; // ebx
  unsigned int v13; // eax
  SC_HANDLE v14; // r14
  __int64 v15; // rsi
  unsigned int v16; // r15d
  _WORD *v17; // rbx
  SC_HANDLE v18; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  unsigned __int8 *v22; // rcx
  __int64 v23; // rbx
  __int128 v24; // xmm1
  __int64 v25; // rdi
  unsigned __int8 *v26; // rdx
  LPQUERY_SERVICE_CONFIGW v27; // rax
  size_t v28; // r8
  signed int LastError; // eax
  signed int v30; // eax
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v33; // [rsp+24h] [rbp-DCh]
  unsigned int v34; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+2Ch] [rbp-D4h]
  unsigned __int8 *v36; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h]
  unsigned int *v38; // [rsp+40h] [rbp-C0h]
  unsigned int *v39; // [rsp+48h] [rbp-B8h]
  _BYTE v40[32]; // [rsp+50h] [rbp-B0h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+70h] [rbp-90h]
  DWORD cbBufSize; // [rsp+78h] [rbp-88h]
  __int16 v43; // [rsp+7Ch] [rbp-84h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-80h] BYREF
  char v45; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v46[8191]; // [rsp+A1h] [rbp-5Fh] BYREF

  v5 = a5;
  v34 = a2;
  v38 = a4;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v36 = a3;
  v39 = a5;
  pcbBytesNeeded = 0;
  v8 = a4;
  memset_0(v46, 0, sizeof(v46));
  v45 = 0;
  lpServiceConfig = (LPQUERY_SERVICE_CONFIGW)&v45;
  cbBufSize = 0x2000;
  v43 = 256;
  if ( a3 && a5 )
  {
    v9 = OpenSCManagerW(0, 0, 1u);
    v10 = v9;
    if ( v9 )
    {
      v12 = SERVICES_MANAGER::ResolveDependencies(this, v9);
      if ( v12 >= 0 )
      {
        v13 = *((_DWORD *)this + 2);
        v14 = 0;
        v15 = 36 * v13;
        if ( v13 )
        {
          v16 = 0;
          while ( 1 )
          {
            if ( v16 > v13 - 1 )
            {
              v12 = -2147023483;
              goto LABEL_35;
            }
            Src = *(void **)(*((_QWORD *)this + 6) + 8LL * v16);
            v17 = Src;
            v18 = OpenServiceW(v10, (LPCWSTR)Src, 0xF01FFu);
            v14 = v18;
            if ( !v18 )
              break;
            if ( !QueryServiceStatus(v18, &ServiceStatus) )
              goto LABEL_29;
            if ( !QueryServiceConfigW(v14, 0, 0, &pcbBytesNeeded) )
            {
              if ( GetLastError() != 122 )
                goto LABEL_29;
              if ( !BUFFER::Resize((BUFFER *)v40, pcbBytesNeeded) )
              {
                v12 = -2147024888;
                goto LABEL_36;
              }
              if ( !QueryServiceConfigW(v14, lpServiceConfig, cbBufSize, &pcbBytesNeeded) )
              {
LABEL_29:
                LastError = GetLastError();
                v12 = LastError;
                if ( LastError > 0 )
                  v12 = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_36;
              }
            }
            v19 = -1;
            do
              ++v19;
            while ( v17[v19] );
            v20 = (unsigned int)(v19 + 1);
            v35 = v19 + 1;
            v21 = -1;
            do
              ++v21;
            while ( lpServiceConfig->lpDisplayName[v21] );
            v33 = v21 + 1;
            if ( v34 >= v15 + 2 * (unsigned __int64)(unsigned int)(v20 + v21 + 1) )
            {
              v22 = v36;
              v23 = 2 * v20;
              v24 = *(_OWORD *)&ServiceStatus.dwWin32ExitCode;
              v25 = 9LL * v16;
              *(_OWORD *)&v36[4 * v25 + 8] = *(_OWORD *)&ServiceStatus.dwServiceType;
              *(_OWORD *)&v22[4 * v25 + 20] = v24;
              memcpy_0(&v22[(unsigned int)v15], Src, 2 * v20);
              v26 = v36;
              v27 = lpServiceConfig;
              v28 = 2LL * v33;
              *(_DWORD *)&v36[36 * v16] = v15;
              memcpy_0(&v26[v23 + (unsigned int)v15], v27->lpDisplayName, v28);
              LODWORD(v20) = v35;
              *(_DWORD *)&v36[36 * v16 + 4] = v15 + 2 * v35;
            }
            ++v16;
            v15 = (unsigned int)v15 + 2 * ((_DWORD)v20 + v33);
            v13 = *((_DWORD *)this + 2);
            if ( v16 >= v13 )
            {
              v5 = v39;
              v12 = 0;
              v8 = v38;
              goto LABEL_24;
            }
          }
          v30 = GetLastError();
          v12 = v30;
          if ( v30 > 0 )
            v12 = (unsigned __int16)v30 | 0x80070000;
        }
        else
        {
LABEL_24:
          if ( v34 >= (unsigned int)v15 )
          {
            *v5 = v13;
          }
          else
          {
            if ( v8 )
              *v8 = v15;
            v12 = -2147024774;
          }
LABEL_35:
          if ( v14 )
LABEL_36:
            CloseServiceHandle(v14);
        }
      }
      CloseServiceHandle(v10);
    }
    else
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
    }
    SERVICES_MANAGER::ResetDependencies(this);
    BUFFER::~BUFFER((BUFFER *)v40);
    return (unsigned int)v12;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v40);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1400042d8  mov     [rsp-8+arg_8], rbx
0x1400042dd  push    rbp
0x1400042de  push    rsi
0x1400042df  push    rdi
0x1400042e0  push    r12
0x1400042e2  push    r13
0x1400042e4  push    r14
0x1400042e6  push    r15
0x1400042e8  lea     rbp, [rsp-1FB0h]
0x1400042f0  mov     eax, 20B0h
0x1400042f5  call    _alloca_probe
0x1400042fa  sub     rsp, rax
0x1400042fd  mov     rax, cs:__security_cookie
0x140004304  xor     rax, rsp
0x140004307  mov     [rbp+1FE0h+var_40], rax
0x14000430e  mov     r15, [rbp+1FE0h+arg_20]
0x140004315  xorps   xmm0, xmm0
0x140004318  mov     rbx, r8
0x14000431b  mov     [rsp+20E0h+var_20B8], edx
0x14000431f  mov     r13, rcx
0x140004322  mov     [rsp+20E0h+var_20A0], r9
0x140004327  movups  xmmword ptr [rbp+1FE0h+ServiceStatus.dwServiceType], xmm0
0x14000432b  xor     esi, esi
0x14000432d  mov     [rsp+20E0h+var_20B0], rbx
0x140004332  xor     edx, edx; Val
0x140004334  mov     [rsp+20E0h+var_2098], r15
0x140004339  mov     r8d, 1FFFh; Size
0x14000433f  mov     [rsp+20E0h+pcbBytesNeeded], esi
0x140004343  lea     rcx, [rbp+1FE0h+var_203F]; void *
0x140004347  mov     rdi, r9
0x14000434a  movups  xmmword ptr [rbp+1FE0h+ServiceStatus.dwWin32ExitCode], xmm0
0x14000434e  call    memset_0
0x140004353  mov     [rbp+1FE0h+var_2040], sil
0x140004357  lea     rax, [rbp+1FE0h+var_2040]
0x14000435b  mov     [rsp+20E0h+lpServiceConfig], rax
0x140004360  mov     [rsp+20E0h+cbBufSize], 2000h
0x140004368  mov     [rsp+20E0h+var_2064], 100h
0x14000436f  test    rbx, rbx
0x140004372  jz      loc_1400045E6
0x140004378  test    r15, r15
0x14000437b  jz      loc_1400045E6
0x140004381  xor     edx, edx; lpDatabaseName
0x140004383  lea     r8d, [rsi+1]; dwDesiredAccess
0x140004387  xor     ecx, ecx; lpMachineName
0x140004389  call    cs:__imp_OpenSCManagerW
0x14000438f  mov     r12, rax
0x140004392  test    rax, rax
0x140004395  jnz     short loc_1400043B5
0x140004397  call    cs:__imp_GetLastError
0x14000439d  mov     ebx, eax
0x14000439f  test    eax, eax
0x1400043a1  jle     loc_1400045CF
0x1400043a7  movzx   ebx, ax
0x1400043aa  or      ebx, 80070000h
0x1400043b0  jmp     loc_1400045CF
0x1400043b5  mov     rdx, r12; struct SC_HANDLE__ *
0x1400043b8  mov     rcx, r13; this
0x1400043bb  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x1400043c0  mov     ebx, eax
0x1400043c2  test    eax, eax
0x1400043c4  js      loc_1400045C6
0x1400043ca  mov     eax, [r13+8]
0x1400043ce  mov     r14, rsi
0x1400043d1  lea     esi, [rax+rax*8]
0x1400043d4  shl     esi, 2
0x1400043d7  test    eax, eax
0x1400043d9  jz      loc_140004565
0x1400043df  xor     edi, edi
0x1400043e1  mov     r15d, edi
0x1400043e4  dec     eax
0x1400043e6  cmp     r15d, eax
0x1400043e9  ja      loc_1400045AE
0x1400043ef  mov     rax, [r13+30h]
0x1400043f3  mov     r8d, 0F01FFh; dwDesiredAccess
0x1400043f9  mov     ecx, r15d
0x1400043fc  mov     rbx, [rax+rcx*8]
0x140004400  mov     rcx, r12; hSCManager
0x140004403  mov     rdx, rbx; lpServiceName
0x140004406  mov     [rsp+20E0h+Src], rbx
0x14000440b  call    cs:__imp_OpenServiceW
0x140004411  mov     r14, rax
0x140004414  test    rax, rax
0x140004417  jz      loc_140004597
0x14000441d  lea     rdx, [rbp+1FE0h+ServiceStatus]; lpServiceStatus
0x140004421  mov     rcx, rax; hService
0x140004424  call    cs:__imp_QueryServiceStatus
0x14000442a  test    eax, eax
0x14000442c  jz      loc_140004580
0x140004432  lea     r9, [rsp+20E0h+pcbBytesNeeded]; pcbBytesNeeded
0x140004437  xor     r8d, r8d; cbBufSize
0x14000443a  xor     edx, edx; lpServiceConfig
0x14000443c  mov     rcx, r14; hService
0x14000443f  call    cs:__imp_QueryServiceConfigW
0x140004445  test    eax, eax
0x140004447  jnz     short loc_14000448F
0x140004449  call    cs:__imp_GetLastError
0x14000444f  cmp     eax, 7Ah ; 'z'
0x140004452  jnz     loc_140004580
0x140004458  mov     edx, [rsp+20E0h+pcbBytesNeeded]
0x14000445c  lea     rcx, [rsp+20E0h+var_2090]
0x140004461  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x140004467  test    al, al
0x140004469  jz      loc_140004579
0x14000446f  mov     r8d, [rsp+20E0h+cbBufSize]; cbBufSize
0x140004474  lea     r9, [rsp+20E0h+pcbBytesNeeded]; pcbBytesNeeded
0x140004479  mov     rdx, [rsp+20E0h+lpServiceConfig]; lpServiceConfig
0x14000447e  mov     rcx, r14; hService
0x140004481  call    cs:__imp_QueryServiceConfigW
0x140004487  test    eax, eax
0x140004489  jz      loc_140004580
0x14000448f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004493  inc     rax
0x140004496  cmp     [rbx+rax*2], di
0x14000449a  jnz     short loc_140004493
0x14000449c  mov     rcx, [rsp+20E0h+lpServiceConfig]
0x1400044a1  lea     r8d, [rax+1]
0x1400044a5  mov     [rsp+20E0h+var_20B4], r8d
0x1400044aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400044ae  mov     rcx, [rcx+38h]
0x1400044b2  inc     rax
0x1400044b5  cmp     [rcx+rax*2], di
0x1400044b9  jnz     short loc_1400044B2
0x1400044bb  inc     eax
0x1400044bd  mov     edx, esi
0x1400044bf  mov     [rsp+20E0h+var_20BC], eax
0x1400044c3  add     eax, r8d
0x1400044c6  lea     rcx, [rsi+rax*2]
0x1400044ca  mov     eax, [rsp+20E0h+var_20B8]
0x1400044ce  cmp     rax, rcx
0x1400044d1  jb      short loc_14000453F
0x1400044d3  mov     rcx, [rsp+20E0h+var_20B0]
0x1400044d8  lea     rbx, [r8+r8]
0x1400044dc  movups  xmm0, xmmword ptr [rbp+1FE0h+ServiceStatus.dwServiceType]
0x1400044e0  mov     eax, r15d
0x1400044e3  mov     r8, rbx; Size
0x1400044e6  movups  xmm1, xmmword ptr [rbp+1FE0h+ServiceStatus.dwWin32ExitCode]
0x1400044ea  lea     rdi, [rax+rax*8]
0x1400044ee  movups  xmmword ptr [rcx+rdi*4+8], xmm0
0x1400044f3  movups  xmmword ptr [rcx+rdi*4+14h], xmm1
0x1400044f8  add     rcx, rdx; void *
0x1400044fb  mov     rdx, [rsp+20E0h+Src]; Src
0x140004500  call    memcpy_0
0x140004505  mov     rdx, [rsp+20E0h+var_20B0]
0x14000450a  mov     rax, [rsp+20E0h+lpServiceConfig]
0x14000450f  mov     r8d, [rsp+20E0h+var_20BC]
0x140004514  mov     ecx, esi
0x140004516  add     r8, r8; Size
0x140004519  add     rcx, rbx
0x14000451c  mov     [rdx+rdi*4], esi
0x14000451f  add     rcx, rdx; void *
0x140004522  mov     rdx, [rax+38h]; Src
0x140004526  call    memcpy_0
0x14000452b  mov     r8d, [rsp+20E0h+var_20B4]
0x140004530  mov     rcx, [rsp+20E0h+var_20B0]
0x140004535  lea     eax, [rsi+r8*2]
0x140004539  mov     [rcx+rdi*4+4], eax
0x14000453d  xor     edi, edi
0x14000453f  mov     eax, [rsp+20E0h+var_20BC]
0x140004543  inc     r15d
0x140004546  add     eax, r8d
0x140004549  lea     esi, [rsi+rax*2]
0x14000454c  mov     eax, [r13+8]
0x140004550  cmp     r15d, eax
0x140004553  jb      loc_1400043E4
0x140004559  mov     r15, [rsp+20E0h+var_2098]
0x14000455e  mov     ebx, edi
0x140004560  mov     rdi, [rsp+20E0h+var_20A0]
0x140004565  cmp     [rsp+20E0h+var_20B8], esi
0x140004569  jnb     short loc_1400045B5
0x14000456b  test    rdi, rdi
0x14000456e  jz      short loc_140004572
0x140004570  mov     [rdi], esi
0x140004572  mov     ebx, 8007007Ah
0x140004577  jmp     short loc_1400045B8
0x140004579  mov     ebx, 80070008h
0x14000457e  jmp     short loc_1400045BD
0x140004580  call    cs:__imp_GetLastError
0x140004586  mov     ebx, eax
0x140004588  test    eax, eax
0x14000458a  jle     short loc_1400045BD
0x14000458c  movzx   ebx, ax
0x14000458f  or      ebx, 80070000h
0x140004595  jmp     short loc_1400045BD
0x140004597  call    cs:__imp_GetLastError
0x14000459d  mov     ebx, eax
0x14000459f  test    eax, eax
0x1400045a1  jle     short loc_1400045C6
0x1400045a3  movzx   ebx, ax
0x1400045a6  or      ebx, 80070000h
0x1400045ac  jmp     short loc_1400045C6
0x1400045ae  mov     ebx, 80070585h
0x1400045b3  jmp     short loc_1400045B8
0x1400045b5  mov     [r15], eax
0x1400045b8  test    r14, r14
0x1400045bb  jz      short loc_1400045C6
0x1400045bd  mov     rcx, r14; hSCObject
0x1400045c0  call    cs:__imp_CloseServiceHandle
0x1400045c6  mov     rcx, r12; hSCObject
0x1400045c9  call    cs:__imp_CloseServiceHandle
0x1400045cf  mov     rcx, r13; this
0x1400045d2  call    ?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ; SERVICES_MANAGER::ResetDependencies(void)
0x1400045d7  lea     rcx, [rsp+20E0h+var_2090]
0x1400045dc  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1400045e2  mov     eax, ebx
0x1400045e4  jmp     short loc_1400045F6
0x1400045e6  lea     rcx, [rsp+20E0h+var_2090]
0x1400045eb  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1400045f1  mov     eax, 80070057h
0x1400045f6  mov     rcx, [rbp+1FE0h+var_40]
0x1400045fd  xor     rcx, rsp; StackCookie
0x140004600  call    __security_check_cookie
0x140004605  mov     rbx, [rsp+20E0h+arg_8]
0x14000460d  add     rsp, 20B0h
0x140004614  pop     r15
0x140004616  pop     r14
0x140004618  pop     r13
0x14000461a  pop     r12
0x14000461c  pop     rdi
0x14000461d  pop     rsi
0x14000461e  pop     rbp
0x14000461f  retn
```
