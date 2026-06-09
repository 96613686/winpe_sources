# Etw_Trace2_int_int

- ea: `0x18000acac`
- end: `0x18000ad25`
- name: `Etw_Trace2_int_int`
- size: `121`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af88`
- `0x18000b0d8`

## callees

- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ad0c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ad0c`

## pseudocode

```c
ULONG __fastcall Etw_Trace2_int_int(PCEVENT_DESCRIPTOR EventDescriptor, int a2, int a3)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-38h] BYREF
  int *v6; // [rsp+30h] [rbp-28h]
  __int64 v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+68h] [rbp+10h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v8 = a2;
  EtwInitProvider();
  UserData.Ptr = (ULONGLONG)&v8;
  *(_QWORD *)&UserData.Size = 4;
  v6 = &v9;
  v7 = 4;
  return EventWrite(RegistrationHandle, EventDescriptor, 2u, &UserData);
}

```

## disassembly

```asm
0x18000acac  mov     [rsp+arg_10], r8d
0x18000acb1  mov     [rsp+arg_8], edx
0x18000acb5  push    rbx
0x18000acb6  sub     rsp, 50h
0x18000acba  mov     rax, cs:__security_cookie
0x18000acc1  xor     rax, rsp
0x18000acc4  mov     [rsp+58h+var_18], rax
0x18000acc9  mov     rbx, rcx
0x18000accc  call    EtwInitProvider
0x18000acd1  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000acd8  lea     rax, [rsp+58h+arg_8]
0x18000acdd  mov     [rsp+58h+UserData.Ptr], rax
0x18000ace2  lea     r9, [rsp+58h+UserData]; UserData
0x18000ace7  lea     rax, [rsp+58h+arg_10]
0x18000acec  mov     qword ptr [rsp+58h+UserData.Size], 4
0x18000acf5  mov     r8d, 2; UserDataCount
0x18000acfb  mov     [rsp+58h+var_28], rax
0x18000ad00  mov     rdx, rbx; EventDescriptor
0x18000ad03  mov     [rsp+58h+var_20], 4
0x18000ad0c  call    cs:__imp_EventWrite
0x18000ad12  mov     rcx, [rsp+58h+var_18]
0x18000ad17  xor     rcx, rsp; StackCookie
0x18000ad1a  call    __security_check_cookie
0x18000ad1f  add     rsp, 50h
0x18000ad23  pop     rbx
0x18000ad24  retn
```
