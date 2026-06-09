# DWMIndirect::UpdateSurface(HRGN__ *,_DWMIndirectMoveMetaData *,uint)

- ea: `0x180006950`
- end: `0x180006a3a`
- name: `?UpdateSurface@DWMIndirect@@UEAAJPEAUHRGN__@@PEAU_DWMIndirectMoveMetaData@@I@Z`
- size: `234`
- prototype: `int(DWMIndirect *__hidden this, HRGN, struct _DWMIndirectMoveMetaData *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001474`
- `0x180003d7c`
- `0x180006240`
- `0x180006950`
- `0x18002b960`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006a12`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006a12`

## string_xrefs

- `0x1800069ad`: `DWMIndirect::UpdateSurface for device %s (hrgnDirty=%p, metadataCount=%d `

## pseudocode

```c
__int64 __fastcall DWMIndirect::UpdateSurface(
        DWMIndirect *this,
        HRGN a2,
        struct _DWMIndirectMoveMetaData *a3,
        unsigned int a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+40h] [rbp-58h] BYREF
  HRGN v14; // [rsp+48h] [rbp-50h] BYREF
  char *v15; // [rsp+50h] [rbp-48h] BYREF
  const char *v16; // [rsp+58h] [rbp-40h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-38h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &stru_1800440EC);
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v13 = a4;
    v15 = (char *)this + 788;
    v14 = a2;
    v16 = "DWMIndirect::UpdateSurface for device %s (hrgnDirty=%p, metadataCount=%d ";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v8,
      (__int64)&byte_180037427,
      v9,
      v10,
      (const unsigned __int16 **)&v16,
      &v15,
      (__int64)&v14,
      (__int64)&v13);
  }
  v11 = ((int)DWMIndirect::UpdateMonitorSurface((DWMIndirect *)((char *)this - 48), a2, a3, a4) >> 31) & 0x80004005;
  EventActivityIdControl(2u, &ActivityId);
  return v11;
}

```

## disassembly

```asm
0x180006950  mov     [rsp+arg_18], rbx
0x180006955  push    rbp
0x180006956  push    rsi
0x180006957  push    rdi
0x180006958  sub     rsp, 80h
0x18000695f  mov     rax, cs:__security_cookie
0x180006966  xor     rax, rsp
0x180006969  mov     [rsp+98h+var_28], rax
0x18000696e  mov     rsi, rdx
0x180006971  mov     rdi, rcx
0x180006974  lea     rdx, stru_1800440EC; struct _GUID *
0x18000697b  mov     ebx, r9d
0x18000697e  lea     rcx, [rsp+98h+ActivityId]; ActivityId
0x180006983  mov     rbp, r8
0x180006986  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000698b  mov     eax, cs:dword_180044008
0x180006991  cmp     eax, 5
0x180006994  jbe     short loc_1800069EB
0x180006996  lea     rax, [rdi+314h]
0x18000699d  mov     [rsp+98h+var_58], ebx
0x1800069a1  mov     [rsp+98h+var_48], rax
0x1800069a6  lea     rdx, byte_180037427
0x1800069ad  lea     rax, aDwmindirectUpd_1; "DWMIndirect::UpdateSurface for device %"...
0x1800069b4  mov     [rsp+98h+var_50], rsi
0x1800069b9  mov     [rsp+98h+var_40], rax
0x1800069be  lea     rax, [rsp+98h+var_58]
0x1800069c3  mov     [rsp+98h+var_60], rax
0x1800069c8  lea     rax, [rsp+98h+var_50]
0x1800069cd  mov     [rsp+98h+var_68], rax
0x1800069d2  lea     rax, [rsp+98h+var_48]
0x1800069d7  mov     [rsp+98h+var_70], rax
0x1800069dc  lea     rax, [rsp+98h+var_40]
0x1800069e1  mov     [rsp+98h+var_78], rax
0x1800069e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800069eb  lea     rcx, [rdi-30h]; this
0x1800069ef  mov     r9d, ebx; unsigned int
0x1800069f2  mov     r8, rbp; struct _DWMIndirectMoveMetaData *
0x1800069f5  mov     rdx, rsi; HRGN
0x1800069f8  call    ?UpdateMonitorSurface@DWMIndirect@@IEAAJPEAUHRGN__@@PEAU_DWMIndirectMoveMetaData@@I@Z; DWMIndirect::UpdateMonitorSurface(HRGN__ *,_DWMIndirectMoveMetaData *,uint)
0x1800069fd  mov     ebx, eax
0x1800069ff  lea     rdx, [rsp+98h+ActivityId]; ActivityId
0x180006a04  sar     ebx, 1Fh
0x180006a07  mov     ecx, 2; ControlCode
0x180006a0c  and     ebx, 80004005h
0x180006a12  call    cs:__imp_EventActivityIdControl
0x180006a18  mov     eax, ebx
0x180006a1a  mov     rcx, [rsp+98h+var_28]
0x180006a1f  xor     rcx, rsp; StackCookie
0x180006a22  call    __security_check_cookie
0x180006a27  mov     rbx, [rsp+98h+arg_18]
0x180006a2f  add     rsp, 80h
0x180006a36  pop     rdi
0x180006a37  pop     rsi
0x180006a38  pop     rbp
0x180006a39  retn
```
