# Rdp::Avenc::Ic3::CIc3Processor::CommitMonitors(void)

- ea: `0x18003ef00`
- end: `0x18003f22b`
- name: `?CommitMonitors@CIc3Processor@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `811`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CIc3Processor *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x18000e848`
- `0x1800126b0`
- `0x1800146bc`
- `0x180015480`
- `0x18001a810`
- `0x1800203d4`
- `0x18003ef00`
- `0x180041074`
- `0x1800422bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ef60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f1e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ef60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f1e0`

## string_xrefs

- `0x18003effb`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003f0aa`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003f126`: `Skipping virtual desktop update - not supported by client`
- `0x18003f0f6`: `Unable to send update virtual desktop pdu.`
- `0x18003f135`: `Rdp::Avenc::Ic3::CIc3Processor::CommitMonitors`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CIc3Processor::CommitMonitors(Rdp::Avenc::Ic3::CIc3Processor *this)
{
  char v2; // bl
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int *v8; // r9
  unsigned int Int32; // eax
  int *v10; // r9
  unsigned int v11; // eax
  unsigned int *v12; // r9
  unsigned int UInt32; // eax
  unsigned int *v14; // r9
  unsigned int v15; // eax
  int v16; // r8d
  const char *v17; // r9
  Rdp::Avenc::Ic3::CDsGfxChannel *v18; // rcx
  unsigned int updated; // eax
  bool v20; // di
  char v21; // al
  int v22; // r8d
  int v23; // edx
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-68h]
  int v26; // [rsp+20h] [rbp-68h]
  int v27; // [rsp+28h] [rbp-60h]
  char *v28; // [rsp+28h] [rbp-60h]
  char *v29; // [rsp+28h] [rbp-60h]
  char *v30; // [rsp+28h] [rbp-60h]
  char *v31; // [rsp+28h] [rbp-60h]
  char *v32; // [rsp+28h] [rbp-60h]
  char *v33; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v35; // [rsp+90h] [rbp+8h] BYREF
  const char *v36; // [rsp+98h] [rbp+10h] BYREF
  const char *v37; // [rsp+A0h] [rbp+18h] BYREF
  const char *v38; // [rsp+A8h] [rbp+20h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v25,
      v27,
      16,
      &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v25) = *((_BYTE *)this + 152) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)0x8000FFFFLL,
      v25,
      (bool)"Processor is not started",
      v33);
    Int32 = Rdp::Utils::Props::IPropertyStore_GetInt32(
              *((Rdp::Utils::Props **)this + 1),
              (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
              (const struct _tagpropertykey *)this + 3,
              v8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Int32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_X",
      v28);
    v11 = Rdp::Utils::Props::IPropertyStore_GetInt32(
            *((Rdp::Utils::Props **)this + 1),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
            (const struct _tagpropertykey *)((char *)this + 64),
            v10);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v11,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_Y",
      v29);
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *((Rdp::Utils::Props **)this + 1),
               (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
               (const struct _tagpropertykey *)((char *)this + 68),
               v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Width property",
      v30);
    v15 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            *((Rdp::Utils::Props **)this + 1),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
            (const struct _tagpropertykey *)((char *)this + 72),
            v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v15,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Height property",
      v31);
    v18 = (Rdp::Avenc::Ic3::CDsGfxChannel *)*((_QWORD *)this + 20);
    if ( v18 && Rdp::Avenc::Ic3::CDsGfxChannel::GetClientSupportsMultiMonitor(v18) )
    {
      updated = Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu(
                  *((Rdp::Avenc::Ic3::CDsGfxChannel **)this + 20),
                  *((_DWORD *)this + 15),
                  *((_DWORD *)this + 16),
                  *((_DWORD *)this + 17),
                  *((_DWORD *)this + 18));
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)updated,
        (int)"Unable to send update virtual desktop pdu.",
        v32);
    }
    else if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v36 = "Skipping virtual desktop update - not supported by client";
      v37 = "Rdp::Avenc::Ic3::CIc3Processor::CommitMonitors";
      v35 = 380;
      v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800AFBDA,
        v16,
        (_DWORD)v17,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v37,
        (__int64)&v36);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = GetCurrentThreadId();
      LOBYTE(v22) = v20;
      LOBYTE(v23) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v22,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v26,
        (int)v32,
        17,
        &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
        v21);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x182,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18003ef00  push    rbx
0x18003ef02  push    rsi
0x18003ef03  push    rdi
0x18003ef04  push    r12
0x18003ef06  push    r13
0x18003ef08  push    r14
0x18003ef0a  push    r15
0x18003ef0c  sub     rsp, 50h
0x18003ef10  mov     rdi, rcx
0x18003ef13  lea     rcx, WPP_GLOBAL_Control
0x18003ef1a  mov     rax, cs:WPP_GLOBAL_Control
0x18003ef21  mov     bl, 1
0x18003ef23  cmp     rax, rcx
0x18003ef26  jz      short loc_18003EF38
0x18003ef28  test    [rax+1Ch], bl
0x18003ef2b  jz      short loc_18003EF38
0x18003ef2d  cmp     byte ptr [rax+19h], 4
0x18003ef31  jb      short loc_18003EF38
0x18003ef33  mov     sil, bl
0x18003ef36  jmp     short loc_18003EF3B
0x18003ef38  xor     sil, sil
0x18003ef3b  lea     rax, WPP_RECORDER_INITIALIZED
0x18003ef42  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003ef49  setnz   r14b
0x18003ef4d  test    sil, sil
0x18003ef50  jnz     short loc_18003EF60
0x18003ef52  test    r14b, r14b
0x18003ef55  jnz     short loc_18003EF60
0x18003ef57  lea     r15, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x18003ef5e  jmp     short loc_18003EF97
0x18003ef60  call    cs:__imp_GetCurrentThreadId
0x18003ef66  mov     dword ptr [rsp+88h+var_48], eax; char
0x18003ef6a  lea     r15, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x18003ef71  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18003ef76  mov     word ptr [rsp+88h+var_58], 10h; char *
0x18003ef7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef84  mov     r9, [rcx+28h]; int
0x18003ef88  mov     r8b, r14b; int
0x18003ef8b  mov     dl, sil; int
0x18003ef8e  mov     rcx, [rcx+10h]; int
0x18003ef92  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003ef97  cmp     byte ptr [rdi+98h], 0
0x18003ef9e  setz    al
0x18003efa1  mov     rcx, [rsp+88h]; this
0x18003efa9  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18003efb0  mov     [rsp+88h+var_60], rdx; char *
0x18003efb5  mov     byte ptr [rsp+88h+var_68], al; int
0x18003efb9  mov     r9d, 8000FFFFh; char *
0x18003efbf  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003efc6  mov     edx, 16Ch; void *
0x18003efcb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003efd0  lea     r8, [rdi+3Ch]; struct _tagpropertykey *
0x18003efd4  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x18003efdb  mov     rcx, [rdi+8]; this
0x18003efdf  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x18003efe4  mov     rcx, [rsp+88h]; this
0x18003efec  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003eff3  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18003eff8  mov     r9d, eax; char *
0x18003effb  lea     rsi, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003f002  mov     r8, rsi; unsigned int
0x18003f005  mov     edx, 10Bh; void *
0x18003f00a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f00f  lea     r8, [rdi+40h]; struct _tagpropertykey *
0x18003f013  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x18003f01a  mov     rcx, [rdi+8]; this
0x18003f01e  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x18003f023  mov     rcx, [rsp+88h]; this
0x18003f02b  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003f032  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18003f037  mov     r9d, eax; char *
0x18003f03a  mov     r8, rsi; unsigned int
0x18003f03d  mov     edx, 112h; void *
0x18003f042  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f047  lea     r8, [rdi+44h]; struct _tagpropertykey *
0x18003f04b  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x18003f052  mov     rcx, [rdi+8]; this
0x18003f056  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18003f05b  mov     rcx, [rsp+88h]; this
0x18003f063  lea     rdx, aFailedToRetrie_15; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003f06a  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18003f06f  mov     r9d, eax; char *
0x18003f072  mov     r8, rsi; unsigned int
0x18003f075  mov     edx, 11Ch; void *
0x18003f07a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f07f  lea     r8, [rdi+48h]; struct _tagpropertykey *
0x18003f083  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x18003f08a  mov     rcx, [rdi+8]; this
0x18003f08e  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18003f093  mov     rcx, [rsp+88h]; this
0x18003f09b  lea     rdx, aFailedToRetrie_23; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003f0a2  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18003f0a7  mov     r9d, eax; char *
0x18003f0aa  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003f0b1  mov     edx, 123h; void *
0x18003f0b6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f0bb  mov     rcx, [rdi+0A0h]; this
0x18003f0c2  test    rcx, rcx
0x18003f0c5  jz      short loc_18003F11B
0x18003f0c7  call    ?GetClientSupportsMultiMonitor@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAA_NXZ; Rdp::Avenc::Ic3::CDsGfxChannel::GetClientSupportsMultiMonitor(void)
0x18003f0cc  test    al, al
0x18003f0ce  jz      short loc_18003F11B
0x18003f0d0  mov     eax, [rdi+48h]
0x18003f0d3  mov     [rsp+88h+var_68], eax; unsigned int
0x18003f0d7  mov     r9d, [rdi+44h]; unsigned int
0x18003f0db  mov     r8d, [rdi+40h]; int
0x18003f0df  mov     edx, [rdi+3Ch]; int
0x18003f0e2  mov     rcx, [rdi+0A0h]; this
0x18003f0e9  call    ?SendUpdateVirtualDesktopPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJHHII@Z; Rdp::Avenc::Ic3::CDsGfxChannel::SendUpdateVirtualDesktopPdu(int,int,uint,uint)
0x18003f0ee  mov     rcx, [rsp+88h]; this
0x18003f0f6  lea     rdx, aUnableToSendUp; "Unable to send update virtual desktop p"...
0x18003f0fd  mov     qword ptr [rsp+88h+var_68], rdx; int
0x18003f102  mov     r9d, eax; char *
0x18003f105  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003f10c  mov     edx, 178h; void *
0x18003f111  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f116  jmp     loc_18003F1A5
0x18003f11b  mov     eax, cs:dword_1800C1058
0x18003f121  cmp     eax, 4
0x18003f124  jbe     short loc_18003F1A5
0x18003f126  lea     rax, aSkippingVirtua; "Skipping virtual desktop update - not s"...
0x18003f12d  mov     [rsp+88h+arg_8], rax
0x18003f135  lea     rax, aRdpAvencIc3Cic_3; "Rdp::Avenc::Ic3::CIc3Processor::CommitM"...
0x18003f13c  mov     [rsp+88h+arg_10], rax
0x18003f144  mov     [rsp+88h+arg_0], 17Ch
0x18003f14f  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003f156  mov     [rsp+88h+arg_18], rax
0x18003f15e  lea     rax, [rsp+88h+arg_8]
0x18003f166  mov     [rsp+88h+MessageGuid], rax
0x18003f16b  lea     rax, [rsp+88h+arg_10]
0x18003f173  mov     [rsp+88h+var_58], rax
0x18003f178  lea     rax, [rsp+88h+arg_0]
0x18003f180  mov     [rsp+88h+var_60], rax; int
0x18003f185  lea     rax, [rsp+88h+arg_18]
0x18003f18d  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003f192  lea     rdx, word_1800AFBDA
0x18003f199  lea     rcx, dword_1800C1058
0x18003f1a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003f1a5  mov     rax, cs:WPP_GLOBAL_Control
0x18003f1ac  lea     rcx, WPP_GLOBAL_Control
0x18003f1b3  cmp     rax, rcx
0x18003f1b6  jz      short loc_18003F1C3
0x18003f1b8  test    [rax+1Ch], bl
0x18003f1bb  jz      short loc_18003F1C3
0x18003f1bd  cmp     byte ptr [rax+19h], 4
0x18003f1c1  jnb     short loc_18003F1C5
0x18003f1c3  xor     bl, bl
0x18003f1c5  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f1cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f1d3  setnz   dil
0x18003f1d7  test    bl, bl
0x18003f1d9  jnz     short loc_18003F1E0
0x18003f1db  test    dil, dil
0x18003f1de  jz      short loc_18003F20F
0x18003f1e0  call    cs:__imp_GetCurrentThreadId
0x18003f1e6  mov     dword ptr [rsp+88h+var_48], eax; char
0x18003f1ea  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18003f1ef  mov     word ptr [rsp+88h+var_58], 11h; __int16
0x18003f1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f1fd  mov     r9, [rcx+28h]; int
0x18003f201  mov     r8b, dil; int
0x18003f204  mov     dl, bl; int
0x18003f206  mov     rcx, [rcx+10h]; int
0x18003f20a  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003f20f  xor     eax, eax
0x18003f211  jmp     short loc_18003F21A
0x18003f213  mov     eax, [rsp+88h+arg_0]
0x18003f21a  add     rsp, 50h
0x18003f21e  pop     r15
0x18003f220  pop     r14
0x18003f222  pop     r13
0x18003f224  pop     r12
0x18003f226  pop     rdi
0x18003f227  pop     rsi
0x18003f228  pop     rbx
0x18003f229  retn
```
