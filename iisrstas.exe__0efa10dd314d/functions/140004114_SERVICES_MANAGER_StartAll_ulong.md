# SERVICES_MANAGER::StartAll(ulong *)

- ea: `0x140004114`
- end: `0x1400042d2`
- name: `?StartAll@SERVICES_MANAGER@@QEAAJPEAK@Z`
- size: `446`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003110`

## callees

- `0x140003cd8`
- `0x140003d1c`
- `0x140004114`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000422f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000422f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000425d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000427d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000425d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000427d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000423e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140004275`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000429c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000423e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140004275`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000429c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140004154`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140004154`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400041f4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400041f4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400041c1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400041c1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400041db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140004204`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400041db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x140004204`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::StartAll(SERVICES_MANAGER *this, unsigned int *a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r15
  signed int v6; // eax
  signed int v7; // ebx
  unsigned int v8; // edi
  DWORD v9; // r14d
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rsi
  signed int LastError; // eax
  signed int v13; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    v7 = SERVICES_MANAGER::ResolveDependencies(this, v4);
    if ( v7 >= 0 )
    {
      v8 = *((_DWORD *)this + 2);
      v9 = 1000;
LABEL_20:
      if ( (--v8 & 0x80000000) == 0 )
      {
        if ( v8 > *((_DWORD *)this + 2) - 1 )
        {
          v7 = -2147023483;
        }
        else
        {
          v10 = OpenServiceW(v5, *(LPCWSTR *)(*((_QWORD *)this + 6) + 8LL * v8), 0xF01FFu);
          v11 = v10;
          if ( v10 )
          {
            if ( QueryServiceStatus(v10, &ServiceStatus) )
            {
              if ( ServiceStatus.dwCurrentState != 4 )
                StartServiceW(v11, 0, 0);
              v7 = 0;
              while ( QueryServiceStatus(v11, &ServiceStatus) )
              {
                if ( ServiceStatus.dwCurrentState == 1 )
                {
                  v7 = -2147023834;
                  goto LABEL_26;
                }
                if ( ServiceStatus.dwCurrentState == 4 )
                {
                  CloseServiceHandle(v11);
                  goto LABEL_20;
                }
                if ( *a2 < v9 )
                {
                  if ( !*a2 )
                  {
                    v7 = -2147023843;
                    goto LABEL_26;
                  }
                  v9 = *a2;
                }
                Sleep(v9);
                *a2 -= v9;
              }
            }
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
            CloseServiceHandle(v11);
          }
          else
          {
            v13 = GetLastError();
            v7 = v13;
            if ( v13 > 0 )
              v7 = (unsigned __int16)v13 | 0x80070000;
          }
        }
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140004114  mov     [rsp+arg_10], rbx
0x140004119  mov     [rsp+arg_18], rbp
0x14000411e  push    rsi
0x14000411f  push    rdi
0x140004120  push    r12
0x140004122  push    r14
0x140004124  push    r15
0x140004126  sub     rsp, 50h
0x14000412a  mov     rax, cs:__security_cookie
0x140004131  xor     rax, rsp
0x140004134  mov     [rsp+78h+var_38], rax
0x140004139  xorps   xmm0, xmm0
0x14000413c  mov     r12, rdx
0x14000413f  xor     edx, edx; lpDatabaseName
0x140004141  mov     rbp, rcx
0x140004144  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x140004149  xor     ecx, ecx; lpMachineName
0x14000414b  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x140004150  lea     r8d, [rdx+1]; dwDesiredAccess
0x140004154  call    cs:__imp_OpenSCManagerW
0x14000415a  mov     r15, rax
0x14000415d  test    rax, rax
0x140004160  jnz     short loc_140004180
0x140004162  call    cs:__imp_GetLastError
0x140004168  mov     ebx, eax
0x14000416a  test    eax, eax
0x14000416c  jle     loc_1400042A2
0x140004172  movzx   ebx, ax
0x140004175  or      ebx, 80070000h
0x14000417b  jmp     loc_1400042A2
0x140004180  mov     rdx, r15; struct SC_HANDLE__ *
0x140004183  mov     rcx, rbp; this
0x140004186  call    ?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z; SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)
0x14000418b  mov     ebx, eax
0x14000418d  test    eax, eax
0x14000418f  js      loc_140004299
0x140004195  mov     edi, [rbp+8]
0x140004198  mov     r14d, 3E8h
0x14000419e  jmp     loc_140004244
0x1400041a3  mov     eax, [rbp+8]
0x1400041a6  dec     eax
0x1400041a8  cmp     edi, eax
0x1400041aa  ja      loc_140004294
0x1400041b0  mov     rdx, [rbp+30h]
0x1400041b4  mov     r8d, 0F01FFh; dwDesiredAccess
0x1400041ba  mov     rcx, r15; hSCManager
0x1400041bd  mov     rdx, [rdx+rdi*8]; lpServiceName
0x1400041c1  call    cs:__imp_OpenServiceW
0x1400041c7  mov     rsi, rax
0x1400041ca  test    rax, rax
0x1400041cd  jz      loc_14000427D
0x1400041d3  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1400041d8  mov     rcx, rax; hService
0x1400041db  call    cs:__imp_QueryServiceStatus
0x1400041e1  test    eax, eax
0x1400041e3  jz      short loc_14000425D
0x1400041e5  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x1400041ea  jz      short loc_1400041FA
0x1400041ec  xor     r8d, r8d; lpServiceArgVectors
0x1400041ef  xor     edx, edx; dwNumServiceArgs
0x1400041f1  mov     rcx, rsi; hService
0x1400041f4  call    cs:__imp_StartServiceW
0x1400041fa  xor     ebx, ebx
0x1400041fc  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x140004201  mov     rcx, rsi; hService
0x140004204  call    cs:__imp_QueryServiceStatus
0x14000420a  test    eax, eax
0x14000420c  jz      short loc_14000425D
0x14000420e  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 1
0x140004213  jz      short loc_140004256
0x140004215  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x14000421a  jz      short loc_14000423B
0x14000421c  cmp     [r12], r14d
0x140004220  jnb     short loc_14000422C
0x140004222  cmp     [r12], ebx
0x140004226  jz      short loc_14000424F
0x140004228  mov     r14d, [r12]
0x14000422c  mov     ecx, r14d; dwMilliseconds
0x14000422f  call    cs:__imp_Sleep
0x140004235  sub     [r12], r14d
0x140004239  jmp     short loc_1400041FC
0x14000423b  mov     rcx, rsi; hSCObject
0x14000423e  call    cs:__imp_CloseServiceHandle
0x140004244  sub     edi, 1
0x140004247  jns     loc_1400041A3
0x14000424d  jmp     short loc_140004299
0x14000424f  mov     ebx, 8007041Dh
0x140004254  jmp     short loc_140004272
0x140004256  mov     ebx, 80070426h
0x14000425b  jmp     short loc_140004272
0x14000425d  call    cs:__imp_GetLastError
0x140004263  mov     ebx, eax
0x140004265  test    eax, eax
0x140004267  jle     short loc_140004272
0x140004269  movzx   ebx, ax
0x14000426c  or      ebx, 80070000h
0x140004272  mov     rcx, rsi; hSCObject
0x140004275  call    cs:__imp_CloseServiceHandle
0x14000427b  jmp     short loc_140004299
0x14000427d  call    cs:__imp_GetLastError
0x140004283  mov     ebx, eax
0x140004285  test    eax, eax
0x140004287  jle     short loc_140004299
0x140004289  movzx   ebx, ax
0x14000428c  or      ebx, 80070000h
0x140004292  jmp     short loc_140004299
0x140004294  mov     ebx, 80070585h
0x140004299  mov     rcx, r15; hSCObject
0x14000429c  call    cs:__imp_CloseServiceHandle
0x1400042a2  mov     rcx, rbp; this
0x1400042a5  call    ?ResetDependencies@SERVICES_MANAGER@@AEAAJXZ; SERVICES_MANAGER::ResetDependencies(void)
0x1400042aa  mov     eax, ebx
0x1400042ac  mov     rcx, [rsp+78h+var_38]
0x1400042b1  xor     rcx, rsp; StackCookie
0x1400042b4  call    __security_check_cookie
0x1400042b9  lea     r11, [rsp+78h+var_28]
0x1400042be  mov     rbx, [r11+40h]
0x1400042c2  mov     rbp, [r11+48h]
0x1400042c6  mov     rsp, r11
0x1400042c9  pop     r15
0x1400042cb  pop     r14
0x1400042cd  pop     r12
0x1400042cf  pop     rdi
0x1400042d0  pop     rsi
0x1400042d1  retn
```
