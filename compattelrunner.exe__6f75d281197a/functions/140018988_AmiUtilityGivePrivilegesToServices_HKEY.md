# AmiUtilityGivePrivilegesToServices(HKEY__ *)

- ea: `0x140018988`
- end: `0x140018a2c`
- name: `?AmiUtilityGivePrivilegesToServices@@YAKPEAUHKEY__@@@Z`
- size: `164`
- prototype: `unsigned int __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140019930`

## callees

- `0x1400151b0`
- `0x140018988`
- `0x140018a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400189f2`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1400189f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018a19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018a19`

## string_xrefs

- `0x1400189ce`: `AmiUtilityGivePrivilegesToServices`
- `0x1400189c1`: `AmiUtilityInitSecurityDescriptor failed [%d]`
- `0x1400189fe`: `RegSetKeySecurity failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiUtilityGivePrivilegesToServices(HKEY hKey)
{
  int inited; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+50h] [rbp-18h]
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  hMem = 0;
  v8 = 0;
  inited = AmiUtilityInitSecurityDescriptor(pSecurityDescriptor, (PACL *)&hMem);
  v3 = inited;
  if ( inited )
  {
    v4 = "AmiUtilityInitSecurityDescriptor failed [%d]";
    v5 = 235;
LABEL_3:
    AslLogCallPrintf(1, "AmiUtilityGivePrivilegesToServices", v5, v4, inited);
    goto LABEL_7;
  }
  inited = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
  v3 = inited;
  if ( inited )
  {
    v4 = "RegSetKeySecurity failed [%d]";
    v5 = 244;
    goto LABEL_3;
  }
  v3 = 0;
LABEL_7:
  if ( hMem )
    LocalFree(hMem);
  return v3;
}

```

## disassembly

```asm
0x140018988  mov     r11, rsp
0x14001898b  mov     [r11+8], rbx
0x14001898f  push    rdi
0x140018990  sub     rsp, 60h
0x140018994  xorps   xmm0, xmm0
0x140018997  lea     rdx, [r11+10h]; NewAcl
0x14001899b  xor     eax, eax
0x14001899d  mov     rdi, rcx
0x1400189a0  movups  [rsp+68h+pSecurityDescriptor], xmm0
0x1400189a5  lea     rcx, [r11-38h]; pSecurityDescriptor
0x1400189a9  mov     [r11+10h], rax
0x1400189ad  movups  [rsp+68h+var_28], xmm0
0x1400189b2  mov     [r11-18h], rax
0x1400189b6  call    ?AmiUtilityInitSecurityDescriptor@@YAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; AmiUtilityInitSecurityDescriptor(_SECURITY_DESCRIPTOR &,_ACL * &)
0x1400189bb  mov     ebx, eax
0x1400189bd  test    eax, eax
0x1400189bf  jz      short loc_1400189E5
0x1400189c1  lea     r9, aAmiutilityinit_0; "AmiUtilityInitSecurityDescriptor failed"...
0x1400189c8  mov     r8d, 0EBh
0x1400189ce  lea     rdx, aAmiutilitygive; "AmiUtilityGivePrivilegesToServices"
0x1400189d5  mov     [rsp+68h+var_48], eax
0x1400189d9  mov     ecx, 1
0x1400189de  call    AslLogCallPrintf
0x1400189e3  jmp     short loc_140018A0F
0x1400189e5  lea     r8, [rsp+68h+pSecurityDescriptor]; pSecurityDescriptor
0x1400189ea  mov     edx, 4; SecurityInformation
0x1400189ef  mov     rcx, rdi; hKey
0x1400189f2  call    cs:__imp_RegSetKeySecurity
0x1400189f8  mov     ebx, eax
0x1400189fa  test    eax, eax
0x1400189fc  jz      short loc_140018A0D
0x1400189fe  lea     r9, aRegsetkeysecur; "RegSetKeySecurity failed [%d]"
0x140018a05  mov     r8d, 0F4h
0x140018a0b  jmp     short loc_1400189CE
0x140018a0d  xor     ebx, ebx
0x140018a0f  mov     rcx, [rsp+68h+hMem]; hMem
0x140018a14  test    rcx, rcx
0x140018a17  jz      short loc_140018A1F
0x140018a19  call    cs:__imp_LocalFree
0x140018a1f  mov     eax, ebx
0x140018a21  mov     rbx, [rsp+68h+arg_0]
0x140018a26  add     rsp, 60h
0x140018a2a  pop     rdi
0x140018a2b  retn
```
