# CfOpenProgressEvent

- ea: `0x180002d00`
- end: `0x180002db5`
- name: `CfOpenProgressEvent`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002d00`
- `0x180012054`
- `0x18001cba8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d7b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002d54`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002d54`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002d2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002d2b`

## pseudocode

```c
__int64 __fastcall CfOpenProgressEvent(_QWORD *a1)
{
  int v2; // edi
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  HANDLE v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  signed int v9; // eax

  v2 = 0;
  v3 = GlobalPortInit(0);
  while ( 1 )
  {
    v5 = v3;
    if ( v3 >= 0 )
      break;
    if ( v2 >= 3 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(v4, (unsigned int)v3);
      return v5;
    }
    Sleep(0x1Eu);
    v3 = GlobalPortInit(0);
    ++v2;
  }
  v6 = OpenEventW(0x100000u, 0, L"Global\\CfProgressEvent");
  if ( !v6 )
  {
    LastError = GetLastError();
    MicrosoftTelemetryAssertTriggeredArgs(v8, LastError);
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
  }
  *a1 = v6;
  return v5;
}

```

## disassembly

```asm
0x180002d00  mov     [rsp+arg_0], rbx
0x180002d05  mov     [rsp+arg_8], rsi
0x180002d0a  push    rdi
0x180002d0b  sub     rsp, 20h
0x180002d0f  mov     rsi, rcx
0x180002d12  xor     edi, edi
0x180002d14  xor     ecx, ecx
0x180002d16  call    GlobalPortInit
0x180002d1b  jmp     short loc_180002D40
0x180002d1d  cmp     edi, 3
0x180002d20  jge     loc_180002DAC
0x180002d26  mov     ecx, 1Eh; dwMilliseconds
0x180002d2b  call    cs:__imp_Sleep
0x180002d32  nop     dword ptr [rax+rax+00h]
0x180002d37  xor     ecx, ecx
0x180002d39  call    GlobalPortInit
0x180002d3e  inc     edi
0x180002d40  mov     ebx, eax
0x180002d42  test    eax, eax
0x180002d44  js      short loc_180002D1D
0x180002d46  lea     r8, Name; "Global\\CfProgressEvent"
0x180002d4d  xor     edx, edx; bInheritHandle
0x180002d4f  mov     ecx, 100000h; dwDesiredAccess
0x180002d54  call    cs:__imp_OpenEventW
0x180002d5b  nop     dword ptr [rax+rax+00h]
0x180002d60  mov     rdi, rax
0x180002d63  test    rax, rax
0x180002d66  jnz     short loc_180002D96
0x180002d68  call    cs:__imp_GetLastError
0x180002d6f  nop     dword ptr [rax+rax+00h]
0x180002d74  mov     edx, eax
0x180002d76  call    MicrosoftTelemetryAssertTriggeredArgs
0x180002d7b  call    cs:__imp_GetLastError
0x180002d82  nop     dword ptr [rax+rax+00h]
0x180002d87  mov     ebx, eax
0x180002d89  test    eax, eax
0x180002d8b  jle     short loc_180002D96
0x180002d8d  movzx   ebx, ax
0x180002d90  or      ebx, 80070000h
0x180002d96  mov     [rsi], rdi
0x180002d99  mov     rsi, [rsp+28h+arg_8]
0x180002d9e  mov     eax, ebx
0x180002da0  mov     rbx, [rsp+28h+arg_0]
0x180002da5  add     rsp, 20h
0x180002da9  pop     rdi
0x180002daa  retn
0x180002dac  mov     edx, ebx
0x180002dae  call    MicrosoftTelemetryAssertTriggeredArgs
0x180002db3  jmp     short loc_180002D99
```
