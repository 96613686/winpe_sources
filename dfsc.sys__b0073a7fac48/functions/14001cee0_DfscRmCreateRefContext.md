# DfscRmCreateRefContext

- ea: `0x14001cee0`
- end: `0x14001cfc5`
- name: `DfscRmCreateRefContext`
- size: `229`
- prototype: `__int64 __fastcall(__int64, char, __int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140002cd0`
- `0x140003020`
- `0x14001abc0`
- `0x14001b230`
- `0x140022840`

## callees

- `0x1400050fc`
- `0x14001cee0`
- `0x14001cfd0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001cf04`
- `ntoskrnl!ExAllocatePool2` at `0x14001cf04`

## pseudocode

```c
__int64 __fastcall DfscRmCreateRefContext(__int64 a1, char a2, __int64 *a3)
{
  int v6; // edx
  __int64 Pool2; // rbx
  int v8; // r8d
  __int64 result; // rax

  Pool2 = ExAllocatePool2(258, 40, 1648584260);
  if ( !Pool2 )
    return 3221225626LL;
  *(_QWORD *)(Pool2 + 8) = 0;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)Pool2 = 2654467;
  *(_DWORD *)(Pool2 + 4) = 1;
  *(_QWORD *)(Pool2 + 16) = a1;
  if ( a2 )
    DfscRmIsTimeToRefresh(Pool2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qqDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      Pool2,
      *(_QWORD *)(Pool2 + 16),
      *(_DWORD *)(Pool2 + 8),
      a1 + 144);
  if ( !*(_DWORD *)(a1 + 8) && !*(_WORD *)(a1 + 24) )
    *(_DWORD *)(Pool2 + 8) |= 2u;
  *(_WORD *)(Pool2 + 32) = -1;
  result = 0;
  *a3 = Pool2;
  return result;
}

```

## disassembly

```asm
0x14001cee0  push    rbx
0x14001cee2  push    rbp
0x14001cee3  push    rsi
0x14001cee4  push    rdi
0x14001cee5  push    r14
0x14001cee7  sub     rsp, 40h
0x14001ceeb  mov     rsi, r8
0x14001ceee  movzx   ebp, dl
0x14001cef1  mov     rdi, rcx
0x14001cef4  mov     edx, 28h ; '('
0x14001cef9  mov     ecx, 102h
0x14001cefe  mov     r8d, 62436644h
0x14001cf04  call    cs:__imp_ExAllocatePool2
0x14001cf0b  nop     dword ptr [rax+rax+00h]
0x14001cf10  mov     rbx, rax
0x14001cf13  test    rax, rax
0x14001cf16  jz      short loc_14001CF7D
0x14001cf18  xor     eax, eax
0x14001cf1a  mov     [rbx+8], rax
0x14001cf1e  mov     [rbx+18h], rax
0x14001cf22  mov     [rbx+20h], rax
0x14001cf26  mov     dword ptr [rbx], 288103h
0x14001cf2c  mov     dword ptr [rbx+4], 1
0x14001cf33  mov     [rbx+10h], rdi
0x14001cf37  test    bpl, bpl
0x14001cf3a  jz      short loc_14001CF44
0x14001cf3c  mov     rcx, rbx
0x14001cf3f  call    DfscRmIsTimeToRefresh
0x14001cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf4b  lea     rax, WPP_GLOBAL_Control
0x14001cf52  cmp     rcx, rax
0x14001cf55  jz      short loc_14001CF60
0x14001cf57  test    dword ptr [rcx+2Ch], 400000h
0x14001cf5e  jnz     short loc_14001CF8E
0x14001cf60  cmp     dword ptr [rdi+8], 0
0x14001cf64  jz      short loc_14001CFB8
0x14001cf66  mov     word ptr [rbx+20h], 0FFFFh
0x14001cf6c  xor     eax, eax
0x14001cf6e  mov     [rsi], rbx
0x14001cf71  add     rsp, 40h
0x14001cf75  pop     r14
0x14001cf77  pop     rdi
0x14001cf78  pop     rsi
0x14001cf79  pop     rbp
0x14001cf7a  pop     rbx
0x14001cf7b  retn
0x14001cf7d  mov     eax, 0C000009Ah
0x14001cf82  add     rsp, 40h
0x14001cf86  pop     r14
0x14001cf88  pop     rdi
0x14001cf89  pop     rsi
0x14001cf8a  pop     rbp
0x14001cf8b  pop     rbx
0x14001cf8c  retn
0x14001cf8e  mov     rcx, [rcx+18h]
0x14001cf92  lea     rax, [rdi+90h]
0x14001cf99  mov     [rsp+68h+var_38], rax
0x14001cf9e  mov     r9, rbx
0x14001cfa1  mov     eax, [rbx+8]
0x14001cfa4  mov     [rsp+68h+var_40], eax
0x14001cfa8  mov     rax, [rbx+10h]
0x14001cfac  mov     [rsp+68h+var_48], rax
0x14001cfb1  call    WPP_SF_qqDZ
0x14001cfb6  jmp     short loc_14001CF60
0x14001cfb8  cmp     word ptr [rdi+18h], 0
0x14001cfbd  jnz     short loc_14001CF66
0x14001cfbf  or      dword ptr [rbx+8], 2
0x14001cfc3  jmp     short loc_14001CF66
```
