# CreateTaskForUser(ushort const *,ITaskDefinition * *,ITaskFolder * *,ushort const *,ushort const *)

- ea: `0x180016b88`
- end: `0x180016c9f`
- name: `?CreateTaskForUser@@YAJPEBGPEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@00@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct ITaskDefinition **, struct ITaskFolder **, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ac08`

## callees

- `0x18000aab8`
- `0x180011d5c`
- `0x180012ed4`
- `0x180016b88`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016c87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016c87`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016bae`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016bae`

## string_xrefs

- `0x180016bb9`: `CreateTaskForUser`

## pseudocode

```c
__int64 __fastcall CreateTaskForUser(
        unsigned __int16 *a1,
        struct ITaskDefinition **a2,
        struct ITaskFolder **a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  HRESULT v8; // edi
  int Task; // ebx
  struct ITaskDefinition *v10; // rcx
  struct ITaskFolder *v11; // rcx
  int v13[2]; // [rsp+70h] [rbp-11h] BYREF
  int v14[2]; // [rsp+78h] [rbp-9h] BYREF
  int v15[2]; // [rsp+80h] [rbp-1h] BYREF
  int v16[2]; // [rsp+88h] [rbp+7h] BYREF
  _QWORD v17[8]; // [rsp+90h] [rbp+Fh] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp+77h] BYREF

  v18 = a4;
  v8 = CoInitializeEx(0, 0);
  LODWORD(v18) = v8;
  v17[0] = "CreateTaskForUser";
  v17[1] = &v18;
  *(_QWORD *)v16 = 0;
  *(_QWORD *)v14 = 0;
  *(_QWORD *)v13 = 0;
  *(_QWORD *)v15 = 0;
  Task = CreateTask(v16, (__int64 *)v14, v13, v15, 0, a1, 0, a5, 0, 1, 0, 0, 0);
  LODWORD(v18) = Task;
  if ( Task >= 0 )
  {
    v10 = *(struct ITaskDefinition **)v13;
    *(_QWORD *)v13 = 0;
    *a2 = v10;
    v11 = *(struct ITaskFolder **)v14;
    *(_QWORD *)v14 = 0;
    *a3 = v11;
  }
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v15);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v13);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)v14);
  if ( *(_QWORD *)v16 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 16LL))(*(_QWORD *)v16);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v17);
  if ( v8 >= 0 )
    CoUninitialize();
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x180016b88  mov     [rsp-8+arg_18], r9
0x180016b8d  push    rbp
0x180016b8e  push    rbx
0x180016b8f  push    rsi
0x180016b90  push    rdi
0x180016b91  push    r14
0x180016b93  push    r15
0x180016b95  lea     rbp, [rsp-27h]
0x180016b9a  sub     rsp, 0A8h
0x180016ba1  mov     rsi, r8
0x180016ba4  mov     r14, rdx
0x180016ba7  mov     rbx, rcx
0x180016baa  xor     edx, edx; dwCoInit
0x180016bac  xor     ecx, ecx; pvReserved
0x180016bae  call    cs:__imp_CoInitializeEx
0x180016bb4  mov     edi, eax
0x180016bb6  mov     dword ptr [rbp+4Fh+arg_18], eax
0x180016bb9  lea     rax, aCreatetaskforu; "CreateTaskForUser"
0x180016bc0  mov     [rbp+4Fh+var_40], rax
0x180016bc4  lea     rax, [rbp+4Fh+arg_18]
0x180016bc8  mov     [rbp+4Fh+var_38], rax
0x180016bcc  xor     r15d, r15d
0x180016bcf  mov     qword ptr [rbp+4Fh+var_48], r15
0x180016bd3  mov     qword ptr [rbp+4Fh+var_58], r15
0x180016bd7  mov     qword ptr [rbp+4Fh+var_60], r15
0x180016bdb  mov     qword ptr [rbp+4Fh+var_50], r15
0x180016bdf  mov     [rsp+0D0h+var_70], r15d; int
0x180016be4  mov     [rsp+0D0h+var_78], r15d; int
0x180016be9  mov     [rsp+0D0h+var_80], r15d; int
0x180016bee  mov     [rsp+0D0h+var_88], 1; int
0x180016bf6  mov     [rsp+0D0h+var_90], r15d; int
0x180016bfb  mov     rax, [rbp+4Fh+arg_20]
0x180016bff  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x180016c04  mov     [rsp+0D0h+var_A0], r15; unsigned __int16 *
0x180016c09  mov     [rsp+0D0h+var_A8], rbx; unsigned __int16 *
0x180016c0e  mov     [rsp+0D0h+var_B0], r15; unsigned __int16 *
0x180016c13  lea     r9, [rbp+4Fh+var_50]; int
0x180016c17  lea     r8, [rbp+4Fh+var_60]; int
0x180016c1b  lea     rdx, [rbp+4Fh+var_58]; int
0x180016c1f  lea     rcx, [rbp+4Fh+var_48]; int
0x180016c23  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180016c28  mov     ebx, eax
0x180016c2a  mov     dword ptr [rbp+4Fh+arg_18], eax
0x180016c2d  test    eax, eax
0x180016c2f  js      short loc_180016C47
0x180016c31  mov     rcx, qword ptr [rbp+4Fh+var_60]
0x180016c35  mov     qword ptr [rbp+4Fh+var_60], r15
0x180016c39  mov     [r14], rcx
0x180016c3c  mov     rcx, qword ptr [rbp+4Fh+var_58]
0x180016c40  mov     qword ptr [rbp+4Fh+var_58], r15
0x180016c44  mov     [rsi], rcx
0x180016c47  lea     rcx, [rbp+4Fh+var_50]
0x180016c4b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016c50  nop
0x180016c51  lea     rcx, [rbp+4Fh+var_60]
0x180016c55  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016c5a  nop
0x180016c5b  lea     rcx, [rbp+4Fh+var_58]
0x180016c5f  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180016c64  nop
0x180016c65  mov     rcx, qword ptr [rbp+4Fh+var_48]
0x180016c69  test    rcx, rcx
0x180016c6c  jz      short loc_180016C7A
0x180016c6e  mov     rax, [rcx]
0x180016c71  mov     rax, [rax+10h]
0x180016c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c7a  lea     rcx, [rbp+4Fh+var_40]; this
0x180016c7e  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180016c83  test    edi, edi
0x180016c85  js      short loc_180016C8D
0x180016c87  call    cs:__imp_CoUninitialize
0x180016c8d  mov     eax, ebx
0x180016c8f  add     rsp, 0A8h
0x180016c96  pop     r15
0x180016c98  pop     r14
0x180016c9a  pop     rdi
0x180016c9b  pop     rsi
0x180016c9c  pop     rbx
0x180016c9d  pop     rbp
0x180016c9e  retn
```
