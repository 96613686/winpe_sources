# wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(void)

- ea: `0x14008079c`
- end: `0x14008086f`
- name: `??1Completer@?$static_lazy@VUalPrintLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140080a18`

## callees

- `0x14008079c`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x140080812`
- `ADVAPI32!EventRegister` at `0x140080812`
- `ADVAPI32!EventSetInformation` at `0x14008082a`
- `ADVAPI32!EventSetInformation` at `0x14008082a`
- `KERNEL32!InitOnceComplete` at `0x140080852`
- `KERNEL32!InitOnceComplete` at `0x140080852`

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
0x14008079c  push    rbx
0x14008079e  push    rsi
0x14008079f  push    rdi
0x1400807a0  push    r14
0x1400807a2  sub     rsp, 48h
0x1400807a6  mov     rax, cs:__security_cookie
0x1400807ad  xor     rax, rsp
0x1400807b0  mov     [rsp+68h+var_38], rax
0x1400807b5  cmp     dword ptr [rcx+8], 0
0x1400807b9  mov     rdi, rcx
0x1400807bc  jnz     loc_140080848
0x1400807c2  mov     rbx, [rcx]
0x1400807c5  mov     rsi, [rbx+20h]
0x1400807c9  mov     [rbx+10h], rsi
0x1400807cd  mov     byte ptr [rbx+18h], 1
0x1400807d1  mov     rax, [rsi+8]
0x1400807d5  lea     r14, [rsi+20h]
0x1400807d9  cmp     qword ptr [r14], 0
0x1400807dd  movups  xmm0, xmmword ptr [rax-10h]
0x1400807e1  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1400807e7  jz      short loc_1400807F0
0x1400807e9  mov     ecx, 5
0x1400807ee  int     29h; Win8: RtlFailFast(ecx)
0x1400807f0  mov     r9, r14; RegHandle
0x1400807f3  mov     qword ptr [rsi+28h], 0
0x1400807fb  mov     r8, rsi; CallbackContext
0x1400807fe  mov     qword ptr [rsi+30h], 0
0x140080806  lea     rdx, _tlgEnableCallback; EnableCallback
0x14008080d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140080812  call    cs:__imp_EventRegister
0x140080818  test    eax, eax
0x14008081a  jnz     short loc_140080830
0x14008081c  mov     r8, [rsi+8]
0x140080820  lea     edx, [rax+2]
0x140080823  mov     rcx, [r14]
0x140080826  movzx   r9d, word ptr [r8]
0x14008082a  call    cs:__imp_EventSetInformation
0x140080830  mov     rax, [rbx+8]
0x140080834  lea     rcx, [rbx+8]
0x140080838  mov     dword ptr [rbx+1Ch], 1
0x14008083f  mov     rax, [rax+8]
0x140080843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080848  mov     rcx, [rdi]; lpInitOnce
0x14008084b  mov     edx, [rdi+8]; dwFlags
0x14008084e  lea     r8, [rcx+8]; lpContext
0x140080852  call    cs:__imp_InitOnceComplete
0x140080858  mov     rcx, [rsp+68h+var_38]
0x14008085d  xor     rcx, rsp; StackCookie
0x140080860  call    __security_check_cookie
0x140080865  add     rsp, 48h
0x140080869  pop     r14
0x14008086b  pop     rdi
0x14008086c  pop     rsi
0x14008086d  pop     rbx
0x14008086e  retn
```
