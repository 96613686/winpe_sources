# NrpNotifyAfd

- ea: `0x180051c5c`
- end: `0x180051d13`
- name: `NrpNotifyAfd`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035838`
- `0x180051d1c`

## callees

- `0x180051c5c`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cd9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180051c9b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180051c9b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180051cbc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180051cbc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180051cc4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180051cc4`

## string_xrefs

- `0x180051c91`: `Global\NameRes_StartCompleted`

## pseudocode

```c
__int64 __fastcall NrpNotifyAfd(unsigned int a1)
{
  HANDLE v2; // rax
  void *v3; // rdi
  DWORD LastError; // ebx
  BOOL v5; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 10, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, a1);
  v2 = OpenEventW(2u, 0, L"Global\\NameRes_StartCompleted");
  v3 = v2;
  if ( v2 )
  {
    LastError = 0;
    if ( a1 )
      v5 = SetEvent(v2);
    else
      v5 = ResetEvent(v2);
    if ( !v5 )
      LastError = GetLastError();
    CloseHandle(v3);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 11, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180051c5c  mov     [rsp+arg_0], rbx
0x180051c61  mov     [rsp+arg_8], rsi
0x180051c66  push    rdi
0x180051c67  sub     rsp, 20h
0x180051c6b  mov     esi, ecx
0x180051c6d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051c74  jz      short loc_180051C8F
0x180051c76  mov     edx, 0Ah
0x180051c7b  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180051c82  mov     ecx, 40Bh
0x180051c87  mov     r9d, esi
0x180051c8a  call    WPP_SF_d
0x180051c8f  xor     edx, edx; bInheritHandle
0x180051c91  lea     r8, aGlobalNameresS; "Global\\NameRes_StartCompleted"
0x180051c98  lea     ecx, [rdx+2]; dwDesiredAccess
0x180051c9b  call    cs:__imp_OpenEventW
0x180051ca1  mov     rdi, rax
0x180051ca4  test    rax, rax
0x180051ca7  jnz     short loc_180051CB3
0x180051ca9  call    cs:__imp_GetLastError
0x180051caf  mov     ebx, eax
0x180051cb1  jmp     short loc_180051CDF
0x180051cb3  xor     ebx, ebx
0x180051cb5  mov     rcx, rdi; hEvent
0x180051cb8  test    esi, esi
0x180051cba  jz      short loc_180051CC4
0x180051cbc  call    cs:__imp_SetEvent
0x180051cc2  jmp     short loc_180051CCA
0x180051cc4  call    cs:__imp_ResetEvent
0x180051cca  test    eax, eax
0x180051ccc  jnz     short loc_180051CD6
0x180051cce  call    cs:__imp_GetLastError
0x180051cd4  mov     ebx, eax
0x180051cd6  mov     rcx, rdi; hObject
0x180051cd9  call    cs:__imp_CloseHandle
0x180051cdf  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051ce6  jz      short loc_180051D01
0x180051ce8  mov     edx, 0Bh
0x180051ced  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180051cf4  mov     ecx, 40Bh
0x180051cf9  mov     r9d, ebx
0x180051cfc  call    WPP_SF_d
0x180051d01  mov     rsi, [rsp+28h+arg_8]
0x180051d06  mov     eax, ebx
0x180051d08  mov     rbx, [rsp+28h+arg_0]
0x180051d0d  add     rsp, 20h
0x180051d11  pop     rdi
0x180051d12  retn
```
