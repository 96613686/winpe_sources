# AppContainerRegistrationHelper::IsChildAppContainerSid(void * const,int *)

- ea: `0x18000c770`
- end: `0x18000c7bf`
- name: `?IsChildAppContainerSid@AppContainerRegistrationHelper@@CAJQEAXPEAH@Z`
- size: `79`
- prototype: `static int(void *const, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016740`
- `0x180017014`

## callees

- `0x18000c770`
- `0x18000f83c`

## import_xrefs

- `ntdll!RtlGetAppContainerSidType` at `0x18000c786`
- `ntdll!RtlGetAppContainerSidType` at `0x18000c786`

## pseudocode

```c
int __fastcall AppContainerRegistrationHelper::IsChildAppContainerSid(void *const a1, int *a2)
{
  int AppContainerSidType; // eax
  unsigned int v4; // r8d
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  AppContainerSidType = RtlGetAppContainerSidType(a1, &v8);
  if ( AppContainerSidType < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x173,
             v4,
             (const char *)(unsigned int)AppContainerSidType,
             v6);
  *a2 = v8 == 1;
  return 0;
}

```

## disassembly

```asm
0x18000c770  push    rbx; int
0x18000c772  sub     rsp, 20h
0x18000c776  mov     rbx, rdx
0x18000c779  mov     [rsp+28h+arg_10], 0
0x18000c781  lea     rdx, [rsp+28h+arg_10]
0x18000c786  call    cs:__imp_RtlGetAppContainerSidType
0x18000c78d  nop     dword ptr [rax+rax+00h]
0x18000c792  test    eax, eax
0x18000c794  jns     short loc_18000C7AA
0x18000c796  mov     rcx, [rsp+28h]; this
0x18000c79b  mov     r9d, eax; char *
0x18000c79e  mov     edx, 173h; void *
0x18000c7a3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000c7a8  jmp     short loc_18000C7B8
0x18000c7aa  xor     eax, eax
0x18000c7ac  cmp     [rsp+28h+arg_10], 1
0x18000c7b1  setz    al
0x18000c7b4  mov     [rbx], eax
0x18000c7b6  xor     eax, eax
0x18000c7b8  add     rsp, 20h
0x18000c7bc  pop     rbx
0x18000c7bd  retn
```
