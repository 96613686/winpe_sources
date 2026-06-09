# GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)

- ea: `0x14000d314`
- end: `0x14000d366`
- name: `?GetRegistrationRootKeyFromIntegrityLevel@@YAJPEAPEAUHKEY__@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005188`
- `0x1400061e4`
- `0x140006fa4`
- `0x140007340`

## callees

- `0x14000d2a8`
- `0x14000d314`

## pseudocode

```c
__int64 __fastcall GetRegistrationRootKeyFromIntegrityLevel(HKEY *a1)
{
  __int64 result; // rax
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v3 = 0;
  result = GetInstallScopeFromIntegrityLevel(&v3);
  if ( !(_DWORD)result )
  {
    if ( v3 == 1 )
    {
      *a1 = HKEY_LOCAL_MACHINE;
    }
    else if ( v3 == 2 )
    {
      *a1 = HKEY_CURRENT_USER;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d314  push    rbx
0x14000d316  sub     rsp, 20h
0x14000d31a  mov     rbx, rcx
0x14000d31d  mov     qword ptr [rcx], 0
0x14000d324  lea     rcx, [rsp+28h+arg_0]; unsigned int *
0x14000d329  mov     [rsp+28h+arg_0], 0
0x14000d331  call    ?GetInstallScopeFromIntegrityLevel@@YAJPEAK@Z; GetInstallScopeFromIntegrityLevel(ulong *)
0x14000d336  test    eax, eax
0x14000d338  jnz     short loc_14000D35F
0x14000d33a  cmp     [rsp+28h+arg_0], 1
0x14000d33f  jnz     short loc_14000D34A
0x14000d341  mov     qword ptr [rbx], 0FFFFFFFF80000002h
0x14000d348  jmp     short loc_14000D35F
0x14000d34a  cmp     [rsp+28h+arg_0], 2
0x14000d34f  jnz     short loc_14000D35A
0x14000d351  mov     qword ptr [rbx], 0FFFFFFFF80000001h
0x14000d358  jmp     short loc_14000D35F
0x14000d35a  mov     eax, 80004005h
0x14000d35f  add     rsp, 20h
0x14000d363  pop     rbx
0x14000d364  retn
```
