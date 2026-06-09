# ClasspReceivePopulateTokenInformation

- ea: `0x1400206f8`
- end: `0x140020a56`
- name: `ClasspReceivePopulateTokenInformation`
- size: `862`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400252a0`

## callees

- `0x140002230`
- `0x140004950`
- `0x14001fc38`
- `0x1400206f8`
- `0x140020a5c`
- `0x140022668`
- `0x140023d08`
- `0x14003e640`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14002086f`
- `ntoskrnl!IoFreeIrp` at `0x14002086f`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140020856`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140020856`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140020835`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140020835`

## pseudocode

```c
NTSTATUS __fastcall ClasspReceivePopulateTokenInformation(_QWORD *P)
{
  size_t v1; // rbp
  __int64 v3; // rdi
  _OWORD *v4; // rsi
  int v5; // r15d
  int v6; // r12d
  PSLIST_ENTRY v7; // rax
  __int64 v8; // r13
  char *v10; // rbp
  IRP *v11; // rcx
  char *v12; // rbp
  __int64 v13; // rdx
  char v14; // si
  unsigned __int8 v15; // r10
  unsigned int v16; // ebx
  unsigned int v17; // r11d
  char v18; // di
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  int v22; // ecx
  int v23; // ecx
  const void *v24; // r9
  unsigned int v25; // edi
  unsigned int v26; // ebx
  char v27; // si
  __int64 v28; // rcx
  unsigned __int64 v29; // r11
  __int64 v30; // r8
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // r9

  v1 = *((unsigned int *)P + 62);
  v3 = *P;
  v4 = (_OWORD *)P[1];
  v5 = *((_DWORD *)P + 64);
  v6 = *((_DWORD *)P + 63);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 242, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v3, v4);
  }
  P[34] = 0;
  v7 = DequeueFreeTransferPacket(v3);
  v8 = (__int64)v7;
  if ( v7 )
  {
    P[29] = v7;
    memset(P + 48, 0, v1);
    *((_BYTE *)P + 387) = v5 - 4;
    v10 = (char *)(P + 2);
    *((_BYTE *)P + 386) = (unsigned __int16)(v5 - 4) >> 8;
    *((_BYTE *)P + 384) = (unsigned int)(v5 - 4) >> 24;
    *((_BYTE *)P + 385) = (unsigned int)(v5 - 4) >> 16;
    memset(P + 2, 0, 0xD0u);
    v11 = (IRP *)P[28];
    if ( !v11 )
      goto LABEL_18;
    if ( ClassPnPETWEnabled )
    {
      if ( (int)IoGetActivityIdIrp(v4, v8 + 328) < 0 )
        *(_OWORD *)(v8 + 328) = *v4;
      if ( (int)IoSetActivityIdIrp(P[28], v8 + 328) >= 0 )
      {
LABEL_18:
        if ( P[28] )
          v10 = (char *)P[28];
        *((_DWORD *)v10 + 12) = 0;
        *((_QWORD *)v10 + 7) = 0;
        *((_QWORD *)v10 + 15) = 1;
        *((_QWORD *)v10 + 1) = P[30];
        ClasspSetupReceivePopulateTokenInformationTransferPacket((_DWORD)P, v8, v5, (_DWORD)P + 384, (__int64)v10, v6);
        v12 = (char *)(P + 36);
        memset(P + 36, 0, 0x58u);
        v13 = *(_QWORD *)(v8 + 288);
        v14 = *(_BYTE *)(v13 + 2);
        if ( v14 == 40 )
        {
          v15 = 0;
          if ( *(_DWORD *)(v13 + 20) )
            goto LABEL_39;
          v16 = *(_DWORD *)(v13 + 56);
          if ( v16 )
          {
            v17 = 0;
            v18 = 0;
            while ( 1 )
            {
              v19 = *(unsigned int *)(v13 + 4LL * v17 + 120);
              if ( (unsigned int)v19 >= 0x80 )
              {
                v20 = *(unsigned int *)(v13 + 16);
                if ( (unsigned int)v19 < (unsigned int)v20 )
                {
                  v21 = (unsigned int)v19;
                  v22 = *(_DWORD *)(v19 + v13) - 64;
                  if ( v22 )
                  {
                    v23 = v22 - 1;
                    if ( v23 )
                    {
                      if ( v23 == 1 && v21 + 40 <= v20 )
                        goto LABEL_39;
                    }
                    else if ( v21 + 56 <= v20 )
                    {
                      v15 = *(_BYTE *)(v21 + v13 + 10);
                      v18 = 1;
                    }
                  }
                  else if ( v21 + 40 <= v20 )
                  {
                    v15 = *(_BYTE *)(v21 + v13 + 10);
                    goto LABEL_39;
                  }
                  if ( v18 )
                    goto LABEL_39;
                }
              }
              if ( ++v17 >= v16 )
                goto LABEL_39;
            }
          }
        }
        else
        {
          v15 = *(_BYTE *)(v13 + 10);
LABEL_39:
          if ( v15 > 0x10u )
            return SubmitTransferPacket(v8);
        }
        if ( v14 != 40 )
        {
          v24 = (const void *)(v13 + 72);
          goto LABEL_63;
        }
        v24 = 0;
        if ( !*(_DWORD *)(v13 + 20) )
        {
          v25 = *(_DWORD *)(v13 + 56);
          if ( v25 )
          {
            v26 = 0;
            v27 = 0;
            do
            {
              v28 = *(unsigned int *)(v13 + 4LL * v26 + 120);
              if ( (unsigned int)v28 >= 0x80 )
              {
                v29 = *(unsigned int *)(v13 + 16);
                if ( (unsigned int)v28 < (unsigned int)v29 )
                {
                  v30 = (unsigned int)v28;
                  v31 = *(_DWORD *)(v28 + v13) - 64;
                  if ( v31 )
                  {
                    v32 = v31 - 1;
                    if ( v32 )
                    {
                      if ( v32 == 1 && v30 + 40 <= v29 )
                      {
                        if ( !*(_DWORD *)(v30 + v13 + 12) )
                          break;
                        v33 = v13 + 32;
                        goto LABEL_61;
                      }
                    }
                    else if ( v30 + 56 <= v29 )
                    {
                      if ( !*(_BYTE *)(v30 + v13 + 10) )
                        break;
                      v27 = 1;
                      v24 = (const void *)(v30 + v13 + 24);
                    }
                  }
                  else if ( v30 + 40 <= v29 )
                  {
                    if ( !*(_BYTE *)(v30 + v13 + 10) )
                      break;
                    v33 = v13 + 24;
LABEL_61:
                    v24 = (const void *)(v30 + v33);
                    break;
                  }
                  if ( v27 )
                    break;
                }
              }
              ++v26;
            }
            while ( v26 < v25 );
          }
        }
LABEL_63:
        memmove(v12 + 72, v24, v15);
        return SubmitTransferPacket(v8);
      }
      v11 = (IRP *)P[28];
    }
    IoFreeIrp(v11);
    P[28] = 0;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 243, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v3);
  }
  return ClasspCompleteOffloadRead(P);
}

```

## disassembly

```asm
0x1400206f8  push    rbx
0x1400206fa  push    rbp
0x1400206fb  push    rsi
0x1400206fc  push    rdi
0x1400206fd  push    r12
0x1400206ff  push    r13
0x140020701  push    r14
0x140020703  push    r15
0x140020705  sub     rsp, 38h
0x140020709  mov     ebp, [rcx+0F8h]
0x14002070f  mov     rbx, rcx
0x140020712  mov     rdi, [rcx]
0x140020715  mov     rsi, [rcx+8]
0x140020719  mov     r15d, [rcx+100h]
0x140020720  mov     r12d, [rcx+0FCh]
0x140020727  mov     rcx, cs:WPP_GLOBAL_Control
0x14002072e  lea     r14, WPP_GLOBAL_Control
0x140020735  cmp     rcx, r14
0x140020738  jz      short loc_140020764
0x14002073a  mov     eax, [rcx+2Ch]
0x14002073d  test    al, 10h
0x14002073f  jz      short loc_140020764
0x140020741  cmp     byte ptr [rcx+29h], 5
0x140020745  jb      short loc_140020764
0x140020747  mov     rcx, [rcx+18h]
0x14002074b  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140020752  mov     edx, 0F2h
0x140020757  mov     [rsp+78h+var_58], rsi
0x14002075c  mov     r9, rdi
0x14002075f  call    WPP_SF_qq
0x140020764  mov     rcx, rdi
0x140020767  mov     qword ptr [rbx+110h], 0
0x140020772  call    DequeueFreeTransferPacket
0x140020777  mov     r13, rax
0x14002077a  test    rax, rax
0x14002077d  jnz     short loc_1400207C2
0x14002077f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020786  cmp     rcx, r14
0x140020789  jz      short loc_1400207B0
0x14002078b  mov     eax, [rcx+2Ch]
0x14002078e  test    al, 10h
0x140020790  jz      short loc_1400207B0
0x140020792  cmp     byte ptr [rcx+29h], 2
0x140020796  jb      short loc_1400207B0
0x140020798  mov     rcx, [rcx+18h]
0x14002079c  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400207a3  mov     edx, 0F3h
0x1400207a8  mov     r9, rdi
0x1400207ab  call    WPP_SF_q
0x1400207b0  mov     edx, 0C000009Ah
0x1400207b5  mov     rcx, rbx; P
0x1400207b8  call    ClasspCompleteOffloadRead
0x1400207bd  jmp     loc_140020A44
0x1400207c2  lea     r14, [rbx+180h]
0x1400207c9  mov     [rbx+0E8h], r13
0x1400207d0  mov     rcx, r14; void *
0x1400207d3  mov     r8, rbp; Size
0x1400207d6  xor     edx, edx; Val
0x1400207d8  call    memset
0x1400207dd  lea     ecx, [r15-4]
0x1400207e1  xor     edx, edx; Val
0x1400207e3  mov     eax, ecx
0x1400207e5  mov     [r14+3], cl
0x1400207e9  shr     eax, 8
0x1400207ec  lea     rbp, [rbx+10h]
0x1400207f0  mov     [r14+2], al
0x1400207f4  mov     r8d, 0D0h; Size
0x1400207fa  mov     eax, ecx
0x1400207fc  shr     ecx, 18h
0x1400207ff  mov     [r14], cl
0x140020802  mov     rcx, rbp; void *
0x140020805  shr     eax, 10h
0x140020808  mov     [r14+1], al
0x14002080c  call    memset
0x140020811  mov     rcx, [rbx+0E0h]
0x140020818  xor     edi, edi
0x14002081a  test    rcx, rcx
0x14002081d  jz      short loc_140020882
0x14002081f  cmp     cs:ClassPnPETWEnabled, dil
0x140020826  jz      short loc_14002086F
0x140020828  lea     rdi, [r13+148h]
0x14002082f  mov     rcx, rsi
0x140020832  mov     rdx, rdi
0x140020835  call    cs:__imp_IoGetActivityIdIrp
0x14002083c  nop     dword ptr [rax+rax+00h]
0x140020841  test    eax, eax
0x140020843  jns     short loc_14002084C
0x140020845  movups  xmm0, xmmword ptr [rsi]
0x140020848  movdqu  xmmword ptr [rdi], xmm0
0x14002084c  mov     rcx, [rbx+0E0h]
0x140020853  mov     rdx, rdi
0x140020856  call    cs:__imp_IoSetActivityIdIrp
0x14002085d  nop     dword ptr [rax+rax+00h]
0x140020862  xor     edi, edi
0x140020864  test    eax, eax
0x140020866  jns     short loc_140020882
0x140020868  mov     rcx, [rbx+0E0h]; Irp
0x14002086f  call    cs:__imp_IoFreeIrp
0x140020876  nop     dword ptr [rax+rax+00h]
0x14002087b  mov     [rbx+0E0h], rdi
0x140020882  mov     rax, [rbx+0E0h]
0x140020889  mov     r9, r14
0x14002088c  test    rax, rax
0x14002088f  mov     [rsp+78h+var_50], r12d
0x140020894  mov     r8d, r15d
0x140020897  mov     rdx, r13
0x14002089a  cmovnz  rbp, rax
0x14002089e  mov     rcx, rbx
0x1400208a1  mov     [rsp+78h+var_58], rbp
0x1400208a6  mov     [rbp+30h], edi
0x1400208a9  mov     [rbp+38h], rdi
0x1400208ad  mov     qword ptr [rbp+78h], 1
0x1400208b5  mov     rax, [rbx+0F0h]
0x1400208bc  mov     [rbp+8], rax
0x1400208c0  call    ClasspSetupReceivePopulateTokenInformationTransferPacket
0x1400208c5  xor     edx, edx; Val
0x1400208c7  lea     rbp, [rbx+120h]
0x1400208ce  mov     rcx, rbp; void *
0x1400208d1  lea     r8d, [rdx+58h]; Size
0x1400208d5  call    memset
0x1400208da  mov     rdx, [r13+120h]
0x1400208e1  xor     r14d, r14d
0x1400208e4  mov     r15d, 80h
0x1400208ea  mov     sil, [rdx+2]
0x1400208ee  cmp     sil, 28h ; '('
0x1400208f2  jnz     short loc_140020971
0x1400208f4  mov     r10b, r14b
0x1400208f7  cmp     [rdx+14h], r14d
0x1400208fb  jnz     short loc_140020975
0x1400208fd  mov     ebx, [rdx+38h]
0x140020900  test    ebx, ebx
0x140020902  jz      short loc_14002097F
0x140020904  mov     r11d, r14d
0x140020907  mov     dil, r14b
0x14002090a  mov     eax, r11d
0x14002090d  mov     ecx, [rdx+rax*4+78h]
0x140020911  cmp     ecx, r15d
0x140020914  jb      short loc_140020960
0x140020916  mov     r9d, [rdx+10h]
0x14002091a  cmp     ecx, r9d
0x14002091d  jnb     short loc_140020960
0x14002091f  mov     r8d, ecx
0x140020922  mov     ecx, [rcx+rdx]
0x140020925  sub     ecx, 40h ; '@'
0x140020928  jz      short loc_140020952
0x14002092a  sub     ecx, 1
0x14002092d  jz      short loc_14002093F
0x14002092f  cmp     ecx, 1
0x140020932  jnz     short loc_14002095B
0x140020934  lea     rcx, [r8+28h]
0x140020938  cmp     rcx, r9
0x14002093b  jbe     short loc_140020975
0x14002093d  jmp     short loc_14002095B
0x14002093f  lea     rcx, [r8+38h]
0x140020943  cmp     rcx, r9
0x140020946  ja      short loc_14002095B
0x140020948  mov     r10b, [r8+rdx+0Ah]
0x14002094d  mov     dil, 1
0x140020950  jmp     short loc_14002095B
0x140020952  lea     rcx, [r8+28h]
0x140020956  cmp     rcx, r9
0x140020959  jbe     short loc_14002096A
0x14002095b  test    dil, dil
0x14002095e  jnz     short loc_140020975
0x140020960  inc     r11d
0x140020963  cmp     r11d, ebx
0x140020966  jb      short loc_14002090A
0x140020968  jmp     short loc_140020975
0x14002096a  mov     r10b, [r8+rdx+0Ah]
0x14002096f  jmp     short loc_140020975
0x140020971  mov     r10b, [rdx+0Ah]
0x140020975  cmp     r10b, 10h
0x140020979  ja      loc_140020A3C
0x14002097f  cmp     sil, 28h ; '('
0x140020983  jnz     loc_140020A28
0x140020989  mov     r9, r14
0x14002098c  cmp     [rdx+14h], r14d
0x140020990  jnz     loc_140020A2C
0x140020996  mov     edi, [rdx+38h]
0x140020999  test    edi, edi
0x14002099b  jz      loc_140020A2C
0x1400209a1  mov     ebx, r14d
0x1400209a4  mov     sil, r14b
0x1400209a7  mov     eax, ebx
0x1400209a9  mov     ecx, [rdx+rax*4+78h]
0x1400209ad  cmp     ecx, r15d
0x1400209b0  jb      short loc_140020A10
0x1400209b2  mov     r11d, [rdx+10h]
0x1400209b6  cmp     ecx, r11d
0x1400209b9  jnb     short loc_140020A10
0x1400209bb  mov     r8d, ecx
0x1400209be  mov     ecx, [rcx+rdx]
0x1400209c1  sub     ecx, 40h ; '@'
0x1400209c4  jz      short loc_140020A02
0x1400209c6  sub     ecx, 1
0x1400209c9  jz      short loc_1400209E6
0x1400209cb  cmp     ecx, 1
0x1400209ce  jnz     short loc_140020A0B
0x1400209d0  lea     rcx, [r8+28h]
0x1400209d4  cmp     rcx, r11
0x1400209d7  ja      short loc_140020A0B
0x1400209d9  cmp     [r8+rdx+0Ch], r14d
0x1400209de  jbe     short loc_140020A2C
0x1400209e0  lea     r9, [rdx+20h]
0x1400209e4  jmp     short loc_140020A23
0x1400209e6  lea     rcx, [r8+38h]
0x1400209ea  cmp     rcx, r11
0x1400209ed  ja      short loc_140020A0B
0x1400209ef  cmp     [r8+rdx+0Ah], r14b
0x1400209f4  jbe     short loc_140020A2C
0x1400209f6  lea     r9, [rdx+18h]
0x1400209fa  mov     sil, 1
0x1400209fd  add     r9, r8
0x140020a00  jmp     short loc_140020A0B
0x140020a02  lea     rcx, [r8+28h]
0x140020a06  cmp     rcx, r11
0x140020a09  jbe     short loc_140020A18
0x140020a0b  test    sil, sil
0x140020a0e  jnz     short loc_140020A2C
0x140020a10  inc     ebx
0x140020a12  cmp     ebx, edi
0x140020a14  jb      short loc_1400209A7
0x140020a16  jmp     short loc_140020A2C
0x140020a18  cmp     [r8+rdx+0Ah], r14b
0x140020a1d  jbe     short loc_140020A2C
0x140020a1f  lea     r9, [rdx+18h]
0x140020a23  add     r9, r8
0x140020a26  jmp     short loc_140020A2C
0x140020a28  lea     r9, [rdx+48h]
0x140020a2c  movzx   r8d, r10b; Size
0x140020a30  lea     rcx, [rbp+48h]; void *
0x140020a34  mov     rdx, r9; Src
0x140020a37  call    memmove
0x140020a3c  mov     rcx, r13
0x140020a3f  call    SubmitTransferPacket
0x140020a44  add     rsp, 38h
0x140020a48  pop     r15
0x140020a4a  pop     r14
0x140020a4c  pop     r13
0x140020a4e  pop     r12
0x140020a50  pop     rdi
0x140020a51  pop     rsi
0x140020a52  pop     rbp
0x140020a53  pop     rbx
0x140020a54  retn
```
