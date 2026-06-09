# CiLogWhqlSettingsEvent

- ea: `0x18006e55c`
- end: `0x18006e65a`
- name: `CiLogWhqlSettingsEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e4ca8`

## callees

- `0x18002bf20`
- `0x18006e55c`
- `0x1800a7204`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006e5a9`
- `ntoskrnl!EtwEventEnabled` at `0x18006e5a9`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e60e`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e60e`
- `ntoskrnl!EtwWrite` at `0x18006e636`
- `ntoskrnl!EtwWrite` at `0x18006e636`

## pseudocode

```c
NTSTATUS CiLogWhqlSettingsEvent()
{
  const EVENT_DESCRIPTOR *v0; // rbx
  int v2; // eax
  const GUID *ActivityIdThread; // rax
  _BYTE v4[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v5; // [rsp+34h] [rbp-2Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  _BYTE *v7; // [rsp+48h] [rbp-18h]
  __int64 v8; // [rsp+50h] [rbp-10h]

  v5 = 0;
  v4[0] = 0;
  v0 = (const EVENT_DESCRIPTOR *)WhqlEnforcementDisabled;
  if ( (unsigned __int8)CipWhqlEnforcementEnabled(v4) )
    v0 = &WhqlEnforcementEnabled;
  if ( !EtwEventEnabled(g_EtwEventHandle, v0) )
    return 0;
  v2 = v5;
  if ( (g_CiOptions & 0x40000) != 0 )
  {
    v2 = v5 | 1;
    v5 |= 1u;
  }
  if ( (g_CiOptions & 0x80000) != 0 )
  {
    v2 |= 2u;
    v5 = v2;
  }
  if ( (g_CiOptions & 0x20000) != 0 )
    v5 = v2 | 0x80000000;
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v5;
  v7 = v4;
  v8 = 1;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread((unsigned int)g_CiOptions);
  return EtwWrite(g_EtwEventHandle, v0, ActivityIdThread, 2u, &UserData);
}

```

## disassembly

```asm
0x18006e55c  mov     [rsp-8+arg_0], rbx
0x18006e561  push    rbp
0x18006e562  mov     rbp, rsp
0x18006e565  sub     rsp, 60h
0x18006e569  mov     rax, cs:__security_cookie
0x18006e570  xor     rax, rsp
0x18006e573  mov     [rbp+var_8], rax
0x18006e577  lea     rcx, [rbp+var_30]
0x18006e57b  mov     [rbp+var_2C], 0
0x18006e582  mov     [rbp+var_30], 0
0x18006e586  call    CipWhqlEnforcementEnabled
0x18006e58b  test    al, al
0x18006e58d  lea     rcx, WhqlEnforcementEnabled
0x18006e594  lea     rbx, WhqlEnforcementDisabled
0x18006e59b  cmovnz  rbx, rcx
0x18006e59f  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e5a6  mov     rdx, rbx; EventDescriptor
0x18006e5a9  call    cs:__imp_EtwEventEnabled
0x18006e5b0  nop     dword ptr [rax+rax+00h]
0x18006e5b5  test    al, al
0x18006e5b7  jnz     short loc_18006E5C0
0x18006e5b9  xor     eax, eax
0x18006e5bb  jmp     loc_18006E642
0x18006e5c0  mov     ecx, cs:g_CiOptions
0x18006e5c6  mov     eax, [rbp+var_2C]
0x18006e5c9  bt      ecx, 12h
0x18006e5cd  jnb     short loc_18006E5D5
0x18006e5cf  or      eax, 1
0x18006e5d2  mov     [rbp+var_2C], eax
0x18006e5d5  bt      ecx, 13h
0x18006e5d9  jnb     short loc_18006E5E1
0x18006e5db  or      eax, 2
0x18006e5de  mov     [rbp+var_2C], eax
0x18006e5e1  bt      ecx, 11h
0x18006e5e5  jnb     short loc_18006E5EE
0x18006e5e7  bts     eax, 1Fh
0x18006e5eb  mov     [rbp+var_2C], eax
0x18006e5ee  lea     rax, [rbp+var_2C]
0x18006e5f2  mov     qword ptr [rbp+var_28.Size], 4
0x18006e5fa  mov     [rbp+var_28.Ptr], rax
0x18006e5fe  lea     rax, [rbp+var_30]
0x18006e602  mov     [rbp+var_18], rax
0x18006e606  mov     [rbp+var_10], 1
0x18006e60e  call    cs:__imp_IoGetActivityIdThread
0x18006e615  nop     dword ptr [rax+rax+00h]
0x18006e61a  lea     rcx, [rbp+var_28]
0x18006e61e  mov     r9d, 2; UserDataCount
0x18006e624  mov     [rsp+60h+UserData], rcx; UserData
0x18006e629  mov     r8, rax; ActivityId
0x18006e62c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e633  mov     rdx, rbx; EventDescriptor
0x18006e636  call    cs:__imp_EtwWrite
0x18006e63d  nop     dword ptr [rax+rax+00h]
0x18006e642  mov     rcx, [rbp+var_8]
0x18006e646  xor     rcx, rsp; StackCookie
0x18006e649  call    __security_check_cookie
0x18006e64e  mov     rbx, [rsp+60h+arg_0]
0x18006e653  add     rsp, 60h
0x18006e657  pop     rbp
0x18006e658  retn
```
