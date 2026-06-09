# CKsOutputPin2::DA_PluginInputItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)

- ea: `0x1001cfd0`
- end: `0x1001d0fd`
- name: `?DA_PluginInputItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z`
- size: `301`
- prototype: `void __stdcall(enum ASYNC_ITEM_STATUS, struct _ASYNC_ITEM *Block)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1001a001`
- `0x1001a270`
- `0x1001ce70`
- `0x1001cfd0`
- `0x1002d510`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001d088`
- `KERNEL32!GetLastError` at `0x1001d088`
- `KERNEL32!CloseHandle` at `0x1001d0dc`
- `KERNEL32!CloseHandle` at `0x1001d0dc`
- `KERNEL32!LeaveCriticalSection` at `0x1001d0ce`
- `KERNEL32!LeaveCriticalSection` at `0x1001d0ce`
- `KERNEL32!EnterCriticalSection` at `0x1001d044`
- `KERNEL32!EnterCriticalSection` at `0x1001d044`
- `KERNEL32!GetOverlappedResult` at `0x1001d07e`
- `KERNEL32!GetOverlappedResult` at `0x1001d07e`

## string_xrefs

- `0x1001cffb`: `CKsOutputPin2::DA_PluginInputItem`

## pseudocode

```c
void __stdcall CKsOutputPin2::DA_PluginInputItem(enum ASYNC_ITEM_STATUS a1, struct _ASYNC_ITEM *Block)
{
  void *context; // edi
  int v3; // esi
  _DWORD *v4; // ecx
  struct _KSSTREAM_SEGMENT_EX2 *v5; // [esp+0h] [ebp-18h]
  struct _KSSTREAM_SEGMENT_EX2 *v6; // [esp+4h] [ebp-14h]
  DWORD NumberOfBytesTransferred; // [esp+10h] [ebp-8h] BYREF
  int v8; // [esp+14h] [ebp-4h]

  context = Block->context;
  v3 = *(_DWORD *)(*(_DWORD *)context + 40);
  v8 = v3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x23u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      "CKsOutputPin2::DA_PluginInputItem");
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      (int)&Microsoft_Windows_DirectShow_KernelSupport_Context,
      (const EVENT_DESCRIPTOR *)DeviceIo_Complete,
      *(_DWORD *)(*(_DWORD *)(*((_DWORD *)context + 2) + 280) + 40),
      *(_DWORD *)(*(_DWORD *)(*((_DWORD *)context + 2) + 280) + 8),
      *(_DWORD *)(*(_DWORD *)(*((_DWORD *)context + 2) + 280) + 12));
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 244));
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(*(_DWORD *)context + 272) + 56))(
    *(_DWORD *)(*(_DWORD *)(*(_DWORD *)context + 272) + 56),
    *(_DWORD *)context + 272);
  if ( a1 == EVENT_SIGNALLED )
  {
    if ( GetOverlappedResult(
           *(HANDLE *)(*(_DWORD *)context + 356),
           (LPOVERLAPPED)(*((_DWORD *)context + 2) + 284),
           &NumberOfBytesTransferred,
           0) )
    {
      v4 = *(_DWORD **)context;
      if ( *(_DWORD *)(*(_DWORD *)(*(_DWORD *)context + 40) + 20) && !v4[144] && !v4[145] && !v4[160] && v4[38] )
        CKsOutputPin2::DA_QueueBuffersToPluginInput(
          *((_DWORD *)context + 2),
          (int)v4,
          *((CKsOutputPin2 **)context + 1),
          v5,
          v6);
    }
    else
    {
      GetLastError();
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 244));
  if ( Block->event )
    CloseHandle(Block->event);
  operator delete(Block->context, 0);
  operator delete(Block, 0x18u);
}

```

## disassembly

```asm
0x1001cfd0  mov     edi, edi
0x1001cfd2  push    ebp
0x1001cfd3  mov     ebp, esp
0x1001cfd5  sub     esp, 0Ch
0x1001cfd8  push    ebx
0x1001cfd9  mov     ebx, [ebp+Block]
0x1001cfdc  push    esi; struct _KSSTREAM_SEGMENT_EX2 *
0x1001cfdd  push    edi; struct _KSSTREAM_SEGMENT_EX2 *
0x1001cfde  mov     edi, [ebx+14h]
0x1001cfe1  mov     eax, [edi]
0x1001cfe3  mov     esi, [eax+28h]
0x1001cfe6  mov     [ebp+var_4], esi
0x1001cfe9  mov     eax, _WPP_GLOBAL_Control
0x1001cfee  cmp     eax, offset _WPP_GLOBAL_Control
0x1001cff3  jz      short loc_1001D013
0x1001cff5  cmp     byte ptr [eax+19h], 2
0x1001cff9  jb      short loc_1001D013
0x1001cffb  push    offset aCksoutputpin2D_5; "CKsOutputPin2::DA_PluginInputItem"
0x1001d000  push    dword ptr [eax+14h]
0x1001d003  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001d008  push    dword ptr [eax+10h]; LoggerHandle
0x1001d00b  push    23h ; '#'
0x1001d00d  pop     ecx; MessageNumber
0x1001d00e  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001d013  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001d01a  jz      short loc_1001D03D
0x1001d01c  mov     eax, [edi+8]
0x1001d01f  mov     edx, offset _DeviceIo_Complete
0x1001d024  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001d029  mov     eax, [eax+118h]
0x1001d02f  push    dword ptr [eax+0Ch]
0x1001d032  push    dword ptr [eax+8]
0x1001d035  push    dword ptr [eax+28h]
0x1001d038  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001d03d  lea     eax, [esi+0F4h]
0x1001d043  push    eax; lpCriticalSection
0x1001d044  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d04a  mov     eax, [edi]
0x1001d04c  add     eax, 110h
0x1001d051  push    eax
0x1001d052  mov     ecx, [eax]
0x1001d054  mov     esi, [ecx+38h]
0x1001d057  mov     ecx, esi; this
0x1001d059  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001d05f  call    esi
0x1001d061  xor     esi, esi
0x1001d063  cmp     [ebp+arg_0], esi
0x1001d066  jnz     short loc_1001D0C5
0x1001d068  push    esi; bWait
0x1001d069  lea     eax, [ebp+NumberOfBytesTransferred]
0x1001d06c  push    eax; lpNumberOfBytesTransferred
0x1001d06d  mov     eax, [edi+8]
0x1001d070  add     eax, 11Ch
0x1001d075  push    eax; lpOverlapped
0x1001d076  mov     eax, [edi]
0x1001d078  push    dword ptr [eax+164h]; hFile
0x1001d07e  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x1001d084  test    eax, eax
0x1001d086  jnz     short loc_1001D090
0x1001d088  call    ds:__imp__GetLastError@0; GetLastError()
0x1001d08e  jmp     short loc_1001D0C5
0x1001d090  mov     ecx, [edi]
0x1001d092  mov     eax, [ecx+28h]
0x1001d095  cmp     [eax+14h], esi
0x1001d098  jz      short loc_1001D0C5
0x1001d09a  cmp     [ecx+240h], esi
0x1001d0a0  jnz     short loc_1001D0C5
0x1001d0a2  cmp     [ecx+244h], esi
0x1001d0a8  jnz     short loc_1001D0C5
0x1001d0aa  cmp     [ecx+280h], esi
0x1001d0b0  jnz     short loc_1001D0C5
0x1001d0b2  cmp     [ecx+98h], esi
0x1001d0b8  jz      short loc_1001D0C5
0x1001d0ba  push    dword ptr [edi+4]; this
0x1001d0bd  mov     edx, [edi+8]
0x1001d0c0  call    ?DA_QueueBuffersToPluginInput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@0@Z; CKsOutputPin2::DA_QueueBuffersToPluginInput(_KSSTREAM_SEGMENT_EX2 *,_KSSTREAM_SEGMENT_EX2 *)
0x1001d0c5  mov     eax, [ebp+var_4]
0x1001d0c8  add     eax, 0F4h
0x1001d0cd  push    eax; lpCriticalSection
0x1001d0ce  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d0d4  cmp     [ebx+0Ch], esi
0x1001d0d7  jz      short loc_1001D0E2
0x1001d0d9  push    dword ptr [ebx+0Ch]; hObject
0x1001d0dc  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001d0e2  push    esi; unsigned int
0x1001d0e3  push    dword ptr [ebx+14h]; Block
0x1001d0e6  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d0eb  push    18h; unsigned int
0x1001d0ed  push    ebx; Block
0x1001d0ee  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d0f3  add     esp, 10h
0x1001d0f6  pop     edi
0x1001d0f7  pop     esi
0x1001d0f8  pop     ebx
0x1001d0f9  leave
0x1001d0fa  retn    8
```
