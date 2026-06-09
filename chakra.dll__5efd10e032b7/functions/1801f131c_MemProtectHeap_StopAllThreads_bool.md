# MemProtectHeap::StopAllThreads(bool)

- ea: `0x1801f131c`
- end: `0x1801f14a7`
- name: `?StopAllThreads@MemProtectHeap@@AEAAX_N@Z`
- size: `395`
- prototype: `void __fastcall(MemProtectHeap *__hidden this, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801f14f0`
- `0x1803a0d10`
- `0x1803dfff0`

## callees

- `0x1801f131c`
- `0x1801f14b0`
- `0x1801f1814`
- `0x1801f19c4`
- `0x1801f1bbc`
- `0x1803d9ed8`
- `0x180494734`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801f1472`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801f1472`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801f1346`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801f1346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f1380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f1380`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f13aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f13aa`

## pseudocode

```c
void __fastcall MemProtectHeap::StopAllThreads(MemProtectHeap *this, char a2)
{
  MemProtectThreadContext *Value; // rax
  __int64 v4; // rcx
  MemProtectThreadContext *v5; // rsi
  MemProtectHeap *v6; // rcx
  __int64 i; // rdi
  __int64 j; // rdi
  MemProtectThreadContext *v9; // rdi
  char v10; // bp
  void (__fastcall *v11)(_QWORD); // rax
  MemProtectThreadContext *k; // rdi

  if ( *((_QWORD *)this + 7) )
  {
    Value = (MemProtectThreadContext *)TlsGetValue(*(_DWORD *)this);
    v4 = *((_QWORD *)this + 7);
    v5 = Value;
    if ( Value != (MemProtectThreadContext *)v4 || *(_QWORD *)(v4 + 8) )
    {
      if ( *((_DWORD *)this + 13) == 1 )
      {
        if ( a2 )
        {
          *((_DWORD *)this + 20) = GetCurrentThreadId();
          if ( !(unsigned int)Memory::Recycler::RequestConcurrentWrapperCallback((MemProtectHeap *)((char *)this + 560)) )
            RaiseFailFastException(0, 0, 0);
        }
        else
        {
          MemProtectHeap::BeginSuspendProtection((MemProtectHeap *)v4);
          for ( i = *((_QWORD *)this + 7); i; i = *(_QWORD *)(i + 8) )
          {
            if ( *(_DWORD *)(i + 80) != *((_DWORD *)this + 20) )
              MemProtectThreadContext::RequestSuspension((MemProtectThreadContext *)i);
          }
          for ( j = *((_QWORD *)this + 7); j; j = *(_QWORD *)(j + 8) )
          {
            if ( *(_DWORD *)(j + 80) != *((_DWORD *)this + 20) )
              MemProtectThreadContext::EnsureSuspended((MemProtectThreadContext *)j);
          }
          MemProtectHeap::EndSuspendProtection(v6);
        }
      }
      else
      {
        while ( v4 )
        {
          if ( (MemProtectThreadContext *)v4 != Value )
            _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 20), 1, 0);
          v4 = *(_QWORD *)(v4 + 8);
        }
        v9 = (MemProtectThreadContext *)*((_QWORD *)this + 7);
        v10 = 0;
        if ( v9 )
        {
          do
          {
            if ( v9 != v5 && MemProtectThreadContext::IsRunning(v9) )
            {
              v11 = (void (__fastcall *)(_QWORD))*((_QWORD *)v9 + 8);
              if ( v11 )
                v11(*((_QWORD *)v9 + 9));
              v10 = 1;
            }
            v9 = (MemProtectThreadContext *)*((_QWORD *)v9 + 1);
          }
          while ( v9 );
          if ( v10 )
          {
            for ( k = (MemProtectThreadContext *)*((_QWORD *)this + 7); k; k = (MemProtectThreadContext *)*((_QWORD *)k + 1) )
            {
              if ( k != v5 )
              {
                while ( MemProtectThreadContext::IsRunning(k) )
                  WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801f131c  mov     rax, rsp
0x1801f131f  mov     [rax+18h], rbx
0x1801f1323  mov     [rax+20h], rbp
0x1801f1327  mov     [rax+10h], dl
0x1801f132a  mov     [rax+8], rcx
0x1801f132e  push    rsi
0x1801f132f  push    rdi
0x1801f1330  push    r15
0x1801f1332  sub     rsp, 20h
0x1801f1336  cmp     qword ptr [rcx+38h], 0
0x1801f133b  mov     rbx, rcx
0x1801f133e  jz      loc_1801F1493
0x1801f1344  mov     ecx, [rcx]; dwTlsIndex
0x1801f1346  call    cs:__imp_TlsGetValue
0x1801f134d  nop     dword ptr [rax+rax+00h]
0x1801f1352  mov     rcx, [rbx+38h]; this
0x1801f1356  mov     rsi, rax
0x1801f1359  cmp     rax, rcx
0x1801f135c  jnz     short loc_1801F1369
0x1801f135e  cmp     qword ptr [rcx+8], 0
0x1801f1363  jz      loc_1801F1493
0x1801f1369  mov     r15d, 1
0x1801f136f  cmp     [rbx+34h], r15d
0x1801f1373  jnz     loc_1801F1419
0x1801f1379  cmp     [rsp+38h+arg_8], 0
0x1801f137e  jz      short loc_1801F13BB
0x1801f1380  call    cs:__imp_GetCurrentThreadId
0x1801f1387  nop     dword ptr [rax+rax+00h]
0x1801f138c  lea     rcx, [rbx+230h]; this
0x1801f1393  mov     [rbx+50h], eax
0x1801f1396  call    ?RequestConcurrentWrapperCallback@Recycler@Memory@@QEAAHXZ; Memory::Recycler::RequestConcurrentWrapperCallback(void)
0x1801f139b  test    eax, eax
0x1801f139d  jnz     loc_1801F1493
0x1801f13a3  xor     r8d, r8d; dwFlags
0x1801f13a6  xor     edx, edx; pContextRecord
0x1801f13a8  xor     ecx, ecx; pExceptionRecord
0x1801f13aa  call    cs:__imp_RaiseFailFastException
0x1801f13b1  nop     dword ptr [rax+rax+00h]
0x1801f13b6  jmp     loc_1801F1493
0x1801f13bb  call    ?BeginSuspendProtection@MemProtectHeap@@AEAAXXZ; MemProtectHeap::BeginSuspendProtection(void)
0x1801f13c0  mov     rdi, [rbx+38h]
0x1801f13c4  jmp     short loc_1801F13DA
0x1801f13c6  mov     eax, [rbx+50h]
0x1801f13c9  cmp     [rdi+50h], eax
0x1801f13cc  jz      short loc_1801F13D6
0x1801f13ce  mov     rcx, rdi; this
0x1801f13d1  call    ?RequestSuspension@MemProtectThreadContext@@QEAAXXZ; MemProtectThreadContext::RequestSuspension(void)
0x1801f13d6  mov     rdi, [rdi+8]
0x1801f13da  test    rdi, rdi
0x1801f13dd  jnz     short loc_1801F13C6
0x1801f13df  mov     rdi, [rbx+38h]
0x1801f13e3  jmp     short loc_1801F13F9
0x1801f13e5  mov     eax, [rbx+50h]
0x1801f13e8  cmp     [rdi+50h], eax
0x1801f13eb  jz      short loc_1801F13F5
0x1801f13ed  mov     rcx, rdi; this
0x1801f13f0  call    ?EnsureSuspended@MemProtectThreadContext@@QEAAXXZ; MemProtectThreadContext::EnsureSuspended(void)
0x1801f13f5  mov     rdi, [rdi+8]
0x1801f13f9  test    rdi, rdi
0x1801f13fc  jnz     short loc_1801F13E5
0x1801f13fe  call    ?EndSuspendProtection@MemProtectHeap@@AEAAXXZ; MemProtectHeap::EndSuspendProtection(void)
0x1801f1403  jmp     loc_1801F1493
0x1801f1408  cmp     rcx, rsi
0x1801f140b  jz      short loc_1801F1415
0x1801f140d  xor     eax, eax
0x1801f140f  lock cmpxchg [rcx+14h], r15d
0x1801f1415  mov     rcx, [rcx+8]
0x1801f1419  test    rcx, rcx
0x1801f141c  jnz     short loc_1801F1408
0x1801f141e  mov     rdi, [rbx+38h]
0x1801f1422  xor     bpl, bpl
0x1801f1425  test    rdi, rdi
0x1801f1428  jz      short loc_1801F1493
0x1801f142a  cmp     rdi, rsi
0x1801f142d  jz      short loc_1801F1450
0x1801f142f  mov     rcx, rdi; this
0x1801f1432  call    ?IsRunning@MemProtectThreadContext@@QEAA_NXZ; MemProtectThreadContext::IsRunning(void)
0x1801f1437  test    al, al
0x1801f1439  jz      short loc_1801F1450
0x1801f143b  mov     rax, [rdi+40h]
0x1801f143f  test    rax, rax
0x1801f1442  jz      short loc_1801F144D
0x1801f1444  mov     rcx, [rdi+48h]
0x1801f1448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f144d  mov     bpl, r15b
0x1801f1450  mov     rdi, [rdi+8]
0x1801f1454  test    rdi, rdi
0x1801f1457  jnz     short loc_1801F142A
0x1801f1459  test    bpl, bpl
0x1801f145c  jz      short loc_1801F1493
0x1801f145e  mov     rdi, [rbx+38h]
0x1801f1462  jmp     short loc_1801F148E
0x1801f1464  cmp     rdi, rsi
0x1801f1467  jnz     short loc_1801F147E
0x1801f1469  jmp     short loc_1801F148A
0x1801f146b  mov     rcx, [rbx+48h]; hHandle
0x1801f146f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801f1472  call    cs:__imp_WaitForSingleObject
0x1801f1479  nop     dword ptr [rax+rax+00h]
0x1801f147e  mov     rcx, rdi; this
0x1801f1481  call    ?IsRunning@MemProtectThreadContext@@QEAA_NXZ; MemProtectThreadContext::IsRunning(void)
0x1801f1486  test    al, al
0x1801f1488  jnz     short loc_1801F146B
0x1801f148a  mov     rdi, [rdi+8]
0x1801f148e  test    rdi, rdi
0x1801f1491  jnz     short loc_1801F1464
0x1801f1493  mov     rbx, [rsp+38h+arg_10]
0x1801f1498  mov     rbp, [rsp+38h+arg_18]
0x1801f149d  add     rsp, 20h
0x1801f14a1  pop     r15
0x1801f14a3  pop     rdi
0x1801f14a4  pop     rsi
0x1801f14a5  retn
```
