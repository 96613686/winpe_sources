# DWMIndirect::UpdateSurfaceEx(_DWMIndirectMetaData *,uint)

- ea: `0x180006a40`
- end: `0x180006cd5`
- name: `?UpdateSurfaceEx@DWMIndirect@@UEAAJPEAU_DWMIndirectMetaData@@I@Z`
- size: `661`
- prototype: `__int64 __fastcall(DWMIndirect *__hidden this, struct _DWMIndirectMetaData *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180001290`
- `0x180001724`
- `0x180003d7c`
- `0x180004af8`
- `0x180005fcc`
- `0x18000687c`
- `0x180006a40`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006caf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006caf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b8e`

## string_xrefs

- `0x180006aa9`: `DWMIndirect::UpdateSurfaceEx for device %s`
- `0x180006aed`: `Processor not created!`
- `0x180006b06`: `UpdateSurfaceEx`
- `0x180006c0f`: `UpdateSurfaceEx`

## pseudocode

```c
__int64 __fastcall DWMIndirect::UpdateSurfaceEx(DWMIndirect *this, struct _DWMIndirectMetaData *a2, unsigned int a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 HnsTime; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  int v14; // [rsp+50h] [rbp-29h] BYREF
  int v15; // [rsp+54h] [rbp-25h] BYREF
  const char *v16; // [rsp+58h] [rbp-21h] BYREF
  char *v17; // [rsp+60h] [rbp-19h] BYREF
  const char *v18; // [rsp+68h] [rbp-11h] BYREF
  const char *v19; // [rsp+70h] [rbp-9h] BYREF
  const char *v20; // [rsp+78h] [rbp-1h] BYREF
  const char *v21; // [rsp+80h] [rbp+7h] BYREF
  GUID ActivityId; // [rsp+88h] [rbp+Fh] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &stru_1800440EC);
  v15 = 0;
  v14 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v17 = (char *)this + 788;
    v16 = "DWMIndirect::UpdateSurfaceEx for device %s";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v6,
      (__int64)word_1800373FA,
      v7,
      v8,
      (const unsigned __int16 **)&v16,
      &v17);
  }
  if ( *((_QWORD *)this + 108) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    HnsTime = DWMIndirect::GetHnsTime((DWMIndirect *)((char *)this - 48), *((_QWORD *)this + 18));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 108) + 32LL))(
      *((_QWORD *)this + 108),
      *((_QWORD *)this + 4),
      *((_QWORD *)this + 3));
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct _DWMIndirectMetaData *, _QWORD, __int64, int *, int *))(**((_QWORD **)this + 108) + 24LL))(
           *((_QWORD *)this + 108),
           a2,
           a3,
           HnsTime,
           &v15,
           &v14);
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 108) + 32LL))(*((_QWORD *)this + 108), 0, 0);
      if ( v14 )
        DWMIndirect::StopSyncThread((DWMIndirect *)((char *)this - 48));
      if ( v15 )
        DWMIndirect::UpdatePresentStats((DWMIndirect *)((char *)this - 48));
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v17) = 1070;
      v21 = "Failed to process the surface metadata";
      LODWORD(v16) = v9;
      v20 = "UpdateSurfaceEx";
      v19 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      v18 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)qword_180037360,
        v11,
        v12,
        (const unsigned __int16 **)&v18,
        (__int64)&v16,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        (const unsigned __int16 **)&v20,
        (const unsigned __int16 **)&v21);
    }
  }
  else
  {
    v9 = -2147467263;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v16) = 1048;
      v18 = "Processor not created!";
      LODWORD(v17) = -2147467263;
      v19 = "UpdateSurfaceEx";
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
      v21 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (__int64)byte_1800373AD,
        v7,
        v8,
        (const unsigned __int16 **)&v21,
        (__int64)&v17,
        (const unsigned __int16 **)&v20,
        (__int64)&v16,
        (const unsigned __int16 **)&v19,
        (const unsigned __int16 **)&v18);
    }
  }
  EventActivityIdControl(2u, &ActivityId);
  return (v9 >> 31) & 0x80004005;
}

```

## disassembly

```asm
0x180006a40  push    rbp
0x180006a42  push    rbx
0x180006a43  push    rsi
0x180006a44  push    rdi
0x180006a45  push    r12
0x180006a47  push    r14
0x180006a49  push    r15
0x180006a4b  lea     rbp, [rsp-27h]
0x180006a50  sub     rsp, 0A0h
0x180006a57  mov     rax, cs:__security_cookie
0x180006a5e  xor     rax, rsp
0x180006a61  mov     [rbp+57h+var_38], rax
0x180006a65  mov     r15, rdx
0x180006a68  mov     rsi, rcx
0x180006a6b  lea     rdx, stru_1800440EC; struct _GUID *
0x180006a72  mov     r12d, r8d
0x180006a75  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180006a79  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180006a7e  mov     eax, cs:dword_180044008
0x180006a84  mov     [rbp+57h+var_7C], 0
0x180006a8b  mov     [rbp+57h+var_80], 0
0x180006a92  cmp     eax, 5
0x180006a95  jbe     short loc_180006ACB
0x180006a97  lea     rax, [rsi+314h]
0x180006a9e  mov     [rbp+57h+var_70], rax
0x180006aa2  lea     rdx, word_1800373FA
0x180006aa9  lea     rax, aDwmindirectUpd; "DWMIndirect::UpdateSurfaceEx for device"...
0x180006ab0  mov     [rbp+57h+var_78], rax
0x180006ab4  lea     rax, [rbp+57h+var_70]
0x180006ab8  mov     [rsp+0D0h+var_A8], rax
0x180006abd  lea     rax, [rbp+57h+var_78]
0x180006ac1  mov     [rsp+0D0h+var_B0], rax
0x180006ac6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180006acb  cmp     qword ptr [rsi+360h], 0
0x180006ad3  jnz     loc_180006B6A
0x180006ad9  mov     eax, cs:dword_180044008
0x180006adf  mov     ebx, 80004001h
0x180006ae4  cmp     eax, 2
0x180006ae7  jbe     loc_180006C9D
0x180006aed  lea     rax, aProcessorNotCr; "Processor not created!"
0x180006af4  mov     dword ptr [rbp+57h+var_78], 418h
0x180006afb  mov     [rbp+57h+var_68], rax
0x180006aff  lea     rdx, byte_1800373AD
0x180006b06  lea     rax, aUpdatesurfacee; "UpdateSurfaceEx"
0x180006b0d  mov     dword ptr [rbp+57h+var_70], ebx
0x180006b10  mov     [rbp+57h+var_60], rax
0x180006b14  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180006b1b  mov     [rbp+57h+var_58], rax
0x180006b1f  lea     rax, aErrorCondition; "Error condition failed"
0x180006b26  mov     [rbp+57h+var_50], rax
0x180006b2a  lea     rax, [rbp+57h+var_68]
0x180006b2e  mov     [rsp+0D0h+var_88], rax
0x180006b33  lea     rax, [rbp+57h+var_60]
0x180006b37  mov     [rsp+0D0h+var_90], rax
0x180006b3c  lea     rax, [rbp+57h+var_78]
0x180006b40  mov     [rsp+0D0h+var_98], rax
0x180006b45  lea     rax, [rbp+57h+var_58]
0x180006b49  mov     [rsp+0D0h+var_A0], rax
0x180006b4e  lea     rax, [rbp+57h+var_70]
0x180006b52  mov     [rsp+0D0h+var_A8], rax
0x180006b57  lea     rax, [rbp+57h+var_50]
0x180006b5b  mov     [rsp+0D0h+var_B0], rax
0x180006b60  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180006b65  jmp     loc_180006C9D
0x180006b6a  lea     rcx, [rsi+58h]; lpCriticalSection
0x180006b6e  call    cs:__imp_EnterCriticalSection
0x180006b74  lea     r14, [rsi-30h]
0x180006b78  mov     rdx, [r14+0C0h]; __int64
0x180006b7f  mov     rcx, r14; this
0x180006b82  call    ?GetHnsTime@DWMIndirect@@IEAA_J_J@Z; DWMIndirect::GetHnsTime(__int64)
0x180006b87  lea     rcx, [rsi+58h]; lpCriticalSection
0x180006b8b  mov     rdi, rax
0x180006b8e  call    cs:__imp_LeaveCriticalSection
0x180006b94  mov     rcx, [rsi+360h]
0x180006b9b  mov     r8, [rsi+18h]
0x180006b9f  mov     rdx, [rsi+20h]
0x180006ba3  mov     rax, [rcx]
0x180006ba6  mov     rax, [rax+20h]
0x180006baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006baf  mov     rcx, [rsi+360h]
0x180006bb6  lea     rdx, [rbp+57h+var_80]
0x180006bba  mov     [rsp+0D0h+var_A8], rdx
0x180006bbf  mov     r9, rdi
0x180006bc2  lea     rdx, [rbp+57h+var_7C]
0x180006bc6  mov     r8d, r12d
0x180006bc9  mov     [rsp+0D0h+var_B0], rdx
0x180006bce  mov     rdx, r15
0x180006bd1  mov     rax, [rcx]
0x180006bd4  mov     rax, [rax+18h]
0x180006bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdd  mov     ebx, eax
0x180006bdf  test    eax, eax
0x180006be1  jns     loc_180006C69
0x180006be7  mov     ecx, cs:dword_180044008
0x180006bed  cmp     ecx, 2
0x180006bf0  jbe     loc_180006C9D
0x180006bf6  lea     rax, aFailedToProces_3; "Failed to process the surface metadata"
0x180006bfd  mov     dword ptr [rbp+57h+var_70], 42Eh
0x180006c04  mov     [rbp+57h+var_50], rax
0x180006c08  lea     rdx, qword_180037360
0x180006c0f  lea     rax, aUpdatesurfacee; "UpdateSurfaceEx"
0x180006c16  mov     dword ptr [rbp+57h+var_78], ebx
0x180006c19  mov     [rbp+57h+var_58], rax
0x180006c1d  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180006c24  mov     [rbp+57h+var_60], rax
0x180006c28  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180006c2f  mov     [rbp+57h+var_68], rax
0x180006c33  lea     rax, [rbp+57h+var_50]
0x180006c37  mov     [rsp+0D0h+var_88], rax
0x180006c3c  lea     rax, [rbp+57h+var_58]
0x180006c40  mov     [rsp+0D0h+var_90], rax
0x180006c45  lea     rax, [rbp+57h+var_70]
0x180006c49  mov     [rsp+0D0h+var_98], rax
0x180006c4e  lea     rax, [rbp+57h+var_60]
0x180006c52  mov     [rsp+0D0h+var_A0], rax
0x180006c57  lea     rax, [rbp+57h+var_78]
0x180006c5b  mov     [rsp+0D0h+var_A8], rax
0x180006c60  lea     rax, [rbp+57h+var_68]
0x180006c64  jmp     loc_180006B5B
0x180006c69  mov     rcx, [rsi+360h]
0x180006c70  xor     r8d, r8d
0x180006c73  xor     edx, edx
0x180006c75  mov     rax, [rcx]
0x180006c78  mov     rax, [rax+20h]
0x180006c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c81  cmp     [rbp+57h+var_80], 0
0x180006c85  jz      short loc_180006C8F
0x180006c87  mov     rcx, r14; this
0x180006c8a  call    ?StopSyncThread@DWMIndirect@@IEAAXXZ; DWMIndirect::StopSyncThread(void)
0x180006c8f  cmp     [rbp+57h+var_7C], 0
0x180006c93  jz      short loc_180006C9D
0x180006c95  mov     rcx, r14; this
0x180006c98  call    ?UpdatePresentStats@DWMIndirect@@IEAAXXZ; DWMIndirect::UpdatePresentStats(void)
0x180006c9d  sar     ebx, 1Fh
0x180006ca0  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180006ca4  and     ebx, 80004005h
0x180006caa  mov     ecx, 2; ControlCode
0x180006caf  call    cs:__imp_EventActivityIdControl
0x180006cb5  mov     eax, ebx
0x180006cb7  mov     rcx, [rbp+57h+var_38]
0x180006cbb  xor     rcx, rsp; StackCookie
0x180006cbe  call    __security_check_cookie
0x180006cc3  add     rsp, 0A0h
0x180006cca  pop     r15
0x180006ccc  pop     r14
0x180006cce  pop     r12
0x180006cd0  pop     rdi
0x180006cd1  pop     rsi
0x180006cd2  pop     rbx
0x180006cd3  pop     rbp
0x180006cd4  retn
```
