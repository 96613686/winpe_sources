# IsWellKnownFormatType(_GUID const &)

- ea: `0x14000aed8`
- end: `0x14000af3a`
- name: `?IsWellKnownFormatType@@YA_NAEBU_GUID@@@Z`
- size: `98`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003520`
- `0x14000af44`

## callees

- `0x14000aed8`

## pseudocode

```c
bool __fastcall IsWellKnownFormatType(const struct _GUID *a1)
{
  __int64 v1; // rdx

  v1 = *(_QWORD *)&a1->Data1;
  return *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
      && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4
      || v1 == *(_QWORD *)&GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
      && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4
      || v1 == *(_QWORD *)&GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data1
      && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data4
      || v1 == *(_QWORD *)&GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data1
      && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data4;
}

```

## disassembly

```asm
0x14000aed8  mov     rdx, [rcx]
0x14000aedb  cmp     rdx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14000aee2  jnz     short loc_14000AEF1
0x14000aee4  mov     rax, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4
0x14000aeeb  cmp     [rcx+8], rax
0x14000aeef  jz      short loc_14000AF33
0x14000aef1  cmp     rdx, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14000aef8  jnz     short loc_14000AF07
0x14000aefa  mov     rax, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4
0x14000af01  cmp     [rcx+8], rax
0x14000af05  jz      short loc_14000AF33
0x14000af07  cmp     rdx, qword ptr cs:_GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data1
0x14000af0e  jnz     short loc_14000AF1D
0x14000af10  mov     rax, qword ptr cs:_GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data4
0x14000af17  cmp     [rcx+8], rax
0x14000af1b  jz      short loc_14000AF33
0x14000af1d  cmp     rdx, qword ptr cs:_GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data1
0x14000af24  jnz     short loc_14000AF37
0x14000af26  mov     rax, qword ptr cs:_GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data4
0x14000af2d  cmp     [rcx+8], rax
0x14000af31  jnz     short loc_14000AF37
0x14000af33  mov     al, 1
0x14000af35  retn
0x14000af37  xor     al, al
0x14000af39  retn
```
