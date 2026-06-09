# cdp::ProtocolTraceClient::WriteQueueItemToPipe(cdp::ProtocolTraceClient::ForwardQueueItem &)

- ea: `0x1802ca098`
- end: `0x1802ca259`
- name: `?WriteQueueItemToPipe@ProtocolTraceClient@cdp@@AEAAXAEAUForwardQueueItem@12@@Z`
- size: `449`
- prototype: `void __fastcall(cdp::ProtocolTraceClient *__hidden this, struct cdp::ProtocolTraceClient::ForwardQueueItem *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1802c9e10`

## callees

- `0x1800110f8`
- `0x18003d0e0`
- `0x18008dbc0`
- `0x180096d20`
- `0x1800d177c`
- `0x1800df1dc`
- `0x18012d5cc`
- `0x180135738`
- `0x1801ed418`
- `0x1802bb1b8`
- `0x1802bbbb0`
- `0x1802ca098`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ca1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ca1b2`
- `msvcp_win!_Mtx_unlock` at `0x1802ca245`
- `msvcp_win!_Mtx_unlock` at `0x1802ca245`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802ca19c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802ca19c`

## string_xrefs

- `0x1802ca1fe`: `{"text":"Reset ProtocolTraceClient named pipe!"}`
- `0x1802ca1e6`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failure writing to Live Protocol Trace pipe."}`
- `0x1802ca1a6`: `{"text":"Successfully wrote to Live Protocol Trace pipe."}`
- `0x1802ca1db`: `.\protocoltraceclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall cdp::ProtocolTraceClient::WriteQueueItemToPipe(
        cdp::ProtocolTraceClient *this,
        struct cdp::ProtocolTraceClient::ForwardQueueItem *a2)
{
  HANDLE *v3; // rsi
  struct _Mtx_internal_imp_t *v4; // rdi
  unsigned __int64 SerializedLength; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  const char *v8; // rdx
  __int64 v9; // rcx
  signed int LastError; // eax
  int v11; // ecx
  _BYTE v12[24]; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v14[3]; // [rsp+60h] [rbp-19h] BYREF
  LPCVOID lpBuffer; // [rsp+78h] [rbp-1h] BYREF
  int v16; // [rsp+80h] [rbp+7h]
  _BYTE v17[24]; // [rsp+90h] [rbp+17h] BYREF
  char *v18; // [rsp+A8h] [rbp+2Fh]
  DWORD NumberOfBytesWritten; // [rsp+E0h] [rbp+67h] BYREF
  int v20; // [rsp+F0h] [rbp+77h] BYREF
  signed int v21; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = (HANDLE *)((char *)this + 304);
  v4 = (cdp::ProtocolTraceClient *)((char *)this + 312);
  v18 = (char *)this + 312;
  std::_Mutex_base::lock((cdp::ProtocolTraceClient *)((char *)this + 312));
  if ( (((unsigned __int64)*v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    SerializedLength = shared::Endpoint::GetSerializedLength((struct cdp::ProtocolTraceClient::ForwardQueueItem *)((char *)a2 + 16));
    cdp::BigEndianStreamWriter::BigEndianStreamWriter((cdp::BigEndianStreamWriter *)v17, SerializedLength);
    shared::Endpoint::Write(
      (struct cdp::ProtocolTraceClient::ForwardQueueItem *)((char *)a2 + 16),
      (struct cdp::BigEndianStreamWriter *)v17);
    std::vector<unsigned char>::vector<unsigned char>(v14, v17);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)a2 + 336LL))(*(_QWORD *)a2, v13);
    cdp::BigEndianStreamWriter::BigEndianStreamWriter(
      (cdp::BigEndianStreamWriter *)v12,
      v14[1] + v13[1] - v13[0] - v14[0]);
    LOBYTE(v6) = 1;
    cdp::BigEndianStreamWriter::WriteNumber<unsigned char>(v12, v6);
    LOBYTE(v7) = *((_DWORD *)a2 + 2) == 0;
    cdp::BigEndianStreamWriter::WriteNumber<unsigned char>(v12, v7);
    cdp::BigEndianStreamWriter::WriteBytesWithCount<unsigned int>((cdp::BigEndianStreamWriter *)v12);
    cdp::BigEndianStreamWriter::WriteBytesWithCount<unsigned int>((cdp::BigEndianStreamWriter *)v12);
    std::vector<unsigned char>::vector<unsigned char>(&lpBuffer, v12);
    NumberOfBytesWritten = 0;
    if ( WriteFile(*v3, lpBuffer, v16 - (_DWORD)lpBuffer, &NumberOfBytesWritten, 0) )
    {
      v8 = "{\"text\":\"Successfully wrote to Live Protocol Trace pipe.\"}";
      v9 = 4;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v21 = LastError;
      if ( LastError < 0 )
      {
        v20 = 195;
        Log<long &,char const (&)[36],int>(
          v11,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failure writing to Live Protocol Trace pipe.\"}",
          (unsigned int)&v21,
          (unsigned int)".\\protocoltraceclient.cpp",
          (__int64)&v20);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v3,
        -1);
      v8 = "{\"text\":\"Reset ProtocolTraceClient named pipe!\"}";
      v9 = 3;
    }
    Log<>(v9, v8);
    std::vector<unsigned char>::_Tidy(&lpBuffer);
    std::vector<unsigned char>::_Tidy(v12);
    std::vector<unsigned char>::_Tidy(v13);
    std::vector<unsigned char>::_Tidy(v14);
    std::vector<unsigned char>::_Tidy(v17);
  }
  _Mtx_unlock(v4);
}

```

## disassembly

```asm
0x1802ca098  push    rbp
0x1802ca09a  push    rbx
0x1802ca09b  push    rsi
0x1802ca09c  push    rdi
0x1802ca09d  push    r14
0x1802ca09f  lea     rbp, [rsp-37h]
0x1802ca0a4  sub     rsp, 0B0h
0x1802ca0ab  mov     r14, rdx
0x1802ca0ae  lea     rsi, [rcx+130h]
0x1802ca0b5  lea     rdi, [rcx+138h]
0x1802ca0bc  mov     [rbp+57h+var_28], rdi
0x1802ca0c0  mov     rcx, rdi; this
0x1802ca0c3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802ca0c8  nop
0x1802ca0c9  mov     rax, [rsi]
0x1802ca0cc  inc     rax
0x1802ca0cf  test    rax, 0FFFFFFFFFFFFFFFEh
0x1802ca0d5  jz      loc_1802CA242
0x1802ca0db  lea     rcx, [r14+10h]; this
0x1802ca0df  call    ?GetSerializedLength@Endpoint@shared@@QEBA_KXZ; shared::Endpoint::GetSerializedLength(void)
0x1802ca0e4  mov     rdx, rax; unsigned __int64
0x1802ca0e7  lea     rcx, [rbp+57h+var_40]; this
0x1802ca0eb  call    ??0BigEndianStreamWriter@cdp@@QEAA@_K@Z; cdp::BigEndianStreamWriter::BigEndianStreamWriter(unsigned __int64)
0x1802ca0f0  nop
0x1802ca0f1  lea     rdx, [rbp+57h+var_40]; struct cdp::BigEndianStreamWriter *
0x1802ca0f5  lea     rcx, [r14+10h]; this
0x1802ca0f9  call    ?Write@Endpoint@shared@@QEBAXAEAVBigEndianStreamWriter@cdp@@@Z; shared::Endpoint::Write(cdp::BigEndianStreamWriter &)
0x1802ca0fe  lea     rdx, [rbp+57h+var_40]
0x1802ca102  lea     rcx, [rbp+57h+var_70]
0x1802ca106  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1802ca10b  nop
0x1802ca10c  mov     rcx, [r14]
0x1802ca10f  mov     rax, [rcx]
0x1802ca112  lea     rdx, [rbp+57h+var_88]
0x1802ca116  mov     rax, [rax+150h]
0x1802ca11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ca122  nop
0x1802ca123  mov     rdx, [rbp+57h+var_80]
0x1802ca127  sub     rdx, [rbp+57h+var_88]
0x1802ca12b  sub     rdx, [rbp+57h+var_70]
0x1802ca12f  add     rdx, [rbp+57h+var_68]; unsigned __int64
0x1802ca133  lea     rcx, [rbp+57h+var_A0]; this
0x1802ca137  call    ??0BigEndianStreamWriter@cdp@@QEAA@_K@Z; cdp::BigEndianStreamWriter::BigEndianStreamWriter(unsigned __int64)
0x1802ca13c  nop
0x1802ca13d  mov     dl, 1
0x1802ca13f  lea     rcx, [rbp+57h+var_A0]
0x1802ca143  call    ??$WriteNumber@E@BigEndianStreamWriter@cdp@@AEAAXE@Z; cdp::BigEndianStreamWriter::WriteNumber<uchar>(uchar)
0x1802ca148  xor     ebx, ebx
0x1802ca14a  cmp     [r14+8], ebx
0x1802ca14e  setz    dl
0x1802ca151  lea     rcx, [rbp+57h+var_A0]
0x1802ca155  call    ??$WriteNumber@E@BigEndianStreamWriter@cdp@@AEAAXE@Z; cdp::BigEndianStreamWriter::WriteNumber<uchar>(uchar)
0x1802ca15a  lea     rdx, [rbp+57h+var_70]
0x1802ca15e  lea     rcx, [rbp+57h+var_A0]; this
0x1802ca162  call    ??$WriteBytesWithCount@I@BigEndianStreamWriter@cdp@@QEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; cdp::BigEndianStreamWriter::WriteBytesWithCount<uint>(std::vector<uchar> const &)
0x1802ca167  lea     rdx, [rbp+57h+var_88]
0x1802ca16b  lea     rcx, [rbp+57h+var_A0]; this
0x1802ca16f  call    ??$WriteBytesWithCount@I@BigEndianStreamWriter@cdp@@QEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; cdp::BigEndianStreamWriter::WriteBytesWithCount<uint>(std::vector<uchar> const &)
0x1802ca174  lea     rdx, [rbp+57h+var_A0]
0x1802ca178  lea     rcx, [rbp+57h+lpBuffer]
0x1802ca17c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1802ca181  nop
0x1802ca182  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x1802ca185  mov     r8d, [rbp+57h+var_50]
0x1802ca189  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1802ca18d  sub     r8d, edx; nNumberOfBytesToWrite
0x1802ca190  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x1802ca195  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802ca199  mov     rcx, [rsi]; hFile
0x1802ca19c  call    cs:__imp_WriteFile
0x1802ca1a2  test    eax, eax
0x1802ca1a4  jz      short loc_1802CA1B2
0x1802ca1a6  lea     rdx, aTextSuccessful_6; "{\"text\":\"Successfully wrote to Live "...
0x1802ca1ad  lea     ecx, [rbx+4]
0x1802ca1b0  jmp     short loc_1802CA20A
0x1802ca1b2  call    cs:__imp_GetLastError
0x1802ca1b8  test    eax, eax
0x1802ca1ba  jle     short loc_1802CA1C4
0x1802ca1bc  movzx   eax, ax
0x1802ca1bf  or      eax, 80070000h
0x1802ca1c4  mov     [rbp+57h+arg_18], eax
0x1802ca1c7  test    eax, eax
0x1802ca1c9  jns     short loc_1802CA1F2
0x1802ca1cb  mov     [rbp+57h+arg_10], 0C3h
0x1802ca1d2  lea     rax, [rbp+57h+arg_10]
0x1802ca1d6  mov     [rsp+0D0h+lpOverlapped], rax
0x1802ca1db  lea     r9, aProtocoltracec; ".\\protocoltraceclient.cpp"
0x1802ca1e2  lea     r8, [rbp+57h+arg_18]
0x1802ca1e6  lea     rdx, aHr0x08xFileSLi_75; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802ca1ed  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1802ca1f2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1802ca1f6  mov     rcx, rsi
0x1802ca1f9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802ca1fe  lea     rdx, aTextResetProto; "{\"text\":\"Reset ProtocolTraceClient n"...
0x1802ca205  mov     ecx, 3
0x1802ca20a  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1802ca20f  nop
0x1802ca210  lea     rcx, [rbp+57h+lpBuffer]
0x1802ca214  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802ca219  nop
0x1802ca21a  lea     rcx, [rbp+57h+var_A0]
0x1802ca21e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802ca223  nop
0x1802ca224  lea     rcx, [rbp+57h+var_88]
0x1802ca228  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802ca22d  nop
0x1802ca22e  lea     rcx, [rbp+57h+var_70]
0x1802ca232  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802ca237  nop
0x1802ca238  lea     rcx, [rbp+57h+var_40]
0x1802ca23c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802ca241  nop
0x1802ca242  mov     rcx, rdi; _Mtx_t
0x1802ca245  call    cs:__imp__Mtx_unlock
0x1802ca24b  add     rsp, 0B0h
0x1802ca252  pop     r14
0x1802ca254  pop     rdi
0x1802ca255  pop     rsi
0x1802ca256  pop     rbx
0x1802ca257  pop     rbp
0x1802ca258  retn
```
