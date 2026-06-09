# RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)

- ea: `0x18005de08`
- end: `0x18005df6d`
- name: `?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f928`
- `0x18005da9c`
- `0x18005dc48`
- `0x18005dcfc`
- `0x18005ddc0`
- `0x180093914`
- `0x18009c5a4`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18005de08`
- `0x1800ca140`

## import_xrefs

- `ntdll!TpDisablePoolCallbackChecks` at `0x18005decf`
- `ntdll!TpDisablePoolCallbackChecks` at `0x18005decf`
- `ntdll!TpSetPoolStackInformation` at `0x18005def5`
- `ntdll!TpSetPoolStackInformation` at `0x18005def5`
- `ntdll!RtlNtStatusToDosError` at `0x18005defd`
- `ntdll!RtlNtStatusToDosError` at `0x18005defd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005deba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005deba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005df65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005df65`

## pseudocode

```c
__int64 RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
{
  unsigned int v0; // edi
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  PTP_POOL Threadpool; // rax
  struct _TP_POOL *v4; // rsi
  NTSTATUS v5; // eax
  unsigned __int128 v7; // [rsp+20h] [rbp-28h] BYREF

  v7 = 0;
  if ( !RPC_THREAD_POOL::PoolStarted )
    RPC_THREAD_POOL::PoolStarted = 1;
  if ( !RPC_THREAD_POOL::CallbackEnvironment && RPC_THREAD_POOL::PrivatePool )
  {
    v1 = AllocWrapper(0x48u);
    v2 = v1;
    if ( !v1 )
      return 14;
    *(_DWORD *)v1 = 3;
    v1[1] = 0;
    v1[2] = 0;
    v1[3] = 0;
    v1[4] = 0;
    v1[5] = 0;
    v1[6] = 0;
    *((_DWORD *)v1 + 14) = 0;
    *((_DWORD *)v1 + 15) = 1;
    *((_DWORD *)v1 + 16) = 72;
    Threadpool = CreateThreadpool(0);
    v4 = Threadpool;
    if ( !Threadpool )
    {
      v0 = 14;
      goto LABEL_16;
    }
    TpDisablePoolCallbackChecks(Threadpool);
    v7 = __PAIR128__(RPC_THREAD_POOL::CommitStackSize, RPC_THREAD_POOL::ReserveStackSize);
    v5 = TpSetPoolStackInformation(v4, &v7);
    if ( RtlNtStatusToDosError(v5) )
    {
      v0 = 14;
    }
    else
    {
      v2[1] = v4;
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)&RPC_THREAD_POOL::CallbackEnvironment,
              (signed __int64)v2,
              0) )
      {
        v4 = 0;
        v2 = 0;
      }
      v0 = 0;
      if ( !v4 )
      {
LABEL_12:
        if ( !v2 )
          return v0;
LABEL_16:
        FreeWrapper(v2);
        return v0;
      }
    }
    CloseThreadpool(v4);
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x18005de08  mov     [rsp+arg_0], rbx
0x18005de0d  mov     [rsp+arg_8], rsi
0x18005de12  push    rdi
0x18005de13  sub     rsp, 40h
0x18005de17  mov     rax, cs:__security_cookie
0x18005de1e  xor     rax, rsp
0x18005de21  mov     [rsp+48h+var_18], rax
0x18005de26  cmp     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, 0; int RPC_THREAD_POOL::PoolStarted
0x18005de2d  xorps   xmm0, xmm0
0x18005de30  movups  [rsp+48h+var_28], xmm0
0x18005de35  mov     edi, 1
0x18005de3a  jnz     short loc_18005DE42
0x18005de3c  mov     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, edi; int RPC_THREAD_POOL::PoolStarted
0x18005de42  mov     rax, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18005de49  test    rax, rax
0x18005de4c  jnz     short loc_18005DE56
0x18005de4e  cmp     cs:?PrivatePool@RPC_THREAD_POOL@@0HA, eax; int RPC_THREAD_POOL::PrivatePool
0x18005de54  jnz     short loc_18005DE5D
0x18005de56  xor     edi, edi
0x18005de58  jmp     loc_18005DF28
0x18005de5d  mov     esi, 48h ; 'H'
0x18005de62  mov     ecx, esi; dwBytes
0x18005de64  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18005de69  mov     rbx, rax
0x18005de6c  test    rax, rax
0x18005de6f  jz      loc_18005DF47
0x18005de75  xor     ecx, ecx; reserved
0x18005de77  mov     dword ptr [rax], 3
0x18005de7d  mov     qword ptr [rax+8], 0
0x18005de85  mov     qword ptr [rax+10h], 0
0x18005de8d  mov     qword ptr [rax+18h], 0
0x18005de95  mov     qword ptr [rax+20h], 0
0x18005de9d  mov     qword ptr [rax+28h], 0
0x18005dea5  mov     qword ptr [rax+30h], 0
0x18005dead  mov     dword ptr [rax+38h], 0
0x18005deb4  mov     [rax+3Ch], edi
0x18005deb7  mov     [rax+40h], esi
0x18005deba  call    cs:__imp_CreateThreadpool
0x18005dec0  mov     rsi, rax
0x18005dec3  test    rax, rax
0x18005dec6  jz      loc_18005DF4E
0x18005decc  mov     rcx, rax
0x18005decf  call    cs:__imp_TpDisablePoolCallbackChecks
0x18005ded5  mov     rax, cs:?ReserveStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::ReserveStackSize
0x18005dedc  lea     rdx, [rsp+48h+var_28]
0x18005dee1  mov     qword ptr [rsp+48h+var_28], rax
0x18005dee6  mov     rcx, rsi
0x18005dee9  mov     rax, cs:?CommitStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::CommitStackSize
0x18005def0  mov     qword ptr [rsp+48h+var_28+8], rax
0x18005def5  call    cs:__imp_TpSetPoolStackInformation
0x18005defb  mov     ecx, eax; Status
0x18005defd  call    cs:__imp_RtlNtStatusToDosError
0x18005df03  test    eax, eax
0x18005df05  jnz     short loc_18005DF5D
0x18005df07  mov     [rbx+8], rsi
0x18005df0b  xor     eax, eax
0x18005df0d  lock cmpxchg cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA, rbx; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18005df16  jnz     short loc_18005DF1C
0x18005df18  xor     esi, esi
0x18005df1a  xor     ebx, ebx
0x18005df1c  xor     edi, edi
0x18005df1e  test    rsi, rsi
0x18005df21  jnz     short loc_18005DF62
0x18005df23  test    rbx, rbx
0x18005df26  jnz     short loc_18005DF53
0x18005df28  mov     eax, edi
0x18005df2a  mov     rcx, [rsp+48h+var_18]
0x18005df2f  xor     rcx, rsp; StackCookie
0x18005df32  call    __security_check_cookie
0x18005df37  mov     rbx, [rsp+48h+arg_0]
0x18005df3c  mov     rsi, [rsp+48h+arg_8]
0x18005df41  add     rsp, 40h
0x18005df45  pop     rdi
0x18005df46  retn
0x18005df47  mov     edi, 0Eh
0x18005df4c  jmp     short loc_18005DF28
0x18005df4e  mov     edi, 0Eh
0x18005df53  mov     rcx, rbx; lpMem
0x18005df56  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005df5b  jmp     short loc_18005DF28
0x18005df5d  mov     edi, 0Eh
0x18005df62  mov     rcx, rsi; ptpp
0x18005df65  call    cs:__imp_CloseThreadpool
0x18005df6b  jmp     short loc_18005DF23
```
