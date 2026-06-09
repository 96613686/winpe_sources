# CInboundContext::~CInboundContext(void)

- ea: `0x180035320`
- end: `0x1800354af`
- name: `??1CInboundContext@@IEAA@XZ`
- size: `399`
- prototype: `void __fastcall(CInboundContext *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004577c`

## callees

- `0x180015b64`
- `0x18002d764`
- `0x180035320`
- `0x1800354b8`
- `0x1800355e0`
- `0x180045720`
- `0x180045df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035396`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035396`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800353ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035436`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800353ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800353fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800353ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800353eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800353ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800353eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035417`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035429`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035417`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035429`

## string_xrefs

- `0x18003534b`: `onecore\base\devices\association\service\lib\inboundcontext.cpp`

## pseudocode

```c
void __fastcall CInboundContext::~CInboundContext(CInboundContext *this)
{
  int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  CInboundContext **v4; // rax
  CInboundContext **v5; // rsi
  CInboundContext *v6; // rcx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rbx
  HANDLE v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)this = &CInboundContext::`vftable';
  v2 = DAS::ProviderManagement::InboundOps::Deactivate((PSRWLOCK)this + 17);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\inboundcontext.cpp",
      (const char *)(unsigned int)v2,
      v16);
  while ( 1 )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
    if ( *((CInboundContext **)this + 12) == (CInboundContext *)((char *)this + 96) )
      break;
    EnterCriticalSection(v3);
    v4 = (CInboundContext **)((char *)this + 96);
    v5 = (CInboundContext **)*((_QWORD *)this + 12);
    if ( v5[1] != (CInboundContext *)((char *)this + 96) || (v6 = *v5, *((CInboundContext ***)*v5 + 1) != v5) )
      __fastfail(3u);
    *v4 = v6;
    *((_QWORD *)v6 + 1) = v4;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    FreeInboundResultEntry((struct _INBOUND_RESULT_ENTRY *)(v5 - 1));
  }
  DeleteCriticalSection(v3);
  v7 = (void *)*((_QWORD *)this + 23);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (void *)*((_QWORD *)this + 5);
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  v11 = (void *)*((_QWORD *)this + 6);
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  v13 = (void *)*((_QWORD *)this + 15);
  if ( v13 )
    CloseHandle(v13);
  v14 = (void *)*((_QWORD *)this + 16);
  if ( v14 )
    CloseHandle(v14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 240);
  v15 = *((_QWORD *)this + 18);
  if ( v15 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<DAS::ProviderManagement::InboundOp>>>(
      v15,
      *((_QWORD *)this + 19));
    std::_Deallocate<16>(
      *((void **)this + 18),
      (*((_QWORD *)this + 20) - *((_QWORD *)this + 18)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
  }
}

```

## disassembly

```asm
0x180035320  push    rbx
0x180035322  push    rbp
0x180035323  push    rsi
0x180035324  push    rdi
0x180035325  sub     rsp, 28h
0x180035329  lea     rax, ??_7CInboundContext@@6B@; const CInboundContext::`vftable'
0x180035330  mov     rdi, rcx
0x180035333  mov     [rcx], rax
0x180035336  add     rcx, 88h; SRWLock
0x18003533d  call    ?Deactivate@InboundOps@ProviderManagement@DAS@@QEAAJXZ; DAS::ProviderManagement::InboundOps::Deactivate(void)
0x180035342  test    eax, eax
0x180035344  jns     short loc_18003535F
0x180035346  mov     rcx, [rsp+48h]; this
0x18003534b  lea     r8, aOnecoreBaseDev_6; "onecore\\base\\devices\\association\\se"...
0x180035352  mov     r9d, eax; char *
0x180035355  mov     edx, 42h ; 'B'; void *
0x18003535a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003535f  lea     rbx, [rdi+38h]
0x180035363  lea     rbp, [rbx+28h]
0x180035367  mov     rcx, rbx; lpCriticalSection
0x18003536a  cmp     [rbp+0], rbp
0x18003536e  jz      short loc_1800353AE
0x180035370  call    cs:__imp_EnterCriticalSection
0x180035376  lea     rax, [rdi+60h]
0x18003537a  mov     rsi, [rax]
0x18003537d  cmp     [rsi+8], rax
0x180035381  jnz     short loc_1800353A7
0x180035383  mov     rcx, [rsi]
0x180035386  cmp     [rcx+8], rsi
0x18003538a  jnz     short loc_1800353A7
0x18003538c  mov     [rax], rcx
0x18003538f  mov     [rcx+8], rax
0x180035393  mov     rcx, rbx; lpCriticalSection
0x180035396  call    cs:__imp_LeaveCriticalSection
0x18003539c  lea     rcx, [rsi-8]; struct _INBOUND_RESULT_ENTRY *
0x1800353a0  call    ?FreeInboundResultEntry@@YAXPEAU_INBOUND_RESULT_ENTRY@@@Z; FreeInboundResultEntry(_INBOUND_RESULT_ENTRY *)
0x1800353a5  jmp     short loc_180035367
0x1800353a7  mov     ecx, 3
0x1800353ac  int     29h; Win8: RtlFailFast(ecx)
0x1800353ae  call    cs:__imp_DeleteCriticalSection
0x1800353b4  mov     rbx, [rdi+0B8h]
0x1800353bb  test    rbx, rbx
0x1800353be  jz      short loc_1800353D4
0x1800353c0  call    cs:__imp_GetProcessHeap
0x1800353c6  mov     r8, rbx; lpMem
0x1800353c9  xor     edx, edx; dwFlags
0x1800353cb  mov     rcx, rax; hHeap
0x1800353ce  call    cs:__imp_HeapFree
0x1800353d4  mov     rbx, [rdi+28h]
0x1800353d8  test    rbx, rbx
0x1800353db  jz      short loc_1800353F1
0x1800353dd  call    cs:__imp_GetProcessHeap
0x1800353e3  mov     r8, rbx; lpMem
0x1800353e6  xor     edx, edx; dwFlags
0x1800353e8  mov     rcx, rax; hHeap
0x1800353eb  call    cs:__imp_HeapFree
0x1800353f1  mov     rbx, [rdi+30h]
0x1800353f5  test    rbx, rbx
0x1800353f8  jz      short loc_18003540E
0x1800353fa  call    cs:__imp_GetProcessHeap
0x180035400  mov     r8, rbx; lpMem
0x180035403  xor     edx, edx; dwFlags
0x180035405  mov     rcx, rax; hHeap
0x180035408  call    cs:__imp_HeapFree
0x18003540e  mov     rcx, [rdi+78h]; hObject
0x180035412  test    rcx, rcx
0x180035415  jz      short loc_18003541D
0x180035417  call    cs:__imp_CloseHandle
0x18003541d  mov     rcx, [rdi+80h]; hObject
0x180035424  test    rcx, rcx
0x180035427  jz      short loc_18003542F
0x180035429  call    cs:__imp_CloseHandle
0x18003542f  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x180035436  call    cs:__imp_DeleteCriticalSection
0x18003543c  lea     rbx, [rdi+0F0h]
0x180035443  mov     rcx, rbx
0x180035446  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003544b  mov     rcx, rbx
0x18003544e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035453  mov     rcx, [rdi+90h]
0x18003545a  test    rcx, rcx
0x18003545d  jz      short loc_1800354A6
0x18003545f  mov     rdx, [rdi+98h]
0x180035466  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VInboundOp@ProviderManagement@DAS@@U?$default_delete@VInboundOp@ProviderManagement@DAS@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VInboundOp@ProviderManagement@DAS@@U?$default_delete@VInboundOp@ProviderManagement@DAS@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VInboundOp@ProviderManagement@DAS@@U?$default_delete@VInboundOp@ProviderManagement@DAS@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<DAS::ProviderManagement::InboundOp>>>(std::unique_ptr<DAS::ProviderManagement::InboundOp> *,std::unique_ptr<DAS::ProviderManagement::InboundOp> * const,std::allocator<std::unique_ptr<DAS::ProviderManagement::InboundOp>> &)
0x18003546b  mov     rcx, [rdi+90h]
0x180035472  mov     rdx, [rdi+0A0h]
0x180035479  sub     rdx, rcx
0x18003547c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180035480  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035485  mov     qword ptr [rdi+90h], 0
0x180035490  mov     qword ptr [rdi+98h], 0
0x18003549b  mov     qword ptr [rdi+0A0h], 0
0x1800354a6  add     rsp, 28h
0x1800354aa  pop     rdi
0x1800354ab  pop     rsi
0x1800354ac  pop     rbp
0x1800354ad  pop     rbx
0x1800354ae  retn
```
