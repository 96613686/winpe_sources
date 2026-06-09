# appIsolation::EnterpriseDomainProtection::FwMoneisCreateEdpLoopbackRule(_tag_FW_DIRECTION,_tag_FW_RULE * *)

- ea: `0x1800c2f20`
- end: `0x1800c3107`
- name: `?FwMoneisCreateEdpLoopbackRule@EnterpriseDomainProtection@appIsolation@@AEAAKW4_tag_FW_DIRECTION@@PEAPEAU_tag_FW_RULE@@@Z`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800c3ea0`

## callees

- `0x18000a66c`
- `0x1800729c0`
- `0x180073488`
- `0x1800c2f20`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800c2ff7`
- `fwbase!FwHResultToWindowsError` at `0x1800c3040`
- `fwbase!FwHResultToWindowsError` at `0x1800c2ff7`
- `fwbase!FwHResultToWindowsError` at `0x1800c3040`
- `fwbase!FwStringCopy` at `0x1800c2fe9`
- `fwbase!FwStringCopy` at `0x1800c3032`
- `fwbase!FwStringCopy` at `0x1800c2fe9`
- `fwbase!FwStringCopy` at `0x1800c3032`
- `fwbase!FwAlloc` at `0x1800c2faa`
- `fwbase!FwAlloc` at `0x1800c2faa`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c3092`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c3092`

## string_xrefs

- `0x1800c3074`: `FwStringCopy`

## pseudocode

```c
__int64 __fastcall appIsolation::EnterpriseDomainProtection::FwMoneisCreateEdpLoopbackRule(
        __int64 a1,
        int a2,
        _QWORD *a3)
{
  _WORD *v5; // rax
  _WORD *v6; // rbx
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // edx
  unsigned int v12; // eax
  _OWORD v13[3]; // [rsp+30h] [rbp-88h] BYREF
  _OWORD v14[2]; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v15[2]; // [rsp+80h] [rbp-38h]

  v13[0] = *(_OWORD *)L"EDP Loopback Allow rule";
  v13[1] = *(_OWORD *)L"back Allow rule";
  v13[2] = *(_OWORD *)L"ow rule";
  v14[0] = *(_OWORD *)L"Allow loopback traffic in EDP";
  v14[1] = *(_OWORD *)L"opback traffic in EDP";
  *a3 = 0;
  v15[0] = *(_OWORD *)L"raffic in EDP";
  *(_OWORD *)((char *)v15 + 12) = *(_OWORD *)L" in EDP";
  v5 = (_WORD *)FwAlloc(504);
  v6 = v5;
  if ( !v5 )
    return 14;
  memset_0(v5, 0, 0x1F8u);
  v8 = FwStringCopy(v13, v6 + 12);
  v9 = FwHResultToWindowsError(v8);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_12;
    v11 = 17;
    goto LABEL_11;
  }
  v12 = FwStringCopy(v14, v6 + 16);
  v9 = FwHResultToWindowsError(v12);
  if ( !v9 )
  {
    v6[146] |= 1u;
    v6[212] |= 0x600u;
    v6[4] = 545;
    v6[24] = 256;
    *((_DWORD *)v6 + 72) = 3;
    *((_DWORD *)v6 + 10) = 0x7FFFFFFF;
    *((_DWORD *)v6 + 11) = a2;
    *a3 = v6;
    return v9;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v11 = 18;
LABEL_11:
    WPP_SF_Ds(
      *(_QWORD *)(v10 + 16),
      v11,
      (unsigned int)WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids,
      v9,
      (__int64)"FwStringCopy");
  }
LABEL_12:
  FwFreeWFRule(v6);
  return v9;
}

```

## disassembly

```asm
0x1800c2f20  mov     r11, rsp
0x1800c2f23  mov     [r11+10h], rbx
0x1800c2f27  mov     [r11+20h], rbp
0x1800c2f2b  push    rsi
0x1800c2f2c  sub     rsp, 0B0h
0x1800c2f33  mov     rax, cs:__security_cookie
0x1800c2f3a  xor     rax, rsp
0x1800c2f3d  mov     [rsp+0B8h+var_18], rax
0x1800c2f45  movups  xmm0, xmmword ptr cs:aEdpLoopbackAll; "EDP Loopback Allow rule"
0x1800c2f4c  mov     ecx, 1F8h
0x1800c2f51  mov     rsi, r8
0x1800c2f54  movups  xmm1, xmmword ptr cs:aEdpLoopbackAll+10h; "back Allow rule"
0x1800c2f5b  mov     ebp, edx
0x1800c2f5d  movups  [rsp+0B8h+var_88], xmm0
0x1800c2f62  movups  xmm0, xmmword ptr cs:aEdpLoopbackAll+20h; "ow rule"
0x1800c2f69  movups  [rsp+0B8h+var_78], xmm1
0x1800c2f6e  movups  xmm1, xmmword ptr cs:aAllowLoopbackT; "Allow loopback traffic in EDP"
0x1800c2f75  movups  [rsp+0B8h+var_68], xmm0
0x1800c2f7a  movups  xmm0, xmmword ptr cs:aAllowLoopbackT+10h; "opback traffic in EDP"
0x1800c2f81  movups  [rsp+0B8h+var_58], xmm1
0x1800c2f86  movups  xmm1, xmmword ptr cs:aAllowLoopbackT+20h; "raffic in EDP"
0x1800c2f8d  movups  [rsp+0B8h+var_48], xmm0
0x1800c2f92  movups  xmm0, xmmword ptr cs:aAllowLoopbackT+2Ch; " in EDP"
0x1800c2f99  mov     qword ptr [r8], 0
0x1800c2fa0  movups  xmmword ptr [r11-38h], xmm1
0x1800c2fa5  movups  xmmword ptr [r11-2Ch], xmm0
0x1800c2faa  call    cs:__imp_FwAlloc
0x1800c2fb1  nop     dword ptr [rax+rax+00h]
0x1800c2fb6  mov     rbx, rax
0x1800c2fb9  test    rax, rax
0x1800c2fbc  jnz     short loc_1800C2FC8
0x1800c2fbe  mov     eax, 0Eh
0x1800c2fc3  jmp     loc_1800C30E1
0x1800c2fc8  xor     edx, edx; Val
0x1800c2fca  mov     [rsp+0B8h+arg_0], rdi
0x1800c2fd2  mov     r8d, 1F8h; Size
0x1800c2fd8  mov     rcx, rbx; void *
0x1800c2fdb  call    memset_0
0x1800c2fe0  lea     rdx, [rbx+18h]
0x1800c2fe4  lea     rcx, [rsp+0B8h+var_88]
0x1800c2fe9  call    cs:__imp_FwStringCopy
0x1800c2ff0  nop     dword ptr [rax+rax+00h]
0x1800c2ff5  mov     ecx, eax
0x1800c2ff7  call    cs:__imp_FwHResultToWindowsError
0x1800c2ffe  nop     dword ptr [rax+rax+00h]
0x1800c3003  mov     edi, eax
0x1800c3005  test    eax, eax
0x1800c3007  jz      short loc_1800C3029
0x1800c3009  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3010  lea     rax, WPP_GLOBAL_Control
0x1800c3017  cmp     rcx, rax
0x1800c301a  jz      short loc_1800C308F
0x1800c301c  test    byte ptr [rcx+1Ch], 1
0x1800c3020  jz      short loc_1800C308F
0x1800c3022  mov     edx, 11h
0x1800c3027  jmp     short loc_1800C3070
0x1800c3029  lea     rdx, [rbx+20h]
0x1800c302d  lea     rcx, [rsp+0B8h+var_58]
0x1800c3032  call    cs:__imp_FwStringCopy
0x1800c3039  nop     dword ptr [rax+rax+00h]
0x1800c303e  mov     ecx, eax
0x1800c3040  call    cs:__imp_FwHResultToWindowsError
0x1800c3047  nop     dword ptr [rax+rax+00h]
0x1800c304c  mov     edi, eax
0x1800c304e  test    eax, eax
0x1800c3050  jz      short loc_1800C30A0
0x1800c3052  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3059  lea     rax, WPP_GLOBAL_Control
0x1800c3060  cmp     rcx, rax
0x1800c3063  jz      short loc_1800C308F
0x1800c3065  test    byte ptr [rcx+1Ch], 1
0x1800c3069  jz      short loc_1800C308F
0x1800c306b  mov     edx, 12h
0x1800c3070  mov     rcx, [rcx+10h]
0x1800c3074  lea     rax, aFwstringcopy_0; "FwStringCopy"
0x1800c307b  mov     r9d, edi
0x1800c307e  mov     [rsp+0B8h+var_98], rax
0x1800c3083  lea     r8, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids
0x1800c308a  call    WPP_SF_Ds
0x1800c308f  mov     rcx, rbx
0x1800c3092  call    cs:__imp_FwFreeWFRule
0x1800c3099  nop     dword ptr [rax+rax+00h]
0x1800c309e  jmp     short loc_1800C30D7
0x1800c30a0  or      word ptr [rbx+124h], 1
0x1800c30a8  mov     eax, 600h
0x1800c30ad  or      [rbx+1A8h], ax
0x1800c30b4  mov     word ptr [rbx+8], 221h
0x1800c30ba  mov     word ptr [rbx+30h], 100h
0x1800c30c0  mov     dword ptr [rbx+120h], 3
0x1800c30ca  mov     dword ptr [rbx+28h], 7FFFFFFFh
0x1800c30d1  mov     [rbx+2Ch], ebp
0x1800c30d4  mov     [rsi], rbx
0x1800c30d7  mov     eax, edi
0x1800c30d9  mov     rdi, [rsp+0B8h+arg_0]
0x1800c30e1  mov     rcx, [rsp+0B8h+var_18]
0x1800c30e9  xor     rcx, rsp; StackCookie
0x1800c30ec  call    __security_check_cookie
0x1800c30f1  lea     r11, [rsp+0B8h+var_8]
0x1800c30f9  mov     rbx, [r11+18h]
0x1800c30fd  mov     rbp, [r11+28h]
0x1800c3101  mov     rsp, r11
0x1800c3104  pop     rsi
0x1800c3105  retn
```
