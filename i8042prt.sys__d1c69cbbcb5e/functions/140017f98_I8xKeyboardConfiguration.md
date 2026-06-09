# I8xKeyboardConfiguration

- ea: `0x140017f98`
- end: `0x14001839c`
- name: `I8xKeyboardConfiguration`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1400198e0`

## callees

- `0x1400014e0`
- `0x1400043e0`
- `0x140004530`
- `0x140007b10`
- `0x14000a9c0`
- `0x14000aaac`
- `0x140017f98`

## pseudocode

```c
__int64 __fastcall I8xKeyboardConfiguration(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  unsigned int v4; // r12d
  unsigned __int8 *v5; // r14
  __int64 v6; // rsi
  unsigned int v7; // r15d
  int v8; // r8d
  int v9; // r9d
  int v10; // r13d
  const char *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  char v14; // al
  const char *v15; // rdx
  const char *v16; // rcx
  unsigned int v17; // eax
  int v18; // ecx
  __int64 v19; // r8
  wchar_t v20; // ax
  __int64 i; // rcx
  char v22; // al
  __int16 *v23; // rcx
  int v24; // [rsp+20h] [rbp-68h]

  if ( !a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        17,
        59,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    return 3221225626LL;
  }
  if ( a2 == (_DWORD *)-4LL )
    return 3221225626LL;
  v4 = a2[4];
  v5 = (unsigned __int8 *)(a2 + 5);
  v6 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  v7 = 0;
  *(_BYTE *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 80LL) = 0;
  v8 = 1;
  *(_DWORD *)(v6 + 20) = a2[2];
  v9 = 2;
  v10 = a2[1];
  for ( *(_DWORD *)(v6 + 16) = v10; v7 < v4; v5 += 20 )
  {
    LODWORD(a2) = *v5;
    if ( (_DWORD)a2 != 1 )
    {
      if ( *v5 == 2 )
      {
        *(_OWORD *)(a1 + 536) = *(_OWORD *)v5;
        *(_DWORD *)(a1 + 552) = *((_DWORD *)v5 + 4);
        v14 = 3;
        if ( v10 != 3 )
          v14 = 1;
        *(_BYTE *)(a1 + 537) = v14;
        goto LABEL_25;
      }
      if ( *v5 != 3 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            1,
            62,
            (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
LABEL_24:
          v9 = 2;
          v8 = 1;
          goto LABEL_25;
        }
        goto LABEL_25;
      }
      BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = "memory";
      if ( !BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) )
        v11 = "io";
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        14,
        60,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        (__int64)v11);
      v8 = 1;
      v9 = 2;
    }
    v12 = *(unsigned int *)(v6 + 64);
    if ( (unsigned int)v12 >= 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          17,
          61,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
          *(_DWORD *)(v6 + 64));
        goto LABEL_24;
      }
    }
    else
    {
      v13 = 5 * v12;
      *(_OWORD *)(v6 + 4 * v13 + 24) = *(_OWORD *)v5;
      *(_DWORD *)(v6 + 4 * v13 + 40) = *((_DWORD *)v5 + 4);
      *(_BYTE *)(v6 + 20LL * (unsigned int)(*(_DWORD *)(v6 + 64))++ + 25) = 2;
    }
LABEL_25:
    ++v7;
  }
  if ( (*(_BYTE *)(a1 + 536) & 2) != 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = "Latched";
    if ( *(_WORD *)(a1 + 538) != 1 )
      v15 = "Level Sensitive";
    v16 = "Sharable";
    if ( *(_BYTE *)(a1 + 537) != 3 )
      v16 = "NonSharable";
    WPP_RECORDER_SF_ssD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v15,
      (unsigned int)"NonSharable",
      63,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      (__int64)v16,
      (__int64)v15,
      *(_DWORD *)(a1 + 544));
  }
  LOBYTE(a2) = *(_BYTE *)(a1 + 688);
  if ( !(_BYTE)a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        16,
        64,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    LODWORD(a2) = 4;
    *(_BYTE *)(a1 + 688) = 4;
    *(_WORD *)(a1 + 732) = 0;
    *(_DWORD *)(a1 + 716) = 4;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ddD(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned __int8)a2,
      v8,
      v9,
      v24,
      (char)a2,
      *(_BYTE *)(a1 + 689),
      *(_WORD *)(a1 + 732));
  v17 = *(unsigned __int8 *)(a1 + 688);
  if ( (unsigned __int8)v17 > 8u || (v18 = 404, !_bittest(&v18, v17)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        16,
        66,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    *(_WORD *)(v6 + 72) = *(_WORD *)(v6 + 74);
  }
  v19 = *(unsigned __int8 *)(a1 + 688);
  if ( (unsigned __int8)(v19 - 7) <= 1u )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v22 = byte_140010730[8 * i];
      if ( !v22 )
        break;
      if ( v22 == (_BYTE)v19 && byte_140010731[8 * i] == *(_BYTE *)(a1 + 689) )
      {
        v23 = &word_140010732[4 * (unsigned int)i];
        if ( v23 )
          goto LABEL_53;
        break;
      }
    }
    v23 = word_140010712;
LABEL_53:
    *(_WORD *)(a1 + 692) = *v23;
    *(_WORD *)(a1 + 694) = v23[1];
    v20 = v23[2];
  }
  else
  {
    *(_WORD *)(a1 + 692) = aKdenableonctrl[3 * v19 + 17];
    *(_WORD *)(a1 + 694) = aKdenableonctrl[3 * v19 + 18];
    v20 = aKdenableonctrl[3 * v19 + 19];
  }
  *(_WORD *)(a1 + 696) = v20;
  result = 0;
  *(_WORD *)(a1 + 690) = 1;
  *(_DWORD *)(a1 + 706) = 16384002;
  *(_DWORD *)(a1 + 712) = 65536030;
  *(_DWORD *)(a1 + 726) = 16384030;
  return result;
}

```

## disassembly

```asm
0x140017f98  push    rbx
0x140017f9a  push    rbp
0x140017f9b  push    rsi
0x140017f9c  push    rdi
0x140017f9d  push    r12
0x140017f9f  push    r13
0x140017fa1  push    r14
0x140017fa3  push    r15
0x140017fa5  sub     rsp, 48h
0x140017fa9  mov     rbx, rcx
0x140017fac  test    rdx, rdx
0x140017faf  jnz     short loc_140017FE7
0x140017fb1  lea     rdi, WPP_RECORDER_INITIALIZED
0x140017fb8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140017fbf  jz      short loc_140017FF0
0x140017fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fc8  lea     rbp, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140017fcf  lea     r9d, [rdx+3Bh]
0x140017fd3  mov     [rsp+88h+var_68], rbp
0x140017fd8  lea     r8d, [rdx+11h]
0x140017fdc  mov     rcx, [rcx+40h]
0x140017fe0  call    WPP_RECORDER_SF_
0x140017fe5  jmp     short loc_140017FF0
0x140017fe7  lea     rcx, [rdx+4]
0x140017feb  test    rcx, rcx
0x140017fee  jnz     short loc_140017FFA
0x140017ff0  mov     eax, 0C000009Ah
0x140017ff5  jmp     loc_14001838A
0x140017ffa  mov     r12d, [rcx+0Ch]
0x140017ffe  lea     r14, [rcx+10h]
0x140018002  mov     rsi, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140018009  lea     rdi, WPP_RECORDER_INITIALIZED
0x140018010  xor     r15d, r15d
0x140018013  lea     rbp, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x14001801a  mov     byte ptr [rsi+50h], 0
0x14001801e  mov     eax, [rcx+4]
0x140018021  lea     r8d, [r15+1]
0x140018025  mov     [rsi+14h], eax
0x140018028  lea     r9d, [r15+2]
0x14001802c  mov     r13d, [rcx]
0x14001802f  mov     [rsi+10h], r13d
0x140018033  test    r12d, r12d
0x140018036  jz      loc_14001817B
0x14001803c  movzx   edx, byte ptr [r14]
0x140018040  mov     ecx, edx
0x140018042  sub     ecx, 1
0x140018045  jz      short loc_14001808D
0x140018047  sub     ecx, 1
0x14001804a  jz      loc_14001810C
0x140018050  cmp     ecx, 1
0x140018053  jz      short loc_140018086
0x140018055  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001805c  jz      loc_14001816B
0x140018062  mov     rcx, cs:WPP_GLOBAL_Control
0x140018069  mov     r9d, 3Eh ; '>'
0x14001806f  mov     dword ptr [rsp+88h+var_60], edx
0x140018073  mov     [rsp+88h+var_68], rbp
0x140018078  mov     rcx, [rcx+40h]
0x14001807c  call    WPP_RECORDER_SF_D
0x140018081  jmp     loc_140018161
0x140018086  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, r8b
0x14001808d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140018094  jz      short loc_1400180DD
0x140018096  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 0
0x14001809d  lea     rcx, aIo; "io"
0x1400180a4  mov     r9d, 3Ch ; '<'
0x1400180aa  lea     rax, aMemory; "memory"
0x1400180b1  cmovz   rax, rcx
0x1400180b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180bc  mov     [rsp+88h+var_60], rax
0x1400180c1  mov     [rsp+88h+var_68], rbp
0x1400180c6  lea     r8d, [r9-2Eh]
0x1400180ca  mov     rcx, [rcx+40h]
0x1400180ce  call    WPP_RECORDER_SF_s
0x1400180d3  mov     r8d, 1
0x1400180d9  lea     r9d, [r8+1]
0x1400180dd  mov     eax, [rsi+40h]
0x1400180e0  cmp     eax, r9d
0x1400180e3  jnb     short loc_140018135
0x1400180e5  movups  xmm0, xmmword ptr [r14]
0x1400180e9  lea     rcx, [rax+rax*4]
0x1400180ed  movups  xmmword ptr [rsi+rcx*4+18h], xmm0
0x1400180f2  mov     eax, [r14+10h]
0x1400180f6  mov     [rsi+rcx*4+28h], eax
0x1400180fa  mov     eax, [rsi+40h]
0x1400180fd  lea     rcx, [rax+rax*4]
0x140018101  mov     [rsi+rcx*4+19h], r9b
0x140018106  add     [rsi+40h], r8d
0x14001810a  jmp     short loc_14001816B
0x14001810c  movups  xmm0, xmmword ptr [r14]
0x140018110  movups  xmmword ptr [rbx+218h], xmm0
0x140018117  mov     eax, [r14+10h]
0x14001811b  mov     [rbx+228h], eax
0x140018121  mov     eax, 3
0x140018126  cmp     r13d, eax
0x140018129  cmovnz  eax, r8d
0x14001812d  mov     [rbx+219h], al
0x140018133  jmp     short loc_14001816B
0x140018135  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001813c  jz      short loc_14001816B
0x14001813e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018145  mov     r9d, 3Dh ; '='
0x14001814b  mov     dword ptr [rsp+88h+var_60], eax
0x14001814f  mov     [rsp+88h+var_68], rbp
0x140018154  mov     rcx, [rcx+40h]
0x140018158  lea     r8d, [r9-2Ch]
0x14001815c  call    WPP_RECORDER_SF_d
0x140018161  mov     r9d, 2
0x140018167  lea     r8d, [r9-1]
0x14001816b  add     r15d, r8d
0x14001816e  add     r14, 14h
0x140018172  cmp     r15d, r12d
0x140018175  jb      loc_14001803C
0x14001817b  test    [rbx+218h], r9b
0x140018182  jz      short loc_1400181EF
0x140018184  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001818b  jz      short loc_1400181EF
0x14001818d  cmp     [rbx+21Ah], r8w
0x140018195  lea     rcx, aLevelSensitive; "Level Sensitive"
0x14001819c  mov     eax, [rbx+220h]
0x1400181a2  lea     r8, aNonsharable; "NonSharable"
0x1400181a9  mov     [rsp+88h+var_50], eax
0x1400181ad  lea     rdx, aLatched; "Latched"
0x1400181b4  cmovnz  rdx, rcx
0x1400181b8  mov     r9d, 3Fh ; '?'
0x1400181be  cmp     byte ptr [rbx+219h], 3
0x1400181c5  lea     rcx, aSharable; "Sharable"
0x1400181cc  mov     [rsp+88h+var_58], rdx
0x1400181d1  cmovnz  rcx, r8
0x1400181d5  mov     [rsp+88h+var_60], rcx
0x1400181da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181e1  mov     [rsp+88h+var_68], rbp
0x1400181e6  mov     rcx, [rcx+40h]
0x1400181ea  call    WPP_RECORDER_SF_ssD
0x1400181ef  mov     dl, [rbx+2B0h]
0x1400181f5  mov     r14d, 10h
0x1400181fb  test    dl, dl
0x1400181fd  jnz     short loc_14001823E
0x1400181ff  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140018206  jz      short loc_140018224
0x140018208  mov     rcx, cs:WPP_GLOBAL_Control
0x14001820f  lea     r9d, [r14+30h]
0x140018213  mov     r8d, r14d
0x140018216  mov     [rsp+88h+var_68], rbp
0x14001821b  mov     rcx, [rcx+40h]
0x14001821f  call    WPP_RECORDER_SF_
0x140018224  mov     edx, 4
0x140018229  xor     eax, eax
0x14001822b  mov     [rbx+2B0h], dl
0x140018231  mov     [rbx+2DCh], ax
0x140018238  mov     [rbx+2CCh], edx
0x14001823e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140018245  jz      short loc_140018274
0x140018247  movzx   ecx, byte ptr [rbx+2B1h]
0x14001824e  movzx   eax, word ptr [rbx+2DCh]
0x140018255  mov     [rsp+88h+var_50], eax
0x140018259  mov     dword ptr [rsp+88h+var_58], ecx
0x14001825d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018264  movzx   edx, dl
0x140018267  mov     dword ptr [rsp+88h+var_60], edx
0x14001826b  mov     rcx, [rcx+40h]
0x14001826f  call    WPP_RECORDER_SF_ddD
0x140018274  movzx   eax, byte ptr [rbx+2B0h]
0x14001827b  cmp     al, 8
0x14001827d  ja      short loc_140018289
0x14001827f  mov     ecx, 194h
0x140018284  bt      ecx, eax
0x140018287  jb      short loc_1400182B8
0x140018289  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140018290  jz      short loc_1400182B0
0x140018292  mov     rcx, cs:WPP_GLOBAL_Control
0x140018299  mov     r9d, 42h ; 'B'
0x14001829f  mov     r8d, r14d
0x1400182a2  mov     [rsp+88h+var_68], rbp
0x1400182a7  mov     rcx, [rcx+40h]
0x1400182ab  call    WPP_RECORDER_SF_
0x1400182b0  movzx   eax, word ptr [rsi+4Ah]
0x1400182b4  mov     [rsi+48h], ax
0x1400182b8  movzx   r8d, byte ptr [rbx+2B0h]
0x1400182c0  lea     rdx, cs:140000000h
0x1400182c7  mov     r10d, 1
0x1400182cd  lea     eax, [r8-7]
0x1400182d1  cmp     al, r10b
0x1400182d4  jbe     short loc_140018302
0x1400182d6  lea     rcx, [r8+r8*2]
0x1400182da  movzx   eax, word ptr ds:(rva aKdenableonctrl+22h)[rdx+rcx*2]; "Rq" ...
0x1400182e2  mov     [rbx+2B4h], ax
0x1400182e9  movzx   eax, word ptr ds:(rva aKdenableonctrl+24h)[rdx+rcx*2]; "q" ...
0x1400182f1  mov     [rbx+2B6h], ax
0x1400182f8  movzx   eax, word ptr ds:(rva aKdenableonctrl+26h)[rdx+rcx*2]; "" ...
0x140018300  jmp     short loc_14001835B
0x140018302  xor     ecx, ecx
0x140018304  mov     al, ds:rva byte_140010730[rdx+rcx*8]
0x14001830b  mov     r9d, ecx
0x14001830e  test    al, al
0x140018310  jz      short loc_14001833B
0x140018312  cmp     al, r8b
0x140018315  jnz     short loc_140018326
0x140018317  mov     al, [rbx+2B1h]
0x14001831d  cmp     ds:rva byte_140010731[rdx+rcx*8], al
0x140018324  jz      short loc_14001832B
0x140018326  add     ecx, r10d
0x140018329  jmp     short loc_140018304
0x14001832b  lea     rcx, rva word_140010732[rdx]
0x140018332  lea     rcx, [rcx+r9*8]
0x140018336  test    rcx, rcx
0x140018339  jnz     short loc_140018342
0x14001833b  lea     rcx, word_140010712
0x140018342  movzx   eax, word ptr [rcx]
0x140018345  mov     [rbx+2B4h], ax
0x14001834c  movzx   eax, word ptr [rcx+2]
0x140018350  mov     [rbx+2B6h], ax
0x140018357  movzx   eax, word ptr [rcx+4]
0x14001835b  mov     [rbx+2B8h], ax
0x140018362  xor     eax, eax
0x140018364  mov     [rbx+2B2h], r10w
0x14001836c  mov     dword ptr [rbx+2C2h], 0FA0002h
0x140018376  mov     dword ptr [rbx+2C8h], 3E8001Eh
0x140018380  mov     dword ptr [rbx+2D6h], 0FA001Eh
0x14001838a  add     rsp, 48h
0x14001838e  pop     r15
0x140018390  pop     r14
0x140018392  pop     r13
0x140018394  pop     r12
0x140018396  pop     rdi
0x140018397  pop     rsi
0x140018398  pop     rbp
0x140018399  pop     rbx
0x14001839a  retn
```
