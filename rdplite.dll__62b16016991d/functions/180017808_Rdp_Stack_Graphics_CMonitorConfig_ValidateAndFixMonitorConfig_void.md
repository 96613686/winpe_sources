# Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(void)

- ea: `0x180017808`
- end: `0x180017cf5`
- name: `?ValidateAndFixMonitorConfig@CMonitorConfig@Graphics@Stack@Rdp@@AEAAXXZ`
- size: `1261`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfig *this, __int64, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016b1c`
- `0x180016ce0`

## callees

- `0x18000208c`
- `0x180004154`
- `0x180004260`
- `0x180004958`
- `0x18000fcd0`
- `0x18001721c`
- `0x180017808`

## string_xrefs

- `0x180017826`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfig.cpp`
- `0x18001781f`: `Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig(
        Rdp::Stack::Graphics::CMonitorConfig *this,
        __int64 a2,
        int a3,
        int a4)
{
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  _DWORD *v8; // rbx
  _DWORD *v9; // rbx
  _DWORD *v10; // rbx
  char *Buffer[2]; // [rsp+40h] [rbp-20h] BYREF
  char *v12; // [rsp+50h] [rbp-10h]
  __int64 v13; // [rsp+A0h] [rbp+40h] BYREF
  const char *v14; // [rsp+A8h] [rbp+48h] BYREF
  const char *v15; // [rsp+B0h] [rbp+50h] BYREF
  const char *v16; // [rsp+B8h] [rbp+58h] BYREF

  if ( (*((_BYTE *)this + 100) & 2) != 0 )
  {
    if ( *((_DWORD *)this + 34) < 0xC8u )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "Resolution.cx is less than minimum allowed(200). Resetting to 200";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 341;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_1800354C3,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 34) = 200;
    }
    if ( *((_DWORD *)this + 35) < 0xC8u )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "Resolution.cy is less than minimum allowed(200). Resetting to 200";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 347;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_18003548B,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 35) = 200;
    }
    v5 = *((_DWORD *)this + 37);
    if ( v5 && v5 != 90 && v5 != 180 && v5 != 270 )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "Orientation does not have a valid value. Resetting to 0";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 356;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_180035453,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 37) = 0;
    }
    if ( *((_DWORD *)this + 24) )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        Buffer[0] = (char *)std::_Allocate<16,std::_Default_allocate_traits>(2048);
        v12 = Buffer[0] + 2048;
        memset_0(Buffer[0], 0, 0x800u);
        Buffer[1] = Buffer[0] + 2048;
        v13 = 0;
        std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(&v13);
        snprintf(Buffer[0], 0x800u, "Overriding RefreshRate. Resetting to %dHz", *((_DWORD *)this + 24));
        if ( (unsigned int)dword_18003C058 > 3 )
        {
          v14 = Buffer[0];
          v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
          LODWORD(v13) = 362;
          v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)byte_18003541B,
            v6,
            v7,
            (__int64)&v16,
            (__int64)&v13,
            (__int64)&v15,
            (__int64)&v14);
        }
        std::vector<char>::_Tidy(Buffer);
      }
      *((_DWORD *)this + 38) = *((_DWORD *)this + 24);
      *((_DWORD *)this + 39) = 1;
    }
    else
    {
      v8 = (_DWORD *)((char *)this + 156);
      if ( !*((_DWORD *)this + 38) || !*v8 )
      {
        if ( (unsigned int)dword_18003C058 > 3 )
        {
          v14 = "RefreshRate is out of range. Resetting to 32Hz";
          v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
          LODWORD(v13) = 369;
          v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)byte_1800353E3,
            a3,
            a4,
            (__int64)&v16,
            (__int64)&v13,
            (__int64)&v15,
            (__int64)&v14);
        }
        *((_DWORD *)this + 38) = 32;
        *v8 = 1;
      }
    }
    if ( !*((_DWORD *)this + 40) )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "VSyncFreqDivider is 0. Resetting to 1";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 376;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_1800353AB,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 40) = 1;
    }
  }
  if ( (*((_BYTE *)this + 100) & 8) != 0 )
  {
    v9 = (_DWORD *)((char *)this + 196);
    if ( !*((_DWORD *)this + 48) || !*v9 )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "PhysicalSize.cx or PhysicalSize.cy is 0. Resetting both to 0";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 389;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_180035373,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 48) = 0;
      *v9 = 0;
    }
  }
  if ( (*((_BYTE *)this + 100) & 4) != 0 && (unsigned int)(*((_DWORD *)this + 44) - 100) > 0x190 )
  {
    if ( (unsigned int)dword_18003C058 > 3 )
    {
      v14 = "DesktopScaleFactor is out of range(100-500). Resetting to 100";
      v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
      LODWORD(v13) = 403;
      v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_18003C058,
        (unsigned int)byte_18003533B,
        a3,
        a4,
        (__int64)&v16,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v14);
    }
    *((_DWORD *)this + 44) = 100;
  }
  if ( *((char *)this + 100) < 0 )
  {
    v10 = (_DWORD *)((char *)this + 316);
    if ( !*((_DWORD *)this + 78) || !*v10 )
    {
      if ( (unsigned int)dword_18003C058 > 3 )
      {
        v14 = "ContainerInfo.VSyncFreq is out of range. Resetting to 32Hz";
        v15 = "Rdp::Stack::Graphics::CMonitorConfig::ValidateAndFixMonitorConfig";
        LODWORD(v13) = 416;
        v16 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_180035303,
          a3,
          a4,
          (__int64)&v16,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v14);
      }
      *((_DWORD *)this + 78) = 32;
      *v10 = 1;
    }
  }
}

```

## disassembly

```asm
0x180017808  mov     r11, rsp
0x18001780b  push    rbp
0x18001780c  push    rbx
0x18001780d  push    rsi
0x18001780e  push    rdi
0x18001780f  push    r12
0x180017811  push    r13
0x180017813  push    r14
0x180017815  mov     rbp, rsp
0x180017818  sub     rsp, 60h
0x18001781c  mov     rdi, rcx
0x18001781f  lea     r12, aRdpStackGraphi_6; "Rdp::Stack::Graphics::CMonitorConfig::V"...
0x180017826  lea     r13, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001782d  lea     rsi, dword_18003C058
0x180017834  xor     r14d, r14d
0x180017837  test    byte ptr [rcx+64h], 2
0x18001783b  jz      loc_180017B6E
0x180017841  mov     ebx, 0C8h
0x180017846  cmp     [rcx+88h], ebx
0x18001784c  jnb     short loc_1800178A8
0x18001784e  mov     eax, cs:dword_18003C058
0x180017854  cmp     eax, 3
0x180017857  jbe     short loc_1800178A2
0x180017859  lea     rax, aResolutionCxIs; "Resolution.cx is less than minimum allo"...
0x180017860  mov     [rbp+arg_8], rax
0x180017864  mov     [rbp+arg_10], r12
0x180017868  mov     dword ptr [rbp+arg_0], 155h
0x18001786f  mov     [rbp+arg_18], r13
0x180017873  lea     rax, [rbp+arg_8]
0x180017877  mov     [r11-60h], rax
0x18001787b  lea     rax, [rbp+arg_10]
0x18001787f  mov     [r11-68h], rax
0x180017883  lea     rax, [rbp+arg_0]
0x180017887  mov     [r11-70h], rax
0x18001788b  lea     rax, [rbp+arg_18]
0x18001788f  mov     [r11-78h], rax
0x180017893  lea     rdx, byte_1800354C3
0x18001789a  mov     rcx, rsi
0x18001789d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800178a2  mov     [rdi+88h], ebx
0x1800178a8  cmp     [rdi+8Ch], ebx
0x1800178ae  jnb     short loc_18001790E
0x1800178b0  mov     eax, cs:dword_18003C058
0x1800178b6  cmp     eax, 3
0x1800178b9  jbe     short loc_180017908
0x1800178bb  lea     rax, aResolutionCyIs; "Resolution.cy is less than minimum allo"...
0x1800178c2  mov     [rbp+arg_8], rax
0x1800178c6  mov     [rbp+arg_10], r12
0x1800178ca  mov     dword ptr [rbp+arg_0], 15Bh
0x1800178d1  mov     [rbp+arg_18], r13
0x1800178d5  lea     rax, [rbp+arg_8]
0x1800178d9  mov     [rsp+60h+var_28], rax
0x1800178de  lea     rax, [rbp+arg_10]
0x1800178e2  mov     [rsp+60h+var_30], rax
0x1800178e7  lea     rax, [rbp+arg_0]
0x1800178eb  mov     [rsp+60h+var_38], rax
0x1800178f0  lea     rax, [rbp+arg_18]
0x1800178f4  mov     [rsp+60h+var_40], rax
0x1800178f9  lea     rdx, byte_18003548B
0x180017900  mov     rcx, rsi
0x180017903  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017908  mov     [rdi+8Ch], ebx
0x18001790e  mov     eax, [rdi+94h]
0x180017914  test    eax, eax
0x180017916  jz      short loc_18001798A
0x180017918  cmp     eax, 5Ah ; 'Z'
0x18001791b  jz      short loc_18001798A
0x18001791d  cmp     eax, 0B4h
0x180017922  jz      short loc_18001798A
0x180017924  cmp     eax, 10Eh
0x180017929  jz      short loc_18001798A
0x18001792b  mov     eax, cs:dword_18003C058
0x180017931  cmp     eax, 3
0x180017934  jbe     short loc_180017983
0x180017936  lea     rax, aOrientationDoe; "Orientation does not have a valid value"...
0x18001793d  mov     [rbp+arg_8], rax
0x180017941  mov     [rbp+arg_10], r12
0x180017945  mov     dword ptr [rbp+arg_0], 164h
0x18001794c  mov     [rbp+arg_18], r13
0x180017950  lea     rax, [rbp+arg_8]
0x180017954  mov     [rsp+60h+var_28], rax
0x180017959  lea     rax, [rbp+arg_10]
0x18001795d  mov     [rsp+60h+var_30], rax
0x180017962  lea     rax, [rbp+arg_0]
0x180017966  mov     [rsp+60h+var_38], rax
0x18001796b  lea     rax, [rbp+arg_18]
0x18001796f  mov     [rsp+60h+var_40], rax
0x180017974  lea     rdx, byte_180035453
0x18001797b  mov     rcx, rsi
0x18001797e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017983  mov     [rdi+94h], r14d
0x18001798a  cmp     [rdi+60h], r14d
0x18001798e  jz      loc_180017A86
0x180017994  mov     eax, cs:dword_18003C058
0x18001799a  cmp     eax, 3
0x18001799d  jbe     loc_180017A71
0x1800179a3  xorps   xmm0, xmm0
0x1800179a6  movdqu  xmmword ptr [rbp+Buffer], xmm0
0x1800179ab  mov     [rbp+var_10], r14
0x1800179af  mov     esi, 800h
0x1800179b4  mov     ecx, esi
0x1800179b6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800179bb  mov     [rbp+Buffer], rax
0x1800179bf  lea     rbx, [rax+800h]
0x1800179c6  mov     [rbp+var_10], rbx
0x1800179ca  mov     r8d, esi; Size
0x1800179cd  xor     edx, edx; Val
0x1800179cf  mov     rcx, rax; void *
0x1800179d2  call    memset_0
0x1800179d7  mov     [rbp+Buffer+8], rbx
0x1800179db  mov     [rbp+arg_0], r14
0x1800179df  lea     rcx, [rbp+arg_0]
0x1800179e3  call    ??1?$_Tidy_guard@V?$vector@DV?$allocator@D@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(void)
0x1800179e8  mov     rdx, [rbp+Buffer+8]
0x1800179ec  mov     rcx, [rbp+Buffer]; Buffer
0x1800179f0  sub     rdx, rcx; BufferCount
0x1800179f3  mov     r9d, [rdi+60h]
0x1800179f7  lea     r8, Format; "Overriding RefreshRate. Resetting to %d"...
0x1800179fe  call    snprintf
0x180017a03  mov     eax, cs:dword_18003C058
0x180017a09  cmp     eax, 3
0x180017a0c  jbe     short loc_180017A61
0x180017a0e  mov     rax, [rbp+Buffer]
0x180017a12  mov     [rbp+arg_8], rax
0x180017a16  mov     [rbp+arg_10], r12
0x180017a1a  mov     dword ptr [rbp+arg_0], 16Ah
0x180017a21  mov     [rbp+arg_18], r13
0x180017a25  lea     rax, [rbp+arg_8]
0x180017a29  mov     [rsp+60h+var_28], rax
0x180017a2e  lea     rax, [rbp+arg_10]
0x180017a32  mov     [rsp+60h+var_30], rax
0x180017a37  lea     rax, [rbp+arg_0]
0x180017a3b  mov     [rsp+60h+var_38], rax
0x180017a40  lea     rax, [rbp+arg_18]
0x180017a44  mov     [rsp+60h+var_40], rax
0x180017a49  lea     rdx, byte_18003541B
0x180017a50  lea     rsi, dword_18003C058
0x180017a57  mov     rcx, rsi
0x180017a5a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017a5f  jmp     short loc_180017A68
0x180017a61  lea     rsi, dword_18003C058
0x180017a68  lea     rcx, [rbp+Buffer]
0x180017a6c  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180017a71  mov     eax, [rdi+60h]
0x180017a74  mov     [rdi+98h], eax
0x180017a7a  mov     dword ptr [rdi+9Ch], 1
0x180017a84  jmp     short loc_180017B03
0x180017a86  lea     rbx, [rdi+9Ch]
0x180017a8d  cmp     [rdi+98h], r14d
0x180017a94  jz      short loc_180017A9B
0x180017a96  cmp     [rbx], r14d
0x180017a99  jnz     short loc_180017B03
0x180017a9b  mov     eax, cs:dword_18003C058
0x180017aa1  cmp     eax, 3
0x180017aa4  jbe     short loc_180017AF3
0x180017aa6  lea     rax, aRefreshrateIsO; "RefreshRate is out of range. Resetting "...
0x180017aad  mov     [rbp+arg_8], rax
0x180017ab1  mov     [rbp+arg_10], r12
0x180017ab5  mov     dword ptr [rbp+arg_0], 171h
0x180017abc  mov     [rbp+arg_18], r13
0x180017ac0  lea     rax, [rbp+arg_8]
0x180017ac4  mov     [rsp+60h+var_28], rax
0x180017ac9  lea     rax, [rbp+arg_10]
0x180017acd  mov     [rsp+60h+var_30], rax
0x180017ad2  lea     rax, [rbp+arg_0]
0x180017ad6  mov     [rsp+60h+var_38], rax
0x180017adb  lea     rax, [rbp+arg_18]
0x180017adf  mov     [rsp+60h+var_40], rax
0x180017ae4  lea     rdx, byte_1800353E3
0x180017aeb  mov     rcx, rsi
0x180017aee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017af3  mov     dword ptr [rdi+98h], 20h ; ' '
0x180017afd  mov     dword ptr [rbx], 1
0x180017b03  cmp     [rdi+0A0h], r14d
0x180017b0a  jnz     short loc_180017B6E
0x180017b0c  mov     eax, cs:dword_18003C058
0x180017b12  cmp     eax, 3
0x180017b15  jbe     short loc_180017B64
0x180017b17  lea     rax, aVsyncfreqdivid; "VSyncFreqDivider is 0. Resetting to 1"
0x180017b1e  mov     [rbp+arg_8], rax
0x180017b22  mov     [rbp+arg_10], r12
0x180017b26  mov     dword ptr [rbp+arg_0], 178h
0x180017b2d  mov     [rbp+arg_18], r13
0x180017b31  lea     rax, [rbp+arg_8]
0x180017b35  mov     [rsp+60h+var_28], rax
0x180017b3a  lea     rax, [rbp+arg_10]
0x180017b3e  mov     [rsp+60h+var_30], rax
0x180017b43  lea     rax, [rbp+arg_0]
0x180017b47  mov     [rsp+60h+var_38], rax
0x180017b4c  lea     rax, [rbp+arg_18]
0x180017b50  mov     [rsp+60h+var_40], rax
0x180017b55  lea     rdx, byte_1800353AB
0x180017b5c  mov     rcx, rsi
0x180017b5f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017b64  mov     dword ptr [rdi+0A0h], 1
0x180017b6e  test    byte ptr [rdi+64h], 8
0x180017b72  jz      short loc_180017BEB
0x180017b74  lea     rbx, [rdi+0C4h]
0x180017b7b  cmp     [rdi+0C0h], r14d
0x180017b82  jz      short loc_180017B89
0x180017b84  cmp     [rbx], r14d
0x180017b87  jnz     short loc_180017BEB
0x180017b89  mov     eax, cs:dword_18003C058
0x180017b8f  cmp     eax, 3
0x180017b92  jbe     short loc_180017BE1
0x180017b94  lea     rax, aPhysicalsizeCx; "PhysicalSize.cx or PhysicalSize.cy is 0"...
0x180017b9b  mov     [rbp+arg_8], rax
0x180017b9f  mov     [rbp+arg_10], r12
0x180017ba3  mov     dword ptr [rbp+arg_0], 185h
0x180017baa  mov     [rbp+arg_18], r13
0x180017bae  lea     rax, [rbp+arg_8]
0x180017bb2  mov     [rsp+60h+var_28], rax
0x180017bb7  lea     rax, [rbp+arg_10]
0x180017bbb  mov     [rsp+60h+var_30], rax
0x180017bc0  lea     rax, [rbp+arg_0]
0x180017bc4  mov     [rsp+60h+var_38], rax
0x180017bc9  lea     rax, [rbp+arg_18]
0x180017bcd  mov     [rsp+60h+var_40], rax
0x180017bd2  lea     rdx, byte_180035373
0x180017bd9  mov     rcx, rsi
0x180017bdc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017be1  mov     [rdi+0C0h], r14d
0x180017be8  mov     [rbx], r14d
0x180017beb  test    byte ptr [rdi+64h], 4
0x180017bef  jz      short loc_180017C63
0x180017bf1  mov     eax, [rdi+0B0h]
0x180017bf7  sub     eax, 64h ; 'd'
0x180017bfa  cmp     eax, 190h
0x180017bff  jbe     short loc_180017C63
0x180017c01  mov     eax, cs:dword_18003C058
0x180017c07  cmp     eax, 3
0x180017c0a  jbe     short loc_180017C59
0x180017c0c  lea     rax, aDesktopscalefa; "DesktopScaleFactor is out of range(100-"...
0x180017c13  mov     [rbp+arg_8], rax
0x180017c17  mov     [rbp+arg_10], r12
0x180017c1b  mov     dword ptr [rbp+arg_0], 193h
0x180017c22  mov     [rbp+arg_18], r13
0x180017c26  lea     rax, [rbp+arg_8]
0x180017c2a  mov     [rsp+60h+var_28], rax
0x180017c2f  lea     rax, [rbp+arg_10]
0x180017c33  mov     [rsp+60h+var_30], rax
0x180017c38  lea     rax, [rbp+arg_0]
0x180017c3c  mov     [rsp+60h+var_38], rax
0x180017c41  lea     rax, [rbp+arg_18]
0x180017c45  mov     [rsp+60h+var_40], rax
0x180017c4a  lea     rdx, byte_18003533B
0x180017c51  mov     rcx, rsi
0x180017c54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017c59  mov     dword ptr [rdi+0B0h], 64h ; 'd'
0x180017c63  test    byte ptr [rdi+64h], 80h
0x180017c67  jz      short loc_180017CE6
0x180017c69  lea     rbx, [rdi+13Ch]
0x180017c70  cmp     [rdi+138h], r14d
0x180017c77  jz      short loc_180017C7E
0x180017c79  cmp     [rbx], r14d
0x180017c7c  jnz     short loc_180017CE6
0x180017c7e  mov     eax, cs:dword_18003C058
0x180017c84  cmp     eax, 3
0x180017c87  jbe     short loc_180017CD6
0x180017c89  lea     rax, aContainerinfoV; "ContainerInfo.VSyncFreq is out of range"...
0x180017c90  mov     [rbp+arg_8], rax
0x180017c94  mov     [rbp+arg_10], r12
0x180017c98  mov     dword ptr [rbp+arg_0], 1A0h
0x180017c9f  mov     [rbp+arg_18], r13
0x180017ca3  lea     rax, [rbp+arg_8]
0x180017ca7  mov     [rsp+60h+var_28], rax
0x180017cac  lea     rax, [rbp+arg_10]
0x180017cb0  mov     [rsp+60h+var_30], rax
0x180017cb5  lea     rax, [rbp+arg_0]
0x180017cb9  mov     [rsp+60h+var_38], rax
0x180017cbe  lea     rax, [rbp+arg_18]
0x180017cc2  mov     [rsp+60h+var_40], rax
0x180017cc7  lea     rdx, byte_180035303
0x180017cce  mov     rcx, rsi
0x180017cd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017cd6  mov     dword ptr [rdi+138h], 20h ; ' '
0x180017ce0  mov     dword ptr [rbx], 1
0x180017ce6  add     rsp, 60h
0x180017cea  pop     r14
0x180017cec  pop     r13
0x180017cee  pop     r12
0x180017cf0  pop     rdi
0x180017cf1  pop     rsi
0x180017cf2  pop     rbx
0x180017cf3  pop     rbp
0x180017cf4  retn
```
