# DfsCheckAccessToADContainer(ushort *,ulong)

- ea: `0x140033054`
- end: `0x1400331f3`
- name: `?DfsCheckAccessToADContainer@@YAKPEAGK@Z`
- size: `415`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000c214`
- `0x140045dec`

## callees

- `0x140005a94`
- `0x140005b90`
- `0x140007d38`
- `0x140033054`
- `0x14003345c`
- `0x14004a53c`
- `0x14004ac38`
- `0x140059558`
- `0x1400595c8`
- `0x1400599c4`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x1400331c7`
- `WLDAP32!__imp_ldap_unbind` at `0x1400331c7`

## pseudocode

```c
__int64 __fastcall DfsCheckAccessToADContainer(unsigned __int16 *a1)
{
  __int64 v1; // rdi
  unsigned int AdSecurityDescriptor; // ebx
  CLocalMachine *Instance; // rax
  const unsigned __int16 *AdDfsConfigurationContainerDn; // rax
  int v5; // esi
  int v6; // edx
  int v7; // r8d
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF
  LDAP *ld; // [rsp+58h] [rbp+20h] BYREF

  v1 = 0;
  ld = 0;
  v9 = 0;
  AdSecurityDescriptor = DfsLdapConnect(a1, &ld);
  if ( AdSecurityDescriptor )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x840) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 10, WPP_f2d29e4a629339934e04001d39f1b3c7_Traceguids, AdSecurityDescriptor);
    }
  }
  else
  {
    Instance = CLocalMachine::_GetInstance(0);
    AdDfsConfigurationContainerDn = CLocalMachine::GetAdDfsConfigurationContainerDn(Instance);
    v5 = (int)AdDfsConfigurationContainerDn;
    if ( AdDfsConfigurationContainerDn )
    {
      AdSecurityDescriptor = DfsGetAdSecurityDescriptor(ld, AdDfsConfigurationContainerDn, &v9);
      if ( AdSecurityDescriptor )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x840) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_SD(
            *((_QWORD *)pWppControl + 2),
            11,
            (unsigned int)WPP_f2d29e4a629339934e04001d39f1b3c7_Traceguids,
            v5,
            AdSecurityDescriptor);
        }
        v1 = v9;
      }
      else
      {
        v1 = v9;
        AdSecurityDescriptor = DfsDoesUserHaveDesiredAccessToAd(2, v9);
        if ( AdSecurityDescriptor
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x840) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_SDD(*((_QWORD *)pWppControl + 2), v6, v7, v5);
        }
      }
    }
    else
    {
      AdSecurityDescriptor = 1355;
    }
  }
  if ( ld )
    ldap_unbind(ld);
  if ( v1 )
    DfsDeallocateSecurityData(v1);
  return AdSecurityDescriptor;
}

```

## disassembly

```asm
0x140033054  mov     rax, rsp
0x140033057  mov     [rax+8], rbx
0x14003305b  mov     [rax+10h], rsi
0x14003305f  push    rdi
0x140033060  sub     rsp, 30h
0x140033064  xor     edi, edi
0x140033066  lea     rdx, [rax+20h]; struct ldap **
0x14003306a  and     [rax+20h], rdi
0x14003306e  mov     [rax+18h], rdi
0x140033072  call    ?DfsLdapConnect@@YAKPEAGPEAPEAUldap@@@Z; DfsLdapConnect(ushort *,ldap * *)
0x140033077  mov     ebx, eax
0x140033079  test    eax, eax
0x14003307b  jz      short loc_1400330D6
0x14003307d  lea     rax, WPP_GLOBAL_Control
0x140033084  cmp     cs:WPP_GLOBAL_Control, rax
0x14003308b  jz      loc_1400331BA
0x140033091  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140033098  test    rcx, rcx
0x14003309b  jz      loc_1400331BA
0x1400330a1  lea     eax, [rdi+40h]
0x1400330a4  bts     eax, 0Bh
0x1400330a8  test    [rcx+1Ch], eax
0x1400330ab  jz      loc_1400331BA
0x1400330b1  cmp     byte ptr [rcx+19h], 1
0x1400330b5  jb      loc_1400331BA
0x1400330bb  mov     rcx, [rcx+10h]
0x1400330bf  lea     edx, [rdi+0Ah]
0x1400330c2  mov     r9d, ebx
0x1400330c5  lea     r8, WPP_f2d29e4a629339934e04001d39f1b3c7_Traceguids
0x1400330cc  call    WPP_SF_D
0x1400330d1  jmp     loc_1400331BA
0x1400330d6  xor     ecx, ecx; unsigned int *
0x1400330d8  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x1400330dd  mov     rcx, rax; this
0x1400330e0  call    ?GetAdDfsConfigurationContainerDn@CLocalMachine@@QEAAPEBGXZ; CLocalMachine::GetAdDfsConfigurationContainerDn(void)
0x1400330e5  mov     rsi, rax
0x1400330e8  test    rax, rax
0x1400330eb  jnz     short loc_1400330F7
0x1400330ed  mov     ebx, 54Bh
0x1400330f2  jmp     loc_1400331BA
0x1400330f7  mov     rcx, [rsp+38h+ld]
0x1400330fc  lea     r8, [rsp+38h+arg_10]
0x140033101  mov     rdx, rsi
0x140033104  call    DfsGetAdSecurityDescriptor
0x140033109  mov     ebx, eax
0x14003310b  test    eax, eax
0x14003310d  jz      short loc_140033162
0x14003310f  lea     rax, WPP_GLOBAL_Control
0x140033116  cmp     cs:WPP_GLOBAL_Control, rax
0x14003311d  jz      short loc_14003315B
0x14003311f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140033126  test    rcx, rcx
0x140033129  jz      short loc_14003315B
0x14003312b  mov     eax, 40h ; '@'
0x140033130  bts     eax, 0Bh
0x140033134  test    [rcx+1Ch], eax
0x140033137  jz      short loc_14003315B
0x140033139  cmp     byte ptr [rcx+19h], 1
0x14003313d  jb      short loc_14003315B
0x14003313f  mov     rcx, [rcx+10h]
0x140033143  lea     r8, WPP_f2d29e4a629339934e04001d39f1b3c7_Traceguids
0x14003314a  mov     edx, 0Bh
0x14003314f  mov     [rsp+38h+var_18], ebx
0x140033153  mov     r9, rsi
0x140033156  call    WPP_SF_SD
0x14003315b  mov     rdi, [rsp+38h+arg_10]
0x140033160  jmp     short loc_1400331BA
0x140033162  mov     rdi, [rsp+38h+arg_10]
0x140033167  mov     ecx, 2
0x14003316c  mov     rdx, rdi
0x14003316f  call    DfsDoesUserHaveDesiredAccessToAd
0x140033174  mov     ebx, eax
0x140033176  test    eax, eax
0x140033178  jz      short loc_1400331BA
0x14003317a  lea     rax, WPP_GLOBAL_Control
0x140033181  cmp     cs:WPP_GLOBAL_Control, rax
0x140033188  jz      short loc_1400331BA
0x14003318a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140033191  test    rcx, rcx
0x140033194  jz      short loc_1400331BA
0x140033196  mov     eax, 40h ; '@'
0x14003319b  bts     eax, 0Bh
0x14003319f  test    [rcx+1Ch], eax
0x1400331a2  jz      short loc_1400331BA
0x1400331a4  cmp     byte ptr [rcx+19h], 1
0x1400331a8  jb      short loc_1400331BA
0x1400331aa  mov     rcx, [rcx+10h]
0x1400331ae  mov     r9, rsi
0x1400331b1  mov     [rsp+38h+var_10], ebx
0x1400331b5  call    WPP_SF_SDD
0x1400331ba  cmp     [rsp+38h+ld], 0
0x1400331c0  jz      short loc_1400331D3
0x1400331c2  mov     rcx, [rsp+38h+ld]; ld
0x1400331c7  call    cs:__imp_ldap_unbind
0x1400331ce  nop     dword ptr [rax+rax+00h]
0x1400331d3  test    rdi, rdi
0x1400331d6  jz      short loc_1400331E0
0x1400331d8  mov     rcx, rdi
0x1400331db  call    DfsDeallocateSecurityData
0x1400331e0  mov     rsi, [rsp+38h+arg_8]
0x1400331e5  mov     eax, ebx
0x1400331e7  mov     rbx, [rsp+38h+arg_0]
0x1400331ec  add     rsp, 30h
0x1400331f0  pop     rdi
0x1400331f1  retn
```
