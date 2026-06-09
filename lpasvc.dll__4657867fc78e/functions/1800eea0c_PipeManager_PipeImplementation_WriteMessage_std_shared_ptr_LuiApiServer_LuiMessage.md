# PipeManager::PipeImplementation::WriteMessage(std::shared_ptr<LuiApiServer::LuiMessage>)

- ea: `0x1800eea0c`
- end: `0x1800eec04`
- name: `?WriteMessage@PipeImplementation@PipeManager@@QEAAXV?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@@Z`
- size: `504`
- prototype: `void __fastcall(struct PipeManager::PipeImplementation *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ece98`

## callees

- `0x1800017c8`
- `0x18005fd34`
- `0x1800636dc`
- `0x180064e40`
- `0x18006ba8c`
- `0x1800709e4`
- `0x1800ecb60`
- `0x1800eea0c`
- `0x180101010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800eeb2d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800eeb2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eebd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eebd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eea2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eea2f`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x1800eead0`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x1800eead0`

## string_xrefs

- `0x1800eea5f`: `PipeManager::PipeImplementation::WriteMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PipeManager::PipeImplementation::WriteMessage(struct PipeManager::PipeImplementation *a1, __int64 a2)
{
  int v4; // r14d
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned __int64 v8; // rax
  int *v9; // rdx
  CommonUtil *v10; // rcx
  int LastErrorToHResultAndForceFailure; // eax
  __int64 v12; // rbx
  __int64 v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // r8
  __int64 v16; // rdi
  __int64 v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // r8
  PipeManager *v20; // rcx
  std::_Ref_count_base *v21; // rcx
  char *v22; // [rsp+40h] [rbp-10h] BYREF
  __int64 v23; // [rsp+48h] [rbp-8h]
  int v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+98h] [rbp+48h]
  const char *v26; // [rsp+A0h] [rbp+50h] BYREF
  const char *v27; // [rsp+A8h] [rbp+58h] BYREF

  v25 = a2;
  v4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 3);
  v8 = *((_QWORD *)a1 + 21);
  if ( v8 >= 0x64 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_14;
    v24 = 100;
    v9 = &dword_180135894;
    goto LABEL_4;
  }
  if ( v8 )
  {
    v16 = *((_QWORD *)a1 + 20);
    v22 = (char *)a1 + 160;
    v23 = 0;
    v17 = std::_Allocate<16,std::_Default_allocate_traits>(32);
    std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v17 + 16, a2, v17);
    ++*((_QWORD *)a1 + 21);
    v18 = *(_QWORD **)(v16 + 8);
    *v19 = v16;
    v19[1] = v18;
    *(_QWORD *)(v16 + 8) = v19;
    *v18 = v19;
LABEL_13:
    v23 = 0;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<LPA::ApduHelper::UiccOperation>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<LPA::ApduHelper::UiccOperation>,void *>>>(&v22);
    goto LABEL_14;
  }
  (*(void (__fastcall **)(struct PipeManager::PipeImplementation *))(*(_QWORD *)a1 + 8LL))(a1);
  if ( WriteFileEx(
         *((HANDLE *)a1 + 4),
         *(LPCVOID *)(*(_QWORD *)a2 + 8LL),
         **(_DWORD **)a2,
         *((LPOVERLAPPED *)a1 + 12),
         PipeManager::PipeImplementation::OnWriteMessage) )
  {
    if ( *((_QWORD *)a1 + 21) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("list too long");
    v12 = *((_QWORD *)a1 + 20);
    v22 = (char *)a1 + 160;
    v23 = 0;
    v13 = std::_Allocate<16,std::_Default_allocate_traits>(32);
    std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v13 + 16, a2, v13);
    ++*((_QWORD *)a1 + 21);
    v14 = *(_QWORD **)(v12 + 8);
    *v15 = v12;
    v15[1] = v14;
    *(_QWORD *)(v12 + 8) = v15;
    *v14 = v15;
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct PipeManager::PipeImplementation *))(*(_QWORD *)a1 + 16LL))(a1);
  LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v10);
  v4 = LastErrorToHResultAndForceFailure;
  v5 = (int)CallbackContext;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v24 = LastErrorToHResultAndForceFailure;
    v9 = (int *)&unk_180135858;
LABEL_4:
    v26 = "PipeManager::PipeImplementation::WriteMessage";
    v27 = "LuiPipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v24);
  }
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 3);
  if ( v4 < 0 )
    PipeManager::OnPipeError(v20, a1, v4);
  v21 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
}

```

## disassembly

```asm
0x1800eea0c  mov     [rsp-38h+arg_8], rdx
0x1800eea11  push    rbp
0x1800eea12  push    rbx
0x1800eea13  push    rsi
0x1800eea14  push    rdi
0x1800eea15  push    r12
0x1800eea17  push    r14
0x1800eea19  push    r15
0x1800eea1b  mov     rbp, rsp
0x1800eea1e  sub     rsp, 50h
0x1800eea22  mov     r15, rdx
0x1800eea25  mov     rsi, rcx
0x1800eea28  xor     r14d, r14d
0x1800eea2b  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800eea2f  call    cs:__imp_EnterCriticalSection
0x1800eea35  mov     rax, [rsi+0A8h]
0x1800eea3c  cmp     rax, 64h ; 'd'
0x1800eea40  jb      short loc_1800EEA9A
0x1800eea42  mov     eax, cs:CallbackContext
0x1800eea48  cmp     eax, 2
0x1800eea4b  jbe     loc_1800EEBCC
0x1800eea51  mov     [rbp+arg_0], 64h ; 'd'
0x1800eea58  lea     rdx, dword_180135894
0x1800eea5f  lea     rax, aPipemanagerPip_2; "PipeManager::PipeImplementation::WriteM"...
0x1800eea66  mov     [rbp+arg_10], rax
0x1800eea6a  lea     rax, aLuipipe; "LuiPipe"
0x1800eea71  mov     [rbp+arg_18], rax
0x1800eea75  lea     rax, [rbp+arg_0]
0x1800eea79  mov     [rsp+50h+var_20], rax
0x1800eea7e  lea     rax, [rbp+arg_10]
0x1800eea82  mov     [rsp+50h+var_28], rax
0x1800eea87  lea     rax, [rbp+arg_18]
0x1800eea8b  mov     [rsp+50h+lpCompletionRoutine], rax
0x1800eea90  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800eea95  jmp     loc_1800EEBCC
0x1800eea9a  test    rax, rax
0x1800eea9d  jnz     loc_1800EEB75
0x1800eeaa3  mov     rax, [rsi]
0x1800eeaa6  mov     rcx, rsi
0x1800eeaa9  mov     rax, [rax+8]
0x1800eeaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeab2  mov     rdx, [r15]
0x1800eeab5  lea     rax, ?OnWriteMessage@PipeImplementation@PipeManager@@CAXKKPEAU_OVERLAPPED@@@Z; PipeManager::PipeImplementation::OnWriteMessage(ulong,ulong,_OVERLAPPED *)
0x1800eeabc  mov     [rsp+50h+lpCompletionRoutine], rax; lpCompletionRoutine
0x1800eeac1  mov     r9, [rsi+60h]; lpOverlapped
0x1800eeac5  mov     r8d, [rdx]; nNumberOfBytesToWrite
0x1800eeac8  mov     rdx, [rdx+8]; lpBuffer
0x1800eeacc  mov     rcx, [rsi+20h]; hFile
0x1800eead0  call    cs:__imp_WriteFileEx
0x1800eead6  test    eax, eax
0x1800eead8  jnz     short loc_1800EEB0F
0x1800eeada  mov     rax, [rsi]
0x1800eeadd  mov     rcx, rsi
0x1800eeae0  mov     rax, [rax+10h]
0x1800eeae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeae9  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800eeaee  mov     r14d, eax
0x1800eeaf1  mov     ecx, cs:CallbackContext
0x1800eeaf7  cmp     ecx, 2
0x1800eeafa  jbe     loc_1800EEBCC
0x1800eeb00  mov     [rbp+arg_0], eax
0x1800eeb03  lea     rdx, unk_180135858
0x1800eeb0a  jmp     loc_1800EEA5F
0x1800eeb0f  lea     rdi, [rsi+0A0h]
0x1800eeb16  mov     rax, 7FFFFFFFFFFFFFFh
0x1800eeb20  cmp     [rdi+8], rax
0x1800eeb24  jnz     short loc_1800EEB34
0x1800eeb26  lea     rcx, aListTooLong; "list too long"
0x1800eeb2d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800eeb34  mov     rbx, [rdi]
0x1800eeb37  mov     [rbp+var_10], rdi
0x1800eeb3b  mov     [rbp+var_8], 0
0x1800eeb43  mov     ecx, 20h ; ' '
0x1800eeb48  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800eeb4d  mov     r8, rax
0x1800eeb50  lea     rcx, [rax+10h]
0x1800eeb54  mov     rdx, r15
0x1800eeb57  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800eeb5c  nop
0x1800eeb5d  inc     qword ptr [rdi+8]
0x1800eeb61  mov     rcx, [rbx+8]
0x1800eeb65  mov     [r8], rbx
0x1800eeb68  mov     [r8+8], rcx
0x1800eeb6c  mov     [rbx+8], r8
0x1800eeb70  mov     [rcx], r8
0x1800eeb73  jmp     short loc_1800EEBBB
0x1800eeb75  lea     rbx, [rsi+0A0h]
0x1800eeb7c  mov     rdi, [rbx]
0x1800eeb7f  mov     [rbp+var_10], rbx
0x1800eeb83  mov     [rbp+var_8], 0
0x1800eeb8b  mov     ecx, 20h ; ' '
0x1800eeb90  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800eeb95  mov     r8, rax
0x1800eeb98  lea     rcx, [rax+10h]
0x1800eeb9c  mov     rdx, r15
0x1800eeb9f  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800eeba4  nop
0x1800eeba5  inc     qword ptr [rbx+8]
0x1800eeba9  mov     rdx, [rdi+8]
0x1800eebad  mov     [r8], rdi
0x1800eebb0  mov     [r8+8], rdx
0x1800eebb4  mov     [rdi+8], r8
0x1800eebb8  mov     [rdx], r8
0x1800eebbb  mov     [rbp+var_8], 0
0x1800eebc3  lea     rcx, [rbp+var_10]
0x1800eebc7  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<LPA::ApduHelper::UiccOperation>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<LPA::ApduHelper::UiccOperation>,void *>>>(void)
0x1800eebcc  lea     rcx, [rsi+78h]; lpCriticalSection
0x1800eebd0  call    cs:__imp_LeaveCriticalSection
0x1800eebd6  test    r14d, r14d
0x1800eebd9  jns     short loc_1800EEBE7
0x1800eebdb  mov     r8d, r14d; int
0x1800eebde  mov     rdx, rsi; struct PipeManager::PipeImplementation *
0x1800eebe1  call    ?OnPipeError@PipeManager@@AEAAXPEAVPipeImplementation@1@J@Z; PipeManager::OnPipeError(PipeManager::PipeImplementation *,long)
0x1800eebe6  nop
0x1800eebe7  mov     rcx, [r15+8]; this
0x1800eebeb  test    rcx, rcx
0x1800eebee  jz      short loc_1800EEBF5
0x1800eebf0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800eebf5  add     rsp, 50h
0x1800eebf9  pop     r15
0x1800eebfb  pop     r14
0x1800eebfd  pop     r12
0x1800eebff  pop     rdi
0x1800eec00  pop     rsi
0x1800eec01  pop     rbx
0x1800eec02  pop     rbp
0x1800eec03  retn
```
