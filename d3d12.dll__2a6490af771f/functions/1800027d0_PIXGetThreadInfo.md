# PIXGetThreadInfo

- ea: `0x1800027d0`
- end: `0x1800028a7`
- name: `PIXGetThreadInfo`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012e30`

## callees

- `0x1800027d0`
- `0x1800119d0`
- `0x180012a0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000287c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000287c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002823`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002823`

## pseudocode

```c
__int64 *PIXGetThreadInfo()
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  _DWORD *v3; // rax
  _BOOL8 v4; // rax
  _QWORD *v5; // rdx

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
0x1800027d0  sub     rsp, 28h
0x1800027d4  test    cs:Microsoft_Graphics_Tools_PixMarkersEnableBits, 1
0x1800027db  jnz     short loc_1800027E9
0x1800027dd  lea     rax, qword_18001C808
0x1800027e4  add     rsp, 28h
0x1800027e8  retn
0x1800027e9  mov     rax, gs:58h
0x1800027f2  mov     [rsp+28h+arg_0], rbx
0x1800027f7  mov     [rsp+28h+arg_8], rsi
0x1800027fc  mov     [rsp+28h+var_8], rdi
0x180002801  mov     edi, cs:_tls_index
0x180002807  mov     esi, 18h
0x18000280c  mov     rbx, [rax+rdi*8]
0x180002810  cmp     qword ptr [rbx+rsi], 0
0x180002815  jnz     short loc_180002882
0x180002817  call    ?PEvtInitService@@YAJXZ; PEvtInitService(void)
0x18000281c  lea     rcx, SRWLock; SRWLock
0x180002823  call    cs:__imp_AcquireSRWLockExclusive
0x180002829  call    ??$emplace_back@$$V@?$list@UPIXEventsThreadInfo@@V?$allocator@UPIXEventsThreadInfo@@@std@@@std@@QEAAAEAUPIXEventsThreadInfo@@XZ; std::list<PIXEventsThreadInfo>::emplace_back<>(void)
0x18000282e  mov     rax, cs:qword_18001E8A0
0x180002835  mov     rcx, [rax+8]
0x180002839  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180002840  add     rcx, 10h
0x180002844  mov     [rbx+rsi], rcx
0x180002848  test    rax, rax
0x18000284b  jz      short loc_18000285C
0x18000284d  mov     eax, [rax+8]
0x180002850  cmp     eax, 1
0x180002853  jz      short loc_18000285C
0x180002855  mov     eax, 1
0x18000285a  jmp     short loc_18000285E
0x18000285c  xor     eax, eax
0x18000285e  mov     rdx, [rbx+rsi]
0x180002862  lea     rcx, SRWLock; SRWLock
0x180002869  mov     qword ptr [rdx], 0
0x180002870  mov     [rdx+8], rax
0x180002874  mov     qword ptr [rdx+10h], 0FFFFFFFFFFFFFFFFh
0x18000287c  call    cs:__imp_ReleaseSRWLockExclusive
0x180002882  mov     rcx, gs:58h
0x18000288b  mov     rbx, [rsp+28h+arg_0]
0x180002890  mov     rax, [rcx+rdi*8]
0x180002894  mov     rdi, [rsp+28h+var_8]
0x180002899  mov     rax, [rsi+rax]
0x18000289d  mov     rsi, [rsp+28h+arg_8]
0x1800028a2  jmp     loc_1800027E4
```
