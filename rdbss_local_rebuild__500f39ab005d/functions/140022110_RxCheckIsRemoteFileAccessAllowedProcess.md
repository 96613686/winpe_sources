# RxCheckIsRemoteFileAccessAllowedProcess

- ea: `0x140022110`
- end: `0x1400221ed`
- name: `RxCheckIsRemoteFileAccessAllowedProcess`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007a510`

## callees

- `0x140022110`
- `0x140025c20`

## import_xrefs

- `ntoskrnl!RtlInitializeSidEx` at `0x14002219e`
- `ntoskrnl!RtlInitializeSidEx` at `0x14002219e`
- `ntoskrnl!RtlCheckTokenCapability` at `0x1400221be`
- `ntoskrnl!RtlCheckTokenCapability` at `0x1400221be`

## pseudocode

```c
bool __fastcall RxCheckIsRemoteFileAccessAllowedProcess(__int64 a1)
{
  _BYTE v3[4]; // [rsp+70h] [rbp-58h] BYREF
  int v4; // [rsp+74h] [rbp-54h] BYREF
  __int16 v5; // [rsp+78h] [rbp-50h]
  _BYTE v6[48]; // [rsp+80h] [rbp-48h] BYREF

  v4 = 0;
  v5 = 3840;
  v3[0] = 0;
  return (int)RtlInitializeSidEx(v6, &v4, 10) >= 0 && (int)RtlCheckTokenCapability(a1, v6, v3) >= 0;
}

```

## disassembly

```asm
0x140022110  mov     r11, rsp
0x140022113  push    rbx
0x140022114  sub     rsp, 0C0h
0x14002211b  mov     rax, cs:__security_cookie
0x140022122  xor     rax, rsp
0x140022125  mov     [rsp+0C8h+var_18], rax
0x14002212d  mov     [rsp+0C8h+var_68], 0D9F74BF8h
0x140022135  lea     rdx, [r11-54h]
0x140022139  mov     [rsp+0C8h+var_70], 0D541522h
0x140022141  mov     r9d, 3
0x140022147  mov     [rsp+0C8h+var_78], 7CF7A57Ch
0x14002214f  mov     rbx, rcx
0x140022152  mov     [rsp+0C8h+var_80], 8C533294h
0x14002215a  lea     rcx, [r11-48h]
0x14002215e  mov     [rsp+0C8h+var_88], 9EE7B662h
0x140022166  mov     [rsp+0C8h+var_90], 0D83485C0h
0x14002216e  lea     r8d, [r9+7]
0x140022172  mov     [rsp+0C8h+var_98], 3B0B0B25h
0x14002217a  mov     [rsp+0C8h+var_A0], 55CCB487h
0x140022182  mov     [rsp+0C8h+var_A8], 400h
0x14002218a  mov     [rsp+0C8h+var_54], 0
0x140022192  mov     [rsp+0C8h+var_50], 0F00h
0x140022199  mov     [rsp+0C8h+var_58], 0
0x14002219e  call    cs:__imp_RtlInitializeSidEx
0x1400221a5  nop     dword ptr [rax+rax+00h]
0x1400221aa  test    eax, eax
0x1400221ac  js      short loc_1400221D1
0x1400221ae  lea     r8, [rsp+0C8h+var_58]
0x1400221b3  mov     rcx, rbx
0x1400221b6  lea     rdx, [rsp+0C8h+var_48]
0x1400221be  call    cs:__imp_RtlCheckTokenCapability
0x1400221c5  nop     dword ptr [rax+rax+00h]
0x1400221ca  test    eax, eax
0x1400221cc  setns   al
0x1400221cf  jmp     short loc_1400221D3
0x1400221d1  xor     al, al
0x1400221d3  mov     rcx, [rsp+0C8h+var_18]
0x1400221db  xor     rcx, rsp; StackCookie
0x1400221de  call    __security_check_cookie
0x1400221e3  add     rsp, 0C0h
0x1400221ea  pop     rbx
0x1400221eb  retn
```
