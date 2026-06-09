# RdsDWMDirectDriverIO::OnMapSurfaceToWindow(HWND__ *,HDC__ *,uint,uint)

- ea: `0x18000ad10`
- end: `0x18000ae6c`
- name: `?OnMapSurfaceToWindow@RdsDWMDirectDriverIO@@UEAAJPEAUHWND__@@PEAUHDC__@@II@Z`
- size: `348`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *this, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001188`
- `0x180002374`
- `0x18000ad10`
- `0x18000bdbc`
- `0x18002b960`

## string_xrefs

- `0x18000ae0f`: `SendToRemoteDriver:Failed to send map surface to window update`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnMapSurfaceToWindow(
        RdsDWMDirectDriverIO *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  int v5; // ebx
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  unsigned __int8 *v14; // [rsp+20h] [rbp-71h]
  int v15; // [rsp+50h] [rbp-41h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-3Dh] BYREF
  const char *v17; // [rsp+58h] [rbp-39h] BYREF
  const char *v18; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int8 v19[8]; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int8 v20[4]; // [rsp+70h] [rbp-21h] BYREF
  int v21; // [rsp+74h] [rbp-1Dh]
  int v22; // [rsp+78h] [rbp-19h]
  int v23; // [rsp+7Ch] [rbp-15h]
  int v24; // [rsp+80h] [rbp-11h]
  __int64 v25; // [rsp+84h] [rbp-Dh]
  const unsigned __int16 *v26; // [rsp+8Ch] [rbp-5h]
  const unsigned __int16 *v27; // [rsp+94h] [rbp+3h]
  unsigned int v28; // [rsp+9Ch] [rbp+Bh]
  int v29; // [rsp+A0h] [rbp+Fh]

  v5 = a4;
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v18 = (const char *)a2;
    *(_QWORD *)v19 = "Sending map surface to window notification";
    v16 = a5;
    v15 = a4;
    v17 = (const char *)a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&dword_180037FD4,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v15,
      (__int64)&v16);
  }
  v25 = 0;
  *(_DWORD *)v20 = 52;
  v21 = -1884332398;
  v22 = 2;
  v26 = a3;
  v27 = a2;
  v29 = v5;
  v28 = a5;
  v23 = 18;
  v24 = 40;
  v9 = RdsDWMDirectDriverIO::SendToRemoteDriver((RdsDWMDirectDriverIO *)((char *)this - 48), 52, v20, a4, v14);
  v12 = v9;
  if ( v9 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v15 = v9;
    *(_QWORD *)v19 = "OnMapSurfaceToWindow";
    v18 = "SendToRemoteDriver:Failed to send map surface to window update";
    v17 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_180037F91,
      v10,
      v11,
      (const unsigned __int16 **)&v17,
      (const unsigned __int16 **)&v18,
      (__int64)&v15,
      (const unsigned __int16 **)v19);
  }
  return v12;
}

```

## disassembly

```asm
0x18000ad10  push    rbp
0x18000ad12  push    rbx
0x18000ad13  push    rsi
0x18000ad14  push    rdi
0x18000ad15  push    r14
0x18000ad17  push    r15
0x18000ad19  lea     rbp, [rsp-27h]
0x18000ad1e  sub     rsp, 0B8h
0x18000ad25  mov     rax, cs:__security_cookie
0x18000ad2c  xor     rax, rsp
0x18000ad2f  mov     [rbp+4Fh+var_38], rax
0x18000ad33  mov     eax, cs:dword_180044008
0x18000ad39  mov     ebx, r9d
0x18000ad3c  mov     r14d, [rbp+4Fh+arg_20]
0x18000ad40  mov     rdi, r8
0x18000ad43  mov     rsi, rdx
0x18000ad46  mov     r15, rcx
0x18000ad49  cmp     eax, 4
0x18000ad4c  jbe     short loc_18000ADA1
0x18000ad4e  lea     rax, aSendingMapSurf; "Sending map surface to window notificat"...
0x18000ad55  mov     [rbp+4Fh+var_80], rdx
0x18000ad59  mov     qword ptr [rbp+4Fh+var_78], rax
0x18000ad5d  lea     rdx, dword_180037FD4
0x18000ad64  lea     rax, [rbp+4Fh+var_8C]
0x18000ad68  mov     [rbp+4Fh+var_8C], r14d
0x18000ad6c  mov     [rsp+0E0h+var_A0], rax
0x18000ad71  lea     rax, [rbp+4Fh+var_90]
0x18000ad75  mov     [rsp+0E0h+var_A8], rax
0x18000ad7a  lea     rax, [rbp+4Fh+var_88]
0x18000ad7e  mov     [rsp+0E0h+var_B0], rax
0x18000ad83  lea     rax, [rbp+4Fh+var_80]
0x18000ad87  mov     [rsp+0E0h+var_B8], rax
0x18000ad8c  lea     rax, [rbp+4Fh+var_78]
0x18000ad90  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 *
0x18000ad95  mov     [rbp+4Fh+var_90], ebx
0x18000ad98  mov     [rbp+4Fh+var_88], r8
0x18000ad9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ada1  mov     edx, 34h ; '4'; int
0x18000ada6  mov     [rbp+4Fh+var_5C], 0
0x18000adae  lea     rcx, [r15-30h]; this
0x18000adb2  mov     dword ptr [rbp+4Fh+var_70], edx
0x18000adb5  lea     r8, [rbp+4Fh+var_70]; unsigned __int8 *
0x18000adb9  mov     [rbp+4Fh+var_6C], 8FAF5E92h
0x18000adc0  mov     [rbp+4Fh+var_68], 2
0x18000adc7  mov     [rbp+4Fh+var_54], rdi
0x18000adcb  mov     [rbp+4Fh+var_4C], rsi
0x18000adcf  mov     [rbp+4Fh+var_40], ebx
0x18000add2  mov     [rbp+4Fh+var_44], r14d
0x18000add6  mov     [rbp+4Fh+var_64], 12h
0x18000addd  mov     [rbp+4Fh+var_60], 28h ; '('
0x18000ade4  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000ade9  mov     ebx, eax
0x18000adeb  test    eax, eax
0x18000aded  jns     short loc_18000AE4E
0x18000adef  mov     ecx, cs:dword_180044008
0x18000adf5  cmp     ecx, 3
0x18000adf8  jbe     short loc_18000AE4E
0x18000adfa  lea     rax, aOnmapsurfaceto; "OnMapSurfaceToWindow"
0x18000ae01  mov     [rbp+4Fh+var_90], ebx
0x18000ae04  mov     qword ptr [rbp+4Fh+var_78], rax
0x18000ae08  lea     rdx, byte_180037F91
0x18000ae0f  lea     rax, aSendtoremotedr_6; "SendToRemoteDriver:Failed to send map s"...
0x18000ae16  mov     [rbp+4Fh+var_80], rax
0x18000ae1a  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000ae21  mov     [rbp+4Fh+var_88], rax
0x18000ae25  lea     rax, [rbp+4Fh+var_78]
0x18000ae29  mov     [rsp+0E0h+var_A8], rax
0x18000ae2e  lea     rax, [rbp+4Fh+var_90]
0x18000ae32  mov     [rsp+0E0h+var_B0], rax
0x18000ae37  lea     rax, [rbp+4Fh+var_80]
0x18000ae3b  mov     [rsp+0E0h+var_B8], rax
0x18000ae40  lea     rax, [rbp+4Fh+var_88]
0x18000ae44  mov     [rsp+0E0h+var_C0], rax
0x18000ae49  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ae4e  mov     eax, ebx
0x18000ae50  mov     rcx, [rbp+4Fh+var_38]
0x18000ae54  xor     rcx, rsp; StackCookie
0x18000ae57  call    __security_check_cookie
0x18000ae5c  add     rsp, 0B8h
0x18000ae63  pop     r15
0x18000ae65  pop     r14
0x18000ae67  pop     rdi
0x18000ae68  pop     rsi
0x18000ae69  pop     rbx
0x18000ae6a  pop     rbp
0x18000ae6b  retn
```
