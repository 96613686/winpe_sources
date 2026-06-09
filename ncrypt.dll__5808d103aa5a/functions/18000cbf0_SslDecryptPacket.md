# SslDecryptPacket

- ea: `0x18000cbf0`
- end: `0x18000d026`
- name: `SslDecryptPacket`
- size: `1078`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000cbf0`
- `0x18000d02c`
- `0x180020010`

## string_xrefs

- `0x18000cc4b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000cceb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslDecryptPacket(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // r8d

  if ( !a1 || *(_DWORD *)a1 < 0x1B0u || *(_DWORD *)(a1 + 4) != 1145324609 || *(_DWORD *)(a1 + 12) )
  {
    v3 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        0);
    return v3;
  }
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
  {
    v3 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        8);
    return v3;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 80))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
  if ( (v3 & 0x80000000) == 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v5,
      (unsigned int)"Status",
      v3,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      29);
  if ( (v3 & 0x1FFF0000) == 0x90000 || (v3 & 0x1FFF0000) == 0x100000 )
    return v3;
  if ( v3 > 0xC000007B )
  {
    if ( v3 <= 0xC0000135 )
    {
      if ( v3 == -1073741515 )
        return 2148073502LL;
      if ( v3 == -1073741637 )
        return 2148073513LL;
      if ( v3 != -1073741670 )
      {
        if ( v3 != -1073741595 )
          return v3;
        return 2148073517LL;
      }
      return 2148073486LL;
    }
    if ( v3 != -1073741502 && v3 != -1073741511 )
    {
      if ( v3 != -1073700864 )
        return v3;
      return 2148073478LL;
    }
    return 2148073501LL;
  }
  if ( v3 == -1073741701 )
    return 2148073501LL;
  if ( v3 == -1073741816 )
    return 2148073510LL;
  if ( v3 > 0xC0000008 )
  {
    if ( v3 == -1073741811 )
      return 2148073511LL;
    if ( v3 != -1073741801 )
    {
      if ( v3 != -1073741789 )
        return v3;
      return 2148073512LL;
    }
    return 2148073486LL;
  }
  if ( v3 == -2147023680 )
    return 2147943616LL;
  if ( v3 == -2147023673 )
    return 2147943623LL;
  if ( v3 != -2147023496 )
    return v3;
  return 2147943800LL;
}

```

## disassembly

```asm
0x18000cbf0  push    rbx
0x18000cbf2  sub     rsp, 50h
0x18000cbf6  mov     rax, rcx
0x18000cbf9  test    rcx, rcx
0x18000cbfc  jz      short loc_18000CC19
0x18000cbfe  cmp     dword ptr [rcx], 1B0h
0x18000cc04  jb      short loc_18000CC19
0x18000cc06  cmp     dword ptr [rcx+4], 44444441h
0x18000cc0d  jnz     short loc_18000CC19
0x18000cc0f  cmp     dword ptr [rcx+0Ch], 0
0x18000cc13  jz      loc_18000CDC9
0x18000cc19  mov     ebx, 80090026h
0x18000cc1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc25  lea     rax, WPP_GLOBAL_Control
0x18000cc2c  cmp     rcx, rax
0x18000cc2f  jz      def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cc35  test    byte ptr [rcx+1Ch], 1
0x18000cc39  jz      def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cc3f  mov     dword ptr [rsp+58h+var_28], 400h
0x18000cc47  mov     rcx, [rcx+10h]
0x18000cc4b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cc52  mov     [rsp+58h+var_30], rax
0x18000cc57  lea     r9, aStatus; "Status"
0x18000cc5e  mov     dword ptr [rsp+58h+var_38], 80090026h
0x18000cc66  call    WPP_SF_sDsd
0x18000cc6b  jmp     short def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cc6d  mov     ecx, [rsp+58h+arg_40]
0x18000cc74  mov     rdx, [rdx+10h]
0x18000cc78  mov     [rsp+58h+var_18], ecx
0x18000cc7c  mov     rcx, [rsp+58h+arg_38]
0x18000cc84  mov     [rsp+58h+var_20], rcx
0x18000cc89  mov     rcx, [rsp+58h+arg_30]
0x18000cc91  mov     [rsp+58h+var_28], rcx
0x18000cc96  mov     ecx, [rsp+58h+arg_28]
0x18000cc9d  mov     dword ptr [rsp+58h+var_30], ecx
0x18000cca1  mov     rcx, [rsp+58h+arg_20]
0x18000cca9  mov     [rsp+58h+var_38], rcx
0x18000ccae  mov     rcx, [rax+1A8h]
0x18000ccb5  mov     rax, [rax+50h]
0x18000ccb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccbe  mov     ebx, eax
0x18000ccc0  test    eax, eax
0x18000ccc2  js      short loc_18000CCCE
0x18000ccc4  xor     ebx, ebx
0x18000ccc6  mov     eax, ebx; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ccc8  add     rsp, 50h
0x18000cccc  pop     rbx
0x18000cccd  retn
0x18000ccce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccd5  lea     rax, WPP_GLOBAL_Control
0x18000ccdc  cmp     rcx, rax
0x18000ccdf  jz      short loc_18000CD0F
0x18000cce1  test    byte ptr [rcx+1Ch], 1
0x18000cce5  jz      short loc_18000CD0F
0x18000cce7  mov     rcx, [rcx+10h]
0x18000cceb  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ccf2  mov     dword ptr [rsp+58h+var_28], 41Dh
0x18000ccfa  lea     r9, aStatus; "Status"
0x18000cd01  mov     [rsp+58h+var_30], rax
0x18000cd06  mov     dword ptr [rsp+58h+var_38], ebx
0x18000cd0a  call    WPP_SF_sDsd
0x18000cd0f  mov     eax, ebx
0x18000cd11  and     eax, 1FFF0000h
0x18000cd16  cmp     eax, 90000h
0x18000cd1b  jz      short def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cd1d  cmp     eax, 100000h
0x18000cd22  jz      short def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cd24  test    ebx, ebx
0x18000cd26  jz      short loc_18000CCC4
0x18000cd28  cmp     ebx, 216h
0x18000cd2e  ja      short loc_18000CD68
0x18000cd30  jz      loc_18000CEC6
0x18000cd36  lea     eax, [rbx-2]; switch 182 cases
0x18000cd39  cmp     eax, 0B5h
0x18000cd3e  ja      short def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cd40  lea     rdx, __ImageBase
0x18000cd47  movzx   eax, ds:(byte_18000CF70 - 180000000h)[rdx+rax]
0x18000cd4f  mov     ecx, ds:(jpt_18000CD59 - 180000000h)[rdx+rax*4]
0x18000cd56  add     rcx, rdx
0x18000cd59  jmp     rcx; switch jump
0x18000cd5b  mov     ebx, 80090027h; jumptable 000000018000CD59 case 87
0x18000cd60  mov     eax, ebx
0x18000cd62  add     rsp, 50h
0x18000cd66  pop     rbx
0x18000cd67  retn
0x18000cd68  cmp     ebx, 0C000007Bh
0x18000cd6e  ja      loc_18000CE13
0x18000cd74  jz      loc_18000CF07
0x18000cd7a  cmp     ebx, 0C0000008h
0x18000cd80  jz      loc_18000CE78
0x18000cd86  ja      loc_18000CF14
0x18000cd8c  cmp     ebx, 800704C0h
0x18000cd92  jz      loc_18000CE6B
0x18000cd98  cmp     ebx, 54Fh
0x18000cd9e  jz      loc_18000CED3
0x18000cda4  cmp     ebx, 800704C7h
0x18000cdaa  jz      loc_18000CEE0
0x18000cdb0  cmp     ebx, 80070578h
0x18000cdb6  jnz     def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cdbc  mov     ebx, 80070578h
0x18000cdc1  mov     eax, ebx
0x18000cdc3  add     rsp, 50h
0x18000cdc7  pop     rbx
0x18000cdc8  retn
0x18000cdc9  test    rdx, rdx
0x18000cdcc  jz      short loc_18000CDE0
0x18000cdce  cmp     dword ptr [rdx], 20h ; ' '
0x18000cdd1  jb      short loc_18000CDE0
0x18000cdd3  cmp     dword ptr [rdx+4], 44444442h
0x18000cdda  jz      loc_18000CC6D
0x18000cde0  mov     ebx, 80090026h
0x18000cde5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdec  lea     rax, WPP_GLOBAL_Control
0x18000cdf3  cmp     rcx, rax
0x18000cdf6  jz      def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cdfc  test    byte ptr [rcx+1Ch], 1
0x18000ce00  jz      def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ce06  mov     dword ptr [rsp+58h+var_28], 408h
0x18000ce0e  jmp     loc_18000CC47
0x18000ce13  cmp     ebx, 0C0000135h
0x18000ce19  ja      short loc_18000CE3A
0x18000ce1b  jz      loc_18000CEFA
0x18000ce21  cmp     ebx, 0C00000BBh
0x18000ce27  jnz     loc_18000CF39
0x18000ce2d  mov     ebx, 80090029h
0x18000ce32  mov     eax, ebx
0x18000ce34  add     rsp, 50h
0x18000ce38  pop     rbx
0x18000ce39  retn
0x18000ce3a  cmp     ebx, 0C0000142h
0x18000ce40  jz      loc_18000CF07
0x18000ce46  cmp     ebx, 0C0000139h
0x18000ce4c  jz      loc_18000CF07
0x18000ce52  cmp     ebx, 0C000A000h
0x18000ce58  jnz     def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ce5e  mov     ebx, 80090006h
0x18000ce63  mov     eax, ebx
0x18000ce65  add     rsp, 50h
0x18000ce69  pop     rbx
0x18000ce6a  retn
0x18000ce6b  mov     ebx, 800704C0h
0x18000ce70  mov     eax, ebx
0x18000ce72  add     rsp, 50h
0x18000ce76  pop     rbx
0x18000ce77  retn
0x18000ce78  mov     ebx, 80090026h
0x18000ce7d  mov     eax, ebx
0x18000ce7f  add     rsp, 50h
0x18000ce83  pop     rbx
0x18000ce84  retn
0x18000ce85  mov     ebx, 80090028h; jumptable 000000018000CD59 case 122
0x18000ce8a  mov     eax, ebx
0x18000ce8c  add     rsp, 50h
0x18000ce90  pop     rbx
0x18000ce91  retn
0x18000ce92  mov     ebx, 80090011h; jumptable 000000018000CD59 cases 2,3
0x18000ce97  mov     eax, ebx
0x18000ce99  add     rsp, 50h
0x18000ce9d  pop     rbx
0x18000ce9e  retn
0x18000ce9f  mov     ebx, 80090010h; jumptable 000000018000CD59 case 5
0x18000cea4  mov     eax, ebx
0x18000cea6  add     rsp, 50h
0x18000ceaa  pop     rbx
0x18000ceab  retn
0x18000ceac  mov     ebx, 80070070h; jumptable 000000018000CD59 case 112
0x18000ceb1  mov     eax, ebx
0x18000ceb3  add     rsp, 50h
0x18000ceb7  pop     rbx
0x18000ceb8  retn
0x18000ceb9  mov     ebx, 8009000Fh; jumptable 000000018000CD59 case 183
0x18000cebe  mov     eax, ebx
0x18000cec0  add     rsp, 50h
0x18000cec4  pop     rbx
0x18000cec5  retn
0x18000cec6  mov     ebx, 80070216h
0x18000cecb  mov     eax, ebx
0x18000cecd  add     rsp, 50h
0x18000ced1  pop     rbx
0x18000ced2  retn
0x18000ced3  mov     ebx, 8009002Dh
0x18000ced8  mov     eax, ebx
0x18000ceda  add     rsp, 50h
0x18000cede  pop     rbx
0x18000cedf  retn
0x18000cee0  mov     ebx, 800704C7h
0x18000cee5  mov     eax, ebx
0x18000cee7  add     rsp, 50h
0x18000ceeb  pop     rbx
0x18000ceec  retn
0x18000ceed  mov     ebx, 8009000Eh; jumptable 000000018000CD59 cases 8,14
0x18000cef2  mov     eax, ebx
0x18000cef4  add     rsp, 50h
0x18000cef8  pop     rbx
0x18000cef9  retn
0x18000cefa  mov     ebx, 8009001Eh
0x18000ceff  mov     eax, ebx
0x18000cf01  add     rsp, 50h
0x18000cf05  pop     rbx
0x18000cf06  retn
0x18000cf07  mov     ebx, 8009001Dh
0x18000cf0c  mov     eax, ebx
0x18000cf0e  add     rsp, 50h
0x18000cf12  pop     rbx
0x18000cf13  retn
0x18000cf14  cmp     ebx, 0C000000Dh
0x18000cf1a  jz      loc_18000CD5B; jumptable 000000018000CD59 case 87
0x18000cf20  cmp     ebx, 0C0000017h
0x18000cf26  jz      short loc_18000CEED; jumptable 000000018000CD59 cases 8,14
0x18000cf28  cmp     ebx, 0C0000023h
0x18000cf2e  jnz     def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cf34  jmp     loc_18000CE85; jumptable 000000018000CD59 case 122
0x18000cf39  cmp     ebx, 0C000009Ah
0x18000cf3f  jz      short loc_18000CEED; jumptable 000000018000CD59 cases 8,14
0x18000cf41  cmp     ebx, 0C00000E5h
0x18000cf47  jnz     def_18000CD59; jumptable 000000018000CD59 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000cf4d  jmp     short loc_18000CED3
```
