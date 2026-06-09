# LuafvFindUser

- ea: `0x140001e98`
- end: `0x140001f73`
- name: `LuafvFindUser`
- size: `219`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c0c`
- `0x140004e18`

## callees

- `0x140001e98`
- `0x140001f7c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f54`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f54`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001eb4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001eb4`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140001ede`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140001ede`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f10`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f41`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f10`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f41`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140001f25`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140001f25`

## pseudocode

```c
__int64 __fastcall LuafvFindUser(PACCESS_TOKEN Token, _QWORD *a2)
{
  int UserWithToken; // edi

  if ( ExAcquireRundownProtection(&RunRef) )
  {
    FltAcquirePushLockSharedEx(&UserListLock, 0);
    while ( 1 )
    {
      UserWithToken = FindUserWithToken(Token);
      if ( UserWithToken < 0 )
        break;
      if ( *a2 )
      {
        UserWithToken = 0;
        break;
      }
      FltReleasePushLockEx(&UserListLock, 0);
      FltAcquirePushLockExclusiveEx(&UserListLock, 0);
    }
    FltReleasePushLockEx(&UserListLock, 0);
    ExReleaseRundownProtection(&RunRef);
    return (unsigned int)UserWithToken;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x140001e98  mov     [rsp+arg_0], rbx
0x140001e9d  mov     [rsp+arg_8], rsi
0x140001ea2  push    rdi
0x140001ea3  sub     rsp, 20h
0x140001ea7  mov     rsi, rcx
0x140001eaa  mov     rbx, rdx
0x140001ead  lea     rcx, RunRef; RunRef
0x140001eb4  call    cs:__imp_ExAcquireRundownProtection
0x140001ebb  nop     dword ptr [rax+rax+00h]
0x140001ec0  test    al, al
0x140001ec2  jnz     short loc_140001ED2
0x140001ec4  mov     qword ptr [rbx], 0
0x140001ecb  xor     eax, eax
0x140001ecd  jmp     loc_140001F62
0x140001ed2  xor     dil, dil
0x140001ed5  lea     rcx, UserListLock
0x140001edc  xor     edx, edx
0x140001ede  call    cs:__imp_FltAcquirePushLockSharedEx
0x140001ee5  nop     dword ptr [rax+rax+00h]
0x140001eea  mov     r9, rbx
0x140001eed  mov     r8b, 1
0x140001ef0  mov     dl, dil
0x140001ef3  mov     rcx, rsi; Token
0x140001ef6  call    FindUserWithToken
0x140001efb  mov     edi, eax
0x140001efd  test    eax, eax
0x140001eff  js      short loc_140001F38
0x140001f01  cmp     qword ptr [rbx], 0
0x140001f05  jnz     short loc_140001F36
0x140001f07  xor     edx, edx
0x140001f09  lea     rcx, UserListLock
0x140001f10  call    cs:__imp_FltReleasePushLockEx
0x140001f17  nop     dword ptr [rax+rax+00h]
0x140001f1c  xor     edx, edx
0x140001f1e  lea     rcx, UserListLock
0x140001f25  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140001f2c  nop     dword ptr [rax+rax+00h]
0x140001f31  mov     dil, 1
0x140001f34  jmp     short loc_140001EEA
0x140001f36  xor     edi, edi
0x140001f38  xor     edx, edx
0x140001f3a  lea     rcx, UserListLock
0x140001f41  call    cs:__imp_FltReleasePushLockEx
0x140001f48  nop     dword ptr [rax+rax+00h]
0x140001f4d  lea     rcx, RunRef; RunRef
0x140001f54  call    cs:__imp_ExReleaseRundownProtection
0x140001f5b  nop     dword ptr [rax+rax+00h]
0x140001f60  mov     eax, edi
0x140001f62  mov     rbx, [rsp+28h+arg_0]
0x140001f67  mov     rsi, [rsp+28h+arg_8]
0x140001f6c  add     rsp, 20h
0x140001f70  pop     rdi
0x140001f71  retn
```
