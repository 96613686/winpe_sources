# CiIsPermissionsElevatedOrSystem

- ea: `0x18005ea94`
- end: `0x18005eb0b`
- name: `CiIsPermissionsElevatedOrSystem`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18005eb20`
- `0x18005ec10`

## callees

- `0x18005ea94`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x18005eae9`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005eae9`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ea9d`
- `ntoskrnl!ExGetPreviousMode` at `0x18005ea9d`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005eab9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x18005eab9`
- `ntoskrnl!SeExports` at `0x18005eaa9`
- `ntoskrnl!SeExports` at `0x18005ead1`

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
0x18005ea94  sub     rsp, 28h
0x18005ea98  mov     [rsp+28h+arg_0], 0
0x18005ea9d  call    cs:__imp_ExGetPreviousMode
0x18005eaa4  nop     dword ptr [rax+rax+00h]
0x18005eaa9  mov     rcx, cs:__imp_SeExports
0x18005eab0  mov     dl, al; PreviousMode
0x18005eab2  mov     rcx, [rcx]
0x18005eab5  mov     rcx, [rcx+28h]; PrivilegeValue
0x18005eab9  call    cs:__imp_SeSinglePrivilegeCheck
0x18005eac0  nop     dword ptr [rax+rax+00h]
0x18005eac5  mov     [rsp+28h+arg_0], al
0x18005eac9  test    al, al
0x18005eacb  jz      short loc_18005EAD1
0x18005eacd  mov     al, 1
0x18005eacf  jmp     short loc_18005EB05
0x18005ead1  mov     rax, cs:__imp_SeExports
0x18005ead8  lea     r8, [rsp+28h+arg_0]
0x18005eadd  xor     ecx, ecx
0x18005eadf  mov     rdx, [rax]
0x18005eae2  mov     rdx, [rdx+110h]
0x18005eae9  call    cs:__imp_RtlCheckTokenMembership
0x18005eaf0  nop     dword ptr [rax+rax+00h]
0x18005eaf5  test    eax, eax
0x18005eaf7  js      short loc_18005EB03
0x18005eaf9  cmp     [rsp+28h+arg_0], 0
0x18005eafe  setnz   al
0x18005eb01  jmp     short loc_18005EB05
0x18005eb03  xor     al, al
0x18005eb05  add     rsp, 28h
0x18005eb09  retn
```
