# WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(WcmCommon::QueueingScheme)

- ea: `0x180036ab8`
- end: `0x180036c27`
- name: `??0ThreadPoolWorkQueue@WcmCommon@@QEAA@W4QueueingScheme@1@@Z`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180072974`
- `0x180081a68`
- `0x18009b338`
- `0x18009d46c`
- `0x1800ba774`
- `0x180127024`

## callees

- `0x180036ab8`
- `0x180036c30`
- `0x180036c58`
- `0x180036c7c`
- `0x180047640`
- `0x1800a8dac`
- `0x1800a9738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180036ae3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180036ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036bf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036bf6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036bee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036bee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036be5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036be5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(__int64 a1)
{
  struct _TP_WORK **v2; // r14
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  struct _TP_WORK *v8; // rbp
  struct _TP_WORK *v9; // rdi
  DWORD LastError; // ebx
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  *(_DWORD *)a1 = 1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 8), 0x1F4u, 0);
  *(_QWORD *)(a1 + 120) = 0;
  memset_0((void *)(a1 + 48), 0, 0x48u);
  v2 = (struct _TP_WORK **)(a1 + 128);
  *(_QWORD *)(a1 + 128) = 0;
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(a1 + 136);
  std::atomic<unsigned long>::atomic<unsigned long>(a1 + 144);
  v12 = a1 + 152;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  v3 = operator new(0x10u);
  v3[1] = 0;
  *(_QWORD *)(a1 + 152) = v3;
  *v3 = a1 + 152;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  v4 = operator new(0x10u);
  v4[1] = 0;
  *(_QWORD *)(a1 + 192) = v4;
  *v4 = a1 + 192;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  v5 = operator new(0x10u);
  v5[1] = 0;
  *(_QWORD *)(a1 + 232) = v5;
  *v5 = a1 + 232;
  *(_BYTE *)(a1 + 272) = 0;
  v6 = (_QWORD *)WcmCommon::details::TPEnvironment::create_tp(
                   a1 + 48,
                   &v12,
                   WcmCommon::ThreadPoolWorkQueue::WorkCallback,
                   a1);
  v7 = v6;
  if ( (_QWORD *)(a1 + 128) != v6 )
  {
    v8 = (struct _TP_WORK *)*v6;
    v9 = *v2;
    if ( *v2 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v9, 1);
      CloseThreadpoolWork(v9);
      SetLastError(LastError);
    }
    *v2 = v8;
    *v7 = 0;
  }
  if ( v12 )
    wil::details::DestroyThreadPoolWork<0>::Destroy();
  return a1;
}

```

## disassembly

```asm
0x180036ab8  mov     [rsp+arg_0], rcx
0x180036abd  push    rbx
0x180036abe  push    rbp
0x180036abf  push    rsi
0x180036ac0  push    rdi
0x180036ac1  push    r12
0x180036ac3  push    r14
0x180036ac5  push    r15
0x180036ac7  sub     rsp, 20h
0x180036acb  mov     r15, rcx
0x180036ace  xor     r12d, r12d
0x180036ad1  mov     dword ptr [rcx], 1
0x180036ad7  add     rcx, 8; lpCriticalSection
0x180036adb  xor     r8d, r8d; Flags
0x180036ade  mov     edx, 1F4h; dwSpinCount
0x180036ae3  call    cs:__imp_InitializeCriticalSectionEx
0x180036ae9  nop
0x180036aea  mov     [r15+78h], r12
0x180036aee  xor     edx, edx; Val
0x180036af0  lea     r8d, [r12+48h]; Size
0x180036af5  lea     rcx, [r15+30h]; void *
0x180036af9  call    memset_0
0x180036afe  nop
0x180036aff  lea     r14, [r15+80h]
0x180036b06  mov     [r14], r12
0x180036b09  lea     rcx, [r15+88h]
0x180036b10  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180036b15  lea     rcx, [r15+90h]
0x180036b1c  call    ??0?$atomic@K@std@@QEAA@K@Z; std::atomic<ulong>::atomic<ulong>(ulong)
0x180036b21  lea     rdi, [r15+98h]
0x180036b28  mov     [rsp+58h+arg_10], rdi
0x180036b2d  mov     [rdi], r12
0x180036b30  mov     [rdi+8], r12
0x180036b34  mov     [rdi+10h], r12
0x180036b38  mov     [rdi+18h], r12
0x180036b3c  mov     [rdi+20h], r12
0x180036b40  lea     ebp, [r12+10h]
0x180036b45  mov     ecx, ebp; Size
0x180036b47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036b4c  mov     [rax+8], r12
0x180036b50  mov     [rdi], rax
0x180036b53  mov     [rax], rdi
0x180036b56  lea     rbx, [rdi+28h]
0x180036b5a  mov     [rbx], r12
0x180036b5d  mov     [rbx+8], r12
0x180036b61  mov     [rbx+10h], r12
0x180036b65  mov     [rbx+18h], r12
0x180036b69  mov     [rbx+20h], r12
0x180036b6d  mov     ecx, ebp; Size
0x180036b6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036b74  mov     [rax+8], r12
0x180036b78  mov     [rbx], rax
0x180036b7b  mov     [rax], rbx
0x180036b7e  lea     rbx, [rdi+50h]
0x180036b82  mov     [rbx], r12
0x180036b85  mov     [rbx+8], r12
0x180036b89  mov     [rbx+10h], r12
0x180036b8d  mov     [rbx+18h], r12
0x180036b91  mov     [rbx+20h], r12
0x180036b95  mov     ecx, ebp; Size
0x180036b97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036b9c  mov     [rax+8], r12
0x180036ba0  mov     [rbx], rax
0x180036ba3  mov     [rax], rbx
0x180036ba6  mov     [rdi+78h], r12b
0x180036baa  mov     r9, r15
0x180036bad  lea     r8, ?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x180036bb4  lea     rdx, [rsp+58h+arg_10]
0x180036bb9  lea     rcx, [r15+30h]
0x180036bbd  call    ?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x180036bc2  mov     rsi, rax
0x180036bc5  cmp     r14, rax
0x180036bc8  jz      short loc_180036C02
0x180036bca  mov     rbp, [rax]
0x180036bcd  mov     rdi, [r14]
0x180036bd0  test    rdi, rdi
0x180036bd3  jz      short loc_180036BFC
0x180036bd5  call    cs:__imp_GetLastError
0x180036bdb  mov     ebx, eax
0x180036bdd  lea     edx, [r12+1]; fCancelPendingCallbacks
0x180036be2  mov     rcx, rdi; pwk
0x180036be5  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180036beb  mov     rcx, rdi; pwk
0x180036bee  call    cs:__imp_CloseThreadpoolWork
0x180036bf4  mov     ecx, ebx; dwErrCode
0x180036bf6  call    cs:__imp_SetLastError
0x180036bfc  mov     [r14], rbp
0x180036bff  mov     [rsi], r12
0x180036c02  mov     rcx, [rsp+58h+arg_10]
0x180036c07  test    rcx, rcx
0x180036c0a  jnz     short loc_180036C1E
0x180036c0c  mov     rax, r15
0x180036c0f  add     rsp, 20h
0x180036c13  pop     r15
0x180036c15  pop     r14
0x180036c17  pop     r12
0x180036c19  pop     rdi
0x180036c1a  pop     rsi
0x180036c1b  pop     rbp
0x180036c1c  pop     rbx
0x180036c1d  retn
0x180036c1e  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x180036c23  nop
0x180036c24  jmp     short loc_180036C0C
```
