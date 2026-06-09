# AppContainerRegistrationHelper::IsAppContainerToken(void *,int *)

- ea: `0x18000beb0`
- end: `0x18000bf1a`
- name: `?IsAppContainerToken@AppContainerRegistrationHelper@@SAJPEAXPEAH@Z`
- size: `106`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`
- `0x18000ca58`
- `0x18001fed0`

## callees

- `0x18000beb0`
- `0x18000f83c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000bee2`
- `ntdll!NtQueryInformationToken` at `0x18000bee2`

## pseudocode

```c
int __fastcall AppContainerRegistrationHelper::IsAppContainerToken(void *a1, int *a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // r8d
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int TokenInformation; // [rsp+50h] [rbp+18h] BYREF
  ULONG v9; // [rsp+58h] [rbp+20h] BYREF

  TokenInformation = 0;
  v9 = 0;
  v3 = NtQueryInformationToken(a1, TokenIsAppContainer, &TokenInformation, 4u, &v9);
  if ( v3 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x168,
             v4,
             (const char *)(unsigned int)v3,
             ReturnLength);
  *a2 = TokenInformation != 0;
  return 0;
}

```

## disassembly

```asm
0x18000beb0  push    rbx
0x18000beb2  sub     rsp, 30h
0x18000beb6  mov     r9d, 4; TokenInformationLength
0x18000bebc  mov     [rsp+38h+TokenInformation], 0
0x18000bec4  mov     rbx, rdx
0x18000bec7  mov     [rsp+38h+arg_18], 0
0x18000becf  lea     rax, [rsp+38h+arg_18]
0x18000bed4  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18000bed9  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18000bede  lea     edx, [r9+19h]; TokenInformationClass
0x18000bee2  call    cs:__imp_NtQueryInformationToken
0x18000bee9  nop     dword ptr [rax+rax+00h]
0x18000beee  test    eax, eax
0x18000bef0  js      short loc_18000BF06
0x18000bef2  xor     eax, eax
0x18000bef4  cmp     [rsp+38h+TokenInformation], eax
0x18000bef8  setnz   al
0x18000befb  mov     [rbx], eax
0x18000befd  xor     eax, eax
0x18000beff  add     rsp, 30h
0x18000bf03  pop     rbx
0x18000bf04  retn
0x18000bf06  mov     rcx, [rsp+38h]; this
0x18000bf0b  mov     r9d, eax; char *
0x18000bf0e  mov     edx, 168h; void *
0x18000bf13  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000bf18  jmp     short loc_18000BEFF
```
