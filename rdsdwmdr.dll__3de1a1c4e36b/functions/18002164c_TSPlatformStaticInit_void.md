# TSPlatformStaticInit(void)

- ea: `0x18002164c`
- end: `0x18002176a`
- name: `?TSPlatformStaticInit@@YAJXZ`
- size: `286`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002063c`

## callees

- `0x18000160c`
- `0x18001e40c`
- `0x18002164c`

## string_xrefs

- `0x180021685`: `onecore\termsrv\rdpplatform\common\devplatform\plat_ind\platformmini.cpp`
- `0x180021708`: `onecore\termsrv\rdpplatform\common\devplatform\plat_ind\platformmini.cpp`

## pseudocode

```c
__int64 __fastcall TSPlatformStaticInit(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  const unsigned __int16 *v8[3]; // [rsp+50h] [rbp-18h] BYREF
  int v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF
  const char *v11; // [rsp+90h] [rbp+28h] BYREF
  const char *v12; // [rsp+98h] [rbp+30h] BYREF

  if ( g_dwTSPlatformInitCount )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v9 = 56;
      v11 = "TSPlatformStaticInit";
      v10 = -2147467259;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\plat_ind\\platformmini.cpp";
      v8[0] = (const unsigned __int16 *)"Static TS Platform initialization should only be done once!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (__int64)byte_18003F135,
        a3,
        a4,
        v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v12,
        (__int64)&v9,
        (const unsigned __int16 **)&v11);
    }
    return (unsigned int)-2147467259;
  }
  else
  {
    v4 = PAL_System_Initialize();
    if ( v4 >= 0 )
    {
      ++g_dwTSPlatformInitCount;
      return 0;
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v9 = 66;
      v11 = "TSPlatformStaticInit";
      v10 = -2147467259;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\plat_ind\\platformmini.cpp";
      v8[0] = (const unsigned __int16 *)"System PAL failed to initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)qword_18003F0F0,
        v5,
        v6,
        v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v12,
        (__int64)&v9,
        (const unsigned __int16 **)&v11);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002164c  mov     r11, rsp
0x18002164f  push    rbp
0x180021650  push    rbx
0x180021651  mov     rbp, rsp
0x180021654  sub     rsp, 68h
0x180021658  cmp     cs:?g_dwTSPlatformInitCount@@3KA, 0; ulong g_dwTSPlatformInitCount
0x18002165f  jz      short loc_1800216D9
0x180021661  mov     eax, cs:dword_180044008
0x180021667  cmp     eax, 2
0x18002166a  jbe     short loc_1800216CF
0x18002166c  lea     rax, aTsplatformstat; "TSPlatformStaticInit"
0x180021673  mov     [rbp+arg_0], 38h ; '8'
0x18002167a  mov     [rbp+arg_10], rax
0x18002167e  lea     rdx, byte_18003F135
0x180021685  lea     rax, aOnecoreTermsrv_6; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002168c  mov     [rbp+arg_8], 80004005h
0x180021693  mov     [rbp+arg_18], rax
0x180021697  lea     rax, aStaticTsPlatfo; "Static TS Platform initialization shoul"...
0x18002169e  mov     [rbp+var_18], rax
0x1800216a2  lea     rax, [rbp+arg_10]
0x1800216a6  mov     [r11-38h], rax
0x1800216aa  lea     rax, [rbp+arg_0]
0x1800216ae  mov     [r11-40h], rax
0x1800216b2  lea     rax, [rbp+arg_18]
0x1800216b6  mov     [r11-48h], rax
0x1800216ba  lea     rax, [rbp+arg_8]
0x1800216be  mov     [r11-50h], rax
0x1800216c2  lea     rax, [rbp+var_18]
0x1800216c6  mov     [r11-58h], rax
0x1800216ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800216cf  mov     ebx, 80004005h
0x1800216d4  jmp     loc_180021761
0x1800216d9  call    ?PAL_System_Initialize@@YAJXZ; PAL_System_Initialize(void)
0x1800216de  mov     ebx, eax
0x1800216e0  test    eax, eax
0x1800216e2  jns     short loc_180021759
0x1800216e4  mov     ecx, cs:dword_180044008
0x1800216ea  cmp     ecx, 2
0x1800216ed  jbe     short loc_180021761
0x1800216ef  lea     rax, aTsplatformstat; "TSPlatformStaticInit"
0x1800216f6  mov     [rbp+arg_0], 42h ; 'B'
0x1800216fd  mov     [rbp+arg_10], rax
0x180021701  lea     rdx, qword_18003F0F0
0x180021708  lea     rax, aOnecoreTermsrv_6; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002170f  mov     [rbp+arg_8], 80004005h
0x180021716  mov     [rbp+arg_18], rax
0x18002171a  lea     rax, aSystemPalFaile; "System PAL failed to initialize"
0x180021721  mov     [rbp+var_18], rax
0x180021725  lea     rax, [rbp+arg_10]
0x180021729  mov     [rsp+68h+var_28], rax
0x18002172e  lea     rax, [rbp+arg_0]
0x180021732  mov     [rsp+68h+var_30], rax
0x180021737  lea     rax, [rbp+arg_18]
0x18002173b  mov     [rsp+68h+var_38], rax
0x180021740  lea     rax, [rbp+arg_8]
0x180021744  mov     [rsp+68h+var_40], rax
0x180021749  lea     rax, [rbp+var_18]
0x18002174d  mov     [rsp+68h+var_48], rax
0x180021752  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021757  jmp     short loc_180021761
0x180021759  inc     cs:?g_dwTSPlatformInitCount@@3KA; ulong g_dwTSPlatformInitCount
0x18002175f  xor     ebx, ebx
0x180021761  mov     eax, ebx
0x180021763  add     rsp, 68h
0x180021767  pop     rbx
0x180021768  pop     rbp
0x180021769  retn
```
