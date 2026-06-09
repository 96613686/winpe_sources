# wil::details::static_lazy<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider>::Completer::~Completer(void)

- ea: `0x180005098`
- end: `0x18000516b`
- name: `??1Completer@?$static_lazy@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006f50`

## callees

- `0x180005098`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000514e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000514e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005126`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005126`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000510e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000510e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider>::Completer::~Completer(
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
0x180005098  push    rbx
0x18000509a  push    rsi
0x18000509b  push    rdi
0x18000509c  push    r14
0x18000509e  sub     rsp, 48h
0x1800050a2  mov     rax, cs:__security_cookie
0x1800050a9  xor     rax, rsp
0x1800050ac  mov     [rsp+68h+var_38], rax
0x1800050b1  cmp     dword ptr [rcx+8], 0
0x1800050b5  mov     rdi, rcx
0x1800050b8  jnz     loc_180005144
0x1800050be  mov     rbx, [rcx]
0x1800050c1  mov     rsi, [rbx+20h]
0x1800050c5  mov     [rbx+10h], rsi
0x1800050c9  mov     byte ptr [rbx+18h], 1
0x1800050cd  mov     rax, [rsi+8]
0x1800050d1  lea     r14, [rsi+20h]
0x1800050d5  cmp     qword ptr [r14], 0
0x1800050d9  movups  xmm0, xmmword ptr [rax-10h]
0x1800050dd  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1800050e3  jz      short loc_1800050EC
0x1800050e5  mov     ecx, 5
0x1800050ea  int     29h; Win8: RtlFailFast(ecx)
0x1800050ec  mov     r9, r14; RegHandle
0x1800050ef  mov     qword ptr [rsi+28h], 0
0x1800050f7  mov     r8, rsi; CallbackContext
0x1800050fa  mov     qword ptr [rsi+30h], 0
0x180005102  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005109  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000510e  call    cs:__imp_EventRegister
0x180005114  test    eax, eax
0x180005116  jnz     short loc_18000512C
0x180005118  mov     r8, [rsi+8]
0x18000511c  lea     edx, [rax+2]
0x18000511f  mov     rcx, [r14]
0x180005122  movzx   r9d, word ptr [r8]
0x180005126  call    cs:__imp_EventSetInformation
0x18000512c  mov     rax, [rbx+8]
0x180005130  lea     rcx, [rbx+8]
0x180005134  mov     dword ptr [rbx+1Ch], 1
0x18000513b  mov     rax, [rax+8]
0x18000513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005144  mov     rcx, [rdi]; lpInitOnce
0x180005147  mov     edx, [rdi+8]; dwFlags
0x18000514a  lea     r8, [rcx+8]; lpContext
0x18000514e  call    cs:__imp_InitOnceComplete
0x180005154  mov     rcx, [rsp+68h+var_38]
0x180005159  xor     rcx, rsp; StackCookie
0x18000515c  call    __security_check_cookie
0x180005161  add     rsp, 48h
0x180005165  pop     r14
0x180005167  pop     rdi
0x180005168  pop     rsi
0x180005169  pop     rbx
0x18000516a  retn
```
