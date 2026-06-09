# Microsoft::HostGuardian::Client::HgService::~HgService(void)

- ea: `0x1800096d0`
- end: `0x180009773`
- name: `??1HgService@Client@HostGuardian@Microsoft@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgService *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009f30`
- `0x1800156f5`

## callees

- `0x180001bb4`
- `0x180004274`
- `0x18000734c`
- `0x1800096d0`
- `0x18000c574`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009733`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180009724`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x180009724`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000974b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000974b`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgService::~HgService(
        Microsoft::HostGuardian::Client::HgService *this)
{
  void *v2; // rdi
  __int64 v3; // rcx
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  char *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 24);
  if ( v2 )
  {
    Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(*((Microsoft::HostGuardian::Client::HgServiceController **)this
                                                                               + 24));
    operator delete(v2);
  }
  v3 = *((_QWORD *)this + 23);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((_QWORD *)this + 22) )
    CoDecrementMTAUsage();
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  v7 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    UnregisterWait(v7);
  std::wstring::~wstring((char **)this);
}

```

## disassembly

```asm
0x1800096d0  mov     [rsp+arg_0], rbx
0x1800096d5  push    rdi
0x1800096d6  sub     rsp, 20h
0x1800096da  mov     rbx, rcx
0x1800096dd  mov     rdi, [rcx+0C0h]
0x1800096e4  test    rdi, rdi
0x1800096e7  jz      short loc_1800096FF
0x1800096e9  mov     rcx, rdi; this
0x1800096ec  call    ??1HgServiceController@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::HgServiceController::~HgServiceController(void)
0x1800096f1  mov     edx, 110h
0x1800096f6  mov     rcx, rdi; Block
0x1800096f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800096fe  nop
0x1800096ff  mov     rcx, [rbx+0B8h]
0x180009706  test    rcx, rcx
0x180009709  jz      short loc_180009718
0x18000970b  mov     rax, [rcx]
0x18000970e  mov     rax, [rax+10h]
0x180009712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009717  nop
0x180009718  mov     rcx, [rbx+0B0h]
0x18000971f  test    rcx, rcx
0x180009722  jz      short loc_18000972A
0x180009724  call    cs:__imp_CoDecrementMTAUsage
0x18000972a  mov     rcx, [rbx+58h]; hObject
0x18000972e  test    rcx, rcx
0x180009731  jz      short loc_18000973D
0x180009733  call    cs:__imp_CloseHandle
0x180009739  test    eax, eax
0x18000973b  jz      short loc_180009763
0x18000973d  mov     rcx, [rbx+50h]; WaitHandle
0x180009741  lea     rax, [rcx-1]
0x180009745  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009749  ja      short loc_180009751
0x18000974b  call    cs:__imp_UnregisterWait
0x180009751  mov     rcx, rbx
0x180009754  mov     rbx, [rsp+28h+arg_0]
0x180009759  add     rsp, 20h
0x18000975d  pop     rdi
0x18000975e  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009763  mov     rcx, [rsp+28h]; this
0x180009768  mov     edx, 0A0Bh; void *
0x18000976d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
