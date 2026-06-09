# UalPrintTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x18000a9a4`
- end: `0x18000aaa6`
- name: `?WriteDbgTraceInfo@UalPrintTelemetry@@SAXPEADPEAGZZ`
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
- `0x18000a9a4`
- `0x18000d7e0`

## pseudocode

```c
void UalPrintTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
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
          if ( *v6 > 4u )
          {
            v9 = (const unsigned __int16 *)a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (__int64)v6,
              (__int64)byte_180010019,
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
0x18000a9a4  mov     rax, rsp
0x18000a9a7  mov     [rax+10h], rdx
0x18000a9ab  mov     [rax+18h], r8
0x18000a9af  mov     [rax+20h], r9
0x18000a9b3  push    rbp
0x18000a9b4  push    rbx
0x18000a9b5  lea     rbp, [rax-1F68h]
0x18000a9bc  mov     eax, 2058h
0x18000a9c1  call    _alloca_probe
0x18000a9c6  sub     rsp, rax
0x18000a9c9  mov     rax, cs:__security_cookie
0x18000a9d0  xor     rax, rsp
0x18000a9d3  mov     [rbp+1F60h+var_20], rax
0x18000a9da  mov     rbx, rcx
0x18000a9dd  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000a9e2  mov     rax, [rax+8]
0x18000a9e6  test    rax, rax
0x18000a9e9  jz      loc_18000AA8D
0x18000a9ef  mov     eax, [rax]
0x18000a9f1  test    eax, eax
0x18000a9f3  jz      loc_18000AA8D
0x18000a9f9  mov     r8, [rbp+1F60h+Format]; Format
0x18000aa00  lea     r9, [rbp+1F60h+Args]; Args
0x18000aa07  mov     edx, 0FFFh; BufferCount
0x18000aa0c  mov     [rsp+2060h+var_2030], 0
0x18000aa15  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x18000aa1a  call    _vsnwprintf
0x18000aa1f  test    eax, eax
0x18000aa21  js      short loc_18000AA8D
0x18000aa23  cmp     eax, 0FFFh
0x18000aa28  ja      short loc_18000AA8D
0x18000aa2a  jnz     short loc_18000AA35
0x18000aa2c  xor     eax, eax
0x18000aa2e  mov     [rbp+1F60h+var_22], ax
0x18000aa35  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000aa3a  mov     rax, [rax+8]
0x18000aa3e  test    rax, rax
0x18000aa41  jz      short loc_18000AA8D
0x18000aa43  mov     eax, [rax]
0x18000aa45  test    eax, eax
0x18000aa47  jz      short loc_18000AA8D
0x18000aa49  call    ?Instance@UalPrintTelemetry@@KAPEAV1@XZ; UalPrintTelemetry::Instance(void)
0x18000aa4e  call    ?Instance@UalPrintLogging@@KAPEAV1@XZ; UalPrintLogging::Instance(void)
0x18000aa53  mov     rcx, [rax+8]
0x18000aa57  mov     eax, [rcx]
0x18000aa59  cmp     eax, 4
0x18000aa5c  jbe     short loc_18000AA8D
0x18000aa5e  lea     rax, [rsp+2060h+Buffer]
0x18000aa63  mov     [rsp+2060h+var_2030], rbx
0x18000aa68  mov     [rsp+2060h+var_2028], rax
0x18000aa6d  lea     rdx, byte_180010019
0x18000aa74  lea     rax, [rsp+2060h+var_2028]
0x18000aa79  mov     [rsp+2060h+var_2038], rax
0x18000aa7e  lea     rax, [rsp+2060h+var_2030]
0x18000aa83  mov     [rsp+2060h+var_2040], rax
0x18000aa88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000aa8d  mov     rcx, [rbp+1F60h+var_20]
0x18000aa94  xor     rcx, rsp; StackCookie
0x18000aa97  call    __security_check_cookie
0x18000aa9c  add     rsp, 2058h
0x18000aaa3  pop     rbx
0x18000aaa4  pop     rbp
0x18000aaa5  retn
```
