# SPAEEntryStartAuth

- ea: `0x18000ade0`
- end: `0x18000b321`
- name: `SPAEEntryStartAuth`
- size: `1345`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180004710`
- `0x180005440`
- `0x180007f60`
- `0x18000ade0`
- `0x18000cf70`
- `0x180010ae0`
- `0x180010d40`
- `0x180012660`
- `0x1800214f0`
- `0x180022104`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18000afd0`
- `MobileNetworking!AllocateMemory` at `0x18000b188`
- `MobileNetworking!AllocateMemory` at `0x18000afd0`
- `MobileNetworking!AllocateMemory` at `0x18000b188`

## string_xrefs

- `0x18000afbf`: `OneXCreateEvent`
- `0x18000b177`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall SPAEEntryStartAuth(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v3; // r14d
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  unsigned int v6; // ebp
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // ebp
  unsigned int v15; // esi
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  unsigned int v18; // eax
  __int64 v20; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v3 = *(_DWORD *)(v1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 83, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  *(_QWORD *)(v1 + 2368) = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(v1 + 36) = 0;
  *(_QWORD *)(v1 + 28) = 1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(v1 + 104) )
  {
    FreeEapError(*(_QWORD *)(v1 + 104));
    *(_QWORD *)(v1 + 104) = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_D(v4[7], 68, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
  if ( *(_DWORD *)(v1 + 2432)
    && (unsigned int)MSMNotifyAuthRestarted(v1, 1)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 84, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  }
  ++*(_DWORD *)(v1 + 2432);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      85,
      WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids,
      *(unsigned int *)(v1 + 20));
    v5 = WPP_GLOBAL_Control;
  }
  if ( (byte_18003DF41 & 0x10) != 0 )
  {
    McTemplateU0qq_EtwEventWriteTransfer(v5, StartAuth, *(unsigned int *)(v1 + 20), 2);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(_DWORD *)(v1 + 20);
  v20 = 0;
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v5[7], 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(v1 + 20);
  if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
    WPP_SF_(v5[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v8 = AllocateMemory(56, &v20, "OneXCreateEvent", 67);
  v9 = v8;
  if ( !v8 )
  {
    *(_DWORD *)(v20 + 16) = 26;
    *(_DWORD *)(v20 + 32) = 0;
    *(_QWORD *)(v20 + 24) = v1;
    goto LABEL_33;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_45:
    OneXDeleteEvent(v20);
    goto LABEL_46;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v7, v8);
LABEL_33:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v10[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v9);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
      WPP_SF_dd(v10[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v6, v9);
    goto LABEL_45;
  }
  v11 = QueueSupplicantEvent(v20);
  v9 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v6, v11);
    goto LABEL_45;
  }
LABEL_46:
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v9);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !v9 )
  {
    v14 = *(_DWORD *)(v1 + 20);
    v20 = 0;
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    {
      WPP_SF_(v12[7], 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    v15 = *(_DWORD *)(v1 + 20);
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
      WPP_SF_(v12[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v16 = AllocateMemory(56, &v20, "OneXCreateEvent", 67);
    v9 = v16;
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_76;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_65:
        if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x800) != 0 )
        {
          WPP_SF_D(v17[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v9);
          v17 = WPP_GLOBAL_Control;
        }
        if ( v9 )
        {
          if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 68) & 1) != 0 )
            WPP_SF_dd(v17[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v14, v9);
        }
        else
        {
          v18 = QueueSupplicantEvent(v20);
          v9 = v18;
          if ( !v18 )
          {
LABEL_77:
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v9);
              v12 = WPP_GLOBAL_Control;
            }
            if ( !v9 )
              goto LABEL_85;
            if ( v12 == &WPP_GLOBAL_Control )
              return v9;
            if ( (*((_BYTE *)v12 + 68) & 1) == 0 )
              goto LABEL_85;
            v13 = 87;
            goto LABEL_84;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              20,
              WPP_c98c90d098d532f46181864aabb10d65_Traceguids,
              v14,
              v18);
        }
LABEL_76:
        OneXDeleteEvent(v20);
        goto LABEL_77;
      }
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v15, v16);
    }
    else
    {
      *(_DWORD *)(v20 + 16) = 4;
      *(_DWORD *)(v20 + 32) = 0;
      *(_QWORD *)(v20 + 24) = v1;
    }
    v17 = WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  if ( v12 == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)v12 + 68) & 1) != 0 )
  {
    v13 = 86;
LABEL_84:
    WPP_SF_dd(v12[7], v13, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v3, v9);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_85:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_D(v12[7], 88, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000ade0  mov     [rsp+arg_8], rbx
0x18000ade5  mov     [rsp+arg_10], rbp
0x18000adea  push    rsi
0x18000adeb  push    rdi
0x18000adec  push    r12
0x18000adee  push    r14
0x18000adf0  push    r15
0x18000adf2  sub     rsp, 30h
0x18000adf6  mov     rbx, [rcx+18h]
0x18000adfa  mov     rdi, rcx
0x18000adfd  mov     r14d, [rbx+14h]
0x18000ae01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae08  lea     r15, WPP_GLOBAL_Control
0x18000ae0f  cmp     rcx, r15
0x18000ae12  jz      short loc_18000AE32
0x18000ae14  test    dword ptr [rcx+44h], 800h
0x18000ae1b  jz      short loc_18000AE32
0x18000ae1d  mov     rcx, [rcx+38h]
0x18000ae21  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18000ae28  mov     edx, 53h ; 'S'
0x18000ae2d  call    WPP_SF_
0x18000ae32  mov     rax, [rdi+30h]
0x18000ae36  xor     r12d, r12d
0x18000ae39  mov     [rbx+940h], rax
0x18000ae40  mov     [rbx+24h], r12d
0x18000ae44  mov     qword ptr [rbx+1Ch], 1
0x18000ae4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae53  cmp     rcx, r15
0x18000ae56  jz      short loc_18000AE7D
0x18000ae58  test    dword ptr [rcx+44h], 800h
0x18000ae5f  jz      short loc_18000AE7D
0x18000ae61  mov     rcx, [rcx+38h]
0x18000ae65  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000ae6c  mov     edx, 42h ; 'B'
0x18000ae71  call    WPP_SF_
0x18000ae76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae7d  mov     rax, [rbx+68h]
0x18000ae81  test    rax, rax
0x18000ae84  jz      short loc_18000AE99
0x18000ae86  mov     rcx, rax
0x18000ae89  call    FreeEapError
0x18000ae8e  mov     [rbx+68h], r12
0x18000ae92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae99  cmp     rcx, r15
0x18000ae9c  jz      short loc_18000AEBF
0x18000ae9e  test    dword ptr [rcx+44h], 800h
0x18000aea5  jz      short loc_18000AEBF
0x18000aea7  mov     rcx, [rcx+38h]
0x18000aeab  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000aeb2  mov     edx, 44h ; 'D'
0x18000aeb7  xor     r9d, r9d
0x18000aeba  call    WPP_SF_D
0x18000aebf  cmp     [rbx+980h], r12d
0x18000aec6  jz      short loc_18000AF00
0x18000aec8  mov     edx, 1
0x18000aecd  mov     rcx, rbx
0x18000aed0  call    MSMNotifyAuthRestarted
0x18000aed5  test    eax, eax
0x18000aed7  jz      short loc_18000AF00
0x18000aed9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aee0  cmp     rcx, r15
0x18000aee3  jz      short loc_18000AF00
0x18000aee5  test    byte ptr [rcx+44h], 1
0x18000aee9  jz      short loc_18000AF00
0x18000aeeb  mov     rcx, [rcx+38h]
0x18000aeef  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18000aef6  mov     edx, 54h ; 'T'
0x18000aefb  call    WPP_SF_
0x18000af00  inc     dword ptr [rbx+980h]
0x18000af06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af0d  cmp     rcx, r15
0x18000af10  jz      short loc_18000AF3B
0x18000af12  test    dword ptr [rcx+44h], 200h
0x18000af19  jz      short loc_18000AF3B
0x18000af1b  mov     r9d, [rbx+14h]
0x18000af1f  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18000af26  mov     rcx, [rcx+38h]
0x18000af2a  mov     edx, 55h ; 'U'
0x18000af2f  call    WPP_SF_d
0x18000af34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af3b  test    cs:byte_18003DF41, 10h
0x18000af42  jz      short loc_18000AF61
0x18000af44  mov     r8d, [rbx+14h]
0x18000af48  lea     rdx, StartAuth
0x18000af4f  mov     r9d, 2
0x18000af55  call    McTemplateU0qq_EtwEventWriteTransfer
0x18000af5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af61  mov     ebp, [rbx+14h]
0x18000af64  mov     [rsp+58h+arg_0], r12
0x18000af69  cmp     rcx, r15
0x18000af6c  jz      short loc_18000AF93
0x18000af6e  test    dword ptr [rcx+44h], 800h
0x18000af75  jz      short loc_18000AF93
0x18000af77  mov     rcx, [rcx+38h]
0x18000af7b  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000af82  mov     edx, 12h
0x18000af87  call    WPP_SF_
0x18000af8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af93  mov     esi, [rbx+14h]
0x18000af96  cmp     rcx, r15
0x18000af99  jz      short loc_18000AFB9
0x18000af9b  test    dword ptr [rcx+44h], 800h
0x18000afa2  jz      short loc_18000AFB9
0x18000afa4  mov     rcx, [rcx+38h]
0x18000afa8  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000afaf  mov     edx, 0Ah
0x18000afb4  call    WPP_SF_
0x18000afb9  mov     r9d, 43h ; 'C'
0x18000afbf  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000afc6  lea     rdx, [rsp+58h+arg_0]
0x18000afcb  mov     ecx, 38h ; '8'
0x18000afd0  call    cs:__imp_AllocateMemory
0x18000afd6  mov     edi, eax
0x18000afd8  test    eax, eax
0x18000afda  jz      short loc_18000B010
0x18000afdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afe3  cmp     rcx, r15
0x18000afe6  jz      loc_18000B0BA
0x18000afec  test    byte ptr [rcx+44h], 1
0x18000aff0  jz      short loc_18000B035
0x18000aff2  mov     rcx, [rcx+38h]
0x18000aff6  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000affd  mov     edx, 0Bh
0x18000b002  mov     [rsp+58h+var_38], eax
0x18000b006  mov     r9d, esi
0x18000b009  call    WPP_SF_dd
0x18000b00e  jmp     short loc_18000B02E
0x18000b010  mov     rax, [rsp+58h+arg_0]
0x18000b015  mov     dword ptr [rax+10h], 1Ah
0x18000b01c  mov     rax, [rsp+58h+arg_0]
0x18000b021  mov     [rax+20h], r12d
0x18000b025  mov     rax, [rsp+58h+arg_0]
0x18000b02a  mov     [rax+18h], rbx
0x18000b02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b035  cmp     rcx, r15
0x18000b038  jz      short loc_18000B062
0x18000b03a  test    dword ptr [rcx+44h], 800h
0x18000b041  jz      short loc_18000B062
0x18000b043  mov     rcx, [rcx+38h]
0x18000b047  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b04e  mov     edx, 0Ch
0x18000b053  mov     r9d, edi
0x18000b056  call    WPP_SF_D
0x18000b05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b062  test    edi, edi
0x18000b064  jz      short loc_18000B07C
0x18000b066  cmp     rcx, r15
0x18000b069  jz      short loc_18000B0BA
0x18000b06b  test    byte ptr [rcx+44h], 1
0x18000b06f  jz      short loc_18000B0BA
0x18000b071  mov     edx, 13h
0x18000b076  mov     [rsp+58h+var_38], edi
0x18000b07a  jmp     short loc_18000B0A7
0x18000b07c  mov     rcx, [rsp+58h+arg_0]
0x18000b081  call    QueueSupplicantEvent
0x18000b086  mov     edi, eax
0x18000b088  test    eax, eax
0x18000b08a  jz      short loc_18000B0C4
0x18000b08c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b093  cmp     rcx, r15
0x18000b096  jz      short loc_18000B0BA
0x18000b098  test    byte ptr [rcx+44h], 1
0x18000b09c  jz      short loc_18000B0BA
0x18000b09e  mov     edx, 14h
0x18000b0a3  mov     [rsp+58h+var_38], eax
0x18000b0a7  mov     rcx, [rcx+38h]
0x18000b0ab  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000b0b2  mov     r9d, ebp
0x18000b0b5  call    WPP_SF_dd
0x18000b0ba  mov     rcx, [rsp+58h+arg_0]
0x18000b0bf  call    OneXDeleteEvent
0x18000b0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0cb  cmp     rcx, r15
0x18000b0ce  jz      short loc_18000B0F8
0x18000b0d0  test    dword ptr [rcx+44h], 800h
0x18000b0d7  jz      short loc_18000B0F8
0x18000b0d9  mov     rcx, [rcx+38h]
0x18000b0dd  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000b0e4  mov     edx, 15h
0x18000b0e9  mov     r9d, edi
0x18000b0ec  call    WPP_SF_D
0x18000b0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0f8  test    edi, edi
0x18000b0fa  jz      short loc_18000B119
0x18000b0fc  cmp     rcx, r15
0x18000b0ff  jz      loc_18000B308
0x18000b105  test    byte ptr [rcx+44h], 1
0x18000b109  jz      loc_18000B2E2
0x18000b10f  mov     edx, 56h ; 'V'
0x18000b114  jmp     loc_18000B2C4
0x18000b119  mov     ebp, [rbx+14h]
0x18000b11c  mov     [rsp+58h+arg_0], r12
0x18000b121  cmp     rcx, r15
0x18000b124  jz      short loc_18000B14B
0x18000b126  test    dword ptr [rcx+44h], 800h
0x18000b12d  jz      short loc_18000B14B
0x18000b12f  mov     rcx, [rcx+38h]
0x18000b133  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000b13a  mov     edx, 12h
0x18000b13f  call    WPP_SF_
0x18000b144  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b14b  mov     esi, [rbx+14h]
0x18000b14e  cmp     rcx, r15
0x18000b151  jz      short loc_18000B171
0x18000b153  test    dword ptr [rcx+44h], 800h
0x18000b15a  jz      short loc_18000B171
0x18000b15c  mov     rcx, [rcx+38h]
0x18000b160  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b167  mov     edx, 0Ah
0x18000b16c  call    WPP_SF_
0x18000b171  mov     r9d, 43h ; 'C'
0x18000b177  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18000b17e  lea     rdx, [rsp+58h+arg_0]
0x18000b183  mov     ecx, 38h ; '8'
0x18000b188  call    cs:__imp_AllocateMemory
0x18000b18e  mov     edi, eax
0x18000b190  test    eax, eax
0x18000b192  jz      short loc_18000B1C8
0x18000b194  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b19b  cmp     rcx, r15
0x18000b19e  jz      loc_18000B272
0x18000b1a4  test    byte ptr [rcx+44h], 1
0x18000b1a8  jz      short loc_18000B1ED
0x18000b1aa  mov     rcx, [rcx+38h]
0x18000b1ae  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b1b5  mov     edx, 0Bh
0x18000b1ba  mov     [rsp+58h+var_38], eax
0x18000b1be  mov     r9d, esi
0x18000b1c1  call    WPP_SF_dd
0x18000b1c6  jmp     short loc_18000B1E6
0x18000b1c8  mov     rax, [rsp+58h+arg_0]
0x18000b1cd  mov     dword ptr [rax+10h], 4
0x18000b1d4  mov     rax, [rsp+58h+arg_0]
0x18000b1d9  mov     [rax+20h], r12d
0x18000b1dd  mov     rax, [rsp+58h+arg_0]
0x18000b1e2  mov     [rax+18h], rbx
0x18000b1e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1ed  cmp     rcx, r15
0x18000b1f0  jz      short loc_18000B21A
0x18000b1f2  test    dword ptr [rcx+44h], 800h
0x18000b1f9  jz      short loc_18000B21A
0x18000b1fb  mov     rcx, [rcx+38h]
0x18000b1ff  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000b206  mov     edx, 0Ch
0x18000b20b  mov     r9d, edi
0x18000b20e  call    WPP_SF_D
0x18000b213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b21a  test    edi, edi
0x18000b21c  jz      short loc_18000B234
0x18000b21e  cmp     rcx, r15
0x18000b221  jz      short loc_18000B272
0x18000b223  test    byte ptr [rcx+44h], 1
0x18000b227  jz      short loc_18000B272
0x18000b229  mov     edx, 13h
0x18000b22e  mov     [rsp+58h+var_38], edi
0x18000b232  jmp     short loc_18000B25F
0x18000b234  mov     rcx, [rsp+58h+arg_0]
0x18000b239  call    QueueSupplicantEvent
0x18000b23e  mov     edi, eax
0x18000b240  test    eax, eax
0x18000b242  jz      short loc_18000B27C
0x18000b244  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b24b  cmp     rcx, r15
0x18000b24e  jz      short loc_18000B272
0x18000b250  test    byte ptr [rcx+44h], 1
0x18000b254  jz      short loc_18000B272
0x18000b256  mov     edx, 14h
0x18000b25b  mov     [rsp+58h+var_38], eax
0x18000b25f  mov     rcx, [rcx+38h]
0x18000b263  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000b26a  mov     r9d, ebp
0x18000b26d  call    WPP_SF_dd
0x18000b272  mov     rcx, [rsp+58h+arg_0]
0x18000b277  call    OneXDeleteEvent
0x18000b27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b283  cmp     rcx, r15
0x18000b286  jz      short loc_18000B2B0
0x18000b288  test    dword ptr [rcx+44h], 800h
0x18000b28f  jz      short loc_18000B2B0
0x18000b291  mov     rcx, [rcx+38h]
0x18000b295  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000b29c  mov     edx, 15h
0x18000b2a1  mov     r9d, edi
0x18000b2a4  call    WPP_SF_D
0x18000b2a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b0  test    edi, edi
0x18000b2b2  jz      short loc_18000B2E2
0x18000b2b4  cmp     rcx, r15
0x18000b2b7  jz      short loc_18000B308
0x18000b2b9  test    byte ptr [rcx+44h], 1
0x18000b2bd  jz      short loc_18000B2E2
0x18000b2bf  mov     edx, 57h ; 'W'
0x18000b2c4  mov     rcx, [rcx+38h]
0x18000b2c8  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18000b2cf  mov     r9d, r14d
0x18000b2d2  mov     [rsp+58h+var_38], edi
0x18000b2d6  call    WPP_SF_dd
0x18000b2db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2e2  cmp     rcx, r15
0x18000b2e5  jz      short loc_18000B308
  ... truncated ...
```
