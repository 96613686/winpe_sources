# ESIMPM::ControlCellularCost(bool,_GUID const &,_WCM_CONNECTION_COST &)

- ea: `0x140020168`
- end: `0x1400203e3`
- name: `?ControlCellularCost@ESIMPM@@YAK_NAEBU_GUID@@AEAW4_WCM_CONNECTION_COST@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(ESIMPM *this, __int64, const struct _GUID *, enum _WCM_CONNECTION_COST *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140027364`

## callees

- `0x140001278`
- `0x140001308`
- `0x140020168`
- `0x140020620`

## import_xrefs

- `wcmapi!WcmCloseHandle` at `0x14002033f`
- `wcmapi!WcmCloseHandle` at `0x140020388`
- `wcmapi!WcmCloseHandle` at `0x14002033f`
- `wcmapi!WcmCloseHandle` at `0x140020388`
- `wcmapi!WcmQueryProperty` at `0x1400201ef`
- `wcmapi!WcmQueryProperty` at `0x1400201ef`
- `wcmapi!WcmOpenHandle` at `0x1400202ac`
- `wcmapi!WcmOpenHandle` at `0x1400202ac`
- `wcmapi!WcmSetParameter` at `0x1400202fd`
- `wcmapi!WcmSetParameter` at `0x1400202fd`

## string_xrefs

- `0x140020273`: `No need to change cost, as it is already set to %d`

## pseudocode

```c
__int64 __fastcall ESIMPM::ControlCellularCost(
        ESIMPM *this,
        __int64 a2,
        const struct _GUID *a3,
        enum _WCM_CONNECTION_COST *a4)
{
  unsigned int Property; // edi
  int v6; // r8d
  int v7; // r9d
  _QWORD v9[2]; // [rsp+60h] [rbp-10h] BYREF
  const char *v10; // [rsp+B8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_140075078 > 5 )
  {
    v10 = "ESIMPM::ControlCellularCost";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_BYTE)this,
      (unsigned int)byte_14006A183,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v10);
  }
  Property = WcmQueryProperty(a2, 0, 4);
  if ( Property )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      LODWORD(v10) = Property;
      v9[0] = "ESIMPM::ControlCellularCost";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_140075078,
        (unsigned int)&word_14006A13E,
        v6,
        v7,
        (__int64)&v10,
        (__int64)v9);
    }
    return Property;
  }
  else
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v9[0] = "ESIMPM::ControlCellularCost";
      LODWORD(v10) = 1627;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&v10,
        (unsigned int)byte_14006A0EB,
        v6,
        v7,
        (__int64)&v10,
        (__int64)v9);
    }
    return 1627;
  }
}

```

## disassembly

```asm
0x140020168  mov     [rsp-28h+arg_8], rbx
0x14002016d  mov     [rsp-28h+arg_10], rsi
0x140020172  push    rbp
0x140020173  push    rdi
0x140020174  push    r12
0x140020176  push    r14
0x140020178  push    r15
0x14002017a  mov     rbp, rsp
0x14002017d  sub     rsp, 70h
0x140020181  mov     eax, cs:dword_140075078
0x140020187  lea     r12, aEsimpmControlc; "ESIMPM::ControlCellularCost"
0x14002018e  mov     r14, r8
0x140020191  mov     r15, rdx
0x140020194  mov     sil, cl
0x140020197  cmp     eax, 5
0x14002019a  jbe     short loc_1400201B5
0x14002019c  lea     rax, [rbp+arg_18]
0x1400201a0  mov     [rbp+arg_18], r12
0x1400201a4  lea     rdx, byte_14006A183
0x1400201ab  mov     [rsp+70h+var_50], rax
0x1400201b0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400201b5  mov     [rbp+arg_0], 0
0x1400201bc  mov     ebx, 1
0x1400201c1  mov     [rbp+var_20], 0
0x1400201c9  test    sil, sil
0x1400201cc  jnz     short loc_1400201D1
0x1400201ce  mov     ebx, [r14]
0x1400201d1  xor     r9d, r9d
0x1400201d4  lea     rax, [rbp+var_20]
0x1400201d8  mov     [rsp+70h+var_48], rax
0x1400201dd  xor     edx, edx
0x1400201df  lea     rax, [rbp+arg_0]
0x1400201e3  mov     rcx, r15
0x1400201e6  mov     [rsp+70h+var_50], rax
0x1400201eb  lea     r8d, [r9+4]
0x1400201ef  call    cs:__imp_WcmQueryProperty
0x1400201f5  mov     edi, eax
0x1400201f7  test    eax, eax
0x1400201f9  jz      short loc_140020232
0x1400201fb  mov     ecx, cs:dword_140075078
0x140020201  cmp     ecx, 2
0x140020204  jbe     short loc_14002022B
0x140020206  lea     rdx, word_14006A13E
0x14002020d  lea     rax, [rbp+var_10]
0x140020211  mov     dword ptr [rbp+arg_18], edi
0x140020214  mov     [rsp+70h+var_48], rax
0x140020219  lea     rax, [rbp+arg_18]
0x14002021d  mov     [rsp+70h+var_50], rax
0x140020222  mov     [rbp+var_10], r12
0x140020226  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002022b  mov     eax, edi
0x14002022d  jmp     loc_1400203CA
0x140020232  cmp     [rbp+arg_0], 8
0x140020236  jnz     loc_140020393
0x14002023c  mov     rdi, [rbp+var_20]
0x140020240  test    rdi, rdi
0x140020243  jz      loc_140020393
0x140020249  mov     edi, [rdi]
0x14002024b  movzx   edi, di
0x14002024e  test    sil, sil
0x140020251  jz      short loc_14002026A
0x140020253  mov     r9d, edi
0x140020256  lea     r8, aDetectedCurren; "Detected current cellular cost as %d. S"...
0x14002025d  xor     edx, edx; struct _GUID *
0x14002025f  mov     rcx, r12; char *
0x140020262  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140020267  mov     [r14], edi
0x14002026a  xor     edx, edx; struct _GUID *
0x14002026c  cmp     edi, ebx
0x14002026e  jnz     short loc_140020289
0x140020270  mov     r9d, ebx
0x140020273  lea     r8, aNoNeedToChange; "No need to change cost, as it is alread"...
0x14002027a  mov     rcx, r12; char *
0x14002027d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140020282  xor     eax, eax
0x140020284  jmp     loc_1400203CA
0x140020289  mov     ecx, 1
0x14002028e  mov     [rbp+var_18], 0
0x140020296  lea     r9, [rbp+var_28]
0x14002029a  mov     [rbp+var_30], ecx
0x14002029d  lea     r8, [rbp+var_30]
0x1400202a1  mov     [rbp+var_28], 0
0x1400202a9  mov     dword ptr [rbp+var_18], ebx
0x1400202ac  call    cs:__imp_WcmOpenHandle
0x1400202b2  mov     edi, eax
0x1400202b4  test    eax, eax
0x1400202b6  jz      short loc_1400202D3
0x1400202b8  mov     ecx, cs:dword_140075078
0x1400202be  cmp     ecx, 2
0x1400202c1  jbe     loc_14002022B
0x1400202c7  lea     rdx, byte_14006A06B
0x1400202ce  jmp     loc_14002020D
0x1400202d3  mov     rcx, [rbp+var_28]
0x1400202d7  lea     rax, [rbp+var_18]
0x1400202db  mov     [rsp+70h+var_40], rax
0x1400202e0  mov     r9d, 104h
0x1400202e6  mov     dword ptr [rsp+70h+var_48], 8
0x1400202ee  xor     r8d, r8d
0x1400202f1  mov     rdx, r15
0x1400202f4  mov     [rsp+70h+var_50], 0
0x1400202fd  call    cs:__imp_WcmSetParameter
0x140020303  mov     edi, eax
0x140020305  test    eax, eax
0x140020307  jz      short loc_14002034A
0x140020309  mov     ecx, cs:dword_140075078
0x14002030f  cmp     ecx, 2
0x140020312  jbe     short loc_140020339
0x140020314  mov     dword ptr [rbp+arg_18], eax
0x140020317  lea     rdx, byte_14006A02F
0x14002031e  lea     rax, [rbp+var_10]
0x140020322  mov     [rbp+var_10], r12
0x140020326  mov     [rsp+70h+var_48], rax
0x14002032b  lea     rax, [rbp+arg_18]
0x14002032f  mov     [rsp+70h+var_50], rax
0x140020334  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140020339  mov     rcx, [rbp+var_28]
0x14002033d  xor     edx, edx
0x14002033f  call    cs:__imp_WcmCloseHandle
0x140020345  jmp     loc_14002022B
0x14002034a  mov     r9d, ebx
0x14002034d  lea     r8, aSuccessfullySe; "Successfully set connection cost of cel"...
0x140020354  xor     edx, edx; struct _GUID *
0x140020356  mov     rcx, r12; char *
0x140020359  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002035e  mov     eax, cs:dword_140075078
0x140020364  cmp     eax, 5
0x140020367  jbe     short loc_140020382
0x140020369  lea     rax, [rbp+arg_18]
0x14002036d  mov     [rbp+arg_18], r12
0x140020371  lea     rdx, byte_14006A015
0x140020378  mov     [rsp+70h+var_50], rax
0x14002037d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140020382  mov     rcx, [rbp+var_28]
0x140020386  xor     edx, edx
0x140020388  call    cs:__imp_WcmCloseHandle
0x14002038e  jmp     loc_140020282
0x140020393  mov     ecx, cs:dword_140075078
0x140020399  mov     ebx, 65Bh
0x14002039e  cmp     ecx, 2
0x1400203a1  jbe     short loc_1400203C8
0x1400203a3  lea     rcx, [rbp+var_10]
0x1400203a7  mov     [rbp+var_10], r12
0x1400203ab  mov     [rsp+70h+var_48], rcx
0x1400203b0  lea     rdx, byte_14006A0EB
0x1400203b7  lea     rcx, [rbp+arg_18]
0x1400203bb  mov     dword ptr [rbp+arg_18], ebx
0x1400203be  mov     [rsp+70h+var_50], rcx
0x1400203c3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400203c8  mov     eax, ebx
0x1400203ca  lea     r11, [rsp+70h+var_s0]
0x1400203cf  mov     rbx, [r11+38h]
0x1400203d3  mov     rsi, [r11+40h]
0x1400203d7  mov     rsp, r11
0x1400203da  pop     r15
0x1400203dc  pop     r14
0x1400203de  pop     r12
0x1400203e0  pop     rdi
0x1400203e1  pop     rbp
0x1400203e2  retn
```
