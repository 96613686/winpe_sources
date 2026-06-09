# GetThreadEvent(void * &)

- ea: `0x18004ca7c`
- end: `0x18004cb37`
- name: `?GetThreadEvent@@YAJAEAPEAX@Z`
- size: `187`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180013d9c`
- `0x1800215b0`
- `0x1800217c0`
- `0x180021aa0`
- `0x180022540`
- `0x1800227a0`
- `0x180035f8c`
- `0x18003610c`
- `0x18003f348`

## callees

- `0x18002c6c8`
- `0x18004ca7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004caa1`
- `KERNEL32!GetLastError` at `0x18004cadf`
- `KERNEL32!GetLastError` at `0x18004cb0d`
- `KERNEL32!GetLastError` at `0x18004caa1`
- `KERNEL32!GetLastError` at `0x18004cadf`
- `KERNEL32!GetLastError` at `0x18004cb0d`
- `KERNEL32!CloseHandle` at `0x18004cb18`
- `KERNEL32!CloseHandle` at `0x18004cb18`
- `KERNEL32!CreateEventW` at `0x18004cad1`
- `KERNEL32!CreateEventW` at `0x18004cad1`
- `KERNEL32!TlsGetValue` at `0x18004ca8f`
- `KERNEL32!TlsGetValue` at `0x18004ca8f`
- `KERNEL32!TlsSetValue` at `0x18004cb03`
- `KERNEL32!TlsSetValue` at `0x18004cb03`

## pseudocode

```c
__int64 __fastcall GetThreadEvent(void **a1)
{
  void *Value; // rax
  DWORD LastError; // ebx
  unsigned __int16 v4; // r8
  unsigned __int64 EventW; // rax
  DWORD v7; // ecx

  Value = TlsGetValue(g_dwThreadEventIndex);
  *a1 = Value;
  if ( !Value )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v4 = 1111;
      goto LABEL_4;
    }
    EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
    *a1 = (void *)EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( !LastError )
        return LastError;
      v4 = 1112;
LABEL_4:
      LogMsgNTStatus(LastError, (wchar_t *)L"qmutil", v4);
      return LastError;
    }
    v7 = g_dwThreadEventIndex;
    *a1 = (void *)(EventW | 1);
    if ( !TlsSetValue(v7, (LPVOID)(EventW | 1)) )
    {
      LastError = GetLastError();
      CloseHandle(*a1);
      if ( !LastError )
        return LastError;
      v4 = 1113;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004ca7c  mov     [rsp+arg_0], rbx
0x18004ca81  push    rdi
0x18004ca82  sub     rsp, 20h
0x18004ca86  mov     rdi, rcx
0x18004ca89  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x18004ca8f  call    cs:__imp_TlsGetValue
0x18004ca95  mov     [rdi], rax
0x18004ca98  test    rax, rax
0x18004ca9b  jnz     loc_18004CB2A
0x18004caa1  call    cs:__imp_GetLastError
0x18004caa7  mov     ebx, eax
0x18004caa9  test    eax, eax
0x18004caab  jz      short loc_18004CAC5
0x18004caad  mov     r8d, 457h; unsigned __int16
0x18004cab3  lea     rdx, aQmutil; "qmutil"
0x18004caba  mov     ecx, ebx; int
0x18004cabc  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18004cac1  mov     eax, ebx
0x18004cac3  jmp     short loc_18004CB2C
0x18004cac5  xor     r9d, r9d; lpName
0x18004cac8  xor     r8d, r8d; bInitialState
0x18004cacb  xor     ecx, ecx; lpEventAttributes
0x18004cacd  lea     edx, [r9+1]; bManualReset
0x18004cad1  call    cs:__imp_CreateEventW
0x18004cad7  mov     [rdi], rax
0x18004cada  test    rax, rax
0x18004cadd  jnz     short loc_18004CAF3
0x18004cadf  call    cs:__imp_GetLastError
0x18004cae5  mov     ebx, eax
0x18004cae7  test    eax, eax
0x18004cae9  jz      short loc_18004CAC1
0x18004caeb  mov     r8d, 458h
0x18004caf1  jmp     short loc_18004CAB3
0x18004caf3  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x18004caf9  or      rax, 1
0x18004cafd  mov     rdx, rax; lpTlsValue
0x18004cb00  mov     [rdi], rax
0x18004cb03  call    cs:__imp_TlsSetValue
0x18004cb09  test    eax, eax
0x18004cb0b  jnz     short loc_18004CB2A
0x18004cb0d  call    cs:__imp_GetLastError
0x18004cb13  mov     rcx, [rdi]; hObject
0x18004cb16  mov     ebx, eax
0x18004cb18  call    cs:__imp_CloseHandle
0x18004cb1e  test    ebx, ebx
0x18004cb20  jz      short loc_18004CAC1
0x18004cb22  mov     r8d, 459h
0x18004cb28  jmp     short loc_18004CAB3
0x18004cb2a  xor     eax, eax
0x18004cb2c  mov     rbx, [rsp+28h+arg_0]
0x18004cb31  add     rsp, 20h
0x18004cb35  pop     rdi
0x18004cb36  retn
```
