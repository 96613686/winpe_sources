# EvReportWithError(ulong,long,ushort,...)

- ea: `0x140017cf4`
- end: `0x140017de1`
- name: `?EvReportWithError@@YAXKJGZZ`
- size: `237`
- prototype: `void(unsigned int, signed int dwMessageId, unsigned __int16, ...)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140006478`
- `0x140008f50`
- `0x14000d75c`
- `0x14000e768`
- `0x14000eb04`
- `0x14001d760`
- `0x14001d855`
- `0x14001d914`
- `0x14001da47`

## callees

- `0x1400037dc`
- `0x140017330`
- `0x140017cf4`
- `0x14001a0e4`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140017d84`
- `KERNEL32!LocalAlloc` at `0x140017d84`
- `KERNEL32!FormatMessageW` at `0x140017d74`
- `KERNEL32!FormatMessageW` at `0x140017d74`

## pseudocode

```c
void EvReportWithError(unsigned int a1, signed int dwMessageId, unsigned __int16 a3, ...)
{
  const wchar_t *v5; // r8
  CEventReporter *v6; // rcx
  const wchar_t *v7; // r9
  WCHAR Buffer[4]; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-1h] BYREF
  wchar_t v10[20]; // [rsp+58h] [rbp+Fh] BYREF
  va_list va; // [rsp+C8h] [rbp+7Fh] BYREF

  va_start(va, a3);
  v5 = L"%#x";
  if ( dwMessageId >= 0 )
    v5 = L"%d";
  StringCchPrintfW(v10, 0x14u, v5, (unsigned int)dwMessageId);
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, Buffer, 0, 0) )
  {
    v7 = *(const wchar_t **)Buffer;
  }
  else
  {
    v7 = (const wchar_t *)LocalAlloc(0x40u, 2u);
    *(_QWORD *)Buffer = v7;
  }
  v9[0] = v7;
  v9[1] = 0;
  CEventReporter::Report(v6, a1, v10, v7, a3, va);
  CAutoLocalFreePtr::~CAutoLocalFreePtr((CAutoLocalFreePtr *)v9);
}

```

## disassembly

```asm
0x140017cf4  mov     [rsp-8+arg_10], r8w
0x140017cfa  mov     qword ptr [rsp-8+arg_18], r9
0x140017cff  push    rbp
0x140017d00  push    rbx
0x140017d01  push    rdi
0x140017d02  lea     rbp, [rsp-47h]
0x140017d07  sub     rsp, 90h
0x140017d0e  mov     rax, cs:__security_cookie
0x140017d15  xor     rax, rsp
0x140017d18  mov     [rbp+57h+var_20], rax
0x140017d1c  mov     ebx, edx
0x140017d1e  mov     edi, ecx
0x140017d20  lea     rax, aD; "%d"
0x140017d27  lea     r8, asc_140023198; "%#x"
0x140017d2e  test    edx, edx
0x140017d30  cmovns  r8, rax; wchar_t *
0x140017d34  mov     r9d, edx
0x140017d37  mov     edx, 14h; unsigned __int64
0x140017d3c  lea     rcx, [rbp+57h+var_48]; wchar_t *
0x140017d40  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140017d45  mov     qword ptr [rbp+57h+Buffer], 0
0x140017d4d  mov     [rsp+0A0h+Arguments], 0; Arguments
0x140017d56  mov     [rsp+0A0h+nSize], 0; nSize
0x140017d5e  lea     rax, [rbp+57h+Buffer]
0x140017d62  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x140017d67  xor     r9d, r9d; dwLanguageId
0x140017d6a  mov     r8d, ebx; dwMessageId
0x140017d6d  xor     edx, edx; lpSource
0x140017d6f  mov     ecx, 1100h; dwFlags
0x140017d74  call    cs:__imp_FormatMessageW
0x140017d7a  test    eax, eax
0x140017d7c  jnz     short loc_140017D93
0x140017d7e  lea     edx, [rax+2]; uBytes
0x140017d81  lea     ecx, [rax+40h]; uFlags
0x140017d84  call    cs:__imp_LocalAlloc
0x140017d8a  mov     r9, rax
0x140017d8d  mov     qword ptr [rbp+57h+Buffer], rax
0x140017d91  jmp     short loc_140017D97
0x140017d93  mov     r9, qword ptr [rbp+57h+Buffer]; wchar_t *
0x140017d97  mov     [rbp+57h+var_58], r9
0x140017d9b  mov     [rbp+57h+var_50], 0
0x140017da3  lea     rax, [rbp+57h+arg_18]
0x140017da7  mov     qword ptr [rsp+0A0h+nSize], rax; char *
0x140017dac  movzx   eax, [rbp+57h+arg_10]
0x140017db0  mov     word ptr [rsp+0A0h+lpBuffer], ax; unsigned __int16
0x140017db5  lea     r8, [rbp+57h+var_48]; wchar_t *
0x140017db9  mov     edx, edi; unsigned int
0x140017dbb  call    ?Report@CEventReporter@@QEAAXKPEB_W0GPEAD@Z; CEventReporter::Report(ulong,wchar_t const *,wchar_t const *,ushort,char *)
0x140017dc0  nop
0x140017dc1  lea     rcx, [rbp+57h+var_58]; this
0x140017dc5  call    ??1CAutoLocalFreePtr@@QEAA@XZ; CAutoLocalFreePtr::~CAutoLocalFreePtr(void)
0x140017dca  mov     rcx, [rbp+57h+var_20]
0x140017dce  xor     rcx, rsp; StackCookie
0x140017dd1  call    __security_check_cookie
0x140017dd6  add     rsp, 90h
0x140017ddd  pop     rdi
0x140017dde  pop     rbx
0x140017ddf  pop     rbp
0x140017de0  retn
```
