# NamedPipeAdaptor::SetTargetProcess(ulong)

- ea: `0x14002dd30`
- end: `0x14002df62`
- name: `?SetTargetProcess@NamedPipeAdaptor@@QEAAJK@Z`
- size: `562`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002ca50`

## callees

- `0x140002018`
- `0x140006058`
- `0x140006344`
- `0x140008188`
- `0x14002cc10`
- `0x14002dca4`
- `0x14002dd30`
- `0x140032690`
- `0x140032754`
- `0x140032880`
- `0x140032a64`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002df49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002df49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002dd50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14002dd50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ddbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002de66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ddbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002de66`

## string_xrefs

- `0x14002dd83`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002de37`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002ddf5`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`
- `0x14002de9f`: `clientcore\termsrv\rdpplatform\common\rdpsid\rdpsid.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::SetTargetProcess(RTL_SRWLOCK *this, DWORD a2)
{
  RTL_SRWLOCK *v2; // r15
  const char *v5; // rax
  __int64 v6; // rdx
  int v7; // ebx
  PVOID Ptr; // rbx
  int ProcessToken; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  PVOID v12; // rbx
  int IntegrityLevelSid; // eax
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v19; // [rsp+20h] [rbp-20h]
  const char *v20; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *TokenHandle; // [rsp+70h] [rbp+30h] BYREF
  const unsigned __int16 *ModeName; // [rsp+80h] [rbp+40h] BYREF
  __int64 v24; // [rsp+88h] [rbp+48h] BYREF

  v2 = this + 7;
  AcquireSRWLockExclusive(this + 7);
  if ( LODWORD(this[8].Ptr) != 1 )
  {
    v5 = "SetTargetProcess can only be called on a pipe server";
    v6 = 154;
LABEL_5:
    v7 = -2147019873;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)0x8007139FLL,
      (int)v5,
      v20);
    goto LABEL_30;
  }
  if ( LODWORD(this[24].Ptr) )
  {
    v5 = "SetTargetProcess must be called before initializing the pipe";
    v6 = 155;
    goto LABEL_5;
  }
  Ptr = this[19].Ptr;
  if ( Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&TokenHandle);
    LocalFree(Ptr);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&TokenHandle);
  }
  this[19].Ptr = 0;
  TokenHandle = 0;
  ProcessToken = GetProcessToken(a2, &TokenHandle);
  v7 = ProcessToken;
  if ( ProcessToken < 0 )
  {
    v10 = 87;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
      (const char *)(unsigned int)ProcessToken,
      v19);
    goto LABEL_14;
  }
  ProcessToken = GetAppContainerSid(TokenHandle, &this[19].Ptr);
  v7 = ProcessToken;
  if ( ProcessToken < 0 )
  {
    v10 = 88;
    goto LABEL_10;
  }
  v7 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v7 < 0 )
  {
    v11 = 157;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)(unsigned int)v7,
      v19);
    goto LABEL_30;
  }
  v12 = this[20].Ptr;
  if ( v12 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&TokenHandle);
    LocalFree(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&TokenHandle);
  }
  this[20].Ptr = 0;
  TokenHandle = 0;
  IntegrityLevelSid = GetProcessToken(a2, &TokenHandle);
  v7 = IntegrityLevelSid;
  if ( IntegrityLevelSid < 0 )
  {
    v14 = 109;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\rdpsid\\rdpsid.cpp",
      (const char *)(unsigned int)IntegrityLevelSid,
      v19);
    goto LABEL_25;
  }
  IntegrityLevelSid = GetIntegrityLevelSid(TokenHandle, &this[20].Ptr);
  v7 = IntegrityLevelSid;
  if ( IntegrityLevelSid < 0 )
  {
    v14 = 110;
    goto LABEL_21;
  }
  v7 = 0;
LABEL_25:
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v7 < 0 )
  {
    v11 = 158;
    goto LABEL_16;
  }
  LODWORD(this[18].Ptr) = a2;
  if ( (unsigned int)dword_140088090 > 5 )
  {
    LODWORD(TokenHandle) = this[18].Ptr;
    ModeName = NamedPipeAdaptor::GetModeName((NamedPipeAdaptor *)this);
    v24 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this[6].Ptr + 6))(this + 6);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v15,
      (unsigned int)byte_14007FEA9,
      v16,
      v17,
      (__int64)&v24,
      (__int64)&ModeName,
      (__int64)&TokenHandle);
  }
  v7 = 0;
LABEL_30:
  ReleaseSRWLockExclusive(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002dd30  mov     [rsp-28h+arg_8], rbx
0x14002dd35  push    rbp
0x14002dd36  push    rsi
0x14002dd37  push    rdi
0x14002dd38  push    r14
0x14002dd3a  push    r15
0x14002dd3c  mov     rbp, rsp
0x14002dd3f  sub     rsp, 40h
0x14002dd43  lea     r15, [rcx+38h]
0x14002dd47  mov     rdi, rcx
0x14002dd4a  mov     rcx, r15; SRWLock
0x14002dd4d  mov     r14d, edx
0x14002dd50  call    cs:__imp_AcquireSRWLockExclusive
0x14002dd56  cmp     dword ptr [rdi+40h], 1
0x14002dd5a  jz      short loc_14002DD6A
0x14002dd5c  lea     rax, aSettargetproce_0; "SetTargetProcess can only be called on "...
0x14002dd63  mov     edx, 9Ah
0x14002dd68  jmp     short loc_14002DD7F
0x14002dd6a  cmp     dword ptr [rdi+0C0h], 0
0x14002dd71  jz      short loc_14002DDA1
0x14002dd73  lea     rax, aSettargetproce; "SetTargetProcess must be called before "...
0x14002dd7a  mov     edx, 9Bh; void *
0x14002dd7f  mov     rcx, [rbp+28h]; this
0x14002dd83  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002dd8a  mov     ebx, 8007139Fh
0x14002dd8f  mov     qword ptr [rsp+40h+var_20], rax; int
0x14002dd94  mov     r9d, ebx; char *
0x14002dd97  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14002dd9c  jmp     loc_14002DF46
0x14002dda1  lea     rsi, [rdi+98h]
0x14002dda8  mov     rbx, [rsi]
0x14002ddab  test    rbx, rbx
0x14002ddae  jz      short loc_14002DDCB
0x14002ddb0  lea     rcx, [rbp+TokenHandle]; this
0x14002ddb4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002ddb9  mov     rcx, rbx; hMem
0x14002ddbc  call    cs:__imp_LocalFree
0x14002ddc2  lea     rcx, [rbp+TokenHandle]; this
0x14002ddc6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002ddcb  lea     rdx, [rbp+TokenHandle]; TokenHandle
0x14002ddcf  mov     qword ptr [rsi], 0
0x14002ddd6  mov     ecx, r14d; dwProcessId
0x14002ddd9  mov     [rbp+TokenHandle], 0
0x14002dde1  call    ?GetProcessToken@@YAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; GetProcessToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x14002dde6  mov     ebx, eax
0x14002dde8  test    eax, eax
0x14002ddea  jns     short loc_14002DE06
0x14002ddec  mov     edx, 57h ; 'W'; void *
0x14002ddf1  mov     rcx, [rbp+28h]; this
0x14002ddf5  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002ddfc  mov     r9d, eax; char *
0x14002ddff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002de04  jmp     short loc_14002DE21
0x14002de06  mov     rcx, [rbp+TokenHandle]; void *
0x14002de0a  mov     rdx, rsi; void **
0x14002de0d  call    ?GetAppContainerSid@@YAJPEAXPEAPEAX@Z; GetAppContainerSid(void *,void * *)
0x14002de12  mov     ebx, eax
0x14002de14  test    eax, eax
0x14002de16  jns     short loc_14002DE1F
0x14002de18  mov     edx, 58h ; 'X'
0x14002de1d  jmp     short loc_14002DDF1
0x14002de1f  xor     ebx, ebx
0x14002de21  lea     rcx, [rbp+TokenHandle]
0x14002de25  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002de2a  test    ebx, ebx
0x14002de2c  jns     short loc_14002DE4B
0x14002de2e  mov     edx, 9Dh; void *
0x14002de33  mov     rcx, [rbp+28h]; this
0x14002de37  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002de3e  mov     r9d, ebx; char *
0x14002de41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002de46  jmp     loc_14002DF46
0x14002de4b  lea     rsi, [rdi+0A0h]
0x14002de52  mov     rbx, [rsi]
0x14002de55  test    rbx, rbx
0x14002de58  jz      short loc_14002DE75
0x14002de5a  lea     rcx, [rbp+TokenHandle]; this
0x14002de5e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002de63  mov     rcx, rbx; hMem
0x14002de66  call    cs:__imp_LocalFree
0x14002de6c  lea     rcx, [rbp+TokenHandle]; this
0x14002de70  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002de75  lea     rdx, [rbp+TokenHandle]; TokenHandle
0x14002de79  mov     qword ptr [rsi], 0
0x14002de80  mov     ecx, r14d; dwProcessId
0x14002de83  mov     [rbp+TokenHandle], 0
0x14002de8b  call    ?GetProcessToken@@YAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; GetProcessToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x14002de90  mov     ebx, eax
0x14002de92  test    eax, eax
0x14002de94  jns     short loc_14002DEB0
0x14002de96  mov     edx, 6Dh ; 'm'; void *
0x14002de9b  mov     rcx, [rbp+28h]; this
0x14002de9f  lea     r8, aClientcoreTerm_1; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002dea6  mov     r9d, eax; char *
0x14002dea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002deae  jmp     short loc_14002DECB
0x14002deb0  mov     rcx, [rbp+TokenHandle]; void *
0x14002deb4  mov     rdx, rsi; void **
0x14002deb7  call    ?GetIntegrityLevelSid@@YAJPEAXPEAPEAX@Z; GetIntegrityLevelSid(void *,void * *)
0x14002debc  mov     ebx, eax
0x14002debe  test    eax, eax
0x14002dec0  jns     short loc_14002DEC9
0x14002dec2  mov     edx, 6Eh ; 'n'
0x14002dec7  jmp     short loc_14002DE9B
0x14002dec9  xor     ebx, ebx
0x14002decb  lea     rcx, [rbp+TokenHandle]
0x14002decf  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002ded4  test    ebx, ebx
0x14002ded6  jns     short loc_14002DEE2
0x14002ded8  mov     edx, 9Eh
0x14002dedd  jmp     loc_14002DE33
0x14002dee2  mov     [rdi+90h], r14d
0x14002dee9  mov     eax, cs:dword_140088090
0x14002deef  cmp     eax, 5
0x14002def2  jbe     short loc_14002DF44
0x14002def4  mov     eax, [rdi+90h]
0x14002defa  mov     rcx, rdi; this
0x14002defd  mov     dword ptr [rbp+TokenHandle], eax
0x14002df00  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002df05  mov     [rbp+arg_10], rax
0x14002df09  lea     rcx, [rdi+30h]
0x14002df0d  mov     rax, [rcx]
0x14002df10  mov     rax, [rax+30h]
0x14002df14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002df19  mov     [rbp+arg_18], rax
0x14002df1d  lea     rdx, byte_14007FEA9
0x14002df24  lea     rax, [rbp+TokenHandle]
0x14002df28  mov     [rsp+40h+var_10], rax
0x14002df2d  lea     rax, [rbp+arg_10]
0x14002df31  mov     [rsp+40h+var_18], rax
0x14002df36  lea     rax, [rbp+arg_18]
0x14002df3a  mov     qword ptr [rsp+40h+var_20], rax
0x14002df3f  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14002df44  xor     ebx, ebx
0x14002df46  mov     rcx, r15; SRWLock
0x14002df49  call    cs:__imp_ReleaseSRWLockExclusive
0x14002df4f  mov     eax, ebx
0x14002df51  mov     rbx, [rsp+40h+arg_8]
0x14002df56  add     rsp, 40h
0x14002df5a  pop     r15
0x14002df5c  pop     r14
0x14002df5e  pop     rdi
0x14002df5f  pop     rsi
0x14002df60  pop     rbp
0x14002df61  retn
```
