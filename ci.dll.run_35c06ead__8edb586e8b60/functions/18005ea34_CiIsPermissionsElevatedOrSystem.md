# CiIsPermissionsElevatedOrSystem

- ea: `0x18005ea34`
- end: `0x18005eaab`
- name: `CiIsPermissionsElevatedOrSystem`
- size: `119`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18005eac0`
- `0x18005ebb0`

## callees

- `0x18005ea34`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ea89`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005ea89`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ea3d`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ea3d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005ea59`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005ea59`
- `ntoskrnl!SeExports` at `0x18005ea49`
- `ntoskrnl!SeExports` at `0x18005ea71`

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
0x18005ea34  sub     rsp, 28h
0x18005ea38  mov     [rsp+28h+arg_0], 0
0x18005ea3d  call    cs:__imp_ExGetPreviousMode
0x18005ea44  nop     dword ptr [rax+rax+00h]
0x18005ea49  mov     rcx, cs:__imp_SeExports
0x18005ea50  mov     dl, al; PreviousMode
0x18005ea52  mov     rcx, [rcx]
0x18005ea55  mov     rcx, [rcx+28h]; PrivilegeValue
0x18005ea59  call    cs:__imp_SeSinglePrivilegeCheck
0x18005ea60  nop     dword ptr [rax+rax+00h]
0x18005ea65  mov     [rsp+28h+arg_0], al
0x18005ea69  test    al, al
0x18005ea6b  jz      short loc_18005EA71
0x18005ea6d  mov     al, 1
0x18005ea6f  jmp     short loc_18005EAA5
0x18005ea71  mov     rax, cs:__imp_SeExports
0x18005ea78  lea     r8, [rsp+28h+arg_0]
0x18005ea7d  xor     ecx, ecx
0x18005ea7f  mov     rdx, [rax]
0x18005ea82  mov     rdx, [rdx+110h]
0x18005ea89  call    cs:__imp_RtlCheckTokenMembership
0x18005ea90  nop     dword ptr [rax+rax+00h]
0x18005ea95  test    eax, eax
0x18005ea97  js      short loc_18005EAA3
0x18005ea99  cmp     [rsp+28h+arg_0], 0
0x18005ea9e  setnz   al
0x18005eaa1  jmp     short loc_18005EAA5
0x18005eaa3  xor     al, al
0x18005eaa5  add     rsp, 28h
0x18005eaa9  retn
```
