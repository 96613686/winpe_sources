# wil::details::static_lazy<CflApiTraceProvider>::Completer::~Completer(void)

- ea: `0x180008da4`
- end: `0x180008e77`
- name: `??1Completer@?$static_lazy@VCflApiTraceProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a31c`

## callees

- `0x180002490`
- `0x180008da4`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e1a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e1a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008e32`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008e32`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008e5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008e5a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CflApiTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x180008da4  push    rbx
0x180008da6  push    rsi
0x180008da7  push    rdi
0x180008da8  push    r14
0x180008daa  sub     rsp, 48h
0x180008dae  mov     rax, cs:__security_cookie
0x180008db5  xor     rax, rsp
0x180008db8  mov     [rsp+68h+var_38], rax
0x180008dbd  cmp     dword ptr [rcx+8], 0
0x180008dc1  mov     rdi, rcx
0x180008dc4  jnz     loc_180008E50
0x180008dca  mov     rbx, [rcx]
0x180008dcd  mov     rsi, [rbx+20h]
0x180008dd1  mov     [rbx+10h], rsi
0x180008dd5  mov     byte ptr [rbx+18h], 1
0x180008dd9  mov     rax, [rsi+8]
0x180008ddd  lea     r14, [rsi+20h]
0x180008de1  cmp     qword ptr [r14], 0
0x180008de5  movups  xmm0, xmmword ptr [rax-10h]
0x180008de9  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180008def  jz      short loc_180008DF8
0x180008df1  mov     ecx, 5
0x180008df6  int     29h; Win8: RtlFailFast(ecx)
0x180008df8  mov     r9, r14; RegHandle
0x180008dfb  mov     qword ptr [rsi+28h], 0
0x180008e03  mov     r8, rsi; CallbackContext
0x180008e06  mov     qword ptr [rsi+30h], 0
0x180008e0e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180008e15  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180008e1a  call    cs:__imp_EventRegister
0x180008e20  test    eax, eax
0x180008e22  jnz     short loc_180008E38
0x180008e24  mov     r8, [rsi+8]
0x180008e28  lea     edx, [rax+2]
0x180008e2b  mov     rcx, [r14]
0x180008e2e  movzx   r9d, word ptr [r8]
0x180008e32  call    cs:__imp_EventSetInformation
0x180008e38  mov     rax, [rbx+8]
0x180008e3c  lea     rcx, [rbx+8]
0x180008e40  mov     dword ptr [rbx+1Ch], 1
0x180008e47  mov     rax, [rax+8]
0x180008e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e50  mov     rcx, [rdi]; lpInitOnce
0x180008e53  mov     edx, [rdi+8]; dwFlags
0x180008e56  lea     r8, [rcx+8]; lpContext
0x180008e5a  call    cs:__imp_InitOnceComplete
0x180008e60  mov     rcx, [rsp+68h+var_38]
0x180008e65  xor     rcx, rsp; StackCookie
0x180008e68  call    __security_check_cookie
0x180008e6d  add     rsp, 48h
0x180008e71  pop     r14
0x180008e73  pop     rdi
0x180008e74  pop     rsi
0x180008e75  pop     rbx
0x180008e76  retn
```
