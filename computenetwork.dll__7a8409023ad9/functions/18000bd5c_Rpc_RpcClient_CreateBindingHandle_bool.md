# Rpc::RpcClient::CreateBindingHandle(bool)

- ea: `0x18000bd5c`
- end: `0x18000beeb`
- name: `?CreateBindingHandle@RpcClient@Rpc@@AEAAX_N@Z`
- size: `399`
- prototype: `void __fastcall(RTL_SRWLOCK *this, char)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028bc`
- `0x180002a08`
- `0x180002b60`
- `0x180002cd0`
- `0x180002d74`
- `0x180002e18`
- `0x180002ebc`

## callees

- `0x18000bbe0`
- `0x18000bd5c`
- `0x18000bef4`
- `0x18000c0bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000be05`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000be05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bdb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bdb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bd97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bdaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bd97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000bdaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bd7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000bd7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bddd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000be9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be87`
- `RPCRT4!RpcBindingSetOption` at `0x18000be68`
- `RPCRT4!RpcBindingSetOption` at `0x18000be68`
- `RPCRT4!RpcBindingFree` at `0x18000bdd5`
- `RPCRT4!RpcBindingFree` at `0x18000be4a`
- `RPCRT4!RpcBindingFree` at `0x18000be97`
- `RPCRT4!RpcBindingFree` at `0x18000beb7`
- `RPCRT4!RpcBindingFree` at `0x18000bdd5`
- `RPCRT4!RpcBindingFree` at `0x18000be4a`
- `RPCRT4!RpcBindingFree` at `0x18000be97`
- `RPCRT4!RpcBindingFree` at `0x18000beb7`

## pseudocode

```c
void __fastcall Rpc::RpcClient::CreateBindingHandle(RTL_SRWLOCK *this, char a2)
{
  RTL_SRWLOCK *v4; // r14
  PVOID Ptr; // rsi
  DWORD LastError; // ebx
  void *v7; // rsi
  RTL_SRWLOCK *v8; // rcx
  void **v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r8d
  PVOID v12; // r15
  DWORD v13; // ebx
  unsigned int v14[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+30h] BYREF
  RPC_BINDING_HANDLE v17; // [rsp+70h] [rbp+40h] BYREF
  RTL_SRWLOCK *v18; // [rsp+78h] [rbp+48h]

  v4 = this + 1;
  AcquireSRWLockShared(this + 1);
  if ( !this->Ptr || a2 )
  {
    if ( v4 )
      ReleaseSRWLockShared(v4);
    AcquireSRWLockExclusive(v4);
    v18 = v4;
    Ptr = this->Ptr;
    if ( this->Ptr )
    {
      LastError = GetLastError();
      Binding = Ptr;
      RpcBindingFree(&Binding);
      SetLastError(LastError);
    }
    this->Ptr = 0;
    v7 = 0;
    *(_QWORD *)v14 = 0;
    v8 = this + 6;
    if ( this[9].Ptr > (PVOID)7 )
      v8 = (RTL_SRWLOCK *)v8->Ptr;
    if ( (unsigned int)_o__wcsicmp(v8, L"ncalrpc") )
      v9 = (void **)Rpc::RpcClient::CreateAnonymousCustomBindingHandle(this, &Binding);
    else
      v9 = (void **)Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle(this, &Binding);
    if ( v14 != (unsigned int *)v9 )
    {
      v7 = *v9;
      *(_QWORD *)v14 = *v9;
      *v9 = 0;
    }
    if ( Binding )
    {
      v17 = Binding;
      RpcBindingFree(&v17);
    }
    if ( BYTE4(this[19].Ptr) )
    {
      v10 = RpcBindingSetOption(v7, 0xCu, LODWORD(this[19].Ptr));
      if ( v10 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC8, v11, (const char *)v10, v14[0]);
    }
    if ( this != (RTL_SRWLOCK *)v14 )
    {
      v12 = this->Ptr;
      if ( this->Ptr )
      {
        v13 = GetLastError();
        Binding = v12;
        RpcBindingFree(&Binding);
        SetLastError(v13);
      }
      this->Ptr = v7;
      v7 = 0;
    }
    if ( v7 )
    {
      Binding = v7;
      RpcBindingFree(&Binding);
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
  else if ( v4 )
  {
    ReleaseSRWLockShared(v4);
  }
}

```

## disassembly

```asm
0x18000bd5c  mov     [rsp-28h+arg_8], rbx
0x18000bd61  push    rbp
0x18000bd62  push    rsi
0x18000bd63  push    rdi
0x18000bd64  push    r14
0x18000bd66  push    r15
0x18000bd68  mov     rbp, rsp
0x18000bd6b  sub     rsp, 30h
0x18000bd6f  mov     bl, dl
0x18000bd71  mov     rdi, rcx
0x18000bd74  lea     r14, [rcx+8]
0x18000bd78  mov     rcx, r14; SRWLock
0x18000bd7b  call    cs:__imp_AcquireSRWLockShared
0x18000bd81  cmp     qword ptr [rdi], 0
0x18000bd85  jz      short loc_18000BDA2
0x18000bd87  test    bl, bl
0x18000bd89  jnz     short loc_18000BDA2
0x18000bd8b  test    r14, r14
0x18000bd8e  jz      loc_18000BECC
0x18000bd94  mov     rcx, r14; SRWLock
0x18000bd97  call    cs:__imp_ReleaseSRWLockShared
0x18000bd9d  jmp     loc_18000BECC
0x18000bda2  test    r14, r14
0x18000bda5  jz      short loc_18000BDB0
0x18000bda7  mov     rcx, r14; SRWLock
0x18000bdaa  call    cs:__imp_ReleaseSRWLockShared
0x18000bdb0  mov     rcx, r14; SRWLock
0x18000bdb3  call    cs:__imp_AcquireSRWLockExclusive
0x18000bdb9  mov     [rbp+arg_18], r14
0x18000bdbd  mov     rsi, [rdi]
0x18000bdc0  test    rsi, rsi
0x18000bdc3  jz      short loc_18000BDE3
0x18000bdc5  call    cs:__imp_GetLastError
0x18000bdcb  mov     ebx, eax
0x18000bdcd  mov     [rbp+Binding], rsi
0x18000bdd1  lea     rcx, [rbp+Binding]; Binding
0x18000bdd5  call    cs:__imp_RpcBindingFree
0x18000bddb  mov     ecx, ebx; dwErrCode
0x18000bddd  call    cs:__imp_SetLastError
0x18000bde3  mov     qword ptr [rdi], 0
0x18000bdea  xor     esi, esi
0x18000bdec  mov     qword ptr [rbp+var_10], rsi
0x18000bdf0  lea     rcx, [rdi+30h]
0x18000bdf4  cmp     qword ptr [rcx+18h], 7
0x18000bdf9  jbe     short loc_18000BDFE
0x18000bdfb  mov     rcx, [rcx]
0x18000bdfe  lea     rdx, aNcalrpc; "ncalrpc"
0x18000be05  call    cs:__imp__o__wcsicmp
0x18000be0b  lea     rdx, [rbp+Binding]
0x18000be0f  mov     rcx, rdi
0x18000be12  test    eax, eax
0x18000be14  jnz     short loc_18000BE1D
0x18000be16  call    ?CreateIdentifyableLrpcBindingHandle@RpcClient@Rpc@@AEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Rpc::RpcClient::CreateIdentifyableLrpcBindingHandle(void)
0x18000be1b  jmp     short loc_18000BE22
0x18000be1d  call    ?CreateAnonymousCustomBindingHandle@RpcClient@Rpc@@AEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Rpc::RpcClient::CreateAnonymousCustomBindingHandle(void)
0x18000be22  lea     rcx, [rbp+var_10]
0x18000be26  cmp     rcx, rax
0x18000be29  jz      short loc_18000BE39
0x18000be2b  mov     rsi, [rax]
0x18000be2e  mov     qword ptr [rbp+var_10], rsi
0x18000be32  mov     qword ptr [rax], 0
0x18000be39  mov     rax, [rbp+Binding]
0x18000be3d  test    rax, rax
0x18000be40  jz      short loc_18000BE50
0x18000be42  mov     [rbp+arg_10], rax
0x18000be46  lea     rcx, [rbp+arg_10]; Binding
0x18000be4a  call    cs:__imp_RpcBindingFree
0x18000be50  cmp     byte ptr [rdi+9Ch], 0
0x18000be57  jz      short loc_18000BE76
0x18000be59  mov     r8d, [rdi+98h]; optionValue
0x18000be60  mov     edx, 0Ch; option
0x18000be65  mov     rcx, rsi; hBinding
0x18000be68  call    cs:__imp_RpcBindingSetOption
0x18000be6e  mov     rcx, [rbp+28h]; this
0x18000be72  test    eax, eax
0x18000be74  jnz     short loc_18000BEDD
0x18000be76  lea     rax, [rbp+var_10]
0x18000be7a  cmp     rdi, rax
0x18000be7d  jz      short loc_18000BEAA
0x18000be7f  mov     r15, [rdi]
0x18000be82  test    r15, r15
0x18000be85  jz      short loc_18000BEA5
0x18000be87  call    cs:__imp_GetLastError
0x18000be8d  mov     ebx, eax
0x18000be8f  mov     [rbp+Binding], r15
0x18000be93  lea     rcx, [rbp+Binding]; Binding
0x18000be97  call    cs:__imp_RpcBindingFree
0x18000be9d  mov     ecx, ebx; dwErrCode
0x18000be9f  call    cs:__imp_SetLastError
0x18000bea5  mov     [rdi], rsi
0x18000bea8  xor     esi, esi
0x18000beaa  test    rsi, rsi
0x18000bead  jz      short loc_18000BEBE
0x18000beaf  mov     [rbp+Binding], rsi
0x18000beb3  lea     rcx, [rbp+Binding]; Binding
0x18000beb7  call    cs:__imp_RpcBindingFree
0x18000bebd  nop
0x18000bebe  test    r14, r14
0x18000bec1  jz      short loc_18000BECC
0x18000bec3  mov     rcx, r14; SRWLock
0x18000bec6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000becc  mov     rbx, [rsp+30h+arg_8]
0x18000bed1  add     rsp, 30h
0x18000bed5  pop     r15
0x18000bed7  pop     r14
0x18000bed9  pop     rdi
0x18000beda  pop     rsi
0x18000bedb  pop     rbp
0x18000bedc  retn
0x18000bedd  mov     r9d, eax; char *
0x18000bee0  mov     edx, 0C8h; void *
0x18000bee5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
