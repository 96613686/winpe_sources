# StartRemoteQueryStub(_GUID const *,_PROVIDER_QUERY_TYPE,_PROVIDER_QUERY_ENTRY *,_DEV_QUERY_DATA *,void *)

- ea: `0x18004c950`
- end: `0x18004cbbe`
- name: `?StartRemoteQueryStub@@YAJPEBU_GUID@@W4_PROVIDER_QUERY_TYPE@@PEAU_PROVIDER_QUERY_ENTRY@@PEAU_DEV_QUERY_DATA@@PEAX@Z`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020168`

## callees

- `0x180007500`
- `0x180024294`
- `0x18002482c`
- `0x18002cc94`
- `0x18004bd78`
- `0x18004c950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ca04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ca04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cb0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004c9c1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004c9c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004cb9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004cb9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ca27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ca27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cad5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ca52`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004cb00`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ca52`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004cb00`

## pseudocode

```c
__int64 StartRemoteQueryStub(__int64 a1, int a2, ...)
{
  _QWORD *v2; // rax
  PTP_WAIT ThreadpoolWait; // rax
  signed int v4; // eax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  HANDLE v13; // rdi
  void *v14; // rbx
  HANDLE v15; // rax
  unsigned int HostContext; // [rsp+48h] [rbp-31h] BYREF
  CHostContext *v18; // [rsp+50h] [rbp-29h] BYREF
  HANDLE v19; // [rsp+58h] [rbp-21h] BYREF
  HANDLE TargetHandle; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v21[8]; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v22[4]; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v23; // [rsp+D8h] [rbp+5Fh] BYREF
  int v24; // [rsp+E0h] [rbp+67h] BYREF
  PVOID pv; // [rsp+E8h] [rbp+6Fh] BYREF
  va_list pva; // [rsp+E8h] [rbp+6Fh]
  __int64 v27; // [rsp+F0h] [rbp+77h] BYREF
  va_list va1; // [rsp+F0h] [rbp+77h]
  HANDLE hSourceHandle; // [rsp+F8h] [rbp+7Fh]
  va_list va2; // [rsp+100h] [rbp+87h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(pva, a2);
  pv = va_arg(va1, PVOID);
  va_copy(va2, va1);
  v27 = va_arg(va2, _QWORD);
  hSourceHandle = va_arg(va2, HANDLE);
  v24 = a2;
  v23 = a1;
  v18 = 0;
  TargetHandle = 0;
  v19 = 0;
  v2 = std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(v22, (_QWORD *)pv + 7);
  HostContext = CHostContext::GetHostContext(v2, &v18);
  if ( !HostContext )
  {
    ThreadpoolWait = CreateThreadpoolWait(RemoteProviderQueryWaitCallback, pv, 0);
    *((_QWORD *)pv + 19) = ThreadpoolWait;
    if ( *((_QWORD *)pv + 19)
      && (*((_QWORD *)pv + 9) = CreateEventW(0, 0, 0, 0), (v5 = (void *)*((_QWORD *)pv + 9)) != 0) )
    {
      v6 = (void *)*((_QWORD *)v18 + 1);
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, v5, v6, &TargetHandle, 0, 0, 2u) )
      {
        v12 = *((_QWORD *)pv + 7);
        if ( *(_DWORD *)(v12 + 72)
          && *(_DWORD *)(v12 + 84)
          && (v13 = hSourceHandle) != 0
          && (v14 = (void *)*((_QWORD *)v18 + 1),
              v15 = GetCurrentProcess(),
              !DuplicateHandle(v15, v13, v14, &v19, 0, 0, 2u)) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          HostContext = LastError;
          if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v11 = 56;
            goto LABEL_12;
          }
        }
        else
        {
          v21[0] = &HostContext;
          v21[1] = &v18;
          v21[2] = &v23;
          v21[3] = &v24;
          va_copy((va_list)&v21[4], pva);
          va_copy((va_list)&v21[5], va1);
          v21[6] = &v19;
          v21[7] = &TargetHandle;
          HostContext = lambda_72ee87ff226771ad95e636492ee4c28a_::operator()(v21);
          if ( !HostContext )
            SetThreadpoolWait(*((PTP_WAIT *)pv + 19), *((HANDLE *)pv + 9), 0);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        HostContext = LastError;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v11 = 55;
LABEL_12:
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v9,
            v10,
            v11,
            &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
            LastError);
        }
      }
    }
    else
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      HostContext = v4;
    }
  }
  if ( v18 )
    CHostContext::Release(v18);
  return HostContext;
}

```

## disassembly

```asm
0x18004c950  mov     rax, rsp
0x18004c953  mov     [rax+20h], r9
0x18004c957  mov     [rax+18h], r8
0x18004c95b  mov     [rax+10h], edx
0x18004c95e  mov     [rax+8], rcx
0x18004c962  push    rbp
0x18004c963  push    rbx
0x18004c964  push    rdi
0x18004c965  lea     rbp, [rax-57h]
0x18004c969  sub     rsp, 0B0h
0x18004c970  mov     [rbp+4Fh+var_80], 0
0x18004c977  mov     [rbp+4Fh+var_78], 0
0x18004c97f  mov     [rbp+4Fh+TargetHandle], 0
0x18004c987  mov     [rbp+4Fh+var_70], 0
0x18004c98f  lea     rdx, [r8+38h]
0x18004c993  lea     rcx, [rbp+4Fh+var_20]
0x18004c997  call    ??0?$shared_ptr@VProviderContext@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ProviderContext>::shared_ptr<ProviderContext>(std::shared_ptr<ProviderContext> const &)
0x18004c99c  mov     rcx, rax
0x18004c99f  lea     rdx, [rbp+4Fh+var_78]
0x18004c9a3  call    ?GetHostContext@CHostContext@@SAJV?$shared_ptr@VProviderContext@@@std@@PEAPEAV1@@Z; CHostContext::GetHostContext(std::shared_ptr<ProviderContext>,CHostContext * *)
0x18004c9a8  mov     [rbp+4Fh+var_80], eax
0x18004c9ab  test    eax, eax
0x18004c9ad  jnz     loc_18004CBA2
0x18004c9b3  xor     r8d, r8d; pcbe
0x18004c9b6  mov     rdx, [rbp+4Fh+pv]; pv
0x18004c9ba  lea     rcx, ?RemoteProviderQueryWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18004c9c1  call    cs:__imp_CreateThreadpoolWait
0x18004c9c7  mov     rcx, [rbp+4Fh+pv]
0x18004c9cb  mov     [rcx+98h], rax
0x18004c9d2  mov     rax, [rbp+4Fh+pv]
0x18004c9d6  cmp     qword ptr [rax+98h], 0
0x18004c9de  jnz     short loc_18004C9FA
0x18004c9e0  call    cs:__imp_GetLastError
0x18004c9e6  test    eax, eax
0x18004c9e8  jle     short loc_18004C9F2
0x18004c9ea  movzx   eax, ax
0x18004c9ed  or      eax, 80070000h
0x18004c9f2  mov     [rbp+4Fh+var_80], eax
0x18004c9f5  jmp     loc_18004CBA2
0x18004c9fa  xor     r9d, r9d; lpName
0x18004c9fd  xor     r8d, r8d; bInitialState
0x18004ca00  xor     edx, edx; bManualReset
0x18004ca02  xor     ecx, ecx; lpEventAttributes
0x18004ca04  call    cs:__imp_CreateEventW
0x18004ca0a  mov     rcx, [rbp+4Fh+pv]
0x18004ca0e  mov     [rcx+48h], rax
0x18004ca12  mov     rax, [rbp+4Fh+pv]
0x18004ca16  mov     rdi, [rax+48h]
0x18004ca1a  test    rdi, rdi
0x18004ca1d  jz      short loc_18004C9E0
0x18004ca1f  mov     rax, [rbp+4Fh+var_78]
0x18004ca23  mov     rbx, [rax+8]
0x18004ca27  call    cs:__imp_GetCurrentProcess
0x18004ca2d  mov     dword ptr [rsp+30h], 2; dwOptions
0x18004ca35  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x18004ca3d  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x18004ca45  lea     r9, [rbp+4Fh+TargetHandle]; lpTargetHandle
0x18004ca49  mov     r8, rbx; hTargetProcessHandle
0x18004ca4c  mov     rdx, rdi; hSourceHandle
0x18004ca4f  mov     rcx, rax; hSourceProcessHandle
0x18004ca52  call    cs:__imp_DuplicateHandle
0x18004ca58  test    eax, eax
0x18004ca5a  jnz     short loc_18004CAB0
0x18004ca5c  call    cs:__imp_GetLastError
0x18004ca62  test    eax, eax
0x18004ca64  jle     short loc_18004CA6E
0x18004ca66  movzx   eax, ax
0x18004ca69  or      eax, 80070000h
0x18004ca6e  mov     [rbp+4Fh+var_80], eax
0x18004ca71  lea     rcx, WPP_RECORDER_INITIALIZED
0x18004ca78  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18004ca7f  jz      loc_18004CBA2
0x18004ca85  mov     r9d, 37h ; '7'; int
0x18004ca8b  mov     [rsp+0C0h+bInheritHandle], eax; char
0x18004ca8f  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18004ca96  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax; MessageGuid
0x18004ca9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004caa2  mov     rcx, [rcx+28h]; int
0x18004caa6  call    WPP_RECORDER_SF_D
0x18004caab  jmp     loc_18004CBA2
0x18004cab0  mov     rax, [rbp+4Fh+pv]
0x18004cab4  mov     rcx, [rax+38h]
0x18004cab8  cmp     dword ptr [rcx+48h], 0
0x18004cabc  jz      short loc_18004CB3A
0x18004cabe  cmp     dword ptr [rcx+54h], 0
0x18004cac2  jz      short loc_18004CB3A
0x18004cac4  mov     rdi, [rbp+4Fh+hSourceHandle]
0x18004cac8  test    rdi, rdi
0x18004cacb  jz      short loc_18004CB3A
0x18004cacd  mov     rax, [rbp+4Fh+var_78]
0x18004cad1  mov     rbx, [rax+8]
0x18004cad5  call    cs:__imp_GetCurrentProcess
0x18004cadb  mov     dword ptr [rsp+30h], 2; dwOptions
0x18004cae3  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x18004caeb  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x18004caf3  lea     r9, [rbp+4Fh+var_70]; lpTargetHandle
0x18004caf7  mov     r8, rbx; hTargetProcessHandle
0x18004cafa  mov     rdx, rdi; hSourceHandle
0x18004cafd  mov     rcx, rax; hSourceProcessHandle
0x18004cb00  call    cs:__imp_DuplicateHandle
0x18004cb06  test    eax, eax
0x18004cb08  jnz     short loc_18004CB3A
0x18004cb0a  call    cs:__imp_GetLastError
0x18004cb10  test    eax, eax
0x18004cb12  jle     short loc_18004CB1C
0x18004cb14  movzx   eax, ax
0x18004cb17  or      eax, 80070000h
0x18004cb1c  mov     [rbp+4Fh+var_80], eax
0x18004cb1f  lea     rcx, WPP_RECORDER_INITIALIZED
0x18004cb26  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18004cb2d  jz      short loc_18004CBA2
0x18004cb2f  mov     r9d, 38h ; '8'
0x18004cb35  jmp     loc_18004CA8B
0x18004cb3a  lea     rax, [rbp+4Fh+var_80]
0x18004cb3e  mov     [rbp+4Fh+var_60], rax
0x18004cb42  lea     rax, [rbp+4Fh+var_78]
0x18004cb46  mov     [rbp+4Fh+var_58], rax
0x18004cb4a  lea     rax, [rbp+4Fh+arg_0]
0x18004cb4e  mov     [rbp+4Fh+var_50], rax
0x18004cb52  lea     rax, [rbp+4Fh+arg_8]
0x18004cb56  mov     [rbp+4Fh+var_48], rax
0x18004cb5a  lea     rax, [rbp+4Fh+pv]
0x18004cb5e  mov     [rbp+4Fh+var_40], rax
0x18004cb62  lea     rax, [rbp+4Fh+arg_18]
0x18004cb66  mov     [rbp+4Fh+var_38], rax
0x18004cb6a  lea     rax, [rbp+4Fh+var_70]
0x18004cb6e  mov     [rbp+4Fh+var_30], rax
0x18004cb72  lea     rax, [rbp+4Fh+TargetHandle]
0x18004cb76  mov     [rbp+4Fh+var_28], rax
0x18004cb7a  lea     rcx, [rbp+4Fh+var_60]
0x18004cb7e  call    _lambda_72ee87ff226771ad95e636492ee4c28a___operator__
0x18004cb83  mov     [rbp+4Fh+var_80], eax
0x18004cb86  test    eax, eax
0x18004cb88  jnz     short loc_18004CBA2
0x18004cb8a  xor     r8d, r8d; pftTimeout
0x18004cb8d  mov     rcx, [rbp+4Fh+pv]
0x18004cb91  mov     rdx, [rcx+48h]; h
0x18004cb95  mov     rcx, [rcx+98h]; pwa
0x18004cb9c  call    cs:__imp_SetThreadpoolWait
0x18004cba2  mov     rcx, [rbp+4Fh+var_78]; this
0x18004cba6  test    rcx, rcx
0x18004cba9  jz      short loc_18004CBB0
0x18004cbab  call    ?Release@CHostContext@@QEAAKXZ; CHostContext::Release(void)
0x18004cbb0  mov     eax, [rbp+4Fh+var_80]
0x18004cbb3  add     rsp, 0B0h
0x18004cbba  pop     rdi
0x18004cbbb  pop     rbx
0x18004cbbc  pop     rbp
0x18004cbbd  retn
```
