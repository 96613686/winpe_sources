# CiLogFileRequestedValidationEventWithProcessName

- ea: `0x18009ec28`
- end: `0x18009ed5a`
- name: `CiLogFileRequestedValidationEventWithProcessName`
- size: `306`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009eb60`
- `0x1800e4cb8`

## callees

- `0x18002bef0`
- `0x18009ec28`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009ec71`
- `ntoskrnl!EtwEventEnabled` at `0x18009ec71`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009ed06`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009ed06`
- `ntoskrnl!EtwWrite` at `0x18009ed2e`
- `ntoskrnl!EtwWrite` at `0x18009ed2e`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileRequestedValidationEventWithProcessName(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        char a4,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  unsigned __int16 v9; // ax
  int v10; // ecx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+38h] [rbp-41h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-3Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-31h] BYREF
  __int64 v15; // [rsp+58h] [rbp-21h]
  int v16; // [rsp+60h] [rbp-19h]
  int v17; // [rsp+64h] [rbp-15h]
  int *v18; // [rsp+68h] [rbp-11h]
  __int64 v19; // [rsp+70h] [rbp-9h]
  char *v20; // [rsp+78h] [rbp-1h]
  __int64 v21; // [rsp+80h] [rbp+7h]
  __int16 *v22; // [rsp+88h] [rbp+Fh]
  __int64 v23; // [rsp+90h] [rbp+17h]
  __int64 v24; // [rsp+98h] [rbp+1Fh]
  int v25; // [rsp+A0h] [rbp+27h]
  int v26; // [rsp+A4h] [rbp+2Bh]
  int v27; // [rsp+E8h] [rbp+6Fh] BYREF
  char v28; // [rsp+F0h] [rbp+77h] BYREF

  v28 = a4;
  v27 = a3;
  v5 = EventDescriptor;
  v12 = 0;
  v13 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v9 = *a1;
  v16 = *a1;
  v10 = *a2;
  v12 = v9 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v15 = *((_QWORD *)a1 + 1);
  v18 = &v27;
  v20 = &v28;
  v13 = (unsigned __int16)v10 >> 1;
  v22 = &v13;
  v24 = *((_QWORD *)a2 + 1);
  *(_QWORD *)&UserData.Size = 2;
  v17 = 0;
  v19 = 4;
  v21 = 1;
  v23 = 2;
  v25 = v10;
  v26 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x18009ec28  mov     rax, rsp
0x18009ec2b  mov     [rax+8], rbx
0x18009ec2f  mov     [rax+20h], r9b
0x18009ec33  mov     [rax+18h], r8d
0x18009ec37  push    rbp
0x18009ec38  push    rsi
0x18009ec39  push    rdi
0x18009ec3a  lea     rbp, [rax-57h]
0x18009ec3e  sub     rsp, 0B0h
0x18009ec45  mov     rax, cs:__security_cookie
0x18009ec4c  xor     rax, rsp
0x18009ec4f  mov     [rbp+4Fh+var_20], rax
0x18009ec53  mov     rbx, [rbp+4Fh+EventDescriptor]
0x18009ec57  xor     eax, eax
0x18009ec59  mov     rdi, rdx
0x18009ec5c  mov     [rbp+4Fh+var_90], ax
0x18009ec60  mov     rsi, rcx
0x18009ec63  mov     [rbp+4Fh+var_8C], ax
0x18009ec67  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009ec6e  mov     rdx, rbx; EventDescriptor
0x18009ec71  call    cs:__imp_EtwEventEnabled
0x18009ec78  nop     dword ptr [rax+rax+00h]
0x18009ec7d  test    al, al
0x18009ec7f  jnz     short loc_18009EC88
0x18009ec81  xor     eax, eax
0x18009ec83  jmp     loc_18009ED3A
0x18009ec88  movzx   ecx, word ptr [rsi]
0x18009ec8b  movzx   eax, cx
0x18009ec8e  mov     [rbp+4Fh+var_68], ecx
0x18009ec91  movzx   ecx, word ptr [rdi]
0x18009ec94  shr     ax, 1
0x18009ec97  mov     [rbp+4Fh+var_90], ax
0x18009ec9b  lea     rax, [rbp+4Fh+var_90]
0x18009ec9f  mov     [rbp+4Fh+UserData.Ptr], rax
0x18009eca3  mov     rax, [rsi+8]
0x18009eca7  mov     [rbp+4Fh+var_70], rax
0x18009ecab  lea     rax, [rbp+4Fh+arg_10]
0x18009ecaf  mov     [rbp+4Fh+var_60], rax
0x18009ecb3  lea     rax, [rbp+4Fh+arg_18]
0x18009ecb7  mov     [rbp+4Fh+var_50], rax
0x18009ecbb  movzx   eax, cx
0x18009ecbe  shr     ax, 1
0x18009ecc1  mov     [rbp+4Fh+var_8C], ax
0x18009ecc5  lea     rax, [rbp+4Fh+var_8C]
0x18009ecc9  mov     [rbp+4Fh+var_40], rax
0x18009eccd  mov     rax, [rdi+8]
0x18009ecd1  mov     [rbp+4Fh+var_30], rax
0x18009ecd5  mov     qword ptr [rbp+4Fh+UserData.Size], 2
0x18009ecdd  mov     [rbp+4Fh+var_64], 0
0x18009ece4  mov     [rbp+4Fh+var_58], 4
0x18009ecec  mov     [rbp+4Fh+var_48], 1
0x18009ecf4  mov     [rbp+4Fh+var_38], 2
0x18009ecfc  mov     [rbp+4Fh+var_28], ecx
0x18009ecff  mov     [rbp+4Fh+var_24], 0
0x18009ed06  call    cs:__imp_IoGetActivityIdThread
0x18009ed0d  nop     dword ptr [rax+rax+00h]
0x18009ed12  lea     rcx, [rbp+4Fh+UserData]
0x18009ed16  mov     r9d, 6; UserDataCount
0x18009ed1c  mov     [rsp+20h], rcx; UserData
0x18009ed21  mov     r8, rax; ActivityId
0x18009ed24  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009ed2b  mov     rdx, rbx; EventDescriptor
0x18009ed2e  call    cs:__imp_EtwWrite
0x18009ed35  nop     dword ptr [rax+rax+00h]
0x18009ed3a  mov     rcx, [rbp+4Fh+var_20]
0x18009ed3e  xor     rcx, rsp; StackCookie
0x18009ed41  call    __security_check_cookie
0x18009ed46  mov     rbx, [rsp+0C0h+arg_0]
0x18009ed4e  add     rsp, 0B0h
0x18009ed55  pop     rdi
0x18009ed56  pop     rsi
0x18009ed57  pop     rbp
0x18009ed58  retn
```
