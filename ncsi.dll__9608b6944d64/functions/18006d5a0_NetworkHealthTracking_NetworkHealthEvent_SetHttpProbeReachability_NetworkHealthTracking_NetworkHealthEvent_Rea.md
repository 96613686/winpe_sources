# NetworkHealthTracking::NetworkHealthEvent::SetHttpProbeReachability(NetworkHealthTracking::NetworkHealthEvent::Reachability,ushort,ulong)

- ea: `0x18006d5a0`
- end: `0x18006d6a9`
- name: `?SetHttpProbeReachability@NetworkHealthEvent@NetworkHealthTracking@@QEAAXW4Reachability@12@GK@Z`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002ea80`
- `0x180042764`

## callees

- `0x18000787c`
- `0x18001d110`
- `0x180047240`
- `0x18006d5a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d5f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d5f2`

## pseudocode

```c
__int64 __fastcall NetworkHealthTracking::NetworkHealthEvent::SetHttpProbeReachability(
        __int64 *a1,
        int a2,
        __int16 a3,
        DWORD a4)
{
  struct _TP_TIMER *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 result; // rax
  bool v11; // zf
  bool v12; // [rsp+60h] [rbp-20h] BYREF
  bool v13; // [rsp+61h] [rbp-1Fh] BYREF
  bool v14; // [rsp+62h] [rbp-1Eh] BYREF
  bool v15; // [rsp+63h] [rbp-1Dh] BYREF
  bool v16[4]; // [rsp+64h] [rbp-1Ch] BYREF
  __int64 v17; // [rsp+68h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp-10h] BYREF

  if ( a3 == 2 )
    *((_DWORD *)a1 + 15) = a2;
  else
    *((_DWORD *)a1 + 16) = a2;
  if ( !a2 )
  {
    v6 = (struct _TP_TIMER *)a1[3];
    pftDueTime = 0;
    SetThreadpoolTimer(v6, &pftDueTime, 0, 0);
  }
  NetworkHealthTracking::NetworkHealthEvent::UpdateWcm((NetworkHealthTracking::NetworkHealthEvent *)a1);
  result = (unsigned int)dword_18009A048;
  if ( (unsigned int)dword_18009A048 > 5 )
  {
    v11 = *((_DWORD *)a1 + 16) == 0;
    v17 = *a1;
    v12 = v11;
    v13 = *((_DWORD *)a1 + 15) == 0;
    v14 = *((_DWORD *)a1 + 14) == 0;
    v15 = *((_DWORD *)a1 + 13) == 0;
    v11 = *((_DWORD *)a1 + 12) == 0;
    pftDueTime.dwLowDateTime = a4;
    v16[0] = v11;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
             v7,
             (int)&word_18008D3D6,
             v8,
             v9,
             (__int64)&v17,
             (__int64)v16,
             (__int64)&v15,
             (__int64)&v14,
             (__int64)&v13,
             (__int64)&v12,
             (__int64)&pftDueTime);
  }
  return result;
}

```

## disassembly

```asm
0x18006d5a0  mov     [rsp-8+arg_8], rbx
0x18006d5a5  mov     [rsp-8+arg_10], rdi
0x18006d5aa  push    rbp
0x18006d5ab  mov     rbp, rsp
0x18006d5ae  sub     rsp, 80h
0x18006d5b5  mov     rax, cs:__security_cookie
0x18006d5bc  xor     rax, rsp
0x18006d5bf  mov     [rbp+var_8], rax
0x18006d5c3  mov     edi, r9d
0x18006d5c6  mov     rbx, rcx
0x18006d5c9  cmp     r8w, 2
0x18006d5ce  jnz     short loc_18006D5D5
0x18006d5d0  mov     [rcx+3Ch], edx
0x18006d5d3  jmp     short loc_18006D5D8
0x18006d5d5  mov     [rcx+40h], edx
0x18006d5d8  test    edx, edx
0x18006d5da  jnz     short loc_18006D5F8
0x18006d5dc  mov     rcx, [rcx+18h]; pti
0x18006d5e0  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18006d5e4  xor     r9d, r9d; msWindowLength
0x18006d5e7  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x18006d5ef  xor     r8d, r8d; msPeriod
0x18006d5f2  call    cs:__imp_SetThreadpoolTimer
0x18006d5f8  mov     rcx, rbx; this
0x18006d5fb  call    ?UpdateWcm@NetworkHealthEvent@NetworkHealthTracking@@AEBAXXZ; NetworkHealthTracking::NetworkHealthEvent::UpdateWcm(void)
0x18006d600  mov     eax, cs:dword_18009A048
0x18006d606  cmp     eax, 5
0x18006d609  jbe     short loc_18006D688
0x18006d60b  cmp     dword ptr [rbx+40h], 0
0x18006d60f  lea     rdx, word_18008D3D6
0x18006d616  mov     rax, [rbx]
0x18006d619  mov     [rbp+var_18], rax
0x18006d61d  setz    [rbp+var_20]
0x18006d621  cmp     dword ptr [rbx+3Ch], 0
0x18006d625  lea     rax, [rbp+pftDueTime]
0x18006d629  mov     [rsp+80h+var_30], rax
0x18006d62e  lea     rax, [rbp+var_20]
0x18006d632  mov     [rsp+80h+var_38], rax
0x18006d637  setz    [rbp+var_1F]
0x18006d63b  cmp     dword ptr [rbx+38h], 0
0x18006d63f  lea     rax, [rbp+var_1F]
0x18006d643  mov     [rsp+80h+var_40], rax
0x18006d648  lea     rax, [rbp+var_1E]
0x18006d64c  mov     [rsp+80h+var_48], rax
0x18006d651  setz    [rbp+var_1E]
0x18006d655  cmp     dword ptr [rbx+34h], 0
0x18006d659  lea     rax, [rbp+var_1D]
0x18006d65d  mov     [rsp+80h+var_50], rax
0x18006d662  lea     rax, [rbp+var_1C]
0x18006d666  mov     [rsp+80h+var_58], rax
0x18006d66b  setz    [rbp+var_1D]
0x18006d66f  cmp     dword ptr [rbx+30h], 0
0x18006d673  lea     rax, [rbp+var_18]
0x18006d677  mov     [rsp+80h+var_60], rax
0x18006d67c  mov     [rbp+pftDueTime.dwLowDateTime], edi
0x18006d67f  setz    [rbp+var_1C]
0x18006d683  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@4444AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18006d688  mov     rcx, [rbp+var_8]
0x18006d68c  xor     rcx, rsp; StackCookie
0x18006d68f  call    __security_check_cookie
0x18006d694  lea     r11, [rsp+80h+var_s0]
0x18006d69c  mov     rbx, [r11+18h]
0x18006d6a0  mov     rdi, [r11+20h]
0x18006d6a4  mov     rsp, r11
0x18006d6a7  pop     rbp
0x18006d6a8  retn
```
