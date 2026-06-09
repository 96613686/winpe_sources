# IsDuplicateMessage

- ea: `0x1400096ac`
- end: `0x1400097bc`
- name: `IsDuplicateMessage`
- size: `272`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140009b68`

## callees

- `0x140003104`
- `0x1400031a0`
- `0x140003530`
- `0x1400080f0`
- `0x1400096ac`
- `0x14000ec24`

## import_xrefs

- `msvcrt!_wtoi64` at `0x140009724`
- `msvcrt!_wtoi64` at `0x140009724`
- `OLEAUT32!__imp_VariantCopy` at `0x14000978b`
- `OLEAUT32!__imp_VariantCopy` at `0x14000978b`

## pseudocode

```c
char __fastcall IsDuplicateMessage(__int64 a1, __int64 a2)
{
  VARIANTARG *v3; // r14
  __int64 MsgLookupID; // rax
  char v5; // bl
  __int64 v6; // rax
  bool v7; // di
  VARIANTARG *v9; // rbx
  HRESULT v10; // eax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG v12; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v13; // [rsp+50h] [rbp-20h] BYREF

  v3 = (VARIANTARG *)(a1 + 152);
  _variant_t::_variant_t(&pvargDest, (VARIANTARG *)(a1 + 152));
  MsgLookupID = CMsgProperties::GetMsgLookupID(a2, &v13);
  v5 = 11;
  v7 = 0;
  if ( (unsigned __int8)_variant_t::operator==(&pvargDest, MsgLookupID) )
  {
    v6 = CMsgProperties::GetMsgLookupID(a2, &v12);
    v5 = 15;
    if ( _wtoi64(*(const wchar_t **)(v6 + 8)) )
      v7 = 1;
  }
  if ( (v5 & 4) != 0 )
  {
    v5 &= ~4u;
    _variant_t::~_variant_t(&v12);
  }
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    _variant_t::~_variant_t(&v13);
  }
  if ( (v5 & 1) != 0 )
    _variant_t::~_variant_t(&pvargDest);
  if ( v7 )
    return 1;
  v9 = (VARIANTARG *)CMsgProperties::GetMsgLookupID(a2, &v13);
  v10 = VariantCopy(v3, v9);
  if ( v10 < 0 )
    _com_issue_error(v10);
  _variant_t::~_variant_t(v9);
  return 0;
}

```

## disassembly

```asm
0x1400096ac  mov     [rsp-18h+arg_8], rbx
0x1400096b1  mov     [rsp-18h+arg_10], rsi
0x1400096b6  push    rbp
0x1400096b7  push    rdi
0x1400096b8  push    r14
0x1400096ba  mov     rbp, rsp
0x1400096bd  sub     rsp, 70h
0x1400096c1  mov     rsi, rdx
0x1400096c4  mov     dword ptr [rbp+arg_0], 0
0x1400096cb  lea     r14, [rcx+98h]
0x1400096d2  mov     rdx, r14; pvargSrc
0x1400096d5  lea     rcx, [rbp+pvargDest]; pvargDest
0x1400096d9  call    ??0_variant_t@@QEAA@AEBV0@@Z; _variant_t::_variant_t(_variant_t const &)
0x1400096de  nop
0x1400096df  mov     dword ptr [rbp+arg_0], 9
0x1400096e6  lea     rdx, [rbp+var_20]
0x1400096ea  mov     rcx, rsi
0x1400096ed  call    ?GetMsgLookupID@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetMsgLookupID(void)
0x1400096f2  nop
0x1400096f3  mov     ebx, 0Bh
0x1400096f8  mov     dword ptr [rbp+arg_0], ebx
0x1400096fb  mov     rdx, rax
0x1400096fe  lea     rcx, [rbp+pvargDest]
0x140009702  call    ??8_variant_t@@QEBA_NPEBUtagVARIANT@@@Z; _variant_t::operator==(tagVARIANT const *)
0x140009707  test    al, al
0x140009709  jz      short loc_140009734
0x14000970b  lea     rdx, [rbp+var_38]
0x14000970f  mov     rcx, rsi
0x140009712  call    ?GetMsgLookupID@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetMsgLookupID(void)
0x140009717  nop
0x140009718  mov     ebx, 0Fh
0x14000971d  mov     dword ptr [rbp+arg_0], ebx
0x140009720  mov     rcx, [rax+8]; String
0x140009724  call    cs:__imp__wtoi64
0x14000972a  test    rax, rax
0x14000972d  jz      short loc_140009734
0x14000972f  mov     dil, 1
0x140009732  jmp     short loc_140009737
0x140009734  xor     dil, dil
0x140009737  test    bl, 4
0x14000973a  jz      short loc_140009749
0x14000973c  and     ebx, 0FFFFFFFBh
0x14000973f  lea     rcx, [rbp+var_38]; this
0x140009743  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009748  nop
0x140009749  test    bl, 2
0x14000974c  jz      short loc_14000975B
0x14000974e  and     ebx, 0FFFFFFFDh
0x140009751  lea     rcx, [rbp+var_20]; this
0x140009755  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000975a  nop
0x14000975b  test    bl, 1
0x14000975e  jz      short loc_140009769
0x140009760  lea     rcx, [rbp+pvargDest]; this
0x140009764  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009769  test    dil, dil
0x14000976c  jz      short loc_140009772
0x14000976e  mov     al, 1
0x140009770  jmp     short loc_1400097A7
0x140009772  lea     rdx, [rbp+var_20]
0x140009776  mov     rcx, rsi
0x140009779  call    ?GetMsgLookupID@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetMsgLookupID(void)
0x14000977e  mov     rbx, rax
0x140009781  mov     [rbp+arg_0], rax
0x140009785  mov     rdx, rax; pvargSrc
0x140009788  mov     rcx, r14; pvargDest
0x14000978b  call    cs:__imp_VariantCopy
0x140009791  test    eax, eax
0x140009793  jns     short loc_14000979D
0x140009795  mov     ecx, eax; int
0x140009797  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000979d  mov     rcx, rbx; this
0x1400097a0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400097a5  xor     al, al
0x1400097a7  lea     r11, [rsp+70h+var_s0]
0x1400097ac  mov     rbx, [r11+28h]
0x1400097b0  mov     rsi, [r11+30h]
0x1400097b4  mov     rsp, r11
0x1400097b7  pop     r14
0x1400097b9  pop     rdi
0x1400097ba  pop     rbp
0x1400097bb  retn
```
