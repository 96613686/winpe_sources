# FveLogPcrUnsealInfoDatum

- ea: `0x1400b64e8`
- end: `0x1400b6a7f`
- name: `FveLogPcrUnsealInfoDatum`
- size: `1431`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14009f0f0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140006730`
- `0x140007088`
- `0x140007da8`
- `0x14000a540`
- `0x14000d938`
- `0x1400181dc`
- `0x140018650`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x1400b64e8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400b68c6`
- `ntoskrnl!EtwWrite` at `0x1400b68c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6a46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6a46`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6708`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6708`

## pseudocode

```c
__int64 __fastcall FveLogPcrUnsealInfoDatum(__int64 a1, unsigned __int16 *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  NTSTATUS v6; // ebx
  __int64 v7; // r15
  char *v8; // r14
  __int64 v9; // r13
  int MustBe; // eax
  ULONG v11; // r11d
  const wchar_t *v12; // rdx
  int v13; // ecx
  __int64 i; // rdx
  int v15; // ecx
  __int64 j; // r8
  unsigned __int16 v17; // r9
  int v18; // r11d
  __int64 Pool2; // rax
  unsigned __int16 v20; // si
  unsigned __int16 v21; // r9
  int v22; // r11d
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  USHORT pusResult[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v26[2]; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v27; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pulResult; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v29; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v30; // [rsp+5Ch] [rbp-A4h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  ULONGLONG v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[12]; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+150h] [rbp+50h] BYREF
  _WORD *v39; // [rsp+170h] [rbp+70h]
  __int64 v40; // [rsp+178h] [rbp+78h]
  __int64 *v41; // [rsp+180h] [rbp+80h]
  __int64 v42; // [rsp+188h] [rbp+88h]
  USHORT *v43; // [rsp+190h] [rbp+90h]
  __int64 v44; // [rsp+198h] [rbp+98h]
  __int16 *v45; // [rsp+1A0h] [rbp+A0h]
  __int64 v46; // [rsp+1A8h] [rbp+A8h]
  ULONGLONG *v47; // [rsp+1B0h] [rbp+B0h]
  __int64 v48; // [rsp+1B8h] [rbp+B8h]
  __int64 *v49; // [rsp+1C0h] [rbp+C0h]
  __int64 v50; // [rsp+1C8h] [rbp+C8h]
  _DWORD *v51; // [rsp+1D0h] [rbp+D0h]
  __int64 v52; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 *v53; // [rsp+1E0h] [rbp+E0h]
  _DWORD v54[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 *v55; // [rsp+1F0h] [rbp+F0h]
  __int64 v56; // [rsp+1F8h] [rbp+F8h]

  memset(UserData, 0, sizeof(UserData));
  WORD2(v24) = 0;
  v6 = 0;
  v27 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v32 = 0;
  LOWORD(v24) = 0;
  pulResult = 0;
  v34 = 0;
  pusResult[0] = 0;
  v26[0] = 0;
  v30 = 0;
  v33 = 0;
  if ( !a1 )
    goto LABEL_42;
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL);
  if ( !v9 )
    goto LABEL_42;
  if ( !*(_QWORD *)(v9 + 88) )
    goto LABEL_42;
  MustBe = FveDatumMustBe(a2, 32, v4, v5);
  v11 = 0;
  v6 = MustBe;
  if ( MustBe < 0 )
    goto LABEL_42;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v12 = L"true";
    if ( !*((_BYTE *)a2 + 18) )
      v12 = L"false";
    WPP_SF_ISDLL(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v12,
      *(unsigned __int16 *)((char *)a2 + 19),
      *(_QWORD *)(a2 + 5),
      (__int64)v12,
      *(unsigned __int16 *)((char *)a2 + 19),
      *(_DWORD *)((char *)a2 + 21),
      *(_DWORD *)((char *)a2 + 25),
      v24);
    v11 = 0;
  }
  v13 = *(_DWORD *)((char *)a2 + 21);
  for ( i = 0; v13; v13 &= v13 - 1 )
    LOWORD(i) = i + 1;
  WORD2(v24) = i;
  v15 = *(_DWORD *)((char *)a2 + 25);
  for ( j = 0; v15; v15 &= v15 - 1 )
    LOWORD(j) = j + 1;
  v32 = *(unsigned __int16 *)((char *)a2 + 19);
  v27 = j;
  switch ( v32 )
  {
    case 4:
      v17 = 20;
      goto LABEL_28;
    case 11:
      goto LABEL_26;
    case 12:
LABEL_25:
      v17 = 48;
      goto LABEL_28;
    case 13:
LABEL_24:
      v17 = 64;
      goto LABEL_28;
    case 18:
    case 39:
LABEL_26:
      v17 = 32;
      goto LABEL_28;
    case 40:
      goto LABEL_25;
    case 41:
      goto LABEL_24;
  }
  v17 = 0;
LABEL_28:
  LOWORD(v24) = v17;
  if ( (_WORD)i )
  {
    v6 = FveAllAllPurposeArraysFromPcrUnsealInfo(a2, i, j, &v34);
    if ( v6 < 0 )
      goto LABEL_42;
    v6 = RtlULongLongToULong(WORD2(v24) * (unsigned __int64)(unsigned __int16)v24, &pulResult);
    if ( v6 < 0 )
      goto LABEL_42;
    Pool2 = ExAllocatePool2((unsigned int)(v18 + 64), pulResult, 809850438);
    v11 = 0;
    v8 = (char *)Pool2;
    if ( !Pool2 )
    {
      v6 = -1073741801;
      goto LABEL_42;
    }
    LOWORD(i) = WORD2(v24);
    v17 = v24;
    v7 = v34;
  }
  v20 = 0;
  if ( (_WORD)i )
  {
    while ( 1 )
    {
      v6 = RtlULongToUShort(v17 * v20, pusResult);
      if ( v6 < 0 )
        break;
      memmove(&v8[pusResult[0]], (const void *)(*(_QWORD *)(v7 + 8LL * v20) + 8LL), v21);
      v11 = 0;
      if ( ++v20 >= WORD2(v24) )
        goto LABEL_38;
      v17 = v24;
    }
  }
  else
  {
LABEL_38:
    if ( !v27
      || (v6 = FveNthPcrDataFromPcrUnsealInfo((_DWORD)a2, 0, j, (unsigned int)v26, (__int64)&v33), v6 >= 0)
      && (v6 = RtlULongSub(*a2, v26[0], &v30), v6 >= 0) )
    {
      *(_QWORD *)&UserData[0].Size = 8;
      UserData[0].Ptr = (ULONGLONG)(a2 + 5);
      v31 = *((unsigned __int8 *)a2 + 18);
      *(_QWORD *)&UserData[1].Size = 4;
      UserData[1].Ptr = (ULONGLONG)&v31;
      UserData[2].Ptr = (ULONGLONG)&v32;
      UserData[3].Ptr = (ULONGLONG)&v24;
      UserData[4].Ptr = (ULONGLONG)a2 + 21;
      UserData[5].Ptr = (ULONGLONG)&v24 + 4;
      UserData[7].Ptr = (ULONGLONG)&v27;
      UserData[8].Ptr = (ULONGLONG)&pulResult;
      UserData[9].Size = pulResult;
      UserData[10].Ptr = (ULONGLONG)&v30;
      UserData[11].Ptr = v33;
      UserData[11].Size = v30;
      *(_QWORD *)&UserData[2].Size = 4;
      *(_QWORD *)&UserData[3].Size = 2;
      *(_QWORD *)&UserData[4].Size = 4;
      *(_QWORD *)&UserData[5].Size = 2;
      UserData[6].Ptr = (ULONGLONG)a2 + 25;
      *(_QWORD *)&UserData[6].Size = 4;
      *(_QWORD *)&UserData[7].Size = 2;
      *(_QWORD *)&UserData[8].Size = 4;
      UserData[9].Ptr = (ULONGLONG)v8;
      UserData[9].Reserved = v11;
      *(_QWORD *)&UserData[10].Size = 4;
      UserData[11].Reserved = v11;
      v6 = EtwWrite(*(_QWORD *)(v9 + 88), &FVE_KEYRING_PCR_UNSEAL_INFO, 0, 0xCu, UserData);
    }
  }
LABEL_42:
  if ( a2 && (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
  {
    v26[0] = a2[4];
    v40 = 2;
    v39 = v26;
    v35 = *(_QWORD *)(a2 + 5);
    v41 = &v35;
    LOBYTE(pusResult[0]) = *((_BYTE *)a2 + 18);
    v43 = pusResult;
    v29 = *(unsigned __int16 *)((char *)a2 + 19);
    v45 = &v29;
    LODWORD(v33) = *(_DWORD *)((char *)a2 + 21);
    v47 = &v33;
    LODWORD(v34) = *(_DWORD *)((char *)a2 + 25);
    v49 = &v34;
    v51 = v54;
    v54[0] = *a2;
    v55 = &v36;
    v42 = 8;
    v44 = 1;
    v46 = 2;
    v48 = 4;
    v50 = 4;
    v52 = 2;
    v53 = a2;
    v54[1] = v22;
    v36 = 0x1000000;
    v56 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140046040, (unsigned __int8 *)word_14003CE4A, 0, 0, 0xBu, &v38);
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x30455646u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b64e8  mov     [rsp-8+arg_10], rbx
0x1400b64ed  push    rbp
0x1400b64ee  push    rsi
0x1400b64ef  push    rdi
0x1400b64f0  push    r12
0x1400b64f2  push    r13
0x1400b64f4  push    r14
0x1400b64f6  push    r15
0x1400b64f8  lea     rbp, [rsp-110h]
0x1400b6500  sub     rsp, 210h
0x1400b6507  mov     rax, cs:__security_cookie
0x1400b650e  xor     rax, rsp
0x1400b6511  mov     [rbp+140h+var_40], rax
0x1400b6518  mov     rdi, rdx
0x1400b651b  mov     rsi, rcx
0x1400b651e  xor     edx, edx; Val
0x1400b6520  lea     rcx, [rbp+140h+var_1B0]; void *
0x1400b6524  mov     r8d, 0C0h; Size
0x1400b652a  call    memset
0x1400b652f  xor     r11d, r11d
0x1400b6532  mov     [rsp+240h+var_1FC], r11w
0x1400b6538  mov     ebx, r11d
0x1400b653b  mov     [rsp+240h+var_1F0], r11w
0x1400b6541  mov     r15d, r11d
0x1400b6544  mov     [rsp+240h+var_1E0], r11d
0x1400b6549  mov     r14d, r11d
0x1400b654c  mov     [rsp+240h+var_1DC], r11d
0x1400b6551  lea     r12d, [r11+1]
0x1400b6555  mov     [rsp+240h+var_200], r11w
0x1400b655b  mov     [rsp+240h+pulResult], r11d
0x1400b6560  mov     [rsp+240h+var_1D0], r11
0x1400b6565  mov     [rsp+240h+pusResult], r11w
0x1400b656b  mov     [rsp+240h+var_1F4], r11w
0x1400b6571  mov     [rsp+240h+var_1E4], r11d
0x1400b6576  mov     [rsp+240h+var_1D8], r11
0x1400b657b  test    rsi, rsi
0x1400b657e  jz      loc_1400B68D7
0x1400b6584  mov     rax, [rsi+40h]
0x1400b6588  mov     r13, [rax+8]
0x1400b658c  test    r13, r13
0x1400b658f  jz      loc_1400B68D7
0x1400b6595  cmp     [r13+58h], r11
0x1400b6599  jz      loc_1400B68D7
0x1400b659f  lea     esi, [r11+20h]
0x1400b65a3  mov     rcx, rdi
0x1400b65a6  mov     edx, esi
0x1400b65a8  call    FveDatumMustBe
0x1400b65ad  xor     r11d, r11d
0x1400b65b0  mov     ebx, eax
0x1400b65b2  test    eax, eax
0x1400b65b4  js      loc_1400B68D7
0x1400b65ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b65c1  lea     rax, WPP_GLOBAL_Control
0x1400b65c8  cmp     rcx, rax
0x1400b65cb  jz      short loc_1400B661F
0x1400b65cd  test    dword ptr [rcx+2Ch], 8000h
0x1400b65d4  jz      short loc_1400B661F
0x1400b65d6  cmp     byte ptr [rcx+29h], 5
0x1400b65da  jb      short loc_1400B661F
0x1400b65dc  mov     eax, [rdi+19h]
0x1400b65df  lea     r9, aFalse; "false"
0x1400b65e6  cmp     [rdi+12h], r11b
0x1400b65ea  lea     rdx, aTrue; "true"
0x1400b65f1  movzx   r8d, word ptr [rdi+13h]
0x1400b65f6  mov     rcx, [rcx+18h]
0x1400b65fa  cmovz   rdx, r9
0x1400b65fe  mov     r9, [rdi+0Ah]
0x1400b6602  mov     [rsp+240h+var_208], eax
0x1400b6606  mov     eax, [rdi+15h]
0x1400b6609  mov     [rsp+240h+var_210], eax
0x1400b660d  mov     dword ptr [rsp+240h+var_218], r8d
0x1400b6612  mov     [rsp+240h+UserData], rdx
0x1400b6617  call    WPP_SF_ISDLL
0x1400b661c  xor     r11d, r11d
0x1400b661f  mov     ecx, [rdi+15h]
0x1400b6622  mov     edx, r11d
0x1400b6625  test    ecx, ecx
0x1400b6627  jz      short loc_1400B6634
0x1400b6629  add     dx, r12w
0x1400b662d  lea     eax, [rcx-1]
0x1400b6630  and     ecx, eax
0x1400b6632  jnz     short loc_1400B6629
0x1400b6634  lea     r12, [rdi+19h]
0x1400b6638  mov     [rsp+240h+var_1FC], dx
0x1400b663d  mov     ecx, [r12]
0x1400b6641  mov     r8d, r11d
0x1400b6644  test    ecx, ecx
0x1400b6646  jz      short loc_1400B6659
0x1400b6648  mov     r9d, 1
0x1400b664e  add     r8w, r9w
0x1400b6652  lea     eax, [rcx-1]
0x1400b6655  and     ecx, eax
0x1400b6657  jnz     short loc_1400B664E
0x1400b6659  movzx   ecx, word ptr [rdi+13h]
0x1400b665d  mov     eax, 40h ; '@'
0x1400b6662  mov     [rsp+240h+var_1DC], ecx
0x1400b6666  mov     [rsp+240h+var_1F0], r8w
0x1400b666c  sub     ecx, 4
0x1400b666f  jz      short loc_1400B66AD
0x1400b6671  sub     ecx, 7
0x1400b6674  jz      short loc_1400B66A7
0x1400b6676  sub     ecx, 1
0x1400b6679  jz      short loc_1400B669F
0x1400b667b  sub     ecx, 1
0x1400b667e  jz      short loc_1400B6699
0x1400b6680  sub     ecx, 5
0x1400b6683  jz      short loc_1400B66A7
0x1400b6685  sub     ecx, 15h
0x1400b6688  jz      short loc_1400B66A7
0x1400b668a  sub     ecx, 1
0x1400b668d  jz      short loc_1400B669F
0x1400b668f  cmp     ecx, 1
0x1400b6692  jz      short loc_1400B6699
0x1400b6694  mov     r9d, r11d
0x1400b6697  jmp     short loc_1400B66B3
0x1400b6699  movzx   r9d, ax
0x1400b669d  jmp     short loc_1400B66B3
0x1400b669f  mov     r9d, 30h ; '0'
0x1400b66a5  jmp     short loc_1400B66B3
0x1400b66a7  movzx   r9d, si
0x1400b66ab  jmp     short loc_1400B66B3
0x1400b66ad  mov     r9d, 14h
0x1400b66b3  mov     [rsp+240h+var_200], r9w
0x1400b66b9  test    dx, dx
0x1400b66bc  jz      short loc_1400B6739
0x1400b66be  lea     r9, [rsp+240h+var_1D0]
0x1400b66c3  mov     rcx, rdi
0x1400b66c6  call    FveAllAllPurposeArraysFromPcrUnsealInfo
0x1400b66cb  xor     r11d, r11d
0x1400b66ce  mov     ebx, eax
0x1400b66d0  test    eax, eax
0x1400b66d2  js      loc_1400B68D7
0x1400b66d8  movzx   eax, [rsp+240h+var_1FC]
0x1400b66dd  lea     rdx, [rsp+240h+pulResult]; pulResult
0x1400b66e2  movzx   ecx, [rsp+240h+var_200]
0x1400b66e7  imul    rcx, rax; ullOperand
0x1400b66eb  call    RtlULongLongToULong
0x1400b66f0  mov     ebx, eax
0x1400b66f2  test    eax, eax
0x1400b66f4  js      loc_1400B68D7
0x1400b66fa  mov     edx, [rsp+240h+pulResult]
0x1400b66fe  lea     ecx, [r11+40h]
0x1400b6702  mov     r8d, 30455646h
0x1400b6708  call    cs:__imp_ExAllocatePool2
0x1400b670f  nop     dword ptr [rax+rax+00h]
0x1400b6714  xor     r11d, r11d
0x1400b6717  mov     r14, rax
0x1400b671a  test    rax, rax
0x1400b671d  jnz     short loc_1400B6729
0x1400b671f  mov     ebx, 0C0000017h
0x1400b6724  jmp     loc_1400B68D7
0x1400b6729  movzx   edx, [rsp+240h+var_1FC]
0x1400b672e  movzx   r9d, [rsp+240h+var_200]
0x1400b6734  mov     r15, [rsp+240h+var_1D0]
0x1400b6739  mov     esi, r11d
0x1400b673c  cmp     r11w, dx
0x1400b6740  jnb     short loc_1400B6791
0x1400b6742  movzx   eax, r9w
0x1400b6746  lea     rdx, [rsp+240h+pusResult]; pusResult
0x1400b674b  movzx   ecx, si
0x1400b674e  imul    ecx, eax; ulOperand
0x1400b6751  call    RtlULongToUShort
0x1400b6756  mov     ebx, eax
0x1400b6758  test    eax, eax
0x1400b675a  js      loc_1400B68D7
0x1400b6760  movzx   ecx, [rsp+240h+pusResult]
0x1400b6765  movzx   eax, si
0x1400b6768  add     rcx, r14; void *
0x1400b676b  movzx   r8d, r9w; Size
0x1400b676f  mov     rdx, [r15+rax*8]
0x1400b6773  add     rdx, 8; Src
0x1400b6777  call    memmove
0x1400b677c  xor     r11d, r11d
0x1400b677f  inc     si
0x1400b6782  cmp     si, [rsp+240h+var_1FC]
0x1400b6787  jnb     short loc_1400B6791
0x1400b6789  movzx   r9d, [rsp+240h+var_200]
0x1400b678f  jmp     short loc_1400B6742
0x1400b6791  cmp     [rsp+240h+var_1F0], r11w
0x1400b6797  jz      short loc_1400B67DB
0x1400b6799  lea     rax, [rsp+240h+var_1D8]
0x1400b679e  xor     edx, edx
0x1400b67a0  lea     r9, [rsp+240h+var_1F4]
0x1400b67a5  mov     [rsp+240h+UserData], rax
0x1400b67aa  mov     rcx, rdi
0x1400b67ad  call    FveNthPcrDataFromPcrUnsealInfo
0x1400b67b2  xor     r11d, r11d
0x1400b67b5  mov     ebx, eax
0x1400b67b7  test    eax, eax
0x1400b67b9  js      loc_1400B68D7
0x1400b67bf  movzx   edx, [rsp+240h+var_1F4]; ulSubtrahend
0x1400b67c4  lea     r8, [rsp+240h+var_1E4]; pulResult
0x1400b67c9  movzx   ecx, word ptr [rdi]; ulMinuend
0x1400b67cc  call    RtlULongSub
0x1400b67d1  mov     ebx, eax
0x1400b67d3  test    eax, eax
0x1400b67d5  js      loc_1400B68D7
0x1400b67db  lea     rax, [rdi+0Ah]
0x1400b67df  mov     qword ptr [rbp+140h+var_1B0.Size], 8
0x1400b67e7  mov     [rbp+140h+var_1B0.Ptr], rax
0x1400b67eb  lea     rdx, FVE_KEYRING_PCR_UNSEAL_INFO; EventDescriptor
0x1400b67f2  movzx   eax, byte ptr [rdi+12h]
0x1400b67f6  mov     r9d, 0Ch; UserDataCount
0x1400b67fc  mov     [rsp+240h+var_1E0], eax
0x1400b6800  xor     r8d, r8d; ActivityId
0x1400b6803  lea     rax, [rsp+240h+var_1E0]
0x1400b6808  mov     [rbp+140h+var_198], 4
0x1400b6810  mov     [rbp+140h+var_1A0], rax
0x1400b6814  lea     rax, [rsp+240h+var_1DC]
0x1400b6819  mov     [rbp+140h+var_190], rax
0x1400b681d  lea     rax, [rsp+240h+var_200]
0x1400b6822  mov     [rbp+140h+var_180], rax
0x1400b6826  lea     rax, [rdi+15h]
0x1400b682a  mov     [rbp+140h+var_170], rax
0x1400b682e  lea     rax, [rsp+240h+var_1FC]
0x1400b6833  mov     [rbp+140h+var_160], rax
0x1400b6837  lea     rax, [rsp+240h+var_1F0]
0x1400b683c  mov     [rbp+140h+var_140], rax
0x1400b6840  lea     rax, [rsp+240h+pulResult]
0x1400b6845  mov     [rbp+140h+var_130], rax
0x1400b6849  mov     eax, [rsp+240h+pulResult]
0x1400b684d  mov     [rbp+140h+var_118], eax
0x1400b6850  lea     rax, [rsp+240h+var_1E4]
0x1400b6855  mov     [rbp+140h+var_110], rax
0x1400b6859  mov     rax, [rsp+240h+var_1D8]
0x1400b685e  mov     [rbp+140h+var_100], rax
0x1400b6862  mov     eax, [rsp+240h+var_1E4]
0x1400b6866  mov     [rbp+140h+var_F8], eax
0x1400b6869  lea     rax, [rbp+140h+var_1B0]
0x1400b686d  mov     [rbp+140h+var_188], 4
0x1400b6875  mov     [rbp+140h+var_178], 2
0x1400b687d  mov     [rbp+140h+var_168], 4
0x1400b6885  mov     [rbp+140h+var_158], 2
0x1400b688d  mov     [rbp+140h+var_150], r12
0x1400b6891  mov     [rbp+140h+var_148], 4
0x1400b6899  mov     [rbp+140h+var_138], 2
0x1400b68a1  mov     [rbp+140h+var_128], 4
0x1400b68a9  mov     [rbp+140h+var_120], r14
0x1400b68ad  mov     [rbp+140h+var_114], r11d
0x1400b68b1  mov     [rbp+140h+var_108], 4
0x1400b68b9  mov     [rbp+140h+var_F4], r11d
0x1400b68bd  mov     rcx, [r13+58h]; RegHandle
0x1400b68c1  mov     [rsp+240h+UserData], rax; UserData
0x1400b68c6  call    cs:__imp_EtwWrite
0x1400b68cd  nop     dword ptr [rax+rax+00h]
0x1400b68d2  mov     ebx, eax
0x1400b68d4  xor     r11d, r11d
0x1400b68d7  test    rdi, rdi
0x1400b68da  jz      loc_1400B6A39
0x1400b68e0  mov     eax, cs:dword_140046040
0x1400b68e6  cmp     eax, 4
0x1400b68e9  jbe     loc_1400B6A39
0x1400b68ef  mov     rdx, 400000000000h
0x1400b68f9  lea     rcx, dword_140046040
0x1400b6900  call    _tlgKeywordOn
0x1400b6905  test    al, al
0x1400b6907  jz      loc_1400B6A39
0x1400b690d  movzx   eax, word ptr [rdi+8]
0x1400b6911  lea     rdx, word_14003CE4A
0x1400b6918  mov     [rsp+240h+var_1F4], ax
0x1400b691d  lea     rcx, dword_140046040
0x1400b6924  lea     rax, [rsp+240h+var_1F4]
0x1400b6929  mov     [rbp+140h+var_C8], 2
0x1400b6931  mov     [rbp+140h+var_D0], rax
0x1400b6935  xor     r9d, r9d
0x1400b6938  mov     rax, [rdi+0Ah]
0x1400b693c  xor     r8d, r8d
0x1400b693f  mov     [rsp+240h+var_1C8], rax
0x1400b6944  lea     rax, [rsp+240h+var_1C8]
0x1400b6949  mov     [rbp+140h+var_C0], rax
0x1400b6950  mov     al, [rdi+12h]
0x1400b6953  mov     byte ptr [rsp+240h+pusResult], al
0x1400b6957  lea     rax, [rsp+240h+pusResult]
0x1400b695c  mov     [rbp+140h+var_B0], rax
0x1400b6963  movzx   eax, word ptr [rdi+13h]
0x1400b6967  mov     [rsp+240h+var_1E8], ax
0x1400b696c  lea     rax, [rsp+240h+var_1E8]
0x1400b6971  mov     [rbp+140h+var_A0], rax
0x1400b6978  mov     eax, [rdi+15h]
0x1400b697b  mov     dword ptr [rsp+240h+var_1D8], eax
0x1400b697f  lea     rax, [rsp+240h+var_1D8]
0x1400b6984  mov     [rbp+140h+var_90], rax
0x1400b698b  mov     eax, [rdi+19h]
0x1400b698e  mov     dword ptr [rsp+240h+var_1D0], eax
0x1400b6992  lea     rax, [rsp+240h+var_1D0]
0x1400b6997  mov     [rbp+140h+var_80], rax
0x1400b699e  lea     rax, [rbp+140h+var_58]
0x1400b69a5  mov     [rbp+140h+var_70], rax
0x1400b69ac  movzx   eax, word ptr [rdi]
0x1400b69af  mov     [rbp+140h+var_58], eax
0x1400b69b5  lea     rax, [rbp+140h+var_1C0]
0x1400b69b9  mov     [rbp+140h+var_50], rax
0x1400b69c0  lea     rax, [rbp+140h+var_F0]
0x1400b69c4  mov     [rsp+240h+var_218], rax
0x1400b69c9  mov     dword ptr [rsp+240h+UserData], 0Bh
0x1400b69d1  mov     [rbp+140h+var_B8], 8
0x1400b69dc  mov     [rbp+140h+var_A8], 1
0x1400b69e7  mov     [rbp+140h+var_98], 2
0x1400b69f2  mov     [rbp+140h+var_88], 4
0x1400b69fd  mov     [rbp+140h+var_78], 4
  ... truncated ...
```
