# Mso::Http::CHttpRequest_WinHttp::ReadBytesFromResponse(void *,ulong,ulong *)

- ea: `0x1800e10d0`
- end: `0x1800e128a`
- name: `?ReadBytesFromResponse@CHttpRequest_WinHttp@Http@Mso@@UEAAJPEAXKPEAK@Z`
- size: `442`
- prototype: `int(Mso::Http::CHttpRequest_WinHttp *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000ffb0`
- `0x180010a84`
- `0x1800d1094`
- `0x1800d113c`
- `0x1800de508`
- `0x1800e10d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e115f`
- `KERNEL32!GetLastError` at `0x1800e1203`
- `KERNEL32!GetLastError` at `0x1800e115f`
- `KERNEL32!GetLastError` at `0x1800e1203`
- `WINHTTP!WinHttpReadData` at `0x1800e11c9`
- `WINHTTP!WinHttpReadData` at `0x1800e11c9`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e1151`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e1151`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Mso::Http::CHttpRequest_WinHttp::ReadBytesFromResponse(
        Mso::Http::CHttpRequest_WinHttp *this,
        char *a2,
        DWORD a3,
        unsigned int *a4)
{
  char *v6; // r13
  DWORD v8; // esi
  unsigned int v9; // r14d
  char *v10; // rax
  void *v11; // rcx
  signed int v12; // ebx
  signed int LastError; // eax
  bool v14; // sf
  void *v15; // rcx
  signed int v16; // eax
  DWORD dwNumberOfBytesRead; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v19[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v20[16]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v21[24]; // [rsp+48h] [rbp-18h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+98h] [rbp+38h] BYREF

  v6 = a2;
  if ( !a2 || !a4 )
    return 2147680265LL;
  *a4 = 0;
  v8 = a3;
  v9 = 0;
  if ( !a3 )
    goto LABEL_25;
  v10 = (char *)this + 232;
  while ( 1 )
  {
    dwNumberOfBytesAvailable = 0;
    std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v20, v10);
    v11 = (void *)*((_QWORD *)this + 15);
    if ( v11 )
    {
      if ( WinHttpQueryDataAvailable(v11, &dwNumberOfBytesAvailable) )
      {
        v12 = 0;
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v12 = -2147287035;
    }
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v20);
    v14 = v12 < 0;
    if ( v12 )
      break;
    if ( !dwNumberOfBytesAvailable )
      goto LABEL_25;
    if ( dwNumberOfBytesAvailable > v8 )
      dwNumberOfBytesAvailable = v8;
    dwNumberOfBytesRead = 0;
    std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v21, (char *)this + 232);
    v15 = (void *)*((_QWORD *)this + 15);
    if ( v15 )
    {
      if ( WinHttpReadData(v15, v6, dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
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
    }
    else
    {
      v12 = -2147287035;
    }
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v21);
    v14 = v12 < 0;
    if ( v12 )
      break;
    v9 += dwNumberOfBytesRead;
    v6 += dwNumberOfBytesRead;
    v8 -= dwNumberOfBytesRead;
    v10 = (char *)this + 232;
    if ( !v8 )
    {
      v14 = 0;
      break;
    }
  }
  if ( !v14 )
  {
LABEL_25:
    LOBYTE(dwNumberOfBytesAvailable) = 10;
    Mso::Http::HttpRequestWinTimings::SetTiming(
      (Mso::Http::CHttpRequest_WinHttp *)((char *)this + 320),
      (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)&dwNumberOfBytesAvailable,
      1);
    *a4 = v9;
    return v9 < a3;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800e10d0  mov     [rsp-28h+arg_0], rbx
0x1800e10d5  mov     [rsp-28h+arg_10], rsi
0x1800e10da  mov     [rsp-28h+arg_18], rdi
0x1800e10df  push    rbp
0x1800e10e0  push    r12
0x1800e10e2  push    r13
0x1800e10e4  push    r14
0x1800e10e6  push    r15
0x1800e10e8  mov     rbp, rsp
0x1800e10eb  sub     rsp, 60h
0x1800e10ef  mov     r15, r9
0x1800e10f2  mov     r12d, r8d
0x1800e10f5  mov     r13, rdx
0x1800e10f8  mov     rdi, rcx
0x1800e10fb  test    rdx, rdx
0x1800e10fe  jz      loc_1800E1267
0x1800e1104  test    r9, r9
0x1800e1107  jz      loc_1800E1267
0x1800e110d  mov     dword ptr [r9], 0
0x1800e1114  mov     esi, r8d
0x1800e1117  xor     r14d, r14d
0x1800e111a  test    r8d, r8d
0x1800e111d  jz      loc_1800E1241
0x1800e1123  lea     rax, [rcx+0E8h]
0x1800e112a  mov     [rbp+dwNumberOfBytesAvailable], 0
0x1800e1131  mov     rdx, rax
0x1800e1134  lea     rcx, [rbp+var_28]
0x1800e1138  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800e113d  mov     rcx, [rdi+78h]; hRequest
0x1800e1141  test    rcx, rcx
0x1800e1144  jnz     short loc_1800E114D
0x1800e1146  mov     ebx, 80030005h
0x1800e114b  jmp     short loc_1800E1174
0x1800e114d  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800e1151  call    cs:__imp_WinHttpQueryDataAvailable
0x1800e1157  test    eax, eax
0x1800e1159  jz      short loc_1800E115F
0x1800e115b  xor     ebx, ebx
0x1800e115d  jmp     short loc_1800E1174
0x1800e115f  call    cs:__imp_GetLastError
0x1800e1165  mov     ebx, eax
0x1800e1167  test    eax, eax
0x1800e1169  jle     short loc_1800E1174
0x1800e116b  movzx   ebx, ax
0x1800e116e  or      ebx, 80070000h
0x1800e1174  lea     rcx, [rbp+var_28]
0x1800e1178  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e117d  test    ebx, ebx
0x1800e117f  jnz     loc_1800E123F
0x1800e1185  mov     eax, [rbp+dwNumberOfBytesAvailable]
0x1800e1188  test    eax, eax
0x1800e118a  jz      loc_1800E1241
0x1800e1190  cmp     eax, esi
0x1800e1192  jbe     short loc_1800E1197
0x1800e1194  mov     [rbp+dwNumberOfBytesAvailable], esi
0x1800e1197  mov     [rbp+dwNumberOfBytesRead], 0
0x1800e119e  lea     rdx, [rdi+0E8h]
0x1800e11a5  lea     rcx, [rbp+var_18]
0x1800e11a9  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800e11ae  mov     rcx, [rdi+78h]; hRequest
0x1800e11b2  test    rcx, rcx
0x1800e11b5  jnz     short loc_1800E11BE
0x1800e11b7  mov     ebx, 80030005h
0x1800e11bc  jmp     short loc_1800E1218
0x1800e11be  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800e11c2  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x1800e11c6  mov     rdx, r13; lpBuffer
0x1800e11c9  call    cs:__imp_WinHttpReadData
0x1800e11cf  test    eax, eax
0x1800e11d1  jz      short loc_1800E1203
0x1800e11d3  xor     ebx, ebx
0x1800e11d5  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e11d8  add     [rdi+0CCh], eax
0x1800e11de  lea     rdx, [rdi+0A8h]
0x1800e11e5  lea     rcx, [rbp+var_38]
0x1800e11e9  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x1800e11ee  mov     rcx, [rbp+var_38]
0x1800e11f2  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e11f5  add     [rcx+14h], eax
0x1800e11f8  lea     rcx, [rbp+var_38]; void *
0x1800e11fc  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800e1201  jmp     short loc_1800E1218
0x1800e1203  call    cs:__imp_GetLastError
0x1800e1209  mov     ebx, eax
0x1800e120b  test    eax, eax
0x1800e120d  jle     short loc_1800E1218
0x1800e120f  movzx   ebx, ax
0x1800e1212  or      ebx, 80070000h
0x1800e1218  lea     rcx, [rbp+var_18]
0x1800e121c  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e1221  test    ebx, ebx
0x1800e1223  jnz     short loc_1800E123F
0x1800e1225  mov     eax, [rbp+dwNumberOfBytesRead]
0x1800e1228  add     r14d, eax
0x1800e122b  add     r13, rax
0x1800e122e  sub     esi, eax
0x1800e1230  lea     rax, [rdi+0E8h]
0x1800e1237  jnz     loc_1800E112A
0x1800e123d  test    ebx, ebx
0x1800e123f  js      short loc_1800E1263
0x1800e1241  mov     byte ptr [rbp+dwNumberOfBytesAvailable], 0Ah
0x1800e1245  lea     rcx, [rdi+140h]; this
0x1800e124c  mov     r8b, 1; bool
0x1800e124f  lea     rdx, [rbp+dwNumberOfBytesAvailable]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e1253  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e1258  mov     [r15], r14d
0x1800e125b  xor     ebx, ebx
0x1800e125d  cmp     r14d, r12d
0x1800e1260  setb    bl
0x1800e1263  mov     eax, ebx
0x1800e1265  jmp     short loc_1800E126C
0x1800e1267  mov     eax, 80030009h
0x1800e126c  lea     r11, [rsp+60h+var_s0]
0x1800e1271  mov     rbx, [r11+30h]
0x1800e1275  mov     rsi, [r11+40h]
0x1800e1279  mov     rdi, [r11+48h]
0x1800e127d  mov     rsp, r11
0x1800e1280  pop     r15
0x1800e1282  pop     r14
0x1800e1284  pop     r13
0x1800e1286  pop     r12
0x1800e1288  pop     rbp
0x1800e1289  retn
```
