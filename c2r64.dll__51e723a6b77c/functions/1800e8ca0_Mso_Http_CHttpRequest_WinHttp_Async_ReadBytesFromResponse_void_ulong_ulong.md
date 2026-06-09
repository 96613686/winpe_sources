# Mso::Http::CHttpRequest_WinHttp_Async::ReadBytesFromResponse(void *,ulong,ulong *)

- ea: `0x1800e8ca0`
- end: `0x1800e8e01`
- name: `?ReadBytesFromResponse@CHttpRequest_WinHttp_Async@Http@Mso@@UEAAJPEAXKPEAK@Z`
- size: `353`
- prototype: `int(Mso::Http::CHttpRequest_WinHttp_Async *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000ffb0`
- `0x180010a84`
- `0x1800e8ca0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e8d14`
- `KERNEL32!GetLastError` at `0x1800e8d9b`
- `KERNEL32!GetLastError` at `0x1800e8d14`
- `KERNEL32!GetLastError` at `0x1800e8d9b`
- `WINHTTP!WinHttpReadData` at `0x1800e8d60`
- `WINHTTP!WinHttpReadData` at `0x1800e8d60`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e8d0a`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e8d0a`

## pseudocode

```c
__int64 __fastcall Mso::Http::CHttpRequest_WinHttp_Async::ReadBytesFromResponse(
        Mso::Http::CHttpRequest_WinHttp_Async *this,
        char *a2,
        DWORD a3,
        unsigned int *a4)
{
  char *v6; // r12
  DWORD v8; // edi
  unsigned int v9; // esi
  void *v10; // rcx
  signed int LastError; // eax
  signed int v12; // ebx
  bool v13; // sf
  DWORD v14; // r8d
  void *v15; // rcx
  signed int v16; // eax
  DWORD dwNumberOfBytesAvailable; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+28h] [rbp-18h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+78h] [rbp+38h] BYREF

  v6 = a2;
  if ( !a2 || !a4 )
    return 2147680265LL;
  *a4 = 0;
  v8 = a3;
  v9 = 0;
  if ( a3 )
  {
    do
    {
      dwNumberOfBytesAvailable = 0;
      v10 = (void *)*((_QWORD *)this + 15);
      if ( !v10 )
        return (unsigned int)-2147287035;
      if ( !WinHttpQueryDataAvailable(v10, &dwNumberOfBytesAvailable) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v13 = v12 < 0;
        if ( v12 )
          goto LABEL_20;
      }
      v14 = dwNumberOfBytesAvailable;
      if ( !dwNumberOfBytesAvailable )
        goto LABEL_21;
      if ( dwNumberOfBytesAvailable > v8 )
      {
        v14 = v8;
        dwNumberOfBytesAvailable = v8;
      }
      dwNumberOfBytesRead = 0;
      v15 = (void *)*((_QWORD *)this + 15);
      if ( !v15 )
        return (unsigned int)-2147287035;
      if ( WinHttpReadData(v15, v6, v14, &dwNumberOfBytesRead) )
      {
        v12 = 0;
        *((_DWORD *)this + 51) += dwNumberOfBytesRead;
        std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
          v19,
          (char *)this + 168);
        *(_DWORD *)(v19[0] + 20LL) += dwNumberOfBytesRead;
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v19);
      }
      else
      {
        v16 = GetLastError();
        v12 = v16;
        if ( v16 > 0 )
          v12 = (unsigned __int16)v16 | 0x80070000;
      }
      v13 = v12 < 0;
      if ( v12 )
        goto LABEL_20;
      v9 += dwNumberOfBytesRead;
      v6 += dwNumberOfBytesRead;
      v8 -= dwNumberOfBytesRead;
    }
    while ( v8 );
    v13 = 0;
LABEL_20:
    if ( v13 )
      return (unsigned int)v12;
  }
LABEL_21:
  *a4 = v9;
  return v9 < a3;
}

```

## disassembly

```asm
0x1800e8ca0  mov     [rsp-28h+arg_0], rbx
0x1800e8ca5  mov     [rsp-28h+arg_10], rsi
0x1800e8caa  mov     [rsp-28h+arg_18], rdi
0x1800e8caf  push    rbp
0x1800e8cb0  push    r12
0x1800e8cb2  push    r13
0x1800e8cb4  push    r14
0x1800e8cb6  push    r15
0x1800e8cb8  mov     rbp, rsp
0x1800e8cbb  sub     rsp, 40h
0x1800e8cbf  mov     r14, r9
0x1800e8cc2  mov     r15d, r8d
0x1800e8cc5  mov     r12, rdx
0x1800e8cc8  mov     r13, rcx
0x1800e8ccb  test    rdx, rdx
0x1800e8cce  jz      loc_1800E8DDE
0x1800e8cd4  test    r9, r9
0x1800e8cd7  jz      loc_1800E8DDE
0x1800e8cdd  mov     dword ptr [r9], 0
0x1800e8ce4  mov     edi, r8d
0x1800e8ce7  xor     esi, esi
0x1800e8ce9  test    r8d, r8d
0x1800e8cec  jz      loc_1800E8DC8
0x1800e8cf2  mov     [rbp+dwNumberOfBytesAvailable], 0
0x1800e8cf9  mov     rcx, [r13+78h]; hRequest
0x1800e8cfd  test    rcx, rcx
0x1800e8d00  jz      loc_1800E8DD7
0x1800e8d06  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800e8d0a  call    cs:__imp_WinHttpQueryDataAvailable
0x1800e8d10  test    eax, eax
0x1800e8d12  jnz     short loc_1800E8D31
0x1800e8d14  call    cs:__imp_GetLastError
0x1800e8d1a  mov     ebx, eax
0x1800e8d1c  test    eax, eax
0x1800e8d1e  jle     short loc_1800E8D29
0x1800e8d20  movzx   ebx, ax
0x1800e8d23  or      ebx, 80070000h
0x1800e8d29  test    ebx, ebx
0x1800e8d2b  jnz     loc_1800E8DC6
0x1800e8d31  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x1800e8d35  test    r8d, r8d
0x1800e8d38  jz      loc_1800E8DC8
0x1800e8d3e  cmp     r8d, edi
0x1800e8d41  jbe     short loc_1800E8D49
0x1800e8d43  mov     r8d, edi; dwNumberOfBytesToRead
0x1800e8d46  mov     [rbp+dwNumberOfBytesAvailable], edi
0x1800e8d49  mov     [rbp+dwNumberOfBytesRead], 0
0x1800e8d50  mov     rcx, [r13+78h]; hRequest
0x1800e8d54  test    rcx, rcx
0x1800e8d57  jz      short loc_1800E8DD7
0x1800e8d59  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800e8d5d  mov     rdx, r12; lpBuffer
0x1800e8d60  call    cs:__imp_WinHttpReadData
0x1800e8d66  test    eax, eax
0x1800e8d68  jz      short loc_1800E8D9B
0x1800e8d6a  xor     ebx, ebx
0x1800e8d6c  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e8d6f  add     [r13+0CCh], eax
0x1800e8d76  lea     rdx, [r13+0A8h]
0x1800e8d7d  lea     rcx, [rbp+var_18]
0x1800e8d81  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x1800e8d86  mov     rcx, [rbp+var_18]
0x1800e8d8a  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e8d8d  add     [rcx+14h], eax
0x1800e8d90  lea     rcx, [rbp+var_18]; void *
0x1800e8d94  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800e8d99  jmp     short loc_1800E8DB0
0x1800e8d9b  call    cs:__imp_GetLastError
0x1800e8da1  mov     ebx, eax
0x1800e8da3  test    eax, eax
0x1800e8da5  jle     short loc_1800E8DB0
0x1800e8da7  movzx   ebx, ax
0x1800e8daa  or      ebx, 80070000h
0x1800e8db0  test    ebx, ebx
0x1800e8db2  jnz     short loc_1800E8DC6
0x1800e8db4  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e8db7  add     esi, eax
0x1800e8db9  add     r12, rax
0x1800e8dbc  sub     edi, eax
0x1800e8dbe  jnz     loc_1800E8CF2
0x1800e8dc4  test    ebx, ebx
0x1800e8dc6  js      short loc_1800E8DD3
0x1800e8dc8  mov     [r14], esi
0x1800e8dcb  xor     ebx, ebx
0x1800e8dcd  cmp     esi, r15d
0x1800e8dd0  setb    bl
0x1800e8dd3  mov     eax, ebx
0x1800e8dd5  jmp     short loc_1800E8DE3
0x1800e8dd7  mov     ebx, 80030005h
0x1800e8ddc  jmp     short loc_1800E8DD3
0x1800e8dde  mov     eax, 80030009h
0x1800e8de3  lea     r11, [rsp+40h+var_s0]
0x1800e8de8  mov     rbx, [r11+30h]
0x1800e8dec  mov     rsi, [r11+40h]
0x1800e8df0  mov     rdi, [r11+48h]
0x1800e8df4  mov     rsp, r11
0x1800e8df7  pop     r15
0x1800e8df9  pop     r14
0x1800e8dfb  pop     r13
0x1800e8dfd  pop     r12
0x1800e8dff  pop     rbp
0x1800e8e00  retn
```
