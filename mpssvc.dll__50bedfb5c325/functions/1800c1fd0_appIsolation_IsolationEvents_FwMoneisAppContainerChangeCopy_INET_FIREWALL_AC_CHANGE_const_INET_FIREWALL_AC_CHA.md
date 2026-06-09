# appIsolation::IsolationEvents::FwMoneisAppContainerChangeCopy(_INET_FIREWALL_AC_CHANGE * const,_INET_FIREWALL_AC_CHANGE * *)

- ea: `0x1800c1fd0`
- end: `0x1800c2299`
- name: `?FwMoneisAppContainerChangeCopy@IsolationEvents@appIsolation@@AEAAKQEAU_INET_FIREWALL_AC_CHANGE@@PEAPEAU3@@Z`
- size: `713`
- prototype: `unsigned int __fastcall(appIsolation::IsolationEvents *__hidden this, struct _INET_FIREWALL_AC_CHANGE *const, struct _INET_FIREWALL_AC_CHANGE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c2350`

## callees

- `0x18000a710`
- `0x180056008`
- `0x1800c1fd0`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800c20dd`
- `fwbase!FwHResultToWindowsError` at `0x1800c21dc`
- `fwbase!FwHResultToWindowsError` at `0x1800c20dd`
- `fwbase!FwHResultToWindowsError` at `0x1800c21dc`
- `fwbase!FwAllocArray` at `0x1800c2185`
- `fwbase!FwAllocArray` at `0x1800c2185`
- `fwbase!FwStringCopy` at `0x1800c20cf`
- `fwbase!FwStringCopy` at `0x1800c21ce`
- `fwbase!FwStringCopy` at `0x1800c20cf`
- `fwbase!FwStringCopy` at `0x1800c21ce`
- `fwbase!FwAlloc` at `0x1800c1fe5`
- `fwbase!FwAlloc` at `0x1800c1fe5`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800c212d`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800c212d`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c222f`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c222f`

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
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_f6f972174fd732e1ff65570a16390702_Traceguids, v7);
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
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_a875d200678f3c386c19a36d1916a086_Traceguids, 0);
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
    WPP_SF_d(*(_QWORD *)(v18 + 16), v19, WPP_a875d200678f3c386c19a36d1916a086_Traceguids, v20);
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
0x1800c1fd0  push    rbp
0x1800c1fd2  push    rsi
0x1800c1fd3  push    rdi
0x1800c1fd4  push    r13
0x1800c1fd6  sub     rsp, 28h
0x1800c1fda  mov     ecx, 30h ; '0'
0x1800c1fdf  mov     r13, r8
0x1800c1fe2  mov     rsi, rdx
0x1800c1fe5  call    cs:__imp_FwAlloc
0x1800c1fec  nop     dword ptr [rax+rax+00h]
0x1800c1ff1  mov     rdi, rax
0x1800c1ff4  test    rax, rax
0x1800c1ff7  jnz     short loc_1800C2044
0x1800c1ff9  mov     ebp, 0Eh
0x1800c1ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2005  lea     rax, WPP_GLOBAL_Control
0x1800c200c  cmp     rcx, rax
0x1800c200f  jz      loc_1800C228C
0x1800c2015  test    byte ptr [rcx+1Ch], 1
0x1800c2019  jz      loc_1800C228C
0x1800c201f  mov     edx, 10h
0x1800c2024  mov     rcx, [rcx+10h]
0x1800c2028  lea     r8, WPP_f6f972174fd732e1ff65570a16390702_Traceguids
0x1800c202f  mov     r9d, ebp
0x1800c2032  call    WPP_SF_d
0x1800c2037  mov     eax, ebp
0x1800c2039  add     rsp, 28h
0x1800c203d  pop     r13
0x1800c203f  pop     rdi
0x1800c2040  pop     rsi
0x1800c2041  pop     rbp
0x1800c2042  retn
0x1800c2044  mov     eax, [rsi]
0x1800c2046  lea     rdx, [rdi+8]
0x1800c204a  mov     rcx, [rsi+8]; SourceSid
0x1800c204e  mov     [rdi], eax
0x1800c2050  mov     eax, [rsi+4]
0x1800c2053  mov     [rdi+4], eax
0x1800c2056  call    FwSidCopy
0x1800c205b  mov     ebp, eax
0x1800c205d  test    eax, eax
0x1800c205f  jz      short loc_1800C2089
0x1800c2061  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2068  lea     rax, WPP_GLOBAL_Control
0x1800c206f  cmp     rcx, rax
0x1800c2072  jz      loc_1800C228C
0x1800c2078  test    byte ptr [rcx+1Ch], 1
0x1800c207c  jz      loc_1800C228C
0x1800c2082  mov     edx, 11h
0x1800c2087  jmp     short loc_1800C2024
0x1800c2089  mov     rcx, [rsi+10h]; SourceSid
0x1800c208d  lea     rdx, [rdi+10h]
0x1800c2091  call    FwSidCopy
0x1800c2096  mov     ebp, eax
0x1800c2098  test    eax, eax
0x1800c209a  jz      short loc_1800C20C7
0x1800c209c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c20a3  lea     rax, WPP_GLOBAL_Control
0x1800c20aa  cmp     rcx, rax
0x1800c20ad  jz      loc_1800C228C
0x1800c20b3  test    byte ptr [rcx+1Ch], 1
0x1800c20b7  jz      loc_1800C228C
0x1800c20bd  mov     edx, 12h
0x1800c20c2  jmp     loc_1800C2024
0x1800c20c7  mov     rcx, [rsi+18h]
0x1800c20cb  lea     rdx, [rdi+18h]
0x1800c20cf  call    cs:__imp_FwStringCopy
0x1800c20d6  nop     dword ptr [rax+rax+00h]
0x1800c20db  mov     ecx, eax
0x1800c20dd  call    cs:__imp_FwHResultToWindowsError
0x1800c20e4  nop     dword ptr [rax+rax+00h]
0x1800c20e9  mov     ebp, eax
0x1800c20eb  test    eax, eax
0x1800c20ed  jz      short loc_1800C211A
0x1800c20ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c20f6  lea     rax, WPP_GLOBAL_Control
0x1800c20fd  cmp     rcx, rax
0x1800c2100  jz      loc_1800C228C
0x1800c2106  test    byte ptr [rcx+1Ch], 1
0x1800c210a  jz      loc_1800C228C
0x1800c2110  mov     edx, 13h
0x1800c2115  jmp     loc_1800C2024
0x1800c211a  mov     eax, [rsi+4]
0x1800c211d  cmp     eax, 1
0x1800c2120  jnz     short loc_1800C213E
0x1800c2122  mov     rdx, [rsi+28h]
0x1800c2126  lea     r8, [rdi+28h]
0x1800c212a  mov     ecx, [rsi+20h]
0x1800c212d  call    cs:__imp_FwSidAndAttributesCopy
0x1800c2134  nop     dword ptr [rax+rax+00h]
0x1800c2139  jmp     loc_1800C2282
0x1800c213e  cmp     eax, 2
0x1800c2141  jnz     loc_1800C2288
0x1800c2147  mov     [rsp+48h+arg_10], r14
0x1800c214c  mov     r14d, [rsi+20h]
0x1800c2150  mov     [rsp+48h+arg_0], rbx
0x1800c2155  mov     [rsp+48h+arg_8], r12
0x1800c215a  mov     [rsp+48h+var_28], r15
0x1800c215f  mov     qword ptr [rdi+28h], 0
0x1800c2167  test    r14d, r14d
0x1800c216a  jz      loc_1800C223D
0x1800c2170  mov     r12, [rsi+28h]
0x1800c2174  test    r12, r12
0x1800c2177  jz      loc_1800C223D
0x1800c217d  mov     edx, r14d
0x1800c2180  mov     ecx, 8
0x1800c2185  call    cs:__imp_FwAllocArray
0x1800c218c  nop     dword ptr [rax+rax+00h]
0x1800c2191  xor     ebx, ebx
0x1800c2193  mov     r15, rax
0x1800c2196  test    rax, rax
0x1800c2199  jnz     short loc_1800C21C1
0x1800c219b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c21a2  lea     rax, WPP_GLOBAL_Control
0x1800c21a9  cmp     rcx, rax
0x1800c21ac  jz      short loc_1800C222A
0x1800c21ae  test    byte ptr [rcx+1Ch], 1
0x1800c21b2  jz      short loc_1800C222A
0x1800c21b4  mov     edx, 20h ; ' '
0x1800c21b9  mov     r9d, 0Eh
0x1800c21bf  jmp     short loc_1800C221A
0x1800c21c1  test    r14d, r14d
0x1800c21c4  jz      short loc_1800C21F6
0x1800c21c6  mov     rcx, [r12+rbx*8]
0x1800c21ca  lea     rdx, [r15+rbx*8]
0x1800c21ce  call    cs:__imp_FwStringCopy
0x1800c21d5  nop     dword ptr [rax+rax+00h]
0x1800c21da  mov     ecx, eax
0x1800c21dc  call    cs:__imp_FwHResultToWindowsError
0x1800c21e3  nop     dword ptr [rax+rax+00h]
0x1800c21e8  mov     r9d, eax
0x1800c21eb  test    eax, eax
0x1800c21ed  jnz     short loc_1800C21FC
0x1800c21ef  inc     ebx
0x1800c21f1  cmp     ebx, r14d
0x1800c21f4  jb      short loc_1800C21C6
0x1800c21f6  mov     [rdi+28h], r15
0x1800c21fa  jmp     short loc_1800C226E
0x1800c21fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2203  lea     rax, WPP_GLOBAL_Control
0x1800c220a  cmp     rcx, rax
0x1800c220d  jz      short loc_1800C222A
0x1800c220f  test    byte ptr [rcx+1Ch], 1
0x1800c2213  jz      short loc_1800C222A
0x1800c2215  mov     edx, 21h ; '!'
0x1800c221a  mov     rcx, [rcx+10h]
0x1800c221e  lea     r8, WPP_a875d200678f3c386c19a36d1916a086_Traceguids
0x1800c2225  call    WPP_SF_d
0x1800c222a  mov     rdx, r15
0x1800c222d  mov     ecx, ebx
0x1800c222f  call    cs:__imp_FwBinariesFree
0x1800c2236  nop     dword ptr [rax+rax+00h]
0x1800c223b  jmp     short loc_1800C226E
0x1800c223d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2244  lea     rax, WPP_GLOBAL_Control
0x1800c224b  cmp     rcx, rax
0x1800c224e  jz      short loc_1800C226E
0x1800c2250  test    byte ptr [rcx+1Ch], 1
0x1800c2254  jz      short loc_1800C226E
0x1800c2256  mov     rcx, [rcx+10h]
0x1800c225a  lea     r8, WPP_a875d200678f3c386c19a36d1916a086_Traceguids
0x1800c2261  mov     edx, 1Fh
0x1800c2266  xor     r9d, r9d
0x1800c2269  call    WPP_SF_d
0x1800c226e  mov     r15, [rsp+48h+var_28]
0x1800c2273  mov     r14, [rsp+48h+arg_10]
0x1800c2278  mov     r12, [rsp+48h+arg_8]
0x1800c227d  mov     rbx, [rsp+48h+arg_0]
0x1800c2282  mov     eax, [rsi+20h]
0x1800c2285  mov     [rdi+20h], eax
0x1800c2288  mov     [r13+0], rdi
0x1800c228c  mov     eax, ebp
0x1800c228e  add     rsp, 28h
0x1800c2292  pop     r13
0x1800c2294  pop     rdi
0x1800c2295  pop     rsi
0x1800c2296  pop     rbp
0x1800c2297  retn
```
