# LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)

- ea: `0x1400067bc`
- end: `0x14000697b`
- name: `??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z`
- size: `447`
- prototype: `__int64 __fastcall(__int64, char, int, struct Windows::Rtl::IRtlFormattedOutputStream *)`
- caller_count: `46`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007524`
- `0x1400089c0`
- `0x140008de8`
- `0x14000903c`
- `0x1400092fc`
- `0x1400098b8`
- `0x140009f08`
- `0x14000a1dc`
- `0x14000aab4`
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
- `0x140012b88`
- `0x140013288`
- `0x140015a08`
- `0x140016328`
- `0x1400165f8`
- `0x140016bc8`
- `0x140016dc8`
- `0x1400170c0`
- `0x140017390`
- `0x140017568`
- `0x140017b80`
- `0x140017eb4`
- `0x1400237c0`
- `0x140023880`
- `0x1400243e8`

## callees

- `0x140002360`
- `0x1400067bc`
- `0x1400070ec`
- `0x1400071c8`
- `0x1400074c0`
- `0x1400074ec`
- `0x140027cd8`
- `0x14002a010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<>(
        __int64 a1,
        char a2,
        int a3,
        struct Windows::Rtl::IRtlFormattedOutputStream *a4)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  const struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v13; // [rsp+28h] [rbp-29h] BYREF
  char v14; // [rsp+30h] [rbp-21h]
  _QWORD v15[4]; // [rsp+38h] [rbp-19h] BYREF
  _QWORD v16[5]; // [rsp+58h] [rbp+7h] BYREF
  int v17; // [rsp+80h] [rbp+2Fh] BYREF

  v16[4] = -2;
  v17 = 0;
  v13 = (const struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)(a1 + 4160);
  v14 = 0;
  v8 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  if ( v8 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v9 >= 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)(a1 + 4152) = a3;
        if ( *(_QWORD *)(a1 + 32) )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 224LL))(*(_QWORD *)(a1 + 16), a1 + 40);
          *(_BYTE *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 32) = 0;
        }
        Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 16), a4, 0, 0, v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
        v11 = *(unsigned int *)(a1 + 4156);
        if ( (int)v11 < 0 )
        {
          v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
          v16[1] = "LogAdapter::Logger::LogNumObjects";
          v16[2] = 215;
          v16[3] = "m_FlushSink.Hr()";
          v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                 &v17,
                 v16,
                 v11);
          goto LABEL_4;
        }
      }
      else
      {
        Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 8), a4, 0, 0, v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      }
      v10 = 0;
      goto LABEL_12;
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
LABEL_4:
  v10 = v9;
LABEL_12:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  return v10;
}

```

## disassembly

```asm
0x1400067bc  mov     rax, rsp
0x1400067bf  push    rbp
0x1400067c0  push    rdi
0x1400067c1  push    r14
0x1400067c3  lea     rbp, [rax-5Fh]
0x1400067c7  sub     rsp, 90h
0x1400067ce  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFEh
0x1400067d6  mov     [rax+10h], rbx
0x1400067da  mov     [rax+18h], rsi
0x1400067de  mov     rax, cs:__security_cookie
0x1400067e5  xor     rax, rsp
0x1400067e8  mov     [rbp+57h+var_20], rax
0x1400067ec  mov     r14, r9
0x1400067ef  mov     esi, r8d
0x1400067f2  mov     bl, dl
0x1400067f4  mov     rdi, rcx
0x1400067f7  mov     [rbp+57h+var_28], 0
0x1400067fe  lea     rax, [rcx+1040h]
0x140006805  mov     [rbp+57h+var_80], rax
0x140006809  mov     [rbp+57h+var_78], 0
0x14000680d  lea     rcx, [rbp+57h+var_80]; this
0x140006811  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140006816  test    eax, eax
0x140006818  jns     short loc_140006855
0x14000681a  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140006821  mov     [rbp+57h+var_70], rcx
0x140006825  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x14000682c  mov     [rbp+57h+var_68], rcx
0x140006830  mov     [rbp+57h+var_60], 0C3h
0x140006838  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x14000683f  mov     [rbp+57h+var_58], rcx
0x140006843  mov     r8d, eax
0x140006846  lea     rdx, [rbp+57h+var_70]
0x14000684a  lea     rcx, [rbp+57h+var_28]
0x14000684e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006853  jmp     short loc_140006867
0x140006855  mov     rax, [rdi]
0x140006858  mov     rcx, rdi
0x14000685b  mov     rax, [rax]
0x14000685e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006863  test    eax, eax
0x140006865  jns     short loc_14000686E
0x140006867  mov     ebx, eax
0x140006869  jmp     loc_14000694C
0x14000686e  test    bl, bl
0x140006870  jz      loc_140006925
0x140006876  mov     [rdi+1038h], esi
0x14000687c  cmp     qword ptr [rdi+20h], 0
0x140006881  jbe     short loc_1400068B9
0x140006883  mov     rcx, [rdi+8]
0x140006887  mov     rax, [rcx]
0x14000688a  mov     rax, [rax+1F0h]
0x140006891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006896  mov     rcx, [rdi+10h]
0x14000689a  mov     rax, [rcx]
0x14000689d  lea     rdx, [rdi+28h]
0x1400068a1  mov     rax, [rax+0E0h]
0x1400068a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068ad  mov     byte ptr [rdi+28h], 0
0x1400068b1  mov     qword ptr [rdi+20h], 0
0x1400068b9  xor     r9d, r9d; unsigned __int64
0x1400068bc  xor     r8d, r8d; char *
0x1400068bf  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x1400068c2  mov     rcx, [rdi+10h]; this
0x1400068c6  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x1400068cb  mov     rcx, [rdi+10h]
0x1400068cf  mov     rax, [rcx]
0x1400068d2  mov     rax, [rax+1F0h]
0x1400068d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068de  mov     r8d, [rdi+103Ch]
0x1400068e5  test    r8d, r8d
0x1400068e8  jns     short loc_14000694A
0x1400068ea  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x1400068f1  mov     [rbp+57h+var_50], rcx
0x1400068f5  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x1400068fc  mov     [rbp+57h+var_48], rcx
0x140006900  mov     [rbp+57h+var_40], 0D7h
0x140006908  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x14000690f  mov     [rbp+57h+var_38], rax
0x140006913  lea     rdx, [rbp+57h+var_50]
0x140006917  lea     rcx, [rbp+57h+var_28]
0x14000691b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006920  jmp     loc_140006867
0x140006925  xor     r9d, r9d; unsigned __int64
0x140006928  xor     r8d, r8d; char *
0x14000692b  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x14000692e  mov     rcx, [rdi+8]; this
0x140006932  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140006937  mov     rcx, [rdi+8]
0x14000693b  mov     rax, [rcx]
0x14000693e  mov     rax, [rax+1F0h]
0x140006945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000694a  xor     ebx, ebx
0x14000694c  lea     rcx, [rbp+57h+var_80]; this
0x140006950  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140006955  mov     eax, ebx
0x140006957  mov     rcx, [rbp+57h+var_20]
0x14000695b  xor     rcx, rsp; StackCookie
0x14000695e  call    __security_check_cookie
0x140006963  lea     r11, [rsp+0A0h+var_10]
0x14000696b  mov     rbx, [r11+28h]
0x14000696f  mov     rsi, [r11+30h]
0x140006973  mov     rsp, r11
0x140006976  pop     r14
0x140006978  pop     rdi
0x140006979  pop     rbp
0x14000697a  retn
```
