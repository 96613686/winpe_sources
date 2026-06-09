# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)

- ea: `0x180019c10`
- end: `0x180019d64`
- name: `?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z`
- size: `340`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180011d10`
- `0x180011d40`
- `0x1800123a0`
- `0x180012430`
- `0x180012950`
- `0x180013264`
- `0x180013878`
- `0x18001a700`
- `0x18001ab50`
- `0x180020850`
- `0x180020930`
- `0x180020a08`
- `0x180020b44`
- `0x1800219c0`
- `0x1800219e0`

## callees

- `0x180001008`
- `0x1800080cc`
- `0x180019998`
- `0x1800199cc`
- `0x180019c10`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x180019c3d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x180019c3d`

## string_xrefs

- `0x180019c6d`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019cee`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019d13`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019d43`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019c74`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::lock`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(
        __int64 a1,
        DWORD a2)
{
  DWORD v3; // eax
  int v4; // r9d
  __int64 result; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  char *v8; // [rsp+20h] [rbp-48h]
  const char *v9; // [rsp+28h] [rbp-40h]
  const char *v10; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Handles[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v13; // [rsp+70h] [rbp+8h] BYREF
  const char *v14; // [rsp+80h] [rbp+18h] BYREF
  const char *v15; // [rsp+88h] [rbp+20h] BYREF

  Handles[0] = *(HANDLE *)(a1 + 136);
  Handles[1] = *(HANDLE *)(a1 + 120);
  v3 = WaitForMultipleObjects(2u, Handles, 0, a2);
  if ( v3 )
  {
    if ( v3 != 1 )
    {
      if ( v3 != 258 )
      {
        LODWORD(v8) = v3;
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0xF4,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
          "Wait failed 0x%x",
          v8);
      }
      v7 = wil::verify_hresult<long>(2147943860LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        (const char *)v7,
        (int)"UserModeLockEvent event timed out!",
        v9);
    }
    v6 = wil::verify_hresult<long>(2147500036LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v6,
      (int)"Abort event was signaled!",
      v9);
  }
  result = (unsigned int)dword_1800C1058;
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v13 = 231;
    v14 = "UserModeLockEvent locked";
    v10 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
    v15 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::lock";
    result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
               (unsigned int)&dword_1800C1058,
               (unsigned int)qword_1800AC9F8,
               (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
               v4,
               (__int64)&v10,
               (__int64)&v13,
               (__int64)&v15,
               (__int64)&v14);
  }
  *(_BYTE *)(a1 + 144) = 1;
  return result;
}

```

## disassembly

```asm
0x180019c10  push    rbx
0x180019c12  sub     rsp, 60h
0x180019c16  mov     rax, [rcx+88h]
0x180019c1d  xor     r8d, r8d; bWaitAll
0x180019c20  mov     [rsp+68h+Handles], rax
0x180019c25  mov     rbx, rcx
0x180019c28  mov     rax, [rcx+78h]
0x180019c2c  mov     r9d, edx; dwMilliseconds
0x180019c2f  lea     rdx, [rsp+68h+Handles]; lpHandles
0x180019c34  mov     [rsp+68h+var_18], rax
0x180019c39  lea     ecx, [r8+2]; nCount
0x180019c3d  call    cs:__imp_WaitForMultipleObjects
0x180019c43  test    eax, eax
0x180019c45  jnz     loc_180019CD6
0x180019c4b  mov     eax, cs:dword_1800C1058
0x180019c51  cmp     eax, 5
0x180019c54  jbe     short loc_180019CC9
0x180019c56  lea     rax, aUsermodelockev_0; "UserModeLockEvent locked"
0x180019c5d  mov     [rsp+68h+arg_0], 0E7h
0x180019c65  mov     [rsp+68h+arg_10], rax
0x180019c6d  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019c74  lea     rax, aRdpAvencUmrdpC_6; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180019c7b  mov     [rsp+68h+var_28], r8
0x180019c80  mov     [rsp+68h+arg_18], rax
0x180019c88  lea     rdx, qword_1800AC9F8
0x180019c8f  lea     rax, [rsp+68h+arg_10]
0x180019c97  mov     [rsp+68h+var_30], rax
0x180019c9c  lea     rcx, dword_1800C1058
0x180019ca3  lea     rax, [rsp+68h+arg_18]
0x180019cab  mov     [rsp+68h+var_38], rax
0x180019cb0  lea     rax, [rsp+68h+arg_0]
0x180019cb5  mov     [rsp+68h+var_40], rax
0x180019cba  lea     rax, [rsp+68h+var_28]
0x180019cbf  mov     [rsp+68h+var_48], rax
0x180019cc4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180019cc9  mov     byte ptr [rbx+90h], 1
0x180019cd0  add     rsp, 60h
0x180019cd4  pop     rbx
0x180019cd5  retn
0x180019cd6  cmp     eax, 1
0x180019cd9  jz      short loc_180019D04
0x180019cdb  cmp     eax, 102h
0x180019ce0  jz      short loc_180019D34
0x180019ce2  mov     rcx, [rsp+68h]; this
0x180019ce7  lea     r9, aWaitFailed0xX; "Wait failed 0x%x"
0x180019cee  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019cf5  mov     dword ptr [rsp+68h+var_48], eax; char *
0x180019cf9  mov     edx, 0F4h; void *
0x180019cfe  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180019d04  mov     ecx, 80004004h
0x180019d09  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180019d0e  mov     rcx, [rsp+68h]; this
0x180019d13  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019d1a  mov     r9d, eax; char *
0x180019d1d  mov     edx, 0ECh; void *
0x180019d22  lea     rax, aAbortEventWasS; "Abort event was signaled!"
0x180019d29  mov     [rsp+68h+var_48], rax; int
0x180019d2e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019d34  mov     ecx, 800705B4h
0x180019d39  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180019d3e  mov     rcx, [rsp+68h]; this
0x180019d43  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019d4a  mov     r9d, eax; char *
0x180019d4d  mov     edx, 0F0h; void *
0x180019d52  lea     rax, aUsermodelockev; "UserModeLockEvent event timed out!"
0x180019d59  mov     [rsp+68h+var_48], rax; int
0x180019d5e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
