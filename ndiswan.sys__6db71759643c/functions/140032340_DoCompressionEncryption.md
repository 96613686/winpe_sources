# DoCompressionEncryption

- ea: `0x140032340`
- end: `0x140032b94`
- name: `DoCompressionEncryption`
- size: `2132`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140031b80`

## callees

- `0x140008bf4`
- `0x14000a290`
- `0x14000a2c0`
- `0x1400107dc`
- `0x140016400`
- `0x1400320f0`
- `0x140032300`
- `0x140032340`
- `0x140033c30`
- `0x1400345a0`
- `0x140035ef8`

## import_xrefs

- `cng!BCryptDestroyKey` at `0x140032947`
- `cng!BCryptDestroyKey` at `0x140032b04`
- `cng!BCryptDestroyKey` at `0x140032947`
- `cng!BCryptDestroyKey` at `0x140032b04`
- `cng!BCryptGenerateSymmetricKey` at `0x1400324c3`
- `cng!BCryptGenerateSymmetricKey` at `0x1400325ab`
- `cng!BCryptGenerateSymmetricKey` at `0x1400324c3`
- `cng!BCryptGenerateSymmetricKey` at `0x1400325ab`
- `cng!BCryptEncrypt` at `0x14003250f`
- `cng!BCryptEncrypt` at `0x140032601`
- `cng!BCryptEncrypt` at `0x14003250f`
- `cng!BCryptEncrypt` at `0x140032601`

## pseudocode

```c
char __fastcall DoCompressionEncryption(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rbp
  int v4; // esi
  __int64 v6; // rdi
  __int64 v8; // r15
  unsigned int v9; // ecx
  unsigned int v10; // eax
  __int16 v11; // ax
  unsigned __int8 *v12; // r12
  __int64 v13; // rdx
  char v14; // bl
  BCRYPT_KEY_HANDLE *v15; // r14
  UCHAR *pbSecret; // r15
  ULONG cbSecret; // ebp
  bool v18; // zf
  BCRYPT_KEY_HANDLE v19; // rcx
  __int64 v20; // rdx
  __int64 SendDesc; // rax
  __int64 v23; // r15
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rcx
  ULONG v36; // eax
  int v37; // edx
  int v38; // r8d
  char v39; // r10
  char v40; // cl
  int v41; // r9d
  char v42; // r11
  char v43; // di
  char v44; // si
  char v45; // bp
  char v46; // r14
  char v47; // r15
  char v48; // r12
  char v49; // r13
  __int16 v50; // [rsp+A0h] [rbp-88h]
  ULONG pcbResult; // [rsp+A4h] [rbp-84h] BYREF
  unsigned __int8 *v52; // [rsp+A8h] [rbp-80h]
  int v53; // [rsp+B0h] [rbp-78h]
  int v54; // [rsp+B4h] [rbp-74h]
  unsigned __int8 *v55; // [rsp+B8h] [rbp-70h]
  PDEVICE_OBJECT v56; // [rsp+C0h] [rbp-68h]
  BCRYPT_KEY_HANDLE *v57; // [rsp+C8h] [rbp-60h]
  UCHAR *v58; // [rsp+D0h] [rbp-58h]
  __int64 v60; // [rsp+138h] [rbp+10h] BYREF
  __int16 v61; // [rsp+140h] [rbp+18h]
  ULONG cbInput; // [rsp+148h] [rbp+20h] BYREF

  v60 = a2;
  v3 = *a3;
  v4 = *(_DWORD *)(a2 + 12);
  v6 = a2;
  v50 = v4;
  v8 = *(_QWORD *)(*a3 + 40);
  cbInput = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  v9 = *(_DWORD *)(v6 + 64);
  v10 = *(_DWORD *)(v6 + 8);
  if ( v10 >= v9 )
  {
    *(_DWORD *)(v6 + 8) = v10 - v9;
    *(_DWORD *)(v3 + 100) += v9;
    v11 = *(_WORD *)(a1 + 1320);
    v12 = (unsigned __int8 *)(*(_QWORD *)(v3 + 88) + *(unsigned int *)(v6 + 8));
    v13 = *(unsigned int *)(v3 + 100);
    v61 = v11 & 0xFFF;
    v14 = HIBYTE(v11) & 0xF;
    v55 = v12;
    cbInput = v13;
    *(_WORD *)(a1 + 1320) = v11 + 1;
    if ( (v4 & 2) != 0 )
    {
      SendDesc = NdisWanAllocateSendDesc(v8);
      v23 = SendDesc;
      if ( SendDesc )
      {
        v24 = (unsigned __int64)*(unsigned int *)(a1 + 1736) << 32;
        v52 = (unsigned __int8 *)(*(unsigned int *)(v6 + 8) + *(_QWORD *)(SendDesc + 88));
        v25 = *(unsigned int *)(a1 + 1652) + cbInput + v24;
        *(_DWORD *)(a1 + 1652) = v25;
        *(_DWORD *)(a1 + 1736) = HIDWORD(v25);
        if ( (v4 & 0x820) != 0 )
          initsendcontext(*(_QWORD *)(a1 + 776));
        v14 |= compress(v12, v52, &cbInput, *(unsigned int **)(a1 + 776));
        HIBYTE(v61) = v14;
        if ( v14 >= 0 )
        {
          memmove(*(void **)(v23 + 88), *(const void **)(v3 + 88), *(unsigned int *)(v6 + 8));
          v29 = *(unsigned int *)(v6 + 16);
          v30 = *(unsigned int *)(v6 + 32);
          v31 = *(unsigned int *)(v6 + 48);
          *(_DWORD *)(v6 + 64) = 0;
          v32 = *(_QWORD *)(v23 + 88);
          *(_QWORD *)(v6 + 24) = v32;
          v33 = v32 + v29;
          *(_QWORD *)(v6 + 40) = v33;
          v34 = v33 + v30;
          *(_QWORD *)(v6 + 56) = v34;
          *(_QWORD *)(v6 + 72) = v34 + v31;
          *(_DWORD *)(v23 + 100) = cbInput;
          *(_QWORD *)(v23 + 48) = *(_QWORD *)(v3 + 48);
          *(_QWORD *)(v23 + 112) = *(_QWORD *)(v3 + 112);
          *(_DWORD *)(v23 + 32) = *(_DWORD *)(v3 + 32);
          *(_DWORD *)(v23 + 28) = *(_DWORD *)(v3 + 28);
          NdisWanFreeSendDesc(v3, v33);
          v13 = *(_DWORD *)(v6 + 8) + cbInput;
          v12 = v52;
          v35 = *(_QWORD *)(*(_QWORD *)(v23 + 80) + 8LL);
          *a3 = v23;
          *(_DWORD *)(v35 + 24) = v13;
        }
        else
        {
          NdisWanFreeSendDesc(v23, v26);
          LOWORD(v4) = v4 | 0x20;
        }
        v27 = cbInput + ((unsigned __int64)*(unsigned int *)(a1 + 1744) << 32);
        v55 = v12;
        v28 = *(unsigned int *)(a1 + 1660) + v27;
        *(_DWORD *)(a1 + 1660) = v28;
        *(_DWORD *)(a1 + 1744) = HIDWORD(v28);
      }
      else
      {
        if ( (v4 & 4) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
          }
          goto LABEL_5;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
        }
        --v61;
        --*(_WORD *)(a1 + 1320);
        v14 = HIBYTE(v61);
        LOWORD(v4) = v4 | 0x20;
      }
      v50 = v4;
    }
LABEL_5:
    if ( (v4 & 4) != 0 )
    {
      v15 = *(BCRYPT_KEY_HANDLE **)(a1 + 1208);
      pbSecret = (UCHAR *)(a1 + 1180);
      cbSecret = *(_DWORD *)(a1 + 1196);
      v58 = (UCHAR *)(a1 + 1180);
      v57 = v15;
      LODWORD(v52) = cbSecret;
      if ( (v4 & 0x20) != 0 && (v4 & 0x800) == 0 )
        CngRsa32Compat_rc4_key_Ex(v15, cbSecret, (PUCHAR)(a1 + 1180));
      v14 |= 0x10u;
      v18 = *(_BYTE *)(a1 + 1320) == 0;
      HIBYTE(v61) = v14;
      if ( v18 || (v4 & 0x800) != 0 )
      {
        if ( (v4 & 0x40) != 0 )
        {
          ++*(_BYTE *)(a1 + 1183);
          *(_BYTE *)(a1 + 1184) += 3;
          *(_BYTE *)(a1 + 1185) += 13;
          *(_BYTE *)(a1 + 1186) += 57;
          *(_BYTE *)(a1 + 1187) += 19;
        }
        else
        {
          GetNewKeyFromSHA(a1 + 1160, v13, a3);
        }
        if ( !v15 )
          __fastfail(7u);
        if ( *v15 )
        {
          BCryptDestroyKey(*v15);
          *v15 = 0;
        }
        if ( BCryptGenerateSymmetricKey(ghAlgRC4, v15, 0, 0, (PUCHAR)(a1 + 1180), cbSecret, 0) < 0 )
          __fastfail(7u);
        pcbResult = 0;
        if ( BCryptEncrypt(*v15, (PUCHAR)(a1 + 1180), cbSecret, 0, 0, 0, (PUCHAR)(a1 + 1180), cbSecret, &pcbResult, 0) < 0 )
          __fastfail(7u);
        if ( (v4 & 0x80u) != 0 )
        {
          *(_WORD *)pbSecret = 9937;
          *(_BYTE *)(a1 + 1182) = -98;
        }
        else if ( (v4 & 0x1000) != 0 )
        {
          *pbSecret = -47;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_8fab404a276b37b5b154f85d9d785092_Traceguids,
              *(unsigned int *)(a1 + 1196));
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v36 = *(unsigned __int8 *)(a1 + 1195);
            v37 = *(unsigned __int8 *)(a1 + 1194);
            v38 = *(unsigned __int8 *)(a1 + 1193);
            v39 = *(_BYTE *)(a1 + 1192);
            v40 = *(_BYTE *)(a1 + 1183);
            v41 = *(unsigned __int8 *)(a1 + 1182);
            v42 = *(_BYTE *)(a1 + 1191);
            v43 = *(_BYTE *)(a1 + 1190);
            v44 = *(_BYTE *)(a1 + 1189);
            v45 = *(_BYTE *)(a1 + 1188);
            v46 = *(_BYTE *)(a1 + 1187);
            v47 = *(_BYTE *)(a1 + 1186);
            v48 = *(_BYTE *)(a1 + 1185);
            v49 = *(_BYTE *)(a1 + 1184);
            pcbResult = v36;
            v53 = v41;
            v54 = *(unsigned __int8 *)(a1 + 1181);
            WPP_SF_DDDDDDDDDDDDDDDD(
              v56->AttachedDevice,
              v37,
              v38,
              *(unsigned __int8 *)(a1 + 1180),
              v54,
              v41,
              v40,
              v49,
              v48,
              v47,
              v46,
              v45,
              v44,
              v43,
              v42,
              v39,
              v38,
              v37,
              v36);
            v6 = v60;
            LOWORD(v4) = v50;
            v15 = v57;
            pbSecret = v58;
            v12 = v55;
            cbSecret = (unsigned int)v52;
          }
        }
        if ( *v15 )
        {
          BCryptDestroyKey(*v15);
          *v15 = 0;
        }
        if ( BCryptGenerateSymmetricKey(ghAlgRC4, v15, 0, 0, pbSecret, cbSecret, 0) < 0 )
          __fastfail(7u);
      }
      v19 = *v15;
      LODWORD(v60) = 0;
      if ( BCryptEncrypt(v19, v12, cbInput, 0, 0, 0, v12, cbInput, (ULONG *)&v60, 0) < 0 )
        __fastfail(7u);
    }
    if ( (v4 & 0x820) != 0 )
      HIBYTE(v61) = v14 | 0x80;
    if ( *(_DWORD *)(v6 + 48) )
    {
      v20 = *(_QWORD *)(v6 + 56) + 1LL;
      if ( (*(_DWORD *)v6 & 0x400) != 0 )
        v20 = *(_QWORD *)(v6 + 56);
      *(_BYTE *)(v20 + 1) = HIBYTE(v61);
      *(_BYTE *)(v20 + 2) = v61;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
    }
    return 1;
  }
  *(_DWORD *)(v6 + 8) = -1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140032340  mov     [rsp+arg_8], rdx
0x140032345  mov     [rsp+arg_0], rcx
0x14003234a  push    rbp
0x14003234b  push    rsi
0x14003234c  push    rdi
0x14003234d  push    r13
0x14003234f  push    r14
0x140032351  push    r15
0x140032353  sub     rsp, 0F8h
0x14003235a  mov     rbp, [r8]
0x14003235d  xor     r9d, r9d
0x140032360  mov     esi, [rdx+0Ch]
0x140032363  mov     r14, r8
0x140032366  mov     rdi, rdx
0x140032369  mov     [rsp+128h+var_88], esi
0x140032370  mov     r13, rcx
0x140032373  mov     r15, [rbp+28h]
0x140032377  mov     [rsp+128h+cbInput], r9d
0x14003237f  mov     rcx, cs:WPP_GLOBAL_Control
0x140032386  lea     rdx, WPP_GLOBAL_Control
0x14003238d  cmp     rcx, rdx
0x140032390  jz      short loc_14003239D
0x140032392  mov     eax, [rcx+2Ch]
0x140032395  test    al, 8
0x140032397  jnz     loc_140032848
0x14003239d  mov     ecx, [rdi+40h]
0x1400323a0  mov     eax, [rdi+8]
0x1400323a3  cmp     eax, ecx
0x1400323a5  jb      loc_140032B58
0x1400323ab  mov     [rsp+128h+var_38], rbx
0x1400323b3  sub     eax, ecx
0x1400323b5  mov     [rsp+128h+var_40], r12
0x1400323bd  mov     [rdi+8], eax
0x1400323c0  add     [rbp+64h], ecx
0x1400323c3  movzx   eax, word ptr [r13+528h]
0x1400323cb  mov     r12d, [rdi+8]
0x1400323cf  movzx   ebx, ax
0x1400323d2  add     r12, [rbp+58h]
0x1400323d6  mov     edx, [rbp+64h]
0x1400323d9  shr     bx, 8
0x1400323dd  mov     [rsp+128h+arg_10], ax
0x1400323e5  and     bl, 0Fh
0x1400323e8  inc     ax
0x1400323eb  mov     [rsp+128h+var_70], r12
0x1400323f3  mov     [rsp+128h+cbInput], edx
0x1400323fa  mov     byte ptr [rsp+128h+arg_10+1], bl
0x140032401  mov     [r13+528h], ax
0x140032409  test    sil, 2
0x14003240d  jnz     loc_1400326C8
0x140032413  test    sil, 4
0x140032417  jz      loc_140032615
0x14003241d  mov     r14, [r13+4B8h]
0x140032424  lea     r15, [r13+49Ch]
0x14003242b  mov     ebp, [r13+4ACh]
0x140032432  mov     [rsp+128h+var_58], r15
0x14003243a  mov     [rsp+128h+var_60], r14
0x140032442  mov     dword ptr [rsp+128h+var_80], ebp
0x140032449  test    sil, 20h
0x14003244d  jnz     loc_14003291C
0x140032453  or      bl, 10h
0x140032456  cmp     byte ptr [r13+528h], 0
0x14003245e  mov     byte ptr [rsp+128h+arg_10+1], bl
0x140032465  setnz   cl
0x140032468  bt      esi, 0Bh
0x14003246c  setnb   al
0x14003246f  test    al, cl
0x140032471  jnz     loc_1400325C2
0x140032477  test    sil, 40h
0x14003247b  jnz     loc_1400326AB
0x140032481  lea     rcx, [r13+488h]
0x140032488  call    GetNewKeyFromSHA
0x14003248d  test    r14, r14
0x140032490  jz      loc_14003293B
0x140032496  mov     rcx, [r14]; hKey
0x140032499  test    rcx, rcx
0x14003249c  jnz     loc_140032947
0x1400324a2  mov     rcx, cs:ghAlgRC4; hAlgorithm
0x1400324a9  xor     r9d, r9d; cbKeyObject
0x1400324ac  mov     [rsp+128h+dwFlags], 0; dwFlags
0x1400324b4  xor     r8d, r8d; pbKeyObject
0x1400324b7  mov     [rsp+128h+cbSecret], ebp; cbSecret
0x1400324bb  mov     rdx, r14; phKey
0x1400324be  mov     [rsp+128h+pbSecret], r15; pbSecret
0x1400324c3  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400324ca  nop     dword ptr [rax+rax+00h]
0x1400324cf  test    eax, eax
0x1400324d1  js      loc_14003295F
0x1400324d7  xor     ecx, ecx
0x1400324d9  lea     rax, [rsp+128h+var_84]
0x1400324e1  mov     [rsp+128h+var_E0], ecx; dwFlags
0x1400324e5  xor     r9d, r9d; pPaddingInfo
0x1400324e8  mov     [rsp+128h+pcbResult], rax; pcbResult
0x1400324ed  mov     r8d, ebp; cbInput
0x1400324f0  mov     [rsp+128h+cbOutput], ebp; cbOutput
0x1400324f4  mov     rdx, r15; pbInput
0x1400324f7  mov     qword ptr [rsp+128h+dwFlags], r15; pbOutput
0x1400324fc  mov     [rsp+128h+cbSecret], ecx; cbIV
0x140032500  mov     [rsp+128h+pbSecret], rcx; pbIV
0x140032505  mov     [rsp+128h+var_84], ecx
0x14003250c  mov     rcx, [r14]; hKey
0x14003250f  call    cs:__imp_BCryptEncrypt
0x140032516  nop     dword ptr [rax+rax+00h]
0x14003251b  test    eax, eax
0x14003251d  js      loc_14003296B
0x140032523  test    sil, sil
0x140032526  js      loc_14003269B
0x14003252c  bt      esi, 0Ch
0x140032530  jb      loc_140032977
0x140032536  mov     rcx, cs:WPP_GLOBAL_Control
0x14003253d  lea     rax, WPP_GLOBAL_Control
0x140032544  cmp     rcx, rax
0x140032547  jz      short loc_14003257E
0x140032549  test    dword ptr [rcx+2Ch], 200h
0x140032550  jnz     loc_140032980
0x140032556  mov     rcx, cs:WPP_GLOBAL_Control
0x14003255d  lea     rax, WPP_GLOBAL_Control
0x140032564  mov     [rsp+128h+var_68], rcx
0x14003256c  cmp     rcx, rax
0x14003256f  jz      short loc_14003257E
0x140032571  test    dword ptr [rcx+2Ch], 200h
0x140032578  jnz     loc_1400329AB
0x14003257e  mov     rcx, [r14]; hKey
0x140032581  test    rcx, rcx
0x140032584  jnz     loc_140032B04
0x14003258a  mov     rcx, cs:ghAlgRC4; hAlgorithm
0x140032591  xor     r9d, r9d; cbKeyObject
0x140032594  mov     [rsp+128h+dwFlags], 0; dwFlags
0x14003259c  xor     r8d, r8d; pbKeyObject
0x14003259f  mov     [rsp+128h+cbSecret], ebp; cbSecret
0x1400325a3  mov     rdx, r14; phKey
0x1400325a6  mov     [rsp+128h+pbSecret], r15; pbSecret
0x1400325ab  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400325b2  nop     dword ptr [rax+rax+00h]
0x1400325b7  test    eax, eax
0x1400325b9  js      loc_140032B1C
0x1400325bf  xor     r9d, r9d
0x1400325c2  mov     r8d, [rsp+128h+cbInput]; cbInput
0x1400325ca  lea     rax, [rsp+128h+arg_8]
0x1400325d2  mov     rcx, [r14]; hKey
0x1400325d5  mov     rdx, r12; pbInput
0x1400325d8  mov     [rsp+128h+var_E0], r9d; dwFlags
0x1400325dd  mov     [rsp+128h+pcbResult], rax; pcbResult
0x1400325e2  mov     [rsp+128h+cbOutput], r8d; cbOutput
0x1400325e7  mov     qword ptr [rsp+128h+dwFlags], r12; pbOutput
0x1400325ec  mov     [rsp+128h+cbSecret], r9d; cbIV
0x1400325f1  mov     [rsp+128h+pbSecret], r9; pbIV
0x1400325f6  mov     dword ptr [rsp+128h+arg_8], r9d
0x1400325fe  xor     r9d, r9d; pPaddingInfo
0x140032601  call    cs:__imp_BCryptEncrypt
0x140032608  nop     dword ptr [rax+rax+00h]
0x14003260d  test    eax, eax
0x14003260f  js      loc_140032B28
0x140032615  mov     r12, [rsp+128h+var_40]
0x14003261d  test    esi, 820h
0x140032623  jz      short loc_14003262F
0x140032625  or      bl, 80h
0x140032628  mov     byte ptr [rsp+128h+arg_10+1], bl
0x14003262f  cmp     dword ptr [rdi+30h], 0
0x140032633  mov     rbx, [rsp+128h+var_38]
0x14003263b  jz      short loc_140032669
0x14003263d  mov     rcx, [rdi+38h]
0x140032641  test    dword ptr [rdi], 400h
0x140032647  movzx   eax, [rsp+128h+arg_10]
0x14003264f  lea     rdx, [rcx+1]
0x140032653  cmovnz  rdx, rcx
0x140032657  shr     ax, 8
0x14003265b  mov     [rdx+1], al
0x14003265e  movzx   eax, byte ptr [rsp+128h+arg_10]
0x140032666  mov     [rdx+2], al
0x140032669  mov     rcx, cs:WPP_GLOBAL_Control
0x140032670  lea     rax, WPP_GLOBAL_Control
0x140032677  cmp     rcx, rax
0x14003267a  jz      short loc_140032687
0x14003267c  mov     eax, [rcx+2Ch]
0x14003267f  test    al, 8
0x140032681  jnz     loc_140032B34
0x140032687  mov     al, 1
0x140032689  add     rsp, 0F8h
0x140032690  pop     r15
0x140032692  pop     r14
0x140032694  pop     r13
0x140032696  pop     rdi
0x140032697  pop     rsi
0x140032698  pop     rbp
0x140032699  retn
0x14003269b  mov     word ptr [r15], 26D1h
0x1400326a1  mov     byte ptr [r15+2], 9Eh
0x1400326a6  jmp     loc_140032536
0x1400326ab  inc     byte ptr [r15+3]
0x1400326af  add     byte ptr [r15+4], 3
0x1400326b4  add     byte ptr [r15+5], 0Dh
0x1400326b9  add     byte ptr [r15+6], 39h ; '9'
0x1400326be  add     byte ptr [r15+7], 13h
0x1400326c3  jmp     loc_14003248D
0x1400326c8  mov     rcx, r15
0x1400326cb  call    NdisWanAllocateSendDesc
0x1400326d0  mov     r15, rax
0x1400326d3  test    rax, rax
0x1400326d6  jz      loc_140032876
0x1400326dc  mov     rax, [rax+58h]
0x1400326e0  mov     ecx, [rdi+8]
0x1400326e3  add     rax, rcx
0x1400326e6  mov     ecx, [r13+6C8h]
0x1400326ed  shl     rcx, 20h
0x1400326f1  mov     [rsp+128h+var_80], rax
0x1400326f9  mov     eax, [rsp+128h+cbInput]
0x140032700  add     rcx, rax
0x140032703  mov     eax, [r13+674h]
0x14003270a  add     rcx, rax
0x14003270d  mov     [r13+674h], ecx
0x140032714  shr     rcx, 20h
0x140032718  mov     [r13+6C8h], ecx
0x14003271f  test    esi, 820h
0x140032725  jz      short loc_140032733
0x140032727  mov     rcx, [r13+308h]
0x14003272e  call    initsendcontext
0x140032733  mov     r9, [r13+308h]
0x14003273a  lea     r8, [rsp+128h+cbInput]
0x140032742  mov     rdx, [rsp+128h+var_80]
0x14003274a  mov     rcx, r12
0x14003274d  call    compress
0x140032752  or      al, bl
0x140032754  movzx   ebx, al
0x140032757  mov     byte ptr [rsp+128h+arg_10+1], al
0x14003275e  jge     short loc_1400327B3
0x140032760  mov     rcx, r15
0x140032763  call    NdisWanFreeSendDesc
0x140032768  or      esi, 20h
0x14003276b  mov     ecx, [r13+6D0h]
0x140032772  mov     eax, [rsp+128h+cbInput]
0x140032779  shl     rcx, 20h
0x14003277d  add     rcx, rax
0x140032780  mov     [rsp+128h+var_70], r12
0x140032788  mov     eax, [r13+67Ch]
0x14003278f  add     rcx, rax
0x140032792  mov     [r13+67Ch], ecx
0x140032799  shr     rcx, 20h
0x14003279d  mov     [r13+6D0h], ecx
0x1400327a4  mov     [rsp+128h+var_88], esi
0x1400327ab  xor     r9d, r9d
0x1400327ae  jmp     loc_140032413
0x1400327b3  mov     r8d, [rdi+8]; Size
0x1400327b7  mov     rdx, [rbp+58h]; Src
0x1400327bb  mov     rcx, [r15+58h]; void *
0x1400327bf  call    memmove
0x1400327c4  mov     edx, [rdi+10h]
0x1400327c7  mov     r8d, [rdi+20h]
0x1400327cb  mov     eax, [rdi+30h]
0x1400327ce  mov     dword ptr [rdi+40h], 0
0x1400327d5  mov     rcx, [r15+58h]
0x1400327d9  mov     [rdi+18h], rcx
0x1400327dd  add     rdx, rcx
0x1400327e0  mov     [rdi+28h], rdx
0x1400327e4  add     r8, rdx
0x1400327e7  mov     [rdi+38h], r8
0x1400327eb  add     rax, r8
0x1400327ee  mov     [rdi+48h], rax
0x1400327f2  mov     rcx, rbp
0x1400327f5  mov     eax, [rsp+128h+cbInput]
0x1400327fc  mov     [r15+64h], eax
0x140032800  mov     rax, [rbp+30h]
0x140032804  mov     [r15+30h], rax
0x140032808  mov     rax, [rbp+70h]
0x14003280c  mov     [r15+70h], rax
0x140032810  mov     eax, [rbp+20h]
0x140032813  mov     [r15+20h], eax
0x140032817  mov     eax, [rbp+1Ch]
0x14003281a  mov     [r15+1Ch], eax
0x14003281e  call    NdisWanFreeSendDesc
0x140032823  mov     rax, [r15+50h]
0x140032827  mov     edx, [rsp+128h+cbInput]
0x14003282e  add     edx, [rdi+8]
0x140032831  mov     r12, [rsp+128h+var_80]
0x140032839  mov     rcx, [rax+8]
0x14003283d  mov     [r14], r15
0x140032840  mov     [rcx+18h], edx
0x140032843  jmp     loc_14003276B
0x140032848  cmp     byte ptr [rcx+29h], 5
0x14003284c  jb      loc_14003239D
0x140032852  mov     rcx, [rcx+18h]
0x140032856  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x14003285d  mov     edx, 25h ; '%'
0x140032862  call    WPP_SF_
0x140032867  xor     r9d, r9d
0x14003286a  lea     rdx, WPP_GLOBAL_Control
0x140032871  jmp     loc_14003239D
0x140032876  test    sil, 4
0x14003287a  jnz     short loc_1400328D6
0x14003287c  mov     rcx, cs:WPP_GLOBAL_Control
0x140032883  lea     rax, WPP_GLOBAL_Control
0x14003288a  cmp     rcx, rax
0x14003288d  jz      short loc_1400328B1
0x14003288f  mov     eax, [rcx+2Ch]
0x140032892  test    al, 8
0x140032894  jz      short loc_1400328B1
0x140032896  cmp     byte ptr [rcx+29h], 5
0x14003289a  jb      short loc_1400328B1
0x14003289c  mov     rcx, [rcx+18h]
0x1400328a0  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x1400328a7  mov     edx, 27h ; '''
  ... truncated ...
```
