# CertProtectCryptsvcDllCtrl

- ea: `0x18000a690`
- end: `0x18000a787`
- name: `CertProtectCryptsvcDllCtrl`
- size: `247`
- prototype: `__int64 __fastcall(int, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a690`
- `0x18000a790`
- `0x18000a814`
- `0x18000c8b4`
- `0x18000cb10`
- `0x18000d25c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a756`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a723`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a71d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a71d`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000a738`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000a738`

## pseudocode

```c
__int64 __fastcall CertProtectCryptsvcDllCtrl(int a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // ebx
  unsigned int v10; // ecx

  v6 = a1 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        if ( a3 == 6 )
        {
          v10 = *(_DWORD *)(a4 + 4);
          if ( v10 )
          {
            if ( fUrlCacheSvcStarted )
            {
              _InterlockedIncrement(&lUrlCacheSvcActiveRefCnt);
              if ( !(unsigned int)FindAndAddToBeRunSessionLogoffJob(v10) )
                GetLastError();
              _InterlockedDecrement(&lUrlCacheSvcActiveRefCnt);
            }
          }
        }
        v8 = 0;
        CertLogoffSessionChange(a3, a4);
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
    else
    {
      v8 = RpcServerUnregisterIf(qword_180019300, 0, 1u);
      CryptnetUrlCacheSvcServiceStop();
      CertLogoffStop();
    }
  }
  else
  {
    InitializeSRWLock(&SRWLock);
    dword_180020358 = 1;
    qword_180020368 = (__int64)&qword_180020360;
    qword_180020360 = &qword_180020360;
    return (unsigned int)CertProtectStart();
  }
  return v8;
}

```

## disassembly

```asm
0x18000a690  mov     [rsp+arg_0], rbx
0x18000a695  mov     [rsp+arg_8], rsi
0x18000a69a  push    rdi
0x18000a69b  sub     rsp, 20h
0x18000a69f  mov     rsi, r9
0x18000a6a2  mov     edi, r8d
0x18000a6a5  sub     ecx, 1
0x18000a6a8  jz      loc_18000A74F
0x18000a6ae  sub     ecx, 1
0x18000a6b1  jz      short loc_18000A72B
0x18000a6b3  cmp     ecx, 1
0x18000a6b6  jnz     short loc_18000A711
0x18000a6b8  cmp     r8d, 6
0x18000a6bc  jz      short loc_18000A6DC
0x18000a6be  xor     ebx, ebx
0x18000a6c0  mov     rdx, rsi
0x18000a6c3  mov     ecx, edi
0x18000a6c5  call    CertLogoffSessionChange
0x18000a6ca  mov     rsi, [rsp+28h+arg_8]
0x18000a6cf  mov     eax, ebx
0x18000a6d1  mov     rbx, [rsp+28h+arg_0]
0x18000a6d6  add     rsp, 20h
0x18000a6da  pop     rdi
0x18000a6db  retn
0x18000a6dc  mov     ecx, [r9+4]
0x18000a6e0  test    ecx, ecx
0x18000a6e2  jz      short loc_18000A6BE
0x18000a6e4  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000a6ea  test    eax, eax
0x18000a6ec  jz      short loc_18000A6BE
0x18000a6ee  lock inc cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x18000a6f5  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000a6fb  test    eax, eax
0x18000a6fd  jz      short loc_18000A718
0x18000a6ff  call    FindAndAddToBeRunSessionLogoffJob
0x18000a704  test    eax, eax
0x18000a706  jz      short loc_18000A723
0x18000a708  lock dec cs:?lUrlCacheSvcActiveRefCnt@@3JC; long volatile lUrlCacheSvcActiveRefCnt
0x18000a70f  jmp     short loc_18000A6BE
0x18000a711  mov     ebx, 8000FFFFh
0x18000a716  jmp     short loc_18000A6CA
0x18000a718  mov     ecx, 426h; dwErrCode
0x18000a71d  call    cs:__imp_SetLastError
0x18000a723  call    cs:__imp_GetLastError
0x18000a729  jmp     short loc_18000A708
0x18000a72b  xor     edx, edx; MgrTypeUuid
0x18000a72d  lea     rcx, qword_180019300; IfSpec
0x18000a734  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000a738  call    cs:__imp_RpcServerUnregisterIf
0x18000a73e  mov     ebx, eax
0x18000a740  call    CryptnetUrlCacheSvcServiceStop
0x18000a745  call    CertLogoffStop
0x18000a74a  jmp     loc_18000A6CA
0x18000a74f  lea     rcx, SRWLock; SRWLock
0x18000a756  call    cs:__imp_InitializeSRWLock
0x18000a75c  lea     rax, qword_180020360
0x18000a763  mov     cs:dword_180020358, 1
0x18000a76d  mov     cs:qword_180020368, rax
0x18000a774  mov     cs:qword_180020360, rax
0x18000a77b  call    CertProtectStart
0x18000a780  mov     ebx, eax
0x18000a782  jmp     loc_18000A6CA
```
