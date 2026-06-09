# appIsolation::EnterpriseDomainProtection::FwMoneisCreatePersonalRule(_tag_FW_RULE * *,ushort const *,ushort const *,_tag_FW_DIRECTION)

- ea: `0x1800bc100`
- end: `0x1800bc3b0`
- name: `?FwMoneisCreatePersonalRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1W4_tag_FW_DIRECTION@@@Z`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bcae0`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800bc100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800bc2e8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800bc2e8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc32e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc32e`
- `fwbase!FwHResultToWindowsError` at `0x1800bc212`
- `fwbase!FwHResultToWindowsError` at `0x1800bc276`
- `fwbase!FwHResultToWindowsError` at `0x1800bc2f0`
- `fwbase!FwHResultToWindowsError` at `0x1800bc212`
- `fwbase!FwHResultToWindowsError` at `0x1800bc276`
- `fwbase!FwHResultToWindowsError` at `0x1800bc2f0`
- `fwbase!FwStringCopy` at `0x1800bc20a`
- `fwbase!FwStringCopy` at `0x1800bc26e`
- `fwbase!FwStringCopy` at `0x1800bc20a`
- `fwbase!FwStringCopy` at `0x1800bc26e`
- `fwbase!FwAlloc` at `0x1800bc1a0`
- `fwbase!FwAlloc` at `0x1800bc2af`
- `fwbase!FwAlloc` at `0x1800bc1a0`
- `fwbase!FwAlloc` at `0x1800bc2af`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bc25a`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bc340`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bc25a`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bc340`

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
        WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_0766a64133523165692ca09dfc63f730_Traceguids, v8);
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
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_0766a64133523165692ca09dfc63f730_Traceguids, 14);
  return v8;
}

```

## disassembly

```asm
0x1800bc100  mov     r11, rsp
0x1800bc103  mov     [r11+8], rbx
0x1800bc107  mov     [r11+18h], rsi
0x1800bc10b  push    rdi
0x1800bc10c  sub     rsp, 0B0h
0x1800bc113  mov     rax, cs:__security_cookie
0x1800bc11a  xor     rax, rsp
0x1800bc11d  mov     [rsp+0B8h+var_18], rax
0x1800bc125  movups  xmm0, xmmword ptr cs:aPersonalConten; "Personal content Allow rule"
0x1800bc12c  mov     ecx, 1F8h
0x1800bc131  mov     rsi, rdx
0x1800bc134  movups  xmm1, xmmword ptr cs:aPersonalConten+10h; " content Allow rule"
0x1800bc13b  movups  [rsp+0B8h+var_88], xmm0
0x1800bc140  movups  xmm0, xmmword ptr cs:aPersonalConten+20h; " Allow rule"
0x1800bc147  movups  [rsp+0B8h+var_78], xmm1
0x1800bc14c  movsd   xmm1, qword ptr cs:aPersonalConten+30h; "ule"
0x1800bc154  movups  [rsp+0B8h+var_68], xmm0
0x1800bc159  movups  xmm0, xmmword ptr cs:aPersonalConten_0; "Personal content allow rule"
0x1800bc160  movsd   [rsp+0B8h+var_58], xmm1
0x1800bc166  movups  xmm1, xmmword ptr cs:aPersonalConten_0+10h; " content allow rule"
0x1800bc16d  movups  [rsp+0B8h+var_50], xmm0
0x1800bc172  movups  xmm0, xmmword ptr cs:aPersonalConten_0+20h; " allow rule"
0x1800bc179  movups  [rsp+0B8h+var_40], xmm1
0x1800bc17e  movsd   xmm1, qword ptr cs:aPersonalConten_0+30h; "ule"
0x1800bc186  movups  xmmword ptr [r11-30h], xmm0
0x1800bc18b  mov     qword ptr [rdx], 0
0x1800bc192  xorps   xmm0, xmm0
0x1800bc195  movsd   qword ptr [r11-20h], xmm1
0x1800bc19b  movups  xmmword ptr [rsp+0B8h+pguid.Data1], xmm0
0x1800bc1a0  call    cs:__imp_FwAlloc
0x1800bc1a6  mov     rdi, rax
0x1800bc1a9  test    rax, rax
0x1800bc1ac  jnz     short loc_1800BC1F1
0x1800bc1ae  mov     ebx, 0Eh
0x1800bc1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc1ba  lea     rax, WPP_GLOBAL_Control
0x1800bc1c1  cmp     rcx, rax
0x1800bc1c4  jz      loc_1800BC389
0x1800bc1ca  test    byte ptr [rcx+1Ch], 1
0x1800bc1ce  jz      loc_1800BC389
0x1800bc1d4  mov     rcx, [rcx+10h]
0x1800bc1d8  lea     r8, WPP_0766a64133523165692ca09dfc63f730_Traceguids
0x1800bc1df  mov     edx, 0Bh
0x1800bc1e4  mov     r9d, ebx
0x1800bc1e7  call    WPP_SF_d
0x1800bc1ec  jmp     loc_1800BC389
0x1800bc1f1  xor     edx, edx; Val
0x1800bc1f3  mov     r8d, 1F8h; Size
0x1800bc1f9  mov     rcx, rdi; void *
0x1800bc1fc  call    memset_0
0x1800bc201  lea     rdx, [rdi+18h]
0x1800bc205  lea     rcx, [rsp+0B8h+var_88]
0x1800bc20a  call    cs:__imp_FwStringCopy
0x1800bc210  mov     ecx, eax
0x1800bc212  call    cs:__imp_FwHResultToWindowsError
0x1800bc218  mov     ebx, eax
0x1800bc21a  test    eax, eax
0x1800bc21c  jz      short loc_1800BC265
0x1800bc21e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc225  lea     rax, WPP_GLOBAL_Control
0x1800bc22c  cmp     rcx, rax
0x1800bc22f  jz      loc_1800BC33D
0x1800bc235  test    byte ptr [rcx+1Ch], 1
0x1800bc239  jz      loc_1800BC33D
0x1800bc23f  mov     edx, 0Ch
0x1800bc244  mov     rcx, [rcx+10h]
0x1800bc248  lea     r8, WPP_0766a64133523165692ca09dfc63f730_Traceguids
0x1800bc24f  mov     r9d, ebx
0x1800bc252  call    WPP_SF_d
0x1800bc257  mov     rcx, rdi
0x1800bc25a  call    cs:__imp_FwFreeWFRule
0x1800bc260  jmp     loc_1800BC389
0x1800bc265  lea     rdx, [rdi+20h]
0x1800bc269  lea     rcx, [rsp+0B8h+var_50]
0x1800bc26e  call    cs:__imp_FwStringCopy
0x1800bc274  mov     ecx, eax
0x1800bc276  call    cs:__imp_FwHResultToWindowsError
0x1800bc27c  mov     ebx, eax
0x1800bc27e  test    eax, eax
0x1800bc280  jz      short loc_1800BC2AA
0x1800bc282  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc289  lea     rax, WPP_GLOBAL_Control
0x1800bc290  cmp     rcx, rax
0x1800bc293  jz      loc_1800BC33D
0x1800bc299  test    byte ptr [rcx+1Ch], 1
0x1800bc29d  jz      loc_1800BC33D
0x1800bc2a3  mov     edx, 0Dh
0x1800bc2a8  jmp     short loc_1800BC244
0x1800bc2aa  mov     ecx, 4Eh ; 'N'
0x1800bc2af  call    cs:__imp_FwAlloc
0x1800bc2b5  mov     [rdi+10h], rax
0x1800bc2b9  test    rax, rax
0x1800bc2bc  jnz     short loc_1800BC2E3
0x1800bc2be  mov     ebx, 0Eh
0x1800bc2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc2ca  lea     rax, WPP_GLOBAL_Control
0x1800bc2d1  cmp     rcx, rax
0x1800bc2d4  jz      short loc_1800BC33D
0x1800bc2d6  test    byte ptr [rcx+1Ch], 1
0x1800bc2da  jz      short loc_1800BC33D
0x1800bc2dc  mov     edx, ebx
0x1800bc2de  jmp     loc_1800BC244
0x1800bc2e3  lea     rcx, [rsp+0B8h+pguid]; pguid
0x1800bc2e8  call    cs:__imp_CoCreateGuid
0x1800bc2ee  mov     ecx, eax
0x1800bc2f0  call    cs:__imp_FwHResultToWindowsError
0x1800bc2f6  mov     ebx, eax
0x1800bc2f8  test    eax, eax
0x1800bc2fa  jz      short loc_1800BC31F
0x1800bc2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc303  lea     rax, WPP_GLOBAL_Control
0x1800bc30a  cmp     rcx, rax
0x1800bc30d  jz      short loc_1800BC33D
0x1800bc30f  test    byte ptr [rcx+1Ch], 1
0x1800bc313  jz      short loc_1800BC33D
0x1800bc315  mov     edx, 0Fh
0x1800bc31a  jmp     loc_1800BC244
0x1800bc31f  mov     rdx, [rdi+10h]; lpsz
0x1800bc323  lea     rcx, [rsp+0B8h+pguid]; rguid
0x1800bc328  mov     r8d, 27h ; '''; cchMax
0x1800bc32e  call    cs:__imp_StringFromGUID2
0x1800bc334  test    eax, eax
0x1800bc336  jnz     short loc_1800BC348
0x1800bc338  mov     ebx, 7Ah ; 'z'
0x1800bc33d  mov     rcx, rdi
0x1800bc340  call    cs:__imp_FwFreeWFRule
0x1800bc346  jmp     short loc_1800BC389
0x1800bc348  mov     eax, [rsp+0B8h+arg_20]
0x1800bc34f  mov     [rdi+2Ch], eax
0x1800bc352  mov     word ptr [rdi+8], 221h
0x1800bc358  mov     dword ptr [rdi+120h], 3
0x1800bc362  mov     word ptr [rdi+30h], 100h
0x1800bc368  mov     dword ptr [rdi+150h], 10000h
0x1800bc372  mov     dword ptr [rdi+0B0h], 40h ; '@'
0x1800bc37c  mov     dword ptr [rdi+0B4h], 40h ; '@'
0x1800bc386  mov     [rsi], rdi
0x1800bc389  mov     eax, ebx
0x1800bc38b  mov     rcx, [rsp+0B8h+var_18]
0x1800bc393  xor     rcx, rsp; StackCookie
0x1800bc396  call    __security_check_cookie
0x1800bc39b  lea     r11, [rsp+0B8h+var_8]
0x1800bc3a3  mov     rbx, [r11+10h]
0x1800bc3a7  mov     rsi, [r11+20h]
0x1800bc3ab  mov     rsp, r11
0x1800bc3ae  pop     rdi
0x1800bc3af  retn
```
