# RdsDWMDirectDriverIO::OnWndSurfaceDestroyed(HWND__ *,HDC__ *)

- ea: `0x18000b6e0`
- end: `0x18000b812`
- name: `?OnWndSurfaceDestroyed@RdsDWMDirectDriverIO@@UEAAJPEAUHWND__@@PEAUHDC__@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this, HWND, HDC)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x180001188`
- `0x1800022b0`
- `0x18000b6e0`
- `0x18000bdbc`
- `0x18002b960`

## string_xrefs

- `0x18000b7b0`: `SendToRemoteDriver:Failed to send surface delete update`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnWndSurfaceDestroyed(
        HDC *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v11; // [rsp+48h] [rbp+7h] BYREF
  const char *v12; // [rsp+50h] [rbp+Fh] BYREF
  const char *v13; // [rsp+58h] [rbp+17h] BYREF
  const char *v14; // [rsp+60h] [rbp+1Fh] BYREF
  unsigned __int8 v15[4]; // [rsp+68h] [rbp+27h] BYREF
  int v16; // [rsp+6Ch] [rbp+2Bh]
  int v17; // [rsp+70h] [rbp+2Fh]
  int v18; // [rsp+74h] [rbp+33h]
  int v19; // [rsp+78h] [rbp+37h]
  __int64 v20; // [rsp+7Ch] [rbp+3Bh]
  __int64 v21; // [rsp+84h] [rbp+43h]

  if ( (unsigned int)dword_180044008 > 4 )
  {
    v12 = (const char *)a2;
    v13 = "Sending surface destroyed notification";
    v11 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)&dword_18003806C,
      a3,
      a4,
      (const unsigned __int16 **)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
  v20 = 0;
  *(_DWORD *)v15 = 36;
  v16 = -1884332398;
  v17 = 2;
  v21 = a3;
  v18 = 11;
  v19 = 24;
  v6 = RdsDWMDirectDriverIO::SendToRemoteDriver(this - 6, (const unsigned __int16 *)0x24, (CHAR *)v15);
  v9 = v6;
  if ( v6 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    LODWORD(v11) = v6;
    v13 = "OnWndSurfaceDestroyed";
    v12 = "SendToRemoteDriver:Failed to send surface delete update";
    v14 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_180038029,
      v7,
      v8,
      (const unsigned __int16 **)&v14,
      (const unsigned __int16 **)&v12,
      (__int64)&v11,
      (const unsigned __int16 **)&v13);
  }
  return v9;
}

```

## disassembly

```asm
0x18000b6e0  mov     r11, rsp
0x18000b6e3  mov     [r11+10h], rbx
0x18000b6e7  mov     [r11+18h], rdi
0x18000b6eb  push    rbp
0x18000b6ec  lea     rbp, [r11-5Fh]
0x18000b6f0  sub     rsp, 90h
0x18000b6f7  mov     rax, cs:__security_cookie
0x18000b6fe  xor     rax, rsp
0x18000b701  mov     [rbp+57h+var_8], rax
0x18000b705  mov     eax, cs:dword_180044008
0x18000b70b  mov     rbx, r8
0x18000b70e  mov     rdi, rcx
0x18000b711  cmp     eax, 4
0x18000b714  jbe     short loc_18000B74D
0x18000b716  lea     rax, aSendingSurface; "Sending surface destroyed notification"
0x18000b71d  mov     [rbp+57h+var_48], rdx
0x18000b721  mov     [rbp+57h+var_40], rax
0x18000b725  lea     rdx, dword_18003806C
0x18000b72c  lea     rax, [rbp+57h+var_50]
0x18000b730  mov     [rbp+57h+var_50], rbx
0x18000b734  mov     [r11-68h], rax
0x18000b738  lea     rax, [rbp+57h+var_48]
0x18000b73c  mov     [r11-70h], rax
0x18000b740  lea     rax, [rbp+57h+var_40]
0x18000b744  mov     [r11-78h], rax
0x18000b748  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000b74d  mov     edx, 24h ; '$'; int
0x18000b752  mov     [rbp+57h+var_1C], 0
0x18000b75a  lea     rcx, [rdi-30h]; this
0x18000b75e  mov     dword ptr [rbp+57h+var_30], edx
0x18000b761  lea     r8, [rbp+57h+var_30]; unsigned __int8 *
0x18000b765  mov     [rbp+57h+var_2C], 8FAF5E92h
0x18000b76c  mov     [rbp+57h+var_28], 2
0x18000b773  mov     [rbp+57h+var_14], rbx
0x18000b777  mov     [rbp+57h+var_24], 0Bh
0x18000b77e  mov     [rbp+57h+var_20], 18h
0x18000b785  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000b78a  mov     ebx, eax
0x18000b78c  test    eax, eax
0x18000b78e  jns     short loc_18000B7EF
0x18000b790  mov     ecx, cs:dword_180044008
0x18000b796  cmp     ecx, 3
0x18000b799  jbe     short loc_18000B7EF
0x18000b79b  lea     rax, aOnwndsurfacede; "OnWndSurfaceDestroyed"
0x18000b7a2  mov     dword ptr [rbp+57h+var_50], ebx
0x18000b7a5  mov     [rbp+57h+var_40], rax
0x18000b7a9  lea     rdx, byte_180038029
0x18000b7b0  lea     rax, aSendtoremotedr_4; "SendToRemoteDriver:Failed to send surfa"...
0x18000b7b7  mov     [rbp+57h+var_48], rax
0x18000b7bb  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000b7c2  mov     [rbp+57h+var_38], rax
0x18000b7c6  lea     rax, [rbp+57h+var_40]
0x18000b7ca  mov     [rsp+90h+var_58], rax
0x18000b7cf  lea     rax, [rbp+57h+var_50]
0x18000b7d3  mov     [rsp+90h+var_60], rax
0x18000b7d8  lea     rax, [rbp+57h+var_48]
0x18000b7dc  mov     [rsp+90h+var_68], rax
0x18000b7e1  lea     rax, [rbp+57h+var_38]
0x18000b7e5  mov     [rsp+90h+var_70], rax
0x18000b7ea  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b7ef  mov     eax, ebx
0x18000b7f1  mov     rcx, [rbp+57h+var_8]
0x18000b7f5  xor     rcx, rsp; StackCookie
0x18000b7f8  call    __security_check_cookie
0x18000b7fd  lea     r11, [rsp+90h+var_s0]
0x18000b805  mov     rbx, [r11+18h]
0x18000b809  mov     rdi, [r11+20h]
0x18000b80d  mov     rsp, r11
0x18000b810  pop     rbp
0x18000b811  retn
```
