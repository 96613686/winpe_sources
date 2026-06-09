# wil::details::static_lazy<WorkerEtwProvider>::Completer::~Completer(void)

- ea: `0x140003ca0`
- end: `0x140003d86`
- name: `??1Completer@?$static_lazy@VWorkerEtwProvider@@@details@wil@@QEAA@XZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006894`

## callees

- `0x1400020b0`
- `0x140003ca0`
- `0x140034010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140003d34`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140003d34`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140003d16`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140003d16`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140003d62`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140003d62`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<WorkerEtwProvider>::Completer::~Completer(_DWORD *a1)
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
0x140003ca0  push    rbx
0x140003ca2  push    rsi
0x140003ca3  push    rdi
0x140003ca4  push    r14
0x140003ca6  sub     rsp, 48h
0x140003caa  mov     rax, cs:__security_cookie
0x140003cb1  xor     rax, rsp
0x140003cb4  mov     [rsp+68h+var_38], rax
0x140003cb9  cmp     dword ptr [rcx+8], 0
0x140003cbd  mov     rdi, rcx
0x140003cc0  jnz     loc_140003D58
0x140003cc6  mov     rbx, [rcx]
0x140003cc9  mov     rsi, [rbx+20h]
0x140003ccd  mov     [rbx+10h], rsi
0x140003cd1  mov     byte ptr [rbx+18h], 1
0x140003cd5  mov     rax, [rsi+8]
0x140003cd9  lea     r14, [rsi+20h]
0x140003cdd  cmp     qword ptr [r14], 0
0x140003ce1  movups  xmm0, xmmword ptr [rax-10h]
0x140003ce5  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x140003ceb  jz      short loc_140003CF4
0x140003ced  mov     ecx, 5
0x140003cf2  int     29h; Win8: RtlFailFast(ecx)
0x140003cf4  mov     r9, r14; RegHandle
0x140003cf7  mov     qword ptr [rsi+28h], 0
0x140003cff  mov     r8, rsi; CallbackContext
0x140003d02  mov     qword ptr [rsi+30h], 0
0x140003d0a  lea     rdx, _tlgEnableCallback; EnableCallback
0x140003d11  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140003d16  call    cs:__imp_EventRegister
0x140003d1d  nop     dword ptr [rax+rax+00h]
0x140003d22  test    eax, eax
0x140003d24  jnz     short loc_140003D40
0x140003d26  mov     r8, [rsi+8]
0x140003d2a  lea     edx, [rax+2]
0x140003d2d  mov     rcx, [r14]
0x140003d30  movzx   r9d, word ptr [r8]
0x140003d34  call    cs:__imp_EventSetInformation
0x140003d3b  nop     dword ptr [rax+rax+00h]
0x140003d40  mov     rax, [rbx+8]
0x140003d44  lea     rcx, [rbx+8]
0x140003d48  mov     dword ptr [rbx+1Ch], 1
0x140003d4f  mov     rax, [rax+8]
0x140003d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d58  mov     rcx, [rdi]; lpInitOnce
0x140003d5b  mov     edx, [rdi+8]; dwFlags
0x140003d5e  lea     r8, [rcx+8]; lpContext
0x140003d62  call    cs:__imp_InitOnceComplete
0x140003d69  nop     dword ptr [rax+rax+00h]
0x140003d6e  mov     rcx, [rsp+68h+var_38]
0x140003d73  xor     rcx, rsp; StackCookie
0x140003d76  call    __security_check_cookie
0x140003d7b  add     rsp, 48h
0x140003d7f  pop     r14
0x140003d81  pop     rdi
0x140003d82  pop     rsi
0x140003d83  pop     rbx
0x140003d84  retn
```
