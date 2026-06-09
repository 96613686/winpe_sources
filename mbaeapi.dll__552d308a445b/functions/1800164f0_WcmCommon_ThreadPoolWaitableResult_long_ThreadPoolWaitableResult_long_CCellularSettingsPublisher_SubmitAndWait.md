# WcmCommon::ThreadPoolWaitableResult_long_::ThreadPoolWaitableResult_long___CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___

- ea: `0x1800164f0`
- end: `0x1800165c9`
- name: `WcmCommon::ThreadPoolWaitableResult_long_::ThreadPoolWaitableResult_long___CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016754`

## callees

- `0x18000ad5c`
- `0x1800164f0`
- `0x18001b054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016552`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016552`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001658a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001658a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001656e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001656e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016579`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall WcmCommon::ThreadPoolWaitableResult_long_::ThreadPoolWaitableResult_long___CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___(
        _QWORD *a1,
        _QWORD *a2)
{
  void **v3; // rsi
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  HANDLE Event; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = &WcmCommon::ThreadPoolWaitableResult<long>::`vftable';
  a1[8] = 0;
  a1[1] = off_18005DF20;
  a1[2] = *a2;
  a1[8] = a1 + 1;
  v3 = (void **)(a1 + 9);
  a1[9] = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v5, v6);
  GetLastError();
  v8 = *v3;
  if ( *v3 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
    SetLastError(LastError);
  }
  *v3 = Event;
  a1[10] = 0;
  *(_QWORD *)((char *)a1 + 92) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800164f0  mov     r11, rsp
0x1800164f3  mov     [r11+10h], rbx
0x1800164f7  mov     [r11+20h], rbp
0x1800164fb  mov     [r11+8], rcx
0x1800164ff  push    rsi
0x180016500  push    rdi
0x180016501  push    r14
0x180016503  sub     rsp, 20h
0x180016507  mov     rbx, rcx
0x18001650a  lea     rax, ??_7?$ThreadPoolWaitableResult@J@WcmCommon@@6B@; const WcmCommon::ThreadPoolWaitableResult<long>::`vftable'
0x180016511  mov     [rcx], rax
0x180016514  lea     r8, [rcx+8]
0x180016518  mov     qword ptr [r8+38h], 0
0x180016520  lea     rax, off_18005DF20
0x180016527  mov     [r8], rax
0x18001652a  mov     rax, [rdx]
0x18001652d  mov     [r8+8], rax
0x180016531  mov     [r8+38h], r8
0x180016535  lea     rsi, [rcx+48h]
0x180016539  mov     [r11+18h], rsi
0x18001653d  mov     qword ptr [rsi], 0
0x180016544  xor     edx, edx; lpName
0x180016546  xor     ecx, ecx; lpEventAttributes
0x180016548  mov     r9d, 1F0003h; dwDesiredAccess
0x18001654e  lea     r8d, [rdx+1]; dwFlags
0x180016552  call    cs:__imp_CreateEventExW
0x180016558  mov     r14, rax
0x18001655b  test    rax, rax
0x18001655e  jz      short loc_1800165BE
0x180016560  call    cs:__imp_GetLastError
0x180016566  mov     rdi, [rsi]
0x180016569  test    rdi, rdi
0x18001656c  jz      short loc_180016590
0x18001656e  call    cs:__imp_GetLastError
0x180016574  mov     ebp, eax
0x180016576  mov     rcx, rdi; hObject
0x180016579  call    cs:__imp_CloseHandle
0x18001657f  mov     rcx, [rsp+38h]; this
0x180016584  test    eax, eax
0x180016586  jz      short loc_1800165B3
0x180016588  mov     ecx, ebp; dwErrCode
0x18001658a  call    cs:__imp_SetLastError
0x180016590  mov     [rsi], r14
0x180016593  xor     eax, eax
0x180016595  mov     [rbx+50h], rax
0x180016599  mov     [rbx+5Ch], rax
0x18001659d  mov     rax, rbx
0x1800165a0  mov     rbx, [rsp+38h+arg_8]
0x1800165a5  mov     rbp, [rsp+38h+arg_18]
0x1800165aa  add     rsp, 20h
0x1800165ae  pop     r14
0x1800165b0  pop     rdi
0x1800165b1  pop     rsi
0x1800165b2  retn
0x1800165b3  mov     edx, 0A0Bh; void *
0x1800165b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800165be  mov     rcx, [rsp+38h]; this
0x1800165c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
