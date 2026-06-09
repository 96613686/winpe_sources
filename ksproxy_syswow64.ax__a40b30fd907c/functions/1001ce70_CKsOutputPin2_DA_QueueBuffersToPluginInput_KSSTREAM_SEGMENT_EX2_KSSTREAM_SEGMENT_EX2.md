# CKsOutputPin2::DA_QueueBuffersToPluginInput(_KSSTREAM_SEGMENT_EX2 *,_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x1001ce70`
- end: `0x1001cfc2`
- name: `?DA_QueueBuffersToPluginInput@CKsOutputPin2@@QAGJPAU_KSSTREAM_SEGMENT_EX2@@0@Z`
- size: `338`
- prototype: `int __userpurge@<eax>(int@<edx>, int@<ecx>, CKsOutputPin2 *this, struct _KSSTREAM_SEGMENT_EX2 *, struct _KSSTREAM_SEGMENT_EX2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1001cfd0`

## callees

- `0x1001a270`
- `0x1001ce70`
- `0x1002bd71`
- `0x1002d510`
- `0x1002ff0f`
- `0x1003a6fd`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1001cf89`
- `KERNEL32!SetEvent` at `0x1001cfa3`
- `KERNEL32!SetEvent` at `0x1001cf89`
- `KERNEL32!SetEvent` at `0x1001cfa3`
- `KERNEL32!CreateEventW` at `0x1001ce89`
- `KERNEL32!CreateEventW` at `0x1001ce89`

## pseudocode

```c
int __userpurge CKsOutputPin2::DA_QueueBuffersToPluginInput@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        CKsOutputPin2 *this,
        struct _KSSTREAM_SEGMENT_EX2 *a4,
        struct _KSSTREAM_SEGMENT_EX2 *a5)
{
  HANDLE EventW; // ebx
  int v7; // esi
  _DWORD *v8; // edi
  _DWORD *v9; // eax
  int (__thiscall *v10)(_DWORD, _DWORD, _DWORD, _DWORD *); // ecx
  int v11; // eax
  CAsyncItemHandler *v13; // [esp+0h] [ebp-1Ch]
  struct _ASYNC_ITEM *v14; // [esp+4h] [ebp-18h]
  _DWORD *v15; // [esp+10h] [ebp-Ch]

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v8 = operator new(0x18u);
    if ( !v8 )
      return -2147024882;
    v9 = operator new(0x14u);
    v15 = v9;
    if ( !v9 )
      return -2147024882;
    v9[3] = EventW;
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(a2 + 272) + 52))(
      *(_DWORD *)(*(_DWORD *)(a2 + 272) + 52),
      a2 + 272);
    if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
      McTemplateU0pi_EventWriteTransfer(
        (int)&Microsoft_Windows_DirectShow_KernelSupport_Context,
        (const EVENT_DESCRIPTOR *)ProcessInput_Start,
        *(_DWORD *)(*(_DWORD *)(a1 + 280) + 40),
        *(_DWORD *)(*(_DWORD *)(a1 + 280) + 8),
        *(_DWORD *)(*(_DWORD *)(a1 + 280) + 12));
    v15[1] = this;
    *v15 = a2;
    v15[2] = a1;
    v8[1] = 0;
    *v8 = 0;
    *((_BYTE *)v8 + 8) = 1;
    v8[3] = EventW;
    v8[4] = CKsOutputPin2::DA_PluginInputCompletionItem;
    v8[5] = v15;
    v10 = *(int (__thiscall **)(_DWORD, _DWORD, _DWORD, _DWORD *))(**(_DWORD **)(a2 + 760) + 52);
    v11 = v10(v10, *(_DWORD *)(a2 + 760), *(_DWORD *)(a1 + 280), v15 + 3);
    v7 = v11;
    if ( v11 >= 0 || v11 == -2147483638 )
    {
      if ( !CBaseList::AddTailI((CBaseList *)(a2 + 728), v8) )
      {
        v7 = -2147024882;
        goto LABEL_17;
      }
      v11 = v7;
      if ( !v7 )
      {
        SetEvent(EventW);
        return v7;
      }
    }
    v7 = v11;
    if ( v11 == -2147483638 )
      return 0;
    if ( v11 >= 0 )
      return v7;
LABEL_17:
    SetEvent(EventW);
    CAsyncItemHandler::QueueAsyncItem(v13, v14);
    return v7;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x1001ce70  mov     edi, edi
0x1001ce72  push    ebp
0x1001ce73  mov     ebp, esp
0x1001ce75  sub     esp, 10h
0x1001ce78  push    ebx
0x1001ce79  push    esi; struct _ASYNC_ITEM *
0x1001ce7a  push    edi; this
0x1001ce7b  xor     eax, eax
0x1001ce7d  mov     [ebp+var_4], edx
0x1001ce80  push    eax; lpName
0x1001ce81  push    eax; bInitialState
0x1001ce82  push    eax; bManualReset
0x1001ce83  mov     esi, ecx
0x1001ce85  push    eax; lpEventAttributes
0x1001ce86  mov     [ebp+var_8], esi
0x1001ce89  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001ce8f  mov     ebx, eax
0x1001ce91  test    ebx, ebx
0x1001ce93  jnz     short loc_1001CE9F
0x1001ce95  mov     esi, 80004005h
0x1001ce9a  jmp     loc_1001CFB9
0x1001ce9f  push    18h; Size
0x1001cea1  call    ??2@YAPAXI@Z; operator new(uint)
0x1001cea6  mov     edi, eax
0x1001cea8  pop     ecx
0x1001cea9  test    edi, edi
0x1001ceab  jnz     short loc_1001CEB7
0x1001cead  mov     esi, 8007000Eh
0x1001ceb2  jmp     loc_1001CFB9
0x1001ceb7  push    14h; Size
0x1001ceb9  call    ??2@YAPAXI@Z; operator new(uint)
0x1001cebe  mov     [ebp+var_C], eax
0x1001cec1  pop     ecx
0x1001cec2  test    eax, eax
0x1001cec4  jz      short loc_1001CEAD
0x1001cec6  mov     [eax+0Ch], ebx
0x1001cec9  lea     eax, [esi+110h]
0x1001cecf  mov     ecx, [eax]
0x1001ced1  push    eax
0x1001ced2  mov     esi, [ecx+34h]
0x1001ced5  mov     ecx, esi; this
0x1001ced7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001cedd  call    esi
0x1001cedf  test    _Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1001cee6  mov     esi, [ebp+var_4]
0x1001cee9  jz      short loc_1001CF09
0x1001ceeb  mov     eax, [esi+118h]
0x1001cef1  mov     edx, offset _ProcessInput_Start
0x1001cef6  mov     ecx, offset _Microsoft_Windows_DirectShow_KernelSupport_Context
0x1001cefb  push    dword ptr [eax+0Ch]
0x1001cefe  push    dword ptr [eax+8]
0x1001cf01  push    dword ptr [eax+28h]
0x1001cf04  call    _McTemplateU0pi_EventWriteTransfer@20; McTemplateU0pi_EventWriteTransfer(x,x,x,x,x)
0x1001cf09  mov     edx, [ebp+var_C]
0x1001cf0c  mov     ecx, [ebp+var_8]
0x1001cf0f  mov     eax, [ebp+this]
0x1001cf12  mov     [edx+4], eax
0x1001cf15  mov     [edx], ecx
0x1001cf17  mov     [edx+8], esi
0x1001cf1a  mov     dword ptr [edi+4], 0
0x1001cf21  mov     dword ptr [edi], 0
0x1001cf27  mov     byte ptr [edi+8], 1
0x1001cf2b  mov     [edi+0Ch], ebx
0x1001cf2e  mov     dword ptr [edi+10h], offset ?DA_PluginInputCompletionItem@CKsOutputPin2@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DA_PluginInputCompletionItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x1001cf35  mov     [edi+14h], edx
0x1001cf38  mov     ecx, [ecx+2F8h]
0x1001cf3e  mov     eax, [ecx]
0x1001cf40  mov     esi, [eax+34h]
0x1001cf43  lea     eax, [edx+0Ch]
0x1001cf46  push    eax
0x1001cf47  mov     eax, [ebp+var_4]
0x1001cf4a  push    dword ptr [eax+118h]
0x1001cf50  push    ecx
0x1001cf51  mov     ecx, esi; this
0x1001cf53  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001cf59  call    esi
0x1001cf5b  mov     esi, eax
0x1001cf5d  test    eax, eax
0x1001cf5f  jns     short loc_1001CF68
0x1001cf61  cmp     eax, 8000000Ah
0x1001cf66  jnz     short loc_1001CF91
0x1001cf68  mov     ecx, [ebp+var_8]
0x1001cf6b  push    edi; void *
0x1001cf6c  add     ecx, 2D8h; this
0x1001cf72  call    ?AddTailI@CBaseList@@IAEPAU__POSITION@@PAX@Z; CBaseList::AddTailI(void *)
0x1001cf77  test    eax, eax
0x1001cf79  jnz     short loc_1001CF82
0x1001cf7b  mov     esi, 8007000Eh
0x1001cf80  jmp     short loc_1001CFA2
0x1001cf82  mov     eax, esi
0x1001cf84  test    esi, esi
0x1001cf86  jnz     short loc_1001CF91
0x1001cf88  push    ebx; hEvent
0x1001cf89  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001cf8f  jmp     short loc_1001CFB9
0x1001cf91  mov     esi, eax
0x1001cf93  cmp     eax, 8000000Ah
0x1001cf98  jnz     short loc_1001CF9E
0x1001cf9a  xor     esi, esi
0x1001cf9c  jmp     short loc_1001CFB9
0x1001cf9e  test    esi, esi
0x1001cfa0  jns     short loc_1001CFB9
0x1001cfa2  push    ebx; hEvent
0x1001cfa3  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001cfa9  mov     eax, [ebp+var_8]
0x1001cfac  mov     edx, edi
0x1001cfae  mov     ecx, [eax+2F4h]
0x1001cfb4  call    ?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1001cfb9  pop     edi
0x1001cfba  mov     eax, esi
0x1001cfbc  pop     esi
0x1001cfbd  pop     ebx
0x1001cfbe  leave
0x1001cfbf  retn    4
```
