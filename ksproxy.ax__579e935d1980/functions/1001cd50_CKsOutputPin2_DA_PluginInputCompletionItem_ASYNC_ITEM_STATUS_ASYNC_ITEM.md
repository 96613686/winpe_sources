# CKsOutputPin2::DA_PluginInputCompletionItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x1001cd50`
- end: `0x1001ce6a`
- name: `?DA_PluginInputCompletionItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z`
- size: `282`
- prototype: `static void __stdcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1001a001`
- `0x1001a270`
- `0x1001cd50`
- `0x1002bd71`
- `0x1002d510`
- `0x1002fea7`
- `0x1003a6f2`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1001ce2a`
- `KERNEL32!CloseHandle` at `0x1001ce2a`
- `KERNEL32!LeaveCriticalSection` at `0x1001ce1b`
- `KERNEL32!LeaveCriticalSection` at `0x1001ce1b`
- `KERNEL32!EnterCriticalSection` at `0x1001cde2`
- `KERNEL32!EnterCriticalSection` at `0x1001cde2`

## string_xrefs

- `0x1001cd79`: `CKsOutputPin2::DA_PluginInputCompletionItem`

## pseudocode

```c
void __stdcall CKsOutputPin2::DA_PluginInputCompletionItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *Block)
{
  void **context; // edi
  struct __POSITION *v3; // eax
  CAsyncItemHandler *v4; // [esp+8h] [ebp-10h]
  struct _ASYNC_ITEM *v5; // [esp+Ch] [ebp-Ch]
  int v6; // [esp+14h] [ebp-4h]

  context = (void **)Block->context;
  v6 = *((_DWORD *)*context + 10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x22u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)"CKsOutputPin2::DA_PluginInputCompletionItem");
  (*(void (__thiscall **)(_DWORD, int))(*((_DWORD *)*context + 68) + 56))(
    *(_DWORD *)(*((_DWORD *)*context + 68) + 56),
    (int)*context + 272);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      *(_DWORD *)(*((_DWORD *)context[2] + 70) + 40),
      *(_DWORD *)(*((_DWORD *)context[2] + 70) + 8),
      *(_DWORD *)(*((_DWORD *)context[2] + 70) + 12));
  if ( a1 == EVENT_SIGNALLED )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 244));
    v3 = (struct __POSITION *)*((_DWORD *)*context + 182);
    if ( v3 && v3[2].unused )
    {
      CBaseList::RemoveI((CBaseList *)((char *)*context + 728), v3);
      CAsyncItemHandler::QueueAsyncItem(v4, v5);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 244));
  }
  if ( Block->event )
    CloseHandle(Block->event);
  operator delete[](*(void **)(*((_DWORD *)context[2] + 70) + 40));
  operator delete(context[2], 0x138u);
  operator delete(context, 0x14u);
  operator delete(Block, 0x18u);
}

```

## disassembly

```asm
0x1001cd50  mov     edi, edi
0x1001cd52  push    ebp
0x1001cd53  mov     ebp, esp
0x1001cd55  push    ecx
0x1001cd56  push    ebx
0x1001cd57  mov     ebx, [ebp+Block]
0x1001cd5a  push    esi; struct _ASYNC_ITEM *
0x1001cd5b  push    edi; this
0x1001cd5c  mov     edi, [ebx+14h]
0x1001cd5f  mov     eax, [edi]
0x1001cd61  mov     eax, [eax+28h]
0x1001cd64  mov     [ebp+var_4], eax
0x1001cd67  mov     eax, _WPP_GLOBAL_Control
0x1001cd6c  cmp     eax, offset _WPP_GLOBAL_Control
0x1001cd71  jz      short loc_1001CD91
0x1001cd73  cmp     byte ptr [eax+19h], 2
0x1001cd77  jb      short loc_1001CD91
0x1001cd79  push    offset aCksoutputpin2D_4; "CKsOutputPin2::DA_PluginInputCompletion"...
0x1001cd7e  push    dword ptr [eax+14h]
0x1001cd81  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001cd86  push    dword ptr [eax+10h]; LoggerHandle
0x1001cd89  push    22h ; '"'
0x1001cd8b  pop     ecx; MessageNumber
0x1001cd8c  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001cd91  mov     eax, [edi]
0x1001cd93  add     eax, 110h
0x1001cd98  push    eax
0x1001cd99  mov     ecx, [eax]
0x1001cd9b  mov     esi, [ecx+38h]
0x1001cd9e  mov     ecx, esi; this
0x1001cda0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001cda6  call    esi
0x1001cda8  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001cdaf  jz      short loc_1001CDD2
0x1001cdb1  mov     eax, [edi+8]
0x1001cdb4  mov     edx, offset _ProcessOutput_Complete
0x1001cdb9  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001cdbe  mov     eax, [eax+118h]
0x1001cdc4  push    dword ptr [eax+0Ch]
0x1001cdc7  push    dword ptr [eax+8]
0x1001cdca  push    dword ptr [eax+28h]
0x1001cdcd  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001cdd2  cmp     [ebp+arg_0], 0
0x1001cdd6  jnz     short loc_1001CE21
0x1001cdd8  mov     esi, [ebp+var_4]
0x1001cddb  add     esi, 0F4h
0x1001cde1  push    esi; lpCriticalSection
0x1001cde2  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001cde8  mov     edx, [edi]
0x1001cdea  mov     eax, [edx+2D8h]
0x1001cdf0  test    eax, eax
0x1001cdf2  jz      short loc_1001CE1A
0x1001cdf4  mov     ecx, [eax+8]
0x1001cdf7  mov     [ebp+var_4], ecx
0x1001cdfa  test    ecx, ecx
0x1001cdfc  jz      short loc_1001CE1A
0x1001cdfe  push    eax; struct __POSITION *
0x1001cdff  lea     ecx, [edx+2D8h]; this
0x1001ce05  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1001ce0a  mov     ecx, [edi]
0x1001ce0c  mov     edx, [ebp+var_4]
0x1001ce0f  mov     ecx, [ecx+2F4h]
0x1001ce15  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001ce1a  push    esi; lpCriticalSection
0x1001ce1b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ce21  cmp     dword ptr [ebx+0Ch], 0
0x1001ce25  jz      short loc_1001CE30
0x1001ce27  push    dword ptr [ebx+0Ch]; hObject
0x1001ce2a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001ce30  mov     eax, [edi+8]
0x1001ce33  mov     eax, [eax+118h]
0x1001ce39  push    dword ptr [eax+28h]; Block
0x1001ce3c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ce41  mov     [esp+14h+var_14], 138h; unsigned int
0x1001ce48  push    dword ptr [edi+8]; Block
0x1001ce4b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001ce50  push    14h; unsigned int
0x1001ce52  push    edi; Block
0x1001ce53  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001ce58  push    18h; unsigned int
0x1001ce5a  push    ebx; Block
0x1001ce5b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001ce60  add     esp, 18h
0x1001ce63  pop     edi
0x1001ce64  pop     esi
0x1001ce65  pop     ebx
0x1001ce66  leave
0x1001ce67  retn    8
```
