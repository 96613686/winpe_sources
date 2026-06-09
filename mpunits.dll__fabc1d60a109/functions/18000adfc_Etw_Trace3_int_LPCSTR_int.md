# Etw_Trace3_int_LPCSTR_int

- ea: `0x18000adfc`
- end: `0x18000ae8f`
- name: `Etw_Trace3_int_LPCSTR_int`
- size: `147`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b3b4`
- `0x18000b408`
- `0x18000b568`

## callees

- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ae6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ae6f`

## pseudocode

```c
ULONG __fastcall Etw_Trace3_int_LPCSTR_int(PCEVENT_DESCRIPTOR EventDescriptor, int a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-40h] BYREF
  const char *v7; // [rsp+30h] [rbp-30h]
  __int64 v8; // [rsp+38h] [rbp-28h]
  int *v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]
  int v11; // [rsp+78h] [rbp+18h] BYREF
  int v12; // [rsp+88h] [rbp+28h] BYREF

  v12 = a4;
  v11 = a2;
  EtwInitProvider();
  UserData.Ptr = (ULONGLONG)&v11;
  *(_QWORD *)&UserData.Size = 4;
  v7 = "admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
  v8 = 42;
  v9 = &v12;
  v10 = 4;
  return EventWrite(RegistrationHandle, EventDescriptor, 3u, &UserData);
}

```

## disassembly

```asm
0x18000adfc  mov     [rsp-8+arg_10], rbx
0x18000ae01  mov     [rsp-8+arg_18], r9d
0x18000ae06  mov     [rsp-8+arg_8], edx
0x18000ae0a  push    rbp
0x18000ae0b  mov     rbp, rsp
0x18000ae0e  sub     rsp, 60h
0x18000ae12  mov     rax, cs:__security_cookie
0x18000ae19  xor     rax, rsp
0x18000ae1c  mov     [rbp+var_10], rax
0x18000ae20  mov     rbx, rcx
0x18000ae23  call    EtwInitProvider
0x18000ae28  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000ae2f  lea     rax, [rbp+arg_8]
0x18000ae33  mov     [rbp+UserData.Ptr], rax
0x18000ae37  lea     r9, [rbp+UserData]; UserData
0x18000ae3b  lea     rax, aAdminWmiWinomi_15; "admin\\wmi\\winomi\\mp\\perf\\formatted"...
0x18000ae42  mov     qword ptr [rbp+UserData.Size], 4
0x18000ae4a  mov     [rbp+var_30], rax
0x18000ae4e  mov     r8d, 3; UserDataCount
0x18000ae54  lea     rax, [rbp+arg_18]
0x18000ae58  mov     [rbp+var_28], 2Ah ; '*'
0x18000ae60  mov     rdx, rbx; EventDescriptor
0x18000ae63  mov     [rbp+var_20], rax
0x18000ae67  mov     [rbp+var_18], 4
0x18000ae6f  call    cs:__imp_EventWrite
0x18000ae75  mov     rcx, [rbp+var_10]
0x18000ae79  xor     rcx, rsp; StackCookie
0x18000ae7c  call    __security_check_cookie
0x18000ae81  mov     rbx, [rsp+60h+arg_10]
0x18000ae89  add     rsp, 60h
0x18000ae8d  pop     rbp
0x18000ae8e  retn
```
