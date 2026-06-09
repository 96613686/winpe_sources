# NcaEvCollNamePrefValidateNrptRelevantPolicyConfig(void)

- ea: `0x180014248`
- end: `0x180014323`
- name: `?NcaEvCollNamePrefValidateNrptRelevantPolicyConfig@@YAJXZ`
- size: `219`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014058`

## callees

- `0x180004f34`
- `0x180014248`
- `0x18001cc70`

## import_xrefs

- `DNSAPI!DnsGetPolicyTableInfo` at `0x18001427d`
- `DNSAPI!DnsGetPolicyTableInfo` at `0x18001427d`
- `DNSAPI!DnsFreePolicyConfig` at `0x1800142f4`
- `DNSAPI!DnsFreePolicyConfig` at `0x1800142f4`

## pseudocode

```c
__int64 NcaEvCollNamePrefValidateNrptRelevantPolicyConfig(void)
{
  int PolicyTableInfo; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  v4 = 0;
  v5 = 0;
  v6 = 0;
  PolicyTableInfo = DnsGetPolicyTableInfo(0, 0, &v4, &v5);
  if ( PolicyTableInfo )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 29;
LABEL_9:
      WPP_SF_d(v1[2], v2, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids, (unsigned int)PolicyTableInfo);
    }
  }
  else if ( (v5 & 1) == 0 )
  {
    PolicyTableInfo = 50;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 30;
      goto LABEL_9;
    }
  }
  if ( v4 )
    DnsFreePolicyConfig();
  if ( PolicyTableInfo > 0 )
    return (unsigned __int16)PolicyTableInfo | 0x80070000;
  return (unsigned int)PolicyTableInfo;
}

```

## disassembly

```asm
0x180014248  mov     r11, rsp
0x18001424b  push    rbx
0x18001424c  sub     rsp, 40h
0x180014250  mov     rax, cs:__security_cookie
0x180014257  xor     rax, rsp
0x18001425a  mov     [rsp+48h+var_10], rax
0x18001425f  xor     eax, eax
0x180014261  mov     qword ptr [r11-28h], 0
0x180014269  mov     [r11-20h], rax
0x18001426d  lea     r9, [r11-20h]
0x180014271  lea     r8, [r11-28h]
0x180014275  mov     [rsp+48h+var_18], eax
0x180014279  xor     edx, edx
0x18001427b  xor     ecx, ecx
0x18001427d  call    cs:__imp_DnsGetPolicyTableInfo
0x180014284  nop     dword ptr [rax+rax+00h]
0x180014289  mov     ebx, eax
0x18001428b  test    eax, eax
0x18001428d  jz      short loc_1800142AF
0x18001428f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014296  lea     rax, WPP_GLOBAL_Control
0x18001429d  cmp     rcx, rax
0x1800142a0  jz      short loc_1800142EA
0x1800142a2  test    byte ptr [rcx+1Ch], 1
0x1800142a6  jz      short loc_1800142EA
0x1800142a8  mov     edx, 1Dh
0x1800142ad  jmp     short loc_1800142D7
0x1800142af  test    byte ptr [rsp+48h+var_20], 1
0x1800142b4  jnz     short loc_1800142EA
0x1800142b6  mov     ebx, 32h ; '2'
0x1800142bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142c2  lea     rax, WPP_GLOBAL_Control
0x1800142c9  cmp     rcx, rax
0x1800142cc  jz      short loc_1800142EA
0x1800142ce  test    byte ptr [rcx+1Ch], 1
0x1800142d2  jz      short loc_1800142EA
0x1800142d4  lea     edx, [rbx-14h]
0x1800142d7  mov     rcx, [rcx+10h]
0x1800142db  lea     r8, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids
0x1800142e2  mov     r9d, ebx
0x1800142e5  call    WPP_SF_d
0x1800142ea  mov     rcx, [rsp+48h+var_28]
0x1800142ef  test    rcx, rcx
0x1800142f2  jz      short loc_180014300
0x1800142f4  call    cs:__imp_DnsFreePolicyConfig
0x1800142fb  nop     dword ptr [rax+rax+00h]
0x180014300  test    ebx, ebx
0x180014302  jle     short loc_18001430D
0x180014304  movzx   ebx, bx
0x180014307  or      ebx, 80070000h
0x18001430d  mov     eax, ebx
0x18001430f  mov     rcx, [rsp+48h+var_10]
0x180014314  xor     rcx, rsp; StackCookie
0x180014317  call    __security_check_cookie
0x18001431c  add     rsp, 40h
0x180014320  pop     rbx
0x180014321  retn
```
