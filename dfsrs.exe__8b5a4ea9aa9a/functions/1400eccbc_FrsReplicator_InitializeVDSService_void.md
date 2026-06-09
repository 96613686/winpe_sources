# FrsReplicator::InitializeVDSService(void)

- ea: `0x1400eccbc`
- end: `0x1400ecfe1`
- name: `?InitializeVDSService@FrsReplicator@@QEAAPEAVFrsStatus@@XZ`
- size: `805`
- prototype: `struct FrsStatus *__fastcall(FrsReplicator *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400ec46c`
- `0x14013fce0`

## callees

- `0x1400036d0`
- `0x14000be44`
- `0x14000d980`
- `0x14000dcc0`
- `0x1400eccbc`
- `0x14013ed28`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400ecd45`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecdbb`
- `KERNEL32!GetCurrentThreadId` at `0x1400ece20`
- `KERNEL32!GetCurrentThreadId` at `0x1400eced0`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecf6c`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecd45`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecdbb`
- `KERNEL32!GetCurrentThreadId` at `0x1400ece20`
- `KERNEL32!GetCurrentThreadId` at `0x1400eced0`
- `KERNEL32!GetCurrentThreadId` at `0x1400ecf6c`
- `ole32!CoCreateInstance` at `0x1400ecd1c`
- `ole32!CoCreateInstance` at `0x1400ecd1c`

## string_xrefs

- `0x1400ecd30`: `FrsReplicator::InitializeVDSService`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct FrsStatus *__fastcall FrsReplicator::InitializeVDSService(FrsReplicator *this)
{
  __int64 v2; // rbx
  HRESULT v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  unsigned int *v6; // rdi
  struct IVdsService **v7; // r14
  int v8; // edi
  DWORD v9; // eax
  __int64 v10; // rcx
  int v11; // edi
  DWORD v12; // eax
  __int64 v13; // rcx
  VdsAdviseSink *v14; // rax
  int v15; // edi
  DWORD v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  _BYTE v23[72]; // [rsp+50h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+8h] BYREF
  VdsAdviseSink *v25; // [rsp+A8h] [rbp+10h]

  ScopedLock::ScopedLock((ScopedLock *)v23, (FrsReplicator *)((char *)this + 600));
  v2 = 0;
  if ( !*((_DWORD *)this + 149) )
  {
    ppv = 0;
    v3 = CoCreateInstance(&CLSID_VdsLoader, 0, 0x17u, &IID_IVdsServiceLoader, &ppv);
    if ( v3 < 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = v3 & 0x1FFF0000;
      if ( (_DWORD)v5 == 458752 )
        v3 = (unsigned __int16)v3;
      v6 = (unsigned int *)FrsStatusList::PushNewError(
                             v5,
                             (unsigned int)v3,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                             "FrsReplicator::InitializeVDSService",
                             4908,
                             CurrentThreadId,
                             0);
      if ( v6 )
        goto LABEL_29;
    }
    v7 = (struct IVdsService **)((char *)this + 664);
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)ppv + 24LL))(ppv, 0, (char *)this + 664);
    if ( v8 < 0 )
    {
      v9 = GetCurrentThreadId();
      v10 = v8 & 0x1FFF0000;
      if ( (_DWORD)v10 == 458752 )
        v8 = (unsigned __int16)v8;
      v6 = (unsigned int *)FrsStatusList::PushNewError(
                             v10,
                             (unsigned int)v8,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                             "FrsReplicator::InitializeVDSService",
                             4919,
                             v9,
                             0);
      if ( v6 )
        goto LABEL_29;
    }
    v11 = ((__int64 (__fastcall *)(struct IVdsService *))(*v7)->lpVtbl->WaitForServiceReady)(*v7);
    if ( v11 < 0 )
    {
      v12 = GetCurrentThreadId();
      v13 = v11 & 0x1FFF0000;
      if ( (_DWORD)v13 == 458752 )
        v11 = (unsigned __int16)v11;
      v6 = (unsigned int *)FrsStatusList::PushNewError(
                             v13,
                             (unsigned int)v11,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                             "FrsReplicator::InitializeVDSService",
                             4930,
                             v12,
                             0);
      if ( v6 )
        goto LABEL_29;
    }
    v25 = (VdsAdviseSink *)operator new(0x48u);
    v14 = VdsAdviseSink::VdsAdviseSink(v25, this, *v7);
    *((_QWORD *)this + 82) = v14;
    (*(void (__fastcall **)(VdsAdviseSink *))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = ((__int64 (__fastcall *)(struct IVdsService *, _QWORD, char *))(*v7)->lpVtbl->Advise)(
            *v7,
            *((_QWORD *)this + 82),
            (char *)this + 592);
    if ( v15 >= 0 )
      goto LABEL_24;
    v16 = GetCurrentThreadId();
    v17 = v15 & 0x1FFF0000;
    if ( (_DWORD)v17 == 458752 )
      v15 = (unsigned __int16)v15;
    v6 = (unsigned int *)FrsStatusList::PushNewError(
                           v17,
                           (unsigned int)v15,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                           "FrsReplicator::InitializeVDSService",
                           4942,
                           v16,
                           0);
    if ( v6 )
    {
LABEL_29:
      if ( *((_QWORD *)this + 83) )
      {
        v18 = *((_QWORD *)this + 82);
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          *((_QWORD *)this + 82) = 0;
        }
        v19 = *((_QWORD *)this + 83);
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          *((_QWORD *)this + 83) = 0;
        }
      }
      v20 = GetCurrentThreadId();
      v2 = FrsStatusList::PushNewError(
             v21,
             v6[1],
             v6[2],
             *v6,
             "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
             "FrsReplicator::InitializeVDSService",
             4970,
             v20,
             v6);
    }
    else
    {
LABEL_24:
      *((_DWORD *)this + 149) = 1;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  }
  ScopedLock::~ScopedLock((ScopedLock *)v23);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x1400eccbc  mov     [rsp+arg_10], rbx
0x1400eccc1  push    rbp
0x1400eccc2  push    rsi
0x1400eccc3  push    rdi
0x1400eccc4  push    r12
0x1400eccc6  push    r13
0x1400eccc8  push    r14
0x1400eccca  push    r15
0x1400ecccc  sub     rsp, 60h
0x1400eccd0  mov     rsi, rcx
0x1400eccd3  lea     rdx, [rcx+258h]; struct ScopedCS *
0x1400eccda  lea     rcx, [rsp+98h+var_48]; this
0x1400eccdf  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1400ecce4  nop
0x1400ecce5  xor     ebx, ebx
0x1400ecce7  cmp     [rsi+254h], ebx
0x1400ecced  jnz     loc_1400ECFBB
0x1400eccf3  mov     [rsp+98h+arg_0], rbx
0x1400eccfb  lea     rax, [rsp+98h+arg_0]
0x1400ecd03  mov     [rsp+98h+ppv], rax; ppv
0x1400ecd08  lea     r9, IID_IVdsServiceLoader; riid
0x1400ecd0f  xor     edx, edx; pUnkOuter
0x1400ecd11  lea     r8d, [rbx+17h]; dwClsContext
0x1400ecd15  lea     rcx, CLSID_VdsLoader; rclsid
0x1400ecd1c  call    cs:__imp_CoCreateInstance
0x1400ecd23  nop     dword ptr [rax+rax+00h]
0x1400ecd28  mov     edi, eax
0x1400ecd2a  mov     r13d, 1FFF0000h
0x1400ecd30  lea     r15, aFrsreplicatorI_4; "FrsReplicator::InitializeVDSService"
0x1400ecd37  lea     r12, aBaseFsRemotefs_28; "base\\fs\\remotefs\\frs\\src\\sync\\frs"...
0x1400ecd3e  lea     ebp, [rbx+1]
0x1400ecd41  test    eax, eax
0x1400ecd43  jns     short loc_1400ECD95
0x1400ecd45  call    cs:__imp_GetCurrentThreadId
0x1400ecd4c  nop     dword ptr [rax+rax+00h]
0x1400ecd51  mov     ecx, edi
0x1400ecd53  and     ecx, r13d
0x1400ecd56  cmp     ecx, 70000h
0x1400ecd5c  jnz     short loc_1400ECD61
0x1400ecd5e  movzx   edi, di
0x1400ecd61  mov     [rsp+98h+var_58], rbx
0x1400ecd66  mov     [rsp+98h+var_60], eax
0x1400ecd6a  mov     [rsp+98h+var_68], 132Ch
0x1400ecd72  mov     [rsp+98h+var_70], r15
0x1400ecd77  mov     [rsp+98h+ppv], r12
0x1400ecd7c  mov     r9d, ebp
0x1400ecd7f  xor     r8d, r8d
0x1400ecd82  mov     edx, edi
0x1400ecd84  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ecd89  mov     rdi, rax
0x1400ecd8c  test    rax, rax
0x1400ecd8f  jnz     loc_1400ECF20
0x1400ecd95  mov     rcx, [rsp+98h+arg_0]
0x1400ecd9d  mov     rax, [rcx]
0x1400ecda0  lea     r14, [rsi+298h]
0x1400ecda7  mov     r8, r14
0x1400ecdaa  xor     edx, edx
0x1400ecdac  mov     rax, [rax+18h]
0x1400ecdb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ecdb5  mov     edi, eax
0x1400ecdb7  test    eax, eax
0x1400ecdb9  jns     short loc_1400ECE0B
0x1400ecdbb  call    cs:__imp_GetCurrentThreadId
0x1400ecdc2  nop     dword ptr [rax+rax+00h]
0x1400ecdc7  mov     ecx, edi
0x1400ecdc9  and     ecx, r13d
0x1400ecdcc  cmp     ecx, 70000h
0x1400ecdd2  jnz     short loc_1400ECDD7
0x1400ecdd4  movzx   edi, di
0x1400ecdd7  mov     [rsp+98h+var_58], rbx
0x1400ecddc  mov     [rsp+98h+var_60], eax
0x1400ecde0  mov     [rsp+98h+var_68], 1337h
0x1400ecde8  mov     [rsp+98h+var_70], r15
0x1400ecded  mov     [rsp+98h+ppv], r12
0x1400ecdf2  mov     r9d, ebp
0x1400ecdf5  xor     r8d, r8d
0x1400ecdf8  mov     edx, edi
0x1400ecdfa  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ecdff  mov     rdi, rax
0x1400ece02  test    rax, rax
0x1400ece05  jnz     loc_1400ECF20
0x1400ece0b  mov     rcx, [r14]
0x1400ece0e  mov     rax, [rcx]
0x1400ece11  mov     rax, [rax+20h]
0x1400ece15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ece1a  mov     edi, eax
0x1400ece1c  test    eax, eax
0x1400ece1e  jns     short loc_1400ECE70
0x1400ece20  call    cs:__imp_GetCurrentThreadId
0x1400ece27  nop     dword ptr [rax+rax+00h]
0x1400ece2c  mov     ecx, edi
0x1400ece2e  and     ecx, r13d
0x1400ece31  cmp     ecx, 70000h
0x1400ece37  jnz     short loc_1400ECE3C
0x1400ece39  movzx   edi, di
0x1400ece3c  mov     [rsp+98h+var_58], rbx
0x1400ece41  mov     [rsp+98h+var_60], eax
0x1400ece45  mov     [rsp+98h+var_68], 1342h
0x1400ece4d  mov     [rsp+98h+var_70], r15
0x1400ece52  mov     [rsp+98h+ppv], r12
0x1400ece57  mov     r9d, ebp
0x1400ece5a  xor     r8d, r8d
0x1400ece5d  mov     edx, edi
0x1400ece5f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ece64  mov     rdi, rax
0x1400ece67  test    rax, rax
0x1400ece6a  jnz     loc_1400ECF20
0x1400ece70  mov     ecx, 48h ; 'H'; Size
0x1400ece75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400ece7a  mov     [rsp+98h+arg_8], rax
0x1400ece82  mov     r8, [r14]; struct IVdsService *
0x1400ece85  mov     rdx, rsi; struct FrsReplicator *
0x1400ece88  mov     rcx, rax; this
0x1400ece8b  call    ??0VdsAdviseSink@@QEAA@PEAVFrsReplicator@@PEAUIVdsService@@@Z; VdsAdviseSink::VdsAdviseSink(FrsReplicator *,IVdsService *)
0x1400ece90  mov     rdx, rax
0x1400ece93  mov     [rsi+290h], rax
0x1400ece9a  mov     rcx, [rax]
0x1400ece9d  mov     rax, [rcx+8]
0x1400ecea1  mov     rcx, rdx
0x1400ecea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ecea9  mov     rcx, [r14]
0x1400eceac  mov     rax, [rcx]
0x1400eceaf  lea     r8, [rsi+250h]
0x1400eceb6  mov     rdx, [rsi+290h]
0x1400ecebd  mov     rax, [rax+78h]
0x1400ecec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ecec6  mov     edi, eax
0x1400ecec8  test    eax, eax
0x1400ececa  jns     loc_1400ECFA7
0x1400eced0  call    cs:__imp_GetCurrentThreadId
0x1400eced7  nop     dword ptr [rax+rax+00h]
0x1400ecedc  mov     ecx, edi
0x1400ecede  and     ecx, r13d
0x1400ecee1  cmp     ecx, 70000h
0x1400ecee7  jnz     short loc_1400ECEEC
0x1400ecee9  movzx   edi, di
0x1400eceec  mov     [rsp+98h+var_58], rbx
0x1400ecef1  mov     [rsp+98h+var_60], eax
0x1400ecef5  mov     [rsp+98h+var_68], 134Eh
0x1400ecefd  mov     [rsp+98h+var_70], r15
0x1400ecf02  mov     [rsp+98h+ppv], r12
0x1400ecf07  mov     r9d, ebp
0x1400ecf0a  xor     r8d, r8d
0x1400ecf0d  mov     edx, edi
0x1400ecf0f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ecf14  mov     rdi, rax
0x1400ecf17  test    rax, rax
0x1400ecf1a  jz      loc_1400ECFA7
0x1400ecf20  cmp     [rsi+298h], rbx
0x1400ecf27  jz      short loc_1400ECF67
0x1400ecf29  mov     rcx, [rsi+290h]
0x1400ecf30  test    rcx, rcx
0x1400ecf33  jz      short loc_1400ECF48
0x1400ecf35  mov     rax, [rcx]
0x1400ecf38  mov     rax, [rax+10h]
0x1400ecf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ecf41  mov     [rsi+290h], rbx
0x1400ecf48  mov     rcx, [rsi+298h]
0x1400ecf4f  test    rcx, rcx
0x1400ecf52  jz      short loc_1400ECF67
0x1400ecf54  mov     rax, [rcx]
0x1400ecf57  mov     rax, [rax+10h]
0x1400ecf5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ecf60  mov     [rsi+298h], rbx
0x1400ecf67  test    rdi, rdi
0x1400ecf6a  jz      short loc_1400ECFAD
0x1400ecf6c  call    cs:__imp_GetCurrentThreadId
0x1400ecf73  nop     dword ptr [rax+rax+00h]
0x1400ecf78  mov     [rsp+98h+var_58], rdi
0x1400ecf7d  mov     [rsp+98h+var_60], eax
0x1400ecf81  mov     [rsp+98h+var_68], 136Ah
0x1400ecf89  mov     [rsp+98h+var_70], r15
0x1400ecf8e  mov     [rsp+98h+ppv], r12
0x1400ecf93  mov     r9d, [rdi]
0x1400ecf96  mov     r8d, [rdi+8]
0x1400ecf9a  mov     edx, [rdi+4]
0x1400ecf9d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ecfa2  mov     rbx, rax
0x1400ecfa5  jmp     short loc_1400ECFAD
0x1400ecfa7  mov     [rsi+254h], ebp
0x1400ecfad  lea     rcx, [rsp+98h+arg_0]
0x1400ecfb5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400ecfba  nop
0x1400ecfbb  lea     rcx, [rsp+98h+var_48]; this
0x1400ecfc0  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1400ecfc5  mov     rax, rbx
0x1400ecfc8  mov     rbx, [rsp+98h+arg_10]
0x1400ecfd0  add     rsp, 60h
0x1400ecfd4  pop     r15
0x1400ecfd6  pop     r14
0x1400ecfd8  pop     r13
0x1400ecfda  pop     r12
0x1400ecfdc  pop     rdi
0x1400ecfdd  pop     rsi
0x1400ecfde  pop     rbp
0x1400ecfdf  retn
```
