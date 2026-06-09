# wil::details::static_lazy<EduPrintProvLogging>::Completer::~Completer(void)

- ea: `0x14000cd88`
- end: `0x14000ce5b`
- name: `??1Completer@?$static_lazy@VEduPrintProvLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cfac`

## callees

- `0x140002600`
- `0x14000cd88`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ce3e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ce3e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000cdfe`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000cdfe`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000ce16`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000ce16`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<EduPrintProvLogging>::Completer::~Completer(_DWORD *a1)
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
0x14000cd88  push    rbx
0x14000cd8a  push    rsi
0x14000cd8b  push    rdi
0x14000cd8c  push    r14
0x14000cd8e  sub     rsp, 48h
0x14000cd92  mov     rax, cs:__security_cookie
0x14000cd99  xor     rax, rsp
0x14000cd9c  mov     [rsp+68h+var_38], rax
0x14000cda1  cmp     dword ptr [rcx+8], 0
0x14000cda5  mov     rdi, rcx
0x14000cda8  jnz     loc_14000CE34
0x14000cdae  mov     rbx, [rcx]
0x14000cdb1  mov     rsi, [rbx+20h]
0x14000cdb5  mov     [rbx+10h], rsi
0x14000cdb9  mov     byte ptr [rbx+18h], 1
0x14000cdbd  mov     rax, [rsi+8]
0x14000cdc1  lea     r14, [rsi+20h]
0x14000cdc5  cmp     qword ptr [r14], 0
0x14000cdc9  movups  xmm0, xmmword ptr [rax-10h]
0x14000cdcd  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x14000cdd3  jz      short loc_14000CDDC
0x14000cdd5  mov     ecx, 5
0x14000cdda  int     29h; Win8: RtlFailFast(ecx)
0x14000cddc  mov     r9, r14; RegHandle
0x14000cddf  mov     qword ptr [rsi+28h], 0
0x14000cde7  mov     r8, rsi; CallbackContext
0x14000cdea  mov     qword ptr [rsi+30h], 0
0x14000cdf2  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000cdf9  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x14000cdfe  call    cs:__imp_EventRegister
0x14000ce04  test    eax, eax
0x14000ce06  jnz     short loc_14000CE1C
0x14000ce08  mov     r8, [rsi+8]
0x14000ce0c  lea     edx, [rax+2]
0x14000ce0f  mov     rcx, [r14]
0x14000ce12  movzx   r9d, word ptr [r8]
0x14000ce16  call    cs:__imp_EventSetInformation
0x14000ce1c  mov     rax, [rbx+8]
0x14000ce20  lea     rcx, [rbx+8]
0x14000ce24  mov     dword ptr [rbx+1Ch], 1
0x14000ce2b  mov     rax, [rax+8]
0x14000ce2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce34  mov     rcx, [rdi]; lpInitOnce
0x14000ce37  mov     edx, [rdi+8]; dwFlags
0x14000ce3a  lea     r8, [rcx+8]; lpContext
0x14000ce3e  call    cs:__imp_InitOnceComplete
0x14000ce44  mov     rcx, [rsp+68h+var_38]
0x14000ce49  xor     rcx, rsp; StackCookie
0x14000ce4c  call    __security_check_cookie
0x14000ce51  add     rsp, 48h
0x14000ce55  pop     r14
0x14000ce57  pop     rdi
0x14000ce58  pop     rsi
0x14000ce59  pop     rbx
0x14000ce5a  retn
```
