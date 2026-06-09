# Rdp::Utils::TP::details::CCompletionPortIo::~CCompletionPortIo(void)

- ea: `0x18000fd80`
- end: `0x18000fe36`
- name: `??1CCompletionPortIo@details@TP@Utils@Rdp@@QEAA@XZ`
- size: `182`
- prototype: `void __fastcall(Rdp::Utils::TP::details::CCompletionPortIo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800100d4`

## callees

- `0x1800092b0`
- `0x18000fcac`
- `0x18000fd80`
- `0x18000ff8c`
- `0x180012520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fde4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fde4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fdc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fdc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdf2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000fdb2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18000fdb2`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::CCompletionPortIo::~CCompletionPortIo(
        Rdp::Utils::TP::details::CCompletionPortIo *this)
{
  char *v2; // rcx
  HANDLE *v3; // rdi
  HANDLE v4; // rsi

  *((_BYTE *)this + 24) = 1;
  v2 = *(char **)this;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    PostQueuedCompletionStatus(v2, 0, 0xDEADBEEF, 0);
  v3 = (HANDLE *)((char *)this + 8);
  if ( *((_DWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) == GetCurrentThreadId() )
      std::_Throw_Cpp_error(5);
    v4 = *v3;
    if ( WaitForSingleObjectEx(*v3, 0xFFFFFFFF, 0) == -1 || !CloseHandle(v4) )
      std::_Throw_Cpp_error(2);
    *(_OWORD *)v3 = 0;
  }
  std::_Func_class<void,void *,unsigned long,unsigned __int64>::_Tidy((char *)this + 32);
  std::thread::~thread((Rdp::Utils::TP::details::CCompletionPortIo *)((char *)this + 8));
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(this);
}

```

## disassembly

```asm
0x18000fd80  mov     [rsp+arg_0], rbx
0x18000fd85  mov     [rsp+arg_8], rsi
0x18000fd8a  push    rdi
0x18000fd8b  sub     rsp, 20h
0x18000fd8f  mov     rbx, rcx
0x18000fd92  mov     eax, 1
0x18000fd97  xchg    al, [rcx+18h]
0x18000fd9a  mov     rcx, [rcx]; CompletionPort
0x18000fd9d  lea     rax, [rcx-1]
0x18000fda1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000fda5  ja      short loc_18000FDB8
0x18000fda7  xor     r9d, r9d; lpOverlapped
0x18000fdaa  xor     edx, edx; dwNumberOfBytesTransferred
0x18000fdac  mov     r8d, 0DEADBEEFh; dwCompletionKey
0x18000fdb2  call    cs:__imp_PostQueuedCompletionStatus
0x18000fdb8  lea     rdi, [rbx+8]
0x18000fdbc  cmp     dword ptr [rdi+8], 0
0x18000fdc0  jz      short loc_18000FE03
0x18000fdc2  call    cs:__imp_GetCurrentThreadId
0x18000fdc8  cmp     [rdi+8], eax
0x18000fdcb  jnz     short loc_18000FDD8
0x18000fdcd  mov     ecx, 5; int
0x18000fdd2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000fdd8  mov     rsi, [rdi]
0x18000fddb  xor     r8d, r8d; bAlertable
0x18000fdde  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fde1  mov     rcx, rsi; hHandle
0x18000fde4  call    cs:__imp_WaitForSingleObjectEx
0x18000fdea  cmp     eax, 0FFFFFFFFh
0x18000fded  jz      short loc_18000FE2B
0x18000fdef  mov     rcx, rsi; hObject
0x18000fdf2  call    cs:__imp_CloseHandle
0x18000fdf8  test    eax, eax
0x18000fdfa  jz      short loc_18000FE2B
0x18000fdfc  xorps   xmm0, xmm0
0x18000fdff  movdqu  xmmword ptr [rdi], xmm0
0x18000fe03  lea     rcx, [rbx+20h]
0x18000fe07  call    ?_Tidy@?$_Func_class@XPEAXK_K@std@@IEAAXXZ; std::_Func_class<void,void *,ulong,unsigned __int64>::_Tidy(void)
0x18000fe0c  mov     rcx, rdi; this
0x18000fe0f  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18000fe14  mov     rcx, rbx
0x18000fe17  mov     rbx, [rsp+28h+arg_0]
0x18000fe1c  mov     rsi, [rsp+28h+arg_8]
0x18000fe21  add     rsp, 20h
0x18000fe25  pop     rdi
0x18000fe26  jmp     ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000fe2b  mov     ecx, 2; int
0x18000fe30  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
