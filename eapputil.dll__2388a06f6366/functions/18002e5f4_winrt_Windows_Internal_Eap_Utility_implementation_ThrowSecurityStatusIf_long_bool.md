# winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)

- ea: `0x18002e5f4`
- end: `0x18002e64d`
- name: `?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z`
- size: `89`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation *__hidden this, int, bool)`
- caller_count: `9`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800188f0`
- `0x180018e1c`
- `0x180019794`
- `0x180019dc4`
- `0x18001d040`
- `0x18002647c`
- `0x180026844`
- `0x180027044`
- `0x18002a2a8`

## callees

- `0x180004380`
- `0x180008d90`
- `0x1800101c4`
- `0x18002cdcc`
- `0x18002e5f4`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
        winrt::Windows::Internal::Eap::Utility::implementation *this,
        char a2)
{
  int v2; // eax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v5; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 )
  {
    v5 = (int)this;
    v2 = wil::verify_hresult<long>((unsigned int)this);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\utilities.cpp",
        (const char *)(unsigned int)v2,
        v3);
    winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::UnexpectedSchannelSuccessWithCondition<long const &>(&v5);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\utilities.cpp",
      (const char *)0x139F,
      v3);
  }
}

```

## disassembly

```asm
0x18002e5f4  test    dl, dl
0x18002e5f6  jz      short locret_18002E60B
0x18002e5f8  mov     [rsp+arg_0], ecx
0x18002e5fc  sub     rsp, 28h
0x18002e600  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e605  test    eax, eax
0x18002e607  jns     short loc_18002E626
0x18002e609  jmp     short loc_18002E60C
0x18002e60b  retn
0x18002e60c  mov     rcx, [rsp+28h]; this
0x18002e611  lea     r8, aOnecoreuapNetE_5; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002e618  mov     r9d, eax; char *
0x18002e61b  mov     edx, 14h; void *
0x18002e620  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e626  lea     rcx, [rsp+28h+arg_0]
0x18002e62b  call    ??$UnexpectedSchannelSuccessWithCondition@AEBJ@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXAEBJ@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::UnexpectedSchannelSuccessWithCondition<long const &>(long const &)
0x18002e630  mov     rcx, [rsp+28h]; this
0x18002e635  lea     r8, aOnecoreuapNetE_5; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002e63c  mov     r9d, 139Fh; char *
0x18002e642  mov     edx, 19h; void *
0x18002e647  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
