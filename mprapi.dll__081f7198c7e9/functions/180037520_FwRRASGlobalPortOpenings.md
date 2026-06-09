# FwRRASGlobalPortOpenings

- ea: `0x180037520`
- end: `0x180037654`
- name: `FwRRASGlobalPortOpenings`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000aafc`

## callees

- `0x180037520`
- `0x180051136`

## import_xrefs

- `FirewallAPI!FWEnumFirewallRules` at `0x1800375a5`
- `FirewallAPI!FWEnumFirewallRules` at `0x1800375a5`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003756a`
- `FirewallAPI!FWOpenPolicyStore` at `0x18003756a`
- `FirewallAPI!FWSetFirewallRule` at `0x180037612`
- `FirewallAPI!FWSetFirewallRule` at `0x180037612`
- `FirewallAPI!FWFreeFirewallRules` at `0x180037633`
- `FirewallAPI!FWFreeFirewallRules` at `0x180037633`
- `FirewallAPI!FWClosePolicyStore` at `0x180037643`
- `FirewallAPI!FWClosePolicyStore` at `0x180037643`

## string_xrefs

- `0x1800375cc`: `@FirewallAPI.dll,-33752`
- `0x1800375e3`: `@sstpsvc.dll,-35001`

## pseudocode

```c
__int64 FwRRASGlobalPortOpenings()
{
  unsigned int v0; // edi
  __int64 *v1; // rbx
  __int16 v2; // ax
  int v4; // [rsp+58h] [rbp+10h] BYREF
  __int64 v5; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v6; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v0 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v5);
  if ( !v0 )
  {
    v0 = FWEnumFirewallRules(v5, 4294901760LL, 0x7FFFFFFF, 1, &v4, &v6);
    if ( !v0 )
    {
      v1 = v6;
      if ( !v6 )
        goto LABEL_12;
      do
      {
        if ( v1[39]
          && (!wcscmp_0(L"@FirewallAPI.dll,-33752", (const wchar_t *)v1[39])
           || !wcscmp_0(L"@sstpsvc.dll,-35001", (const wchar_t *)v1[39])) )
        {
          v2 = *((_WORD *)v1 + 146);
          if ( (v2 & 1) == 0 )
          {
            *((_WORD *)v1 + 146) = v2 | 1;
            v0 = FWSetFirewallRule(v5, v1);
            if ( v0 )
              break;
          }
        }
        v1 = (__int64 *)*v1;
      }
      while ( v1 );
    }
  }
  if ( v6 )
    FWFreeFirewallRules(v6);
LABEL_12:
  if ( v5 )
    FWClosePolicyStore();
  return v0;
}

```

## disassembly

```asm
0x180037520  mov     rax, rsp
0x180037523  mov     [rax+18h], r8
0x180037527  mov     [rax+10h], edx
0x18003752a  push    rbx
0x18003752b  push    rdi
0x18003752c  push    r14
0x18003752e  sub     rsp, 30h
0x180037532  mov     dword ptr [rax+10h], 0
0x180037539  mov     r8d, 2
0x18003753f  mov     qword ptr [rax+18h], 0
0x180037547  mov     ecx, 221h
0x18003754c  mov     qword ptr [rax+20h], 0
0x180037554  lea     rax, [rax+18h]
0x180037558  mov     [rsp+48h+var_20], rax
0x18003755d  mov     r9d, r8d
0x180037560  xor     edx, edx
0x180037562  mov     dword ptr [rsp+48h+var_28], 0
0x18003756a  call    cs:__imp_FWOpenPolicyStore
0x180037570  mov     edi, eax
0x180037572  test    eax, eax
0x180037574  jnz     loc_180037626
0x18003757a  mov     rcx, [rsp+48h+arg_10]
0x18003757f  lea     r14d, [rax+1]
0x180037583  lea     rax, [rsp+48h+arg_18]
0x180037588  mov     r9d, r14d
0x18003758b  mov     [rsp+48h+var_20], rax
0x180037590  mov     edx, 0FFFF0000h
0x180037595  lea     rax, [rsp+48h+arg_8]
0x18003759a  mov     r8d, 7FFFFFFFh
0x1800375a0  mov     [rsp+48h+var_28], rax
0x1800375a5  call    cs:__imp_FWEnumFirewallRules
0x1800375ab  mov     edi, eax
0x1800375ad  test    eax, eax
0x1800375af  jnz     short loc_180037626
0x1800375b1  mov     rbx, [rsp+48h+arg_18]
0x1800375b6  test    rbx, rbx
0x1800375b9  jz      short loc_180037639
0x1800375bb  cmp     qword ptr [rbx+138h], 0
0x1800375c3  jz      short loc_18003761E
0x1800375c5  mov     rdx, [rbx+138h]; String2
0x1800375cc  lea     rcx, aFirewallapiDll; "@FirewallAPI.dll,-33752"
0x1800375d3  call    wcscmp_0
0x1800375d8  test    eax, eax
0x1800375da  jz      short loc_1800375F3
0x1800375dc  mov     rdx, [rbx+138h]; String2
0x1800375e3  lea     rcx, aSstpsvcDll3500; "@sstpsvc.dll,-35001"
0x1800375ea  call    wcscmp_0
0x1800375ef  test    eax, eax
0x1800375f1  jnz     short loc_18003761E
0x1800375f3  movzx   eax, word ptr [rbx+124h]
0x1800375fa  test    r14b, al
0x1800375fd  jnz     short loc_18003761E
0x1800375ff  or      ax, r14w
0x180037603  mov     rdx, rbx
0x180037606  mov     [rbx+124h], ax
0x18003760d  mov     rcx, [rsp+48h+arg_10]
0x180037612  call    cs:__imp_FWSetFirewallRule
0x180037618  mov     edi, eax
0x18003761a  test    eax, eax
0x18003761c  jnz     short loc_180037626
0x18003761e  mov     rbx, [rbx]
0x180037621  test    rbx, rbx
0x180037624  jnz     short loc_1800375BB
0x180037626  mov     rbx, [rsp+48h+arg_18]
0x18003762b  test    rbx, rbx
0x18003762e  jz      short loc_180037639
0x180037630  mov     rcx, rbx
0x180037633  call    cs:__imp_FWFreeFirewallRules
0x180037639  mov     rcx, [rsp+48h+arg_10]
0x18003763e  test    rcx, rcx
0x180037641  jz      short loc_180037649
0x180037643  call    cs:__imp_FWClosePolicyStore
0x180037649  mov     eax, edi
0x18003764b  add     rsp, 30h
0x18003764f  pop     r14
0x180037651  pop     rdi
0x180037652  pop     rbx
0x180037653  retn
```
