# EtRemoveAllFilters

- ea: `0x180007698`
- end: `0x1800077d2`
- name: `EtRemoveAllFilters`
- size: `314`
- prototype: `__int64 __fastcall(HANDLE engineHandle)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006ba0`
- `0x1800363b4`
- `0x18005f440`

## callees

- `0x180004c54`
- `0x180007698`
- `0x180009000`
- `0x1800190e0`

## import_xrefs

- `fwpuclnt!FwpmTransactionAbort0` at `0x18000778c`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18000778c`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180007763`
- `fwpuclnt!FwpmTransactionCommit0` at `0x180007763`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x180007723`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x180007723`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800076ed`
- `fwpuclnt!FwpmTransactionBegin0` at `0x1800076ed`

## string_xrefs

- `0x180007737`: `Unable to delete filter with id %I64d`
- `0x180007778`: `Unable to commit the transaction, Error(%u)`

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
0x180007698  push    rbx
0x18000769a  push    rbp
0x18000769b  push    rsi
0x18000769c  push    rdi
0x18000769d  push    r14
0x18000769f  sub     rsp, 20h
0x1800076a3  xor     sil, sil
0x1800076a6  mov     rdi, rdx
0x1800076a9  cmp     cs:IpHlpSvcEtwEnabled, sil
0x1800076b0  mov     rbp, rcx
0x1800076b3  mov     r14d, 1
0x1800076b9  jz      short loc_1800076DE
0x1800076bb  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, r14b
0x1800076c2  jz      short loc_1800076DE
0x1800076c4  lea     r8, aEtRemovingAllF; "ET: Removing all filters"
0x1800076cb  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_STARTED
0x1800076d2  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800076d9  call    McTemplateU0z_EventWriteTransfer
0x1800076de  cmp     [rdi], rdi
0x1800076e1  jz      short loc_180007759
0x1800076e3  test    sil, sil
0x1800076e6  jnz     short loc_180007703
0x1800076e8  xor     edx, edx; flags
0x1800076ea  mov     rcx, rbp; engineHandle
0x1800076ed  call    cs:__imp_FwpmTransactionBegin0
0x1800076f4  nop     dword ptr [rax+rax+00h]
0x1800076f9  test    eax, eax
0x1800076fb  movzx   esi, sil
0x1800076ff  cmovz   esi, r14d
0x180007703  mov     rbx, [rdi]
0x180007706  cmp     [rbx+8], rdi
0x18000770a  jnz     short loc_180007752
0x18000770c  mov     rax, [rbx]
0x18000770f  cmp     [rax+8], rbx
0x180007713  jnz     short loc_180007752
0x180007715  mov     [rdi], rax
0x180007718  mov     rcx, rbp; engineHandle
0x18000771b  mov     [rax+8], rdi
0x18000771f  mov     rdx, [rbx+10h]; id
0x180007723  call    cs:__imp_FwpmFilterDeleteById0
0x18000772a  nop     dword ptr [rax+rax+00h]
0x18000772f  test    eax, eax
0x180007731  jz      short loc_180007748
0x180007733  mov     r8, [rbx+10h]
0x180007737  lea     rdx, aUnableToDelete_2; "Unable to delete filter with id %I64d"
0x18000773e  mov     ecx, 100000h
0x180007743  call    EventWriteError0
0x180007748  mov     rcx, rbx
0x18000774b  call    FREE
0x180007750  jmp     short loc_1800076DE
0x180007752  mov     ecx, 3
0x180007757  int     29h; Win8: RtlFailFast(ecx)
0x180007759  xor     ebx, ebx
0x18000775b  cmp     sil, r14b
0x18000775e  jnz     short loc_180007798
0x180007760  mov     rcx, rbp; engineHandle
0x180007763  call    cs:__imp_FwpmTransactionCommit0
0x18000776a  nop     dword ptr [rax+rax+00h]
0x18000776f  mov     ebx, eax
0x180007771  test    eax, eax
0x180007773  jz      short loc_180007798
0x180007775  mov     r8d, eax
0x180007778  lea     rdx, aUnableToCommit; "Unable to commit the transaction, Error"...
0x18000777f  mov     ecx, 100000h
0x180007784  call    EventWriteError0
0x180007789  mov     rcx, rbp; engineHandle
0x18000778c  call    cs:__imp_FwpmTransactionAbort0
0x180007793  nop     dword ptr [rax+rax+00h]
0x180007798  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18000779f  jz      short loc_1800077C4
0x1800077a1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 2
0x1800077a8  jz      short loc_1800077C4
0x1800077aa  lea     r8, aEtFinishedRemo; "ET: Finished removing all filters"
0x1800077b1  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CURRENT_OPERATION_ENDED
0x1800077b8  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800077bf  call    McTemplateU0z_EventWriteTransfer
0x1800077c4  mov     eax, ebx
0x1800077c6  add     rsp, 20h
0x1800077ca  pop     r14
0x1800077cc  pop     rdi
0x1800077cd  pop     rsi
0x1800077ce  pop     rbp
0x1800077cf  pop     rbx
0x1800077d0  retn
```
