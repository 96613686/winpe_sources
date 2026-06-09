# LauncherGetSystemPartitionFilePath(ushort const *,ushort *)

- ea: `0x1800077f8`
- end: `0x18000798d`
- name: `?LauncherGetSystemPartitionFilePath@@YAHPEBGPEAG@Z`
- size: `405`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005c98`
- `0x1800070ec`
- `0x180007e74`
- `0x180008488`

## callees

- `0x180005528`
- `0x1800077f8`
- `0x180007994`
- `0x18000886c`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fdd6`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000786a`
- `KERNEL32!GetLastError` at `0x18000792f`
- `KERNEL32!GetLastError` at `0x18000786a`
- `KERNEL32!GetLastError` at `0x18000792f`
- `KERNEL32!SetLastError` at `0x180007917`
- `KERNEL32!SetLastError` at `0x180007917`

## string_xrefs

- `0x180007890`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x1800078ea`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherGetSystemPartitionFilePath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // edi
  DWORD LastError; // eax
  DWORD v6; // ebx
  int v7; // eax
  int v8; // r8d
  int v9; // r9d
  const char *v10; // rcx
  char v12; // [rsp+30h] [rbp-258h]
  unsigned __int16 v13[264]; // [rsp+40h] [rbp-248h] BYREF

  v4 = 0;
  memset_0(v13, 0, 0x20Au);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  if ( (unsigned int)LauncherGetSystemPartitionPath(v13) )
  {
    v7 = StringCchPrintfW(a2, 0x105u, a1, v13);
    if ( v7 >= 0 )
    {
      v6 = 0;
      v4 = 1;
    }
    else
    {
      v6 = 1359;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          76,
          v7);
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        66,
        LastError);
  }
  SetLastError(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = GetLastError();
    v10 = "Success";
    if ( !v4 )
      v10 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v8, v9, 85, (__int64)v10, v12);
  }
  return v4;
}

```

## disassembly

```asm
0x1800077f8  push    rbx
0x1800077fa  push    rbp
0x1800077fb  push    rsi
0x1800077fc  push    rdi
0x1800077fd  sub     rsp, 268h
0x180007804  mov     rax, cs:__security_cookie
0x18000780b  xor     rax, rsp
0x18000780e  mov     [rsp+288h+var_38], rax
0x180007816  mov     rsi, rdx
0x180007819  mov     rbx, rcx
0x18000781c  xor     edx, edx; Val
0x18000781e  lea     rcx, [rsp+288h+var_248]; void *
0x180007823  xor     edi, edi
0x180007825  mov     r8d, 20Ah; Size
0x18000782b  call    memset_0
0x180007830  mov     rcx, cs:WPP_GLOBAL_Control
0x180007837  lea     rbp, WPP_GLOBAL_Control
0x18000783e  cmp     rcx, rbp
0x180007841  jz      short loc_18000785C
0x180007843  test    byte ptr [rcx+1Ch], 8
0x180007847  jz      short loc_18000785C
0x180007849  mov     rcx, [rcx+10h]
0x18000784d  lea     edx, [rdi+18h]
0x180007850  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180007857  call    WPP_SF_
0x18000785c  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180007861  call    ?LauncherGetSystemPartitionPath@@YAHPEAG@Z; LauncherGetSystemPartitionPath(ushort *)
0x180007866  test    eax, eax
0x180007868  jnz     short loc_1800078B6
0x18000786a  call    cs:__imp_GetLastError
0x180007870  mov     ebx, eax
0x180007872  mov     rcx, cs:WPP_GLOBAL_Control
0x180007879  cmp     rcx, rbp
0x18000787c  jz      loc_180007915
0x180007882  test    byte ptr [rcx+1Ch], 1
0x180007886  jz      loc_180007915
0x18000788c  mov     rcx, [rcx+10h]
0x180007890  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007897  mov     dword ptr [rsp+288h+var_260], eax
0x18000789b  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800078a2  mov     edx, 19h
0x1800078a7  mov     [rsp+288h+var_268], 142h
0x1800078af  call    WPP_SF_sdD
0x1800078b4  jmp     short loc_180007915
0x1800078b6  lea     r9, [rsp+288h+var_248]
0x1800078bb  mov     r8, rbx; unsigned __int16 *
0x1800078be  mov     edx, 105h; unsigned __int64
0x1800078c3  mov     rcx, rsi; unsigned __int16 *
0x1800078c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800078cb  test    eax, eax
0x1800078cd  jns     short loc_180007910
0x1800078cf  mov     ebx, 54Fh
0x1800078d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078db  cmp     rcx, rbp
0x1800078de  jz      short loc_180007915
0x1800078e0  test    byte ptr [rcx+1Ch], 1
0x1800078e4  jz      short loc_180007915
0x1800078e6  mov     rcx, [rcx+10h]
0x1800078ea  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800078f1  mov     dword ptr [rsp+288h+var_260], eax
0x1800078f5  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800078fc  mov     edx, 1Ah
0x180007901  mov     [rsp+288h+var_268], 14Ch
0x180007909  call    WPP_SF_sdD
0x18000790e  jmp     short loc_180007915
0x180007910  xor     ebx, ebx
0x180007912  lea     edi, [rbx+1]
0x180007915  mov     ecx, ebx; dwErrCode
0x180007917  call    cs:__imp_SetLastError
0x18000791d  mov     rax, cs:WPP_GLOBAL_Control
0x180007924  cmp     rax, rbp
0x180007927  jz      short loc_18000796F
0x180007929  test    byte ptr [rax+1Ch], 4
0x18000792d  jz      short loc_18000796F
0x18000792f  call    cs:__imp_GetLastError
0x180007935  lea     rdx, aFailure; "Failure"
0x18000793c  mov     dword ptr [rsp+288h+var_258], eax
0x180007940  test    edi, edi
0x180007942  lea     rcx, aSuccess; "Success"
0x180007949  cmovz   rcx, rdx
0x18000794d  mov     edx, 1Bh
0x180007952  mov     [rsp+288h+var_260], rcx
0x180007957  mov     rcx, cs:WPP_GLOBAL_Control
0x18000795e  mov     [rsp+288h+var_268], 155h
0x180007966  mov     rcx, [rcx+10h]
0x18000796a  call    WPP_SF_sdsd
0x18000796f  mov     eax, edi
0x180007971  mov     rcx, [rsp+288h+var_38]
0x180007979  xor     rcx, rsp; StackCookie
0x18000797c  call    __security_check_cookie
0x180007981  add     rsp, 268h
0x180007988  pop     rdi
0x180007989  pop     rsi
0x18000798a  pop     rbp
0x18000798b  pop     rbx
0x18000798c  retn
```
