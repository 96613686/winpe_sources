# CKsOutputPin2::DA_QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x18002eb68`
- end: `0x18002ecdf`
- name: `?DA_QueueBuffersToPluginOutput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(CKsOutputPin2 *__hidden this, struct _KSSTREAM_SEGMENT_EX2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002e8d0`

## callees

- `0x18000df50`
- `0x18000e400`
- `0x18001f1d0`
- `0x18002eb68`
- `0x180031d5c`
- `0x180045010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002ec96`
- `KERNEL32!SetEvent` at `0x18002ecb4`
- `KERNEL32!SetEvent` at `0x18002ec96`
- `KERNEL32!SetEvent` at `0x18002ecb4`
- `KERNEL32!CreateEventW` at `0x18002eb85`
- `KERNEL32!CreateEventW` at `0x18002eb85`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::DA_QueueBuffersToPluginOutput(CKsOutputPin2 *this, struct _KSSTREAM_SEGMENT_EX2 *a2)
{
  HANDLE EventW; // rsi
  int v5; // ebx
  struct _ASYNC_ITEM *v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx

  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return (unsigned int)-2147467259;
  v6 = (struct _ASYNC_ITEM *)operator new(0x30u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v7 = operator new(0x28u);
  v8 = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v7[3] = EventW;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 48) + 104LL))((char *)this + 384);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      ProcessOutput_Start,
      *(_QWORD *)(*((_QWORD *)a2 + 69) + 40LL),
      *(_QWORD *)(*((_QWORD *)a2 + 69) + 8LL));
  *v8 = this;
  v8[1] = a2;
  v6->itemRoutine = CKsOutputPin2::DA_AppQueueItem;
  v6->link.bLink = 0;
  v6->link.fLink = 0;
  v6->remove = 1;
  v6->event = EventW;
  v6->context = v8;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 141) + 112LL))(
         *((_QWORD *)this + 141),
         *((_QWORD *)a2 + 69),
         v8 + 3);
  if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147483638 )
  {
    if ( CBaseList::AddTailI((CBaseList *)this + 18, v6) )
    {
      if ( !v5 )
      {
        SetEvent(EventW);
        return (unsigned int)v5;
      }
      if ( v5 == -2147483638 )
        return 0;
      goto LABEL_15;
    }
    return (unsigned int)-2147024882;
  }
LABEL_15:
  if ( v5 < 0 )
  {
    SetEvent(EventW);
    CAsyncItemHandler::QueueAsyncItem(*((CAsyncItemHandler **)this + 140), v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002eb68  push    rbx
0x18002eb6a  push    rbp
0x18002eb6b  push    rsi
0x18002eb6c  push    rdi
0x18002eb6d  push    r14
0x18002eb6f  push    r15
0x18002eb71  sub     rsp, 28h
0x18002eb75  mov     r14, rdx
0x18002eb78  mov     rbp, rcx
0x18002eb7b  xor     edx, edx; bManualReset
0x18002eb7d  xor     ecx, ecx; lpEventAttributes
0x18002eb7f  xor     r9d, r9d; lpName
0x18002eb82  xor     r8d, r8d; bInitialState
0x18002eb85  call    cs:__imp_CreateEventW
0x18002eb8c  nop     dword ptr [rax+rax+00h]
0x18002eb91  mov     rsi, rax
0x18002eb94  test    rax, rax
0x18002eb97  jnz     short loc_18002EBA3
0x18002eb99  mov     ebx, 80004005h
0x18002eb9e  jmp     loc_18002ECCF
0x18002eba3  mov     ecx, 30h ; '0'; Size
0x18002eba8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ebad  mov     rdi, rax
0x18002ebb0  test    rax, rax
0x18002ebb3  jnz     short loc_18002EBBF
0x18002ebb5  mov     ebx, 8007000Eh
0x18002ebba  jmp     loc_18002ECCF
0x18002ebbf  mov     ecx, 28h ; '('; Size
0x18002ebc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ebc9  mov     rbx, rax
0x18002ebcc  test    rax, rax
0x18002ebcf  jz      short loc_18002EBB5
0x18002ebd1  mov     [rax+18h], rsi
0x18002ebd5  lea     rcx, [rbp+180h]
0x18002ebdc  mov     rax, [rcx]
0x18002ebdf  mov     rax, [rax+68h]
0x18002ebe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebe8  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x18002ebef  jz      short loc_18002EC13
0x18002ebf1  mov     r8, [r14+228h]
0x18002ebf8  lea     rdx, ProcessOutput_Start
0x18002ebff  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x18002ec06  mov     r9, [r8+8]
0x18002ec0a  mov     r8, [r8+28h]
0x18002ec0e  call    McTemplateU0pi_EventWriteTransfer
0x18002ec13  mov     [rbx], rbp
0x18002ec16  lea     rax, ?DA_AppQueueItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin2::DA_AppQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18002ec1d  mov     [rbx+8], r14
0x18002ec21  lea     r8, [rbx+18h]
0x18002ec25  mov     [rdi+20h], rax
0x18002ec29  mov     qword ptr [rdi+8], 0
0x18002ec31  mov     qword ptr [rdi], 0
0x18002ec38  mov     byte ptr [rdi+10h], 1
0x18002ec3c  mov     [rdi+18h], rsi
0x18002ec40  mov     [rdi+28h], rbx
0x18002ec44  mov     rcx, [rbp+468h]
0x18002ec4b  mov     rdx, [r14+228h]
0x18002ec52  mov     rax, [rcx]
0x18002ec55  mov     rax, [rax+70h]
0x18002ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5e  mov     ebx, eax
0x18002ec60  mov     r14d, 8000000Ah
0x18002ec66  mov     eax, 80000000h
0x18002ec6b  lea     ecx, [rbx+rax]
0x18002ec6e  test    eax, ecx
0x18002ec70  jnz     short loc_18002EC77
0x18002ec72  cmp     ebx, r14d
0x18002ec75  jnz     short loc_18002ECAD
0x18002ec77  lea     rcx, [rbp+2D0h]; this
0x18002ec7e  mov     rdx, rdi; void *
0x18002ec81  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18002ec86  test    rax, rax
0x18002ec89  jz      loc_18002EBB5
0x18002ec8f  test    ebx, ebx
0x18002ec91  jnz     short loc_18002ECA4
0x18002ec93  mov     rcx, rsi; hEvent
0x18002ec96  call    cs:__imp_SetEvent
0x18002ec9d  nop     dword ptr [rax+rax+00h]
0x18002eca2  jmp     short loc_18002ECCF
0x18002eca4  cmp     ebx, r14d
0x18002eca7  jnz     short loc_18002ECAD
0x18002eca9  xor     ebx, ebx
0x18002ecab  jmp     short loc_18002ECCF
0x18002ecad  test    ebx, ebx
0x18002ecaf  jns     short loc_18002ECCF
0x18002ecb1  mov     rcx, rsi; hEvent
0x18002ecb4  call    cs:__imp_SetEvent
0x18002ecbb  nop     dword ptr [rax+rax+00h]
0x18002ecc0  mov     rcx, [rbp+460h]; this
0x18002ecc7  mov     rdx, rdi; struct _ASYNC_ITEM *
0x18002ecca  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18002eccf  mov     eax, ebx
0x18002ecd1  add     rsp, 28h
0x18002ecd5  pop     r15
0x18002ecd7  pop     r14
0x18002ecd9  pop     rdi
0x18002ecda  pop     rsi
0x18002ecdb  pop     rbp
0x18002ecdc  pop     rbx
0x18002ecdd  retn
```
