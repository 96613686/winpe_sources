# CRDPENCNamedPipeListener::StartListeningInternal(ushort const *,int,int)

- ea: `0x180101f18`
- end: `0x1801022be`
- name: `?StartListeningInternal@CRDPENCNamedPipeListener@@IEAAJPEBGHH@Z`
- size: `934`
- prototype: `int(CRDPENCNamedPipeListener *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180101a00`
- `0x180101c10`

## callees

- `0x1800018a4`
- `0x180005090`
- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x180038984`
- `0x1800506ac`
- `0x180101f18`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801021c4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801021c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180102211`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180102211`

## string_xrefs

- `0x1801021b4`: `Failed to create the listener worker thread`
- `0x1801021fe`: `Failed to start the listener worker thread`
- `0x180102085`: `Failed to copy Pipe Name`
- `0x180102012`: `Named pipe listener already started`
- `0x180102164`: `Failed to start the listener connection completed callback thread`
- `0x18010211f`: `Failed to create the listener connection completed callback thread`

## pseudocode

```c
__int64 __fastcall CRDPENCNamedPipeListener::StartListeningInternal(
        CRDPENCNamedPipeListener *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  char *v11; // rdx
  const char **v12; // rax
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  char *v16; // rdx
  const char *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rsi
  __int64 v20; // rcx
  _QWORD *v21; // rsi
  __int64 v22; // rcx
  const char **v24; // [rsp+40h] [rbp-19h]
  int v25; // [rsp+50h] [rbp-9h] BYREF
  const char *v26; // [rsp+58h] [rbp-1h] BYREF
  const char *v27; // [rsp+60h] [rbp+7h] BYREF
  const char *v28; // [rsp+68h] [rbp+Fh] BYREF
  char *v29; // [rsp+70h] [rbp+17h] BYREF
  int v30; // [rsp+C0h] [rbp+67h] BYREF

  v29 = (char *)this + 136;
  CTSCriticalSection::Lock((CRDPENCNamedPipeListener *)((char *)this + 136));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    v10 = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    v30 = 277;
    v26 = "StartListeningInternal";
    v11 = byte_1801C64BB;
    v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v28 = "Ignoring start listen on named pipe call after termination";
    v24 = &v26;
    v12 = &v28;
    goto LABEL_4;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    v10 = StringCchCopyW((unsigned __int16 *)this + 76, 0x100u, a2);
    if ( v10 >= 0 )
    {
      v18 = *((_QWORD *)this + 12);
      *((_DWORD *)this + 166) = a3;
      *((_DWORD *)this + 167) = a4;
      v10 = (*(__int64 (__fastcall **)(__int64, void (__fastcall *)(void *), __int64, char *))(*(_QWORD *)v18 + 56LL))(
              v18,
              CRDPENCNamedPipeListener::STATIC_OnConnectionCompletedCallbackThreadProc,
              v18,
              (char *)this + 104);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 13) + 32LL))(*((_QWORD *)this + 13), 0);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(void *), CRDPENCNamedPipeListener *, char *))(**((_QWORD **)this + 12) + 56LL))(
                  *((_QWORD *)this + 12),
                  CRDPENCNamedPipeListener::STATIC_WorkerThreadProc,
                  this,
                  (char *)this + 112);
          if ( v10 >= 0 )
          {
            ResetEvent(*((HANDLE *)this + 15));
            v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14) + 32LL))(
                    *((_QWORD *)this + 14),
                    0);
            if ( v10 >= 0 )
            {
              if ( WaitForSingleObject(*((HANDLE *)this + 15), 0xFFFFFFFF) )
              {
                v10 = -2147467259;
              }
              else
              {
                v10 = *((_DWORD *)this + 32);
                if ( v10 >= 0 )
                  goto LABEL_35;
              }
              goto LABEL_28;
            }
            if ( (unsigned int)CallbackContext <= 3 )
              goto LABEL_28;
            v28 = "StartListeningInternal";
            v16 = byte_1801C63BB;
            v17 = "Failed to start the listener worker thread";
          }
          else
          {
            if ( (unsigned int)CallbackContext <= 3 )
              goto LABEL_28;
            v28 = "StartListeningInternal";
            v16 = byte_1801C637B;
            v17 = "Failed to create the listener worker thread";
          }
        }
        else
        {
          if ( (unsigned int)CallbackContext <= 3 )
            goto LABEL_28;
          v28 = "StartListeningInternal";
          v16 = byte_1801C643B;
          v17 = "Failed to start the listener connection completed callback thread";
        }
      }
      else
      {
        if ( (unsigned int)CallbackContext <= 3 )
          goto LABEL_28;
        v28 = "StartListeningInternal";
        v16 = byte_1801C63FB;
        v17 = "Failed to create the listener connection completed callback thread";
      }
    }
    else
    {
      v15 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 3 )
        goto LABEL_28;
      v28 = "StartListeningInternal";
      v16 = byte_1801C647B;
      v17 = "Failed to copy Pipe Name";
    }
    v27 = v17;
    v26 = "Warning HResult failed";
    v30 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v15,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v30,
      (__int64)&v28);
    goto LABEL_28;
  }
  v10 = -2147418113;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v30 = 283;
    v28 = "StartListeningInternal";
    v11 = byte_1801C6505;
    v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v26 = "Named pipe listener already started";
    v24 = &v28;
    v12 = &v26;
LABEL_4:
    v25 = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147418113,
      (_DWORD)v11,
      v8,
      v9,
      (__int64)v12,
      (__int64)&v25,
      (__int64)&v27,
      (__int64)&v30,
      (__int64)v24);
  }
LABEL_28:
  v19 = (_QWORD *)((char *)this + 112);
  v20 = *((_QWORD *)this + 14);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 56LL))(v20, 0);
    if ( *v19 )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 112);
      *v19 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 112);
    }
  }
  v21 = (_QWORD *)((char *)this + 104);
  v22 = *((_QWORD *)this + 13);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, 0);
    if ( *v21 )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 104);
      *v21 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 104);
    }
  }
  *((_WORD *)this + 76) = 0;
LABEL_35:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180101f18  push    rbp
0x180101f1a  push    rbx
0x180101f1b  push    rsi
0x180101f1c  push    rdi
0x180101f1d  push    r14
0x180101f1f  push    r15
0x180101f21  lea     rbp, [rsp-2Fh]
0x180101f26  sub     rsp, 88h
0x180101f2d  mov     rdi, rcx
0x180101f30  mov     r14d, r9d
0x180101f33  add     rcx, 88h; this
0x180101f3a  mov     r15d, r8d
0x180101f3d  mov     [rbp+57h+var_40], rcx
0x180101f41  mov     rbx, rdx
0x180101f44  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180101f49  test    byte ptr [rdi+24h], 4
0x180101f4d  jz      short loc_180101FCE
0x180101f4f  mov     eax, cs:CallbackContext
0x180101f55  mov     ecx, 8000FFFFh
0x180101f5a  mov     ebx, ecx
0x180101f5c  cmp     eax, 2
0x180101f5f  jbe     loc_18010222C
0x180101f65  lea     rax, aStartlistening_1; "StartListeningInternal"
0x180101f6c  mov     [rbp+57h+arg_0], 115h
0x180101f73  mov     [rbp+57h+var_58], rax
0x180101f77  lea     rdx, byte_1801C64BB
0x180101f7e  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180101f85  mov     [rbp+57h+var_50], rax
0x180101f89  lea     rax, aIgnoringStartL; "Ignoring start listen on named pipe cal"...
0x180101f90  mov     [rbp+57h+var_48], rax
0x180101f94  lea     rax, [rbp+57h+var_58]
0x180101f98  mov     [rsp+0B0h+var_70], rax
0x180101f9d  lea     rax, [rbp+57h+arg_0]
0x180101fa1  mov     [rsp+0B0h+var_78], rax
0x180101fa6  lea     rax, [rbp+57h+var_50]
0x180101faa  mov     [rsp+0B0h+var_80], rax
0x180101faf  lea     rax, [rbp+57h+var_60]
0x180101fb3  mov     [rsp+0B0h+var_88], rax
0x180101fb8  lea     rax, [rbp+57h+var_48]
0x180101fbc  mov     [rsp+0B0h+var_90], rax
0x180101fc1  mov     [rbp+57h+var_60], ecx
0x180101fc4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180101fc9  jmp     loc_18010222C
0x180101fce  lea     rsi, [rdi+70h]
0x180101fd2  cmp     qword ptr [rsi], 0
0x180101fd6  jz      short loc_18010204A
0x180101fd8  mov     eax, cs:CallbackContext
0x180101fde  mov     ecx, 8000FFFFh
0x180101fe3  mov     ebx, ecx
0x180101fe5  cmp     eax, 2
0x180101fe8  jbe     loc_18010222C
0x180101fee  lea     rax, aStartlistening_1; "StartListeningInternal"
0x180101ff5  mov     [rbp+57h+arg_0], 11Bh
0x180101ffc  mov     [rbp+57h+var_48], rax
0x180102000  lea     rdx, byte_1801C6505
0x180102007  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010200e  mov     [rbp+57h+var_50], rax
0x180102012  lea     rax, aNamedPipeListe; "Named pipe listener already started"
0x180102019  mov     [rbp+57h+var_58], rax
0x18010201d  lea     rax, [rbp+57h+var_48]
0x180102021  mov     [rsp+0B0h+var_70], rax
0x180102026  lea     rax, [rbp+57h+arg_0]
0x18010202a  mov     [rsp+0B0h+var_78], rax
0x18010202f  lea     rax, [rbp+57h+var_50]
0x180102033  mov     [rsp+0B0h+var_80], rax
0x180102038  lea     rax, [rbp+57h+var_60]
0x18010203c  mov     [rsp+0B0h+var_88], rax
0x180102041  lea     rax, [rbp+57h+var_58]
0x180102045  jmp     loc_180101FBC
0x18010204a  lea     rcx, [rdi+98h]; unsigned __int16 *
0x180102051  mov     r8, rbx; unsigned __int16 *
0x180102054  mov     edx, 100h; unsigned __int64
0x180102059  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010205e  mov     ebx, eax
0x180102060  test    eax, eax
0x180102062  jns     short loc_1801020CC
0x180102064  mov     ecx, cs:CallbackContext
0x18010206a  cmp     ecx, 3
0x18010206d  jbe     loc_18010222C
0x180102073  lea     rax, aStartlistening_1; "StartListeningInternal"
0x18010207a  mov     [rbp+57h+var_48], rax
0x18010207e  lea     rdx, byte_1801C647B
0x180102085  lea     rax, aFailedToCopyPi; "Failed to copy Pipe Name"
0x18010208c  mov     [rbp+57h+var_50], rax
0x180102090  lea     rax, aWarningHresult; "Warning HResult failed"
0x180102097  mov     [rbp+57h+var_58], rax
0x18010209b  lea     rax, [rbp+57h+var_48]
0x18010209f  mov     [rsp+0B0h+var_78], rax
0x1801020a4  lea     rax, [rbp+57h+arg_0]
0x1801020a8  mov     [rsp+0B0h+var_80], rax
0x1801020ad  lea     rax, [rbp+57h+var_50]
0x1801020b1  mov     [rsp+0B0h+var_88], rax
0x1801020b6  lea     rax, [rbp+57h+var_58]
0x1801020ba  mov     [rsp+0B0h+var_90], rax
0x1801020bf  mov     [rbp+57h+arg_0], ebx
0x1801020c2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801020c7  jmp     loc_18010222C
0x1801020cc  mov     rcx, [rdi+60h]
0x1801020d0  lea     r9, [rdi+68h]
0x1801020d4  mov     [rdi+298h], r15d
0x1801020db  lea     rdx, ?STATIC_OnConnectionCompletedCallbackThreadProc@CRDPENCNamedPipeListener@@KAXPEAX@Z; CRDPENCNamedPipeListener::STATIC_OnConnectionCompletedCallbackThreadProc(void *)
0x1801020e2  mov     [rdi+29Ch], r14d
0x1801020e9  mov     r8, rcx
0x1801020ec  mov     rax, [rcx]
0x1801020ef  mov     rax, [rax+38h]
0x1801020f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801020f8  mov     ebx, eax
0x1801020fa  test    eax, eax
0x1801020fc  jns     short loc_18010212B
0x1801020fe  mov     eax, cs:CallbackContext
0x180102104  cmp     eax, 3
0x180102107  jbe     loc_18010222C
0x18010210d  lea     rax, aStartlistening_1; "StartListeningInternal"
0x180102114  mov     [rbp+57h+var_48], rax
0x180102118  lea     rdx, byte_1801C63FB
0x18010211f  lea     rax, aFailedToCreate_81; "Failed to create the listener connectio"...
0x180102126  jmp     loc_18010208C
0x18010212b  mov     rcx, [rdi+68h]
0x18010212f  xor     edx, edx
0x180102131  mov     rax, [rcx]
0x180102134  mov     rax, [rax+20h]
0x180102138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010213d  mov     ebx, eax
0x18010213f  test    eax, eax
0x180102141  jns     short loc_180102170
0x180102143  mov     eax, cs:CallbackContext
0x180102149  cmp     eax, 3
0x18010214c  jbe     loc_18010222C
0x180102152  lea     rax, aStartlistening_1; "StartListeningInternal"
0x180102159  mov     [rbp+57h+var_48], rax
0x18010215d  lea     rdx, byte_1801C643B
0x180102164  lea     rax, aFailedToStartT_4; "Failed to start the listener connection"...
0x18010216b  jmp     loc_18010208C
0x180102170  mov     rcx, [rdi+60h]
0x180102174  lea     rdx, ?STATIC_WorkerThreadProc@CRDPENCNamedPipeListener@@KAXPEAX@Z; CRDPENCNamedPipeListener::STATIC_WorkerThreadProc(void *)
0x18010217b  mov     r9, rsi
0x18010217e  mov     r8, rdi
0x180102181  mov     rax, [rcx]
0x180102184  mov     rax, [rax+38h]
0x180102188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010218d  mov     ebx, eax
0x18010218f  test    eax, eax
0x180102191  jns     short loc_1801021C0
0x180102193  mov     eax, cs:CallbackContext
0x180102199  cmp     eax, 3
0x18010219c  jbe     loc_18010222C
0x1801021a2  lea     rax, aStartlistening_1; "StartListeningInternal"
0x1801021a9  mov     [rbp+57h+var_48], rax
0x1801021ad  lea     rdx, byte_1801C637B
0x1801021b4  lea     rax, aFailedToCreate_55; "Failed to create the listener worker th"...
0x1801021bb  jmp     loc_18010208C
0x1801021c0  mov     rcx, [rdi+78h]; hEvent
0x1801021c4  call    cs:__imp_ResetEvent
0x1801021ca  mov     rcx, [rsi]
0x1801021cd  xor     edx, edx
0x1801021cf  mov     rax, [rcx]
0x1801021d2  mov     rax, [rax+20h]
0x1801021d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021db  mov     ebx, eax
0x1801021dd  test    eax, eax
0x1801021df  jns     short loc_18010220A
0x1801021e1  mov     eax, cs:CallbackContext
0x1801021e7  cmp     eax, 3
0x1801021ea  jbe     short loc_18010222C
0x1801021ec  lea     rax, aStartlistening_1; "StartListeningInternal"
0x1801021f3  mov     [rbp+57h+var_48], rax
0x1801021f7  lea     rdx, byte_1801C63BB
0x1801021fe  lea     rax, aFailedToStartT_1; "Failed to start the listener worker thr"...
0x180102205  jmp     loc_18010208C
0x18010220a  mov     rcx, [rdi+78h]; hHandle
0x18010220e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180102211  call    cs:__imp_WaitForSingleObject
0x180102217  test    eax, eax
0x180102219  jnz     short loc_180102227
0x18010221b  mov     ebx, [rdi+80h]
0x180102221  test    ebx, ebx
0x180102223  jns     short loc_1801022A3
0x180102225  jmp     short loc_18010222C
0x180102227  mov     ebx, 80004005h
0x18010222c  lea     rsi, [rdi+70h]
0x180102230  mov     rcx, [rsi]
0x180102233  test    rcx, rcx
0x180102236  jz      short loc_180102263
0x180102238  mov     rax, [rcx]
0x18010223b  xor     edx, edx
0x18010223d  mov     rax, [rax+38h]
0x180102241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102246  cmp     qword ptr [rsi], 0
0x18010224a  jz      short loc_180102263
0x18010224c  mov     rcx, rsi; void *
0x18010224f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180102254  mov     rcx, rsi
0x180102257  mov     qword ptr [rsi], 0
0x18010225e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180102263  lea     rsi, [rdi+68h]
0x180102267  mov     rcx, [rsi]
0x18010226a  test    rcx, rcx
0x18010226d  jz      short loc_18010229A
0x18010226f  mov     rax, [rcx]
0x180102272  xor     edx, edx
0x180102274  mov     rax, [rax+38h]
0x180102278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010227d  cmp     qword ptr [rsi], 0
0x180102281  jz      short loc_18010229A
0x180102283  mov     rcx, rsi; void *
0x180102286  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010228b  mov     rcx, rsi
0x18010228e  mov     qword ptr [rsi], 0
0x180102295  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010229a  xor     eax, eax
0x18010229c  mov     [rdi+98h], ax
0x1801022a3  lea     rcx, [rbp+57h+var_40]; this
0x1801022a7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1801022ac  mov     eax, ebx
0x1801022ae  add     rsp, 88h
0x1801022b5  pop     r15
0x1801022b7  pop     r14
0x1801022b9  pop     rdi
0x1801022ba  pop     rsi
0x1801022bb  pop     rbx
0x1801022bc  pop     rbp
0x1801022bd  retn
```
