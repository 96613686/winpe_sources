# FIETWLogSimpleOperationInit

- ea: `0x140014e00`
- end: `0x140014f28`
- name: `FIETWLogSimpleOperationInit`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014dc0`

## callees

- `0x140003920`
- `0x140003a00`
- `0x140014e00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140014e77`
- `ntoskrnl!PsGetThreadId` at `0x140014e77`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014eb4`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014eb4`

## pseudocode

```c
__int64 __fastcall FIETWLogSimpleOperationInit(unsigned __int64 a1, __int64 a2, __int16 a3)
{
  __int64 result; // rax
  __int64 (__fastcall *v7)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  struct _KTHREAD *v8; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v11; // rdx
  _OWORD v12[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v13; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+70h] [rbp-38h] BYREF

  result = qword_140009A00;
  memset(v12, 0, 28);
  v13 = 0;
  v7 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v7 )
  {
    v12[0] = a1;
    v8 = *(struct _KTHREAD **)(a1 + 8);
    *(_QWORD *)&v12[1] = 0;
    DWORD2(v12[1]) = 0;
    if ( v8 )
      ThreadId = (unsigned int)PsGetThreadId(v8);
    else
      ThreadId = -1;
    DWORD2(v12[1]) = ThreadId;
    *((_QWORD *)&v12[0] + 1) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)&v12[1] = *(_QWORD *)(*((_QWORD *)&v12[0] + 1) + 24LL);
    v14[0] = v12;
    v14[1] = 28;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v13);
    v11 = &v13;
    if ( ActivityIdCallbackData < 0 )
      v11 = 0;
    return v7(*(_QWORD *)(a1 + 8), v14, 1, 0x4000000, a3, v11);
  }
  return result;
}

```

## disassembly

```asm
0x140014e00  mov     r11, rsp
0x140014e03  mov     [r11+20h], rbx
0x140014e07  push    rbp
0x140014e08  push    rsi
0x140014e09  push    rdi
0x140014e0a  sub     rsp, 90h
0x140014e11  mov     rax, cs:__security_cookie
0x140014e18  xor     rax, rsp
0x140014e1b  mov     [rsp+0A8h+var_28], rax
0x140014e23  mov     rax, cs:qword_140009A00
0x140014e2a  xorps   xmm0, xmm0
0x140014e2d  movups  [rsp+0A8h+var_68], xmm0
0x140014e32  movzx   ebp, r8w
0x140014e36  mov     rsi, rdx
0x140014e39  movups  [rsp+0A8h+var_68+0Ch], xmm0
0x140014e3e  mov     rbx, rcx
0x140014e41  movups  [rsp+0A8h+var_48], xmm0
0x140014e46  mov     rdi, [rax+10h]
0x140014e4a  test    rdi, rdi
0x140014e4d  jz      loc_140014EFA
0x140014e53  mov     [r11+10h], r14
0x140014e57  xor     r14d, r14d
0x140014e5a  mov     [r11-68h], rcx
0x140014e5e  mov     rcx, [rcx+8]; Thread
0x140014e62  mov     [r11-60h], r14
0x140014e66  mov     [r11-58h], r14
0x140014e6a  mov     [r11-50h], r14d
0x140014e6e  test    rcx, rcx
0x140014e71  jz      loc_140014F1E
0x140014e77  call    cs:__imp_PsGetThreadId
0x140014e7e  nop     dword ptr [rax+rax+00h]
0x140014e83  mov     [rsp+0A8h+var_50], eax
0x140014e87  lea     rdx, [rsp+0A8h+var_48]
0x140014e8c  mov     rax, [rsi+20h]
0x140014e90  mov     rcx, rbx
0x140014e93  mov     qword ptr [rsp+0A8h+var_68+8], rax
0x140014e98  mov     rax, [rax+18h]
0x140014e9c  mov     [rsp+0A8h+var_58], rax
0x140014ea1  lea     rax, [rsp+0A8h+var_68]
0x140014ea6  mov     [rsp+0A8h+var_38], rax
0x140014eab  mov     [rsp+0A8h+var_30], 1Ch
0x140014eb4  call    cs:__imp_FltGetActivityIdCallbackData
0x140014ebb  nop     dword ptr [rax+rax+00h]
0x140014ec0  mov     rcx, [rbx+8]
0x140014ec4  lea     rdx, [rsp+0A8h+var_48]
0x140014ec9  test    eax, eax
0x140014ecb  mov     r9d, 4000000h
0x140014ed1  mov     r8d, 1
0x140014ed7  mov     rax, rdi
0x140014eda  cmovs   rdx, r14
0x140014ede  mov     [rsp+0A8h+var_80], rdx
0x140014ee3  lea     rdx, [rsp+0A8h+var_38]
0x140014ee8  mov     [rsp+0A8h+var_88], bp
0x140014eed  call    _guard_dispatch_icall
0x140014ef2  mov     r14, [rsp+0A8h+arg_8]
0x140014efa  mov     rcx, [rsp+0A8h+var_28]
0x140014f02  xor     rcx, rsp; StackCookie
0x140014f05  call    __security_check_cookie
0x140014f0a  mov     rbx, [rsp+0A8h+arg_18]
0x140014f12  add     rsp, 90h
0x140014f19  pop     rdi
0x140014f1a  pop     rsi
0x140014f1b  pop     rbp
0x140014f1c  retn
0x140014f1e  mov     eax, 0FFFFFFFFh
0x140014f23  jmp     loc_140014E83
```
