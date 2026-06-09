# FwLoadIndirectString

- ea: `0x180002e70`
- end: `0x1800030a8`
- name: `FwLoadIndirectString`
- size: `568`
- prototype: `__int64 __fastcall(PCWSTR pszSource)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800037f0`

## callees

- `0x180001eb0`
- `0x180002e70`
- `0x1800045f0`
- `0x1800047e0`
- `0x1800130bc`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002ede`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002ede`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180003031`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180003031`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000304e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000304e`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180002f0d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180002f0d`

## string_xrefs

- `0x180002ed4`: `@FirewallAPI.dll,-`

## pseudocode

```c
__int64 __fastcall FwLoadIndirectString(PCWSTR pszSource, _QWORD *a2, int a3)
{
  int String; // ebx
  int v6; // eax
  __int64 v8; // rdx
  UINT v9; // eax
  wchar_t *EndPtr; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszOutBuf[512]; // [rsp+30h] [rbp-428h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, pszSource);
  EndPtr = 0;
  if ( !a2 || !pszSource )
  {
    String = -2147024809;
    goto LABEL_22;
  }
  *a2 = 0;
  if ( (unsigned int)_o__wcsnicmp(pszSource, L"@FirewallAPI.dll,-", 18)
    || !(unsigned int)_o_iswdigit(pszSource[18])
    || (v9 = wcstoul(pszSource + 18, &EndPtr, 10), v9 == -1)
    || *EndPtr
    || (String = FwLoadString(v9, a2), String < 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, pszSource);
    String = SHLoadIndirectString(pszSource, pszOutBuf, 0x200u, 0);
    if ( String < 0 )
      String = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, pszSource);
    if ( String >= 0 )
    {
      v6 = FwStringCopy(pszOutBuf, a2);
      String = v6;
      if ( v6 >= 0 )
        goto LABEL_13;
      v8 = (unsigned int)v6;
LABEL_23:
      FwReportReturnError((int)"FwLoadIndirectString", v8, a3);
      goto LABEL_13;
    }
LABEL_22:
    v8 = (unsigned int)String;
    goto LABEL_23;
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, pszSource);
  if ( String < 0 )
    return (unsigned int)FwReportReturnError((int)"FwLoadIndirectString", (unsigned int)String, a3);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180002e70  mov     [rsp+arg_10], rbx
0x180002e75  mov     [rsp+arg_18], rbp
0x180002e7a  push    rsi
0x180002e7b  push    rdi
0x180002e7c  push    r12
0x180002e7e  sub     rsp, 440h
0x180002e85  mov     rax, cs:__security_cookie
0x180002e8c  xor     rax, rsp
0x180002e8f  mov     [rsp+458h+var_28], rax
0x180002e97  mov     rsi, rdx
0x180002e9a  mov     rdi, rcx
0x180002e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ea4  lea     r12, WPP_GLOBAL_Control
0x180002eab  cmp     rcx, r12
0x180002eae  jnz     loc_180002FB2
0x180002eb4  xor     ebp, ebp
0x180002eb6  mov     [rsp+458h+EndPtr], rbp
0x180002ebb  test    rsi, rsi
0x180002ebe  jz      loc_180002FD9
0x180002ec4  test    rdi, rdi
0x180002ec7  jz      loc_180002FD9
0x180002ecd  lea     r8d, [rbp+12h]
0x180002ed1  mov     [rsi], rbp
0x180002ed4  lea     rdx, aFirewallapiDll_3; "@FirewallAPI.dll,-"
0x180002edb  mov     rcx, rdi
0x180002ede  call    cs:__imp__o__wcsnicmp
0x180002ee4  test    eax, eax
0x180002ee6  jz      loc_18000302D
0x180002eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ef3  cmp     rcx, r12
0x180002ef6  jnz     loc_180003006
0x180002efc  xor     r9d, r9d; ppvReserved
0x180002eff  lea     rdx, [rsp+458h+pszOutBuf]; pszOutBuf
0x180002f04  mov     r8d, 200h; cchOutBuf
0x180002f0a  mov     rcx, rdi; pszSource
0x180002f0d  call    cs:__imp_SHLoadIndirectString
0x180002f13  mov     ebx, eax
0x180002f15  mov     eax, 80004005h
0x180002f1a  test    ebx, ebx
0x180002f1c  cmovs   ebx, eax
0x180002f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f26  cmp     rcx, r12
0x180002f29  jz      short loc_180002F35
0x180002f2b  test    byte ptr [rcx+1Ch], 4
0x180002f2f  jnz     loc_180003084
0x180002f35  test    ebx, ebx
0x180002f37  js      loc_180002FDE
0x180002f3d  mov     rdx, rsi
0x180002f40  lea     rcx, [rsp+458h+pszOutBuf]; Src
0x180002f45  call    FwStringCopy
0x180002f4a  mov     ebx, eax
0x180002f4c  test    eax, eax
0x180002f4e  js      loc_1800030A1
0x180002f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f5b  cmp     rcx, r12
0x180002f5e  jnz     short loc_180002F92
0x180002f60  test    ebx, ebx
0x180002f62  js      loc_180002FF1
0x180002f68  mov     eax, ebx
0x180002f6a  mov     rcx, [rsp+458h+var_28]
0x180002f72  xor     rcx, rsp; StackCookie
0x180002f75  call    __security_check_cookie
0x180002f7a  lea     r11, [rsp+458h+var_18]
0x180002f82  mov     rbx, [r11+30h]
0x180002f86  mov     rbp, [r11+38h]
0x180002f8a  mov     rsp, r11
0x180002f8d  pop     r12
0x180002f8f  pop     rdi
0x180002f90  pop     rsi
0x180002f91  retn
0x180002f92  test    byte ptr [rcx+1Ch], 4
0x180002f96  jz      short loc_180002F60
0x180002f98  mov     rcx, [rcx+10h]
0x180002f9c  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180002fa3  mov     edx, 16h
0x180002fa8  mov     r9, rdi
0x180002fab  call    WPP_SF_S
0x180002fb0  jmp     short loc_180002F60
0x180002fb2  test    byte ptr [rcx+1Ch], 4
0x180002fb6  jz      loc_180002EB4
0x180002fbc  mov     rcx, [rcx+10h]
0x180002fc0  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180002fc7  mov     edx, 13h
0x180002fcc  mov     r9, rdi
0x180002fcf  call    WPP_SF_S
0x180002fd4  jmp     loc_180002EB4
0x180002fd9  mov     ebx, 80070057h
0x180002fde  mov     edx, ebx
0x180002fe0  lea     rcx, aFwloadindirect_0; "FwLoadIndirectString"
0x180002fe7  call    FwReportReturnError
0x180002fec  jmp     loc_180002F54
0x180002ff1  mov     edx, ebx
0x180002ff3  lea     rcx, aFwloadindirect_0; "FwLoadIndirectString"
0x180002ffa  call    FwReportReturnError
0x180002fff  mov     ebx, eax
0x180003001  jmp     loc_180002F68
0x180003006  test    byte ptr [rcx+1Ch], 4
0x18000300a  jz      loc_180002EFC
0x180003010  mov     rcx, [rcx+10h]
0x180003014  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x18000301b  mov     edx, 14h
0x180003020  mov     r9, rdi
0x180003023  call    WPP_SF_S
0x180003028  jmp     loc_180002EFC
0x18000302d  movzx   ecx, word ptr [rdi+24h]
0x180003031  call    cs:__imp__o_iswdigit
0x180003037  test    eax, eax
0x180003039  jz      loc_180002EEC
0x18000303f  mov     r8d, 0Ah; Radix
0x180003045  lea     rdx, [rsp+458h+EndPtr]; EndPtr
0x18000304a  lea     rcx, [rdi+24h]; String
0x18000304e  call    cs:__imp_wcstoul
0x180003054  cmp     eax, 0FFFFFFFFh
0x180003057  jz      loc_180002EEC
0x18000305d  mov     rcx, [rsp+458h+EndPtr]
0x180003062  cmp     [rcx], bp
0x180003065  jnz     loc_180002EEC
0x18000306b  mov     rdx, rsi
0x18000306e  mov     ecx, eax; uID
0x180003070  call    FwLoadString
0x180003075  mov     ebx, eax
0x180003077  test    eax, eax
0x180003079  jns     loc_180002F54
0x18000307f  jmp     loc_180002EEC
0x180003084  mov     rcx, [rcx+10h]
0x180003088  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x18000308f  mov     edx, 15h
0x180003094  mov     r9, rdi
0x180003097  call    WPP_SF_S
0x18000309c  jmp     loc_180002F35
0x1800030a1  mov     edx, eax
0x1800030a3  jmp     loc_180002FE0
```
