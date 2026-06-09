# NOTIFICATION_THREAD::ThreadProc(void *)

- ea: `0x180051510`
- end: `0x1800516ae`
- name: `?ThreadProc@NOTIFICATION_THREAD@@CAKPEAX@Z`
- size: `414`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18004f600`
- `0x180050c44`
- `0x180050d98`
- `0x180050f6c`
- `0x18005102c`
- `0x180051190`
- `0x180051510`
- `0x1800516b4`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180051587`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180051587`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800515a7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005162d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180051665`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800515a7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18005162d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180051665`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051616`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051646`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051698`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051616`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051646`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180051698`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_THREAD::ThreadProc(PVOID Parameter)
{
  void *v3; // rcx
  BOOL QueuedCompletionStatus; // ebx
  __int64 *p_hEvent; // rdi
  NOTIFICATION_THREAD *v6; // rcx
  char IsSchemaMonitor; // al
  int v8; // ebx
  NOTIFICATION_THREAD *v9; // rcx
  bool v10; // zf
  int v11; // ebx
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+8h] BYREF
  int v13; // [rsp+88h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+98h] [rbp+20h] BYREF

  CompletionKey = 0;
  v13 = 0;
  if ( !Parameter )
    return 87;
  while ( !*((_DWORD *)Parameter + 14) || *((int *)Parameter + 15) > 0 )
  {
    v3 = (void *)*((_QWORD *)Parameter + 6);
    NumberOfBytesTransferred = 0;
    Overlapped = 0;
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               v3,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               0xFFFFFFFF);
    if ( Overlapped )
    {
      p_hEvent = (__int64 *)&Overlapped[-2].hEvent;
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&Overlapped[1].16);
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
      {
        IsSchemaMonitor = CONFIG_MONITOR::IsSchemaMonitor((CONFIG_MONITOR *)p_hEvent);
        McTemplateU0pzzzttt_EtwEventWriteTransfer(
          p_hEvent[3] == -1,
          (unsigned int)NATIVERD_EVENT_FILE_CHANGE_NOTIFICATION_MONITOR_ALERTED,
          (_DWORD)p_hEvent,
          *p_hEvent,
          p_hEvent[1],
          p_hEvent[2],
          *((_DWORD *)p_hEvent + 19),
          p_hEvent[3] == -1,
          IsSchemaMonitor);
      }
      if ( !QueuedCompletionStatus || *((_DWORD *)p_hEvent + 21) )
      {
LABEL_17:
        NOTIFICATION_THREAD::FreeMonitor((NOTIFICATION_THREAD *)Parameter, (struct CONFIG_MONITOR *)p_hEvent);
      }
      else
      {
        if ( NumberOfBytesTransferred )
        {
          if ( !NOTIFICATION_THREAD::ConfigFileChanged(v6, (struct CONFIG_MONITOR *)p_hEvent) )
            goto LABEL_16;
          CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(p_hEvent + 11));
          v11 = CONFIG_CACHE::HandleChangeNotification(
                  *((CONFIG_CACHE **)Parameter + 4),
                  (struct CONFIG_MONITOR *)p_hEvent,
                  &v13);
          CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(p_hEvent + 11));
          if ( v11 < 0 )
            goto LABEL_17;
          v10 = v13 == 0;
        }
        else
        {
          CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(p_hEvent + 11));
          v8 = NOTIFICATION_THREAD::ConfigFileChanged(
                 (struct CONFIG_MONITOR *)p_hEvent,
                 *((struct CONFIG_CACHE **)Parameter + 4));
          CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(p_hEvent + 11));
          v10 = v8 == 0;
        }
        if ( !v10 )
          goto LABEL_17;
LABEL_16:
        if ( NOTIFICATION_THREAD::ReadDirectoryChanges(v9, (struct CONFIG_MONITOR *)p_hEvent) < 0 )
          goto LABEL_17;
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(p_hEvent + 11));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180051510  mov     rax, rsp
0x180051513  push    rbx
0x180051514  push    rbp
0x180051515  push    rsi
0x180051516  push    rdi
0x180051517  sub     rsp, 58h
0x18005151b  mov     qword ptr [rax+20h], 0
0x180051523  mov     rsi, rcx
0x180051526  mov     dword ptr [rax+10h], 0
0x18005152d  test    rcx, rcx
0x180051530  jnz     short loc_18005153A
0x180051532  lea     eax, [rcx+57h]
0x180051535  jmp     loc_1800516A5
0x18005153a  mov     eax, [rsi+38h]
0x18005153d  test    eax, eax
0x18005153f  jz      short loc_18005154C
0x180051541  mov     eax, [rsi+3Ch]
0x180051544  test    eax, eax
0x180051546  jle     loc_1800516A3
0x18005154c  mov     rcx, [rsi+30h]; CompletionPort
0x180051550  lea     r9, [rsp+78h+Overlapped]; lpOverlapped
0x180051558  lea     r8, [rsp+78h+CompletionKey]; lpCompletionKey
0x180051560  mov     [rsp+78h+NumberOfBytesTransferred], 0
0x18005156b  lea     rdx, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180051573  mov     [rsp+78h+Overlapped], 0
0x18005157f  mov     [rsp+78h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180051587  call    cs:__imp_GetQueuedCompletionStatus
0x18005158d  mov     rdi, [rsp+78h+Overlapped]
0x180051595  mov     ebx, eax
0x180051597  test    rdi, rdi
0x18005159a  jz      short loc_18005153A
0x18005159c  add     rdi, 0FFFFFFFFFFFFFFD8h
0x1800515a0  lea     rbp, [rdi+58h]
0x1800515a4  mov     rcx, rbp
0x1800515a7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800515ad  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x1800515b4  jz      short loc_1800515FB
0x1800515b6  mov     rcx, rdi; this
0x1800515b9  call    ?IsSchemaMonitor@CONFIG_MONITOR@@QEAAHXZ; CONFIG_MONITOR::IsSchemaMonitor(void)
0x1800515be  mov     r9, [rdi]
0x1800515c1  lea     rdx, NATIVERD_EVENT_FILE_CHANGE_NOTIFICATION_MONITOR_ALERTED
0x1800515c8  mov     [rsp+78h+var_38], eax
0x1800515cc  xor     ecx, ecx
0x1800515ce  mov     eax, [rdi+4Ch]
0x1800515d1  mov     r8, rdi
0x1800515d4  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800515d9  setz    cl
0x1800515dc  mov     [rsp+78h+var_40], ecx
0x1800515e0  mov     [rsp+78h+var_48], eax
0x1800515e4  mov     rax, [rdi+10h]
0x1800515e8  mov     [rsp+78h+var_50], rax
0x1800515ed  mov     rax, [rdi+8]
0x1800515f1  mov     qword ptr [rsp+78h+dwMilliseconds], rax
0x1800515f6  call    McTemplateU0pzzzttt_EtwEventWriteTransfer
0x1800515fb  test    ebx, ebx
0x1800515fd  jz      loc_180051685
0x180051603  mov     eax, [rdi+54h]
0x180051606  test    eax, eax
0x180051608  jnz     short loc_180051685
0x18005160a  cmp     [rsp+78h+NumberOfBytesTransferred], eax
0x180051611  jnz     short loc_180051637
0x180051613  mov     rcx, rbp
0x180051616  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18005161c  mov     rdx, [rsi+20h]; struct CONFIG_CACHE *
0x180051620  mov     rcx, rdi; struct CONFIG_MONITOR *
0x180051623  call    ?ConfigFileChanged@NOTIFICATION_THREAD@@CAHPEAUCONFIG_MONITOR@@PEAVCONFIG_CACHE@@@Z; NOTIFICATION_THREAD::ConfigFileChanged(CONFIG_MONITOR *,CONFIG_CACHE *)
0x180051628  mov     rcx, rbp
0x18005162b  mov     ebx, eax
0x18005162d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180051633  test    ebx, ebx
0x180051635  jmp     short loc_180051677
0x180051637  mov     rdx, rdi; struct CONFIG_MONITOR *
0x18005163a  call    ?ConfigFileChanged@NOTIFICATION_THREAD@@AEAAHPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::ConfigFileChanged(CONFIG_MONITOR *)
0x18005163f  test    eax, eax
0x180051641  jz      short loc_180051679
0x180051643  mov     rcx, rbp
0x180051646  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18005164c  mov     rcx, [rsi+20h]; this
0x180051650  lea     r8, [rsp+78h+arg_8]; int *
0x180051658  mov     rdx, rdi; struct CONFIG_MONITOR *
0x18005165b  call    ?HandleChangeNotification@CONFIG_CACHE@@QEAAJPEAUCONFIG_MONITOR@@PEAH@Z; CONFIG_CACHE::HandleChangeNotification(CONFIG_MONITOR *,int *)
0x180051660  mov     rcx, rbp
0x180051663  mov     ebx, eax
0x180051665  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18005166b  test    ebx, ebx
0x18005166d  js      short loc_180051685
0x18005166f  cmp     [rsp+78h+arg_8], 0
0x180051677  jnz     short loc_180051685
0x180051679  mov     rdx, rdi; struct CONFIG_MONITOR *
0x18005167c  call    ?ReadDirectoryChanges@NOTIFICATION_THREAD@@AEAAJPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::ReadDirectoryChanges(CONFIG_MONITOR *)
0x180051681  test    eax, eax
0x180051683  jns     short loc_180051695
0x180051685  mov     rdx, rdi; struct CONFIG_MONITOR *
0x180051688  mov     rcx, rsi; this
0x18005168b  call    ?FreeMonitor@NOTIFICATION_THREAD@@QEAAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::FreeMonitor(CONFIG_MONITOR *)
0x180051690  jmp     loc_18005153A
0x180051695  mov     rcx, rbp
0x180051698  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18005169e  jmp     loc_18005153A
0x1800516a3  xor     eax, eax
0x1800516a5  add     rsp, 58h
0x1800516a9  pop     rdi
0x1800516aa  pop     rsi
0x1800516ab  pop     rbp
0x1800516ac  pop     rbx
0x1800516ad  retn
```
