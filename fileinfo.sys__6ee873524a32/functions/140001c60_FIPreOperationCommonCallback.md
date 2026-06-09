# FIPreOperationCommonCallback

- ea: `0x140001c60`
- end: `0x140001d99`
- name: `FIPreOperationCommonCallback`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001c40`

## callees

- `0x140001c60`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140001d0d`
- `ntoskrnl!PsGetThreadId` at `0x140001d0d`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001d4d`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001d4d`

## pseudocode

```c
_BOOL8 __fastcall FIPreOperationCommonCallback(unsigned __int64 a1, __int64 a2, __int64 a3, __int16 a4)
{
  void (__fastcall *v7)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rbx
  struct _KTHREAD *v9; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v12; // rdx
  __int128 v13; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v14[24]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v15; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v16[2]; // [rsp+78h] [rbp-30h] BYREF

  v13 = 0;
  memset(v14, 0, sizeof(v14));
  v15 = 0;
  v7 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v7 )
  {
    v9 = *(struct _KTHREAD **)(a1 + 8);
    memset(v14, 0, sizeof(v14));
    v13 = a1;
    if ( v9 )
      ThreadId = (unsigned int)PsGetThreadId(v9);
    else
      ThreadId = -1;
    *(_DWORD *)&v14[16] = ThreadId;
    *((_QWORD *)&v13 + 1) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)v14 = *(_QWORD *)(*((_QWORD *)&v13 + 1) + 24LL);
    v16[0] = &v13;
    v16[1] = 40;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v15);
    v12 = &v15;
    if ( ActivityIdCallbackData < 0 )
      v12 = 0;
    v7(*(_QWORD *)(a1 + 8), v16, 1, 0x4000000, a4, v12);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140001c60  mov     [rsp+arg_8], rbx
0x140001c65  push    rbp
0x140001c66  push    rsi
0x140001c67  push    rdi
0x140001c68  sub     rsp, 90h
0x140001c6f  mov     rax, cs:__security_cookie
0x140001c76  xor     rax, rsp
0x140001c79  mov     [rsp+0A8h+var_20], rax
0x140001c81  mov     rbx, cs:qword_140009A00
0x140001c88  xorps   xmm0, xmm0
0x140001c8b  xor     eax, eax
0x140001c8d  movzx   ebp, r9w
0x140001c91  movups  [rsp+0A8h+var_68], xmm0
0x140001c96  mov     [rsp+0A8h+var_48], rax
0x140001c9b  mov     rsi, rdx
0x140001c9e  movups  [rsp+0A8h+var_58], xmm0
0x140001ca3  mov     rdi, rcx
0x140001ca6  movups  [rsp+0A8h+var_40], xmm0
0x140001cab  mov     rbx, [rbx+10h]
0x140001caf  test    rbx, rbx
0x140001cb2  jnz     short loc_140001CEB
0x140001cb4  mov     rax, cs:qword_140009A00
0x140001cbb  mov     rcx, [rax+18h]
0x140001cbf  xor     eax, eax
0x140001cc1  test    rcx, rcx
0x140001cc4  setz    al
0x140001cc7  mov     rcx, [rsp+0A8h+var_20]
0x140001ccf  xor     rcx, rsp; StackCookie
0x140001cd2  call    __security_check_cookie
0x140001cd7  mov     rbx, [rsp+0A8h+arg_8]
0x140001cdf  add     rsp, 90h
0x140001ce6  pop     rdi
0x140001ce7  pop     rsi
0x140001ce8  pop     rbp
0x140001ce9  retn
0x140001ceb  mov     rcx, [rcx+8]; Thread
0x140001cef  mov     qword ptr [rsp+0A8h+var_68+8], rax
0x140001cf4  mov     qword ptr [rsp+0A8h+var_58], rax
0x140001cf9  mov     qword ptr [rsp+0A8h+var_68], rdi
0x140001cfe  movdqu  [rsp+0A8h+var_58+8], xmm0
0x140001d04  test    rcx, rcx
0x140001d07  jz      loc_140001D92
0x140001d0d  call    cs:__imp_PsGetThreadId
0x140001d14  nop     dword ptr [rax+rax+00h]
0x140001d19  mov     dword ptr [rsp+0A8h+var_48], eax
0x140001d1d  lea     rdx, [rsp+0A8h+var_40]
0x140001d22  mov     rax, [rsi+20h]
0x140001d26  mov     rcx, rdi
0x140001d29  mov     qword ptr [rsp+0A8h+var_68+8], rax
0x140001d2e  mov     rax, [rax+18h]
0x140001d32  mov     qword ptr [rsp+0A8h+var_58], rax
0x140001d37  lea     rax, [rsp+0A8h+var_68]
0x140001d3c  mov     [rsp+0A8h+var_30], rax
0x140001d41  mov     [rsp+0A8h+var_28], 28h ; '('
0x140001d4d  call    cs:__imp_FltGetActivityIdCallbackData
0x140001d54  nop     dword ptr [rax+rax+00h]
0x140001d59  xor     ecx, ecx
0x140001d5b  lea     rdx, [rsp+0A8h+var_40]
0x140001d60  test    eax, eax
0x140001d62  mov     r9d, 4000000h
0x140001d68  mov     r8d, 1
0x140001d6e  mov     rax, rbx
0x140001d71  cmovs   rdx, rcx
0x140001d75  mov     rcx, [rdi+8]
0x140001d79  mov     [rsp+0A8h+var_80], rdx
0x140001d7e  lea     rdx, [rsp+0A8h+var_30]
0x140001d83  mov     [rsp+0A8h+var_88], bp
0x140001d88  call    _guard_dispatch_icall
0x140001d8d  jmp     loc_140001CB4
0x140001d92  mov     eax, 0FFFFFFFFh
0x140001d97  jmp     short loc_140001D19
```
