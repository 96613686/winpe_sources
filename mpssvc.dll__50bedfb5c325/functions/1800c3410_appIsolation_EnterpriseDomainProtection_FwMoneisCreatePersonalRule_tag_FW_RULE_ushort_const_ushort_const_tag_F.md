# appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)

- ea: `0x1800c3410`
- end: `0x1800c3703`
- name: `?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3ea0`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x180073488`
- `0x1800c3410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3622`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3622`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c3674`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c3674`
- `fwbase!FwHResultToWindowsError` at `0x1800c352e`
- `fwbase!FwHResultToWindowsError` at `0x1800c35a4`
- `fwbase!FwHResultToWindowsError` at `0x1800c3630`
- `fwbase!FwHResultToWindowsError` at `0x1800c352e`
- `fwbase!FwHResultToWindowsError` at `0x1800c35a4`
- `fwbase!FwHResultToWindowsError` at `0x1800c3630`
- `fwbase!FwStringCopy` at `0x1800c3520`
- `fwbase!FwStringCopy` at `0x1800c3596`
- `fwbase!FwStringCopy` at `0x1800c3520`
- `fwbase!FwStringCopy` at `0x1800c3596`
- `fwbase!FwAlloc` at `0x1800c34b0`
- `fwbase!FwAlloc` at `0x1800c35e3`
- `fwbase!FwAlloc` at `0x1800c34b0`
- `fwbase!FwAlloc` at `0x1800c35e3`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c357c`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c368c`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c357c`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c368c`

## pseudocode

```c
__int64 __fastcall appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  char *v6; // rax
  char *v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  GUID pguid; // [rsp+20h] [rbp-98h] BYREF
  _OWORD v17[3]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v18; // [rsp+60h] [rbp-58h]
  _OWORD v19[3]; // [rsp+68h] [rbp-50h] BYREF
  __int64 v20; // [rsp+98h] [rbp-20h]

  v17[0] = *(_OWORD *)L"Personal content Allow rule";
  v17[1] = *(_OWORD *)L" content Allow rule";
  v17[2] = *(_OWORD *)L" Allow rule";
  v18 = *(_QWORD *)L"ule";
  v19[0] = *(_OWORD *)L"Personal content allow rule";
  v19[1] = *(_OWORD *)L" content allow rule";
  v19[2] = *(_OWORD *)L" allow rule";
  *a2 = 0;
  v20 = *(_QWORD *)L"ule";
  pguid = 0;
  v6 = (char *)FwAlloc(504);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0x1F8u);
    v9 = FwStringCopy(v17, v7 + 24);
    v8 = FwHResultToWindowsError(v9);
    if ( v8 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v11 = 12;
LABEL_9:
        WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids, v8);
        FwFreeWFRule(v7);
        return v8;
      }
    }
    else
    {
      v12 = FwStringCopy(v19, v7 + 32);
      v8 = FwHResultToWindowsError(v12);
      if ( v8 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v11 = 13;
          goto LABEL_9;
        }
      }
      else
      {
        v13 = FwAlloc(78);
        *((_QWORD *)v7 + 2) = v13;
        if ( v13 )
        {
          v14 = CoCreateGuid(&pguid);
          v8 = FwHResultToWindowsError(v14);
          if ( v8 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v11 = 15;
              goto LABEL_9;
            }
          }
          else
          {
            if ( StringFromGUID2(&pguid, *((LPOLESTR *)v7 + 2), 39) )
            {
              *((_DWORD *)v7 + 11) = a5;
              *((_WORD *)v7 + 4) = 545;
              *((_DWORD *)v7 + 72) = 3;
              *((_WORD *)v7 + 24) = 256;
              *((_DWORD *)v7 + 84) = 0x10000;
              *((_DWORD *)v7 + 44) = 64;
              *((_DWORD *)v7 + 45) = 64;
              *a2 = v7;
              return v8;
            }
            v8 = 122;
          }
        }
        else
        {
          v8 = 14;
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v11 = 14;
            goto LABEL_9;
          }
        }
      }
    }
    FwFreeWFRule(v7);
    return v8;
  }
  v8 = 14;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids, 14);
  return v8;
}

```

## disassembly

```asm
0x1800c3410  mov     r11, rsp
0x1800c3413  mov     [r11+8], rbx
0x1800c3417  mov     [r11+18h], rsi
0x1800c341b  push    rdi
0x1800c341c  sub     rsp, 0B0h
0x1800c3423  mov     rax, cs:__security_cookie
0x1800c342a  xor     rax, rsp
0x1800c342d  mov     [rsp+0B8h+var_18], rax
0x1800c3435  movups  xmm0, xmmword ptr cs:aPersonalConten; "Personal content Allow rule"
0x1800c343c  mov     ecx, 1F8h
0x1800c3441  mov     rsi, rdx
0x1800c3444  movups  xmm1, xmmword ptr cs:aPersonalConten+10h; " content Allow rule"
0x1800c344b  movups  [rsp+0B8h+var_88], xmm0
0x1800c3450  movups  xmm0, xmmword ptr cs:aPersonalConten+20h; " Allow rule"
0x1800c3457  movups  [rsp+0B8h+var_78], xmm1
0x1800c345c  movsd   xmm1, qword ptr cs:aPersonalConten+30h; "ule"
0x1800c3464  movups  [rsp+0B8h+var_68], xmm0
0x1800c3469  movups  xmm0, xmmword ptr cs:aPersonalConten_0; "Personal content allow rule"
0x1800c3470  movsd   [rsp+0B8h+var_58], xmm1
0x1800c3476  movups  xmm1, xmmword ptr cs:aPersonalConten_0+10h; " content allow rule"
0x1800c347d  movups  [rsp+0B8h+var_50], xmm0
0x1800c3482  movups  xmm0, xmmword ptr cs:aPersonalConten_0+20h; " allow rule"
0x1800c3489  movups  [rsp+0B8h+var_40], xmm1
0x1800c348e  movsd   xmm1, qword ptr cs:aPersonalConten_0+30h; "ule"
0x1800c3496  movups  xmmword ptr [r11-30h], xmm0
0x1800c349b  mov     qword ptr [rdx], 0
0x1800c34a2  xorps   xmm0, xmm0
0x1800c34a5  movsd   qword ptr [r11-20h], xmm1
0x1800c34ab  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x1800c34b0  call    cs:__imp_FwAlloc
0x1800c34b7  nop     dword ptr [rax+rax+00h]
0x1800c34bc  mov     rdi, rax
0x1800c34bf  test    rax, rax
0x1800c34c2  jnz     short loc_1800C3507
0x1800c34c4  mov     ebx, 0Eh
0x1800c34c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c34d0  lea     rax, WPP_GLOBAL_Control
0x1800c34d7  cmp     rcx, rax
0x1800c34da  jz      loc_1800C36DB
0x1800c34e0  test    byte ptr [rcx+1Ch], 1
0x1800c34e4  jz      loc_1800C36DB
0x1800c34ea  mov     rcx, [rcx+10h]
0x1800c34ee  lea     r8, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids
0x1800c34f5  mov     edx, 0Bh
0x1800c34fa  mov     r9d, ebx
0x1800c34fd  call    WPP_SF_d
0x1800c3502  jmp     loc_1800C36DB
0x1800c3507  xor     edx, edx; Val
0x1800c3509  mov     r8d, 1F8h; Size
0x1800c350f  mov     rcx, rdi; void *
0x1800c3512  call    memset_0
0x1800c3517  lea     rdx, [rdi+18h]
0x1800c351b  lea     rcx, [rsp+0B8h+var_88]
0x1800c3520  call    cs:__imp_FwStringCopy
0x1800c3527  nop     dword ptr [rax+rax+00h]
0x1800c352c  mov     ecx, eax
0x1800c352e  call    cs:__imp_FwHResultToWindowsError
0x1800c3535  nop     dword ptr [rax+rax+00h]
0x1800c353a  mov     ebx, eax
0x1800c353c  test    eax, eax
0x1800c353e  jz      short loc_1800C358D
0x1800c3540  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3547  lea     rax, WPP_GLOBAL_Control
0x1800c354e  cmp     rcx, rax
0x1800c3551  jz      loc_1800C3689
0x1800c3557  test    byte ptr [rcx+1Ch], 1
0x1800c355b  jz      loc_1800C3689
0x1800c3561  mov     edx, 0Ch
0x1800c3566  mov     rcx, [rcx+10h]
0x1800c356a  lea     r8, WPP_8a4c25f4ce093197c3f0fcd6b5570cca_Traceguids
0x1800c3571  mov     r9d, ebx
0x1800c3574  call    WPP_SF_d
0x1800c3579  mov     rcx, rdi
0x1800c357c  call    cs:__imp_FwFreeWFRule
0x1800c3583  nop     dword ptr [rax+rax+00h]
0x1800c3588  jmp     loc_1800C36DB
0x1800c358d  lea     rdx, [rdi+20h]
0x1800c3591  lea     rcx, [rsp+0B8h+var_50]
0x1800c3596  call    cs:__imp_FwStringCopy
0x1800c359d  nop     dword ptr [rax+rax+00h]
0x1800c35a2  mov     ecx, eax
0x1800c35a4  call    cs:__imp_FwHResultToWindowsError
0x1800c35ab  nop     dword ptr [rax+rax+00h]
0x1800c35b0  mov     ebx, eax
0x1800c35b2  test    eax, eax
0x1800c35b4  jz      short loc_1800C35DE
0x1800c35b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c35bd  lea     rax, WPP_GLOBAL_Control
0x1800c35c4  cmp     rcx, rax
0x1800c35c7  jz      loc_1800C3689
0x1800c35cd  test    byte ptr [rcx+1Ch], 1
0x1800c35d1  jz      loc_1800C3689
0x1800c35d7  mov     edx, 0Dh
0x1800c35dc  jmp     short loc_1800C3566
0x1800c35de  mov     ecx, 4Eh ; 'N'
0x1800c35e3  call    cs:__imp_FwAlloc
0x1800c35ea  nop     dword ptr [rax+rax+00h]
0x1800c35ef  mov     [rdi+10h], rax
0x1800c35f3  test    rax, rax
0x1800c35f6  jnz     short loc_1800C361D
0x1800c35f8  mov     ebx, 0Eh
0x1800c35fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3604  lea     rax, WPP_GLOBAL_Control
0x1800c360b  cmp     rcx, rax
0x1800c360e  jz      short loc_1800C3689
0x1800c3610  test    byte ptr [rcx+1Ch], 1
0x1800c3614  jz      short loc_1800C3689
0x1800c3616  mov     edx, ebx
0x1800c3618  jmp     loc_1800C3566
0x1800c361d  lea     rcx, [rsp+0B8h+pguid]; pguid
0x1800c3622  call    cs:__imp_CoCreateGuid
0x1800c3629  nop     dword ptr [rax+rax+00h]
0x1800c362e  mov     ecx, eax
0x1800c3630  call    cs:__imp_FwHResultToWindowsError
0x1800c3637  nop     dword ptr [rax+rax+00h]
0x1800c363c  mov     ebx, eax
0x1800c363e  test    eax, eax
0x1800c3640  jz      short loc_1800C3665
0x1800c3642  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3649  lea     rax, WPP_GLOBAL_Control
0x1800c3650  cmp     rcx, rax
0x1800c3653  jz      short loc_1800C3689
0x1800c3655  test    byte ptr [rcx+1Ch], 1
0x1800c3659  jz      short loc_1800C3689
0x1800c365b  mov     edx, 0Fh
0x1800c3660  jmp     loc_1800C3566
0x1800c3665  mov     rdx, [rdi+10h]; lpsz
0x1800c3669  lea     rcx, [rsp+0B8h+pguid]; rguid
0x1800c366e  mov     r8d, 27h ; '''; cchMax
0x1800c3674  call    cs:__imp_StringFromGUID2
0x1800c367b  nop     dword ptr [rax+rax+00h]
0x1800c3680  test    eax, eax
0x1800c3682  jnz     short loc_1800C369A
0x1800c3684  mov     ebx, 7Ah ; 'z'
0x1800c3689  mov     rcx, rdi
0x1800c368c  call    cs:__imp_FwFreeWFRule
0x1800c3693  nop     dword ptr [rax+rax+00h]
0x1800c3698  jmp     short loc_1800C36DB
0x1800c369a  mov     eax, [rsp+0B8h+arg_20]
0x1800c36a1  mov     [rdi+2Ch], eax
0x1800c36a4  mov     word ptr [rdi+8], 221h
0x1800c36aa  mov     dword ptr [rdi+120h], 3
0x1800c36b4  mov     word ptr [rdi+30h], 100h
0x1800c36ba  mov     dword ptr [rdi+150h], 10000h
0x1800c36c4  mov     dword ptr [rdi+0B0h], 40h ; '@'
0x1800c36ce  mov     dword ptr [rdi+0B4h], 40h ; '@'
0x1800c36d8  mov     [rsi], rdi
0x1800c36db  mov     eax, ebx
0x1800c36dd  mov     rcx, [rsp+0B8h+var_18]
0x1800c36e5  xor     rcx, rsp; StackCookie
0x1800c36e8  call    __security_check_cookie
0x1800c36ed  lea     r11, [rsp+0B8h+var_8]
0x1800c36f5  mov     rbx, [r11+10h]
0x1800c36f9  mov     rsi, [r11+20h]
0x1800c36fd  mov     rsp, r11
0x1800c3700  pop     rdi
0x1800c3701  retn
```
