# CWPPLoggerConfig::StartTraceW(void)

- ea: `0x18007f558`
- end: `0x18007f80d`
- name: `?StartTraceW@CWPPLoggerConfig@@AEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003d6b8`
- `0x18007f274`

## callees

- `0x180003660`
- `0x180003978`
- `0x180018200`
- `0x18001aa50`
- `0x18004b460`
- `0x18004bf44`
- `0x18007f474`
- `0x18007f558`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007f5b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007f5b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007f62b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007f62b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18007f6ea`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18007f71d`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18007f6ea`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18007f71d`

## pseudocode

```c
__int64 __fastcall CWPPLoggerConfig::StartTraceW(CWPPLoggerConfig *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // r15
  signed int started; // eax
  int v7; // r8d
  int v8; // r9d
  ULONG v9; // esi
  int v10; // ecx
  __int64 v11; // rax
  const char *v12; // rcx
  int wYear; // [rsp+28h] [rbp-D8h]
  int wMonth; // [rsp+30h] [rbp-D0h]
  int wDay; // [rsp+38h] [rbp-C8h]
  int wHour; // [rsp+40h] [rbp-C0h]
  int wMinute; // [rsp+48h] [rbp-B8h]
  int wSecond; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  const char *v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v24; // [rsp+80h] [rbp-80h] BYREF
  const char *v25; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  SystemTime = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    GetSystemDirectoryW(Buffer, 0x104u);
    **((_DWORD **)this + 4) = *((_DWORD *)this + 10);
    *(_DWORD *)(*((_QWORD *)this + 4) + 44LL) = 0x20000;
    *(_DWORD *)(*((_QWORD *)this + 4) + 40LL) = 2;
    if ( *((_DWORD *)this + 2) )
      *(_OWORD *)(*((_QWORD *)this + 4) + 24LL) = *(_OWORD *)*((_QWORD *)this + 2);
    *(_DWORD *)(*((_QWORD *)this + 4) + 72LL) = 0xFFFF;
    *(_DWORD *)(*((_QWORD *)this + 4) + 116LL) = 120;
    *(_DWORD *)(*((_QWORD *)this + 4) + 112LL) = *(_DWORD *)(*((_QWORD *)this + 4) + 116LL) + 520;
    v3 = *((_QWORD *)this + 4);
    v4 = (unsigned __int16 *)(v3 + *(unsigned int *)(v3 + 116));
    v5 = (unsigned __int16 *)(v3 + *(unsigned int *)(v3 + 112));
    GetSystemTime(&SystemTime);
    StringCchCopyW(v4, 0x104u, *(const unsigned __int16 **)this);
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    wYear = SystemTime.wYear;
    StringCchPrintfW(
      v5,
      0x104u,
      L"%s\\LogFiles\\WMI\\%s-%04d%02d%02d-%02d%02d%02d.etl",
      Buffer,
      *(_QWORD *)this,
      wYear,
      wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond);
    *(_DWORD *)(*((_QWORD *)this + 4) + 48LL) = 20;
    *(_DWORD *)(*((_QWORD *)this + 4) + 60LL) = *((_DWORD *)this + 13);
    *(_DWORD *)(*((_QWORD *)this + 4) + 52LL) = 10;
    *(_DWORD *)(*((_QWORD *)this + 4) + 68LL) = 60;
    *(_DWORD *)(*((_QWORD *)this + 4) + 64LL) = 2;
    if ( CWPPLoggerConfig::IsTraceToDebugger(this) )
      *(_DWORD *)(*((_QWORD *)this + 4) + 64LL) |= 0x80000u;
    started = StartTraceW((PTRACEHANDLE)this + 3, *(LPCWSTR *)this, *((PEVENT_TRACE_PROPERTIES *)this + 4));
    v9 = started;
    if ( started > 0 )
      v2 = (unsigned __int16)started | 0x80070000;
    else
      v2 = started;
    if ( started == 112 )
    {
      *(_DWORD *)(*((_QWORD *)this + 4) + 60LL) = 1;
      v9 = StartTraceW((PTRACEHANDLE)this + 3, *(LPCWSTR *)this, *((PEVENT_TRACE_PROPERTIES *)this + 4));
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v20 = *((unsigned int *)this + 13);
        v21 = "Specified buffer size is too large, using something smaller. Buffer size set to 1MB (which ends up being 2"
              "01MB according to the API)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)byte_1800C84EB,
          v7,
          v8,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    if ( v9 && (unsigned int)dword_1800DA020 > 2 )
    {
      v11 = *((_QWORD *)this + 4);
      v23 = v5;
      v12 = (const char *)*(unsigned int *)(v11 + 60);
      v22 = *((_QWORD *)this + 3);
      v24 = *(_DWORD **)this;
      v25 = "StartTraceW failed with these values";
      v21 = v12;
      LODWORD(v20) = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)qword_1800C82F8,
        v7,
        v8,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18007f558  push    rbp
0x18007f55a  push    rbx
0x18007f55b  push    rsi
0x18007f55c  push    rdi
0x18007f55d  push    r14
0x18007f55f  push    r15
0x18007f561  lea     rbp, [rsp-1C8h]
0x18007f569  sub     rsp, 2C8h
0x18007f570  mov     rax, cs:__security_cookie
0x18007f577  xor     rax, rsp
0x18007f57a  mov     [rbp+1F0h+var_40], rax
0x18007f581  mov     rdi, rcx
0x18007f584  mov     r15d, 208h
0x18007f58a  mov     r8d, r15d; Size
0x18007f58d  lea     rcx, [rbp+1F0h+Buffer]; void *
0x18007f591  xor     edx, edx; Val
0x18007f593  xor     ebx, ebx
0x18007f595  call    memset_0
0x18007f59a  lea     r14, [rdi+18h]
0x18007f59e  xorps   xmm0, xmm0
0x18007f5a1  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18007f5a5  cmp     [r14], rbx
0x18007f5a8  jnz     loc_18007F7EC
0x18007f5ae  mov     esi, 104h
0x18007f5b3  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18007f5b7  mov     edx, esi; uSize
0x18007f5b9  call    cs:__imp_GetSystemDirectoryW
0x18007f5bf  mov     eax, [rdi+28h]
0x18007f5c2  mov     rcx, [rdi+20h]
0x18007f5c6  mov     [rcx], eax
0x18007f5c8  mov     rax, [rdi+20h]
0x18007f5cc  mov     dword ptr [rax+2Ch], 20000h
0x18007f5d3  mov     rax, [rdi+20h]
0x18007f5d7  mov     dword ptr [rax+28h], 2
0x18007f5de  cmp     [rdi+8], ebx
0x18007f5e1  jbe     short loc_18007F5F3
0x18007f5e3  mov     rax, [rdi+10h]
0x18007f5e7  movups  xmm0, xmmword ptr [rax]
0x18007f5ea  mov     rax, [rdi+20h]
0x18007f5ee  movdqu  xmmword ptr [rax+18h], xmm0
0x18007f5f3  mov     rax, [rdi+20h]
0x18007f5f7  mov     dword ptr [rax+48h], 0FFFFh
0x18007f5fe  mov     rax, [rdi+20h]
0x18007f602  mov     dword ptr [rax+74h], 78h ; 'x'
0x18007f609  mov     rcx, [rdi+20h]
0x18007f60d  mov     eax, [rcx+74h]
0x18007f610  add     eax, r15d
0x18007f613  mov     [rcx+70h], eax
0x18007f616  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18007f61a  mov     rdx, [rdi+20h]
0x18007f61e  mov     ebx, [rdx+74h]
0x18007f621  mov     r15d, [rdx+70h]
0x18007f625  add     rbx, rdx
0x18007f628  add     r15, rdx
0x18007f62b  call    cs:__imp_GetSystemTime
0x18007f631  mov     r8, [rdi]; unsigned __int16 *
0x18007f634  mov     rdx, rsi; unsigned __int64
0x18007f637  mov     rcx, rbx; unsigned __int16 *
0x18007f63a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007f63f  movzx   eax, [rbp+1F0h+SystemTime.wMinute]
0x18007f643  mov     rdx, rsi; unsigned __int64
0x18007f646  movzx   ecx, [rbp+1F0h+SystemTime.wHour]
0x18007f64a  movzx   r8d, [rbp+1F0h+SystemTime.wDay]
0x18007f64f  movzx   r9d, [rbp+1F0h+SystemTime.wMonth]
0x18007f654  movzx   r10d, [rbp+1F0h+SystemTime.wSecond]
0x18007f659  movzx   r11d, [rbp+1F0h+SystemTime.wYear]
0x18007f65e  mov     [rsp+2F0h+var_2A0], r10d
0x18007f663  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x18007f667  mov     rax, [rdi]
0x18007f66a  mov     dword ptr [rsp+2F0h+var_2B0], ecx
0x18007f66e  mov     rcx, r15; unsigned __int16 *
0x18007f671  mov     dword ptr [rsp+2F0h+var_2B8], r8d
0x18007f676  lea     r8, aSLogfilesWmiS0; "%s\\LogFiles\\WMI\\%s-%04d%02d%02d-%02d"...
0x18007f67d  mov     dword ptr [rsp+2F0h+var_2C0], r9d
0x18007f682  lea     r9, [rbp+1F0h+Buffer]
0x18007f686  mov     dword ptr [rsp+2F0h+var_2C8], r11d
0x18007f68b  mov     [rsp+2F0h+var_2D0], rax
0x18007f690  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f695  mov     rax, [rdi+20h]
0x18007f699  mov     dword ptr [rax+30h], 14h
0x18007f6a0  mov     rcx, [rdi+20h]
0x18007f6a4  mov     eax, [rdi+34h]
0x18007f6a7  mov     [rcx+3Ch], eax
0x18007f6aa  mov     rcx, rdi; this
0x18007f6ad  mov     rax, [rdi+20h]
0x18007f6b1  mov     dword ptr [rax+34h], 0Ah
0x18007f6b8  mov     rax, [rdi+20h]
0x18007f6bc  mov     dword ptr [rax+44h], 3Ch ; '<'
0x18007f6c3  mov     rax, [rdi+20h]
0x18007f6c7  mov     dword ptr [rax+40h], 2
0x18007f6ce  call    ?IsTraceToDebugger@CWPPLoggerConfig@@QEBAEXZ; CWPPLoggerConfig::IsTraceToDebugger(void)
0x18007f6d3  test    al, al
0x18007f6d5  jz      short loc_18007F6E0
0x18007f6d7  mov     rax, [rdi+20h]
0x18007f6db  bts     dword ptr [rax+40h], 13h
0x18007f6e0  mov     r8, [rdi+20h]; Properties
0x18007f6e4  mov     rcx, r14; TraceHandle
0x18007f6e7  mov     rdx, [rdi]; InstanceName
0x18007f6ea  call    cs:__imp_StartTraceW
0x18007f6f0  mov     esi, eax
0x18007f6f2  test    eax, eax
0x18007f6f4  jg      short loc_18007F6FA
0x18007f6f6  mov     ebx, eax
0x18007f6f8  jmp     short loc_18007F703
0x18007f6fa  movzx   ebx, ax
0x18007f6fd  or      ebx, 80070000h
0x18007f703  cmp     eax, 70h ; 'p'
0x18007f706  jnz     short loc_18007F764
0x18007f708  mov     rax, [rdi+20h]
0x18007f70c  mov     rcx, r14; TraceHandle
0x18007f70f  mov     dword ptr [rax+3Ch], 1
0x18007f716  mov     r8, [rdi+20h]; Properties
0x18007f71a  mov     rdx, [rdi]; InstanceName
0x18007f71d  call    cs:__imp_StartTraceW
0x18007f723  mov     esi, eax
0x18007f725  mov     eax, cs:dword_1800DA020
0x18007f72b  cmp     eax, 2
0x18007f72e  jbe     short loc_18007F764
0x18007f730  mov     eax, [rdi+34h]
0x18007f733  lea     rdx, byte_1800C84EB
0x18007f73a  mov     [rsp+2F0h+var_290], rax
0x18007f73f  lea     rax, aSpecifiedBuffe; "Specified buffer size is too large, usi"...
0x18007f746  mov     [rsp+2F0h+var_288], rax
0x18007f74b  lea     rax, [rsp+2F0h+var_290]
0x18007f750  mov     [rsp+2F0h+var_2C8], rax
0x18007f755  lea     rax, [rsp+2F0h+var_288]
0x18007f75a  mov     [rsp+2F0h+var_2D0], rax
0x18007f75f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18007f764  test    esi, esi
0x18007f766  jz      loc_18007F7EC
0x18007f76c  mov     eax, cs:dword_1800DA020
0x18007f772  cmp     eax, 2
0x18007f775  jbe     short loc_18007F7EC
0x18007f777  mov     rax, [rdi+20h]
0x18007f77b  lea     rdx, qword_1800C82F8
0x18007f782  mov     [rsp+2F0h+var_278], r15
0x18007f787  mov     ecx, [rax+3Ch]
0x18007f78a  mov     rax, [r14]
0x18007f78d  mov     [rsp+2F0h+var_280], rax
0x18007f792  mov     rax, [rdi]
0x18007f795  mov     [rbp+1F0h+var_270], rax
0x18007f799  lea     rax, aStarttracewFai; "StartTraceW failed with these values"
0x18007f7a0  mov     [rbp+1F0h+var_268], rax
0x18007f7a4  lea     rax, [rsp+2F0h+var_288]
0x18007f7a9  mov     [rsp+2F0h+var_2A8], rax
0x18007f7ae  lea     rax, [rsp+2F0h+var_280]
0x18007f7b3  mov     [rsp+2F0h+var_2B0], rax
0x18007f7b8  lea     rax, [rsp+2F0h+var_278]
0x18007f7bd  mov     [rsp+2F0h+var_2B8], rax
0x18007f7c2  lea     rax, [rsp+2F0h+var_290]
0x18007f7c7  mov     [rsp+2F0h+var_2C0], rax
0x18007f7cc  lea     rax, [rbp+1F0h+var_270]
0x18007f7d0  mov     [rsp+2F0h+var_2C8], rax
0x18007f7d5  lea     rax, [rbp+1F0h+var_268]
0x18007f7d9  mov     [rsp+2F0h+var_2D0], rax
0x18007f7de  mov     [rsp+2F0h+var_288], rcx
0x18007f7e3  mov     dword ptr [rsp+2F0h+var_290], ebx
0x18007f7e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18007f7ec  mov     eax, ebx
0x18007f7ee  mov     rcx, [rbp+1F0h+var_40]
0x18007f7f5  xor     rcx, rsp; StackCookie
0x18007f7f8  call    __security_check_cookie
0x18007f7fd  add     rsp, 2C8h
0x18007f804  pop     r15
0x18007f806  pop     r14
0x18007f808  pop     rdi
0x18007f809  pop     rsi
0x18007f80a  pop     rbx
0x18007f80b  pop     rbp
0x18007f80c  retn
```
