# CKsOutputPin2::DA_PluginOutputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x18002e8d0`
- end: `0x18002e9d6`
- name: `?DA_PluginOutputItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z`
- size: `262`
- prototype: `void __fastcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x18000ef30`
- `0x18001f1c4`
- `0x18002e8d0`
- `0x18002eb68`
- `0x180031e14`
- `0x18003a1c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002e9b5`
- `KERNEL32!CloseHandle` at `0x18002e9b5`
- `KERNEL32!LeaveCriticalSection` at `0x18002e9a0`
- `KERNEL32!LeaveCriticalSection` at `0x18002e9a0`
- `KERNEL32!EnterCriticalSection` at `0x18002e930`
- `KERNEL32!EnterCriticalSection` at `0x18002e930`

## string_xrefs

- `0x18002e906`: `CKsOutputPin2::DA_PluginOutputItem`

## pseudocode

```c
void __fastcall CKsOutputPin2::DA_PluginOutputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *a2)
{
  struct _KSSTREAM_SEGMENT_EX2 **context; // rdi
  __int64 v5; // rbp
  struct _KSSTREAM_SEGMENT_EX2 *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  void *event; // rcx

  context = (struct _KSSTREAM_SEGMENT_EX2 **)a2->context;
  v5 = *((_QWORD *)*context + 10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::DA_PluginOutputItem");
  if ( a1 == EVENT_SIGNALLED )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 408));
    v6 = *context;
    if ( *(_DWORD *)(*((_QWORD *)*context + 10) + 40LL)
      && !*((_DWORD *)v6 + 214)
      && !*((_DWORD *)v6 + 215)
      && !*((_DWORD *)v6 + 235)
      && *((_QWORD *)v6 + 27) )
    {
      CKsOutputPin2::DA_QueueBuffersToPluginOutput(v6, context[1]);
    }
    if ( CBaseList::GetI((CBaseList *)*context, *((struct __POSITION **)*context + 90)) )
      CAsyncItemHandler::QueueAsyncItemList(*(_QWORD *)(v7 + 984), v8);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 408));
  }
  event = a2->event;
  if ( event )
    CloseHandle(event);
  operator delete(a2);
}

```

## disassembly

```asm
0x18002e8d0  push    rbx
0x18002e8d2  push    rbp
0x18002e8d3  push    rsi
0x18002e8d4  push    rdi
0x18002e8d5  sub     rsp, 28h
0x18002e8d9  mov     rdi, [rdx+28h]
0x18002e8dd  mov     rbx, rdx
0x18002e8e0  mov     esi, ecx
0x18002e8e2  mov     rax, [rdi]
0x18002e8e5  mov     rbp, [rax+50h]
0x18002e8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8f0  lea     rax, WPP_GLOBAL_Control
0x18002e8f7  cmp     rcx, rax
0x18002e8fa  jz      short loc_18002E91E
0x18002e8fc  cmp     byte ptr [rcx+19h], 2
0x18002e900  jb      short loc_18002E91E
0x18002e902  mov     rcx, [rcx+10h]
0x18002e906  lea     r9, aCksoutputpin2D_0; "CKsOutputPin2::DA_PluginOutputItem"
0x18002e90d  mov     edx, 21h ; '!'
0x18002e912  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x18002e919  call    WPP_SF_s
0x18002e91e  test    esi, esi
0x18002e920  jnz     loc_18002E9AC
0x18002e926  lea     rsi, [rbp+198h]
0x18002e92d  mov     rcx, rsi; lpCriticalSection
0x18002e930  call    cs:__imp_EnterCriticalSection
0x18002e937  nop     dword ptr [rax+rax+00h]
0x18002e93c  mov     rcx, [rdi]; this
0x18002e93f  mov     rax, [rcx+50h]
0x18002e943  cmp     dword ptr [rax+28h], 0
0x18002e947  jz      short loc_18002E977
0x18002e949  cmp     dword ptr [rcx+358h], 0
0x18002e950  jnz     short loc_18002E977
0x18002e952  cmp     dword ptr [rcx+35Ch], 0
0x18002e959  jnz     short loc_18002E977
0x18002e95b  cmp     dword ptr [rcx+3ACh], 0
0x18002e962  jnz     short loc_18002E977
0x18002e964  cmp     qword ptr [rcx+0D8h], 0
0x18002e96c  jz      short loc_18002E977
0x18002e96e  mov     rdx, [rdi+8]; struct _KSSTREAM_SEGMENT_EX2 *
0x18002e972  call    ?DA_QueueBuffersToPluginOutput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@@Z; CKsOutputPin2::DA_QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)
0x18002e977  mov     rcx, [rdi]; this
0x18002e97a  lea     r8, [rcx+2D0h]
0x18002e981  mov     rdx, [r8]; struct __POSITION *
0x18002e984  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x18002e989  test    rax, rax
0x18002e98c  jz      short loc_18002E99D
0x18002e98e  mov     rcx, [rcx+3D8h]
0x18002e995  mov     rdx, r8
0x18002e998  call    ?QueueAsyncItemList@CAsyncItemHandler@@QEAAKPEAV?$CGenericList@U_ASYNC_ITEM@@@@@Z; CAsyncItemHandler::QueueAsyncItemList(CGenericList<_ASYNC_ITEM> *)
0x18002e99d  mov     rcx, rsi; lpCriticalSection
0x18002e9a0  call    cs:__imp_LeaveCriticalSection
0x18002e9a7  nop     dword ptr [rax+rax+00h]
0x18002e9ac  mov     rcx, [rbx+18h]; hObject
0x18002e9b0  test    rcx, rcx
0x18002e9b3  jz      short loc_18002E9C1
0x18002e9b5  call    cs:__imp_CloseHandle
0x18002e9bc  nop     dword ptr [rax+rax+00h]
0x18002e9c1  mov     edx, 30h ; '0'; unsigned __int64
0x18002e9c6  mov     rcx, rbx; void *
0x18002e9c9  add     rsp, 28h
0x18002e9cd  pop     rdi
0x18002e9ce  pop     rsi
0x18002e9cf  pop     rbp
0x18002e9d0  pop     rbx
0x18002e9d1  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
