# CiUpdatePolicies

- ea: `0x180071d98`
- end: `0x180071e37`
- name: `CiUpdatePolicies`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005ec0c`
- `0x180063230`
- `0x1800739e0`
- `0x180075c88`

## callees

- `0x180058048`
- `0x180071d98`
- `0x180071f7c`
- `0x180078720`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071e0f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071e0f`

## pseudocode

```c
__int64 __fastcall CiUpdatePolicies(unsigned int a1)
{
  int PolicyFiles; // ebx
  char v4; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v5; // [rsp+60h] [rbp+18h] BYREF
  __int64 v6; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  PolicyFiles = CipGetPolicyFiles(&v5, &v6);
  if ( PolicyFiles >= 0 )
  {
    PolicyFiles = CipRefreshPolicies(a1, v5, v6);
    if ( PolicyFiles >= 0 )
    {
      v4 = 2;
      ZwUpdateWnfStateData(&WNF_CI_CODEINTEGRITY_MODE_CHANGE, &v4, 1);
    }
  }
  SIPolicyFreePolicyData(v6, v5);
  return (unsigned int)PolicyFiles;
}

```

## disassembly

```asm
0x180071d98  mov     rax, rsp
0x180071d9b  mov     [rax+8], rbx
0x180071d9f  push    rdi
0x180071da0  sub     rsp, 40h
0x180071da4  mov     edi, ecx
0x180071da6  mov     dword ptr [rax+18h], 0
0x180071dad  lea     rcx, [rax+18h]
0x180071db1  mov     qword ptr [rax+20h], 0
0x180071db9  lea     rdx, [rax+20h]
0x180071dbd  call    CipGetPolicyFiles
0x180071dc2  mov     ebx, eax
0x180071dc4  test    eax, eax
0x180071dc6  js      short loc_180071E1B
0x180071dc8  mov     r8, [rsp+48h+arg_18]
0x180071dcd  mov     ecx, edi
0x180071dcf  mov     edx, [rsp+48h+arg_10]
0x180071dd3  call    CipRefreshPolicies
0x180071dd8  mov     ebx, eax
0x180071dda  test    eax, eax
0x180071ddc  js      short loc_180071E1B
0x180071dde  xor     r9d, r9d
0x180071de1  mov     [rsp+48h+var_18], 0
0x180071de9  mov     [rsp+48h+var_20], 0
0x180071df1  lea     rdx, [rsp+48h+arg_8]
0x180071df6  lea     rcx, WNF_CI_CODEINTEGRITY_MODE_CHANGE
0x180071dfd  mov     [rsp+48h+arg_8], 2
0x180071e02  mov     [rsp+48h+var_28], 0
0x180071e0b  lea     r8d, [r9+1]
0x180071e0f  call    cs:__imp_ZwUpdateWnfStateData
0x180071e16  nop     dword ptr [rax+rax+00h]
0x180071e1b  mov     edx, [rsp+48h+arg_10]
0x180071e1f  mov     rcx, [rsp+48h+arg_18]
0x180071e24  call    SIPolicyFreePolicyData
0x180071e29  mov     eax, ebx
0x180071e2b  mov     rbx, [rsp+48h+arg_0]
0x180071e30  add     rsp, 40h
0x180071e34  pop     rdi
0x180071e35  retn
```
