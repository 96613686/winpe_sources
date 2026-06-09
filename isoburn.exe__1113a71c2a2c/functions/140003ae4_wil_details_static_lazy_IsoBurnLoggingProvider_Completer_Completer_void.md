# wil::details::static_lazy<IsoBurnLoggingProvider>::Completer::~Completer(void)

- ea: `0x140003ae4`
- end: `0x140003bb7`
- name: `??1Completer@?$static_lazy@VIsoBurnLoggingProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007610`

## callees

- `0x140001fa0`
- `0x140003ae4`
- `0x140010010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x140003b5a`
- `ADVAPI32!EventRegister` at `0x140003b5a`
- `ADVAPI32!EventSetInformation` at `0x140003b72`
- `ADVAPI32!EventSetInformation` at `0x140003b72`
- `KERNEL32!InitOnceComplete` at `0x140003b9a`
- `KERNEL32!InitOnceComplete` at `0x140003b9a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<IsoBurnLoggingProvider>::Completer::~Completer(_DWORD *a1)
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
0x140003ae4  push    rbx
0x140003ae6  push    rsi
0x140003ae7  push    rdi
0x140003ae8  push    r14
0x140003aea  sub     rsp, 48h
0x140003aee  mov     rax, cs:__security_cookie
0x140003af5  xor     rax, rsp
0x140003af8  mov     [rsp+68h+var_38], rax
0x140003afd  cmp     dword ptr [rcx+8], 0
0x140003b01  mov     rdi, rcx
0x140003b04  jnz     loc_140003B90
0x140003b0a  mov     rbx, [rcx]
0x140003b0d  mov     rsi, [rbx+20h]
0x140003b11  mov     [rbx+10h], rsi
0x140003b15  mov     byte ptr [rbx+18h], 1
0x140003b19  mov     rax, [rsi+8]
0x140003b1d  lea     r14, [rsi+20h]
0x140003b21  cmp     qword ptr [r14], 0
0x140003b25  movups  xmm0, xmmword ptr [rax-10h]
0x140003b29  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x140003b2f  jz      short loc_140003B38
0x140003b31  mov     ecx, 5
0x140003b36  int     29h; Win8: RtlFailFast(ecx)
0x140003b38  mov     r9, r14; RegHandle
0x140003b3b  mov     qword ptr [rsi+28h], 0
0x140003b43  mov     r8, rsi; CallbackContext
0x140003b46  mov     qword ptr [rsi+30h], 0
0x140003b4e  lea     rdx, _tlgEnableCallback; EnableCallback
0x140003b55  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140003b5a  call    cs:__imp_EventRegister
0x140003b60  test    eax, eax
0x140003b62  jnz     short loc_140003B78
0x140003b64  mov     r8, [rsi+8]
0x140003b68  lea     edx, [rax+2]
0x140003b6b  mov     rcx, [r14]
0x140003b6e  movzx   r9d, word ptr [r8]
0x140003b72  call    cs:__imp_EventSetInformation
0x140003b78  mov     rax, [rbx+8]
0x140003b7c  lea     rcx, [rbx+8]
0x140003b80  mov     dword ptr [rbx+1Ch], 1
0x140003b87  mov     rax, [rax+8]
0x140003b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b90  mov     rcx, [rdi]; lpInitOnce
0x140003b93  mov     edx, [rdi+8]; dwFlags
0x140003b96  lea     r8, [rcx+8]; lpContext
0x140003b9a  call    cs:__imp_InitOnceComplete
0x140003ba0  mov     rcx, [rsp+68h+var_38]
0x140003ba5  xor     rcx, rsp; StackCookie
0x140003ba8  call    __security_check_cookie
0x140003bad  add     rsp, 48h
0x140003bb1  pop     r14
0x140003bb3  pop     rdi
0x140003bb4  pop     rsi
0x140003bb5  pop     rbx
0x140003bb6  retn
```
