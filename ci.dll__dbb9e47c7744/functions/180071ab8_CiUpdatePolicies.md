# CiUpdatePolicies

- ea: `0x180071ab8`
- end: `0x180071b57`
- name: `CiUpdatePolicies`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005ec6c`
- `0x1800630c0`
- `0x180073700`
- `0x1800759a8`

## callees

- `0x180058120`
- `0x180071ab8`
- `0x180071c9c`
- `0x180078440`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071b2f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180071b2f`

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
0x180071ab8  mov     rax, rsp
0x180071abb  mov     [rax+8], rbx
0x180071abf  push    rdi
0x180071ac0  sub     rsp, 40h
0x180071ac4  mov     edi, ecx
0x180071ac6  mov     dword ptr [rax+18h], 0
0x180071acd  lea     rcx, [rax+18h]
0x180071ad1  mov     qword ptr [rax+20h], 0
0x180071ad9  lea     rdx, [rax+20h]
0x180071add  call    CipGetPolicyFiles
0x180071ae2  mov     ebx, eax
0x180071ae4  test    eax, eax
0x180071ae6  js      short loc_180071B3B
0x180071ae8  mov     r8, [rsp+48h+arg_18]
0x180071aed  mov     ecx, edi
0x180071aef  mov     edx, [rsp+48h+arg_10]
0x180071af3  call    CipRefreshPolicies
0x180071af8  mov     ebx, eax
0x180071afa  test    eax, eax
0x180071afc  js      short loc_180071B3B
0x180071afe  xor     r9d, r9d
0x180071b01  mov     [rsp+48h+var_18], 0
0x180071b09  mov     [rsp+48h+var_20], 0
0x180071b11  lea     rdx, [rsp+48h+arg_8]
0x180071b16  lea     rcx, WNF_CI_CODEINTEGRITY_MODE_CHANGE
0x180071b1d  mov     [rsp+48h+arg_8], 2
0x180071b22  mov     [rsp+48h+var_28], 0
0x180071b2b  lea     r8d, [r9+1]
0x180071b2f  call    cs:__imp_ZwUpdateWnfStateData
0x180071b36  nop     dword ptr [rax+rax+00h]
0x180071b3b  mov     edx, [rsp+48h+arg_10]
0x180071b3f  mov     rcx, [rsp+48h+arg_18]
0x180071b44  call    SIPolicyFreePolicyData
0x180071b49  mov     eax, ebx
0x180071b4b  mov     rbx, [rsp+48h+arg_0]
0x180071b50  add     rsp, 40h
0x180071b54  pop     rdi
0x180071b55  retn
```
