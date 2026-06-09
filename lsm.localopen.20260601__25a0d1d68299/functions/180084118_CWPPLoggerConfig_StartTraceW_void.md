# CWPPLoggerConfig::StartTraceW(void)

- ea: `0x180084118`
- end: `0x1800843e6`
- name: `?StartTraceW@CWPPLoggerConfig@@AEAAJXZ`
- size: `718`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003fdec`
- `0x180083e28`

## callees

- `0x180003680`
- `0x18000399c`
- `0x180009580`
- `0x18000c17c`
- `0x18004e850`
- `0x18004f354`
- `0x180084030`
- `0x180084118`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180084179`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180084179`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800841f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800841f1`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800842b6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800842ef`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800842b6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800842ef`

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
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v20 = *((unsigned int *)this + 13);
        v21 = "Specified buffer size is too large, using something smaller. Buffer size set to 1MB (which ends up being 2"
              "01MB according to the API)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)byte_1800CD673,
          v7,
          v8,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    if ( v9 && (unsigned int)dword_1800DF020 > 2 )
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
        (unsigned int)qword_1800CD480,
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
0x180084118  push    rbp
0x18008411a  push    rbx
0x18008411b  push    rsi
0x18008411c  push    rdi
0x18008411d  push    r14
0x18008411f  push    r15
0x180084121  lea     rbp, [rsp-1C8h]
0x180084129  sub     rsp, 2C8h
0x180084130  mov     rax, cs:__security_cookie
0x180084137  xor     rax, rsp
0x18008413a  mov     [rbp+1F0h+var_40], rax
0x180084141  mov     rdi, rcx
0x180084144  mov     r15d, 208h
0x18008414a  mov     r8d, r15d; Size
0x18008414d  lea     rcx, [rbp+1F0h+Buffer]; void *
0x180084151  xor     edx, edx; Val
0x180084153  xor     ebx, ebx
0x180084155  call    memset_0
0x18008415a  lea     r14, [rdi+18h]
0x18008415e  xorps   xmm0, xmm0
0x180084161  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x180084165  cmp     [r14], rbx
0x180084168  jnz     loc_1800843C4
0x18008416e  mov     esi, 104h
0x180084173  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x180084177  mov     edx, esi; uSize
0x180084179  call    cs:__imp_GetSystemDirectoryW
0x180084180  nop     dword ptr [rax+rax+00h]
0x180084185  mov     eax, [rdi+28h]
0x180084188  mov     rcx, [rdi+20h]
0x18008418c  mov     [rcx], eax
0x18008418e  mov     rax, [rdi+20h]
0x180084192  mov     dword ptr [rax+2Ch], 20000h
0x180084199  mov     rax, [rdi+20h]
0x18008419d  mov     dword ptr [rax+28h], 2
0x1800841a4  cmp     [rdi+8], ebx
0x1800841a7  jbe     short loc_1800841B9
0x1800841a9  mov     rax, [rdi+10h]
0x1800841ad  movups  xmm0, xmmword ptr [rax]
0x1800841b0  mov     rax, [rdi+20h]
0x1800841b4  movdqu  xmmword ptr [rax+18h], xmm0
0x1800841b9  mov     rax, [rdi+20h]
0x1800841bd  mov     dword ptr [rax+48h], 0FFFFh
0x1800841c4  mov     rax, [rdi+20h]
0x1800841c8  mov     dword ptr [rax+74h], 78h ; 'x'
0x1800841cf  mov     rcx, [rdi+20h]
0x1800841d3  mov     eax, [rcx+74h]
0x1800841d6  add     eax, r15d
0x1800841d9  mov     [rcx+70h], eax
0x1800841dc  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x1800841e0  mov     rdx, [rdi+20h]
0x1800841e4  mov     ebx, [rdx+74h]
0x1800841e7  mov     r15d, [rdx+70h]
0x1800841eb  add     rbx, rdx
0x1800841ee  add     r15, rdx
0x1800841f1  call    cs:__imp_GetSystemTime
0x1800841f8  nop     dword ptr [rax+rax+00h]
0x1800841fd  mov     r8, [rdi]; unsigned __int16 *
0x180084200  mov     rdx, rsi; unsigned __int64
0x180084203  mov     rcx, rbx; unsigned __int16 *
0x180084206  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008420b  movzx   eax, [rbp+1F0h+SystemTime.wMinute]
0x18008420f  mov     rdx, rsi; unsigned __int64
0x180084212  movzx   ecx, [rbp+1F0h+SystemTime.wHour]
0x180084216  movzx   r8d, [rbp+1F0h+SystemTime.wDay]
0x18008421b  movzx   r9d, [rbp+1F0h+SystemTime.wMonth]
0x180084220  movzx   r10d, [rbp+1F0h+SystemTime.wSecond]
0x180084225  movzx   r11d, [rbp+1F0h+SystemTime.wYear]
0x18008422a  mov     [rsp+2F0h+var_2A0], r10d
0x18008422f  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x180084233  mov     rax, [rdi]
0x180084236  mov     dword ptr [rsp+2F0h+var_2B0], ecx
0x18008423a  mov     rcx, r15; unsigned __int16 *
0x18008423d  mov     dword ptr [rsp+2F0h+var_2B8], r8d
0x180084242  lea     r8, aSLogfilesWmiS0; "%s\\LogFiles\\WMI\\%s-%04d%02d%02d-%02d"...
0x180084249  mov     dword ptr [rsp+2F0h+var_2C0], r9d
0x18008424e  lea     r9, [rbp+1F0h+Buffer]
0x180084252  mov     dword ptr [rsp+2F0h+var_2C8], r11d
0x180084257  mov     [rsp+2F0h+var_2D0], rax
0x18008425c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180084261  mov     rax, [rdi+20h]
0x180084265  mov     dword ptr [rax+30h], 14h
0x18008426c  mov     rcx, [rdi+20h]
0x180084270  mov     eax, [rdi+34h]
0x180084273  mov     [rcx+3Ch], eax
0x180084276  mov     rcx, rdi; this
0x180084279  mov     rax, [rdi+20h]
0x18008427d  mov     dword ptr [rax+34h], 0Ah
0x180084284  mov     rax, [rdi+20h]
0x180084288  mov     dword ptr [rax+44h], 3Ch ; '<'
0x18008428f  mov     rax, [rdi+20h]
0x180084293  mov     dword ptr [rax+40h], 2
0x18008429a  call    ?IsTraceToDebugger@CWPPLoggerConfig@@QEBAEXZ; CWPPLoggerConfig::IsTraceToDebugger(void)
0x18008429f  test    al, al
0x1800842a1  jz      short loc_1800842AC
0x1800842a3  mov     rax, [rdi+20h]
0x1800842a7  bts     dword ptr [rax+40h], 13h
0x1800842ac  mov     r8, [rdi+20h]; Properties
0x1800842b0  mov     rcx, r14; TraceHandle
0x1800842b3  mov     rdx, [rdi]; InstanceName
0x1800842b6  call    cs:__imp_StartTraceW
0x1800842bd  nop     dword ptr [rax+rax+00h]
0x1800842c2  mov     esi, eax
0x1800842c4  test    eax, eax
0x1800842c6  jg      short loc_1800842CC
0x1800842c8  mov     ebx, eax
0x1800842ca  jmp     short loc_1800842D5
0x1800842cc  movzx   ebx, ax
0x1800842cf  or      ebx, 80070000h
0x1800842d5  cmp     eax, 70h ; 'p'
0x1800842d8  jnz     short loc_18008433C
0x1800842da  mov     rax, [rdi+20h]
0x1800842de  mov     rcx, r14; TraceHandle
0x1800842e1  mov     dword ptr [rax+3Ch], 1
0x1800842e8  mov     r8, [rdi+20h]; Properties
0x1800842ec  mov     rdx, [rdi]; InstanceName
0x1800842ef  call    cs:__imp_StartTraceW
0x1800842f6  nop     dword ptr [rax+rax+00h]
0x1800842fb  mov     esi, eax
0x1800842fd  mov     eax, cs:dword_1800DF020
0x180084303  cmp     eax, 2
0x180084306  jbe     short loc_18008433C
0x180084308  mov     eax, [rdi+34h]
0x18008430b  lea     rdx, byte_1800CD673
0x180084312  mov     [rsp+2F0h+var_290], rax
0x180084317  lea     rax, aSpecifiedBuffe; "Specified buffer size is too large, usi"...
0x18008431e  mov     [rsp+2F0h+var_288], rax
0x180084323  lea     rax, [rsp+2F0h+var_290]
0x180084328  mov     [rsp+2F0h+var_2C8], rax
0x18008432d  lea     rax, [rsp+2F0h+var_288]
0x180084332  mov     [rsp+2F0h+var_2D0], rax
0x180084337  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18008433c  test    esi, esi
0x18008433e  jz      loc_1800843C4
0x180084344  mov     eax, cs:dword_1800DF020
0x18008434a  cmp     eax, 2
0x18008434d  jbe     short loc_1800843C4
0x18008434f  mov     rax, [rdi+20h]
0x180084353  lea     rdx, qword_1800CD480
0x18008435a  mov     [rsp+2F0h+var_278], r15
0x18008435f  mov     ecx, [rax+3Ch]
0x180084362  mov     rax, [r14]
0x180084365  mov     [rsp+2F0h+var_280], rax
0x18008436a  mov     rax, [rdi]
0x18008436d  mov     [rbp+1F0h+var_270], rax
0x180084371  lea     rax, aStarttracewFai; "StartTraceW failed with these values"
0x180084378  mov     [rbp+1F0h+var_268], rax
0x18008437c  lea     rax, [rsp+2F0h+var_288]
0x180084381  mov     [rsp+2F0h+var_2A8], rax
0x180084386  lea     rax, [rsp+2F0h+var_280]
0x18008438b  mov     [rsp+2F0h+var_2B0], rax
0x180084390  lea     rax, [rsp+2F0h+var_278]
0x180084395  mov     [rsp+2F0h+var_2B8], rax
0x18008439a  lea     rax, [rsp+2F0h+var_290]
0x18008439f  mov     [rsp+2F0h+var_2C0], rax
0x1800843a4  lea     rax, [rbp+1F0h+var_270]
0x1800843a8  mov     [rsp+2F0h+var_2C8], rax
0x1800843ad  lea     rax, [rbp+1F0h+var_268]
0x1800843b1  mov     [rsp+2F0h+var_2D0], rax
0x1800843b6  mov     [rsp+2F0h+var_288], rcx
0x1800843bb  mov     dword ptr [rsp+2F0h+var_290], ebx
0x1800843bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800843c4  mov     eax, ebx
0x1800843c6  mov     rcx, [rbp+1F0h+var_40]
0x1800843cd  xor     rcx, rsp; StackCookie
0x1800843d0  call    __security_check_cookie
0x1800843d5  add     rsp, 2C8h
0x1800843dc  pop     r15
0x1800843de  pop     r14
0x1800843e0  pop     rdi
0x1800843e1  pop     rsi
0x1800843e2  pop     rbx
0x1800843e3  pop     rbp
0x1800843e4  retn
```
