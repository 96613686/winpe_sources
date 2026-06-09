# CKsOutputPin2::QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x1001d6ae`
- end: `0x1001d894`
- name: `?QueueBuffersToPluginOutput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `486`
- prototype: `int __fastcall(int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1001d8a0`

## callees

- `0x1001a001`
- `0x1001a270`
- `0x1001d6ae`
- `0x1002bd71`
- `0x1002d510`
- `0x1002fea7`
- `0x1002ff0f`
- `0x1003a6fd`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1001d79e`
- `KERNEL32!SetEvent` at `0x1001d79e`
- `KERNEL32!CreateEventW` at `0x1001d6fb`
- `KERNEL32!CreateEventW` at `0x1001d6fb`
- `KERNEL32!CloseHandle` at `0x1001d855`
- `KERNEL32!CloseHandle` at `0x1001d855`
- `KERNEL32!LeaveCriticalSection` at `0x1001d813`
- `KERNEL32!LeaveCriticalSection` at `0x1001d813`
- `KERNEL32!EnterCriticalSection` at `0x1001d82d`
- `KERNEL32!EnterCriticalSection` at `0x1001d82d`

## string_xrefs

- `0x1001d6df`: `CKsOutputPin2::QueueBuffersToPluginOutput`

## pseudocode

```c
int __fastcall CKsOutputPin2::QueueBuffersToPluginOutput(int a1, int a2)
{
  _DWORD *v2; // ebx
  _DWORD *v3; // esi
  HANDLE EventW; // edi
  int v5; // edi
  int v6; // eax
  struct __POSITION *v7; // eax
  CAsyncItemHandler *v9; // [esp+0h] [ebp-28h]
  struct _ASYNC_ITEM *v10; // [esp+4h] [ebp-24h]
  int v11; // [esp+10h] [ebp-18h]
  HANDLE hEvent; // [esp+1Ch] [ebp-Ch]

  v2 = 0;
  v3 = 0;
  v11 = *(_DWORD *)(a1 + 40);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      0x27u,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      "CKsOutputPin2::QueueBuffersToPluginOutput");
  EventW = CreateEventW(0, 0, 0, 0);
  hEvent = EventW;
  if ( !EventW )
  {
    v5 = -2147467259;
    goto LABEL_18;
  }
  v2 = operator new(0x18u);
  if ( !v2 )
    goto LABEL_7;
  v3 = operator new(0x14u);
  if ( !v3 )
    goto LABEL_7;
  v3[3] = EventW;
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      (int)&Microsoft_Windows_DirectShow_KernelSupport_Context,
      (const EVENT_DESCRIPTOR *)ProcessOutput_Start,
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 40),
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 8),
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 12));
  v6 = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD *))(**(_DWORD **)(a1 + 760) + 56))(
         *(_DWORD *)(**(_DWORD **)(a1 + 760) + 56),
         *(_DWORD *)(a1 + 760),
         *(_DWORD *)(a2 + 280),
         v3 + 3);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 == -2147483638 )
    {
      v5 = 0;
    }
    else if ( v6 < 0 )
    {
      (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(a2 + 16) + 8))(
        *(_DWORD *)(**(_DWORD **)(a2 + 16) + 8),
        *(_DWORD *)(a2 + 16));
LABEL_18:
      operator delete(v2, 0x18u);
      operator delete(v3, 0x14u);
      if ( hEvent )
        CloseHandle(hEvent);
      return v5;
    }
  }
  else
  {
    SetEvent(hEvent);
  }
  *v3 = a1;
  v3[1] = a2;
  v2[1] = 0;
  *v2 = 0;
  *((_BYTE *)v2 + 8) = 1;
  v2[3] = hEvent;
  v2[4] = CKsOutputPin2::AppQueueItem;
  v2[5] = v3;
  if ( !CBaseList::AddTailI((CBaseList *)(a1 + 492), v2) )
  {
LABEL_7:
    v5 = -2147024882;
    goto LABEL_18;
  }
  v7 = *(struct __POSITION **)(*v3 + 492);
  if ( v7 && v7[2].unused )
  {
    CBaseList::RemoveI((CBaseList *)(*v3 + 492), v7);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 244));
    CAsyncItemHandler::QueueAsyncItem(v9, v10);
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 244));
  }
  if ( v5 < 0 )
    goto LABEL_18;
  return v5;
}

```

## disassembly

```asm
0x1001d6ae  mov     edi, edi
0x1001d6b0  push    ebp
0x1001d6b1  mov     ebp, esp
0x1001d6b3  sub     esp, 1Ch
0x1001d6b6  push    ebx
0x1001d6b7  mov     eax, ecx
0x1001d6b9  mov     [ebp+var_4], edx
0x1001d6bc  push    esi; struct _ASYNC_ITEM *
0x1001d6bd  push    edi; this
0x1001d6be  xor     edi, edi
0x1001d6c0  mov     [ebp+var_10], eax
0x1001d6c3  mov     eax, [eax+28h]
0x1001d6c6  mov     ebx, edi
0x1001d6c8  mov     esi, edi
0x1001d6ca  mov     [ebp+var_18], eax
0x1001d6cd  mov     eax, _WPP_GLOBAL_Control
0x1001d6d2  cmp     eax, offset _WPP_GLOBAL_Control
0x1001d6d7  jz      short loc_1001D6F7
0x1001d6d9  cmp     byte ptr [eax+19h], 2
0x1001d6dd  jb      short loc_1001D6F7
0x1001d6df  push    offset aCksoutputpin2Q; "CKsOutputPin2::QueueBuffersToPluginOutp"...
0x1001d6e4  push    dword ptr [eax+14h]
0x1001d6e7  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001d6ec  push    dword ptr [eax+10h]; LoggerHandle
0x1001d6ef  push    27h ; '''
0x1001d6f1  pop     ecx; MessageNumber
0x1001d6f2  call    _WPP_SF_s@20; WPP_SF_s(x,x,x,x,x)
0x1001d6f7  push    edi; lpName
0x1001d6f8  push    edi; bInitialState
0x1001d6f9  push    edi; bManualReset
0x1001d6fa  push    edi; lpEventAttributes
0x1001d6fb  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001d701  mov     edi, eax
0x1001d703  mov     [ebp+hEvent], edi
0x1001d706  test    edi, edi
0x1001d708  jnz     short loc_1001D714
0x1001d70a  mov     edi, 80004005h
0x1001d70f  jmp     loc_1001D83A
0x1001d714  push    18h; Size
0x1001d716  call    ??2@YAPAXI@Z; operator new(uint)
0x1001d71b  mov     ebx, eax
0x1001d71d  pop     ecx
0x1001d71e  test    ebx, ebx
0x1001d720  jnz     short loc_1001D72C
0x1001d722  mov     edi, 8007000Eh
0x1001d727  jmp     loc_1001D83A
0x1001d72c  push    14h; Size
0x1001d72e  call    ??2@YAPAXI@Z; operator new(uint)
0x1001d733  mov     esi, eax
0x1001d735  mov     [ebp+var_8], esi
0x1001d738  pop     ecx
0x1001d739  test    esi, esi
0x1001d73b  jz      short loc_1001D722
0x1001d73d  lea     eax, [esi+0Ch]
0x1001d740  mov     [eax], edi
0x1001d742  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001d749  mov     edi, [ebp+var_4]
0x1001d74c  mov     [ebp+var_14], eax
0x1001d74f  jz      short loc_1001D76F
0x1001d751  mov     eax, [edi+118h]
0x1001d757  mov     edx, offset _ProcessOutput_Start
0x1001d75c  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001d761  push    dword ptr [eax+0Ch]
0x1001d764  push    dword ptr [eax+8]
0x1001d767  push    dword ptr [eax+28h]
0x1001d76a  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001d76f  mov     ecx, [ebp+var_10]
0x1001d772  push    [ebp+var_14]
0x1001d775  push    dword ptr [edi+118h]
0x1001d77b  mov     ecx, [ecx+2F8h]
0x1001d781  push    ecx
0x1001d782  mov     eax, [ecx]
0x1001d784  mov     esi, [eax+38h]
0x1001d787  mov     ecx, esi; this
0x1001d789  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001d78f  call    esi
0x1001d791  mov     edi, eax
0x1001d793  test    edi, edi
0x1001d795  jnz     loc_1001D862
0x1001d79b  push    [ebp+hEvent]; hEvent
0x1001d79e  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001d7a4  mov     esi, [ebp+var_8]
0x1001d7a7  mov     ecx, [ebp+var_10]
0x1001d7aa  mov     eax, [ebp+var_4]
0x1001d7ad  push    ebx; void *
0x1001d7ae  mov     [esi], ecx
0x1001d7b0  add     ecx, 1ECh; this
0x1001d7b6  mov     [esi+4], eax
0x1001d7b9  mov     eax, [ebp+hEvent]
0x1001d7bc  mov     dword ptr [ebx+4], 0
0x1001d7c3  mov     dword ptr [ebx], 0
0x1001d7c9  mov     byte ptr [ebx+8], 1
0x1001d7cd  mov     [ebx+0Ch], eax
0x1001d7d0  mov     dword ptr [ebx+10h], offset ?AppQueueItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin2::AppQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001d7d7  mov     [ebx+14h], esi
0x1001d7da  call    ?AddTailI@CBaseList@@IAEPAU__POSITION@@PAX@Z; CBaseList::AddTailI(void *)
0x1001d7df  test    eax, eax
0x1001d7e1  jz      loc_1001D722
0x1001d7e7  mov     edx, [esi]
0x1001d7e9  mov     eax, [edx+1ECh]
0x1001d7ef  test    eax, eax
0x1001d7f1  jz      short loc_1001D836
0x1001d7f3  mov     ecx, [eax+8]
0x1001d7f6  mov     [ebp+var_14], ecx
0x1001d7f9  test    ecx, ecx
0x1001d7fb  jz      short loc_1001D836
0x1001d7fd  push    eax; struct __POSITION *
0x1001d7fe  lea     ecx, [edx+1ECh]; this
0x1001d804  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1001d809  mov     esi, [ebp+var_18]
0x1001d80c  add     esi, 0F4h
0x1001d812  push    esi; lpCriticalSection
0x1001d813  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001d819  mov     eax, [ebp+var_8]
0x1001d81c  mov     edx, [ebp+var_14]
0x1001d81f  mov     ecx, [eax]
0x1001d821  mov     ecx, [ecx+298h]
0x1001d827  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001d82c  push    esi; lpCriticalSection
0x1001d82d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d833  mov     esi, [ebp+var_8]
0x1001d836  test    edi, edi
0x1001d838  jns     short loc_1001D85B
0x1001d83a  push    18h; unsigned int
0x1001d83c  push    ebx; Block
0x1001d83d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d842  push    14h; unsigned int
0x1001d844  push    esi; Block
0x1001d845  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001d84a  mov     eax, [ebp+hEvent]
0x1001d84d  add     esp, 10h
0x1001d850  test    eax, eax
0x1001d852  jz      short loc_1001D85B
0x1001d854  push    eax; hObject
0x1001d855  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001d85b  mov     eax, edi
0x1001d85d  pop     edi
0x1001d85e  pop     esi
0x1001d85f  pop     ebx
0x1001d860  leave
0x1001d861  retn
0x1001d862  cmp     edi, 8000000Ah
0x1001d868  jnz     short loc_1001D871
0x1001d86a  xor     edi, edi
0x1001d86c  jmp     loc_1001D7A4
0x1001d871  test    edi, edi
0x1001d873  jns     loc_1001D7A4
0x1001d879  mov     eax, [ebp+var_4]
0x1001d87c  mov     eax, [eax+10h]
0x1001d87f  push    eax
0x1001d880  mov     ecx, [eax]
0x1001d882  mov     esi, [ecx+8]
0x1001d885  mov     ecx, esi; this
0x1001d887  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001d88d  call    esi
0x1001d88f  mov     esi, [ebp+var_8]
0x1001d892  jmp     short loc_1001D83A
```
