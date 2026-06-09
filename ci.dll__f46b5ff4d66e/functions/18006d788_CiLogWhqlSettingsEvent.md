# CiLogWhqlSettingsEvent

- ea: `0x18006d788`
- end: `0x18006d886`
- name: `CiLogWhqlSettingsEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e4cb8`

## callees

- `0x18002bef0`
- `0x18006d788`
- `0x1800a5bd4`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d7d5`
- `ntoskrnl!EtwEventEnabled` at `0x18006d7d5`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d83a`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d83a`
- `ntoskrnl!EtwWrite` at `0x18006d862`
- `ntoskrnl!EtwWrite` at `0x18006d862`

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
0x18006d788  mov     [rsp-8+arg_0], rbx
0x18006d78d  push    rbp
0x18006d78e  mov     rbp, rsp
0x18006d791  sub     rsp, 60h
0x18006d795  mov     rax, cs:__security_cookie
0x18006d79c  xor     rax, rsp
0x18006d79f  mov     [rbp+var_8], rax
0x18006d7a3  lea     rcx, [rbp+var_30]
0x18006d7a7  mov     [rbp+var_2C], 0
0x18006d7ae  mov     [rbp+var_30], 0
0x18006d7b2  call    CipWhqlEnforcementEnabled
0x18006d7b7  test    al, al
0x18006d7b9  lea     rcx, WhqlEnforcementEnabled
0x18006d7c0  lea     rbx, WhqlEnforcementDisabled
0x18006d7c7  cmovnz  rbx, rcx
0x18006d7cb  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d7d2  mov     rdx, rbx; EventDescriptor
0x18006d7d5  call    cs:__imp_EtwEventEnabled
0x18006d7dc  nop     dword ptr [rax+rax+00h]
0x18006d7e1  test    al, al
0x18006d7e3  jnz     short loc_18006D7EC
0x18006d7e5  xor     eax, eax
0x18006d7e7  jmp     loc_18006D86E
0x18006d7ec  mov     ecx, cs:g_CiOptions
0x18006d7f2  mov     eax, [rbp+var_2C]
0x18006d7f5  bt      ecx, 12h
0x18006d7f9  jnb     short loc_18006D801
0x18006d7fb  or      eax, 1
0x18006d7fe  mov     [rbp+var_2C], eax
0x18006d801  bt      ecx, 13h
0x18006d805  jnb     short loc_18006D80D
0x18006d807  or      eax, 2
0x18006d80a  mov     [rbp+var_2C], eax
0x18006d80d  bt      ecx, 11h
0x18006d811  jnb     short loc_18006D81A
0x18006d813  bts     eax, 1Fh
0x18006d817  mov     [rbp+var_2C], eax
0x18006d81a  lea     rax, [rbp+var_2C]
0x18006d81e  mov     qword ptr [rbp+var_28.Size], 4
0x18006d826  mov     [rbp+var_28.Ptr], rax
0x18006d82a  lea     rax, [rbp+var_30]
0x18006d82e  mov     [rbp+var_18], rax
0x18006d832  mov     [rbp+var_10], 1
0x18006d83a  call    cs:__imp_IoGetActivityIdThread
0x18006d841  nop     dword ptr [rax+rax+00h]
0x18006d846  lea     rcx, [rbp+var_28]
0x18006d84a  mov     r9d, 2; UserDataCount
0x18006d850  mov     [rsp+60h+UserData], rcx; UserData
0x18006d855  mov     r8, rax; ActivityId
0x18006d858  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d85f  mov     rdx, rbx; EventDescriptor
0x18006d862  call    cs:__imp_EtwWrite
0x18006d869  nop     dword ptr [rax+rax+00h]
0x18006d86e  mov     rcx, [rbp+var_8]
0x18006d872  xor     rcx, rsp; StackCookie
0x18006d875  call    __security_check_cookie
0x18006d87a  mov     rbx, [rsp+60h+arg_0]
0x18006d87f  add     rsp, 60h
0x18006d883  pop     rbp
0x18006d884  retn
```
