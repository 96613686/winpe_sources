# TryGetDiskVolumePath(void *)

- ea: `0x18002a608`
- end: `0x18002a7e4`
- name: `?TryGetDiskVolumePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `476`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028cbc`
- `0x18002a7f0`

## callees

- `0x180001008`
- `0x180002690`
- `0x18000e38c`
- `0x180015a40`
- `0x180015b20`
- `0x1800288b8`
- `0x18002a608`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a6d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a6d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a6e9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002a6e9`

## string_xrefs

- `0x18002a69f`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002a720`: `TryGetDiskVolumePath`

## pseudocode

```c
__int64 __fastcall TryGetDiskVolumePath(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  int v4; // edi
  const struct _tlgProvider_t *v5; // r8
  __int64 v6; // r9
  int v8; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v10[4]; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v11[3]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v12; // [rsp+90h] [rbp-1h]
  int v13; // [rsp+98h] [rbp+7h] BYREF
  LARGE_INTEGER PerformanceCount[2]; // [rsp+A0h] [rbp+Fh] BYREF
  LARGE_INTEGER Frequency[2]; // [rsp+B0h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+C0h] [rbp+2Fh] BYREF
  int v17; // [rsp+C8h] [rbp+37h]
  _QWORD v18[2]; // [rsp+D0h] [rbp+3Fh] BYREF
  _UNKNOWN *retaddr; // [rsp+F0h] [rbp+5Fh]
  __int64 v20; // [rsp+100h] [rbp+6Fh] BYREF

  v20 = a2;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  *(_OWORD *)&Frequency[0].LowPart = 0;
  QueryPerformanceCounter(PerformanceCount);
  v10[3] = a1;
  v16 = 0;
  v17 = 0;
  v13 = 0;
  v10[0] = &v20;
  v10[1] = &v16;
  v10[2] = &v13;
  v11[0] = retaddr;
  v11[1] = "onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp";
  v12 = 168;
  v18[0] = &off_18004A970;
  v18[1] = v10;
  v11[2] = 0;
  v4 = wil::details::ResultFromException(v11, v3, v18);
  QueryPerformanceCounter(&PerformanceCount[1]);
  QueryPerformanceFrequency(Frequency);
  Frequency[1].QuadPart = 1000000
                        * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart)
                        / Frequency[0].QuadPart;
  if ( (unsigned int)VmlIsDebugTraceEnabled(
                       49152,
                       1000000 * (PerformanceCount[1].QuadPart - PerformanceCount[0].QuadPart) % Frequency[0].QuadPart) )
    VmlDebugTrace(49152, L"%s, Time Taken (us) : %llu\n", L"TryGetDiskVolumePath", Frequency[1].QuadPart);
  v5 = ComputeService::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*((_QWORD *)v5 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x200000000000LL) == *((_QWORD *)v5 + 3) )
  {
    v8 = v4;
    v9 = Frequency[1].QuadPart / 0x3E8uLL;
    v18[0] = HIDWORD(v16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)v5,
      (int)&unk_180055700,
      (__int64)v5,
      v6,
      (__int64)&v8,
      (__int64)v18,
      (__int64)&v9);
  }
  return a1;
}

```

## disassembly

```asm
0x18002a608  mov     rax, rsp
0x18002a60b  mov     [rax+18h], rbx
0x18002a60f  mov     [rax+20h], rdi
0x18002a613  mov     [rax+10h], rdx
0x18002a617  push    rbp
0x18002a618  lea     rbp, [rax-5Fh]
0x18002a61c  sub     rsp, 0E0h
0x18002a623  mov     rax, cs:__security_cookie
0x18002a62a  xor     rax, rsp
0x18002a62d  mov     [rbp+57h+var_8], rax
0x18002a631  xorps   xmm0, xmm0
0x18002a634  xor     eax, eax
0x18002a636  movups  xmmword ptr [rcx], xmm0
0x18002a639  mov     qword ptr [rcx+10h], 0
0x18002a641  mov     rbx, rcx
0x18002a644  mov     qword ptr [rcx+18h], 7
0x18002a64c  mov     [rcx], ax
0x18002a64f  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18002a653  movups  xmmword ptr [rbp+57h+PerformanceCount], xmm0
0x18002a657  movups  xmmword ptr [rbp+57h+Frequency], xmm0
0x18002a65b  call    cs:__imp_QueryPerformanceCounter
0x18002a662  nop     dword ptr [rax+rax+00h]
0x18002a667  xor     eax, eax
0x18002a669  mov     [rbp+57h+var_78], rbx
0x18002a66d  mov     [rbp+57h+var_28], rax
0x18002a671  lea     r8, [rbp+57h+var_18]
0x18002a675  mov     [rbp+57h+var_20], eax
0x18002a678  lea     rcx, [rbp+57h+var_70]
0x18002a67c  mov     [rbp+57h+var_50], eax
0x18002a67f  lea     rax, [rbp+57h+arg_8]
0x18002a683  mov     [rbp+57h+var_90], rax
0x18002a687  lea     rax, [rbp+57h+var_28]
0x18002a68b  mov     [rbp+57h+var_88], rax
0x18002a68f  lea     rax, [rbp+57h+var_50]
0x18002a693  mov     [rbp+57h+var_80], rax
0x18002a697  mov     rax, [rbp+5Fh]
0x18002a69b  mov     [rbp+57h+var_70], rax
0x18002a69f  lea     rax, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002a6a6  mov     [rbp+57h+var_68], rax
0x18002a6aa  mov     eax, 0A8h
0x18002a6af  mov     [rbp+57h+var_58], ax
0x18002a6b3  lea     rax, off_18004A970
0x18002a6ba  mov     [rbp+57h+var_18], rax
0x18002a6be  lea     rax, [rbp+57h+var_90]
0x18002a6c2  mov     [rbp+57h+var_10], rax
0x18002a6c6  mov     [rbp+57h+var_60], 0
0x18002a6ce  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x18002a6d3  lea     rcx, [rbp+57h+PerformanceCount+8]; lpPerformanceCount
0x18002a6d7  mov     edi, eax
0x18002a6d9  call    cs:__imp_QueryPerformanceCounter
0x18002a6e0  nop     dword ptr [rax+rax+00h]
0x18002a6e5  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x18002a6e9  call    cs:__imp_QueryPerformanceFrequency
0x18002a6f0  nop     dword ptr [rax+rax+00h]
0x18002a6f5  mov     rax, qword ptr [rbp+57h+PerformanceCount+8]
0x18002a6f9  mov     ecx, 0C000h
0x18002a6fe  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x18002a702  imul    rax, 0F4240h
0x18002a709  cqo
0x18002a70b  idiv    qword ptr [rbp+57h+Frequency]
0x18002a70f  mov     qword ptr [rbp+57h+Frequency+8], rax
0x18002a713  call    VmlIsDebugTraceEnabled
0x18002a718  test    eax, eax
0x18002a71a  jz      short loc_18002A738
0x18002a71c  mov     r9, qword ptr [rbp+57h+Frequency+8]
0x18002a720  lea     r8, aTrygetdiskvolu; "TryGetDiskVolumePath"
0x18002a727  lea     rdx, aSTimeTakenUsLl; "%s, Time Taken (us) : %llu\n"
0x18002a72e  mov     ecx, 0C000h
0x18002a733  call    VmlDebugTrace
0x18002a738  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x18002a73d  mov     r8, rax
0x18002a740  mov     eax, [rax]
0x18002a742  cmp     eax, 5
0x18002a745  jbe     short loc_18002A7BF
0x18002a747  mov     rcx, [r8+18h]
0x18002a74b  mov     rdx, 200000000000h
0x18002a755  mov     rax, [r8+10h]
0x18002a759  test    rdx, rax
0x18002a75c  jz      short loc_18002A7BF
0x18002a75e  mov     rax, rcx
0x18002a761  and     rax, rdx
0x18002a764  cmp     rax, rcx
0x18002a767  jnz     short loc_18002A7BF
0x18002a769  mov     rcx, qword ptr [rbp+57h+Frequency+8]
0x18002a76d  mov     rax, 624DD2F1A9FBE77h
0x18002a777  mul     rcx
0x18002a77a  lea     rax, [rbp+57h+var_98]
0x18002a77e  mov     [rbp+57h+var_A0], edi
0x18002a781  sub     rcx, rdx
0x18002a784  mov     [rsp+0E0h+var_B0], rax
0x18002a789  shr     rcx, 1
0x18002a78c  lea     rax, [rbp+57h+var_18]
0x18002a790  add     rcx, rdx
0x18002a793  mov     [rsp+0E0h+var_B8], rax
0x18002a798  shr     rcx, 9
0x18002a79c  lea     rax, [rbp+57h+var_A0]
0x18002a7a0  mov     [rbp+57h+var_98], rcx
0x18002a7a4  lea     rdx, unk_180055700
0x18002a7ab  mov     ecx, dword ptr [rbp+57h+var_28+4]
0x18002a7ae  mov     [rbp+57h+var_18], rcx
0x18002a7b2  mov     rcx, r8
0x18002a7b5  mov     [rsp+0E0h+var_C0], rax
0x18002a7ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002a7bf  mov     rax, rbx
0x18002a7c2  mov     rcx, [rbp+57h+var_8]
0x18002a7c6  xor     rcx, rsp; StackCookie
0x18002a7c9  call    __security_check_cookie
0x18002a7ce  lea     r11, [rsp+0E0h+var_s0]
0x18002a7d6  mov     rbx, [r11+20h]
0x18002a7da  mov     rdi, [r11+28h]
0x18002a7de  mov     rsp, r11
0x18002a7e1  pop     rbp
0x18002a7e2  retn
```
