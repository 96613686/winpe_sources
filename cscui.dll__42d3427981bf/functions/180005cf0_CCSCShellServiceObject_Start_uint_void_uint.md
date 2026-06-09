# CCSCShellServiceObject::Start(uint,void * *,uint *)

- ea: `0x180005cf0`
- end: `0x180005e70`
- name: `?Start@CCSCShellServiceObject@@UEAAJIPEAPEAXPEAI@Z`
- size: `384`
- prototype: `__int64 __fastcall(CCSCShellServiceObject *__hidden this, unsigned int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005cf0`
- `0x180005e80`
- `0x180008348`
- `0x180008b40`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005db6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005db6`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180005d23`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180005d23`

## pseudocode

```c
__int64 __fastcall CCSCShellServiceObject::Start(CCSCShellServiceObject *this, int a2, void **a3, unsigned int *a4)
{
  signed int Error; // ebx
  HANDLE WaitableTimerW; // rax
  int v10; // eax
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  Error = -2147467259;
  if ( a2 )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
    *a3 = WaitableTimerW;
    if ( WaitableTimerW )
    {
      *((_QWORD *)this + 2) = WaitableTimerW;
    }
    else
    {
      Error = ResultFromLastError();
      if ( Error < 0 )
      {
LABEL_4:
        CloseHandle(*a3);
        *a3 = 0;
        *((_QWORD *)this + 2) = 0;
        return (unsigned int)Error;
      }
    }
    Error = COfflineFilesEventListener::_InitializeServiceListening((CCSCShellServiceObject *)((char *)this - 256));
    if ( Error < 0 )
      goto LABEL_4;
    *((_DWORD *)this - 60) = 0;
    ppv = 0;
    if ( CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310, &ppv) >= 0 )
    {
      v11 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v11) >= 0 )
      {
        v13 = 0;
        v14 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v11 + 24LL))(
                v11,
                1,
                &v14,
                &v13);
        if ( v10 )
        {
          if ( v10 == 1 )
            *((_DWORD *)this - 60) = 1;
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v14 = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( !*((_DWORD *)this - 60) )
      CCSCShellServiceObject::_ScheduleSyncHandlerUpdate((CCSCShellServiceObject *)((char *)this - 256));
    *a4 = 1;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180005cf0  mov     [rsp-28h+arg_0], rbx
0x180005cf5  push    rbp
0x180005cf6  push    rsi
0x180005cf7  push    rdi
0x180005cf8  push    r14
0x180005cfa  push    r15
0x180005cfc  mov     rbp, rsp
0x180005cff  sub     rsp, 40h
0x180005d03  mov     dword ptr [r9], 0
0x180005d0a  mov     r15, r9
0x180005d0d  mov     rsi, r8
0x180005d10  mov     rdi, rcx
0x180005d13  mov     ebx, 80004005h
0x180005d18  test    edx, edx
0x180005d1a  jz      short loc_180005D5B
0x180005d1c  xor     r8d, r8d; lpTimerName
0x180005d1f  xor     edx, edx; bManualReset
0x180005d21  xor     ecx, ecx; lpTimerAttributes
0x180005d23  call    cs:__imp_CreateWaitableTimerW
0x180005d29  mov     [rsi], rax
0x180005d2c  lea     r14, [rdi-100h]
0x180005d33  test    rax, rax
0x180005d36  jnz     short loc_180005D6E
0x180005d38  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180005d3d  mov     ebx, eax
0x180005d3f  test    eax, eax
0x180005d41  jns     short loc_180005D75
0x180005d43  mov     rcx, [rsi]; hObject
0x180005d46  call    cs:__imp_CloseHandle
0x180005d4c  mov     qword ptr [rsi], 0
0x180005d53  mov     qword ptr [rdi+10h], 0
0x180005d5b  mov     eax, ebx
0x180005d5d  mov     rbx, [rsp+40h+arg_0]
0x180005d62  add     rsp, 40h
0x180005d66  pop     r15
0x180005d68  pop     r14
0x180005d6a  pop     rdi
0x180005d6b  pop     rsi
0x180005d6c  pop     rbp
0x180005d6d  retn
0x180005d6e  mov     [r14+110h], rax
0x180005d75  mov     rcx, r14; this
0x180005d78  call    ?_InitializeServiceListening@COfflineFilesEventListener@@IEAAJXZ; COfflineFilesEventListener::_InitializeServiceListening(void)
0x180005d7d  mov     ebx, eax
0x180005d7f  test    eax, eax
0x180005d81  js      short loc_180005D43
0x180005d83  lea     rax, [rbp+var_8]
0x180005d87  mov     dword ptr [rdi-0F0h], 0
0x180005d91  mov     esi, 1
0x180005d96  mov     [rbp+var_8], 0
0x180005d9e  mov     r8d, esi; dwClsContext
0x180005da1  mov     [rsp+40h+ppv], rax; ppv
0x180005da6  lea     r9, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310; riid
0x180005dad  xor     edx, edx; pUnkOuter
0x180005daf  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180005db6  call    cs:__imp_CoCreateInstance
0x180005dbc  test    eax, eax
0x180005dbe  js      loc_180005E57
0x180005dc4  mov     rcx, [rbp+var_8]
0x180005dc8  lea     r8, [rbp+var_10]
0x180005dcc  mov     [rbp+var_10], 0
0x180005dd4  xor     edx, edx
0x180005dd6  mov     rax, [rcx]
0x180005dd9  mov     rax, [rax+18h]
0x180005ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de2  test    eax, eax
0x180005de4  js      short loc_180005E47
0x180005de6  mov     rcx, [rbp+var_10]
0x180005dea  lea     r9, [rbp+arg_8]
0x180005dee  mov     [rbp+arg_8], 0
0x180005df5  lea     r8, [rbp+arg_18]
0x180005df9  mov     [rbp+arg_18], 0
0x180005e01  mov     edx, esi
0x180005e03  mov     rax, [rcx]
0x180005e06  mov     rax, [rax+18h]
0x180005e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e0f  test    eax, eax
0x180005e11  jnz     short loc_180005E2D
0x180005e13  mov     rcx, [rbp+arg_18]
0x180005e17  mov     rax, [rcx]
0x180005e1a  mov     rax, [rax+10h]
0x180005e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e23  mov     [rbp+arg_18], 0
0x180005e2b  jmp     short loc_180005E37
0x180005e2d  cmp     eax, esi
0x180005e2f  jnz     short loc_180005E37
0x180005e31  mov     [rdi-0F0h], esi
0x180005e37  mov     rcx, [rbp+var_10]
0x180005e3b  mov     rax, [rcx]
0x180005e3e  mov     rax, [rax+10h]
0x180005e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e47  mov     rcx, [rbp+var_8]
0x180005e4b  mov     rax, [rcx]
0x180005e4e  mov     rax, [rax+10h]
0x180005e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e57  cmp     dword ptr [rdi-0F0h], 0
0x180005e5e  jnz     short loc_180005E68
0x180005e60  mov     rcx, r14; this
0x180005e63  call    ?_ScheduleSyncHandlerUpdate@CCSCShellServiceObject@@AEAAJXZ; CCSCShellServiceObject::_ScheduleSyncHandlerUpdate(void)
0x180005e68  mov     [r15], esi
0x180005e6b  jmp     loc_180005D5B
```
