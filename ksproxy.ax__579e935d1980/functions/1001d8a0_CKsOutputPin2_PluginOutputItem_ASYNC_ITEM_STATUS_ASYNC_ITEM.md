# CKsOutputPin2::PluginOutputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x1001d8a0`
- end: `0x1001d9f8`
- name: `?PluginOutputItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z`
- size: `344`
- prototype: `static void __stdcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1001a001`
- `0x1001a270`
- `0x1001d6ae`
- `0x1001d8a0`
- `0x1002bd71`
- `0x1002d510`
- `0x1002fea7`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001d95d`
- `KERNEL32!GetLastError` at `0x1001d95d`
- `KERNEL32!LeaveCriticalSection` at `0x1001d982`
- `KERNEL32!LeaveCriticalSection` at `0x1001d9d8`
- `KERNEL32!LeaveCriticalSection` at `0x1001d982`
- `KERNEL32!LeaveCriticalSection` at `0x1001d9d8`
- `KERNEL32!EnterCriticalSection` at `0x1001d91e`
- `KERNEL32!EnterCriticalSection` at `0x1001d9f0`
- `KERNEL32!EnterCriticalSection` at `0x1001d91e`
- `KERNEL32!EnterCriticalSection` at `0x1001d9f0`
- `KERNEL32!GetOverlappedResult` at `0x1001d953`
- `KERNEL32!GetOverlappedResult` at `0x1001d953`

## string_xrefs

- `0x1001d8cb`: `CKsOutputPin2::PluginOutputItem`

## pseudocode

```c
void __stdcall CKsOutputPin2::PluginOutputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *Block)
{
  int *context; // edi
  int v3; // esi
  int v4; // ecx
  struct _RTL_CRITICAL_SECTION *v5; // esi
  struct __POSITION *v6; // eax
  CAsyncItemHandler *v7; // [esp+0h] [ebp-18h]
  struct _ASYNC_ITEM *v8; // [esp+4h] [ebp-14h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [esp+Ch] [ebp-Ch]
  DWORD NumberOfBytesTransferred; // [esp+14h] [ebp-4h] BYREF

  context = (int *)Block->context;
  v3 = *(_DWORD *)(*context + 40);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x28u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)"CKsOutputPin2::PluginOutputItem");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      *(_DWORD *)(*(_DWORD *)(context[1] + 280) + 40),
      *(_DWORD *)(*(_DWORD *)(context[1] + 280) + 8),
      *(_DWORD *)(*(_DWORD *)(context[1] + 280) + 12));
  if ( a1 == EVENT_SIGNALLED )
  {
    lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v3 + 244);
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 244));
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(*context + 272) + 56))(
      *(_DWORD *)(*(_DWORD *)(*context + 272) + 56),
      *context + 272);
    if ( GetOverlappedResult(
           *(HANDLE *)(*context + 356),
           (LPOVERLAPPED)(context[1] + 284),
           &NumberOfBytesTransferred,
           0) )
    {
      CKsOutputPin2::QueueBuffersToPluginOutput(*context, context[1]);
      v6 = *(struct __POSITION **)(*context + 728);
      if ( v6 && v6[2].unused )
      {
        CBaseList::RemoveI((CBaseList *)(*context + 728), v6);
        v5 = (struct _RTL_CRITICAL_SECTION *)(v3 + 244);
        LeaveCriticalSection(lpCriticalSection);
        CAsyncItemHandler::QueueAsyncItem(v7, v8);
        EnterCriticalSection(lpCriticalSection);
        goto LABEL_11;
      }
    }
    else
    {
      GetLastError();
      v4 = *(_DWORD *)(context[1] + 16);
      if ( v4 )
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v4 + 8))(*(_DWORD *)(*(_DWORD *)v4 + 8), v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)(v3 + 244);
LABEL_11:
    LeaveCriticalSection(v5);
  }
  operator delete(Block->context, 0);
  operator delete(Block, 0x18u);
}

```

## disassembly

```asm
0x1001d8a0  mov     edi, edi
0x1001d8a2  push    ebp
0x1001d8a3  mov     ebp, esp
0x1001d8a5  and     esp, 0FFFFFFF8h
0x1001d8a8  sub     esp, 0Ch
0x1001d8ab  push    ebx
0x1001d8ac  mov     ebx, [ebp+Block]
0x1001d8af  push    esi; struct _ASYNC_ITEM *
0x1001d8b0  push    edi; this
0x1001d8b1  mov     edi, [ebx+14h]
0x1001d8b4  mov     eax, [edi]
0x1001d8b6  mov     esi, [eax+28h]
0x1001d8b9  mov     eax, _WPP_GLOBAL_Control
0x1001d8be  cmp     eax, offset _WPP_GLOBAL_Control
0x1001d8c3  jz      short loc_1001D8E3
0x1001d8c5  cmp     byte ptr [eax+19h], 2
0x1001d8c9  jb      short loc_1001D8E3
0x1001d8cb  push    offset aCksoutputpin2P; "CKsOutputPin2::PluginOutputItem"
0x1001d8d0  push    dword ptr [eax+14h]
0x1001d8d3  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001d8d8  push    dword ptr [eax+10h]; LoggerHandle
0x1001d8db  push    28h ; '('
0x1001d8dd  pop     ecx; MessageNumber
0x1001d8de  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001d8e3  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001d8ea  jz      short loc_1001D90D
0x1001d8ec  mov     eax, [edi+4]
0x1001d8ef  mov     edx, offset _DeviceIo_Complete
0x1001d8f4  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001d8f9  mov     eax, [eax+118h]
0x1001d8ff  push    dword ptr [eax+0Ch]
0x1001d902  push    dword ptr [eax+8]
0x1001d905  push    dword ptr [eax+28h]
0x1001d908  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001d90d  cmp     [ebp+arg_0], 0
0x1001d911  jnz     short loc_1001D988
0x1001d913  lea     eax, [esi+0F4h]
0x1001d919  push    eax; lpCriticalSection
0x1001d91a  mov     [esp+1Ch+lpCriticalSection], eax
0x1001d91e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d924  mov     eax, [edi]
0x1001d926  add     eax, 110h
0x1001d92b  push    eax
0x1001d92c  mov     ecx, [eax]
0x1001d92e  mov     esi, [ecx+38h]
0x1001d931  mov     ecx, esi; this
0x1001d933  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001d939  call    esi
0x1001d93b  push    0; bWait
0x1001d93d  lea     eax, [esp+1Ch+NumberOfBytesTransferred]
0x1001d941  push    eax; lpNumberOfBytesTransferred
0x1001d942  mov     eax, [edi+4]
0x1001d945  add     eax, 11Ch
0x1001d94a  push    eax; lpOverlapped
0x1001d94b  mov     eax, [edi]
0x1001d94d  push    dword ptr [eax+164h]; hFile
0x1001d953  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x1001d959  test    eax, eax
0x1001d95b  jnz     short loc_1001D9A6
0x1001d95d  call    ds:__imp__GetLastError@0; GetLastError()
0x1001d963  mov     eax, [edi+4]
0x1001d966  mov     ecx, [eax+10h]
0x1001d969  test    ecx, ecx
0x1001d96b  jz      short loc_1001D97D
0x1001d96d  mov     eax, [ecx]
0x1001d96f  push    ecx
0x1001d970  mov     esi, [eax+8]
0x1001d973  mov     ecx, esi; this
0x1001d975  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001d97b  call    esi
0x1001d97d  mov     esi, [esp+18h+lpCriticalSection]
0x1001d981  push    esi; lpCriticalSection
0x1001d982  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d988  push    0; unsigned int
0x1001d98a  push    dword ptr [ebx+14h]; Block
0x1001d98d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d992  push    18h; unsigned int
0x1001d994  push    ebx; Block
0x1001d995  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d99a  add     esp, 10h
0x1001d99d  pop     edi
0x1001d99e  pop     esi
0x1001d99f  pop     ebx
0x1001d9a0  mov     esp, ebp
0x1001d9a2  pop     ebp
0x1001d9a3  retn    8
0x1001d9a6  mov     edx, [edi+4]
0x1001d9a9  mov     ecx, [edi]
0x1001d9ab  call    ?QueueBuffersToPluginOutput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@@Z; CKsOutputPin2::QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)
0x1001d9b0  mov     edx, [edi]
0x1001d9b2  mov     eax, [edx+2D8h]
0x1001d9b8  test    eax, eax
0x1001d9ba  jz      short loc_1001D97D
0x1001d9bc  mov     ecx, [eax+8]
0x1001d9bf  mov     dword ptr [esp+18h+var_8], ecx
0x1001d9c3  test    ecx, ecx
0x1001d9c5  jz      short loc_1001D97D
0x1001d9c7  push    eax; struct __POSITION *
0x1001d9c8  lea     ecx, [edx+2D8h]; this
0x1001d9ce  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1001d9d3  mov     esi, [esp+18h+lpCriticalSection]
0x1001d9d7  push    esi; lpCriticalSection
0x1001d9d8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d9de  mov     ecx, [edi]
0x1001d9e0  mov     edx, dword ptr [esp+18h+var_8]
0x1001d9e4  mov     ecx, [ecx+2F4h]
0x1001d9ea  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001d9ef  push    esi; lpCriticalSection
0x1001d9f0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d9f6  jmp     short loc_1001D981
```
