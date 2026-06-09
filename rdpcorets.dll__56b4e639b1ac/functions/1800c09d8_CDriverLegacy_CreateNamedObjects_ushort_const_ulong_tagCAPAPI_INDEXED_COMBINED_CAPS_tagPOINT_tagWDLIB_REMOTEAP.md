# CDriverLegacy::CreateNamedObjects(ushort const *,ulong,tagCAPAPI_INDEXED_COMBINED_CAPS,tagPOINT,tagWDLIB_REMOTEAPP_MODES,ulong,tagTS_MONITOR_DEF *,tagTS_MONITOR_ATTRIBUTES *,_UMRDP_MONITOR_CONTAINER_ATTRIBUTES *)

- ea: `0x1800c09d8`
- end: `0x1800c1111`
- name: `?CreateNamedObjects@CDriverLegacy@@IEAAJPEBGKUtagCAPAPI_INDEXED_COMBINED_CAPS@@UtagPOINT@@W4tagWDLIB_REMOTEAPP_MODES@@KPEAUtagTS_MONITOR_DEF@@PEAUtagTS_MONITOR_ATTRIBUTES@@PEAU_UMRDP_MONITOR_CONTAINER_ATTRIBUTES@@@Z`
- size: `1849`
- prototype: `__int64 __fastcall(__int64, __int64, int, _OWORD *, __int64, int, unsigned int, void *Src, void *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800c1df0`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x180009628`
- `0x180010960`
- `0x180034970`
- `0x1800c05c8`
- `0x1800c09d8`
- `0x1800c1118`
- `0x18014c328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c0e2b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c0e2b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0e95`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0efd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0e95`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c0efd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c0c70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c0c70`

## string_xrefs

- `0x1800c0a1b`: `CreateNamedObjects`
- `0x1800c0b52`: `CreateNamedObjects`
- `0x1800c0f79`: `CreateNamedObjects`
- `0x1800c1095`: `CreateNamedObjects`
- `0x1800c0d41`: `RdpUpdatesFlushedEvent`
- `0x1800c0e47`: `RdpProtocolStartedEvent`
- `0x1800c0e78`: `Failed to allocate protocol started event`
- `0x1800c0f1e`: `RdpUpdateBufferEmptyEvent`
- `0x1800c1040`: `RdpUpdateBuffer`
- `0x1800c107c`: `Failed to create and map update buffer`
- `0x1800c0acd`: `Re-attempt to allocate command channel buffer for legacy driver`
- `0x1800c0aa1`: `RdpCommandChannel`
- `0x1800c0b00`: `RdpCommandChannel`
- `0x1800c0bae`: `Command channel name`
- `0x1800c0b39`: `Failed to create and map command channel`

## pseudocode

```c
__int64 __fastcall CDriverLegacy::CreateNamedObjects(
        __int64 a1,
        __int64 a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        void *Src,
        void *a9,
        void *a10)
{
  _OWORD *v10; // r14
  int SharedBuffer; // ebx
  int *v14; // rdx
  const char **v15; // rax
  unsigned int v16; // r13d
  __int64 v17; // r12
  __int16 *v18; // rdx
  const char **v19; // rax
  _DWORD *v20; // rsi
  void *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // r13
  size_t v24; // rbx
  bool v25; // zf
  _DWORD *v26; // rbx
  __int64 v27; // rax
  _OWORD *v28; // rcx
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  int v36; // eax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  const char *v42; // rax
  _OWORD *v43; // rcx
  __int128 v44; // xmm1
  const char **v46; // [rsp+30h] [rbp-50h]
  const char **v47; // [rsp+30h] [rbp-50h]
  const char **v48; // [rsp+40h] [rbp-40h]
  const char **v49; // [rsp+40h] [rbp-40h]
  const char **v50; // [rsp+48h] [rbp-38h]
  int v51; // [rsp+50h] [rbp-30h] BYREF
  const char *v52; // [rsp+58h] [rbp-28h] BYREF
  const char *v53; // [rsp+60h] [rbp-20h] BYREF
  const char *v54; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v55[2]; // [rsp+70h] [rbp-10h] BYREF
  const char *v56; // [rsp+C0h] [rbp+40h] BYREF
  int v57; // [rsp+D0h] [rbp+50h]

  v57 = a3;
  v10 = a4;
  if ( *(_DWORD *)(a1 + 56) == -1 )
  {
    SharedBuffer = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v56) = 269;
      v52 = "CreateNamedObjects";
      v14 = (int *)byte_1801A8833;
      v53 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
      v54 = "******Session ID -1 still****";
      v48 = &v52;
      v46 = &v53;
      v15 = &v54;
LABEL_4:
      v51 = SharedBuffer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (_DWORD)v14,
        a3,
        (_DWORD)a4,
        (__int64)v15,
        (__int64)&v51,
        (__int64)v46,
        (__int64)&v56,
        (__int64)v48);
      return (unsigned int)SharedBuffer;
    }
    return (unsigned int)SharedBuffer;
  }
  v16 = 3160452;
  SharedBuffer = CDriverLegacy::CreateSharedBuffer(
                   (CDriverLegacy *)a1,
                   L"RdpCommandChannel",
                   0x303984u,
                   (unsigned __int16 *)(a1 + 120),
                   (unsigned __int8 **)(a1 + 72),
                   (void **)(a1 + 80));
  v17 = 4;
  if ( SharedBuffer == -2147024891 )
  {
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v56 = "Re-attempt to allocate command channel buffer for legacy driver";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (unsigned int)byte_1801A887D,
        a3,
        (_DWORD)a4,
        (__int64)&v56);
    }
    *(_DWORD *)(a1 + 764) = 1;
    v16 = 3151804;
    SharedBuffer = CDriverLegacy::CreateSharedBuffer(
                     (CDriverLegacy *)a1,
                     L"RdpCommandChannel",
                     0x3017BCu,
                     (unsigned __int16 *)(a1 + 120),
                     (unsigned __int8 **)(a1 + 72),
                     (void **)(a1 + 80));
  }
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    LODWORD(v56) = 306;
    v54 = "Failed to create and map command channel";
    v18 = &word_1801A87AE;
    v53 = "CreateNamedObjects";
    v52 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
    v55[0] = "Error HResult failed";
    v50 = &v54;
    v49 = &v53;
    v47 = &v52;
    v19 = (const char **)v55;
LABEL_45:
    v51 = SharedBuffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      a1,
      (_DWORD)v18,
      a3,
      (_DWORD)a4,
      (__int64)v19,
      (__int64)&v51,
      (__int64)v47,
      (__int64)&v56,
      (__int64)v49,
      (__int64)v50);
    return (unsigned int)SharedBuffer;
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v56 = (const char *)(a1 + 120);
    v55[0] = "Command channel name";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      a1,
      (unsigned int)&unk_1801A8800,
      a3,
      (_DWORD)a4,
      (__int64)v55,
      (__int64)&v56);
  }
  v20 = *(_DWORD **)(a1 + 72);
  memset_0(v20, 0, v16);
  v21 = Src;
  v20[4] = v57;
  v22 = a7;
  v20[787951] = v16;
  v23 = (unsigned int)v22;
  v20[1] = 1;
  v20[5] = v22;
  v24 = 20 * v22;
  memcpy_0(v20 + 6, v21, 20 * v22);
  memcpy_0(v20 + 86, a9, v24);
  *((_QWORD *)v20 + 83) = a5;
  v25 = a6 == 0;
  v20[3] = 1;
  v20[170] = 1;
  v20[168] = !v25;
  v20[171] = *(_DWORD *)(a1 + 56);
  v20[172] = GetCurrentProcessId();
  v20[169] = 0;
  if ( !*(_DWORD *)(a1 + 764) )
  {
    v26 = a10;
    memcpy_0(v20 + 787953, a10, 540 * v23);
    v20[787952] = *v26 || v26[1];
  }
  v27 = 7;
  v28 = v20 + 334;
  do
  {
    v29 = v10[1];
    *v28 = *v10;
    v30 = v10[2];
    v28[1] = v29;
    v31 = v10[3];
    v28[2] = v30;
    v32 = v10[4];
    v28[3] = v31;
    v33 = v10[5];
    v28[4] = v32;
    v34 = v10[6];
    v28[5] = v33;
    v35 = v10[7];
    v10 += 8;
    v28[6] = v34;
    v28[7] = v35;
    v28 += 8;
    --v27;
  }
  while ( v27 );
  v36 = *((_DWORD *)v10 + 24);
  v37 = v10[1];
  *v28 = *v10;
  *v20 = 1;
  v38 = v10[2];
  v28[1] = v37;
  v39 = v10[3];
  v28[2] = v38;
  v40 = v10[4];
  v28[3] = v39;
  v41 = v10[5];
  v28[4] = v40;
  v28[5] = v41;
  *((_DWORD *)v28 + 24) = v36;
  SharedBuffer = CDriverLegacy::AllocateNamedEvent(
                   (CDriverLegacy *)a1,
                   L"RdpUpdatesFlushedEvent",
                   0,
                   0,
                   (unsigned __int16 *)v20 + 1574061,
                   (void **)(a1 + 648));
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    v42 = "Failed to allocate flush event";
    LODWORD(v56) = 385;
    v18 = word_1801A870A;
    goto LABEL_44;
  }
  SharedBuffer = CDriverLegacy::AllocateNamedEvent(
                   (CDriverLegacy *)a1,
                   L"RdpWaitAbortEvent",
                   1,
                   0,
                   (unsigned __int16 *)v20 + 1574321,
                   (void **)(a1 + 656));
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    v42 = "Failed to allocate abort event";
    LODWORD(v56) = 394;
    v18 = (__int16 *)&dword_1801A875C;
    goto LABEL_44;
  }
  ResetEvent(*(HANDLE *)(a1 + 656));
  SharedBuffer = CDriverLegacy::AllocateNamedEvent(
                   (CDriverLegacy *)a1,
                   L"RdpProtocolStartedEvent",
                   1,
                   1,
                   (unsigned __int16 *)v20 + 1574841,
                   (void **)(a1 + 664));
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    v42 = "Failed to allocate protocol started event";
    LODWORD(v56) = 412;
    v18 = &word_1801A8666;
    goto LABEL_44;
  }
  SetEvent(*(HANDLE *)(a1 + 664));
  SharedBuffer = CDriverLegacy::AllocateNamedEvent(
                   (CDriverLegacy *)a1,
                   L"RdpPipeLockevent",
                   0,
                   1,
                   (unsigned __int16 *)v20 + 1575641,
                   (void **)(a1 + 680));
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    v42 = "Failed to allocate buffer empty event";
    LODWORD(v56) = 426;
    v18 = (__int16 *)&unk_1801A86B8;
    goto LABEL_44;
  }
  SetEvent(*(HANDLE *)(a1 + 680));
  SharedBuffer = CDriverLegacy::AllocateNamedEvent(
                   (CDriverLegacy *)a1,
                   L"RdpUpdateBufferEmptyEvent",
                   0,
                   0,
                   (unsigned __int16 *)v20 + 1574581,
                   (void **)(a1 + 672));
  if ( SharedBuffer < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    v42 = "Failed to allocate buffer empty event";
    LODWORD(v56) = 438;
    v18 = word_1801A85CA;
    goto LABEL_44;
  }
  if ( !*(_WORD *)a2 )
  {
    SharedBuffer = -2147418113;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      return (unsigned int)SharedBuffer;
    LODWORD(v56) = 450;
    v55[0] = "CreateNamedObjects";
    v14 = &dword_1801A861C;
    v54 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
    v53 = "Unexpected event name";
    v48 = (const char **)v55;
    v46 = &v54;
    v15 = &v53;
    goto LABEL_4;
  }
  v43 = (_OWORD *)((char *)v20 + 3150202);
  do
  {
    *v43 = *(_OWORD *)a2;
    v43[1] = *(_OWORD *)(a2 + 16);
    v43[2] = *(_OWORD *)(a2 + 32);
    v43[3] = *(_OWORD *)(a2 + 48);
    v43[4] = *(_OWORD *)(a2 + 64);
    v43[5] = *(_OWORD *)(a2 + 80);
    v43[6] = *(_OWORD *)(a2 + 96);
    v44 = *(_OWORD *)(a2 + 112);
    a2 += 128;
    v43[7] = v44;
    v43 += 8;
    --v17;
  }
  while ( v17 );
  *(_QWORD *)v43 = *(_QWORD *)a2;
  SharedBuffer = CDriverLegacy::CreateSharedBuffer(
                   (CDriverLegacy *)a1,
                   L"RdpUpdateBuffer",
                   0x100000u,
                   (unsigned __int16 *)v20 + 1575361,
                   (unsigned __int8 **)(a1 + 64),
                   (void **)(a1 + 88));
  if ( SharedBuffer < 0 && (unsigned int)dword_1801B76C8 > 2 )
  {
    v42 = "Failed to create and map update buffer";
    LODWORD(v56) = 471;
    v18 = (__int16 *)&byte_1801A8527;
LABEL_44:
    v55[0] = v42;
    v54 = "CreateNamedObjects";
    v53 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverlegacy.cpp";
    v52 = "Error HResult failed";
    v50 = (const char **)v55;
    v49 = &v54;
    v47 = &v53;
    v19 = &v52;
    goto LABEL_45;
  }
  return (unsigned int)SharedBuffer;
}

```

## disassembly

```asm
0x1800c09d8  mov     r11, rsp
0x1800c09db  mov     [r11+10h], rbx
0x1800c09df  mov     [r11+18h], r8d
0x1800c09e3  push    rbp
0x1800c09e4  push    rsi
0x1800c09e5  push    rdi
0x1800c09e6  push    r12
0x1800c09e8  push    r13
0x1800c09ea  push    r14
0x1800c09ec  push    r15
0x1800c09ee  mov     rbp, rsp
0x1800c09f1  sub     rsp, 80h
0x1800c09f8  cmp     dword ptr [rcx+38h], 0FFFFFFFFh
0x1800c09fc  mov     r14, r9
0x1800c09ff  mov     r15, rdx
0x1800c0a02  mov     rdi, rcx
0x1800c0a05  jnz     short loc_1800C0A82
0x1800c0a07  mov     eax, cs:dword_1801B76C8
0x1800c0a0d  mov     ebx, 80070057h
0x1800c0a12  cmp     eax, 2
0x1800c0a15  jbe     loc_1800C10F4
0x1800c0a1b  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800c0a22  mov     dword ptr [rbp+arg_0], 10Dh
0x1800c0a29  mov     [rbp+var_28], rax
0x1800c0a2d  lea     rdx, byte_1801A8833
0x1800c0a34  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c0a3b  mov     [rbp+var_20], rax
0x1800c0a3f  lea     rax, aSessionId1Stil; "******Session ID -1 still****"
0x1800c0a46  mov     [rbp+var_18], rax
0x1800c0a4a  lea     rax, [rbp+var_28]
0x1800c0a4e  mov     [r11-78h], rax
0x1800c0a52  lea     rax, [rbp+arg_0]
0x1800c0a56  mov     [r11-80h], rax
0x1800c0a5a  lea     rax, [rbp+var_20]
0x1800c0a5e  mov     [rsp+80h+var_50], rax
0x1800c0a63  lea     rax, [rbp+var_30]
0x1800c0a67  mov     [rsp+80h+var_58], rax
0x1800c0a6c  lea     rax, [rbp+var_18]
0x1800c0a70  mov     [rsp+80h+var_60], rax
0x1800c0a75  mov     [rbp+var_30], ebx
0x1800c0a78  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c0a7d  jmp     loc_1800C10F4
0x1800c0a82  lea     rax, [rcx+50h]
0x1800c0a86  mov     r13d, 303984h
0x1800c0a8c  add     rcx, 48h ; 'H'
0x1800c0a90  mov     [rsp+80h+var_58], rax; void **
0x1800c0a95  mov     [rsp+80h+var_60], rcx; unsigned __int8 **
0x1800c0a9a  lea     rsi, [rdi+78h]
0x1800c0a9e  mov     rcx, rdi; this
0x1800c0aa1  lea     rdx, aRdpcommandchan; "RdpCommandChannel"
0x1800c0aa8  mov     r9, rsi; unsigned __int16 *
0x1800c0aab  mov     r8d, r13d; unsigned int
0x1800c0aae  call    ?CreateSharedBuffer@CDriverLegacy@@IEAAJPEAGK0PEAPEAEPEAPEAX@Z; CDriverLegacy::CreateSharedBuffer(ushort *,ulong,ushort *,uchar * *,void * *)
0x1800c0ab3  mov     ebx, eax
0x1800c0ab5  mov     r12d, 4
0x1800c0abb  cmp     eax, 80070005h
0x1800c0ac0  jnz     short loc_1800C0B26
0x1800c0ac2  mov     eax, cs:dword_1801B76C8
0x1800c0ac8  cmp     eax, r12d
0x1800c0acb  jbe     short loc_1800C0AED
0x1800c0acd  lea     rax, aReAttemptToAll; "Re-attempt to allocate command channel "...
0x1800c0ad4  mov     [rbp+arg_0], rax
0x1800c0ad8  lea     rdx, byte_1801A887D
0x1800c0adf  lea     rax, [rbp+arg_0]
0x1800c0ae3  mov     [rsp+80h+var_60], rax
0x1800c0ae8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800c0aed  lea     rax, [rdi+50h]
0x1800c0af1  mov     dword ptr [rdi+2FCh], 1
0x1800c0afb  mov     [rsp+80h+var_58], rax; void **
0x1800c0b00  lea     rdx, aRdpcommandchan; "RdpCommandChannel"
0x1800c0b07  lea     rax, [rdi+48h]
0x1800c0b0b  mov     r13d, 3017BCh
0x1800c0b11  mov     r9, rsi; unsigned __int16 *
0x1800c0b14  mov     [rsp+80h+var_60], rax; unsigned __int8 **
0x1800c0b19  mov     r8d, r13d; unsigned int
0x1800c0b1c  mov     rcx, rdi; this
0x1800c0b1f  call    ?CreateSharedBuffer@CDriverLegacy@@IEAAJPEAGK0PEAPEAEPEAPEAX@Z; CDriverLegacy::CreateSharedBuffer(ushort *,ulong,ushort *,uchar * *,void * *)
0x1800c0b24  mov     ebx, eax
0x1800c0b26  mov     eax, cs:dword_1801B76C8
0x1800c0b2c  test    ebx, ebx
0x1800c0b2e  jns     short loc_1800C0BA9
0x1800c0b30  cmp     eax, 2
0x1800c0b33  jbe     loc_1800C10F4
0x1800c0b39  lea     rax, aFailedToCreate_67; "Failed to create and map command channe"...
0x1800c0b40  mov     dword ptr [rbp+arg_0], 132h
0x1800c0b47  mov     [rbp+var_18], rax
0x1800c0b4b  lea     rdx, word_1801A87AE
0x1800c0b52  lea     rax, aCreatenamedobj; "CreateNamedObjects"
0x1800c0b59  mov     [rbp+var_20], rax
0x1800c0b5d  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c0b64  mov     [rbp+var_28], rax
0x1800c0b68  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c0b6f  mov     [rbp+var_10], rax
0x1800c0b73  lea     rax, [rbp+var_18]
0x1800c0b77  mov     [rsp+80h+var_38], rax
0x1800c0b7c  lea     rax, [rbp+var_20]
0x1800c0b80  mov     [rsp+80h+var_40], rax
0x1800c0b85  lea     rax, [rbp+arg_0]
0x1800c0b89  mov     [rsp+80h+var_48], rax
0x1800c0b8e  lea     rax, [rbp+var_28]
0x1800c0b92  mov     [rsp+80h+var_50], rax
0x1800c0b97  lea     rax, [rbp+var_30]
0x1800c0b9b  mov     [rsp+80h+var_58], rax
0x1800c0ba0  lea     rax, [rbp+var_10]
0x1800c0ba4  jmp     loc_1800C10E7
0x1800c0ba9  cmp     eax, r12d
0x1800c0bac  jbe     short loc_1800C0BDB
0x1800c0bae  lea     rax, aCommandChannel; "Command channel name"
0x1800c0bb5  mov     [rbp+arg_0], rsi
0x1800c0bb9  mov     [rbp+var_10], rax
0x1800c0bbd  lea     rdx, unk_1801A8800
0x1800c0bc4  lea     rax, [rbp+arg_0]
0x1800c0bc8  mov     [rsp+80h+var_58], rax
0x1800c0bcd  lea     rax, [rbp+var_10]
0x1800c0bd1  mov     [rsp+80h+var_60], rax
0x1800c0bd6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800c0bdb  mov     rsi, [rdi+48h]
0x1800c0bdf  xor     edx, edx; Val
0x1800c0be1  mov     rcx, rsi; void *
0x1800c0be4  mov     r8d, r13d; Size
0x1800c0be7  call    memset_0
0x1800c0bec  mov     eax, [rbp+arg_10]
0x1800c0bef  lea     rcx, [rsi+18h]; void *
0x1800c0bf3  mov     rdx, [rbp+Src]; Src
0x1800c0bf7  mov     [rsi+10h], eax
0x1800c0bfa  mov     eax, [rbp+arg_30]
0x1800c0bfd  mov     [rsi+3017BCh], r13d
0x1800c0c04  mov     r13d, eax
0x1800c0c07  mov     dword ptr [rsi+4], 1
0x1800c0c0e  mov     [rsi+14h], eax
0x1800c0c11  lea     rbx, ds:0[rax*4]
0x1800c0c19  add     rbx, rax
0x1800c0c1c  shl     rbx, 2
0x1800c0c20  mov     r8, rbx; Size
0x1800c0c23  call    memcpy_0
0x1800c0c28  mov     rdx, [rbp+arg_40]; Src
0x1800c0c2f  lea     rcx, [rsi+158h]; void *
0x1800c0c36  mov     r8, rbx; Size
0x1800c0c39  call    memcpy_0
0x1800c0c3e  mov     rax, [rbp+arg_20]
0x1800c0c42  mov     ecx, 1
0x1800c0c47  mov     [rsi+298h], rax
0x1800c0c4e  xor     ebx, ebx
0x1800c0c50  cmp     [rbp+arg_28], ebx
0x1800c0c53  mov     eax, ebx
0x1800c0c55  mov     [rsi+0Ch], ecx
0x1800c0c58  setnz   al
0x1800c0c5b  mov     [rsi+2A8h], ecx
0x1800c0c61  mov     [rsi+2A0h], eax
0x1800c0c67  mov     eax, [rdi+38h]
0x1800c0c6a  mov     [rsi+2ACh], eax
0x1800c0c70  call    cs:__imp_GetCurrentProcessId
0x1800c0c76  mov     [rsi+2B0h], eax
0x1800c0c7c  mov     [rsi+2A4h], ebx
0x1800c0c82  cmp     [rdi+2FCh], ebx
0x1800c0c88  jnz     short loc_1800C0CCA
0x1800c0c8a  mov     rbx, [rbp+arg_48]
0x1800c0c91  lea     rcx, [rsi+3017C4h]; void *
0x1800c0c98  imul    r8, r13, 21Ch; Size
0x1800c0c9f  mov     rdx, rbx; Src
0x1800c0ca2  call    memcpy_0
0x1800c0ca7  xor     r13d, r13d
0x1800c0caa  cmp     [rbx], r13d
0x1800c0cad  jnz     short loc_1800C0CBE
0x1800c0caf  cmp     [rbx+4], r13d
0x1800c0cb3  jnz     short loc_1800C0CBE
0x1800c0cb5  mov     [rsi+3017C0h], r13d
0x1800c0cbc  jmp     short loc_1800C0CCD
0x1800c0cbe  mov     dword ptr [rsi+3017C0h], 1
0x1800c0cc8  jmp     short loc_1800C0CCD
0x1800c0cca  xor     r13d, r13d
0x1800c0ccd  mov     eax, 7
0x1800c0cd2  lea     rcx, [rsi+538h]
0x1800c0cd9  lea     edx, [rax+79h]
0x1800c0cdc  movups  xmm0, xmmword ptr [r14]
0x1800c0ce0  movups  xmm1, xmmword ptr [r14+10h]
0x1800c0ce5  movups  xmmword ptr [rcx], xmm0
0x1800c0ce8  movups  xmm0, xmmword ptr [r14+20h]
0x1800c0ced  movups  xmmword ptr [rcx+10h], xmm1
0x1800c0cf1  movups  xmm1, xmmword ptr [r14+30h]
0x1800c0cf6  movups  xmmword ptr [rcx+20h], xmm0
0x1800c0cfa  movups  xmm0, xmmword ptr [r14+40h]
0x1800c0cff  movups  xmmword ptr [rcx+30h], xmm1
0x1800c0d03  movups  xmm1, xmmword ptr [r14+50h]
0x1800c0d08  movups  xmmword ptr [rcx+40h], xmm0
0x1800c0d0c  movups  xmm0, xmmword ptr [r14+60h]
0x1800c0d11  movups  xmmword ptr [rcx+50h], xmm1
0x1800c0d15  movups  xmm1, xmmword ptr [r14+70h]
0x1800c0d1a  add     r14, rdx
0x1800c0d1d  movups  xmmword ptr [rcx+60h], xmm0
0x1800c0d21  movups  xmmword ptr [rcx+70h], xmm1
0x1800c0d25  add     rcx, rdx
0x1800c0d28  sub     rax, 1
0x1800c0d2c  jnz     short loc_1800C0CDC
0x1800c0d2e  movups  xmm0, xmmword ptr [r14]
0x1800c0d32  mov     eax, [r14+60h]
0x1800c0d36  xor     r9d, r9d; int
0x1800c0d39  movups  xmm1, xmmword ptr [r14+10h]
0x1800c0d3e  xor     r8d, r8d; int
0x1800c0d41  lea     rdx, aRdpupdatesflus; "RdpUpdatesFlushedEvent"
0x1800c0d48  movups  xmmword ptr [rcx], xmm0
0x1800c0d4b  mov     dword ptr [rsi], 1
0x1800c0d51  movups  xmm0, xmmword ptr [r14+20h]
0x1800c0d56  movups  xmmword ptr [rcx+10h], xmm1
0x1800c0d5a  movups  xmm1, xmmword ptr [r14+30h]
0x1800c0d5f  movups  xmmword ptr [rcx+20h], xmm0
0x1800c0d63  movups  xmm0, xmmword ptr [r14+40h]
0x1800c0d68  movups  xmmword ptr [rcx+30h], xmm1
0x1800c0d6c  movups  xmm1, xmmword ptr [r14+50h]
0x1800c0d71  movups  xmmword ptr [rcx+40h], xmm0
0x1800c0d75  movups  xmmword ptr [rcx+50h], xmm1
0x1800c0d79  mov     [rcx+60h], eax
0x1800c0d7c  lea     rax, [rdi+288h]
0x1800c0d83  lea     rcx, [rsi+30095Ah]
0x1800c0d8a  mov     [rsp+80h+var_58], rax; void **
0x1800c0d8f  mov     [rsp+80h+var_60], rcx; unsigned __int16 *
0x1800c0d94  mov     rcx, rdi; this
0x1800c0d97  call    ?AllocateNamedEvent@CDriverLegacy@@IEAAJPEAGHH0PEAPEAX@Z; CDriverLegacy::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800c0d9c  mov     ebx, eax
0x1800c0d9e  test    eax, eax
0x1800c0da0  jns     short loc_1800C0DCB
0x1800c0da2  mov     eax, cs:dword_1801B76C8
0x1800c0da8  cmp     eax, 2
0x1800c0dab  jbe     loc_1800C10F4
0x1800c0db1  lea     rax, aFailedToAlloca_12; "Failed to allocate flush event"
0x1800c0db8  mov     dword ptr [rbp+arg_0], 181h
0x1800c0dbf  lea     rdx, word_1801A870A
0x1800c0dc6  jmp     loc_1800C1091
0x1800c0dcb  xor     r9d, r9d; int
0x1800c0dce  lea     rax, [rsi+300B62h]
0x1800c0dd5  lea     r14, [rdi+290h]
0x1800c0ddc  mov     rcx, rdi; this
0x1800c0ddf  mov     [rsp+80h+var_58], r14; void **
0x1800c0de4  lea     rdx, aRdpwaitabortev; "RdpWaitAbortEvent"
0x1800c0deb  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800c0df0  lea     r8d, [r9+1]; int
0x1800c0df4  call    ?AllocateNamedEvent@CDriverLegacy@@IEAAJPEAGHH0PEAPEAX@Z; CDriverLegacy::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800c0df9  mov     ebx, eax
0x1800c0dfb  test    eax, eax
0x1800c0dfd  jns     short loc_1800C0E28
0x1800c0dff  mov     eax, cs:dword_1801B76C8
0x1800c0e05  cmp     eax, 2
0x1800c0e08  jbe     loc_1800C10F4
0x1800c0e0e  lea     rax, aFailedToAlloca_3; "Failed to allocate abort event"
0x1800c0e15  mov     dword ptr [rbp+arg_0], 18Ah
0x1800c0e1c  lea     rdx, dword_1801A875C
0x1800c0e23  jmp     loc_1800C1091
0x1800c0e28  mov     rcx, [r14]; hEvent
0x1800c0e2b  call    cs:__imp_ResetEvent
0x1800c0e31  lea     rax, [rsi+300F72h]
0x1800c0e38  mov     rcx, rdi; this
0x1800c0e3b  lea     r14, [rdi+298h]
0x1800c0e42  mov     [rsp+80h+var_58], r14; void **
0x1800c0e47  lea     rdx, aRdpprotocolsta; "RdpProtocolStartedEvent"
0x1800c0e4e  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800c0e53  mov     eax, 1
0x1800c0e58  mov     r9d, eax; int
0x1800c0e5b  mov     r8d, eax; int
0x1800c0e5e  call    ?AllocateNamedEvent@CDriverLegacy@@IEAAJPEAGHH0PEAPEAX@Z; CDriverLegacy::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800c0e63  mov     ebx, eax
0x1800c0e65  test    eax, eax
0x1800c0e67  jns     short loc_1800C0E92
0x1800c0e69  mov     eax, cs:dword_1801B76C8
0x1800c0e6f  cmp     eax, 2
0x1800c0e72  jbe     loc_1800C10F4
0x1800c0e78  lea     rax, aFailedToAlloca_1; "Failed to allocate protocol started eve"...
0x1800c0e7f  mov     dword ptr [rbp+arg_0], 19Ch
0x1800c0e86  lea     rdx, word_1801A8666
0x1800c0e8d  jmp     loc_1800C1091
0x1800c0e92  mov     rcx, [r14]; hEvent
0x1800c0e95  call    cs:__imp_SetEvent
0x1800c0e9b  lea     rax, [rsi+3015B2h]
0x1800c0ea2  mov     r9d, 1; int
0x1800c0ea8  lea     r14, [rdi+2A8h]
0x1800c0eaf  xor     r8d, r8d; int
0x1800c0eb2  mov     [rsp+80h+var_58], r14; void **
0x1800c0eb7  lea     rdx, aRdppipelockeve; "RdpPipeLockevent"
0x1800c0ebe  mov     rcx, rdi; this
0x1800c0ec1  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800c0ec6  call    ?AllocateNamedEvent@CDriverLegacy@@IEAAJPEAGHH0PEAPEAX@Z; CDriverLegacy::AllocateNamedEvent(ushort *,int,int,ushort *,void * *)
0x1800c0ecb  mov     ebx, eax
0x1800c0ecd  test    eax, eax
0x1800c0ecf  jns     short loc_1800C0EFA
0x1800c0ed1  mov     eax, cs:dword_1801B76C8
0x1800c0ed7  cmp     eax, 2
0x1800c0eda  jbe     loc_1800C10F4
0x1800c0ee0  lea     rax, aFailedToAlloca_10; "Failed to allocate buffer empty event"
0x1800c0ee7  mov     dword ptr [rbp+arg_0], 1AAh
0x1800c0eee  lea     rdx, unk_1801A86B8
0x1800c0ef5  jmp     loc_1800C1091
0x1800c0efa  mov     rcx, [r14]; hEvent
0x1800c0efd  call    cs:__imp_SetEvent
0x1800c0f03  lea     rax, [rdi+2A0h]
0x1800c0f0a  xor     r9d, r9d; int
0x1800c0f0d  lea     rcx, [rsi+300D6Ah]
0x1800c0f14  mov     [rsp+80h+var_58], rax; void **
0x1800c0f19  mov     [rsp+80h+var_60], rcx; unsigned __int16 *
0x1800c0f1e  lea     rdx, aRdpupdatebuffe; "RdpUpdateBufferEmptyEvent"
0x1800c0f25  mov     rcx, rdi; this
0x1800c0f28  xor     r8d, r8d; int
  ... truncated ...
```
