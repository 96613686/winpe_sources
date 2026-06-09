# CService::SetTermSrvReadyEvent(void)

- ea: `0x180047508`
- end: `0x1800475a4`
- name: `?SetTermSrvReadyEvent@CService@@IEAAJXZ`
- size: `156`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002ae4c`

## callees

- `0x1800074c0`
- `0x180047508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004751d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004751d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004755a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004755a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004752c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004752c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047564`

## string_xrefs

- `0x180047510`: `Global\TermSrvReadyEvent`
- `0x180047544`: `OpenEvent( Global\TermSrvReadyEvent ): 0x%x`
- `0x18004757d`: `CService::SetTermSrvReadyEvent`
- `0x180047587`: `SetEvent( Global\TermSrvReadyEvent ) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CService::SetTermSrvReadyEvent(CService *this)
{
  HANDLE v2; // rax
  signed int v3; // eax
  signed int v4; // ebx
  signed int LastError; // eax

  v2 = OpenEventW(2u, 0, L"Global\\TermSrvReadyEvent");
  *((_QWORD *)this + 9) = v2;
  if ( v2 )
  {
    if ( SetEvent(v2) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
        _DbgPrintMessage(
          8,
          "SetEvent( Global\\TermSrvReadyEvent ) failed: 0x%x in %s",
          v4,
          "CService::SetTermSrvReadyEvent");
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    _DbgPrintMessage(8, "OpenEvent( Global\\TermSrvReadyEvent ): 0x%x", v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047508  push    rbx
0x18004750a  sub     rsp, 20h
0x18004750e  xor     edx, edx; bInheritHandle
0x180047510  lea     r8, aGlobalTermsrvr; "Global\\TermSrvReadyEvent"
0x180047517  mov     rbx, rcx
0x18004751a  lea     ecx, [rdx+2]; dwDesiredAccess
0x18004751d  call    cs:__imp_OpenEventW
0x180047523  mov     [rbx+48h], rax
0x180047527  test    rax, rax
0x18004752a  jnz     short loc_180047557
0x18004752c  call    cs:__imp_GetLastError
0x180047532  mov     ebx, eax
0x180047534  test    eax, eax
0x180047536  jle     short loc_180047541
0x180047538  movzx   ebx, ax
0x18004753b  or      ebx, 80070000h
0x180047541  mov     r8d, ebx
0x180047544  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ):"...
0x18004754b  mov     ecx, 8; int
0x180047550  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180047555  jmp     short loc_18004759C
0x180047557  mov     rcx, rax; hEvent
0x18004755a  call    cs:__imp_SetEvent
0x180047560  test    eax, eax
0x180047562  jnz     short loc_18004759A
0x180047564  call    cs:__imp_GetLastError
0x18004756a  mov     ebx, eax
0x18004756c  test    eax, eax
0x18004756e  jle     short loc_180047579
0x180047570  movzx   ebx, ax
0x180047573  or      ebx, 80070000h
0x180047579  test    ebx, ebx
0x18004757b  jns     short loc_18004759C
0x18004757d  lea     r9, aCserviceSetter; "CService::SetTermSrvReadyEvent"
0x180047584  mov     r8d, ebx
0x180047587  lea     rdx, aSeteventGlobal; "SetEvent( Global\\TermSrvReadyEvent ) f"...
0x18004758e  mov     ecx, 8; int
0x180047593  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180047598  jmp     short loc_18004759C
0x18004759a  xor     ebx, ebx
0x18004759c  mov     eax, ebx
0x18004759e  add     rsp, 20h
0x1800475a2  pop     rbx
0x1800475a3  retn
```
