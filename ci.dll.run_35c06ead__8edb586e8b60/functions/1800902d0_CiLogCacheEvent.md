# CiLogCacheEvent

- ea: `0x1800902d0`
- end: `0x1800903cd`
- name: `CiLogCacheEvent`
- size: `253`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18008f2f4`
- `0x18008fa34`

## callees

- `0x18002c0d0`
- `0x1800902d0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009030a`
- `ntoskrnl!EtwEventEnabled` at `0x18009030a`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009037e`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009037e`
- `ntoskrnl!EtwWrite` at `0x1800903a6`
- `ntoskrnl!EtwWrite` at `0x1800903a6`

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
0x1800902d0  mov     rax, rsp
0x1800902d3  mov     [rax+20h], r9d
0x1800902d7  mov     [rax+18h], r8b
0x1800902db  mov     [rax+10h], edx
0x1800902de  mov     [rax+8], ecx
0x1800902e1  push    rbp
0x1800902e2  push    rbx
0x1800902e3  lea     rbp, [rax-47h]
0x1800902e7  sub     rsp, 0A8h
0x1800902ee  mov     rax, cs:__security_cookie
0x1800902f5  xor     rax, rsp
0x1800902f8  mov     [rbp+3Fh+var_20], rax
0x1800902fc  mov     rbx, [rbp+3Fh+EventDescriptor]
0x180090300  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180090307  mov     rdx, rbx; EventDescriptor
0x18009030a  call    cs:__imp_EtwEventEnabled
0x180090311  nop     dword ptr [rax+rax+00h]
0x180090316  test    al, al
0x180090318  jz      loc_1800903C9
0x18009031e  lea     rax, [rbp+3Fh+arg_0]
0x180090322  mov     qword ptr [rbp+3Fh+UserData.Size], 4
0x18009032a  mov     [rbp+3Fh+UserData.Ptr], rax
0x18009032e  lea     rax, [rbp+3Fh+arg_18]
0x180090332  mov     [rbp+3Fh+var_70], rax
0x180090336  lea     rax, [rbp+3Fh+arg_8]
0x18009033a  mov     [rbp+3Fh+var_60], rax
0x18009033e  lea     rax, [rbp+3Fh+arg_10]
0x180090342  mov     [rbp+3Fh+var_50], rax
0x180090346  lea     rax, [rbp+3Fh+arg_20]
0x18009034a  mov     [rbp+3Fh+var_40], rax
0x18009034e  lea     rax, [rbp+3Fh+arg_28]
0x180090352  mov     [rbp+3Fh+var_30], rax
0x180090356  mov     [rbp+3Fh+var_68], 4
0x18009035e  mov     [rbp+3Fh+var_58], 1
0x180090366  mov     [rbp+3Fh+var_48], 1
0x18009036e  mov     [rbp+3Fh+var_38], 4
0x180090376  mov     [rbp+3Fh+var_28], 8
0x18009037e  call    cs:__imp_IoGetActivityIdThread
0x180090385  nop     dword ptr [rax+rax+00h]
0x18009038a  lea     rcx, [rbp+3Fh+UserData]
0x18009038e  mov     r9d, 6; UserDataCount
0x180090394  mov     [rsp+20h], rcx; UserData
0x180090399  mov     r8, rax; ActivityId
0x18009039c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800903a3  mov     rdx, rbx; EventDescriptor
0x1800903a6  call    cs:__imp_EtwWrite
0x1800903ad  nop     dword ptr [rax+rax+00h]
0x1800903b2  mov     rcx, [rbp+3Fh+var_20]
0x1800903b6  xor     rcx, rsp; StackCookie
0x1800903b9  call    __security_check_cookie
0x1800903be  add     rsp, 0A8h
0x1800903c5  pop     rbx
0x1800903c6  pop     rbp
0x1800903c7  retn
0x1800903c9  xor     eax, eax
0x1800903cb  jmp     short loc_1800903B2
```
