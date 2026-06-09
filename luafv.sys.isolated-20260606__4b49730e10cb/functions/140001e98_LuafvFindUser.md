# LuafvFindUser

- ea: `0x140001e98`
- end: `0x1400020ba`
- name: `LuafvFindUser`
- size: `546`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140001c0c`
- `0x140004c50`

## callees

- `0x140001e98`
- `0x1400051a8`
- `0x1400058cc`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140002096`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002096`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001ee3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140001ee3`
- `ntoskrnl!ZwClose` at `0x140002083`
- `ntoskrnl!ZwClose` at `0x140002083`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140001f06`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140001f06`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f2b`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f63`
- `FLTMGR!FltReleasePushLockEx` at `0x140001fcd`
- `FLTMGR!FltReleasePushLockEx` at `0x140002042`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f2b`
- `FLTMGR!FltReleasePushLockEx` at `0x140001f63`
- `FLTMGR!FltReleasePushLockEx` at `0x140001fcd`
- `FLTMGR!FltReleasePushLockEx` at `0x140002042`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140001f9b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140001f9b`

## pseudocode

```c
__int64 __fastcall LuafvFindUser(PACCESS_TOKEN Token, __int64 *a2)
{
  int UserWithToken; // ebx
  __int64 v6; // rcx
  struct _UNICODE_STRING v7; // xmm0
  UNICODE_STRING v8; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING v9; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v10; // [rsp+50h] [rbp-10h] BYREF
  __int64 v11; // [rsp+88h] [rbp+28h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+30h] BYREF

  v11 = 0;
  Handle = 0;
  *a2 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !ExAcquireRundownProtection(&RunRef) )
    return 0;
  FltAcquirePushLockSharedEx(&UserListLock, 0);
  UserWithToken = FindUserWithToken(Token, 0, &v11);
  if ( UserWithToken < 0 )
    goto LABEL_4;
  if ( v11 && *(_QWORD *)(v11 + 112) && *(_QWORD *)(v11 + 184) )
  {
    *a2 = v11;
    goto LABEL_18;
  }
  FltReleasePushLockEx(&UserListLock, 0);
  UserWithToken = LuafvFetchProfileDataForToken(Token, &v8, &v9, &Handle, &v10);
  if ( UserWithToken < 0 )
    goto LABEL_19;
  FltAcquirePushLockExclusiveEx(&UserListLock, 0);
  UserWithToken = FindUserWithToken(Token, 1, &v11);
  if ( UserWithToken >= 0 )
  {
    v6 = v11;
    if ( !v11 )
    {
      FltReleasePushLockEx(&UserListLock, 0);
      UserWithToken = -1073741275;
      goto LABEL_19;
    }
    if ( !*(_QWORD *)(v11 + 112) )
    {
      *(UNICODE_STRING *)(v11 + 104) = v8;
      *(UNICODE_STRING *)(v6 + 120) = v9;
      v8.Buffer = 0;
      v9.Buffer = 0;
    }
    if ( !*(_QWORD *)(v6 + 184) )
    {
      v7 = v10;
      *(_QWORD *)(v6 + 184) = Handle;
      *(struct _UNICODE_STRING *)(v6 + 152) = v7;
      Handle = 0;
      v10.Buffer = 0;
    }
    *a2 = v6;
LABEL_18:
    FltReleasePushLockEx(&UserListLock, 0);
    UserWithToken = 0;
    goto LABEL_19;
  }
LABEL_4:
  FltReleasePushLockEx(&UserListLock, 0);
LABEL_19:
  if ( v8.Buffer )
    LuafvFreePool((__int64)v8.Buffer);
  if ( v9.Buffer )
    LuafvFreePool((__int64)v9.Buffer);
  if ( v10.Buffer )
    LuafvFreePool((__int64)v10.Buffer);
  if ( Handle )
    ZwClose(Handle);
  ExReleaseRundownProtection(&RunRef);
  return (unsigned int)UserWithToken;
}

```

## disassembly

```asm
0x140001e98  mov     [rsp-18h+arg_0], rbx
0x140001e9d  mov     [rsp-18h+arg_18], rsi
0x140001ea2  push    rbp
0x140001ea3  push    rdi
0x140001ea4  push    r15
0x140001ea6  mov     rbp, rsp
0x140001ea9  sub     rsp, 60h
0x140001ead  xorps   xmm0, xmm0
0x140001eb0  mov     [rbp+arg_8], 0
0x140001eb8  mov     rsi, rcx
0x140001ebb  mov     [rbp+Handle], 0
0x140001ec3  xorps   xmm1, xmm1
0x140001ec6  mov     qword ptr [rdx], 0
0x140001ecd  lea     rcx, RunRef; RunRef
0x140001ed4  mov     rdi, rdx
0x140001ed7  movups  [rbp+var_30], xmm0
0x140001edb  movups  [rbp+var_20], xmm1
0x140001edf  movups  [rbp+var_10], xmm0
0x140001ee3  call    cs:__imp_ExAcquireRundownProtection
0x140001eea  nop     dword ptr [rax+rax+00h]
0x140001eef  test    al, al
0x140001ef1  jnz     short loc_140001EFA
0x140001ef3  xor     eax, eax
0x140001ef5  jmp     loc_1400020A4
0x140001efa  lea     r15, UserListLock
0x140001f01  xor     edx, edx
0x140001f03  mov     rcx, r15
0x140001f06  call    cs:__imp_FltAcquirePushLockSharedEx
0x140001f0d  nop     dword ptr [rax+rax+00h]
0x140001f12  lea     r8, [rbp+arg_8]
0x140001f16  xor     edx, edx
0x140001f18  mov     rcx, rsi; Token
0x140001f1b  call    FindUserWithToken
0x140001f20  mov     ebx, eax
0x140001f22  test    eax, eax
0x140001f24  jns     short loc_140001F3C
0x140001f26  xor     edx, edx
0x140001f28  mov     rcx, r15
0x140001f2b  call    cs:__imp_FltReleasePushLockEx
0x140001f32  nop     dword ptr [rax+rax+00h]
0x140001f37  jmp     loc_140002050
0x140001f3c  mov     rax, [rbp+arg_8]
0x140001f40  test    rax, rax
0x140001f43  jz      short loc_140001F5E
0x140001f45  cmp     qword ptr [rax+70h], 0
0x140001f4a  jz      short loc_140001F5E
0x140001f4c  cmp     qword ptr [rax+0B8h], 0
0x140001f54  jz      short loc_140001F5E
0x140001f56  mov     [rdi], rax
0x140001f59  jmp     loc_14000203D
0x140001f5e  xor     edx, edx
0x140001f60  mov     rcx, r15
0x140001f63  call    cs:__imp_FltReleasePushLockEx
0x140001f6a  nop     dword ptr [rax+rax+00h]
0x140001f6f  lea     rax, [rbp+var_10]
0x140001f73  mov     rcx, rsi
0x140001f76  lea     r9, [rbp+Handle]
0x140001f7a  mov     [rsp+60h+var_40], rax
0x140001f7f  lea     r8, [rbp+var_20]
0x140001f83  lea     rdx, [rbp+var_30]
0x140001f87  call    LuafvFetchProfileDataForToken
0x140001f8c  mov     ebx, eax
0x140001f8e  test    eax, eax
0x140001f90  js      loc_140002050
0x140001f96  xor     edx, edx
0x140001f98  mov     rcx, r15
0x140001f9b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140001fa2  nop     dword ptr [rax+rax+00h]
0x140001fa7  lea     r8, [rbp+arg_8]
0x140001fab  mov     dl, 1
0x140001fad  mov     rcx, rsi; Token
0x140001fb0  call    FindUserWithToken
0x140001fb5  mov     ebx, eax
0x140001fb7  test    eax, eax
0x140001fb9  js      loc_140001F26
0x140001fbf  mov     rcx, [rbp+arg_8]
0x140001fc3  test    rcx, rcx
0x140001fc6  jnz     short loc_140001FE0
0x140001fc8  xor     edx, edx
0x140001fca  mov     rcx, r15
0x140001fcd  call    cs:__imp_FltReleasePushLockEx
0x140001fd4  nop     dword ptr [rax+rax+00h]
0x140001fd9  mov     ebx, 0C0000225h
0x140001fde  jmp     short loc_140002050
0x140001fe0  cmp     qword ptr [rcx+70h], 0
0x140001fe5  jnz     short loc_140002009
0x140001fe7  movups  xmm0, [rbp+var_30]
0x140001feb  movdqu  xmmword ptr [rcx+68h], xmm0
0x140001ff0  movups  xmm1, [rbp+var_20]
0x140001ff4  movdqu  xmmword ptr [rcx+78h], xmm1
0x140001ff9  mov     qword ptr [rbp+var_30+8], 0
0x140002001  mov     qword ptr [rbp+var_20+8], 0
0x140002009  cmp     qword ptr [rcx+0B8h], 0
0x140002011  jnz     short loc_14000203A
0x140002013  movups  xmm0, [rbp+var_10]
0x140002017  mov     rax, [rbp+Handle]
0x14000201b  mov     [rcx+0B8h], rax
0x140002022  movdqu  xmmword ptr [rcx+98h], xmm0
0x14000202a  mov     [rbp+Handle], 0
0x140002032  mov     qword ptr [rbp+var_10+8], 0
0x14000203a  mov     [rdi], rcx
0x14000203d  xor     edx, edx
0x14000203f  mov     rcx, r15
0x140002042  call    cs:__imp_FltReleasePushLockEx
0x140002049  nop     dword ptr [rax+rax+00h]
0x14000204e  xor     ebx, ebx
0x140002050  mov     rcx, qword ptr [rbp+var_30+8]
0x140002054  test    rcx, rcx
0x140002057  jz      short loc_14000205E
0x140002059  call    LuafvFreePool
0x14000205e  mov     rcx, qword ptr [rbp+var_20+8]
0x140002062  test    rcx, rcx
0x140002065  jz      short loc_14000206C
0x140002067  call    LuafvFreePool
0x14000206c  mov     rcx, qword ptr [rbp+var_10+8]
0x140002070  test    rcx, rcx
0x140002073  jz      short loc_14000207A
0x140002075  call    LuafvFreePool
0x14000207a  mov     rcx, [rbp+Handle]; Handle
0x14000207e  test    rcx, rcx
0x140002081  jz      short loc_14000208F
0x140002083  call    cs:__imp_ZwClose
0x14000208a  nop     dword ptr [rax+rax+00h]
0x14000208f  lea     rcx, RunRef; RunRef
0x140002096  call    cs:__imp_ExReleaseRundownProtection
0x14000209d  nop     dword ptr [rax+rax+00h]
0x1400020a2  mov     eax, ebx
0x1400020a4  lea     r11, [rsp+60h+var_s0]
0x1400020a9  mov     rbx, [r11+20h]
0x1400020ad  mov     rsi, [r11+38h]
0x1400020b1  mov     rsp, r11
0x1400020b4  pop     r15
0x1400020b6  pop     rdi
0x1400020b7  pop     rbp
0x1400020b8  retn
```
