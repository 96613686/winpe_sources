# ComputeService::Client::NotificationCallbacks::OnNotificationPending(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x18002d768`
- end: `0x18002d8da`
- name: `?OnNotificationPending@NotificationCallbacks@Client@ComputeService@@AEAAXPEAUNotificationContext@123@@Z`
- size: `370`
- prototype: `void(ComputeService::Client::NotificationCallbacks *__hidden this, struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e0c0`

## callees

- `0x1800067c0`
- `0x180018110`
- `0x18002cda8`
- `0x18002d708`
- `0x18002d768`
- `0x18002df6c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d8a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002d8a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d8b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d8b3`

## string_xrefs

- `0x18002d80b`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Client::NotificationCallbacks::OnNotificationPending(
        ComputeService::Client::NotificationCallbacks *this,
        struct ComputeService::Client::NotificationCallbacks::NotificationContext *a2)
{
  struct ComputeService::Client::NotificationCallbacks::NotificationContext *v2; // rbx
  char v4; // di
  char v5; // si
  int v6; // eax
  ComputeService::Client::NotificationCallbacks *v7; // rcx
  void (__fastcall *v8)(__int128 *, void **, _QWORD); // rax
  HLOCAL v9; // rdi
  DWORD LastError; // ebx
  char v11; // [rsp+30h] [rbp-68h]
  void *p_hMem; // [rsp+38h] [rbp-60h] BYREF
  struct ComputeService::Client::NotificationCallbacks::NotificationContext *v14; // [rsp+40h] [rbp-58h]
  __int128 *v15; // [rsp+48h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-48h] BYREF
  __int128 v17; // [rsp+58h] [rbp-40h] BYREF
  __int64 v18; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = a2;
  v14 = a2;
  if ( ComputeService::Client::NotificationCallbacks::StartCallback(this, a2) )
  {
    try
    {
      v17 = 0;
      v18 = 0;
      v4 = 1;
      v11 = 1;
      v5 = 1;
      hMem = 0;
      p_hMem = &hMem;
      v15 = &v17;
      v6 = ComputeService::Client::InvokeRpcFunction<long (*)(void *,void * *,void * *),void * &,void * *,void * *>(
             *((_QWORD *)this + 2),
             v2,
             &v15,
             &p_hMem);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v6,
          (int)"Failed to query notification for handle %p",
          *(const char **)v2);
        v4 = 0;
        v11 = 0;
      }
    }
    catch ( ... )
    {
      *((_QWORD *)&v17 + 1) = 0x1000000;
      *(_QWORD *)&v17 = -1;
      v9 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v9);
        SetLastError(LastError);
      }
      hMem = 0;
      v4 = v11;
      v5 = 0;
      v2 = v14;
    }
    if ( v4 )
    {
      v8 = (void (__fastcall *)(__int128 *, void **, _QWORD))*((_QWORD *)v2 + 2);
      if ( v8 )
      {
        p_hMem = hMem;
        hMem = 0;
        v8(&v17, &p_hMem, *((_QWORD *)v2 + 3));
      }
      else
      {
        (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, HLOCAL))v2 + 1))(
          DWORD2(v17),
          *((_QWORD *)v2 + 3),
          HIDWORD(v17),
          hMem);
      }
    }
    if ( ComputeService::Client::NotificationCallbacks::CompleteCallback(v7, v2) && v5 )
      SetThreadpoolWait(*((PTP_WAIT *)v2 + 5), *((HANDLE *)v2 + 4), 0);
    if ( hMem )
      LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x18002d768  mov     [rsp+arg_10], rbx
0x18002d76d  push    rsi
0x18002d76e  push    rdi
0x18002d76f  push    r14
0x18002d771  sub     rsp, 80h
0x18002d778  mov     rax, cs:__security_cookie
0x18002d77f  xor     rax, rsp
0x18002d782  mov     [rsp+98h+var_28], rax
0x18002d787  mov     rbx, rdx
0x18002d78a  mov     r14, rcx
0x18002d78d  mov     [rsp+98h+var_58], rdx
0x18002d792  call    ?StartCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::StartCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x18002d797  test    al, al
0x18002d799  jz      loc_18002D8B9
0x18002d79f  xorps   xmm0, xmm0
0x18002d7a2  xor     eax, eax
0x18002d7a4  movups  [rsp+98h+var_40], xmm0
0x18002d7a9  mov     [rsp+98h+var_30], rax
0x18002d7ae  mov     dil, 1
0x18002d7b1  mov     [rsp+98h+var_68], dil
0x18002d7b6  mov     sil, dil
0x18002d7b9  mov     [rsp+98h+hMem], rax
0x18002d7be  lea     rax, [rsp+98h+hMem]
0x18002d7c3  mov     [rsp+98h+var_60], rax
0x18002d7c8  lea     rax, [rsp+98h+var_40]
0x18002d7cd  mov     [rsp+98h+var_50], rax
0x18002d7d2  lea     r9, [rsp+98h+var_60]
0x18002d7d7  lea     r8, [rsp+98h+var_50]
0x18002d7dc  mov     rdx, rbx
0x18002d7df  mov     rcx, [r14+10h]
0x18002d7e3  call    ??$InvokeRpcFunction@P6AJPEAXPEAPEAX1@ZAEAPEAXPEAPEAXPEAPEAX@Client@ComputeService@@YA?A_TP6AJPEAXPEAPEAX1@ZAEAPEAX$$QEAPEAPEAX4@Z
0x18002d7e8  test    eax, eax
0x18002d7ea  jns     short loc_18002D824
0x18002d7ec  mov     rcx, [rsp+98h]; this
0x18002d7f4  mov     rdx, [rbx]
0x18002d7f7  mov     [rsp+98h+var_70], rdx; char *
0x18002d7fc  lea     rdx, aFailedToQueryN; "Failed to query notification for handle"...
0x18002d803  mov     qword ptr [rsp+98h+var_78], rdx; int
0x18002d808  mov     r9d, eax; char *
0x18002d80b  lea     r8, aOnecoreVmCompu_16; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x18002d812  mov     edx, 1A2h; void *
0x18002d817  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d81c  xor     dil, dil
0x18002d81f  mov     [rsp+98h+var_68], dil
0x18002d824  jmp     short loc_18002D835
0x18002d826  mov     dil, [rsp+98h+var_68]
0x18002d82b  mov     sil, [rsp+98h+var_67]
0x18002d830  mov     rbx, [rsp+98h+var_58]
0x18002d835  test    dil, dil
0x18002d838  jz      short loc_18002D886
0x18002d83a  mov     rax, [rbx+10h]
0x18002d83e  test    rax, rax
0x18002d841  jz      short loc_18002D86B
0x18002d843  mov     rcx, [rsp+98h+hMem]
0x18002d848  mov     [rsp+98h+var_60], rcx
0x18002d84d  mov     [rsp+98h+hMem], 0
0x18002d856  mov     r8, [rbx+18h]
0x18002d85a  lea     rdx, [rsp+98h+var_60]
0x18002d85f  lea     rcx, [rsp+98h+var_40]
0x18002d864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d869  jmp     short loc_18002D886
0x18002d86b  mov     r9, [rsp+98h+hMem]
0x18002d870  mov     r8d, dword ptr [rsp+98h+var_40+0Ch]
0x18002d875  mov     rdx, [rbx+18h]
0x18002d879  mov     ecx, dword ptr [rsp+98h+var_40+8]
0x18002d87d  mov     rax, [rbx+8]
0x18002d881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d886  mov     rdx, rbx; struct ComputeService::Client::NotificationCallbacks::NotificationContext *
0x18002d889  call    ?CompleteCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::CompleteCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x18002d88e  test    al, al
0x18002d890  jz      short loc_18002D8A9
0x18002d892  test    sil, sil
0x18002d895  jz      short loc_18002D8A9
0x18002d897  xor     r8d, r8d; pftTimeout
0x18002d89a  mov     rdx, [rbx+20h]; h
0x18002d89e  mov     rcx, [rbx+28h]; pwa
0x18002d8a2  call    cs:__imp_SetThreadpoolWait
0x18002d8a8  nop
0x18002d8a9  mov     rcx, [rsp+98h+hMem]; hMem
0x18002d8ae  test    rcx, rcx
0x18002d8b1  jz      short loc_18002D8B9
0x18002d8b3  call    cs:__imp_LocalFree
0x18002d8b9  mov     rcx, [rsp+98h+var_28]
0x18002d8be  xor     rcx, rsp; StackCookie
0x18002d8c1  call    __security_check_cookie
0x18002d8c6  mov     rbx, [rsp+98h+arg_10]
0x18002d8ce  add     rsp, 80h
0x18002d8d5  pop     r14
0x18002d8d7  pop     rdi
0x18002d8d8  pop     rsi
0x18002d8d9  retn
```
