# ESIMPM::ControlWiFi(bool)

- ea: `0x1400203ec`
- end: `0x140020618`
- name: `?ControlWiFi@ESIMPM@@YAK_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(ESIMPM *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140027364`

## callees

- `0x140001278`
- `0x140001308`
- `0x140002f60`
- `0x140013df8`
- `0x140014f64`
- `0x14001e75c`
- `0x14001ea94`
- `0x14001fa90`
- `0x1400203ec`
- `0x140020620`
- `0x140022f0c`

## string_xrefs

- `0x140020598`: `Results XML did not match expected. Results XML: %ws, expected XML: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::ControlWiFi(ESIMPM *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  __int64 *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  wchar_t **v13; // rbx
  const wchar_t *v14; // rdx
  wchar_t *v15; // rax
  unsigned __int64 v16; // r9
  const wchar_t *v17; // rcx
  wchar_t *v18; // r10
  unsigned __int64 v19; // r11
  wchar_t **v20; // r9
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  const unsigned __int16 *v25[2]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v26; // [rsp+40h] [rbp-39h] BYREF
  __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-21h]
  wchar_t *S1[2]; // [rsp+60h] [rbp-19h] BYREF
  size_t N; // [rsp+70h] [rbp-9h]
  unsigned __int64 v31; // [rsp+78h] [rbp-1h]
  char *Src[4]; // [rsp+80h] [rbp+7h] BYREF

  v4 = (unsigned __int8)this;
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v25[0] = (const unsigned __int16 *)"ESIMPM::ControlWiFi";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)word_140069FFA,
      a3,
      a4,
      v25);
  }
  v5 = v4;
  ESIMPM::Log::Info("ESIMPM::ControlWiFi", 0, L"Setting AllowWiFi to %d", v4);
  *(_OWORD *)S1 = 0;
  N = 0;
  v31 = 7;
  LOWORD(S1[0]) = 0;
  std::_Format_arg_index::_Format_arg_index((std::_Format_arg_index *)&v27);
  v28 = v4;
  v27 = 0x1000000000000000LL;
  v6 = &qword_140075CA8;
  if ( (unsigned __int64)qword_140075CC0 > 7 )
    v6 = (__int64 *)qword_140075CA8;
  v25[0] = (const unsigned __int16 *)1;
  v25[1] = (const unsigned __int16 *)&v27;
  *(_QWORD *)&v26 = v6;
  *((_QWORD *)&v26 + 1) = qword_140075CB8;
  std::vformat<0>(Src, &v26, (unsigned __int64 *)v25);
  v9 = ESIMPM::ApplySyncml((__int64)Src, (char **)S1, v7, v8);
  v12 = v9;
  if ( v9 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v27 = (__int64)"ESIMPM::ControlWiFi";
      LODWORD(v25[0]) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_140075078,
        (__int64)&word_140069FC6,
        v10,
        v11,
        (__int64)v25,
        (const unsigned __int16 **)&v27);
    }
    goto LABEL_21;
  }
  v13 = &S2;
  v14 = (const wchar_t *)&S2;
  v15 = S2;
  v16 = qword_140075CE0;
  if ( (unsigned __int64)qword_140075CE0 > 7 )
    v14 = S2;
  v17 = (const wchar_t *)S1;
  v18 = S1[0];
  v19 = v31;
  if ( v31 > 7 )
    v17 = S1[0];
  if ( N != qword_140075CD8 )
    goto LABEL_16;
  if ( N && wmemcmp(v17, v14, N) )
  {
    v19 = v31;
    v18 = S1[0];
    v16 = qword_140075CE0;
    v15 = S2;
LABEL_16:
    if ( v16 > 7 )
      v13 = (wchar_t **)v15;
    v20 = S1;
    if ( v19 > 7 )
      v20 = (wchar_t **)v18;
    ESIMPM::Log::Error(
      "ESIMPM::ControlWiFi",
      0,
      L"Results XML did not match expected. Results XML: %ws, expected XML: %ws",
      v20,
      v13);
    v12 = 1627;
    goto LABEL_21;
  }
  ESIMPM::Log::Info("ESIMPM::ControlWiFi", 0, L"Successfully set AllowWifi to %d", v5);
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v27 = (__int64)"ESIMPM::ControlWiFi";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v22,
      (__int64)&dword_140069FAC,
      v23,
      v24,
      (const unsigned __int16 **)&v27);
  }
  v12 = 0;
LABEL_21:
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate((char **)S1);
  return v12;
}

```

## disassembly

```asm
0x1400203ec  push    rbp
0x1400203ee  push    rbx
0x1400203ef  push    rsi
0x1400203f0  push    rdi
0x1400203f1  lea     rbp, [rsp-3Fh]
0x1400203f6  sub     rsp, 0B8h
0x1400203fd  mov     rax, cs:__security_cookie
0x140020404  xor     rax, rsp
0x140020407  mov     [rbp+57h+var_30], rax
0x14002040b  movzx   ebx, cl
0x14002040e  mov     eax, cs:dword_140075078
0x140020414  lea     rsi, aEsimpmControlw; "ESIMPM::ControlWiFi"
0x14002041b  cmp     eax, 5
0x14002041e  jbe     short loc_140020439
0x140020420  mov     [rbp+57h+var_A0], rsi
0x140020424  lea     rax, [rbp+57h+var_A0]
0x140020428  mov     [rsp+0D0h+var_B0], rax
0x14002042d  lea     rdx, word_140069FFA
0x140020434  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140020439  mov     edi, ebx
0x14002043b  mov     r9d, ebx
0x14002043e  lea     r8, aSettingAllowwi; "Setting AllowWiFi to %d"
0x140020445  xor     edx, edx; struct _GUID *
0x140020447  mov     rcx, rsi; char *
0x14002044a  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002044f  xorps   xmm0, xmm0
0x140020452  movups  xmmword ptr [rbp+57h+S1], xmm0
0x140020456  mov     [rbp+57h+N], 0
0x14002045e  mov     [rbp+57h+var_58], 7
0x140020466  xor     eax, eax
0x140020468  mov     word ptr [rbp+57h+S1], ax
0x14002046c  lea     rcx, [rbp+57h+var_80]; this
0x140020470  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x140020475  mov     [rbp+57h+var_78], ebx
0x140020478  mov     rax, 1000000000000000h
0x140020482  mov     [rbp+57h+var_80], rax
0x140020486  lea     rax, qword_140075CA8
0x14002048d  cmp     cs:qword_140075CC0, 7
0x140020495  cmova   rax, cs:qword_140075CA8
0x14002049d  mov     [rbp+57h+var_A0], 1
0x1400204a5  lea     rcx, [rbp+57h+var_80]
0x1400204a9  mov     [rbp+57h+var_98], rcx
0x1400204ad  mov     [rbp+57h+var_90], rax
0x1400204b1  mov     rax, cs:qword_140075CB8
0x1400204b8  mov     [rbp+57h+var_88], rax
0x1400204bc  lea     r8, [rbp+57h+var_A0]
0x1400204c0  lea     rdx, [rbp+57h+var_90]
0x1400204c4  lea     rcx, [rbp+57h+Src]; Src
0x1400204c8  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$basic_string_view@GU?$char_traits@G@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@G@std@@@0@@Z; std::vformat<0>(std::basic_string_view<ushort>,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<ushort>>,ushort>>)
0x1400204cd  nop
0x1400204ce  lea     rdx, [rbp+57h+S1]
0x1400204d2  lea     rcx, [rbp+57h+Src]
0x1400204d6  call    ?ApplySyncml@ESIMPM@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; ESIMPM::ApplySyncml(std::wstring const &,std::wstring &)
0x1400204db  mov     ebx, eax
0x1400204dd  test    eax, eax
0x1400204df  jz      short loc_14002051A
0x1400204e1  mov     ecx, cs:dword_140075078
0x1400204e7  cmp     ecx, 2
0x1400204ea  jbe     loc_1400205AE
0x1400204f0  mov     [rbp+57h+var_80], rsi
0x1400204f4  mov     dword ptr [rbp+57h+var_A0], eax
0x1400204f7  lea     rax, [rbp+57h+var_80]
0x1400204fb  mov     [rsp+0D0h+var_A8], rax
0x140020500  lea     rax, [rbp+57h+var_A0]
0x140020504  mov     [rsp+0D0h+var_B0], rax
0x140020509  lea     rdx, word_140069FC6
0x140020510  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140020515  jmp     loc_1400205AE
0x14002051a  lea     rbx, S2
0x140020521  mov     rdx, rbx
0x140020524  mov     rax, cs:S2
0x14002052b  mov     r9, cs:qword_140075CE0
0x140020532  cmp     r9, 7
0x140020536  cmova   rdx, rax; S2
0x14002053a  mov     r8, [rbp+57h+N]; N
0x14002053e  lea     rcx, [rbp+57h+S1]
0x140020542  mov     r10, [rbp+57h+S1]
0x140020546  mov     r11, [rbp+57h+var_58]
0x14002054a  cmp     r11, 7
0x14002054e  cmova   rcx, r10; S1
0x140020552  cmp     r8, cs:qword_140075CD8
0x140020559  jnz     short loc_14002057F
0x14002055b  test    r8, r8
0x14002055e  jz      short loc_1400205DB
0x140020560  call    wmemcmp
0x140020565  test    eax, eax
0x140020567  jz      short loc_1400205DB
0x140020569  mov     r11, [rbp+57h+var_58]
0x14002056d  mov     r10, [rbp+57h+S1]
0x140020571  mov     r9, cs:qword_140075CE0
0x140020578  mov     rax, cs:S2
0x14002057f  cmp     r9, 7
0x140020583  cmova   rbx, rax
0x140020587  lea     r9, [rbp+57h+S1]
0x14002058b  cmp     r11, 7
0x14002058f  cmova   r9, r10
0x140020593  mov     [rsp+0D0h+var_B0], rbx
0x140020598  lea     r8, aResultsXmlDidN; "Results XML did not match expected. Res"...
0x14002059f  xor     edx, edx; struct _GUID *
0x1400205a1  mov     rcx, rsi; char *
0x1400205a4  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400205a9  mov     ebx, 65Bh
0x1400205ae  lea     rcx, [rbp+57h+Src]
0x1400205b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400205b7  nop
0x1400205b8  lea     rcx, [rbp+57h+S1]
0x1400205bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400205c1  mov     eax, ebx
0x1400205c3  mov     rcx, [rbp+57h+var_30]
0x1400205c7  xor     rcx, rsp; StackCookie
0x1400205ca  call    __security_check_cookie
0x1400205cf  add     rsp, 0B8h
0x1400205d6  pop     rdi
0x1400205d7  pop     rsi
0x1400205d8  pop     rbx
0x1400205d9  pop     rbp
0x1400205da  retn
0x1400205db  mov     r9d, edi
0x1400205de  lea     r8, aSuccessfullySe_0; "Successfully set AllowWifi to %d"
0x1400205e5  xor     edx, edx; struct _GUID *
0x1400205e7  mov     rcx, rsi; char *
0x1400205ea  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x1400205ef  mov     eax, cs:dword_140075078
0x1400205f5  cmp     eax, 5
0x1400205f8  jbe     short loc_140020613
0x1400205fa  mov     [rbp+57h+var_80], rsi
0x1400205fe  lea     rax, [rbp+57h+var_80]
0x140020602  mov     [rsp+0D0h+var_B0], rax
0x140020607  lea     rdx, dword_140069FAC
0x14002060e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140020613  xor     ebx, ebx
0x140020615  jmp     short loc_1400205AE
```
