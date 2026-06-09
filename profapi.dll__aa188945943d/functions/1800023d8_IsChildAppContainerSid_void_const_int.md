# _IsChildAppContainerSid(void * const,int *)

- ea: `0x1800023d8`
- end: `0x180002452`
- name: `?_IsChildAppContainerSid@@YAJQEAXPEAH@Z`
- size: `122`
- prototype: `int __fastcall(void *const, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800017e4`
- `0x180001d3c`
- `0x180002650`

## callees

- `0x1800023d8`
- `0x180005b60`
- `0x18000d5fc`

## import_xrefs

- `ntdll!RtlGetAppContainerSidType` at `0x1800023f4`
- `ntdll!RtlGetAppContainerSidType` at `0x1800023f4`

## pseudocode

```c
int __fastcall _IsChildAppContainerSid(void *const a1, int *a2)
{
  int AppContainerSidType; // eax
  unsigned int v4; // r8d
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v8 = 0;
  AppContainerSidType = RtlGetAppContainerSidType(a1, &v8);
  if ( AppContainerSidType < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x39,
             v4,
             (const char *)(unsigned int)AppContainerSidType,
             v6);
  if ( v8 == 1 )
  {
    *a2 = 1;
    return 0;
  }
  if ( v8 == 2 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x41,
    (unsigned int)"minio\\profapi\\appcontainer.cpp",
    (const char *)0x80070057LL,
    v6);
  return -2147024809;
}

```

## disassembly

```asm
0x1800023d8  push    rbx; int
0x1800023da  sub     rsp, 20h
0x1800023de  mov     rbx, rdx
0x1800023e1  mov     dword ptr [rdx], 0
0x1800023e7  lea     rdx, [rsp+28h+arg_8]
0x1800023ec  mov     [rsp+28h+arg_8], 0
0x1800023f4  call    cs:__imp_RtlGetAppContainerSidType
0x1800023fa  test    eax, eax
0x1800023fc  js      short loc_180002414
0x1800023fe  cmp     [rsp+28h+arg_8], 1
0x180002403  jz      short loc_180002428
0x180002405  cmp     [rsp+28h+arg_8], 2
0x18000240a  jnz     short loc_180002430
0x18000240c  xor     eax, eax
0x18000240e  add     rsp, 20h
0x180002412  pop     rbx
0x180002413  retn
0x180002414  mov     rcx, [rsp+28h]; this
0x180002419  mov     r9d, eax; char *
0x18000241c  mov     edx, 39h ; '9'; void *
0x180002421  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180002426  jmp     short loc_18000240E
0x180002428  mov     dword ptr [rbx], 1
0x18000242e  jmp     short loc_18000240C
0x180002430  mov     rcx, [rsp+28h]; this
0x180002435  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000243c  mov     ebx, 80070057h
0x180002441  mov     edx, 41h ; 'A'; void *
0x180002446  mov     r9d, ebx; char *
0x180002449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000244e  mov     eax, ebx
0x180002450  jmp     short loc_18000240E
```
