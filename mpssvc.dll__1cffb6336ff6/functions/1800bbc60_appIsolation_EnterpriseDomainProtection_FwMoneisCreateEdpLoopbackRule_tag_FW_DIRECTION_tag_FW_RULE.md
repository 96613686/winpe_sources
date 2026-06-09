# appIsolation::EnterpriseDomainProtection::FwMoneisCreateEdpLoopbackRule(_tag_FW_DIRECTION,_tag_FW_RULE * *)

- ea: `0x1800bbc60`
- end: `0x1800bbe22`
- name: `?FwMoneisCreateEdpLoopbackRule@EnterpriseDomainProtection@appIsolation@@AEAAKW4_tag_FW_DIRECTION@@PEAPEAU_tag_FW_RULE@@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800bcae0`

## callees

- `0x18000ae9c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800bbc60`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800bbd2b`
- `fwbase!FwHResultToWindowsError` at `0x1800bbd68`
- `fwbase!FwHResultToWindowsError` at `0x1800bbd2b`
- `fwbase!FwHResultToWindowsError` at `0x1800bbd68`
- `fwbase!FwStringCopy` at `0x1800bbd23`
- `fwbase!FwStringCopy` at `0x1800bbd60`
- `fwbase!FwStringCopy` at `0x1800bbd23`
- `fwbase!FwStringCopy` at `0x1800bbd60`
- `fwbase!FwAlloc` at `0x1800bbcea`
- `fwbase!FwAlloc` at `0x1800bbcea`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bbdb4`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bbdb4`

## string_xrefs

- `0x1800bbd96`: `FwStringCopy`

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
      (unsigned int)WPP_0766a64133523165692ca09dfc63f730_Traceguids,
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
0x1800bbc60  mov     r11, rsp
0x1800bbc63  mov     [r11+10h], rbx
0x1800bbc67  mov     [r11+20h], rbp
0x1800bbc6b  push    rsi
0x1800bbc6c  sub     rsp, 0B0h
0x1800bbc73  mov     rax, cs:__security_cookie
0x1800bbc7a  xor     rax, rsp
0x1800bbc7d  mov     [rsp+0B8h+var_18], rax
0x1800bbc85  movups  xmm0, xmmword ptr cs:aEdpLoopbackAll; "EDP Loopback Allow rule"
0x1800bbc8c  mov     ecx, 1F8h
0x1800bbc91  mov     rsi, r8
0x1800bbc94  movups  xmm1, xmmword ptr cs:aEdpLoopbackAll+10h; "back Allow rule"
0x1800bbc9b  mov     ebp, edx
0x1800bbc9d  movups  [rsp+0B8h+var_88], xmm0
0x1800bbca2  movups  xmm0, xmmword ptr cs:aEdpLoopbackAll+20h; "ow rule"
0x1800bbca9  movups  [rsp+0B8h+var_78], xmm1
0x1800bbcae  movups  xmm1, xmmword ptr cs:aAllowLoopbackT; "Allow loopback traffic in EDP"
0x1800bbcb5  movups  [rsp+0B8h+var_68], xmm0
0x1800bbcba  movups  xmm0, xmmword ptr cs:aAllowLoopbackT+10h; "opback traffic in EDP"
0x1800bbcc1  movups  [rsp+0B8h+var_58], xmm1
0x1800bbcc6  movups  xmm1, xmmword ptr cs:aAllowLoopbackT+20h; "raffic in EDP"
0x1800bbccd  movups  [rsp+0B8h+var_48], xmm0
0x1800bbcd2  movups  xmm0, xmmword ptr cs:aAllowLoopbackT+2Ch; " in EDP"
0x1800bbcd9  mov     qword ptr [r8], 0
0x1800bbce0  movups  xmmword ptr [r11-38h], xmm1
0x1800bbce5  movups  xmmword ptr [r11-2Ch], xmm0
0x1800bbcea  call    cs:__imp_FwAlloc
0x1800bbcf0  mov     rbx, rax
0x1800bbcf3  test    rax, rax
0x1800bbcf6  jnz     short loc_1800BBD02
0x1800bbcf8  mov     eax, 0Eh
0x1800bbcfd  jmp     loc_1800BBDFD
0x1800bbd02  xor     edx, edx; Val
0x1800bbd04  mov     [rsp+0B8h+arg_0], rdi
0x1800bbd0c  mov     r8d, 1F8h; Size
0x1800bbd12  mov     rcx, rbx; void *
0x1800bbd15  call    memset_0
0x1800bbd1a  lea     rdx, [rbx+18h]
0x1800bbd1e  lea     rcx, [rsp+0B8h+var_88]
0x1800bbd23  call    cs:__imp_FwStringCopy
0x1800bbd29  mov     ecx, eax
0x1800bbd2b  call    cs:__imp_FwHResultToWindowsError
0x1800bbd31  mov     edi, eax
0x1800bbd33  test    eax, eax
0x1800bbd35  jz      short loc_1800BBD57
0x1800bbd37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbd3e  lea     rax, WPP_GLOBAL_Control
0x1800bbd45  cmp     rcx, rax
0x1800bbd48  jz      short loc_1800BBDB1
0x1800bbd4a  test    byte ptr [rcx+1Ch], 1
0x1800bbd4e  jz      short loc_1800BBDB1
0x1800bbd50  mov     edx, 11h
0x1800bbd55  jmp     short loc_1800BBD92
0x1800bbd57  lea     rdx, [rbx+20h]
0x1800bbd5b  lea     rcx, [rsp+0B8h+var_58]
0x1800bbd60  call    cs:__imp_FwStringCopy
0x1800bbd66  mov     ecx, eax
0x1800bbd68  call    cs:__imp_FwHResultToWindowsError
0x1800bbd6e  mov     edi, eax
0x1800bbd70  test    eax, eax
0x1800bbd72  jz      short loc_1800BBDBC
0x1800bbd74  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bbd7b  lea     rax, WPP_GLOBAL_Control
0x1800bbd82  cmp     rcx, rax
0x1800bbd85  jz      short loc_1800BBDB1
0x1800bbd87  test    byte ptr [rcx+1Ch], 1
0x1800bbd8b  jz      short loc_1800BBDB1
0x1800bbd8d  mov     edx, 12h
0x1800bbd92  mov     rcx, [rcx+10h]
0x1800bbd96  lea     rax, aFwstringcopy_0; "FwStringCopy"
0x1800bbd9d  mov     r9d, edi
0x1800bbda0  mov     [rsp+0B8h+var_98], rax
0x1800bbda5  lea     r8, WPP_0766a64133523165692ca09dfc63f730_Traceguids
0x1800bbdac  call    WPP_SF_Ds
0x1800bbdb1  mov     rcx, rbx
0x1800bbdb4  call    cs:__imp_FwFreeWFRule
0x1800bbdba  jmp     short loc_1800BBDF3
0x1800bbdbc  or      word ptr [rbx+124h], 1
0x1800bbdc4  mov     eax, 600h
0x1800bbdc9  or      [rbx+1A8h], ax
0x1800bbdd0  mov     word ptr [rbx+8], 221h
0x1800bbdd6  mov     word ptr [rbx+30h], 100h
0x1800bbddc  mov     dword ptr [rbx+120h], 3
0x1800bbde6  mov     dword ptr [rbx+28h], 7FFFFFFFh
0x1800bbded  mov     [rbx+2Ch], ebp
0x1800bbdf0  mov     [rsi], rbx
0x1800bbdf3  mov     eax, edi
0x1800bbdf5  mov     rdi, [rsp+0B8h+arg_0]
0x1800bbdfd  mov     rcx, [rsp+0B8h+var_18]
0x1800bbe05  xor     rcx, rsp; StackCookie
0x1800bbe08  call    __security_check_cookie
0x1800bbe0d  lea     r11, [rsp+0B8h+var_8]
0x1800bbe15  mov     rbx, [r11+18h]
0x1800bbe19  mov     rbp, [r11+28h]
0x1800bbe1d  mov     rsp, r11
0x1800bbe20  pop     rsi
0x1800bbe21  retn
```
