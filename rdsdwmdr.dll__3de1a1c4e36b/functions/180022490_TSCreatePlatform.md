# TSCreatePlatform

- ea: `0x180022490`
- end: `0x1800225dc`
- name: `TSCreatePlatform`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002063c`

## callees

- `0x18000160c`
- `0x1800032d4`
- `0x180022490`
- `0x18002c010`

## string_xrefs

- `0x18002254b`: `TSCreatePlatform`
- `0x180022569`: `onecore\termsrv\rdpplatform\common\devplatform\platform\platform.cpp`

## pseudocode

```c
__int64 __fastcall TSCreatePlatform(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const char *v8; // [rsp+50h] [rbp-28h] BYREF
  const char *v9; // [rsp+58h] [rbp-20h] BYREF
  const char *v10; // [rsp+60h] [rbp-18h] BYREF
  int v11; // [rsp+90h] [rbp+18h] BYREF
  int v12; // [rsp+98h] [rbp+20h] BYREF

  v4 = operator new(0x48u);
  if ( v4 )
  {
    *v4 = &ITSPlatform::`vftable';
    v4[3] = "CTSPlatform";
    v4[1] = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    v4[2] = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v4 + 8) = -607474739;
    *((_DWORD *)v4 + 9) = 1;
    *((_DWORD *)v4 + 12) = 0;
    v4[5] = v4 + 1;
    *v4 = &CTSPlatform::`vftable';
    v4[1] = &CTSPlatform::`vftable'{for `INonDelegatingUnknown'};
    v4[2] = &CTSPlatform::`vftable'{for `CTSObject'};
    *((_DWORD *)v4 + 14) = 0;
    v4[8] = a1;
    *a2 = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v11 = 54;
      v8 = "TSCreatePlatform";
      v12 = -2147467259;
      v9 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\platform.cpp";
      v10 = "OOM on CTSPlatform allocation";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)byte_18003F201,
        v5,
        v6,
        (const unsigned __int16 **)&v10,
        (__int64)&v12,
        (const unsigned __int16 **)&v9,
        (__int64)&v11,
        (const unsigned __int16 **)&v8);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180022490  mov     [rsp+arg_0], rbx
0x180022495  push    rdi
0x180022496  sub     rsp, 70h
0x18002249a  mov     rbx, rdx
0x18002249d  mov     rdi, rcx
0x1800224a0  mov     ecx, 48h ; 'H'; Size
0x1800224a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800224aa  mov     rcx, rax
0x1800224ad  test    rax, rax
0x1800224b0  jz      loc_180022540
0x1800224b6  lea     r8, [rcx+8]
0x1800224ba  lea     rax, ??_7ITSPlatform@@6B@; const ITSPlatform::`vftable'
0x1800224c1  mov     [rcx], rax
0x1800224c4  lea     rax, aCtsplatform; "CTSPlatform"
0x1800224cb  mov     [r8+10h], rax
0x1800224cf  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x1800224d6  mov     [r8], rax
0x1800224d9  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x1800224e0  mov     [r8+8], rax
0x1800224e4  lea     rax, ??_7CTSPlatform@@6B@; const CTSPlatform::`vftable'
0x1800224eb  mov     dword ptr [r8+18h], 0DBCAABCDh
0x1800224f3  mov     dword ptr [r8+1Ch], 1
0x1800224fb  mov     dword ptr [r8+28h], 0
0x180022503  mov     [r8+20h], r8
0x180022507  mov     [rcx], rax
0x18002250a  lea     rax, ??_7CTSPlatform@@6BINonDelegatingUnknown@@@; const CTSPlatform::`vftable'{for `INonDelegatingUnknown'}
0x180022511  mov     [r8], rax
0x180022514  lea     rax, ??_7CTSPlatform@@6BCTSObject@@@; const CTSPlatform::`vftable'{for `CTSObject'}
0x18002251b  mov     [rcx+10h], rax
0x18002251f  mov     dword ptr [rcx+38h], 0
0x180022526  mov     [rcx+40h], rdi
0x18002252a  mov     [rbx], rcx
0x18002252d  mov     rax, [rcx]
0x180022530  mov     rax, [rax+8]
0x180022534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022539  xor     eax, eax
0x18002253b  jmp     loc_1800225CE
0x180022540  mov     eax, cs:dword_180044008
0x180022546  cmp     eax, 2
0x180022549  jbe     short loc_1800225C9
0x18002254b  lea     rax, aTscreateplatfo_0; "TSCreatePlatform"
0x180022552  mov     [rsp+78h+arg_10], 36h ; '6'
0x18002255d  mov     [rsp+78h+var_28], rax
0x180022562  lea     rdx, byte_18003F201
0x180022569  lea     rax, aOnecoreTermsrv_2; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180022570  mov     [rsp+78h+arg_18], 80004005h
0x18002257b  mov     [rsp+78h+var_20], rax
0x180022580  lea     rax, aOomOnCtsplatfo; "OOM on CTSPlatform allocation"
0x180022587  mov     [rsp+78h+var_18], rax
0x18002258c  lea     rax, [rsp+78h+var_28]
0x180022591  mov     [rsp+78h+var_38], rax
0x180022596  lea     rax, [rsp+78h+arg_10]
0x18002259e  mov     [rsp+78h+var_40], rax
0x1800225a3  lea     rax, [rsp+78h+var_20]
0x1800225a8  mov     [rsp+78h+var_48], rax
0x1800225ad  lea     rax, [rsp+78h+arg_18]
0x1800225b5  mov     [rsp+78h+var_50], rax
0x1800225ba  lea     rax, [rsp+78h+var_18]
0x1800225bf  mov     [rsp+78h+var_58], rax
0x1800225c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800225c9  mov     eax, 8007000Eh
0x1800225ce  mov     rbx, [rsp+78h+arg_0]
0x1800225d6  add     rsp, 70h
0x1800225da  pop     rdi
0x1800225db  retn
```
