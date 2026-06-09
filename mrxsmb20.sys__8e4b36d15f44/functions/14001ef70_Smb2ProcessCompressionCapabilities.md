# Smb2ProcessCompressionCapabilities

- ea: `0x14001ef70`
- end: `0x14001f316`
- name: `Smb2ProcessCompressionCapabilities`
- size: `934`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140056aa0`
- `0x140056c30`

## callees

- `0x14001ef70`
- `0x140028000`
- `0x140028950`
- `0x1400297fc`
- `0x14002a9ac`
- `0x14002ccb4`

## import_xrefs

- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14001ef86`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14001ef86`

## pseudocode

```c
__int64 __fastcall Smb2ProcessCompressionCapabilities(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        _DWORD *a4,
        __int64 a5)
{
  unsigned __int64 v6; // rsi
  __int64 CompressionConfigBlock; // r11
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r10d
  __int64 i; // rax
  __int64 j; // rdx
  unsigned int v16; // ebx
  int v17; // edx

  v6 = a3;
  CompressionConfigBlock = MRxSmbGetCompressionConfigBlock();
  if ( (*(_BYTE *)(CompressionConfigBlock + 26) & 2) == 0 || *(_BYTE *)(a1 + 605) )
  {
    if ( (*a4 & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
      }
      Smb2LkmdTelCollectParsingFailure(a5, 0, 21);
      return 3221225667LL;
    }
    else
    {
      *a4 |= 4u;
      if ( (unsigned int)v6 < 0xA )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
        }
        Smb2LkmdTelCollectParsingFailure(a5, 0, 22);
        return 3221225667LL;
      }
      else
      {
        v10 = *a2;
        if ( *a2 )
        {
          if ( 2 * v10 + 8 > v6 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
            }
            Smb2LkmdTelCollectParsingFailure(a5, 0, 24);
            return 3221225667LL;
          }
          else
          {
            v11 = 0;
            v12 = 0;
            if ( (_WORD)v10 != 1 || a2[4] )
            {
              for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
              {
                v16 = a2[i + 4];
                if ( !a2[i + 4] || v16 >= 0x20 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_Hq(WPP_GLOBAL_Control->AttachedDevice, 21, v11, (unsigned __int16)v16, a1);
                  }
                  Smb2LkmdTelCollectParsingFailure(a5, 0, 25);
                  return 3221225667LL;
                }
                v17 = 1 << (v16 - 1);
                if ( (v17 & (unsigned int)v11) != 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_Hq(WPP_GLOBAL_Control->AttachedDevice, 22, v11, (unsigned __int16)v16, a1);
                  }
                  Smb2LkmdTelCollectParsingFailure(a5, 0, 26);
                  return 3221225667LL;
                }
                v11 = v17 | (unsigned int)v11;
              }
              if ( (~*(_DWORD *)(CompressionConfigBlock + 20) & (unsigned int)v11) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    23,
                    WPP_48214901e2dc3d654588515547715784_Traceguids,
                    a1,
                    *(_DWORD *)(CompressionConfigBlock + 20),
                    v11);
                }
                Smb2LkmdTelCollectParsingFailure(a5, 0, 27);
                return 3221225667LL;
              }
              for ( j = 0; (unsigned int)j < *(unsigned __int16 *)(CompressionConfigBlock + 24); j = (unsigned int)(j + 1) )
              {
                if ( _bittest((const int *)&v11, (unsigned __int8)(*(_DWORD *)(CompressionConfigBlock + 4 * j) - 1)) )
                {
                  v12 = *(_DWORD *)(CompressionConfigBlock + 4 * j);
                  break;
                }
              }
            }
            *(_DWORD *)(a1 + 592) = v11;
            *(_DWORD *)(a1 + 588) = v12;
            if ( (a2[2] & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_48214901e2dc3d654588515547715784_Traceguids);
              }
              *(_BYTE *)(a1 + 596) = 1;
            }
            return 0;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
          }
          Smb2LkmdTelCollectParsingFailure(a5, 0, 23);
          return 3221225667LL;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_48214901e2dc3d654588515547715784_Traceguids, a1);
    }
    Smb2LkmdTelCollectParsingFailure(a5, 0, 20);
    return 3221225667LL;
  }
}

```

## disassembly

```asm
0x14001ef70  push    rbx
0x14001ef72  push    rsi
0x14001ef73  push    rdi
0x14001ef74  push    r14
0x14001ef76  sub     rsp, 38h
0x14001ef7a  mov     rbx, r9
0x14001ef7d  mov     esi, r8d
0x14001ef80  mov     r14, rdx
0x14001ef83  mov     rdi, rcx
0x14001ef86  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x14001ef8d  nop     dword ptr [rax+rax+00h]
0x14001ef92  mov     r11, rax
0x14001ef95  test    byte ptr [rax+1Ah], 2
0x14001ef99  jnz     loc_14003C0EA
0x14001ef9f  mov     eax, [rbx]
0x14001efa1  test    al, 4
0x14001efa3  jnz     loc_14001F123
0x14001efa9  or      eax, 4
0x14001efac  mov     [rbx], eax
0x14001efae  cmp     esi, 0Ah
0x14001efb1  jb      loc_14001F16D
0x14001efb7  movzx   edx, word ptr [r14]
0x14001efbb  cmp     edx, 1
0x14001efbe  jb      loc_14001F1B7
0x14001efc4  lea     rcx, ds:8[rdx*2]
0x14001efcc  cmp     rcx, rsi
0x14001efcf  ja      loc_14001F201
0x14001efd5  xor     r8d, r8d
0x14001efd8  xor     r10d, r10d
0x14001efdb  mov     esi, 1
0x14001efe0  cmp     si, dx
0x14001efe3  jz      loc_14001F24B
0x14001efe9  xor     eax, eax
0x14001efeb  mov     r9d, edx
0x14001efee  cmp     eax, r9d
0x14001eff1  jb      short loc_14001F06E
0x14001eff3  mov     r9d, [r11+14h]
0x14001eff7  mov     eax, r9d
0x14001effa  not     eax
0x14001effc  test    r8d, eax
0x14001efff  jnz     loc_14001F0CD
0x14001f005  movzx   ebx, word ptr [r11+18h]
0x14001f00a  xor     edx, edx
0x14001f00c  cmp     edx, ebx
0x14001f00e  jnb     short loc_14001F028
0x14001f010  mov     r9d, [r11+rdx*4]
0x14001f014  lea     ecx, [r9-1]
0x14001f018  movzx   eax, cl
0x14001f01b  bt      r8d, eax
0x14001f01f  jnb     loc_14001F0C6
0x14001f025  mov     r10d, r9d
0x14001f028  mov     [rdi+250h], r8d
0x14001f02f  mov     [rdi+24Ch], r10d
0x14001f036  test    [r14+4], sil
0x14001f03a  jz      short loc_14001F061
0x14001f03c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f043  lea     rax, WPP_GLOBAL_Control
0x14001f04a  cmp     rcx, rax
0x14001f04d  jz      short loc_14001F05A
0x14001f04f  mov     eax, [rcx+2Ch]
0x14001f052  test    al, 4
0x14001f054  jnz     loc_14001F2F2
0x14001f05a  mov     [rdi+254h], sil
0x14001f061  xor     eax, eax
0x14001f063  add     rsp, 38h
0x14001f067  pop     r14
0x14001f069  pop     rdi
0x14001f06a  pop     rsi
0x14001f06b  pop     rbx
0x14001f06c  retn
0x14001f06e  movzx   ebx, word ptr [r14+rax*2+8]
0x14001f074  test    ebx, ebx
0x14001f076  jnz     loc_14001F25D
0x14001f07c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f083  lea     rax, WPP_GLOBAL_Control
0x14001f08a  cmp     rcx, rax
0x14001f08d  jz      loc_14003C1E9
0x14001f093  mov     eax, [rcx+2Ch]
0x14001f096  test    sil, al
0x14001f099  jz      loc_14003C1E9
0x14001f09f  cmp     [rcx+29h], sil
0x14001f0a3  jb      loc_14003C1E9
0x14001f0a9  mov     rcx, [rcx+18h]
0x14001f0ad  mov     edx, 15h
0x14001f0b2  movzx   r9d, bx
0x14001f0b6  mov     [rsp+58h+var_38], rdi
0x14001f0bb  call    WPP_SF_Hq
0x14001f0c0  nop
0x14001f0c1  jmp     loc_14003C1E9
0x14001f0c6  inc     edx
0x14001f0c8  jmp     loc_14001F00C
0x14001f0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0d4  lea     rax, WPP_GLOBAL_Control
0x14001f0db  cmp     rcx, rax
0x14001f0de  jnz     loc_14001F2B5
0x14001f0e4  mov     rcx, [rsp+58h+arg_20]
0x14001f0ec  xor     edx, edx
0x14001f0ee  mov     r8d, 1Bh
0x14001f0f4  call    Smb2LkmdTelCollectParsingFailure
0x14001f0f9  mov     eax, 0C00000C3h
0x14001f0fe  add     rsp, 38h
0x14001f102  pop     r14
0x14001f104  pop     rdi
0x14001f105  pop     rsi
0x14001f106  pop     rbx
0x14001f107  retn
0x14001f109  lea     ecx, [rbx-1]
0x14001f10c  mov     edx, esi
0x14001f10e  shl     edx, cl
0x14001f110  test    r8d, edx
0x14001f113  jnz     loc_14001F26B
0x14001f119  or      r8d, edx
0x14001f11c  inc     eax
0x14001f11e  jmp     loc_14001EFEE
0x14001f123  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f12a  lea     rax, WPP_GLOBAL_Control
0x14001f131  cmp     rcx, rax
0x14001f134  jz      loc_14003C14E
0x14001f13a  mov     eax, [rcx+2Ch]
0x14001f13d  test    al, 1
0x14001f13f  jz      loc_14003C14E
0x14001f145  cmp     byte ptr [rcx+29h], 1
0x14001f149  jb      loc_14003C14E
0x14001f14f  mov     rcx, [rcx+18h]
0x14001f153  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f15a  mov     edx, 11h
0x14001f15f  mov     r9, rdi
0x14001f162  call    WPP_SF_q
0x14001f167  nop
0x14001f168  jmp     loc_14003C14E
0x14001f16d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f174  lea     rax, WPP_GLOBAL_Control
0x14001f17b  cmp     rcx, rax
0x14001f17e  jz      loc_14003C16D
0x14001f184  mov     eax, [rcx+2Ch]
0x14001f187  test    al, 1
0x14001f189  jz      loc_14003C16D
0x14001f18f  cmp     byte ptr [rcx+29h], 1
0x14001f193  jb      loc_14003C16D
0x14001f199  mov     rcx, [rcx+18h]
0x14001f19d  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f1a4  mov     edx, 12h
0x14001f1a9  mov     r9, rdi
0x14001f1ac  call    WPP_SF_q
0x14001f1b1  nop
0x14001f1b2  jmp     loc_14003C16D
0x14001f1b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1be  lea     rax, WPP_GLOBAL_Control
0x14001f1c5  cmp     rcx, rax
0x14001f1c8  jz      loc_14003C18C
0x14001f1ce  mov     eax, [rcx+2Ch]
0x14001f1d1  test    al, 1
0x14001f1d3  jz      loc_14003C18C
0x14001f1d9  cmp     byte ptr [rcx+29h], 1
0x14001f1dd  jb      loc_14003C18C
0x14001f1e3  mov     rcx, [rcx+18h]
0x14001f1e7  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f1ee  mov     edx, 13h
0x14001f1f3  mov     r9, rdi
0x14001f1f6  call    WPP_SF_q
0x14001f1fb  nop
0x14001f1fc  jmp     loc_14003C18C
0x14001f201  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f208  lea     rax, WPP_GLOBAL_Control
0x14001f20f  cmp     rcx, rax
0x14001f212  jz      loc_14003C1AB
0x14001f218  mov     eax, [rcx+2Ch]
0x14001f21b  test    al, 1
0x14001f21d  jz      loc_14003C1AB
0x14001f223  cmp     byte ptr [rcx+29h], 1
0x14001f227  jb      loc_14003C1AB
0x14001f22d  mov     rcx, [rcx+18h]
0x14001f231  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f238  mov     edx, 14h
0x14001f23d  mov     r9, rdi
0x14001f240  call    WPP_SF_q
0x14001f245  nop
0x14001f246  jmp     loc_14003C1AB
0x14001f24b  xor     eax, eax
0x14001f24d  cmp     ax, [r14+8]
0x14001f252  jz      loc_14001F028
0x14001f258  jmp     loc_14001EFE9
0x14001f25d  cmp     ebx, 20h ; ' '
0x14001f260  jnb     loc_14001F07C
0x14001f266  jmp     loc_14001F109
0x14001f26b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f272  lea     rax, WPP_GLOBAL_Control
0x14001f279  cmp     rcx, rax
0x14001f27c  jz      loc_14003C1CA
0x14001f282  mov     eax, [rcx+2Ch]
0x14001f285  test    sil, al
0x14001f288  jz      loc_14003C1CA
0x14001f28e  cmp     [rcx+29h], sil
0x14001f292  jb      loc_14003C1CA
0x14001f298  mov     rcx, [rcx+18h]
0x14001f29c  mov     edx, 16h
0x14001f2a1  movzx   r9d, bx
0x14001f2a5  mov     [rsp+58h+var_38], rdi
0x14001f2aa  call    WPP_SF_Hq
0x14001f2af  nop
0x14001f2b0  jmp     loc_14003C1CA
0x14001f2b5  mov     eax, [rcx+2Ch]
0x14001f2b8  test    sil, al
0x14001f2bb  jz      loc_14001F0E4
0x14001f2c1  cmp     [rcx+29h], sil
0x14001f2c5  jb      loc_14001F0E4
0x14001f2cb  mov     rcx, [rcx+18h]
0x14001f2cf  mov     edx, 17h
0x14001f2d4  mov     [rsp+58h+var_30], r8d
0x14001f2d9  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f2e0  mov     dword ptr [rsp+58h+var_38], r9d
0x14001f2e5  mov     r9, rdi
0x14001f2e8  call    WPP_SF_qDD
0x14001f2ed  jmp     loc_14001F0E4
0x14001f2f2  cmp     byte ptr [rcx+29h], 4
0x14001f2f6  jb      loc_14001F05A
0x14001f2fc  mov     rcx, [rcx+18h]
0x14001f300  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14001f307  mov     edx, 18h
0x14001f30c  call    WPP_SF_
0x14001f311  jmp     loc_14001F05A
0x14003c0ea  cmp     byte ptr [rdi+25Dh], 0
0x14003c0f1  jnz     loc_14001EF9F
0x14003c0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c0fe  lea     rax, WPP_GLOBAL_Control
0x14003c105  cmp     rcx, rax
0x14003c108  jz      short loc_14003C12F
0x14003c10a  mov     eax, [rcx+2Ch]
0x14003c10d  test    al, 1
0x14003c10f  jz      short loc_14003C12F
0x14003c111  cmp     byte ptr [rcx+29h], 1
0x14003c115  jb      short loc_14003C12F
0x14003c117  mov     rcx, [rcx+18h]
0x14003c11b  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14003c122  mov     edx, 10h
0x14003c127  mov     r9, rdi
0x14003c12a  call    WPP_SF_q
0x14003c12f  mov     rcx, [rsp+58h+arg_20]
0x14003c137  xor     edx, edx
0x14003c139  mov     r8d, 14h
0x14003c13f  call    Smb2LkmdTelCollectParsingFailure
0x14003c144  mov     eax, 0C00000C3h
0x14003c149  jmp     loc_14001F063
0x14003c14e  mov     rcx, [rsp+58h+arg_20]
0x14003c156  xor     edx, edx
0x14003c158  mov     r8d, 15h
0x14003c15e  call    Smb2LkmdTelCollectParsingFailure
0x14003c163  mov     eax, 0C00000C3h
0x14003c168  jmp     loc_14001F063
0x14003c16d  mov     rcx, [rsp+58h+arg_20]
0x14003c175  xor     edx, edx
0x14003c177  mov     r8d, 16h
0x14003c17d  call    Smb2LkmdTelCollectParsingFailure
0x14003c182  mov     eax, 0C00000C3h
0x14003c187  jmp     loc_14001F063
0x14003c18c  mov     rcx, [rsp+58h+arg_20]
0x14003c194  xor     edx, edx
0x14003c196  mov     r8d, 17h
0x14003c19c  call    Smb2LkmdTelCollectParsingFailure
0x14003c1a1  mov     eax, 0C00000C3h
0x14003c1a6  jmp     loc_14001F063
0x14003c1ab  mov     rcx, [rsp+58h+arg_20]
0x14003c1b3  xor     edx, edx
0x14003c1b5  mov     r8d, 18h
0x14003c1bb  call    Smb2LkmdTelCollectParsingFailure
0x14003c1c0  mov     eax, 0C00000C3h
0x14003c1c5  jmp     loc_14001F063
0x14003c1ca  mov     rcx, [rsp+58h+arg_20]
0x14003c1d2  xor     edx, edx
0x14003c1d4  mov     r8d, 1Ah
0x14003c1da  call    Smb2LkmdTelCollectParsingFailure
0x14003c1df  mov     eax, 0C00000C3h
0x14003c1e4  jmp     loc_14001F063
0x14003c1e9  mov     rcx, [rsp+58h+arg_20]
0x14003c1f1  xor     edx, edx
0x14003c1f3  mov     r8d, 19h
0x14003c1f9  call    Smb2LkmdTelCollectParsingFailure
0x14003c1fe  mov     eax, 0C00000C3h
0x14003c203  jmp     loc_14001F063
```
