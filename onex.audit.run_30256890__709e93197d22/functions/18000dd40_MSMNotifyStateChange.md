# MSMNotifyStateChange

- ea: `0x18000dd40`
- end: `0x18000e21b`
- name: `MSMNotifyStateChange`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000ba30`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000dd40`
- `0x18000f290`
- `0x180010ae0`
- `0x180012070`
- `0x1800127a0`
- `0x180020250`
- `0x1800214f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e166`
- `MobileNetworking!ReleaseWriteLock` at `0x18000dfbf`
- `MobileNetworking!ReleaseWriteLock` at `0x18000dfbf`
- `MobileNetworking!AcquireWriteLock` at `0x18000e026`
- `MobileNetworking!AcquireWriteLock` at `0x18000e026`
- `MobileNetworking!FreeMemory` at `0x18000e19f`
- `MobileNetworking!FreeMemory` at `0x18000e19f`

## string_xrefs

- `0x18000dfae`: `MSMUpdateOneXResult`
- `0x18000e015`: `MSMUpdateOneXResult`

## pseudocode

```c
__int64 __fastcall MSMNotifyStateChange(__int64 a1)
{
  unsigned int v1; // esi
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // r14d
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  int updated; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // r12
  unsigned int v13; // ebp
  __int64 v14; // r13
  _DWORD *v15; // rsi
  _DWORD *v16; // rdi
  _DWORD *v17; // r14
  _DWORD *v18; // r15
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  void *v22; // rcx
  _BYTE *v23; // rax
  __int64 v24; // rcx
  unsigned int v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+38h] [rbp-50h] BYREF
  __int64 v28; // [rsp+40h] [rbp-48h]
  __int128 v29; // [rsp+48h] [rbp-40h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  v27 = 0;
  v26 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
  if ( (*(_BYTE *)(a1 + 24) & 1) != 0 )
  {
    LODWORD(v29) = *(_DWORD *)(a1 + 116);
    DWORD1(v29) = *(_DWORD *)(a1 + 2400);
    DWORD2(v29) = *(_DWORD *)(a1 + 124);
    HIDWORD(v29) = *(_DWORD *)(a1 + 2464);
    v3 = MSMSendOneXEventNotification(a1, 65537, 16, &v29);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v1, v3);
    }
  }
  v4 = CreateOneXResultCopy(a1, &v27, &v26);
  v6 = v26;
  v7 = v4;
  if ( !v4 )
  {
    updated = MSMSendResultUpdateNotification(a1, v5, v27);
    if ( updated )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_18:
        v11 = *(_QWORD *)(a1 + 2368);
        v12 = v27;
        v13 = *(_DWORD *)(a1 + 20);
        v14 = *(_QWORD *)(a1 + 192);
        v28 = v11;
        if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
        {
          WPP_SF_(v10[7], 25, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
          v10 = WPP_GLOBAL_Control;
        }
        if ( *(_DWORD *)(a1 + 80) == *(_DWORD *)(a1 + 28) )
        {
          v15 = (_DWORD *)(a1 + 40);
          v16 = (_DWORD *)(a1 + 92);
          if ( *(_DWORD *)(a1 + 92) == *(_DWORD *)(a1 + 40) )
          {
            v17 = (_DWORD *)(a1 + 44);
            v18 = (_DWORD *)(a1 + 96);
            if ( *(_DWORD *)(a1 + 96) == *(_DWORD *)(a1 + 44) )
            {
              if ( v10 == &WPP_GLOBAL_Control )
              {
LABEL_41:
                if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
                  WPP_SF_(v10[7], 61, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
                v20 = *(_DWORD *)(a1 + 36);
                *(_QWORD *)(a1 + 80) = *(_QWORD *)(a1 + 28);
                *(_DWORD *)(a1 + 88) = v20;
                *v16 = *v15;
                *v18 = *v17;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
                {
                  WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
                }
                v6 = v26;
                v7 = 0;
                *(_OWORD *)(a1 + 112) = v29;
                goto LABEL_48;
              }
              if ( *((char *)v10 + 68) >= 0 )
              {
LABEL_38:
                if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
                {
                  WPP_SF_D(v10[7], 29, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
                  v10 = WPP_GLOBAL_Control;
                }
                goto LABEL_41;
              }
              WPP_SF_d(v10[7], 28, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v13);
LABEL_37:
              v10 = WPP_GLOBAL_Control;
              goto LABEL_38;
            }
            v6 = v26;
          }
          v11 = v28;
        }
        if ( v10 != &WPP_GLOBAL_Control && *((char *)v10 + 68) < 0 )
          WPP_SF_d(v10[7], 26, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v13);
        ReleaseWriteLock(a1, a1 + 2896, "MSMUpdateOneXResult", 224);
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(a1 + 2280))(v14, v11, v6, v12);
        if ( v19
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v13, v19);
        }
        AcquireWriteLock(a1, a1 + 2896, "MSMUpdateOneXResult", 238);
        v15 = (_DWORD *)(a1 + 40);
        v16 = (_DWORD *)(a1 + 92);
        v17 = (_DWORD *)(a1 + 44);
        v18 = (_DWORD *)(a1 + 96);
        goto LABEL_37;
      }
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v1, updated);
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_52;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 37, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v1, v4);
LABEL_48:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v8[7], 20, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
LABEL_52:
  if ( v27 )
  {
    v21 = v27 + *(unsigned int *)(v27 + 24);
    if ( v21 )
    {
      v22 = *(void **)(v21 + 32);
      if ( v22 )
        CloseHandle(v22);
    }
    v23 = (_BYTE *)v27;
    v24 = v6;
    if ( v6 )
    {
      do
      {
        *v23++ = 0;
        --v24;
      }
      while ( v24 );
    }
    FreeMemory(&v27, "FreeOneXResult", 316);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(v8[7], 21, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, 0);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
      WPP_SF_D(v8[7], 41, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18000dd40  mov     r11, rsp
0x18000dd43  push    rdi
0x18000dd44  push    r15
0x18000dd46  sub     rsp, 78h
0x18000dd4a  mov     rax, cs:__security_cookie
0x18000dd51  xor     rax, rsp
0x18000dd54  mov     [rsp+88h+var_30], rax
0x18000dd59  mov     [r11+10h], rbx
0x18000dd5d  xor     eax, eax
0x18000dd5f  mov     [r11+20h], rsi
0x18000dd63  xorps   xmm0, xmm0
0x18000dd66  mov     esi, [rcx+14h]
0x18000dd69  mov     rbx, rcx
0x18000dd6c  mov     [r11-28h], r14
0x18000dd70  mov     [r11-50h], rax
0x18000dd74  mov     [rsp+88h+var_58], eax
0x18000dd78  movups  [rsp+88h+var_40], xmm0
0x18000dd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd84  lea     r15, WPP_GLOBAL_Control
0x18000dd8b  cmp     rcx, r15
0x18000dd8e  jz      short loc_18000DDAE
0x18000dd90  test    dword ptr [rcx+44h], 800h
0x18000dd97  jz      short loc_18000DDAE
0x18000dd99  mov     rcx, [rcx+38h]
0x18000dd9d  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000dda4  mov     edx, 23h ; '#'
0x18000dda9  call    WPP_SF_
0x18000ddae  test    byte ptr [rbx+18h], 1
0x18000ddb2  jz      short loc_18000DE20
0x18000ddb4  mov     eax, [rbx+74h]
0x18000ddb7  lea     r9, [rsp+88h+var_40]
0x18000ddbc  mov     dword ptr [rsp+88h+var_40], eax
0x18000ddc0  mov     edx, 10001h
0x18000ddc5  mov     eax, [rbx+960h]
0x18000ddcb  mov     r8d, 10h
0x18000ddd1  mov     dword ptr [rsp+88h+var_40+4], eax
0x18000ddd5  mov     rcx, rbx
0x18000ddd8  mov     eax, [rbx+7Ch]
0x18000dddb  mov     dword ptr [rsp+88h+var_40+8], eax
0x18000dddf  mov     eax, [rbx+9A0h]
0x18000dde5  mov     dword ptr [rsp+88h+var_40+0Ch], eax
0x18000dde9  call    MSMSendOneXEventNotification
0x18000ddee  test    eax, eax
0x18000ddf0  jz      short loc_18000DE20
0x18000ddf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddf9  cmp     rcx, r15
0x18000ddfc  jz      short loc_18000DE20
0x18000ddfe  test    byte ptr [rcx+44h], 1
0x18000de02  jz      short loc_18000DE20
0x18000de04  mov     rcx, [rcx+38h]
0x18000de08  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000de0f  mov     edx, 24h ; '$'
0x18000de14  mov     [rsp+88h+var_68], eax
0x18000de18  mov     r9d, esi
0x18000de1b  call    WPP_SF_dd
0x18000de20  lea     r8, [rsp+88h+var_58]
0x18000de25  mov     rcx, rbx
0x18000de28  lea     rdx, [rsp+88h+var_50]
0x18000de2d  call    CreateOneXResultCopy
0x18000de32  mov     r14d, [rsp+88h+var_58]
0x18000de37  mov     edi, eax
0x18000de39  test    eax, eax
0x18000de3b  jz      short loc_18000DE78
0x18000de3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de44  cmp     rcx, r15
0x18000de47  jz      loc_18000E13B
0x18000de4d  test    byte ptr [rcx+44h], 1
0x18000de51  jz      loc_18000E111
0x18000de57  mov     rcx, [rcx+38h]
0x18000de5b  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000de62  mov     edx, 25h ; '%'
0x18000de67  mov     [rsp+88h+var_68], eax
0x18000de6b  mov     r9d, esi
0x18000de6e  call    WPP_SF_dd
0x18000de73  jmp     loc_18000E10A
0x18000de78  mov     r8, [rsp+88h+var_50]
0x18000de7d  mov     rcx, rbx
0x18000de80  mov     [rsp+88h+arg_10], rbp
0x18000de88  mov     [rsp+88h+var_18], r12
0x18000de8d  mov     [rsp+88h+var_20], r13
0x18000de92  call    MSMSendResultUpdateNotification
0x18000de97  test    eax, eax
0x18000de99  jz      short loc_18000DEC9
0x18000de9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dea2  cmp     rcx, r15
0x18000dea5  jz      short loc_18000DED0
0x18000dea7  test    byte ptr [rcx+44h], 1
0x18000deab  jz      short loc_18000DED0
0x18000dead  mov     rcx, [rcx+38h]
0x18000deb1  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000deb8  mov     edx, 26h ; '&'
0x18000debd  mov     [rsp+88h+var_68], eax
0x18000dec1  mov     r9d, esi
0x18000dec4  call    WPP_SF_dd
0x18000dec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ded0  mov     rsi, [rbx+940h]
0x18000ded7  mov     r12, [rsp+88h+var_50]
0x18000dedc  mov     ebp, [rbx+14h]
0x18000dedf  mov     r13, [rbx+0C0h]
0x18000dee6  mov     [rsp+88h+var_48], rsi
0x18000deeb  cmp     rcx, r15
0x18000deee  jz      short loc_18000DF15
0x18000def0  test    dword ptr [rcx+44h], 800h
0x18000def7  jz      short loc_18000DF15
0x18000def9  mov     rcx, [rcx+38h]
0x18000defd  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000df04  mov     edx, 19h
0x18000df09  call    WPP_SF_
0x18000df0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df15  mov     eax, [rbx+1Ch]
0x18000df18  cmp     [rbx+50h], eax
0x18000df1b  jnz     short loc_18000DF85
0x18000df1d  mov     eax, [rbx+28h]
0x18000df20  lea     rsi, [rbx+28h]
0x18000df24  cmp     [rbx+5Ch], eax
0x18000df27  lea     rdi, [rbx+5Ch]
0x18000df2b  jnz     short loc_18000DF80
0x18000df2d  mov     eax, [rbx+2Ch]
0x18000df30  lea     r14, [rbx+2Ch]
0x18000df34  cmp     [rbx+60h], eax
0x18000df37  lea     r15, [rbx+60h]
0x18000df3b  jnz     short loc_18000DF74
0x18000df3d  lea     r12, WPP_GLOBAL_Control
0x18000df44  cmp     rcx, r12
0x18000df47  jz      loc_18000E077
0x18000df4d  test    byte ptr [rcx+44h], 80h
0x18000df51  jz      loc_18000E04A
0x18000df57  mov     rcx, [rcx+38h]
0x18000df5b  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000df62  mov     edx, 1Ch
0x18000df67  mov     r9d, ebp
0x18000df6a  call    WPP_SF_d
0x18000df6f  jmp     loc_18000E043
0x18000df74  mov     r14d, [rsp+88h+var_58]
0x18000df79  lea     r15, WPP_GLOBAL_Control
0x18000df80  mov     rsi, [rsp+88h+var_48]
0x18000df85  cmp     rcx, r15
0x18000df88  jz      short loc_18000DFA8
0x18000df8a  test    byte ptr [rcx+44h], 80h
0x18000df8e  jz      short loc_18000DFA8
0x18000df90  mov     rcx, [rcx+38h]
0x18000df94  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000df9b  mov     edx, 1Ah
0x18000dfa0  mov     r9d, ebp
0x18000dfa3  call    WPP_SF_d
0x18000dfa8  mov     r9d, 0E0h
0x18000dfae  lea     r8, aMsmupdateonexr; "MSMUpdateOneXResult"
0x18000dfb5  lea     rdx, [rbx+0B50h]
0x18000dfbc  mov     rcx, rbx
0x18000dfbf  call    cs:__imp_ReleaseWriteLock
0x18000dfc5  mov     rax, [rbx+8E8h]
0x18000dfcc  mov     r9, r12
0x18000dfcf  mov     r8d, r14d
0x18000dfd2  mov     rdx, rsi
0x18000dfd5  mov     rcx, r13
0x18000dfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfdd  test    eax, eax
0x18000dfdf  jz      short loc_18000E00F
0x18000dfe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfe8  cmp     rcx, r15
0x18000dfeb  jz      short loc_18000E00F
0x18000dfed  test    byte ptr [rcx+44h], 1
0x18000dff1  jz      short loc_18000E00F
0x18000dff3  mov     rcx, [rcx+38h]
0x18000dff7  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000dffe  mov     edx, 1Bh
0x18000e003  mov     [rsp+88h+var_68], eax
0x18000e007  mov     r9d, ebp
0x18000e00a  call    WPP_SF_dd
0x18000e00f  mov     r9d, 0EEh
0x18000e015  lea     r8, aMsmupdateonexr; "MSMUpdateOneXResult"
0x18000e01c  lea     rdx, [rbx+0B50h]
0x18000e023  mov     rcx, rbx
0x18000e026  call    cs:__imp_AcquireWriteLock
0x18000e02c  lea     rsi, [rbx+28h]
0x18000e030  lea     rdi, [rbx+5Ch]
0x18000e034  lea     r14, [rbx+2Ch]
0x18000e038  lea     r15, [rbx+60h]
0x18000e03c  lea     r12, WPP_GLOBAL_Control
0x18000e043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e04a  cmp     rcx, r12
0x18000e04d  jz      short loc_18000E077
0x18000e04f  test    dword ptr [rcx+44h], 800h
0x18000e056  jz      short loc_18000E077
0x18000e058  mov     rcx, [rcx+38h]
0x18000e05c  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000e063  mov     edx, 1Dh
0x18000e068  xor     r9d, r9d
0x18000e06b  call    WPP_SF_D
0x18000e070  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e077  mov     r13, [rsp+88h+var_20]
0x18000e07c  mov     rbp, [rsp+88h+arg_10]
0x18000e084  cmp     rcx, r12
0x18000e087  mov     r12, [rsp+88h+var_18]
0x18000e08c  jz      short loc_18000E0AC
0x18000e08e  test    dword ptr [rcx+44h], 800h
0x18000e095  jz      short loc_18000E0AC
0x18000e097  mov     rcx, [rcx+38h]
0x18000e09b  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e0a2  mov     edx, 3Dh ; '='
0x18000e0a7  call    WPP_SF_
0x18000e0ac  mov     eax, [rbx+24h]
0x18000e0af  movsd   xmm0, qword ptr [rbx+1Ch]
0x18000e0b4  movsd   qword ptr [rbx+50h], xmm0
0x18000e0b9  mov     [rbx+58h], eax
0x18000e0bc  mov     eax, [rsi]
0x18000e0be  mov     [rdi], eax
0x18000e0c0  mov     eax, [r14]
0x18000e0c3  mov     [r15], eax
0x18000e0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0cd  lea     r15, WPP_GLOBAL_Control
0x18000e0d4  cmp     rcx, r15
0x18000e0d7  jz      short loc_18000E0FA
0x18000e0d9  test    dword ptr [rcx+44h], 800h
0x18000e0e0  jz      short loc_18000E0FA
0x18000e0e2  mov     rcx, [rcx+38h]
0x18000e0e6  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000e0ed  mov     edx, 3Eh ; '>'
0x18000e0f2  xor     r9d, r9d
0x18000e0f5  call    WPP_SF_D
0x18000e0fa  movups  xmm0, [rsp+88h+var_40]
0x18000e0ff  mov     r14d, [rsp+88h+var_58]
0x18000e104  xor     edi, edi
0x18000e106  movups  xmmword ptr [rbx+70h], xmm0
0x18000e10a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e111  cmp     rcx, r15
0x18000e114  jz      short loc_18000E13B
0x18000e116  test    dword ptr [rcx+44h], 800h
0x18000e11d  jz      short loc_18000E13B
0x18000e11f  mov     rcx, [rcx+38h]
0x18000e123  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18000e12a  mov     edx, 14h
0x18000e12f  call    WPP_SF_
0x18000e134  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e13b  mov     rdx, [rsp+88h+var_50]
0x18000e140  mov     rsi, [rsp+88h+arg_18]
0x18000e148  mov     rbx, [rsp+88h+arg_8]
0x18000e150  test    rdx, rdx
0x18000e153  jz      short loc_18000E1AC
0x18000e155  mov     ecx, [rdx+18h]
0x18000e158  add     rcx, rdx
0x18000e15b  jz      short loc_18000E16C
0x18000e15d  mov     rcx, [rcx+20h]; hObject
0x18000e161  test    rcx, rcx
0x18000e164  jz      short loc_18000E16C
0x18000e166  call    cs:__imp_CloseHandle
0x18000e16c  mov     rax, [rsp+88h+var_50]
0x18000e171  mov     ecx, r14d
0x18000e174  test    r14d, r14d
0x18000e177  jz      short loc_18000E18D
0x18000e179  nop     dword ptr [rax+00000000h]
0x18000e180  mov     byte ptr [rax], 0
0x18000e183  lea     rax, [rax+1]
0x18000e187  sub     rcx, 1
0x18000e18b  jnz     short loc_18000E180
0x18000e18d  mov     r8d, 13Ch
0x18000e193  lea     rdx, aFreeonexresult; "FreeOneXResult"
0x18000e19a  lea     rcx, [rsp+88h+var_50]
0x18000e19f  call    cs:__imp_FreeMemory
0x18000e1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ac  mov     r14, [rsp+88h+var_28]
0x18000e1b1  cmp     rcx, r15
0x18000e1b4  jz      short loc_18000E204
0x18000e1b6  test    dword ptr [rcx+44h], 800h
0x18000e1bd  jz      short loc_18000E1DE
0x18000e1bf  mov     rcx, [rcx+38h]
0x18000e1c3  lea     r8, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x18000e1ca  mov     edx, 15h
0x18000e1cf  xor     r9d, r9d
0x18000e1d2  call    WPP_SF_D
0x18000e1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1de  cmp     rcx, r15
0x18000e1e1  jz      short loc_18000E204
0x18000e1e3  test    dword ptr [rcx+44h], 800h
0x18000e1ea  jz      short loc_18000E204
0x18000e1ec  mov     rcx, [rcx+38h]
0x18000e1f0  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000e1f7  mov     edx, 29h ; ')'
0x18000e1fc  mov     r9d, edi
0x18000e1ff  call    WPP_SF_D
0x18000e204  mov     eax, edi
0x18000e206  mov     rcx, [rsp+88h+var_30]
0x18000e20b  xor     rcx, rsp; StackCookie
0x18000e20e  call    __security_check_cookie
0x18000e213  add     rsp, 78h
0x18000e217  pop     r15
0x18000e219  pop     rdi
0x18000e21a  retn
```
