# CiLogCacheEvent

- ea: `0x18009da14`
- end: `0x18009db11`
- name: `CiLogCacheEvent`
- size: `253`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009ca38`
- `0x18009d178`

## callees

- `0x18002bef0`
- `0x18009da14`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009da4e`
- `ntoskrnl!EtwEventEnabled` at `0x18009da4e`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009dac2`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009dac2`
- `ntoskrnl!EtwWrite` at `0x18009daea`
- `ntoskrnl!EtwWrite` at `0x18009daea`

## pseudocode

```c
NTSTATUS __fastcall CiLogCacheEvent(
        int a1,
        int a2,
        char a3,
        int a4,
        char a5,
        char a6,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v7; // rbx
  const GUID *ActivityIdThread; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-41h] BYREF
  int *v11; // [rsp+48h] [rbp-31h]
  __int64 v12; // [rsp+50h] [rbp-29h]
  int *v13; // [rsp+58h] [rbp-21h]
  __int64 v14; // [rsp+60h] [rbp-19h]
  char *v15; // [rsp+68h] [rbp-11h]
  __int64 v16; // [rsp+70h] [rbp-9h]
  char *v17; // [rsp+78h] [rbp-1h]
  __int64 v18; // [rsp+80h] [rbp+7h]
  char *v19; // [rsp+88h] [rbp+Fh]
  __int64 v20; // [rsp+90h] [rbp+17h]
  int v21; // [rsp+C8h] [rbp+4Fh] BYREF
  int v22; // [rsp+D0h] [rbp+57h] BYREF
  char v23; // [rsp+D8h] [rbp+5Fh] BYREF
  int v24; // [rsp+E0h] [rbp+67h] BYREF

  v24 = a4;
  v23 = a3;
  v22 = a2;
  v21 = a1;
  v7 = EventDescriptor;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v21;
  v11 = &v24;
  v13 = &v22;
  v15 = &v23;
  v17 = &a5;
  v19 = &a6;
  v12 = 4;
  v14 = 1;
  v16 = 1;
  v18 = 4;
  v20 = 8;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v7, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x18009da14  mov     rax, rsp
0x18009da17  mov     [rax+20h], r9d
0x18009da1b  mov     [rax+18h], r8b
0x18009da1f  mov     [rax+10h], edx
0x18009da22  mov     [rax+8], ecx
0x18009da25  push    rbp
0x18009da26  push    rbx
0x18009da27  lea     rbp, [rax-47h]
0x18009da2b  sub     rsp, 0A8h
0x18009da32  mov     rax, cs:__security_cookie
0x18009da39  xor     rax, rsp
0x18009da3c  mov     [rbp+3Fh+var_20], rax
0x18009da40  mov     rbx, [rbp+3Fh+EventDescriptor]
0x18009da44  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009da4b  mov     rdx, rbx; EventDescriptor
0x18009da4e  call    cs:__imp_EtwEventEnabled
0x18009da55  nop     dword ptr [rax+rax+00h]
0x18009da5a  test    al, al
0x18009da5c  jz      loc_18009DB0D
0x18009da62  lea     rax, [rbp+3Fh+arg_0]
0x18009da66  mov     qword ptr [rbp+3Fh+UserData.Size], 4
0x18009da6e  mov     [rbp+3Fh+UserData.Ptr], rax
0x18009da72  lea     rax, [rbp+3Fh+arg_18]
0x18009da76  mov     [rbp+3Fh+var_70], rax
0x18009da7a  lea     rax, [rbp+3Fh+arg_8]
0x18009da7e  mov     [rbp+3Fh+var_60], rax
0x18009da82  lea     rax, [rbp+3Fh+arg_10]
0x18009da86  mov     [rbp+3Fh+var_50], rax
0x18009da8a  lea     rax, [rbp+3Fh+arg_20]
0x18009da8e  mov     [rbp+3Fh+var_40], rax
0x18009da92  lea     rax, [rbp+3Fh+arg_28]
0x18009da96  mov     [rbp+3Fh+var_30], rax
0x18009da9a  mov     [rbp+3Fh+var_68], 4
0x18009daa2  mov     [rbp+3Fh+var_58], 1
0x18009daaa  mov     [rbp+3Fh+var_48], 1
0x18009dab2  mov     [rbp+3Fh+var_38], 4
0x18009daba  mov     [rbp+3Fh+var_28], 8
0x18009dac2  call    cs:__imp_IoGetActivityIdThread
0x18009dac9  nop     dword ptr [rax+rax+00h]
0x18009dace  lea     rcx, [rbp+3Fh+UserData]
0x18009dad2  mov     r9d, 6; UserDataCount
0x18009dad8  mov     [rsp+20h], rcx; UserData
0x18009dadd  mov     r8, rax; ActivityId
0x18009dae0  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009dae7  mov     rdx, rbx; EventDescriptor
0x18009daea  call    cs:__imp_EtwWrite
0x18009daf1  nop     dword ptr [rax+rax+00h]
0x18009daf6  mov     rcx, [rbp+3Fh+var_20]
0x18009dafa  xor     rcx, rsp; StackCookie
0x18009dafd  call    __security_check_cookie
0x18009db02  add     rsp, 0A8h
0x18009db09  pop     rbx
0x18009db0a  pop     rbp
0x18009db0b  retn
0x18009db0d  xor     eax, eax
0x18009db0f  jmp     short loc_18009DAF6
```
