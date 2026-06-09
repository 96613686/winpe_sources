# StartAndWaitForService

- ea: `0x180003518`
- end: `0x18000366e`
- name: `StartAndWaitForService`
- size: `342`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800031a8`

## callees

- `0x180001200`
- `0x180002350`
- `0x180003518`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800035c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800035d0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000364d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000365b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800035c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800035d0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000364d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000365b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000352d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000352d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000354d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000354d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180003575`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180003575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000360b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000360b`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000359c`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18000359c`

## string_xrefs

- `0x180003636`: `StartAndWaitForService`

## pseudocode

```c
__int64 __fastcall StartAndWaitForService(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int *a6)
{
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbx
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rsi
  int v11; // ebp
  unsigned __int8 i; // r14
  int v13; // eax
  int *v14; // rax
  unsigned int v16; // esi
  signed int LastError; // eax
  DSLogger *v18; // rax

  v6 = 0;
  v7 = OpenSCManagerW(0, 0, 1u);
  v8 = v7;
  if ( !v7 )
  {
    v8 = 0;
LABEL_20:
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_22;
  }
  v9 = OpenServiceW(v7, L"dssvc", 0x14u);
  v10 = v9;
  if ( !v9 )
    goto LABEL_20;
  v11 = 0;
  v6 = v9;
  for ( i = 0; ; ++i )
  {
    if ( i >= 2u )
      goto LABEL_11;
    if ( !StartServiceW(v10, 0, 0) && GetLastError() != 1056 )
      goto LABEL_20;
    v13 = WaitServiceState(v10, 9, 30000);
    if ( !v13 )
      break;
    if ( v13 == 4 )
    {
      v11 = 1;
LABEL_11:
      v14 = a6;
      if ( a6 )
      {
LABEL_12:
        *v14 = v11;
LABEL_13:
        CloseServiceHandle(v8);
        CloseServiceHandle(v10);
        return 0;
      }
      if ( v11 )
        goto LABEL_13;
      v16 = -2147023819;
      goto LABEL_22;
    }
  }
  if ( GetLastError() != 1460 )
    goto LABEL_20;
  v14 = a6;
  if ( a6 )
    goto LABEL_12;
  v16 = -2147023826;
LABEL_22:
  v18 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogError(v18, L"StartAndWaitForService", 0xCDu, L"hr=0x%x.", v16);
  if ( v8 )
    CloseServiceHandle(v8);
  if ( v6 )
    CloseServiceHandle(v6);
  return v16;
}

```

## disassembly

```asm
0x180003518  push    rbx
0x18000351a  push    rbp
0x18000351b  push    rsi
0x18000351c  push    rdi
0x18000351d  push    r14
0x18000351f  sub     rsp, 30h
0x180003523  xor     edi, edi
0x180003525  xor     edx, edx; lpDatabaseName
0x180003527  xor     ecx, ecx; lpMachineName
0x180003529  lea     r8d, [rdi+1]; dwDesiredAccess
0x18000352d  call    cs:__imp_OpenSCManagerW
0x180003533  mov     rbx, rax
0x180003536  test    rax, rax
0x180003539  jz      loc_180003609
0x18000353f  lea     r8d, [rdi+14h]; dwDesiredAccess
0x180003543  mov     rcx, rax; hSCManager
0x180003546  lea     rdx, ServiceName; "dssvc"
0x18000354d  call    cs:__imp_OpenServiceW
0x180003553  mov     rsi, rax
0x180003556  test    rax, rax
0x180003559  jz      loc_18000360B
0x18000355f  xor     ebp, ebp
0x180003561  mov     rdi, rax
0x180003564  xor     r14b, r14b
0x180003567  cmp     r14b, 2
0x18000356b  jnb     short loc_1800035B5
0x18000356d  xor     r8d, r8d; lpServiceArgVectors
0x180003570  xor     edx, edx; dwNumServiceArgs
0x180003572  mov     rcx, rsi; hService
0x180003575  call    cs:__imp_StartServiceW
0x18000357b  test    eax, eax
0x18000357d  jnz     short loc_18000358C
0x18000357f  call    cs:__imp_GetLastError
0x180003585  cmp     eax, 420h
0x18000358a  jnz     short loc_18000360B
0x18000358c  xor     r9d, r9d
0x18000358f  mov     r8d, 7530h
0x180003595  mov     rcx, rsi
0x180003598  lea     edx, [r9+9]
0x18000359c  call    cs:__imp_WaitServiceState
0x1800035a2  test    eax, eax
0x1800035a4  jz      short loc_1800035DD
0x1800035a6  cmp     eax, 4
0x1800035a9  jz      short loc_1800035B0
0x1800035ab  inc     r14b
0x1800035ae  jmp     short loc_180003567
0x1800035b0  mov     ebp, 1
0x1800035b5  mov     rax, [rsp+58h+arg_28]
0x1800035bd  test    rax, rax
0x1800035c0  jz      short loc_1800035FE
0x1800035c2  mov     [rax], ebp
0x1800035c4  mov     rcx, rbx; hSCObject
0x1800035c7  call    cs:__imp_CloseServiceHandle
0x1800035cd  mov     rcx, rsi; hSCObject
0x1800035d0  call    cs:__imp_CloseServiceHandle
0x1800035d6  xor     eax, eax
0x1800035d8  jmp     loc_180003663
0x1800035dd  call    cs:__imp_GetLastError
0x1800035e3  cmp     eax, 5B4h
0x1800035e8  jnz     short loc_18000360B
0x1800035ea  mov     rax, [rsp+58h+arg_28]
0x1800035f2  test    rax, rax
0x1800035f5  jnz     short loc_1800035C2
0x1800035f7  mov     esi, 8007042Eh
0x1800035fc  jmp     short loc_180003620
0x1800035fe  test    ebp, ebp
0x180003600  jnz     short loc_1800035C4
0x180003602  mov     esi, 80070435h
0x180003607  jmp     short loc_180003620
0x180003609  xor     ebx, ebx
0x18000360b  call    cs:__imp_GetLastError
0x180003611  mov     esi, eax
0x180003613  test    eax, eax
0x180003615  jle     short loc_180003620
0x180003617  movzx   esi, ax
0x18000361a  or      esi, 80070000h
0x180003620  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003625  lea     r9, aHr0xX; "hr=0x%x."
0x18000362c  mov     [rsp+58h+var_38], esi
0x180003630  mov     r8d, 0CDh; unsigned int
0x180003636  lea     rdx, aStartandwaitfo; "StartAndWaitForService"
0x18000363d  mov     rcx, rax; this
0x180003640  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180003645  test    rbx, rbx
0x180003648  jz      short loc_180003653
0x18000364a  mov     rcx, rbx; hSCObject
0x18000364d  call    cs:__imp_CloseServiceHandle
0x180003653  test    rdi, rdi
0x180003656  jz      short loc_180003661
0x180003658  mov     rcx, rdi; hSCObject
0x18000365b  call    cs:__imp_CloseServiceHandle
0x180003661  mov     eax, esi
0x180003663  add     rsp, 30h
0x180003667  pop     r14
0x180003669  pop     rdi
0x18000366a  pop     rsi
0x18000366b  pop     rbp
0x18000366c  pop     rbx
0x18000366d  retn
```
