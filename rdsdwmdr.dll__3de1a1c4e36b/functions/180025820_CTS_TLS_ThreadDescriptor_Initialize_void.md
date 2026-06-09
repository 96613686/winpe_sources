# CTS_TLS_ThreadDescriptor::Initialize(void)

- ea: `0x180025820`
- end: `0x1800259ad`
- name: `?Initialize@CTS_TLS_ThreadDescriptor@@EEAAJXZ`
- size: `397`
- prototype: `__int64 __fastcall(CTS_TLS_ThreadDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023fec`

## callees

- `0x18000160c`
- `0x18001d114`
- `0x18001eeac`
- `0x18001f424`
- `0x180025820`
- `0x18002a1c4`

## string_xrefs

- `0x18002593b`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800258b8`: `Getting thread id failed\n`
- `0x180025955`: `Fail to set pTlsThreadDescriptor in TLS`

## pseudocode

```c
__int64 __fastcall CTS_TLS_ThreadDescriptor::Initialize(CTS_TLS_ThreadDescriptor *this)
{
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int Id; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  int ActivityIdPrefix; // eax
  unsigned int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+28h] [rbp-50h]
  const char *v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+80h] [rbp+8h] BYREF
  int v18; // [rsp+88h] [rbp+10h] BYREF
  const char *v19; // [rsp+90h] [rbp+18h] BYREF
  const char *v20; // [rsp+98h] [rbp+20h] BYREF

  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 6) = (char *)this + 64;
  v2 = 0;
  *((_DWORD *)this + 14) = 4;
  *((_QWORD *)this + 8) = 0;
  do
  {
    v3 = v2 + 2 * v2 + 1;
    ++v2;
    v4 = *((_QWORD *)this + 6) + 8 * v3;
    *(_QWORD *)(v4 + 8) = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v4;
  }
  while ( v2 != 16 );
  Id = PAL_System_ThreadGetId((char *)this + 492);
  if ( Id >= 0 )
  {
    v10 = g_PAL_SYS_threadContextIndex;
    *((_DWORD *)this + 124) = g_PAL_SYS_threadContextIndex;
    Id = PAL_System_ThreadSetContext(v10, (char *)this - 8);
    if ( Id < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v17 = 3406;
      v19 = "Initialize";
      v18 = -2147467259;
      v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v16 = "Fail to set pTlsThreadDescriptor in TLS";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (__int64)qword_18003F2D0,
        v12,
        v13,
        (const unsigned __int16 **)&v16,
        (__int64)&v18,
        (const unsigned __int16 **)&v20,
        (__int64)&v17,
        (const unsigned __int16 **)&v19);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5, v7, v8);
    v15 = Id;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      159,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"Getting thread id failed\n",
      v15);
  }
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x180025820  push    rbx
0x180025822  push    rdi
0x180025823  sub     rsp, 68h
0x180025827  mov     rbx, rcx
0x18002582a  lea     rax, [rcx+40h]
0x18002582e  mov     qword ptr [rcx+1C8h], 0
0x180025839  mov     [rcx+30h], rax
0x18002583d  xor     r8d, r8d
0x180025840  mov     dword ptr [rcx+38h], 4
0x180025847  mov     qword ptr [rax], 0
0x18002584e  mov     rax, [rcx+30h]
0x180025852  lea     rdx, ds:1[r8*2]
0x18002585a  add     rdx, r8
0x18002585d  inc     r8
0x180025860  lea     rdx, [rax+rdx*8]
0x180025864  mov     rax, [rcx+28h]
0x180025868  mov     [rdx+8], rax
0x18002586c  mov     [rcx+28h], rdx
0x180025870  cmp     r8, 10h
0x180025874  jnz     short loc_18002584E
0x180025876  add     rcx, 1ECh
0x18002587d  call    PAL_System_ThreadGetId
0x180025882  mov     edi, eax
0x180025884  test    eax, eax
0x180025886  jns     short loc_1800258EC
0x180025888  mov     rax, cs:WPP_GLOBAL_Control
0x18002588f  lea     rcx, WPP_GLOBAL_Control
0x180025896  cmp     rax, rcx
0x180025899  jz      loc_1800259A4
0x18002589f  test    byte ptr [rax+1Ch], 8
0x1800258a3  jz      loc_1800259A4
0x1800258a9  cmp     byte ptr [rax+19h], 2
0x1800258ad  jb      loc_1800259A4
0x1800258b3  call    RdpX_GetActivityIdPrefix
0x1800258b8  lea     rcx, aGettingThreadI; "Getting thread id failed\n"
0x1800258bf  mov     dword ptr [rsp+78h+var_50], edi
0x1800258c3  mov     [rsp+78h+var_58], rcx
0x1800258c8  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800258cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258d6  mov     edx, 9Fh
0x1800258db  mov     r9d, eax
0x1800258de  mov     rcx, [rcx+10h]
0x1800258e2  call    WPP_SF_DsD
0x1800258e7  jmp     loc_1800259A4
0x1800258ec  mov     ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; unsigned int
0x1800258f2  lea     rdx, [rbx-8]; void *
0x1800258f6  mov     [rdx+1F8h], ecx
0x1800258fc  call    ?PAL_System_ThreadSetContext@@YAJKPEAX@Z; PAL_System_ThreadSetContext(ulong,void *)
0x180025901  mov     edi, eax
0x180025903  test    eax, eax
0x180025905  jns     loc_1800259A4
0x18002590b  mov     eax, cs:dword_180044008
0x180025911  cmp     eax, 2
0x180025914  jbe     loc_1800259A4
0x18002591a  lea     rax, aInitialize; "Initialize"
0x180025921  mov     [rsp+78h+arg_0], 0D4Eh
0x18002592c  mov     [rsp+78h+arg_10], rax
0x180025934  lea     rdx, qword_18003F2D0
0x18002593b  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180025942  mov     [rsp+78h+arg_8], 80004005h
0x18002594d  mov     [rsp+78h+arg_18], rax
0x180025955  lea     rax, aFailToSetPtlst; "Fail to set pTlsThreadDescriptor in TLS"
0x18002595c  mov     [rsp+78h+var_28], rax
0x180025961  lea     rax, [rsp+78h+arg_10]
0x180025969  mov     [rsp+78h+var_38], rax
0x18002596e  lea     rax, [rsp+78h+arg_0]
0x180025976  mov     [rsp+78h+var_40], rax
0x18002597b  lea     rax, [rsp+78h+arg_18]
0x180025983  mov     [rsp+78h+var_48], rax
0x180025988  lea     rax, [rsp+78h+arg_8]
0x180025990  mov     [rsp+78h+var_50], rax
0x180025995  lea     rax, [rsp+78h+var_28]
0x18002599a  mov     [rsp+78h+var_58], rax
0x18002599f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800259a4  mov     eax, edi
0x1800259a6  add     rsp, 68h
0x1800259aa  pop     rdi
0x1800259ab  pop     rbx
0x1800259ac  retn
```
