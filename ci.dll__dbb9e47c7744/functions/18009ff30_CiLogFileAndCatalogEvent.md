# CiLogFileAndCatalogEvent

- ea: `0x18009ff30`
- end: `0x1800a002e`
- name: `CiLogFileAndCatalogEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009e3e4`

## callees

- `0x18002bf20`
- `0x18009ff30`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009ff6c`
- `ntoskrnl!EtwEventEnabled` at `0x18009ff6c`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009ffe1`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009ffe1`
- `ntoskrnl!EtwWrite` at `0x1800a0009`
- `ntoskrnl!EtwWrite` at `0x1800a0009`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileAndCatalogEvent(unsigned __int16 *a1, unsigned __int16 *a2, const EVENT_DESCRIPTOR *a3)
{
  unsigned __int16 v7; // ax
  __int64 v8; // rcx
  const GUID *ActivityIdThread; // rax
  __int16 v10; // [rsp+30h] [rbp-29h] BYREF
  __int16 v11; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-19h] BYREF
  __int64 v13; // [rsp+50h] [rbp-9h]
  int v14; // [rsp+58h] [rbp-1h]
  int v15; // [rsp+5Ch] [rbp+3h]
  __int16 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int64 v18; // [rsp+70h] [rbp+17h]
  int v19; // [rsp+78h] [rbp+1Fh]
  int v20; // [rsp+7Ch] [rbp+23h]

  v10 = 0;
  v11 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, a3) )
    return 0;
  v7 = *a1;
  v14 = *a1;
  v8 = *a2;
  v10 = v7 >> 1;
  UserData.Ptr = (ULONGLONG)&v10;
  v13 = *((_QWORD *)a1 + 1);
  v11 = (unsigned __int16)v8 >> 1;
  v16 = &v11;
  v18 = *((_QWORD *)a2 + 1);
  *(_QWORD *)&UserData.Size = 2;
  v15 = 0;
  v17 = 2;
  v19 = v8;
  v20 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v8);
  return EtwWrite(g_EtwEventHandle, a3, ActivityIdThread, 4u, &UserData);
}

```

## disassembly

```asm
0x18009ff30  push    rbp
0x18009ff32  push    rbx
0x18009ff33  push    rsi
0x18009ff34  push    rdi
0x18009ff35  lea     rbp, [rsp-3Fh]
0x18009ff3a  sub     rsp, 98h
0x18009ff41  mov     rax, cs:__security_cookie
0x18009ff48  xor     rax, rsp
0x18009ff4b  mov     [rbp+57h+var_30], rax
0x18009ff4f  xor     eax, eax
0x18009ff51  mov     rdi, rdx
0x18009ff54  mov     rsi, rcx
0x18009ff57  mov     [rbp+57h+var_80], ax
0x18009ff5b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009ff62  mov     rdx, r8; EventDescriptor
0x18009ff65  mov     [rbp+57h+var_7C], ax
0x18009ff69  mov     rbx, r8
0x18009ff6c  call    cs:__imp_EtwEventEnabled
0x18009ff73  nop     dword ptr [rax+rax+00h]
0x18009ff78  test    al, al
0x18009ff7a  jnz     short loc_18009FF83
0x18009ff7c  xor     eax, eax
0x18009ff7e  jmp     loc_1800A0015
0x18009ff83  movzx   ecx, word ptr [rsi]
0x18009ff86  movzx   eax, cx
0x18009ff89  mov     [rbp+57h+var_58], ecx
0x18009ff8c  movzx   ecx, word ptr [rdi]
0x18009ff8f  shr     ax, 1
0x18009ff92  mov     [rbp+57h+var_80], ax
0x18009ff96  lea     rax, [rbp+57h+var_80]
0x18009ff9a  mov     [rbp+57h+var_70.Ptr], rax
0x18009ff9e  mov     rax, [rsi+8]
0x18009ffa2  mov     [rbp+57h+var_60], rax
0x18009ffa6  movzx   eax, cx
0x18009ffa9  shr     ax, 1
0x18009ffac  mov     [rbp+57h+var_7C], ax
0x18009ffb0  lea     rax, [rbp+57h+var_7C]
0x18009ffb4  mov     [rbp+57h+var_50], rax
0x18009ffb8  mov     rax, [rdi+8]
0x18009ffbc  mov     [rbp+57h+var_40], rax
0x18009ffc0  mov     qword ptr [rbp+57h+var_70.Size], 2
0x18009ffc8  mov     [rbp+57h+var_54], 0
0x18009ffcf  mov     [rbp+57h+var_48], 2
0x18009ffd7  mov     [rbp+57h+var_38], ecx
0x18009ffda  mov     [rbp+57h+var_34], 0
0x18009ffe1  call    cs:__imp_IoGetActivityIdThread
0x18009ffe8  nop     dword ptr [rax+rax+00h]
0x18009ffed  lea     rcx, [rbp+57h+var_70]
0x18009fff1  mov     r9d, 4; UserDataCount
0x18009fff7  mov     [rsp+0B0h+UserData], rcx; UserData
0x18009fffc  mov     r8, rax; ActivityId
0x18009ffff  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a0006  mov     rdx, rbx; EventDescriptor
0x1800a0009  call    cs:__imp_EtwWrite
0x1800a0010  nop     dword ptr [rax+rax+00h]
0x1800a0015  mov     rcx, [rbp+57h+var_30]
0x1800a0019  xor     rcx, rsp; StackCookie
0x1800a001c  call    __security_check_cookie
0x1800a0021  add     rsp, 98h
0x1800a0028  pop     rdi
0x1800a0029  pop     rsi
0x1800a002a  pop     rbx
0x1800a002b  pop     rbp
0x1800a002c  retn
```
