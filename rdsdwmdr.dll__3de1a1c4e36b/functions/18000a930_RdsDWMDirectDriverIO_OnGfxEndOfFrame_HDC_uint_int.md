# RdsDWMDirectDriverIO::OnGfxEndOfFrame(HDC__ *,uint,int)

- ea: `0x18000a930`
- end: `0x18000aa6b`
- name: `?OnGfxEndOfFrame@RdsDWMDirectDriverIO@@UEAAJPEAUHDC__@@IH@Z`
- size: `315`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *this, const unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001188`
- `0x180001ca4`
- `0x18000a930`
- `0x18000bdbc`
- `0x18002b960`

## string_xrefs

- `0x18000a97a`: `Sending EndOfFrame update (hdcMon = 0x%p, frameId = %d)`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::OnGfxEndOfFrame(
        RdsDWMDirectDriverIO *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r14d
  int v5; // edi
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  unsigned __int8 *v13; // [rsp+20h] [rbp-39h]
  int v14; // [rsp+40h] [rbp-19h] BYREF
  const char *v15; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int8 v16[8]; // [rsp+50h] [rbp-9h] BYREF
  const char *v17; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int8 v18[4]; // [rsp+60h] [rbp+7h] BYREF
  __int128 v19; // [rsp+64h] [rbp+Bh]
  __int128 v20; // [rsp+74h] [rbp+1Bh]

  *(_DWORD *)v18 = 0;
  v4 = a4;
  v5 = a3;
  v19 = 0;
  v20 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v15 = (const char *)a2;
    *(_QWORD *)v16 = "Sending EndOfFrame update (hdcMon = 0x%p, frameId = %d)";
    v14 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)byte_18003818D,
      a3,
      a4,
      (const unsigned __int16 **)v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  LODWORD(v19) = -1884332398;
  *(_DWORD *)v18 = 36;
  *(_QWORD *)((char *)&v19 + 4) = 1;
  LODWORD(v20) = 0;
  HIDWORD(v19) = v5;
  *((_QWORD *)&v20 + 1) = a2;
  DWORD1(v20) = v4;
  v8 = RdsDWMDirectDriverIO::SendToRemoteDriver((RdsDWMDirectDriverIO *)((char *)this - 48), 36, v18, a4, v13);
  v11 = v8;
  if ( v8 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v14 = v8;
    *(_QWORD *)v16 = "OnGfxEndOfFrame";
    v15 = "SendToRemoteDriver:Failed to send end frame";
    v17 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)word_18003814A,
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
0x18000a930  push    rbp
0x18000a932  push    rbx
0x18000a933  push    rsi
0x18000a934  push    rdi
0x18000a935  push    r14
0x18000a937  lea     rbp, [rsp-37h]
0x18000a93c  sub     rsp, 90h
0x18000a943  mov     rax, cs:__security_cookie
0x18000a94a  xor     rax, rsp
0x18000a94d  mov     [rbp+57h+var_28], rax
0x18000a951  mov     eax, cs:dword_180044008
0x18000a957  xorps   xmm0, xmm0
0x18000a95a  mov     dword ptr [rbp+57h+var_50], 0
0x18000a961  mov     r14d, r9d
0x18000a964  mov     edi, r8d
0x18000a967  mov     rbx, rdx
0x18000a96a  mov     rsi, rcx
0x18000a96d  movups  [rbp+57h+var_4C], xmm0
0x18000a971  movups  [rbp+57h+var_3C], xmm0
0x18000a975  cmp     eax, 5
0x18000a978  jbe     short loc_18000A9B4
0x18000a97a  lea     rax, aSendingEndoffr; "Sending EndOfFrame update (hdcMon = 0x%"...
0x18000a981  mov     [rbp+57h+var_68], rdx
0x18000a985  mov     qword ptr [rbp+57h+var_60], rax
0x18000a989  lea     rdx, byte_18003818D
0x18000a990  lea     rax, [rbp+57h+var_70]
0x18000a994  mov     [rbp+57h+var_70], r8d
0x18000a998  mov     [rsp+0B0h+var_80], rax
0x18000a99d  lea     rax, [rbp+57h+var_68]
0x18000a9a1  mov     [rsp+0B0h+var_88], rax
0x18000a9a6  lea     rax, [rbp+57h+var_60]
0x18000a9aa  mov     [rsp+0B0h+var_90], rax; unsigned __int8 *
0x18000a9af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000a9b4  mov     edx, 24h ; '$'; int
0x18000a9b9  mov     dword ptr [rbp+57h+var_4C], 8FAF5E92h
0x18000a9c0  lea     rcx, [rsi-30h]; this
0x18000a9c4  mov     dword ptr [rbp+57h+var_50], edx
0x18000a9c7  lea     r8, [rbp+57h+var_50]; unsigned __int8 *
0x18000a9cb  mov     qword ptr [rbp+57h+var_4C+4], 1
0x18000a9d3  mov     dword ptr [rbp+57h+var_3C], 0
0x18000a9da  mov     dword ptr [rbp+57h+var_4C+0Ch], edi
0x18000a9dd  mov     qword ptr [rbp+57h+var_3C+8], rbx
0x18000a9e1  mov     dword ptr [rbp+57h+var_3C+4], r14d
0x18000a9e5  call    ?SendToRemoteDriver@RdsDWMDirectDriverIO@@IEAAJHPEAEH0@Z; RdsDWMDirectDriverIO::SendToRemoteDriver(int,uchar *,int,uchar *)
0x18000a9ea  mov     ebx, eax
0x18000a9ec  test    eax, eax
0x18000a9ee  jns     short loc_18000AA4F
0x18000a9f0  mov     ecx, cs:dword_180044008
0x18000a9f6  cmp     ecx, 3
0x18000a9f9  jbe     short loc_18000AA4F
0x18000a9fb  lea     rax, aOngfxendoffram; "OnGfxEndOfFrame"
0x18000aa02  mov     [rbp+57h+var_70], ebx
0x18000aa05  mov     qword ptr [rbp+57h+var_60], rax
0x18000aa09  lea     rdx, word_18003814A
0x18000aa10  lea     rax, aSendtoremotedr_3; "SendToRemoteDriver:Failed to send end f"...
0x18000aa17  mov     [rbp+57h+var_68], rax
0x18000aa1b  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000aa22  mov     [rbp+57h+var_58], rax
0x18000aa26  lea     rax, [rbp+57h+var_60]
0x18000aa2a  mov     [rsp+0B0h+var_78], rax
0x18000aa2f  lea     rax, [rbp+57h+var_70]
0x18000aa33  mov     [rsp+0B0h+var_80], rax
0x18000aa38  lea     rax, [rbp+57h+var_68]
0x18000aa3c  mov     [rsp+0B0h+var_88], rax
0x18000aa41  lea     rax, [rbp+57h+var_58]
0x18000aa45  mov     [rsp+0B0h+var_90], rax
0x18000aa4a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000aa4f  mov     eax, ebx
0x18000aa51  mov     rcx, [rbp+57h+var_28]
0x18000aa55  xor     rcx, rsp; StackCookie
0x18000aa58  call    __security_check_cookie
0x18000aa5d  add     rsp, 90h
0x18000aa64  pop     r14
0x18000aa66  pop     rdi
0x18000aa67  pop     rsi
0x18000aa68  pop     rbx
0x18000aa69  pop     rbp
0x18000aa6a  retn
```
