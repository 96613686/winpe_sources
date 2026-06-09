# PAL_System_ThreadGetContext(ulong,void * *)

- ea: `0x140018148`
- end: `0x140018272`
- name: `?PAL_System_ThreadGetContext@@YAJKPEAPEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001e6dc`

## callees

- `0x1400014d4`
- `0x140018148`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14001825a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14001825a`

## string_xrefs

- `0x14001818c`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x14001820e`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x140018173`: `PAL_System_ThreadGetContext`
- `0x1400181f5`: `PAL_System_ThreadGetContext`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetContext(DWORD a1, void **a2, int a3, int a4)
{
  unsigned int v4; // ebx
  char *v5; // rdx
  const char **v6; // rax
  const char **v8; // [rsp+30h] [rbp-30h]
  const char *v9; // [rsp+50h] [rbp-10h] BYREF
  const char *v10; // [rsp+58h] [rbp-8h] BYREF
  int v11; // [rsp+78h] [rbp+18h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  const char *v13; // [rsp+88h] [rbp+28h] BYREF

  if ( a2 )
  {
    if ( g_PAL_SYS_initState != 2 )
    {
      v4 = -2092629815;
      if ( (unsigned int)dword_1400880C8 <= 2 )
        return v4;
      v11 = 1376;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_14007DB4B;
      v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = "System PAL not initialized";
      v8 = &v10;
      v6 = &v9;
      goto LABEL_4;
    }
    if ( !a1 )
      a1 = g_PAL_SYS_threadContextIndex;
    *a2 = TlsGetValue(a1);
    return 0;
  }
  else
  {
    v4 = -2147024809;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v11 = 1370;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_14007DEC9;
      v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v8 = &v9;
      v6 = &v10;
LABEL_4:
      v12 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (_DWORD)v5,
        a3,
        a4,
        (__int64)v6,
        (__int64)&v12,
        (__int64)v8,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140018148  mov     r11, rsp
0x14001814b  mov     [r11+8], rbx
0x14001814f  push    rbp
0x140018150  mov     rbp, rsp
0x140018153  sub     rsp, 60h
0x140018157  mov     rbx, rdx
0x14001815a  test    rdx, rdx
0x14001815d  jnz     short loc_1400181DC
0x14001815f  mov     eax, cs:dword_1400880C8
0x140018165  mov     ebx, 80070057h
0x14001816a  cmp     eax, 2
0x14001816d  jbe     loc_140018265
0x140018173  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x14001817a  mov     [rbp+arg_8], 55Ah
0x140018181  mov     [rbp+arg_18], rax
0x140018185  lea     rdx, byte_14007DEC9
0x14001818c  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140018193  mov     [rbp+var_10], rax
0x140018197  lea     rax, aNullParameterP; "NULL parameter passed"
0x14001819e  mov     [rbp+var_8], rax
0x1400181a2  lea     rax, [rbp+arg_18]
0x1400181a6  mov     [r11-28h], rax
0x1400181aa  lea     rax, [rbp+arg_8]
0x1400181ae  mov     [r11-30h], rax
0x1400181b2  lea     rax, [rbp+var_10]
0x1400181b6  mov     [r11-38h], rax
0x1400181ba  lea     rax, [rbp+arg_10]
0x1400181be  mov     [r11-40h], rax
0x1400181c2  lea     rax, [rbp+var_8]
0x1400181c6  mov     [rsp+60h+var_40], rax
0x1400181cb  mov     [rbp+arg_10], 80004005h
0x1400181d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400181d7  jmp     loc_140018265
0x1400181dc  cmp     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 2; PAL_SYS_STATE g_PAL_SYS_initState
0x1400181e3  jz      short loc_140018251
0x1400181e5  mov     eax, cs:dword_1400880C8
0x1400181eb  mov     ebx, 834500C9h
0x1400181f0  cmp     eax, 2
0x1400181f3  jbe     short loc_140018265
0x1400181f5  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x1400181fc  mov     [rbp+arg_8], 560h
0x140018203  mov     [rbp+arg_18], rax
0x140018207  lea     rdx, byte_14007DB4B
0x14001820e  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140018215  mov     [rbp+var_8], rax
0x140018219  lea     rax, aSystemPalNotIn; "System PAL not initialized"
0x140018220  mov     [rbp+var_10], rax
0x140018224  lea     rax, [rbp+arg_18]
0x140018228  mov     [rsp+60h+var_20], rax
0x14001822d  lea     rax, [rbp+arg_8]
0x140018231  mov     [rsp+60h+var_28], rax
0x140018236  lea     rax, [rbp+var_8]
0x14001823a  mov     [rsp+60h+var_30], rax
0x14001823f  lea     rax, [rbp+arg_10]
0x140018243  mov     [rsp+60h+var_38], rax
0x140018248  lea     rax, [rbp+var_10]
0x14001824c  jmp     loc_1400181C6
0x140018251  test    ecx, ecx
0x140018253  cmovz   ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; dwTlsIndex
0x14001825a  call    cs:__imp_TlsGetValue
0x140018260  mov     [rbx], rax
0x140018263  xor     ebx, ebx
0x140018265  mov     eax, ebx
0x140018267  mov     rbx, [rsp+60h+arg_0]
0x14001826c  add     rsp, 60h
0x140018270  pop     rbp
0x140018271  retn
```
