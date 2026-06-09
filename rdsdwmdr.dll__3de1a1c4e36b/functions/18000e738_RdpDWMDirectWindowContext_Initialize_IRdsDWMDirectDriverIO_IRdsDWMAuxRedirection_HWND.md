# RdpDWMDirectWindowContext::Initialize(IRdsDWMDirectDriverIO *,IRdsDWMAuxRedirection *,HWND__ *)

- ea: `0x18000e738`
- end: `0x18000ea09`
- name: `?Initialize@RdpDWMDirectWindowContext@@IEAAJPEAUIRdsDWMDirectDriverIO@@PEAUIRdsDWMAuxRedirection@@PEAUHWND__@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, struct IRdsDWMDirectDriverIO *, struct IRdsDWMAuxRedirection *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d6ac`

## callees

- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180005c20`
- `0x18000d56c`
- `0x18000e738`
- `0x18000f068`
- `0x18000f08c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89e`
- `GDI32!CreateCompatibleDC` at `0x18000e88b`
- `GDI32!CreateCompatibleDC` at `0x18000e88b`

## string_xrefs

- `0x18000e780`: `Called to create a window context with NULL hwnd`
- `0x18000e819`: `Called to create a window context with no driverIO object`
- `0x18000e8f3`: `Failed to create a memory DC`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::Initialize(
        RdpDWMDirectWindowContext *this,
        struct IRdsDWMDirectDriverIO *a2,
        struct IRdsDWMAuxRedirection *a3,
        __int64 a4)
{
  unsigned int v8; // ebx
  int *v9; // rdx
  const unsigned __int16 **v10; // rax
  HDC CompatibleDC; // rax
  int v12; // r9d
  signed int LastError; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // eax
  const char **v22; // [rsp+38h] [rbp-29h]
  const char **v23; // [rsp+48h] [rbp-19h]
  const unsigned __int16 **v24; // [rsp+50h] [rbp-11h]
  int v25; // [rsp+58h] [rbp-9h] BYREF
  const char *v26; // [rsp+60h] [rbp-1h] BYREF
  const char *v27; // [rsp+68h] [rbp+7h] BYREF
  const char *v28; // [rsp+70h] [rbp+Fh] BYREF
  const unsigned __int16 *v29[8]; // [rsp+78h] [rbp+17h] BYREF
  unsigned int v30; // [rsp+E0h] [rbp+7Fh] BYREF

  v30 = 0;
  if ( a4 )
  {
    if ( !a2 )
    {
      v8 = -2147418113;
      if ( (unsigned int)dword_180044008 <= 2 )
        return v8;
      v30 = 158;
      v29[0] = (const unsigned __int16 *)"Called to create a window context with no driverIO object";
      v9 = (int *)&byte_1800399D7;
      v28 = "Initialize";
      v27 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v26 = "Error condition failed";
      v24 = v29;
      v23 = &v28;
      v22 = &v27;
      v10 = (const unsigned __int16 **)&v26;
      goto LABEL_4;
    }
    CompatibleDC = CreateCompatibleDC(0);
    *((_QWORD *)this + 7) = CompatibleDC;
    if ( CompatibleDC )
    {
      v8 = 0;
      v20 = (int)ReadRegistryUINT(L"SOFTWARE\\Microsoft\\HVSI", L"LimitRDPSharedMemory", &v30, v12) >= 0 && v30 != 0;
      *((_DWORD *)this + 172) = v20;
      if ( (unsigned int)dword_180044008 > 4 )
      {
        v30 = *((_DWORD *)this + 172);
        v29[0] = (const unsigned __int16 *)"Lazy alloc setting: %d";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)word_18003995A,
          v18,
          v19,
          v29,
          (__int64)&v30);
      }
      *((_QWORD *)this + 8) = a4;
      if ( a2 != *((struct IRdsDWMDirectDriverIO **)this + 82) )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 656);
        *((_QWORD *)this + 82) = a2;
        TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 656);
      }
      if ( a3 != *((struct IRdsDWMAuxRedirection **)this + 83) )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 664);
        *((_QWORD *)this + 83) = a3;
        if ( a3 )
          (*(void (__fastcall **)(struct IRdsDWMAuxRedirection *))(*(_QWORD *)a3 + 8LL))(a3);
      }
      RdpDWMDirectWindowContext::CreateDebugObjects(this);
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
        v8 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v30 = 161;
        v29[0] = (const unsigned __int16 *)"Initialize";
        v25 = v8;
        v28 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
        v27 = "Failed to create a memory DC";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v14,
          (__int64)word_180039992,
          v15,
          v16,
          (const unsigned __int16 **)&v27,
          (__int64)&v25,
          (const unsigned __int16 **)&v28,
          (__int64)&v30,
          v29);
      }
    }
  }
  else
  {
    v8 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v30 = 157;
      v26 = "Called to create a window context with NULL hwnd";
      v9 = &dword_180039A24;
      v27 = "Initialize";
      v28 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
      v29[0] = (const unsigned __int16 *)"Error condition failed";
      v24 = (const unsigned __int16 **)&v26;
      v23 = &v27;
      v22 = &v28;
      v10 = v29;
LABEL_4:
      v25 = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        2147549183LL,
        (__int64)v9,
        (__int64)a3,
        a4,
        v10,
        (__int64)&v25,
        (const unsigned __int16 **)v22,
        (__int64)&v30,
        (const unsigned __int16 **)v23,
        v24);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000e738  mov     r11, rsp
0x18000e73b  push    rbp
0x18000e73c  push    rbx
0x18000e73d  push    rsi
0x18000e73e  push    rdi
0x18000e73f  push    r14
0x18000e741  push    r15
0x18000e743  lea     rbp, [r11-5Fh]
0x18000e747  sub     rsp, 88h
0x18000e74e  mov     [rbp+57h+arg_18], 0
0x18000e755  mov     r14, r9
0x18000e758  mov     rsi, r8
0x18000e75b  mov     r15, rdx
0x18000e75e  mov     rdi, rcx
0x18000e761  test    r9, r9
0x18000e764  jnz     loc_18000E7FA
0x18000e76a  mov     eax, cs:dword_180044008
0x18000e770  mov     ecx, 8000FFFFh
0x18000e775  mov     ebx, ecx
0x18000e777  cmp     eax, 2
0x18000e77a  jbe     loc_18000E9F7
0x18000e780  lea     rax, aCalledToCreate_0; "Called to create a window context with "...
0x18000e787  mov     [rbp+57h+arg_18], 9Dh
0x18000e78e  mov     [rbp+57h+var_58], rax
0x18000e792  lea     rdx, dword_180039A24
0x18000e799  lea     rax, aInitialize; "Initialize"
0x18000e7a0  mov     [rbp+57h+var_50], rax
0x18000e7a4  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000e7ab  mov     [rbp+57h+var_48], rax
0x18000e7af  lea     rax, aErrorCondition; "Error condition failed"
0x18000e7b6  mov     [rbp+57h+var_40], rax
0x18000e7ba  lea     rax, [rbp+57h+var_58]
0x18000e7be  mov     [r11-70h], rax
0x18000e7c2  lea     rax, [rbp+57h+var_50]
0x18000e7c6  mov     [r11-78h], rax
0x18000e7ca  lea     rax, [rbp+57h+arg_18]
0x18000e7ce  mov     [r11-80h], rax
0x18000e7d2  lea     rax, [rbp+57h+var_48]
0x18000e7d6  mov     [rsp+0B0h+var_80], rax
0x18000e7db  lea     rax, [rbp+57h+var_60]
0x18000e7df  mov     [rsp+0B0h+var_88], rax
0x18000e7e4  lea     rax, [rbp+57h+var_40]
0x18000e7e8  mov     [rsp+0B0h+var_90], rax
0x18000e7ed  mov     [rbp+57h+var_60], ecx
0x18000e7f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000e7f5  jmp     loc_18000E9F7
0x18000e7fa  test    r15, r15
0x18000e7fd  jnz     loc_18000E889
0x18000e803  mov     eax, cs:dword_180044008
0x18000e809  mov     ecx, 8000FFFFh
0x18000e80e  mov     ebx, ecx
0x18000e810  cmp     eax, 2
0x18000e813  jbe     loc_18000E9F7
0x18000e819  lea     rax, aCalledToCreate; "Called to create a window context with "...
0x18000e820  mov     [rbp+57h+arg_18], 9Eh
0x18000e827  mov     [rbp+57h+var_40], rax
0x18000e82b  lea     rdx, byte_1800399D7
0x18000e832  lea     rax, aInitialize; "Initialize"
0x18000e839  mov     [rbp+57h+var_48], rax
0x18000e83d  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000e844  mov     [rbp+57h+var_50], rax
0x18000e848  lea     rax, aErrorCondition; "Error condition failed"
0x18000e84f  mov     [rbp+57h+var_58], rax
0x18000e853  lea     rax, [rbp+57h+var_40]
0x18000e857  mov     [rsp+48h], rax
0x18000e85c  lea     rax, [rbp+57h+var_48]
0x18000e860  mov     [rsp+0B0h+var_70], rax
0x18000e865  lea     rax, [rbp+57h+arg_18]
0x18000e869  mov     [rsp+0B0h+var_78], rax
0x18000e86e  lea     rax, [rbp+57h+var_50]
0x18000e872  mov     [rsp+0B0h+var_80], rax
0x18000e877  lea     rax, [rbp+57h+var_60]
0x18000e87b  mov     [rsp+0B0h+var_88], rax
0x18000e880  lea     rax, [rbp+57h+var_58]
0x18000e884  jmp     loc_18000E7E8
0x18000e889  xor     ecx, ecx; hdc
0x18000e88b  call    cs:__imp_CreateCompatibleDC
0x18000e891  mov     [rdi+38h], rax
0x18000e895  test    rax, rax
0x18000e898  jnz     loc_18000E935
0x18000e89e  call    cs:__imp_GetLastError
0x18000e8a4  mov     ebx, eax
0x18000e8a6  test    eax, eax
0x18000e8a8  jle     short loc_18000E8B3
0x18000e8aa  movzx   ebx, ax
0x18000e8ad  or      ebx, 80070000h
0x18000e8b3  test    ebx, ebx
0x18000e8b5  mov     eax, 80004005h
0x18000e8ba  cmovns  ebx, eax
0x18000e8bd  mov     eax, cs:dword_180044008
0x18000e8c3  cmp     eax, 2
0x18000e8c6  jbe     loc_18000E9F7
0x18000e8cc  lea     rax, aInitialize; "Initialize"
0x18000e8d3  mov     [rbp+57h+arg_18], 0A1h
0x18000e8da  mov     [rbp+57h+var_40], rax
0x18000e8de  lea     rdx, word_180039992
0x18000e8e5  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000e8ec  mov     [rbp+57h+var_60], ebx
0x18000e8ef  mov     [rbp+57h+var_48], rax
0x18000e8f3  lea     rax, aFailedToCreate_8; "Failed to create a memory DC"
0x18000e8fa  mov     [rbp+57h+var_50], rax
0x18000e8fe  lea     rax, [rbp+57h+var_40]
0x18000e902  mov     [rsp+0B0h+var_70], rax
0x18000e907  lea     rax, [rbp+57h+arg_18]
0x18000e90b  mov     [rsp+0B0h+var_78], rax
0x18000e910  lea     rax, [rbp+57h+var_48]
0x18000e914  mov     [rsp+0B0h+var_80], rax
0x18000e919  lea     rax, [rbp+57h+var_60]
0x18000e91d  mov     [rsp+0B0h+var_88], rax
0x18000e922  lea     rax, [rbp+57h+var_50]
0x18000e926  mov     [rsp+0B0h+var_90], rax
0x18000e92b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e930  jmp     loc_18000E9F7
0x18000e935  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x18000e939  xor     ebx, ebx
0x18000e93b  lea     rdx, aLimitrdpshared; "LimitRDPSharedMemory"
0x18000e942  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HVSI"
0x18000e949  call    ?ReadRegistryUINT@@YAJPEAG0PEAI@Z; ReadRegistryUINT(ushort *,ushort *,uint *)
0x18000e94e  test    eax, eax
0x18000e950  jns     short loc_18000E956
0x18000e952  xor     eax, eax
0x18000e954  jmp     short loc_18000E95E
0x18000e956  xor     eax, eax
0x18000e958  cmp     [rbp+57h+arg_18], eax
0x18000e95b  setnz   al
0x18000e95e  mov     [rdi+2B0h], eax
0x18000e964  mov     eax, cs:dword_180044008
0x18000e96a  cmp     eax, 4
0x18000e96d  jbe     short loc_18000E9A1
0x18000e96f  mov     eax, [rdi+2B0h]
0x18000e975  lea     rdx, word_18003995A
0x18000e97c  mov     [rbp+57h+arg_18], eax
0x18000e97f  lea     rax, aLazyAllocSetti; "Lazy alloc setting: %d"
0x18000e986  mov     [rbp+57h+var_40], rax
0x18000e98a  lea     rax, [rbp+57h+arg_18]
0x18000e98e  mov     [rsp+0B0h+var_88], rax
0x18000e993  lea     rax, [rbp+57h+var_40]
0x18000e997  mov     [rsp+0B0h+var_90], rax
0x18000e99c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000e9a1  mov     [rdi+40h], r14
0x18000e9a5  lea     r14, [rdi+290h]
0x18000e9ac  cmp     r15, [r14]
0x18000e9af  jz      short loc_18000E9C4
0x18000e9b1  mov     rcx, r14
0x18000e9b4  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18000e9b9  mov     rcx, r14
0x18000e9bc  mov     [r14], r15
0x18000e9bf  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18000e9c4  lea     r14, [rdi+298h]
0x18000e9cb  cmp     rsi, [r14]
0x18000e9ce  jz      short loc_18000E9EF
0x18000e9d0  mov     rcx, r14
0x18000e9d3  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18000e9d8  mov     [r14], rsi
0x18000e9db  test    rsi, rsi
0x18000e9de  jz      short loc_18000E9EF
0x18000e9e0  mov     rcx, [rsi]
0x18000e9e3  mov     rax, [rcx+8]
0x18000e9e7  mov     rcx, rsi
0x18000e9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ef  mov     rcx, rdi; this
0x18000e9f2  call    ?CreateDebugObjects@RdpDWMDirectWindowContext@@IEAAXXZ; RdpDWMDirectWindowContext::CreateDebugObjects(void)
0x18000e9f7  mov     eax, ebx
0x18000e9f9  add     rsp, 88h
0x18000ea00  pop     r15
0x18000ea02  pop     r14
0x18000ea04  pop     rdi
0x18000ea05  pop     rsi
0x18000ea06  pop     rbx
0x18000ea07  pop     rbp
0x18000ea08  retn
```
