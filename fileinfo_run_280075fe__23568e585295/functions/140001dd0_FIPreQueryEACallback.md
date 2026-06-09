# FIPreQueryEACallback

- ea: `0x140001dd0`
- end: `0x140001f0f`
- name: `FIPreQueryEACallback`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001dd0`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140001e7e`
- `ntoskrnl!PsGetThreadId` at `0x140001e7e`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001ebe`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140001ebe`

## pseudocode

```c
_BOOL8 __fastcall FIPreQueryEACallback(unsigned __int64 a1, __int64 a2)
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
    v4(*(_QWORD *)(a1 + 8), v13, 1, 0x4000000, 1110, v9);
  }
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140001dd0  mov     [rsp+arg_8], rbx
0x140001dd5  mov     [rsp+arg_10], rsi
0x140001dda  push    rdi
0x140001ddb  sub     rsp, 90h
0x140001de2  mov     rax, cs:__security_cookie
0x140001de9  xor     rax, rsp
0x140001dec  mov     [rsp+98h+var_10], rax
0x140001df4  mov     rbx, cs:qword_140009A00
0x140001dfb  xorps   xmm0, xmm0
0x140001dfe  xor     eax, eax
0x140001e00  mov     rsi, rdx
0x140001e03  movups  [rsp+98h+var_58], xmm0
0x140001e08  mov     [rsp+98h+var_38], rax
0x140001e0d  mov     rdi, rcx
0x140001e10  movups  [rsp+98h+var_48], xmm0
0x140001e15  movups  [rsp+98h+var_30], xmm0
0x140001e1a  mov     rbx, [rbx+10h]
0x140001e1e  test    rbx, rbx
0x140001e21  jnz     short loc_140001E5C
0x140001e23  mov     rax, cs:qword_140009A00
0x140001e2a  mov     rcx, [rax+18h]
0x140001e2e  xor     eax, eax
0x140001e30  test    rcx, rcx
0x140001e33  setz    al
0x140001e36  mov     rcx, [rsp+98h+var_10]
0x140001e3e  xor     rcx, rsp; StackCookie
0x140001e41  call    __security_check_cookie
0x140001e46  lea     r11, [rsp+98h+var_8]
0x140001e4e  mov     rbx, [r11+18h]
0x140001e52  mov     rsi, [r11+20h]
0x140001e56  mov     rsp, r11
0x140001e59  pop     rdi
0x140001e5a  retn
0x140001e5c  mov     rcx, [rcx+8]; Thread
0x140001e60  mov     qword ptr [rsp+98h+var_58+8], rax
0x140001e65  mov     qword ptr [rsp+98h+var_48], rax
0x140001e6a  mov     qword ptr [rsp+98h+var_58], rdi
0x140001e6f  movdqu  [rsp+98h+var_48+8], xmm0
0x140001e75  test    rcx, rcx
0x140001e78  jz      loc_140001F05
0x140001e7e  call    cs:__imp_PsGetThreadId
0x140001e85  nop     dword ptr [rax+rax+00h]
0x140001e8a  mov     dword ptr [rsp+98h+var_38], eax
0x140001e8e  lea     rdx, [rsp+98h+var_30]
0x140001e93  mov     rax, [rsi+20h]
0x140001e97  mov     rcx, rdi
0x140001e9a  mov     qword ptr [rsp+98h+var_58+8], rax
0x140001e9f  mov     rax, [rax+18h]
0x140001ea3  mov     qword ptr [rsp+98h+var_48], rax
0x140001ea8  lea     rax, [rsp+98h+var_58]
0x140001ead  mov     [rsp+98h+var_20], rax
0x140001eb2  mov     [rsp+98h+var_18], 28h ; '('
0x140001ebe  call    cs:__imp_FltGetActivityIdCallbackData
0x140001ec5  nop     dword ptr [rax+rax+00h]
0x140001eca  xor     ecx, ecx
0x140001ecc  lea     rdx, [rsp+98h+var_30]
0x140001ed1  test    eax, eax
0x140001ed3  mov     r9d, 4000000h
0x140001ed9  mov     r8d, 1
0x140001edf  mov     rax, rbx
0x140001ee2  cmovs   rdx, rcx
0x140001ee6  mov     rcx, [rdi+8]
0x140001eea  mov     [rsp+98h+var_70], rdx
0x140001eef  lea     rdx, [rsp+98h+var_20]
0x140001ef4  mov     [rsp+98h+var_78], 456h
0x140001efb  call    _guard_dispatch_icall
0x140001f00  jmp     loc_140001E23
0x140001f05  mov     eax, 0FFFFFFFFh
0x140001f0a  jmp     loc_140001E8A
```
