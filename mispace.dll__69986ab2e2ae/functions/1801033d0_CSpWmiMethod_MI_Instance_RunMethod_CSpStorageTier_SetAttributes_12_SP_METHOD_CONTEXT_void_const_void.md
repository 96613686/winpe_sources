# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStorageTier::SetAttributes,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1801033d0`
- end: `0x180103751`
- name: `??$RunMethod@VSetAttributes@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180105a90`

## callees

- `0x180001504`
- `0x180001994`
- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x1800142e8`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x18006de84`
- `0x1801033d0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801035b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801035b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180103585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180103585`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801035a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801035a0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180103565`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180103565`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010365b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010365b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010371b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010371b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103707`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStorageTier::SetAttributes,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v6; // r14
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int128 *v8; // rdi
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  enum _MI_Result v14; // eax
  HANDLE CurrentThread; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  BOOL v21; // [rsp+44h] [rbp-3Ch] BYREF
  int v22; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+70h] [rbp-10h]

  v26 = 0;
  v20 = 0;
  v25 = 0;
  TokenHandle = 0;
  v6 = 0;
  ThreadpoolWork = 0;
  v24 = (__int128 *)operator new(0x160u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpStorageTier::SetAttributes::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_180341019,
      v9,
      v10,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v12 = *a1;
  if ( !*a1 || !*(_QWORD *)v12 )
  {
    v13 = 4;
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          (_QWORD *)v8 + 4);
  if ( !v13 )
  {
    if ( *((_DWORD *)a1 + 4) )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release((char *)v8 + 328);
      if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)v8 + 41) )
      {
        v13 = 28;
        goto LABEL_28;
      }
      v6 = (__int128 **)operator new(0x10u);
      *v6 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v6,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v6[1] = (__int128 *)TokenHandle;
          (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
          v16 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
          v13 = v16;
          if ( !v16 || v16 == 7 )
          {
            v13 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
            if ( !v13
              && (*((_QWORD *)v8 + 42) != *(_QWORD *)&GUID_NULL.Data1
               || *((_QWORD *)v8 + 43) != *(_QWORD *)GUID_NULL.Data4) )
            {
              v13 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
              if ( !v13 )
              {
                SubmitThreadpoolWork(ThreadpoolWork);
                return v13;
              }
            }
          }
          goto LABEL_28;
        }
      }
      v14 = GleToMiResult();
    }
    else
    {
      (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v17 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v13 = v17;
      if ( v17 && v17 != 7 )
        goto LABEL_28;
      v18 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
      v13 = v18;
      if ( v18 )
      {
        if ( v18 != 7 )
          goto LABEL_28;
      }
      v14 = (*(unsigned int (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
    }
    v13 = v14;
  }
LABEL_28:
  (**(void (__fastcall ***)(__int128 *, __int64))v8)(v8, 1);
  if ( v6 )
    operator delete(v6);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1801033d0  mov     [rsp-38h+arg_18], rbx
0x1801033d5  push    rbp
0x1801033d6  push    rsi
0x1801033d7  push    rdi
0x1801033d8  push    r12
0x1801033da  push    r13
0x1801033dc  push    r14
0x1801033de  push    r15
0x1801033e0  mov     rbp, rsp
0x1801033e3  sub     rsp, 80h
0x1801033ea  mov     rax, cs:__security_cookie
0x1801033f1  xor     rax, rsp
0x1801033f4  mov     [rbp+var_8], rax
0x1801033f8  xor     eax, eax
0x1801033fa  mov     r12, rcx
0x1801033fd  xorps   xmm0, xmm0
0x180103400  mov     [rbp+var_10], eax
0x180103403  mov     ecx, 160h; Size
0x180103408  mov     [rbp+var_40], eax
0x18010340b  movups  [rbp+var_20], xmm0
0x18010340f  mov     [rbp+TokenHandle], rax
0x180103413  mov     r15, r8
0x180103416  mov     r13, rdx
0x180103419  xor     r14d, r14d
0x18010341c  xor     esi, esi
0x18010341e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180103423  mov     rcx, rax
0x180103426  mov     [rbp+var_28], rax
0x18010342a  mov     rdi, rax
0x18010342d  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x180103432  lea     rax, ??_7SetAttributes@CSpStorageTier@@6B@; const CSpStorageTier::SetAttributes::`vftable'
0x180103439  mov     rdx, r12
0x18010343c  mov     [rdi], rax
0x18010343f  mov     rcx, rdi
0x180103442  mov     rax, cs:off_18020A780
0x180103449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010344e  lea     rcx, [rbp+var_40]
0x180103452  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180103457  mov     [rdi+1Ch], eax
0x18010345a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18010345e  mov     ecx, [r12+14h]; unsigned int
0x180103463  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180103468  mov     eax, cs:dword_18039EB68
0x18010346e  cmp     eax, 5
0x180103471  jbe     short loc_1801034E3
0x180103473  mov     rdx, 400000000000h
0x18010347d  lea     rcx, dword_18039EB68
0x180103484  call    _tlgKeywordOn
0x180103489  test    al, al
0x18010348b  jz      short loc_1801034E3
0x18010348d  mov     eax, [rbp+var_40]
0x180103490  lea     rdx, byte_180341019
0x180103497  xor     ecx, ecx
0x180103499  cmp     [rdi+1Ch], eax
0x18010349c  movzx   eax, word ptr [rbp+var_10]
0x1801034a0  mov     word ptr [rbp+var_40], ax
0x1801034a4  setnz   cl
0x1801034a7  mov     eax, [r12+14h]
0x1801034ac  mov     [rbp+var_38], eax
0x1801034af  lea     rax, [rbp+var_20]
0x1801034b3  mov     [rbp+var_28], rax
0x1801034b7  lea     rax, [rbp+var_3C]
0x1801034bb  mov     [rsp+80h+var_48], rax
0x1801034c0  lea     rax, [rbp+var_40]
0x1801034c4  mov     [rsp+80h+var_50], rax
0x1801034c9  lea     rax, [rbp+var_38]
0x1801034cd  mov     [rsp+80h+var_58], rax
0x1801034d2  lea     rax, [rbp+var_28]
0x1801034d6  mov     [rsp+80h+var_60], rax
0x1801034db  mov     [rbp+var_3C], ecx
0x1801034de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801034e3  mov     rcx, [r12]
0x1801034e7  test    rcx, rcx
0x1801034ea  jz      loc_1801036D4
0x1801034f0  mov     rax, [rcx]
0x1801034f3  test    rax, rax
0x1801034f6  jz      loc_1801036D4
0x1801034fc  mov     rax, [rax+18h]
0x180103500  lea     r8, [rdi+20h]
0x180103504  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18010350b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103510  mov     ebx, eax
0x180103512  test    eax, eax
0x180103514  jnz     loc_1801036D9
0x18010351a  cmp     [r12+10h], esi
0x18010351f  jz      loc_18010366C
0x180103525  lea     rbx, [rdi+148h]
0x18010352c  mov     rcx, rbx
0x18010352f  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180103534  mov     rcx, rbx; struct CSpJobMgr **
0x180103537  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18010353c  test    eax, eax
0x18010353e  jnz     short loc_180103548
0x180103540  lea     ebx, [rax+1Ch]
0x180103543  jmp     loc_1801036D9
0x180103548  mov     ecx, 10h; Size
0x18010354d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180103552  xor     r8d, r8d; pcbe
0x180103555  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18010355c  mov     rdx, rax; pv
0x18010355f  mov     r14, rax
0x180103562  mov     [rax], rdi
0x180103565  call    cs:__imp_CreateThreadpoolWork
0x18010356c  nop     dword ptr [rax+rax+00h]
0x180103571  mov     rsi, rax
0x180103574  test    rax, rax
0x180103577  jnz     short loc_180103585
0x180103579  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18010357e  mov     ebx, eax
0x180103580  jmp     loc_1801036D9
0x180103585  call    cs:__imp_GetCurrentThread
0x18010358c  nop     dword ptr [rax+rax+00h]
0x180103591  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180103595  xor     r8d, r8d; OpenAsSelf
0x180103598  mov     rcx, rax; ThreadHandle
0x18010359b  mov     edx, 2000Ch; DesiredAccess
0x1801035a0  call    cs:__imp_OpenThreadToken
0x1801035a7  nop     dword ptr [rax+rax+00h]
0x1801035ac  test    eax, eax
0x1801035ae  jnz     short loc_1801035C3
0x1801035b0  call    cs:__imp_GetLastError
0x1801035b7  nop     dword ptr [rax+rax+00h]
0x1801035bc  cmp     eax, 3F0h
0x1801035c1  jnz     short loc_180103579
0x1801035c3  mov     rax, [rbp+TokenHandle]
0x1801035c7  mov     r8, r13
0x1801035ca  mov     [r14+8], rax
0x1801035ce  mov     rcx, rdi
0x1801035d1  mov     rax, [rdi]
0x1801035d4  mov     rdx, [r12+8]
0x1801035d9  mov     rax, [rax+18h]
0x1801035dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035e2  mov     rax, [rdi]
0x1801035e5  mov     rdx, r15
0x1801035e8  mov     rcx, rdi
0x1801035eb  mov     rax, [rax+28h]
0x1801035ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035f4  mov     ebx, eax
0x1801035f6  test    eax, eax
0x1801035f8  jz      short loc_180103603
0x1801035fa  cmp     eax, 7
0x1801035fd  jnz     loc_1801036D9
0x180103603  mov     rax, [rdi]
0x180103606  mov     rdx, r15
0x180103609  mov     rcx, rdi
0x18010360c  mov     rax, [rax+38h]
0x180103610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103615  mov     ebx, eax
0x180103617  test    eax, eax
0x180103619  jnz     loc_1801036D9
0x18010361f  mov     rax, [rdi+150h]
0x180103626  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18010362d  jnz     short loc_180103643
0x18010362f  mov     rax, [rdi+158h]
0x180103636  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18010363d  jz      loc_1801036D9
0x180103643  mov     rdx, r15
0x180103646  mov     rcx, rdi
0x180103649  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18010364e  mov     ebx, eax
0x180103650  test    eax, eax
0x180103652  jnz     loc_1801036D9
0x180103658  mov     rcx, rsi; pwk
0x18010365b  call    cs:__imp_SubmitThreadpoolWork
0x180103662  nop     dword ptr [rax+rax+00h]
0x180103667  jmp     loc_180103727
0x18010366c  mov     rax, [rdi]
0x18010366f  mov     r8, r13
0x180103672  mov     rdx, [r12+8]
0x180103677  mov     rcx, rdi
0x18010367a  mov     rax, [rax+10h]
0x18010367e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103683  mov     rax, [rdi]
0x180103686  mov     rdx, r15
0x180103689  mov     rcx, rdi
0x18010368c  mov     rax, [rax+30h]
0x180103690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103695  mov     ebx, eax
0x180103697  test    eax, eax
0x180103699  jz      short loc_1801036A0
0x18010369b  cmp     eax, 7
0x18010369e  jnz     short loc_1801036D9
0x1801036a0  mov     rax, [rdi]
0x1801036a3  mov     rdx, r15
0x1801036a6  mov     rcx, rdi
0x1801036a9  mov     rax, [rax+28h]
0x1801036ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801036b2  mov     ebx, eax
0x1801036b4  test    eax, eax
0x1801036b6  jz      short loc_1801036BD
0x1801036b8  cmp     eax, 7
0x1801036bb  jnz     short loc_1801036D9
0x1801036bd  mov     rax, [rdi]
0x1801036c0  mov     rdx, r15
0x1801036c3  mov     rcx, rdi
0x1801036c6  mov     rax, [rax+38h]
0x1801036ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801036cf  jmp     loc_18010357E
0x1801036d4  mov     ebx, 4
0x1801036d9  mov     rax, [rdi]
0x1801036dc  mov     edx, 1
0x1801036e1  mov     rcx, rdi
0x1801036e4  mov     rax, [rax]
0x1801036e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801036ec  test    r14, r14
0x1801036ef  jz      short loc_1801036FE
0x1801036f1  mov     edx, 10h
0x1801036f6  mov     rcx, r14; Block
0x1801036f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801036fe  mov     rcx, [rbp+TokenHandle]; hObject
0x180103702  test    rcx, rcx
0x180103705  jz      short loc_180103713
0x180103707  call    cs:__imp_CloseHandle
0x18010370e  nop     dword ptr [rax+rax+00h]
0x180103713  test    rsi, rsi
0x180103716  jz      short loc_180103727
0x180103718  mov     rcx, rsi; pwk
0x18010371b  call    cs:__imp_CloseThreadpoolWork
0x180103722  nop     dword ptr [rax+rax+00h]
0x180103727  mov     eax, ebx
0x180103729  mov     rcx, [rbp+var_8]
0x18010372d  xor     rcx, rsp; StackCookie
0x180103730  call    __security_check_cookie
0x180103735  mov     rbx, [rsp+80h+arg_18]
0x18010373d  add     rsp, 80h
0x180103744  pop     r15
0x180103746  pop     r14
0x180103748  pop     r13
0x18010374a  pop     r12
0x18010374c  pop     rdi
0x18010374d  pop     rsi
0x18010374e  pop     rbp
0x18010374f  retn
```
