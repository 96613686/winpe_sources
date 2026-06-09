# CSpWmiMethod<_SPACES_VirtualDisk_Detach>::RunMethod<CSpVirtualDisk::Detach,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ddec0`
- end: `0x1800de20e`
- name: `??$RunMethod@VDetach@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Detach@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800e4700`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x1800ddec0`
- `0x1800e086c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de08c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de06d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de082`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de082`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de053`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de053`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de12c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de12c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de1df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de1df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de1d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de1d1`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Detach>::RunMethod<CSpVirtualDisk::Detach,16>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r15
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  enum _MI_Result v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v21; // [rsp+40h] [rbp-40h] BYREF
  BOOL v22; // [rsp+44h] [rbp-3Ch] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  CSpVirtualDisk::Detach *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Detach *)operator new(0x160u);
  v7 = CSpVirtualDisk::Detach::Detach(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpVirtualDisk::Detach *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180332B29,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v14 = *a1;
    if ( *a1 && *(_QWORD *)v14 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v14 + 24LL))(
             v14,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_30;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_30;
        }
        v10 = (__int64 *)operator new(0x10u);
        *v10 = v8;
        ThreadpoolWork = CreateThreadpoolWork(
                           CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                           v10,
                           0);
        if ( ThreadpoolWork )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
          {
            v10[1] = (__int64)TokenHandle;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v17;
            if ( !v17 || v17 == 7 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
              if ( !v9
                && (*(_QWORD *)(v8 + 336) != *(_QWORD *)&GUID_NULL.Data1
                 || *(_QWORD *)(v8 + 344) != *(_QWORD *)GUID_NULL.Data4) )
              {
                v9 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
                if ( !v9 )
                {
                  SubmitThreadpoolWork(ThreadpoolWork);
                  return v9;
                }
              }
            }
            goto LABEL_30;
          }
        }
        v15 = GleToMiResult();
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v18;
      if ( !v18 || v18 == 7 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v19;
        if ( !v19 || v19 == 7 )
        {
          v15 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_14:
          v9 = v15;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_30:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_32;
  }
  v9 = 27;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x1800ddec0  mov     [rsp-38h+arg_18], rbx
0x1800ddec5  push    rbp
0x1800ddec6  push    rsi
0x1800ddec7  push    rdi
0x1800ddec8  push    r12
0x1800ddeca  push    r13
0x1800ddecc  push    r14
0x1800ddece  push    r15
0x1800dded0  mov     rbp, rsp
0x1800dded3  sub     rsp, 80h
0x1800ddeda  mov     rax, cs:__security_cookie
0x1800ddee1  xor     rax, rsp
0x1800ddee4  mov     [rbp+var_8], rax
0x1800ddee8  xor     eax, eax
0x1800ddeea  mov     rsi, rcx
0x1800ddeed  xorps   xmm0, xmm0
0x1800ddef0  mov     [rbp+var_10], eax
0x1800ddef3  mov     ecx, 160h; Size
0x1800ddef8  mov     [rbp+var_40], eax
0x1800ddefb  movups  [rbp+var_20], xmm0
0x1800ddeff  mov     [rbp+TokenHandle], rax
0x1800ddf03  mov     r12, r8
0x1800ddf06  mov     r13, rdx
0x1800ddf09  xor     r14d, r14d
0x1800ddf0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ddf11  mov     rcx, rax; this
0x1800ddf14  mov     [rbp+var_28], rax
0x1800ddf18  call    ??0Detach@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Detach::Detach(void)
0x1800ddf1d  mov     rdi, rax
0x1800ddf20  test    rax, rax
0x1800ddf23  jnz     short loc_1800DDF2D
0x1800ddf25  lea     ebx, [rax+1Bh]
0x1800ddf28  jmp     loc_1800DE1C8
0x1800ddf2d  mov     rax, [rax]
0x1800ddf30  mov     rdx, rsi
0x1800ddf33  mov     rcx, rdi
0x1800ddf36  xor     r15d, r15d
0x1800ddf39  mov     rax, [rax+8]
0x1800ddf3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddf42  lea     rcx, [rbp+var_40]
0x1800ddf46  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ddf4b  mov     [rdi+1Ch], eax
0x1800ddf4e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ddf52  mov     ecx, [rsi+14h]; unsigned int
0x1800ddf55  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ddf5a  mov     eax, cs:dword_180397B68
0x1800ddf60  cmp     eax, 5
0x1800ddf63  jbe     short loc_1800DDFD3
0x1800ddf65  mov     rdx, 400000000000h
0x1800ddf6f  lea     rcx, dword_180397B68
0x1800ddf76  call    _tlgKeywordOn
0x1800ddf7b  test    al, al
0x1800ddf7d  jz      short loc_1800DDFD3
0x1800ddf7f  mov     eax, [rbp+var_40]
0x1800ddf82  lea     rdx, byte_180332B29
0x1800ddf89  xor     ecx, ecx
0x1800ddf8b  cmp     [rdi+1Ch], eax
0x1800ddf8e  movzx   eax, word ptr [rbp+var_10]
0x1800ddf92  mov     word ptr [rbp+var_40], ax
0x1800ddf96  setnz   cl
0x1800ddf99  mov     eax, [rsi+14h]
0x1800ddf9c  mov     [rbp+var_38], eax
0x1800ddf9f  lea     rax, [rbp+var_20]
0x1800ddfa3  mov     [rbp+var_28], rax
0x1800ddfa7  lea     rax, [rbp+var_3C]
0x1800ddfab  mov     [rsp+80h+var_48], rax
0x1800ddfb0  lea     rax, [rbp+var_40]
0x1800ddfb4  mov     [rsp+80h+var_50], rax
0x1800ddfb9  lea     rax, [rbp+var_38]
0x1800ddfbd  mov     [rsp+80h+var_58], rax
0x1800ddfc2  lea     rax, [rbp+var_28]
0x1800ddfc6  mov     [rsp+80h+var_60], rax
0x1800ddfcb  mov     [rbp+var_3C], ecx
0x1800ddfce  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ddfd3  mov     rcx, [rsi]
0x1800ddfd6  test    rcx, rcx
0x1800ddfd9  jz      loc_1800DE19E
0x1800ddfdf  mov     rax, [rcx]
0x1800ddfe2  test    rax, rax
0x1800ddfe5  jz      loc_1800DE19E
0x1800ddfeb  mov     rax, [rax+18h]
0x1800ddfef  lea     r8, [rdi+20h]
0x1800ddff3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ddffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddfff  mov     ebx, eax
0x1800de001  test    eax, eax
0x1800de003  jnz     loc_1800DE1A3
0x1800de009  cmp     [rsi+10h], r14d
0x1800de00d  jz      loc_1800DE137
0x1800de013  lea     rbx, [rdi+148h]
0x1800de01a  mov     rcx, rbx
0x1800de01d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800de022  mov     rcx, rbx; struct CSpJobMgr **
0x1800de025  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800de02a  test    eax, eax
0x1800de02c  jnz     short loc_1800DE036
0x1800de02e  lea     ebx, [rax+1Ch]
0x1800de031  jmp     loc_1800DE1A3
0x1800de036  mov     ecx, 10h; Size
0x1800de03b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de040  xor     r8d, r8d; pcbe
0x1800de043  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800de04a  mov     rdx, rax; pv
0x1800de04d  mov     r15, rax
0x1800de050  mov     [rax], rdi
0x1800de053  call    cs:__imp_CreateThreadpoolWork
0x1800de059  mov     r14, rax
0x1800de05c  test    rax, rax
0x1800de05f  jnz     short loc_1800DE06D
0x1800de061  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800de066  mov     ebx, eax
0x1800de068  jmp     loc_1800DE1A3
0x1800de06d  call    cs:__imp_GetCurrentThread
0x1800de073  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800de077  xor     r8d, r8d; OpenAsSelf
0x1800de07a  mov     rcx, rax; ThreadHandle
0x1800de07d  mov     edx, 2000Ch; DesiredAccess
0x1800de082  call    cs:__imp_OpenThreadToken
0x1800de088  test    eax, eax
0x1800de08a  jnz     short loc_1800DE099
0x1800de08c  call    cs:__imp_GetLastError
0x1800de092  cmp     eax, 3F0h
0x1800de097  jnz     short loc_1800DE061
0x1800de099  mov     rax, [rbp+TokenHandle]
0x1800de09d  mov     r8, r13
0x1800de0a0  mov     [r15+8], rax
0x1800de0a4  mov     rcx, rdi
0x1800de0a7  mov     rax, [rdi]
0x1800de0aa  mov     rdx, [rsi+8]
0x1800de0ae  mov     rax, [rax+18h]
0x1800de0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de0b7  mov     rax, [rdi]
0x1800de0ba  mov     rdx, r12
0x1800de0bd  mov     rcx, rdi
0x1800de0c0  mov     rax, [rax+28h]
0x1800de0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de0c9  mov     ebx, eax
0x1800de0cb  test    eax, eax
0x1800de0cd  jz      short loc_1800DE0D8
0x1800de0cf  cmp     eax, 7
0x1800de0d2  jnz     loc_1800DE1A3
0x1800de0d8  mov     rax, [rdi]
0x1800de0db  mov     rdx, r12
0x1800de0de  mov     rcx, rdi
0x1800de0e1  mov     rax, [rax+38h]
0x1800de0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de0ea  mov     ebx, eax
0x1800de0ec  test    eax, eax
0x1800de0ee  jnz     loc_1800DE1A3
0x1800de0f4  mov     rax, [rdi+150h]
0x1800de0fb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800de102  jnz     short loc_1800DE118
0x1800de104  mov     rax, [rdi+158h]
0x1800de10b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800de112  jz      loc_1800DE1A3
0x1800de118  mov     rdx, r12
0x1800de11b  mov     rcx, rdi
0x1800de11e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800de123  mov     ebx, eax
0x1800de125  test    eax, eax
0x1800de127  jnz     short loc_1800DE1A3
0x1800de129  mov     rcx, r14; pwk
0x1800de12c  call    cs:__imp_SubmitThreadpoolWork
0x1800de132  jmp     loc_1800DE1E5
0x1800de137  mov     rax, [rdi]
0x1800de13a  mov     r8, r13
0x1800de13d  mov     rdx, [rsi+8]
0x1800de141  mov     rcx, rdi
0x1800de144  mov     rax, [rax+10h]
0x1800de148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de14d  mov     rax, [rdi]
0x1800de150  mov     rdx, r12
0x1800de153  mov     rcx, rdi
0x1800de156  mov     rax, [rax+30h]
0x1800de15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de15f  mov     ebx, eax
0x1800de161  test    eax, eax
0x1800de163  jz      short loc_1800DE16A
0x1800de165  cmp     eax, 7
0x1800de168  jnz     short loc_1800DE1A3
0x1800de16a  mov     rax, [rdi]
0x1800de16d  mov     rdx, r12
0x1800de170  mov     rcx, rdi
0x1800de173  mov     rax, [rax+28h]
0x1800de177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de17c  mov     ebx, eax
0x1800de17e  test    eax, eax
0x1800de180  jz      short loc_1800DE187
0x1800de182  cmp     eax, 7
0x1800de185  jnz     short loc_1800DE1A3
0x1800de187  mov     rax, [rdi]
0x1800de18a  mov     rdx, r12
0x1800de18d  mov     rcx, rdi
0x1800de190  mov     rax, [rax+38h]
0x1800de194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de199  jmp     loc_1800DE066
0x1800de19e  mov     ebx, 4
0x1800de1a3  mov     rax, [rdi]
0x1800de1a6  mov     edx, 1
0x1800de1ab  mov     rcx, rdi
0x1800de1ae  mov     rax, [rax]
0x1800de1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de1b6  test    r15, r15
0x1800de1b9  jz      short loc_1800DE1C8
0x1800de1bb  mov     edx, 10h
0x1800de1c0  mov     rcx, r15; Block
0x1800de1c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800de1c8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800de1cc  test    rcx, rcx
0x1800de1cf  jz      short loc_1800DE1D7
0x1800de1d1  call    cs:__imp_CloseHandle
0x1800de1d7  test    r14, r14
0x1800de1da  jz      short loc_1800DE1E5
0x1800de1dc  mov     rcx, r14; pwk
0x1800de1df  call    cs:__imp_CloseThreadpoolWork
0x1800de1e5  mov     eax, ebx
0x1800de1e7  mov     rcx, [rbp+var_8]
0x1800de1eb  xor     rcx, rsp; StackCookie
0x1800de1ee  call    __security_check_cookie
0x1800de1f3  mov     rbx, [rsp+80h+arg_18]
0x1800de1fb  add     rsp, 80h
0x1800de202  pop     r15
0x1800de204  pop     r14
0x1800de206  pop     r13
0x1800de208  pop     r12
0x1800de20a  pop     rdi
0x1800de20b  pop     rsi
0x1800de20c  pop     rbp
0x1800de20d  retn
```
