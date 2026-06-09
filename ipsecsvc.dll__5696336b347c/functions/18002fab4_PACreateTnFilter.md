# PACreateTnFilter

- ea: `0x18002fab4`
- end: `0x18002ff07`
- name: `PACreateTnFilter`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002a6f8`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x18000f638`
- `0x18001cc50`
- `0x180029504`
- `0x180029fb8`
- `0x18002fab4`
- `0x1800302b4`
- `0x1800302ec`
- `0x180042f28`
- `0x180043078`
- `0x180043460`
- `0x18004d090`

## pseudocode

```c
__int64 __fastcall PACreateTnFilter(unsigned int a1, _OWORD *a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  unsigned int *v10; // rax
  unsigned int *v11; // rbx
  unsigned int v12; // ebp
  _QWORD *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rdx
  _WORD *v16; // r8
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r11
  __int64 v22; // rax
  __int64 result; // rax
  _BYTE v24[528]; // [rsp+30h] [rbp-268h] BYREF

  v10 = (unsigned int *)IpsecAllocMem(0xE8u);
  v11 = v10;
  if ( !v10 )
  {
    v12 = 14;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids, 14);
      v13 = WPP_GLOBAL_Control;
    }
    v14 = a4 + 24;
    goto LABEL_55;
  }
  *v10 = MapProtocolVersion(a1);
  v14 = a4 + 24;
  *(_OWORD *)(v11 + 1) = *(_OWORD *)(a4 + 24);
  v16 = *(_WORD **)(a4 + 16);
  if ( v16 && *v16 != (_WORD)v15 )
  {
    v17 = NsuStringDupW(v11 + 6, v15, v16);
    v12 = v17;
    if ( v17 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 18;
LABEL_12:
          v19 = v17;
LABEL_54:
          WPP_SF_d(v13[2], v18, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids, v19);
          v13 = WPP_GLOBAL_Control;
          goto LABEL_55;
        }
        goto LABEL_55;
      }
      goto LABEL_58;
    }
LABEL_21:
    PASetInterfaceType(*(unsigned int *)(a3 + 40), v11 + 8);
    v20 = *v11;
    *(_QWORD *)(v11 + 9) = 0;
    v17 = PASetAddressForTunnel(v20, a4 + 44, v11 + 12);
    v12 = v17;
    if ( v17 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 21;
          goto LABEL_12;
        }
        goto LABEL_55;
      }
    }
    else
    {
      v17 = PASetAddressForTunnel(*v11, a4 + 84, v11 + 20);
      v12 = v17;
      if ( v17 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v18 = 22;
            goto LABEL_12;
          }
          goto LABEL_55;
        }
      }
      else
      {
        *(_OWORD *)(v11 + 34) = 0;
        *(_OWORD *)(v11 + 38) = 0;
        v11[34] = 8;
        if ( *v11 == (_DWORD)v21 )
        {
          v11[43] = *(_DWORD *)(a3 + 56);
          if ( *(_DWORD *)(a3 + 56) != (_DWORD)v21 )
          {
            v11[42] = 1;
            v11[44] = -1;
          }
          *((_QWORD *)v11 + 23) = v21;
        }
        else
        {
          *(_OWORD *)(v11 + 43) = *(_OWORD *)(a3 + 60);
          v22 = *(_QWORD *)(a3 + 60) - qword_180060990;
          if ( !v22 )
            v22 = *(_QWORD *)(a3 + 68) - qword_180060998;
          if ( v22 )
          {
            v11[42] = 1;
            *((_BYTE *)v11 + 188) = 0x80;
          }
          *((_QWORD *)v11 + 24) = v21;
        }
        v11[28] = 1;
        if ( *(_DWORD *)(a4 + 140) != (_DWORD)v21 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids);
            v13 = WPP_GLOBAL_Control;
          }
          v19 = 87;
          v12 = 87;
          if ( v13 == &WPP_GLOBAL_Control )
            goto LABEL_58;
          if ( (*((_BYTE *)v13 + 28) & 0x10) == 0 )
            goto LABEL_55;
          v18 = 24;
          goto LABEL_54;
        }
        v11[29] = v21;
        v11[30] = 1;
        *((_WORD *)v11 + 62) = v21;
        v11[32] = 1;
        *((_WORD *)v11 + 66) = v21;
        if ( *(_WORD *)(a4 + 128) == (_WORD)v21 && *(_WORD *)(a4 + 136) == (_WORD)v21 )
        {
          SetFilterActions(a5, v11 + 50, v11 + 51);
          *((_QWORD *)v11 + 26) = 0;
          result = 0;
          *(_OWORD *)(v11 + 54) = *a2;
          *a6 = v11;
          return result;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids);
          v13 = WPP_GLOBAL_Control;
        }
        v19 = 87;
        v12 = 87;
        if ( v13 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v13 + 28) & 0x10) != 0 )
          {
            v18 = 26;
            goto LABEL_54;
          }
          goto LABEL_55;
        }
      }
    }
    goto LABEL_58;
  }
  ++gdwTnFilterCounter;
  v17 = NsuStringSprintW(v24, 260, L"%d");
  v12 = v17;
  if ( !v17 )
  {
    v17 = NsuStringDupW(v11 + 6, 0, v24);
    v12 = v17;
    if ( v17 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v18 = 20;
          goto LABEL_12;
        }
        goto LABEL_55;
      }
      goto LABEL_58;
    }
    goto LABEL_21;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v18 = 19;
      goto LABEL_12;
    }
LABEL_55:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF__guid_D(v13[2], 27, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids, v14, v12);
  }
LABEL_58:
  if ( v11 )
    PAFreeTnFilter(v11);
  *a6 = 0;
  return v12;
}

```

## disassembly

```asm
0x18002fab4  push    rbx
0x18002fab6  push    rbp
0x18002fab7  push    rsi
0x18002fab8  push    rdi
0x18002fab9  push    r12
0x18002fabb  push    r13
0x18002fabd  push    r14
0x18002fabf  push    r15
0x18002fac1  sub     rsp, 258h
0x18002fac8  mov     rax, cs:__security_cookie
0x18002facf  xor     rax, rsp
0x18002fad2  mov     [rsp+298h+var_58], rax
0x18002fada  mov     r12, [rsp+298h+arg_20]
0x18002fae2  mov     esi, ecx
0x18002fae4  mov     r13, [rsp+298h+arg_28]
0x18002faec  mov     ecx, 0E8h
0x18002faf1  mov     r14, r9
0x18002faf4  mov     rdi, r8
0x18002faf7  mov     r15, rdx
0x18002fafa  call    IpsecAllocMem
0x18002faff  xor     edx, edx
0x18002fb01  mov     rbx, rax
0x18002fb04  test    rax, rax
0x18002fb07  jnz     short loc_18002FB4B
0x18002fb09  lea     ebp, [rax+0Eh]
0x18002fb0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb13  lea     rdi, WPP_GLOBAL_Control
0x18002fb1a  cmp     rcx, rdi
0x18002fb1d  jz      short loc_18002FB42
0x18002fb1f  test    byte ptr [rcx+1Ch], 10h
0x18002fb23  jz      short loc_18002FB42
0x18002fb25  mov     rcx, [rcx+10h]
0x18002fb29  lea     edx, [rax+11h]
0x18002fb2c  mov     r9d, ebp
0x18002fb2f  lea     r8, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids
0x18002fb36  call    WPP_SF_d
0x18002fb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb42  lea     rsi, [r14+18h]
0x18002fb46  jmp     loc_18002FEA7
0x18002fb4b  mov     ecx, esi
0x18002fb4d  call    MapProtocolVersion
0x18002fb52  mov     [rbx], eax
0x18002fb54  lea     rsi, [r14+18h]
0x18002fb58  movups  xmm0, xmmword ptr [rsi]
0x18002fb5b  movdqu  xmmword ptr [rbx+4], xmm0
0x18002fb60  mov     r8, [r14+10h]
0x18002fb64  test    r8, r8
0x18002fb67  jz      short loc_18002FBB2
0x18002fb69  cmp     [r8], dx
0x18002fb6d  jz      short loc_18002FBB2
0x18002fb6f  lea     rcx, [rbx+18h]
0x18002fb73  call    NsuStringDupW
0x18002fb78  xor     r11d, r11d
0x18002fb7b  mov     ebp, eax
0x18002fb7d  test    eax, eax
0x18002fb7f  jz      loc_18002FC4A
0x18002fb85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb8c  lea     rdi, WPP_GLOBAL_Control
0x18002fb93  cmp     rcx, rdi
0x18002fb96  jz      loc_18002FECE
0x18002fb9c  test    byte ptr [rcx+1Ch], 10h
0x18002fba0  jz      loc_18002FEA7
0x18002fba6  lea     edx, [r11+12h]
0x18002fbaa  mov     r9d, eax
0x18002fbad  jmp     loc_18002FE90
0x18002fbb2  mov     r9d, cs:gdwTnFilterCounter
0x18002fbb9  lea     r8, aD; "%d"
0x18002fbc0  inc     r9d
0x18002fbc3  lea     rcx, [rsp+298h+var_268]
0x18002fbc8  mov     edx, 104h
0x18002fbcd  mov     cs:gdwTnFilterCounter, r9d
0x18002fbd4  call    NsuStringSprintW
0x18002fbd9  mov     ebp, eax
0x18002fbdb  test    eax, eax
0x18002fbdd  jz      short loc_18002FC07
0x18002fbdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbe6  lea     rdi, WPP_GLOBAL_Control
0x18002fbed  cmp     rcx, rdi
0x18002fbf0  jz      loc_18002FECE
0x18002fbf6  test    byte ptr [rcx+1Ch], 10h
0x18002fbfa  jz      loc_18002FEA7
0x18002fc00  mov     edx, 13h
0x18002fc05  jmp     short loc_18002FBAA
0x18002fc07  lea     rcx, [rbx+18h]
0x18002fc0b  xor     edx, edx
0x18002fc0d  lea     r8, [rsp+298h+var_268]
0x18002fc12  call    NsuStringDupW
0x18002fc17  xor     r11d, r11d
0x18002fc1a  mov     ebp, eax
0x18002fc1c  test    eax, eax
0x18002fc1e  jz      short loc_18002FC4A
0x18002fc20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc27  lea     rdi, WPP_GLOBAL_Control
0x18002fc2e  cmp     rcx, rdi
0x18002fc31  jz      loc_18002FECE
0x18002fc37  test    byte ptr [rcx+1Ch], 10h
0x18002fc3b  jz      loc_18002FEA7
0x18002fc41  lea     edx, [r11+14h]
0x18002fc45  jmp     loc_18002FBAA
0x18002fc4a  mov     ecx, [rdi+28h]
0x18002fc4d  lea     rdx, [rbx+20h]
0x18002fc51  call    PASetInterfaceType
0x18002fc56  mov     ecx, [rbx]
0x18002fc58  lea     r8, [rbx+30h]
0x18002fc5c  lea     rdx, [r14+2Ch]
0x18002fc60  mov     qword ptr [rbx+24h], 0
0x18002fc68  call    PASetAddressForTunnel
0x18002fc6d  mov     ebp, eax
0x18002fc6f  test    eax, eax
0x18002fc71  jz      short loc_18002FC9E
0x18002fc73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc7a  lea     rdi, WPP_GLOBAL_Control
0x18002fc81  cmp     rcx, rdi
0x18002fc84  jz      loc_18002FECE
0x18002fc8a  test    byte ptr [rcx+1Ch], 10h
0x18002fc8e  jz      loc_18002FEA7
0x18002fc94  mov     edx, 15h
0x18002fc99  jmp     loc_18002FBAA
0x18002fc9e  mov     ecx, [rbx]
0x18002fca0  lea     r8, [rbx+50h]
0x18002fca4  lea     rdx, [r14+54h]
0x18002fca8  call    PASetAddressForTunnel
0x18002fcad  mov     ebp, eax
0x18002fcaf  test    eax, eax
0x18002fcb1  jz      short loc_18002FCDE
0x18002fcb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcba  lea     rdi, WPP_GLOBAL_Control
0x18002fcc1  cmp     rcx, rdi
0x18002fcc4  jz      loc_18002FECE
0x18002fcca  test    byte ptr [rcx+1Ch], 10h
0x18002fcce  jz      loc_18002FEA7
0x18002fcd4  mov     edx, 16h
0x18002fcd9  jmp     loc_18002FBAA
0x18002fcde  xorps   xmm0, xmm0
0x18002fce1  movups  xmmword ptr [rbx+88h], xmm0
0x18002fce8  movups  xmmword ptr [rbx+98h], xmm0
0x18002fcef  mov     dword ptr [rbx+88h], 8
0x18002fcf9  cmp     [rbx], r11d
0x18002fcfc  jnz     short loc_18002FD2A
0x18002fcfe  mov     eax, [rdi+38h]
0x18002fd01  mov     [rbx+0ACh], eax
0x18002fd07  cmp     [rdi+38h], r11d
0x18002fd0b  jz      short loc_18002FD21
0x18002fd0d  mov     dword ptr [rbx+0A8h], 1
0x18002fd17  mov     dword ptr [rbx+0B0h], 0FFFFFFFFh
0x18002fd21  mov     [rbx+0B8h], r11
0x18002fd28  jmp     short loc_18002FD6B
0x18002fd2a  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002fd2e  movdqu  xmmword ptr [rbx+0ACh], xmm0
0x18002fd36  mov     rax, [rdi+3Ch]
0x18002fd3a  sub     rax, cs:qword_180060990
0x18002fd41  jnz     short loc_18002FD4E
0x18002fd43  mov     rax, [rdi+44h]
0x18002fd47  sub     rax, cs:qword_180060998
0x18002fd4e  test    rax, rax
0x18002fd51  jz      short loc_18002FD64
0x18002fd53  mov     dword ptr [rbx+0A8h], 1
0x18002fd5d  mov     byte ptr [rbx+0BCh], 80h
0x18002fd64  mov     [rbx+0C0h], r11
0x18002fd6b  mov     dword ptr [rbx+70h], 1
0x18002fd72  cmp     [r14+8Ch], r11d
0x18002fd79  jz      short loc_18002FDD5
0x18002fd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd82  lea     rdi, WPP_GLOBAL_Control
0x18002fd89  cmp     rcx, rdi
0x18002fd8c  jz      short loc_18002FDB0
0x18002fd8e  test    byte ptr [rcx+1Ch], 10h
0x18002fd92  jz      short loc_18002FDB0
0x18002fd94  mov     rcx, [rcx+10h]
0x18002fd98  lea     r8, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids
0x18002fd9f  mov     edx, 17h
0x18002fda4  call    WPP_SF_
0x18002fda9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdb0  mov     r9d, 57h ; 'W'
0x18002fdb6  mov     ebp, r9d
0x18002fdb9  cmp     rcx, rdi
0x18002fdbc  jz      loc_18002FECE
0x18002fdc2  test    byte ptr [rcx+1Ch], 10h
0x18002fdc6  jz      loc_18002FEA7
0x18002fdcc  lea     edx, [r9-3Fh]
0x18002fdd0  jmp     loc_18002FE90
0x18002fdd5  mov     [rbx+74h], r11d
0x18002fdd9  mov     dword ptr [rbx+78h], 1
0x18002fde0  mov     [rbx+7Ch], r11w
0x18002fde5  mov     dword ptr [rbx+80h], 1
0x18002fdef  mov     [rbx+84h], r11w
0x18002fdf7  cmp     [r14+80h], r11w
0x18002fdff  jnz     short loc_18002FE43
0x18002fe01  cmp     [r14+88h], r11w
0x18002fe09  jnz     short loc_18002FE43
0x18002fe0b  lea     r8, [rbx+0CCh]
0x18002fe12  mov     rcx, r12
0x18002fe15  lea     rdx, [rbx+0C8h]
0x18002fe1c  call    SetFilterActions
0x18002fe21  mov     qword ptr [rbx+0D0h], 0
0x18002fe2c  xor     eax, eax
0x18002fe2e  movups  xmm0, xmmword ptr [r15]
0x18002fe32  movdqu  xmmword ptr [rbx+0D8h], xmm0
0x18002fe3a  mov     [r13+0], rbx
0x18002fe3e  jmp     loc_18002FEE3
0x18002fe43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe4a  lea     rdi, WPP_GLOBAL_Control
0x18002fe51  cmp     rcx, rdi
0x18002fe54  jz      short loc_18002FE78
0x18002fe56  test    byte ptr [rcx+1Ch], 10h
0x18002fe5a  jz      short loc_18002FE78
0x18002fe5c  mov     rcx, [rcx+10h]
0x18002fe60  lea     r8, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids
0x18002fe67  mov     edx, 19h
0x18002fe6c  call    WPP_SF_
0x18002fe71  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe78  mov     r9d, 57h ; 'W'
0x18002fe7e  mov     ebp, r9d
0x18002fe81  cmp     rcx, rdi
0x18002fe84  jz      short loc_18002FECE
0x18002fe86  test    byte ptr [rcx+1Ch], 10h
0x18002fe8a  jz      short loc_18002FEA7
0x18002fe8c  lea     edx, [r9-3Dh]
0x18002fe90  mov     rcx, [rcx+10h]
0x18002fe94  lea     r8, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids
0x18002fe9b  call    WPP_SF_d
0x18002fea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fea7  cmp     rcx, rdi
0x18002feaa  jz      short loc_18002FECE
0x18002feac  test    byte ptr [rcx+1Ch], 8
0x18002feb0  jz      short loc_18002FECE
0x18002feb2  mov     rcx, [rcx+10h]
0x18002feb6  lea     r8, WPP_e799bbcf81ba3a993b0d42457ba44b31_Traceguids
0x18002febd  mov     edx, 1Bh
0x18002fec2  mov     [rsp+298h+var_278], ebp
0x18002fec6  mov     r9, rsi
0x18002fec9  call    WPP_SF__guid_D
0x18002fece  xor     edi, edi
0x18002fed0  test    rbx, rbx
0x18002fed3  jz      short loc_18002FEDD
0x18002fed5  mov     rcx, rbx; lpMem
0x18002fed8  call    PAFreeTnFilter
0x18002fedd  mov     [r13+0], rdi
0x18002fee1  mov     eax, ebp
0x18002fee3  mov     rcx, [rsp+298h+var_58]
0x18002feeb  xor     rcx, rsp; StackCookie
0x18002feee  call    __security_check_cookie
0x18002fef3  add     rsp, 258h
0x18002fefa  pop     r15
0x18002fefc  pop     r14
0x18002fefe  pop     r13
0x18002ff00  pop     r12
0x18002ff02  pop     rdi
0x18002ff03  pop     rsi
0x18002ff04  pop     rbp
0x18002ff05  pop     rbx
0x18002ff06  retn
```
