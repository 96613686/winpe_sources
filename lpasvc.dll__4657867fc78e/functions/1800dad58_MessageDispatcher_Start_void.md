# MessageDispatcher::Start(void)

- ea: `0x1800dad58`
- end: `0x1800dae6a`
- name: `?Start@MessageDispatcher@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(PVOID pvCleanupContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180072ad4`

## callees

- `0x18000e4e0`
- `0x18000ebf4`
- `0x18006ba8c`
- `0x1800dab74`
- `0x1800dad58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dae30`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dae30`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dadee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dadee`

## pseudocode

```c
__int64 __fastcall MessageDispatcher::Start(PVOID pvCleanupContext)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  int LastErrorToHResultAndForceFailure; // ebx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v6; // rcx
  __int64 v7; // rax
  PTP_WORK ThreadpoolWork; // rax
  CommonUtil *v9; // rcx

  v2 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( v2 )
    memset_0(v2, 0, 0x48u);
  else
    v3 = 0;
  *((_QWORD *)pvCleanupContext + 14) = v3;
  if ( v3 )
  {
    *(_DWORD *)v3 = 3;
    v3[1] = 0;
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    *((_DWORD *)v3 + 14) = 0;
    *((_DWORD *)v3 + 15) = 1;
    *((_DWORD *)v3 + 16) = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)pvCleanupContext + 15) = ThreadpoolCleanupGroup;
    v6 = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      v7 = *((_QWORD *)pvCleanupContext + 14);
      LastErrorToHResultAndForceFailure = 0;
      *(_QWORD *)(v7 + 16) = v6;
      *(_QWORD *)(v7 + 24) = Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size;
    }
    else
    {
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(0);
      if ( LastErrorToHResultAndForceFailure < 0 )
        goto LABEL_12;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       MessageDispatcher::_ThreadpoolWorkCallback,
                       pvCleanupContext,
                       *((PTP_CALLBACK_ENVIRON *)pvCleanupContext + 14));
    *((_QWORD *)pvCleanupContext + 16) = ThreadpoolWork;
    if ( ThreadpoolWork
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v9),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      *(_DWORD *)pvCleanupContext = 2;
      return (unsigned int)LastErrorToHResultAndForceFailure;
    }
  }
  else
  {
    LastErrorToHResultAndForceFailure = -2147024882;
  }
LABEL_12:
  MessageDispatcher::CleanupThreadpoolEnvironment(pvCleanupContext);
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800dad58  mov     [rsp+arg_0], rbx
0x1800dad5d  push    rdi
0x1800dad5e  sub     rsp, 20h
0x1800dad62  mov     rdi, rcx
0x1800dad65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dad6c  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800dad71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800dad76  mov     rbx, rax
0x1800dad79  test    rax, rax
0x1800dad7c  jz      short loc_1800DAD8E
0x1800dad7e  xor     edx, edx; Val
0x1800dad80  mov     rcx, rax; void *
0x1800dad83  lea     r8d, [rdx+48h]; Size
0x1800dad87  call    memset_0
0x1800dad8c  jmp     short loc_1800DAD90
0x1800dad8e  xor     ebx, ebx
0x1800dad90  mov     [rdi+70h], rbx
0x1800dad94  test    rbx, rbx
0x1800dad97  jnz     short loc_1800DADA3
0x1800dad99  mov     ebx, 8007000Eh
0x1800dad9e  jmp     loc_1800DAE4D
0x1800dada3  mov     dword ptr [rbx], 3
0x1800dada9  mov     qword ptr [rbx+8], 0
0x1800dadb1  mov     qword ptr [rbx+10h], 0
0x1800dadb9  mov     qword ptr [rbx+18h], 0
0x1800dadc1  mov     qword ptr [rbx+20h], 0
0x1800dadc9  mov     qword ptr [rbx+28h], 0
0x1800dadd1  mov     qword ptr [rbx+30h], 0
0x1800dadd9  mov     dword ptr [rbx+38h], 0
0x1800dade0  mov     dword ptr [rbx+3Ch], 1
0x1800dade7  mov     dword ptr [rbx+40h], 48h ; 'H'
0x1800dadee  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800dadf4  mov     [rdi+78h], rax
0x1800dadf8  mov     rcx, rax; this
0x1800dadfb  test    rax, rax
0x1800dadfe  jnz     short loc_1800DAE0D
0x1800dae00  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800dae05  mov     ebx, eax
0x1800dae07  test    eax, eax
0x1800dae09  js      short loc_1800DAE4D
0x1800dae0b  jmp     short loc_1800DAE22
0x1800dae0d  mov     rax, [rdi+70h]
0x1800dae11  xor     ebx, ebx
0x1800dae13  mov     [rax+10h], rcx
0x1800dae17  lea     rcx, ?set_buffer_size@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@UEAAX_KH@Z; Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::set_buffer_size(unsigned __int64,int)
0x1800dae1e  mov     [rax+18h], rcx
0x1800dae22  mov     r8, [rdi+70h]; pcbe
0x1800dae26  lea     rcx, ?_ThreadpoolWorkCallback@MessageDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dae2d  mov     rdx, rdi; pv
0x1800dae30  call    cs:__imp_CreateThreadpoolWork
0x1800dae36  mov     [rdi+80h], rax
0x1800dae3d  test    rax, rax
0x1800dae40  jnz     short loc_1800DAE57
0x1800dae42  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800dae47  mov     ebx, eax
0x1800dae49  test    eax, eax
0x1800dae4b  jns     short loc_1800DAE57
0x1800dae4d  mov     rcx, rdi; pvCleanupContext
0x1800dae50  call    ?CleanupThreadpoolEnvironment@MessageDispatcher@@AEAAXXZ; MessageDispatcher::CleanupThreadpoolEnvironment(void)
0x1800dae55  jmp     short loc_1800DAE5D
0x1800dae57  mov     dword ptr [rdi], 2
0x1800dae5d  mov     eax, ebx
0x1800dae5f  mov     rbx, [rsp+28h+arg_0]
0x1800dae64  add     rsp, 20h
0x1800dae68  pop     rdi
0x1800dae69  retn
```
