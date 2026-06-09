# ShowNotification(_DUSM_MEDIA_TYPE,_DUSM_DPU_STATE,int,int,_FILETIME const &,int)

- ea: `0x18003edd0`
- end: `0x18003f0b2`
- name: `?ShowNotification@@YAXW4_DUSM_MEDIA_TYPE@@W4_DUSM_DPU_STATE@@HHAEBU_FILETIME@@H@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003e258`

## callees

- `0x180001294`
- `0x180007320`
- `0x180007424`
- `0x180007c90`
- `0x180013444`
- `0x1800173ac`
- `0x18001742c`
- `0x18003edd0`
- `0x18003f0b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003eeb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ef13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003eeb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ef13`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003eec6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003ef20`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003eec6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003ef20`

## pseudocode

```c
void __fastcall ShowNotification(unsigned int a1, unsigned int a2, int a3, int a4, __int64 *a5, int a6)
{
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 *v15; // rbx
  __int64 *v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _DWORD *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // [rsp+60h] [rbp-39h] BYREF
  __int64 v24; // [rsp+68h] [rbp-31h] BYREF
  __int64 v25; // [rsp+70h] [rbp-29h] BYREF
  __int64 v26; // [rsp+78h] [rbp-21h] BYREF
  __int64 v27; // [rsp+80h] [rbp-19h] BYREF
  FILETIME v28; // [rsp+88h] [rbp-11h] BYREF
  __int64 v29; // [rsp+90h] [rbp-9h] BYREF
  __int64 v30; // [rsp+98h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp+7h] BYREF

  if ( a4 && !a6 )
  {
    v10 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v10 > 5u )
    {
      LODWORD(v23) = 0;
      LODWORD(v24) = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)v10,
        (int)byte_18005BF7B,
        v11,
        v12,
        (__int64)&v24,
        (__int64)&v23);
    }
    return;
  }
  v13 = a1 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 != 1 )
        return;
      v15 = &qword_180068F70;
      if ( a4 )
        v15 = (__int64 *)&FileTime2;
      v16 = &qword_180068F78;
      if ( a4 )
        v16 = (__int64 *)&stru_180068F68;
    }
    else
    {
      v15 = &qword_180068F50;
      v16 = &qword_180068F58;
    }
  }
  else
  {
    v15 = &qword_180068F40;
    v16 = &qword_180068F48;
  }
  SystemTimeAsFileTime = 0;
  if ( a2 == 1 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)v15) <= 0 )
      return;
    *v15 = *a5;
    v17 = 0;
    switch ( a1 )
    {
      case 1u:
        v17 = 7;
        break;
      case 2u:
        v17 = 5;
        break;
      case 3u:
        v17 = 2;
        break;
    }
  }
  else
  {
    if ( !a3 )
      return;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)v16) <= 0 )
      return;
    *v16 = *a5;
    if ( a1 == 1 )
    {
      v17 = 6;
    }
    else if ( a1 == 2 )
    {
      v17 = 4;
    }
    else
    {
      v17 = a1 == 3;
    }
  }
  TriggerToast(v17);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
  {
    v25 = (__int64)SystemTimeAsFileTime;
    LODWORD(v24) = a4;
    LODWORD(v23) = a3;
    v26 = DusmDpuStateToSz(a2);
    v27 = DusmMediaTypeToSz(a1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v18,
      (int)&dword_18005BFC4,
      v18,
      v19,
      (const WCHAR **)&v27,
      (const WCHAR **)&v26,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25);
  }
  v20 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v20 > 5u )
  {
    v27 = qword_180068F48;
    v26 = qword_180068F40;
    v25 = qword_180068F58;
    v24 = qword_180068F50;
    v23 = (__int64)stru_180068F68;
    v28 = FileTime2;
    v29 = qword_180068F78;
    v30 = qword_180068F70;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)v20,
      (int)byte_18005BE0B,
      v21,
      v22,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v26,
      (__int64)&v27);
  }
}

```

## disassembly

```asm
0x18003edd0  push    rbp
0x18003edd2  push    rbx
0x18003edd3  push    rsi
0x18003edd4  push    rdi
0x18003edd5  push    r12
0x18003edd7  push    r14
0x18003edd9  push    r15
0x18003eddb  lea     rbp, [rsp-17h]
0x18003ede0  sub     rsp, 0B0h
0x18003ede7  mov     rax, cs:__security_cookie
0x18003edee  xor     rax, rsp
0x18003edf1  mov     [rbp+47h+var_38], rax
0x18003edf5  mov     r14d, r9d
0x18003edf8  mov     r15d, r8d
0x18003edfb  mov     r12d, edx
0x18003edfe  mov     edi, ecx
0x18003ee00  test    r9d, r9d
0x18003ee03  jz      short loc_18003EE4D
0x18003ee05  cmp     [rbp+47h+arg_28], 0
0x18003ee09  jnz     short loc_18003EE4D
0x18003ee0b  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003ee10  mov     rcx, [rax+8]
0x18003ee14  mov     eax, [rcx]
0x18003ee16  cmp     eax, 5
0x18003ee19  jbe     loc_18003F094
0x18003ee1f  lea     rax, [rbp+47h+var_80]
0x18003ee23  mov     dword ptr [rbp+47h+var_80], 0
0x18003ee2a  mov     [rsp+0E0h+var_B8], rax
0x18003ee2f  lea     rdx, byte_18005BF7B
0x18003ee36  lea     rax, [rbp+47h+var_78]
0x18003ee3a  mov     dword ptr [rbp+47h+var_78], r14d
0x18003ee3e  mov     [rsp+0E0h+var_C0], rax
0x18003ee43  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ee48  jmp     loc_18003F094
0x18003ee4d  sub     ecx, 1
0x18003ee50  jz      short loc_18003EE99
0x18003ee52  sub     ecx, 1
0x18003ee55  jz      short loc_18003EE89
0x18003ee57  cmp     ecx, 1
0x18003ee5a  jnz     loc_18003F094
0x18003ee60  test    r14d, r14d
0x18003ee63  lea     rax, FileTime2
0x18003ee6a  lea     rbx, qword_180068F70
0x18003ee71  cmovnz  rbx, rax
0x18003ee75  lea     rsi, qword_180068F78
0x18003ee7c  lea     rax, stru_180068F68
0x18003ee83  cmovnz  rsi, rax
0x18003ee87  jmp     short loc_18003EEA7
0x18003ee89  lea     rbx, qword_180068F50
0x18003ee90  lea     rsi, qword_180068F58
0x18003ee97  jmp     short loc_18003EEA7
0x18003ee99  lea     rbx, qword_180068F40
0x18003eea0  lea     rsi, qword_180068F48
0x18003eea7  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003eeaf  cmp     r12d, 1
0x18003eeb3  jnz     short loc_18003EF06
0x18003eeb5  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003eeb9  call    cs:__imp_GetSystemTimeAsFileTime
0x18003eebf  mov     rdx, rbx; lpFileTime2
0x18003eec2  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x18003eec6  call    cs:__imp_CompareFileTime
0x18003eecc  test    eax, eax
0x18003eece  jle     loc_18003F094
0x18003eed4  mov     rax, [rbp+47h+arg_20]
0x18003eed8  mov     edx, edi
0x18003eeda  mov     rcx, [rax]
0x18003eedd  mov     [rbx], rcx
0x18003eee0  xor     ecx, ecx
0x18003eee2  sub     edx, r12d
0x18003eee5  jz      short loc_18003EEFF
0x18003eee7  sub     edx, r12d
0x18003eeea  jz      short loc_18003EEF8
0x18003eeec  cmp     edx, r12d
0x18003eeef  jnz     short loc_18003EF5B
0x18003eef1  lea     ecx, [r12+1]
0x18003eef6  jmp     short loc_18003EF5B
0x18003eef8  mov     ecx, 5
0x18003eefd  jmp     short loc_18003EF5B
0x18003eeff  mov     ecx, 7
0x18003ef04  jmp     short loc_18003EF5B
0x18003ef06  test    r15d, r15d
0x18003ef09  jz      loc_18003F094
0x18003ef0f  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003ef13  call    cs:__imp_GetSystemTimeAsFileTime
0x18003ef19  mov     rdx, rsi; lpFileTime2
0x18003ef1c  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x18003ef20  call    cs:__imp_CompareFileTime
0x18003ef26  test    eax, eax
0x18003ef28  jle     loc_18003F094
0x18003ef2e  mov     rax, [rbp+47h+arg_20]
0x18003ef32  mov     edx, edi
0x18003ef34  mov     rcx, [rax]
0x18003ef37  mov     [rsi], rcx
0x18003ef3a  xor     ecx, ecx
0x18003ef3c  sub     edx, 1
0x18003ef3f  jz      short loc_18003EF56
0x18003ef41  sub     edx, 1
0x18003ef44  jz      short loc_18003EF4F
0x18003ef46  cmp     edx, 1
0x18003ef49  jnz     short loc_18003EF5B
0x18003ef4b  mov     ecx, edx
0x18003ef4d  jmp     short loc_18003EF5B
0x18003ef4f  mov     ecx, 4
0x18003ef54  jmp     short loc_18003EF5B
0x18003ef56  mov     ecx, 6
0x18003ef5b  call    ?TriggerToast@@YAXW4TOAST_MESSAGE@@@Z; TriggerToast(TOAST_MESSAGE)
0x18003ef60  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003ef65  mov     r8, [rax+8]
0x18003ef69  mov     eax, [r8]
0x18003ef6c  cmp     eax, 5
0x18003ef6f  jbe     short loc_18003EFD4
0x18003ef71  mov     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x18003ef75  mov     ecx, r12d
0x18003ef78  mov     [rbp+47h+var_70], rax
0x18003ef7c  mov     dword ptr [rbp+47h+var_78], r14d
0x18003ef80  mov     dword ptr [rbp+47h+var_80], r15d
0x18003ef84  call    ?DusmDpuStateToSz@@YAPEB_WW4_DUSM_DPU_STATE@@@Z; DusmDpuStateToSz(_DUSM_DPU_STATE)
0x18003ef89  mov     ecx, edi
0x18003ef8b  mov     [rbp+47h+var_68], rax
0x18003ef8f  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18003ef94  mov     [rbp+47h+var_60], rax
0x18003ef98  lea     rdx, dword_18005BFC4; int
0x18003ef9f  lea     rax, [rbp+47h+var_70]
0x18003efa3  mov     rcx, r8; int
0x18003efa6  mov     [rsp+0E0h+var_A0], rax; __int64
0x18003efab  lea     rax, [rbp+47h+var_78]
0x18003efaf  mov     [rsp+0E0h+var_A8], rax; __int64
0x18003efb4  lea     rax, [rbp+47h+var_80]
0x18003efb8  mov     [rsp+0E0h+var_B0], rax; __int64
0x18003efbd  lea     rax, [rbp+47h+var_68]
0x18003efc1  mov     [rsp+0E0h+var_B8], rax; __int64
0x18003efc6  lea     rax, [rbp+47h+var_60]
0x18003efca  mov     [rsp+0E0h+var_C0], rax; __int64
0x18003efcf  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003efd4  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003efd9  mov     rcx, [rax+8]
0x18003efdd  mov     eax, [rcx]
0x18003efdf  cmp     eax, 5
0x18003efe2  jbe     loc_18003F094
0x18003efe8  mov     rax, cs:qword_180068F48
0x18003efef  lea     rdx, byte_18005BE0B
0x18003eff6  mov     [rbp+47h+var_60], rax
0x18003effa  mov     rax, cs:qword_180068F40
0x18003f001  mov     [rbp+47h+var_68], rax
0x18003f005  mov     rax, cs:qword_180068F58
0x18003f00c  mov     [rbp+47h+var_70], rax
0x18003f010  mov     rax, cs:qword_180068F50
0x18003f017  mov     [rbp+47h+var_78], rax
0x18003f01b  mov     rax, qword ptr cs:stru_180068F68.dwLowDateTime
0x18003f022  mov     [rbp+47h+var_80], rax
0x18003f026  mov     rax, qword ptr cs:FileTime2.dwLowDateTime
0x18003f02d  mov     [rbp+47h+var_58], rax
0x18003f031  mov     rax, cs:qword_180068F78
0x18003f038  mov     [rbp+47h+var_50], rax
0x18003f03c  mov     rax, cs:qword_180068F70
0x18003f043  mov     [rbp+47h+var_48], rax
0x18003f047  lea     rax, [rbp+47h+var_60]
0x18003f04b  mov     [rsp+0E0h+var_88], rax
0x18003f050  lea     rax, [rbp+47h+var_68]
0x18003f054  mov     [rsp+0E0h+var_90], rax
0x18003f059  lea     rax, [rbp+47h+var_70]
0x18003f05d  mov     [rsp+0E0h+var_98], rax
0x18003f062  lea     rax, [rbp+47h+var_78]
0x18003f066  mov     [rsp+0E0h+var_A0], rax
0x18003f06b  lea     rax, [rbp+47h+var_80]
0x18003f06f  mov     [rsp+0E0h+var_A8], rax
0x18003f074  lea     rax, [rbp+47h+var_58]
0x18003f078  mov     [rsp+0E0h+var_B0], rax
0x18003f07d  lea     rax, [rbp+47h+var_50]
0x18003f081  mov     [rsp+0E0h+var_B8], rax
0x18003f086  lea     rax, [rbp+47h+var_48]
0x18003f08a  mov     [rsp+0E0h+var_C0], rax
0x18003f08f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18003f094  mov     rcx, [rbp+47h+var_38]
0x18003f098  xor     rcx, rsp; StackCookie
0x18003f09b  call    __security_check_cookie
0x18003f0a0  add     rsp, 0B0h
0x18003f0a7  pop     r15
0x18003f0a9  pop     r14
0x18003f0ab  pop     r12
0x18003f0ad  pop     rdi
0x18003f0ae  pop     rsi
0x18003f0af  pop     rbx
0x18003f0b0  pop     rbp
0x18003f0b1  retn
```
