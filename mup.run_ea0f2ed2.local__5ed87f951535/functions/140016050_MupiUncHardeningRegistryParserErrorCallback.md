# MupiUncHardeningRegistryParserErrorCallback

- ea: `0x140016050`
- end: `0x1400162c8`
- name: `MupiUncHardeningRegistryParserErrorCallback`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000426c`
- `0x140004304`
- `0x1400044bc`
- `0x140016050`

## pseudocode

```c
__int64 __fastcall MupiUncHardeningRegistryParserErrorCallback(int a1, unsigned __int16 *a2, __int64 a3)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  char v13; // [rsp+38h] [rbp-30h]
  __int16 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+48h] [rbp-20h]

  if ( a1 > 6 )
  {
    v8 = a1 - 7;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( (unsigned int)(v9 - 1) <= 1 && (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
        {
          v10 = *a2;
          LOWORD(v10) = (unsigned __int16)v10 >> 1;
          McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer(
            v10,
            (unsigned int)UncHardening_InvalidSyntax_IllegalString,
            *(_QWORD *)a3,
            **(_WORD **)a3 >> 1,
            *(_QWORD *)(*(_QWORD *)a3 + 8LL),
            *(_DWORD *)(a3 + 16) >> 1,
            *(_QWORD *)(a3 + 8),
            5,
            v10,
            *((_QWORD *)a2 + 1));
        }
      }
      else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
      {
        v11 = *a2;
        LOWORD(v11) = (unsigned __int16)v11 >> 1;
        McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer(
          v11,
          (unsigned int)UncHardening_InvalidSyntax_IllegalInteger,
          *(_QWORD *)a3,
          **(_WORD **)a3 >> 1,
          *(_QWORD *)(*(_QWORD *)a3 + 8LL),
          *(_DWORD *)(a3 + 16) >> 1,
          *(_QWORD *)(a3 + 8),
          4,
          v11,
          *((_QWORD *)a2 + 1));
      }
      return 0;
    }
LABEL_26:
    if ( (Microsoft_Windows_NetworkProviderEnableBits & 2) != 0 )
      McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer(
        *a2 >> 1,
        (unsigned int)UncHardening_UnsupportedProperty_StrValue,
        *(_QWORD *)a3,
        **(_WORD **)a3 >> 1,
        *(_QWORD *)(*(_QWORD *)a3 + 8LL),
        *(_DWORD *)(a3 + 16) >> 1,
        *(_QWORD *)(a3 + 8),
        *a2 >> 1,
        *((_QWORD *)a2 + 1),
        0,
        0);
    return 0;
  }
  if ( a1 == 6 )
    goto LABEL_26;
  v3 = a1 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( !v4 )
    {
      if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) == 0 )
        return 0;
      v7 = *a2;
      v15 = *((_QWORD *)a2 + 1);
      LOWORD(v7) = (unsigned __int16)v7 >> 1;
      v14 = v7;
      v13 = 1;
      goto LABEL_10;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) == 0 )
        return 0;
      v7 = *a2;
      v15 = *((_QWORD *)a2 + 1);
      LOWORD(v7) = (unsigned __int16)v7 >> 1;
      v14 = v7;
      v13 = 2;
      goto LABEL_10;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) == 0 )
        return 0;
      v7 = *a2;
      v15 = *((_QWORD *)a2 + 1);
      LOWORD(v7) = (unsigned __int16)v7 >> 1;
      v14 = v7;
      v13 = 3;
      goto LABEL_10;
    }
    if ( v6 == 1 && (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
    {
      v7 = *a2;
      v15 = *((_QWORD *)a2 + 1);
      LOWORD(v7) = (unsigned __int16)v7 >> 1;
      v14 = v7;
      v13 = 6;
LABEL_10:
      McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer(
        v7,
        (unsigned int)UncHardening_InvalidSyntax_UnexpectedToken,
        *(_QWORD *)a3,
        **(_WORD **)a3 >> 1,
        *(_QWORD *)(*(_QWORD *)a3 + 8LL),
        *(_DWORD *)(a3 + 16) >> 1,
        *(_QWORD *)(a3 + 8),
        v13,
        v14,
        v15);
    }
  }
  else if ( (Microsoft_Windows_NetworkProviderEnableBits & 1) != 0 )
  {
    McTemplateK0hzr0qzr2_EtwWriteTransfer(
      *(_DWORD *)(a3 + 16) >> 1,
      (unsigned int)UncHardening_InvalidSyntax_UnknownError,
      a3,
      **(_WORD **)a3 >> 1,
      *(_QWORD *)(*(_QWORD *)a3 + 8LL),
      *(_DWORD *)(a3 + 16) >> 1,
      *(_QWORD *)(a3 + 8));
  }
  return 0;
}

```

## disassembly

```asm
0x140016050  sub     rsp, 68h
0x140016054  mov     r10, r8
0x140016057  mov     r11, rdx
0x14001605a  cmp     ecx, 6
0x14001605d  jg      loc_1400161A2
0x140016063  jz      loc_140016264
0x140016069  sub     ecx, 1
0x14001606c  jz      loc_14001615D
0x140016072  sub     ecx, 1
0x140016075  jz      loc_14001612F
0x14001607b  sub     ecx, 1
0x14001607e  jz      loc_140016104
0x140016084  sub     ecx, 1
0x140016087  jz      short loc_1400160D9
0x140016089  cmp     ecx, 1
0x14001608c  jnz     loc_1400162C0
0x140016092  test    cs:Microsoft_Windows_NetworkProviderEnableBits, cl
0x140016098  jz      loc_1400162C0
0x14001609e  movzx   ecx, word ptr [rdx]
0x1400160a1  mov     rax, [rdx+8]
0x1400160a5  mov     [rsp+68h+var_20], rax
0x1400160aa  shr     cx, 1
0x1400160ad  mov     word ptr [rsp+68h+var_28], cx
0x1400160b2  mov     dword ptr [rsp+68h+var_30], 6
0x1400160ba  mov     edx, [r10+10h]
0x1400160be  mov     rax, [r10+8]
0x1400160c2  shr     edx, 1
0x1400160c4  mov     [rsp+68h+var_38], rax
0x1400160c9  mov     [rsp+68h+var_40], edx
0x1400160cd  lea     rdx, UncHardening_InvalidSyntax_UnexpectedToken
0x1400160d4  jmp     loc_140016201
0x1400160d9  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x1400160e0  jz      loc_1400162C0
0x1400160e6  movzx   ecx, word ptr [rdx]
0x1400160e9  mov     rax, [r11+8]
0x1400160ed  mov     [rsp+68h+var_20], rax
0x1400160f2  shr     cx, 1
0x1400160f5  mov     word ptr [rsp+68h+var_28], cx
0x1400160fa  mov     dword ptr [rsp+68h+var_30], 3
0x140016102  jmp     short loc_1400160BA
0x140016104  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x14001610b  jz      loc_1400162C0
0x140016111  movzx   ecx, word ptr [rdx]
0x140016114  mov     rax, [r11+8]
0x140016118  mov     [rsp+68h+var_20], rax
0x14001611d  shr     cx, 1
0x140016120  mov     word ptr [rsp+68h+var_28], cx
0x140016125  mov     dword ptr [rsp+68h+var_30], 2
0x14001612d  jmp     short loc_1400160BA
0x14001612f  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016136  jz      loc_1400162C0
0x14001613c  movzx   ecx, word ptr [rdx]
0x14001613f  mov     rax, [r11+8]
0x140016143  mov     [rsp+68h+var_20], rax
0x140016148  shr     cx, 1
0x14001614b  mov     word ptr [rsp+68h+var_28], cx
0x140016150  mov     dword ptr [rsp+68h+var_30], 1
0x140016158  jmp     loc_1400160BA
0x14001615d  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016164  jz      loc_1400162C0
0x14001616a  mov     rdx, [r8]
0x14001616d  mov     rax, [r8+8]
0x140016171  mov     ecx, [r8+10h]
0x140016175  mov     [rsp+68h+var_38], rax
0x14001617a  movzx   r9d, word ptr [rdx]
0x14001617e  mov     rax, [rdx+8]
0x140016182  lea     rdx, UncHardening_InvalidSyntax_UnknownError
0x140016189  shr     ecx, 1
0x14001618b  mov     [rsp+68h+var_40], ecx
0x14001618f  shr     r9w, 1
0x140016193  mov     [rsp+68h+var_48], rax
0x140016198  call    McTemplateK0hzr0qzr2_EtwWriteTransfer
0x14001619d  jmp     loc_1400162C0
0x1400161a2  sub     ecx, 7
0x1400161a5  jz      loc_140016264
0x1400161ab  sub     ecx, 1
0x1400161ae  jz      short loc_14001621F
0x1400161b0  sub     ecx, 1
0x1400161b3  jz      short loc_1400161BE
0x1400161b5  cmp     ecx, 1
0x1400161b8  jnz     loc_1400162C0
0x1400161be  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x1400161c5  jz      loc_1400162C0
0x1400161cb  movzx   ecx, word ptr [rdx]
0x1400161ce  mov     rax, [r11+8]
0x1400161d2  mov     edx, [r10+10h]
0x1400161d6  mov     [rsp+68h+var_20], rax
0x1400161db  mov     rax, [r10+8]
0x1400161df  shr     cx, 1
0x1400161e2  mov     word ptr [rsp+68h+var_28], cx
0x1400161e7  mov     dword ptr [rsp+68h+var_30], 5
0x1400161ef  shr     edx, 1
0x1400161f1  mov     [rsp+68h+var_38], rax
0x1400161f6  mov     [rsp+68h+var_40], edx
0x1400161fa  lea     rdx, UncHardening_InvalidSyntax_IllegalString
0x140016201  mov     r8, [r8]
0x140016204  movzx   r9d, word ptr [r8]
0x140016208  mov     rax, [r8+8]
0x14001620c  shr     r9w, 1
0x140016210  mov     [rsp+68h+var_48], rax
0x140016215  call    McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer
0x14001621a  jmp     loc_1400162C0
0x14001621f  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016226  jz      loc_1400162C0
0x14001622c  movzx   ecx, word ptr [rdx]
0x14001622f  mov     rax, [r11+8]
0x140016233  mov     edx, [r10+10h]
0x140016237  mov     [rsp+68h+var_20], rax
0x14001623c  mov     rax, [r10+8]
0x140016240  shr     cx, 1
0x140016243  mov     word ptr [rsp+68h+var_28], cx
0x140016248  mov     dword ptr [rsp+68h+var_30], 4
0x140016250  shr     edx, 1
0x140016252  mov     [rsp+68h+var_38], rax
0x140016257  mov     [rsp+68h+var_40], edx
0x14001625b  lea     rdx, UncHardening_InvalidSyntax_IllegalInteger
0x140016262  jmp     short loc_140016201
0x140016264  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x14001626b  jz      short loc_1400162C0
0x14001626d  movzx   ecx, word ptr [rdx]
0x140016270  xor     eax, eax
0x140016272  mov     r8, [r8]
0x140016275  mov     edx, [r10+10h]
0x140016279  mov     [rsp+68h+var_18], rax
0x14001627e  mov     word ptr [rsp+68h+var_20], ax
0x140016283  mov     rax, [r11+8]
0x140016287  movzx   r9d, word ptr [r8]
0x14001628b  mov     [rsp+68h+var_28], rax
0x140016290  mov     rax, [r10+8]
0x140016294  shr     edx, 1
0x140016296  shr     cx, 1
0x140016299  mov     word ptr [rsp+68h+var_30], cx
0x14001629e  mov     [rsp+68h+var_38], rax
0x1400162a3  mov     rax, [r8+8]
0x1400162a7  mov     [rsp+68h+var_40], edx
0x1400162ab  lea     rdx, UncHardening_UnsupportedProperty_StrValue
0x1400162b2  shr     r9w, 1
0x1400162b6  mov     [rsp+68h+var_48], rax
0x1400162bb  call    McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer
0x1400162c0  xor     eax, eax
0x1400162c2  add     rsp, 68h
0x1400162c6  retn
```
