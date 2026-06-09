# CFwCplLua::EditGlobalPort(ushort *,ushort *,long,long,long,long,ushort * *)

- ea: `0x18002af60`
- end: `0x18002b320`
- name: `?EditGlobalPort@CFwCplLua@@UEAAJPEAG0JJJJPEAPEAG@Z`
- size: `960`
- prototype: `__int64 __fastcall(void **this, LPCWSTR lpString2, unsigned __int16 *, __int16, __int16, int, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009924`
- `0x18000994c`
- `0x18002af60`
- `0x18002c2a0`
- `0x18002c2e0`
- `0x18002c3d8`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b2bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2bd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b19e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002b19e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b1e3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b1e3`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002b2fa`
- `FirewallAPI!FWFreeFirewallRules` at `0x18002b2fa`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b14a`
- `FirewallAPI!FWSetFirewallRule` at `0x18002b14a`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b283`
- `FirewallAPI!FWAddFirewallRule` at `0x18002b283`
- `FirewallAPI!FwFree` at `0x18002b0cc`
- `FirewallAPI!FwFree` at `0x18002b224`
- `FirewallAPI!FwFree` at `0x18002b0cc`
- `FirewallAPI!FwFree` at `0x18002b224`
- `fwbase!FwStringCopy` at `0x18002b0df`
- `fwbase!FwStringCopy` at `0x18002b238`
- `fwbase!FwStringCopy` at `0x18002b0df`
- `fwbase!FwStringCopy` at `0x18002b238`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFwCplLua::EditGlobalPort(
        void **this,
        LPCWSTR lpString2,
        unsigned __int16 *a3,
        __int16 a4,
        __int16 a5,
        int a6,
        int a7,
        unsigned __int16 **a8)
{
  CFwCplLua *v12; // rcx
  int FwRules; // ebx
  __int64 v14; // rdx
  struct _tag_FW_RULE *v15; // rdi
  _QWORD *v16; // rbx
  int v17; // eax
  int v18; // eax
  struct _tag_FW_RULE *v20; // [rsp+20h] [rbp-79h] BYREF
  struct _tag_FW_RULE *v21; // [rsp+28h] [rbp-71h] BYREF
  GUID pguid; // [rsp+30h] [rbp-69h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-59h] BYREF

  v20 = 0;
  v21 = 0;
  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( lpString2 && a3 )
  {
    FwRules = CFwCplLua::EnsurePolicyHandle((CFwCplLua *)this);
    if ( FwRules >= 0 )
    {
      FwRules = GetFwRules(this[8], &v20);
      if ( FwRules >= 0 )
      {
        FwRules = GetRuleByIDWithScopedProfiles(lpString2, v20, &v21);
        if ( FwRules >= 0 )
        {
          v15 = v21;
          v16 = (_QWORD *)((char *)v21 + 24);
          FwFree(*((_QWORD *)v21 + 3));
          *v16 = 0;
          FwRules = FwStringCopy(a3, v16);
          if ( FwRules >= 0 )
          {
            *((_WORD *)v15 + 24) = a5;
            *(_WORD *)(*((_QWORD *)v15 + 9) + 2LL) = a4;
            **((_WORD **)v15 + 9) = a4;
            *((_DWORD *)v15 + 10) = ~a7 & (*((_DWORD *)v15 + 10) | a6);
            v17 = FWSetFirewallRule(this[8], v15);
            FwRules = v17;
            if ( v17 > 0 )
              FwRules = (unsigned __int16)v17 | 0x80070000;
            if ( FwRules >= 0 )
            {
              if ( a7 <= 0 )
                goto LABEL_52;
              FwRules = CoCreateGuid(&pguid);
              if ( FwRules >= 0 )
              {
                if ( StringFromGUID2(&pguid, sz, 40) )
                {
                  FwFree(*((_QWORD *)v15 + 2));
                  *((_QWORD *)v15 + 2) = 0;
                  FwRules = FwStringCopy(sz, (char *)v15 + 16);
                  if ( FwRules >= 0 )
                  {
                    *((_DWORD *)v15 + 10) = a7;
                    *((_WORD *)v15 + 146) &= ~1u;
                    v18 = FWAddFirewallRule(this[8], v15);
                    FwRules = v18;
                    if ( v18 > 0 )
                      FwRules = (unsigned __int16)v18 | 0x80070000;
                    if ( FwRules >= 0 )
                    {
                      *a8 = SysAllocString(sz);
                      goto LABEL_52;
                    }
                    v12 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v14 = 99;
                      goto LABEL_51;
                    }
                  }
                  else
                  {
                    v12 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      v14 = 98;
                      goto LABEL_51;
                    }
                  }
                }
                else
                {
                  FwRules = -2147024774;
                  v12 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v14 = 97;
                    goto LABEL_51;
                  }
                }
              }
              else
              {
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v14 = 96;
                  goto LABEL_51;
                }
              }
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v14 = 95;
                goto LABEL_51;
              }
            }
          }
          else
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v14 = 94;
              goto LABEL_51;
            }
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 93;
            goto LABEL_51;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 92;
          goto LABEL_51;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 91;
LABEL_51:
        WPP_SF_d(*((_QWORD *)v12 + 2), v14, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, (unsigned int)FwRules);
      }
    }
  }
  else
  {
    FwRules = -2147024809;
    if ( v12 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    {
      v14 = 90;
      goto LABEL_51;
    }
  }
LABEL_52:
  if ( v20 )
    FWFreeFirewallRules(v20);
  return (unsigned int)FwRules;
}

```

## disassembly

```asm
0x18002af60  push    rbp
0x18002af62  push    rbx
0x18002af63  push    rsi
0x18002af64  push    rdi
0x18002af65  push    r12
0x18002af67  push    r14
0x18002af69  push    r15
0x18002af6b  lea     rbp, [rsp-7]
0x18002af70  sub     rsp, 0A0h
0x18002af77  mov     rax, cs:__security_cookie
0x18002af7e  xor     rax, rsp
0x18002af81  mov     [rbp+37h+var_40], rax
0x18002af85  mov     r12, [rbp+37h+arg_38]
0x18002af89  mov     rdi, rdx
0x18002af8c  xor     edx, edx; Val
0x18002af8e  mov     [rbp+37h+var_B0], 0
0x18002af96  mov     r14, r8
0x18002af99  mov     [rbp+37h+var_A8], 0
0x18002afa1  mov     rsi, rcx
0x18002afa4  xorps   xmm0, xmm0
0x18002afa7  lea     rcx, [rbp+37h+sz]; void *
0x18002afab  mov     r15d, r9d
0x18002afae  lea     r8d, [rdx+50h]; Size
0x18002afb2  movups  xmmword ptr [rbp+37h+pguid.Data1], xmm0
0x18002afb6  call    memset_0
0x18002afbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afc2  lea     rax, WPP_GLOBAL_Control
0x18002afc9  cmp     rcx, rax
0x18002afcc  jz      short loc_18002AFF7
0x18002afce  test    byte ptr [rcx+1Ch], 8
0x18002afd2  jz      short loc_18002AFF7
0x18002afd4  mov     rcx, [rcx+10h]
0x18002afd8  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002afdf  mov     edx, 59h ; 'Y'
0x18002afe4  call    WPP_SF_
0x18002afe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aff0  lea     rax, WPP_GLOBAL_Control
0x18002aff7  test    rdi, rdi
0x18002affa  jz      loc_18002B2C9
0x18002b000  test    r14, r14
0x18002b003  jz      loc_18002B2C9
0x18002b009  mov     rcx, rsi; this
0x18002b00c  call    ?EnsurePolicyHandle@CFwCplLua@@AEAAJXZ; CFwCplLua::EnsurePolicyHandle(void)
0x18002b011  mov     ebx, eax
0x18002b013  test    eax, eax
0x18002b015  jns     short loc_18002B042
0x18002b017  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b01e  lea     rax, WPP_GLOBAL_Control
0x18002b025  cmp     rcx, rax
0x18002b028  jz      loc_18002B2F1
0x18002b02e  test    byte ptr [rcx+1Ch], 1
0x18002b032  jz      loc_18002B2F1
0x18002b038  mov     edx, 5Bh ; '['
0x18002b03d  jmp     loc_18002B2DE
0x18002b042  mov     rcx, [rsi+40h]; void *
0x18002b046  lea     rdx, [rbp+37h+var_B0]; struct _tag_FW_RULE **
0x18002b04a  call    ?GetFwRules@@YAJPEAXPEAPEAU_tag_FW_RULE@@@Z; GetFwRules(void *,_tag_FW_RULE * *)
0x18002b04f  mov     ebx, eax
0x18002b051  test    eax, eax
0x18002b053  jns     short loc_18002B080
0x18002b055  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b05c  lea     rax, WPP_GLOBAL_Control
0x18002b063  cmp     rcx, rax
0x18002b066  jz      loc_18002B2F1
0x18002b06c  test    byte ptr [rcx+1Ch], 1
0x18002b070  jz      loc_18002B2F1
0x18002b076  mov     edx, 5Ch ; '\'
0x18002b07b  jmp     loc_18002B2DE
0x18002b080  mov     rdx, [rbp+37h+var_B0]; struct _tag_FW_RULE *
0x18002b084  lea     r8, [rbp+37h+var_A8]; struct _tag_FW_RULE **
0x18002b088  mov     rcx, rdi; lpString2
0x18002b08b  call    ?GetRuleByIDWithScopedProfiles@@YAJPEAGPEAU_tag_FW_RULE@@PEAPEAU1@@Z; GetRuleByIDWithScopedProfiles(ushort *,_tag_FW_RULE *,_tag_FW_RULE * *)
0x18002b090  mov     ebx, eax
0x18002b092  test    eax, eax
0x18002b094  jns     short loc_18002B0C1
0x18002b096  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b09d  lea     rax, WPP_GLOBAL_Control
0x18002b0a4  cmp     rcx, rax
0x18002b0a7  jz      loc_18002B2F1
0x18002b0ad  test    byte ptr [rcx+1Ch], 1
0x18002b0b1  jz      loc_18002B2F1
0x18002b0b7  mov     edx, 5Dh ; ']'
0x18002b0bc  jmp     loc_18002B2DE
0x18002b0c1  mov     rdi, [rbp+37h+var_A8]
0x18002b0c5  lea     rbx, [rdi+18h]
0x18002b0c9  mov     rcx, [rbx]
0x18002b0cc  call    cs:__imp_FwFree
0x18002b0d2  mov     rdx, rbx
0x18002b0d5  mov     qword ptr [rbx], 0
0x18002b0dc  mov     rcx, r14
0x18002b0df  call    cs:__imp_FwStringCopy
0x18002b0e5  mov     ebx, eax
0x18002b0e7  test    eax, eax
0x18002b0e9  jns     short loc_18002B116
0x18002b0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0f2  lea     rax, WPP_GLOBAL_Control
0x18002b0f9  cmp     rcx, rax
0x18002b0fc  jz      loc_18002B2F1
0x18002b102  test    byte ptr [rcx+1Ch], 1
0x18002b106  jz      loc_18002B2F1
0x18002b10c  mov     edx, 5Eh ; '^'
0x18002b111  jmp     loc_18002B2DE
0x18002b116  movzx   eax, [rbp+37h+arg_20]
0x18002b11a  mov     rdx, rdi
0x18002b11d  mov     ecx, [rbp+37h+arg_28]
0x18002b120  mov     r14d, [rbp+37h+arg_30]
0x18002b124  mov     [rdi+30h], ax
0x18002b128  mov     rax, [rdi+48h]
0x18002b12c  mov     [rax+2], r15w
0x18002b131  mov     rax, [rdi+48h]
0x18002b135  mov     [rax], r15w
0x18002b139  mov     eax, r14d
0x18002b13c  or      ecx, [rdi+28h]
0x18002b13f  not     eax
0x18002b141  and     ecx, eax
0x18002b143  mov     [rdi+28h], ecx
0x18002b146  mov     rcx, [rsi+40h]
0x18002b14a  call    cs:__imp_FWSetFirewallRule
0x18002b150  mov     ebx, eax
0x18002b152  mov     r15d, 80070000h
0x18002b158  test    eax, eax
0x18002b15a  jle     short loc_18002B162
0x18002b15c  movzx   ebx, ax
0x18002b15f  or      ebx, r15d
0x18002b162  test    ebx, ebx
0x18002b164  jns     short loc_18002B191
0x18002b166  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b16d  lea     rax, WPP_GLOBAL_Control
0x18002b174  cmp     rcx, rax
0x18002b177  jz      loc_18002B2F1
0x18002b17d  test    byte ptr [rcx+1Ch], 1
0x18002b181  jz      loc_18002B2F1
0x18002b187  mov     edx, 5Fh ; '_'
0x18002b18c  jmp     loc_18002B2DE
0x18002b191  test    r14d, r14d
0x18002b194  jle     loc_18002B2F1
0x18002b19a  lea     rcx, [rbp+37h+pguid]; pguid
0x18002b19e  call    cs:__imp_CoCreateGuid
0x18002b1a4  mov     ebx, eax
0x18002b1a6  test    eax, eax
0x18002b1a8  jns     short loc_18002B1D5
0x18002b1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1b1  lea     rax, WPP_GLOBAL_Control
0x18002b1b8  cmp     rcx, rax
0x18002b1bb  jz      loc_18002B2F1
0x18002b1c1  test    byte ptr [rcx+1Ch], 1
0x18002b1c5  jz      loc_18002B2F1
0x18002b1cb  mov     edx, 60h ; '`'
0x18002b1d0  jmp     loc_18002B2DE
0x18002b1d5  mov     r8d, 28h ; '('; cchMax
0x18002b1db  lea     rdx, [rbp+37h+sz]; lpsz
0x18002b1df  lea     rcx, [rbp+37h+pguid]; rguid
0x18002b1e3  call    cs:__imp_StringFromGUID2
0x18002b1e9  test    eax, eax
0x18002b1eb  jnz     short loc_18002B21D
0x18002b1ed  mov     ebx, 8007007Ah
0x18002b1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f9  lea     rax, WPP_GLOBAL_Control
0x18002b200  cmp     rcx, rax
0x18002b203  jz      loc_18002B2F1
0x18002b209  test    byte ptr [rcx+1Ch], 1
0x18002b20d  jz      loc_18002B2F1
0x18002b213  mov     edx, 61h ; 'a'
0x18002b218  jmp     loc_18002B2DE
0x18002b21d  lea     rbx, [rdi+10h]
0x18002b221  mov     rcx, [rbx]
0x18002b224  call    cs:__imp_FwFree
0x18002b22a  mov     rdx, rbx
0x18002b22d  mov     qword ptr [rbx], 0
0x18002b234  lea     rcx, [rbp+37h+sz]
0x18002b238  call    cs:__imp_FwStringCopy
0x18002b23e  mov     ebx, eax
0x18002b240  test    eax, eax
0x18002b242  jns     short loc_18002B26C
0x18002b244  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b24b  lea     rax, WPP_GLOBAL_Control
0x18002b252  cmp     rcx, rax
0x18002b255  jz      loc_18002B2F1
0x18002b25b  test    byte ptr [rcx+1Ch], 1
0x18002b25f  jz      loc_18002B2F1
0x18002b265  mov     edx, 62h ; 'b'
0x18002b26a  jmp     short loc_18002B2DE
0x18002b26c  mov     [rdi+28h], r14d
0x18002b270  mov     eax, 0FFFEh
0x18002b275  and     [rdi+124h], ax
0x18002b27c  mov     rdx, rdi
0x18002b27f  mov     rcx, [rsi+40h]
0x18002b283  call    cs:__imp_FWAddFirewallRule
0x18002b289  mov     ebx, eax
0x18002b28b  test    eax, eax
0x18002b28d  jle     short loc_18002B295
0x18002b28f  movzx   ebx, ax
0x18002b292  or      ebx, r15d
0x18002b295  test    ebx, ebx
0x18002b297  jns     short loc_18002B2B9
0x18002b299  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2a0  lea     rax, WPP_GLOBAL_Control
0x18002b2a7  cmp     rcx, rax
0x18002b2aa  jz      short loc_18002B2F1
0x18002b2ac  test    byte ptr [rcx+1Ch], 1
0x18002b2b0  jz      short loc_18002B2F1
0x18002b2b2  mov     edx, 63h ; 'c'
0x18002b2b7  jmp     short loc_18002B2DE
0x18002b2b9  lea     rcx, [rbp+37h+sz]; psz
0x18002b2bd  call    cs:__imp_SysAllocString
0x18002b2c3  mov     [r12], rax
0x18002b2c7  jmp     short loc_18002B2F1
0x18002b2c9  mov     ebx, 80070057h
0x18002b2ce  cmp     rcx, rax
0x18002b2d1  jz      short loc_18002B2F1
0x18002b2d3  test    byte ptr [rcx+1Ch], 1
0x18002b2d7  jz      short loc_18002B2F1
0x18002b2d9  mov     edx, 5Ah ; 'Z'
0x18002b2de  mov     rcx, [rcx+10h]
0x18002b2e2  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002b2e9  mov     r9d, ebx
0x18002b2ec  call    WPP_SF_d
0x18002b2f1  mov     rcx, [rbp+37h+var_B0]
0x18002b2f5  test    rcx, rcx
0x18002b2f8  jz      short loc_18002B300
0x18002b2fa  call    cs:__imp_FWFreeFirewallRules
0x18002b300  mov     eax, ebx
0x18002b302  mov     rcx, [rbp+37h+var_40]
0x18002b306  xor     rcx, rsp; StackCookie
0x18002b309  call    __security_check_cookie
0x18002b30e  add     rsp, 0A0h
0x18002b315  pop     r15
0x18002b317  pop     r14
0x18002b319  pop     r12
0x18002b31b  pop     rdi
0x18002b31c  pop     rsi
0x18002b31d  pop     rbx
0x18002b31e  pop     rbp
0x18002b31f  retn
```
