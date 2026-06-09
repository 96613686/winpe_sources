# wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(void)

- ea: `0x18000a26c`
- end: `0x18000a33f`
- name: `??1Completer@?$static_lazy@VUalPrintLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a3bc`

## callees

- `0x180001ce0`
- `0x18000a26c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a2fa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a2fa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a2e2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a2e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a322`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a322`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(_DWORD *a1)
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
0x18000a26c  push    rbx
0x18000a26e  push    rsi
0x18000a26f  push    rdi
0x18000a270  push    r14
0x18000a272  sub     rsp, 48h
0x18000a276  mov     rax, cs:__security_cookie
0x18000a27d  xor     rax, rsp
0x18000a280  mov     [rsp+68h+var_38], rax
0x18000a285  cmp     dword ptr [rcx+8], 0
0x18000a289  mov     rdi, rcx
0x18000a28c  jnz     loc_18000A318
0x18000a292  mov     rbx, [rcx]
0x18000a295  mov     rsi, [rbx+20h]
0x18000a299  mov     [rbx+10h], rsi
0x18000a29d  mov     byte ptr [rbx+18h], 1
0x18000a2a1  mov     rax, [rsi+8]
0x18000a2a5  lea     r14, [rsi+20h]
0x18000a2a9  cmp     qword ptr [r14], 0
0x18000a2ad  movups  xmm0, xmmword ptr [rax-10h]
0x18000a2b1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000a2b7  jz      short loc_18000A2C0
0x18000a2b9  mov     ecx, 5
0x18000a2be  int     29h; Win8: RtlFailFast(ecx)
0x18000a2c0  mov     r9, r14; RegHandle
0x18000a2c3  mov     qword ptr [rsi+28h], 0
0x18000a2cb  mov     r8, rsi; CallbackContext
0x18000a2ce  mov     qword ptr [rsi+30h], 0
0x18000a2d6  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a2dd  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000a2e2  call    cs:__imp_EventRegister
0x18000a2e8  test    eax, eax
0x18000a2ea  jnz     short loc_18000A300
0x18000a2ec  mov     r8, [rsi+8]
0x18000a2f0  lea     edx, [rax+2]
0x18000a2f3  mov     rcx, [r14]
0x18000a2f6  movzx   r9d, word ptr [r8]
0x18000a2fa  call    cs:__imp_EventSetInformation
0x18000a300  mov     rax, [rbx+8]
0x18000a304  lea     rcx, [rbx+8]
0x18000a308  mov     dword ptr [rbx+1Ch], 1
0x18000a30f  mov     rax, [rax+8]
0x18000a313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a318  mov     rcx, [rdi]; lpInitOnce
0x18000a31b  mov     edx, [rdi+8]; dwFlags
0x18000a31e  lea     r8, [rcx+8]; lpContext
0x18000a322  call    cs:__imp_InitOnceComplete
0x18000a328  mov     rcx, [rsp+68h+var_38]
0x18000a32d  xor     rcx, rsp; StackCookie
0x18000a330  call    __security_check_cookie
0x18000a335  add     rsp, 48h
0x18000a339  pop     r14
0x18000a33b  pop     rdi
0x18000a33c  pop     rsi
0x18000a33d  pop     rbx
0x18000a33e  retn
```
