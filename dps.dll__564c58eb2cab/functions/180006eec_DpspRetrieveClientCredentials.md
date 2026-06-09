# DpspRetrieveClientCredentials

- ea: `0x180006eec`
- end: `0x18000719d`
- name: `DpspRetrieveClientCredentials`
- size: `689`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, DWORD, void **, LPVOID TokenInformation, int *, void *TokenHandle, PHANDLE phNewToken)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002510`
- `0x180002a08`
- `0x18000c21c`
- `0x1800146b0`
- `0x1800149dc`
- `0x180014df0`

## callees

- `0x180006eec`
- `0x180009090`
- `0x1800122d4`
- `0x18001246c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006fbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007137`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006fbc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007137`
- `ntdll!RtlNtStatusToDosError` at `0x180006f92`
- `ntdll!RtlNtStatusToDosError` at `0x180006f92`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x180006f76`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x180006f76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007087`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007087`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000716a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000716a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180007056`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180007056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007182`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006fc2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006fd9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006fd9`

## pseudocode

```c
__int64 __fastcall DpspRetrieveClientCredentials(
        RTL_SRWLOCK *a1,
        __int64 a2,
        DWORD a3,
        void **a4,
        LPVOID TokenInformation,
        int *a6,
        void *TokenHandle,
        PHANDLE phNewToken)
{
  signed int v12; // ebx
  RTL_SRWLOCK *v13; // rdi
  PVOID Ptr; // rcx
  NTSTATUS v15; // ebx
  signed int v16; // eax
  HANDLE CurrentThread; // rax
  int v18; // r8d
  signed int LastError; // eax
  int ClientSID; // eax
  signed int v21; // eax
  signed int v22; // eax
  int IsClientAdmin; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  if ( !a1 )
  {
    v12 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspRetrieveClientCredentials",
      1418,
      (int)L"Error = %d",
      87);
    goto LABEL_41;
  }
  if ( !a2 )
  {
    v12 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspRetrieveClientCredentials",
      1419,
      (int)L"Error = %d",
      87);
    goto LABEL_41;
  }
  v13 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1[99].Ptr;
  if ( !Ptr )
  {
    ReleaseSRWLockExclusive(v13);
    v18 = 1439;
    goto LABEL_40;
  }
  v15 = NtAlpcImpersonateClientOfPort(Ptr, a2, 0);
  if ( v15 < 0 )
  {
    ReleaseSRWLockExclusive(v13);
    v16 = RtlNtStatusToDosError(v15);
    v12 = v16;
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    if ( v12 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (int)L"DpspRetrieveClientCredentials",
        1433,
        (int)L"Error = %d",
        v12);
      goto LABEL_41;
    }
  }
  ReleaseSRWLockExclusive(v13);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a3, 0, &TokenHandle) )
  {
    v12 = 0;
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (int)L"DpspRetrieveClientCredentials",
        1452,
        (int)L"Error = %d",
        v12);
      goto LABEL_41;
    }
  }
  if ( !TokenHandle )
  {
    v18 = 1455;
LABEL_40:
    v12 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspRetrieveClientCredentials",
      v18,
      (int)L"Error = %d",
      5);
    goto LABEL_41;
  }
  if ( phNewToken )
  {
    if ( DuplicateTokenEx(TokenHandle, a3, 0, SecurityImpersonation, (TOKEN_TYPE)(((a3 & 1) == 0) + 1), phNewToken) )
    {
      v12 = 0;
    }
    else
    {
      v21 = GetLastError();
      v12 = v21;
      if ( v21 > 0 )
        v12 = (unsigned __int16)v21 | 0x80070000;
      if ( v12 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientCredentials",
          1470,
          (int)L"Error = %d",
          v12);
        goto LABEL_41;
      }
    }
  }
  if ( TokenInformation )
  {
    if ( GetTokenInformation(TokenHandle, TokenSessionId, TokenInformation, 8u, &ReturnLength) )
    {
      v12 = 0;
    }
    else
    {
      v22 = GetLastError();
      v12 = v22;
      if ( v22 > 0 )
        v12 = (unsigned __int16)v22 | 0x80070000;
      if ( v12 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveClientCredentials",
          1483,
          (int)L"Error = %d",
          v12);
        goto LABEL_41;
      }
    }
  }
  if ( a4 && (ClientSID = DpspRetrieveClientSID(TokenHandle, a4), v12 = ClientSID, ClientSID < 0) )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspRetrieveClientCredentials",
      1492,
      (int)L"Error = %d",
      ClientSID);
  }
  else if ( a6 )
  {
    IsClientAdmin = DpspIsClientAdmin(TokenHandle, a6);
    v12 = IsClientAdmin;
    if ( IsClientAdmin < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (int)L"DpspRetrieveClientCredentials",
        1501,
        (int)L"Error = %d",
        IsClientAdmin);
  }
LABEL_41:
  RevertToSelf();
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006eec  mov     rax, rsp
0x180006eef  mov     [rax+10h], rbx
0x180006ef3  mov     [rax+18h], rbp
0x180006ef7  push    rsi
0x180006ef8  push    rdi
0x180006ef9  push    r14
0x180006efb  sub     rsp, 30h
0x180006eff  mov     qword ptr [rax+38h], 0
0x180006f07  mov     rbp, r9
0x180006f0a  mov     dword ptr [rax+8], 0
0x180006f11  mov     r14d, r8d
0x180006f14  mov     rsi, rdx
0x180006f17  mov     rbx, rcx
0x180006f1a  test    rcx, rcx
0x180006f1d  jnz     short loc_180006F36
0x180006f1f  mov     ebx, 80070057h
0x180006f24  mov     dword ptr [rax-28h], 57h ; 'W'
0x180006f2b  mov     r8d, 58Ah
0x180006f31  jmp     loc_180007150
0x180006f36  test    rsi, rsi
0x180006f39  jnz     short loc_180006F53
0x180006f3b  mov     ebx, 80070057h
0x180006f40  mov     [rsp+48h+TokenType], 57h ; 'W'
0x180006f48  mov     r8d, 58Bh
0x180006f4e  jmp     loc_180007150
0x180006f53  lea     rdi, [rcx+10h]
0x180006f57  mov     rcx, rdi; SRWLock
0x180006f5a  call    cs:__imp_AcquireSRWLockExclusive
0x180006f60  mov     rcx, [rbx+318h]
0x180006f67  test    rcx, rcx
0x180006f6a  jz      loc_180007134
0x180006f70  xor     r8d, r8d
0x180006f73  mov     rdx, rsi
0x180006f76  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x180006f7c  mov     ebx, eax
0x180006f7e  mov     esi, 80070000h
0x180006f83  test    eax, eax
0x180006f85  jns     short loc_180006FB9
0x180006f87  mov     rcx, rdi; SRWLock
0x180006f8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006f90  mov     ecx, ebx; Status
0x180006f92  call    cs:__imp_RtlNtStatusToDosError
0x180006f98  mov     ebx, eax
0x180006f9a  test    eax, eax
0x180006f9c  jle     short loc_180006FA3
0x180006f9e  movzx   ebx, ax
0x180006fa1  or      ebx, esi
0x180006fa3  test    ebx, ebx
0x180006fa5  jns     short loc_180006FB9
0x180006fa7  movzx   eax, bx
0x180006faa  mov     r8d, 599h
0x180006fb0  mov     [rsp+48h+TokenType], eax
0x180006fb4  jmp     loc_180007150
0x180006fb9  mov     rcx, rdi; SRWLock
0x180006fbc  call    cs:__imp_ReleaseSRWLockExclusive
0x180006fc2  call    cs:__imp_GetCurrentThread
0x180006fc8  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180006fd0  xor     r8d, r8d; OpenAsSelf
0x180006fd3  mov     rcx, rax; ThreadHandle
0x180006fd6  mov     edx, r14d; DesiredAccess
0x180006fd9  call    cs:__imp_OpenThreadToken
0x180006fdf  test    eax, eax
0x180006fe1  jz      short loc_180006FFB
0x180006fe3  xor     ebx, ebx
0x180006fe5  cmp     [rsp+48h+TokenHandle], 0
0x180006fee  jnz     short loc_180007022
0x180006ff0  mov     r8d, 5AFh
0x180006ff6  jmp     loc_180007143
0x180006ffb  call    cs:__imp_GetLastError
0x180007001  mov     ebx, eax
0x180007003  test    eax, eax
0x180007005  jle     short loc_18000700C
0x180007007  movzx   ebx, ax
0x18000700a  or      ebx, esi
0x18000700c  test    ebx, ebx
0x18000700e  jns     short loc_180006FE5
0x180007010  movzx   eax, bx
0x180007013  mov     r8d, 5ACh
0x180007019  mov     [rsp+48h+TokenType], eax
0x18000701d  jmp     loc_180007150
0x180007022  mov     rcx, [rsp+48h+arg_38]
0x18000702a  test    rcx, rcx
0x18000702d  jz      short loc_180007062
0x18000702f  mov     [rsp+48h+phNewToken], rcx; phNewToken
0x180007034  mov     eax, r14d
0x180007037  mov     rcx, [rsp+48h+TokenHandle]; hExistingToken
0x18000703f  not     eax
0x180007041  and     eax, 1
0x180007044  mov     r9d, 2; ImpersonationLevel
0x18000704a  inc     eax
0x18000704c  xor     r8d, r8d; lpTokenAttributes
0x18000704f  mov     edx, r14d; dwDesiredAccess
0x180007052  mov     [rsp+48h+TokenType], eax; TokenType
0x180007056  call    cs:__imp_DuplicateTokenEx
0x18000705c  test    eax, eax
0x18000705e  jz      short loc_1800070C0
0x180007060  xor     ebx, ebx
0x180007062  mov     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180007067  test    r8, r8
0x18000706a  jz      short loc_180007093
0x18000706c  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180007074  lea     rax, [rsp+48h+ReturnLength]
0x180007079  mov     edx, 0Ch; TokenInformationClass
0x18000707e  mov     qword ptr [rsp+48h+TokenType], rax; ReturnLength
0x180007083  lea     r9d, [rdx-4]; TokenInformationLength
0x180007087  call    cs:__imp_GetTokenInformation
0x18000708d  test    eax, eax
0x18000708f  jz      short loc_1800070E4
0x180007091  xor     ebx, ebx
0x180007093  test    rbp, rbp
0x180007096  jz      short loc_180007108
0x180007098  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800070a0  mov     rdx, rbp; void **
0x1800070a3  call    ?DpspRetrieveClientSID@@YAJPEAXPEAPEAX@Z; DpspRetrieveClientSID(void *,void * *)
0x1800070a8  mov     ebx, eax
0x1800070aa  test    eax, eax
0x1800070ac  jns     short loc_180007108
0x1800070ae  movzx   ecx, ax
0x1800070b1  mov     r8d, 5D4h
0x1800070b7  mov     [rsp+48h+TokenType], ecx
0x1800070bb  jmp     loc_180007150
0x1800070c0  call    cs:__imp_GetLastError
0x1800070c6  mov     ebx, eax
0x1800070c8  test    eax, eax
0x1800070ca  jle     short loc_1800070D1
0x1800070cc  movzx   ebx, ax
0x1800070cf  or      ebx, esi
0x1800070d1  test    ebx, ebx
0x1800070d3  jns     short loc_180007062
0x1800070d5  movzx   eax, bx
0x1800070d8  mov     r8d, 5BEh
0x1800070de  mov     [rsp+48h+TokenType], eax
0x1800070e2  jmp     short loc_180007150
0x1800070e4  call    cs:__imp_GetLastError
0x1800070ea  mov     ebx, eax
0x1800070ec  test    eax, eax
0x1800070ee  jle     short loc_1800070F5
0x1800070f0  movzx   ebx, ax
0x1800070f3  or      ebx, esi
0x1800070f5  test    ebx, ebx
0x1800070f7  jns     short loc_180007093
0x1800070f9  movzx   eax, bx
0x1800070fc  mov     r8d, 5CBh
0x180007102  mov     [rsp+48h+TokenType], eax
0x180007106  jmp     short loc_180007150
0x180007108  mov     rdx, [rsp+48h+arg_28]; int *
0x18000710d  test    rdx, rdx
0x180007110  jz      short loc_18000716A
0x180007112  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000711a  call    ?DpspIsClientAdmin@@YAJPEAXPEAH@Z; DpspIsClientAdmin(void *,int *)
0x18000711f  mov     ebx, eax
0x180007121  test    eax, eax
0x180007123  jns     short loc_18000716A
0x180007125  movzx   eax, ax
0x180007128  mov     r8d, 5DDh
0x18000712e  mov     [rsp+48h+TokenType], eax
0x180007132  jmp     short loc_180007150
0x180007134  mov     rcx, rdi; SRWLock
0x180007137  call    cs:__imp_ReleaseSRWLockExclusive
0x18000713d  mov     r8d, 59Fh; int
0x180007143  mov     [rsp+48h+TokenType], 4005h; Args
0x18000714b  mov     ebx, 80004005h
0x180007150  lea     r9, aErrorD; "Error = %d"
0x180007157  lea     rdx, aDpspretrievecl_0; "DpspRetrieveClientCredentials"
0x18000715e  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007165  call    WdipTraceError
0x18000716a  call    cs:__imp_RevertToSelf
0x180007170  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180007178  lea     rax, [rcx-1]
0x18000717c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007180  ja      short loc_180007188
0x180007182  call    cs:__imp_CloseHandle
0x180007188  mov     rbp, [rsp+48h+arg_10]
0x18000718d  mov     eax, ebx
0x18000718f  mov     rbx, [rsp+48h+arg_8]
0x180007194  add     rsp, 30h
0x180007198  pop     r14
0x18000719a  pop     rdi
0x18000719b  pop     rsi
0x18000719c  retn
```
