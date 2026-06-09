# CRemoteAssistanceApp::~CRemoteAssistanceApp(void)

- ea: `0x14000c33c`
- end: `0x14000c632`
- name: `??1CRemoteAssistanceApp@@UEAA@XZ`
- size: `758`
- prototype: `void __fastcall(CRemoteAssistanceApp *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x14000c840`

## callees

- `0x14000a23c`
- `0x14000c224`
- `0x14000c33c`
- `0x140017f00`
- `0x140019cc8`
- `0x14001f124`
- `0x140037810`
- `0x1400389bc`
- `0x14003a16c`
- `0x1400442a4`
- `0x140044320`
- `0x14004d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000c4e6`
- `KERNEL32!FreeLibrary` at `0x14000c4e6`
- `KERNEL32!DeleteCriticalSection` at `0x14000c53b`
- `KERNEL32!DeleteCriticalSection` at `0x14000c53b`
- `KERNEL32!CloseHandle` at `0x14000c4ce`
- `KERNEL32!CloseHandle` at `0x14000c528`
- `KERNEL32!CloseHandle` at `0x14000c58e`
- `KERNEL32!CloseHandle` at `0x14000c4ce`
- `KERNEL32!CloseHandle` at `0x14000c528`
- `KERNEL32!CloseHandle` at `0x14000c58e`
- `GDI32!DeleteObject` at `0x14000c366`
- `GDI32!DeleteObject` at `0x14000c366`
- `msvcrt!free` at `0x14000c495`
- `msvcrt!free` at `0x14000c495`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c390`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3af`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3f8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c422`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c476`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c390`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3af`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c3f8`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c422`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000c476`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c4b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c505`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c560`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5da`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c4b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c505`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c560`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5b4`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c5da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRemoteAssistanceApp::~CRemoteAssistanceApp(CRemoteAssistanceApp *this)
{
  void *v2; // rcx
  void *v3; // rdi
  void *v4; // rcx
  void *v5; // rdi
  void *v6; // rcx
  void *v7; // rdi
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  void *v11; // rcx
  OLECHAR *v12; // rcx
  HMODULE v13; // rcx
  OLECHAR *v14; // rcx
  void *v15; // rcx
  _QWORD *v16; // rdi
  void *v17; // rcx

  *(_QWORD *)this = &CRemoteAssistanceApp::`vftable';
  v2 = (void *)*((_QWORD *)this + 122);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 122) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 112);
  if ( v3 )
  {
    RAFileReceiverClient::~RAFileReceiverClient(*((RAFileReceiverClient **)this + 112));
    operator delete(v3);
    *((_QWORD *)this + 112) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 113);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 113) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 121);
  if ( v5 )
  {
    RAChatReceiverClient::~RAChatReceiverClient(*((RAChatReceiverClient **)this + 121));
    operator delete(v5);
    *((_QWORD *)this + 121) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 120);
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 120) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 104);
  if ( v7 )
  {
    CRATicket::~CRATicket(*((CRATicket **)this + 104));
    operator delete(v7);
    *((_QWORD *)this + 104) = 0;
  }
  v8 = (_QWORD *)*((_QWORD *)this + 61);
  if ( v8 )
  {
    v9 = v8[2];
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v8[2] = 0;
    }
    v10 = v8[3];
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v8[3] = 0;
    }
    operator delete(v8);
    *((_QWORD *)this + 61) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 110);
  if ( v11 )
  {
    free(v11);
    *((_QWORD *)this + 110) = 0;
  }
  v12 = (OLECHAR *)*((_QWORD *)this + 115);
  if ( v12 )
  {
    SysFreeString(v12);
    *((_QWORD *)this + 115) = 0;
  }
  CloseHandle(*((HANDLE *)this + 106));
  v13 = (HMODULE)*((_QWORD *)this + 79);
  if ( v13 )
  {
    FreeLibrary(v13);
    *((_QWORD *)this + 79) = 0;
  }
  v14 = (OLECHAR *)*((_QWORD *)this + 80);
  if ( v14 )
  {
    SysFreeString(v14);
    *((_QWORD *)this + 80) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 132);
  if ( v15 )
  {
    CloseHandle(v15);
    *((_QWORD *)this + 132) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1008));
  v16 = (_QWORD *)((char *)this + 728);
  if ( *((_DWORD *)this + 196) == 1 )
    CSessionLogger::CloseLog((CRemoteAssistanceApp *)((char *)this + 728));
  SysFreeString(*((BSTR *)this + 92));
  if ( *v16 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 16LL))(*v16);
  v17 = (void *)*((_QWORD *)this + 87);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)this + 87) = 0;
  }
  CReadWriteLock::~CReadWriteLock((CRemoteAssistanceApp *)((char *)this + 672));
  SysFreeString(*((BSTR *)this + 83));
  SysFreeString(*((BSTR *)this + 82));
  SysFreeString(*((BSTR *)this + 81));
  CEventWatcher::~CEventWatcher((CRemoteAssistanceApp *)((char *)this + 568));
  CSqmManager::~CSqmManager((CRemoteAssistanceApp *)((char *)this + 496));
  CNovInterDlg::~CNovInterDlg((CRemoteAssistanceApp *)((char *)this + 272));
  CExpInterDlg::~CExpInterDlg((CRemoteAssistanceApp *)((char *)this + 72));
  ATL::CAtlModule::Term(this);
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x14000c33c  mov     [rsp+arg_0], rbx
0x14000c341  mov     [rsp+arg_8], rsi
0x14000c346  push    rdi
0x14000c347  sub     rsp, 20h
0x14000c34b  mov     rbx, rcx
0x14000c34e  lea     rax, ??_7CRemoteAssistanceApp@@6B@; const CRemoteAssistanceApp::`vftable'
0x14000c355  mov     [rcx], rax
0x14000c358  mov     rcx, [rcx+3D0h]; ho
0x14000c35f  xor     esi, esi
0x14000c361  test    rcx, rcx
0x14000c364  jz      short loc_14000C379
0x14000c366  call    cs:__imp_DeleteObject
0x14000c36d  nop     dword ptr [rax+rax+00h]
0x14000c372  mov     [rbx+3D0h], rsi
0x14000c379  mov     rdi, [rbx+380h]
0x14000c380  test    rdi, rdi
0x14000c383  jz      short loc_14000C3A3
0x14000c385  mov     rcx, rdi; this
0x14000c388  call    ??1RAFileReceiverClient@@QEAA@XZ; RAFileReceiverClient::~RAFileReceiverClient(void)
0x14000c38d  mov     rcx, rdi
0x14000c390  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c397  nop     dword ptr [rax+rax+00h]
0x14000c39c  mov     [rbx+380h], rsi
0x14000c3a3  mov     rcx, [rbx+388h]
0x14000c3aa  test    rcx, rcx
0x14000c3ad  jz      short loc_14000C3C2
0x14000c3af  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c3b6  nop     dword ptr [rax+rax+00h]
0x14000c3bb  mov     [rbx+388h], rsi
0x14000c3c2  mov     rdi, [rbx+3C8h]
0x14000c3c9  test    rdi, rdi
0x14000c3cc  jz      short loc_14000C3EC
0x14000c3ce  mov     rcx, rdi; this
0x14000c3d1  call    ??1RAChatReceiverClient@@QEAA@XZ; RAChatReceiverClient::~RAChatReceiverClient(void)
0x14000c3d6  mov     rcx, rdi
0x14000c3d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c3e0  nop     dword ptr [rax+rax+00h]
0x14000c3e5  mov     [rbx+3C8h], rsi
0x14000c3ec  mov     rcx, [rbx+3C0h]
0x14000c3f3  test    rcx, rcx
0x14000c3f6  jz      short loc_14000C40B
0x14000c3f8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c3ff  nop     dword ptr [rax+rax+00h]
0x14000c404  mov     [rbx+3C0h], rsi
0x14000c40b  mov     rdi, [rbx+340h]
0x14000c412  test    rdi, rdi
0x14000c415  jz      short loc_14000C435
0x14000c417  mov     rcx, rdi; this
0x14000c41a  call    ??1CRATicket@@QEAA@XZ; CRATicket::~CRATicket(void)
0x14000c41f  mov     rcx, rdi
0x14000c422  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c429  nop     dword ptr [rax+rax+00h]
0x14000c42e  mov     [rbx+340h], rsi
0x14000c435  mov     rdi, [rbx+1E8h]
0x14000c43c  test    rdi, rdi
0x14000c43f  jz      short loc_14000C489
0x14000c441  mov     rcx, [rdi+10h]
0x14000c445  test    rcx, rcx
0x14000c448  jz      short loc_14000C45A
0x14000c44a  mov     rax, [rcx]
0x14000c44d  mov     rax, [rax+10h]
0x14000c451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c456  mov     [rdi+10h], rsi
0x14000c45a  mov     rcx, [rdi+18h]
0x14000c45e  test    rcx, rcx
0x14000c461  jz      short loc_14000C473
0x14000c463  mov     rax, [rcx]
0x14000c466  mov     rax, [rax+10h]
0x14000c46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c46f  mov     [rdi+18h], rsi
0x14000c473  mov     rcx, rdi
0x14000c476  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000c47d  nop     dword ptr [rax+rax+00h]
0x14000c482  mov     [rbx+1E8h], rsi
0x14000c489  mov     rcx, [rbx+370h]; Block
0x14000c490  test    rcx, rcx
0x14000c493  jz      short loc_14000C4A8
0x14000c495  call    cs:__imp_free
0x14000c49c  nop     dword ptr [rax+rax+00h]
0x14000c4a1  mov     [rbx+370h], rsi
0x14000c4a8  mov     rcx, [rbx+398h]; bstrString
0x14000c4af  test    rcx, rcx
0x14000c4b2  jz      short loc_14000C4C7
0x14000c4b4  call    cs:__imp_SysFreeString
0x14000c4bb  nop     dword ptr [rax+rax+00h]
0x14000c4c0  mov     [rbx+398h], rsi
0x14000c4c7  mov     rcx, [rbx+350h]; hObject
0x14000c4ce  call    cs:__imp_CloseHandle
0x14000c4d5  nop     dword ptr [rax+rax+00h]
0x14000c4da  mov     rcx, [rbx+278h]; hLibModule
0x14000c4e1  test    rcx, rcx
0x14000c4e4  jz      short loc_14000C4F9
0x14000c4e6  call    cs:__imp_FreeLibrary
0x14000c4ed  nop     dword ptr [rax+rax+00h]
0x14000c4f2  mov     [rbx+278h], rsi
0x14000c4f9  mov     rcx, [rbx+280h]; bstrString
0x14000c500  test    rcx, rcx
0x14000c503  jz      short loc_14000C518
0x14000c505  call    cs:__imp_SysFreeString
0x14000c50c  nop     dword ptr [rax+rax+00h]
0x14000c511  mov     [rbx+280h], rsi
0x14000c518  lea     rdi, [rbx+3F0h]
0x14000c51f  mov     rcx, [rdi+30h]; hObject
0x14000c523  test    rcx, rcx
0x14000c526  jz      short loc_14000C538
0x14000c528  call    cs:__imp_CloseHandle
0x14000c52f  nop     dword ptr [rax+rax+00h]
0x14000c534  mov     [rdi+30h], rsi
0x14000c538  mov     rcx, rdi; lpCriticalSection
0x14000c53b  call    cs:__imp_DeleteCriticalSection
0x14000c542  nop     dword ptr [rax+rax+00h]
0x14000c547  lea     rdi, [rbx+2D8h]
0x14000c54e  cmp     dword ptr [rdi+38h], 1
0x14000c552  jnz     short loc_14000C55C
0x14000c554  mov     rcx, rdi; this
0x14000c557  call    ?CloseLog@CSessionLogger@@QEAAJXZ; CSessionLogger::CloseLog(void)
0x14000c55c  mov     rcx, [rdi+8]; bstrString
0x14000c560  call    cs:__imp_SysFreeString
0x14000c567  nop     dword ptr [rax+rax+00h]
0x14000c56c  nop
0x14000c56d  mov     rcx, [rdi]
0x14000c570  test    rcx, rcx
0x14000c573  jz      short loc_14000C582
0x14000c575  mov     rax, [rcx]
0x14000c578  mov     rax, [rax+10h]
0x14000c57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c581  nop
0x14000c582  mov     rcx, [rbx+2B8h]; hObject
0x14000c589  test    rcx, rcx
0x14000c58c  jz      short loc_14000C5A1
0x14000c58e  call    cs:__imp_CloseHandle
0x14000c595  nop     dword ptr [rax+rax+00h]
0x14000c59a  mov     [rbx+2B8h], rsi
0x14000c5a1  lea     rcx, [rbx+2A0h]; this
0x14000c5a8  call    ??1CReadWriteLock@@QEAA@XZ; CReadWriteLock::~CReadWriteLock(void)
0x14000c5ad  mov     rcx, [rbx+298h]; bstrString
0x14000c5b4  call    cs:__imp_SysFreeString
0x14000c5bb  nop     dword ptr [rax+rax+00h]
0x14000c5c0  mov     rcx, [rbx+290h]; bstrString
0x14000c5c7  call    cs:__imp_SysFreeString
0x14000c5ce  nop     dword ptr [rax+rax+00h]
0x14000c5d3  mov     rcx, [rbx+288h]; bstrString
0x14000c5da  call    cs:__imp_SysFreeString
0x14000c5e1  nop     dword ptr [rax+rax+00h]
0x14000c5e6  lea     rcx, [rbx+238h]; this
0x14000c5ed  call    ??1CEventWatcher@@QEAA@XZ; CEventWatcher::~CEventWatcher(void)
0x14000c5f2  lea     rcx, [rbx+1F0h]; this
0x14000c5f9  call    ??1CSqmManager@@QEAA@XZ; CSqmManager::~CSqmManager(void)
0x14000c5fe  lea     rcx, [rbx+110h]; this
0x14000c605  call    ??1CNovInterDlg@@UEAA@XZ; CNovInterDlg::~CNovInterDlg(void)
0x14000c60a  lea     rcx, [rbx+48h]; this
0x14000c60e  call    ??1CExpInterDlg@@UEAA@XZ; CExpInterDlg::~CExpInterDlg(void)
0x14000c613  mov     rcx, rbx; this
0x14000c616  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000c61b  mov     rcx, rbx; this
0x14000c61e  mov     rbx, [rsp+28h+arg_0]
0x14000c623  mov     rsi, [rsp+28h+arg_8]
0x14000c628  add     rsp, 20h
0x14000c62c  pop     rdi
0x14000c62d  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
