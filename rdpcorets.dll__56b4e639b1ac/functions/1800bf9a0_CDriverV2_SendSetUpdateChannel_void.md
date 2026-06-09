# CDriverV2::SendSetUpdateChannel(void)

- ea: `0x1800bf9a0`
- end: `0x1800bffd2`
- name: `?SendSetUpdateChannel@CDriverV2@@MEAAJXZ`
- size: `1586`
- prototype: `__int64 __fastcall(CDriverV2 *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x18000e420`
- `0x180033da0`
- `0x180034970`
- `0x1800bf9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800bfad2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800bfad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfdef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfdef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bfde1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bfde1`

## string_xrefs

- `0x1800bfa3d`: `opSetUpdateChannel.UpdateChannelName is not initialized!`
- `0x1800bfa49`: `SendSetUpdateChannel`
- `0x1800bfb26`: `SendSetUpdateChannel`
- `0x1800bfbd5`: `SendSetUpdateChannel`
- `0x1800bfc84`: `SendSetUpdateChannel`
- `0x1800bfd33`: `SendSetUpdateChannel`
- `0x1800bfe23`: `SendSetUpdateChannel`
- `0x1800bfebc`: `SendSetUpdateChannel`
- `0x1800bff3c`: `SendSetUpdateChannel`
- `0x1800bfbc9`: `opSetUpdateChannel.UpdateBufferEmptyEventName is not initialized!`
- `0x1800bfb1a`: `opSetUpdateChannel.SchedulerEventName is not initialized!`
- `0x1800bfd27`: `opSetUpdateChannel.LockEventName is not initialized!`
- `0x1800bfc78`: `opSetUpdateChannel.AbortEventName is not initialized!`
- `0x1800bfe17`: `Failed to send RDPIDD_OPCODE_TYPE_SET_UPDATE_CHANNEL`

## pseudocode

```c
__int64 __fastcall CDriverV2::SendSetUpdateChannel(CDriverV2 *this)
{
  signed int v2; // ebx
  int v3; // r8d
  int v4; // r9d
  wchar_t *v5; // rax
  int v6; // ecx
  const unsigned __int16 *v7; // r8
  int v8; // r9d
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  signed int LastError; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v26; // [rsp+50h] [rbp-A88h] BYREF
  int v27; // [rsp+54h] [rbp-A84h] BYREF
  const char *v28; // [rsp+58h] [rbp-A80h] BYREF
  const char *v29; // [rsp+60h] [rbp-A78h] BYREF
  const char *v30; // [rsp+68h] [rbp-A70h] BYREF
  const char *v31; // [rsp+70h] [rbp-A68h] BYREF
  DWORD BytesReturned[2]; // [rsp+78h] [rbp-A60h] BYREF
  __int64 InBuffer; // [rsp+80h] [rbp-A58h] BYREF
  int v34; // [rsp+88h] [rbp-A50h]
  int v35; // [rsp+8Ch] [rbp-A4Ch]
  unsigned __int16 v36[260]; // [rsp+90h] [rbp-A48h] BYREF
  unsigned __int16 v37[260]; // [rsp+298h] [rbp-840h] BYREF
  unsigned __int16 v38[260]; // [rsp+4A0h] [rbp-638h] BYREF
  unsigned __int16 v39[260]; // [rsp+6A8h] [rbp-430h] BYREF
  unsigned __int16 v40[264]; // [rsp+8B0h] [rbp-228h] BYREF

  BytesReturned[0] = 0;
  memset_0(v36, 0, 0xA28u);
  v34 = 1033;
  InBuffer = 2616;
  v35 = 0x100000;
  v2 = StringCchCopyW(v36, 0x104u, (const unsigned __int16 *)this + 1664);
  if ( v2 >= 0 )
  {
    v5 = wcschr((const wchar_t *)this + 1404, 0x5Cu);
    if ( v5 && (v7 = v5 + 1, v5[1]) )
    {
      v2 = StringCchCopyW(v37, 0x104u, v7);
      if ( v2 >= 0 )
      {
        v2 = StringCchCopyW(v38, 0x104u, (const unsigned __int16 *)this + 884);
        if ( v2 >= 0 )
        {
          v2 = StringCchCopyW(v39, 0x104u, (const unsigned __int16 *)this + 624);
          if ( v2 >= 0 )
          {
            v2 = StringCchCopyW(v40, 0x104u, (const unsigned __int16 *)this + 1944);
            if ( v2 >= 0 )
            {
              if ( DeviceIoControl(*((HANDLE *)this + 11), 0x80000040, &InBuffer, 0xA38u, 0, 0, BytesReturned, 0) )
              {
                return 0;
              }
              else
              {
                LastError = GetLastError();
                v2 = LastError;
                if ( LastError > 0 )
                  v2 = (unsigned __int16)LastError | 0x80070000;
                BytesReturned[1] = v2;
                if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  v30 = "Failed to send RDPIDD_OPCODE_TYPE_SET_UPDATE_CHANNEL";
                  v29 = "SendSetUpdateChannel";
                  v27 = 446;
                  v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
                  v26 = v2;
                  v31 = "Error condition failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v22,
                    (unsigned int)&dword_1801A711C,
                    v23,
                    v24,
                    (__int64)&v31,
                    (__int64)&v26,
                    (__int64)&v28,
                    (__int64)&v27,
                    (__int64)&v29,
                    (__int64)&v30);
                }
              }
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v30 = "opSetUpdateChannel.LockEventName is not initialized!";
              v29 = "SendSetUpdateChannel";
              v27 = 430;
              v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
              v26 = v2;
              v31 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v18,
                (unsigned int)byte_1801A70CB,
                v19,
                v20,
                (__int64)&v31,
                (__int64)&v26,
                (__int64)&v28,
                (__int64)&v27,
                (__int64)&v29,
                (__int64)&v30);
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v30 = "opSetUpdateChannel.AbortEventName is not initialized!";
            v29 = "SendSetUpdateChannel";
            v27 = 423;
            v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
            v26 = v2;
            v31 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v15,
              (unsigned int)&word_1801A71BE,
              v16,
              v17,
              (__int64)&v31,
              (__int64)&v26,
              (__int64)&v28,
              (__int64)&v27,
              (__int64)&v29,
              (__int64)&v30);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v30 = "opSetUpdateChannel.UpdateBufferEmptyEventName is not initialized!";
          v29 = "SendSetUpdateChannel";
          v27 = 416;
          v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
          v26 = v2;
          v31 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_1801A716D,
            v13,
            v14,
            (__int64)&v31,
            (__int64)&v26,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v29,
            (__int64)&v30);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v30 = "opSetUpdateChannel.SchedulerEventName is not initialized!";
        v29 = "SendSetUpdateChannel";
        v27 = 409;
        v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
        v26 = v2;
        v31 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)qword_1801A7258,
          v10,
          v11,
          (__int64)&v31,
          (__int64)&v26,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v29,
          (__int64)&v30);
      }
    }
    else
    {
      v2 = -2147418113;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v30 = "SendSetUpdateChannel";
        v27 = 399;
        v29 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
        v26 = -2147418113;
        v28 = "Unexpected scheduler event name";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)&byte_1801A720F,
          (_DWORD)v7,
          v8,
          (__int64)&v28,
          (__int64)&v26,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v30);
      }
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v31 = "opSetUpdateChannel.UpdateChannelName is not initialized!";
    v28 = "SendSetUpdateChannel";
    v26 = 390;
    v29 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv2.cpp";
    v27 = v2;
    v30 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)byte_1801A72A9,
      v3,
      v4,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v26,
      (__int64)&v28,
      (__int64)&v31);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800bf9a0  mov     [rsp+arg_8], rbx
0x1800bf9a5  mov     [rsp+arg_10], rdi
0x1800bf9aa  push    r14
0x1800bf9ac  sub     rsp, 0AD0h
0x1800bf9b3  mov     rax, cs:__security_cookie
0x1800bf9ba  xor     rax, rsp
0x1800bf9bd  mov     [rsp+0AD8h+var_18], rax
0x1800bf9c5  mov     rdi, rcx
0x1800bf9c8  mov     [rsp+0AD8h+BytesReturned], 0
0x1800bf9d0  xor     edx, edx; Val
0x1800bf9d2  mov     r8d, 0A28h; Size
0x1800bf9d8  lea     rcx, [rsp+0AD8h+var_A48]; void *
0x1800bf9e0  call    memset_0
0x1800bf9e5  mov     [rsp+0AD8h+var_A50], 409h
0x1800bf9f0  mov     [rsp+0AD8h+InBuffer], 0A38h
0x1800bf9fc  mov     [rsp+0AD8h+var_A4C], 100000h
0x1800bfa07  lea     r8, [rdi+0D00h]; unsigned __int16 *
0x1800bfa0e  mov     r14d, 104h
0x1800bfa14  mov     edx, r14d; unsigned __int64
0x1800bfa17  lea     rcx, [rsp+0AD8h+var_A48]; unsigned __int16 *
0x1800bfa1f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfa24  mov     ebx, eax
0x1800bfa26  test    eax, eax
0x1800bfa28  jns     loc_1800BFAC6
0x1800bfa2e  mov     ecx, cs:dword_1801B76C8
0x1800bfa34  cmp     ecx, 2
0x1800bfa37  jbe     loc_1800BFFAA
0x1800bfa3d  lea     rax, aOpsetupdatecha_0; "opSetUpdateChannel.UpdateChannelName is"...
0x1800bfa44  mov     [rsp+0AD8h+var_A68], rax
0x1800bfa49  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfa50  mov     [rsp+0AD8h+var_A80], rax
0x1800bfa55  mov     [rsp+0AD8h+var_A88], 186h
0x1800bfa5d  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfa64  mov     [rsp+0AD8h+var_A78], rax
0x1800bfa69  mov     [rsp+0AD8h+var_A84], ebx
0x1800bfa6d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bfa74  mov     [rsp+0AD8h+var_A70], rax
0x1800bfa79  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfa7e  mov     [rsp+0AD8h+var_A90], rax
0x1800bfa83  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfa88  mov     [rsp+0AD8h+var_A98], rax
0x1800bfa8d  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfa92  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfa97  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfa9c  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfaa1  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfaa6  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfaab  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfab0  lea     rdx, byte_1801A72A9
0x1800bfab7  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800bfabc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800bfac1  jmp     loc_1800BFFAA
0x1800bfac6  mov     edx, 5Ch ; '\'; Ch
0x1800bfacb  lea     rcx, [rdi+0AF8h]; Str
0x1800bfad2  call    cs:__imp_wcschr
0x1800bfad8  test    rax, rax
0x1800bfadb  jz      loc_1800BFF2C
0x1800bfae1  lea     r8, [rax+2]; unsigned __int16 *
0x1800bfae5  xor     eax, eax
0x1800bfae7  cmp     ax, [r8]
0x1800bfaeb  jz      loc_1800BFF2C
0x1800bfaf1  mov     rdx, r14; unsigned __int64
0x1800bfaf4  lea     rcx, [rsp+0AD8h+var_840]; unsigned __int16 *
0x1800bfafc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfb01  mov     ebx, eax
0x1800bfb03  test    eax, eax
0x1800bfb05  jns     loc_1800BFB99
0x1800bfb0b  mov     eax, cs:dword_1801B76C8
0x1800bfb11  cmp     eax, 2
0x1800bfb14  jbe     loc_1800BFFAA
0x1800bfb1a  lea     rax, aOpsetupdatecha_1; "opSetUpdateChannel.SchedulerEventName i"...
0x1800bfb21  mov     [rsp+0AD8h+var_A70], rax
0x1800bfb26  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfb2d  mov     [rsp+0AD8h+var_A78], rax
0x1800bfb32  mov     [rsp+0AD8h+var_A84], 199h
0x1800bfb3a  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfb41  mov     [rsp+0AD8h+var_A80], rax
0x1800bfb46  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfb4a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bfb51  mov     [rsp+0AD8h+var_A68], rax
0x1800bfb56  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfb5b  mov     [rsp+0AD8h+var_A90], rax
0x1800bfb60  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfb65  mov     [rsp+0AD8h+var_A98], rax
0x1800bfb6a  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfb6f  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfb74  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfb79  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfb7e  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfb83  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfb88  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfb8d  lea     rdx, qword_1801A7258
0x1800bfb94  jmp     loc_1800BFAB7
0x1800bfb99  lea     r8, [rdi+6E8h]; unsigned __int16 *
0x1800bfba0  mov     rdx, r14; unsigned __int64
0x1800bfba3  lea     rcx, [rsp+0AD8h+var_638]; unsigned __int16 *
0x1800bfbab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfbb0  mov     ebx, eax
0x1800bfbb2  test    eax, eax
0x1800bfbb4  jns     loc_1800BFC48
0x1800bfbba  mov     eax, cs:dword_1801B76C8
0x1800bfbc0  cmp     eax, 2
0x1800bfbc3  jbe     loc_1800BFFAA
0x1800bfbc9  lea     rax, aOpsetupdatecha_2; "opSetUpdateChannel.UpdateBufferEmptyEve"...
0x1800bfbd0  mov     [rsp+0AD8h+var_A70], rax
0x1800bfbd5  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfbdc  mov     [rsp+0AD8h+var_A78], rax
0x1800bfbe1  mov     [rsp+0AD8h+var_A84], 1A0h
0x1800bfbe9  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfbf0  mov     [rsp+0AD8h+var_A80], rax
0x1800bfbf5  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfbf9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bfc00  mov     [rsp+0AD8h+var_A68], rax
0x1800bfc05  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfc0a  mov     [rsp+0AD8h+var_A90], rax
0x1800bfc0f  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfc14  mov     [rsp+0AD8h+var_A98], rax
0x1800bfc19  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfc1e  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfc23  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfc28  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfc2d  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfc32  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfc37  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfc3c  lea     rdx, byte_1801A716D
0x1800bfc43  jmp     loc_1800BFAB7
0x1800bfc48  lea     r8, [rdi+4E0h]; unsigned __int16 *
0x1800bfc4f  mov     rdx, r14; unsigned __int64
0x1800bfc52  lea     rcx, [rsp+0AD8h+var_430]; unsigned __int16 *
0x1800bfc5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfc5f  mov     ebx, eax
0x1800bfc61  test    eax, eax
0x1800bfc63  jns     loc_1800BFCF7
0x1800bfc69  mov     eax, cs:dword_1801B76C8
0x1800bfc6f  cmp     eax, 2
0x1800bfc72  jbe     loc_1800BFFAA
0x1800bfc78  lea     rax, aOpsetupdatecha; "opSetUpdateChannel.AbortEventName is no"...
0x1800bfc7f  mov     [rsp+0AD8h+var_A70], rax
0x1800bfc84  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfc8b  mov     [rsp+0AD8h+var_A78], rax
0x1800bfc90  mov     [rsp+0AD8h+var_A84], 1A7h
0x1800bfc98  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfc9f  mov     [rsp+0AD8h+var_A80], rax
0x1800bfca4  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfca8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bfcaf  mov     [rsp+0AD8h+var_A68], rax
0x1800bfcb4  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfcb9  mov     [rsp+0AD8h+var_A90], rax
0x1800bfcbe  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfcc3  mov     [rsp+0AD8h+var_A98], rax
0x1800bfcc8  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfccd  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfcd2  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfcd7  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfcdc  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfce1  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfce6  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfceb  lea     rdx, word_1801A71BE
0x1800bfcf2  jmp     loc_1800BFAB7
0x1800bfcf7  lea     r8, [rdi+0F30h]; unsigned __int16 *
0x1800bfcfe  mov     rdx, r14; unsigned __int64
0x1800bfd01  lea     rcx, [rsp+0AD8h+var_228]; unsigned __int16 *
0x1800bfd09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bfd0e  mov     ebx, eax
0x1800bfd10  test    eax, eax
0x1800bfd12  jns     loc_1800BFDA6
0x1800bfd18  mov     eax, cs:dword_1801B76C8
0x1800bfd1e  cmp     eax, 2
0x1800bfd21  jbe     loc_1800BFFAA
0x1800bfd27  lea     rax, aOpsetupdatecha_3; "opSetUpdateChannel.LockEventName is not"...
0x1800bfd2e  mov     [rsp+0AD8h+var_A70], rax
0x1800bfd33  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfd3a  mov     [rsp+0AD8h+var_A78], rax
0x1800bfd3f  mov     [rsp+0AD8h+var_A84], 1AEh
0x1800bfd47  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfd4e  mov     [rsp+0AD8h+var_A80], rax
0x1800bfd53  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfd57  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800bfd5e  mov     [rsp+0AD8h+var_A68], rax
0x1800bfd63  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfd68  mov     [rsp+0AD8h+var_A90], rax
0x1800bfd6d  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfd72  mov     [rsp+0AD8h+var_A98], rax
0x1800bfd77  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfd7c  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfd81  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfd86  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfd8b  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfd90  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfd95  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfd9a  lea     rdx, byte_1801A70CB
0x1800bfda1  jmp     loc_1800BFAB7
0x1800bfda6  mov     [rsp+0AD8h+lpOverlapped], 0; lpOverlapped
0x1800bfdaf  lea     rax, [rsp+0AD8h+BytesReturned]
0x1800bfdb4  mov     [rsp+0AD8h+lpBytesReturned], rax; lpBytesReturned
0x1800bfdb9  mov     [rsp+0AD8h+nOutBufferSize], 0; nOutBufferSize
0x1800bfdc1  mov     [rsp+0AD8h+lpOutBuffer], 0; lpOutBuffer
0x1800bfdca  mov     r9d, 0A38h; nInBufferSize
0x1800bfdd0  lea     r8, [rsp+0AD8h+InBuffer]; lpInBuffer
0x1800bfdd8  mov     edx, 80000040h; dwIoControlCode
0x1800bfddd  mov     rcx, [rdi+58h]; hDevice
0x1800bfde1  call    cs:__imp_DeviceIoControl
0x1800bfde7  test    eax, eax
0x1800bfde9  jnz     loc_1800BFEA0
0x1800bfdef  call    cs:__imp_GetLastError
0x1800bfdf5  mov     ebx, eax
0x1800bfdf7  test    eax, eax
0x1800bfdf9  jle     short loc_1800BFE04
0x1800bfdfb  movzx   ebx, ax
0x1800bfdfe  or      ebx, 80070000h
0x1800bfe04  mov     [rsp+0AD8h+var_A5C], ebx
0x1800bfe08  mov     eax, cs:dword_1801B76C8
0x1800bfe0e  cmp     eax, 2
0x1800bfe11  jbe     loc_1800BFE9B
0x1800bfe17  lea     rax, aFailedToSendRd_5; "Failed to send RDPIDD_OPCODE_TYPE_SET_U"...
0x1800bfe1e  mov     [rsp+0AD8h+var_A70], rax
0x1800bfe23  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfe2a  mov     [rsp+0AD8h+var_A78], rax
0x1800bfe2f  mov     [rsp+0AD8h+var_A84], 1BEh
0x1800bfe37  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfe3e  mov     [rsp+0AD8h+var_A80], rax
0x1800bfe43  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfe47  lea     rax, aErrorCondition; "Error condition failed"
0x1800bfe4e  mov     [rsp+0AD8h+var_A68], rax
0x1800bfe53  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfe58  mov     [rsp+0AD8h+var_A90], rax
0x1800bfe5d  lea     rax, [rsp+0AD8h+var_A78]
0x1800bfe62  mov     [rsp+0AD8h+var_A98], rax
0x1800bfe67  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfe6c  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bfe71  lea     rax, [rsp+0AD8h+var_A80]
0x1800bfe76  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bfe7b  lea     rax, [rsp+0AD8h+var_A88]
0x1800bfe80  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bfe85  lea     rax, [rsp+0AD8h+var_A68]
0x1800bfe8a  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800bfe8f  lea     rdx, dword_1801A711C
0x1800bfe96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800bfe9b  jmp     loc_1800BFFAA
0x1800bfea0  xor     ebx, ebx
0x1800bfea2  jmp     loc_1800BFFAA
0x1800bfea7  mov     ebx, eax
0x1800bfea9  bts     ebx, 1Ch
0x1800bfead  mov     [rsp+0AD8h+var_A5C], ebx
0x1800bfeb1  mov     eax, cs:dword_1801B76C8
0x1800bfeb7  cmp     eax, 2
0x1800bfeba  jbe     short loc_1800BFF2A
0x1800bfebc  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bfec3  mov     [rsp+0AD8h+var_A70], rax
0x1800bfec8  mov     [rsp+0AD8h+var_A84], 1C3h
0x1800bfed0  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bfed7  mov     [rsp+0AD8h+var_A78], rax
0x1800bfedc  mov     [rsp+0AD8h+var_A88], ebx
0x1800bfee0  lea     rax, aRaisedExceptio; "Raised exception while I/O with RDPIDD."...
0x1800bfee7  mov     [rsp+0AD8h+var_A80], rax
0x1800bfeec  lea     rax, [rsp+0AD8h+var_A70]
0x1800bfef1  mov     [rsp+0AD8h+var_A98], rax
0x1800bfef6  lea     rax, [rsp+0AD8h+var_A84]
0x1800bfefb  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bff00  lea     rax, [rsp+0AD8h+var_A78]
0x1800bff05  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bff0a  lea     rax, [rsp+0AD8h+var_A88]
0x1800bff0f  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bff14  lea     rax, [rsp+0AD8h+var_A80]
0x1800bff19  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800bff1e  lea     rdx, word_1801A7082
0x1800bff25  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800bff2a  jmp     short loc_1800BFFAA
0x1800bff2c  mov     ebx, 8000FFFFh
0x1800bff31  mov     eax, cs:dword_1801B76C8
0x1800bff37  cmp     eax, 2
0x1800bff3a  jbe     short loc_1800BFFAA
0x1800bff3c  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800bff43  mov     [rsp+0AD8h+var_A70], rax
0x1800bff48  mov     [rsp+0AD8h+var_A84], 18Fh
0x1800bff50  lea     rax, aClientcoreTerm_5; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800bff57  mov     [rsp+0AD8h+var_A78], rax
0x1800bff5c  mov     [rsp+0AD8h+var_A88], ebx
0x1800bff60  lea     rax, aUnexpectedSche; "Unexpected scheduler event name"
0x1800bff67  mov     [rsp+0AD8h+var_A80], rax
0x1800bff6c  lea     rax, [rsp+0AD8h+var_A70]
0x1800bff71  mov     [rsp+0AD8h+var_A98], rax
0x1800bff76  lea     rax, [rsp+0AD8h+var_A84]
0x1800bff7b  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800bff80  lea     rax, [rsp+0AD8h+var_A78]
0x1800bff85  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800bff8a  lea     rax, [rsp+0AD8h+var_A88]
0x1800bff8f  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800bff94  lea     rax, [rsp+0AD8h+var_A80]
0x1800bff99  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800bff9e  lea     rdx, byte_1801A720F
0x1800bffa5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800bffaa  mov     eax, ebx
0x1800bffac  mov     rcx, [rsp+0AD8h+var_18]
0x1800bffb4  xor     rcx, rsp; StackCookie
0x1800bffb7  call    __security_check_cookie
0x1800bffbc  lea     r11, [rsp+0AD8h+var_8]
0x1800bffc4  mov     rbx, [r11+18h]
0x1800bffc8  mov     rdi, [r11+20h]
0x1800bffcc  mov     rsp, r11
  ... truncated ...
```
