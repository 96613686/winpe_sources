# DnsQueueWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180028840`
- end: `0x18002891c`
- name: `?DnsQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `220`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c110`
- `0x180010744`
- `0x180028840`
- `0x180028924`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800288a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800288a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800288af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800288af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002886d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002886d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180028859`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180028859`

## pseudocode

```c
void __fastcall DnsQueueWorkCallback(PTP_CALLBACK_INSTANCE Instance, DNS_RECORDA *Context, PTP_WORK Work)
{
  PSTR pNamePrimaryServer; // rsi
  __int64 v6; // r8
  HANDLE ProcessHeap; // rax

  pNamePrimaryServer = Context->Data.SOA.pNamePrimaryServer;
  CallbackMayRunLong(Instance);
  DnsProcessQueryMessage((struct _DNS_INTERFACE *)pNamePrimaryServer, Context, v6);
  CloseThreadpoolWork(Work);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)pNamePrimaryServer + 14, 0xFFFFFFFF) == 1 )
    DnsCleanupInterface((struct _DNS_INTERFACE *)pNamePrimaryServer);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids);
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, Context);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids);
  }
  _InterlockedDecrement(&gDnsQueueWorkCount);
}

```

## disassembly

```asm
0x180028840  mov     [rsp+arg_0], rbx
0x180028845  mov     [rsp+arg_8], rsi
0x18002884a  push    rdi
0x18002884b  sub     rsp, 20h
0x18002884f  mov     rsi, [rdx+20h]
0x180028853  mov     rbx, r8
0x180028856  mov     rdi, rdx
0x180028859  call    cs:__imp_CallbackMayRunLong
0x18002885f  mov     rdx, rdi; struct _NH_BUFFER *
0x180028862  mov     rcx, rsi; struct _DNS_INTERFACE *
0x180028865  call    ?DnsProcessQueryMessage@@YAXPEAU_DNS_INTERFACE@@PEAU_NH_BUFFER@@@Z; DnsProcessQueryMessage(_DNS_INTERFACE *,_NH_BUFFER *)
0x18002886a  mov     rcx, rbx; pwk
0x18002886d  call    cs:__imp_CloseThreadpoolWork
0x180028873  mov     eax, 0FFFFFFFFh
0x180028878  lock xadd [rsi+38h], eax
0x18002887d  cmp     eax, 1
0x180028880  jz      short loc_1800288E4
0x180028882  mov     rcx, cs:WPP_GLOBAL_Control
0x180028889  lea     rbx, WPP_GLOBAL_Control
0x180028890  cmp     rcx, rbx
0x180028893  jz      short loc_1800288A1
0x180028895  test    byte ptr [rcx+1Ch], 8
0x180028899  jz      short loc_1800288A1
0x18002889b  cmp     byte ptr [rcx+19h], 6
0x18002889f  jnb     short loc_1800288EE
0x1800288a1  call    cs:__imp_GetProcessHeap
0x1800288a7  mov     r8, rdi; lpMem
0x1800288aa  xor     edx, edx; dwFlags
0x1800288ac  mov     rcx, rax; hHeap
0x1800288af  call    cs:__imp_HeapFree
0x1800288b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288bc  cmp     rcx, rbx
0x1800288bf  jz      short loc_1800288CD
0x1800288c1  test    byte ptr [rcx+1Ch], 8
0x1800288c5  jz      short loc_1800288CD
0x1800288c7  cmp     byte ptr [rcx+19h], 6
0x1800288cb  jnb     short loc_180028905
0x1800288cd  lock dec cs:?gDnsQueueWorkCount@@3JA; long gDnsQueueWorkCount
0x1800288d4  mov     rbx, [rsp+28h+arg_0]
0x1800288d9  mov     rsi, [rsp+28h+arg_8]
0x1800288de  add     rsp, 20h
0x1800288e2  pop     rdi
0x1800288e3  retn
0x1800288e4  mov     rcx, rsi; lpMem
0x1800288e7  call    ?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsCleanupInterface(_DNS_INTERFACE *)
0x1800288ec  jmp     short loc_180028882
0x1800288ee  mov     rcx, [rcx+10h]
0x1800288f2  lea     r8, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids
0x1800288f9  mov     edx, 13h
0x1800288fe  call    WPP_SF_
0x180028903  jmp     short loc_1800288A1
0x180028905  mov     rcx, [rcx+10h]
0x180028909  lea     r8, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids
0x180028910  mov     edx, 14h
0x180028915  call    WPP_SF_
0x18002891a  jmp     short loc_1800288CD
```
