# RdpRemoteAppAuxRedirectionHandler::SendCreateVailSuperWetInk(HWND__ *,_GUID const &,uint,uint,uint,_GUID const &,uint,uint,uint)

- ea: `0x180018b2c`
- end: `0x180018e68`
- name: `?SendCreateVailSuperWetInk@RdpRemoteAppAuxRedirectionHandler@@IEAAJPEAUHWND__@@AEBU_GUID@@III1III@Z`
- size: `828`
- prototype: `__int64 __usercall@<rax>(RdpRemoteAppAuxRedirectionHandler *__hidden this@<rcx>, HWND@<rdx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, const struct _GUID *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180018020`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x1800144c8`
- `0x180017a78`
- `0x180018b2c`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x180018b96`: `Channel not initialized. Dropping RDPXREMOTEAPPAUXREDIRECTION_CREATE_VAIL_SUPER_WET_INK_PDU`
- `0x180018baf`: `SendCreateVailSuperWetInk`
- `0x180018c5d`: `SendCreateVailSuperWetInk`
- `0x180018ddb`: `SendCreateVailSuperWetInk`
- `0x180018dc2`: `Failed to send XREMOTEAPPAUXREDIRECTION_PDU_TYPE_CREATE_VAIL_SUPER_WET_INK PDU`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::SendCreateVailSuperWetInk(
        RdpRemoteAppAuxRedirectionHandler *this,
        HWND a2,
        const struct _GUID *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        const struct _GUID *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10)
{
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  int v25; // [rsp+50h] [rbp-79h] BYREF
  int v26; // [rsp+54h] [rbp-75h] BYREF
  CTSCriticalSection *v27; // [rsp+58h] [rbp-71h] BYREF
  const char *v28; // [rsp+60h] [rbp-69h] BYREF
  const char *v29; // [rsp+68h] [rbp-61h] BYREF
  __int64 v30; // [rsp+70h] [rbp-59h] BYREF
  const char *v31; // [rsp+78h] [rbp-51h] BYREF
  _DWORD v32[2]; // [rsp+80h] [rbp-49h] BYREF
  HWND v33; // [rsp+88h] [rbp-41h]
  unsigned int Data1; // [rsp+90h] [rbp-39h]
  unsigned __int16 Data2; // [rsp+94h] [rbp-35h]
  unsigned __int16 Data3; // [rsp+96h] [rbp-33h]
  unsigned __int8 v37; // [rsp+98h] [rbp-31h]
  unsigned __int8 v38; // [rsp+99h] [rbp-30h]
  unsigned __int8 v39; // [rsp+9Ah] [rbp-2Fh]
  unsigned __int8 v40; // [rsp+9Bh] [rbp-2Eh]
  unsigned __int8 v41; // [rsp+9Ch] [rbp-2Dh]
  unsigned __int8 v42; // [rsp+9Dh] [rbp-2Ch]
  unsigned __int8 v43; // [rsp+9Eh] [rbp-2Bh]
  unsigned __int8 v44; // [rsp+9Fh] [rbp-2Ah]
  int v45; // [rsp+A0h] [rbp-29h]
  unsigned int v46; // [rsp+A4h] [rbp-25h]
  unsigned int v47; // [rsp+A8h] [rbp-21h]
  struct _GUID v48; // [rsp+ACh] [rbp-1Dh]
  unsigned int v49; // [rsp+BCh] [rbp-Dh]
  unsigned int v50; // [rsp+C0h] [rbp-9h]
  unsigned int v51; // [rsp+C4h] [rbp-5h]

  memset_0(v32, 0, 0x48u);
  v30 = 0;
  v14 = RdpRemoteAppAuxRedirectionHandler::EnsureChannelInitialized(this);
  if ( v14 >= 0 )
  {
    v27 = (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64);
    CTSCriticalSection::Lock((RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64));
    if ( *((_QWORD *)this + 10) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v30);
      v17 = *((_QWORD *)this + 10);
      v30 = v17;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v30);
    }
    else
    {
      v17 = 0;
    }
    CTSAutoLock::~CTSAutoLock(&v27);
    if ( v17 )
    {
      Data1 = a3->Data1;
      Data2 = a3->Data2;
      Data3 = a3->Data3;
      v37 = a3->Data4[0];
      v38 = a3->Data4[1];
      v39 = a3->Data4[2];
      v40 = a3->Data4[3];
      v41 = a3->Data4[4];
      v42 = a3->Data4[5];
      v43 = a3->Data4[6];
      v44 = a3->Data4[7];
      v46 = a5;
      v47 = a6;
      v48 = *a7;
      v49 = a8;
      v50 = a9;
      v51 = a10;
      v32[0] = 3;
      v32[1] = 72;
      v33 = a2;
      v45 = a4;
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v17 + 24LL))(v17, 72, v32);
      if ( v14 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v26 = 653;
        v27 = (CTSCriticalSection *)"Failed to send XREMOTEAPPAUXREDIRECTION_PDU_TYPE_CREATE_VAIL_SUPER_WET_INK PDU";
        v25 = v14;
        v29 = "SendCreateVailSuperWetInk";
        v28 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v31 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v21,
          (__int64)&unk_18003DBF8,
          v22,
          v23,
          (const unsigned __int16 **)&v31,
          (__int64)&v25,
          (const unsigned __int16 **)&v28,
          (__int64)&v26,
          (const unsigned __int16 **)&v29,
          (const unsigned __int16 **)&v27);
      }
    }
    else
    {
      v14 = -2147467261;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v26 = 632;
        v27 = (CTSCriticalSection *)"SendCreateVailSuperWetInk";
        v25 = -2147467261;
        v29 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v28 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v18,
          (__int64)word_18003DC5A,
          v19,
          v20,
          (const unsigned __int16 **)&v28,
          (__int64)&v25,
          (const unsigned __int16 **)&v29,
          (__int64)&v26,
          (const unsigned __int16 **)&v27);
      }
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v25 = 625;
    v31 = "Channel not initialized. Dropping RDPXREMOTEAPPAUXREDIRECTION_CREATE_VAIL_SUPER_WET_INK_PDU";
    v26 = v14;
    v28 = "SendCreateVailSuperWetInk";
    v29 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
    v27 = (CTSCriticalSection *)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_18003DCB4,
      v15,
      v16,
      (const unsigned __int16 **)&v27,
      (__int64)&v26,
      (const unsigned __int16 **)&v29,
      (__int64)&v25,
      (const unsigned __int16 **)&v28,
      (const unsigned __int16 **)&v31);
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v30);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180018b2c  mov     [rsp-8+arg_10], rbx
0x180018b31  push    rbp
0x180018b32  push    rsi
0x180018b33  push    rdi
0x180018b34  push    r14
0x180018b36  push    r15
0x180018b38  lea     rbp, [rsp-7]
0x180018b3d  sub     rsp, 0D0h
0x180018b44  mov     rax, cs:__security_cookie
0x180018b4b  xor     rax, rsp
0x180018b4e  mov     [rbp+27h+var_28], rax
0x180018b52  mov     r14, rdx
0x180018b55  mov     rsi, r8
0x180018b58  xor     edx, edx; Val
0x180018b5a  mov     rdi, rcx
0x180018b5d  lea     rcx, [rbp+27h+var_70]; void *
0x180018b61  mov     r15d, r9d
0x180018b64  lea     r8d, [rdx+48h]; Size
0x180018b68  call    memset_0
0x180018b6d  mov     rcx, rdi; this
0x180018b70  mov     [rbp+27h+var_80], 0
0x180018b78  call    ?EnsureChannelInitialized@RdpRemoteAppAuxRedirectionHandler@@IEAAJXZ; RdpRemoteAppAuxRedirectionHandler::EnsureChannelInitialized(void)
0x180018b7d  mov     ebx, eax
0x180018b7f  test    eax, eax
0x180018b81  jns     loc_180018C09
0x180018b87  mov     ecx, cs:dword_180044008
0x180018b8d  cmp     ecx, 2
0x180018b90  jbe     loc_180018E3A
0x180018b96  lea     rax, aChannelNotInit_6; "Channel not initialized. Dropping RDPXR"...
0x180018b9d  mov     [rbp+27h+var_A0], 271h
0x180018ba4  mov     [rbp+27h+var_78], rax
0x180018ba8  lea     rdx, dword_18003DCB4
0x180018baf  lea     rax, aSendcreatevail; "SendCreateVailSuperWetInk"
0x180018bb6  mov     [rbp+27h+var_9C], ebx
0x180018bb9  mov     [rbp+27h+var_90], rax
0x180018bbd  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018bc4  mov     [rbp+27h+var_88], rax
0x180018bc8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180018bcf  mov     [rbp+27h+var_98], rax
0x180018bd3  lea     rax, [rbp+27h+var_78]
0x180018bd7  mov     [rsp+0F0h+var_A8], rax
0x180018bdc  lea     rax, [rbp+27h+var_90]
0x180018be0  mov     [rsp+0F0h+var_B0], rax
0x180018be5  lea     rax, [rbp+27h+var_A0]
0x180018be9  mov     [rsp+0F0h+var_B8], rax
0x180018bee  lea     rax, [rbp+27h+var_88]
0x180018bf2  mov     [rsp+0F0h+var_C0], rax
0x180018bf7  lea     rax, [rbp+27h+var_9C]
0x180018bfb  mov     [rsp+0F0h+var_C8], rax
0x180018c00  lea     rax, [rbp+27h+var_98]
0x180018c04  jmp     loc_180018E30
0x180018c09  lea     rcx, [rdi+40h]; this
0x180018c0d  mov     [rbp+27h+var_98], rcx
0x180018c11  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180018c16  cmp     qword ptr [rdi+50h], 0
0x180018c1b  jnz     short loc_180018C21
0x180018c1d  xor     ebx, ebx
0x180018c1f  jmp     short loc_180018C3B
0x180018c21  lea     rcx, [rbp+27h+var_80]
0x180018c25  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018c2a  mov     rbx, [rdi+50h]
0x180018c2e  lea     rcx, [rbp+27h+var_80]
0x180018c32  mov     [rbp+27h+var_80], rbx
0x180018c36  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180018c3b  lea     rcx, [rbp+27h+var_98]; this
0x180018c3f  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180018c44  test    rbx, rbx
0x180018c47  jnz     short loc_180018CC6
0x180018c49  mov     eax, cs:dword_180044008
0x180018c4f  mov     ebx, 80004003h
0x180018c54  cmp     eax, 2
0x180018c57  jbe     loc_180018E3A
0x180018c5d  lea     rax, aSendcreatevail; "SendCreateVailSuperWetInk"
0x180018c64  mov     [rbp+27h+var_9C], 278h
0x180018c6b  mov     [rbp+27h+var_98], rax
0x180018c6f  lea     rdx, word_18003DC5A
0x180018c76  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018c7d  mov     [rbp+27h+var_A0], ebx
0x180018c80  mov     [rbp+27h+var_88], rax
0x180018c84  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180018c8b  mov     [rbp+27h+var_90], rax
0x180018c8f  lea     rax, [rbp+27h+var_98]
0x180018c93  mov     [rsp+0F0h+var_B0], rax
0x180018c98  lea     rax, [rbp+27h+var_9C]
0x180018c9c  mov     [rsp+0F0h+var_B8], rax
0x180018ca1  lea     rax, [rbp+27h+var_88]
0x180018ca5  mov     [rsp+0F0h+var_C0], rax
0x180018caa  lea     rax, [rbp+27h+var_A0]
0x180018cae  mov     [rsp+0F0h+var_C8], rax
0x180018cb3  lea     rax, [rbp+27h+var_90]
0x180018cb7  mov     [rsp+0F0h+var_D0], rax
0x180018cbc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018cc1  jmp     loc_180018E3A
0x180018cc6  mov     r8, [rbp+27h+arg_30]
0x180018cca  xor     r9d, r9d
0x180018ccd  mov     eax, [rsi]
0x180018ccf  mov     rcx, rbx
0x180018cd2  mov     [rbp+27h+var_60], eax
0x180018cd5  movzx   eax, word ptr [rsi+4]
0x180018cd9  mov     [rbp+27h+var_5C], ax
0x180018cdd  lea     edx, [r9+48h]
0x180018ce1  movzx   eax, word ptr [rsi+6]
0x180018ce5  mov     [rbp+27h+var_5A], ax
0x180018ce9  mov     al, [rsi+8]
0x180018cec  mov     [rbp+27h+var_58], al
0x180018cef  mov     al, [rsi+9]
0x180018cf2  mov     [rbp+27h+var_57], al
0x180018cf5  mov     al, [rsi+0Ah]
0x180018cf8  mov     [rbp+27h+var_56], al
0x180018cfb  mov     al, [rsi+0Bh]
0x180018cfe  mov     [rbp+27h+var_55], al
0x180018d01  mov     al, [rsi+0Ch]
0x180018d04  mov     [rbp+27h+var_54], al
0x180018d07  mov     al, [rsi+0Dh]
0x180018d0a  mov     [rbp+27h+var_53], al
0x180018d0d  mov     al, [rsi+0Eh]
0x180018d10  mov     [rbp+27h+var_52], al
0x180018d13  mov     al, [rsi+0Fh]
0x180018d16  mov     [rbp+27h+var_51], al
0x180018d19  mov     eax, [rbp+27h+arg_20]
0x180018d1c  mov     [rbp+27h+var_4C], eax
0x180018d1f  mov     eax, [rbp+27h+arg_28]
0x180018d22  mov     [rbp+27h+var_48], eax
0x180018d25  mov     eax, [r8]
0x180018d28  mov     [rbp+27h+var_44], eax
0x180018d2b  movzx   eax, word ptr [r8+4]
0x180018d30  mov     [rbp+27h+var_40], ax
0x180018d34  movzx   eax, word ptr [r8+6]
0x180018d39  mov     [rbp+27h+var_3E], ax
0x180018d3d  mov     al, [r8+8]
0x180018d41  mov     [rbp+27h+var_3C], al
0x180018d44  mov     al, [r8+9]
0x180018d48  mov     [rbp+27h+var_3B], al
0x180018d4b  mov     al, [r8+0Ah]
0x180018d4f  mov     [rbp+27h+var_3A], al
0x180018d52  mov     al, [r8+0Bh]
0x180018d56  mov     [rbp+27h+var_39], al
0x180018d59  mov     al, [r8+0Ch]
0x180018d5d  mov     [rbp+27h+var_38], al
0x180018d60  mov     al, [r8+0Dh]
0x180018d64  mov     [rbp+27h+var_37], al
0x180018d67  mov     al, [r8+0Eh]
0x180018d6b  mov     [rbp+27h+var_36], al
0x180018d6e  mov     al, [r8+0Fh]
0x180018d72  lea     r8, [rbp+27h+var_70]
0x180018d76  mov     [rbp+27h+var_35], al
0x180018d79  mov     eax, [rbp+27h+arg_38]
0x180018d7c  mov     [rbp+27h+var_34], eax
0x180018d7f  mov     eax, [rbp+27h+arg_40]
0x180018d82  mov     [rbp+27h+var_30], eax
0x180018d85  mov     eax, [rbp+27h+arg_48]
0x180018d88  mov     [rbp+27h+var_2C], eax
0x180018d8b  mov     [rbp+27h+var_70], 3
0x180018d92  mov     [rbp+27h+var_6C], 48h ; 'H'
0x180018d99  mov     [rbp+27h+var_68], r14
0x180018d9d  mov     [rbp+27h+var_50], r15d
0x180018da1  mov     rax, [rbx]
0x180018da4  mov     rax, [rax+18h]
0x180018da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dad  mov     ebx, eax
0x180018daf  test    eax, eax
0x180018db1  jns     loc_180018E3A
0x180018db7  mov     eax, cs:dword_180044008
0x180018dbd  cmp     eax, 2
0x180018dc0  jbe     short loc_180018E3A
0x180018dc2  lea     rax, aFailedToSendXr_1; "Failed to send XREMOTEAPPAUXREDIRECTION"...
0x180018dc9  mov     [rbp+27h+var_9C], 28Dh
0x180018dd0  mov     [rbp+27h+var_98], rax
0x180018dd4  lea     rdx, unk_18003DBF8
0x180018ddb  lea     rax, aSendcreatevail; "SendCreateVailSuperWetInk"
0x180018de2  mov     [rbp+27h+var_A0], ebx
0x180018de5  mov     [rbp+27h+var_88], rax
0x180018de9  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018df0  mov     [rbp+27h+var_90], rax
0x180018df4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180018dfb  mov     [rbp+27h+var_78], rax
0x180018dff  lea     rax, [rbp+27h+var_98]
0x180018e03  mov     [rsp+0F0h+var_A8], rax
0x180018e08  lea     rax, [rbp+27h+var_88]
0x180018e0c  mov     [rsp+0F0h+var_B0], rax
0x180018e11  lea     rax, [rbp+27h+var_9C]
0x180018e15  mov     [rsp+0F0h+var_B8], rax
0x180018e1a  lea     rax, [rbp+27h+var_90]
0x180018e1e  mov     [rsp+0F0h+var_C0], rax
0x180018e23  lea     rax, [rbp+27h+var_A0]
0x180018e27  mov     [rsp+0F0h+var_C8], rax
0x180018e2c  lea     rax, [rbp+27h+var_78]
0x180018e30  mov     [rsp+0F0h+var_D0], rax
0x180018e35  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180018e3a  lea     rcx, [rbp+27h+var_80]
0x180018e3e  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018e43  mov     eax, ebx
0x180018e45  mov     rcx, [rbp+27h+var_28]
0x180018e49  xor     rcx, rsp; StackCookie
0x180018e4c  call    __security_check_cookie
0x180018e51  mov     rbx, [rsp+0F0h+arg_10]
0x180018e59  add     rsp, 0D0h
0x180018e60  pop     r15
0x180018e62  pop     r14
0x180018e64  pop     rdi
0x180018e65  pop     rsi
0x180018e66  pop     rbp
0x180018e67  retn
```
