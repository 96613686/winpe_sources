# CiLogWhqlSettingsEvent

- ea: `0x18006e83c`
- end: `0x18006e93a`
- name: `CiLogWhqlSettingsEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e5228`

## callees

- `0x18002c0d0`
- `0x18006e83c`
- `0x1800a6da4`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006e889`
- `ntoskrnl!EtwEventEnabled` at `0x18006e889`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e8ee`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e8ee`
- `ntoskrnl!EtwWrite` at `0x18006e916`
- `ntoskrnl!EtwWrite` at `0x18006e916`

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
0x18006e83c  mov     [rsp-8+arg_0], rbx
0x18006e841  push    rbp
0x18006e842  mov     rbp, rsp
0x18006e845  sub     rsp, 60h
0x18006e849  mov     rax, cs:__security_cookie
0x18006e850  xor     rax, rsp
0x18006e853  mov     [rbp+var_8], rax
0x18006e857  lea     rcx, [rbp+var_30]
0x18006e85b  mov     [rbp+var_2C], 0
0x18006e862  mov     [rbp+var_30], 0
0x18006e866  call    CipWhqlEnforcementEnabled
0x18006e86b  test    al, al
0x18006e86d  lea     rcx, WhqlEnforcementEnabled
0x18006e874  lea     rbx, WhqlEnforcementDisabled
0x18006e87b  cmovnz  rbx, rcx
0x18006e87f  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e886  mov     rdx, rbx; EventDescriptor
0x18006e889  call    cs:__imp_EtwEventEnabled
0x18006e890  nop     dword ptr [rax+rax+00h]
0x18006e895  test    al, al
0x18006e897  jnz     short loc_18006E8A0
0x18006e899  xor     eax, eax
0x18006e89b  jmp     loc_18006E922
0x18006e8a0  mov     ecx, cs:g_CiOptions
0x18006e8a6  mov     eax, [rbp+var_2C]
0x18006e8a9  bt      ecx, 12h
0x18006e8ad  jnb     short loc_18006E8B5
0x18006e8af  or      eax, 1
0x18006e8b2  mov     [rbp+var_2C], eax
0x18006e8b5  bt      ecx, 13h
0x18006e8b9  jnb     short loc_18006E8C1
0x18006e8bb  or      eax, 2
0x18006e8be  mov     [rbp+var_2C], eax
0x18006e8c1  bt      ecx, 11h
0x18006e8c5  jnb     short loc_18006E8CE
0x18006e8c7  bts     eax, 1Fh
0x18006e8cb  mov     [rbp+var_2C], eax
0x18006e8ce  lea     rax, [rbp+var_2C]
0x18006e8d2  mov     qword ptr [rbp+var_28.Size], 4
0x18006e8da  mov     [rbp+var_28.Ptr], rax
0x18006e8de  lea     rax, [rbp+var_30]
0x18006e8e2  mov     [rbp+var_18], rax
0x18006e8e6  mov     [rbp+var_10], 1
0x18006e8ee  call    cs:__imp_IoGetActivityIdThread
0x18006e8f5  nop     dword ptr [rax+rax+00h]
0x18006e8fa  lea     rcx, [rbp+var_28]
0x18006e8fe  mov     r9d, 2; UserDataCount
0x18006e904  mov     [rsp+60h+UserData], rcx; UserData
0x18006e909  mov     r8, rax; ActivityId
0x18006e90c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e913  mov     rdx, rbx; EventDescriptor
0x18006e916  call    cs:__imp_EtwWrite
0x18006e91d  nop     dword ptr [rax+rax+00h]
0x18006e922  mov     rcx, [rbp+var_8]
0x18006e926  xor     rcx, rsp; StackCookie
0x18006e929  call    __security_check_cookie
0x18006e92e  mov     rbx, [rsp+60h+arg_0]
0x18006e933  add     rsp, 60h
0x18006e937  pop     rbp
0x18006e938  retn
```
