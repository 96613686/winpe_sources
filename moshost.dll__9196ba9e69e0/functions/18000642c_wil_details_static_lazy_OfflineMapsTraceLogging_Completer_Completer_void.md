# wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)

- ea: `0x18000642c`
- end: `0x1800064ff`
- name: `??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000689c`

## callees

- `0x180001d00`
- `0x18000642c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800064ba`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800064ba`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800064a2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800064a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800064e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800064e2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x18000642c  push    rbx
0x18000642e  push    rsi
0x18000642f  push    rdi
0x180006430  push    r14
0x180006432  sub     rsp, 48h
0x180006436  mov     rax, cs:__security_cookie
0x18000643d  xor     rax, rsp
0x180006440  mov     [rsp+68h+var_38], rax
0x180006445  cmp     dword ptr [rcx+8], 0
0x180006449  mov     rdi, rcx
0x18000644c  jnz     loc_1800064D8
0x180006452  mov     rbx, [rcx]
0x180006455  mov     rsi, [rbx+20h]
0x180006459  mov     [rbx+10h], rsi
0x18000645d  mov     byte ptr [rbx+18h], 1
0x180006461  mov     rax, [rsi+8]
0x180006465  lea     r14, [rsi+20h]
0x180006469  cmp     qword ptr [r14], 0
0x18000646d  movups  xmm0, xmmword ptr [rax-10h]
0x180006471  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180006477  jz      short loc_180006480
0x180006479  mov     ecx, 5
0x18000647e  int     29h; Win8: RtlFailFast(ecx)
0x180006480  mov     r9, r14; RegHandle
0x180006483  mov     qword ptr [rsi+28h], 0
0x18000648b  mov     r8, rsi; CallbackContext
0x18000648e  mov     qword ptr [rsi+30h], 0
0x180006496  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000649d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800064a2  call    cs:__imp_EventRegister
0x1800064a8  test    eax, eax
0x1800064aa  jnz     short loc_1800064C0
0x1800064ac  mov     r8, [rsi+8]
0x1800064b0  lea     edx, [rax+2]
0x1800064b3  mov     rcx, [r14]
0x1800064b6  movzx   r9d, word ptr [r8]
0x1800064ba  call    cs:__imp_EventSetInformation
0x1800064c0  mov     rax, [rbx+8]
0x1800064c4  lea     rcx, [rbx+8]
0x1800064c8  mov     dword ptr [rbx+1Ch], 1
0x1800064cf  mov     rax, [rax+8]
0x1800064d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d8  mov     rcx, [rdi]; lpInitOnce
0x1800064db  mov     edx, [rdi+8]; dwFlags
0x1800064de  lea     r8, [rcx+8]; lpContext
0x1800064e2  call    cs:__imp_InitOnceComplete
0x1800064e8  mov     rcx, [rsp+68h+var_38]
0x1800064ed  xor     rcx, rsp; StackCookie
0x1800064f0  call    __security_check_cookie
0x1800064f5  add     rsp, 48h
0x1800064f9  pop     r14
0x1800064fb  pop     rdi
0x1800064fc  pop     rsi
0x1800064fd  pop     rbx
0x1800064fe  retn
```
