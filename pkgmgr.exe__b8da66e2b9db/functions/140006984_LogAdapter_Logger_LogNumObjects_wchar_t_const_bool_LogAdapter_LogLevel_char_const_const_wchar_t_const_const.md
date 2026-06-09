# LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)

- ea: `0x140006984`
- end: `0x140006b3f`
- name: `??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z`
- size: `443`
- prototype: `__int64 __fastcall(__int64, char, int, __int64, __int64)`
- caller_count: `17`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140007524`
- `0x140008de8`
- `0x14000903c`
- `0x14000a1dc`
- `0x14000aca8`
- `0x14000ccac`
- `0x14001263c`
- `0x140013288`
- `0x140015a08`
- `0x140016ac4`
- `0x140016bc8`
- `0x140016dc8`
- `0x140017390`
- `0x140017568`
- `0x140017b80`
- `0x140017eb4`
- `0x140018394`

## callees

- `0x140002360`
- `0x140006984`
- `0x140006de8`
- `0x1400070ec`
- `0x1400071c8`
- `0x1400074c0`
- `0x1400074ec`
- `0x14002a010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r8
  __int64 v14; // [rsp+28h] [rbp-41h] BYREF
  char v15; // [rsp+30h] [rbp-39h]
  _QWORD v16[4]; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v17[5]; // [rsp+58h] [rbp-11h] BYREF
  int v18; // [rsp+80h] [rbp+17h] BYREF

  v17[4] = -2;
  v18 = 0;
  v14 = a1 + 4160;
  v15 = 0;
  v9 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v14);
  if ( v9 >= 0 )
  {
    v10 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v10 >= 0 )
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
        Windows::Tracing::RtlFormatIntoStream<wchar_t *>(*(_QWORD *)(a1 + 16), a4, a5);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
        v12 = *(unsigned int *)(a1 + 4156);
        if ( (int)v12 < 0 )
        {
          v17[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
          v17[1] = "LogAdapter::Logger::LogNumObjects";
          v17[2] = 215;
          v17[3] = "m_FlushSink.Hr()";
          v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v18,
                  v17,
                  v12);
          goto LABEL_4;
        }
      }
      else
      {
        Windows::Tracing::RtlFormatIntoStream<wchar_t *>(*(_QWORD *)(a1 + 8), a4, a5);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      }
      v11 = 0;
      goto LABEL_12;
    }
  }
  else
  {
    v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v16[1] = "LogAdapter::Logger::LogNumObjects";
    v16[2] = 195;
    v16[3] = "QueueLock.Acquire()";
    v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
            &v18,
            v16,
            (unsigned int)v9);
  }
LABEL_4:
  v11 = v10;
LABEL_12:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v14);
  return v11;
}

```

## disassembly

```asm
0x140006984  mov     rax, rsp
0x140006987  push    rbp
0x140006988  push    rsi
0x140006989  push    rdi
0x14000698a  push    r14
0x14000698c  push    r15
0x14000698e  lea     rbp, [rax-57h]
0x140006992  sub     rsp, 90h
0x140006999  mov     [rbp+4Fh+var_40], 0FFFFFFFFFFFFFFFEh
0x1400069a1  mov     [rax+10h], rbx
0x1400069a5  mov     rax, cs:__security_cookie
0x1400069ac  xor     rax, rsp
0x1400069af  mov     [rbp+4Fh+var_30], rax
0x1400069b3  mov     r14, r9
0x1400069b6  mov     esi, r8d
0x1400069b9  mov     bl, dl
0x1400069bb  mov     rdi, rcx
0x1400069be  mov     r15, [rbp+4Fh+arg_20]
0x1400069c2  mov     [rbp+4Fh+var_38], 0
0x1400069c9  lea     rax, [rcx+1040h]
0x1400069d0  mov     [rbp+4Fh+var_90], rax
0x1400069d4  mov     [rbp+4Fh+var_88], 0
0x1400069d8  lea     rcx, [rbp+4Fh+var_90]; this
0x1400069dc  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x1400069e1  test    eax, eax
0x1400069e3  jns     short loc_140006A20
0x1400069e5  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x1400069ec  mov     [rbp+4Fh+var_80], rcx
0x1400069f0  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x1400069f7  mov     [rbp+4Fh+var_78], rcx
0x1400069fb  mov     [rbp+4Fh+var_70], 0C3h
0x140006a03  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140006a0a  mov     [rbp+4Fh+var_68], rcx
0x140006a0e  mov     r8d, eax
0x140006a11  lea     rdx, [rbp+4Fh+var_80]
0x140006a15  lea     rcx, [rbp+4Fh+var_38]
0x140006a19  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006a1e  jmp     short loc_140006A32
0x140006a20  mov     rax, [rdi]
0x140006a23  mov     rcx, rdi
0x140006a26  mov     rax, [rax]
0x140006a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a2e  test    eax, eax
0x140006a30  jns     short loc_140006A39
0x140006a32  mov     ebx, eax
0x140006a34  jmp     loc_140006B11
0x140006a39  test    bl, bl
0x140006a3b  jz      loc_140006AED
0x140006a41  mov     [rdi+1038h], esi
0x140006a47  cmp     qword ptr [rdi+20h], 0
0x140006a4c  jbe     short loc_140006A84
0x140006a4e  mov     rcx, [rdi+8]
0x140006a52  mov     rax, [rcx]
0x140006a55  mov     rax, [rax+1F0h]
0x140006a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a61  mov     rcx, [rdi+10h]
0x140006a65  mov     rax, [rcx]
0x140006a68  lea     rdx, [rdi+28h]
0x140006a6c  mov     rax, [rax+0E0h]
0x140006a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a78  mov     byte ptr [rdi+28h], 0
0x140006a7c  mov     qword ptr [rdi+20h], 0
0x140006a84  mov     r8, r15
0x140006a87  mov     rdx, r14
0x140006a8a  mov     rcx, [rdi+10h]
0x140006a8e  call    ??$RtlFormatIntoStream@PEA_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBQEA_W@Z; Windows::Tracing::RtlFormatIntoStream<wchar_t *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t * const &)
0x140006a93  mov     rcx, [rdi+10h]
0x140006a97  mov     rax, [rcx]
0x140006a9a  mov     rax, [rax+1F0h]
0x140006aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aa6  mov     r8d, [rdi+103Ch]
0x140006aad  test    r8d, r8d
0x140006ab0  jns     short loc_140006B0F
0x140006ab2  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140006ab9  mov     [rbp+4Fh+var_60], rcx
0x140006abd  lea     rcx, aLogadapterLogg; "LogAdapter::Logger::LogNumObjects"
0x140006ac4  mov     [rbp+4Fh+var_58], rcx
0x140006ac8  mov     [rbp+4Fh+var_50], 0D7h
0x140006ad0  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x140006ad7  mov     [rbp+4Fh+var_48], rax
0x140006adb  lea     rdx, [rbp+4Fh+var_60]
0x140006adf  lea     rcx, [rbp+4Fh+var_38]
0x140006ae3  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140006ae8  jmp     loc_140006A32
0x140006aed  mov     r8, r15
0x140006af0  mov     rdx, r14
0x140006af3  mov     rcx, [rdi+8]
0x140006af7  call    ??$RtlFormatIntoStream@PEA_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBQEA_W@Z; Windows::Tracing::RtlFormatIntoStream<wchar_t *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t * const &)
0x140006afc  mov     rcx, [rdi+8]
0x140006b00  mov     rax, [rcx]
0x140006b03  mov     rax, [rax+1F0h]
0x140006b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b0f  xor     ebx, ebx
0x140006b11  lea     rcx, [rbp+4Fh+var_90]; this
0x140006b15  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140006b1a  mov     eax, ebx
0x140006b1c  mov     rcx, [rbp+4Fh+var_30]
0x140006b20  xor     rcx, rsp; StackCookie
0x140006b23  call    __security_check_cookie
0x140006b28  mov     rbx, [rsp+0B0h+arg_8]
0x140006b30  add     rsp, 90h
0x140006b37  pop     r15
0x140006b39  pop     r14
0x140006b3b  pop     rdi
0x140006b3c  pop     rsi
0x140006b3d  pop     rbp
0x140006b3e  retn
```
