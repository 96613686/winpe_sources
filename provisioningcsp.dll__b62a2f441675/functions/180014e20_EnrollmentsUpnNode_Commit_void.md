# EnrollmentsUpnNode::Commit(void)

- ea: `0x180014e20`
- end: `0x180014e67`
- name: `?Commit@EnrollmentsUpnNode@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(EnrollmentsUpnNode *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014e20`
- `0x180014f14`
- `0x180016a90`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180014e3b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180014e3b`

## pseudocode

```c
Enroll *__fastcall EnrollmentsUpnNode::Commit(EnrollmentsUpnNode *this)
{
  Enroll *result; // rax
  int v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v3, 0);
  if ( v3 != 10 )
    return EnrollmentsUpnNode::Enroll((EnrollmentsUpnNode *)((char *)this - 8));
  result = (Enroll *)EnrollmentsUpnNode::EnsureNetworkReady();
  if ( (int)result >= 0 )
    return EnrollmentsUpnNode::Enroll((EnrollmentsUpnNode *)((char *)this - 8));
  return result;
}

```

## disassembly

```asm
0x180014e20  push    rbx
0x180014e22  sub     rsp, 20h
0x180014e26  mov     rbx, rcx
0x180014e29  mov     [rsp+28h+arg_8], 0
0x180014e31  xor     ecx, ecx
0x180014e33  lea     rdx, [rsp+28h+arg_8]
0x180014e38  xor     r8d, r8d
0x180014e3b  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180014e42  nop     dword ptr [rax+rax+00h]
0x180014e47  cmp     [rsp+28h+arg_8], 0Ah
0x180014e4c  jnz     short loc_180014E57
0x180014e4e  call    ?EnsureNetworkReady@EnrollmentsUpnNode@@CAJK@Z; EnrollmentsUpnNode::EnsureNetworkReady(ulong)
0x180014e53  test    eax, eax
0x180014e55  js      short loc_180014E60
0x180014e57  lea     rcx, [rbx-8]; this
0x180014e5b  call    ?Enroll@EnrollmentsUpnNode@@QEAAJXZ; EnrollmentsUpnNode::Enroll(void)
0x180014e60  add     rsp, 20h
0x180014e64  pop     rbx
0x180014e65  retn
```
