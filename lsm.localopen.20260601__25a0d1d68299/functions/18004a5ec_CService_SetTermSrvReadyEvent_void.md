# CService::SetTermSrvReadyEvent(void)

- ea: `0x18004a5ec`
- end: `0x18004a6a1`
- name: `?SetTermSrvReadyEvent@CService@@IEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002cf00`

## callees

- `0x1800077a0`
- `0x18004a5ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004a601`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004a601`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a64a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a64a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a65a`

## string_xrefs

- `0x18004a5f4`: `Global\TermSrvReadyEvent`
- `0x18004a634`: `OpenEvent( Global\TermSrvReadyEvent ): 0x%x`
- `0x18004a679`: `CService::SetTermSrvReadyEvent`
- `0x18004a683`: `SetEvent( Global\TermSrvReadyEvent ) failed: 0x%x in %s`

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
0x18004a5ec  push    rbx
0x18004a5ee  sub     rsp, 20h
0x18004a5f2  xor     edx, edx; bInheritHandle
0x18004a5f4  lea     r8, aGlobalTermsrvr; "Global\\TermSrvReadyEvent"
0x18004a5fb  mov     rbx, rcx
0x18004a5fe  lea     ecx, [rdx+2]; dwDesiredAccess
0x18004a601  call    cs:__imp_OpenEventW
0x18004a608  nop     dword ptr [rax+rax+00h]
0x18004a60d  mov     [rbx+48h], rax
0x18004a611  test    rax, rax
0x18004a614  jnz     short loc_18004A647
0x18004a616  call    cs:__imp_GetLastError
0x18004a61d  nop     dword ptr [rax+rax+00h]
0x18004a622  mov     ebx, eax
0x18004a624  test    eax, eax
0x18004a626  jle     short loc_18004A631
0x18004a628  movzx   ebx, ax
0x18004a62b  or      ebx, 80070000h
0x18004a631  mov     r8d, ebx
0x18004a634  lea     rdx, aOpeneventGloba; "OpenEvent( Global\\TermSrvReadyEvent ):"...
0x18004a63b  mov     ecx, 8; int
0x18004a640  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a645  jmp     short loc_18004A698
0x18004a647  mov     rcx, rax; hEvent
0x18004a64a  call    cs:__imp_SetEvent
0x18004a651  nop     dword ptr [rax+rax+00h]
0x18004a656  test    eax, eax
0x18004a658  jnz     short loc_18004A696
0x18004a65a  call    cs:__imp_GetLastError
0x18004a661  nop     dword ptr [rax+rax+00h]
0x18004a666  mov     ebx, eax
0x18004a668  test    eax, eax
0x18004a66a  jle     short loc_18004A675
0x18004a66c  movzx   ebx, ax
0x18004a66f  or      ebx, 80070000h
0x18004a675  test    ebx, ebx
0x18004a677  jns     short loc_18004A698
0x18004a679  lea     r9, aCserviceSetter; "CService::SetTermSrvReadyEvent"
0x18004a680  mov     r8d, ebx
0x18004a683  lea     rdx, aSeteventGlobal; "SetEvent( Global\\TermSrvReadyEvent ) f"...
0x18004a68a  mov     ecx, 8; int
0x18004a68f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a694  jmp     short loc_18004A698
0x18004a696  xor     ebx, ebx
0x18004a698  mov     eax, ebx
0x18004a69a  add     rsp, 20h
0x18004a69e  pop     rbx
0x18004a69f  retn
```
