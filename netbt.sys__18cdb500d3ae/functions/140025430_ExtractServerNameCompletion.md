# ExtractServerNameCompletion

- ea: `0x140025430`
- end: `0x140025714`
- name: `ExtractServerNameCompletion`
- size: `740`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140001ca0`
- `0x140006900`
- `0x140007c4c`
- `0x14000e268`
- `0x1400251c4`
- `0x140025430`
- `0x140028f44`
- `0x1400400a4`
- `0x14004025c`
- `0x140040294`

## pseudocode

```c
void __fastcall ExtractServerNameCompletion(__int64 a1, unsigned int a2)
{
  unsigned int v2; // esi
  __int64 v4; // r13
  unsigned int DestType; // r12d
  int v6; // r15d
  unsigned __int8 v7; // r14
  int v8; // r9d
  __int64 DeviceFromInterface; // rbp
  __int64 i; // r8
  char v11; // dl
  __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // r14
  __int64 v15; // r14
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-78h]
  int v19; // [rsp+28h] [rbp-70h]
  unsigned int v20; // [rsp+A8h] [rbp+10h]

  v2 = a2;
  if ( !a2 )
  {
    v4 = *(_QWORD *)(a1 + 104);
    v20 = *(_DWORD *)(a1 + 208);
    DestType = GetDestType();
    v6 = *(_DWORD *)(a1 + 240);
    v7 = *(_BYTE *)(*(_QWORD *)(a1 + 40) + 15LL);
    if ( DestType != 2 && (unsigned __int8)(v7 - 33) <= 0x5Du )
      v7 = 32;
    if ( (xmmword_140038420 & 0x40) != 0 )
      WPP_SF_d(1030, 39, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, DestType);
    v8 = 0;
    v2 = -1073741636;
    DeviceFromInterface = 0;
    while ( 2 )
    {
      for ( i = 0; (unsigned int)i < *(unsigned __int8 *)(v4 + 10); i = (unsigned int)(i + 1) )
      {
        v11 = *(_BYTE *)(v4 + 18 * i + 27);
        v12 = v4 + 11 + 18 * i;
        if ( (v11 & 0x18) == 0 && ((((unsigned __int8)~v11 >> 7) & ((v6 & 0x2000) != 0)) != 0 || (v6 & 0x5000) != 0) )
        {
          if ( DestType <= 1 )
          {
            if ( *(char *)(v12 + 15) == v7 )
            {
              if ( (*(_DWORD *)(a1 + 240) & 0x4000) != 0 )
              {
                if ( (xmmword_140038420 & 0x40) != 0 )
                  WPP_SF_(1030, 40, WPP_80b00531435b366d117ee6d697c26c58_Traceguids);
                *(_BYTE *)(v12 + 15) = 0;
              }
LABEL_26:
              LOBYTE(i) = 1;
              DeviceFromInterface = GetDeviceFromInterface(_byteswap_ulong(v20), *(_QWORD *)(a1 + 32), i);
              v2 = 0;
              v13 = *(_DWORD *)(a1 + 240);
              if ( (v13 & 0x8000) != 0 )
              {
                if ( (BYTE3(xmmword_140038420) & 2) == 0 )
                  goto LABEL_39;
                v16 = 44;
                v17 = 1049;
              }
              else
              {
                if ( (v13 & 0x2000) != 0 )
                {
                  *(_OWORD *)*(_QWORD *)(a1 + 80) = *(_OWORD *)v12;
                  *(_OWORD *)(*(_QWORD *)(a1 + 96) + 52LL) = *(_OWORD *)v12;
                  ConvertToHalfAscii(*(_QWORD *)(a1 + 64) + 4LL, v12, Str2, (unsigned __int16)word_1400395DC);
LABEL_39:
                  LockAndAddToHashTable((_DWORD)qword_140039468, v12, (_DWORD)Str2, v20, v18, v19);
                  goto LABEL_40;
                }
                if ( (v13 & 0x4000) == 0 )
                  goto LABEL_39;
                *(_OWORD *)*(_QWORD *)(a1 + 40) = *(_OWORD *)v12;
                v14 = *(_QWORD *)(a1 + 64) + 14LL;
                if ( (xmmword_140038420 & 0x40) != 0 )
                  WPP_SF_q(1030, 41, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, *(_QWORD *)(a1 + 64) + 14LL);
                v15 = (unsigned int)(unsigned __int16)word_1400395DC + 33 + v14;
                if ( (xmmword_140038420 & 0x40) != 0 )
                  WPP_SF_q(1030, 42, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, v15);
                ConvertToHalfAscii(v15, v12, Str2, (unsigned __int16)word_1400395DC);
                if ( (xmmword_140038420 & 0x40) == 0 )
                  goto LABEL_39;
                v16 = 43;
                v17 = 1030;
              }
              WPP_SF_(v17, v16, WPP_80b00531435b366d117ee6d697c26c58_Traceguids);
              goto LABEL_39;
            }
          }
          else if ( *(_BYTE *)(v12 + 15) == *(_BYTE *)(*(_QWORD *)(a1 + 40) + 15LL) )
          {
            goto LABEL_26;
          }
        }
      }
      if ( !v8 && (unsigned __int8)(v7 - 33) <= 0x5Du && *(_DWORD *)(a1 + 212) == 16 )
      {
        v8 = 1;
        v7 = 32;
        DestType = 1;
        continue;
      }
      break;
    }
LABEL_40:
    if ( DeviceFromInterface )
      NBT_DEREFERENCE_DEVICE(DeviceFromInterface, 10);
  }
  CompleteClientReq(*(void (__fastcall **)(_QWORD *, _QWORD))(a1 + 160), (_QWORD *)a1, v2);
}

```

## disassembly

```asm
0x140025430  push    rbx
0x140025432  push    rbp
0x140025433  push    rsi
0x140025434  push    rdi
0x140025435  push    r12
0x140025437  push    r13
0x140025439  push    r14
0x14002543b  push    r15
0x14002543d  sub     rsp, 58h
0x140025441  mov     esi, edx
0x140025443  mov     rbx, rcx
0x140025446  test    edx, edx
0x140025448  jnz     loc_1400256F0
0x14002544e  mov     eax, [rcx+0D0h]
0x140025454  mov     r13, [rcx+68h]
0x140025458  mov     [rsp+98h+arg_8], eax
0x14002545f  call    GetDestType
0x140025464  mov     rcx, [rbx+28h]
0x140025468  mov     r12d, eax
0x14002546b  mov     r15d, [rbx+0F0h]
0x140025472  movzx   r14d, byte ptr [rcx+0Fh]
0x140025477  lea     ecx, [rsi+20h]
0x14002547a  cmp     eax, 2
0x14002547d  jz      short loc_140025489
0x14002547f  lea     eax, [r14-21h]
0x140025483  cmp     al, 5Dh ; ']'
0x140025485  cmovbe  r14d, ecx
0x140025489  test    byte ptr cs:xmmword_140038420, 40h
0x140025490  jz      short loc_1400254AB
0x140025492  mov     edx, 27h ; '''
0x140025497  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x14002549e  mov     ecx, 406h
0x1400254a3  mov     r9d, r12d
0x1400254a6  call    WPP_SF_d
0x1400254ab  xor     r9d, r9d
0x1400254ae  mov     esi, 0C00000BCh
0x1400254b3  xor     ebp, ebp
0x1400254b5  movzx   r10d, byte ptr [r13+0Ah]
0x1400254ba  xor     r8d, r8d
0x1400254bd  cmp     r8d, r10d
0x1400254c0  jnb     short loc_140025517
0x1400254c2  lea     rcx, [r8+r8*8]
0x1400254c6  mov     dl, [r13+rcx*2+1Bh]
0x1400254cb  lea     rdi, [r13+0Bh]
0x1400254cf  lea     rdi, [rdi+rcx*2]
0x1400254d3  test    dl, 18h
0x1400254d6  jnz     short loc_140025512
0x1400254d8  not     dl
0x1400254da  shr     dl, 7
0x1400254dd  bt      r15d, 0Dh
0x1400254e2  setb    al
0x1400254e5  test    al, dl
0x1400254e7  jnz     short loc_1400254F2
0x1400254e9  test    r15d, 5000h
0x1400254f0  jz      short loc_140025512
0x1400254f2  cmp     r12d, 1
0x1400254f6  jbe     short loc_140025506
0x1400254f8  mov     rax, [rbx+28h]
0x1400254fc  mov     cl, [rax+0Fh]
0x1400254ff  cmp     [rdi+0Fh], cl
0x140025502  jnz     short loc_140025512
0x140025504  jmp     short loc_14002557B
0x140025506  movsx   ecx, byte ptr [rdi+0Fh]
0x14002550a  movzx   eax, r14b
0x14002550e  cmp     ecx, eax
0x140025510  jz      short loc_14002554C
0x140025512  inc     r8d
0x140025515  jmp     short loc_1400254BD
0x140025517  test    r9d, r9d
0x14002551a  jnz     loc_1400256DC
0x140025520  sub     r14b, 21h ; '!'
0x140025524  cmp     r14b, 5Dh ; ']'
0x140025528  ja      loc_1400256DC
0x14002552e  cmp     dword ptr [rbx+0D4h], 10h
0x140025535  jnz     loc_1400256DC
0x14002553b  mov     r9d, 1
0x140025541  mov     r14b, 20h ; ' '
0x140025544  mov     r12d, r9d
0x140025547  jmp     loc_1400254B5
0x14002554c  test    dword ptr [rbx+0F0h], 4000h
0x140025556  jz      short loc_14002557B
0x140025558  test    byte ptr cs:xmmword_140038420, 40h
0x14002555f  jz      short loc_140025577
0x140025561  mov     edx, 28h ; '('
0x140025566  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x14002556d  mov     ecx, 406h
0x140025572  call    WPP_SF_
0x140025577  mov     [rdi+0Fh], bpl
0x14002557b  mov     r12d, [rsp+98h+arg_8]
0x140025583  mov     r8b, 1
0x140025586  mov     rdx, [rbx+20h]
0x14002558a  mov     ecx, r12d
0x14002558d  bswap   ecx
0x14002558f  call    GetDeviceFromInterface
0x140025594  mov     rbp, rax
0x140025597  xor     esi, esi
0x140025599  mov     eax, [rbx+0F0h]
0x14002559f  bt      eax, 0Fh
0x1400255a3  jb      loc_14002568A
0x1400255a9  bt      eax, 0Dh
0x1400255ad  jnb     short loc_1400255EA
0x1400255af  mov     rax, [rbx+50h]
0x1400255b3  mov     rdx, rdi
0x1400255b6  movups  xmm0, xmmword ptr [rdi]
0x1400255b9  movdqu  xmmword ptr [rax], xmm0
0x1400255bd  mov     rax, [rbx+60h]
0x1400255c1  movups  xmm1, xmmword ptr [rdi]
0x1400255c4  movdqu  xmmword ptr [rax+34h], xmm1
0x1400255c9  mov     rcx, [rbx+40h]
0x1400255cd  movzx   r9d, cs:word_1400395DC
0x1400255d5  add     rcx, 4
0x1400255d9  mov     r8, cs:Str2
0x1400255e0  call    ConvertToHalfAscii
0x1400255e5  jmp     loc_1400256A9
0x1400255ea  bt      eax, 0Eh
0x1400255ee  jnb     loc_1400256A9
0x1400255f4  mov     rax, [rbx+28h]
0x1400255f8  movups  xmm0, xmmword ptr [rdi]
0x1400255fb  movdqu  xmmword ptr [rax], xmm0
0x1400255ff  mov     r14, [rbx+40h]
0x140025603  add     r14, 0Eh
0x140025607  mov     r13b, 40h ; '@'
0x14002560a  test    byte ptr cs:xmmword_140038420, r13b
0x140025611  jz      short loc_14002562C
0x140025613  mov     edx, 29h ; ')'
0x140025618  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x14002561f  mov     ecx, 406h
0x140025624  mov     r9, r14
0x140025627  call    WPP_SF_q
0x14002562c  movzx   eax, cs:word_1400395DC
0x140025633  add     eax, 21h ; '!'
0x140025636  add     r14, rax
0x140025639  test    byte ptr cs:xmmword_140038420, r13b
0x140025640  jz      short loc_14002565B
0x140025642  mov     edx, 2Ah ; '*'
0x140025647  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x14002564e  mov     ecx, 406h
0x140025653  mov     r9, r14
0x140025656  call    WPP_SF_q
0x14002565b  movzx   r9d, cs:word_1400395DC
0x140025663  mov     rdx, rdi
0x140025666  mov     r8, cs:Str2
0x14002566d  mov     rcx, r14
0x140025670  call    ConvertToHalfAscii
0x140025675  test    byte ptr cs:xmmword_140038420, r13b
0x14002567c  jz      short loc_1400256A9
0x14002567e  mov     edx, 2Bh ; '+'
0x140025683  mov     ecx, 406h
0x140025688  jmp     short loc_14002569D
0x14002568a  test    byte ptr cs:xmmword_140038420+3, 2
0x140025691  jz      short loc_1400256A9
0x140025693  mov     edx, 2Ch ; ','
0x140025698  mov     ecx, 419h
0x14002569d  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x1400256a4  call    WPP_SF_
0x1400256a9  mov     r8, cs:Str2
0x1400256b0  mov     r9d, r12d
0x1400256b3  mov     rcx, cs:qword_140039468
0x1400256ba  mov     rdx, rdi
0x1400256bd  shr     r15d, 4
0x1400256c1  and     r15w, 8
0x1400256c6  or      r15w, 100h
0x1400256cc  mov     [rsp+98h+var_58], r15w
0x1400256d2  mov     [rsp+98h+var_60], rbp
0x1400256d7  call    LockAndAddToHashTable
0x1400256dc  test    rbp, rbp
0x1400256df  jz      short loc_1400256F0
0x1400256e1  xor     r8d, r8d
0x1400256e4  mov     rcx, rbp
0x1400256e7  lea     edx, [r8+0Ah]
0x1400256eb  call    NBT_DEREFERENCE_DEVICE
0x1400256f0  mov     rcx, [rbx+0A0h]
0x1400256f7  mov     r8d, esi
0x1400256fa  mov     rdx, rbx
0x1400256fd  call    CompleteClientReq
0x140025702  add     rsp, 58h
0x140025706  pop     r15
0x140025708  pop     r14
0x14002570a  pop     r13
0x14002570c  pop     r12
0x14002570e  pop     rdi
0x14002570f  pop     rsi
0x140025710  pop     rbp
0x140025711  pop     rbx
0x140025712  retn
```
