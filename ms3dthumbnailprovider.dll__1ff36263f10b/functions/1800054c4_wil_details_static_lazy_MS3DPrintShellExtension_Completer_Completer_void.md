# wil::details::static_lazy<MS3DPrintShellExtension>::Completer::~Completer(void)

- ea: `0x1800054c4`
- end: `0x180005597`
- name: `??1Completer@?$static_lazy@VMS3DPrintShellExtension@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c04`

## callees

- `0x180001ef0`
- `0x1800054c4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18000557a`
- `KERNEL32!InitOnceComplete` at `0x18000557a`
- `ADVAPI32!EventSetInformation` at `0x180005552`
- `ADVAPI32!EventSetInformation` at `0x180005552`
- `ADVAPI32!EventRegister` at `0x18000553a`
- `ADVAPI32!EventRegister` at `0x18000553a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MS3DPrintShellExtension>::Completer::~Completer(_DWORD *a1)
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
0x1800054c4  push    rbx
0x1800054c6  push    rsi
0x1800054c7  push    rdi
0x1800054c8  push    r14
0x1800054ca  sub     rsp, 48h
0x1800054ce  mov     rax, cs:__security_cookie
0x1800054d5  xor     rax, rsp
0x1800054d8  mov     [rsp+68h+var_38], rax
0x1800054dd  cmp     dword ptr [rcx+8], 0
0x1800054e1  mov     rdi, rcx
0x1800054e4  jnz     loc_180005570
0x1800054ea  mov     rbx, [rcx]
0x1800054ed  mov     rsi, [rbx+20h]
0x1800054f1  mov     [rbx+10h], rsi
0x1800054f5  mov     byte ptr [rbx+18h], 1
0x1800054f9  mov     rax, [rsi+8]
0x1800054fd  lea     r14, [rsi+20h]
0x180005501  cmp     qword ptr [r14], 0
0x180005505  movups  xmm0, xmmword ptr [rax-10h]
0x180005509  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000550f  jz      short loc_180005518
0x180005511  mov     ecx, 5
0x180005516  int     29h; Win8: RtlFailFast(ecx)
0x180005518  mov     r9, r14; RegHandle
0x18000551b  mov     qword ptr [rsi+28h], 0
0x180005523  mov     r8, rsi; CallbackContext
0x180005526  mov     qword ptr [rsi+30h], 0
0x18000552e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180005535  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000553a  call    cs:__imp_EventRegister
0x180005540  test    eax, eax
0x180005542  jnz     short loc_180005558
0x180005544  mov     r8, [rsi+8]
0x180005548  lea     edx, [rax+2]
0x18000554b  mov     rcx, [r14]
0x18000554e  movzx   r9d, word ptr [r8]
0x180005552  call    cs:__imp_EventSetInformation
0x180005558  mov     rax, [rbx+8]
0x18000555c  lea     rcx, [rbx+8]
0x180005560  mov     dword ptr [rbx+1Ch], 1
0x180005567  mov     rax, [rax+8]
0x18000556b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005570  mov     rcx, [rdi]; lpInitOnce
0x180005573  mov     edx, [rdi+8]; dwFlags
0x180005576  lea     r8, [rcx+8]; lpContext
0x18000557a  call    cs:__imp_InitOnceComplete
0x180005580  mov     rcx, [rsp+68h+var_38]
0x180005585  xor     rcx, rsp; StackCookie
0x180005588  call    __security_check_cookie
0x18000558d  add     rsp, 48h
0x180005591  pop     r14
0x180005593  pop     rdi
0x180005594  pop     rsi
0x180005595  pop     rbx
0x180005596  retn
```
