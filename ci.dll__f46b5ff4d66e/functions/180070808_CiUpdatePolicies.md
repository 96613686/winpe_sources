# CiUpdatePolicies

- ea: `0x180070808`
- end: `0x1800708a7`
- name: `CiUpdatePolicies`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e56c`
- `0x180062880`
- `0x180072450`
- `0x1800743dc`

## callees

- `0x180057408`
- `0x180070808`
- `0x1800709ec`
- `0x180076e90`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x18007087f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x18007087f`

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
0x180070808  mov     rax, rsp
0x18007080b  mov     [rax+8], rbx
0x18007080f  push    rdi
0x180070810  sub     rsp, 40h
0x180070814  mov     edi, ecx
0x180070816  mov     dword ptr [rax+18h], 0
0x18007081d  lea     rcx, [rax+18h]
0x180070821  mov     qword ptr [rax+20h], 0
0x180070829  lea     rdx, [rax+20h]
0x18007082d  call    CipGetPolicyFiles
0x180070832  mov     ebx, eax
0x180070834  test    eax, eax
0x180070836  js      short loc_18007088B
0x180070838  mov     r8, [rsp+48h+arg_18]
0x18007083d  mov     ecx, edi
0x18007083f  mov     edx, [rsp+48h+arg_10]
0x180070843  call    CipRefreshPolicies
0x180070848  mov     ebx, eax
0x18007084a  test    eax, eax
0x18007084c  js      short loc_18007088B
0x18007084e  xor     r9d, r9d
0x180070851  mov     [rsp+48h+var_18], 0
0x180070859  mov     [rsp+48h+var_20], 0
0x180070861  lea     rdx, [rsp+48h+arg_8]
0x180070866  lea     rcx, WNF_CI_CODEINTEGRITY_MODE_CHANGE
0x18007086d  mov     [rsp+48h+arg_8], 2
0x180070872  mov     [rsp+48h+var_28], 0
0x18007087b  lea     r8d, [r9+1]
0x18007087f  call    cs:__imp_ZwUpdateWnfStateData
0x180070886  nop     dword ptr [rax+rax+00h]
0x18007088b  mov     edx, [rsp+48h+arg_10]
0x18007088f  mov     rcx, [rsp+48h+arg_18]
0x180070894  call    SIPolicyFreePolicyData
0x180070899  mov     eax, ebx
0x18007089b  mov     rbx, [rsp+48h+arg_0]
0x1800708a0  add     rsp, 40h
0x1800708a4  pop     rdi
0x1800708a5  retn
```
