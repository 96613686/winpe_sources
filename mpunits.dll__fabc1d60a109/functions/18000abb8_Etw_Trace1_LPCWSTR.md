# Etw_Trace1_LPCWSTR

- ea: `0x18000abb8`
- end: `0x18000ac3d`
- name: `Etw_Trace1_LPCWSTR`
- size: `133`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x18000afdc`
- `0x18000b030`
- `0x18000b084`
- `0x18001a020`
- `0x18001ced0`
- `0x1800252b0`
- `0x1800279b0`
- `0x180028948`
- `0x180028b00`
- `0x1800290f4`
- `0x1800292cc`
- `0x18002add0`

## callees

- `0x18000abb8`
- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ac1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ac1f`

## pseudocode

```c
ULONG __fastcall Etw_Trace1_LPCWSTR(PCEVENT_DESCRIPTOR EventDescriptor, ULONGLONG a2)
{
  __int64 v4; // rax
  ULONG v5; // eax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

  EtwInitProvider();
  UserData.Ptr = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a2 + 2 * v4) );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 0;
  }
  UserData.Reserved = 0;
  UserData.Size = v5;
  return EventWrite(RegistrationHandle, EventDescriptor, 1u, &UserData);
}

```

## disassembly

```asm
0x18000abb8  mov     [rsp+arg_8], rbx
0x18000abbd  push    rdi
0x18000abbe  sub     rsp, 40h
0x18000abc2  mov     rax, cs:__security_cookie
0x18000abc9  xor     rax, rsp
0x18000abcc  mov     [rsp+48h+var_18], rax
0x18000abd1  mov     rbx, rdx
0x18000abd4  mov     rdi, rcx
0x18000abd7  call    EtwInitProvider
0x18000abdc  xor     ecx, ecx
0x18000abde  mov     [rsp+48h+UserData.Ptr], rbx
0x18000abe3  test    rbx, rbx
0x18000abe6  jz      short loc_18000ABFF
0x18000abe8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000abec  inc     rax
0x18000abef  cmp     [rbx+rax*2], cx
0x18000abf3  jnz     short loc_18000ABEC
0x18000abf5  lea     rax, ds:2[rax*2]
0x18000abfd  jmp     short loc_18000AC02
0x18000abff  mov     rax, rcx
0x18000ac02  mov     dword ptr [rsp+48h+UserData.0Ch], ecx
0x18000ac06  lea     r9, [rsp+48h+UserData]; UserData
0x18000ac0b  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000ac12  mov     r8d, 1; UserDataCount
0x18000ac18  mov     rdx, rdi; EventDescriptor
0x18000ac1b  mov     [rsp+48h+UserData.Size], eax
0x18000ac1f  call    cs:__imp_EventWrite
0x18000ac25  mov     rcx, [rsp+48h+var_18]
0x18000ac2a  xor     rcx, rsp; StackCookie
0x18000ac2d  call    __security_check_cookie
0x18000ac32  mov     rbx, [rsp+48h+arg_8]
0x18000ac37  add     rsp, 40h
0x18000ac3b  pop     rdi
0x18000ac3c  retn
```
