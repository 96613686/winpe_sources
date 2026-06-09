# UalPrintTelemetry::WriteDbgTraceError(char *,ushort *,...)

- ea: `0x18000a89c`
- end: `0x18000a99e`
- name: `?WriteDbgTraceError@UalPrintTelemetry@@SAXPEADPEAGZZ`
- size: `258`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a14`

## callees

- `0x180001008`
- `0x180001ce0`
- `0x180002624`
- `0x18000a3bc`
- `0x18000a470`
- `0x18000a89c`
- `0x18000d7e0`

## pseudocode

```c
void UalPrintTelemetry::WriteDbgTraceError(char *a1, unsigned __int16 *a2, ...)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax
  _DWORD *v5; // rax
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v10; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[4096]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Args; // [rsp+2088h] [rbp+1F80h] BYREF
  va_list Argsa; // [rsp+2088h] [rbp+1F80h]
  __int64 v15; // [rsp+2090h] [rbp+1F88h]
  va_list va1; // [rsp+2098h] [rbp+1F90h] BYREF

  va_start(va1, a2);
  va_start(Argsa, a2);
  Args = va_arg(va1, _QWORD);
  v15 = va_arg(va1, _QWORD);
  v3 = (_DWORD *)*((_QWORD *)UalPrintTelemetry::Instance() + 1);
  if ( v3 )
  {
    if ( *v3 )
    {
      v9 = 0;
      v4 = vsnwprintf(Buffer, 0xFFFu, a2, Argsa);
      if ( v4 < 0x1000 )
      {
        if ( v4 == 4095 )
          Buffer[4095] = 0;
        v5 = (_DWORD *)*((_QWORD *)UalPrintTelemetry::Instance() + 1);
        if ( v5 && *v5 )
        {
          UalPrintTelemetry::Instance();
          v6 = (_DWORD *)*((_QWORD *)UalPrintLogging::Instance() + 1);
          if ( *v6 > 2u )
          {
            v9 = (const unsigned __int16 *)a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (__int64)v6,
              (__int64)byte_18000FFF1,
              v7,
              v8,
              &v9,
              (char **)&v10);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000a89c  mov     rax, rsp
0x18000a89f  mov     [rax+10h], rdx
0x18000a8a3  mov     [rax+18h], r8
0x18000a8a7  mov     [rax+20h], r9
0x18000a8ab  push    rbp
0x18000a8ac  push    rbx
0x18000a8ad  lea     rbp, [rax-1F68h]
0x18000a8b4  mov     eax, 2058h
0x18000a8b9  call    _alloca_probe
0x18000a8be  sub     rsp, rax
0x18000a8c1  mov     rax, cs:__security_cookie
0x18000a8c8  xor     rax, rsp
0x18000a8cb  mov     [rbp+1F60h+var_20], rax
0x18000a8d2  mov     rbx, rcx
0x18000a8d5  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000a8da  mov     rax, [rax+8]
0x18000a8de  test    rax, rax
0x18000a8e1  jz      loc_18000A985
0x18000a8e7  mov     eax, [rax]
0x18000a8e9  test    eax, eax
0x18000a8eb  jz      loc_18000A985
0x18000a8f1  mov     r8, [rbp+1F60h+Format]; Format
0x18000a8f8  lea     r9, [rbp+1F60h+Args]; Args
0x18000a8ff  mov     edx, 0FFFh; BufferCount
0x18000a904  mov     [rsp+2060h+var_2030], 0
0x18000a90d  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x18000a912  call    _vsnwprintf
0x18000a917  test    eax, eax
0x18000a919  js      short loc_18000A985
0x18000a91b  cmp     eax, 0FFFh
0x18000a920  ja      short loc_18000A985
0x18000a922  jnz     short loc_18000A92D
0x18000a924  xor     eax, eax
0x18000a926  mov     [rbp+1F60h+var_22], ax
0x18000a92d  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000a932  mov     rax, [rax+8]
0x18000a936  test    rax, rax
0x18000a939  jz      short loc_18000A985
0x18000a93b  mov     eax, [rax]
0x18000a93d  test    eax, eax
0x18000a93f  jz      short loc_18000A985
0x18000a941  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000a946  call    ?Instance@UalPrintLogging@@KAPEAV1@XZ; UalPrintLogging::Instance(void)
0x18000a94b  mov     rcx, [rax+8]
0x18000a94f  mov     eax, [rcx]
0x18000a951  cmp     eax, 2
0x18000a954  jbe     short loc_18000A985
0x18000a956  lea     rax, [rsp+2060h+Buffer]
0x18000a95b  mov     [rsp+2060h+var_2030], rbx
0x18000a960  mov     [rsp+2060h+var_2028], rax
0x18000a965  lea     rdx, byte_18000FFF1
0x18000a96c  lea     rax, [rsp+2060h+var_2028]
0x18000a971  mov     [rsp+2060h+var_2038], rax
0x18000a976  lea     rax, [rsp+2060h+var_2030]
0x18000a97b  mov     [rsp+2060h+var_2040], rax
0x18000a980  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000a985  mov     rcx, [rbp+1F60h+var_20]
0x18000a98c  xor     rcx, rsp; StackCookie
0x18000a98f  call    __security_check_cookie
0x18000a994  add     rsp, 2058h
0x18000a99b  pop     rbx
0x18000a99c  pop     rbp
0x18000a99d  retn
```
