# ServiceManager::ExecuteService(void)

- ea: `0x18000e2bc`
- end: `0x18000e3f4`
- name: `?ExecuteService@ServiceManager@@QEAAXXZ`
- size: `312`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c2a0`

## callees

- `0x18000d338`
- `0x18000d4c8`
- `0x18000e2bc`
- `0x18000e3fc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e382`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e382`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e363`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e363`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000e2dc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000e2dc`

## string_xrefs

- `0x18000e3c3`: `RegisterServiceCtrlHandlerExW`

## pseudocode

```c
void __fastcall ServiceManager::ExecuteService(LPCWSTR *this)
{
  LPCWSTR *v1; // rbx
  SERVICE_STATUS_HANDLE v2; // rax
  int v3; // eax
  __int64 v4; // rcx
  DWORD v5; // edi
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  const Exception *v10; // [rsp+30h] [rbp-18h] BYREF
  DWORD dwindex; // [rsp+58h] [rbp+10h] BYREF

  v1 = this;
  v2 = RegisterServiceCtrlHandlerExW(this[9], (LPHANDLER_FUNCTION_EX)ServiceManager::CommonControlHandler, this);
  v1[13] = (LPCWSTR)v2;
  if ( !v2 )
    SystemError::Throw(L"RegisterServiceCtrlHandlerExW");
  v3 = ServiceManager::ReportStatusNoThrow((ServiceManager *)v1, 2u, 0);
  if ( v3 )
    SystemError::Throw<unsigned long>(v4, v3);
  v5 = 0;
  try
  {
    (*((void (**)(void))*v1 + 1))();
    v6 = ServiceManager::ReportStatusNoThrow((ServiceManager *)v1, 4u, 0);
    if ( v6 )
      SystemError::Throw<unsigned long>(v7, v6);
    (*((void (__fastcall **)(LPCWSTR *))*v1 + 2))(v1);
    if ( *((_BYTE *)v1 + 80) )
    {
      dwindex = 0;
      CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, (LPHANDLE)v1 + 12, &dwindex);
    }
    else if ( WaitForSingleObject((HANDLE)v1[12], 0xFFFFFFFF) == -1 )
    {
      SystemError::Throw(L"WaitForSingleObject");
    }
    v8 = ServiceManager::ReportStatusNoThrow((ServiceManager *)v1, 3u, 0);
    if ( v8 )
      SystemError::Throw<unsigned long>(v9, v8);
  }
  catch ( const Exception *v10 )
  {
    dwindex = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v10 + 16LL))(v10);
    v1 = this;
    v5 = dwindex;
  }
  (*((void (**)(void))*v1 + 1))();
  v6 = ServiceManager::ReportStatusNoThrow((ServiceManager *)v1, 4u, 0);
}

```

## disassembly

```asm
0x18000e2bc  mov     [rsp+arg_10], rbx
0x18000e2c1  mov     [rsp+arg_0], rcx
0x18000e2c6  push    rdi
0x18000e2c7  sub     rsp, 40h
0x18000e2cb  mov     rbx, rcx
0x18000e2ce  mov     r8, rcx; lpContext
0x18000e2d1  lea     rdx, ?CommonControlHandler@ServiceManager@@CAKKKPEAX0@Z; lpHandlerProc
0x18000e2d8  mov     rcx, [rcx+48h]; lpServiceName
0x18000e2dc  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000e2e2  mov     [rbx+68h], rax
0x18000e2e6  test    rax, rax
0x18000e2e9  jz      loc_18000E3C3
0x18000e2ef  xor     r8d, r8d; unsigned int
0x18000e2f2  lea     edx, [r8+2]; unsigned int
0x18000e2f6  mov     rcx, rbx; this
0x18000e2f9  call    ?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z; ServiceManager::ReportStatusNoThrow(ulong,ulong)
0x18000e2fe  test    eax, eax
0x18000e300  jnz     loc_18000E3D0
0x18000e306  xor     edi, edi
0x18000e308  mov     rax, [rbx]
0x18000e30b  mov     rcx, rbx
0x18000e30e  mov     rax, [rax+8]
0x18000e312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e317  xor     r8d, r8d; unsigned int
0x18000e31a  lea     edx, [rdi+4]; unsigned int
0x18000e31d  mov     rcx, rbx; this
0x18000e320  call    ?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z; ServiceManager::ReportStatusNoThrow(ulong,ulong)
0x18000e325  test    eax, eax
0x18000e327  jnz     loc_18000E3D8
0x18000e32d  mov     rax, [rbx]
0x18000e330  mov     rcx, rbx
0x18000e333  mov     rax, [rax+10h]
0x18000e337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000e33f  cmp     byte ptr [rbx+50h], 0
0x18000e343  jz      short loc_18000E37E
0x18000e345  mov     [rsp+48h+dwindex], 0
0x18000e34d  lea     rax, [rsp+48h+dwindex]
0x18000e352  mov     [rsp+48h+lpdwindex], rax; lpdwindex
0x18000e357  lea     r9, [rbx+60h]; pHandles
0x18000e35b  mov     r8d, 1; cHandles
0x18000e361  xor     ecx, ecx; dwFlags
0x18000e363  call    cs:__imp_CoWaitForMultipleHandles
0x18000e369  xor     r8d, r8d; unsigned int
0x18000e36c  lea     edx, [r8+3]; unsigned int
0x18000e370  mov     rcx, rbx; this
0x18000e373  call    ?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z; ServiceManager::ReportStatusNoThrow(ulong,ulong)
0x18000e378  test    eax, eax
0x18000e37a  jnz     short loc_18000E3DF
0x18000e37c  jmp     short loc_18000E38F
0x18000e37e  mov     rcx, [rbx+60h]; hHandle
0x18000e382  call    cs:__imp_WaitForSingleObject
0x18000e388  cmp     eax, 0FFFFFFFFh
0x18000e38b  jz      short loc_18000E3E6
0x18000e38d  jmp     short loc_18000E369
0x18000e38f  jmp     short loc_18000E39A
0x18000e391  mov     rbx, [rsp+48h+arg_0]
0x18000e396  mov     edi, [rsp+48h+dwindex]
0x18000e39a  mov     rax, [rbx]
0x18000e39d  mov     rcx, rbx
0x18000e3a0  mov     rax, [rax+28h]
0x18000e3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a9  mov     r8d, edi; unsigned int
0x18000e3ac  mov     edx, 1; unsigned int
0x18000e3b1  mov     rcx, rbx; this
0x18000e3b4  mov     rbx, [rsp+48h+arg_10]
0x18000e3b9  add     rsp, 40h
0x18000e3bd  pop     rdi
0x18000e3be  jmp     ?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z; ServiceManager::ReportStatusNoThrow(ulong,ulong)
0x18000e3c3  lea     rcx, aRegisterservic_0; "RegisterServiceCtrlHandlerExW"
0x18000e3ca  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18000e3d0  mov     edx, eax
0x18000e3d2  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x18000e3d8  mov     edx, eax
0x18000e3da  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x18000e3df  mov     edx, eax
0x18000e3e1  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x18000e3e6  lea     rcx, aWaitforsingleo; "WaitForSingleObject"
0x18000e3ed  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
