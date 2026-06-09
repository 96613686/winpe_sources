# SERVICES_MANAGER::StopAll(ulong *)

- ea: `0x140004628`
- end: `0x1400048a6`
- name: `?StopAll@SERVICES_MANAGER@@QEAAJPEAK@Z`
- size: `638`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400032a0`

## callees

- `0x140003cd8`
- `0x140003d1c`
- `0x140003fec`
- `0x140004628`
- `0x14000548e`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400047fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400047fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000469e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000481c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000469e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000481c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000484f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140004865`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000484f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140004865`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000468c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000468c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000472b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000472b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x140004877`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x140004877`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1400046db`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1400046db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14000476d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14000476d`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::StopAll(SERVICES_MANAGER *this, unsigned int *a2)
{
  unsigned int *v2; // r15
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r12
  signed int v6; // eax
  signed int v7; // ebx
  _QWORD *v8; // r14
  __int64 v9; // rdi
  SC_HANDLE v10; // rax
  int v11; // eax
  DWORD v12; // r12d
  int v13; // r13d
  __int64 v14; // rdi
  SC_HANDLE v15; // rcx
  unsigned int v16; // edx
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  int v20; // edi
  SC_HANDLE v21; // rcx
  SC_HANDLE v23; // [rsp+20h] [rbp-49h]
  _QWORD v25[4]; // [rsp+30h] [rbp-39h] BYREF
  void *v26; // [rsp+50h] [rbp-19h]
  int v27; // [rsp+58h] [rbp-11h]
  __int16 v28; // [rsp+5Ch] [rbp-Dh]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-9h] BYREF

  v2 = a2;
  v25[0] = 0;
  v27 = 32;
  v28 = 256;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v26 = v25;
  v4 = OpenSCManagerW(0, 0, 1u);
  v23 = v4;
  v5 = v4;
  if ( v4 )
  {
    v7 = SERVICES_MANAGER::ResolveDependencies(this, v4);
    if ( v7 >= 0 )
    {
      if ( BUFFER::Resize((BUFFER *)v25, 8 * *((_DWORD *)this + 2)) )
      {
        v8 = v26;
        memset_0(v26, 0, 8LL * *((unsigned int *)this + 2));
        v9 = (unsigned int)(*((_DWORD *)this + 2) - 1);
        if ( (int)v9 < 0 )
        {
LABEL_12:
          v11 = *((_DWORD *)this + 2);
          if ( v11 )
          {
            v12 = 1000;
            do
            {
              v13 = 0;
              v14 = (unsigned int)(v11 - 1);
              if ( (int)v14 >= 0 )
              {
                while ( 1 )
                {
                  v15 = (SC_HANDLE)v8[v14];
                  if ( v15 )
                  {
                    if ( !QueryServiceStatus(v15, &ServiceStatus) )
                    {
                      LastError = GetLastError();
                      v7 = LastError;
                      if ( LastError > 0 )
                        v7 = (unsigned __int16)LastError | 0x80070000;
                      goto LABEL_37;
                    }
                    if ( ServiceStatus.dwCurrentState == 1 )
                    {
                      ++v13;
                    }
                    else if ( ServiceStatus.dwCurrentState != 3 )
                    {
                      v18 = SendControlToService((struct SC_HANDLE__ *)v8[v14], v16, a2);
                      v7 = v18;
                      if ( v18 == -2147023843 )
                      {
                        v8[v14] = 0;
                        goto LABEL_37;
                      }
                      if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2147023845 )
                        goto LABEL_37;
                    }
                  }
                  v14 = (unsigned int)(v14 - 1);
                  if ( (int)v14 < 0 )
                  {
                    v2 = a2;
                    break;
                  }
                }
              }
              if ( *v2 < v12 )
              {
                if ( !*v2 )
                {
                  v7 = -2147023843;
                  break;
                }
                v12 = *v2;
              }
              Sleep(v12);
              *v2 -= v12;
              v11 = *((_DWORD *)this + 2);
            }
            while ( v13 != v11 );
LABEL_37:
            v5 = v23;
          }
        }
        else
        {
          while ( 1 )
          {
            if ( (unsigned int)v9 > *((_DWORD *)this + 2) - 1 )
            {
              v7 = -2147023483;
              goto LABEL_38;
            }
            v10 = OpenServiceW(v5, *(LPCWSTR *)(*((_QWORD *)this + 6) + 8 * v9), 0xF01FFu);
            v8[v9] = v10;
            if ( !v10 )
              break;
            v9 = (unsigned int)(v9 - 1);
            if ( (int)v9 < 0 )
            {
              v7 = 0;
              goto LABEL_12;
            }
          }
          v17 = GetLastError();
          v7 = v17;
          if ( v17 > 0 )
            v7 = (unsigned __int16)v17 | 0x80070000;
        }
LABEL_38:
        if ( v8 )
        {
          v20 = *((_DWORD *)this + 2);
          while ( --v20 >= 0 )
          {
            v21 = (SC_HANDLE)v8[v20];
            if ( v21 )
            {
              CloseServiceHandle(v21);
              v8[v20] = 0;
            }
          }
        }
      }
      else
      {
        v7 = -2147024888;
      }
    }
    CloseServiceHandle(v5);
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  SERVICES_MANAGER::ResetDependencies(this);
  BUFFER::~BUFFER((BUFFER *)v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140004628  mov     [rsp-8+arg_10], rbx
0x14000462d  push    rbp
0x14000462e  push    rsi
0x14000462f  push    rdi
0x140004630  push    r12
0x140004632  push    r13
0x140004634  push    r14
0x140004636  push    r15
0x140004638  lea     rbp, [rsp-27h]
0x14000463d  sub     rsp, 90h
0x140004644  mov     rax, cs:__security_cookie
0x14000464b  xor     rax, rsp
0x14000464e  mov     [rbp+57h+var_40], rax
0x140004652  xorps   xmm0, xmm0
0x140004655  mov     [rbp+57h+var_98], rdx
0x140004659  mov     r15, rdx
0x14000465c  mov     [rbp+57h+var_90], 0
0x140004664  xor     edx, edx; lpDatabaseName
0x140004666  mov     [rbp+57h+var_68], 20h ; ' '
0x14000466d  mov     rsi, rcx
0x140004670  mov     [rbp+57h+var_64], 100h
0x140004676  lea     rax, [rbp+57h+var_90]
0x14000467a  xor     ecx, ecx; lpMachineName
0x14000467c  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x140004680  lea     r8d, [rdx+1]; dwDesiredAccess
0x140004684  mov     [rbp+57h+var_70], rax
0x140004688  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x14000468c  call    cs:__imp_OpenSCManagerW
0x140004692  mov     [rbp+57h+var_A0], rax
0x140004696  mov     r12, rax
0x140004699  test    rax, rax
0x14000469c  jnz     short loc_1400046BC
0x14000469e  call    cs:__imp_GetLastError
0x1400046a4  mov     ebx, eax
0x1400046a6  test    eax, eax
0x1400046a8  jle     loc_14000486B
0x1400046ae  movzx   ebx, ax
0x1400046b1  or      ebx, 80070000h
0x1400046b7  jmp     loc_14000486B
0x1400046bc  mov     rdx, r12; struct SC_HANDLE__ *
0x1400046bf  mov     rcx, rsi; this
0x1400046c2  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x1400046c7  mov     ebx, eax
0x1400046c9  test    eax, eax
0x1400046cb  js      loc_140004862
0x1400046d1  mov     edx, [rsi+8]
0x1400046d4  lea     rcx, [rbp+57h+var_90]
0x1400046d8  shl     edx, 3
0x1400046db  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1400046e1  test    al, al
0x1400046e3  jnz     short loc_1400046EF
0x1400046e5  mov     ebx, 80070008h
0x1400046ea  jmp     loc_140004862
0x1400046ef  mov     r14, [rbp+57h+var_70]
0x1400046f3  xor     edx, edx; Val
0x1400046f5  mov     r8d, [rsi+8]
0x1400046f9  mov     rcx, r14; void *
0x1400046fc  shl     r8, 3; Size
0x140004700  call    memset_0
0x140004705  mov     edi, [rsi+8]
0x140004708  sub     edi, 1
0x14000470b  js      short loc_140004741
0x14000470d  mov     eax, [rsi+8]
0x140004710  dec     eax
0x140004712  cmp     edi, eax
0x140004714  ja      loc_1400047A4
0x14000471a  mov     rdx, [rsi+30h]
0x14000471e  mov     r8d, 0F01FFh; dwDesiredAccess
0x140004724  mov     rcx, r12; hSCManager
0x140004727  mov     rdx, [rdx+rdi*8]; lpServiceName
0x14000472b  call    cs:__imp_OpenServiceW
0x140004731  mov     [r14+rdi*8], rax
0x140004735  test    rax, rax
0x140004738  jz      short loc_140004786
0x14000473a  sub     edi, 1
0x14000473d  jns     short loc_14000470D
0x14000473f  xor     ebx, ebx
0x140004741  mov     eax, [rsi+8]
0x140004744  test    eax, eax
0x140004746  jz      loc_14000483C
0x14000474c  mov     r12d, 3E8h
0x140004752  xor     r13d, r13d
0x140004755  lea     edi, [rax-1]
0x140004758  test    edi, edi
0x14000475a  js      loc_1400047EA
0x140004760  mov     rcx, [r14+rdi*8]; hService
0x140004764  test    rcx, rcx
0x140004767  jz      short loc_1400047DD
0x140004769  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x14000476d  call    cs:__imp_QueryServiceStatus
0x140004773  test    eax, eax
0x140004775  jz      loc_14000481C
0x14000477b  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x14000477f  jnz     short loc_1400047AE
0x140004781  inc     r13d
0x140004784  jmp     short loc_1400047DD
0x140004786  call    cs:__imp_GetLastError
0x14000478c  mov     ebx, eax
0x14000478e  test    eax, eax
0x140004790  jle     loc_14000483C
0x140004796  movzx   ebx, ax
0x140004799  or      ebx, 80070000h
0x14000479f  jmp     loc_14000483C
0x1400047a4  mov     ebx, 80070585h
0x1400047a9  jmp     loc_14000483C
0x1400047ae  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 3
0x1400047b2  jz      short loc_1400047DD
0x1400047b4  mov     r8, [rbp+57h+var_98]; unsigned int *
0x1400047b8  mov     rcx, [r14+rdi*8]; struct SC_HANDLE__ *
0x1400047bc  call    ?SendControlToService@@YAJPEAUSC_HANDLE__@@KPEAK@Z; SendControlToService(SC_HANDLE__ *,ulong,ulong *)
0x1400047c1  mov     ebx, eax
0x1400047c3  cmp     eax, 8007041Dh
0x1400047c8  jz      short loc_140004812
0x1400047ca  mov     ecx, 80000000h
0x1400047cf  add     eax, ecx
0x1400047d1  test    ecx, eax
0x1400047d3  jnz     short loc_1400047DD
0x1400047d5  cmp     ebx, 8007041Bh
0x1400047db  jnz     short loc_140004838
0x1400047dd  sub     edi, 1
0x1400047e0  jns     loc_140004760
0x1400047e6  mov     r15, [rbp+57h+var_98]
0x1400047ea  cmp     [r15], r12d
0x1400047ed  jnb     short loc_1400047F8
0x1400047ef  cmp     dword ptr [r15], 0
0x1400047f3  jz      short loc_140004833
0x1400047f5  mov     r12d, [r15]
0x1400047f8  mov     ecx, r12d; dwMilliseconds
0x1400047fb  call    cs:__imp_Sleep
0x140004801  sub     [r15], r12d
0x140004804  mov     eax, [rsi+8]
0x140004807  cmp     r13d, eax
0x14000480a  jnz     loc_140004752
0x140004810  jmp     short loc_140004838
0x140004812  mov     qword ptr [r14+rdi*8], 0
0x14000481a  jmp     short loc_140004838
0x14000481c  call    cs:__imp_GetLastError
0x140004822  mov     ebx, eax
0x140004824  test    eax, eax
0x140004826  jle     short loc_140004838
0x140004828  movzx   ebx, ax
0x14000482b  or      ebx, 80070000h
0x140004831  jmp     short loc_140004838
0x140004833  mov     ebx, 8007041Dh
0x140004838  mov     r12, [rbp+57h+var_A0]
0x14000483c  test    r14, r14
0x14000483f  jz      short loc_140004862
0x140004841  mov     edi, [rsi+8]
0x140004844  jmp     short loc_14000485D
0x140004846  mov     rcx, [r14+rdi*8]; hSCObject
0x14000484a  test    rcx, rcx
0x14000484d  jz      short loc_14000485D
0x14000484f  call    cs:__imp_CloseServiceHandle
0x140004855  mov     qword ptr [r14+rdi*8], 0
0x14000485d  sub     edi, 1
0x140004860  jns     short loc_140004846
0x140004862  mov     rcx, r12; hSCObject
0x140004865  call    cs:__imp_CloseServiceHandle
0x14000486b  mov     rcx, rsi; this
0x14000486e  call    ?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ; SERVICES_MANAGER::ResetDependencies(void)
0x140004873  lea     rcx, [rbp+57h+var_90]
0x140004877  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x14000487d  mov     eax, ebx
0x14000487f  mov     rcx, [rbp+57h+var_40]
0x140004883  xor     rcx, rsp; StackCookie
0x140004886  call    __security_check_cookie
0x14000488b  mov     rbx, [rsp+0C0h+arg_10]
0x140004893  add     rsp, 90h
0x14000489a  pop     r15
0x14000489c  pop     r14
0x14000489e  pop     r13
0x1400048a0  pop     r12
0x1400048a2  pop     rdi
0x1400048a3  pop     rsi
0x1400048a4  pop     rbp
0x1400048a5  retn
```
