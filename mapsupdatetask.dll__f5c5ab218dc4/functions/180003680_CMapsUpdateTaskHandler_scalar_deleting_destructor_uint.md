# CMapsUpdateTaskHandler::`scalar deleting destructor'(uint)

- ea: `0x180003680`
- end: `0x1800036e5`
- name: `??_GCMapsUpdateTaskHandler@@UEAAPEAXI@Z`
- size: `101`
- prototype: `CMapsUpdateTaskHandler *__fastcall(CMapsUpdateTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001ff4`
- `0x180003380`
- `0x180003680`
- `0x1800075e4`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800036ab`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800036ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003698`

## pseudocode

```c
CMapsUpdateTaskHandler *__fastcall CMapsUpdateTaskHandler::`scalar deleting destructor'(
        CMapsUpdateTaskHandler *this,
        char a2)
{
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v7);
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003680  mov     [rsp+arg_0], rbx
0x180003685  push    rdi
0x180003686  sub     rsp, 20h
0x18000368a  mov     rbx, rcx
0x18000368d  mov     edi, edx
0x18000368f  mov     rcx, [rcx+60h]; hObject
0x180003693  test    rcx, rcx
0x180003696  jz      short loc_1800036A2
0x180003698  call    cs:__imp_CloseHandle
0x18000369e  test    eax, eax
0x1800036a0  jz      short loc_1800036D5
0x1800036a2  mov     rcx, [rbx+38h]
0x1800036a6  test    rcx, rcx
0x1800036a9  jz      short loc_1800036B1
0x1800036ab  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800036b1  mov     rcx, rbx; this
0x1800036b4  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800036b9  test    dil, 1
0x1800036bd  jz      short loc_1800036C7
0x1800036bf  mov     rcx, rbx; Block
0x1800036c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036c7  mov     rax, rbx
0x1800036ca  mov     rbx, [rsp+28h+arg_0]
0x1800036cf  add     rsp, 20h
0x1800036d3  pop     rdi
0x1800036d4  retn
0x1800036d5  mov     rcx, [rsp+28h]; this
0x1800036da  mov     edx, 0A0Bh; void *
0x1800036df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
