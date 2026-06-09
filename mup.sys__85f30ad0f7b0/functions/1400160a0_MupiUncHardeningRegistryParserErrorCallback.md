# MupiUncHardeningRegistryParserErrorCallback

- ea: `0x1400160a0`
- end: `0x140016318`
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
- `0x1400160a0`

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
0x1400160a0  sub     rsp, 68h
0x1400160a4  mov     r10, r8
0x1400160a7  mov     r11, rdx
0x1400160aa  cmp     ecx, 6
0x1400160ad  jg      loc_1400161F2
0x1400160b3  jz      loc_1400162B4
0x1400160b9  sub     ecx, 1
0x1400160bc  jz      loc_1400161AD
0x1400160c2  sub     ecx, 1
0x1400160c5  jz      loc_14001617F
0x1400160cb  sub     ecx, 1
0x1400160ce  jz      loc_140016154
0x1400160d4  sub     ecx, 1
0x1400160d7  jz      short loc_140016129
0x1400160d9  cmp     ecx, 1
0x1400160dc  jnz     loc_140016310
0x1400160e2  test    cs:Microsoft_Windows_NetworkProviderEnableBits, cl
0x1400160e8  jz      loc_140016310
0x1400160ee  movzx   ecx, word ptr [rdx]
0x1400160f1  mov     rax, [rdx+8]
0x1400160f5  mov     [rsp+68h+var_20], rax
0x1400160fa  shr     cx, 1
0x1400160fd  mov     word ptr [rsp+68h+var_28], cx
0x140016102  mov     dword ptr [rsp+68h+var_30], 6
0x14001610a  mov     edx, [r10+10h]
0x14001610e  mov     rax, [r10+8]
0x140016112  shr     edx, 1
0x140016114  mov     [rsp+68h+var_38], rax
0x140016119  mov     [rsp+68h+var_40], edx
0x14001611d  lea     rdx, UncHardening_InvalidSyntax_UnexpectedToken
0x140016124  jmp     loc_140016251
0x140016129  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016130  jz      loc_140016310
0x140016136  movzx   ecx, word ptr [rdx]
0x140016139  mov     rax, [r11+8]
0x14001613d  mov     [rsp+68h+var_20], rax
0x140016142  shr     cx, 1
0x140016145  mov     word ptr [rsp+68h+var_28], cx
0x14001614a  mov     dword ptr [rsp+68h+var_30], 3
0x140016152  jmp     short loc_14001610A
0x140016154  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x14001615b  jz      loc_140016310
0x140016161  movzx   ecx, word ptr [rdx]
0x140016164  mov     rax, [r11+8]
0x140016168  mov     [rsp+68h+var_20], rax
0x14001616d  shr     cx, 1
0x140016170  mov     word ptr [rsp+68h+var_28], cx
0x140016175  mov     dword ptr [rsp+68h+var_30], 2
0x14001617d  jmp     short loc_14001610A
0x14001617f  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016186  jz      loc_140016310
0x14001618c  movzx   ecx, word ptr [rdx]
0x14001618f  mov     rax, [r11+8]
0x140016193  mov     [rsp+68h+var_20], rax
0x140016198  shr     cx, 1
0x14001619b  mov     word ptr [rsp+68h+var_28], cx
0x1400161a0  mov     dword ptr [rsp+68h+var_30], 1
0x1400161a8  jmp     loc_14001610A
0x1400161ad  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x1400161b4  jz      loc_140016310
0x1400161ba  mov     rdx, [r8]
0x1400161bd  mov     rax, [r8+8]
0x1400161c1  mov     ecx, [r8+10h]
0x1400161c5  mov     [rsp+68h+var_38], rax
0x1400161ca  movzx   r9d, word ptr [rdx]
0x1400161ce  mov     rax, [rdx+8]
0x1400161d2  lea     rdx, UncHardening_InvalidSyntax_UnknownError
0x1400161d9  shr     ecx, 1
0x1400161db  mov     [rsp+68h+var_40], ecx
0x1400161df  shr     r9w, 1
0x1400161e3  mov     [rsp+68h+var_48], rax
0x1400161e8  call    McTemplateK0hzr0qzr2_EtwWriteTransfer
0x1400161ed  jmp     loc_140016310
0x1400161f2  sub     ecx, 7
0x1400161f5  jz      loc_1400162B4
0x1400161fb  sub     ecx, 1
0x1400161fe  jz      short loc_14001626F
0x140016200  sub     ecx, 1
0x140016203  jz      short loc_14001620E
0x140016205  cmp     ecx, 1
0x140016208  jnz     loc_140016310
0x14001620e  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016215  jz      loc_140016310
0x14001621b  movzx   ecx, word ptr [rdx]
0x14001621e  mov     rax, [r11+8]
0x140016222  mov     edx, [r10+10h]
0x140016226  mov     [rsp+68h+var_20], rax
0x14001622b  mov     rax, [r10+8]
0x14001622f  shr     cx, 1
0x140016232  mov     word ptr [rsp+68h+var_28], cx
0x140016237  mov     dword ptr [rsp+68h+var_30], 5
0x14001623f  shr     edx, 1
0x140016241  mov     [rsp+68h+var_38], rax
0x140016246  mov     [rsp+68h+var_40], edx
0x14001624a  lea     rdx, UncHardening_InvalidSyntax_IllegalString
0x140016251  mov     r8, [r8]
0x140016254  movzx   r9d, word ptr [r8]
0x140016258  mov     rax, [r8+8]
0x14001625c  shr     r9w, 1
0x140016260  mov     [rsp+68h+var_48], rax
0x140016265  call    McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer
0x14001626a  jmp     loc_140016310
0x14001626f  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 1
0x140016276  jz      loc_140016310
0x14001627c  movzx   ecx, word ptr [rdx]
0x14001627f  mov     rax, [r11+8]
0x140016283  mov     edx, [r10+10h]
0x140016287  mov     [rsp+68h+var_20], rax
0x14001628c  mov     rax, [r10+8]
0x140016290  shr     cx, 1
0x140016293  mov     word ptr [rsp+68h+var_28], cx
0x140016298  mov     dword ptr [rsp+68h+var_30], 4
0x1400162a0  shr     edx, 1
0x1400162a2  mov     [rsp+68h+var_38], rax
0x1400162a7  mov     [rsp+68h+var_40], edx
0x1400162ab  lea     rdx, UncHardening_InvalidSyntax_IllegalInteger
0x1400162b2  jmp     short loc_140016251
0x1400162b4  test    cs:Microsoft_Windows_NetworkProviderEnableBits, 2
0x1400162bb  jz      short loc_140016310
0x1400162bd  movzx   ecx, word ptr [rdx]
0x1400162c0  xor     eax, eax
0x1400162c2  mov     r8, [r8]
0x1400162c5  mov     edx, [r10+10h]
0x1400162c9  mov     [rsp+68h+var_18], rax
0x1400162ce  mov     word ptr [rsp+68h+var_20], ax
0x1400162d3  mov     rax, [r11+8]
0x1400162d7  movzx   r9d, word ptr [r8]
0x1400162db  mov     [rsp+68h+var_28], rax
0x1400162e0  mov     rax, [r10+8]
0x1400162e4  shr     edx, 1
0x1400162e6  shr     cx, 1
0x1400162e9  mov     word ptr [rsp+68h+var_30], cx
0x1400162ee  mov     [rsp+68h+var_38], rax
0x1400162f3  mov     rax, [r8+8]
0x1400162f7  mov     [rsp+68h+var_40], edx
0x1400162fb  lea     rdx, UncHardening_UnsupportedProperty_StrValue
0x140016302  shr     r9w, 1
0x140016306  mov     [rsp+68h+var_48], rax
0x14001630b  call    McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer
0x140016310  xor     eax, eax
0x140016312  add     rsp, 68h
0x140016316  retn
```
