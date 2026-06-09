# MRxSmbBuildWriteRequest

- ea: `0x140045890`
- end: `0x140045d46`
- name: `MRxSmbBuildWriteRequest`
- size: `1206`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14002e3c0`
- `0x140044c70`

## callees

- `0x14003ff4c`
- `0x14003ff78`
- `0x140045890`
- `0x140046380`

## import_xrefs

- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140045d2a`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildWriteRequest(
        __int64 a1,
        char a2,
        char a3,
        unsigned __int16 a4,
        unsigned int *a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // r13
  __int64 v8; // rbx
  __int64 v9; // r11
  __int64 v11; // rbp
  __int64 v13; // rcx
  int v14; // esi
  unsigned int v15; // r14d
  unsigned int v16; // edx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rdx
  unsigned int v22; // edi
  __int64 result; // rax
  char v24; // al
  int v25; // r13d
  __int64 v26; // [rsp+20h] [rbp-C8h]
  __int64 v27; // [rsp+F0h] [rbp+8h]
  unsigned int v28; // [rsp+108h] [rbp+20h]

  v7 = *(_QWORD *)(a1 + 856);
  v8 = a1 + 888;
  v9 = *(_QWORD *)(a1 + 936);
  v11 = *(_QWORD *)(a1 + 920);
  v13 = *(_QWORD *)(*(_QWORD *)(v9 + 64) + 32LL);
  if ( v13 )
    v27 = *(_QWORD *)(v13 + 48);
  else
    v27 = 0;
  v14 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 420LL);
  v15 = *a5;
  v28 = *a5;
  if ( a3 == 47 )
  {
    v16 = 31;
  }
  else if ( a3 == 11 )
  {
    v16 = 16;
  }
  else
  {
    v16 = 0;
    if ( a3 == -63 )
      v16 = 5;
  }
  if ( *(_DWORD *)(v8 + 72) )
    goto LABEL_26;
  v17 = *(unsigned __int8 *)(v8 + 121);
  *(_BYTE *)(v8 + 123) = 1;
  if ( v17 != 255 )
  {
    switch ( v17 )
    {
      case 36:
      case 45:
      case 46:
      case 47:
      case 115:
      case 117:
      case 162:
        break;
      default:
        goto LABEL_26;
    }
  }
  v18 = *(_QWORD *)(v8 + 80);
  if ( v18 + (unsigned __int64)v16 >= *(_QWORD *)(v8 + 40) )
  {
LABEL_26:
    *(_BYTE *)(v8 + 122) = 1;
  }
  else if ( v9 && v16 + (_DWORD)v18 - *(_DWORD *)(v8 + 32) > 0x1104 )
  {
    *(_BYTE *)(v8 + 122) = 4;
  }
  else
  {
    v19 = *(unsigned __int8 *)(v8 + 124);
    v20 = *(unsigned __int16 *)(v8 + 128);
    *(_BYTE *)(v11 + 9) = v19;
    *(_DWORD *)(v8 + 124) = v19;
    *(_DWORD *)(v8 + 128) = v20;
    *(_WORD *)(v11 + 10) = v20;
    v21 = *(_QWORD *)(v8 + 88);
    if ( !v21 )
    {
      *(_BYTE *)(v11 + 4) = a3;
LABEL_12:
      v22 = 0;
      *(_QWORD *)(v8 + 88) = *(_QWORD *)(v8 + 80);
      *(_BYTE *)(v8 + 121) = a3;
      *(_QWORD *)(v8 + 104) = 0;
      goto LABEL_13;
    }
    if ( *(_QWORD *)(v8 + 80) < *(_QWORD *)(v8 + 40) )
    {
      *(_BYTE *)(v21 + 1) = a3;
      *(_BYTE *)(v21 + 2) = 0;
      *(_WORD *)(v21 + 3) = *(_WORD *)(v8 + 80) - *(_WORD *)(v8 + 32);
      goto LABEL_12;
    }
  }
  v22 = -1073741811;
LABEL_13:
  switch ( a3 )
  {
    case 47:
      if ( (v14 & 0x40000) != 0 && a2 )
        *(_WORD *)(v11 + 10) |= 0x2000u;
      v24 = *(_BYTE *)(a1 + 386);
      if ( v24 < 0 )
      {
        if ( (v24 & 0x40) != 0 )
        {
          v25 = 4;
        }
        else if ( *(_DWORD *)(a1 + 496) >= *(_DWORD *)(v7 + 16) )
        {
          v25 = 8;
        }
        else
        {
          v25 = 12;
          *(_BYTE *)(a1 + 386) = v24 | 0x20;
        }
      }
      else
      {
        v25 = (*(_DWORD *)(v9 + 120) & 4) != 0;
      }
      LODWORD(v26) = -1;
      MRxSmbStuffSMB(v8, "XwddwwwwQ", *(unsigned __int16 *)(v27 + 8), v28, v26, v25);
      break;
    case 11:
      LODWORD(v26) = v15;
      MRxSmbStuffSMB(v8, "0wwdwByw", *(unsigned __int16 *)(v27 + 8), a4, v26, 0);
      break;
    case -63:
      LODWORD(v26) = a4;
      MRxSmbStuffSMB(v8, "0wByw", *(unsigned __int16 *)(v27 + 8), 1, v26, 2 - (a6 != 0));
      break;
    default:
      v22 = -1073741823;
      break;
  }
  if ( a7 )
  {
    MRxSmbStuffAppendRawData(v8);
    MRxSmbStuffSetByteCount();
  }
  result = v22;
  if ( !v22 )
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                    + MRxSmbLegacyPerfCtrs
                                                    + 132));
  return result;
}

```

## disassembly

```asm
0x140045890  mov     [rsp+arg_8], rbx
0x140045895  push    rbp
0x140045896  push    rsi
0x140045897  push    rdi
0x140045898  push    r12
0x14004589a  push    r13
0x14004589c  push    r14
0x14004589e  push    r15
0x1400458a0  sub     rsp, 0B0h
0x1400458a7  mov     r13, [rcx+358h]
0x1400458ae  lea     rbx, [rcx+378h]
0x1400458b5  mov     r11, [rbx+30h]
0x1400458b9  mov     r10, rcx
0x1400458bc  mov     rbp, [rbx+20h]
0x1400458c0  movzx   r12d, dl
0x1400458c4  mov     rax, [r11+40h]
0x1400458c8  mov     rcx, [rax+20h]
0x1400458cc  test    rcx, rcx
0x1400458cf  jnz     loc_1400459F9
0x1400458d5  mov     [rsp+0E8h+arg_0], rcx
0x1400458dd  mov     rax, [r10+50h]
0x1400458e1  movzx   r15d, r9w
0x1400458e5  mov     esi, [rax+1A4h]
0x1400458eb  mov     rax, [rsp+0E8h+arg_20]
0x1400458f3  mov     r14d, [rax]
0x1400458f6  mov     eax, [rax+4]
0x1400458f9  mov     [rsp+0E8h+arg_10], eax
0x140045900  mov     [rsp+0E8h+arg_18], r14d
0x140045908  cmp     r8b, 2Fh ; '/'
0x14004590c  jnz     loc_140045A0A
0x140045912  mov     edx, 1Fh
0x140045917  cmp     dword ptr [rbx+48h], 0
0x14004591b  jnz     def_140045BE5; jumptable 0000000140045BE5 default case, cases 37-44,48-114,116,118-161
0x140045921  movzx   eax, byte ptr [rbx+79h]
0x140045925  mov     byte ptr [rbx+7Bh], 1
0x140045929  cmp     eax, 0FFh
0x14004592e  jnz     loc_140045BBE
0x140045934  mov     rcx, [rbx+50h]; jumptable 0000000140045BE5 cases 36,45-47,115,117,162
0x140045938  mov     eax, edx
0x14004593a  add     rax, rcx
0x14004593d  cmp     rax, [rbx+28h]
0x140045941  jnb     def_140045BE5; jumptable 0000000140045BE5 default case, cases 37-44,48-114,116,118-161
0x140045947  test    r11, r11
0x14004594a  jz      short loc_14004595D
0x14004594c  sub     ecx, [rbx+20h]
0x14004594f  add     ecx, edx
0x140045951  cmp     ecx, 1104h
0x140045957  ja      loc_140045BEB
0x14004595d  movzx   eax, byte ptr [rbx+7Ch]
0x140045961  movzx   ecx, word ptr [rbx+80h]
0x140045968  mov     [rbp+9], al
0x14004596b  mov     [rbx+7Ch], eax
0x14004596e  mov     [rbx+80h], ecx
0x140045974  mov     [rbp+0Ah], cx
0x140045978  mov     rdx, [rbx+58h]
0x14004597c  test    rdx, rdx
0x14004597f  jnz     loc_140045B6D
0x140045985  mov     [rbp+4], r8b
0x140045989  mov     rax, [rbx+50h]
0x14004598d  xor     edi, edi
0x14004598f  mov     [rbx+58h], rax
0x140045993  mov     [rbx+79h], r8b
0x140045997  mov     qword ptr [rbx+68h], 0
0x14004599f  cmp     r8b, 2Fh ; '/'
0x1400459a3  jz      loc_140045A38
0x1400459a9  cmp     r8b, 0Bh
0x1400459ad  jz      loc_140045C99
0x1400459b3  cmp     r8b, 0C1h
0x1400459b7  jz      loc_140045BF4
0x1400459bd  mov     edi, 0C0000001h
0x1400459c2  mov     rdx, [rsp+0E8h+arg_30]
0x1400459ca  test    rdx, rdx
0x1400459cd  jnz     loc_140045D0D
0x1400459d3  mov     eax, edi
0x1400459d5  test    edi, edi
0x1400459d7  jz      loc_140045D1F
0x1400459dd  mov     rbx, [rsp+0E8h+arg_8]
0x1400459e5  add     rsp, 0B0h
0x1400459ec  pop     r15
0x1400459ee  pop     r14
0x1400459f0  pop     r13
0x1400459f2  pop     r12
0x1400459f4  pop     rdi
0x1400459f5  pop     rsi
0x1400459f6  pop     rbp
0x1400459f7  retn
0x1400459f9  mov     rax, [rcx+30h]
0x1400459fd  mov     [rsp+0E8h+arg_0], rax
0x140045a05  jmp     loc_1400458DD
0x140045a0a  cmp     r8b, 0Bh
0x140045a0e  jz      loc_140045BB4
0x140045a14  xor     edx, edx
0x140045a16  cmp     r8b, 0C1h
0x140045a1a  jnz     loc_140045917
0x140045a20  mov     edx, 5
0x140045a25  jmp     loc_140045917
0x140045a2a  mov     byte ptr [rbx+7Ah], 1; jumptable 0000000140045BE5 default case, cases 37-44,48-114,116,118-161
0x140045a2e  mov     edi, 0C000000Dh
0x140045a33  jmp     loc_14004599F
0x140045a38  mov     r14d, r9d
0x140045a3b  shr     r14d, 10h
0x140045a3f  and     esi, 40000h
0x140045a45  jz      short loc_140045A55
0x140045a47  test    r12b, r12b
0x140045a4a  jz      short loc_140045A55
0x140045a4c  mov     eax, 2000h
0x140045a51  or      [rbp+0Ah], ax
0x140045a55  movzx   eax, byte ptr [r10+182h]
0x140045a5d  test    al, al
0x140045a5f  js      loc_140045C56
0x140045a65  mov     eax, [r11+78h]
0x140045a69  xor     ebp, ebp
0x140045a6b  mov     r10, [rsp+0E8h+arg_28]
0x140045a73  test    al, 4
0x140045a75  mov     rax, r10
0x140045a78  jz      loc_140045B65
0x140045a7e  mov     r13d, 1
0x140045a84  neg     rax
0x140045a87  sbb     edx, edx
0x140045a89  add     edx, 2
0x140045a8c  mov     r12d, 2
0x140045a92  jmp     short loc_140045A9A
0x140045a94  mov     r12d, 1
0x140045a9a  mov     rax, [rsp+0E8h+arg_0]
0x140045aa2  neg     esi
0x140045aa4  mov     [rsp+0E8h+var_40], 0
0x140045ab0  mov     [rsp+0E8h+var_48], r10
0x140045ab8  sbb     ecx, ecx
0x140045aba  mov     [rsp+0E8h+var_50], r9d
0x140045ac2  add     ecx, 2
0x140045ac5  movzx   r8d, word ptr [rax+8]
0x140045aca  lea     rax, aC; "c!"
0x140045ad1  mov     r9d, [rsp+0E8h+arg_18]
0x140045ad9  mov     [rsp+0E8h+var_58], rax
0x140045ae1  mov     eax, [r11+238h]
0x140045ae8  mov     [rsp+0E8h+var_60], edx
0x140045aef  lea     rdx, aXwddwwwwq; "XwddwwwwQ"
0x140045af6  mov     [rsp+0E8h+var_68], eax
0x140045afd  lea     rax, aW; "w"
0x140045b04  mov     [rsp+0E8h+var_70], rax
0x140045b09  lea     rax, aBs5; "BS5"
0x140045b10  mov     [rsp+0E8h+var_78], r12d
0x140045b15  mov     [rsp+0E8h+var_80], rax
0x140045b1a  mov     eax, [rsp+0E8h+arg_10]
0x140045b21  mov     dword ptr [rsp+0E8h+var_88], 1
0x140045b29  mov     dword ptr [rsp+0E8h+var_90], eax
0x140045b2d  lea     rax, aD; "D"
0x140045b34  mov     [rsp+0E8h+var_98], rax
0x140045b39  mov     dword ptr [rsp+0E8h+var_A0], ecx
0x140045b3d  mov     rcx, rbx
0x140045b40  mov     dword ptr [rsp+0E8h+var_A8], r15d
0x140045b45  mov     [rsp+0E8h+var_B0], r14d
0x140045b4a  mov     dword ptr [rsp+0E8h+var_B8], ebp
0x140045b4e  mov     [rsp+0E8h+var_C0], r13d
0x140045b53  mov     dword ptr [rsp+0E8h+var_C8], 0FFFFFFFFh
0x140045b5b  call    MRxSmbStuffSMB
0x140045b60  jmp     loc_1400459C2
0x140045b65  xor     r13d, r13d
0x140045b68  jmp     loc_140045A84
0x140045b6d  mov     rax, [rbx+28h]
0x140045b71  cmp     [rbx+50h], rax
0x140045b75  jnb     loc_140045A2E
0x140045b7b  mov     [rdx+1], r8b
0x140045b7f  mov     byte ptr [rdx+2], 0
0x140045b83  movzx   ecx, word ptr [rbx+50h]
0x140045b87  sub     cx, [rbx+20h]
0x140045b8b  mov     [rdx+3], cx
0x140045b8f  jmp     loc_140045989
0x140045b94  mov     r10, [rsp+0E8h+arg_28]
0x140045b9c  mov     rax, r10
0x140045b9f  neg     rax
0x140045ba2  sbb     edx, edx
0x140045ba4  add     edx, 2
0x140045ba7  test    cl, cl
0x140045ba9  jnz     loc_140045A94
0x140045baf  jmp     loc_140045A8C
0x140045bb4  mov     edx, 10h
0x140045bb9  jmp     loc_140045917
0x140045bbe  add     eax, 0FFFFFFDCh; switch 127 cases
0x140045bc1  cmp     eax, 7Eh
0x140045bc4  ja      def_140045BE5; jumptable 0000000140045BE5 default case, cases 37-44,48-114,116,118-161
0x140045bca  lea     rdi, cs:140000000h
0x140045bd1  cdqe
0x140045bd3  movzx   eax, ds:(byte_14001B349 - 140000000h)[rdi+rax]
0x140045bdb  mov     ecx, ds:(jpt_140045BE5 - 140000000h)[rdi+rax*4]
0x140045be2  add     rcx, rdi
0x140045be5  jmp     rcx; switch jump
0x140045beb  mov     byte ptr [rbx+7Ah], 4
0x140045bef  jmp     loc_140045A2E
0x140045bf4  mov     rcx, [rsp+0E8h+arg_28]
0x140045bfc  mov     [rsp+0E8h+var_A0], 0
0x140045c05  mov     rax, rcx
0x140045c08  mov     [rsp+0E8h+var_A8], rcx
0x140045c0d  neg     rax
0x140045c10  mov     rax, [rsp+0E8h+arg_0]
0x140045c18  mov     rcx, rbx
0x140045c1b  mov     [rsp+0E8h+var_B0], r9d
0x140045c20  sbb     edx, edx
0x140045c22  add     edx, 2
0x140045c25  mov     r9d, 1
0x140045c2b  movzx   r8d, word ptr [rax+8]
0x140045c30  lea     rax, aC; "c!"
0x140045c37  mov     [rsp+0E8h+var_B8], rax
0x140045c3c  mov     [rsp+0E8h+var_C0], edx
0x140045c40  lea     rdx, a0wbyw; "0wByw"
0x140045c47  mov     dword ptr [rsp+0E8h+var_C8], r15d
0x140045c4c  call    MRxSmbStuffSMB
0x140045c51  jmp     loc_1400459C2
0x140045c56  mov     ebp, [r13+10h]
0x140045c5a  xor     cl, cl
0x140045c5c  test    al, 40h
0x140045c5e  jnz     short loc_140045C8E
0x140045c60  cmp     [r10+1F0h], ebp
0x140045c67  jnb     short loc_140045C83
0x140045c69  add     r15d, 2
0x140045c6d  mov     cl, 1
0x140045c6f  or      al, 20h
0x140045c71  mov     r13d, 0Ch
0x140045c77  mov     [r10+182h], al
0x140045c7e  jmp     loc_140045B94
0x140045c83  mov     r13d, 8
0x140045c89  jmp     loc_140045B94
0x140045c8e  mov     r13d, 4
0x140045c94  jmp     loc_140045B94
0x140045c99  mov     rcx, [rsp+0E8h+arg_28]
0x140045ca1  mov     [rsp+0E8h+var_88], 0
0x140045caa  mov     rax, rcx
0x140045cad  mov     [rsp+0E8h+var_90], rcx
0x140045cb2  neg     rax
0x140045cb5  mov     rax, [rsp+0E8h+arg_0]
0x140045cbd  mov     rcx, rbx
0x140045cc0  mov     dword ptr [rsp+0E8h+var_98], r9d
0x140045cc5  sbb     edx, edx
0x140045cc7  add     edx, 2
0x140045cca  mov     r9d, r15d
0x140045ccd  movzx   r8d, word ptr [rax+8]
0x140045cd2  lea     rax, aC; "c!"
0x140045cd9  mov     [rsp+0E8h+var_A0], rax
0x140045cde  mov     dword ptr [rsp+0E8h+var_A8], edx
0x140045ce2  lea     rdx, a0wwdwbyw_0; "0wwdwByw"
0x140045ce9  mov     [rsp+0E8h+var_B0], r15d
0x140045cee  mov     dword ptr [rsp+0E8h+var_B8], 1
0x140045cf6  mov     [rsp+0E8h+var_C0], 0
0x140045cfe  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x140045d03  call    MRxSmbStuffSMB
0x140045d08  jmp     loc_1400459C2
0x140045d0d  mov     rcx, rbx
0x140045d10  call    MRxSmbStuffAppendRawData
0x140045d15  call    MRxSmbStuffSetByteCount
0x140045d1a  jmp     loc_1400459D3
0x140045d1f  mov     ecx, gs:1A4h
0x140045d27  mov     r8d, ecx
0x140045d2a  mov     rcx, cs:__imp_MRxSmbLegacyPerfCtrs
0x140045d31  shl     r8, 8
0x140045d35  mov     rdx, [rcx]
0x140045d38  lock inc dword ptr [r8+rdx+84h]
0x140045d41  jmp     loc_1400459DD
```
