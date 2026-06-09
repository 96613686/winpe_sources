# DnsQueueWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180020340`
- end: `0x180020435`
- name: `?DnsQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `245`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ca20`
- `0x180011428`
- `0x180020340`
- `0x18002043c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800203c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800203c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180020373`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180020373`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180020359`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180020359`

## pseudocode

```c
void __fastcall DnsQueueWorkCallback(PTP_CALLBACK_INSTANCE Instance, struct _NH_BUFFER *Context, PTP_WORK Work)
{
  __int64 v3; // rsi
  HANDLE ProcessHeap; // rax

  v3 = *((_QWORD *)Context + 4);
  CallbackMayRunLong(Instance);
  DnsProcessQueryMessage((struct _DNS_INTERFACE *)v3, Context);
  CloseThreadpoolWork(Work);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 56), 0xFFFFFFFF) == 1 )
    DnsCleanupInterface((struct _DNS_INTERFACE *)v3);
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
0x180020340  mov     [rsp+arg_0], rbx
0x180020345  mov     [rsp+arg_8], rsi
0x18002034a  push    rdi
0x18002034b  sub     rsp, 20h
0x18002034f  mov     rsi, [rdx+20h]
0x180020353  mov     rbx, r8
0x180020356  mov     rdi, rdx
0x180020359  call    cs:__imp_CallbackMayRunLong
0x180020360  nop     dword ptr [rax+rax+00h]
0x180020365  mov     rdx, rdi; struct _NH_BUFFER *
0x180020368  mov     rcx, rsi; struct _DNS_INTERFACE *
0x18002036b  call    ?DnsProcessQueryMessage@@YAXPEAU_DNS_INTERFACE@@PEAU_NH_BUFFER@@@Z; DnsProcessQueryMessage(_DNS_INTERFACE *,_NH_BUFFER *)
0x180020370  mov     rcx, rbx; pwk
0x180020373  call    cs:__imp_CloseThreadpoolWork
0x18002037a  nop     dword ptr [rax+rax+00h]
0x18002037f  mov     eax, 0FFFFFFFFh
0x180020384  lock xadd [rsi+38h], eax
0x180020389  cmp     eax, 1
0x18002038c  jz      short loc_1800203FD
0x18002038e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020395  lea     rbx, WPP_GLOBAL_Control
0x18002039c  cmp     rcx, rbx
0x18002039f  jz      short loc_1800203AD
0x1800203a1  test    byte ptr [rcx+1Ch], 8
0x1800203a5  jz      short loc_1800203AD
0x1800203a7  cmp     byte ptr [rcx+19h], 6
0x1800203ab  jnb     short loc_180020407
0x1800203ad  call    cs:__imp_GetProcessHeap
0x1800203b4  nop     dword ptr [rax+rax+00h]
0x1800203b9  mov     r8, rdi; lpMem
0x1800203bc  xor     edx, edx; dwFlags
0x1800203be  mov     rcx, rax; hHeap
0x1800203c1  call    cs:__imp_HeapFree
0x1800203c8  nop     dword ptr [rax+rax+00h]
0x1800203cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203d4  cmp     rcx, rbx
0x1800203d7  jz      short loc_1800203E5
0x1800203d9  test    byte ptr [rcx+1Ch], 8
0x1800203dd  jz      short loc_1800203E5
0x1800203df  cmp     byte ptr [rcx+19h], 6
0x1800203e3  jnb     short loc_18002041E
0x1800203e5  lock dec cs:?gDnsQueueWorkCount@@3JA; long gDnsQueueWorkCount
0x1800203ec  mov     rbx, [rsp+28h+arg_0]
0x1800203f1  mov     rsi, [rsp+28h+arg_8]
0x1800203f6  add     rsp, 20h
0x1800203fa  pop     rdi
0x1800203fb  retn
0x1800203fd  mov     rcx, rsi; lpMem
0x180020400  call    ?DnsCleanupInterface@@YAXPEAU_DNS_INTERFACE@@@Z; DnsCleanupInterface(_DNS_INTERFACE *)
0x180020405  jmp     short loc_18002038E
0x180020407  mov     rcx, [rcx+10h]
0x18002040b  lea     r8, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids
0x180020412  mov     edx, 13h
0x180020417  call    WPP_SF_
0x18002041c  jmp     short loc_1800203AD
0x18002041e  mov     rcx, [rcx+10h]
0x180020422  lea     r8, WPP_7f7df6538f7639ba213fa1806859d78b_Traceguids
0x180020429  mov     edx, 14h
0x18002042e  call    WPP_SF_
0x180020433  jmp     short loc_1800203E5
```
