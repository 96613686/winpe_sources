# CKsOutputPin2::DA_PluginInputCompletionItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x18002e600`
- end: `0x18002e746`
- name: `?DA_PluginInputCompletionItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z`
- size: `326`
- prototype: `void __fastcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003d60`
- `0x18000df50`
- `0x18000ef30`
- `0x18001f1c4`
- `0x18002e600`
- `0x180031d5c`
- `0x180031e14`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002e6f6`
- `KERNEL32!CloseHandle` at `0x18002e6f6`
- `KERNEL32!LeaveCriticalSection` at `0x18002e6e1`
- `KERNEL32!LeaveCriticalSection` at `0x18002e6e1`
- `KERNEL32!EnterCriticalSection` at `0x18002e6a1`
- `KERNEL32!EnterCriticalSection` at `0x18002e6a1`

## string_xrefs

- `0x18002e636`: `CKsOutputPin2::DA_PluginInputCompletionItem`

## pseudocode

```c
void __fastcall CKsOutputPin2::DA_PluginInputCompletionItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *a2)
{
  void **context; // rbx
  __int64 v5; // rbp
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  CBaseList::CNode *v7; // rdx
  CBaseList *v8; // rcx
  struct _ASYNC_ITEM *v9; // rbp
  void *event; // rcx

  context = (void **)a2->context;
  v5 = *((_QWORD *)*context + 10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::DA_PluginInputCompletionItem");
  (*(void (__fastcall **)(__int64))(*((_QWORD *)*context + 48) + 112LL))((__int64)*context + 384);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      ProcessOutput_Complete,
      *(_QWORD *)(*((_QWORD *)context[2] + 69) + 40LL),
      *(_QWORD *)(*((_QWORD *)context[2] + 69) + 8LL));
  if ( a1 == EVENT_SIGNALLED )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)(v5 + 408);
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 408));
    v9 = (struct _ASYNC_ITEM *)CBaseList::GetI(
                                 (CBaseList *)((char *)*context + 1072),
                                 *((struct __POSITION **)*context + 134));
    if ( v9 )
    {
      CBaseList::RemoveI(v8, v7);
      CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)*context + 140), v9);
    }
    LeaveCriticalSection(v6);
  }
  event = a2->event;
  if ( event )
    CloseHandle(event);
  operator delete(*(void **)(*((_QWORD *)context[2] + 69) + 40LL));
  operator delete(context[2]);
  operator delete(context);
  operator delete(a2);
}

```

## disassembly

```asm
0x18002e600  push    rbx
0x18002e602  push    rbp
0x18002e603  push    rsi
0x18002e604  push    rdi
0x18002e605  sub     rsp, 28h
0x18002e609  mov     rbx, [rdx+28h]
0x18002e60d  mov     rdi, rdx
0x18002e610  mov     esi, ecx
0x18002e612  mov     rax, [rbx]
0x18002e615  mov     rbp, [rax+50h]
0x18002e619  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e620  lea     rax, WPP_GLOBAL_Control
0x18002e627  cmp     rcx, rax
0x18002e62a  jz      short loc_18002E64E
0x18002e62c  cmp     byte ptr [rcx+19h], 2
0x18002e630  jb      short loc_18002E64E
0x18002e632  mov     rcx, [rcx+10h]
0x18002e636  lea     r9, aCksoutputpin2D_4; "CKsOutputPin2::DA_PluginInputCompletion"...
0x18002e63d  mov     edx, 22h ; '"'
0x18002e642  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x18002e649  call    WPP_SF_s
0x18002e64e  mov     rcx, [rbx]
0x18002e651  add     rcx, 180h
0x18002e658  mov     rax, [rcx]
0x18002e65b  mov     rax, [rax+70h]
0x18002e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e664  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x18002e66b  jz      short loc_18002E693
0x18002e66d  mov     rax, [rbx+10h]
0x18002e671  lea     rdx, ProcessOutput_Complete
0x18002e678  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x18002e67f  mov     r8, [rax+228h]
0x18002e686  mov     r9, [r8+8]
0x18002e68a  mov     r8, [r8+28h]
0x18002e68e  call    McTemplateU0pi_EventWriteTransfer
0x18002e693  test    esi, esi
0x18002e695  jnz     short loc_18002E6ED
0x18002e697  lea     rsi, [rbp+198h]
0x18002e69e  mov     rcx, rsi; lpCriticalSection
0x18002e6a1  call    cs:__imp_EnterCriticalSection
0x18002e6a8  nop     dword ptr [rax+rax+00h]
0x18002e6ad  mov     rcx, [rbx]
0x18002e6b0  add     rcx, 430h; this
0x18002e6b7  mov     rdx, [rcx]; struct __POSITION *
0x18002e6ba  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x18002e6bf  mov     rbp, rax
0x18002e6c2  test    rax, rax
0x18002e6c5  jz      short loc_18002E6DE
0x18002e6c7  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18002e6cc  mov     rcx, [rbx]
0x18002e6cf  mov     rdx, rbp; struct _ASYNC_ITEM *
0x18002e6d2  mov     rcx, [rcx+460h]; this
0x18002e6d9  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002e6de  mov     rcx, rsi; lpCriticalSection
0x18002e6e1  call    cs:__imp_LeaveCriticalSection
0x18002e6e8  nop     dword ptr [rax+rax+00h]
0x18002e6ed  mov     rcx, [rdi+18h]; hObject
0x18002e6f1  test    rcx, rcx
0x18002e6f4  jz      short loc_18002E702
0x18002e6f6  call    cs:__imp_CloseHandle
0x18002e6fd  nop     dword ptr [rax+rax+00h]
0x18002e702  mov     rax, [rbx+10h]
0x18002e706  mov     rcx, [rax+228h]
0x18002e70d  mov     rcx, [rcx+28h]; void *
0x18002e711  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e716  mov     rcx, [rbx+10h]; void *
0x18002e71a  mov     edx, 258h; unsigned __int64
0x18002e71f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e724  mov     edx, 28h ; '('; unsigned __int64
0x18002e729  mov     rcx, rbx; void *
0x18002e72c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002e731  mov     edx, 30h ; '0'; unsigned __int64
0x18002e736  mov     rcx, rdi; void *
0x18002e739  add     rsp, 28h
0x18002e73d  pop     rdi
0x18002e73e  pop     rsi
0x18002e73f  pop     rbp
0x18002e740  pop     rbx
0x18002e741  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
