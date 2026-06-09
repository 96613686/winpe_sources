# CiLogFileAndCatalogEvent

- ea: `0x18009e900`
- end: `0x18009e9fe`
- name: `CiLogFileAndCatalogEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009cdb4`

## callees

- `0x18002bef0`
- `0x18009e900`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009e93c`
- `ntoskrnl!EtwEventEnabled` at `0x18009e93c`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009e9b1`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009e9b1`
- `ntoskrnl!EtwWrite` at `0x18009e9d9`
- `ntoskrnl!EtwWrite` at `0x18009e9d9`

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
0x18009e900  push    rbp
0x18009e902  push    rbx
0x18009e903  push    rsi
0x18009e904  push    rdi
0x18009e905  lea     rbp, [rsp-3Fh]
0x18009e90a  sub     rsp, 98h
0x18009e911  mov     rax, cs:__security_cookie
0x18009e918  xor     rax, rsp
0x18009e91b  mov     [rbp+57h+var_30], rax
0x18009e91f  xor     eax, eax
0x18009e921  mov     rdi, rdx
0x18009e924  mov     rsi, rcx
0x18009e927  mov     [rbp+57h+var_80], ax
0x18009e92b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009e932  mov     rdx, r8; EventDescriptor
0x18009e935  mov     [rbp+57h+var_7C], ax
0x18009e939  mov     rbx, r8
0x18009e93c  call    cs:__imp_EtwEventEnabled
0x18009e943  nop     dword ptr [rax+rax+00h]
0x18009e948  test    al, al
0x18009e94a  jnz     short loc_18009E953
0x18009e94c  xor     eax, eax
0x18009e94e  jmp     loc_18009E9E5
0x18009e953  movzx   ecx, word ptr [rsi]
0x18009e956  movzx   eax, cx
0x18009e959  mov     [rbp+57h+var_58], ecx
0x18009e95c  movzx   ecx, word ptr [rdi]
0x18009e95f  shr     ax, 1
0x18009e962  mov     [rbp+57h+var_80], ax
0x18009e966  lea     rax, [rbp+57h+var_80]
0x18009e96a  mov     [rbp+57h+var_70.Ptr], rax
0x18009e96e  mov     rax, [rsi+8]
0x18009e972  mov     [rbp+57h+var_60], rax
0x18009e976  movzx   eax, cx
0x18009e979  shr     ax, 1
0x18009e97c  mov     [rbp+57h+var_7C], ax
0x18009e980  lea     rax, [rbp+57h+var_7C]
0x18009e984  mov     [rbp+57h+var_50], rax
0x18009e988  mov     rax, [rdi+8]
0x18009e98c  mov     [rbp+57h+var_40], rax
0x18009e990  mov     qword ptr [rbp+57h+var_70.Size], 2
0x18009e998  mov     [rbp+57h+var_54], 0
0x18009e99f  mov     [rbp+57h+var_48], 2
0x18009e9a7  mov     [rbp+57h+var_38], ecx
0x18009e9aa  mov     [rbp+57h+var_34], 0
0x18009e9b1  call    cs:__imp_IoGetActivityIdThread
0x18009e9b8  nop     dword ptr [rax+rax+00h]
0x18009e9bd  lea     rcx, [rbp+57h+var_70]
0x18009e9c1  mov     r9d, 4; UserDataCount
0x18009e9c7  mov     [rsp+0B0h+UserData], rcx; UserData
0x18009e9cc  mov     r8, rax; ActivityId
0x18009e9cf  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009e9d6  mov     rdx, rbx; EventDescriptor
0x18009e9d9  call    cs:__imp_EtwWrite
0x18009e9e0  nop     dword ptr [rax+rax+00h]
0x18009e9e5  mov     rcx, [rbp+57h+var_30]
0x18009e9e9  xor     rcx, rsp; StackCookie
0x18009e9ec  call    __security_check_cookie
0x18009e9f1  add     rsp, 98h
0x18009e9f8  pop     rdi
0x18009e9f9  pop     rsi
0x18009e9fa  pop     rbx
0x18009e9fb  pop     rbp
0x18009e9fc  retn
```
