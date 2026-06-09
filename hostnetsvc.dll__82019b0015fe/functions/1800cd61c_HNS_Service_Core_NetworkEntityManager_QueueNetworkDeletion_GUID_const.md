# HNS::Service::Core::NetworkEntityManager::QueueNetworkDeletion(_GUID const &)

- ea: `0x1800cd61c`
- end: `0x1800cd777`
- name: `?QueueNetworkDeletion@NetworkEntityManager@Core@Service@HNS@@QEAAXAEBU_GUID@@@Z`
- size: `347`
- prototype: `void __fastcall(HNS::Service::Core::NetworkEntityManager *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800cbe94`
- `0x18013a75c`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005f560`
- `0x18006038c`
- `0x180061240`
- `0x18007e864`
- `0x1800cd61c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd728`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cd675`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cd675`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cd6ca`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cd6ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800cd6d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800cd6d3`

## string_xrefs

- `0x1800cd707`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800cd756`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800cd765`: `Unable to create thread pool work`

## pseudocode

```c
void __fastcall HNS::Service::Core::NetworkEntityManager::QueueNetworkDeletion(
        HNS::Service::Core::NetworkEntityManager *this,
        const struct _GUID *a2)
{
  struct _GUID *v4; // rax
  struct _GUID *v5; // rdi
  struct _TP_WORK *ThreadpoolWork; // rbx
  unsigned int v7; // eax
  signed int LastError; // ebx
  unsigned int v9; // eax
  const char *v10; // [rsp+28h] [rbp-50h]
  _BYTE v11[32]; // [rsp+30h] [rbp-48h] BYREF
  struct _GUID *v12; // [rsp+50h] [rbp-28h]
  __int64 v13; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = (struct _GUID *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v7 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xDB0,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
      (const char *)v7,
      (int)"Memory allocation failure. Network deletion not queued",
      v10);
  }
  *v4 = *a2;
  ThreadpoolWork = CreateThreadpoolWork(
                     HNS::Service::Core::NetworkEntityManager::NetworkDeletionCallback,
                     v4,
                     (PTP_CALLBACK_ENVIRON)((char *)this + 872));
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    operator delete(v5, (const struct std::nothrow_t *)0x10);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = wil::verify_hresult<long>((unsigned int)LastError);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xDBB,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
      (const char *)v9,
      (int)"Unable to create thread pool work",
      v10);
  }
  if ( *(_DWORD *)qword_1803989E8 > 4u )
  {
    v12 = v5;
    v13 = 16;
    tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &unk_1803355BA, 0, 0, 3, v11);
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(ThreadpoolWork);
}

```

## disassembly

```asm
0x1800cd61c  mov     [rsp+arg_8], rbx
0x1800cd621  mov     [rsp+arg_10], rsi
0x1800cd626  push    rdi
0x1800cd627  sub     rsp, 70h
0x1800cd62b  mov     rax, cs:__security_cookie
0x1800cd632  xor     rax, rsp
0x1800cd635  mov     [rsp+78h+var_18], rax
0x1800cd63a  mov     rbx, rdx
0x1800cd63d  mov     rsi, rcx
0x1800cd640  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cd647  mov     ecx, 10h; unsigned __int64
0x1800cd64c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800cd651  mov     rdi, rax
0x1800cd654  test    rax, rax
0x1800cd657  jz      loc_1800CD6F8
0x1800cd65d  movups  xmm0, xmmword ptr [rbx]
0x1800cd660  lea     r8, [rsi+368h]; pcbe
0x1800cd667  mov     rdx, rax; pv
0x1800cd66a  lea     rcx, ?NetworkDeletionCallback@NetworkEntityManager@Core@Service@HNS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800cd671  movdqu  xmmword ptr [rax], xmm0
0x1800cd675  call    cs:__imp_CreateThreadpoolWork
0x1800cd67b  mov     rbx, rax
0x1800cd67e  test    rax, rax
0x1800cd681  jz      loc_1800CD728
0x1800cd687  mov     rcx, cs:qword_1803989E8
0x1800cd68e  mov     eax, [rcx]
0x1800cd690  cmp     eax, 4
0x1800cd693  jbe     short loc_1800CD6C7
0x1800cd695  lea     rax, [rsp+78h+var_48]
0x1800cd69a  mov     [rsp+78h+var_28], rdi
0x1800cd69f  mov     [rsp+78h+var_50], rax
0x1800cd6a4  lea     rdx, unk_1803355BA
0x1800cd6ab  xor     r9d, r9d
0x1800cd6ae  mov     [rsp+78h+var_58], 3
0x1800cd6b6  xor     r8d, r8d
0x1800cd6b9  mov     [rsp+78h+var_20], 10h
0x1800cd6c2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800cd6c7  mov     rcx, rbx; pwk
0x1800cd6ca  call    cs:__imp_SubmitThreadpoolWork
0x1800cd6d0  mov     rcx, rbx; pwk
0x1800cd6d3  call    cs:__imp_CloseThreadpoolWork
0x1800cd6d9  mov     rcx, [rsp+78h+var_18]
0x1800cd6de  xor     rcx, rsp; StackCookie
0x1800cd6e1  call    __security_check_cookie
0x1800cd6e6  lea     r11, [rsp+78h+var_8]
0x1800cd6eb  mov     rbx, [r11+18h]
0x1800cd6ef  mov     rsi, [r11+20h]
0x1800cd6f3  mov     rsp, r11
0x1800cd6f6  pop     rdi
0x1800cd6f7  retn
0x1800cd6f8  mov     ecx, 8007000Eh
0x1800cd6fd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800cd702  mov     rcx, [rsp+78h]; this
0x1800cd707  lea     r8, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800cd70e  mov     r9d, eax; char *
0x1800cd711  mov     edx, 0DB0h; void *
0x1800cd716  lea     rax, aMemoryAllocati; "Memory allocation failure. Network dele"...
0x1800cd71d  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800cd722  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800cd728  call    cs:__imp_GetLastError
0x1800cd72e  mov     edx, 10h; struct std::nothrow_t *
0x1800cd733  mov     rcx, rdi; void *
0x1800cd736  mov     ebx, eax
0x1800cd738  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cd73d  test    ebx, ebx
0x1800cd73f  jle     short loc_1800CD74A
0x1800cd741  movzx   ebx, bx
0x1800cd744  or      ebx, 80070000h
0x1800cd74a  mov     ecx, ebx
0x1800cd74c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800cd751  mov     rcx, [rsp+78h]; this
0x1800cd756  lea     r8, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800cd75d  mov     r9d, eax; char *
0x1800cd760  mov     edx, 0DBBh; void *
0x1800cd765  lea     rax, aUnableToCreate_2; "Unable to create thread pool work"
0x1800cd76c  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800cd771  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
