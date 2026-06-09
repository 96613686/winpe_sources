# CKsOutputPin2::PluginOutputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x1800306f0`
- end: `0x180030889`
- name: `?PluginOutputItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z`
- size: `409`
- prototype: `void __fastcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003d60`
- `0x18000df50`
- `0x18000ef30`
- `0x18001f1c4`
- `0x1800306f0`
- `0x18003113c`
- `0x180031d5c`
- `0x180031e14`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800307d6`
- `KERNEL32!GetLastError` at `0x1800307d6`
- `KERNEL32!LeaveCriticalSection` at `0x18003082b`
- `KERNEL32!LeaveCriticalSection` at `0x18003085b`
- `KERNEL32!LeaveCriticalSection` at `0x18003082b`
- `KERNEL32!LeaveCriticalSection` at `0x18003085b`
- `KERNEL32!EnterCriticalSection` at `0x180030787`
- `KERNEL32!EnterCriticalSection` at `0x18003084c`
- `KERNEL32!EnterCriticalSection` at `0x180030787`
- `KERNEL32!EnterCriticalSection` at `0x18003084c`
- `KERNEL32!GetOverlappedResult` at `0x1800307c6`
- `KERNEL32!GetOverlappedResult` at `0x1800307c6`

## string_xrefs

- `0x18003072e`: `CKsOutputPin2::PluginOutputItem`

## pseudocode

```c
void __fastcall CKsOutputPin2::PluginOutputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *a2)
{
  CKsOutputPin2 **context; // rbx
  __int64 v5; // rbp
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 v7; // rcx
  CBaseList::CNode *v8; // rdx
  CBaseList *v9; // rcx
  struct _ASYNC_ITEM *v10; // rbp
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF

  context = (CKsOutputPin2 **)a2->context;
  v5 = *((_QWORD *)*context + 10);
  NumberOfBytesTransferred = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::PluginOutputItem");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      DeviceIo_Complete,
      *(_QWORD *)(*((_QWORD *)context[1] + 69) + 40LL),
      *(_QWORD *)(*((_QWORD *)context[1] + 69) + 8LL));
  if ( a1 == EVENT_SIGNALLED )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)(v5 + 408);
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 408));
    (*(void (__fastcall **)(__int64))(*((_QWORD *)*context + 48) + 112LL))((__int64)*context + 384);
    if ( GetOverlappedResult(
           *((HANDLE *)*context + 65),
           (LPOVERLAPPED)((char *)context[1] + 560),
           &NumberOfBytesTransferred,
           0) )
    {
      CKsOutputPin2::QueueBuffersToPluginOutput(*context, context[1]);
      v10 = (struct _ASYNC_ITEM *)CBaseList::GetI(
                                    (CBaseList *)((char *)*context + 1072),
                                    *((struct __POSITION **)*context + 134));
      if ( v10 )
      {
        CBaseList::RemoveI(v9, v8);
        LeaveCriticalSection(v6);
        CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)*context + 140), v10);
        EnterCriticalSection(v6);
      }
    }
    else
    {
      GetLastError();
      v7 = *((_QWORD *)context[1] + 4);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    LeaveCriticalSection(v6);
  }
  operator delete(a2->context);
  operator delete(a2);
}

```

## disassembly

```asm
0x1800306f0  push    rbx
0x1800306f2  push    rbp
0x1800306f3  push    rsi
0x1800306f4  push    rdi
0x1800306f5  sub     rsp, 28h
0x1800306f9  mov     rbx, [rdx+28h]
0x1800306fd  mov     rdi, rdx
0x180030700  mov     esi, ecx
0x180030702  mov     rax, [rbx]
0x180030705  mov     rbp, [rax+50h]
0x180030709  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x180030711  mov     rcx, cs:WPP_GLOBAL_Control
0x180030718  lea     rax, WPP_GLOBAL_Control
0x18003071f  cmp     rcx, rax
0x180030722  jz      short loc_180030746
0x180030724  cmp     byte ptr [rcx+19h], 2
0x180030728  jb      short loc_180030746
0x18003072a  mov     rcx, [rcx+10h]
0x18003072e  lea     r9, aCksoutputpin2P; "CKsOutputPin2::PluginOutputItem"
0x180030735  mov     edx, 28h ; '('
0x18003073a  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x180030741  call    WPP_SF_s
0x180030746  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x18003074d  jz      short loc_180030775
0x18003074f  mov     rax, [rbx+8]
0x180030753  lea     rdx, DeviceIo_Complete
0x18003075a  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x180030761  mov     r8, [rax+228h]
0x180030768  mov     r9, [r8+8]
0x18003076c  mov     r8, [r8+28h]
0x180030770  call    McTemplateU0pi_EventWriteTransfer
0x180030775  test    esi, esi
0x180030777  jnz     loc_180030867
0x18003077d  lea     rsi, [rbp+198h]
0x180030784  mov     rcx, rsi; lpCriticalSection
0x180030787  call    cs:__imp_EnterCriticalSection
0x18003078e  nop     dword ptr [rax+rax+00h]
0x180030793  mov     rcx, [rbx]
0x180030796  add     rcx, 180h
0x18003079d  mov     rax, [rcx]
0x1800307a0  mov     rax, [rax+70h]
0x1800307a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307a9  mov     rcx, [rbx]
0x1800307ac  lea     r8, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800307b1  mov     rdx, [rbx+8]
0x1800307b5  xor     r9d, r9d; bWait
0x1800307b8  add     rdx, 230h; lpOverlapped
0x1800307bf  mov     rcx, [rcx+208h]; hFile
0x1800307c6  call    cs:__imp_GetOverlappedResult
0x1800307cd  nop     dword ptr [rax+rax+00h]
0x1800307d2  test    eax, eax
0x1800307d4  jnz     short loc_1800307FD
0x1800307d6  call    cs:__imp_GetLastError
0x1800307dd  nop     dword ptr [rax+rax+00h]
0x1800307e2  mov     rax, [rbx+8]
0x1800307e6  mov     rcx, [rax+20h]
0x1800307ea  test    rcx, rcx
0x1800307ed  jz      short loc_180030858
0x1800307ef  mov     rax, [rcx]
0x1800307f2  mov     rax, [rax+10h]
0x1800307f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307fb  jmp     short loc_180030858
0x1800307fd  mov     rdx, [rbx+8]; struct _KSSTREAM_SEGMENT_EX2 *
0x180030801  mov     rcx, [rbx]; this
0x180030804  call    ?QueueBuffersToPluginOutput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@@Z; CKsOutputPin2::QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)
0x180030809  mov     rcx, [rbx]
0x18003080c  add     rcx, 430h; this
0x180030813  mov     rdx, [rcx]; struct __POSITION *
0x180030816  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x18003081b  mov     rbp, rax
0x18003081e  test    rax, rax
0x180030821  jz      short loc_180030858
0x180030823  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x180030828  mov     rcx, rsi; lpCriticalSection
0x18003082b  call    cs:__imp_LeaveCriticalSection
0x180030832  nop     dword ptr [rax+rax+00h]
0x180030837  mov     rcx, [rbx]
0x18003083a  mov     rdx, rbp; struct _ASYNC_ITEM *
0x18003083d  mov     rcx, [rcx+460h]; this
0x180030844  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x180030849  mov     rcx, rsi; lpCriticalSection
0x18003084c  call    cs:__imp_EnterCriticalSection
0x180030853  nop     dword ptr [rax+rax+00h]
0x180030858  mov     rcx, rsi; lpCriticalSection
0x18003085b  call    cs:__imp_LeaveCriticalSection
0x180030862  nop     dword ptr [rax+rax+00h]
0x180030867  mov     rcx, [rdi+28h]; void *
0x18003086b  xor     edx, edx; unsigned __int64
0x18003086d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030872  mov     edx, 30h ; '0'; unsigned __int64
0x180030877  mov     rcx, rdi; void *
0x18003087a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003087f  add     rsp, 28h
0x180030883  pop     rdi
0x180030884  pop     rsi
0x180030885  pop     rbp
0x180030886  pop     rbx
0x180030887  retn
```
