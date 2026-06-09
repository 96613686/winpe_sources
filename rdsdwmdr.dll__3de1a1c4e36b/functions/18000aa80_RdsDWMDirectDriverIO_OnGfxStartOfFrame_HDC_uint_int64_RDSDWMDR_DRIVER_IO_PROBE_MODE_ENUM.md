# RdsDWMDirectDriverIO::OnGfxStartOfFrame(HDC__ *,uint,__int64,_RDSDWMDR_DRIVER_IO_PROBE_MODE_ENUM)

- ea: `0x18000aa80`
- end: `0x18000acaa`
- name: `?OnGfxStartOfFrame@RdsDWMDirectDriverIO@@UEAAJPEAUHDC__@@I_JW4_RDSDWMDR_DRIVER_IO_PROBE_MODE_ENUM@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001188`
- `0x180001f98`
- `0x180002630`
- `0x18000aa80`
- `0x18000bdbc`
- `0x18002b960`

## string_xrefs

- `0x18000ab0c`: `Sending StartOfFrame update (hdcMon = 0x%p, frameId = %d, probe mode %s)`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnGfxStartOfFrame(
        const wchar_t *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  RdsDWMDirectDriverIO *v5; // r14
  int v6; // esi
  unsigned int v7; // edi
  const wchar_t *v8; // rax
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  unsigned __int8 *v14; // [rsp+20h] [rbp-61h]
  int v15; // [rsp+50h] [rbp-31h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int8 v17[8]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v18; // [rsp+68h] [rbp-19h] BYREF
  const char *v19; // [rsp+70h] [rbp-11h] BYREF
  const char *v20; // [rsp+78h] [rbp-9h] BYREF
  unsigned __int8 v21[4]; // [rsp+80h] [rbp-1h] BYREF
  __int128 v22; // [rsp+84h] [rbp+3h]
  __int128 v23; // [rsp+94h] [rbp+13h]

  v5 = (RdsDWMDirectDriverIO *)(a1 - 24);
  *((_QWORD *)a1 + 66) = a4;
  v6 = a3;
  *(_DWORD *)v21 = 0;
  v7 = 2;
  v22 = 0;
  v23 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    if ( a5 == 1 )
    {
      v8 = L"CHK_RECONNECT";
    }
    else if ( a5 == 2 )
    {
      v8 = L"ACK_RECONNECT";
    }
    else
    {
      v8 = L"NONE";
      a1 = L"UNKN";
      if ( a5 )
        v8 = L"UNKN";
    }
    v16 = v8;
    *(_QWORD *)v17 = "Sending StartOfFrame update (hdcMon = 0x%p, frameId = %d, probe mode %s)";
    v18 = a2;
    v15 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)a1,
      (__int64)&unk_180038268,
      a3,
      a4,
      (const unsigned __int16 **)v17,
      (__int64)&v18,
      (__int64)&v15,
      (char **)&v16);
  }
  if ( a5 == 1 )
  {
    v7 = 1;
  }
  else if ( a5 != 2 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v15 = a5;
      v19 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      *(_QWORD *)v17 = "OnGfxStartOfFrame";
      v20 = "Probe mode value not handled";
      LODWORD(v18) = 932;
      LODWORD(v16) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)(a5 - 1),
        (__int64)&unk_180038210,
        a3,
        a4,
        (const unsigned __int16 **)&v20,
        (__int64)&v16,
        (const unsigned __int16 **)&v19,
        (__int64)&v18,
        (const unsigned __int16 **)v17,
        (__int64)&v15);
    }
    v7 = 0;
  }
  *(_QWORD *)&v22 = 0x18FAF5E92LL;
  *(_DWORD *)v21 = 36;
  v23 = v7 | 0x100000000uLL;
  HIDWORD(v22) = v6;
  DWORD2(v22) = 1;
  v9 = RdsDWMDirectDriverIO::SendToRemoteDriver(v5, 36, v21, a4, v14);
  v12 = v9;
  if ( v9 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    LODWORD(v16) = v9;
    v20 = "OnGfxStartOfFrame";
    v19 = "SendToRemoteDriver:Failed to send start frame";
    *(_QWORD *)v17 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_1800381CD,
      v10,
      v11,
      (const unsigned __int16 **)v17,
      (const unsigned __int16 **)&v19,
      (__int64)&v16,
      (const unsigned __int16 **)&v20);
  }
  return v12;
}

```

## disassembly

```asm
0x18000aa80  mov     [rsp-8+arg_8], rbx
0x18000aa85  push    rbp
0x18000aa86  push    rsi
0x18000aa87  push    rdi
0x18000aa88  push    r12
0x18000aa8a  push    r14
0x18000aa8c  lea     rbp, [rsp-2Fh]
0x18000aa91  sub     rsp, 0B0h
0x18000aa98  mov     rax, cs:__security_cookie
0x18000aa9f  xor     rax, rsp
0x18000aaa2  mov     [rbp+4Fh+var_28], rax
0x18000aaa6  mov     ebx, [rbp+4Fh+arg_20]
0x18000aaa9  lea     r14, [rcx-30h]
0x18000aaad  xorps   xmm0, xmm0
0x18000aab0  mov     [r14+240h], r9
0x18000aab7  mov     eax, cs:dword_180044008
0x18000aabd  mov     esi, r8d
0x18000aac0  mov     dword ptr [rbp+4Fh+var_50], 0
0x18000aac7  mov     edi, 2
0x18000aacc  movups  [rbp+4Fh+var_4C], xmm0
0x18000aad0  movups  [rbp+4Fh+var_3C], xmm0
0x18000aad4  cmp     eax, 5
0x18000aad7  jbe     short loc_18000AB4E
0x18000aad9  cmp     ebx, 1
0x18000aadc  jnz     short loc_18000AAE7
0x18000aade  lea     rax, aChkReconnect; "CHK_RECONNECT"
0x18000aae5  jmp     short loc_18000AB08
0x18000aae7  cmp     ebx, edi
0x18000aae9  jnz     short loc_18000AAF4
0x18000aaeb  lea     rax, aAckReconnect; "ACK_RECONNECT"
0x18000aaf2  jmp     short loc_18000AB08
0x18000aaf4  test    ebx, ebx
0x18000aaf6  lea     rax, aNone; "NONE"
0x18000aafd  lea     rcx, aUnkn; "UNKN"
0x18000ab04  cmovnz  rax, rcx
0x18000ab08  mov     [rbp+4Fh+var_78], rax
0x18000ab0c  lea     rax, aSendingStartof; "Sending StartOfFrame update (hdcMon = 0"...
0x18000ab13  mov     qword ptr [rbp+4Fh+var_70], rax
0x18000ab17  lea     rax, [rbp+4Fh+var_78]
0x18000ab1b  mov     [rsp+0D0h+var_98], rax
0x18000ab20  lea     rax, [rbp+4Fh+var_80]
0x18000ab24  mov     [rsp+0D0h+var_A0], rax
0x18000ab29  lea     rax, [rbp+4Fh+var_68]
0x18000ab2d  mov     [rsp+0D0h+var_A8], rax
0x18000ab32  lea     rax, [rbp+4Fh+var_70]
0x18000ab36  mov     [rbp+4Fh+var_68], rdx
0x18000ab3a  lea     rdx, unk_180038268
0x18000ab41  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x18000ab46  mov     [rbp+4Fh+var_80], esi
0x18000ab49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000ab4e  mov     ecx, ebx
0x18000ab50  lea     r12, aOngfxstartoffr; "OnGfxStartOfFrame"
0x18000ab57  sub     ecx, 1
0x18000ab5a  jz      loc_18000ABE4
0x18000ab60  cmp     ecx, 1
0x18000ab63  jz      loc_18000ABE9
0x18000ab69  mov     eax, cs:dword_180044008
0x18000ab6f  cmp     eax, edi
0x18000ab71  jbe     short loc_18000ABE0
0x18000ab73  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000ab7a  mov     [rbp+4Fh+var_80], ebx
0x18000ab7d  mov     [rbp+4Fh+var_60], rax
0x18000ab81  lea     rdx, unk_180038210
0x18000ab88  lea     rax, aProbeModeValue; "Probe mode value not handled"
0x18000ab8f  mov     qword ptr [rbp+4Fh+var_70], r12
0x18000ab93  mov     [rbp+4Fh+var_58], rax
0x18000ab97  lea     rax, [rbp+4Fh+var_80]
0x18000ab9b  mov     [rsp+0D0h+var_88], rax
0x18000aba0  lea     rax, [rbp+4Fh+var_70]
0x18000aba4  mov     [rsp+0D0h+var_90], rax
0x18000aba9  lea     rax, [rbp+4Fh+var_68]
0x18000abad  mov     [rsp+0D0h+var_98], rax
0x18000abb2  lea     rax, [rbp+4Fh+var_60]
0x18000abb6  mov     [rsp+0D0h+var_A0], rax
0x18000abbb  lea     rax, [rbp+4Fh+var_78]
0x18000abbf  mov     [rsp+0D0h+var_A8], rax
0x18000abc4  lea     rax, [rbp+4Fh+var_58]
0x18000abc8  mov     [rsp+0D0h+var_B0], rax
0x18000abcd  mov     dword ptr [rbp+4Fh+var_68], 3A4h
0x18000abd4  mov     dword ptr [rbp+4Fh+var_78], 8000FFFFh
0x18000abdb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000abe0  xor     edi, edi
0x18000abe2  jmp     short loc_18000ABE9
0x18000abe4  mov     edi, 1
0x18000abe9  mov     edx, 24h ; '$'; int
0x18000abee  mov     dword ptr [rbp+4Fh+var_4C], 8FAF5E92h
0x18000abf5  lea     r8, [rbp+4Fh+var_50]; unsigned __int8 *
0x18000abf9  mov     dword ptr [rbp+4Fh+var_50], edx
0x18000abfc  mov     rcx, r14; this
0x18000abff  mov     dword ptr [rbp+4Fh+var_4C+4], 1
0x18000ac06  mov     dword ptr [rbp+4Fh+var_3C], edi
0x18000ac09  mov     dword ptr [rbp+4Fh+var_4C+0Ch], esi
0x18000ac0c  mov     dword ptr [rbp+4Fh+var_3C+4], 1
0x18000ac13  mov     qword ptr [rbp+4Fh+var_3C+8], 0
0x18000ac1b  mov     dword ptr [rbp+4Fh+var_4C+8], 1
0x18000ac22  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000ac27  mov     ebx, eax
0x18000ac29  test    eax, eax
0x18000ac2b  jns     short loc_18000AC85
0x18000ac2d  mov     ecx, cs:dword_180044008
0x18000ac33  cmp     ecx, 3
0x18000ac36  jbe     short loc_18000AC85
0x18000ac38  mov     dword ptr [rbp+4Fh+var_78], eax
0x18000ac3b  lea     rdx, byte_1800381CD
0x18000ac42  lea     rax, aSendtoremotedr_1; "SendToRemoteDriver:Failed to send start"...
0x18000ac49  mov     [rbp+4Fh+var_58], r12
0x18000ac4d  mov     [rbp+4Fh+var_60], rax
0x18000ac51  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000ac58  mov     qword ptr [rbp+4Fh+var_70], rax
0x18000ac5c  lea     rax, [rbp+4Fh+var_58]
0x18000ac60  mov     [rsp+0D0h+var_98], rax
0x18000ac65  lea     rax, [rbp+4Fh+var_78]
0x18000ac69  mov     [rsp+0D0h+var_A0], rax
0x18000ac6e  lea     rax, [rbp+4Fh+var_60]
0x18000ac72  mov     [rsp+0D0h+var_A8], rax
0x18000ac77  lea     rax, [rbp+4Fh+var_70]
0x18000ac7b  mov     [rsp+0D0h+var_B0], rax
0x18000ac80  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ac85  mov     eax, ebx
0x18000ac87  mov     rcx, [rbp+4Fh+var_28]
0x18000ac8b  xor     rcx, rsp; StackCookie
0x18000ac8e  call    __security_check_cookie
0x18000ac93  mov     rbx, [rsp+0D0h+arg_8]
0x18000ac9b  add     rsp, 0B0h
0x18000aca2  pop     r14
0x18000aca4  pop     r12
0x18000aca6  pop     rdi
0x18000aca7  pop     rsi
0x18000aca8  pop     rbp
0x18000aca9  retn
```
