# MapAndQueueSupplicantEvent

- ea: `0x18000c870`
- end: `0x18000cd80`
- name: `MapAndQueueSupplicantEvent`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ba30`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000c870`
- `0x18000cf70`
- `0x180010d40`
- `0x1800214f0`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000cb0c`
- `MobileNetworking!AllocateMemory` at `0x18000cb0c`

## string_xrefs

- `0x18000cafa`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall MapAndQueueSupplicantEvent(_DWORD *a1, __int64 a2)
{
  unsigned int v4; // r15d
  _QWORD *v5; // r10
  int v6; // esi
  int v7; // ecx
  unsigned int v8; // eax
  int v9; // ecx
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebp
  unsigned int v14; // r14d
  int v15; // edi
  unsigned int v16; // r12d
  __int64 v17; // r13
  int v18; // ebp
  unsigned int v19; // eax
  _QWORD *v20; // rcx
  unsigned int i; // edx
  int v22; // ecx
  int v23; // ecx
  unsigned int v25; // [rsp+70h] [rbp+8h]
  int v26; // [rsp+78h] [rbp+10h]
  void *v27; // [rsp+80h] [rbp+18h] BYREF

  v4 = a1[5];
  v27 = 0;
  v5 = WPP_GLOBAL_Control;
  v6 = 22;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(a2 + 16);
  if ( v7 )
  {
    switch ( v7 )
    {
      case 2:
        v6 = 7;
        break;
      case 3:
        v6 = 1;
        break;
      case 6:
        v6 = 35;
        break;
      default:
        switch ( v7 )
        {
          case 1:
            v6 = 6;
            goto LABEL_37;
          case 4:
            v6 = 9;
            goto LABEL_37;
          case 5:
            v6 = 11;
            goto LABEL_37;
          case 7:
            v8 = *(_DWORD *)(a2 + 40);
            if ( v8 == 2 )
            {
              v9 = *(_DWORD *)(a2 + 48);
              switch ( v9 )
              {
                case 6:
                  if ( a1[609] >= a1[603] )
                    v6 = (a1[613] != 0) + 15;
                  else
                    v6 = 14;
                  goto LABEL_37;
                case 7:
                  goto LABEL_37;
                case 8:
                  v6 = 34;
                  goto LABEL_37;
              }
              v10 = 13;
              if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
                WPP_SF_dd(v5[7], 23, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v9);
            }
            else
            {
              v10 = 13;
              if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
              {
                v11 = v5[7];
                v12 = 24;
                goto LABEL_79;
              }
            }
            break;
          case 8:
            v6 = 32;
            goto LABEL_37;
          case 9:
            v6 = 39;
            goto LABEL_37;
          case 10:
            v6 = 8;
            goto LABEL_37;
          case 11:
            v6 = 2;
            goto LABEL_37;
          default:
            v10 = 13;
            if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
              WPP_SF_dd(v5[7], 25, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v7);
            goto LABEL_80;
        }
        goto LABEL_80;
    }
  }
  else
  {
    v6 = 5;
  }
LABEL_37:
  v13 = 0;
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v5[7], 13, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v14 = 0;
  if ( v27 )
    goto LABEL_61;
  v15 = *(_DWORD *)(a2 + 32);
  v16 = 56;
  v17 = *(_QWORD *)(a2 + 24);
  v14 = 56;
  v18 = 16 * v15;
  if ( v15 )
    v14 = v18 + 40;
  v26 = *(_DWORD *)(a2 + 16);
  v25 = *(_DWORD *)(v17 + 20);
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_(v5[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  if ( v15 )
    v16 = v18 + 40;
  v19 = AllocateMemory(v16, &v27, "OneXCreateEvent", 67);
  v13 = v19;
  if ( !v19 )
  {
    *((_DWORD *)v27 + 4) = v26;
    *((_DWORD *)v27 + 8) = v15;
    *((_QWORD *)v27 + 3) = v17;
    goto LABEL_53;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_57;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v25, v19);
LABEL_53:
    v20 = WPP_GLOBAL_Control;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v20[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13);
    v20 = WPP_GLOBAL_Control;
  }
LABEL_57:
  if ( !v13 )
  {
LABEL_61:
    memcpy_0(v27, (const void *)a2, v14);
    for ( i = 0; i < *((_DWORD *)v27 + 8); ++i )
    {
      v22 = *((_DWORD *)v27 + 4 * i + 10);
      if ( v22 != 8 )
      {
        v23 = v22 - 5;
        if ( v23 )
        {
          if ( (unsigned int)(v23 - 1) > 1 )
            continue;
        }
      }
      *((_DWORD *)v27 + 4 * i + 10) = 4;
    }
    goto LABEL_67;
  }
  if ( v20 == &WPP_GLOBAL_Control )
  {
LABEL_72:
    v10 = v13;
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 1) != 0 )
      WPP_SF_dd(v20[7], 26, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v13);
LABEL_80:
    OneXDeleteEvent((__int64)v27);
    goto LABEL_81;
  }
  if ( (*((_BYTE *)v20 + 68) & 1) != 0 )
  {
    WPP_SF_dd(v20[7], 15, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, v13);
LABEL_67:
    v20 = WPP_GLOBAL_Control;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v20[7], 16, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13);
    v20 = WPP_GLOBAL_Control;
  }
  if ( v13 )
    goto LABEL_72;
  *((_DWORD *)v27 + 4) = v6;
  v8 = QueueSupplicantEvent((__int64)v27);
  v10 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 7);
      v12 = 27;
LABEL_79:
      WPP_SF_dd(v11, v12, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v4, v8);
    }
    goto LABEL_80;
  }
LABEL_81:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000c870  mov     rax, rsp
0x18000c873  push    rdi
0x18000c874  sub     rsp, 60h
0x18000c878  mov     [rax+20h], rbx
0x18000c87c  mov     rdi, rcx
0x18000c87f  mov     [rax-18h], rsi
0x18000c883  mov     rbx, rdx
0x18000c886  mov     [rax-20h], r12
0x18000c88a  mov     [rax-38h], r15
0x18000c88e  mov     r15d, [rcx+14h]
0x18000c892  mov     qword ptr [rax+18h], 0
0x18000c89a  mov     r10, cs:WPP_GLOBAL_Control
0x18000c8a1  lea     r12, WPP_GLOBAL_Control
0x18000c8a8  mov     esi, 16h
0x18000c8ad  cmp     r10, r12
0x18000c8b0  jz      short loc_18000C8D5
0x18000c8b2  test    dword ptr [r10+44h], 800h
0x18000c8ba  jz      short loc_18000C8D5
0x18000c8bc  mov     rcx, [r10+38h]
0x18000c8c0  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000c8c7  mov     edx, esi
0x18000c8c9  call    WPP_SF_
0x18000c8ce  mov     r10, cs:WPP_GLOBAL_Control
0x18000c8d5  mov     ecx, [rbx+10h]
0x18000c8d8  mov     [rsp+68h+var_10], rbp
0x18000c8dd  mov     [rsp+68h+var_30], r14
0x18000c8e2  test    ecx, ecx
0x18000c8e4  jz      loc_18000CA4C
0x18000c8ea  cmp     ecx, 2
0x18000c8ed  jz      loc_18000CA45
0x18000c8f3  cmp     ecx, 3
0x18000c8f6  jz      loc_18000CA3E
0x18000c8fc  cmp     ecx, 6
0x18000c8ff  jz      loc_18000CA37
0x18000c905  lea     eax, [rcx-1]; switch 11 cases
0x18000c908  cmp     eax, 0Ah
0x18000c90b  ja      def_18000C922; jumptable 000000018000C922 default case, cases 2,3,6
0x18000c911  lea     rdx, __ImageBase
0x18000c918  mov     eax, ds:(jpt_18000C922 - 180000000h)[rdx+rax*4]
0x18000c91f  add     rax, rdx
0x18000c922  jmp     rax; switch jump
0x18000c924  mov     esi, 6; jumptable 000000018000C922 case 1
0x18000c929  jmp     loc_18000CA51
0x18000c92e  mov     esi, 8; jumptable 000000018000C922 case 10
0x18000c933  jmp     loc_18000CA51
0x18000c938  mov     esi, 9; jumptable 000000018000C922 case 4
0x18000c93d  jmp     loc_18000CA51
0x18000c942  mov     esi, 0Bh; jumptable 000000018000C922 case 5
0x18000c947  jmp     loc_18000CA51
0x18000c94c  mov     esi, 20h ; ' '; jumptable 000000018000C922 case 8
0x18000c951  jmp     loc_18000CA51
0x18000c956  mov     esi, 2; jumptable 000000018000C922 case 11
0x18000c95b  jmp     loc_18000CA51
0x18000c960  mov     esi, 27h ; '''; jumptable 000000018000C922 case 9
0x18000c965  jmp     loc_18000CA51
0x18000c96a  mov     eax, [rbx+28h]; jumptable 000000018000C922 case 7
0x18000c96d  cmp     eax, 2
0x18000c970  jnz     short loc_18000C9E5
0x18000c972  mov     ecx, [rbx+30h]
0x18000c975  cmp     ecx, 6
0x18000c978  jz      short loc_18000C9BF
0x18000c97a  mov     edx, ecx
0x18000c97c  sub     edx, 7
0x18000c97f  jz      loc_18000CA51
0x18000c985  cmp     edx, 1
0x18000c988  jz      short loc_18000C9B5
0x18000c98a  mov     edi, 0Dh
0x18000c98f  cmp     r10, r12
0x18000c992  jz      loc_18000CCF1
0x18000c998  test    byte ptr [r10+44h], 1
0x18000c99d  jz      loc_18000CCF1
0x18000c9a3  mov     [rsp+68h+var_48], ecx
0x18000c9a7  mov     edx, 17h
0x18000c9ac  mov     rcx, [r10+38h]
0x18000c9b0  jmp     loc_18000CCE2
0x18000c9b5  mov     esi, 22h ; '"'
0x18000c9ba  jmp     loc_18000CA51
0x18000c9bf  mov     eax, [rdi+96Ch]
0x18000c9c5  cmp     [rdi+984h], eax
0x18000c9cb  jnb     short loc_18000C9D4
0x18000c9cd  mov     esi, 0Eh
0x18000c9d2  jmp     short loc_18000CA51
0x18000c9d4  xor     esi, esi
0x18000c9d6  cmp     [rdi+994h], esi
0x18000c9dc  setnz   sil
0x18000c9e0  add     esi, 0Fh
0x18000c9e3  jmp     short loc_18000CA51
0x18000c9e5  mov     edi, 0Dh
0x18000c9ea  cmp     r10, r12
0x18000c9ed  jz      loc_18000CCF1
0x18000c9f3  test    byte ptr [r10+44h], 1
0x18000c9f8  jz      loc_18000CCF1
0x18000c9fe  mov     rcx, [r10+38h]
0x18000ca02  mov     edx, 18h
0x18000ca07  jmp     loc_18000CCDE
0x18000ca0c  mov     edi, 0Dh; jumptable 000000018000C922 default case, cases 2,3,6
0x18000ca11  cmp     r10, r12
0x18000ca14  jz      loc_18000CCF1
0x18000ca1a  test    byte ptr [r10+44h], 1
0x18000ca1f  jz      loc_18000CCF1
0x18000ca25  mov     [rsp+68h+var_48], ecx
0x18000ca29  mov     edx, 19h
0x18000ca2e  mov     rcx, [r10+38h]
0x18000ca32  jmp     loc_18000CCE2
0x18000ca37  mov     esi, 23h ; '#'
0x18000ca3c  jmp     short loc_18000CA51
0x18000ca3e  mov     esi, 1
0x18000ca43  jmp     short loc_18000CA51
0x18000ca45  mov     esi, 7
0x18000ca4a  jmp     short loc_18000CA51
0x18000ca4c  mov     esi, 5
0x18000ca51  xor     ebp, ebp
0x18000ca53  cmp     r10, r12
0x18000ca56  jz      short loc_18000CA7E
0x18000ca58  test    dword ptr [r10+44h], 800h
0x18000ca60  jz      short loc_18000CA7E
0x18000ca62  mov     rcx, [r10+38h]
0x18000ca66  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000ca6d  mov     edx, 0Dh
0x18000ca72  call    WPP_SF_
0x18000ca77  mov     r10, cs:WPP_GLOBAL_Control
0x18000ca7e  xor     r14d, r14d
0x18000ca81  cmp     [rsp+68h+arg_10], rbp
0x18000ca89  jnz     loc_18000CBF0
0x18000ca8f  mov     edi, [rbx+20h]
0x18000ca92  mov     r12d, 38h ; '8'
0x18000ca98  mov     ebp, edi
0x18000ca9a  mov     [rsp+68h+var_28], r13
0x18000ca9f  mov     r13, [rbx+18h]
0x18000caa3  mov     r14d, r12d
0x18000caa6  shl     ebp, 4
0x18000caa9  test    edi, edi
0x18000caab  lea     eax, [rbp+28h]
0x18000caae  cmovnz  r14d, eax
0x18000cab2  mov     eax, [rbx+10h]
0x18000cab5  mov     [rsp+68h+arg_8], eax
0x18000cab9  mov     eax, [r13+14h]
0x18000cabd  mov     [rsp+68h+arg_0], eax
0x18000cac1  lea     rax, WPP_GLOBAL_Control
0x18000cac8  cmp     r10, rax
0x18000cacb  jz      short loc_18000CAEC
0x18000cacd  test    dword ptr [r10+44h], 800h
0x18000cad5  jz      short loc_18000CAEC
0x18000cad7  mov     rcx, [r10+38h]
0x18000cadb  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cae2  mov     edx, 0Ah
0x18000cae7  call    WPP_SF_
0x18000caec  test    edi, edi
0x18000caee  jz      short loc_18000CAF4
0x18000caf0  lea     r12d, [rbp+28h]
0x18000caf4  mov     r9d, 43h ; 'C'
0x18000cafa  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000cb01  lea     rdx, [rsp+68h+arg_10]
0x18000cb09  mov     ecx, r12d
0x18000cb0c  call    cs:__imp_AllocateMemory
0x18000cb12  mov     ebp, eax
0x18000cb14  test    eax, eax
0x18000cb16  jz      short loc_18000CB55
0x18000cb18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb1f  lea     r12, WPP_GLOBAL_Control
0x18000cb26  cmp     rcx, r12
0x18000cb29  jz      loc_18000CBB6
0x18000cb2f  test    byte ptr [rcx+44h], 1
0x18000cb33  jz      short loc_18000CB89
0x18000cb35  mov     r9d, [rsp+68h+arg_0]
0x18000cb3a  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cb41  mov     rcx, [rcx+38h]
0x18000cb45  mov     edx, 0Bh
0x18000cb4a  mov     [rsp+68h+var_48], eax
0x18000cb4e  call    WPP_SF_dd
0x18000cb53  jmp     short loc_18000CB82
0x18000cb55  mov     rax, [rsp+68h+arg_10]
0x18000cb5d  lea     r12, WPP_GLOBAL_Control
0x18000cb64  mov     ecx, [rsp+68h+arg_8]
0x18000cb68  mov     [rax+10h], ecx
0x18000cb6b  mov     rax, [rsp+68h+arg_10]
0x18000cb73  mov     [rax+20h], edi
0x18000cb76  mov     rax, [rsp+68h+arg_10]
0x18000cb7e  mov     [rax+18h], r13
0x18000cb82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb89  cmp     rcx, r12
0x18000cb8c  jz      short loc_18000CBB6
0x18000cb8e  test    dword ptr [rcx+44h], 800h
0x18000cb95  jz      short loc_18000CBB6
0x18000cb97  mov     rcx, [rcx+38h]
0x18000cb9b  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cba2  mov     edx, 0Ch
0x18000cba7  mov     r9d, ebp
0x18000cbaa  call    WPP_SF_D
0x18000cbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbb6  mov     r13, [rsp+68h+var_28]
0x18000cbbb  test    ebp, ebp
0x18000cbbd  jz      short loc_18000CBF0
0x18000cbbf  cmp     rcx, r12
0x18000cbc2  jz      loc_18000CC89
0x18000cbc8  test    byte ptr [rcx+44h], 1
0x18000cbcc  jz      loc_18000CC58
0x18000cbd2  mov     rcx, [rcx+38h]
0x18000cbd6  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cbdd  mov     edx, 0Fh
0x18000cbe2  mov     [rsp+68h+var_48], ebp
0x18000cbe6  mov     r9d, r15d
0x18000cbe9  call    WPP_SF_dd
0x18000cbee  jmp     short loc_18000CC51
0x18000cbf0  mov     rcx, [rsp+68h+arg_10]; void *
0x18000cbf8  mov     rdx, rbx; Src
0x18000cbfb  mov     r8d, r14d; Size
0x18000cbfe  call    memcpy_0
0x18000cc03  mov     rax, [rsp+68h+arg_10]
0x18000cc0b  xor     edx, edx
0x18000cc0d  cmp     [rax+20h], edx
0x18000cc10  jbe     short loc_18000CC51
0x18000cc12  mov     rax, [rsp+68h+arg_10]
0x18000cc1a  mov     r8d, edx
0x18000cc1d  add     r8, r8
0x18000cc20  mov     ecx, [rax+r8*8+28h]
0x18000cc25  cmp     ecx, 8
0x18000cc28  jz      short loc_18000CC39
0x18000cc2a  sub     ecx, 5
0x18000cc2d  jz      short loc_18000CC39
0x18000cc2f  sub     ecx, 1
0x18000cc32  jz      short loc_18000CC39
0x18000cc34  cmp     ecx, 1
0x18000cc37  jnz     short loc_18000CC42
0x18000cc39  mov     dword ptr [rax+r8*8+28h], 4
0x18000cc42  mov     rax, [rsp+68h+arg_10]
0x18000cc4a  inc     edx
0x18000cc4c  cmp     edx, [rax+20h]
0x18000cc4f  jb      short loc_18000CC12
0x18000cc51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc58  cmp     rcx, r12
0x18000cc5b  jz      short loc_18000CC85
0x18000cc5d  test    dword ptr [rcx+44h], 800h
0x18000cc64  jz      short loc_18000CC85
0x18000cc66  mov     rcx, [rcx+38h]
0x18000cc6a  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cc71  mov     edx, 10h
0x18000cc76  mov     r9d, ebp
0x18000cc79  call    WPP_SF_D
0x18000cc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc85  test    ebp, ebp
0x18000cc87  jz      short loc_18000CCA5
0x18000cc89  mov     edi, ebp
0x18000cc8b  cmp     rcx, r12
0x18000cc8e  jz      short loc_18000CCF1
0x18000cc90  test    byte ptr [rcx+44h], 1
0x18000cc94  jz      short loc_18000CCF1
0x18000cc96  mov     rcx, [rcx+38h]
0x18000cc9a  mov     edx, 1Ah
0x18000cc9f  mov     [rsp+68h+var_48], ebp
0x18000cca3  jmp     short loc_18000CCE2
0x18000cca5  mov     rax, [rsp+68h+arg_10]
0x18000ccad  mov     [rax+10h], esi
0x18000ccb0  mov     rcx, [rsp+68h+arg_10]
0x18000ccb8  call    QueueSupplicantEvent
0x18000ccbd  mov     edi, eax
0x18000ccbf  test    eax, eax
0x18000ccc1  jz      short loc_18000CCFE
0x18000ccc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccca  cmp     rcx, r12
0x18000cccd  jz      short loc_18000CCF1
0x18000cccf  test    byte ptr [rcx+44h], 1
0x18000ccd3  jz      short loc_18000CCF1
0x18000ccd5  mov     rcx, [rcx+38h]
0x18000ccd9  mov     edx, 1Bh
0x18000ccde  mov     [rsp+68h+var_48], eax
0x18000cce2  mov     r9d, r15d
0x18000cce5  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000ccec  call    WPP_SF_dd
0x18000ccf1  mov     rcx, [rsp+68h+arg_10]
0x18000ccf9  call    OneXDeleteEvent
0x18000ccfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd05  mov     r15, [rsp+68h+var_38]
0x18000cd0a  cmp     rcx, r12
0x18000cd0d  mov     r12, [rsp+68h+var_20]
0x18000cd12  mov     r14, [rsp+68h+var_30]
0x18000cd17  mov     rsi, [rsp+68h+var_18]
0x18000cd1c  mov     rbp, [rsp+68h+var_10]
0x18000cd21  mov     rbx, [rsp+68h+arg_18]
0x18000cd29  jz      short loc_18000CD4C
0x18000cd2b  test    dword ptr [rcx+44h], 800h
0x18000cd32  jz      short loc_18000CD4C
0x18000cd34  mov     rcx, [rcx+38h]
0x18000cd38  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000cd3f  mov     edx, 1Ch
0x18000cd44  mov     r9d, edi
0x18000cd47  call    WPP_SF_D
0x18000cd4c  mov     eax, edi
0x18000cd4e  add     rsp, 60h
0x18000cd52  pop     rdi
0x18000cd53  retn
```
