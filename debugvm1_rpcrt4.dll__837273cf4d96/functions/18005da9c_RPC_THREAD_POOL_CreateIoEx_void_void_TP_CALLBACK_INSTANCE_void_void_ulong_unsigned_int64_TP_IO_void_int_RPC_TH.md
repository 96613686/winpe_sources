# RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)

- ea: `0x18005da9c`
- end: `0x18005db56`
- name: `?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z`
- size: `186`
- prototype: `__int64 __usercall@<rax>(HANDLE fl@<rcx>, PTP_WIN32_IO_CALLBACK pfnio@<rdx>, PVOID pv@<r8>, int@<r9d>, struct RPC_THREAD_POOL_IO **)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005cf30`
- `0x18005fe3c`
- `0x18007e494`
- `0x180080400`
- `0x1800992b0`
- `0x1800c70dc`

## callees

- `0x180021e70`
- `0x18005da9c`
- `0x18005de08`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18005dadd`
- `ntdll!NtSetInformationFile` at `0x18005dadd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18005db49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18005db49`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18005db00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18005db00`

## pseudocode

```c
__int64 __fastcall RPC_THREAD_POOL::CreateIoEx(
        HANDLE fl,
        PTP_WIN32_IO_CALLBACK pfnio,
        PVOID pv,
        int a4,
        struct RPC_THREAD_POOL_IO **a5)
{
  __int64 result; // rax
  struct _TP_IO *ThreadpoolIo; // rbx
  struct _TP_IO **v10; // rax
  struct RPC_THREAD_POOL_IO **v11; // rcx
  struct _IO_STATUS_BLOCK v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  if ( a4 )
  {
    v13 = 2;
    v12 = 0;
    if ( NtSetInformationFile(fl, &v12, &v13, 4u, FileIoCompletionNotificationInformation) < 0 )
      return 14;
  }
  result = RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary();
  if ( (_DWORD)result )
    return result;
  ThreadpoolIo = CreateThreadpoolIo(fl, pfnio, pv, RPC_THREAD_POOL::CallbackEnvironment);
  if ( !ThreadpoolIo )
    return 14;
  v10 = (struct _TP_IO **)AllocWrapper(8u);
  if ( !v10 )
  {
    *a5 = 0;
    CloseThreadpoolIo(ThreadpoolIo);
    return 14;
  }
  v11 = a5;
  *v10 = ThreadpoolIo;
  *v11 = (struct RPC_THREAD_POOL_IO *)v10;
  return 0;
}

```

## disassembly

```asm
0x18005da9c  mov     rax, rsp
0x18005da9f  mov     [rax+8], rbx
0x18005daa3  mov     [rax+10h], rsi
0x18005daa7  push    rdi
0x18005daa8  sub     rsp, 40h
0x18005daac  mov     rdi, r8
0x18005daaf  mov     rsi, rdx
0x18005dab2  mov     rbx, rcx
0x18005dab5  test    r9d, r9d
0x18005dab8  jz      short loc_18005DAE7
0x18005daba  xorps   xmm0, xmm0
0x18005dabd  mov     dword ptr [rax+20h], 2
0x18005dac4  mov     r9d, 4; Length
0x18005daca  mov     dword ptr [rax-28h], 29h ; ')'
0x18005dad1  lea     r8, [rax+20h]; FileInformation
0x18005dad5  lea     rdx, [rax-18h]; IoStatusBlock
0x18005dad9  movups  xmmword ptr [rax-18h], xmm0
0x18005dadd  call    cs:__imp_NtSetInformationFile
0x18005dae3  test    eax, eax
0x18005dae5  js      short loc_18005DB4F
0x18005dae7  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18005daec  test    eax, eax
0x18005daee  jnz     short loc_18005DB2A
0x18005daf0  mov     r9, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18005daf7  mov     r8, rdi; pv
0x18005dafa  mov     rdx, rsi; pfnio
0x18005dafd  mov     rcx, rbx; fl
0x18005db00  call    cs:__imp_CreateThreadpoolIo
0x18005db06  mov     rbx, rax
0x18005db09  test    rax, rax
0x18005db0c  jz      short loc_18005DB4F
0x18005db0e  mov     ecx, 8; dwBytes
0x18005db13  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18005db18  test    rax, rax
0x18005db1b  jz      short loc_18005DB3A
0x18005db1d  mov     rcx, [rsp+48h+arg_20]
0x18005db22  mov     [rax], rbx
0x18005db25  mov     [rcx], rax
0x18005db28  xor     eax, eax
0x18005db2a  mov     rbx, [rsp+48h+arg_0]
0x18005db2f  mov     rsi, [rsp+48h+arg_8]
0x18005db34  add     rsp, 40h
0x18005db38  pop     rdi
0x18005db39  retn
0x18005db3a  mov     rax, [rsp+48h+arg_20]
0x18005db3f  mov     rcx, rbx; pio
0x18005db42  mov     qword ptr [rax], 0
0x18005db49  call    cs:__imp_CloseThreadpoolIo
0x18005db4f  mov     eax, 0Eh
0x18005db54  jmp     short loc_18005DB2A
```
