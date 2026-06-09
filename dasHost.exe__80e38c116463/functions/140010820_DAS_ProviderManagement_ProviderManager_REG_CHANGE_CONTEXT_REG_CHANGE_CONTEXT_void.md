# DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT::~_REG_CHANGE_CONTEXT(void)

- ea: `0x140010820`
- end: `0x140010898`
- name: `??1_REG_CHANGE_CONTEXT@ProviderManager@ProviderManagement@DAS@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400083bc`
- `0x140010820`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001084c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001084c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001083e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001083e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140010855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140010855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010877`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010877`

## pseudocode

```c
void __fastcall DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT::~_REG_CHANGE_CONTEXT(
        DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  HKEY v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 4);
  if ( v1 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 4), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (HKEY)*((_QWORD *)this + 2);
  if ( v6 )
    RegCloseKey(v6);
}

```

## disassembly

```asm
0x140010820  mov     [rsp+arg_0], rbx
0x140010825  push    rdi
0x140010826  sub     rsp, 20h
0x14001082a  mov     rdi, [rcx+20h]
0x14001082e  mov     rbx, rcx
0x140010831  test    rdi, rdi
0x140010834  jz      short loc_14001085B
0x140010836  xor     r8d, r8d; pftTimeout
0x140010839  xor     edx, edx; h
0x14001083b  mov     rcx, rdi; pwa
0x14001083e  call    cs:__imp_SetThreadpoolWait
0x140010844  mov     edx, 1; fCancelPendingCallbacks
0x140010849  mov     rcx, rdi; pwa
0x14001084c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140010852  mov     rcx, rdi; pwa
0x140010855  call    cs:__imp_CloseThreadpoolWait
0x14001085b  mov     rcx, [rbx+18h]; hObject
0x14001085f  test    rcx, rcx
0x140010862  jz      short loc_14001086E
0x140010864  call    cs:__imp_CloseHandle
0x14001086a  test    eax, eax
0x14001086c  jz      short loc_140010888
0x14001086e  mov     rcx, [rbx+10h]; hKey
0x140010872  test    rcx, rcx
0x140010875  jz      short loc_14001087D
0x140010877  call    cs:__imp_RegCloseKey
0x14001087d  mov     rbx, [rsp+28h+arg_0]
0x140010882  add     rsp, 20h
0x140010886  pop     rdi
0x140010887  retn
0x140010888  mov     rcx, [rsp+28h]; this
0x14001088d  mov     edx, 0A0Bh; void *
0x140010892  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
