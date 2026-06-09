# appIsolation::IsolationEvents::FwMoneisAppContainerChangeCopy(_INET_FIREWALL_AC_CHANGE * const,_INET_FIREWALL_AC_CHANGE * *)

- ea: `0x1800baea0`
- end: `0x1800bb140`
- name: `?FwMoneisAppContainerChangeCopy@IsolationEvents@appIsolation@@AEAAKQEAU_INET_FIREWALL_AC_CHANGE@@PEAPEAU3@@Z`
- size: `672`
- prototype: `unsigned int __fastcall(appIsolation::IsolationEvents *__hidden this, struct _INET_FIREWALL_AC_CHANGE *const, struct _INET_FIREWALL_AC_CHANGE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bb200`

## callees

- `0x18000af3c`
- `0x180051bec`
- `0x1800baea0`

## import_xrefs

- `fwbase!FwAllocArray` at `0x1800bb03c`
- `fwbase!FwAllocArray` at `0x1800bb03c`
- `fwbase!FwHResultToWindowsError` at `0x1800bafa0`
- `fwbase!FwHResultToWindowsError` at `0x1800bb090`
- `fwbase!FwHResultToWindowsError` at `0x1800bafa0`
- `fwbase!FwHResultToWindowsError` at `0x1800bb090`
- `fwbase!FwStringCopy` at `0x1800baf98`
- `fwbase!FwStringCopy` at `0x1800bb088`
- `fwbase!FwStringCopy` at `0x1800baf98`
- `fwbase!FwStringCopy` at `0x1800bb088`
- `fwbase!FwAlloc` at `0x1800baeb5`
- `fwbase!FwAlloc` at `0x1800baeb5`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bafea`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bafea`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bb0dd`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800bb0dd`

## pseudocode

```c
__int64 __fastcall appIsolation::IsolationEvents::FwMoneisAppContainerChangeCopy(
        appIsolation::IsolationEvents *this,
        struct _INET_FIREWALL_AC_CHANGE *const a2,
        struct _INET_FIREWALL_AC_CHANGE **a3)
{
  struct _INET_FIREWALL_AC_CHANGE *v5; // rax
  struct _INET_FIREWALL_AC_CHANGE *v6; // rdi
  unsigned int v7; // ebp
  __int64 v8; // rcx
  __int64 v9; // rdx
  SID *appContainerSid; // rcx
  unsigned int v12; // eax
  INET_FIREWALL_AC_CREATION_TYPE createType; // eax
  DWORD count; // r14d
  SID_AND_ATTRIBUTES *capabilities; // r12
  __int64 v16; // rbx
  __int64 v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // eax

  v5 = (struct _INET_FIREWALL_AC_CHANGE *)FwAlloc(48);
  v6 = v5;
  if ( !v5 )
  {
    v7 = 14;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 16;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_13adc94aaf263cba21686d19d2700e16_Traceguids, v7);
      return v7;
    }
    return v7;
  }
  appContainerSid = a2->appContainerSid;
  v5->changeType = a2->changeType;
  v5->createType = a2->createType;
  v7 = FwSidCopy(appContainerSid);
  if ( !v7 )
  {
    v7 = FwSidCopy(a2->userSid);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 18;
        goto LABEL_5;
      }
      return v7;
    }
    v12 = FwStringCopy(a2->displayName, &v6->displayName);
    v7 = FwHResultToWindowsError(v12);
    if ( v7 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 19;
        goto LABEL_5;
      }
      return v7;
    }
    createType = a2->createType;
    if ( createType == INET_FIREWALL_AC_PACKAGE_ID_ONLY )
    {
      FwSidAndAttributesCopy(a2->capabilities.count, a2->capabilities.capabilities, &v6->binaries.binaries);
LABEL_38:
      v6->capabilities.count = a2->capabilities.count;
      goto LABEL_39;
    }
    if ( createType != INET_FIREWALL_AC_BINARY )
    {
LABEL_39:
      *a3 = v6;
      return v7;
    }
    count = a2->capabilities.count;
    v6->capabilities.capabilities = 0;
    if ( !count || (capabilities = a2->capabilities.capabilities) == 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, 0);
      goto LABEL_38;
    }
    v16 = 0;
    v17 = FwAllocArray(8, count);
    if ( v17 )
    {
      while ( 1 )
      {
        v21 = FwStringCopy(*((_QWORD *)&capabilities->Sid + v16), v17 + 8 * v16);
        v22 = FwHResultToWindowsError(v21);
        v20 = v22;
        if ( v22 )
          break;
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= count )
        {
          v6->capabilities.capabilities = (SID_AND_ATTRIBUTES *)v17;
          goto LABEL_38;
        }
      }
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_34;
      v19 = 33;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_34;
      v19 = 32;
      v20 = 14;
    }
    WPP_SF_d(*(_QWORD *)(v18 + 16), v19, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v20);
LABEL_34:
    FwBinariesFree((unsigned int)v16, v17);
    goto LABEL_38;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v9 = 17;
    goto LABEL_5;
  }
  return v7;
}

```

## disassembly

```asm
0x1800baea0  push    rbp
0x1800baea2  push    rsi
0x1800baea3  push    rdi
0x1800baea4  push    r13
0x1800baea6  sub     rsp, 28h
0x1800baeaa  mov     ecx, 30h ; '0'
0x1800baeaf  mov     r13, r8
0x1800baeb2  mov     rsi, rdx
0x1800baeb5  call    cs:__imp_FwAlloc
0x1800baebb  mov     rdi, rax
0x1800baebe  test    rax, rax
0x1800baec1  jnz     short loc_1800BAF0D
0x1800baec3  mov     ebp, 0Eh
0x1800baec8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baecf  lea     rax, WPP_GLOBAL_Control
0x1800baed6  cmp     rcx, rax
0x1800baed9  jz      loc_1800BB134
0x1800baedf  test    byte ptr [rcx+1Ch], 1
0x1800baee3  jz      loc_1800BB134
0x1800baee9  mov     edx, 10h
0x1800baeee  mov     rcx, [rcx+10h]
0x1800baef2  lea     r8, WPP_13adc94aaf263cba21686d19d2700e16_Traceguids
0x1800baef9  mov     r9d, ebp
0x1800baefc  call    WPP_SF_d
0x1800baf01  mov     eax, ebp
0x1800baf03  add     rsp, 28h
0x1800baf07  pop     r13
0x1800baf09  pop     rdi
0x1800baf0a  pop     rsi
0x1800baf0b  pop     rbp
0x1800baf0c  retn
0x1800baf0d  mov     eax, [rsi]
0x1800baf0f  lea     rdx, [rdi+8]
0x1800baf13  mov     rcx, [rsi+8]; SourceSid
0x1800baf17  mov     [rdi], eax
0x1800baf19  mov     eax, [rsi+4]
0x1800baf1c  mov     [rdi+4], eax
0x1800baf1f  call    FwSidCopy
0x1800baf24  mov     ebp, eax
0x1800baf26  test    eax, eax
0x1800baf28  jz      short loc_1800BAF52
0x1800baf2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baf31  lea     rax, WPP_GLOBAL_Control
0x1800baf38  cmp     rcx, rax
0x1800baf3b  jz      loc_1800BB134
0x1800baf41  test    byte ptr [rcx+1Ch], 1
0x1800baf45  jz      loc_1800BB134
0x1800baf4b  mov     edx, 11h
0x1800baf50  jmp     short loc_1800BAEEE
0x1800baf52  mov     rcx, [rsi+10h]; SourceSid
0x1800baf56  lea     rdx, [rdi+10h]
0x1800baf5a  call    FwSidCopy
0x1800baf5f  mov     ebp, eax
0x1800baf61  test    eax, eax
0x1800baf63  jz      short loc_1800BAF90
0x1800baf65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baf6c  lea     rax, WPP_GLOBAL_Control
0x1800baf73  cmp     rcx, rax
0x1800baf76  jz      loc_1800BB134
0x1800baf7c  test    byte ptr [rcx+1Ch], 1
0x1800baf80  jz      loc_1800BB134
0x1800baf86  mov     edx, 12h
0x1800baf8b  jmp     loc_1800BAEEE
0x1800baf90  mov     rcx, [rsi+18h]
0x1800baf94  lea     rdx, [rdi+18h]
0x1800baf98  call    cs:__imp_FwStringCopy
0x1800baf9e  mov     ecx, eax
0x1800bafa0  call    cs:__imp_FwHResultToWindowsError
0x1800bafa6  mov     ebp, eax
0x1800bafa8  test    eax, eax
0x1800bafaa  jz      short loc_1800BAFD7
0x1800bafac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bafb3  lea     rax, WPP_GLOBAL_Control
0x1800bafba  cmp     rcx, rax
0x1800bafbd  jz      loc_1800BB134
0x1800bafc3  test    byte ptr [rcx+1Ch], 1
0x1800bafc7  jz      loc_1800BB134
0x1800bafcd  mov     edx, 13h
0x1800bafd2  jmp     loc_1800BAEEE
0x1800bafd7  mov     eax, [rsi+4]
0x1800bafda  cmp     eax, 1
0x1800bafdd  jnz     short loc_1800BAFF5
0x1800bafdf  mov     rdx, [rsi+28h]
0x1800bafe3  lea     r8, [rdi+28h]
0x1800bafe7  mov     ecx, [rsi+20h]
0x1800bafea  call    cs:__imp_FwSidAndAttributesCopy
0x1800baff0  jmp     loc_1800BB12A
0x1800baff5  cmp     eax, 2
0x1800baff8  jnz     loc_1800BB130
0x1800baffe  mov     [rsp+48h+arg_10], r14
0x1800bb003  mov     r14d, [rsi+20h]
0x1800bb007  mov     [rsp+48h+arg_0], rbx
0x1800bb00c  mov     [rsp+48h+arg_8], r12
0x1800bb011  mov     [rsp+48h+var_28], r15
0x1800bb016  mov     qword ptr [rdi+28h], 0
0x1800bb01e  test    r14d, r14d
0x1800bb021  jz      loc_1800BB0E5
0x1800bb027  mov     r12, [rsi+28h]
0x1800bb02b  test    r12, r12
0x1800bb02e  jz      loc_1800BB0E5
0x1800bb034  mov     edx, r14d
0x1800bb037  mov     ecx, 8
0x1800bb03c  call    cs:__imp_FwAllocArray
0x1800bb042  xor     ebx, ebx
0x1800bb044  mov     r15, rax
0x1800bb047  test    rax, rax
0x1800bb04a  jnz     short loc_1800BB072
0x1800bb04c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb053  lea     rax, WPP_GLOBAL_Control
0x1800bb05a  cmp     rcx, rax
0x1800bb05d  jz      short loc_1800BB0D8
0x1800bb05f  test    byte ptr [rcx+1Ch], 1
0x1800bb063  jz      short loc_1800BB0D8
0x1800bb065  mov     edx, 20h ; ' '
0x1800bb06a  mov     r9d, 0Eh
0x1800bb070  jmp     short loc_1800BB0C8
0x1800bb072  test    r14d, r14d
0x1800bb075  jz      short loc_1800BB0A4
0x1800bb077  nop     word ptr [rax+rax+00000000h]
0x1800bb080  mov     rcx, [r12+rbx*8]
0x1800bb084  lea     rdx, [r15+rbx*8]
0x1800bb088  call    cs:__imp_FwStringCopy
0x1800bb08e  mov     ecx, eax
0x1800bb090  call    cs:__imp_FwHResultToWindowsError
0x1800bb096  mov     r9d, eax
0x1800bb099  test    eax, eax
0x1800bb09b  jnz     short loc_1800BB0AA
0x1800bb09d  inc     ebx
0x1800bb09f  cmp     ebx, r14d
0x1800bb0a2  jb      short loc_1800BB080
0x1800bb0a4  mov     [rdi+28h], r15
0x1800bb0a8  jmp     short loc_1800BB116
0x1800bb0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb0b1  lea     rax, WPP_GLOBAL_Control
0x1800bb0b8  cmp     rcx, rax
0x1800bb0bb  jz      short loc_1800BB0D8
0x1800bb0bd  test    byte ptr [rcx+1Ch], 1
0x1800bb0c1  jz      short loc_1800BB0D8
0x1800bb0c3  mov     edx, 21h ; '!'
0x1800bb0c8  mov     rcx, [rcx+10h]
0x1800bb0cc  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bb0d3  call    WPP_SF_d
0x1800bb0d8  mov     rdx, r15
0x1800bb0db  mov     ecx, ebx
0x1800bb0dd  call    cs:__imp_FwBinariesFree
0x1800bb0e3  jmp     short loc_1800BB116
0x1800bb0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb0ec  lea     rax, WPP_GLOBAL_Control
0x1800bb0f3  cmp     rcx, rax
0x1800bb0f6  jz      short loc_1800BB116
0x1800bb0f8  test    byte ptr [rcx+1Ch], 1
0x1800bb0fc  jz      short loc_1800BB116
0x1800bb0fe  mov     rcx, [rcx+10h]
0x1800bb102  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bb109  mov     edx, 1Fh
0x1800bb10e  xor     r9d, r9d
0x1800bb111  call    WPP_SF_d
0x1800bb116  mov     r15, [rsp+48h+var_28]
0x1800bb11b  mov     r14, [rsp+48h+arg_10]
0x1800bb120  mov     r12, [rsp+48h+arg_8]
0x1800bb125  mov     rbx, [rsp+48h+arg_0]
0x1800bb12a  mov     eax, [rsi+20h]
0x1800bb12d  mov     [rdi+20h], eax
0x1800bb130  mov     [r13+0], rdi
0x1800bb134  mov     eax, ebp
0x1800bb136  add     rsp, 28h
0x1800bb13a  pop     r13
0x1800bb13c  pop     rdi
0x1800bb13d  pop     rsi
0x1800bb13e  pop     rbp
0x1800bb13f  retn
```
