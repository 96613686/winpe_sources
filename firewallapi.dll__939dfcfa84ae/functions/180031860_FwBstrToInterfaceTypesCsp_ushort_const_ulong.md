# FwBstrToInterfaceTypesCsp(ushort const *,ulong *)

- ea: `0x180031860`
- end: `0x1800319fa`
- name: `?FwBstrToInterfaceTypesCsp@@YAJPEBGPEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x180031860`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800318ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800318ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031929`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003198c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031929`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18003198c`
- `fwbase!FwBaseFree` at `0x1800319c4`
- `fwbase!FwBaseFree` at `0x1800319c4`
- `fwbase!FwStringCopy` at `0x1800318ca`
- `fwbase!FwStringCopy` at `0x1800318ca`
- `FWPolicyIOMgr!FwParseInterfaceTypeCsp` at `0x18003196c`
- `FWPolicyIOMgr!FwParseInterfaceTypeCsp` at `0x18003196c`

## pseudocode

```c
__int64 __fastcall FwBstrToInterfaceTypesCsp(const unsigned __int16 *a1, unsigned int *a2)
{
  int v4; // ebx
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // rax
  wchar_t *String; // [rsp+20h] [rbp-28h] BYREF
  wchar_t *Context; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-18h] BYREF

  String = 0;
  Context = 0;
  v11 = 0;
  *a2 = 0;
  if ( a1 && *a1 && (unsigned int)_o__wcsicmp(a1, L"All") )
  {
    v4 = FwStringCopy(a1, &String);
    if ( v4 >= 0 )
    {
      v7 = wcstok_s(String, L",", &Context);
      if ( v7 )
      {
        while ( 1 )
        {
          v4 = FwParseInterfaceTypeCsp(v7, &v11);
          if ( v4 < 0 )
            break;
          v7 = wcstok_s(0, L",", &Context);
          if ( !v7 )
            goto LABEL_20;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 14;
          goto LABEL_8;
        }
      }
      else
      {
        v4 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 13;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 12;
LABEL_8:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v4);
      }
    }
  }
  else
  {
    v4 = 0;
  }
LABEL_20:
  FwBaseFree(String);
  if ( v4 >= 0 )
    *a2 = v11;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180031860  mov     r11, rsp
0x180031863  mov     [r11+18h], rbx
0x180031867  mov     [r11+20h], rsi
0x18003186b  push    rdi
0x18003186c  sub     rsp, 40h
0x180031870  mov     rax, cs:__security_cookie
0x180031877  xor     rax, rsp
0x18003187a  mov     [rsp+48h+var_10], rax
0x18003187f  xor     esi, esi
0x180031881  mov     rdi, rdx
0x180031884  mov     [r11-28h], rsi
0x180031888  mov     rbx, rcx
0x18003188b  mov     [r11-20h], rsi
0x18003188f  mov     [rsp+48h+var_18], esi
0x180031893  mov     [rdx], esi
0x180031895  test    rcx, rcx
0x180031898  jz      loc_1800319BD
0x18003189e  cmp     [rcx], si
0x1800318a1  jz      loc_1800319BD
0x1800318a7  lea     rdx, aAll; "All"
0x1800318ae  call    cs:__imp__o__wcsicmp
0x1800318b5  nop     dword ptr [rax+rax+00h]
0x1800318ba  test    eax, eax
0x1800318bc  jz      loc_1800319BD
0x1800318c2  lea     rdx, [rsp+48h+String]
0x1800318c7  mov     rcx, rbx
0x1800318ca  call    cs:__imp_FwStringCopy
0x1800318d1  nop     dword ptr [rax+rax+00h]
0x1800318d6  mov     ebx, eax
0x1800318d8  test    eax, eax
0x1800318da  jns     short loc_180031918
0x1800318dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318e3  lea     rax, WPP_GLOBAL_Control
0x1800318ea  cmp     rcx, rax
0x1800318ed  jz      loc_1800319BF
0x1800318f3  test    byte ptr [rcx+1Ch], 1
0x1800318f7  jz      loc_1800319BF
0x1800318fd  lea     edx, [rsi+0Ch]
0x180031900  mov     rcx, [rcx+10h]
0x180031904  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18003190b  mov     r9d, ebx
0x18003190e  call    WPP_SF_d
0x180031913  jmp     loc_1800319BF
0x180031918  mov     rcx, [rsp+48h+String]; String
0x18003191d  lea     r8, [rsp+48h+Context]; Context
0x180031922  lea     rdx, Delimiter; ","
0x180031929  call    cs:__imp_wcstok_s
0x180031930  nop     dword ptr [rax+rax+00h]
0x180031935  test    rax, rax
0x180031938  jnz     short loc_180031964
0x18003193a  mov     ebx, 80070057h
0x18003193f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031946  lea     rax, WPP_GLOBAL_Control
0x18003194d  cmp     rcx, rax
0x180031950  jz      short loc_1800319BF
0x180031952  test    byte ptr [rcx+1Ch], 1
0x180031956  jz      short loc_1800319BF
0x180031958  mov     edx, 0Dh
0x18003195d  jmp     short loc_180031900
0x18003195f  test    rax, rax
0x180031962  jz      short loc_1800319BF
0x180031964  lea     rdx, [rsp+48h+var_18]
0x180031969  mov     rcx, rax
0x18003196c  call    cs:__imp_?FwParseInterfaceTypeCsp@@YAJPEBGPEAK@Z; FwParseInterfaceTypeCsp(ushort const *,ulong *)
0x180031973  nop     dword ptr [rax+rax+00h]
0x180031978  mov     ebx, eax
0x18003197a  test    eax, eax
0x18003197c  js      short loc_18003199A
0x18003197e  lea     r8, [rsp+48h+Context]; Context
0x180031983  xor     ecx, ecx; String
0x180031985  lea     rdx, Delimiter; ","
0x18003198c  call    cs:__imp_wcstok_s
0x180031993  nop     dword ptr [rax+rax+00h]
0x180031998  jmp     short loc_18003195F
0x18003199a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319a1  lea     rax, WPP_GLOBAL_Control
0x1800319a8  cmp     rcx, rax
0x1800319ab  jz      short loc_1800319BF
0x1800319ad  test    byte ptr [rcx+1Ch], 1
0x1800319b1  jz      short loc_1800319BF
0x1800319b3  mov     edx, 0Eh
0x1800319b8  jmp     loc_180031900
0x1800319bd  mov     ebx, esi
0x1800319bf  mov     rcx, [rsp+48h+String]
0x1800319c4  call    cs:__imp_FwBaseFree
0x1800319cb  nop     dword ptr [rax+rax+00h]
0x1800319d0  test    ebx, ebx
0x1800319d2  js      short loc_1800319DA
0x1800319d4  mov     eax, [rsp+48h+var_18]
0x1800319d8  mov     [rdi], eax
0x1800319da  mov     eax, ebx
0x1800319dc  mov     rcx, [rsp+48h+var_10]
0x1800319e1  xor     rcx, rsp; StackCookie
0x1800319e4  call    __security_check_cookie
0x1800319e9  mov     rbx, [rsp+48h+arg_10]
0x1800319ee  mov     rsi, [rsp+48h+arg_18]
0x1800319f3  add     rsp, 40h
0x1800319f7  pop     rdi
0x1800319f8  retn
```
