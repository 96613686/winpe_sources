# RdsDWMDirectDriverIO::OnWndSurfaceUpdated(HWND__ *,HDC__ *,tagRECT *)

- ea: `0x18000b820`
- end: `0x18000b984`
- name: `?OnWndSurfaceUpdated@RdsDWMDirectDriverIO@@UEAAJPEAUHWND__@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `356`
- prototype: `int(RdsDWMDirectDriverIO *__hidden this, HWND, HDC, struct tagRECT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001188`
- `0x1800022b0`
- `0x18000b820`
- `0x18000bdbc`
- `0x18002b960`

## import_xrefs

- `USER32!CopyRect` at `0x18000b8e6`
- `USER32!CopyRect` at `0x18000b8e6`

## string_xrefs

- `0x18000b856`: `Sending surface update notification (windowId=0x%p hsurf=0x%I64x)`
- `0x18000b90f`: `OnWndSurfaceUpdated`
- `0x18000b924`: `SendToRemoteDriver:Failed to send surface update event`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnWndSurfaceUpdated(
        RdsDWMDirectDriverIO *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct tagRECT *a4)
{
  int v7; // r9d
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  unsigned __int8 *v13; // [rsp+20h] [rbp-59h]
  __int64 v14; // [rsp+40h] [rbp-39h] BYREF
  const char *v15; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int8 v16[8]; // [rsp+50h] [rbp-29h] BYREF
  const char *v17; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int8 v18[4]; // [rsp+60h] [rbp-19h] BYREF
  int v19; // [rsp+64h] [rbp-15h]
  __int64 v20; // [rsp+68h] [rbp-11h]
  int v21; // [rsp+70h] [rbp-9h]
  __int64 v22; // [rsp+74h] [rbp-5h]
  int v23; // [rsp+7Ch] [rbp+3h]
  __int64 v24; // [rsp+80h] [rbp+7h]
  __int64 v25; // [rsp+88h] [rbp+Fh]
  struct tagRECT rcDst; // [rsp+90h] [rbp+17h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+27h]
  __int64 v28; // [rsp+A8h] [rbp+2Fh]

  if ( (unsigned int)dword_180044008 > 5 )
  {
    v15 = (const char *)a2;
    *(_QWORD *)v16 = "Sending surface update notification (windowId=0x%p hsurf=0x%I64x)";
    v14 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)&byte_180037F4F,
      a3,
      (__int64)a4,
      (const unsigned __int16 **)v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  v28 = *((_QWORD *)this + 66);
  rcDst = 0;
  v22 = 0;
  *(_DWORD *)v18 = 80;
  v19 = -1884332398;
  v20 = 2;
  v21 = 68;
  v23 = 0;
  v24 = a3;
  v25 = a3;
  v27 = 0;
  CopyRect(&rcDst, a4);
  v8 = RdsDWMDirectDriverIO::SendToRemoteDriver((RdsDWMDirectDriverIO *)((char *)this - 48), 80, v18, v7, v13);
  v11 = v8;
  if ( v8 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    LODWORD(v14) = v8;
    *(_QWORD *)v16 = "OnWndSurfaceUpdated";
    v15 = "SendToRemoteDriver:Failed to send surface update event";
    v17 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_180037F0C,
      v9,
      v10,
      (const unsigned __int16 **)&v17,
      (const unsigned __int16 **)&v15,
      (__int64)&v14,
      (const unsigned __int16 **)v16);
  }
  return v11;
}

```

## disassembly

```asm
0x18000b820  mov     [rsp-8+arg_8], rbx
0x18000b825  push    rbp
0x18000b826  push    rsi
0x18000b827  push    rdi
0x18000b828  lea     rbp, [rsp-47h]
0x18000b82d  sub     rsp, 0C0h
0x18000b834  mov     rax, cs:__security_cookie
0x18000b83b  xor     rax, rsp
0x18000b83e  mov     [rbp+57h+var_20], rax
0x18000b842  mov     eax, cs:dword_180044008
0x18000b848  mov     rsi, r9
0x18000b84b  mov     rbx, r8
0x18000b84e  mov     rdi, rcx
0x18000b851  cmp     eax, 5
0x18000b854  jbe     short loc_18000B890
0x18000b856  lea     rax, aSendingSurface_0; "Sending surface update notification (wi"...
0x18000b85d  mov     [rbp+57h+var_88], rdx
0x18000b861  mov     qword ptr [rbp+57h+var_80], rax
0x18000b865  lea     rdx, byte_180037F4F
0x18000b86c  lea     rax, [rbp+57h+var_90]
0x18000b870  mov     [rbp+57h+var_90], rbx
0x18000b874  mov     [rsp+0D0h+var_A0], rax
0x18000b879  lea     rax, [rbp+57h+var_88]
0x18000b87d  mov     [rsp+0D0h+var_A8], rax
0x18000b882  lea     rax, [rbp+57h+var_80]
0x18000b886  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 *
0x18000b88b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000b890  mov     rax, [rdi+210h]
0x18000b897  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18000b89b  xorps   xmm0, xmm0
0x18000b89e  mov     [rbp+57h+var_28], rax
0x18000b8a2  mov     rdx, rsi; lprcSrc
0x18000b8a5  movdqa  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18000b8aa  mov     [rbp+57h+var_5C], 0
0x18000b8b2  mov     dword ptr [rbp+57h+var_70], 50h ; 'P'
0x18000b8b9  mov     [rbp+57h+var_6C], 8FAF5E92h
0x18000b8c0  mov     [rbp+57h+var_68], 2
0x18000b8c8  mov     [rbp+57h+var_60], 44h ; 'D'
0x18000b8cf  mov     [rbp+57h+var_54], 0
0x18000b8d6  mov     [rbp+57h+var_50], rbx
0x18000b8da  mov     [rbp+57h+var_48], rbx
0x18000b8de  mov     [rbp+57h+var_30], 0
0x18000b8e6  call    cs:__imp_CopyRect
0x18000b8ec  lea     r8, [rbp+57h+var_70]; unsigned __int8 *
0x18000b8f0  mov     edx, 50h ; 'P'; int
0x18000b8f5  lea     rcx, [rdi-30h]; this
0x18000b8f9  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000b8fe  mov     ebx, eax
0x18000b900  test    eax, eax
0x18000b902  jns     short loc_18000B963
0x18000b904  mov     ecx, cs:dword_180044008
0x18000b90a  cmp     ecx, 3
0x18000b90d  jbe     short loc_18000B963
0x18000b90f  lea     rax, aOnwndsurfaceup; "OnWndSurfaceUpdated"
0x18000b916  mov     dword ptr [rbp+57h+var_90], ebx
0x18000b919  mov     qword ptr [rbp+57h+var_80], rax
0x18000b91d  lea     rdx, dword_180037F0C
0x18000b924  lea     rax, aSendtoremotedr; "SendToRemoteDriver:Failed to send surfa"...
0x18000b92b  mov     [rbp+57h+var_88], rax
0x18000b92f  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000b936  mov     [rbp+57h+var_78], rax
0x18000b93a  lea     rax, [rbp+57h+var_80]
0x18000b93e  mov     [rsp+0D0h+var_98], rax
0x18000b943  lea     rax, [rbp+57h+var_90]
0x18000b947  mov     [rsp+0D0h+var_A0], rax
0x18000b94c  lea     rax, [rbp+57h+var_88]
0x18000b950  mov     [rsp+0D0h+var_A8], rax
0x18000b955  lea     rax, [rbp+57h+var_78]
0x18000b959  mov     [rsp+0D0h+var_B0], rax
0x18000b95e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b963  mov     eax, ebx
0x18000b965  mov     rcx, [rbp+57h+var_20]
0x18000b969  xor     rcx, rsp; StackCookie
0x18000b96c  call    __security_check_cookie
0x18000b971  mov     rbx, [rsp+0D0h+arg_8]
0x18000b979  add     rsp, 0C0h
0x18000b980  pop     rdi
0x18000b981  pop     rsi
0x18000b982  pop     rbp
0x18000b983  retn
```
