# CSpWmiMethod<_SPACES_StorageTier_DeleteObject>::RunMethod<CSpStorageTier::DeleteObject,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18010223c`
- end: `0x1801025b9`
- name: `??$RunMethod@VDeleteObject@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
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
- `0x18010223c`
- `0x180103ed0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010241a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010241a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801023ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801023ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010240a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010240a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801023cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801023cf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801024c4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801024c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102583`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010256f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010256f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_DeleteObject>::RunMethod<CSpStorageTier::DeleteObject,12>(
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
  CSpStorageTier::DeleteObject *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::DeleteObject *)operator new(0x160u);
  v7 = CSpStorageTier::DeleteObject::DeleteObject(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18034067F,
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
0x18010223c  mov     [rsp-38h+arg_18], rbx
0x180102241  push    rbp
0x180102242  push    rsi
0x180102243  push    rdi
0x180102244  push    r12
0x180102246  push    r13
0x180102248  push    r14
0x18010224a  push    r15
0x18010224c  mov     rbp, rsp
0x18010224f  sub     rsp, 80h
0x180102256  mov     rax, cs:__security_cookie
0x18010225d  xor     rax, rsp
0x180102260  mov     [rbp+var_8], rax
0x180102264  xor     eax, eax
0x180102266  mov     rsi, rcx
0x180102269  xorps   xmm0, xmm0
0x18010226c  mov     [rbp+var_10], eax
0x18010226f  mov     ecx, 160h; Size
0x180102274  mov     [rbp+var_40], eax
0x180102277  movups  [rbp+var_20], xmm0
0x18010227b  mov     [rbp+TokenHandle], rax
0x18010227f  mov     r12, r8
0x180102282  mov     r13, rdx
0x180102285  xor     r14d, r14d
0x180102288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010228d  mov     rcx, rax; this
0x180102290  mov     [rbp+var_28], rax
0x180102294  call    ??0DeleteObject@CSpStorageTier@@QEAA@XZ; CSpStorageTier::DeleteObject::DeleteObject(void)
0x180102299  mov     rdi, rax
0x18010229c  test    rax, rax
0x18010229f  jnz     short loc_1801022A9
0x1801022a1  lea     ebx, [rax+1Bh]
0x1801022a4  jmp     loc_180102566
0x1801022a9  mov     rax, [rax]
0x1801022ac  mov     rdx, rsi
0x1801022af  mov     rcx, rdi
0x1801022b2  xor     r15d, r15d
0x1801022b5  mov     rax, [rax+8]
0x1801022b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801022be  lea     rcx, [rbp+var_40]
0x1801022c2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801022c7  mov     [rdi+1Ch], eax
0x1801022ca  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1801022ce  mov     ecx, [rsi+14h]; unsigned int
0x1801022d1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801022d6  mov     eax, cs:dword_18039EB68
0x1801022dc  cmp     eax, 5
0x1801022df  jbe     short loc_18010234F
0x1801022e1  mov     rdx, 400000000000h
0x1801022eb  lea     rcx, dword_18039EB68
0x1801022f2  call    _tlgKeywordOn
0x1801022f7  test    al, al
0x1801022f9  jz      short loc_18010234F
0x1801022fb  mov     eax, [rbp+var_40]
0x1801022fe  lea     rdx, byte_18034067F
0x180102305  xor     ecx, ecx
0x180102307  cmp     [rdi+1Ch], eax
0x18010230a  movzx   eax, word ptr [rbp+var_10]
0x18010230e  mov     word ptr [rbp+var_40], ax
0x180102312  setnz   cl
0x180102315  mov     eax, [rsi+14h]
0x180102318  mov     [rbp+var_38], eax
0x18010231b  lea     rax, [rbp+var_20]
0x18010231f  mov     [rbp+var_28], rax
0x180102323  lea     rax, [rbp+var_3C]
0x180102327  mov     [rsp+80h+var_48], rax
0x18010232c  lea     rax, [rbp+var_40]
0x180102330  mov     [rsp+80h+var_50], rax
0x180102335  lea     rax, [rbp+var_38]
0x180102339  mov     [rsp+80h+var_58], rax
0x18010233e  lea     rax, [rbp+var_28]
0x180102342  mov     [rsp+80h+var_60], rax
0x180102347  mov     [rbp+var_3C], ecx
0x18010234a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18010234f  mov     rcx, [rsi]
0x180102352  test    rcx, rcx
0x180102355  jz      loc_18010253C
0x18010235b  mov     rax, [rcx]
0x18010235e  test    rax, rax
0x180102361  jz      loc_18010253C
0x180102367  mov     rax, [rax+18h]
0x18010236b  lea     r8, [rdi+20h]
0x18010236f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180102376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010237b  mov     ebx, eax
0x18010237d  test    eax, eax
0x18010237f  jnz     loc_180102541
0x180102385  cmp     [rsi+10h], r14d
0x180102389  jz      loc_1801024D5
0x18010238f  lea     rbx, [rdi+148h]
0x180102396  mov     rcx, rbx
0x180102399  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18010239e  mov     rcx, rbx; struct CSpJobMgr **
0x1801023a1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1801023a6  test    eax, eax
0x1801023a8  jnz     short loc_1801023B2
0x1801023aa  lea     ebx, [rax+1Ch]
0x1801023ad  jmp     loc_180102541
0x1801023b2  mov     ecx, 10h; Size
0x1801023b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801023bc  xor     r8d, r8d; pcbe
0x1801023bf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801023c6  mov     rdx, rax; pv
0x1801023c9  mov     r15, rax
0x1801023cc  mov     [rax], rdi
0x1801023cf  call    cs:__imp_CreateThreadpoolWork
0x1801023d6  nop     dword ptr [rax+rax+00h]
0x1801023db  mov     r14, rax
0x1801023de  test    rax, rax
0x1801023e1  jnz     short loc_1801023EF
0x1801023e3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1801023e8  mov     ebx, eax
0x1801023ea  jmp     loc_180102541
0x1801023ef  call    cs:__imp_GetCurrentThread
0x1801023f6  nop     dword ptr [rax+rax+00h]
0x1801023fb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1801023ff  xor     r8d, r8d; OpenAsSelf
0x180102402  mov     rcx, rax; ThreadHandle
0x180102405  mov     edx, 2000Ch; DesiredAccess
0x18010240a  call    cs:__imp_OpenThreadToken
0x180102411  nop     dword ptr [rax+rax+00h]
0x180102416  test    eax, eax
0x180102418  jnz     short loc_18010242D
0x18010241a  call    cs:__imp_GetLastError
0x180102421  nop     dword ptr [rax+rax+00h]
0x180102426  cmp     eax, 3F0h
0x18010242b  jnz     short loc_1801023E3
0x18010242d  mov     rax, [rbp+TokenHandle]
0x180102431  mov     r8, r13
0x180102434  mov     [r15+8], rax
0x180102438  mov     rcx, rdi
0x18010243b  mov     rax, [rdi]
0x18010243e  mov     rdx, [rsi+8]
0x180102442  mov     rax, [rax+18h]
0x180102446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010244b  mov     rax, [rdi]
0x18010244e  mov     rdx, r12
0x180102451  mov     rcx, rdi
0x180102454  mov     rax, [rax+28h]
0x180102458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010245d  mov     ebx, eax
0x18010245f  test    eax, eax
0x180102461  jz      short loc_18010246C
0x180102463  cmp     eax, 7
0x180102466  jnz     loc_180102541
0x18010246c  mov     rax, [rdi]
0x18010246f  mov     rdx, r12
0x180102472  mov     rcx, rdi
0x180102475  mov     rax, [rax+38h]
0x180102479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010247e  mov     ebx, eax
0x180102480  test    eax, eax
0x180102482  jnz     loc_180102541
0x180102488  mov     rax, [rdi+150h]
0x18010248f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180102496  jnz     short loc_1801024AC
0x180102498  mov     rax, [rdi+158h]
0x18010249f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801024a6  jz      loc_180102541
0x1801024ac  mov     rdx, r12
0x1801024af  mov     rcx, rdi
0x1801024b2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1801024b7  mov     ebx, eax
0x1801024b9  test    eax, eax
0x1801024bb  jnz     loc_180102541
0x1801024c1  mov     rcx, r14; pwk
0x1801024c4  call    cs:__imp_SubmitThreadpoolWork
0x1801024cb  nop     dword ptr [rax+rax+00h]
0x1801024d0  jmp     loc_18010258F
0x1801024d5  mov     rax, [rdi]
0x1801024d8  mov     r8, r13
0x1801024db  mov     rdx, [rsi+8]
0x1801024df  mov     rcx, rdi
0x1801024e2  mov     rax, [rax+10h]
0x1801024e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801024eb  mov     rax, [rdi]
0x1801024ee  mov     rdx, r12
0x1801024f1  mov     rcx, rdi
0x1801024f4  mov     rax, [rax+30h]
0x1801024f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801024fd  mov     ebx, eax
0x1801024ff  test    eax, eax
0x180102501  jz      short loc_180102508
0x180102503  cmp     eax, 7
0x180102506  jnz     short loc_180102541
0x180102508  mov     rax, [rdi]
0x18010250b  mov     rdx, r12
0x18010250e  mov     rcx, rdi
0x180102511  mov     rax, [rax+28h]
0x180102515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010251a  mov     ebx, eax
0x18010251c  test    eax, eax
0x18010251e  jz      short loc_180102525
0x180102520  cmp     eax, 7
0x180102523  jnz     short loc_180102541
0x180102525  mov     rax, [rdi]
0x180102528  mov     rdx, r12
0x18010252b  mov     rcx, rdi
0x18010252e  mov     rax, [rax+38h]
0x180102532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102537  jmp     loc_1801023E8
0x18010253c  mov     ebx, 4
0x180102541  mov     rax, [rdi]
0x180102544  mov     edx, 1
0x180102549  mov     rcx, rdi
0x18010254c  mov     rax, [rax]
0x18010254f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102554  test    r15, r15
0x180102557  jz      short loc_180102566
0x180102559  mov     edx, 10h
0x18010255e  mov     rcx, r15; Block
0x180102561  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180102566  mov     rcx, [rbp+TokenHandle]; hObject
0x18010256a  test    rcx, rcx
0x18010256d  jz      short loc_18010257B
0x18010256f  call    cs:__imp_CloseHandle
0x180102576  nop     dword ptr [rax+rax+00h]
0x18010257b  test    r14, r14
0x18010257e  jz      short loc_18010258F
0x180102580  mov     rcx, r14; pwk
0x180102583  call    cs:__imp_CloseThreadpoolWork
0x18010258a  nop     dword ptr [rax+rax+00h]
0x18010258f  mov     eax, ebx
0x180102591  mov     rcx, [rbp+var_8]
0x180102595  xor     rcx, rsp; StackCookie
0x180102598  call    __security_check_cookie
0x18010259d  mov     rbx, [rsp+80h+arg_18]
0x1801025a5  add     rsp, 80h
0x1801025ac  pop     r15
0x1801025ae  pop     r14
0x1801025b0  pop     r13
0x1801025b2  pop     r12
0x1801025b4  pop     rdi
0x1801025b5  pop     rsi
0x1801025b6  pop     rbp
0x1801025b7  retn
```
