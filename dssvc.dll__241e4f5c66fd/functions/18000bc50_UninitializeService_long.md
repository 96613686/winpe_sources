# UninitializeService(long)

- ea: `0x18000bc50`
- end: `0x18000bc98`
- name: `?UninitializeService@@YAJJ@Z`
- size: `72`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b8a0`
- `0x18000ba60`

## callees

- `0x1800047f4`
- `0x180006f78`
- `0x18000bc50`
- `0x18000bf80`
- `0x180018420`

## pseudocode

```c
__int64 __fastcall UninitializeService(DevPlat::Shared *a1, unsigned int a2, void *a3)
{
  __int64 v3; // rcx
  int v4; // ebx
  int *v5; // rax
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-18h]

  v4 = DevPlat::Shared::ShutdownRPCServerInSession(a1, a2, a3);
  if ( v4 < 0 )
  {
    v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v3);
    v7 = v4;
    DSLogger::LogError((DSLogger *)v5, L"SvcUnregisterRPCInterface", 318, L"hr=0x%x.", v7);
  }
  DeInitSvcApi();
  result = 0;
  if ( v4 < 0 )
    return (unsigned int)v4;
  return result;
}

```

## disassembly

```asm
0x18000bc50  push    rbx
0x18000bc52  sub     rsp, 30h
0x18000bc56  call    ?ShutdownRPCServerInSession@Shared@DevPlat@@YAJKPEAX@Z; DevPlat::Shared::ShutdownRPCServerInSession(ulong,void *)
0x18000bc5b  mov     ebx, eax
0x18000bc5d  test    eax, eax
0x18000bc5f  jns     short loc_18000BC86
0x18000bc61  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000bc66  lea     r9, aHr0xX; "hr=0x%x."
0x18000bc6d  mov     [rsp+38h+var_18], ebx
0x18000bc71  mov     r8d, 13Eh; unsigned int
0x18000bc77  lea     rdx, aSvcunregisterr; "SvcUnregisterRPCInterface"
0x18000bc7e  mov     rcx, rax; this
0x18000bc81  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000bc86  call    ?DeInitSvcApi@@YAJXZ; DeInitSvcApi(void)
0x18000bc8b  xor     eax, eax
0x18000bc8d  test    ebx, ebx
0x18000bc8f  cmovs   eax, ebx
0x18000bc92  add     rsp, 30h
0x18000bc96  pop     rbx
0x18000bc97  retn
```
