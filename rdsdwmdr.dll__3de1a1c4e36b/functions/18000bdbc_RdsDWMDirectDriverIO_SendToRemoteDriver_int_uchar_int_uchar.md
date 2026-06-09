# RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)

- ea: `0x18000bdbc`
- end: `0x18000c22b`
- name: `?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z`
- size: `1135`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, int, unsigned __int8 *, int, unsigned __int8 *)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a930`
- `0x18000aa80`
- `0x18000ad10`
- `0x18000ae80`
- `0x18000b2e0`
- `0x18000b4d0`
- `0x18000b6e0`
- `0x18000b820`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x180001f98`
- `0x1800020bc`
- `0x180008fa4`
- `0x18000a0a4`
- `0x18000bdbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c15b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c15b`
- `GDI32!ExtEscape` at `0x18000c094`
- `GDI32!ExtEscape` at `0x18000c094`

## string_xrefs

- `0x18000bdec`: `RDPIDD handle opened successfully`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::SendToRemoteDriver(HDC *this, const unsigned __int16 *a2, CHAR *a3)
{
  int v4; // esi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // edi
  signed int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  signed int LastError; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int8 *cjOutput; // [rsp+20h] [rbp-98h]
  int lpOutData; // [rsp+28h] [rbp-90h]
  int v26; // [rsp+60h] [rbp-58h] BYREF
  int v27; // [rsp+64h] [rbp-54h] BYREF
  unsigned __int8 v28[8]; // [rsp+68h] [rbp-50h] BYREF
  const char *v29; // [rsp+70h] [rbp-48h] BYREF
  const char *v30; // [rsp+78h] [rbp-40h] BYREF
  const char *v31; // [rsp+80h] [rbp-38h] BYREF
  unsigned int v32; // [rsp+88h] [rbp-30h]
  const char *v33; // [rsp+90h] [rbp-28h] BYREF

  v4 = (int)a2;
  if ( !*((_DWORD *)this + 158) )
  {
LABEL_6:
    if ( this[74] == (HDC)-1LL )
    {
      v14 = ExtEscape(this[73], 4124, v4, a3, 0, 0);
      if ( v14 )
      {
        v9 = 0;
        if ( v14 < 0 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v9 = -2147467259;
          }
          if ( (unsigned int)dword_180044008 > 2 )
          {
            LODWORD(v29) = v14;
            v27 = 4124;
            v31 = "SendToRemoteDriver";
            v26 = 863;
            v30 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
            *(_DWORD *)v28 = v9;
            v33 = "ExtEscape failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v20,
              (__int64)byte_1800382B3,
              v21,
              v22,
              (const unsigned __int16 **)&v33,
              (__int64)v28,
              (const unsigned __int16 **)&v30,
              (__int64)&v26,
              (const unsigned __int16 **)&v31,
              (__int64)&v27,
              (__int64)&v29);
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          LODWORD(v29) = 4124;
          v31 = "SendToRemoteDriver";
          v27 = 850;
          v30 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
          v15 = GetLastError();
          if ( v15 > 0 )
            v15 = (unsigned __int16)v15 | 0x80070000;
          v26 = v15;
          *(_QWORD *)v28 = "ExtEscape ignored by driver";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v16,
            (__int64)byte_180038315,
            v17,
            v18,
            (const unsigned __int16 **)v28,
            (__int64)&v26,
            (const unsigned __int16 **)&v30,
            (__int64)&v27,
            (const unsigned __int16 **)&v31,
            (__int64)&v29);
        }
        return (unsigned int)-2147467263;
      }
    }
    else
    {
      *((_DWORD *)a3 + 1) = 0;
      if ( *((_DWORD *)a3 + 2) == 1 )
      {
        *((_DWORD *)a3 + 2) = 512;
      }
      else if ( *((_DWORD *)a3 + 2) != 513 )
      {
        *((_DWORD *)a3 + 2) = 514;
      }
      v10 = RdsDWMDirectDriverIO::IddOverlappedIo(
              (RdsDWMDirectDriverIO *)this,
              0x80000044,
              (unsigned __int8 *)a3,
              v4,
              cjOutput,
              lpOutData,
              0xFFFFFFFF);
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      v32 = v9;
      if ( (v9 & 0x80000000) != 0 && (unsigned int)dword_180044008 > 2 )
      {
        v31 = "IddOverlappedIo failed";
        v30 = "SendToRemoteDriver";
        v27 = 827;
        *(_QWORD *)v28 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v26 = v9;
        v29 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (__int64)byte_1800383CB,
          v12,
          v13,
          (const unsigned __int16 **)&v29,
          (__int64)&v26,
          (const unsigned __int16 **)v28,
          (__int64)&v27,
          (const unsigned __int16 **)&v30,
          (const unsigned __int16 **)&v31);
      }
    }
    return v9;
  }
  if ( (unsigned int)RdsDWMDirectDriverIO::GetDxgkAdapter((RdsDWMDirectDriverIO *)this, a2) )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      *(_QWORD *)v28 = "RDPIDD handle opened successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (__int64)byte_180038475,
        v7,
        v8,
        (const unsigned __int16 **)v28);
    }
    *((_DWORD *)this + 158) = 0;
    goto LABEL_6;
  }
  v9 = -2147024875;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    *(_QWORD *)v28 = "Failed to find RDPIDD driver";
    v29 = "SendToRemoteDriver";
    v26 = 750;
    v30 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    v27 = -2147024875;
    v31 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v6,
      (__int64)&unk_180038420,
      v7,
      v8,
      (const unsigned __int16 **)&v31,
      (__int64)&v27,
      (const unsigned __int16 **)&v30,
      (__int64)&v26,
      (const unsigned __int16 **)&v29,
      (const unsigned __int16 **)v28);
  }
  return v9;
}

```

## disassembly

```asm
0x18000bdbc  push    rbx
0x18000bdbe  push    rsi
0x18000bdbf  push    rdi
0x18000bdc0  sub     rsp, 0A0h
0x18000bdc7  mov     rbx, r8
0x18000bdca  mov     esi, edx
0x18000bdcc  mov     rdi, rcx
0x18000bdcf  cmp     dword ptr [rcx+278h], 0
0x18000bdd6  jz      short loc_18000BE18
0x18000bdd8  call    ?GetDxgkAdapter@RdsDWMDirectDriverIO@@IEAAHPEBG@Z; RdsDWMDirectDriverIO::GetDxgkAdapter(ushort const *)
0x18000bddd  test    eax, eax
0x18000bddf  mov     eax, cs:dword_180044008
0x18000bde5  jz      short loc_18000BE43
0x18000bde7  cmp     eax, 4
0x18000bdea  jbe     short loc_18000BE0E
0x18000bdec  lea     rax, aRdpiddHandleOp; "RDPIDD handle opened successfully"
0x18000bdf3  mov     qword ptr [rsp+0B8h+var_50], rax
0x18000bdf8  lea     rax, [rsp+0B8h+var_50]
0x18000bdfd  mov     qword ptr [rsp+0B8h+cjOutput], rax; unsigned __int8 *
0x18000be02  lea     rdx, byte_180038475
0x18000be09  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000be0e  mov     dword ptr [rdi+278h], 0
0x18000be18  cmp     qword ptr [rdi+250h], 0FFFFFFFFFFFFFFFFh
0x18000be20  jz      loc_18000C06F
0x18000be26  mov     dword ptr [rbx+4], 0
0x18000be2d  cmp     dword ptr [rbx+8], 1
0x18000be31  jnz     loc_18000BEE0
0x18000be37  mov     dword ptr [rbx+8], 200h
0x18000be3e  jmp     loc_18000BEF0
0x18000be43  mov     ebx, 80070015h
0x18000be48  cmp     eax, 2
0x18000be4b  jbe     loc_18000C21E
0x18000be51  lea     rax, aFailedToFindRd; "Failed to find RDPIDD driver"
0x18000be58  mov     qword ptr [rsp+0B8h+var_50], rax
0x18000be5d  lea     rax, aSendtoremotedr_2; "SendToRemoteDriver"
0x18000be64  mov     [rsp+0B8h+var_48], rax
0x18000be69  mov     [rsp+0B8h+var_58], 2EEh
0x18000be71  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000be78  mov     [rsp+0B8h+var_40], rax
0x18000be7d  mov     [rsp+0B8h+var_54], ebx
0x18000be81  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000be88  mov     [rsp+0B8h+var_38], rax
0x18000be90  lea     rax, [rsp+0B8h+var_50]
0x18000be95  mov     [rsp+0B8h+var_70], rax
0x18000be9a  lea     rax, [rsp+0B8h+var_48]
0x18000be9f  mov     [rsp+0B8h+var_78], rax
0x18000bea4  lea     rax, [rsp+0B8h+var_58]
0x18000bea9  mov     [rsp+0B8h+var_80], rax
0x18000beae  lea     rax, [rsp+0B8h+var_40]
0x18000beb3  mov     qword ptr [rsp+0B8h+dwMilliseconds], rax
0x18000beb8  lea     rax, [rsp+0B8h+var_54]
0x18000bebd  mov     [rsp+0B8h+lpOutData], rax
0x18000bec2  lea     rax, [rsp+0B8h+var_38]
0x18000beca  mov     qword ptr [rsp+0B8h+cjOutput], rax
0x18000becf  lea     rdx, unk_180038420
0x18000bed6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000bedb  jmp     loc_18000C21E
0x18000bee0  cmp     dword ptr [rbx+8], 201h
0x18000bee7  jz      short loc_18000BEF0
0x18000bee9  mov     dword ptr [rbx+8], 202h
0x18000bef0  mov     [rsp+0B8h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000bef8  mov     r9d, esi; int
0x18000befb  mov     r8, rbx; unsigned __int8 *
0x18000befe  mov     edx, 80000044h; unsigned int
0x18000bf03  mov     rcx, rdi; this
0x18000bf06  call    ?IddOverlappedIo@RdsDWMDirectDriverIO@@IEAAKKPEAEH0HK@Z; RdsDWMDirectDriverIO::IddOverlappedIo(ulong,uchar *,int,uchar *,int,ulong)
0x18000bf0b  mov     ebx, eax
0x18000bf0d  test    eax, eax
0x18000bf0f  jle     short loc_18000BF1A
0x18000bf11  movzx   ebx, ax
0x18000bf14  or      ebx, 80070000h
0x18000bf1a  mov     [rsp+0B8h+var_30], ebx
0x18000bf21  test    ebx, ebx
0x18000bf23  jns     loc_18000BFC7
0x18000bf29  mov     eax, cs:dword_180044008
0x18000bf2f  cmp     eax, 2
0x18000bf32  jbe     loc_18000BFC2
0x18000bf38  lea     rax, aIddoverlappedi; "IddOverlappedIo failed"
0x18000bf3f  mov     [rsp+0B8h+var_38], rax
0x18000bf47  lea     rax, aSendtoremotedr_2; "SendToRemoteDriver"
0x18000bf4e  mov     [rsp+0B8h+var_40], rax
0x18000bf53  mov     [rsp+0B8h+var_54], 33Bh
0x18000bf5b  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000bf62  mov     qword ptr [rsp+0B8h+var_50], rax
0x18000bf67  mov     [rsp+0B8h+var_58], ebx
0x18000bf6b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000bf72  mov     [rsp+0B8h+var_48], rax
0x18000bf77  lea     rax, [rsp+0B8h+var_38]
0x18000bf7f  mov     [rsp+0B8h+var_70], rax
0x18000bf84  lea     rax, [rsp+0B8h+var_40]
0x18000bf89  mov     [rsp+0B8h+var_78], rax
0x18000bf8e  lea     rax, [rsp+0B8h+var_54]
0x18000bf93  mov     [rsp+0B8h+var_80], rax
0x18000bf98  lea     rax, [rsp+0B8h+var_50]
0x18000bf9d  mov     qword ptr [rsp+0B8h+dwMilliseconds], rax
0x18000bfa2  lea     rax, [rsp+0B8h+var_58]
0x18000bfa7  mov     [rsp+0B8h+lpOutData], rax
0x18000bfac  lea     rax, [rsp+0B8h+var_48]
0x18000bfb1  mov     qword ptr [rsp+0B8h+cjOutput], rax
0x18000bfb6  lea     rdx, byte_1800383CB
0x18000bfbd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000bfc2  jmp     loc_18000C21E
0x18000bfc7  jmp     loc_18000C21E
0x18000bfcc  mov     ebx, eax
0x18000bfce  bts     ebx, 1Ch
0x18000bfd2  mov     [rsp+0B8h+var_30], ebx
0x18000bfd9  mov     ecx, cs:dword_180044008
0x18000bfdf  cmp     ecx, 2
0x18000bfe2  jbe     loc_18000C06A
0x18000bfe8  mov     [rsp+0B8h+var_54], eax
0x18000bfec  lea     rax, aSendtoremotedr_2; "SendToRemoteDriver"
0x18000bff3  mov     [rsp+0B8h+var_38], rax
0x18000bffb  mov     [rsp+0B8h+var_58], 342h
0x18000c003  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000c00a  mov     [rsp+0B8h+var_40], rax
0x18000c00f  mov     dword ptr [rsp+0B8h+var_48], ebx
0x18000c013  lea     rax, aRaisedExceptio; "Raised exception while I/O with RDPIDD."...
0x18000c01a  mov     qword ptr [rsp+0B8h+var_50], rax
0x18000c01f  lea     rax, [rsp+0B8h+var_54]
0x18000c024  mov     [rsp+0B8h+var_70], rax
0x18000c029  lea     rax, [rsp+0B8h+var_38]
0x18000c031  mov     [rsp+0B8h+var_78], rax
0x18000c036  lea     rax, [rsp+0B8h+var_58]
0x18000c03b  mov     [rsp+0B8h+var_80], rax
0x18000c040  lea     rax, [rsp+0B8h+var_40]
0x18000c045  mov     qword ptr [rsp+0B8h+dwMilliseconds], rax
0x18000c04a  lea     rax, [rsp+0B8h+var_48]
0x18000c04f  mov     [rsp+0B8h+lpOutData], rax
0x18000c054  lea     rax, [rsp+0B8h+var_50]
0x18000c059  mov     qword ptr [rsp+0B8h+cjOutput], rax
0x18000c05e  lea     rdx, byte_18003836F
0x18000c065  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c06a  jmp     loc_18000C21E
0x18000c06f  mov     [rsp+0B8h+lpOutData], 0; lpOutData
0x18000c078  mov     [rsp+0B8h+cjOutput], 0; cjOutput
0x18000c080  mov     r9, rbx; lpInData
0x18000c083  mov     r8d, esi; cjInput
0x18000c086  mov     esi, 101Ch
0x18000c08b  mov     edx, esi; iEscape
0x18000c08d  mov     rcx, [rdi+248h]; hdc
0x18000c094  call    cs:__imp_ExtEscape
0x18000c09a  mov     edi, eax
0x18000c09c  test    eax, eax
0x18000c09e  jnz     loc_18000C151
0x18000c0a4  mov     eax, cs:dword_180044008
0x18000c0aa  cmp     eax, 2
0x18000c0ad  jbe     loc_18000C147
0x18000c0b3  mov     dword ptr [rsp+0B8h+var_48], esi
0x18000c0b7  lea     rax, aSendtoremotedr_2; "SendToRemoteDriver"
0x18000c0be  mov     [rsp+0B8h+var_38], rax
0x18000c0c6  mov     [rsp+0B8h+var_54], 352h
0x18000c0ce  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000c0d5  mov     [rsp+0B8h+var_40], rax
0x18000c0da  call    cs:__imp_GetLastError
0x18000c0e0  test    eax, eax
0x18000c0e2  jle     short loc_18000C0EC
0x18000c0e4  movzx   eax, ax
0x18000c0e7  or      eax, 80070000h
0x18000c0ec  mov     [rsp+0B8h+var_58], eax
0x18000c0f0  lea     rax, aExtescapeIgnor; "ExtEscape ignored by driver"
0x18000c0f7  mov     qword ptr [rsp+0B8h+var_50], rax
0x18000c0fc  lea     rax, [rsp+0B8h+var_48]
0x18000c101  mov     [rsp+0B8h+var_70], rax
0x18000c106  lea     rax, [rsp+0B8h+var_38]
0x18000c10e  mov     [rsp+0B8h+var_78], rax
0x18000c113  lea     rax, [rsp+0B8h+var_54]
0x18000c118  mov     [rsp+0B8h+var_80], rax
0x18000c11d  lea     rax, [rsp+0B8h+var_40]
0x18000c122  mov     qword ptr [rsp+0B8h+dwMilliseconds], rax
0x18000c127  lea     rax, [rsp+0B8h+var_58]
0x18000c12c  mov     [rsp+0B8h+lpOutData], rax
0x18000c131  lea     rax, [rsp+0B8h+var_50]
0x18000c136  mov     qword ptr [rsp+0B8h+cjOutput], rax
0x18000c13b  lea     rdx, byte_180038315
0x18000c142  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c147  mov     ebx, 80004001h
0x18000c14c  jmp     loc_18000C21E
0x18000c151  xor     ebx, ebx
0x18000c153  test    edi, edi
0x18000c155  jns     loc_18000C21E
0x18000c15b  call    cs:__imp_GetLastError
0x18000c161  mov     ebx, eax
0x18000c163  test    eax, eax
0x18000c165  jz      short loc_18000C174
0x18000c167  jle     short loc_18000C179
0x18000c169  movzx   ebx, ax
0x18000c16c  or      ebx, 80070000h
0x18000c172  jmp     short loc_18000C179
0x18000c174  mov     ebx, 80004005h
0x18000c179  mov     eax, cs:dword_180044008
0x18000c17f  cmp     eax, 2
0x18000c182  jbe     loc_18000C21E
0x18000c188  mov     dword ptr [rsp+0B8h+var_48], edi
0x18000c18c  mov     [rsp+0B8h+var_54], esi
0x18000c190  lea     rax, aSendtoremotedr_2; "SendToRemoteDriver"
0x18000c197  mov     [rsp+0B8h+var_38], rax
0x18000c19f  mov     [rsp+0B8h+var_58], 35Fh
0x18000c1a7  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000c1ae  mov     [rsp+0B8h+var_40], rax
0x18000c1b3  mov     dword ptr [rsp+0B8h+var_50], ebx
0x18000c1b7  lea     rax, aExtescapeFaile; "ExtEscape failed"
0x18000c1be  mov     [rsp+0B8h+var_28], rax
0x18000c1c6  lea     rax, [rsp+0B8h+var_48]
0x18000c1cb  mov     [rsp+0B8h+var_68], rax
0x18000c1d0  lea     rax, [rsp+0B8h+var_54]
0x18000c1d5  mov     [rsp+0B8h+var_70], rax
0x18000c1da  lea     rax, [rsp+0B8h+var_38]
0x18000c1e2  mov     [rsp+0B8h+var_78], rax
0x18000c1e7  lea     rax, [rsp+0B8h+var_58]
0x18000c1ec  mov     [rsp+0B8h+var_80], rax
0x18000c1f1  lea     rax, [rsp+0B8h+var_40]
0x18000c1f6  mov     qword ptr [rsp+0B8h+dwMilliseconds], rax
0x18000c1fb  lea     rax, [rsp+0B8h+var_50]
0x18000c200  mov     [rsp+0B8h+lpOutData], rax
0x18000c205  lea     rax, [rsp+0B8h+var_28]
0x18000c20d  mov     qword ptr [rsp+0B8h+cjOutput], rax
0x18000c212  lea     rdx, byte_1800382B3
0x18000c219  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c21e  mov     eax, ebx
0x18000c220  add     rsp, 0A0h
0x18000c227  pop     rdi
0x18000c228  pop     rsi
0x18000c229  pop     rbx
0x18000c22a  retn
0x18002bd46  push    rbp
0x18002bd48  sub     rsp, 60h
0x18002bd4c  mov     rbp, rdx
0x18002bd4f  mov     rax, [rcx]
0x18002bd52  xor     ecx, ecx
0x18002bd54  cmp     dword ptr [rax], 0C0000008h
0x18002bd5a  setz    cl
0x18002bd5d  mov     eax, ecx
0x18002bd5f  add     rsp, 60h
0x18002bd63  pop     rbp
0x18002bd64  retn
```
