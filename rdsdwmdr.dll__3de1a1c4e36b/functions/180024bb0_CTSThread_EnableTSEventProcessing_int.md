# CTSThread::EnableTSEventProcessing(int)

- ea: `0x180024bb0`
- end: `0x180024d13`
- name: `?EnableTSEventProcessing@CTSThread@@UEAAJH@Z`
- size: `355`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001f98`
- `0x18000f08c`
- `0x18001d114`
- `0x180023b54`
- `0x180024bb0`
- `0x180026084`
- `0x180026168`
- `0x180026b30`
- `0x180027b6c`
- `0x180027b98`
- `0x18002a1c4`

## string_xrefs

- `0x180024c19`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180024cb8`: `Created Block All Filter failed`

## pseudocode

```c
__int64 __fastcall CTSThread::EnableTSEventProcessing(CTSThread *this, int a2)
{
  CTSReaderWriterLock *v4; // rsi
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  int ActivityIdPrefix; // eax
  int v14; // [rsp+28h] [rbp-40h]
  const char *v15; // [rsp+50h] [rbp-18h] BYREF
  const char *v16; // [rsp+58h] [rbp-10h] BYREF
  struct ITSEventFilter *v17; // [rsp+90h] [rbp+28h] BYREF
  int v18; // [rsp+98h] [rbp+30h] BYREF
  int v19; // [rsp+A0h] [rbp+38h] BYREF
  const char *v20; // [rsp+A8h] [rbp+40h] BYREF

  v4 = (CTSThread *)((char *)this + 164);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 164));
  if ( a2 )
  {
    v6 = CTSThread::PopEventFilter(this);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = v6;
        v20 = "EnableTSEventProcessing";
        LODWORD(v17) = 2327;
        v15 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v16 = "PopEventFilter failed (mismatched push/pop) 0x%x\n";
        v19 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v5,
          (__int64)&dword_18003F5FC,
          v7,
          v8,
          (const unsigned __int16 **)&v16,
          (__int64)&v19,
          (const unsigned __int16 **)&v15,
          (__int64)&v17,
          (const unsigned __int16 **)&v20,
          (__int64)&v18);
      }
    }
    else
    {
      v6 = CTSThread::SignalEventQueue(this);
    }
  }
  else
  {
    v17 = 0;
    v6 = CTSEventFilterFactory::CreateBlockAllFilter(&v17);
    if ( v6 >= 0 )
    {
      v6 = CTSThread::PushEventFilter(this, v17);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v9, v10, v11);
      v14 = v6;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        (__int64)"Created Block All Filter failed",
        v14);
    }
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v17);
  }
  CTSReaderWriterLock::WriteUnlock(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180024bb0  push    rbp
0x180024bb2  push    rbx
0x180024bb3  push    rsi
0x180024bb4  push    rdi
0x180024bb5  mov     rbp, rsp
0x180024bb8  sub     rsp, 68h
0x180024bbc  mov     ebx, edx
0x180024bbe  mov     rdi, rcx
0x180024bc1  lea     rsi, [rcx+0A4h]
0x180024bc8  mov     rcx, rsi; this
0x180024bcb  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180024bd0  test    ebx, ebx
0x180024bd2  jz      loc_180024C7D
0x180024bd8  mov     rcx, rdi
0x180024bdb  call    ?PopEventFilter@CTSThread@@AEAAJW4TSEventFilterType@@@Z; CTSThread::PopEventFilter(TSEventFilterType)
0x180024be0  mov     ebx, eax
0x180024be2  test    eax, eax
0x180024be4  js      short loc_180024BF5
0x180024be6  mov     rcx, rdi; this
0x180024be9  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x180024bee  mov     ebx, eax
0x180024bf0  jmp     loc_180024D00
0x180024bf5  mov     eax, cs:dword_180044008
0x180024bfb  cmp     eax, 2
0x180024bfe  jbe     loc_180024D00
0x180024c04  lea     rax, aEnabletseventp; "EnableTSEventProcessing"
0x180024c0b  mov     [rbp+arg_8], ebx
0x180024c0e  mov     [rbp+arg_18], rax
0x180024c12  lea     rdx, dword_18003F5FC
0x180024c19  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180024c20  mov     dword ptr [rbp+arg_0], 917h
0x180024c27  mov     [rbp+var_18], rax
0x180024c2b  lea     rax, aPopeventfilter; "PopEventFilter failed (mismatched push/"...
0x180024c32  mov     [rbp+var_10], rax
0x180024c36  lea     rax, [rbp+arg_8]
0x180024c3a  mov     [rsp+68h+var_20], rax
0x180024c3f  lea     rax, [rbp+arg_18]
0x180024c43  mov     [rsp+68h+var_28], rax
0x180024c48  lea     rax, [rbp+arg_0]
0x180024c4c  mov     [rsp+68h+var_30], rax
0x180024c51  lea     rax, [rbp+var_18]
0x180024c55  mov     [rsp+68h+var_38], rax
0x180024c5a  lea     rax, [rbp+arg_10]
0x180024c5e  mov     [rsp+68h+var_40], rax
0x180024c63  lea     rax, [rbp+var_10]
0x180024c67  mov     [rsp+68h+var_48], rax
0x180024c6c  mov     [rbp+arg_10], 80004005h
0x180024c73  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180024c78  jmp     loc_180024D00
0x180024c7d  lea     rcx, [rbp+arg_0]; struct ITSEventFilter **
0x180024c81  mov     [rbp+arg_0], 0
0x180024c89  call    ?CreateBlockAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateBlockAllFilter(ITSEventFilter * *)
0x180024c8e  mov     ebx, eax
0x180024c90  test    eax, eax
0x180024c92  jns     short loc_180024CE9
0x180024c94  mov     rax, cs:WPP_GLOBAL_Control
0x180024c9b  lea     rcx, WPP_GLOBAL_Control
0x180024ca2  cmp     rax, rcx
0x180024ca5  jz      short loc_180024CF7
0x180024ca7  test    byte ptr [rax+1Ch], 8
0x180024cab  jz      short loc_180024CF7
0x180024cad  cmp     byte ptr [rax+19h], 2
0x180024cb1  jb      short loc_180024CF7
0x180024cb3  call    RdpX_GetActivityIdPrefix
0x180024cb8  lea     rcx, aCreatedBlockAl; "Created Block All Filter failed"
0x180024cbf  mov     dword ptr [rsp+68h+var_40], ebx
0x180024cc3  mov     [rsp+68h+var_48], rcx
0x180024cc8  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180024ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cd6  mov     edx, 6Fh ; 'o'
0x180024cdb  mov     r9d, eax
0x180024cde  mov     rcx, [rcx+10h]
0x180024ce2  call    WPP_SF_DsD
0x180024ce7  jmp     short loc_180024CF7
0x180024ce9  mov     rdx, [rbp+arg_0]; struct ITSEventFilter *
0x180024ced  mov     rcx, rdi; this
0x180024cf0  call    ?PushEventFilter@CTSThread@@AEAAJPEAVITSEventFilter@@@Z; CTSThread::PushEventFilter(ITSEventFilter *)
0x180024cf5  mov     ebx, eax
0x180024cf7  lea     rcx, [rbp+arg_0]
0x180024cfb  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180024d00  mov     rcx, rsi; this
0x180024d03  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180024d08  mov     eax, ebx
0x180024d0a  add     rsp, 68h
0x180024d0e  pop     rdi
0x180024d0f  pop     rsi
0x180024d10  pop     rbx
0x180024d11  pop     rbp
0x180024d12  retn
```
