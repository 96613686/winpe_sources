# CKsOutputPin2::DA_QueueBuffersToPluginInput(_KSSTREAM_SEGMENT_EX2 *,_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x18002e9dc`
- end: `0x18002eb60`
- name: `?DA_QueueBuffersToPluginInput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@0@Z`
- size: `388`
- prototype: `__int64 __fastcall(CKsOutputPin2 *__hidden this, struct _KSSTREAM_SEGMENT_EX2 *, struct _KSSTREAM_SEGMENT_EX2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002e750`

## callees

- `0x18000df50`
- `0x18000e400`
- `0x18001f1d0`
- `0x18002e9dc`
- `0x180031d5c`
- `0x180045010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002eb15`
- `KERNEL32!SetEvent` at `0x18002eb33`
- `KERNEL32!SetEvent` at `0x18002eb15`
- `KERNEL32!SetEvent` at `0x18002eb33`
- `KERNEL32!CreateEventW` at `0x18002e9fe`
- `KERNEL32!CreateEventW` at `0x18002e9fe`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::DA_QueueBuffersToPluginInput(
        CKsOutputPin2 *this,
        struct _KSSTREAM_SEGMENT_EX2 *a2,
        struct _KSSTREAM_SEGMENT_EX2 *a3)
{
  HANDLE EventW; // rsi
  unsigned int v7; // ebx
  struct _ASYNC_ITEM *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v8 = (struct _ASYNC_ITEM *)operator new(0x30u);
    if ( !v8 )
      return (unsigned int)-2147024882;
    v9 = operator new(0x28u);
    v10 = v9;
    if ( !v9 )
      return (unsigned int)-2147024882;
    v9[3] = EventW;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 48) + 104LL))((char *)this + 384);
    if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
      McTemplateU0pi_EventWriteTransfer(
        &Microsoft_Windows_DirectShow_KernelSupport_Context,
        ProcessInput_Start,
        *(_QWORD *)(*((_QWORD *)a2 + 69) + 40LL),
        *(_QWORD *)(*((_QWORD *)a2 + 69) + 8LL));
    *v10 = this;
    v10[2] = a2;
    v10[1] = a3;
    v8->itemRoutine = CKsOutputPin2::DA_PluginInputCompletionItem;
    v8->link.bLink = 0;
    v8->link.fLink = 0;
    v8->remove = 1;
    v8->event = EventW;
    v8->context = v10;
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 141) + 104LL))(
           *((_QWORD *)this + 141),
           *((_QWORD *)a2 + 69),
           v10 + 3);
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147483638 )
    {
      if ( !CBaseList::AddTailI((CBaseList *)((char *)this + 1072), v8) )
      {
        v7 = -2147024882;
        goto LABEL_17;
      }
      if ( !v7 )
      {
        SetEvent(EventW);
        return v7;
      }
      if ( v7 == -2147483638 )
        return 0;
    }
    if ( (v7 & 0x80000000) == 0 )
      return v7;
LABEL_17:
    SetEvent(EventW);
    CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)this + 140), v8);
    return v7;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18002e9dc  push    rbx
0x18002e9de  push    rbp
0x18002e9df  push    rsi
0x18002e9e0  push    rdi
0x18002e9e1  push    r12
0x18002e9e3  push    r14
0x18002e9e5  push    r15
0x18002e9e7  sub     rsp, 20h
0x18002e9eb  mov     r12, r8
0x18002e9ee  mov     r14, rdx
0x18002e9f1  mov     rbp, rcx
0x18002e9f4  xor     r8d, r8d; bInitialState
0x18002e9f7  xor     edx, edx; bManualReset
0x18002e9f9  xor     ecx, ecx; lpEventAttributes
0x18002e9fb  xor     r9d, r9d; lpName
0x18002e9fe  call    cs:__imp_CreateEventW
0x18002ea05  nop     dword ptr [rax+rax+00h]
0x18002ea0a  mov     rsi, rax
0x18002ea0d  test    rax, rax
0x18002ea10  jnz     short loc_18002EA1C
0x18002ea12  mov     ebx, 80004005h
0x18002ea17  jmp     loc_18002EB4E
0x18002ea1c  mov     ecx, 30h ; '0'; Size
0x18002ea21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ea26  mov     rdi, rax
0x18002ea29  test    rax, rax
0x18002ea2c  jnz     short loc_18002EA38
0x18002ea2e  mov     ebx, 8007000Eh
0x18002ea33  jmp     loc_18002EB4E
0x18002ea38  mov     ecx, 28h ; '('; Size
0x18002ea3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ea42  mov     rbx, rax
0x18002ea45  test    rax, rax
0x18002ea48  jz      short loc_18002EA2E
0x18002ea4a  mov     [rax+18h], rsi
0x18002ea4e  lea     rcx, [rbp+180h]
0x18002ea55  mov     rax, [rcx]
0x18002ea58  mov     rax, [rax+68h]
0x18002ea5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea61  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x18002ea68  jz      short loc_18002EA8C
0x18002ea6a  mov     r8, [r14+228h]
0x18002ea71  lea     rdx, ProcessInput_Start
0x18002ea78  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x18002ea7f  mov     r9, [r8+8]
0x18002ea83  mov     r8, [r8+28h]
0x18002ea87  call    McTemplateU0pi_EventWriteTransfer
0x18002ea8c  mov     [rbx], rbp
0x18002ea8f  lea     rax, ?DA_PluginInputCompletionItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DA_PluginInputCompletionItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18002ea96  mov     [rbx+10h], r14
0x18002ea9a  lea     r8, [rbx+18h]
0x18002ea9e  mov     [rbx+8], r12
0x18002eaa2  mov     [rdi+20h], rax
0x18002eaa6  mov     qword ptr [rdi+8], 0
0x18002eaae  mov     qword ptr [rdi], 0
0x18002eab5  mov     byte ptr [rdi+10h], 1
0x18002eab9  mov     [rdi+18h], rsi
0x18002eabd  mov     [rdi+28h], rbx
0x18002eac1  mov     rcx, [rbp+468h]
0x18002eac8  mov     rdx, [r14+228h]
0x18002eacf  mov     rax, [rcx]
0x18002ead2  mov     rax, [rax+68h]
0x18002ead6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eadb  mov     ecx, 80000000h
0x18002eae0  mov     ebx, eax
0x18002eae2  add     eax, ecx
0x18002eae4  mov     r14d, 8000000Ah
0x18002eaea  test    ecx, eax
0x18002eaec  jnz     short loc_18002EAF3
0x18002eaee  cmp     ebx, r14d
0x18002eaf1  jnz     short loc_18002EB2C
0x18002eaf3  lea     rcx, [rbp+430h]; this
0x18002eafa  mov     rdx, rdi; void *
0x18002eafd  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18002eb02  test    rax, rax
0x18002eb05  jnz     short loc_18002EB0E
0x18002eb07  mov     ebx, 8007000Eh
0x18002eb0c  jmp     short loc_18002EB30
0x18002eb0e  test    ebx, ebx
0x18002eb10  jnz     short loc_18002EB23
0x18002eb12  mov     rcx, rsi; hEvent
0x18002eb15  call    cs:__imp_SetEvent
0x18002eb1c  nop     dword ptr [rax+rax+00h]
0x18002eb21  jmp     short loc_18002EB4E
0x18002eb23  cmp     ebx, r14d
0x18002eb26  jnz     short loc_18002EB2C
0x18002eb28  xor     ebx, ebx
0x18002eb2a  jmp     short loc_18002EB4E
0x18002eb2c  test    ebx, ebx
0x18002eb2e  jns     short loc_18002EB4E
0x18002eb30  mov     rcx, rsi; hEvent
0x18002eb33  call    cs:__imp_SetEvent
0x18002eb3a  nop     dword ptr [rax+rax+00h]
0x18002eb3f  mov     rcx, [rbp+460h]; this
0x18002eb46  mov     rdx, rdi; struct _ASYNC_ITEM *
0x18002eb49  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002eb4e  mov     eax, ebx
0x18002eb50  add     rsp, 20h
0x18002eb54  pop     r15
0x18002eb56  pop     r14
0x18002eb58  pop     r12
0x18002eb5a  pop     rdi
0x18002eb5b  pop     rsi
0x18002eb5c  pop     rbp
0x18002eb5d  pop     rbx
0x18002eb5e  retn
```
