# EtRemoveAllFilters

- ea: `0x1800076a8`
- end: `0x1800077e2`
- name: `EtRemoveAllFilters`
- size: `314`
- prototype: `__int64 __fastcall(HANDLE engineHandle)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006bb0`
- `0x1800363c4`
- `0x18005f460`

## callees

- `0x180004c64`
- `0x1800076a8`
- `0x180009010`
- `0x1800190f0`

## import_xrefs

- `fwpuclnt!FwpmTransactionAbort0` at `0x18000779c`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18000779c`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180007773`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180007773`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x180007733`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x180007733`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800076fd`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800076fd`

## string_xrefs

- `0x180007747`: `Unable to delete filter with id %I64d`
- `0x180007788`: `Unable to commit the transaction, Error(%u)`

## pseudocode

```c
__int64 __fastcall EtRemoveAllFilters(HANDLE engineHandle, UINT64 **a2)
{
  bool v2; // si
  UINT64 *v5; // rbx
  UINT64 v6; // rax
  DWORD v7; // ebx
  DWORD v8; // eax

  v2 = 0;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x100) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED,
      L"ET: Removing all filters");
  while ( *a2 != (UINT64 *)a2 )
  {
    if ( !v2 )
      v2 = FwpmTransactionBegin0(engineHandle, 0) == 0;
    v5 = *a2;
    if ( (UINT64 **)(*a2)[1] != a2 || (v6 = *v5, *(UINT64 **)(*v5 + 8) != v5) )
      __fastfail(3u);
    *a2 = (UINT64 *)v6;
    *(_QWORD *)(v6 + 8) = a2;
    if ( FwpmFilterDeleteById0(engineHandle, v5[2]) )
      EventWriteError0(0x100000, L"Unable to delete filter with id %I64d", v5[2]);
    FREE(v5);
  }
  v7 = 0;
  if ( v2 )
  {
    v8 = FwpmTransactionCommit0(engineHandle);
    v7 = v8;
    if ( v8 )
    {
      EventWriteError0(0x100000, L"Unable to commit the transaction, Error(%u)", v8);
      FwpmTransactionAbort0(engineHandle);
    }
  }
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x200) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED,
      L"ET: Finished removing all filters");
  return v7;
}

```

## disassembly

```asm
0x1800076a8  push    rbx
0x1800076aa  push    rbp
0x1800076ab  push    rsi
0x1800076ac  push    rdi
0x1800076ad  push    r14
0x1800076af  sub     rsp, 20h
0x1800076b3  xor     sil, sil
0x1800076b6  mov     rdi, rdx
0x1800076b9  cmp     cs:IpHlpSvcEtwEnabled, sil
0x1800076c0  mov     rbp, rcx
0x1800076c3  mov     r14d, 1
0x1800076c9  jz      short loc_1800076EE
0x1800076cb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, r14b
0x1800076d2  jz      short loc_1800076EE
0x1800076d4  lea     r8, aEtRemovingAllF; "ET: Removing all filters"
0x1800076db  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x1800076e2  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800076e9  call    McTemplateU0z_EventWriteTransfer
0x1800076ee  cmp     [rdi], rdi
0x1800076f1  jz      short loc_180007769
0x1800076f3  test    sil, sil
0x1800076f6  jnz     short loc_180007713
0x1800076f8  xor     edx, edx; flags
0x1800076fa  mov     rcx, rbp; engineHandle
0x1800076fd  call    cs:__imp_FwpmTransactionBegin0
0x180007704  nop     dword ptr [rax+rax+00h]
0x180007709  test    eax, eax
0x18000770b  movzx   esi, sil
0x18000770f  cmovz   esi, r14d
0x180007713  mov     rbx, [rdi]
0x180007716  cmp     [rbx+8], rdi
0x18000771a  jnz     short loc_180007762
0x18000771c  mov     rax, [rbx]
0x18000771f  cmp     [rax+8], rbx
0x180007723  jnz     short loc_180007762
0x180007725  mov     [rdi], rax
0x180007728  mov     rcx, rbp; engineHandle
0x18000772b  mov     [rax+8], rdi
0x18000772f  mov     rdx, [rbx+10h]; id
0x180007733  call    cs:__imp_FwpmFilterDeleteById0
0x18000773a  nop     dword ptr [rax+rax+00h]
0x18000773f  test    eax, eax
0x180007741  jz      short loc_180007758
0x180007743  mov     r8, [rbx+10h]
0x180007747  lea     rdx, aUnableToDelete_2; "Unable to delete filter with id %I64d"
0x18000774e  mov     ecx, 100000h
0x180007753  call    EventWriteError0
0x180007758  mov     rcx, rbx
0x18000775b  call    FREE
0x180007760  jmp     short loc_1800076EE
0x180007762  mov     ecx, 3
0x180007767  int     29h; Win8: RtlFailFast(ecx)
0x180007769  xor     ebx, ebx
0x18000776b  cmp     sil, r14b
0x18000776e  jnz     short loc_1800077A8
0x180007770  mov     rcx, rbp; engineHandle
0x180007773  call    cs:__imp_FwpmTransactionCommit0
0x18000777a  nop     dword ptr [rax+rax+00h]
0x18000777f  mov     ebx, eax
0x180007781  test    eax, eax
0x180007783  jz      short loc_1800077A8
0x180007785  mov     r8d, eax
0x180007788  lea     rdx, aUnableToCommit; "Unable to commit the transaction, Error"...
0x18000778f  mov     ecx, 100000h
0x180007794  call    EventWriteError0
0x180007799  mov     rcx, rbp; engineHandle
0x18000779c  call    cs:__imp_FwpmTransactionAbort0
0x1800077a3  nop     dword ptr [rax+rax+00h]
0x1800077a8  cmp     cs:IpHlpSvcEtwEnabled, 0
0x1800077af  jz      short loc_1800077D4
0x1800077b1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x1800077b8  jz      short loc_1800077D4
0x1800077ba  lea     r8, aEtFinishedRemo; "ET: Finished removing all filters"
0x1800077c1  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x1800077c8  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800077cf  call    McTemplateU0z_EventWriteTransfer
0x1800077d4  mov     eax, ebx
0x1800077d6  add     rsp, 20h
0x1800077da  pop     r14
0x1800077dc  pop     rdi
0x1800077dd  pop     rsi
0x1800077de  pop     rbp
0x1800077df  pop     rbx
0x1800077e0  retn
```
