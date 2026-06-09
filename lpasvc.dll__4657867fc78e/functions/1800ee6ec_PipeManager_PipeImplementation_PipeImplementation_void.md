# PipeManager::PipeImplementation::~PipeImplementation(void)

- ea: `0x1800ee6ec`
- end: `0x1800ee7e1`
- name: `??1PipeImplementation@PipeManager@@UEAA@XZ`
- size: `245`
- prototype: `void __fastcall(PipeManager::PipeImplementation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ee7f0`

## callees

- `0x1800017c8`
- `0x1800602e0`
- `0x1800ecac0`
- `0x1800ee598`
- `0x1800ee6ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ee7cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ee7cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee70c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee70c`

## pseudocode

```c
void __fastcall PipeManager::PipeImplementation::~PipeImplementation(PipeManager::PipeImplementation *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  int v4; // r8d
  int v5; // r9d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  const char *v7; // [rsp+58h] [rbp+10h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF

  *(_QWORD *)this = &PipeManager::PipeImplementation::`vftable';
  v2 = *(void **)(*((_QWORD *)this + 12) + 24LL);
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)(*((_QWORD *)this + 12) + 24LL) = 0;
  }
  std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>>>(
    v2,
    *((_QWORD *)this + 20));
  **((_QWORD **)this + 20) = *((_QWORD *)this + 20);
  *(_QWORD *)(*((_QWORD *)this + 20) + 8LL) = *((_QWORD *)this + 20);
  *((_QWORD *)this + 21) = 0;
  PipeManager::OnPipeDestroyed(*((PipeManager **)this + 3), this);
  if ( (unsigned int)CallbackContext > 4 )
  {
    v6 = *((_DWORD *)this + 4);
    v7 = "PipeManager::PipeImplementation::~PipeImplementation";
    v8 = "LuiPipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)word_1801358D2,
      v4,
      v5,
      (__int64)&v8,
      (__int64)&v7,
      (__int64)&v6);
  }
  std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>>>(
    v3,
    *((_QWORD *)this + 20));
  std::_Deallocate<16>(*((void **)this + 20), (struct std::nothrow_t *)0x20);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  *(_QWORD *)this = &RefCountingHelpers::RefCountedClass::`vftable';
}

```

## disassembly

```asm
0x1800ee6ec  push    rbx
0x1800ee6ee  sub     rsp, 40h
0x1800ee6f2  mov     rbx, rcx
0x1800ee6f5  lea     rax, ??_7PipeImplementation@PipeManager@@6B@; const PipeManager::PipeImplementation::`vftable'
0x1800ee6fc  mov     [rcx], rax
0x1800ee6ff  mov     rax, [rcx+60h]
0x1800ee703  mov     rcx, [rax+18h]; hObject
0x1800ee707  test    rcx, rcx
0x1800ee70a  jz      short loc_1800EE71E
0x1800ee70c  call    cs:__imp_CloseHandle
0x1800ee712  mov     rax, [rbx+60h]
0x1800ee716  mov     qword ptr [rax+18h], 0
0x1800ee71e  mov     rdx, [rbx+0A0h]
0x1800ee725  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>> &,std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *> *)
0x1800ee72a  mov     rax, [rbx+0A0h]
0x1800ee731  mov     [rax], rax
0x1800ee734  mov     rax, [rbx+0A0h]
0x1800ee73b  mov     [rax+8], rax
0x1800ee73f  mov     qword ptr [rbx+0A8h], 0
0x1800ee74a  mov     rdx, rbx; struct PipeManager::PipeImplementation *
0x1800ee74d  mov     rcx, [rbx+18h]; this
0x1800ee751  call    ?OnPipeDestroyed@PipeManager@@AEAAXPEAVPipeImplementation@1@@Z; PipeManager::OnPipeDestroyed(PipeManager::PipeImplementation *)
0x1800ee756  mov     eax, cs:CallbackContext
0x1800ee75c  cmp     eax, 4
0x1800ee75f  jbe     short loc_1800EE7AA
0x1800ee761  mov     eax, [rbx+10h]
0x1800ee764  mov     [rsp+48h+arg_0], eax
0x1800ee768  lea     rax, aPipemanagerPip_4; "PipeManager::PipeImplementation::~PipeI"...
0x1800ee76f  mov     [rsp+48h+arg_8], rax
0x1800ee774  lea     rax, aLuipipe; "LuiPipe"
0x1800ee77b  mov     [rsp+48h+arg_10], rax
0x1800ee780  lea     rax, [rsp+48h+arg_0]
0x1800ee785  mov     [rsp+48h+var_18], rax
0x1800ee78a  lea     rax, [rsp+48h+arg_8]
0x1800ee78f  mov     [rsp+48h+var_20], rax
0x1800ee794  lea     rax, [rsp+48h+arg_10]
0x1800ee799  mov     [rsp+48h+var_28], rax
0x1800ee79e  lea     rdx, word_1801358D2
0x1800ee7a5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ee7aa  mov     rdx, [rbx+0A0h]
0x1800ee7b1  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VLuiMessage@LuiApiServer@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *>> &,std::_List_node<std::shared_ptr<LuiApiServer::LuiMessage>,void *> *)
0x1800ee7b6  mov     edx, 20h ; ' '
0x1800ee7bb  mov     rcx, [rbx+0A0h]
0x1800ee7c2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ee7c7  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800ee7cb  call    cs:__imp_DeleteCriticalSection
0x1800ee7d1  lea     rax, ??_7RefCountedClass@RefCountingHelpers@@6B@; const RefCountingHelpers::RefCountedClass::`vftable'
0x1800ee7d8  mov     [rbx], rax
0x1800ee7db  add     rsp, 40h
0x1800ee7df  pop     rbx
0x1800ee7e0  retn
```
