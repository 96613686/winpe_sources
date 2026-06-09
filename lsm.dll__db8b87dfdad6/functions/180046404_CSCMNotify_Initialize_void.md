# CSCMNotify::Initialize(void)

- ea: `0x180046404`
- end: `0x180046508`
- name: `?Initialize@CSCMNotify@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002ae4c`

## callees

- `0x1800074c0`
- `0x18001288c`
- `0x180046404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046466`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800464aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800464aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800464f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800464f5`

## string_xrefs

- `0x180046494`: `CreateEvent on NotificationInQueue failed: 0x%x in %s`
- `0x1800464d8`: `QueueUserWorkItem on staticSCMNotificationThread failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSCMNotify::Initialize(char *pv)
{
  int v2; // eax
  signed int v3; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  signed int v7; // eax

  *((_QWORD *)pv + 214) = 0;
  *((_QWORD *)pv + 213) = pv + 1696;
  *((_QWORD *)pv + 212) = pv + 1696;
  v2 = CResource::Initialize((CResource *)(pv + 1592));
  v3 = v2;
  if ( v2 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)pv + 214) = EventW;
    if ( EventW )
      goto LABEL_9;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_9:
      ThreadpoolWait = CreateThreadpoolWait(CSCMNotify::staticSCMNotificationThread, pv, 0);
      *((_QWORD *)pv + 215) = ThreadpoolWait;
      if ( ThreadpoolWait )
        goto LABEL_14;
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 >= 0 )
LABEL_14:
        SetThreadpoolWait(*((PTP_WAIT *)pv + 215), *((HANDLE *)pv + 214), 0);
      else
        _DbgPrintMessage(
          8,
          "QueueUserWorkItem on staticSCMNotificationThread failed: 0x%x in %s",
          (unsigned int)v3,
          "CSCMNotify::Initialize");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CreateEvent on NotificationInQueue failed: 0x%x in %s",
        (unsigned int)v3,
        "CSCMNotify::Initialize");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "NotificationListLock->Initialize failed: 0x%x in %s",
      (unsigned int)v2,
      "CSCMNotify::Initialize");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180046404  mov     [rsp+arg_0], rbx
0x180046409  push    rdi
0x18004640a  sub     rsp, 20h
0x18004640e  mov     qword ptr [rcx+6B0h], 0
0x180046419  lea     rax, [rcx+6A0h]
0x180046420  mov     rdi, rcx
0x180046423  mov     [rax+8], rax
0x180046427  add     rcx, 638h; this
0x18004642e  mov     [rax], rax
0x180046431  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x180046436  mov     ebx, eax
0x180046438  test    eax, eax
0x18004643a  jns     short loc_18004645C
0x18004643c  mov     r8d, eax
0x18004643f  lea     rdx, aNotificationli; "NotificationListLock->Initialize failed"...
0x180046446  lea     r9, aCscmnotifyInit; "CSCMNotify::Initialize"
0x18004644d  mov     ecx, 8; int
0x180046452  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180046457  jmp     loc_1800464FB
0x18004645c  xor     r9d, r9d; lpName
0x18004645f  xor     r8d, r8d; bInitialState
0x180046462  xor     edx, edx; bManualReset
0x180046464  xor     ecx, ecx; lpEventAttributes
0x180046466  call    cs:__imp_CreateEventW
0x18004646c  mov     [rdi+6B0h], rax
0x180046473  test    rax, rax
0x180046476  jnz     short loc_18004649D
0x180046478  call    cs:__imp_GetLastError
0x18004647e  mov     ebx, eax
0x180046480  test    eax, eax
0x180046482  jle     short loc_18004648D
0x180046484  movzx   ebx, ax
0x180046487  or      ebx, 80070000h
0x18004648d  test    ebx, ebx
0x18004648f  jns     short loc_18004649D
0x180046491  mov     r8d, ebx
0x180046494  lea     rdx, aCreateeventOnN; "CreateEvent on NotificationInQueue fail"...
0x18004649b  jmp     short loc_180046446
0x18004649d  xor     r8d, r8d; pcbe
0x1800464a0  lea     rcx, ?staticSCMNotificationThread@CSCMNotify@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800464a7  mov     rdx, rdi; pv
0x1800464aa  call    cs:__imp_CreateThreadpoolWait
0x1800464b0  mov     [rdi+6B8h], rax
0x1800464b7  test    rax, rax
0x1800464ba  jnz     short loc_1800464E4
0x1800464bc  call    cs:__imp_GetLastError
0x1800464c2  mov     ebx, eax
0x1800464c4  test    eax, eax
0x1800464c6  jle     short loc_1800464D1
0x1800464c8  movzx   ebx, ax
0x1800464cb  or      ebx, 80070000h
0x1800464d1  test    ebx, ebx
0x1800464d3  jns     short loc_1800464E4
0x1800464d5  mov     r8d, ebx
0x1800464d8  lea     rdx, aQueueuserworki; "QueueUserWorkItem on staticSCMNotificat"...
0x1800464df  jmp     loc_180046446
0x1800464e4  mov     rdx, [rdi+6B0h]; h
0x1800464eb  xor     r8d, r8d; pftTimeout
0x1800464ee  mov     rcx, [rdi+6B8h]; pwa
0x1800464f5  call    cs:__imp_SetThreadpoolWait
0x1800464fb  mov     eax, ebx
0x1800464fd  mov     rbx, [rsp+28h+arg_0]
0x180046502  add     rsp, 20h
0x180046506  pop     rdi
0x180046507  retn
```
