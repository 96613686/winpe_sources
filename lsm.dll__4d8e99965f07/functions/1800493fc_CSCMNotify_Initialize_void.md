# CSCMNotify::Initialize(void)

- ea: `0x1800493fc`
- end: `0x18004951f`
- name: `?Initialize@CSCMNotify@@AEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002cf00`

## callees

- `0x1800077a0`
- `0x180016740`
- `0x1800493fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004945e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004945e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800494ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800494ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049505`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180049505`

## string_xrefs

- `0x180049498`: `CreateEvent on NotificationInQueue failed: 0x%x in %s`
- `0x1800494e8`: `QueueUserWorkItem on staticSCMNotificationThread failed: 0x%x in %s`

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
0x1800493fc  mov     [rsp+arg_0], rbx
0x180049401  push    rdi
0x180049402  sub     rsp, 20h
0x180049406  mov     qword ptr [rcx+6B0h], 0
0x180049411  lea     rax, [rcx+6A0h]
0x180049418  mov     rdi, rcx
0x18004941b  mov     [rax+8], rax
0x18004941f  add     rcx, 638h; this
0x180049426  mov     [rax], rax
0x180049429  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18004942e  mov     ebx, eax
0x180049430  test    eax, eax
0x180049432  jns     short loc_180049454
0x180049434  mov     r8d, eax
0x180049437  lea     rdx, aNotificationli; "NotificationListLock->Initialize failed"...
0x18004943e  lea     r9, aCscmnotifyInit; "CSCMNotify::Initialize"
0x180049445  mov     ecx, 8; int
0x18004944a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004944f  jmp     loc_180049511
0x180049454  xor     r9d, r9d; lpName
0x180049457  xor     r8d, r8d; bInitialState
0x18004945a  xor     edx, edx; bManualReset
0x18004945c  xor     ecx, ecx; lpEventAttributes
0x18004945e  call    cs:__imp_CreateEventW
0x180049465  nop     dword ptr [rax+rax+00h]
0x18004946a  mov     [rdi+6B0h], rax
0x180049471  test    rax, rax
0x180049474  jnz     short loc_1800494A1
0x180049476  call    cs:__imp_GetLastError
0x18004947d  nop     dword ptr [rax+rax+00h]
0x180049482  mov     ebx, eax
0x180049484  test    eax, eax
0x180049486  jle     short loc_180049491
0x180049488  movzx   ebx, ax
0x18004948b  or      ebx, 80070000h
0x180049491  test    ebx, ebx
0x180049493  jns     short loc_1800494A1
0x180049495  mov     r8d, ebx
0x180049498  lea     rdx, aCreateeventOnN; "CreateEvent on NotificationInQueue fail"...
0x18004949f  jmp     short loc_18004943E
0x1800494a1  xor     r8d, r8d; pcbe
0x1800494a4  lea     rcx, ?staticSCMNotificationThread@CSCMNotify@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800494ab  mov     rdx, rdi; pv
0x1800494ae  call    cs:__imp_CreateThreadpoolWait
0x1800494b5  nop     dword ptr [rax+rax+00h]
0x1800494ba  mov     [rdi+6B8h], rax
0x1800494c1  test    rax, rax
0x1800494c4  jnz     short loc_1800494F4
0x1800494c6  call    cs:__imp_GetLastError
0x1800494cd  nop     dword ptr [rax+rax+00h]
0x1800494d2  mov     ebx, eax
0x1800494d4  test    eax, eax
0x1800494d6  jle     short loc_1800494E1
0x1800494d8  movzx   ebx, ax
0x1800494db  or      ebx, 80070000h
0x1800494e1  test    ebx, ebx
0x1800494e3  jns     short loc_1800494F4
0x1800494e5  mov     r8d, ebx
0x1800494e8  lea     rdx, aQueueuserworki; "QueueUserWorkItem on staticSCMNotificat"...
0x1800494ef  jmp     loc_18004943E
0x1800494f4  mov     rdx, [rdi+6B0h]; h
0x1800494fb  xor     r8d, r8d; pftTimeout
0x1800494fe  mov     rcx, [rdi+6B8h]; pwa
0x180049505  call    cs:__imp_SetThreadpoolWait
0x18004950c  nop     dword ptr [rax+rax+00h]
0x180049511  mov     eax, ebx
0x180049513  mov     rbx, [rsp+28h+arg_0]
0x180049518  add     rsp, 20h
0x18004951c  pop     rdi
0x18004951d  retn
```
