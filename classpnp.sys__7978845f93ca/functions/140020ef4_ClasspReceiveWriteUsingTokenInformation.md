# ClasspReceiveWriteUsingTokenInformation

- ea: `0x140020ef4`
- end: `0x14002126c`
- name: `ClasspReceiveWriteUsingTokenInformation`
- size: `888`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400262d0`

## callees

- `0x140002230`
- `0x140004950`
- `0x14001fc38`
- `0x140020ef4`
- `0x140021274`
- `0x140022668`
- `0x140023f24`
- `0x14003e640`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140021068`
- `ntoskrnl!IoFreeIrp` at `0x14002107d`
- `ntoskrnl!IoFreeIrp` at `0x140021068`
- `ntoskrnl!IoFreeIrp` at `0x14002107d`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14002104f`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14002104f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002102e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14002102e`

## pseudocode

```c
NTSTATUS __fastcall ClasspReceiveWriteUsingTokenInformation(unsigned int *P)
{
  __int64 v2; // rdi
  _OWORD *v3; // rsi
  size_t v4; // r12
  unsigned int v5; // r15d
  __int64 v6; // r13
  char *v8; // rbp
  IRP *v9; // rcx
  __int64 v10; // r15
  _OWORD *v11; // rdi
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
  unsigned int v34; // [rsp+70h] [rbp+8h]
  PSLIST_ENTRY v35; // [rsp+78h] [rbp+10h]

  v2 = *(_QWORD *)P;
  v3 = (_OWORD *)*((_QWORD *)P + 1);
  v4 = P[22];
  v5 = P[23];
  v6 = *((_QWORD *)P + 39);
  v34 = P[92];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 266, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v2, v3);
  }
  v35 = DequeueFreeTransferPacket(v2);
  if ( v35 )
  {
    v8 = (char *)(P + 24);
    memset(P + 120, 0, v4);
    *((_BYTE *)P + 483) = v5 - 4;
    *((_BYTE *)P + 482) = (unsigned __int16)(v5 - 4) >> 8;
    *((_BYTE *)P + 480) = (v5 - 4) >> 24;
    *((_BYTE *)P + 481) = (v5 - 4) >> 16;
    memset(P + 24, 0, 0xD0u);
    v9 = (IRP *)*((_QWORD *)P + 38);
    if ( v9 )
    {
      if ( ClassPnPETWEnabled )
      {
        v10 = (__int64)v35;
        v11 = &v35[20].Next + 1;
        if ( (int)IoGetActivityIdIrp(v3, &v35[20].Next + 1) < 0 )
          *v11 = *v3;
        if ( (int)IoSetActivityIdIrp(*((_QWORD *)P + 38), v11) < 0 )
        {
          IoFreeIrp(*((PIRP *)P + 38));
          *((_QWORD *)P + 38) = 0;
        }
LABEL_19:
        if ( *((_QWORD *)P + 38) )
          v8 = (char *)*((_QWORD *)P + 38);
        *((_DWORD *)v8 + 12) = 0;
        *((_QWORD *)v8 + 7) = 0;
        *((_QWORD *)v8 + 15) = 1;
        *((_QWORD *)v8 + 1) = v6;
        ClasspSetupReceiveWriteUsingTokenInformationTransferPacket(
          (_DWORD)P,
          v10,
          v4,
          (_DWORD)P + 480,
          (__int64)v8,
          v34);
        v12 = (char *)(P + 94);
        memset(P + 94, 0, 0x58u);
        v13 = *(_QWORD *)(v10 + 288);
        v14 = *(_BYTE *)(v13 + 2);
        if ( v14 == 40 )
        {
          v15 = 0;
          if ( *(_DWORD *)(v13 + 20) )
            goto LABEL_40;
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
                        goto LABEL_40;
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
                    goto LABEL_40;
                  }
                  if ( v18 )
                    goto LABEL_40;
                }
              }
              if ( ++v17 >= v16 )
                goto LABEL_40;
            }
          }
        }
        else
        {
          v15 = *(_BYTE *)(v13 + 10);
LABEL_40:
          if ( v15 > 0x10u )
            return SubmitTransferPacket(v10);
        }
        if ( v14 != 40 )
        {
          v24 = (const void *)(v13 + 72);
          goto LABEL_64;
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
                        goto LABEL_62;
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
LABEL_62:
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
LABEL_64:
        memmove(v12 + 72, v24, v15);
        return SubmitTransferPacket(v10);
      }
      IoFreeIrp(v9);
      *((_QWORD *)P + 38) = 0;
    }
    v10 = (__int64)v35;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 267, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v2);
  }
  return ClasspCompleteOffloadWrite(P);
}

```

## disassembly

```asm
0x140020ef4  mov     [rsp+arg_10], rbx
0x140020ef9  push    rbp
0x140020efa  push    rsi
0x140020efb  push    rdi
0x140020efc  push    r12
0x140020efe  push    r13
0x140020f00  push    r14
0x140020f02  push    r15
0x140020f04  sub     rsp, 30h
0x140020f08  mov     eax, [rcx+170h]
0x140020f0e  mov     rbx, rcx
0x140020f11  mov     rdi, [rcx]
0x140020f14  mov     rsi, [rcx+8]
0x140020f18  mov     r12d, [rcx+58h]
0x140020f1c  mov     r15d, [rcx+5Ch]
0x140020f20  mov     r13, [rcx+138h]
0x140020f27  mov     [rsp+68h+arg_0], eax
0x140020f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f32  lea     rbp, WPP_GLOBAL_Control
0x140020f39  cmp     rcx, rbp
0x140020f3c  jz      short loc_140020F68
0x140020f3e  mov     eax, [rcx+2Ch]
0x140020f41  test    al, 10h
0x140020f43  jz      short loc_140020F68
0x140020f45  cmp     byte ptr [rcx+29h], 5
0x140020f49  jb      short loc_140020F68
0x140020f4b  mov     rcx, [rcx+18h]
0x140020f4f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140020f56  mov     edx, 10Ah
0x140020f5b  mov     [rsp+68h+var_48], rsi
0x140020f60  mov     r9, rdi
0x140020f63  call    WPP_SF_qq
0x140020f68  mov     rcx, rdi
0x140020f6b  call    DequeueFreeTransferPacket
0x140020f70  mov     [rsp+68h+arg_8], rax
0x140020f75  test    rax, rax
0x140020f78  jnz     short loc_140020FBD
0x140020f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f81  cmp     rcx, rbp
0x140020f84  jz      short loc_140020FAB
0x140020f86  mov     eax, [rcx+2Ch]
0x140020f89  test    al, 10h
0x140020f8b  jz      short loc_140020FAB
0x140020f8d  cmp     byte ptr [rcx+29h], 2
0x140020f91  jb      short loc_140020FAB
0x140020f93  mov     rcx, [rcx+18h]
0x140020f97  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140020f9e  mov     edx, 10Bh
0x140020fa3  mov     r9, rdi
0x140020fa6  call    WPP_SF_q
0x140020fab  mov     edx, 0C000009Ah
0x140020fb0  mov     rcx, rbx; P
0x140020fb3  call    ClasspCompleteOffloadWrite
0x140020fb8  jmp     loc_140021253
0x140020fbd  lea     r14, [rbx+1E0h]
0x140020fc4  mov     r8, r12; Size
0x140020fc7  mov     rcx, r14; void *
0x140020fca  lea     rbp, [rbx+60h]
0x140020fce  xor     edx, edx; Val
0x140020fd0  call    memset
0x140020fd5  lea     ecx, [r15-4]
0x140020fd9  xor     edx, edx; Val
0x140020fdb  mov     eax, ecx
0x140020fdd  mov     [r14+3], cl
0x140020fe1  shr     eax, 8
0x140020fe4  mov     r8d, 0D0h; Size
0x140020fea  mov     [r14+2], al
0x140020fee  mov     eax, ecx
0x140020ff0  shr     ecx, 18h
0x140020ff3  mov     [r14], cl
0x140020ff6  mov     rcx, rbp; void *
0x140020ff9  shr     eax, 10h
0x140020ffc  mov     [r14+1], al
0x140021000  call    memset
0x140021005  mov     rcx, [rbx+130h]; Irp
0x14002100c  xor     edi, edi
0x14002100e  test    rcx, rcx
0x140021011  jz      short loc_140021090
0x140021013  cmp     cs:ClassPnPETWEnabled, dil
0x14002101a  jz      short loc_14002107D
0x14002101c  mov     r15, [rsp+68h+arg_8]
0x140021021  mov     rcx, rsi
0x140021024  lea     rdi, [r15+148h]
0x14002102b  mov     rdx, rdi
0x14002102e  call    cs:__imp_IoGetActivityIdIrp
0x140021035  nop     dword ptr [rax+rax+00h]
0x14002103a  test    eax, eax
0x14002103c  jns     short loc_140021045
0x14002103e  movups  xmm0, xmmword ptr [rsi]
0x140021041  movdqu  xmmword ptr [rdi], xmm0
0x140021045  mov     rcx, [rbx+130h]
0x14002104c  mov     rdx, rdi
0x14002104f  call    cs:__imp_IoSetActivityIdIrp
0x140021056  nop     dword ptr [rax+rax+00h]
0x14002105b  xor     edi, edi
0x14002105d  test    eax, eax
0x14002105f  jns     short loc_140021095
0x140021061  mov     rcx, [rbx+130h]; Irp
0x140021068  call    cs:__imp_IoFreeIrp
0x14002106f  nop     dword ptr [rax+rax+00h]
0x140021074  mov     [rbx+130h], rdi
0x14002107b  jmp     short loc_140021095
0x14002107d  call    cs:__imp_IoFreeIrp
0x140021084  nop     dword ptr [rax+rax+00h]
0x140021089  mov     [rbx+130h], rdi
0x140021090  mov     r15, [rsp+68h+arg_8]
0x140021095  mov     rax, [rbx+130h]
0x14002109c  mov     r9, r14
0x14002109f  test    rax, rax
0x1400210a2  mov     r8d, r12d
0x1400210a5  mov     rdx, r15
0x1400210a8  mov     rcx, rbx
0x1400210ab  cmovnz  rbp, rax
0x1400210af  mov     eax, [rsp+68h+arg_0]
0x1400210b3  mov     [rsp+68h+var_40], eax
0x1400210b7  mov     [rsp+68h+var_48], rbp
0x1400210bc  mov     [rbp+30h], edi
0x1400210bf  mov     [rbp+38h], rdi
0x1400210c3  mov     qword ptr [rbp+78h], 1
0x1400210cb  mov     [rbp+8], r13
0x1400210cf  call    ClasspSetupReceiveWriteUsingTokenInformationTransferPacket
0x1400210d4  xor     edx, edx; Val
0x1400210d6  lea     rbp, [rbx+178h]
0x1400210dd  mov     rcx, rbp; void *
0x1400210e0  lea     r8d, [rdx+58h]; Size
0x1400210e4  call    memset
0x1400210e9  mov     rdx, [r15+120h]
0x1400210f0  xor     r14d, r14d
0x1400210f3  mov     r12d, 80h
0x1400210f9  mov     sil, [rdx+2]
0x1400210fd  cmp     sil, 28h ; '('
0x140021101  jnz     short loc_140021180
0x140021103  mov     r10b, r14b
0x140021106  cmp     [rdx+14h], r14d
0x14002110a  jnz     short loc_140021184
0x14002110c  mov     ebx, [rdx+38h]
0x14002110f  test    ebx, ebx
0x140021111  jz      short loc_14002118E
0x140021113  mov     r11d, r14d
0x140021116  mov     dil, r14b
0x140021119  mov     eax, r11d
0x14002111c  mov     ecx, [rdx+rax*4+78h]
0x140021120  cmp     ecx, r12d
0x140021123  jb      short loc_14002116F
0x140021125  mov     r9d, [rdx+10h]
0x140021129  cmp     ecx, r9d
0x14002112c  jnb     short loc_14002116F
0x14002112e  mov     r8d, ecx
0x140021131  mov     ecx, [rcx+rdx]
0x140021134  sub     ecx, 40h ; '@'
0x140021137  jz      short loc_140021161
0x140021139  sub     ecx, 1
0x14002113c  jz      short loc_14002114E
0x14002113e  cmp     ecx, 1
0x140021141  jnz     short loc_14002116A
0x140021143  lea     rcx, [r8+28h]
0x140021147  cmp     rcx, r9
0x14002114a  jbe     short loc_140021184
0x14002114c  jmp     short loc_14002116A
0x14002114e  lea     rcx, [r8+38h]
0x140021152  cmp     rcx, r9
0x140021155  ja      short loc_14002116A
0x140021157  mov     r10b, [r8+rdx+0Ah]
0x14002115c  mov     dil, 1
0x14002115f  jmp     short loc_14002116A
0x140021161  lea     rcx, [r8+28h]
0x140021165  cmp     rcx, r9
0x140021168  jbe     short loc_140021179
0x14002116a  test    dil, dil
0x14002116d  jnz     short loc_140021184
0x14002116f  inc     r11d
0x140021172  cmp     r11d, ebx
0x140021175  jb      short loc_140021119
0x140021177  jmp     short loc_140021184
0x140021179  mov     r10b, [r8+rdx+0Ah]
0x14002117e  jmp     short loc_140021184
0x140021180  mov     r10b, [rdx+0Ah]
0x140021184  cmp     r10b, 10h
0x140021188  ja      loc_14002124B
0x14002118e  cmp     sil, 28h ; '('
0x140021192  jnz     loc_140021237
0x140021198  mov     r9, r14
0x14002119b  cmp     [rdx+14h], r14d
0x14002119f  jnz     loc_14002123B
0x1400211a5  mov     edi, [rdx+38h]
0x1400211a8  test    edi, edi
0x1400211aa  jz      loc_14002123B
0x1400211b0  mov     ebx, r14d
0x1400211b3  mov     sil, r14b
0x1400211b6  mov     eax, ebx
0x1400211b8  mov     ecx, [rdx+rax*4+78h]
0x1400211bc  cmp     ecx, r12d
0x1400211bf  jb      short loc_14002121F
0x1400211c1  mov     r11d, [rdx+10h]
0x1400211c5  cmp     ecx, r11d
0x1400211c8  jnb     short loc_14002121F
0x1400211ca  mov     r8d, ecx
0x1400211cd  mov     ecx, [rcx+rdx]
0x1400211d0  sub     ecx, 40h ; '@'
0x1400211d3  jz      short loc_140021211
0x1400211d5  sub     ecx, 1
0x1400211d8  jz      short loc_1400211F5
0x1400211da  cmp     ecx, 1
0x1400211dd  jnz     short loc_14002121A
0x1400211df  lea     rcx, [r8+28h]
0x1400211e3  cmp     rcx, r11
0x1400211e6  ja      short loc_14002121A
0x1400211e8  cmp     [r8+rdx+0Ch], r14d
0x1400211ed  jbe     short loc_14002123B
0x1400211ef  lea     r9, [rdx+20h]
0x1400211f3  jmp     short loc_140021232
0x1400211f5  lea     rcx, [r8+38h]
0x1400211f9  cmp     rcx, r11
0x1400211fc  ja      short loc_14002121A
0x1400211fe  cmp     [r8+rdx+0Ah], r14b
0x140021203  jbe     short loc_14002123B
0x140021205  lea     r9, [rdx+18h]
0x140021209  mov     sil, 1
0x14002120c  add     r9, r8
0x14002120f  jmp     short loc_14002121A
0x140021211  lea     rcx, [r8+28h]
0x140021215  cmp     rcx, r11
0x140021218  jbe     short loc_140021227
0x14002121a  test    sil, sil
0x14002121d  jnz     short loc_14002123B
0x14002121f  inc     ebx
0x140021221  cmp     ebx, edi
0x140021223  jb      short loc_1400211B6
0x140021225  jmp     short loc_14002123B
0x140021227  cmp     [r8+rdx+0Ah], r14b
0x14002122c  jbe     short loc_14002123B
0x14002122e  lea     r9, [rdx+18h]
0x140021232  add     r9, r8
0x140021235  jmp     short loc_14002123B
0x140021237  lea     r9, [rdx+48h]
0x14002123b  movzx   r8d, r10b; Size
0x14002123f  lea     rcx, [rbp+48h]; void *
0x140021243  mov     rdx, r9; Src
0x140021246  call    memmove
0x14002124b  mov     rcx, r15
0x14002124e  call    SubmitTransferPacket
0x140021253  mov     rbx, [rsp+68h+arg_10]
0x14002125b  add     rsp, 30h
0x14002125f  pop     r15
0x140021261  pop     r14
0x140021263  pop     r13
0x140021265  pop     r12
0x140021267  pop     rdi
0x140021268  pop     rsi
0x140021269  pop     rbp
0x14002126a  retn
```
