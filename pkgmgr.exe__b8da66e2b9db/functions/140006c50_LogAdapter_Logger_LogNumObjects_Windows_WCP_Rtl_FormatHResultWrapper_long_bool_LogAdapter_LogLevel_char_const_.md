# LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)

- ea: `0x140006c50`
- end: `0x140006de1`
- name: `??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `49`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007524`
- `0x1400089c0`
- `0x140008de8`
- `0x14000903c`
- `0x1400092fc`
- `0x1400097d4`
- `0x1400098b8`
- `0x140009f08`
- `0x14000a1dc`
- `0x14000aae0`
- `0x14000aca8`
- `0x14000b454`
- `0x14000baa4`
- `0x14000bc74`
- `0x14000bdbc`
- `0x14000bf34`
- `0x14000c080`
- `0x14000c384`
- `0x14000ca60`
- `0x14000ccac`
- `0x14000d410`
- `0x14000d9d0`
- `0x140010b3c`
- `0x140010d34`
- `0x140011100`
- `0x1400113d4`
- `0x14001154c`
- `0x140011884`
- `0x140011a4c`
- `0x140011d50`
- `0x140011e8c`
- `0x14001263c`
- `0x140012b88`
- `0x140013288`
- `0x140015a08`
- `0x140016328`
- `0x1400165f8`
- `0x140016ac4`
- `0x140016bc8`
- `0x140016dc8`
- `0x1400170c0`
- `0x140017390`
- `0x140017568`
- `0x140017b80`
- `0x140017eb4`
- `0x140018394`
- `0x1400237c0`
- `0x140023880`
- `0x1400243e8`

## callees

- `0x140002360`
- `0x140006c50`
- `0x140006e70`
- `0x1400070ec`
- `0x1400071c8`
- `0x1400074c0`
- `0x1400074ec`
- `0x14002a010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v13; // [rsp+28h] [rbp-31h] BYREF
  char v14; // [rsp+30h] [rbp-29h]
  _QWORD v15[4]; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v16[5]; // [rsp+58h] [rbp-1h] BYREF
  int v17; // [rsp+80h] [rbp+27h] BYREF

  v16[4] = -2;
  v17 = 0;
  v13 = a1 + 4160;
  v14 = 0;
  v8 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  if ( v8 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v9 >= 0 )
    {
      *(_DWORD *)(a1 + 4152) = a3;
      if ( *(_QWORD *)(a1 + 32) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 224LL))(*(_QWORD *)(a1 + 16), a1 + 40);
        *(_BYTE *)(a1 + 40) = 0;
        *(_QWORD *)(a1 + 32) = 0;
      }
      Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(*(_QWORD *)(a1 + 16), a4, a5);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
      v11 = *(unsigned int *)(a1 + 4156);
      if ( (int)v11 >= 0 )
      {
        v10 = 0;
        goto LABEL_10;
      }
      v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
      v16[1] = "LogAdapter::Logger::LogNumObjects";
      v16[2] = 215;
      v16[3] = "m_FlushSink.Hr()";
      v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v17,
             v16,
             v11);
    }
  }
  else
  {
    v15[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v15[1] = "LogAdapter::Logger::LogNumObjects";
    v15[2] = 195;
    v15[3] = "QueueLock.Acquire()";
    v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
           &v17,
           v15,
           (unsigned int)v8);
  }
  v10 = v9;
LABEL_10:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  return v10;
}

```

## disassembly

```asm
0x140006c50  mov     rax, rsp
0x140006c53  push    rbp
0x140006c54  push    rdi
0x140006c55  push    r14
0x140006c57  lea     rbp, [rax-57h]
0x140006c5b  sub     rsp, 90h
0x140006c62  mov     [rbp+4Fh+var_30], 0FFFFFFFFFFFFFFFEh
0x140006c6a  mov     [rax+10h], rbx
0x140006c6e  mov     [rax+18h], rsi
0x140006c72  mov     rax, cs:__security_cookie
0x140006c79  xor     rax, rsp
0x140006c7c  mov     [rbp+4Fh+var_20], rax
0x140006c80  mov     rsi, r9
0x140006c83  mov     ebx, r8d
0x140006c86  mov     rdi, rcx
0x140006c89  mov     r14, [rbp+4Fh+arg_20]
0x140006c8d  mov     [rbp+4Fh+var_28], 0
0x140006c94  lea     rax, [rcx+1040h]
0x140006c9b  mov     [rbp+4Fh+var_80], rax
0x140006c9f  mov     [rbp+4Fh+var_78], 0
0x140006ca3  lea     rcx, [rbp+4Fh+var_80]; this
0x140006ca7  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140006cac  test    eax, eax
0x140006cae  jns     short loc_140006CEB
0x140006cb0  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140006cb7  mov     [rbp+4Fh+var_70], rcx
0x140006cbb  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x140006cc2  mov     [rbp+4Fh+var_68], rcx
0x140006cc6  mov     [rbp+4Fh+var_60], 0C3h
0x140006cce  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140006cd5  mov     [rbp+4Fh+var_58], rcx
0x140006cd9  mov     r8d, eax
0x140006cdc  lea     rdx, [rbp+4Fh+var_70]
0x140006ce0  lea     rcx, [rbp+4Fh+var_28]
0x140006ce4  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006ce9  jmp     short loc_140006CFD
0x140006ceb  mov     rax, [rdi]
0x140006cee  mov     rcx, rdi
0x140006cf1  mov     rax, [rax]
0x140006cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cf9  test    eax, eax
0x140006cfb  jns     short loc_140006D04
0x140006cfd  mov     ebx, eax
0x140006cff  jmp     loc_140006DB2
0x140006d04  mov     [rdi+1038h], ebx
0x140006d0a  cmp     qword ptr [rdi+20h], 0
0x140006d0f  jbe     short loc_140006D47
0x140006d11  mov     rcx, [rdi+8]
0x140006d15  mov     rax, [rcx]
0x140006d18  mov     rax, [rax+1F0h]
0x140006d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d24  mov     rcx, [rdi+10h]
0x140006d28  mov     rax, [rcx]
0x140006d2b  lea     rdx, [rdi+28h]
0x140006d2f  mov     rax, [rax+0E0h]
0x140006d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d3b  mov     byte ptr [rdi+28h], 0
0x140006d3f  mov     qword ptr [rdi+20h], 0
0x140006d47  mov     r8, r14
0x140006d4a  mov     rdx, rsi
0x140006d4d  mov     rcx, [rdi+10h]
0x140006d51  call    ??$RtlFormatIntoStream@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBU?$FormatHResultWrapper@J@3WCP@1@@Z; Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140006d56  mov     rcx, [rdi+10h]
0x140006d5a  mov     rax, [rcx]
0x140006d5d  mov     rax, [rax+1F0h]
0x140006d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d69  mov     r8d, [rdi+103Ch]
0x140006d70  test    r8d, r8d
0x140006d73  jns     short loc_140006DB0
0x140006d75  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140006d7c  mov     [rbp+4Fh+var_50], rcx
0x140006d80  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x140006d87  mov     [rbp+4Fh+var_48], rcx
0x140006d8b  mov     [rbp+4Fh+var_40], 0D7h
0x140006d93  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x140006d9a  mov     [rbp+4Fh+var_38], rax
0x140006d9e  lea     rdx, [rbp+4Fh+var_50]
0x140006da2  lea     rcx, [rbp+4Fh+var_28]
0x140006da6  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006dab  jmp     loc_140006CFD
0x140006db0  xor     ebx, ebx
0x140006db2  lea     rcx, [rbp+4Fh+var_80]; this
0x140006db6  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140006dbb  mov     eax, ebx
0x140006dbd  mov     rcx, [rbp+4Fh+var_20]
0x140006dc1  xor     rcx, rsp; StackCookie
0x140006dc4  call    __security_check_cookie
0x140006dc9  lea     r11, [rsp+0A0h+var_10]
0x140006dd1  mov     rbx, [r11+28h]
0x140006dd5  mov     rsi, [r11+30h]
0x140006dd9  mov     rsp, r11
0x140006ddc  pop     r14
0x140006dde  pop     rdi
0x140006ddf  pop     rbp
0x140006de0  retn
```
