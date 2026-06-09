# IpTlsCheckOutsideEnabledInterfaces

- ea: `0x180001ff0`
- end: `0x1800022b6`
- name: `IpTlsCheckOutsideEnabledInterfaces`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800036d0`

## callees

- `0x180001ff0`
- `0x180003ce4`
- `0x18000d7b0`
- `0x18003587c`

## import_xrefs

- `NSI!NsiFreeTable` at `0x180002150`
- `NSI!NsiFreeTable` at `0x18000216f`
- `NSI!NsiFreeTable` at `0x180002150`
- `NSI!NsiFreeTable` at `0x18000216f`
- `NSI!NsiAllocateAndGetTable` at `0x18000205f`
- `NSI!NsiAllocateAndGetTable` at `0x1800020ca`
- `NSI!NsiAllocateAndGetTable` at `0x18000205f`
- `NSI!NsiAllocateAndGetTable` at `0x1800020ca`

## string_xrefs

- `0x18000217e`: `GetInsideOutsideStatus: inside = %d`
- `0x180002196`: `IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d`
- `0x1800021e4`: `IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d`
- `0x18000220b`: `IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces`
- `0x180002265`: `IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces`
- `0x18000228f`: `IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces`

## pseudocode

```c
char IpTlsCheckOutsideEnabledInterfaces()
{
  unsigned int v0; // ebx
  int Table; // eax
  __int64 v2; // r10
  unsigned int i; // eax
  unsigned int j; // edx
  unsigned __int8 v5; // bl
  char result; // al
  char v7; // bl
  char v8; // di
  __int64 v9; // [rsp+20h] [rbp-78h]
  int v10; // [rsp+60h] [rbp-38h]
  __int64 v11; // [rsp+70h] [rbp-28h] BYREF
  __int64 v12; // [rsp+78h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v16; // [rsp+B8h] [rbp+20h] BYREF

  v0 = 0;
  v11 = 0;
  v15 = 0;
  v12 = 0;
  v16 = 0;
  v13 = 0;
  v14 = 0;
  if ( (unsigned int)NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v12, 8, &v16, 240, 0, 0, 0, 0, &v14, 0) )
  {
    v2 = v15;
    goto LABEL_11;
  }
  LOBYTE(v10) = 0;
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v11, 8, &v15, 240, 0, 0, 0, 0, &v13, v10);
  v2 = v15;
  if ( Table )
  {
LABEL_11:
    v0 = 1;
    goto LABEL_12;
  }
  for ( i = 0; i < v13; ++i )
  {
    if ( *(_DWORD *)(240LL * i + v15 + 168) == 1 )
      goto LABEL_11;
  }
  for ( j = 0; j < v14; ++j )
  {
    if ( *(_DWORD *)(240LL * j + v16 + 168) == 1 )
      goto LABEL_11;
  }
LABEL_12:
  NsiFreeTable(v11, v2, 0, 0);
  NsiFreeTable(v12, v16, 0, 0);
  EventWrite0(0x800000, L"GetInsideOutsideStatus: inside = %d", v0);
  v5 = v0 ^ 1;
  LODWORD(v9) = (unsigned __int8)g_IpTlsConfiguredForOutside;
  result = EventWrite0(
             0x10000000,
             L"IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d",
             (unsigned __int8)g_IpTlsIsOutside,
             v5,
             v9);
  if ( g_IpTlsIsOutside != v5 )
  {
    g_IpTlsIsOutside = v5;
    result = EventWrite0(
               0x10000000,
               L"IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d",
               v5);
    if ( g_IpTlsIsOutside )
    {
      if ( !g_IpTlsConfiguredForOutside )
      {
        EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces");
        v7 = IpTlsAddEligibleInterfaces(1, 2);
        v8 = v7 | IpTlsAddEligibleInterfaces(1, 1);
        result = v8 | IpTlsAddEligibleInterfaces(1, 0);
        if ( result )
        {
          result = EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces");
          g_IpTlsConfiguredForOutside = 1;
        }
      }
    }
    else if ( g_IpTlsConfiguredForOutside )
    {
      EventWrite0(0x10000000, L"IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces");
      result = IpTlsRemoveEligibleInterfaces(1);
      g_IpTlsConfiguredForOutside = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001ff0  mov     r11, rsp
0x180001ff3  push    rbx
0x180001ff4  sub     rsp, 90h
0x180001ffb  xor     ebx, ebx
0x180001ffd  lea     rax, [r11+10h]
0x180002001  mov     byte ptr [rsp+98h+var_38], bl
0x180002005  lea     r9, [r11-20h]
0x180002009  mov     [r11-40h], rax
0x18000200d  lea     rdx, NPI_MS_IPV6_MODULEID
0x180002014  mov     [rsp+98h+var_48], ebx
0x180002018  lea     rax, [r11+20h]
0x18000201c  mov     [r11-50h], rbx
0x180002020  mov     r8d, 7
0x180002026  mov     [rsp+98h+var_58], ebx
0x18000202a  mov     ecx, 1
0x18000202f  mov     [r11-60h], rbx
0x180002033  mov     [rsp+98h+var_68], 0F0h
0x18000203b  mov     [r11-70h], rax
0x18000203f  mov     dword ptr [rsp+98h+var_78], 8
0x180002047  mov     [r11-28h], rbx
0x18000204b  mov     [r11+18h], rbx
0x18000204f  mov     [r11-20h], rbx
0x180002053  mov     [r11+20h], rbx
0x180002057  mov     [r11+8], ebx
0x18000205b  mov     [r11+10h], ebx
0x18000205f  call    cs:__imp_NsiAllocateAndGetTable
0x180002066  nop     dword ptr [rax+rax+00h]
0x18000206b  test    eax, eax
0x18000206d  jnz     loc_1800021CE
0x180002073  mov     byte ptr [rsp+98h+var_38], bl
0x180002077  lea     rax, [rsp+98h+arg_0]
0x18000207f  mov     [rsp+98h+var_40], rax
0x180002084  lea     r9, [rsp+98h+var_28]
0x180002089  mov     [rsp+98h+var_48], ebx
0x18000208d  lea     rax, [rsp+98h+arg_10]
0x180002095  mov     [rsp+98h+var_50], rbx
0x18000209a  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800020a1  mov     [rsp+98h+var_58], ebx
0x1800020a5  mov     r8d, 7
0x1800020ab  mov     [rsp+98h+var_60], rbx
0x1800020b0  mov     ecx, 1
0x1800020b5  mov     [rsp+98h+var_68], 0F0h
0x1800020bd  mov     [rsp+98h+var_70], rax
0x1800020c2  mov     dword ptr [rsp+98h+var_78], 8
0x1800020ca  call    cs:__imp_NsiAllocateAndGetTable
0x1800020d1  nop     dword ptr [rax+rax+00h]
0x1800020d6  mov     r10, [rsp+98h+arg_10]
0x1800020de  test    eax, eax
0x1800020e0  jnz     short loc_18000213D
0x1800020e2  mov     r8d, [rsp+98h+arg_0]
0x1800020ea  mov     eax, ebx
0x1800020ec  nop     dword ptr [rax+00h]
0x1800020f0  cmp     eax, r8d
0x1800020f3  jnb     short loc_18000210D
0x1800020f5  mov     ecx, eax
0x1800020f7  imul    rdx, rcx, 0F0h
0x1800020fe  cmp     dword ptr [rdx+r10+0A8h], 1
0x180002107  jz      short loc_18000213D
0x180002109  inc     eax
0x18000210b  jmp     short loc_1800020F0
0x18000210d  mov     r9, [rsp+98h+arg_18]
0x180002115  mov     edx, ebx
0x180002117  mov     r8d, [rsp+98h+arg_8]
0x18000211f  nop
0x180002120  cmp     edx, r8d
0x180002123  jnb     short loc_180002142
0x180002125  mov     eax, edx
0x180002127  imul    rcx, rax, 0F0h
0x18000212e  cmp     dword ptr [rcx+r9+0A8h], 1
0x180002137  jz      short loc_18000213D
0x180002139  inc     edx
0x18000213b  jmp     short loc_180002120
0x18000213d  mov     ebx, 1
0x180002142  mov     rcx, [rsp+98h+var_28]
0x180002147  xor     r9d, r9d
0x18000214a  xor     r8d, r8d
0x18000214d  mov     rdx, r10
0x180002150  call    cs:__imp_NsiFreeTable
0x180002157  nop     dword ptr [rax+rax+00h]
0x18000215c  mov     rdx, [rsp+98h+arg_18]
0x180002164  xor     r9d, r9d
0x180002167  mov     rcx, [rsp+98h+var_20]
0x18000216c  xor     r8d, r8d
0x18000216f  call    cs:__imp_NsiFreeTable
0x180002176  nop     dword ptr [rax+rax+00h]
0x18000217b  mov     r8d, ebx
0x18000217e  lea     rdx, aGetinsideoutsi; "GetInsideOutsideStatus: inside = %d"
0x180002185  mov     ecx, 800000h
0x18000218a  call    EventWrite0
0x18000218f  movzx   eax, cs:g_IpTlsConfiguredForOutside
0x180002196  lea     rdx, aIptlscheckouts_2; "IpTlsCheckOutsideEnabledInterfaces:old "...
0x18000219d  movzx   r8d, cs:g_IpTlsIsOutside
0x1800021a5  xor     bl, 1
0x1800021a8  movzx   ebx, bl
0x1800021ab  mov     ecx, 10000000h
0x1800021b0  mov     r9d, ebx
0x1800021b3  mov     dword ptr [rsp+98h+var_78], eax
0x1800021b7  call    EventWrite0
0x1800021bc  cmp     cs:g_IpTlsIsOutside, bl
0x1800021c2  jnz     short loc_1800021DB
0x1800021c4  add     rsp, 90h
0x1800021cb  pop     rbx
0x1800021cc  retn
0x1800021ce  mov     r10, [rsp+98h+arg_10]
0x1800021d6  jmp     loc_18000213D
0x1800021db  mov     r8d, ebx
0x1800021de  mov     cs:g_IpTlsIsOutside, bl
0x1800021e4  lea     rdx, aIptlscheckouts; "IpTlsCheckOutsideEnabledInterfaces:Insi"...
0x1800021eb  mov     ecx, 10000000h
0x1800021f0  call    EventWrite0
0x1800021f5  cmp     cs:g_IpTlsIsOutside, 0
0x1800021fc  jz      loc_180002282
0x180002202  cmp     cs:g_IpTlsConfiguredForOutside, 0
0x180002209  jnz     short loc_1800021C4
0x18000220b  lea     rdx, aIptlscheckouts_1; "IpTlsCheckOutsideEnabledInterfaces:Addi"...
0x180002212  mov     [rsp+98h+var_10], rdi
0x18000221a  mov     ecx, 10000000h
0x18000221f  call    EventWrite0
0x180002224  mov     edx, 2
0x180002229  mov     ecx, 1
0x18000222e  call    IpTlsAddEligibleInterfaces
0x180002233  mov     edx, 1
0x180002238  movzx   ebx, al
0x18000223b  mov     ecx, edx
0x18000223d  call    IpTlsAddEligibleInterfaces
0x180002242  movzx   edi, al
0x180002245  xor     edx, edx
0x180002247  mov     ecx, 1
0x18000224c  or      dil, bl
0x18000224f  call    IpTlsAddEligibleInterfaces
0x180002254  or      al, dil
0x180002257  mov     rdi, [rsp+98h+var_10]
0x18000225f  jz      loc_1800021C4
0x180002265  lea     rdx, aIptlscheckouts_0; "IpTlsCheckOutsideEnabledInterfaces:Fini"...
0x18000226c  mov     ecx, 10000000h
0x180002271  call    EventWrite0
0x180002276  mov     cs:g_IpTlsConfiguredForOutside, 1
0x18000227d  jmp     loc_1800021C4
0x180002282  cmp     cs:g_IpTlsConfiguredForOutside, 0
0x180002289  jz      loc_1800021C4
0x18000228f  lea     rdx, aIptlscheckouts_3; "IpTlsCheckOutsideEnabledInterfaces:remo"...
0x180002296  mov     ecx, 10000000h
0x18000229b  call    EventWrite0
0x1800022a0  mov     ecx, 1
0x1800022a5  call    IpTlsRemoveEligibleInterfaces
0x1800022aa  mov     cs:g_IpTlsConfiguredForOutside, 0
0x1800022b1  jmp     loc_1800021C4
```
