# CDriverV3::SendSetUpdateChannel(void)

- ea: `0x1800c4970`
- end: `0x1800c4fa2`
- name: `?SendSetUpdateChannel@CDriverV3@@MEAAJXZ`
- size: `1586`
- prototype: `__int64 __fastcall(CDriverV3 *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x18000e420`
- `0x180033da0`
- `0x180034970`
- `0x1800c4970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800c4aa2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800c4aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4dbf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c4db1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c4db1`

## string_xrefs

- `0x1800c4a0d`: `opSetUpdateChannel.UpdateChannelName is not initialized!`
- `0x1800c4a19`: `SendSetUpdateChannel`
- `0x1800c4af6`: `SendSetUpdateChannel`
- `0x1800c4ba5`: `SendSetUpdateChannel`
- `0x1800c4c54`: `SendSetUpdateChannel`
- `0x1800c4d03`: `SendSetUpdateChannel`
- `0x1800c4df3`: `SendSetUpdateChannel`
- `0x1800c4e8c`: `SendSetUpdateChannel`
- `0x1800c4f0c`: `SendSetUpdateChannel`
- `0x1800c4b99`: `opSetUpdateChannel.UpdateBufferEmptyEventName is not initialized!`
- `0x1800c4aea`: `opSetUpdateChannel.SchedulerEventName is not initialized!`
- `0x1800c4cf7`: `opSetUpdateChannel.LockEventName is not initialized!`
- `0x1800c4c48`: `opSetUpdateChannel.AbortEventName is not initialized!`
- `0x1800c4de7`: `Failed to send RDPAVENC_OPCODE_TYPE_SET_UPDATE_CHANNEL`

## pseudocode

```c
__int64 __fastcall CDriverV3::SendSetUpdateChannel(CDriverV3 *this)
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
  v34 = 1;
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
              if ( DeviceIoControl(*((HANDLE *)this + 11), 0x80000048, &InBuffer, 0xA38u, 0, 0, BytesReturned, 0) )
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
                  v30 = "Failed to send RDPAVENC_OPCODE_TYPE_SET_UPDATE_CHANNEL";
                  v29 = "SendSetUpdateChannel";
                  v27 = 257;
                  v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
                  v26 = v2;
                  v31 = "Error condition failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v22,
                    (unsigned int)byte_1801A8E79,
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
              v27 = 241;
              v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
              v26 = v2;
              v31 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v18,
                (unsigned int)&dword_1801A8F64,
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
            v27 = 234;
            v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
            v26 = v2;
            v31 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v15,
              (unsigned int)byte_1801A8F13,
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
          v27 = 227;
          v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
          v26 = v2;
          v31 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)&word_1801A9006,
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
        v27 = 220;
        v28 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
        v26 = v2;
        v31 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)byte_1801A8FB5,
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
        v27 = 210;
        v29 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
        v26 = -2147418113;
        v28 = "Unexpected scheduler event name";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)qword_1801A90A8,
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
    v26 = 201;
    v29 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\driverv3.cpp";
    v27 = v2;
    v30 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&byte_1801A9057,
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
0x1800c4970  mov     [rsp+arg_8], rbx
0x1800c4975  mov     [rsp+arg_10], rdi
0x1800c497a  push    r14
0x1800c497c  sub     rsp, 0AD0h
0x1800c4983  mov     rax, cs:__security_cookie
0x1800c498a  xor     rax, rsp
0x1800c498d  mov     [rsp+0AD8h+var_18], rax
0x1800c4995  mov     rdi, rcx
0x1800c4998  mov     [rsp+0AD8h+BytesReturned], 0
0x1800c49a0  xor     edx, edx; Val
0x1800c49a2  mov     r8d, 0A28h; Size
0x1800c49a8  lea     rcx, [rsp+0AD8h+var_A48]; void *
0x1800c49b0  call    memset_0
0x1800c49b5  mov     [rsp+0AD8h+var_A50], 1
0x1800c49c0  mov     [rsp+0AD8h+InBuffer], 0A38h
0x1800c49cc  mov     [rsp+0AD8h+var_A4C], 100000h
0x1800c49d7  lea     r8, [rdi+0D00h]; unsigned __int16 *
0x1800c49de  mov     r14d, 104h
0x1800c49e4  mov     edx, r14d; unsigned __int64
0x1800c49e7  lea     rcx, [rsp+0AD8h+var_A48]; unsigned __int16 *
0x1800c49ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c49f4  mov     ebx, eax
0x1800c49f6  test    eax, eax
0x1800c49f8  jns     loc_1800C4A96
0x1800c49fe  mov     ecx, cs:dword_1801B76C8
0x1800c4a04  cmp     ecx, 2
0x1800c4a07  jbe     loc_1800C4F7A
0x1800c4a0d  lea     rax, aOpsetupdatecha_0; "opSetUpdateChannel.UpdateChannelName is"...
0x1800c4a14  mov     [rsp+0AD8h+var_A68], rax
0x1800c4a19  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4a20  mov     [rsp+0AD8h+var_A80], rax
0x1800c4a25  mov     [rsp+0AD8h+var_A88], 0C9h
0x1800c4a2d  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4a34  mov     [rsp+0AD8h+var_A78], rax
0x1800c4a39  mov     [rsp+0AD8h+var_A84], ebx
0x1800c4a3d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c4a44  mov     [rsp+0AD8h+var_A70], rax
0x1800c4a49  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4a4e  mov     [rsp+0AD8h+var_A90], rax
0x1800c4a53  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4a58  mov     [rsp+0AD8h+var_A98], rax
0x1800c4a5d  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4a62  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4a67  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4a6c  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4a71  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4a76  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4a7b  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4a80  lea     rdx, byte_1801A9057
0x1800c4a87  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800c4a8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c4a91  jmp     loc_1800C4F7A
0x1800c4a96  mov     edx, 5Ch ; '\'; Ch
0x1800c4a9b  lea     rcx, [rdi+0AF8h]; Str
0x1800c4aa2  call    cs:__imp_wcschr
0x1800c4aa8  test    rax, rax
0x1800c4aab  jz      loc_1800C4EFC
0x1800c4ab1  lea     r8, [rax+2]; unsigned __int16 *
0x1800c4ab5  xor     eax, eax
0x1800c4ab7  cmp     ax, [r8]
0x1800c4abb  jz      loc_1800C4EFC
0x1800c4ac1  mov     rdx, r14; unsigned __int64
0x1800c4ac4  lea     rcx, [rsp+0AD8h+var_840]; unsigned __int16 *
0x1800c4acc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c4ad1  mov     ebx, eax
0x1800c4ad3  test    eax, eax
0x1800c4ad5  jns     loc_1800C4B69
0x1800c4adb  mov     eax, cs:dword_1801B76C8
0x1800c4ae1  cmp     eax, 2
0x1800c4ae4  jbe     loc_1800C4F7A
0x1800c4aea  lea     rax, aOpsetupdatecha_1; "opSetUpdateChannel.SchedulerEventName i"...
0x1800c4af1  mov     [rsp+0AD8h+var_A70], rax
0x1800c4af6  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4afd  mov     [rsp+0AD8h+var_A78], rax
0x1800c4b02  mov     [rsp+0AD8h+var_A84], 0DCh
0x1800c4b0a  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4b11  mov     [rsp+0AD8h+var_A80], rax
0x1800c4b16  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4b1a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c4b21  mov     [rsp+0AD8h+var_A68], rax
0x1800c4b26  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4b2b  mov     [rsp+0AD8h+var_A90], rax
0x1800c4b30  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4b35  mov     [rsp+0AD8h+var_A98], rax
0x1800c4b3a  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4b3f  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4b44  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4b49  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4b4e  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4b53  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4b58  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4b5d  lea     rdx, byte_1801A8FB5
0x1800c4b64  jmp     loc_1800C4A87
0x1800c4b69  lea     r8, [rdi+6E8h]; unsigned __int16 *
0x1800c4b70  mov     rdx, r14; unsigned __int64
0x1800c4b73  lea     rcx, [rsp+0AD8h+var_638]; unsigned __int16 *
0x1800c4b7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c4b80  mov     ebx, eax
0x1800c4b82  test    eax, eax
0x1800c4b84  jns     loc_1800C4C18
0x1800c4b8a  mov     eax, cs:dword_1801B76C8
0x1800c4b90  cmp     eax, 2
0x1800c4b93  jbe     loc_1800C4F7A
0x1800c4b99  lea     rax, aOpsetupdatecha_2; "opSetUpdateChannel.UpdateBufferEmptyEve"...
0x1800c4ba0  mov     [rsp+0AD8h+var_A70], rax
0x1800c4ba5  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4bac  mov     [rsp+0AD8h+var_A78], rax
0x1800c4bb1  mov     [rsp+0AD8h+var_A84], 0E3h
0x1800c4bb9  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4bc0  mov     [rsp+0AD8h+var_A80], rax
0x1800c4bc5  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4bc9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c4bd0  mov     [rsp+0AD8h+var_A68], rax
0x1800c4bd5  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4bda  mov     [rsp+0AD8h+var_A90], rax
0x1800c4bdf  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4be4  mov     [rsp+0AD8h+var_A98], rax
0x1800c4be9  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4bee  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4bf3  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4bf8  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4bfd  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4c02  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4c07  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4c0c  lea     rdx, word_1801A9006
0x1800c4c13  jmp     loc_1800C4A87
0x1800c4c18  lea     r8, [rdi+4E0h]; unsigned __int16 *
0x1800c4c1f  mov     rdx, r14; unsigned __int64
0x1800c4c22  lea     rcx, [rsp+0AD8h+var_430]; unsigned __int16 *
0x1800c4c2a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c4c2f  mov     ebx, eax
0x1800c4c31  test    eax, eax
0x1800c4c33  jns     loc_1800C4CC7
0x1800c4c39  mov     eax, cs:dword_1801B76C8
0x1800c4c3f  cmp     eax, 2
0x1800c4c42  jbe     loc_1800C4F7A
0x1800c4c48  lea     rax, aOpsetupdatecha; "opSetUpdateChannel.AbortEventName is no"...
0x1800c4c4f  mov     [rsp+0AD8h+var_A70], rax
0x1800c4c54  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4c5b  mov     [rsp+0AD8h+var_A78], rax
0x1800c4c60  mov     [rsp+0AD8h+var_A84], 0EAh
0x1800c4c68  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4c6f  mov     [rsp+0AD8h+var_A80], rax
0x1800c4c74  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4c78  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c4c7f  mov     [rsp+0AD8h+var_A68], rax
0x1800c4c84  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4c89  mov     [rsp+0AD8h+var_A90], rax
0x1800c4c8e  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4c93  mov     [rsp+0AD8h+var_A98], rax
0x1800c4c98  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4c9d  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4ca2  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4ca7  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4cac  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4cb1  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4cb6  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4cbb  lea     rdx, byte_1801A8F13
0x1800c4cc2  jmp     loc_1800C4A87
0x1800c4cc7  lea     r8, [rdi+0F30h]; unsigned __int16 *
0x1800c4cce  mov     rdx, r14; unsigned __int64
0x1800c4cd1  lea     rcx, [rsp+0AD8h+var_228]; unsigned __int16 *
0x1800c4cd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c4cde  mov     ebx, eax
0x1800c4ce0  test    eax, eax
0x1800c4ce2  jns     loc_1800C4D76
0x1800c4ce8  mov     eax, cs:dword_1801B76C8
0x1800c4cee  cmp     eax, 2
0x1800c4cf1  jbe     loc_1800C4F7A
0x1800c4cf7  lea     rax, aOpsetupdatecha_3; "opSetUpdateChannel.LockEventName is not"...
0x1800c4cfe  mov     [rsp+0AD8h+var_A70], rax
0x1800c4d03  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4d0a  mov     [rsp+0AD8h+var_A78], rax
0x1800c4d0f  mov     [rsp+0AD8h+var_A84], 0F1h
0x1800c4d17  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4d1e  mov     [rsp+0AD8h+var_A80], rax
0x1800c4d23  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4d27  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c4d2e  mov     [rsp+0AD8h+var_A68], rax
0x1800c4d33  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4d38  mov     [rsp+0AD8h+var_A90], rax
0x1800c4d3d  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4d42  mov     [rsp+0AD8h+var_A98], rax
0x1800c4d47  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4d4c  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4d51  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4d56  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4d5b  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4d60  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4d65  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4d6a  lea     rdx, dword_1801A8F64
0x1800c4d71  jmp     loc_1800C4A87
0x1800c4d76  mov     [rsp+0AD8h+lpOverlapped], 0; lpOverlapped
0x1800c4d7f  lea     rax, [rsp+0AD8h+BytesReturned]
0x1800c4d84  mov     [rsp+0AD8h+lpBytesReturned], rax; lpBytesReturned
0x1800c4d89  mov     [rsp+0AD8h+nOutBufferSize], 0; nOutBufferSize
0x1800c4d91  mov     [rsp+0AD8h+lpOutBuffer], 0; lpOutBuffer
0x1800c4d9a  mov     r9d, 0A38h; nInBufferSize
0x1800c4da0  lea     r8, [rsp+0AD8h+InBuffer]; lpInBuffer
0x1800c4da8  mov     edx, 80000048h; dwIoControlCode
0x1800c4dad  mov     rcx, [rdi+58h]; hDevice
0x1800c4db1  call    cs:__imp_DeviceIoControl
0x1800c4db7  test    eax, eax
0x1800c4db9  jnz     loc_1800C4E70
0x1800c4dbf  call    cs:__imp_GetLastError
0x1800c4dc5  mov     ebx, eax
0x1800c4dc7  test    eax, eax
0x1800c4dc9  jle     short loc_1800C4DD4
0x1800c4dcb  movzx   ebx, ax
0x1800c4dce  or      ebx, 80070000h
0x1800c4dd4  mov     [rsp+0AD8h+var_A5C], ebx
0x1800c4dd8  mov     eax, cs:dword_1801B76C8
0x1800c4dde  cmp     eax, 2
0x1800c4de1  jbe     loc_1800C4E6B
0x1800c4de7  lea     rax, aFailedToSendRd_7; "Failed to send RDPAVENC_OPCODE_TYPE_SET"...
0x1800c4dee  mov     [rsp+0AD8h+var_A70], rax
0x1800c4df3  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4dfa  mov     [rsp+0AD8h+var_A78], rax
0x1800c4dff  mov     [rsp+0AD8h+var_A84], 101h
0x1800c4e07  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4e0e  mov     [rsp+0AD8h+var_A80], rax
0x1800c4e13  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4e17  lea     rax, aErrorCondition; "Error condition failed"
0x1800c4e1e  mov     [rsp+0AD8h+var_A68], rax
0x1800c4e23  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4e28  mov     [rsp+0AD8h+var_A90], rax
0x1800c4e2d  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4e32  mov     [rsp+0AD8h+var_A98], rax
0x1800c4e37  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4e3c  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4e41  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4e46  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4e4b  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4e50  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4e55  lea     rax, [rsp+0AD8h+var_A68]
0x1800c4e5a  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800c4e5f  lea     rdx, byte_1801A8E79
0x1800c4e66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c4e6b  jmp     loc_1800C4F7A
0x1800c4e70  xor     ebx, ebx
0x1800c4e72  jmp     loc_1800C4F7A
0x1800c4e77  mov     ebx, eax
0x1800c4e79  bts     ebx, 1Ch
0x1800c4e7d  mov     [rsp+0AD8h+var_A5C], ebx
0x1800c4e81  mov     eax, cs:dword_1801B76C8
0x1800c4e87  cmp     eax, 2
0x1800c4e8a  jbe     short loc_1800C4EFA
0x1800c4e8c  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4e93  mov     [rsp+0AD8h+var_A70], rax
0x1800c4e98  mov     [rsp+0AD8h+var_A84], 106h
0x1800c4ea0  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4ea7  mov     [rsp+0AD8h+var_A78], rax
0x1800c4eac  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4eb0  lea     rax, aRaisedExceptio; "Raised exception while I/O with RDPIDD."...
0x1800c4eb7  mov     [rsp+0AD8h+var_A80], rax
0x1800c4ebc  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4ec1  mov     [rsp+0AD8h+var_A98], rax
0x1800c4ec6  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4ecb  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4ed0  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4ed5  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4eda  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4edf  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4ee4  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4ee9  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800c4eee  lea     rdx, word_1801A8ECA
0x1800c4ef5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c4efa  jmp     short loc_1800C4F7A
0x1800c4efc  mov     ebx, 8000FFFFh
0x1800c4f01  mov     eax, cs:dword_1801B76C8
0x1800c4f07  cmp     eax, 2
0x1800c4f0a  jbe     short loc_1800C4F7A
0x1800c4f0c  lea     rax, aSendsetupdatec; "SendSetUpdateChannel"
0x1800c4f13  mov     [rsp+0AD8h+var_A70], rax
0x1800c4f18  mov     [rsp+0AD8h+var_A84], 0D2h
0x1800c4f20  lea     rax, aClientcoreTerm_9; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c4f27  mov     [rsp+0AD8h+var_A78], rax
0x1800c4f2c  mov     [rsp+0AD8h+var_A88], ebx
0x1800c4f30  lea     rax, aUnexpectedSche; "Unexpected scheduler event name"
0x1800c4f37  mov     [rsp+0AD8h+var_A80], rax
0x1800c4f3c  lea     rax, [rsp+0AD8h+var_A70]
0x1800c4f41  mov     [rsp+0AD8h+var_A98], rax
0x1800c4f46  lea     rax, [rsp+0AD8h+var_A84]
0x1800c4f4b  mov     [rsp+0AD8h+lpOverlapped], rax
0x1800c4f50  lea     rax, [rsp+0AD8h+var_A78]
0x1800c4f55  mov     [rsp+0AD8h+lpBytesReturned], rax
0x1800c4f5a  lea     rax, [rsp+0AD8h+var_A88]
0x1800c4f5f  mov     qword ptr [rsp+0AD8h+nOutBufferSize], rax
0x1800c4f64  lea     rax, [rsp+0AD8h+var_A80]
0x1800c4f69  mov     [rsp+0AD8h+lpOutBuffer], rax
0x1800c4f6e  lea     rdx, qword_1801A90A8
0x1800c4f75  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c4f7a  mov     eax, ebx
0x1800c4f7c  mov     rcx, [rsp+0AD8h+var_18]
0x1800c4f84  xor     rcx, rsp; StackCookie
0x1800c4f87  call    __security_check_cookie
0x1800c4f8c  lea     r11, [rsp+0AD8h+var_8]
0x1800c4f94  mov     rbx, [r11+18h]
0x1800c4f98  mov     rdi, [r11+20h]
0x1800c4f9c  mov     rsp, r11
  ... truncated ...
```
