# IsWellKnownFormatType(_GUID const &)

- ea: `0x14000be38`
- end: `0x14000be9a`
- name: `?IsWellKnownFormatType@@YA_NAEBU_GUID@@@Z`
- size: `98`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003fa0`
- `0x14000bea4`

## callees

- `0x14000be38`

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
0x14000be38  mov     rdx, [rcx]
0x14000be3b  cmp     rdx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14000be42  jnz     short loc_14000BE51
0x14000be44  mov     rax, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4
0x14000be4b  cmp     [rcx+8], rax
0x14000be4f  jz      short loc_14000BE93
0x14000be51  cmp     rdx, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14000be58  jnz     short loc_14000BE67
0x14000be5a  mov     rax, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4
0x14000be61  cmp     [rcx+8], rax
0x14000be65  jz      short loc_14000BE93
0x14000be67  cmp     rdx, qword ptr cs:_GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data1
0x14000be6e  jnz     short loc_14000BE7D
0x14000be70  mov     rax, qword ptr cs:_GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data4
0x14000be77  cmp     [rcx+8], rax
0x14000be7b  jz      short loc_14000BE93
0x14000be7d  cmp     rdx, qword ptr cs:_GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data1
0x14000be84  jnz     short loc_14000BE97
0x14000be86  mov     rax, qword ptr cs:_GUID_692fa379_d3e8_4651_b5b4_0b94b013eeaf.Data4
0x14000be8d  cmp     [rcx+8], rax
0x14000be91  jnz     short loc_14000BE97
0x14000be93  mov     al, 1
0x14000be95  retn
0x14000be97  xor     al, al
0x14000be99  retn
```
