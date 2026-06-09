# FIPreCleanupCallback

- ea: `0x140012a90`
- end: `0x140012bd1`
- name: `FIPreCleanupCallback`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003920`
- `0x140003a00`
- `0x140012a90`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140012b0e`
- `ntoskrnl!PsGetThreadId` at `0x140012b0e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140012b4b`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140012b4b`

## pseudocode

```c
__int64 __fastcall FIPreCleanupCallback(__int64 a1, __int64 a2)
{
  void (__fastcall *v4)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  struct _KTHREAD *v5; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v8; // rdx
  __int64 v10; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-50h]
  __int64 v12; // [rsp+50h] [rbp-48h]
  unsigned int v13; // [rsp+58h] [rbp-40h]
  __int128 v14; // [rsp+60h] [rbp-38h] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp-28h] BYREF

  if ( !*(_QWORD *)(qword_140009A00 + 16) )
    return 0;
  v14 = 0;
  v4 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( !v4 )
    return 0;
  v5 = *(struct _KTHREAD **)(a1 + 8);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v10 = a1;
  if ( v5 )
    ThreadId = (unsigned int)PsGetThreadId(v5);
  else
    ThreadId = -1;
  v13 = ThreadId;
  v11 = *(_QWORD *)(a2 + 32);
  v12 = *(_QWORD *)(v11 + 24);
  v15[0] = &v10;
  v15[1] = 28;
  ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v14);
  v8 = &v14;
  if ( ActivityIdCallbackData < 0 )
    v8 = 0;
  v4(*(_QWORD *)(a1 + 8), v15, 1, 0x4000000, 1089, v8);
  return 0;
}

```

## disassembly

```asm
0x140012a90  mov     r11, rsp
0x140012a93  mov     [r11+20h], rbx
0x140012a97  push    rsi
0x140012a98  sub     rsp, 90h
0x140012a9f  mov     rax, cs:__security_cookie
0x140012aa6  xor     rax, rsp
0x140012aa9  mov     [rsp+98h+var_18], rax
0x140012ab1  mov     rax, cs:qword_140009A00
0x140012ab8  mov     rbx, rcx
0x140012abb  mov     rsi, rdx
0x140012abe  mov     rcx, [rax+10h]
0x140012ac2  test    rcx, rcx
0x140012ac5  jz      loc_140012BBF
0x140012acb  mov     rax, cs:qword_140009A00
0x140012ad2  xorps   xmm0, xmm0
0x140012ad5  mov     [r11+18h], rdi
0x140012ad9  movups  [rsp+98h+var_38], xmm0
0x140012ade  mov     rdi, [rax+10h]
0x140012ae2  test    rdi, rdi
0x140012ae5  jz      loc_140012BCD
0x140012aeb  mov     rcx, [rbx+8]; Thread
0x140012aef  mov     [r11+10h], rbp
0x140012af3  xor     ebp, ebp
0x140012af5  mov     [r11-50h], rbp
0x140012af9  mov     [r11-48h], rbp
0x140012afd  mov     [rsp+98h+var_40], ebp
0x140012b01  mov     [r11-58h], rbx
0x140012b05  test    rcx, rcx
0x140012b08  jz      loc_140012BC3
0x140012b0e  call    cs:__imp_PsGetThreadId
0x140012b15  nop     dword ptr [rax+rax+00h]
0x140012b1a  mov     [rsp+98h+var_40], eax
0x140012b1e  lea     rdx, [rsp+98h+var_38]
0x140012b23  mov     rax, [rsi+20h]
0x140012b27  mov     rcx, rbx
0x140012b2a  mov     [rsp+98h+var_50], rax
0x140012b2f  mov     rax, [rax+18h]
0x140012b33  mov     [rsp+98h+var_48], rax
0x140012b38  lea     rax, [rsp+98h+var_58]
0x140012b3d  mov     [rsp+98h+var_28], rax
0x140012b42  mov     [rsp+98h+var_20], 1Ch
0x140012b4b  call    cs:__imp_FltGetActivityIdCallbackData
0x140012b52  nop     dword ptr [rax+rax+00h]
0x140012b57  mov     rcx, [rbx+8]
0x140012b5b  lea     rdx, [rsp+98h+var_38]
0x140012b60  test    eax, eax
0x140012b62  mov     r9d, 4000000h
0x140012b68  mov     r8d, 1
0x140012b6e  mov     rax, rdi
0x140012b71  cmovs   rdx, rbp
0x140012b75  mov     [rsp+98h+var_70], rdx
0x140012b7a  lea     rdx, [rsp+98h+var_28]
0x140012b7f  mov     [rsp+98h+var_78], 441h
0x140012b86  call    _guard_dispatch_icall
0x140012b8b  mov     rbp, [rsp+98h+arg_8]
0x140012b93  xor     eax, eax
0x140012b95  mov     rdi, [rsp+98h+arg_10]
0x140012b9d  mov     rcx, [rsp+98h+var_18]
0x140012ba5  xor     rcx, rsp; StackCookie
0x140012ba8  call    __security_check_cookie
0x140012bad  mov     rbx, [rsp+98h+arg_18]
0x140012bb5  add     rsp, 90h
0x140012bbc  pop     rsi
0x140012bbd  retn
0x140012bbf  xor     eax, eax
0x140012bc1  jmp     short loc_140012B9D
0x140012bc3  mov     eax, 0FFFFFFFFh
0x140012bc8  jmp     loc_140012B1A
0x140012bcd  xor     eax, eax
0x140012bcf  jmp     short loc_140012B95
```
