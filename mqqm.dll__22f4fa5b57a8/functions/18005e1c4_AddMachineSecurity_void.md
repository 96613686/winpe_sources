# AddMachineSecurity(void)

- ea: `0x18005e1c4`
- end: `0x18005e24a`
- name: `?AddMachineSecurity@@YAXXZ`
- size: `134`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002cd84`

## callees

- `0x18002c61c`
- `0x180048980`
- `0x18005e1c4`

## import_xrefs

- `msvcrt!free` at `0x18005e23d`
- `msvcrt!free` at `0x18005e23d`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005e20f`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18005e20f`
- `mqsec!MQSec_GetDefaultSecDescriptor` at `0x18005e1f8`
- `mqsec!MQSec_GetDefaultSecDescriptor` at `0x18005e1f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void AddMachineSecurity(void)
{
  PSECURITY_DESCRIPTOR v0; // rbx
  DWORD SecurityDescriptorLength; // eax
  int v2; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR v4; // [rsp+58h] [rbp+10h]

  pSecurityDescriptor = 0;
  if ( (int)MQSec_GetDefaultSecDescriptor(2, &pSecurityDescriptor, 0) >= 0 )
  {
    v0 = pSecurityDescriptor;
    v4 = pSecurityDescriptor;
    SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    v2 = SetMachineSecurityCache(pSecurityDescriptor, SecurityDescriptorLength);
    if ( v2 < 0 )
      LogMsgHR(v2, (wchar_t *)L"setup", 0x5Au);
    free(v0);
  }
}

```

## disassembly

```asm
0x18005e1c4  mov     rax, rsp
0x18005e1c7  push    rbx
0x18005e1c8  sub     rsp, 40h
0x18005e1cc  mov     qword ptr [rax+8], 0
0x18005e1d4  mov     qword ptr [rax-18h], 0
0x18005e1dc  mov     dword ptr [rax-20h], 1
0x18005e1e3  mov     dword ptr [rax-28h], 0
0x18005e1ea  xor     r9d, r9d
0x18005e1ed  xor     r8d, r8d
0x18005e1f0  lea     rdx, [rax+8]
0x18005e1f4  lea     ecx, [r9+2]
0x18005e1f8  call    cs:__imp_?MQSec_GetDefaultSecDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultSecDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *)
0x18005e1fe  test    eax, eax
0x18005e200  js      short loc_18005E244
0x18005e202  mov     rbx, [rsp+48h+pSecurityDescriptor]
0x18005e207  mov     [rsp+48h+arg_8], rbx
0x18005e20c  mov     rcx, rbx; pSecurityDescriptor
0x18005e20f  call    cs:__imp_GetSecurityDescriptorLength
0x18005e215  mov     edx, eax; unsigned int
0x18005e217  mov     rcx, [rsp+48h+pSecurityDescriptor]; void *
0x18005e21c  call    ?SetMachineSecurityCache@@YAJPEBXK@Z; SetMachineSecurityCache(void const *,ulong)
0x18005e221  test    eax, eax
0x18005e223  jns     short loc_18005E23A
0x18005e225  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x18005e22b  lea     rdx, aSetup; "setup"
0x18005e232  mov     ecx, eax; int
0x18005e234  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18005e239  nop
0x18005e23a  mov     rcx, rbx; Block
0x18005e23d  call    cs:__imp_free
0x18005e243  nop
0x18005e244  add     rsp, 40h
0x18005e248  pop     rbx
0x18005e249  retn
```
