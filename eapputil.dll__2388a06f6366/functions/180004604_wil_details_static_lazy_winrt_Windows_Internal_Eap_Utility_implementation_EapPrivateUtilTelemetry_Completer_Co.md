# wil::details::static_lazy<winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry>::Completer::~Completer(void)

- ea: `0x180004604`
- end: `0x1800046d7`
- name: `??1Completer@?$static_lazy@VEapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005efc`

## callees

- `0x1800021d0`
- `0x180004604`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800046ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800046ba`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004692`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180004692`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000467a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000467a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry>::Completer::~Completer(
        _DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    ProviderId = *(GUID *)(v3[1] - 16);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v3, v3 + 4) )
      EventSetInformation(
        v3[4],
        2,
        v3[1],
        *(unsigned __int16 *)v3[1],
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180004604  push    rbx
0x180004606  push    rsi
0x180004607  push    rdi
0x180004608  push    r14
0x18000460a  sub     rsp, 48h
0x18000460e  mov     rax, cs:__security_cookie
0x180004615  xor     rax, rsp
0x180004618  mov     [rsp+68h+var_38], rax
0x18000461d  cmp     dword ptr [rcx+8], 0
0x180004621  mov     rdi, rcx
0x180004624  jnz     loc_1800046B0
0x18000462a  mov     rbx, [rcx]
0x18000462d  mov     rsi, [rbx+20h]
0x180004631  mov     [rbx+10h], rsi
0x180004635  mov     byte ptr [rbx+18h], 1
0x180004639  mov     rax, [rsi+8]
0x18000463d  lea     r14, [rsi+20h]
0x180004641  cmp     qword ptr [r14], 0
0x180004645  movups  xmm0, xmmword ptr [rax-10h]
0x180004649  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000464f  jz      short loc_180004658
0x180004651  mov     ecx, 5
0x180004656  int     29h; Win8: RtlFailFast(ecx)
0x180004658  mov     r9, r14; RegHandle
0x18000465b  mov     qword ptr [rsi+28h], 0
0x180004663  mov     r8, rsi; CallbackContext
0x180004666  mov     qword ptr [rsi+30h], 0
0x18000466e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180004675  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000467a  call    cs:__imp_EventRegister
0x180004680  test    eax, eax
0x180004682  jnz     short loc_180004698
0x180004684  mov     r8, [rsi+8]
0x180004688  lea     edx, [rax+2]
0x18000468b  mov     rcx, [r14]
0x18000468e  movzx   r9d, word ptr [r8]
0x180004692  call    cs:__imp_EventSetInformation
0x180004698  mov     rax, [rbx+8]
0x18000469c  lea     rcx, [rbx+8]
0x1800046a0  mov     dword ptr [rbx+1Ch], 1
0x1800046a7  mov     rax, [rax+8]
0x1800046ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b0  mov     rcx, [rdi]; lpInitOnce
0x1800046b3  mov     edx, [rdi+8]; dwFlags
0x1800046b6  lea     r8, [rcx+8]; lpContext
0x1800046ba  call    cs:__imp_InitOnceComplete
0x1800046c0  mov     rcx, [rsp+68h+var_38]
0x1800046c5  xor     rcx, rsp; StackCookie
0x1800046c8  call    __security_check_cookie
0x1800046cd  add     rsp, 48h
0x1800046d1  pop     r14
0x1800046d3  pop     rdi
0x1800046d4  pop     rsi
0x1800046d5  pop     rbx
0x1800046d6  retn
```
