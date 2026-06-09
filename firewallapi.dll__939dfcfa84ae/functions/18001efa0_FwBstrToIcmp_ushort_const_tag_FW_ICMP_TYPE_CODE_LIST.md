# FwBstrToIcmp(ushort * const,_tag_FW_ICMP_TYPE_CODE_LIST *)

- ea: `0x18001efa0`
- end: `0x18001f0f8`
- name: `?FwBstrToIcmp@@YAJQEAGPEAU_tag_FW_ICMP_TYPE_CODE_LIST@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(unsigned __int16 *const, struct _tag_FW_ICMP_TYPE_CODE_LIST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ed70`

## callees

- `0x180005e0c`
- `0x18001efa0`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001efee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001efee`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001f05e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001f05e`
- `fwbase!FwBaseFree` at `0x18001f0b2`
- `fwbase!FwBaseFree` at `0x18001f0c6`
- `fwbase!FwBaseFree` at `0x18001f0b2`
- `fwbase!FwBaseFree` at `0x18001f0c6`
- `fwbase!FwStringCopy` at `0x18001f00a`
- `fwbase!FwStringCopy` at `0x18001f00a`
- `FWPolicyIOMgr!FwParseICMPTypeCodes` at `0x18001f075`
- `FWPolicyIOMgr!FwParseICMPTypeCodes` at `0x18001f075`

## pseudocode

```c
__int64 __fastcall FwBstrToIcmp(unsigned __int16 *const a1, struct _tag_FW_ICMP_TYPE_CODE_LIST *a2)
{
  int v4; // ebx
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  wchar_t *i; // rcx
  wchar_t *v8; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF

  String = 0;
  Context = 0;
  *(_OWORD *)a2 = 0;
  if ( a1 && *a1 && (unsigned int)_o__wcsicmp(a1, "*") )
  {
    v4 = FwStringCopy(a1, &String);
    if ( v4 >= 0 )
    {
      for ( i = String; ; i = 0 )
      {
        v8 = wcstok_s(i, L",", &Context);
        if ( !v8 )
          break;
        v4 = FwParseICMPTypeCodes(v8, a2);
        if ( v4 < 0 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 33;
            goto LABEL_8;
          }
          break;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 32;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v4);
      }
    }
  }
  else
  {
    v4 = 0;
  }
  FwBaseFree(String);
  if ( v4 < 0 )
  {
    FwBaseFree(*((_QWORD *)a2 + 1));
    *(_OWORD *)a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001efa0  mov     r11, rsp
0x18001efa3  mov     [r11+18h], rbx
0x18001efa7  mov     [r11+20h], rsi
0x18001efab  push    rdi
0x18001efac  sub     rsp, 40h
0x18001efb0  mov     rax, cs:__security_cookie
0x18001efb7  xor     rax, rsp
0x18001efba  mov     [rsp+48h+var_18], rax
0x18001efbf  xor     esi, esi
0x18001efc1  xorps   xmm0, xmm0
0x18001efc4  mov     [r11-28h], rsi
0x18001efc8  mov     rdi, rdx
0x18001efcb  mov     [r11-20h], rsi
0x18001efcf  mov     rbx, rcx
0x18001efd2  movups  xmmword ptr [rdx], xmm0
0x18001efd5  test    rcx, rcx
0x18001efd8  jz      loc_18001F0AB
0x18001efde  cmp     [rcx], si
0x18001efe1  jz      loc_18001F0AB
0x18001efe7  lea     rdx, asc_180080438; "*"
0x18001efee  call    cs:__imp__o__wcsicmp
0x18001eff5  nop     dword ptr [rax+rax+00h]
0x18001effa  test    eax, eax
0x18001effc  jz      loc_18001F0AB
0x18001f002  lea     rdx, [rsp+48h+String]
0x18001f007  mov     rcx, rbx
0x18001f00a  call    cs:__imp_FwStringCopy
0x18001f011  nop     dword ptr [rax+rax+00h]
0x18001f016  mov     ebx, eax
0x18001f018  test    eax, eax
0x18001f01a  jns     short loc_18001F04D
0x18001f01c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f023  lea     rax, WPP_GLOBAL_Control
0x18001f02a  cmp     rcx, rax
0x18001f02d  jz      short loc_18001F0AD
0x18001f02f  test    byte ptr [rcx+1Ch], 1
0x18001f033  jz      short loc_18001F0AD
0x18001f035  lea     edx, [rsi+20h]
0x18001f038  mov     rcx, [rcx+10h]
0x18001f03c  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18001f043  mov     r9d, ebx
0x18001f046  call    WPP_SF_d
0x18001f04b  jmp     short loc_18001F0AD
0x18001f04d  mov     rcx, [rsp+48h+String]; String
0x18001f052  lea     r8, [rsp+48h+Context]; Context
0x18001f057  lea     rdx, Delimiter; ","
0x18001f05e  call    cs:__imp_wcstok_s
0x18001f065  nop     dword ptr [rax+rax+00h]
0x18001f06a  test    rax, rax
0x18001f06d  jz      short loc_18001F0AD
0x18001f06f  mov     rdx, rdi
0x18001f072  mov     rcx, rax
0x18001f075  call    cs:__imp_?FwParseICMPTypeCodes@@YAJPEBGPEAU_tag_FW_ICMP_TYPE_CODE_LIST@@@Z; FwParseICMPTypeCodes(ushort const *,_tag_FW_ICMP_TYPE_CODE_LIST *)
0x18001f07c  nop     dword ptr [rax+rax+00h]
0x18001f081  mov     ebx, eax
0x18001f083  test    eax, eax
0x18001f085  js      short loc_18001F08B
0x18001f087  xor     ecx, ecx
0x18001f089  jmp     short loc_18001F052
0x18001f08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f092  lea     rax, WPP_GLOBAL_Control
0x18001f099  cmp     rcx, rax
0x18001f09c  jz      short loc_18001F0AD
0x18001f09e  test    byte ptr [rcx+1Ch], 1
0x18001f0a2  jz      short loc_18001F0AD
0x18001f0a4  mov     edx, 21h ; '!'
0x18001f0a9  jmp     short loc_18001F038
0x18001f0ab  mov     ebx, esi
0x18001f0ad  mov     rcx, [rsp+48h+String]
0x18001f0b2  call    cs:__imp_FwBaseFree
0x18001f0b9  nop     dword ptr [rax+rax+00h]
0x18001f0be  test    ebx, ebx
0x18001f0c0  jns     short loc_18001F0D8
0x18001f0c2  mov     rcx, [rdi+8]
0x18001f0c6  call    cs:__imp_FwBaseFree
0x18001f0cd  nop     dword ptr [rax+rax+00h]
0x18001f0d2  xorps   xmm0, xmm0
0x18001f0d5  movups  xmmword ptr [rdi], xmm0
0x18001f0d8  mov     eax, ebx
0x18001f0da  mov     rcx, [rsp+48h+var_18]
0x18001f0df  xor     rcx, rsp; StackCookie
0x18001f0e2  call    __security_check_cookie
0x18001f0e7  mov     rbx, [rsp+48h+arg_10]
0x18001f0ec  mov     rsi, [rsp+48h+arg_18]
0x18001f0f1  add     rsp, 40h
0x18001f0f5  pop     rdi
0x18001f0f6  retn
```
