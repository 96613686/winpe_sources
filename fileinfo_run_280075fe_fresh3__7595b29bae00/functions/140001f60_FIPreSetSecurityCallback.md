# FIPreSetSecurityCallback

- ea: `0x140001f60`
- end: `0x14000209f`
- name: `FIPreSetSecurityCallback`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001f60`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14000200e`
- `ntoskrnl!PsGetThreadId` at `0x14000200e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x14000204e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x14000204e`

## pseudocode

```c
_BOOL8 __fastcall FIPreSetSecurityCallback(unsigned __int64 a1, __int64 a2)
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
    v4(*(_QWORD *)(a1 + 8), v13, 1, 0x4000000, 1107, v9);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140001f60  mov     [rsp+arg_8], rbx
0x140001f65  mov     [rsp+arg_10], rsi
0x140001f6a  push    rdi
0x140001f6b  sub     rsp, 90h
0x140001f72  mov     rax, cs:__security_cookie
0x140001f79  xor     rax, rsp
0x140001f7c  mov     [rsp+98h+var_10], rax
0x140001f84  mov     rbx, cs:qword_140009A00
0x140001f8b  xorps   xmm0, xmm0
0x140001f8e  xor     eax, eax
0x140001f90  mov     rsi, rdx
0x140001f93  movups  [rsp+98h+var_58], xmm0
0x140001f98  mov     [rsp+98h+var_38], rax
0x140001f9d  mov     rdi, rcx
0x140001fa0  movups  [rsp+98h+var_48], xmm0
0x140001fa5  movups  [rsp+98h+var_30], xmm0
0x140001faa  mov     rbx, [rbx+10h]
0x140001fae  test    rbx, rbx
0x140001fb1  jnz     short loc_140001FEC
0x140001fb3  mov     rax, cs:qword_140009A00
0x140001fba  mov     rcx, [rax+18h]
0x140001fbe  xor     eax, eax
0x140001fc0  test    rcx, rcx
0x140001fc3  setz    al
0x140001fc6  mov     rcx, [rsp+98h+var_10]
0x140001fce  xor     rcx, rsp; StackCookie
0x140001fd1  call    __security_check_cookie
0x140001fd6  lea     r11, [rsp+98h+var_8]
0x140001fde  mov     rbx, [r11+18h]
0x140001fe2  mov     rsi, [r11+20h]
0x140001fe6  mov     rsp, r11
0x140001fe9  pop     rdi
0x140001fea  retn
0x140001fec  mov     rcx, [rcx+8]; Thread
0x140001ff0  mov     qword ptr [rsp+98h+var_58+8], rax
0x140001ff5  mov     qword ptr [rsp+98h+var_48], rax
0x140001ffa  mov     qword ptr [rsp+98h+var_58], rdi
0x140001fff  movdqu  [rsp+98h+var_48+8], xmm0
0x140002005  test    rcx, rcx
0x140002008  jz      loc_140002095
0x14000200e  call    cs:__imp_PsGetThreadId
0x140002015  nop     dword ptr [rax+rax+00h]
0x14000201a  mov     dword ptr [rsp+98h+var_38], eax
0x14000201e  lea     rdx, [rsp+98h+var_30]
0x140002023  mov     rax, [rsi+20h]
0x140002027  mov     rcx, rdi
0x14000202a  mov     qword ptr [rsp+98h+var_58+8], rax
0x14000202f  mov     rax, [rax+18h]
0x140002033  mov     qword ptr [rsp+98h+var_48], rax
0x140002038  lea     rax, [rsp+98h+var_58]
0x14000203d  mov     [rsp+98h+var_20], rax
0x140002042  mov     [rsp+98h+var_18], 28h ; '('
0x14000204e  call    cs:__imp_FltGetActivityIdCallbackData
0x140002055  nop     dword ptr [rax+rax+00h]
0x14000205a  xor     ecx, ecx
0x14000205c  lea     rdx, [rsp+98h+var_30]
0x140002061  test    eax, eax
0x140002063  mov     r9d, 4000000h
0x140002069  mov     r8d, 1
0x14000206f  mov     rax, rbx
0x140002072  cmovs   rdx, rcx
0x140002076  mov     rcx, [rdi+8]
0x14000207a  mov     [rsp+98h+var_70], rdx
0x14000207f  lea     rdx, [rsp+98h+var_20]
0x140002084  mov     [rsp+98h+var_78], 453h
0x14000208b  call    _guard_dispatch_icall
0x140002090  jmp     loc_140001FB3
0x140002095  mov     eax, 0FFFFFFFFh
0x14000209a  jmp     loc_14000201A
```
