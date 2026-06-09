# lldpSetPortAdminConfig

- ea: `0x1400114d0`
- end: `0x140011863`
- name: `lldpSetPortAdminConfig`
- size: `915`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x14000f330`

## callees

- `0x140002180`
- `0x140003d80`
- `0x140004a60`
- `0x140004b00`
- `0x140006720`
- `0x14000f3b8`
- `0x1400114d0`
- `0x140011a40`
- `0x140011cac`

## pseudocode

```c
__int64 __fastcall lldpSetPortAdminConfig(char *Context, __int64 a2)
{
  __int64 i; // rax
  unsigned int v6; // r8d
  unsigned int v7; // r15d
  char v8; // r12
  __int64 j; // rbx
  unsigned int v10; // ebp
  char *v11; // r14
  unsigned int v12; // r11d
  unsigned int v13; // r10d
  int v14; // eax
  int v15; // ebp
  int v16; // r13d
  int v17; // ecx
  int v18; // r8d
  int v19; // r12d
  int v20; // edx
  int v21; // r9d
  char v22; // bl
  char v23; // r8
  char v24; // dl
  int v25; // ebp
  char v26; // cl
  int v27; // r12d
  char v28; // al
  int v29; // eax
  __int64 v30; // r9
  __int128 v31; // xmm1

  if ( *(_DWORD *)a2 == 1 && *(_QWORD *)(a2 + 8) >= 0x2Cu )
  {
    for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
    {
      v6 = *(_DWORD *)(*((unsigned int *)&lldpParameterRules + 6 * i + 5) + a2);
      if ( v6 != -1
        && (v6 < *((_DWORD *)&lldpParameterRules + 6 * i + 2) || v6 > LODWORD((&lldpParameterRules)[3 * i + 1])) )
      {
        return 3221226539LL;
      }
    }
    v7 = 0;
    v8 = 0;
    for ( j = 0; (unsigned int)j < 7; j = (unsigned int)(j + 1) )
    {
      v10 = *(_DWORD *)(*((unsigned int *)&lldpParameterRules + 6 * j + 5) + a2);
      if ( v10 != -1 )
      {
        if ( *(_BYTE *)(a2 + 44) )
          v8 = 1;
        v11 = &Context[4 * (int)j];
        if ( *((_DWORD *)v11 + 62) == v10 )
        {
          v7 = 0;
        }
        else
        {
          if ( v10 < *((_DWORD *)&lldpParameterRules + 6 * (int)j + 2)
            || v10 > LODWORD((&lldpParameterRules)[3 * (int)j + 1]) )
          {
            v7 = -1073740757;
            v30 = 3221226539LL;
LABEL_56:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids, v30);
            break;
          }
          v7 = 0;
          if ( v8 && (v29 = lldpWriteConfigToRegistry((__int64)Context, j, v10), (v7 = v29) != 0) )
          {
            v30 = (unsigned int)v29;
            if ( v29 < 0 )
              goto LABEL_56;
          }
          else
          {
            *((_DWORD *)v11 + 62) = v10;
          }
        }
      }
    }
    v12 = *((_DWORD *)Context + 66);
    v13 = *((_DWORD *)Context + 73);
    v14 = *((_DWORD *)Context + 74);
    v15 = *((_DWORD *)Context + 62);
    v16 = *((_DWORD *)Context + 67);
    v17 = *((_DWORD *)Context + 64);
    v18 = *((_DWORD *)Context + 63);
    v19 = *((_DWORD *)Context + 69);
    v20 = *((_DWORD *)Context + 71);
    v21 = *((_DWORD *)Context + 70);
    if ( v12 != v13 )
    {
      if ( v12 <= v13 )
      {
        if ( v12 < v13 )
        {
          if ( (signed int)v13 >= *((_DWORD *)Context + 218) )
            v13 = *((_DWORD *)Context + 218);
          *((_DWORD *)Context + 218) = v13;
        }
      }
      else
      {
        *((_DWORD *)Context + 218) += v12 - v13;
      }
    }
    if ( (v17 != v20 || (v22 = 0, v16 != v14)) && (v22 = 1, v17 != v20) || v18 != v21 )
      lldpUpdateTxTtl(Context);
    if ( v15 != v19 )
    {
      v23 = v15 && (v15 == 1 || v15 == 3);
      v24 = v19 && (v19 == 1 || v19 == 3);
      v26 = 0;
      if ( v15 )
      {
        v25 = v15 - 1;
        if ( v25 )
        {
          if ( (unsigned int)(v25 - 1) < 2 )
            v26 = 1;
        }
      }
      v28 = 0;
      if ( v19 )
      {
        v27 = v19 - 1;
        if ( v27 )
        {
          if ( (unsigned int)(v27 - 1) < 2 )
            v28 = 1;
        }
      }
      if ( v23 != v24 )
        v22 = 1;
      if ( v26 != v28 )
        lldpAdjustRxPacketFilters((__int64)Context);
    }
    if ( v22 )
      lldpEnableTxFastMode(Context);
    if ( memcmp(Context + 248, Context + 276, 0x1Cu) )
    {
      v31 = *(_OWORD *)(Context + 260);
      *(_OWORD *)(Context + 276) = *(_OWORD *)(Context + 248);
      *((_OWORD *)Context + 18) = v31;
      lldpQueueChangeNotificationEx(Context);
    }
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids);
    return 3221225560LL;
  }
}

```

## disassembly

```asm
0x1400114d0  push    rsi
0x1400114d2  push    rdi
0x1400114d3  sub     rsp, 38h
0x1400114d7  cmp     dword ptr [rdx], 1
0x1400114da  mov     rdi, rdx
0x1400114dd  mov     rsi, rcx
0x1400114e0  jz      short loc_140011506
0x1400114e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114e9  lea     rax, WPP_GLOBAL_Control
0x1400114f0  cmp     rcx, rax
0x1400114f3  jnz     loc_14001183F
0x1400114f9  mov     eax, 0C0000058h
0x1400114fe  add     rsp, 38h
0x140011502  pop     rdi
0x140011503  pop     rsi
0x140011504  retn
0x140011506  cmp     qword ptr [rdx+8], 2Ch ; ','
0x14001150b  jb      short loc_1400114E2
0x14001150d  mov     [rsp+48h+var_18], r13
0x140011512  xor     eax, eax
0x140011514  lea     r13, lldpParameterRules
0x14001151b  mov     [rsp+48h+var_28], r15
0x140011520  cmp     eax, 7
0x140011523  jnb     short loc_140011552
0x140011525  lea     rdx, [rax+rax*2]
0x140011529  mov     ecx, [r13+rdx*8+14h]
0x14001152e  mov     r8d, [rcx+rdi]
0x140011532  cmp     r8d, 0FFFFFFFFh
0x140011536  jz      short loc_14001154E
0x140011538  cmp     r8d, [r13+rdx*8+8]
0x14001153d  jb      loc_1400116F1
0x140011543  cmp     r8d, [r13+rdx*8+10h]
0x140011548  ja      loc_1400116F1
0x14001154e  inc     eax
0x140011550  jmp     short loc_140011520
0x140011552  mov     [rsp+48h+arg_0], rbx
0x140011557  xor     r15d, r15d
0x14001155a  mov     [rsp+48h+arg_10], rbp
0x14001155f  mov     [rsp+48h+arg_18], r12
0x140011564  xor     r12b, r12b
0x140011567  xor     ebx, ebx
0x140011569  mov     [rsp+48h+var_20], r14
0x14001156e  xchg    ax, ax
0x140011570  cmp     ebx, 7
0x140011573  jnb     short loc_1400115AA
0x140011575  lea     rcx, [rbx+rbx*2]
0x140011579  mov     eax, [r13+rcx*8+14h]
0x14001157e  mov     ebp, [rax+rdi]
0x140011581  cmp     ebp, 0FFFFFFFFh
0x140011584  jz      short loc_1400115A6
0x140011586  cmp     byte ptr [rdi+2Ch], 0
0x14001158a  jz      short loc_14001158F
0x14001158c  mov     r12b, 1
0x14001158f  movsxd  rax, ebx
0x140011592  lea     r14, [rsi+rax*4]
0x140011596  cmp     [r14+0F8h], ebp
0x14001159d  jnz     loc_1400116FB
0x1400115a3  xor     r15d, r15d
0x1400115a6  inc     ebx
0x1400115a8  jmp     short loc_140011570
0x1400115aa  mov     r11d, [rsi+108h]
0x1400115b1  mov     r10d, [rsi+124h]
0x1400115b8  mov     eax, [rsi+128h]
0x1400115be  mov     ebp, [rsi+0F8h]
0x1400115c4  mov     r13d, [rsi+10Ch]
0x1400115cb  mov     ecx, [rsi+100h]
0x1400115d1  mov     r8d, [rsi+0FCh]
0x1400115d8  mov     r12d, [rsi+114h]
0x1400115df  mov     edx, [rsi+11Ch]
0x1400115e5  mov     r9d, [rsi+118h]
0x1400115ec  mov     [rsp+48h+arg_8], eax
0x1400115f0  cmp     r11d, r10d
0x1400115f3  jnz     loc_140011785
0x1400115f9  cmp     ecx, edx
0x1400115fb  jnz     short loc_14001165D
0x1400115fd  xor     bl, bl
0x1400115ff  cmp     r13d, eax
0x140011602  jnz     short loc_14001165D
0x140011604  cmp     r8d, r9d
0x140011607  jnz     short loc_140011663
0x140011609  cmp     ebp, r12d
0x14001160c  jnz     short loc_14001166D
0x14001160e  mov     r12, [rsp+48h+arg_18]
0x140011613  test    bl, bl
0x140011615  mov     rbx, [rsp+48h+arg_0]
0x14001161a  mov     rbp, [rsp+48h+arg_10]
0x14001161f  jnz     loc_140011801
0x140011625  mov     r8d, 1Ch; Size
0x14001162b  lea     rdx, [rsi+114h]; Buf2
0x140011632  lea     rcx, [rsi+0F8h]; Buf1
0x140011639  call    memcmp
0x14001163e  test    eax, eax
0x140011640  jnz     loc_14001180E
0x140011646  mov     r14, [rsp+48h+var_20]
0x14001164b  mov     eax, r15d
0x14001164e  mov     r15, [rsp+48h+var_28]
0x140011653  mov     r13, [rsp+48h+var_18]
0x140011658  jmp     loc_1400114FE
0x14001165d  mov     bl, 1
0x14001165f  cmp     ecx, edx
0x140011661  jz      short loc_140011604
0x140011663  mov     rcx, rsi
0x140011666  call    lldpUpdateTxTtl
0x14001166b  jmp     short loc_140011609
0x14001166d  mov     ecx, ebp
0x14001166f  test    ebp, ebp
0x140011671  jz      short loc_14001168A
0x140011673  sub     ecx, 1
0x140011676  jz      loc_1400117C4
0x14001167c  sub     ecx, 1
0x14001167f  jz      short loc_14001168A
0x140011681  cmp     ecx, 1
0x140011684  jz      loc_1400117C4
0x14001168a  xor     r8b, r8b
0x14001168d  mov     ecx, r12d
0x140011690  test    r12d, r12d
0x140011693  jz      short loc_1400116AC
0x140011695  sub     ecx, 1
0x140011698  jz      loc_1400117CC
0x14001169e  sub     ecx, 1
0x1400116a1  jz      short loc_1400116AC
0x1400116a3  cmp     ecx, 1
0x1400116a6  jz      loc_1400117CC
0x1400116ac  xor     dl, dl
0x1400116ae  test    ebp, ebp
0x1400116b0  jz      short loc_1400116C9
0x1400116b2  sub     ebp, 1
0x1400116b5  jz      short loc_1400116C9
0x1400116b7  sub     ebp, 1
0x1400116ba  jz      loc_1400117D3
0x1400116c0  cmp     ebp, 1
0x1400116c3  jz      loc_1400117D3
0x1400116c9  xor     cl, cl
0x1400116cb  test    r12d, r12d
0x1400116ce  jz      short loc_1400116EA
0x1400116d0  sub     r12d, 1
0x1400116d4  jz      short loc_1400116EA
0x1400116d6  sub     r12d, 1
0x1400116da  jz      loc_1400117DA
0x1400116e0  cmp     r12d, 1
0x1400116e4  jz      loc_1400117DA
0x1400116ea  xor     al, al
0x1400116ec  jmp     loc_1400117DC
0x1400116f1  mov     eax, 0C000042Bh
0x1400116f6  jmp     loc_14001164E
0x1400116fb  lea     rax, [rax+rax*2]
0x1400116ff  cmp     ebp, [r13+rax*8+8]
0x140011704  jb      short loc_140011741
0x140011706  cmp     ebp, [r13+rax*8+10h]
0x14001170b  ja      short loc_140011741
0x14001170d  xor     r15d, r15d
0x140011710  test    r12b, r12b
0x140011713  jz      short loc_140011735
0x140011715  mov     r8d, ebp
0x140011718  mov     edx, ebx
0x14001171a  mov     rcx, rsi
0x14001171d  call    lldpWriteConfigToRegistry
0x140011722  mov     r15d, eax
0x140011725  test    eax, eax
0x140011727  jz      short loc_140011735
0x140011729  mov     r9d, eax
0x14001172c  test    eax, eax
0x14001172e  js      short loc_14001174A
0x140011730  jmp     loc_1400115A6
0x140011735  mov     [r14+0F8h], ebp
0x14001173c  jmp     loc_1400115A6
0x140011741  mov     r15d, 0C000042Bh
0x140011747  mov     r9d, r15d
0x14001174a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011751  lea     rax, WPP_GLOBAL_Control
0x140011758  cmp     rcx, rax
0x14001175b  jz      loc_1400115AA
0x140011761  cmp     byte ptr [rcx+29h], 2
0x140011765  jb      loc_1400115AA
0x14001176b  mov     rcx, [rcx+18h]
0x14001176f  lea     r8, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids
0x140011776  mov     edx, 0Bh
0x14001177b  call    WPP_SF_d
0x140011780  jmp     loc_1400115AA
0x140011785  jbe     short loc_14001179C
0x140011787  mov     eax, [rsi+368h]
0x14001178d  sub     r11d, r10d
0x140011790  add     r11d, eax
0x140011793  mov     [rsi+368h], r11d
0x14001179a  jmp     short loc_1400117BB
0x14001179c  jnb     loc_1400115F9
0x1400117a2  mov     eax, [rsi+368h]
0x1400117a8  cmp     r10d, eax
0x1400117ab  jl      short loc_1400117B4
0x1400117ad  mov     r10d, [rsi+368h]
0x1400117b4  mov     [rsi+368h], r10d
0x1400117bb  mov     eax, [rsp+48h+arg_8]
0x1400117bf  jmp     loc_1400115F9
0x1400117c4  mov     r8b, 1
0x1400117c7  jmp     loc_14001168D
0x1400117cc  mov     dl, 1
0x1400117ce  jmp     loc_1400116AE
0x1400117d3  mov     cl, 1
0x1400117d5  jmp     loc_1400116CB
0x1400117da  mov     al, 1
0x1400117dc  cmp     r8b, dl
0x1400117df  movzx   ebx, bl
0x1400117e2  mov     r9d, 1
0x1400117e8  cmovnz  ebx, r9d
0x1400117ec  cmp     cl, al
0x1400117ee  jz      loc_14001160E
0x1400117f4  mov     rcx, rsi
0x1400117f7  call    lldpAdjustRxPacketFilters
0x1400117fc  jmp     loc_14001160E
0x140011801  mov     rcx, rsi
0x140011804  call    lldpEnableTxFastMode
0x140011809  jmp     loc_140011625
0x14001180e  movups  xmm0, xmmword ptr [rsi+0F8h]
0x140011815  xor     edx, edx
0x140011817  mov     r8d, 4
0x14001181d  movups  xmm1, xmmword ptr [rsi+104h]
0x140011824  mov     rcx, rsi; Context
0x140011827  movups  xmmword ptr [rsi+114h], xmm0
0x14001182e  movups  xmmword ptr [rsi+120h], xmm1
0x140011835  call    lldpQueueChangeNotificationEx
0x14001183a  jmp     loc_140011646
0x14001183f  cmp     byte ptr [rcx+29h], 2
0x140011843  jb      loc_1400114F9
0x140011849  mov     rcx, [rcx+18h]
0x14001184d  lea     r8, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids
0x140011854  mov     edx, 0Ah
0x140011859  call    WPP_SF_
0x14001185e  jmp     loc_1400114F9
```
