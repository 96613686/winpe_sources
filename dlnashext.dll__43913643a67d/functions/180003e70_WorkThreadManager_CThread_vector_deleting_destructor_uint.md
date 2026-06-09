# WorkThreadManager::CThread::`vector deleting destructor'(uint)

- ea: `0x180003e70`
- end: `0x180003f84`
- name: `??_ECThread@WorkThreadManager@@EEAAPEAXI@Z`
- size: `276`
- prototype: `void *__fastcall(WorkThreadManager::CThread *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180003e70`
- `0x180003f8c`
- `0x18000ec48`
- `0x180011df4`
- `0x1800316ac`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003ed6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003ed6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003f27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003eb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003eae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WorkThreadManager::CThread *__fastcall WorkThreadManager::CThread::`vector deleting destructor'(
        WorkThreadManager::CThread *this,
        char a2)
{
  struct _TP_TIMER *v4; // rcx
  void *v5; // rdx
  HMODULE v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  wil::details *v9; // rcx
  HMODULE v10; // rcx
  WorkThreadManager::TaskData *v11; // rcx
  wil::details *v12; // rcx

  *(_QWORD *)this = &WorkThreadManager::CThread::`vftable';
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 192);
  v6 = (HMODULE)*((_QWORD *)this + 23);
  if ( v6 )
    FreeLibrary(v6);
  v7 = *((_QWORD *)this + 15);
  if ( v7 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 14);
  if ( v8 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = (wil::details *)*((_QWORD *)this + 13);
  if ( v9 )
    wil::details::CloseHandle(v9, v5);
  v10 = (HMODULE)*((_QWORD *)this + 8);
  if ( v10 )
    FreeLibrary(v10);
  v11 = (WorkThreadManager::TaskData *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v11 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v11, (unsigned int)v5);
  v12 = (wil::details *)*((_QWORD *)this + 6);
  if ( v12 )
    wil::details::CloseHandle(v12, v5);
  WorkThreadManager::TaskList::Clear((WorkThreadManager::CThread *)((char *)this + 24));
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003e70  mov     [rsp+arg_0], rbx
0x180003e75  mov     [rsp+arg_8], rsi
0x180003e7a  push    rdi
0x180003e7b  sub     rsp, 20h
0x180003e7f  mov     edi, edx
0x180003e81  mov     rbx, rcx
0x180003e84  lea     rax, ??_7CThread@WorkThreadManager@@6B@; const WorkThreadManager::CThread::`vftable'
0x180003e8b  mov     [rcx], rax
0x180003e8e  mov     rcx, [rcx+60h]; pti
0x180003e92  test    rcx, rcx
0x180003e95  jz      short loc_180003EBE
0x180003e97  xor     r9d, r9d; msWindowLength
0x180003e9a  xor     r8d, r8d; msPeriod
0x180003e9d  xor     edx, edx; pftDueTime
0x180003e9f  call    cs:__imp_SetThreadpoolTimer
0x180003ea5  mov     edx, 1; fCancelPendingCallbacks
0x180003eaa  mov     rcx, [rbx+60h]; pti
0x180003eae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003eb4  mov     rcx, [rbx+60h]; pti
0x180003eb8  call    cs:__imp_CloseThreadpoolTimer
0x180003ebe  lea     rcx, [rbx+0C0h]
0x180003ec5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003eca  mov     rcx, [rbx+0B8h]; hLibModule
0x180003ed1  test    rcx, rcx
0x180003ed4  jz      short loc_180003EDC
0x180003ed6  call    cs:__imp_FreeLibrary
0x180003edc  mov     rcx, [rbx+78h]
0x180003ee0  xor     esi, esi
0x180003ee2  test    rcx, rcx
0x180003ee5  jz      short loc_180003EF7
0x180003ee7  mov     [rbx+78h], rsi
0x180003eeb  mov     rax, [rcx]
0x180003eee  mov     rax, [rax+10h]
0x180003ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef7  mov     rcx, [rbx+70h]
0x180003efb  test    rcx, rcx
0x180003efe  jz      short loc_180003F10
0x180003f00  mov     [rbx+70h], rsi
0x180003f04  mov     rax, [rcx]
0x180003f07  mov     rax, [rax+10h]
0x180003f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f10  mov     rcx, [rbx+68h]; this
0x180003f14  test    rcx, rcx
0x180003f17  jz      short loc_180003F1E
0x180003f19  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180003f1e  mov     rcx, [rbx+40h]; hLibModule
0x180003f22  test    rcx, rcx
0x180003f25  jz      short loc_180003F2D
0x180003f27  call    cs:__imp_FreeLibrary
0x180003f2d  mov     rcx, [rbx+38h]; this
0x180003f31  mov     [rbx+38h], rsi
0x180003f35  test    rcx, rcx
0x180003f38  jz      short loc_180003F3F
0x180003f3a  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180003f3f  mov     rcx, [rbx+30h]; this
0x180003f43  test    rcx, rcx
0x180003f46  jz      short loc_180003F4D
0x180003f48  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180003f4d  lea     rcx, [rbx+18h]; this
0x180003f51  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x180003f56  nop
0x180003f57  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180003f5e  test    dil, 1
0x180003f62  jz      short loc_180003F71
0x180003f64  mov     edx, 0E8h
0x180003f69  mov     rcx, rbx; Block
0x180003f6c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003f71  mov     rax, rbx
0x180003f74  mov     rbx, [rsp+28h+arg_0]
0x180003f79  mov     rsi, [rsp+28h+arg_8]
0x180003f7e  add     rsp, 20h
0x180003f82  pop     rdi
0x180003f83  retn
```
