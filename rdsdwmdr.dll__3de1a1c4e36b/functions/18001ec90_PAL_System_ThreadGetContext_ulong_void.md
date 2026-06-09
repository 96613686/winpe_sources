# PAL_System_ThreadGetContext(ulong,void * *)

- ea: `0x18001ec90`
- end: `0x18001edba`
- name: `?PAL_System_ThreadGetContext@@YAJKPEAPEAX@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002709c`

## callees

- `0x18000160c`
- `0x18001ec90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eda2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eda2`

## string_xrefs

- `0x18001ecd4`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ed56`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ecbb`: `PAL_System_ThreadGetContext`
- `0x18001ed3d`: `PAL_System_ThreadGetContext`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetContext(__int64 a1, void **a2, __int64 a3, __int64 a4)
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
      if ( (unsigned int)dword_180044008 <= 2 )
        return v4;
      v11 = 1376;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_18003ED2D;
      v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = "System PAL not initialized";
      v8 = &v10;
      v6 = &v9;
      goto LABEL_4;
    }
    if ( !(_DWORD)a1 )
      LODWORD(a1) = g_PAL_SYS_threadContextIndex;
    *a2 = TlsGetValue(a1);
    return 0;
  }
  else
  {
    v4 = -2147024809;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v11 = 1370;
      v13 = "PAL_System_ThreadGetContext";
      v5 = byte_18003F0AB;
      v9 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v8 = &v9;
      v6 = &v10;
LABEL_4:
      v12 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (__int64)v5,
        a3,
        a4,
        (const unsigned __int16 **)v6,
        (__int64)&v12,
        (const unsigned __int16 **)v8,
        (__int64)&v11,
        (const unsigned __int16 **)&v13);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001ec90  mov     r11, rsp
0x18001ec93  mov     [r11+8], rbx
0x18001ec97  push    rbp
0x18001ec98  mov     rbp, rsp
0x18001ec9b  sub     rsp, 60h
0x18001ec9f  mov     rbx, rdx
0x18001eca2  test    rdx, rdx
0x18001eca5  jnz     short loc_18001ED24
0x18001eca7  mov     eax, cs:dword_180044008
0x18001ecad  mov     ebx, 80070057h
0x18001ecb2  cmp     eax, 2
0x18001ecb5  jbe     loc_18001EDAD
0x18001ecbb  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x18001ecc2  mov     [rbp+arg_8], 55Ah
0x18001ecc9  mov     [rbp+arg_18], rax
0x18001eccd  lea     rdx, byte_18003F0AB
0x18001ecd4  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ecdb  mov     [rbp+var_10], rax
0x18001ecdf  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001ece6  mov     [rbp+var_8], rax
0x18001ecea  lea     rax, [rbp+arg_18]
0x18001ecee  mov     [r11-28h], rax
0x18001ecf2  lea     rax, [rbp+arg_8]
0x18001ecf6  mov     [r11-30h], rax
0x18001ecfa  lea     rax, [rbp+var_10]
0x18001ecfe  mov     [r11-38h], rax
0x18001ed02  lea     rax, [rbp+arg_10]
0x18001ed06  mov     [r11-40h], rax
0x18001ed0a  lea     rax, [rbp+var_8]
0x18001ed0e  mov     [rsp+60h+var_40], rax
0x18001ed13  mov     [rbp+arg_10], 80004005h
0x18001ed1a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ed1f  jmp     loc_18001EDAD
0x18001ed24  cmp     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 2; PAL_SYS_STATE g_PAL_SYS_initState
0x18001ed2b  jz      short loc_18001ED99
0x18001ed2d  mov     eax, cs:dword_180044008
0x18001ed33  mov     ebx, 834500C9h
0x18001ed38  cmp     eax, 2
0x18001ed3b  jbe     short loc_18001EDAD
0x18001ed3d  lea     rax, aPalSystemThrea; "PAL_System_ThreadGetContext"
0x18001ed44  mov     [rbp+arg_8], 560h
0x18001ed4b  mov     [rbp+arg_18], rax
0x18001ed4f  lea     rdx, byte_18003ED2D
0x18001ed56  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ed5d  mov     [rbp+var_8], rax
0x18001ed61  lea     rax, aSystemPalNotIn; "System PAL not initialized"
0x18001ed68  mov     [rbp+var_10], rax
0x18001ed6c  lea     rax, [rbp+arg_18]
0x18001ed70  mov     [rsp+60h+var_20], rax
0x18001ed75  lea     rax, [rbp+arg_8]
0x18001ed79  mov     [rsp+60h+var_28], rax
0x18001ed7e  lea     rax, [rbp+var_8]
0x18001ed82  mov     [rsp+60h+var_30], rax
0x18001ed87  lea     rax, [rbp+arg_10]
0x18001ed8b  mov     [rsp+60h+var_38], rax
0x18001ed90  lea     rax, [rbp+var_10]
0x18001ed94  jmp     loc_18001ED0E
0x18001ed99  test    ecx, ecx
0x18001ed9b  cmovz   ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; dwTlsIndex
0x18001eda2  call    cs:__imp_TlsGetValue
0x18001eda8  mov     [rbx], rax
0x18001edab  xor     ebx, ebx
0x18001edad  mov     eax, ebx
0x18001edaf  mov     rbx, [rsp+60h+arg_0]
0x18001edb4  add     rsp, 60h
0x18001edb8  pop     rbp
0x18001edb9  retn
```
