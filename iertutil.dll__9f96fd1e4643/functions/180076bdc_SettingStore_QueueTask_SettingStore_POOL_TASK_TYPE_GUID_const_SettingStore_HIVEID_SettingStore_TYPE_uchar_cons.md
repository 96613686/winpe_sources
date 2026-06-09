# SettingStore::_QueueTask(SettingStore::POOL_TASK_TYPE,_GUID const *,SettingStore::HIVEID,SettingStore::TYPE,uchar const *,ulong,tagSAFEARRAY *)

- ea: `0x180076bdc`
- end: `0x180076db1`
- name: `?_QueueTask@SettingStore@@YAJW4POOL_TASK_TYPE@1@PEBU_GUID@@W4HIVEID@1@W4TYPE@1@PEBEKPEAUtagSAFEARRAY@@@Z`
- size: `469`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180075c28`
- `0x180075e5c`
- `0x180076050`
- `0x180076204`
- `0x18007649c`
- `0x1800766c0`

## callees

- `0x180022eb0`
- `0x180025c18`
- `0x1800323f0`
- `0x180075b30`
- `0x180076a08`
- `0x180076bdc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180076d4c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180076d4c`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180076cb4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180076cb4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!InSendMessage` at `0x180076c00`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!InSendMessage` at `0x180076c00`

## pseudocode

```c
__int64 __fastcall SettingStore::_QueueTask(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  HRESULT ErrorError; // ebx
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // rax
  int v13; // eax
  unsigned int v14; // edx
  SettingStore::POOL_TASK *v15; // rdi
  struct IBrowsingEnvironment *v16; // rax
  __int64 v18; // [rsp+50h] [rbp-28h] BYREF
  struct IEUserBroker *v19; // [rsp+58h] [rbp-20h] BYREF
  LPUNKNOWN pUnk; // [rsp+60h] [rbp-18h] BYREF
  LPSTREAM ppStm; // [rsp+68h] [rbp-10h] BYREF

  ppStm = 0;
  if ( InSendMessage() )
    goto LABEL_21;
  pUnk = 0;
  v19 = 0;
  ErrorError = CoCreateUserBroker(&v19);
  if ( ErrorError >= 0 )
  {
    v18 = 0;
    ErrorError = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v19 + 48LL))(
                   v19,
                   &CLSID_CSettingsBroker,
                   &IID_IUnknown,
                   &v18);
    if ( ErrorError >= 0 )
    {
      ErrorError = (**(__int64 (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))v18)(
                     v18,
                     &GUID_ea77e0bc_3ce7_4cc1_928f_6f50a0ce5487,
                     &pUnk);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v19 + 16LL))(v19);
    if ( ErrorError >= 0 )
    {
      ErrorError = CoMarshalInterThreadInterfaceInStream(&IID_ISettingsBroker, pUnk, &ppStm);
      ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      if ( ErrorError >= 0 )
      {
LABEL_21:
        pUnk = 0;
        ErrorError = SettingStore::_CreateTask(a1, a2, a3, a4, a5, a6, a7, ppStm, &pUnk);
        if ( ErrorError >= 0 )
        {
          CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
          v13 = (*(__int64 (__fastcall **)(struct IBrowsingEnvironment *))(*(_QWORD *)CorrectBrowsingEnvironment + 72LL))(CorrectBrowsingEnvironment);
          v15 = (SettingStore::POOL_TASK *)pUnk;
          ErrorError = v13;
          if ( v13 < 0 )
            goto LABEL_14;
          if ( TrySubmitThreadpoolCallback(SettingStore::TaskWorkerCallback, pUnk, 0) )
          {
            ErrorError = 0;
          }
          else
          {
            ErrorError = HRESULTFromLastErrorError();
            if ( ErrorError < 0 )
            {
              v16 = GetCorrectBrowsingEnvironment();
              (*(void (__fastcall **)(struct IBrowsingEnvironment *))(*(_QWORD *)v16 + 80LL))(v16);
LABEL_14:
              if ( v15 )
                SettingStore::POOL_TASK::`scalar deleting destructor'(v15, v14);
              goto LABEL_16;
            }
          }
          v15 = 0;
          goto LABEL_14;
        }
      }
    }
  }
LABEL_16:
  if ( ppStm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x180076bdc  push    rbp
0x180076bde  push    rbx
0x180076bdf  push    rsi
0x180076be0  push    rdi
0x180076be1  push    r14
0x180076be3  push    r15
0x180076be5  mov     rbp, rsp
0x180076be8  sub     rsp, 78h
0x180076bec  mov     edi, r9d
0x180076bef  mov     [rbp+ppStm], 0
0x180076bf7  mov     esi, r8d
0x180076bfa  mov     r14, rdx
0x180076bfd  mov     r15d, ecx
0x180076c00  call    cs:__imp_InSendMessage
0x180076c06  test    eax, eax
0x180076c08  jnz     loc_180076CD4
0x180076c0e  lea     rcx, [rbp+var_20]; struct IEUserBroker **
0x180076c12  mov     [rbp+pUnk], 0
0x180076c1a  mov     [rbp+var_20], 0
0x180076c22  call    ?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180076c27  mov     ebx, eax
0x180076c29  test    eax, eax
0x180076c2b  js      loc_180076D8D
0x180076c31  mov     rcx, [rbp+var_20]
0x180076c35  lea     r9, [rbp+var_28]
0x180076c39  mov     [rbp+var_28], 0
0x180076c41  lea     r8, IID_IUnknown
0x180076c48  lea     rdx, CLSID_CSettingsBroker
0x180076c4f  mov     rax, [rcx]
0x180076c52  mov     rax, [rax+30h]
0x180076c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c5b  mov     ebx, eax
0x180076c5d  test    eax, eax
0x180076c5f  js      short loc_180076C8D
0x180076c61  mov     rcx, [rbp+var_28]
0x180076c65  lea     r8, [rbp+pUnk]
0x180076c69  lea     rdx, _GUID_ea77e0bc_3ce7_4cc1_928f_6f50a0ce5487
0x180076c70  mov     rax, [rcx]
0x180076c73  mov     rax, [rax]
0x180076c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c7b  mov     rcx, [rbp+var_28]
0x180076c7f  mov     ebx, eax
0x180076c81  mov     rax, [rcx]
0x180076c84  mov     rax, [rax+10h]
0x180076c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c8d  mov     rcx, [rbp+var_20]
0x180076c91  mov     rax, [rcx]
0x180076c94  mov     rax, [rax+10h]
0x180076c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c9d  test    ebx, ebx
0x180076c9f  js      loc_180076D8D
0x180076ca5  mov     rdx, [rbp+pUnk]; pUnk
0x180076ca9  lea     r8, [rbp+ppStm]; ppStm
0x180076cad  lea     rcx, IID_ISettingsBroker; riid
0x180076cb4  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180076cba  mov     rcx, [rbp+pUnk]
0x180076cbe  mov     ebx, eax
0x180076cc0  mov     rax, [rcx]
0x180076cc3  mov     rax, [rax+10h]
0x180076cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ccc  test    ebx, ebx
0x180076cce  js      loc_180076D8D
0x180076cd4  lea     rax, [rbp+pUnk]
0x180076cd8  mov     [rbp+pUnk], 0
0x180076ce0  mov     [rsp+78h+var_38], rax
0x180076ce5  mov     r9d, edi
0x180076ce8  mov     rax, [rbp+ppStm]
0x180076cec  mov     r8d, esi
0x180076cef  mov     [rsp+78h+var_40], rax
0x180076cf4  mov     rdx, r14
0x180076cf7  mov     rax, [rbp+arg_30]
0x180076cfb  mov     ecx, r15d
0x180076cfe  mov     [rsp+78h+var_48], rax
0x180076d03  mov     eax, [rbp+arg_28]
0x180076d06  mov     [rsp+78h+var_50], eax
0x180076d0a  mov     rax, [rbp+arg_20]
0x180076d0e  mov     [rsp+78h+var_58], rax
0x180076d13  call    ?_CreateTask@SettingStore@@YAJW4POOL_TASK_TYPE@1@PEBU_GUID@@W4HIVEID@1@W4TYPE@1@PEBEKPEAUtagSAFEARRAY@@PEAUIStream@@PEAPEAUPOOL_TASK@1@@Z; SettingStore::_CreateTask(SettingStore::POOL_TASK_TYPE,_GUID const *,SettingStore::HIVEID,SettingStore::TYPE,uchar const *,ulong,tagSAFEARRAY *,IStream *,SettingStore::POOL_TASK * *)
0x180076d18  mov     ebx, eax
0x180076d1a  test    eax, eax
0x180076d1c  js      short loc_180076D8D
0x180076d1e  call    ?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x180076d23  mov     rdx, rax
0x180076d26  mov     rcx, [rax]
0x180076d29  mov     rax, [rcx+48h]
0x180076d2d  mov     rcx, rdx
0x180076d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d35  mov     rdi, [rbp+pUnk]
0x180076d39  mov     ebx, eax
0x180076d3b  test    eax, eax
0x180076d3d  js      short loc_180076D80
0x180076d3f  xor     r8d, r8d; pcbe
0x180076d42  lea     rcx, ?TaskWorkerCallback@SettingStore@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180076d49  mov     rdx, rdi; pv
0x180076d4c  call    cs:__imp_TrySubmitThreadpoolCallback
0x180076d52  test    eax, eax
0x180076d54  jz      short loc_180076D5A
0x180076d56  xor     ebx, ebx
0x180076d58  jmp     short loc_180076D65
0x180076d5a  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180076d5f  mov     ebx, eax
0x180076d61  test    eax, eax
0x180076d63  js      short loc_180076D69
0x180076d65  xor     edi, edi
0x180076d67  jmp     short loc_180076D80
0x180076d69  call    ?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x180076d6e  mov     rdx, rax
0x180076d71  mov     rcx, [rax]
0x180076d74  mov     rax, [rcx+50h]
0x180076d78  mov     rcx, rdx
0x180076d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d80  test    rdi, rdi
0x180076d83  jz      short loc_180076D8D
0x180076d85  mov     rcx, rdi; this
0x180076d88  call    ??_GPOOL_TASK@SettingStore@@QEAAPEAXI@Z; SettingStore::POOL_TASK::`scalar deleting destructor'(uint)
0x180076d8d  mov     rcx, [rbp+ppStm]
0x180076d91  test    rcx, rcx
0x180076d94  jz      short loc_180076DA2
0x180076d96  mov     rax, [rcx]
0x180076d99  mov     rax, [rax+10h]
0x180076d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076da2  mov     eax, ebx
0x180076da4  add     rsp, 78h
0x180076da8  pop     r15
0x180076daa  pop     r14
0x180076dac  pop     rdi
0x180076dad  pop     rsi
0x180076dae  pop     rbx
0x180076daf  pop     rbp
0x180076db0  retn
```
