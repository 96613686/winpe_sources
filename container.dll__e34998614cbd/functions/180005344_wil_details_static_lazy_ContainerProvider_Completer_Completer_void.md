# wil::details::static_lazy<ContainerProvider>::Completer::~Completer(void)

- ea: `0x180005344`
- end: `0x18000542a`
- name: `??1Completer@?$static_lazy@VContainerProvider@@@details@wil@@QEAA@XZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000895c`

## callees

- `0x180002ad0`
- `0x180005344`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005406`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005406`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800053d8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800053d8`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800053ba`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800053ba`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ContainerProvider>::Completer::~Completer(_DWORD *a1)
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
0x180005344  push    rbx
0x180005346  push    rsi
0x180005347  push    rdi
0x180005348  push    r14
0x18000534a  sub     rsp, 48h
0x18000534e  mov     rax, cs:__security_cookie
0x180005355  xor     rax, rsp
0x180005358  mov     [rsp+68h+var_38], rax
0x18000535d  cmp     dword ptr [rcx+8], 0
0x180005361  mov     rdi, rcx
0x180005364  jnz     loc_1800053FC
0x18000536a  mov     rbx, [rcx]
0x18000536d  mov     rsi, [rbx+20h]
0x180005371  mov     [rbx+10h], rsi
0x180005375  mov     byte ptr [rbx+18h], 1
0x180005379  mov     rax, [rsi+8]
0x18000537d  lea     r14, [rsi+20h]
0x180005381  cmp     qword ptr [r14], 0
0x180005385  movups  xmm0, xmmword ptr [rax-10h]
0x180005389  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000538f  jz      short loc_180005398
0x180005391  mov     ecx, 5
0x180005396  int     29h; Win8: RtlFailFast(ecx)
0x180005398  mov     r9, r14; RegHandle
0x18000539b  mov     qword ptr [rsi+28h], 0
0x1800053a3  mov     r8, rsi; CallbackContext
0x1800053a6  mov     qword ptr [rsi+30h], 0
0x1800053ae  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800053b5  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x1800053ba  call    cs:__imp_EventRegister
0x1800053c1  nop     dword ptr [rax+rax+00h]
0x1800053c6  test    eax, eax
0x1800053c8  jnz     short loc_1800053E4
0x1800053ca  mov     r8, [rsi+8]
0x1800053ce  lea     edx, [rax+2]
0x1800053d1  mov     rcx, [r14]
0x1800053d4  movzx   r9d, word ptr [r8]
0x1800053d8  call    cs:__imp_EventSetInformation
0x1800053df  nop     dword ptr [rax+rax+00h]
0x1800053e4  mov     rax, [rbx+8]
0x1800053e8  lea     rcx, [rbx+8]
0x1800053ec  mov     dword ptr [rbx+1Ch], 1
0x1800053f3  mov     rax, [rax+8]
0x1800053f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fc  mov     rcx, [rdi]; lpInitOnce
0x1800053ff  mov     edx, [rdi+8]; dwFlags
0x180005402  lea     r8, [rcx+8]; lpContext
0x180005406  call    cs:__imp_InitOnceComplete
0x18000540d  nop     dword ptr [rax+rax+00h]
0x180005412  mov     rcx, [rsp+68h+var_38]
0x180005417  xor     rcx, rsp; StackCookie
0x18000541a  call    __security_check_cookie
0x18000541f  add     rsp, 48h
0x180005423  pop     r14
0x180005425  pop     rdi
0x180005426  pop     rsi
0x180005427  pop     rbx
0x180005428  retn
```
