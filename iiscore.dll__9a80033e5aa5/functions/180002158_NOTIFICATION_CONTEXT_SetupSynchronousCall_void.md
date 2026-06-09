# NOTIFICATION_CONTEXT::SetupSynchronousCall(void)

- ea: `0x180002158`
- end: `0x1800021c2`
- name: `?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(NOTIFICATION_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002040`
- `0x180002bf0`
- `0x180004340`

## callees

- `0x180002158`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000216e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000216e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002185`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002193`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800021b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800021b1`

## pseudocode

```c
signed int __fastcall NOTIFICATION_CONTEXT::SetupSynchronousCall(NOTIFICATION_CONTEXT *this)
{
  LPVOID Value; // rax
  signed int result; // eax
  HANDLE EventW; // rax

  if ( *((_QWORD *)this + 8) )
    return 0;
  Value = TlsGetValue(g_TlsEventIndex);
  *((_QWORD *)this + 8) = Value;
  if ( Value )
  {
    TlsSetValue(g_TlsEventIndex, 0);
    return 0;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( EventW )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002158  push    rbx
0x18000215a  sub     rsp, 20h
0x18000215e  cmp     qword ptr [rcx+40h], 0
0x180002163  mov     rbx, rcx
0x180002166  jnz     short loc_18000218B
0x180002168  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x18000216e  call    cs:__imp_TlsGetValue
0x180002174  mov     [rbx+40h], rax
0x180002178  test    rax, rax
0x18000217b  jz      short loc_1800021A7
0x18000217d  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180002183  xor     edx, edx; lpTlsValue
0x180002185  call    cs:__imp_TlsSetValue
0x18000218b  xor     eax, eax
0x18000218d  add     rsp, 20h
0x180002191  pop     rbx
0x180002192  retn
0x180002193  call    cs:__imp_GetLastError
0x180002199  test    eax, eax
0x18000219b  jle     short loc_18000218D
0x18000219d  movzx   eax, ax
0x1800021a0  or      eax, 80070000h
0x1800021a5  jmp     short loc_18000218D
0x1800021a7  xor     r9d, r9d; lpName
0x1800021aa  xor     r8d, r8d; bInitialState
0x1800021ad  xor     edx, edx; bManualReset
0x1800021af  xor     ecx, ecx; lpEventAttributes
0x1800021b1  call    cs:__imp_CreateEventW
0x1800021b7  mov     [rbx+40h], rax
0x1800021bb  test    rax, rax
0x1800021be  jnz     short loc_18000218B
0x1800021c0  jmp     short loc_180002193
```
