# container_runtime::GetServiceSessionId(void *)

- ea: `0x180007674`
- end: `0x18000771f`
- name: `?GetServiceSessionId@container_runtime@@YAKPEAX@Z`
- size: `171`
- prototype: `unsigned int __fastcall(container_runtime *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e140`
- `0x1800124b0`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x180007674`
- `0x180007c2c`
- `0x18000b4bc`

## import_xrefs

- `ntdll!NtQueryInformationJobObject` at `0x1800076d4`
- `ntdll!NtQueryInformationJobObject` at `0x1800076d4`

## pseudocode

```c
__int64 __fastcall container_runtime::GetServiceSessionId(container_runtime *this, void *a2)
{
  void *v3; // rdx
  NTSTATUS v4; // eax
  int ReturnLength; // [rsp+20h] [rbp-298h]
  unsigned int JobInformation; // [rsp+30h] [rbp-288h] BYREF
  _BYTE v8[620]; // [rsp+34h] [rbp-284h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  memset_0(v8, 0, sizeof(v8));
  JobInformation = 0;
  if ( container_runtime::IsServerContainer(this, v3) )
  {
    v4 = NtQueryInformationJobObject(this, JobObjectAssociateCompletionPortInformation|0x20, &JobInformation, 0x270u, 0);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime.cpp",
        (const char *)(unsigned int)v4,
        ReturnLength);
  }
  return JobInformation;
}

```

## disassembly

```asm
0x180007674  push    rbx
0x180007676  sub     rsp, 2B0h
0x18000767d  mov     rax, cs:__security_cookie
0x180007684  xor     rax, rsp
0x180007687  mov     [rsp+2B8h+var_18], rax
0x18000768f  mov     rbx, rcx
0x180007692  xor     edx, edx; Val
0x180007694  lea     rcx, [rsp+2B8h+var_284]; void *
0x180007699  mov     r8d, 26Ch; Size
0x18000769f  call    memset_0
0x1800076a4  mov     rcx, rbx; this
0x1800076a7  mov     [rsp+2B8h+JobInformation], 0
0x1800076af  call    ?IsServerContainer@container_runtime@@YA_NPEAX@Z; container_runtime::IsServerContainer(void *)
0x1800076b4  test    al, al
0x1800076b6  jz      short loc_1800076E4
0x1800076b8  mov     r9d, 270h; JobInformationLength
0x1800076be  mov     qword ptr [rsp+2B8h+ReturnLength], 0; int
0x1800076c7  lea     r8, [rsp+2B8h+JobInformation]; JobInformation
0x1800076cc  mov     edx, 27h ; '''; JobInformationClass
0x1800076d1  mov     rcx, rbx; JobHandle
0x1800076d4  call    cs:__imp_NtQueryInformationJobObject
0x1800076db  nop     dword ptr [rax+rax+00h]
0x1800076e0  test    eax, eax
0x1800076e2  js      short loc_180007702
0x1800076e4  mov     eax, [rsp+2B8h+JobInformation]
0x1800076e8  mov     rcx, [rsp+2B8h+var_18]
0x1800076f0  xor     rcx, rsp; StackCookie
0x1800076f3  call    __security_check_cookie
0x1800076f8  add     rsp, 2B0h
0x1800076ff  pop     rbx
0x180007700  retn
0x180007702  mov     rcx, [rsp+2B8h]; this
0x18000770a  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\container"...
0x180007711  mov     r9d, eax; char *
0x180007714  mov     edx, 13Eh; void *
0x180007719  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
