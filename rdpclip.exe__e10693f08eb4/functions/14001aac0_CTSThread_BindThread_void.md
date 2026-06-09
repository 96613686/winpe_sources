# CTSThread::BindThread(void)

- ea: `0x14001aac0`
- end: `0x14001aebc`
- name: `?BindThread@CTSThread@@UEAAJXZ`
- size: `1020`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1400014d4`
- `0x140004cf4`
- `0x140005750`
- `0x1400081d0`
- `0x14000c750`
- `0x14001096c`
- `0x140010998`
- `0x140018278`
- `0x140018850`
- `0x14001a998`
- `0x14001aac0`
- `0x14001b5cc`
- `0x14001bcd0`
- `0x14001d084`
- `0x14001e6dc`
- `0x1400256b4`
- `0x14006b010`

## string_xrefs

- `0x14001ac5d`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001ae32`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001ab59`: `Failed to create thread signal`
- `0x14001abf1`: `thread descriptor creation failed in bind path`
- `0x14001ac44`: `BindThread`
- `0x14001ae19`: `BindThread`
- `0x14001ac6b`: `Failing BindThread - thread does not allow binding`
- `0x14001ae44`: `Failed to InitializeInThreadContext`
- `0x14001ad95`: `Unable to add the current thread to the descriptor`

## pseudocode

```c
__int64 __fastcall CTSThread::BindThread(CTSThread *this)
{
  CTSReaderWriterLock *v2; // r12
  int Id; // ebx
  int ActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  struct CTS_TLS_ThreadDescriptor *v7; // rsi
  int v8; // r15d
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B0h] [rbp+40h] BYREF
  int v25; // [rsp+B8h] [rbp+48h] BYREF
  struct CTS_TLS_ThreadDescriptor *v26; // [rsp+C0h] [rbp+50h] BYREF
  const char *v27; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v26 = 0;
  v2 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( !*((_QWORD *)this + 85) )
  {
    Id = (*(__int64 (__fastcall **)(_QWORD, char *, unsigned int (__fastcall *)(CTSThread *), CTSThread *))(**((_QWORD **)this + 92) + 32LL))(
           *((_QWORD *)this + 92),
           (char *)this + 680,
           CTSThread::OnNotifyThreadMessage,
           this);
    if ( Id < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v5 = 48;
        v6 = "Failed to create thread signal";
LABEL_16:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)v6,
          Id);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
  }
  if ( *((_DWORD *)this + 20) != 1 )
  {
    Id = -2147467259;
    goto LABEL_45;
  }
  v7 = TSGet_TLS_ThreadDescriptor();
  if ( v7 )
  {
    v8 = 0;
    TCntPtr<CRdpClipMainWnd>::SafeRelease(&v26);
    v9 = *((_QWORD *)v7 + 4);
    v26 = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    goto LABEL_18;
  }
  Id = CTS_TLS_ThreadDescriptor::CreateInstance(1, &v26);
  if ( Id >= 0 )
  {
    v7 = v26;
    v8 = 1;
LABEL_18:
    if ( !*((_DWORD *)v7 + 124) )
    {
      Id = -2147467259;
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v24 = 913;
        v27 = "BindThread";
        v25 = -2147467259;
        v21 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v22 = "Failing BindThread - thread does not allow binding";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)&word_14007E956,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v24,
          (__int64)&v27);
      }
      goto LABEL_43;
    }
    Id = PAL_System_ThreadGetId((char *)this + 56);
    if ( Id >= 0 )
    {
      Id = PAL_System_ThreadGetDeathCondition(*((_DWORD *)this + 14), (void **)this + 8);
      if ( Id >= 0 )
      {
        Id = CTSThread::InitializeInThreadContext(this, v15);
        if ( Id < 0 )
        {
          if ( (unsigned int)dword_1400880C8 > 2 )
          {
            v24 = 935;
            v27 = "BindThread";
            v25 = -2147467259;
            v22 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
            v21 = "Failed to InitializeInThreadContext";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v16,
              (unsigned int)byte_14007E911,
              v17,
              v18,
              (__int64)&v21,
              (__int64)&v25,
              (__int64)&v22,
              (__int64)&v24,
              (__int64)&v27);
          }
        }
        else
        {
          *((_DWORD *)this + 20) = 3;
          Id = CTS_TLS_ThreadDescriptor::AddThreadToList(v7, this);
          if ( Id >= 0 )
          {
            *((_DWORD *)this + 46) = 1;
            if ( v7 != *((struct CTS_TLS_ThreadDescriptor **)this + 81) )
            {
              TCntPtr<CRdpClipMainWnd>::SafeRelease((char *)this + 648);
              *((_QWORD *)this + 81) = v7;
              if ( v7 )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 4) + 8LL))(*((_QWORD *)v7 + 4));
            }
            goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
              v19,
              (__int64)"Unable to add the current thread to the descriptor",
              Id);
          }
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v14 = 51;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v14 = 50;
LABEL_26:
        WPP_SF_(v13[2], v14, &WPP_903e1551464439edae082eb88b6439cd_Traceguids);
      }
    }
LABEL_43:
    if ( v8 )
      CTS_TLS_ThreadDescriptor::DetachThread(v7, this);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v5 = 49;
    v6 = "thread descriptor creation failed in bind path";
    goto LABEL_16;
  }
LABEL_45:
  CTSReaderWriterLock::WriteUnlock(v2);
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v26);
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v23);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x14001aac0  push    rbp
0x14001aac2  push    rbx
0x14001aac3  push    rsi
0x14001aac4  push    rdi
0x14001aac5  push    r12
0x14001aac7  push    r14
0x14001aac9  push    r15
0x14001aacb  mov     rbp, rsp
0x14001aace  sub     rsp, 70h
0x14001aad2  mov     rdi, rcx
0x14001aad5  mov     [rbp+var_10], 0
0x14001aadd  mov     [rbp+arg_10], 0
0x14001aae5  lea     r12, [rcx+94h]
0x14001aaec  mov     rcx, r12; this
0x14001aaef  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x14001aaf4  lea     rdx, [rdi+2A8h]
0x14001aafb  cmp     qword ptr [rdx], 0
0x14001aaff  jnz     short loc_14001AB65
0x14001ab01  mov     rcx, [rdi+2E0h]
0x14001ab08  lea     r8, ?OnNotifyThreadMessage@CTSThread@@KAIPEAX@Z; CTSThread::OnNotifyThreadMessage(void *)
0x14001ab0f  mov     r9, rdi
0x14001ab12  mov     rax, [rcx]
0x14001ab15  mov     rax, [rax+20h]
0x14001ab19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ab1e  mov     ebx, eax
0x14001ab20  test    eax, eax
0x14001ab22  jns     short loc_14001AB65
0x14001ab24  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab2b  lea     rax, WPP_GLOBAL_Control
0x14001ab32  cmp     rcx, rax
0x14001ab35  jz      loc_14001AE91
0x14001ab3b  test    byte ptr [rcx+1Ch], 8
0x14001ab3f  jz      loc_14001AE91
0x14001ab45  cmp     byte ptr [rcx+19h], 2
0x14001ab49  jb      loc_14001AE91
0x14001ab4f  call    RdpX_GetActivityIdPrefix
0x14001ab54  mov     edx, 30h ; '0'
0x14001ab59  lea     rcx, aFailedToCreate_19; "Failed to create thread signal"
0x14001ab60  jmp     loc_14001ABF8
0x14001ab65  mov     r14d, 1
0x14001ab6b  cmp     [rdi+50h], r14d
0x14001ab6f  jz      short loc_14001AB7B
0x14001ab71  mov     ebx, 80004005h
0x14001ab76  jmp     loc_14001AE91
0x14001ab7b  call    ?TSGet_TLS_ThreadDescriptor@@YAPEAVCTS_TLS_ThreadDescriptor@@XZ; TSGet_TLS_ThreadDescriptor(void)
0x14001ab80  mov     rsi, rax
0x14001ab83  test    rax, rax
0x14001ab86  jz      short loc_14001ABAA
0x14001ab88  lea     rcx, [rbp+arg_10]
0x14001ab8c  xor     r15d, r15d
0x14001ab8f  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001ab94  mov     rcx, [rsi+20h]
0x14001ab98  mov     [rbp+arg_10], rsi
0x14001ab9c  mov     rax, [rcx]
0x14001ab9f  mov     rax, [rax+8]
0x14001aba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aba8  jmp     short loc_14001AC27
0x14001abaa  lea     rdx, [rbp+arg_10]; struct CTS_TLS_ThreadDescriptor **
0x14001abae  mov     ecx, r14d; int
0x14001abb1  call    ?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z; CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)
0x14001abb6  mov     ebx, eax
0x14001abb8  test    eax, eax
0x14001abba  jns     short loc_14001AC20
0x14001abbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abc3  lea     rax, WPP_GLOBAL_Control
0x14001abca  cmp     rcx, rax
0x14001abcd  jz      loc_14001AE91
0x14001abd3  test    byte ptr [rcx+1Ch], 8
0x14001abd7  jz      loc_14001AE91
0x14001abdd  cmp     byte ptr [rcx+19h], 2
0x14001abe1  jb      loc_14001AE91
0x14001abe7  call    RdpX_GetActivityIdPrefix
0x14001abec  mov     edx, 31h ; '1'
0x14001abf1  lea     rcx, aThreadDescript_0; "thread descriptor creation failed in bi"...
0x14001abf8  mov     dword ptr [rsp+70h+var_48], ebx
0x14001abfc  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001ac03  mov     [rsp+70h+var_50], rcx
0x14001ac08  mov     r9d, eax
0x14001ac0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac12  mov     rcx, [rcx+10h]
0x14001ac16  call    WPP_SF_DsD
0x14001ac1b  jmp     loc_14001AE91
0x14001ac20  mov     rsi, [rbp+arg_10]
0x14001ac24  mov     r15d, r14d
0x14001ac27  cmp     dword ptr [rsi+1F0h], 0
0x14001ac2e  jnz     short loc_14001ACA3
0x14001ac30  mov     eax, cs:dword_1400880C8
0x14001ac36  mov     ebx, 80004005h
0x14001ac3b  cmp     eax, 2
0x14001ac3e  jbe     loc_14001AE81
0x14001ac44  lea     rax, aBindthread; "BindThread"
0x14001ac4b  mov     [rbp+arg_0], 391h
0x14001ac52  mov     [rbp+arg_18], rax
0x14001ac56  lea     rdx, word_14007E956
0x14001ac5d  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001ac64  mov     [rbp+arg_8], ebx
0x14001ac67  mov     [rbp+var_20], rax
0x14001ac6b  lea     rax, aFailingBindthr; "Failing BindThread - thread does not al"...
0x14001ac72  mov     [rbp+var_18], rax
0x14001ac76  lea     rax, [rbp+arg_18]
0x14001ac7a  mov     [rsp+70h+var_30], rax
0x14001ac7f  lea     rax, [rbp+arg_0]
0x14001ac83  mov     [rsp+70h+var_38], rax
0x14001ac88  lea     rax, [rbp+var_20]
0x14001ac8c  mov     [rsp+70h+var_40], rax
0x14001ac91  lea     rax, [rbp+arg_8]
0x14001ac95  mov     [rsp+70h+var_48], rax
0x14001ac9a  lea     rax, [rbp+var_18]
0x14001ac9e  jmp     loc_14001AE77
0x14001aca3  lea     rcx, [rdi+38h]
0x14001aca7  call    PAL_System_ThreadGetId
0x14001acac  mov     ebx, eax
0x14001acae  test    eax, eax
0x14001acb0  jns     short loc_14001ACF7
0x14001acb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001acb9  lea     rax, WPP_GLOBAL_Control
0x14001acc0  cmp     rcx, rax
0x14001acc3  jz      loc_14001AE81
0x14001acc9  test    [rcx+1Ch], r14b
0x14001accd  jz      loc_14001AE81
0x14001acd3  cmp     [rcx+19h], r14b
0x14001acd7  jb      loc_14001AE81
0x14001acdd  mov     edx, 32h ; '2'
0x14001ace2  mov     rcx, [rcx+10h]
0x14001ace6  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001aced  call    WPP_SF_
0x14001acf2  jmp     loc_14001AE81
0x14001acf7  mov     ecx, [rdi+38h]; dwThreadId
0x14001acfa  lea     rdx, [rdi+40h]; void **
0x14001acfe  call    ?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z; PAL_System_ThreadGetDeathCondition(ulong,void * *)
0x14001ad03  mov     ebx, eax
0x14001ad05  test    eax, eax
0x14001ad07  jns     short loc_14001AD3B
0x14001ad09  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad10  lea     rax, WPP_GLOBAL_Control
0x14001ad17  cmp     rcx, rax
0x14001ad1a  jz      loc_14001AE81
0x14001ad20  test    [rcx+1Ch], r14b
0x14001ad24  jz      loc_14001AE81
0x14001ad2a  cmp     [rcx+19h], r14b
0x14001ad2e  jb      loc_14001AE81
0x14001ad34  mov     edx, 33h ; '3'
0x14001ad39  jmp     short loc_14001ACE2
0x14001ad3b  mov     rcx, rdi; this
0x14001ad3e  call    ?InitializeInThreadContext@CTSThread@@AEAAJH@Z; CTSThread::InitializeInThreadContext(int)
0x14001ad43  mov     ebx, eax
0x14001ad45  test    eax, eax
0x14001ad47  js      loc_14001AE0E
0x14001ad4d  mov     rdx, rdi; struct ITSThread *
0x14001ad50  mov     dword ptr [rdi+50h], 3
0x14001ad57  mov     rcx, rsi; this
0x14001ad5a  call    ?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)
0x14001ad5f  mov     ebx, eax
0x14001ad61  test    eax, eax
0x14001ad63  jns     short loc_14001ADC9
0x14001ad65  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad6c  lea     rax, WPP_GLOBAL_Control
0x14001ad73  cmp     rcx, rax
0x14001ad76  jz      loc_14001AE81
0x14001ad7c  test    byte ptr [rcx+1Ch], 8
0x14001ad80  jz      loc_14001AE81
0x14001ad86  cmp     byte ptr [rcx+19h], 2
0x14001ad8a  jb      loc_14001AE81
0x14001ad90  call    RdpX_GetActivityIdPrefix
0x14001ad95  lea     rcx, aUnableToAddThe; "Unable to add the current thread to the"...
0x14001ad9c  mov     dword ptr [rsp+70h+var_48], ebx
0x14001ada0  mov     [rsp+70h+var_50], rcx
0x14001ada5  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001adac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001adb3  mov     edx, 34h ; '4'
0x14001adb8  mov     r9d, eax
0x14001adbb  mov     rcx, [rcx+10h]
0x14001adbf  call    WPP_SF_DsD
0x14001adc4  jmp     loc_14001AE81
0x14001adc9  mov     [rdi+0B8h], r14d
0x14001add0  cmp     rsi, [rdi+288h]
0x14001add7  jz      loc_14001AE91
0x14001addd  lea     rcx, [rdi+288h]
0x14001ade4  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001ade9  mov     [rdi+288h], rsi
0x14001adf0  test    rsi, rsi
0x14001adf3  jz      loc_14001AE91
0x14001adf9  mov     rcx, [rsi+20h]
0x14001adfd  mov     rax, [rcx]
0x14001ae00  mov     rax, [rax+8]
0x14001ae04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ae09  jmp     loc_14001AE91
0x14001ae0e  mov     eax, cs:dword_1400880C8
0x14001ae14  cmp     eax, 2
0x14001ae17  jbe     short loc_14001AE81
0x14001ae19  lea     rax, aBindthread; "BindThread"
0x14001ae20  mov     [rbp+arg_0], 3A7h
0x14001ae27  mov     [rbp+arg_18], rax
0x14001ae2b  lea     rdx, byte_14007E911
0x14001ae32  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001ae39  mov     [rbp+arg_8], 80004005h
0x14001ae40  mov     [rbp+var_18], rax
0x14001ae44  lea     rax, aFailedToInitia_2; "Failed to InitializeInThreadContext"
0x14001ae4b  mov     [rbp+var_20], rax
0x14001ae4f  lea     rax, [rbp+arg_18]
0x14001ae53  mov     [rsp+70h+var_30], rax
0x14001ae58  lea     rax, [rbp+arg_0]
0x14001ae5c  mov     [rsp+70h+var_38], rax
0x14001ae61  lea     rax, [rbp+var_18]
0x14001ae65  mov     [rsp+70h+var_40], rax
0x14001ae6a  lea     rax, [rbp+arg_8]
0x14001ae6e  mov     [rsp+70h+var_48], rax
0x14001ae73  lea     rax, [rbp+var_20]
0x14001ae77  mov     [rsp+70h+var_50], rax
0x14001ae7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001ae81  test    r15d, r15d
0x14001ae84  jz      short loc_14001AE91
0x14001ae86  mov     rdx, rdi; struct ITSThread *
0x14001ae89  mov     rcx, rsi; this
0x14001ae8c  call    ?DetachThread@CTS_TLS_ThreadDescriptor@@QEAAXPEAVITSThread@@@Z; CTS_TLS_ThreadDescriptor::DetachThread(ITSThread *)
0x14001ae91  mov     rcx, r12; this
0x14001ae94  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x14001ae99  lea     rcx, [rbp+arg_10]
0x14001ae9d  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001aea2  lea     rcx, [rbp+var_10]
0x14001aea6  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14001aeab  mov     eax, ebx
0x14001aead  add     rsp, 70h
0x14001aeb1  pop     r15
0x14001aeb3  pop     r14
0x14001aeb5  pop     r12
0x14001aeb7  pop     rdi
0x14001aeb8  pop     rsi
0x14001aeb9  pop     rbx
0x14001aeba  pop     rbp
0x14001aebb  retn
```
