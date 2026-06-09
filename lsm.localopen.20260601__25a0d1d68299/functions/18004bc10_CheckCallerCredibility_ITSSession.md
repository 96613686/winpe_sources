# CheckCallerCredibility(ITSSession *)

- ea: `0x18004bc10`
- end: `0x18004bde1`
- name: `?CheckCallerCredibility@@YAJPEAUITSSession@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(struct ITSSession *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18005e678`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x180011440`
- `0x180012650`
- `0x1800163b4`
- `0x18004bc10`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004bcc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004bcc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004bcac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004bcac`
- `RPCRT4!RpcImpersonateClient` at `0x18004bc38`
- `RPCRT4!RpcImpersonateClient` at `0x18004bc38`
- `RPCRT4!RpcRevertToSelf` at `0x18004bd85`
- `RPCRT4!RpcRevertToSelf` at `0x18004bd85`

## string_xrefs

- `0x18004bcfa`: `OpenThreadToken failed: 0x%x in %s`
- `0x18004bc61`: `RpcImpersonateClient failed: 0x%x in %s`

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
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v13);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v11);
  return (unsigned int)IsCallerSystem;
}

```

## disassembly

```asm
0x18004bc10  push    rbp
0x18004bc12  push    rbx
0x18004bc13  push    rdi
0x18004bc14  mov     rbp, rsp
0x18004bc17  sub     rsp, 20h
0x18004bc1b  mov     rbx, rcx
0x18004bc1e  mov     [rbp+arg_8], 0
0x18004bc26  mov     [rbp+arg_18], 0
0x18004bc2e  mov     [rbp+TokenHandle], 0
0x18004bc36  xor     ecx, ecx; BindingHandle
0x18004bc38  call    cs:__imp_RpcImpersonateClient
0x18004bc3f  nop     dword ptr [rax+rax+00h]
0x18004bc44  mov     edi, eax
0x18004bc46  test    eax, eax
0x18004bc48  jle     short loc_18004BC53
0x18004bc4a  movzx   edi, ax
0x18004bc4d  or      edi, 80070000h
0x18004bc53  test    edi, edi
0x18004bc55  jns     short loc_18004BC77
0x18004bc57  lea     r9, aCheckcallercre_0; "CheckCallerCredibility"
0x18004bc5e  mov     r8d, edi
0x18004bc61  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18004bc68  mov     ecx, 8; int
0x18004bc6d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004bc72  jmp     loc_18004BDB9
0x18004bc77  mov     rax, [rbx]
0x18004bc7a  lea     rdx, [rbp+arg_8]
0x18004bc7e  mov     rcx, rbx
0x18004bc81  mov     rax, [rax+60h]
0x18004bc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc8a  test    eax, eax
0x18004bc8c  js      loc_18004BD72
0x18004bc92  cmp     [rbp+arg_8], 0
0x18004bc97  jz      loc_18004BD72
0x18004bc9d  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x18004bca2  mov     edi, eax
0x18004bca4  test    eax, eax
0x18004bca6  jz      loc_18004BD85
0x18004bcac  call    cs:__imp_GetCurrentThread
0x18004bcb3  nop     dword ptr [rax+rax+00h]
0x18004bcb8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004bcbc  mov     edx, 0Eh; DesiredAccess
0x18004bcc1  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18004bcc5  mov     rcx, rax; ThreadHandle
0x18004bcc8  call    cs:__imp_OpenThreadToken
0x18004bccf  nop     dword ptr [rax+rax+00h]
0x18004bcd4  test    eax, eax
0x18004bcd6  jnz     short loc_18004BD14
0x18004bcd8  call    cs:__imp_GetLastError
0x18004bcdf  nop     dword ptr [rax+rax+00h]
0x18004bce4  mov     edi, eax
0x18004bce6  test    eax, eax
0x18004bce8  jle     short loc_18004BCF3
0x18004bcea  movzx   edi, ax
0x18004bced  or      edi, 80070000h
0x18004bcf3  test    edi, edi
0x18004bcf5  jns     short loc_18004BD14
0x18004bcf7  mov     r8d, edi
0x18004bcfa  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x18004bd01  lea     r9, aCheckcallercre_0; "CheckCallerCredibility"
0x18004bd08  mov     ecx, 8; int
0x18004bd0d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004bd12  jmp     short loc_18004BD85
0x18004bd14  lea     rcx, [rbp+arg_18]; struct IUserName **
0x18004bd18  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18004bd1d  mov     edi, eax
0x18004bd1f  test    eax, eax
0x18004bd21  jns     short loc_18004BD2F
0x18004bd23  mov     r8d, eax
0x18004bd26  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18004bd2d  jmp     short loc_18004BD01
0x18004bd2f  mov     rbx, [rbp+arg_18]
0x18004bd33  mov     rax, [rbx]
0x18004bd36  xor     r8d, r8d
0x18004bd39  mov     rdx, [rbp+TokenHandle]
0x18004bd3d  mov     rcx, rbx
0x18004bd40  mov     rax, [rax+18h]
0x18004bd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd49  mov     edi, eax
0x18004bd4b  test    eax, eax
0x18004bd4d  jns     short loc_18004BD5B
0x18004bd4f  mov     r8d, eax
0x18004bd52  lea     rdx, aPtrusernameIni; "ptrUserName->Initialize failed: 0x%x in"...
0x18004bd59  jmp     short loc_18004BD01
0x18004bd5b  mov     rcx, [rbp+arg_8]
0x18004bd5f  mov     rax, [rcx]
0x18004bd62  mov     rdx, rbx
0x18004bd65  mov     rax, [rax+20h]
0x18004bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd6e  mov     edi, eax
0x18004bd70  jmp     short loc_18004BD85
0x18004bd72  lea     rdx, aCheckcallercre; "CheckCallerCredibiltiy, the session is "...
0x18004bd79  mov     ecx, 1; int
0x18004bd7e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004bd83  xor     edi, edi
0x18004bd85  call    cs:__imp_RpcRevertToSelf
0x18004bd8c  nop     dword ptr [rax+rax+00h]
0x18004bd91  test    eax, eax
0x18004bd93  jz      short loc_18004BDB9
0x18004bd95  mov     edi, 80070005h
0x18004bd9a  jle     short loc_18004BDA4
0x18004bd9c  movzx   eax, ax
0x18004bd9f  or      eax, 80070000h
0x18004bda4  mov     r8d, eax
0x18004bda7  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18004bdae  mov     ecx, 8; int
0x18004bdb3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004bdb8  nop
0x18004bdb9  lea     rcx, [rbp+TokenHandle]; this
0x18004bdbd  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18004bdc2  nop
0x18004bdc3  lea     rcx, [rbp+arg_18]
0x18004bdc7  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004bdcc  nop
0x18004bdcd  lea     rcx, [rbp+arg_8]
0x18004bdd1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004bdd6  mov     eax, edi
0x18004bdd8  add     rsp, 20h
0x18004bddc  pop     rdi
0x18004bddd  pop     rbx
0x18004bdde  pop     rbp
0x18004bddf  retn
```
