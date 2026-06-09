# CEfsClient::StartEfsService(ushort const *)

- ea: `0x18000a974`
- end: `0x18000ab2e`
- name: `?StartEfsService@CEfsClient@@KAKPEBG@Z`
- size: `442`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a870`

## callees

- `0x18000a8f0`
- `0x18000a974`
- `0x18000ab34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa48`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000aadf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000aadf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a9ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ab13`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000a9ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000ab13`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000a9b9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000a9b9`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000aa3e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18000aa3e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000a9e1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000a9e1`

## pseudocode

```c
__int64 __fastcall CEfsClient::StartEfsService(unsigned __int64 a1)
{
  bool v2; // cf
  struct SC_HANDLE__ *v3; // rdi
  int v4; // eax
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  DWORD LastError; // ebx
  SC_HANDLE v8; // rax
  unsigned int v9; // r8d
  DWORD v10; // eax
  bool v11; // zf
  bool v12; // cf
  int v13; // eax
  bool v14; // cf
  int v15; // eax
  int v16; // ebp
  unsigned int v17; // esi
  unsigned int v19; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(_WORD *)a1 < 0x2Eu;
  v11 = *(_WORD *)a1 == 46;
  v3 = 0;
  v19 = 0;
  if ( !v11 || (v2 = 0, *(_WORD *)(a1 + 2)) )
    v4 = v2 ? -1 : 1;
  else
    v4 = 0;
  v5 = OpenSCManagerW((LPCWSTR)(a1 & -(__int64)(v4 != 0)), 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v8 = OpenServiceW(v5, L"EFS", 0x14u);
    if ( v8 )
    {
      LastError = 0;
      v3 = v8;
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v6);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    LastError = CEfsClient::GetServiceState(v3, &v19);
    if ( !LastError && v19 != 4 )
    {
      if ( v19 != 1 || StartServiceW(v3, 0, 0) )
      {
        v12 = *(_WORD *)a1 < 0x2Eu;
        if ( *(_WORD *)a1 != 46 || (v12 = 0, *(_WORD *)(a1 + 2)) )
          v13 = v12 ? -1 : 1;
        else
          v13 = 0;
        LastError = CEfsClient::WaitForServiceReady_Notify(v3, v13 != 0 ? 20000 : 60000, v9);
        if ( LastError == 5 )
        {
          v14 = *(_WORD *)a1 < 0x2Eu;
          if ( *(_WORD *)a1 != 46 || (v14 = 0, *(_WORD *)(a1 + 2)) )
            v15 = v14 ? -1 : 1;
          else
            v15 = 0;
          v19 = 0;
          v16 = 0;
          v17 = v15 != 0 ? 100 : 300;
          while ( 1 )
          {
            LastError = CEfsClient::GetServiceState(v3, &v19);
            if ( LastError || v19 == 4 )
              break;
            Sleep(0xC8u);
            if ( ++v16 >= v17 )
            {
              LastError = CEfsClient::GetServiceState(v3, &v19);
              if ( LastError )
                break;
              v11 = v19 == 4;
              v10 = 1062;
              goto LABEL_32;
            }
          }
        }
      }
      else
      {
        v10 = GetLastError();
        v11 = v10 == 1056;
        LastError = 0;
LABEL_32:
        if ( !v11 )
          LastError = v10;
      }
    }
  }
  if ( v3 )
    CloseServiceHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x18000a974  mov     [rsp+arg_0], rbx
0x18000a979  mov     [rsp+arg_10], rbp
0x18000a97e  push    rsi
0x18000a97f  push    rdi
0x18000a980  push    r14
0x18000a982  sub     rsp, 20h
0x18000a986  xor     r14d, r14d
0x18000a989  mov     rsi, rcx
0x18000a98c  cmp     word ptr [rcx], 2Eh ; '.'
0x18000a990  mov     edi, r14d
0x18000a993  mov     [rsp+38h+arg_8], r14d
0x18000a998  jnz     short loc_18000A9A6
0x18000a99a  cmp     [rcx+2], r14w
0x18000a99f  jnz     short loc_18000A9A6
0x18000a9a1  mov     eax, r14d
0x18000a9a4  jmp     short loc_18000A9AB
0x18000a9a6  sbb     eax, eax
0x18000a9a8  or      eax, 1
0x18000a9ab  neg     eax
0x18000a9ad  sbb     rcx, rcx
0x18000a9b0  xor     edx, edx; lpDatabaseName
0x18000a9b2  and     rcx, rsi; lpMachineName
0x18000a9b5  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000a9b9  call    cs:__imp_OpenSCManagerW
0x18000a9bf  mov     rbp, rax
0x18000a9c2  test    rax, rax
0x18000a9c5  jnz     short loc_18000A9D1
0x18000a9c7  call    cs:__imp_GetLastError
0x18000a9cd  mov     ebx, eax
0x18000a9cf  jmp     short loc_18000AA05
0x18000a9d1  mov     r8d, 14h; dwDesiredAccess
0x18000a9d7  lea     rdx, ServiceName; "EFS"
0x18000a9de  mov     rcx, rbp; hSCManager
0x18000a9e1  call    cs:__imp_OpenServiceW
0x18000a9e7  test    rax, rax
0x18000a9ea  jnz     short loc_18000A9F6
0x18000a9ec  call    cs:__imp_GetLastError
0x18000a9f2  mov     ebx, eax
0x18000a9f4  jmp     short loc_18000A9FC
0x18000a9f6  mov     ebx, r14d
0x18000a9f9  mov     rdi, rax
0x18000a9fc  mov     rcx, rbp; hSCObject
0x18000a9ff  call    cs:__imp_CloseServiceHandle
0x18000aa05  test    ebx, ebx
0x18000aa07  jnz     loc_18000AB0B
0x18000aa0d  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x18000aa12  mov     rcx, rdi; struct SC_HANDLE__ *
0x18000aa15  call    ?GetServiceState@CEfsClient@@KAKPEAUSC_HANDLE__@@PEAK@Z; CEfsClient::GetServiceState(SC_HANDLE__ *,ulong *)
0x18000aa1a  mov     ebx, eax
0x18000aa1c  test    eax, eax
0x18000aa1e  jnz     loc_18000AB0B
0x18000aa24  cmp     [rsp+38h+arg_8], 4
0x18000aa29  jz      loc_18000AB0B
0x18000aa2f  cmp     [rsp+38h+arg_8], 1
0x18000aa34  jnz     short loc_18000AA5B
0x18000aa36  xor     r8d, r8d; lpServiceArgVectors
0x18000aa39  xor     edx, edx; dwNumServiceArgs
0x18000aa3b  mov     rcx, rdi; hService
0x18000aa3e  call    cs:__imp_StartServiceW
0x18000aa44  test    eax, eax
0x18000aa46  jnz     short loc_18000AA5B
0x18000aa48  call    cs:__imp_GetLastError
0x18000aa4e  cmp     eax, 420h
0x18000aa53  mov     ebx, r14d
0x18000aa56  jmp     loc_18000AB08
0x18000aa5b  cmp     word ptr [rsi], 2Eh ; '.'
0x18000aa5f  jnz     short loc_18000AA6D
0x18000aa61  cmp     [rsi+2], r14w
0x18000aa66  jnz     short loc_18000AA6D
0x18000aa68  mov     eax, r14d
0x18000aa6b  jmp     short loc_18000AA72
0x18000aa6d  sbb     eax, eax
0x18000aa6f  or      eax, 1
0x18000aa72  neg     eax
0x18000aa74  mov     rcx, rdi; hService
0x18000aa77  sbb     edx, edx
0x18000aa79  and     edx, 0FFFF63C0h
0x18000aa7f  add     edx, 0EA60h; dwMilliseconds
0x18000aa85  call    ?WaitForServiceReady_Notify@CEfsClient@@KAKPEAUSC_HANDLE__@@KK@Z; CEfsClient::WaitForServiceReady_Notify(SC_HANDLE__ *,ulong,ulong)
0x18000aa8a  mov     ebx, eax
0x18000aa8c  cmp     eax, 5
0x18000aa8f  jnz     short loc_18000AB0B
0x18000aa91  cmp     word ptr [rsi], 2Eh ; '.'
0x18000aa95  jnz     short loc_18000AAA3
0x18000aa97  cmp     [rsi+2], r14w
0x18000aa9c  jnz     short loc_18000AAA3
0x18000aa9e  mov     eax, r14d
0x18000aaa1  jmp     short loc_18000AAA8
0x18000aaa3  sbb     eax, eax
0x18000aaa5  or      eax, 1
0x18000aaa8  neg     eax
0x18000aaaa  mov     [rsp+38h+arg_8], r14d
0x18000aaaf  mov     ebp, r14d
0x18000aab2  sbb     esi, esi
0x18000aab4  and     esi, 0FFFFFF38h
0x18000aaba  add     esi, 12Ch
0x18000aac0  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x18000aac5  mov     rcx, rdi; struct SC_HANDLE__ *
0x18000aac8  call    ?GetServiceState@CEfsClient@@KAKPEAUSC_HANDLE__@@PEAK@Z; CEfsClient::GetServiceState(SC_HANDLE__ *,ulong *)
0x18000aacd  mov     ebx, eax
0x18000aacf  test    eax, eax
0x18000aad1  jnz     short loc_18000AB0B
0x18000aad3  cmp     [rsp+38h+arg_8], 4
0x18000aad8  jz      short loc_18000AB0B
0x18000aada  mov     ecx, 0C8h; dwMilliseconds
0x18000aadf  call    cs:__imp_Sleep
0x18000aae5  inc     ebp
0x18000aae7  cmp     ebp, esi
0x18000aae9  jb      short loc_18000AAC0
0x18000aaeb  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x18000aaf0  mov     rcx, rdi; struct SC_HANDLE__ *
0x18000aaf3  call    ?GetServiceState@CEfsClient@@KAKPEAUSC_HANDLE__@@PEAK@Z; CEfsClient::GetServiceState(SC_HANDLE__ *,ulong *)
0x18000aaf8  mov     ebx, eax
0x18000aafa  test    eax, eax
0x18000aafc  jnz     short loc_18000AB0B
0x18000aafe  cmp     [rsp+38h+arg_8], 4
0x18000ab03  mov     eax, 426h
0x18000ab08  cmovnz  ebx, eax
0x18000ab0b  test    rdi, rdi
0x18000ab0e  jz      short loc_18000AB19
0x18000ab10  mov     rcx, rdi; hSCObject
0x18000ab13  call    cs:__imp_CloseServiceHandle
0x18000ab19  mov     rbp, [rsp+38h+arg_10]
0x18000ab1e  mov     eax, ebx
0x18000ab20  mov     rbx, [rsp+38h+arg_0]
0x18000ab25  add     rsp, 20h
0x18000ab29  pop     r14
0x18000ab2b  pop     rdi
0x18000ab2c  pop     rsi
0x18000ab2d  retn
```
