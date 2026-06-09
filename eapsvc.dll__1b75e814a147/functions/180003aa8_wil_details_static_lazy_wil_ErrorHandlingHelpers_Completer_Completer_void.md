# wil::details::static_lazy<wil::ErrorHandlingHelpers>::Completer::~Completer(void)

- ea: `0x180003aa8`
- end: `0x180003b7b`
- name: `??1Completer@?$static_lazy@VErrorHandlingHelpers@wil@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800050f0`

## callees

- `0x180001f60`
- `0x180003aa8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003b5e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003b5e`
- `ntdll!EtwEventRegister` at `0x180003b1e`
- `ntdll!EtwEventRegister` at `0x180003b1e`
- `ntdll!EtwEventSetInformation` at `0x180003b36`
- `ntdll!EtwEventSetInformation` at `0x180003b36`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::ErrorHandlingHelpers>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(_QWORD **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    v7 = *(_OWORD *)(v3[1] - 16LL);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !(unsigned int)((__int64 (__fastcall *)(__int128 *, __int64 (__fastcall *)(int, int, int, int, __int64, __int64, __int64), _QWORD *, _QWORD *))EtwEventRegister)(
                          &v7,
                          tlgEnableCallback,
                          v3,
                          v3 + 4) )
      EtwEventSetInformation(v3[4], 2, v3[1], *(unsigned __int16 *)v3[1], v7, *((_QWORD *)&v7 + 1));
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180003aa8  push    rbx
0x180003aaa  push    rsi
0x180003aab  push    rdi
0x180003aac  push    r14
0x180003aae  sub     rsp, 48h
0x180003ab2  mov     rax, cs:__security_cookie
0x180003ab9  xor     rax, rsp
0x180003abc  mov     [rsp+68h+var_38], rax
0x180003ac1  cmp     dword ptr [rcx+8], 0
0x180003ac5  mov     rdi, rcx
0x180003ac8  jnz     loc_180003B54
0x180003ace  mov     rbx, [rcx]
0x180003ad1  mov     rsi, [rbx+20h]
0x180003ad5  mov     [rbx+10h], rsi
0x180003ad9  mov     byte ptr [rbx+18h], 1
0x180003add  mov     rax, [rsi+8]
0x180003ae1  lea     r14, [rsi+20h]
0x180003ae5  cmp     qword ptr [r14], 0
0x180003ae9  movups  xmm0, xmmword ptr [rax-10h]
0x180003aed  movdqu  [rsp+68h+var_48], xmm0
0x180003af3  jz      short loc_180003AFC
0x180003af5  mov     ecx, 5
0x180003afa  int     29h; Win8: RtlFailFast(ecx)
0x180003afc  mov     r9, r14
0x180003aff  mov     qword ptr [rsi+28h], 0
0x180003b07  mov     r8, rsi
0x180003b0a  mov     qword ptr [rsi+30h], 0
0x180003b12  lea     rdx, _tlgEnableCallback
0x180003b19  lea     rcx, [rsp+68h+var_48]
0x180003b1e  call    cs:__imp_EtwEventRegister
0x180003b24  test    eax, eax
0x180003b26  jnz     short loc_180003B3C
0x180003b28  mov     r8, [rsi+8]
0x180003b2c  lea     edx, [rax+2]
0x180003b2f  mov     rcx, [r14]
0x180003b32  movzx   r9d, word ptr [r8]
0x180003b36  call    cs:__imp_EtwEventSetInformation
0x180003b3c  mov     rax, [rbx+8]
0x180003b40  lea     rcx, [rbx+8]
0x180003b44  mov     dword ptr [rbx+1Ch], 1
0x180003b4b  mov     rax, [rax+8]
0x180003b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b54  mov     rcx, [rdi]; lpInitOnce
0x180003b57  mov     edx, [rdi+8]; dwFlags
0x180003b5a  lea     r8, [rcx+8]; lpContext
0x180003b5e  call    cs:__imp_InitOnceComplete
0x180003b64  mov     rcx, [rsp+68h+var_38]
0x180003b69  xor     rcx, rsp; StackCookie
0x180003b6c  call    __security_check_cookie
0x180003b71  add     rsp, 48h
0x180003b75  pop     r14
0x180003b77  pop     rdi
0x180003b78  pop     rsi
0x180003b79  pop     rbx
0x180003b7a  retn
```
