# CiIsPermissionsElevatedOrSystem

- ea: `0x18005e394`
- end: `0x18005e40b`
- name: `CiIsPermissionsElevatedOrSystem`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18005e420`
- `0x18005e510`

## callees

- `0x18005e394`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005e3e9`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005e3e9`
- `ntoskrnl!ExGetPreviousMode` at `0x18005e39d`
- `ntoskrnl!ExGetPreviousMode` at `0x18005e39d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005e3b9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005e3b9`
- `ntoskrnl!SeExports` at `0x18005e3a9`
- `ntoskrnl!SeExports` at `0x18005e3d1`

## pseudocode

```c
bool CiIsPermissionsElevatedOrSystem()
{
  KPROCESSOR_MODE PreviousMode; // al
  BOOLEAN v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  PreviousMode = ExGetPreviousMode();
  v2 = SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, PreviousMode);
  if ( v2 )
    return 1;
  if ( (int)RtlCheckTokenMembership(0, SeExports->SeAliasAdminsSid, &v2) < 0 )
    return 0;
  return v2 != 0;
}

```

## disassembly

```asm
0x18005e394  sub     rsp, 28h
0x18005e398  mov     [rsp+28h+arg_0], 0
0x18005e39d  call    cs:__imp_ExGetPreviousMode
0x18005e3a4  nop     dword ptr [rax+rax+00h]
0x18005e3a9  mov     rcx, cs:__imp_SeExports
0x18005e3b0  mov     dl, al; PreviousMode
0x18005e3b2  mov     rcx, [rcx]
0x18005e3b5  mov     rcx, [rcx+28h]; PrivilegeValue
0x18005e3b9  call    cs:__imp_SeSinglePrivilegeCheck
0x18005e3c0  nop     dword ptr [rax+rax+00h]
0x18005e3c5  mov     [rsp+28h+arg_0], al
0x18005e3c9  test    al, al
0x18005e3cb  jz      short loc_18005E3D1
0x18005e3cd  mov     al, 1
0x18005e3cf  jmp     short loc_18005E405
0x18005e3d1  mov     rax, cs:__imp_SeExports
0x18005e3d8  lea     r8, [rsp+28h+arg_0]
0x18005e3dd  xor     ecx, ecx
0x18005e3df  mov     rdx, [rax]
0x18005e3e2  mov     rdx, [rdx+110h]
0x18005e3e9  call    cs:__imp_RtlCheckTokenMembership
0x18005e3f0  nop     dword ptr [rax+rax+00h]
0x18005e3f5  test    eax, eax
0x18005e3f7  js      short loc_18005E403
0x18005e3f9  cmp     [rsp+28h+arg_0], 0
0x18005e3fe  setnz   al
0x18005e401  jmp     short loc_18005E405
0x18005e403  xor     al, al
0x18005e405  add     rsp, 28h
0x18005e409  retn
```
