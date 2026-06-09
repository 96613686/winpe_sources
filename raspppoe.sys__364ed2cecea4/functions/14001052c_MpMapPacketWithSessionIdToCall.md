# MpMapPacketWithSessionIdToCall

- ea: `0x14001052c`
- end: `0x14001070b`
- name: `MpMapPacketWithSessionIdToCall`
- size: `479`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400108d4`
- `0x140010e50`

## callees

- `0x1400024dc`
- `0x140002574`
- `0x14001052c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400106b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010580`

## pseudocode

```c
__int64 __fastcall MpMapPacketWithSessionIdToCall(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  __int16 v6; // r10
  unsigned int v7; // edx
  __int64 v8; // r11
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx

  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x72u,
      (__int64)WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids,
      a2);
  }
  *(_BYTE *)(a1 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v5 = *(_QWORD *)(a2 + 112);
  v6 = __ROR2__(*(_WORD *)(v5 + 16), 8);
  if ( *(_BYTE *)(a1 + 152) )
  {
    v7 = *(_DWORD *)(a1 + 676) * *(_DWORD *)(a1 + 680);
    if ( v7 )
    {
      v8 = *(_QWORD *)(a1 + 96);
      v9 = 0;
      while ( 1 )
      {
        if ( v8 )
        {
          if ( (unsigned int)(unsigned __int16)v9 < *(_DWORD *)(v8 + 8) )
          {
            if ( *(_BYTE *)(*(_QWORD *)v8 + 24LL * (unsigned __int16)v9) )
            {
              v10 = *(_QWORD *)(*(_QWORD *)v8 + 24LL * (unsigned __int16)v9 + 8);
              if ( v10 )
              {
                if ( *(_WORD *)(v10 + 722) == v6
                  && *(_DWORD *)(v10 + 715) == *(_DWORD *)v5
                  && *(_WORD *)(v10 + 719) == *(_WORD *)(v5 + 4)
                  && *(_DWORD *)(v10 + 709) == *(_DWORD *)(v5 + 6)
                  && *(_WORD *)(v10 + 713) == *(_WORD *)(v5 + 10) )
                {
                  break;
                }
              }
            }
          }
        }
        if ( ++v9 >= v7 )
          goto LABEL_30;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 24));
      v4 = v10;
    }
  }
  else
  {
    v11 = *(_QWORD *)(a1 + 96);
    if ( v11 )
    {
      v12 = (unsigned __int16)(v6 - 1);
      if ( (unsigned int)v12 < *(_DWORD *)(v11 + 8) )
      {
        v13 = 3 * v12;
        if ( *(_BYTE *)(*(_QWORD *)v11 + 8 * v13) )
        {
          v14 = *(_QWORD *)(*(_QWORD *)v11 + 8 * v13 + 8);
          if ( v14 )
          {
            if ( *(_WORD *)(v14 + 722) == v6
              && *(_DWORD *)(v14 + 715) == *(_DWORD *)v5
              && *(_WORD *)(v14 + 719) == *(_WORD *)(v5 + 4)
              && *(_DWORD *)(v14 + 709) == *(_DWORD *)(v5 + 6)
              && *(_WORD *)(v14 + 713) == *(_WORD *)(v5 + 10) )
            {
              _InterlockedIncrement((volatile signed __int32 *)(v14 + 24));
              v4 = v14;
            }
          }
        }
      }
    }
  }
LABEL_30:
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a2, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001052c  push    rbx
0x14001052e  push    rbp
0x14001052f  push    rsi
0x140010530  push    rdi
0x140010531  push    r12
0x140010533  push    r15
0x140010535  sub     rsp, 38h
0x140010539  mov     rsi, rdx
0x14001053c  mov     rbx, rcx
0x14001053f  xor     edi, edi
0x140010541  mov     rcx, cs:WPP_GLOBAL_Control
0x140010548  lea     r12, WPP_GLOBAL_Control
0x14001054f  lea     r15d, [rdi+1]
0x140010553  cmp     rcx, r12
0x140010556  jz      short loc_14001057C
0x140010558  mov     eax, [rcx+2Ch]
0x14001055b  test    r15b, al
0x14001055e  jz      short loc_14001057C
0x140010560  cmp     byte ptr [rcx+29h], 4
0x140010564  jb      short loc_14001057C
0x140010566  mov     rcx, [rcx+18h]
0x14001056a  lea     edx, [rdi+72h]
0x14001056d  mov     r9, rsi
0x140010570  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140010577  call    WPP_SF_q
0x14001057c  lea     rcx, [rbx+8]; SpinLock
0x140010580  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010587  nop     dword ptr [rax+rax+00h]
0x14001058c  mov     [rbx+10h], al
0x14001058f  mov     r8, [rsi+70h]
0x140010593  movzx   r10d, word ptr [r8+10h]
0x140010598  ror     r10w, 8
0x14001059d  cmp     [rbx+98h], dil
0x1400105a4  jz      loc_14001063C
0x1400105aa  mov     edx, [rbx+2A8h]
0x1400105b0  imul    edx, [rbx+2A4h]
0x1400105b7  test    edx, edx
0x1400105b9  jz      loc_1400106B0
0x1400105bf  mov     r11, [rbx+60h]
0x1400105c3  xor     r9d, r9d
0x1400105c6  test    r11, r11
0x1400105c9  jz      short loc_140010629
0x1400105cb  movzx   eax, r9w
0x1400105cf  cmp     eax, [r11+8]
0x1400105d3  jnb     short loc_140010629
0x1400105d5  lea     rcx, [rax+rax*2]
0x1400105d9  mov     rax, [r11]
0x1400105dc  cmp     [rax+rcx*8], dil
0x1400105e0  jz      short loc_140010629
0x1400105e2  mov     rcx, [rax+rcx*8+8]
0x1400105e7  test    rcx, rcx
0x1400105ea  jz      short loc_140010629
0x1400105ec  cmp     [rcx+2D2h], r10w
0x1400105f4  jnz     short loc_140010629
0x1400105f6  mov     eax, [rcx+2CBh]
0x1400105fc  cmp     eax, [r8]
0x1400105ff  jnz     short loc_140010629
0x140010601  movzx   eax, word ptr [rcx+2CFh]
0x140010608  cmp     ax, [r8+4]
0x14001060d  jnz     short loc_140010629
0x14001060f  mov     eax, [rcx+2C5h]
0x140010615  cmp     eax, [r8+6]
0x140010619  jnz     short loc_140010629
0x14001061b  movzx   eax, word ptr [rcx+2C9h]
0x140010622  cmp     ax, [r8+0Ah]
0x140010627  jz      short loc_140010633
0x140010629  add     r9d, r15d
0x14001062c  cmp     r9d, edx
0x14001062f  jb      short loc_1400105C6
0x140010631  jmp     short loc_1400106B0
0x140010633  lock inc dword ptr [rcx+18h]
0x140010637  mov     rdi, rcx
0x14001063a  jmp     short loc_1400106B0
0x14001063c  mov     rcx, [rbx+60h]
0x140010640  test    rcx, rcx
0x140010643  jz      short loc_1400106B0
0x140010645  movzx   eax, r10w
0x140010649  sub     ax, r15w
0x14001064d  movzx   edx, ax
0x140010650  cmp     edx, [rcx+8]
0x140010653  jnb     short loc_1400106B0
0x140010655  mov     rax, [rcx]
0x140010658  lea     rdx, [rdx+rdx*2]
0x14001065c  cmp     [rax+rdx*8], dil
0x140010660  jz      short loc_1400106B0
0x140010662  mov     rdx, [rax+rdx*8+8]
0x140010667  test    rdx, rdx
0x14001066a  jz      short loc_1400106B0
0x14001066c  cmp     [rdx+2D2h], r10w
0x140010674  jnz     short loc_1400106B0
0x140010676  mov     eax, [rdx+2CBh]
0x14001067c  cmp     eax, [r8]
0x14001067f  jnz     short loc_1400106B0
0x140010681  movzx   eax, word ptr [rdx+2CFh]
0x140010688  cmp     ax, [r8+4]
0x14001068d  jnz     short loc_1400106B0
0x14001068f  mov     eax, [rdx+2C5h]
0x140010695  cmp     eax, [r8+6]
0x140010699  jnz     short loc_1400106B0
0x14001069b  movzx   eax, word ptr [rdx+2C9h]
0x1400106a2  cmp     ax, [r8+0Ah]
0x1400106a7  jnz     short loc_1400106B0
0x1400106a9  lock inc dword ptr [rdx+18h]
0x1400106ad  mov     rdi, rdx
0x1400106b0  mov     dl, [rbx+10h]; NewIrql
0x1400106b3  lea     rcx, [rbx+8]; SpinLock
0x1400106b7  call    cs:__imp_KeReleaseSpinLock
0x1400106be  nop     dword ptr [rax+rax+00h]
0x1400106c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106ca  cmp     rcx, r12
0x1400106cd  jz      short loc_1400106FA
0x1400106cf  mov     edx, [rcx+2Ch]
0x1400106d2  test    r15b, dl
0x1400106d5  jz      short loc_1400106FA
0x1400106d7  cmp     byte ptr [rcx+29h], 4
0x1400106db  jb      short loc_1400106FA
0x1400106dd  mov     rcx, [rcx+18h]
0x1400106e1  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400106e8  mov     edx, 73h ; 's'
0x1400106ed  mov     [rsp+68h+var_48], rdi
0x1400106f2  mov     r9, rsi
0x1400106f5  call    WPP_SF_qq
0x1400106fa  mov     rax, rdi
0x1400106fd  add     rsp, 38h
0x140010701  pop     r15
0x140010703  pop     r12
0x140010705  pop     rdi
0x140010706  pop     rsi
0x140010707  pop     rbp
0x140010708  pop     rbx
0x140010709  retn
```
