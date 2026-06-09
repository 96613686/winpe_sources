# IpTlsCheckOutsideEnabledInterfaces

- ea: `0x180002000`
- end: `0x1800022c6`
- name: `IpTlsCheckOutsideEnabledInterfaces`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800036e0`

## callees

- `0x180002000`
- `0x180003cf4`
- `0x18000d7c0`
- `0x18003588c`

## import_xrefs

- `NSI!NsiFreeTable` at `0x180002160`
- `NSI!NsiFreeTable` at `0x18000217f`
- `NSI!NsiFreeTable` at `0x180002160`
- `NSI!NsiFreeTable` at `0x18000217f`
- `NSI!NsiAllocateAndGetTable` at `0x18000206f`
- `NSI!NsiAllocateAndGetTable` at `0x1800020da`
- `NSI!NsiAllocateAndGetTable` at `0x18000206f`
- `NSI!NsiAllocateAndGetTable` at `0x1800020da`

## string_xrefs

- `0x18000218e`: `GetInsideOutsideStatus: inside = %d`
- `0x1800021a6`: `IpTlsCheckOutsideEnabledInterfaces:old state = %d; new state = %d; already configured = %d`
- `0x1800021f4`: `IpTlsCheckOutsideEnabledInterfaces:Inside outside state changed - outside = %d`
- `0x18000221b`: `IpTlsCheckOutsideEnabledInterfaces:Adding outside interfaces`
- `0x180002275`: `IpTlsCheckOutsideEnabledInterfaces:Finished adding outside interfaces`
- `0x18000229f`: `IpTlsCheckOutsideEnabledInterfaces:removing outside interfaces`

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
0x180002000  mov     r11, rsp
0x180002003  push    rbx
0x180002004  sub     rsp, 90h
0x18000200b  xor     ebx, ebx
0x18000200d  lea     rax, [r11+10h]
0x180002011  mov     byte ptr [rsp+98h+var_38], bl
0x180002015  lea     r9, [r11-20h]
0x180002019  mov     [r11-40h], rax
0x18000201d  lea     rdx, NPI_MS_IPV6_MODULEID
0x180002024  mov     [rsp+98h+var_48], ebx
0x180002028  lea     rax, [r11+20h]
0x18000202c  mov     [r11-50h], rbx
0x180002030  mov     r8d, 7
0x180002036  mov     [rsp+98h+var_58], ebx
0x18000203a  mov     ecx, 1
0x18000203f  mov     [r11-60h], rbx
0x180002043  mov     [rsp+98h+var_68], 0F0h
0x18000204b  mov     [r11-70h], rax
0x18000204f  mov     dword ptr [rsp+98h+var_78], 8
0x180002057  mov     [r11-28h], rbx
0x18000205b  mov     [r11+18h], rbx
0x18000205f  mov     [r11-20h], rbx
0x180002063  mov     [r11+20h], rbx
0x180002067  mov     [r11+8], ebx
0x18000206b  mov     [r11+10h], ebx
0x18000206f  call    cs:__imp_NsiAllocateAndGetTable
0x180002076  nop     dword ptr [rax+rax+00h]
0x18000207b  test    eax, eax
0x18000207d  jnz     loc_1800021DE
0x180002083  mov     byte ptr [rsp+98h+var_38], bl
0x180002087  lea     rax, [rsp+98h+arg_0]
0x18000208f  mov     [rsp+98h+var_40], rax
0x180002094  lea     r9, [rsp+98h+var_28]
0x180002099  mov     [rsp+98h+var_48], ebx
0x18000209d  lea     rax, [rsp+98h+arg_10]
0x1800020a5  mov     [rsp+98h+var_50], rbx
0x1800020aa  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800020b1  mov     [rsp+98h+var_58], ebx
0x1800020b5  mov     r8d, 7
0x1800020bb  mov     [rsp+98h+var_60], rbx
0x1800020c0  mov     ecx, 1
0x1800020c5  mov     [rsp+98h+var_68], 0F0h
0x1800020cd  mov     [rsp+98h+var_70], rax
0x1800020d2  mov     dword ptr [rsp+98h+var_78], 8
0x1800020da  call    cs:__imp_NsiAllocateAndGetTable
0x1800020e1  nop     dword ptr [rax+rax+00h]
0x1800020e6  mov     r10, [rsp+98h+arg_10]
0x1800020ee  test    eax, eax
0x1800020f0  jnz     short loc_18000214D
0x1800020f2  mov     r8d, [rsp+98h+arg_0]
0x1800020fa  mov     eax, ebx
0x1800020fc  nop     dword ptr [rax+00h]
0x180002100  cmp     eax, r8d
0x180002103  jnb     short loc_18000211D
0x180002105  mov     ecx, eax
0x180002107  imul    rdx, rcx, 0F0h
0x18000210e  cmp     dword ptr [rdx+r10+0A8h], 1
0x180002117  jz      short loc_18000214D
0x180002119  inc     eax
0x18000211b  jmp     short loc_180002100
0x18000211d  mov     r9, [rsp+98h+arg_18]
0x180002125  mov     edx, ebx
0x180002127  mov     r8d, [rsp+98h+arg_8]
0x18000212f  nop
0x180002130  cmp     edx, r8d
0x180002133  jnb     short loc_180002152
0x180002135  mov     eax, edx
0x180002137  imul    rcx, rax, 0F0h
0x18000213e  cmp     dword ptr [rcx+r9+0A8h], 1
0x180002147  jz      short loc_18000214D
0x180002149  inc     edx
0x18000214b  jmp     short loc_180002130
0x18000214d  mov     ebx, 1
0x180002152  mov     rcx, [rsp+98h+var_28]
0x180002157  xor     r9d, r9d
0x18000215a  xor     r8d, r8d
0x18000215d  mov     rdx, r10
0x180002160  call    cs:__imp_NsiFreeTable
0x180002167  nop     dword ptr [rax+rax+00h]
0x18000216c  mov     rdx, [rsp+98h+arg_18]
0x180002174  xor     r9d, r9d
0x180002177  mov     rcx, [rsp+98h+var_20]
0x18000217c  xor     r8d, r8d
0x18000217f  call    cs:__imp_NsiFreeTable
0x180002186  nop     dword ptr [rax+rax+00h]
0x18000218b  mov     r8d, ebx
0x18000218e  lea     rdx, aGetinsideoutsi; "GetInsideOutsideStatus: inside = %d"
0x180002195  mov     ecx, 800000h
0x18000219a  call    EventWrite0
0x18000219f  movzx   eax, cs:g_IpTlsConfiguredForOutside
0x1800021a6  lea     rdx, aIptlscheckouts_2; "IpTlsCheckOutsideEnabledInterfaces:old "...
0x1800021ad  movzx   r8d, cs:g_IpTlsIsOutside
0x1800021b5  xor     bl, 1
0x1800021b8  movzx   ebx, bl
0x1800021bb  mov     ecx, 10000000h
0x1800021c0  mov     r9d, ebx
0x1800021c3  mov     dword ptr [rsp+98h+var_78], eax
0x1800021c7  call    EventWrite0
0x1800021cc  cmp     cs:g_IpTlsIsOutside, bl
0x1800021d2  jnz     short loc_1800021EB
0x1800021d4  add     rsp, 90h
0x1800021db  pop     rbx
0x1800021dc  retn
0x1800021de  mov     r10, [rsp+98h+arg_10]
0x1800021e6  jmp     loc_18000214D
0x1800021eb  mov     r8d, ebx
0x1800021ee  mov     cs:g_IpTlsIsOutside, bl
0x1800021f4  lea     rdx, aIptlscheckouts; "IpTlsCheckOutsideEnabledInterfaces:Insi"...
0x1800021fb  mov     ecx, 10000000h
0x180002200  call    EventWrite0
0x180002205  cmp     cs:g_IpTlsIsOutside, 0
0x18000220c  jz      loc_180002292
0x180002212  cmp     cs:g_IpTlsConfiguredForOutside, 0
0x180002219  jnz     short loc_1800021D4
0x18000221b  lea     rdx, aIptlscheckouts_1; "IpTlsCheckOutsideEnabledInterfaces:Addi"...
0x180002222  mov     [rsp+98h+var_10], rdi
0x18000222a  mov     ecx, 10000000h
0x18000222f  call    EventWrite0
0x180002234  mov     edx, 2
0x180002239  mov     ecx, 1
0x18000223e  call    IpTlsAddEligibleInterfaces
0x180002243  mov     edx, 1
0x180002248  movzx   ebx, al
0x18000224b  mov     ecx, edx
0x18000224d  call    IpTlsAddEligibleInterfaces
0x180002252  movzx   edi, al
0x180002255  xor     edx, edx
0x180002257  mov     ecx, 1
0x18000225c  or      dil, bl
0x18000225f  call    IpTlsAddEligibleInterfaces
0x180002264  or      al, dil
0x180002267  mov     rdi, [rsp+98h+var_10]
0x18000226f  jz      loc_1800021D4
0x180002275  lea     rdx, aIptlscheckouts_0; "IpTlsCheckOutsideEnabledInterfaces:Fini"...
0x18000227c  mov     ecx, 10000000h
0x180002281  call    EventWrite0
0x180002286  mov     cs:g_IpTlsConfiguredForOutside, 1
0x18000228d  jmp     loc_1800021D4
0x180002292  cmp     cs:g_IpTlsConfiguredForOutside, 0
0x180002299  jz      loc_1800021D4
0x18000229f  lea     rdx, aIptlscheckouts_3; "IpTlsCheckOutsideEnabledInterfaces:remo"...
0x1800022a6  mov     ecx, 10000000h
0x1800022ab  call    EventWrite0
0x1800022b0  mov     ecx, 1
0x1800022b5  call    IpTlsRemoveEligibleInterfaces
0x1800022ba  mov     cs:g_IpTlsConfiguredForOutside, 0
0x1800022c1  jmp     loc_1800021D4
```
