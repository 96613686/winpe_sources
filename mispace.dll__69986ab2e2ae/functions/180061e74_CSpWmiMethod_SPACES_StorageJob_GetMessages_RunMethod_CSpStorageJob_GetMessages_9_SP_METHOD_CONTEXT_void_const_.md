# CSpWmiMethod<_SPACES_StorageJob_GetMessages>::RunMethod<CSpStorageJob::GetMessages,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180061e74`
- end: `0x18006215b`
- name: `??$RunMethod@VGetMessages@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetMessages@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180064210`

## callees

- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x180061e74`
- `0x1800627fc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061f99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061fb5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061fb5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180061f79`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180061f79`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062070`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062070`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062130`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006211c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006211c`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_GetMessages>::RunMethod<CSpStorageJob::GetMessages,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 Messages; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r14
  __int64 v11; // rcx
  enum _MI_Result v12; // eax
  HANDLE CurrentThread; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  void *TokenHandle; // [rsp+20h] [rbp-68h] BYREF
  CSpStorageJob::GetMessages *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::GetMessages *)operator new(0x178u);
  Messages = CSpStorageJob::GetMessages::GetMessages(v19);
  v8 = Messages;
  if ( Messages )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Messages + 8LL))(Messages, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v19);
    v11 = *a1;
    if ( *a1 && *(_QWORD *)v11 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v11 + 24LL))(
             v11,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_27;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_27;
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
            v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v14;
            if ( !v14 || v14 == 7 )
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
            goto LABEL_27;
          }
        }
        v12 = GleToMiResult();
        goto LABEL_11;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v15;
      if ( !v15 || v15 == 7 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v16;
        if ( !v16 || v16 == 7 )
        {
          v12 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_11:
          v9 = v12;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_27:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_29;
  }
  v9 = 27;
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x180061e74  push    rbx
0x180061e76  push    rbp
0x180061e77  push    rsi
0x180061e78  push    rdi
0x180061e79  push    r12
0x180061e7b  push    r14
0x180061e7d  push    r15
0x180061e7f  sub     rsp, 50h
0x180061e83  mov     rax, cs:__security_cookie
0x180061e8a  xor     rax, rsp
0x180061e8d  mov     [rsp+88h+var_40], rax
0x180061e92  xor     eax, eax
0x180061e94  mov     r15, rcx
0x180061e97  xorps   xmm0, xmm0
0x180061e9a  mov     [rsp+88h+var_48], eax
0x180061e9e  mov     ecx, 178h; Size
0x180061ea3  mov     [rsp+88h+TokenHandle], rax
0x180061ea8  movups  [rsp+88h+var_58], xmm0
0x180061ead  mov     rbp, r8
0x180061eb0  mov     r12, rdx
0x180061eb3  xor     esi, esi
0x180061eb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061eba  mov     rcx, rax; this
0x180061ebd  mov     [rsp+88h+var_60], rax
0x180061ec2  call    ??0GetMessages@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetMessages::GetMessages(void)
0x180061ec7  mov     rdi, rax
0x180061eca  test    rax, rax
0x180061ecd  jnz     short loc_180061ED7
0x180061ecf  lea     ebx, [rsi+1Bh]
0x180061ed2  jmp     loc_180062112
0x180061ed7  mov     rax, [rax]
0x180061eda  mov     rdx, r15
0x180061edd  mov     rcx, rdi
0x180061ee0  xor     r14d, r14d
0x180061ee3  mov     rax, [rax+8]
0x180061ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061eec  lea     rcx, [rsp+88h+var_60]
0x180061ef1  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180061ef6  mov     [rdi+1Ch], eax
0x180061ef9  mov     rcx, [r15]
0x180061efc  test    rcx, rcx
0x180061eff  jz      loc_1800620E8
0x180061f05  mov     rax, [rcx]
0x180061f08  test    rax, rax
0x180061f0b  jz      loc_1800620E8
0x180061f11  mov     rax, [rax+18h]
0x180061f15  lea     r8, [rdi+20h]
0x180061f19  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180061f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f25  mov     ebx, eax
0x180061f27  test    eax, eax
0x180061f29  jnz     loc_1800620ED
0x180061f2f  cmp     [r15+10h], esi
0x180061f33  jz      loc_180062081
0x180061f39  lea     rbx, [rdi+148h]
0x180061f40  mov     rcx, rbx
0x180061f43  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180061f48  mov     rcx, rbx; struct CSpJobMgr **
0x180061f4b  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180061f50  test    eax, eax
0x180061f52  jnz     short loc_180061F5C
0x180061f54  lea     ebx, [rax+1Ch]
0x180061f57  jmp     loc_1800620ED
0x180061f5c  mov     ecx, 10h; Size
0x180061f61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061f66  xor     r8d, r8d; pcbe
0x180061f69  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180061f70  mov     rdx, rax; pv
0x180061f73  mov     r14, rax
0x180061f76  mov     [rax], rdi
0x180061f79  call    cs:__imp_CreateThreadpoolWork
0x180061f80  nop     dword ptr [rax+rax+00h]
0x180061f85  mov     rsi, rax
0x180061f88  test    rax, rax
0x180061f8b  jnz     short loc_180061F99
0x180061f8d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180061f92  mov     ebx, eax
0x180061f94  jmp     loc_1800620ED
0x180061f99  call    cs:__imp_GetCurrentThread
0x180061fa0  nop     dword ptr [rax+rax+00h]
0x180061fa5  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180061faa  xor     r8d, r8d; OpenAsSelf
0x180061fad  mov     rcx, rax; ThreadHandle
0x180061fb0  mov     edx, 2000Ch; DesiredAccess
0x180061fb5  call    cs:__imp_OpenThreadToken
0x180061fbc  nop     dword ptr [rax+rax+00h]
0x180061fc1  test    eax, eax
0x180061fc3  jnz     short loc_180061FD8
0x180061fc5  call    cs:__imp_GetLastError
0x180061fcc  nop     dword ptr [rax+rax+00h]
0x180061fd1  cmp     eax, 3F0h
0x180061fd6  jnz     short loc_180061F8D
0x180061fd8  mov     rax, [rsp+88h+TokenHandle]
0x180061fdd  mov     r8, r12
0x180061fe0  mov     [r14+8], rax
0x180061fe4  mov     rcx, rdi
0x180061fe7  mov     rax, [rdi]
0x180061fea  mov     rdx, [r15+8]
0x180061fee  mov     rax, [rax+18h]
0x180061ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ff7  mov     rax, [rdi]
0x180061ffa  mov     rdx, rbp
0x180061ffd  mov     rcx, rdi
0x180062000  mov     rax, [rax+28h]
0x180062004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062009  mov     ebx, eax
0x18006200b  test    eax, eax
0x18006200d  jz      short loc_180062018
0x18006200f  cmp     eax, 7
0x180062012  jnz     loc_1800620ED
0x180062018  mov     rax, [rdi]
0x18006201b  mov     rdx, rbp
0x18006201e  mov     rcx, rdi
0x180062021  mov     rax, [rax+38h]
0x180062025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006202a  mov     ebx, eax
0x18006202c  test    eax, eax
0x18006202e  jnz     loc_1800620ED
0x180062034  mov     rax, [rdi+150h]
0x18006203b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180062042  jnz     short loc_180062058
0x180062044  mov     rax, [rdi+158h]
0x18006204b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180062052  jz      loc_1800620ED
0x180062058  mov     rdx, rbp
0x18006205b  mov     rcx, rdi
0x18006205e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180062063  mov     ebx, eax
0x180062065  test    eax, eax
0x180062067  jnz     loc_1800620ED
0x18006206d  mov     rcx, rsi; pwk
0x180062070  call    cs:__imp_SubmitThreadpoolWork
0x180062077  nop     dword ptr [rax+rax+00h]
0x18006207c  jmp     loc_18006213C
0x180062081  mov     rax, [rdi]
0x180062084  mov     r8, r12
0x180062087  mov     rdx, [r15+8]
0x18006208b  mov     rcx, rdi
0x18006208e  mov     rax, [rax+10h]
0x180062092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062097  mov     rax, [rdi]
0x18006209a  mov     rdx, rbp
0x18006209d  mov     rcx, rdi
0x1800620a0  mov     rax, [rax+30h]
0x1800620a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620a9  mov     ebx, eax
0x1800620ab  test    eax, eax
0x1800620ad  jz      short loc_1800620B4
0x1800620af  cmp     eax, 7
0x1800620b2  jnz     short loc_1800620ED
0x1800620b4  mov     rax, [rdi]
0x1800620b7  mov     rdx, rbp
0x1800620ba  mov     rcx, rdi
0x1800620bd  mov     rax, [rax+28h]
0x1800620c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620c6  mov     ebx, eax
0x1800620c8  test    eax, eax
0x1800620ca  jz      short loc_1800620D1
0x1800620cc  cmp     eax, 7
0x1800620cf  jnz     short loc_1800620ED
0x1800620d1  mov     rax, [rdi]
0x1800620d4  mov     rdx, rbp
0x1800620d7  mov     rcx, rdi
0x1800620da  mov     rax, [rax+38h]
0x1800620de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620e3  jmp     loc_180061F92
0x1800620e8  mov     ebx, 4
0x1800620ed  mov     rax, [rdi]
0x1800620f0  mov     edx, 1
0x1800620f5  mov     rcx, rdi
0x1800620f8  mov     rax, [rax]
0x1800620fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062100  test    r14, r14
0x180062103  jz      short loc_180062112
0x180062105  mov     edx, 10h
0x18006210a  mov     rcx, r14; Block
0x18006210d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180062112  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180062117  test    rcx, rcx
0x18006211a  jz      short loc_180062128
0x18006211c  call    cs:__imp_CloseHandle
0x180062123  nop     dword ptr [rax+rax+00h]
0x180062128  test    rsi, rsi
0x18006212b  jz      short loc_18006213C
0x18006212d  mov     rcx, rsi; pwk
0x180062130  call    cs:__imp_CloseThreadpoolWork
0x180062137  nop     dword ptr [rax+rax+00h]
0x18006213c  mov     eax, ebx
0x18006213e  mov     rcx, [rsp+88h+var_40]
0x180062143  xor     rcx, rsp; StackCookie
0x180062146  call    __security_check_cookie
0x18006214b  add     rsp, 50h
0x18006214f  pop     r15
0x180062151  pop     r14
0x180062153  pop     r12
0x180062155  pop     rdi
0x180062156  pop     rsi
0x180062157  pop     rbp
0x180062158  pop     rbx
0x180062159  retn
```
