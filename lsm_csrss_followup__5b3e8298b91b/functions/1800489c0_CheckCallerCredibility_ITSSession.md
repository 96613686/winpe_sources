# CheckCallerCredibility(ITSSession *)

- ea: `0x1800489c0`
- end: `0x180048b78`
- name: `?CheckCallerCredibility@@YAJPEAUITSSession@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(struct ITSSession *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18005ac9c`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180009dd0`
- `0x1800125c0`
- `0x1800489c0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048a6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048a56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b54`
- `RPCRT4!RpcImpersonateClient` at `0x1800489e8`
- `RPCRT4!RpcImpersonateClient` at `0x1800489e8`
- `RPCRT4!RpcRevertToSelf` at `0x180048b1d`
- `RPCRT4!RpcRevertToSelf` at `0x180048b1d`

## string_xrefs

- `0x180048a92`: `OpenThreadToken failed: 0x%x in %s`
- `0x180048a0b`: `RpcImpersonateClient failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CheckCallerCredibility(struct ITSSession *a1)
{
  RPC_STATUS v2; // eax
  signed int IsCallerSystem; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int InstanceOfUserName; // eax
  struct IUserName *v7; // rbx
  int v8; // eax
  int v9; // eax
  __int64 v11; // [rsp+48h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF
  struct IUserName *v13; // [rsp+58h] [rbp+38h] BYREF

  v11 = 0;
  v13 = 0;
  TokenHandle = 0;
  v2 = RpcImpersonateClient(0);
  IsCallerSystem = v2;
  if ( v2 > 0 )
    IsCallerSystem = (unsigned __int16)v2 | 0x80070000;
  if ( IsCallerSystem >= 0 )
  {
    if ( (*(int (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v11) >= 0 && v11 )
    {
      IsCallerSystem = CUtils::IsCallerSystem();
      if ( IsCallerSystem )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
          goto LABEL_14;
        LastError = GetLastError();
        IsCallerSystem = LastError;
        if ( LastError > 0 )
          IsCallerSystem = (unsigned __int16)LastError | 0x80070000;
        if ( IsCallerSystem >= 0 )
        {
LABEL_14:
          InstanceOfUserName = CUtils::GetInstanceOfUserName(&v13);
          IsCallerSystem = InstanceOfUserName;
          if ( InstanceOfUserName >= 0 )
          {
            v7 = v13;
            v8 = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v13 + 24LL))(
                   v13,
                   TokenHandle,
                   0);
            IsCallerSystem = v8;
            if ( v8 >= 0 )
              IsCallerSystem = (*(__int64 (__fastcall **)(__int64, struct IUserName *))(*(_QWORD *)v11 + 32LL))(v11, v7);
            else
              _DbgPrintMessage(
                8,
                "ptrUserName->Initialize failed: 0x%x in %s",
                (unsigned int)v8,
                "CheckCallerCredibility");
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CUtils::GetInstanceOfUserName failed: 0x%x in %s",
              (unsigned int)InstanceOfUserName,
              "CheckCallerCredibility");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "OpenThreadToken failed: 0x%x in %s",
            (unsigned int)IsCallerSystem,
            "CheckCallerCredibility");
        }
      }
    }
    else
    {
      _DbgPrintMessage(1, "CheckCallerCredibiltiy, the session is not logged on");
      IsCallerSystem = 0;
    }
    v9 = RpcRevertToSelf();
    if ( v9 )
    {
      IsCallerSystem = -2147024891;
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v9);
    }
  }
  else
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", IsCallerSystem, "CheckCallerCredibility");
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v13);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v11);
  return (unsigned int)IsCallerSystem;
}

```

## disassembly

```asm
0x1800489c0  push    rbp
0x1800489c2  push    rbx
0x1800489c3  push    rdi
0x1800489c4  mov     rbp, rsp
0x1800489c7  sub     rsp, 20h
0x1800489cb  mov     rbx, rcx
0x1800489ce  mov     [rbp+arg_8], 0
0x1800489d6  mov     [rbp+arg_18], 0
0x1800489de  mov     [rbp+TokenHandle], 0
0x1800489e6  xor     ecx, ecx; BindingHandle
0x1800489e8  call    cs:__imp_RpcImpersonateClient
0x1800489ee  mov     edi, eax
0x1800489f0  test    eax, eax
0x1800489f2  jle     short loc_1800489FD
0x1800489f4  movzx   edi, ax
0x1800489f7  or      edi, 80070000h
0x1800489fd  test    edi, edi
0x1800489ff  jns     short loc_180048A21
0x180048a01  lea     r9, aCheckcallercre_0; "CheckCallerCredibility"
0x180048a08  mov     r8d, edi
0x180048a0b  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180048a12  mov     ecx, 8; int
0x180048a17  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180048a1c  jmp     loc_180048B4B
0x180048a21  mov     rax, [rbx]
0x180048a24  lea     rdx, [rbp+arg_8]
0x180048a28  mov     rcx, rbx
0x180048a2b  mov     rax, [rax+60h]
0x180048a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a34  test    eax, eax
0x180048a36  js      loc_180048B0A
0x180048a3c  cmp     [rbp+arg_8], 0
0x180048a41  jz      loc_180048B0A
0x180048a47  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x180048a4c  mov     edi, eax
0x180048a4e  test    eax, eax
0x180048a50  jz      loc_180048B1D
0x180048a56  call    cs:__imp_GetCurrentThread
0x180048a5c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180048a60  mov     edx, 0Eh; DesiredAccess
0x180048a65  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180048a69  mov     rcx, rax; ThreadHandle
0x180048a6c  call    cs:__imp_OpenThreadToken
0x180048a72  test    eax, eax
0x180048a74  jnz     short loc_180048AAC
0x180048a76  call    cs:__imp_GetLastError
0x180048a7c  mov     edi, eax
0x180048a7e  test    eax, eax
0x180048a80  jle     short loc_180048A8B
0x180048a82  movzx   edi, ax
0x180048a85  or      edi, 80070000h
0x180048a8b  test    edi, edi
0x180048a8d  jns     short loc_180048AAC
0x180048a8f  mov     r8d, edi
0x180048a92  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180048a99  lea     r9, aCheckcallercre_0; "CheckCallerCredibility"
0x180048aa0  mov     ecx, 8; int
0x180048aa5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180048aaa  jmp     short loc_180048B1D
0x180048aac  lea     rcx, [rbp+arg_18]; struct IUserName **
0x180048ab0  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x180048ab5  mov     edi, eax
0x180048ab7  test    eax, eax
0x180048ab9  jns     short loc_180048AC7
0x180048abb  mov     r8d, eax
0x180048abe  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x180048ac5  jmp     short loc_180048A99
0x180048ac7  mov     rbx, [rbp+arg_18]
0x180048acb  mov     rax, [rbx]
0x180048ace  xor     r8d, r8d
0x180048ad1  mov     rdx, [rbp+TokenHandle]
0x180048ad5  mov     rcx, rbx
0x180048ad8  mov     rax, [rax+18h]
0x180048adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ae1  mov     edi, eax
0x180048ae3  test    eax, eax
0x180048ae5  jns     short loc_180048AF3
0x180048ae7  mov     r8d, eax
0x180048aea  lea     rdx, aPtrusernameIni; "ptrUserName->Initialize failed: 0x%x in"...
0x180048af1  jmp     short loc_180048A99
0x180048af3  mov     rcx, [rbp+arg_8]
0x180048af7  mov     rax, [rcx]
0x180048afa  mov     rdx, rbx
0x180048afd  mov     rax, [rax+20h]
0x180048b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b06  mov     edi, eax
0x180048b08  jmp     short loc_180048B1D
0x180048b0a  lea     rdx, aCheckcallercre; "CheckCallerCredibiltiy, the session is "...
0x180048b11  mov     ecx, 1; int
0x180048b16  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180048b1b  xor     edi, edi
0x180048b1d  call    cs:__imp_RpcRevertToSelf
0x180048b23  test    eax, eax
0x180048b25  jz      short loc_180048B4B
0x180048b27  mov     edi, 80070005h
0x180048b2c  jle     short loc_180048B36
0x180048b2e  movzx   eax, ax
0x180048b31  or      eax, 80070000h
0x180048b36  mov     r8d, eax
0x180048b39  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x180048b40  mov     ecx, 8; int
0x180048b45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180048b4a  nop
0x180048b4b  mov     rcx, [rbp+TokenHandle]; hObject
0x180048b4f  test    rcx, rcx
0x180048b52  jz      short loc_180048B5B
0x180048b54  call    cs:__imp_CloseHandle
0x180048b5a  nop
0x180048b5b  lea     rcx, [rbp+arg_18]
0x180048b5f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180048b64  nop
0x180048b65  lea     rcx, [rbp+arg_8]
0x180048b69  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180048b6e  mov     eax, edi
0x180048b70  add     rsp, 20h
0x180048b74  pop     rdi
0x180048b75  pop     rbx
0x180048b76  pop     rbp
0x180048b77  retn
```
