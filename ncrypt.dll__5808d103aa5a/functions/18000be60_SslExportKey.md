# SslExportKey

- ea: `0x18000be60`
- end: `0x18000c25e`
- name: `SslExportKey`
- size: `1022`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000be60`
- `0x18000d02c`
- `0x180020010`

## string_xrefs

- `0x18000bef2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000bf72`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslExportKey(__int64 a1, __int64 a2, int a3)
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
        241);
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
        249);
    return v3;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 104))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
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
      11);
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
0x18000be60  push    rbx
0x18000be62  sub     rsp, 40h
0x18000be66  mov     rax, rcx
0x18000be69  test    rcx, rcx
0x18000be6c  jz      short loc_18000BE85
0x18000be6e  cmp     dword ptr [rcx], 1B0h
0x18000be74  jb      short loc_18000BE85
0x18000be76  cmp     dword ptr [rcx+4], 44444441h
0x18000be7d  jnz     short loc_18000BE85
0x18000be7f  cmp     dword ptr [rcx+0Ch], 0
0x18000be83  jz      short loc_18000BEB5
0x18000be85  mov     ebx, 80090026h
0x18000be8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be91  lea     rax, WPP_GLOBAL_Control
0x18000be98  cmp     rcx, rax
0x18000be9b  jz      def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bea1  test    byte ptr [rcx+1Ch], 1
0x18000bea5  jz      def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000beab  mov     [rsp+48h+var_18], 6F1h
0x18000beb3  jmp     short loc_18000BEEE
0x18000beb5  test    rdx, rdx
0x18000beb8  jz      short loc_18000BEC8
0x18000beba  cmp     dword ptr [rdx], 20h ; ' '
0x18000bebd  jb      short loc_18000BEC8
0x18000bebf  cmp     dword ptr [rdx+4], 44444442h
0x18000bec6  jz      short loc_18000BF14
0x18000bec8  mov     ebx, 80090026h
0x18000becd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bed4  lea     rax, WPP_GLOBAL_Control
0x18000bedb  cmp     rcx, rax
0x18000bede  jz      short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bee0  test    byte ptr [rcx+1Ch], 1
0x18000bee4  jz      short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bee6  mov     [rsp+48h+var_18], 6F9h
0x18000beee  mov     rcx, [rcx+10h]
0x18000bef2  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bef9  mov     [rsp+48h+var_20], rax
0x18000befe  lea     r9, aStatus; "Status"
0x18000bf05  mov     [rsp+48h+var_28], 80090026h
0x18000bf0d  call    WPP_SF_sDsd
0x18000bf12  jmp     short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bf14  mov     ecx, [rsp+48h+arg_30]
0x18000bf1b  mov     rdx, [rdx+10h]
0x18000bf1f  mov     [rsp+48h+var_18], ecx
0x18000bf23  mov     rcx, [rsp+48h+arg_28]
0x18000bf28  mov     [rsp+48h+var_20], rcx
0x18000bf2d  mov     ecx, [rsp+48h+arg_20]
0x18000bf31  mov     [rsp+48h+var_28], ecx
0x18000bf35  mov     rcx, [rax+1A8h]
0x18000bf3c  mov     rax, [rax+68h]
0x18000bf40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf45  mov     ebx, eax
0x18000bf47  test    eax, eax
0x18000bf49  js      short loc_18000BF55
0x18000bf4b  xor     ebx, ebx
0x18000bf4d  mov     eax, ebx; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bf4f  add     rsp, 40h
0x18000bf53  pop     rbx
0x18000bf54  retn
0x18000bf55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf5c  lea     rax, WPP_GLOBAL_Control
0x18000bf63  cmp     rcx, rax
0x18000bf66  jz      short loc_18000BF96
0x18000bf68  test    byte ptr [rcx+1Ch], 1
0x18000bf6c  jz      short loc_18000BF96
0x18000bf6e  mov     rcx, [rcx+10h]
0x18000bf72  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bf79  mov     [rsp+48h+var_18], 70Bh
0x18000bf81  lea     r9, aStatus; "Status"
0x18000bf88  mov     [rsp+48h+var_20], rax
0x18000bf8d  mov     [rsp+48h+var_28], ebx
0x18000bf91  call    WPP_SF_sDsd
0x18000bf96  mov     eax, ebx
0x18000bf98  and     eax, 1FFF0000h
0x18000bf9d  cmp     eax, 90000h
0x18000bfa2  jz      short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bfa4  cmp     eax, 100000h
0x18000bfa9  jz      short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bfab  test    ebx, ebx
0x18000bfad  jz      short loc_18000BF4B
0x18000bfaf  cmp     ebx, 216h
0x18000bfb5  ja      short loc_18000BFEF
0x18000bfb7  jz      loc_18000C0FF
0x18000bfbd  lea     eax, [rbx-2]; switch 182 cases
0x18000bfc0  cmp     eax, 0B5h
0x18000bfc5  ja      short def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000bfc7  lea     rdx, __ImageBase
0x18000bfce  movzx   eax, ds:(byte_18000C1A8 - 180000000h)[rdx+rax]
0x18000bfd6  mov     ecx, ds:(jpt_18000BFE0 - 180000000h)[rdx+rax*4]
0x18000bfdd  add     rcx, rdx
0x18000bfe0  jmp     rcx; switch jump
0x18000bfe2  mov     ebx, 80090027h; jumptable 000000018000BFE0 case 87
0x18000bfe7  mov     eax, ebx
0x18000bfe9  add     rsp, 40h
0x18000bfed  pop     rbx
0x18000bfee  retn
0x18000bfef  cmp     ebx, 0C000007Bh
0x18000bff5  ja      short loc_18000C04C
0x18000bff7  jz      loc_18000C140
0x18000bffd  cmp     ebx, 0C0000008h
0x18000c003  jz      loc_18000C0B1
0x18000c009  ja      loc_18000C14D
0x18000c00f  cmp     ebx, 800704C0h
0x18000c015  jz      loc_18000C0A4
0x18000c01b  cmp     ebx, 54Fh
0x18000c021  jz      loc_18000C10C
0x18000c027  cmp     ebx, 800704C7h
0x18000c02d  jz      loc_18000C119
0x18000c033  cmp     ebx, 80070578h
0x18000c039  jnz     def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c03f  mov     ebx, 80070578h
0x18000c044  mov     eax, ebx
0x18000c046  add     rsp, 40h
0x18000c04a  pop     rbx
0x18000c04b  retn
0x18000c04c  cmp     ebx, 0C0000135h
0x18000c052  ja      short loc_18000C073
0x18000c054  jz      loc_18000C133
0x18000c05a  cmp     ebx, 0C00000BBh
0x18000c060  jnz     loc_18000C172
0x18000c066  mov     ebx, 80090029h
0x18000c06b  mov     eax, ebx
0x18000c06d  add     rsp, 40h
0x18000c071  pop     rbx
0x18000c072  retn
0x18000c073  cmp     ebx, 0C0000142h
0x18000c079  jz      loc_18000C140
0x18000c07f  cmp     ebx, 0C0000139h
0x18000c085  jz      loc_18000C140
0x18000c08b  cmp     ebx, 0C000A000h
0x18000c091  jnz     def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c097  mov     ebx, 80090006h
0x18000c09c  mov     eax, ebx
0x18000c09e  add     rsp, 40h
0x18000c0a2  pop     rbx
0x18000c0a3  retn
0x18000c0a4  mov     ebx, 800704C0h
0x18000c0a9  mov     eax, ebx
0x18000c0ab  add     rsp, 40h
0x18000c0af  pop     rbx
0x18000c0b0  retn
0x18000c0b1  mov     ebx, 80090026h
0x18000c0b6  mov     eax, ebx
0x18000c0b8  add     rsp, 40h
0x18000c0bc  pop     rbx
0x18000c0bd  retn
0x18000c0be  mov     ebx, 80090028h; jumptable 000000018000BFE0 case 122
0x18000c0c3  mov     eax, ebx
0x18000c0c5  add     rsp, 40h
0x18000c0c9  pop     rbx
0x18000c0ca  retn
0x18000c0cb  mov     ebx, 80090011h; jumptable 000000018000BFE0 cases 2,3
0x18000c0d0  mov     eax, ebx
0x18000c0d2  add     rsp, 40h
0x18000c0d6  pop     rbx
0x18000c0d7  retn
0x18000c0d8  mov     ebx, 80090010h; jumptable 000000018000BFE0 case 5
0x18000c0dd  mov     eax, ebx
0x18000c0df  add     rsp, 40h
0x18000c0e3  pop     rbx
0x18000c0e4  retn
0x18000c0e5  mov     ebx, 80070070h; jumptable 000000018000BFE0 case 112
0x18000c0ea  mov     eax, ebx
0x18000c0ec  add     rsp, 40h
0x18000c0f0  pop     rbx
0x18000c0f1  retn
0x18000c0f2  mov     ebx, 8009000Fh; jumptable 000000018000BFE0 case 183
0x18000c0f7  mov     eax, ebx
0x18000c0f9  add     rsp, 40h
0x18000c0fd  pop     rbx
0x18000c0fe  retn
0x18000c0ff  mov     ebx, 80070216h
0x18000c104  mov     eax, ebx
0x18000c106  add     rsp, 40h
0x18000c10a  pop     rbx
0x18000c10b  retn
0x18000c10c  mov     ebx, 8009002Dh
0x18000c111  mov     eax, ebx
0x18000c113  add     rsp, 40h
0x18000c117  pop     rbx
0x18000c118  retn
0x18000c119  mov     ebx, 800704C7h
0x18000c11e  mov     eax, ebx
0x18000c120  add     rsp, 40h
0x18000c124  pop     rbx
0x18000c125  retn
0x18000c126  mov     ebx, 8009000Eh; jumptable 000000018000BFE0 cases 8,14
0x18000c12b  mov     eax, ebx
0x18000c12d  add     rsp, 40h
0x18000c131  pop     rbx
0x18000c132  retn
0x18000c133  mov     ebx, 8009001Eh
0x18000c138  mov     eax, ebx
0x18000c13a  add     rsp, 40h
0x18000c13e  pop     rbx
0x18000c13f  retn
0x18000c140  mov     ebx, 8009001Dh
0x18000c145  mov     eax, ebx
0x18000c147  add     rsp, 40h
0x18000c14b  pop     rbx
0x18000c14c  retn
0x18000c14d  cmp     ebx, 0C000000Dh
0x18000c153  jz      loc_18000BFE2; jumptable 000000018000BFE0 case 87
0x18000c159  cmp     ebx, 0C0000017h
0x18000c15f  jz      short loc_18000C126; jumptable 000000018000BFE0 cases 8,14
0x18000c161  cmp     ebx, 0C0000023h
0x18000c167  jnz     def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c16d  jmp     loc_18000C0BE; jumptable 000000018000BFE0 case 122
0x18000c172  cmp     ebx, 0C000009Ah
0x18000c178  jz      short loc_18000C126; jumptable 000000018000BFE0 cases 8,14
0x18000c17a  cmp     ebx, 0C00000E5h
0x18000c180  jnz     def_18000BFE0; jumptable 000000018000BFE0 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000c186  jmp     short loc_18000C10C
```
