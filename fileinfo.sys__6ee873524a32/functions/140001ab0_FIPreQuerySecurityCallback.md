# FIPreQuerySecurityCallback

- ea: `0x140001ab0`
- end: `0x140001bef`
- name: `FIPreQuerySecurityCallback`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001ab0`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140001b5e`
- `ntoskrnl!PsGetThreadId` at `0x140001b5e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001b9e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001b9e`

## pseudocode

```c
_BOOL8 __fastcall FIPreQuerySecurityCallback(unsigned __int64 a1, __int64 a2)
{
  void (__fastcall *v4)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rbx
  struct _KTHREAD *v6; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v9; // rdx
  __int128 v10; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v11[24]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v12; // [rsp+68h] [rbp-30h] BYREF
  _QWORD v13[2]; // [rsp+78h] [rbp-20h] BYREF

  v10 = 0;
  memset(v11, 0, sizeof(v11));
  v12 = 0;
  v4 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v4 )
  {
    v6 = *(struct _KTHREAD **)(a1 + 8);
    memset(v11, 0, sizeof(v11));
    v10 = a1;
    if ( v6 )
      ThreadId = (unsigned int)PsGetThreadId(v6);
    else
      ThreadId = -1;
    *(_DWORD *)&v11[16] = ThreadId;
    *((_QWORD *)&v10 + 1) = *(_QWORD *)(a2 + 32);
    *(_QWORD *)v11 = *(_QWORD *)(*((_QWORD *)&v10 + 1) + 24LL);
    v13[0] = &v10;
    v13[1] = 40;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v12);
    v9 = &v12;
    if ( ActivityIdCallbackData < 0 )
      v9 = 0;
    v4(*(_QWORD *)(a1 + 8), v13, 1, 0x4000000, 1108, v9);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140001ab0  mov     [rsp+arg_8], rbx
0x140001ab5  mov     [rsp+arg_10], rsi
0x140001aba  push    rdi
0x140001abb  sub     rsp, 90h
0x140001ac2  mov     rax, cs:__security_cookie
0x140001ac9  xor     rax, rsp
0x140001acc  mov     [rsp+98h+var_10], rax
0x140001ad4  mov     rbx, cs:qword_140009A00
0x140001adb  xorps   xmm0, xmm0
0x140001ade  xor     eax, eax
0x140001ae0  mov     rsi, rdx
0x140001ae3  movups  [rsp+98h+var_58], xmm0
0x140001ae8  mov     [rsp+98h+var_38], rax
0x140001aed  mov     rdi, rcx
0x140001af0  movups  [rsp+98h+var_48], xmm0
0x140001af5  movups  [rsp+98h+var_30], xmm0
0x140001afa  mov     rbx, [rbx+10h]
0x140001afe  test    rbx, rbx
0x140001b01  jnz     short loc_140001B3C
0x140001b03  mov     rax, cs:qword_140009A00
0x140001b0a  mov     rcx, [rax+18h]
0x140001b0e  xor     eax, eax
0x140001b10  test    rcx, rcx
0x140001b13  setz    al
0x140001b16  mov     rcx, [rsp+98h+var_10]
0x140001b1e  xor     rcx, rsp; StackCookie
0x140001b21  call    __security_check_cookie
0x140001b26  lea     r11, [rsp+98h+var_8]
0x140001b2e  mov     rbx, [r11+18h]
0x140001b32  mov     rsi, [r11+20h]
0x140001b36  mov     rsp, r11
0x140001b39  pop     rdi
0x140001b3a  retn
0x140001b3c  mov     rcx, [rcx+8]; Thread
0x140001b40  mov     qword ptr [rsp+98h+var_58+8], rax
0x140001b45  mov     qword ptr [rsp+98h+var_48], rax
0x140001b4a  mov     qword ptr [rsp+98h+var_58], rdi
0x140001b4f  movdqu  [rsp+98h+var_48+8], xmm0
0x140001b55  test    rcx, rcx
0x140001b58  jz      loc_140001BE5
0x140001b5e  call    cs:__imp_PsGetThreadId
0x140001b65  nop     dword ptr [rax+rax+00h]
0x140001b6a  mov     dword ptr [rsp+98h+var_38], eax
0x140001b6e  lea     rdx, [rsp+98h+var_30]
0x140001b73  mov     rax, [rsi+20h]
0x140001b77  mov     rcx, rdi
0x140001b7a  mov     qword ptr [rsp+98h+var_58+8], rax
0x140001b7f  mov     rax, [rax+18h]
0x140001b83  mov     qword ptr [rsp+98h+var_48], rax
0x140001b88  lea     rax, [rsp+98h+var_58]
0x140001b8d  mov     [rsp+98h+var_20], rax
0x140001b92  mov     [rsp+98h+var_18], 28h ; '('
0x140001b9e  call    cs:__imp_FltGetActivityIdCallbackData
0x140001ba5  nop     dword ptr [rax+rax+00h]
0x140001baa  xor     ecx, ecx
0x140001bac  lea     rdx, [rsp+98h+var_30]
0x140001bb1  test    eax, eax
0x140001bb3  mov     r9d, 4000000h
0x140001bb9  mov     r8d, 1
0x140001bbf  mov     rax, rbx
0x140001bc2  cmovs   rdx, rcx
0x140001bc6  mov     rcx, [rdi+8]
0x140001bca  mov     [rsp+98h+var_70], rdx
0x140001bcf  lea     rdx, [rsp+98h+var_20]
0x140001bd4  mov     [rsp+98h+var_78], 454h
0x140001bdb  call    _guard_dispatch_icall
0x140001be0  jmp     loc_140001B03
0x140001be5  mov     eax, 0FFFFFFFFh
0x140001bea  jmp     loc_140001B6A
```
