# CNamedPipeStream::Open(IRDPENCNetStreamEvents *)

- ea: `0x180104370`
- end: `0x180104641`
- name: `?Open@CNamedPipeStream@@UEAAJPEAUIRDPENCNetStreamEvents@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CNamedPipeStream *__hidden this, struct IRDPENCNetStreamEvents *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x1800506ac`
- `0x180104370`
- `0x180104648`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180104623`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180104623`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180104500`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180104500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801045cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801045cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1801045bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1801045bd`

## string_xrefs

- `0x1801045ec`: `Failed to associate I/O completion port with threadpool.`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::Open(CNamedPipeStream *this, struct IRDPENCNetStreamEvents *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 (__fastcall *v8)(_QWORD, __int64 *); // rax
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rax
  char *v17; // rdx
  PTP_IO ThreadpoolIo; // rax
  signed int LastError; // eax
  HMODULE v20; // rcx
  __int64 v22; // [rsp+50h] [rbp-30h] BYREF
  const char *v23; // [rsp+58h] [rbp-28h] BYREF
  const char *v24; // [rsp+60h] [rbp-20h] BYREF
  const char *v25; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-10h] BYREF
  int v27; // [rsp+B0h] [rbp+30h] BYREF
  const char *v28; // [rsp+C0h] [rbp+40h] BYREF
  char *v29; // [rsp+C8h] [rbp+48h] BYREF

  v4 = 0;
  v29 = (char *)this + 80;
  CTSCriticalSection::Lock((CNamedPipeStream *)((char *)this + 80));
  CNamedPipeStream::ReinitializeInternal(this);
  if ( *((_QWORD *)this + 7) != -1 )
    goto LABEL_10;
  v8 = (__int64 (__fastcall *)(_QWORD, __int64 *))*((_QWORD *)this + 29);
  v22 = -1;
  if ( v8 )
  {
    v9 = v8(0, &v22);
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v27 = v9;
        v28 = "Open";
        v26[0] = "Failed to generate a new named pipe";
        v25 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_1801C713A,
          v10,
          v11,
          (__int64)&v25,
          (__int64)v26,
          (__int64)&v27,
          (__int64)&v28);
      }
      goto LABEL_5;
    }
    *((_QWORD *)this + 7) = v22;
LABEL_10:
    if ( a2 != *((struct IRDPENCNetStreamEvents **)this + 27) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 216);
      *((_QWORD *)this + 27) = a2;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 216);
    }
    if ( GetModuleHandleExW(4u, (LPCWSTR)CNamedPipeStream::WT_CompleteNamedPipeIo, (HMODULE *)this + 9) )
    {
      ThreadpoolIo = CreateThreadpoolIo(*((HANDLE *)this + 7), CNamedPipeStream::WT_CompleteNamedPipeIo, this, 0);
      *((_QWORD *)this + 8) = ThreadpoolIo;
      if ( ThreadpoolIo )
      {
        *((_DWORD *)this + 24) = 1;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v16 = "Failed to associate I/O completion port with threadpool.";
          v27 = 288;
          v17 = byte_1801C70E9;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v16 = "Failed to get module handle to itself.";
        v27 = 277;
        v17 = byte_1801C7179;
LABEL_17:
        v26[0] = v16;
        v25 = "Open";
        v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
        v23 = "Error condition failed";
        LODWORD(v28) = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v13,
          (_DWORD)v17,
          v14,
          v15,
          (__int64)&v23,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&v27,
          (__int64)&v25,
          (__int64)v26);
      }
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v29);
    if ( (v4 & 0x80000000) == 0 )
      return v4;
    goto LABEL_25;
  }
  v4 = -2147467260;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v27 = 258;
    v23 = "No valid pipe handle found and no pipe factory provided";
    LODWORD(v28) = -2147467260;
    v24 = "Open";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v26[0] = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1801C7209,
      v6,
      v7,
      (__int64)v26,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v23);
  }
LABEL_5:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v29);
LABEL_25:
  v20 = (HMODULE)*((_QWORD *)this + 9);
  if ( v20 )
  {
    FreeLibrary(v20);
    *((_QWORD *)this + 9) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180104370  push    rbp
0x180104372  push    rbx
0x180104373  push    rsi
0x180104374  push    rdi
0x180104375  push    r14
0x180104377  mov     rbp, rsp
0x18010437a  sub     rsp, 80h
0x180104381  mov     rdi, rcx
0x180104384  mov     r14, rdx
0x180104387  add     rcx, 50h ; 'P'; this
0x18010438b  xor     ebx, ebx
0x18010438d  mov     [rbp+arg_18], rcx
0x180104391  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180104396  mov     rcx, rdi; this
0x180104399  call    ?ReinitializeInternal@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::ReinitializeInternal(void)
0x18010439e  cmp     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x1801043a3  jnz     loc_1801044D1
0x1801043a9  mov     rax, [rdi+0E8h]
0x1801043b0  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x1801043b8  test    rax, rax
0x1801043bb  jnz     loc_180104457
0x1801043c1  mov     eax, cs:CallbackContext
0x1801043c7  mov     ebx, 80004004h
0x1801043cc  cmp     eax, 2
0x1801043cf  jbe     short loc_180104449
0x1801043d1  lea     rax, aNoValidPipeHan; "No valid pipe handle found and no pipe "...
0x1801043d8  mov     [rbp+arg_0], 102h
0x1801043df  mov     [rbp+var_28], rax
0x1801043e3  lea     rdx, byte_1801C7209
0x1801043ea  lea     rax, aOpen; "Open"
0x1801043f1  mov     dword ptr [rbp+arg_10], ebx
0x1801043f4  mov     [rbp+var_20], rax
0x1801043f8  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801043ff  mov     [rbp+var_18], rax
0x180104403  lea     rax, aErrorCondition; "Error condition failed"
0x18010440a  mov     [rbp+var_10], rax
0x18010440e  lea     rax, [rbp+var_28]
0x180104412  mov     [rsp+80h+var_38], rax
0x180104417  lea     rax, [rbp+var_20]
0x18010441b  mov     [rsp+80h+var_40], rax
0x180104420  lea     rax, [rbp+arg_0]
0x180104424  mov     [rsp+80h+var_48], rax
0x180104429  lea     rax, [rbp+var_18]
0x18010442d  mov     [rsp+80h+var_50], rax
0x180104432  lea     rax, [rbp+arg_10]
0x180104436  mov     [rsp+80h+var_58], rax
0x18010443b  lea     rax, [rbp+var_10]
0x18010443f  mov     [rsp+80h+var_60], rax
0x180104444  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180104449  lea     rcx, [rbp+arg_18]; this
0x18010444d  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180104452  jmp     loc_18010461A
0x180104457  lea     rdx, [rbp+var_30]
0x18010445b  xor     ecx, ecx
0x18010445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104462  mov     ebx, eax
0x180104464  test    eax, eax
0x180104466  jns     short loc_1801044C9
0x180104468  mov     ecx, cs:CallbackContext
0x18010446e  cmp     ecx, 3
0x180104471  jbe     short loc_180104449
0x180104473  lea     rax, aOpen; "Open"
0x18010447a  mov     [rbp+arg_0], ebx
0x18010447d  mov     [rbp+arg_10], rax
0x180104481  lea     rdx, word_1801C713A
0x180104488  lea     rax, aFailedToGenera; "Failed to generate a new named pipe"
0x18010448f  mov     [rbp+var_10], rax
0x180104493  lea     rax, aWarningHresult; "Warning HResult failed"
0x18010449a  mov     [rbp+var_18], rax
0x18010449e  lea     rax, [rbp+arg_10]
0x1801044a2  mov     [rsp+80h+var_48], rax
0x1801044a7  lea     rax, [rbp+arg_0]
0x1801044ab  mov     [rsp+80h+var_50], rax
0x1801044b0  lea     rax, [rbp+var_10]
0x1801044b4  mov     [rsp+80h+var_58], rax
0x1801044b9  lea     rax, [rbp+var_18]
0x1801044bd  mov     [rsp+80h+var_60], rax
0x1801044c2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801044c7  jmp     short loc_180104449
0x1801044c9  mov     rax, [rbp+var_30]
0x1801044cd  mov     [rdi+38h], rax
0x1801044d1  lea     rsi, [rdi+0D8h]
0x1801044d8  cmp     r14, [rsi]
0x1801044db  jz      short loc_1801044F0
0x1801044dd  mov     rcx, rsi; void *
0x1801044e0  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1801044e5  mov     rcx, rsi
0x1801044e8  mov     [rsi], r14
0x1801044eb  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1801044f0  lea     r8, [rdi+48h]; phModule
0x1801044f4  mov     ecx, 4; dwFlags
0x1801044f9  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; lpModuleName
0x180104500  call    cs:__imp_GetModuleHandleExW
0x180104506  test    eax, eax
0x180104508  jnz     loc_1801045AC
0x18010450e  call    cs:__imp_GetLastError
0x180104514  mov     ebx, eax
0x180104516  test    eax, eax
0x180104518  jle     short loc_180104523
0x18010451a  movzx   ebx, ax
0x18010451d  or      ebx, 80070000h
0x180104523  mov     eax, cs:CallbackContext
0x180104529  cmp     eax, 2
0x18010452c  jbe     loc_18010460D
0x180104532  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x180104539  mov     [rbp+arg_0], 115h
0x180104540  lea     rdx, byte_1801C7179
0x180104547  mov     [rbp+var_10], rax
0x18010454b  lea     rax, aOpen; "Open"
0x180104552  mov     [rbp+var_18], rax
0x180104556  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010455d  mov     [rbp+var_20], rax
0x180104561  lea     rax, aErrorCondition; "Error condition failed"
0x180104568  mov     [rbp+var_28], rax
0x18010456c  lea     rax, [rbp+var_10]
0x180104570  mov     [rsp+80h+var_38], rax
0x180104575  lea     rax, [rbp+var_18]
0x180104579  mov     [rsp+80h+var_40], rax
0x18010457e  lea     rax, [rbp+arg_0]
0x180104582  mov     [rsp+80h+var_48], rax
0x180104587  lea     rax, [rbp+var_20]
0x18010458b  mov     [rsp+80h+var_50], rax
0x180104590  lea     rax, [rbp+arg_10]
0x180104594  mov     [rsp+80h+var_58], rax
0x180104599  lea     rax, [rbp+var_28]
0x18010459d  mov     [rsp+80h+var_60], rax
0x1801045a2  mov     dword ptr [rbp+arg_10], ebx
0x1801045a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801045aa  jmp     short loc_18010460D
0x1801045ac  mov     rcx, [rdi+38h]; fl
0x1801045b0  lea     rdx, ?WT_CompleteNamedPipeIo@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1801045b7  xor     r9d, r9d; pcbe
0x1801045ba  mov     r8, rdi; pv
0x1801045bd  call    cs:__imp_CreateThreadpoolIo
0x1801045c3  mov     [rdi+40h], rax
0x1801045c7  test    rax, rax
0x1801045ca  jnz     short loc_180104606
0x1801045cc  call    cs:__imp_GetLastError
0x1801045d2  mov     ebx, eax
0x1801045d4  test    eax, eax
0x1801045d6  jle     short loc_1801045E1
0x1801045d8  movzx   ebx, ax
0x1801045db  or      ebx, 80070000h
0x1801045e1  mov     eax, cs:CallbackContext
0x1801045e7  cmp     eax, 2
0x1801045ea  jbe     short loc_18010460D
0x1801045ec  lea     rax, aFailedToAssoci_0; "Failed to associate I/O completion port"...
0x1801045f3  mov     [rbp+arg_0], 120h
0x1801045fa  lea     rdx, byte_1801C70E9
0x180104601  jmp     loc_180104547
0x180104606  mov     dword ptr [rdi+60h], 1
0x18010460d  lea     rcx, [rbp+arg_18]; this
0x180104611  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180104616  test    ebx, ebx
0x180104618  jns     short loc_180104631
0x18010461a  mov     rcx, [rdi+48h]; hLibModule
0x18010461e  test    rcx, rcx
0x180104621  jz      short loc_180104631
0x180104623  call    cs:__imp_FreeLibrary
0x180104629  mov     qword ptr [rdi+48h], 0
0x180104631  mov     eax, ebx
0x180104633  add     rsp, 80h
0x18010463a  pop     r14
0x18010463c  pop     rdi
0x18010463d  pop     rsi
0x18010463e  pop     rbx
0x18010463f  pop     rbp
0x180104640  retn
```
