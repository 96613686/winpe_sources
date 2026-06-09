# CiLogSdlEvent

- ea: `0x18006d94c`
- end: `0x18006da76`
- name: `CiLogSdlEvent`
- size: `298`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064a78`

## callees

- `0x18002bf20`
- `0x18006d94c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d994`
- `ntoskrnl!EtwEventEnabled` at `0x18006d994`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006da29`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006da29`
- `ntoskrnl!EtwWrite` at `0x18006da51`
- `ntoskrnl!EtwWrite` at `0x18006da51`

## pseudocode

```c
NTSTATUS __fastcall CiLogSdlEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  int v9; // ecx
  int v10; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+30h] [rbp-51h] BYREF
  __int16 v13; // [rsp+34h] [rbp-4Dh] BYREF
  int v14; // [rsp+38h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-41h] BYREF
  __int64 v16; // [rsp+50h] [rbp-31h]
  int v17; // [rsp+58h] [rbp-29h]
  int v18; // [rsp+5Ch] [rbp-25h]
  __int16 *v19; // [rsp+60h] [rbp-21h]
  __int64 v20; // [rsp+68h] [rbp-19h]
  __int64 v21; // [rsp+70h] [rbp-11h]
  int v22; // [rsp+78h] [rbp-9h]
  int v23; // [rsp+7Ch] [rbp-5h]
  int *v24; // [rsp+80h] [rbp-1h]
  __int64 v25; // [rsp+88h] [rbp+7h]
  int *v26; // [rsp+90h] [rbp+Fh]
  __int64 v27; // [rsp+98h] [rbp+17h]
  int v28; // [rsp+F8h] [rbp+77h] BYREF

  v28 = a4;
  v5 = EventDescriptor;
  v14 = 1;
  v12 = 0;
  v13 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v9 = *a1;
  v10 = *a2;
  v12 = *a1 >> 1;
  v13 = (unsigned __int16)v10 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v13;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v14;
  v26 = &v28;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v9;
  v18 = 0;
  v20 = 2;
  v22 = v10;
  v23 = 0;
  v25 = 1;
  v27 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x18006d94c  mov     [rsp-8+arg_18], r9d
0x18006d951  push    rbp
0x18006d952  push    rbx
0x18006d953  push    rsi
0x18006d954  push    rdi
0x18006d955  lea     rbp, [rsp-37h]
0x18006d95a  sub     rsp, 0B8h
0x18006d961  mov     rax, cs:__security_cookie
0x18006d968  xor     rax, rsp
0x18006d96b  mov     [rbp+4Fh+var_30], rax
0x18006d96f  mov     rbx, [rbp+4Fh+EventDescriptor]
0x18006d973  xor     eax, eax
0x18006d975  mov     rdi, rdx
0x18006d978  mov     [rbp+4Fh+var_98], 1
0x18006d97f  mov     rsi, rcx
0x18006d982  mov     [rbp+4Fh+var_A0], ax
0x18006d986  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d98d  mov     rdx, rbx; EventDescriptor
0x18006d990  mov     [rbp+4Fh+var_9C], ax
0x18006d994  call    cs:__imp_EtwEventEnabled
0x18006d99b  nop     dword ptr [rax+rax+00h]
0x18006d9a0  test    al, al
0x18006d9a2  jnz     short loc_18006D9AB
0x18006d9a4  xor     eax, eax
0x18006d9a6  jmp     loc_18006DA5D
0x18006d9ab  movzx   ecx, word ptr [rsi]
0x18006d9ae  movzx   edx, word ptr [rdi]
0x18006d9b1  movzx   eax, cx
0x18006d9b4  shr     ax, 1
0x18006d9b7  mov     [rbp+4Fh+var_A0], ax
0x18006d9bb  movzx   eax, dx
0x18006d9be  shr     ax, 1
0x18006d9c1  mov     [rbp+4Fh+var_9C], ax
0x18006d9c5  lea     rax, [rbp+4Fh+var_A0]
0x18006d9c9  mov     [rbp+4Fh+var_90.Ptr], rax
0x18006d9cd  mov     rax, [rsi+8]
0x18006d9d1  mov     [rbp+4Fh+var_80], rax
0x18006d9d5  lea     rax, [rbp+4Fh+var_9C]
0x18006d9d9  mov     [rbp+4Fh+var_70], rax
0x18006d9dd  mov     rax, [rdi+8]
0x18006d9e1  mov     [rbp+4Fh+var_60], rax
0x18006d9e5  lea     rax, [rbp+4Fh+var_98]
0x18006d9e9  mov     [rbp+4Fh+var_50], rax
0x18006d9ed  lea     rax, [rbp+4Fh+arg_18]
0x18006d9f1  mov     [rbp+4Fh+var_40], rax
0x18006d9f5  mov     qword ptr [rbp+4Fh+var_90.Size], 2
0x18006d9fd  mov     [rbp+4Fh+var_78], ecx
0x18006da00  mov     [rbp+4Fh+var_74], 0
0x18006da07  mov     [rbp+4Fh+var_68], 2
0x18006da0f  mov     [rbp+4Fh+var_58], edx
0x18006da12  mov     [rbp+4Fh+var_54], 0
0x18006da19  mov     [rbp+4Fh+var_48], 1
0x18006da21  mov     [rbp+4Fh+var_38], 4
0x18006da29  call    cs:__imp_IoGetActivityIdThread
0x18006da30  nop     dword ptr [rax+rax+00h]
0x18006da35  lea     rcx, [rbp+4Fh+var_90]
0x18006da39  mov     r9d, 6; UserDataCount
0x18006da3f  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006da44  mov     r8, rax; ActivityId
0x18006da47  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006da4e  mov     rdx, rbx; EventDescriptor
0x18006da51  call    cs:__imp_EtwWrite
0x18006da58  nop     dword ptr [rax+rax+00h]
0x18006da5d  mov     rcx, [rbp+4Fh+var_30]
0x18006da61  xor     rcx, rsp; StackCookie
0x18006da64  call    __security_check_cookie
0x18006da69  add     rsp, 0B8h
0x18006da70  pop     rdi
0x18006da71  pop     rsi
0x18006da72  pop     rbx
0x18006da73  pop     rbp
0x18006da74  retn
```
