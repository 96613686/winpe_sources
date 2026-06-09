# CKsOutputPin2::DA_QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x1001cb15`
- end: `0x1001cc5e`
- name: `?DA_QueueBuffersToPluginOutput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `329`
- prototype: `int __fastcall(int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1001cc70`

## callees

- `0x1001a270`
- `0x1001cb15`
- `0x1002bd71`
- `0x1002d510`
- `0x1002ff0f`
- `0x1003a6fd`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1001cc28`
- `KERNEL32!SetEvent` at `0x1001cc41`
- `KERNEL32!SetEvent` at `0x1001cc28`
- `KERNEL32!SetEvent` at `0x1001cc41`
- `KERNEL32!CreateEventW` at `0x1001cb2e`
- `KERNEL32!CreateEventW` at `0x1001cb2e`

## pseudocode

```c
int __fastcall CKsOutputPin2::DA_QueueBuffersToPluginOutput(int a1, int a2)
{
  HANDLE EventW; // ebx
  int v4; // esi
  _DWORD *v5; // edi
  _DWORD *v6; // eax
  int v7; // eax
  CAsyncItemHandler *v9; // [esp+0h] [ebp-20h]
  struct _ASYNC_ITEM *v10; // [esp+4h] [ebp-1Ch]
  char *v11; // [esp+10h] [ebp-10h]
  _DWORD *v12; // [esp+14h] [ebp-Ch]

  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return -2147467259;
  v5 = operator new(0x18u);
  if ( !v5 )
    return -2147024882;
  v6 = operator new(0x14u);
  v12 = v6;
  if ( !v6 )
    return -2147024882;
  v11 = (char *)(v6 + 3);
  v6[3] = EventW;
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(a1 + 272) + 52))(*(_DWORD *)(*(_DWORD *)(a1 + 272) + 52), a1 + 272);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      (int)&Microsoft_Windows_DirectShow_KernelSupport_Context,
      (const EVENT_DESCRIPTOR *)ProcessOutput_Start,
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 40),
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 8),
      *(_DWORD *)(*(_DWORD *)(a2 + 280) + 12));
  *v12 = a1;
  v12[1] = a2;
  v5[5] = v12;
  v5[1] = 0;
  *v5 = 0;
  *((_BYTE *)v5 + 8) = 1;
  v5[3] = EventW;
  v5[4] = CKsOutputPin2::DA_AppQueueItem;
  v7 = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD, char *))(**(_DWORD **)(a1 + 760) + 56))(
         *(_DWORD *)(**(_DWORD **)(a1 + 760) + 56),
         *(_DWORD *)(a1 + 760),
         *(_DWORD *)(a2 + 280),
         v11);
  v4 = v7;
  if ( v7 >= 0 || v7 == -2147483638 )
  {
    if ( CBaseList::AddTailI((CBaseList *)(a1 + 492), v5) )
    {
      if ( !v4 )
      {
        SetEvent(EventW);
        return v4;
      }
      if ( v4 == -2147483638 )
        return 0;
      goto LABEL_15;
    }
    return -2147024882;
  }
LABEL_15:
  if ( v4 < 0 )
  {
    SetEvent(EventW);
    CAsyncItemHandler::QueueAsyncItem(v9, v10);
  }
  return v4;
}

```

## disassembly

```asm
0x1001cb15  mov     edi, edi
0x1001cb17  push    ebp
0x1001cb18  mov     ebp, esp
0x1001cb1a  sub     esp, 14h
0x1001cb1d  push    ebx
0x1001cb1e  push    esi; struct _ASYNC_ITEM *
0x1001cb1f  push    edi; this
0x1001cb20  xor     eax, eax
0x1001cb22  mov     [ebp+var_8], edx
0x1001cb25  push    eax; lpName
0x1001cb26  push    eax; bInitialState
0x1001cb27  push    eax; bManualReset
0x1001cb28  mov     esi, ecx
0x1001cb2a  push    eax; lpEventAttributes
0x1001cb2b  mov     [ebp+var_4], esi
0x1001cb2e  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001cb34  mov     ebx, eax
0x1001cb36  test    ebx, ebx
0x1001cb38  jnz     short loc_1001CB44
0x1001cb3a  mov     esi, 80004005h
0x1001cb3f  jmp     loc_1001CC57
0x1001cb44  push    18h; Size
0x1001cb46  call    ??2@YAPAXI@Z; operator new(uint)
0x1001cb4b  mov     edi, eax
0x1001cb4d  pop     ecx
0x1001cb4e  test    edi, edi
0x1001cb50  jnz     short loc_1001CB5C
0x1001cb52  mov     esi, 8007000Eh
0x1001cb57  jmp     loc_1001CC57
0x1001cb5c  push    14h; Size
0x1001cb5e  call    ??2@YAPAXI@Z; operator new(uint)
0x1001cb63  mov     [ebp+var_C], eax
0x1001cb66  pop     ecx
0x1001cb67  test    eax, eax
0x1001cb69  jz      short loc_1001CB52
0x1001cb6b  add     eax, 0Ch
0x1001cb6e  mov     [ebp+var_10], eax
0x1001cb71  mov     [eax], ebx
0x1001cb73  lea     eax, [esi+110h]
0x1001cb79  mov     ecx, [eax]
0x1001cb7b  push    eax
0x1001cb7c  mov     esi, [ecx+34h]
0x1001cb7f  mov     ecx, esi; this
0x1001cb81  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001cb87  call    esi
0x1001cb89  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001cb90  jz      short loc_1001CBB3
0x1001cb92  mov     eax, [ebp+var_8]
0x1001cb95  mov     edx, offset _ProcessOutput_Start
0x1001cb9a  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001cb9f  mov     eax, [eax+118h]
0x1001cba5  push    dword ptr [eax+0Ch]
0x1001cba8  push    dword ptr [eax+8]
0x1001cbab  push    dword ptr [eax+28h]
0x1001cbae  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001cbb3  mov     ecx, [ebp+var_C]
0x1001cbb6  mov     eax, [ebp+var_4]
0x1001cbb9  mov     edx, [ebp+var_8]
0x1001cbbc  push    [ebp+var_10]
0x1001cbbf  mov     [ecx], eax
0x1001cbc1  mov     [ecx+4], edx
0x1001cbc4  mov     [edi+14h], ecx
0x1001cbc7  mov     dword ptr [edi+4], 0
0x1001cbce  mov     dword ptr [edi], 0
0x1001cbd4  mov     byte ptr [edi+8], 1
0x1001cbd8  mov     [edi+0Ch], ebx
0x1001cbdb  mov     dword ptr [edi+10h], offset ?DA_AppQueueItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DA_AppQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001cbe2  mov     ecx, [eax+2F8h]
0x1001cbe8  push    dword ptr [edx+118h]
0x1001cbee  push    ecx
0x1001cbef  mov     eax, [ecx]
0x1001cbf1  mov     esi, [eax+38h]
0x1001cbf4  mov     ecx, esi; this
0x1001cbf6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001cbfc  call    esi
0x1001cbfe  mov     esi, eax
0x1001cc00  test    esi, esi
0x1001cc02  jns     short loc_1001CC0C
0x1001cc04  cmp     esi, 8000000Ah
0x1001cc0a  jnz     short loc_1001CC3C
0x1001cc0c  mov     ecx, [ebp+var_4]
0x1001cc0f  push    edi; void *
0x1001cc10  add     ecx, 1ECh; this
0x1001cc16  call    ?AddTailI@CBaseList@@IAEPAU__POSITION@@PAX@Z; CBaseList::AddTailI(void *)
0x1001cc1b  test    eax, eax
0x1001cc1d  jz      loc_1001CB52
0x1001cc23  test    esi, esi
0x1001cc25  jnz     short loc_1001CC30
0x1001cc27  push    ebx; hEvent
0x1001cc28  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001cc2e  jmp     short loc_1001CC57
0x1001cc30  cmp     esi, 8000000Ah
0x1001cc36  jnz     short loc_1001CC3C
0x1001cc38  xor     esi, esi
0x1001cc3a  jmp     short loc_1001CC57
0x1001cc3c  test    esi, esi
0x1001cc3e  jns     short loc_1001CC57
0x1001cc40  push    ebx; hEvent
0x1001cc41  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001cc47  mov     eax, [ebp+var_4]
0x1001cc4a  mov     edx, edi
0x1001cc4c  mov     ecx, [eax+2F4h]
0x1001cc52  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001cc57  pop     edi
0x1001cc58  mov     eax, esi
0x1001cc5a  pop     esi
0x1001cc5b  pop     ebx
0x1001cc5c  leave
0x1001cc5d  retn
```
