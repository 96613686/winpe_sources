# DhcpNotifyClientOnParamChange

- ea: `0x180008a8c`
- end: `0x180008afc`
- name: `DhcpNotifyClientOnParamChange`
- size: `112`
- prototype: `__int64 __fastcall(int, int, const CHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010e68`

## callees

- `0x180008a8c`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008aae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ac6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ac6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008abb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008abb`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180008aa0`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180008aa0`

## pseudocode

```c
__int64 __fastcall DhcpNotifyClientOnParamChange(int a1, int a2, const CHAR *a3)
{
  HANDLE v5; // rax
  void *v6; // rdi
  int v7; // ecx
  DWORD LastError; // ebx
  BOOL v9; // ebx

  v5 = OpenEventA(0x1F0003u, 0, a3);
  v6 = v5;
  if ( v5 && (v9 = SetEvent(v5), CloseHandle(v6), v9) )
    LastError = 0;
  else
    LastError = GetLastError();
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0qqq_EtwEventWriteTransfer(v7, (unsigned int)ParamChangeNotification, a1, a2, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180008a8c  push    rbx
0x180008a8e  push    rbp
0x180008a8f  push    rsi
0x180008a90  push    rdi
0x180008a91  sub     rsp, 38h
0x180008a95  mov     esi, edx
0x180008a97  mov     ebp, ecx
0x180008a99  xor     edx, edx; bInheritHandle
0x180008a9b  mov     ecx, 1F0003h; dwDesiredAccess
0x180008aa0  call    cs:__imp_OpenEventA
0x180008aa6  mov     rdi, rax
0x180008aa9  test    rax, rax
0x180008aac  jnz     short loc_180008AB8
0x180008aae  call    cs:__imp_GetLastError
0x180008ab4  mov     ebx, eax
0x180008ab6  jmp     short loc_180008AD2
0x180008ab8  mov     rcx, rdi; hEvent
0x180008abb  call    cs:__imp_SetEvent
0x180008ac1  mov     rcx, rdi; hObject
0x180008ac4  mov     ebx, eax
0x180008ac6  call    cs:__imp_CloseHandle
0x180008acc  test    ebx, ebx
0x180008ace  jz      short loc_180008AAE
0x180008ad0  xor     ebx, ebx
0x180008ad2  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180008ad9  jz      short loc_180008AF1
0x180008adb  mov     r9d, esi
0x180008ade  mov     [rsp+58h+var_38], ebx
0x180008ae2  mov     r8d, ebp
0x180008ae5  lea     rdx, ParamChangeNotification
0x180008aec  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180008af1  mov     eax, ebx
0x180008af3  add     rsp, 38h
0x180008af7  pop     rdi
0x180008af8  pop     rsi
0x180008af9  pop     rbp
0x180008afa  pop     rbx
0x180008afb  retn
```
