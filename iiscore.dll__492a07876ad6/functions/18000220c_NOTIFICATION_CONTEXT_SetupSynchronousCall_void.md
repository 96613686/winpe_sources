# NOTIFICATION_CONTEXT::SetupSynchronousCall(void)

- ea: `0x18000220c`
- end: `0x18000228f`
- name: `?SetupSynchronousCall@NOTIFICATION_CONTEXT@@QEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(NOTIFICATION_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800020d0`
- `0x180002db0`
- `0x180004710`

## callees

- `0x18000220c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002222`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002222`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000223f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000223f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002254`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002278`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002278`

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
0x18000220c  push    rbx
0x18000220e  sub     rsp, 20h
0x180002212  cmp     qword ptr [rcx+40h], 0
0x180002217  mov     rbx, rcx
0x18000221a  jnz     short loc_18000224B
0x18000221c  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x180002222  call    cs:__imp_TlsGetValue
0x180002229  nop     dword ptr [rax+rax+00h]
0x18000222e  mov     [rbx+40h], rax
0x180002232  test    rax, rax
0x180002235  jz      short loc_18000226E
0x180002237  mov     ecx, cs:?g_TlsEventIndex@@3KA; dwTlsIndex
0x18000223d  xor     edx, edx; lpTlsValue
0x18000223f  call    cs:__imp_TlsSetValue
0x180002246  nop     dword ptr [rax+rax+00h]
0x18000224b  xor     eax, eax
0x18000224d  add     rsp, 20h
0x180002251  pop     rbx
0x180002252  retn
0x180002254  call    cs:__imp_GetLastError
0x18000225b  nop     dword ptr [rax+rax+00h]
0x180002260  test    eax, eax
0x180002262  jle     short loc_18000224D
0x180002264  movzx   eax, ax
0x180002267  or      eax, 80070000h
0x18000226c  jmp     short loc_18000224D
0x18000226e  xor     r9d, r9d; lpName
0x180002271  xor     r8d, r8d; bInitialState
0x180002274  xor     edx, edx; bManualReset
0x180002276  xor     ecx, ecx; lpEventAttributes
0x180002278  call    cs:__imp_CreateEventW
0x18000227f  nop     dword ptr [rax+rax+00h]
0x180002284  mov     [rbx+40h], rax
0x180002288  test    rax, rax
0x18000228b  jnz     short loc_18000224B
0x18000228d  jmp     short loc_180002254
```
