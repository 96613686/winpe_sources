# D3D12PIXGetThreadInfo

- ea: `0x180002440`
- end: `0x180002517`
- name: `D3D12PIXGetThreadInfo`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002440`
- `0x1800119d0`
- `0x180012a0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800024ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002493`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002493`

## pseudocode

```c
__int64 *D3D12PIXGetThreadInfo()
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  _DWORD *v3; // rax
  _BOOL8 v4; // rcx
  _QWORD *v5; // rax

  if ( (Microsoft_Graphics_Tools_PixMarkersEnableBits & 1) == 0 )
    return qword_18001C808;
  v1 = (unsigned int)tls_index;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_QWORD *)(v2 + 24) )
  {
    PEvtInitService();
    AcquireSRWLockExclusive(&SRWLock);
    std::list<PIXEventsThreadInfo>::emplace_back<>();
    v3 = g_pPixEvtCtrlBlk;
    *(_QWORD *)(v2 + 24) = *(_QWORD *)(qword_18001E8A0 + 8) + 16LL;
    v4 = v3 && v3[2] != 1;
    v5 = *(_QWORD **)(v2 + 24);
    *v5 = 0;
    v5[1] = v4;
    v5[2] = -1;
    ReleaseSRWLockExclusive(&SRWLock);
  }
  return *(__int64 **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v1) + 24LL);
}

```

## disassembly

```asm
0x180002440  sub     rsp, 28h
0x180002444  test    cs:Microsoft_Graphics_Tools_PixMarkersEnableBits, 1
0x18000244b  jnz     short loc_180002459
0x18000244d  lea     rax, qword_18001C808
0x180002454  add     rsp, 28h
0x180002458  retn
0x180002459  mov     rax, gs:58h
0x180002462  mov     [rsp+28h+arg_0], rbx
0x180002467  mov     [rsp+28h+arg_8], rsi
0x18000246c  mov     [rsp+28h+var_8], rdi
0x180002471  mov     edi, cs:_tls_index
0x180002477  mov     esi, 18h
0x18000247c  mov     rbx, [rax+rdi*8]
0x180002480  cmp     qword ptr [rbx+rsi], 0
0x180002485  jnz     short loc_1800024F2
0x180002487  call    ?PEvtInitService@@YAJXZ; PEvtInitService(void)
0x18000248c  lea     rcx, SRWLock; SRWLock
0x180002493  call    cs:__imp_AcquireSRWLockExclusive
0x180002499  call    ??$emplace_back@$$V@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAAAEAUPIXEventsThreadInfo@@XZ; std::list<PIXEventsThreadInfo>::emplace_back<>(void)
0x18000249e  mov     rax, cs:qword_18001E8A0
0x1800024a5  mov     rcx, [rax+8]
0x1800024a9  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x1800024b0  add     rcx, 10h
0x1800024b4  mov     [rbx+rsi], rcx
0x1800024b8  test    rax, rax
0x1800024bb  jz      short loc_1800024CC
0x1800024bd  mov     eax, [rax+8]
0x1800024c0  cmp     eax, 1
0x1800024c3  jz      short loc_1800024CC
0x1800024c5  mov     ecx, 1
0x1800024ca  jmp     short loc_1800024CE
0x1800024cc  xor     ecx, ecx
0x1800024ce  mov     rax, [rbx+rsi]
0x1800024d2  mov     qword ptr [rax], 0
0x1800024d9  mov     [rax+8], rcx
0x1800024dd  lea     rcx, SRWLock; SRWLock
0x1800024e4  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800024ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800024f2  mov     rax, gs:58h
0x1800024fb  mov     rbx, [rsp+28h+arg_0]
0x180002500  mov     rcx, [rax+rdi*8]
0x180002504  mov     rdi, [rsp+28h+var_8]
0x180002509  mov     rax, [rsi+rcx]
0x18000250d  mov     rsi, [rsp+28h+arg_8]
0x180002512  jmp     loc_180002454
```
