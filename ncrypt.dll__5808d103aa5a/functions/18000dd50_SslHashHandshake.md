# SslHashHandshake

- ea: `0x18000dd50`
- end: `0x18000e11a`
- name: `SslHashHandshake`
- size: `970`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d02c`
- `0x18000dd50`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000dd9f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000dde2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000de3c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslHashHandshake(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  __int64 result; // rax
  int v5; // eax

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
        204);
    return v3;
  }
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324611 )
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2516);
    return 2148073510LL;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 160))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
  v3 = v5;
  if ( v5 >= 0 )
    return 0;
  DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2532);
  if ( (v3 & 0x1FFF0000) == 0x90000 || (v3 & 0x1FFF0000) == 0x100000 )
    return v3;
  if ( !v3 )
    return 0;
  if ( v3 > 0x216 )
  {
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
        if ( v3 == -1073700864 )
          return 2148073478LL;
        return v3;
      }
    }
    else if ( v3 != -1073741701 )
    {
      if ( v3 == -1073741816 )
        return 2148073510LL;
      if ( v3 <= 0xC0000008 )
      {
        if ( v3 == -2147023680 )
          return 2147943616LL;
        if ( v3 != 1359 )
        {
          if ( v3 == -2147023673 )
            return 2147943623LL;
          if ( v3 == -2147023496 )
            return 2147943800LL;
          return v3;
        }
        return 2148073517LL;
      }
      if ( v3 == -1073741811 )
        return 2148073511LL;
      if ( v3 != -1073741801 )
      {
        if ( v3 == -1073741789 )
          return 2148073512LL;
        return v3;
      }
      return 2148073486LL;
    }
    return 2148073501LL;
  }
  if ( v3 == 534 )
    return 2147942934LL;
  switch ( v3 )
  {
    case 2u:
    case 3u:
      result = 2148073489LL;
      break;
    case 5u:
      result = 2148073488LL;
      break;
    case 8u:
    case 0xEu:
      return 2148073486LL;
    case 0x57u:
      return 2148073511LL;
    case 0x70u:
      result = 2147942512LL;
      break;
    case 0x7Au:
      return 2148073512LL;
    case 0xB7u:
      result = 2148073487LL;
      break;
    default:
      return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000dd50  push    rbx
0x18000dd52  sub     rsp, 40h
0x18000dd56  mov     rax, rcx
0x18000dd59  test    rcx, rcx
0x18000dd5c  jz      short loc_18000DD75
0x18000dd5e  cmp     dword ptr [rcx], 1B0h
0x18000dd64  jb      short loc_18000DD75
0x18000dd66  cmp     dword ptr [rcx+4], 44444441h
0x18000dd6d  jnz     short loc_18000DD75
0x18000dd6f  cmp     dword ptr [rcx+0Ch], 0
0x18000dd73  jz      short loc_18000DDC9
0x18000dd75  mov     ebx, 80090026h
0x18000dd7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd81  lea     rax, WPP_GLOBAL_Control
0x18000dd88  cmp     rcx, rax
0x18000dd8b  jz      def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000dd91  test    byte ptr [rcx+1Ch], 1
0x18000dd95  jz      def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000dd9b  mov     rcx, [rcx+10h]
0x18000dd9f  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dda6  mov     [rsp+48h+var_18], 9CCh
0x18000ddae  lea     r9, aStatus; "Status"
0x18000ddb5  mov     [rsp+48h+var_20], rax
0x18000ddba  mov     [rsp+48h+var_28], 80090026h
0x18000ddc2  call    WPP_SF_sDsd
0x18000ddc7  jmp     short def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000ddc9  test    rdx, rdx
0x18000ddcc  jz      short loc_18000DDDC
0x18000ddce  cmp     dword ptr [rdx], 20h ; ' '
0x18000ddd1  jb      short loc_18000DDDC
0x18000ddd3  cmp     dword ptr [rdx+4], 44444443h
0x18000ddda  jz      short loc_18000DE07
0x18000dddc  mov     r9d, 9D4h
0x18000dde2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dde9  lea     rdx, aStatus; "Status"
0x18000ddf0  mov     ecx, 80090026h
0x18000ddf5  mov     ebx, 80090026h
0x18000ddfa  call    DebugTraceError
0x18000ddff  mov     eax, ebx
0x18000de01  add     rsp, 40h
0x18000de05  pop     rbx
0x18000de06  retn
0x18000de07  mov     ecx, [rsp+48h+arg_20]
0x18000de0b  mov     rdx, [rdx+10h]
0x18000de0f  mov     [rsp+48h+var_28], ecx
0x18000de13  mov     rcx, [rax+1A8h]
0x18000de1a  mov     rax, [rax+0A0h]
0x18000de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de26  mov     ebx, eax
0x18000de28  test    eax, eax
0x18000de2a  js      short loc_18000DE36
0x18000de2c  xor     ebx, ebx
0x18000de2e  mov     eax, ebx; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000de30  add     rsp, 40h
0x18000de34  pop     rbx
0x18000de35  retn
0x18000de36  mov     r9d, 9E4h
0x18000de3c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000de43  lea     rdx, aStatus; "Status"
0x18000de4a  mov     ecx, ebx
0x18000de4c  call    DebugTraceError
0x18000de51  mov     eax, ebx
0x18000de53  and     eax, 1FFF0000h
0x18000de58  cmp     eax, 90000h
0x18000de5d  jz      short def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000de5f  cmp     eax, 100000h
0x18000de64  jz      short def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000de66  test    ebx, ebx
0x18000de68  jz      short loc_18000DE2C
0x18000de6a  cmp     ebx, 216h
0x18000de70  ja      short loc_18000DEAA
0x18000de72  jz      loc_18000DFBA
0x18000de78  lea     eax, [rbx-2]; switch 182 cases
0x18000de7b  cmp     eax, 0B5h
0x18000de80  ja      short def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000de82  lea     rdx, __ImageBase
0x18000de89  movzx   eax, ds:(byte_18000E064 - 180000000h)[rdx+rax]
0x18000de91  mov     ecx, ds:(jpt_18000DE9B - 180000000h)[rdx+rax*4]
0x18000de98  add     rcx, rdx
0x18000de9b  jmp     rcx; switch jump
0x18000de9d  mov     ebx, 80090027h; jumptable 000000018000DE9B case 87
0x18000dea2  mov     eax, ebx
0x18000dea4  add     rsp, 40h
0x18000dea8  pop     rbx
0x18000dea9  retn
0x18000deaa  cmp     ebx, 0C000007Bh
0x18000deb0  ja      short loc_18000DF07
0x18000deb2  jz      loc_18000DFFB
0x18000deb8  cmp     ebx, 0C0000008h
0x18000debe  jz      loc_18000DF6C
0x18000dec4  ja      loc_18000E008
0x18000deca  cmp     ebx, 800704C0h
0x18000ded0  jz      loc_18000DF5F
0x18000ded6  cmp     ebx, 54Fh
0x18000dedc  jz      loc_18000DFC7
0x18000dee2  cmp     ebx, 800704C7h
0x18000dee8  jz      loc_18000DFD4
0x18000deee  cmp     ebx, 80070578h
0x18000def4  jnz     def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000defa  mov     ebx, 80070578h
0x18000deff  mov     eax, ebx
0x18000df01  add     rsp, 40h
0x18000df05  pop     rbx
0x18000df06  retn
0x18000df07  cmp     ebx, 0C0000135h
0x18000df0d  ja      short loc_18000DF2E
0x18000df0f  jz      loc_18000DFEE
0x18000df15  cmp     ebx, 0C00000BBh
0x18000df1b  jnz     loc_18000E02D
0x18000df21  mov     ebx, 80090029h
0x18000df26  mov     eax, ebx
0x18000df28  add     rsp, 40h
0x18000df2c  pop     rbx
0x18000df2d  retn
0x18000df2e  cmp     ebx, 0C0000142h
0x18000df34  jz      loc_18000DFFB
0x18000df3a  cmp     ebx, 0C0000139h
0x18000df40  jz      loc_18000DFFB
0x18000df46  cmp     ebx, 0C000A000h
0x18000df4c  jnz     def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000df52  mov     ebx, 80090006h
0x18000df57  mov     eax, ebx
0x18000df59  add     rsp, 40h
0x18000df5d  pop     rbx
0x18000df5e  retn
0x18000df5f  mov     ebx, 800704C0h
0x18000df64  mov     eax, ebx
0x18000df66  add     rsp, 40h
0x18000df6a  pop     rbx
0x18000df6b  retn
0x18000df6c  mov     ebx, 80090026h
0x18000df71  mov     eax, ebx
0x18000df73  add     rsp, 40h
0x18000df77  pop     rbx
0x18000df78  retn
0x18000df79  mov     ebx, 80090028h; jumptable 000000018000DE9B case 122
0x18000df7e  mov     eax, ebx
0x18000df80  add     rsp, 40h
0x18000df84  pop     rbx
0x18000df85  retn
0x18000df86  mov     ebx, 80090011h; jumptable 000000018000DE9B cases 2,3
0x18000df8b  mov     eax, ebx
0x18000df8d  add     rsp, 40h
0x18000df91  pop     rbx
0x18000df92  retn
0x18000df93  mov     ebx, 80090010h; jumptable 000000018000DE9B case 5
0x18000df98  mov     eax, ebx
0x18000df9a  add     rsp, 40h
0x18000df9e  pop     rbx
0x18000df9f  retn
0x18000dfa0  mov     ebx, 80070070h; jumptable 000000018000DE9B case 112
0x18000dfa5  mov     eax, ebx
0x18000dfa7  add     rsp, 40h
0x18000dfab  pop     rbx
0x18000dfac  retn
0x18000dfad  mov     ebx, 8009000Fh; jumptable 000000018000DE9B case 183
0x18000dfb2  mov     eax, ebx
0x18000dfb4  add     rsp, 40h
0x18000dfb8  pop     rbx
0x18000dfb9  retn
0x18000dfba  mov     ebx, 80070216h
0x18000dfbf  mov     eax, ebx
0x18000dfc1  add     rsp, 40h
0x18000dfc5  pop     rbx
0x18000dfc6  retn
0x18000dfc7  mov     ebx, 8009002Dh
0x18000dfcc  mov     eax, ebx
0x18000dfce  add     rsp, 40h
0x18000dfd2  pop     rbx
0x18000dfd3  retn
0x18000dfd4  mov     ebx, 800704C7h
0x18000dfd9  mov     eax, ebx
0x18000dfdb  add     rsp, 40h
0x18000dfdf  pop     rbx
0x18000dfe0  retn
0x18000dfe1  mov     ebx, 8009000Eh; jumptable 000000018000DE9B cases 8,14
0x18000dfe6  mov     eax, ebx
0x18000dfe8  add     rsp, 40h
0x18000dfec  pop     rbx
0x18000dfed  retn
0x18000dfee  mov     ebx, 8009001Eh
0x18000dff3  mov     eax, ebx
0x18000dff5  add     rsp, 40h
0x18000dff9  pop     rbx
0x18000dffa  retn
0x18000dffb  mov     ebx, 8009001Dh
0x18000e000  mov     eax, ebx
0x18000e002  add     rsp, 40h
0x18000e006  pop     rbx
0x18000e007  retn
0x18000e008  cmp     ebx, 0C000000Dh
0x18000e00e  jz      loc_18000DE9D; jumptable 000000018000DE9B case 87
0x18000e014  cmp     ebx, 0C0000017h
0x18000e01a  jz      short loc_18000DFE1; jumptable 000000018000DE9B cases 8,14
0x18000e01c  cmp     ebx, 0C0000023h
0x18000e022  jnz     def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e028  jmp     loc_18000DF79; jumptable 000000018000DE9B case 122
0x18000e02d  cmp     ebx, 0C000009Ah
0x18000e033  jz      short loc_18000DFE1; jumptable 000000018000DE9B cases 8,14
0x18000e035  cmp     ebx, 0C00000E5h
0x18000e03b  jnz     def_18000DE9B; jumptable 000000018000DE9B default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e041  jmp     short loc_18000DFC7
```
