# RdpDWMDirectWindowContext::DestroySurface(void)

- ea: `0x18000dd74`
- end: `0x18000de1c`
- name: `?DestroySurface@RdpDWMDirectWindowContext@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cb08`
- `0x18000e0e8`
- `0x1800117ac`

## callees

- `0x180001188`
- `0x18000dd74`
- `0x18002c010`

## string_xrefs

- `0x18000ddbc`: `Failed to send the surface delete notification to the driver on destruction.`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::DestroySurface(RdpDWMDirectWindowContext *this)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  int v6; // [rsp+50h] [rbp+8h] BYREF
  const char *v7; // [rsp+58h] [rbp+10h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF
  const char *v9; // [rsp+68h] [rbp+20h] BYREF

  if ( *((_DWORD *)this + 26) )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 82) + 48LL))(
           *((_QWORD *)this + 82),
           *((_QWORD *)this + 8),
           *((_QWORD *)this + 7));
    if ( v2 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v6 = v2;
      v7 = "DestroySurface";
      v8 = "Failed to send the surface delete notification to the driver on destruction.";
      v9 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"DestroySurface",
        (__int64)qword_1800393D8,
        v3,
        v4,
        (const unsigned __int16 **)&v9,
        (const unsigned __int16 **)&v8,
        (__int64)&v6,
        (const unsigned __int16 **)&v7);
    }
    *((_DWORD *)this + 26) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dd74  push    rbx
0x18000dd76  sub     rsp, 40h
0x18000dd7a  cmp     dword ptr [rcx+68h], 0
0x18000dd7e  mov     rbx, rcx
0x18000dd81  jz      loc_18000DE14
0x18000dd87  mov     rcx, [rcx+290h]
0x18000dd8e  mov     r8, [rbx+38h]
0x18000dd92  mov     rdx, [rbx+40h]
0x18000dd96  mov     rax, [rcx]
0x18000dd99  mov     rax, [rax+30h]
0x18000dd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda2  test    eax, eax
0x18000dda4  jns     short loc_18000DE0D
0x18000dda6  mov     ecx, cs:dword_180044008
0x18000ddac  cmp     ecx, 3
0x18000ddaf  jbe     short loc_18000DE0D
0x18000ddb1  mov     [rsp+48h+arg_0], eax
0x18000ddb5  lea     rcx, aDestroysurface; "DestroySurface"
0x18000ddbc  lea     rax, aFailedToSendTh_7; "Failed to send the surface delete notif"...
0x18000ddc3  mov     [rsp+48h+arg_8], rcx
0x18000ddc8  mov     [rsp+48h+arg_10], rax
0x18000ddcd  lea     rdx, qword_1800393D8
0x18000ddd4  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000dddb  mov     [rsp+48h+arg_18], rax
0x18000dde0  lea     rax, [rsp+48h+arg_8]
0x18000dde5  mov     [rsp+48h+var_10], rax
0x18000ddea  lea     rax, [rsp+48h+arg_0]
0x18000ddef  mov     [rsp+48h+var_18], rax
0x18000ddf4  lea     rax, [rsp+48h+arg_10]
0x18000ddf9  mov     [rsp+48h+var_20], rax
0x18000ddfe  lea     rax, [rsp+48h+arg_18]
0x18000de03  mov     [rsp+48h+var_28], rax
0x18000de08  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000de0d  mov     dword ptr [rbx+68h], 0
0x18000de14  xor     eax, eax
0x18000de16  add     rsp, 40h
0x18000de1a  pop     rbx
0x18000de1b  retn
```
