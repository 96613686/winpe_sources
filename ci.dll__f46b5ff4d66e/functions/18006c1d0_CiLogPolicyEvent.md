# CiLogPolicyEvent

- ea: `0x18006c1d0`
- end: `0x18006c312`
- name: `CiLogPolicyEvent`
- size: `322`
- prototype: `__int64 __fastcall(int, int, int, int, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180064068`
- `0x1800aae2c`
- `0x1800b3c18`

## callees

- `0x18002bef0`
- `0x18006c1d0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006c219`
- `ntoskrnl!EtwEventEnabled` at `0x18006c219`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c2be`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c2be`
- `ntoskrnl!EtwWrite` at `0x18006c2e6`
- `ntoskrnl!EtwWrite` at `0x18006c2e6`

## pseudocode

```c
NTSTATUS __fastcall CiLogPolicyEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        char a3,
        char a4,
        char a5,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v6; // rbx
  int v10; // ecx
  int v11; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v13; // [rsp+38h] [rbp-59h] BYREF
  __int16 v14; // [rsp+3Ch] [rbp-55h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-49h] BYREF
  __int64 v16; // [rsp+58h] [rbp-39h]
  int v17; // [rsp+60h] [rbp-31h]
  int v18; // [rsp+64h] [rbp-2Dh]
  __int16 *v19; // [rsp+68h] [rbp-29h]
  __int64 v20; // [rsp+70h] [rbp-21h]
  __int64 v21; // [rsp+78h] [rbp-19h]
  int v22; // [rsp+80h] [rbp-11h]
  int v23; // [rsp+84h] [rbp-Dh]
  char *v24; // [rsp+88h] [rbp-9h]
  __int64 v25; // [rsp+90h] [rbp-1h]
  char *v26; // [rsp+98h] [rbp+7h]
  __int64 v27; // [rsp+A0h] [rbp+Fh]
  char *v28; // [rsp+A8h] [rbp+17h]
  __int64 v29; // [rsp+B0h] [rbp+1Fh]
  char v30; // [rsp+F8h] [rbp+67h] BYREF
  char v31; // [rsp+100h] [rbp+6Fh] BYREF

  v31 = a4;
  v30 = a3;
  v6 = EventDescriptor;
  v13 = 0;
  v14 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v10 = *a1;
  v11 = *a2;
  v13 = *a1 >> 1;
  v14 = (unsigned __int16)v11 >> 1;
  UserData.Ptr = (ULONGLONG)&v13;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v14;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v30;
  v26 = &v31;
  v28 = &a5;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v10;
  v18 = 0;
  v20 = 2;
  v22 = v11;
  v23 = 0;
  v25 = 1;
  v27 = 1;
  v29 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v6, ActivityIdThread, 7u, &UserData);
}

```

## disassembly

```asm
0x18006c1d0  mov     rax, rsp
0x18006c1d3  mov     [rax+8], rbx
0x18006c1d7  mov     [rax+20h], r9b
0x18006c1db  mov     [rax+18h], r8b
0x18006c1df  push    rbp
0x18006c1e0  push    rsi
0x18006c1e1  push    rdi
0x18006c1e2  lea     rbp, [rax-4Fh]
0x18006c1e6  sub     rsp, 0C0h
0x18006c1ed  mov     rax, cs:__security_cookie
0x18006c1f4  xor     rax, rsp
0x18006c1f7  mov     [rbp+47h+var_20], rax
0x18006c1fb  mov     rbx, [rbp+47h+EventDescriptor]
0x18006c1ff  xor     eax, eax
0x18006c201  mov     rdi, rdx
0x18006c204  mov     [rbp+47h+var_A0], ax
0x18006c208  mov     rsi, rcx
0x18006c20b  mov     [rbp+47h+var_9C], ax
0x18006c20f  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c216  mov     rdx, rbx; EventDescriptor
0x18006c219  call    cs:__imp_EtwEventEnabled
0x18006c220  nop     dword ptr [rax+rax+00h]
0x18006c225  test    al, al
0x18006c227  jnz     short loc_18006C230
0x18006c229  xor     eax, eax
0x18006c22b  jmp     loc_18006C2F2
0x18006c230  movzx   ecx, word ptr [rsi]
0x18006c233  movzx   edx, word ptr [rdi]
0x18006c236  movzx   eax, cx
0x18006c239  shr     ax, 1
0x18006c23c  mov     [rbp+47h+var_A0], ax
0x18006c240  movzx   eax, dx
0x18006c243  shr     ax, 1
0x18006c246  mov     [rbp+47h+var_9C], ax
0x18006c24a  lea     rax, [rbp+47h+var_A0]
0x18006c24e  mov     [rbp+47h+UserData.Ptr], rax
0x18006c252  mov     rax, [rsi+8]
0x18006c256  mov     [rbp+47h+var_80], rax
0x18006c25a  lea     rax, [rbp+47h+var_9C]
0x18006c25e  mov     [rbp+47h+var_70], rax
0x18006c262  mov     rax, [rdi+8]
0x18006c266  mov     [rbp+47h+var_60], rax
0x18006c26a  lea     rax, [rbp+47h+arg_10]
0x18006c26e  mov     [rbp+47h+var_50], rax
0x18006c272  lea     rax, [rbp+47h+arg_18]
0x18006c276  mov     [rbp+47h+var_40], rax
0x18006c27a  lea     rax, [rbp+47h+arg_20]
0x18006c27e  mov     [rbp+47h+var_30], rax
0x18006c282  mov     qword ptr [rbp+47h+UserData.Size], 2
0x18006c28a  mov     [rbp+47h+var_78], ecx
0x18006c28d  mov     [rbp+47h+var_74], 0
0x18006c294  mov     [rbp+47h+var_68], 2
0x18006c29c  mov     [rbp+47h+var_58], edx
0x18006c29f  mov     [rbp+47h+var_54], 0
0x18006c2a6  mov     [rbp+47h+var_48], 1
0x18006c2ae  mov     [rbp+47h+var_38], 1
0x18006c2b6  mov     [rbp+47h+var_28], 4
0x18006c2be  call    cs:__imp_IoGetActivityIdThread
0x18006c2c5  nop     dword ptr [rax+rax+00h]
0x18006c2ca  lea     rcx, [rbp+47h+UserData]
0x18006c2ce  mov     r9d, 7; UserDataCount
0x18006c2d4  mov     [rsp+20h], rcx; UserData
0x18006c2d9  mov     r8, rax; ActivityId
0x18006c2dc  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c2e3  mov     rdx, rbx; EventDescriptor
0x18006c2e6  call    cs:__imp_EtwWrite
0x18006c2ed  nop     dword ptr [rax+rax+00h]
0x18006c2f2  mov     rcx, [rbp+47h+var_20]
0x18006c2f6  xor     rcx, rsp; StackCookie
0x18006c2f9  call    __security_check_cookie
0x18006c2fe  mov     rbx, [rsp+0D0h+arg_0]
0x18006c306  add     rsp, 0C0h
0x18006c30d  pop     rdi
0x18006c30e  pop     rsi
0x18006c30f  pop     rbp
0x18006c310  retn
```
