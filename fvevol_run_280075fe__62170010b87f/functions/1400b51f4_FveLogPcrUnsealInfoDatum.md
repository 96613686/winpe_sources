# FveLogPcrUnsealInfoDatum

- ea: `0x1400b51f4`
- end: `0x1400b5784`
- name: `FveLogPcrUnsealInfoDatum`
- size: `1424`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14009e1b0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140006670`
- `0x140006fc8`
- `0x140007ce8`
- `0x14000a480`
- `0x14000d7a8`
- `0x1400177cc`
- `0x140017c40`
- `0x1400218c0`
- `0x140021a00`
- `0x140021d00`
- `0x1400b51f4`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400b55d2`
- `ntoskrnl!EtwWrite` at `0x1400b55d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b574b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b574b`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5414`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5414`

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
  __int64 v22; // rcx
  int v23; // r11d
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  USHORT pusResult[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v27[2]; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v28; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pulResult; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v30; // [rsp+58h] [rbp-A8h] BYREF
  ULONG v31; // [rsp+5Ch] [rbp-A4h] BYREF
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  ULONGLONG v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[12]; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+150h] [rbp+50h] BYREF
  _WORD *v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+178h] [rbp+78h]
  __int64 *v42; // [rsp+180h] [rbp+80h]
  __int64 v43; // [rsp+188h] [rbp+88h]
  USHORT *v44; // [rsp+190h] [rbp+90h]
  __int64 v45; // [rsp+198h] [rbp+98h]
  __int16 *v46; // [rsp+1A0h] [rbp+A0h]
  __int64 v47; // [rsp+1A8h] [rbp+A8h]
  ULONGLONG *v48; // [rsp+1B0h] [rbp+B0h]
  __int64 v49; // [rsp+1B8h] [rbp+B8h]
  __int64 *v50; // [rsp+1C0h] [rbp+C0h]
  __int64 v51; // [rsp+1C8h] [rbp+C8h]
  _DWORD *v52; // [rsp+1D0h] [rbp+D0h]
  __int64 v53; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 *v54; // [rsp+1E0h] [rbp+E0h]
  _DWORD v55[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 *v56; // [rsp+1F0h] [rbp+F0h]
  __int64 v57; // [rsp+1F8h] [rbp+F8h]

  memset(UserData, 0, sizeof(UserData));
  WORD2(v25) = 0;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v32 = 0;
  v8 = 0;
  v33 = 0;
  LOWORD(v25) = 0;
  pulResult = 0;
  v35 = 0;
  pusResult[0] = 0;
  v27[0] = 0;
  v31 = 0;
  v34 = 0;
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
      v25);
    v11 = 0;
  }
  v13 = *(_DWORD *)((char *)a2 + 21);
  for ( i = 0; v13; v13 &= v13 - 1 )
    LOWORD(i) = i + 1;
  WORD2(v25) = i;
  v15 = *(_DWORD *)((char *)a2 + 25);
  for ( j = 0; v15; v15 &= v15 - 1 )
    LOWORD(j) = j + 1;
  v33 = *(unsigned __int16 *)((char *)a2 + 19);
  v28 = j;
  switch ( v33 )
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
  LOWORD(v25) = v17;
  if ( (_WORD)i )
  {
    v6 = FveAllAllPurposeArraysFromPcrUnsealInfo(a2, i, j, &v35);
    if ( v6 < 0 )
      goto LABEL_42;
    v6 = RtlULongLongToULong(WORD2(v25) * (unsigned __int64)(unsigned __int16)v25, &pulResult);
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
    LOWORD(i) = WORD2(v25);
    v17 = v25;
    v7 = v35;
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
      if ( ++v20 >= WORD2(v25) )
        goto LABEL_38;
      v17 = v25;
    }
  }
  else
  {
LABEL_38:
    if ( !v28
      || (v6 = FveNthPcrDataFromPcrUnsealInfo((_DWORD)a2, 0, j, (unsigned int)v27, (__int64)&v34), v6 >= 0)
      && (v6 = RtlULongSub(*a2, v27[0], &v31), v6 >= 0) )
    {
      *(_QWORD *)&UserData[0].Size = 8;
      UserData[0].Ptr = (ULONGLONG)(a2 + 5);
      v32 = *((unsigned __int8 *)a2 + 18);
      *(_QWORD *)&UserData[1].Size = 4;
      UserData[1].Ptr = (ULONGLONG)&v32;
      UserData[2].Ptr = (ULONGLONG)&v33;
      UserData[3].Ptr = (ULONGLONG)&v25;
      UserData[4].Ptr = (ULONGLONG)a2 + 21;
      UserData[5].Ptr = (ULONGLONG)&v25 + 4;
      UserData[7].Ptr = (ULONGLONG)&v28;
      UserData[8].Ptr = (ULONGLONG)&pulResult;
      UserData[9].Size = pulResult;
      UserData[10].Ptr = (ULONGLONG)&v31;
      UserData[11].Ptr = v34;
      UserData[11].Size = v31;
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
  if ( a2 && (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
  {
    v27[0] = a2[4];
    v41 = 2;
    v40 = v27;
    v36 = *(_QWORD *)(a2 + 5);
    v42 = &v36;
    LOBYTE(pusResult[0]) = *((_BYTE *)a2 + 18);
    v44 = pusResult;
    v30 = *(unsigned __int16 *)((char *)a2 + 19);
    v46 = &v30;
    LODWORD(v34) = *(_DWORD *)((char *)a2 + 21);
    v48 = &v34;
    LODWORD(v35) = *(_DWORD *)((char *)a2 + 25);
    v50 = &v35;
    v52 = v55;
    v55[0] = *a2;
    v56 = &v37;
    v43 = 8;
    v45 = 1;
    v47 = 2;
    v49 = 4;
    v51 = 4;
    v53 = 2;
    v54 = a2;
    v55[1] = v23;
    v37 = 0x1000000;
    v57 = 8;
    tlgWriteTransfer_EtwWriteTransfer(v22, (unsigned __int8 *)word_14003BDCA, 0, 0, 0xBu, &v39);
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0x30455646u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b51f4  mov     [rsp-8+arg_10], rbx
0x1400b51f9  push    rbp
0x1400b51fa  push    rsi
0x1400b51fb  push    rdi
0x1400b51fc  push    r12
0x1400b51fe  push    r13
0x1400b5200  push    r14
0x1400b5202  push    r15
0x1400b5204  lea     rbp, [rsp-110h]
0x1400b520c  sub     rsp, 210h
0x1400b5213  mov     rax, cs:__security_cookie
0x1400b521a  xor     rax, rsp
0x1400b521d  mov     [rbp+140h+var_40], rax
0x1400b5224  mov     rdi, rdx
0x1400b5227  mov     rsi, rcx
0x1400b522a  xor     edx, edx; Val
0x1400b522c  lea     rcx, [rbp+140h+var_1B0]; void *
0x1400b5230  mov     r8d, 0C0h; Size
0x1400b5236  call    memset
0x1400b523b  xor     r11d, r11d
0x1400b523e  mov     [rsp+240h+var_1FC], r11w
0x1400b5244  mov     ebx, r11d
0x1400b5247  mov     [rsp+240h+var_1F0], r11w
0x1400b524d  mov     r15d, r11d
0x1400b5250  mov     [rsp+240h+var_1E0], r11d
0x1400b5255  mov     r14d, r11d
0x1400b5258  mov     [rsp+240h+var_1DC], r11d
0x1400b525d  lea     r12d, [r11+1]
0x1400b5261  mov     [rsp+240h+var_200], r11w
0x1400b5267  mov     [rsp+240h+pulResult], r11d
0x1400b526c  mov     [rsp+240h+var_1D0], r11
0x1400b5271  mov     [rsp+240h+pusResult], r11w
0x1400b5277  mov     [rsp+240h+var_1F4], r11w
0x1400b527d  mov     [rsp+240h+var_1E4], r11d
0x1400b5282  mov     [rsp+240h+var_1D8], r11
0x1400b5287  test    rsi, rsi
0x1400b528a  jz      loc_1400B55E3
0x1400b5290  mov     rax, [rsi+40h]
0x1400b5294  mov     r13, [rax+8]
0x1400b5298  test    r13, r13
0x1400b529b  jz      loc_1400B55E3
0x1400b52a1  cmp     [r13+58h], r11
0x1400b52a5  jz      loc_1400B55E3
0x1400b52ab  lea     esi, [r11+20h]
0x1400b52af  mov     rcx, rdi
0x1400b52b2  mov     edx, esi
0x1400b52b4  call    FveDatumMustBe
0x1400b52b9  xor     r11d, r11d
0x1400b52bc  mov     ebx, eax
0x1400b52be  test    eax, eax
0x1400b52c0  js      loc_1400B55E3
0x1400b52c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b52cd  lea     rax, WPP_GLOBAL_Control
0x1400b52d4  cmp     rcx, rax
0x1400b52d7  jz      short loc_1400B532B
0x1400b52d9  test    dword ptr [rcx+2Ch], 8000h
0x1400b52e0  jz      short loc_1400B532B
0x1400b52e2  cmp     byte ptr [rcx+29h], 5
0x1400b52e6  jb      short loc_1400B532B
0x1400b52e8  mov     eax, [rdi+19h]
0x1400b52eb  lea     r9, aFalse; "false"
0x1400b52f2  cmp     [rdi+12h], r11b
0x1400b52f6  lea     rdx, aTrue; "true"
0x1400b52fd  movzx   r8d, word ptr [rdi+13h]
0x1400b5302  mov     rcx, [rcx+18h]
0x1400b5306  cmovz   rdx, r9
0x1400b530a  mov     r9, [rdi+0Ah]
0x1400b530e  mov     [rsp+240h+var_208], eax
0x1400b5312  mov     eax, [rdi+15h]
0x1400b5315  mov     [rsp+240h+var_210], eax
0x1400b5319  mov     dword ptr [rsp+240h+var_218], r8d
0x1400b531e  mov     [rsp+240h+UserData], rdx
0x1400b5323  call    WPP_SF_ISDLL
0x1400b5328  xor     r11d, r11d
0x1400b532b  mov     ecx, [rdi+15h]
0x1400b532e  mov     edx, r11d
0x1400b5331  test    ecx, ecx
0x1400b5333  jz      short loc_1400B5340
0x1400b5335  add     dx, r12w
0x1400b5339  lea     eax, [rcx-1]
0x1400b533c  and     ecx, eax
0x1400b533e  jnz     short loc_1400B5335
0x1400b5340  lea     r12, [rdi+19h]
0x1400b5344  mov     [rsp+240h+var_1FC], dx
0x1400b5349  mov     ecx, [r12]
0x1400b534d  mov     r8d, r11d
0x1400b5350  test    ecx, ecx
0x1400b5352  jz      short loc_1400B5365
0x1400b5354  mov     r9d, 1
0x1400b535a  add     r8w, r9w
0x1400b535e  lea     eax, [rcx-1]
0x1400b5361  and     ecx, eax
0x1400b5363  jnz     short loc_1400B535A
0x1400b5365  movzx   ecx, word ptr [rdi+13h]
0x1400b5369  mov     eax, 40h ; '@'
0x1400b536e  mov     [rsp+240h+var_1DC], ecx
0x1400b5372  mov     [rsp+240h+var_1F0], r8w
0x1400b5378  sub     ecx, 4
0x1400b537b  jz      short loc_1400B53B9
0x1400b537d  sub     ecx, 7
0x1400b5380  jz      short loc_1400B53B3
0x1400b5382  sub     ecx, 1
0x1400b5385  jz      short loc_1400B53AB
0x1400b5387  sub     ecx, 1
0x1400b538a  jz      short loc_1400B53A5
0x1400b538c  sub     ecx, 5
0x1400b538f  jz      short loc_1400B53B3
0x1400b5391  sub     ecx, 15h
0x1400b5394  jz      short loc_1400B53B3
0x1400b5396  sub     ecx, 1
0x1400b5399  jz      short loc_1400B53AB
0x1400b539b  cmp     ecx, 1
0x1400b539e  jz      short loc_1400B53A5
0x1400b53a0  mov     r9d, r11d
0x1400b53a3  jmp     short loc_1400B53BF
0x1400b53a5  movzx   r9d, ax
0x1400b53a9  jmp     short loc_1400B53BF
0x1400b53ab  mov     r9d, 30h ; '0'
0x1400b53b1  jmp     short loc_1400B53BF
0x1400b53b3  movzx   r9d, si
0x1400b53b7  jmp     short loc_1400B53BF
0x1400b53b9  mov     r9d, 14h
0x1400b53bf  mov     [rsp+240h+var_200], r9w
0x1400b53c5  test    dx, dx
0x1400b53c8  jz      short loc_1400B5445
0x1400b53ca  lea     r9, [rsp+240h+var_1D0]
0x1400b53cf  mov     rcx, rdi
0x1400b53d2  call    FveAllAllPurposeArraysFromPcrUnsealInfo
0x1400b53d7  xor     r11d, r11d
0x1400b53da  mov     ebx, eax
0x1400b53dc  test    eax, eax
0x1400b53de  js      loc_1400B55E3
0x1400b53e4  movzx   eax, [rsp+240h+var_1FC]
0x1400b53e9  lea     rdx, [rsp+240h+pulResult]; pulResult
0x1400b53ee  movzx   ecx, [rsp+240h+var_200]
0x1400b53f3  imul    rcx, rax; ullOperand
0x1400b53f7  call    RtlULongLongToULong
0x1400b53fc  mov     ebx, eax
0x1400b53fe  test    eax, eax
0x1400b5400  js      loc_1400B55E3
0x1400b5406  mov     edx, [rsp+240h+pulResult]
0x1400b540a  lea     ecx, [r11+40h]
0x1400b540e  mov     r8d, 30455646h
0x1400b5414  call    cs:__imp_ExAllocatePool2
0x1400b541b  nop     dword ptr [rax+rax+00h]
0x1400b5420  xor     r11d, r11d
0x1400b5423  mov     r14, rax
0x1400b5426  test    rax, rax
0x1400b5429  jnz     short loc_1400B5435
0x1400b542b  mov     ebx, 0C0000017h
0x1400b5430  jmp     loc_1400B55E3
0x1400b5435  movzx   edx, [rsp+240h+var_1FC]
0x1400b543a  movzx   r9d, [rsp+240h+var_200]
0x1400b5440  mov     r15, [rsp+240h+var_1D0]
0x1400b5445  mov     esi, r11d
0x1400b5448  cmp     r11w, dx
0x1400b544c  jnb     short loc_1400B549D
0x1400b544e  movzx   eax, r9w
0x1400b5452  lea     rdx, [rsp+240h+pusResult]; pusResult
0x1400b5457  movzx   ecx, si
0x1400b545a  imul    ecx, eax; ulOperand
0x1400b545d  call    RtlULongToUShort
0x1400b5462  mov     ebx, eax
0x1400b5464  test    eax, eax
0x1400b5466  js      loc_1400B55E3
0x1400b546c  movzx   ecx, [rsp+240h+pusResult]
0x1400b5471  movzx   eax, si
0x1400b5474  add     rcx, r14; void *
0x1400b5477  movzx   r8d, r9w; Size
0x1400b547b  mov     rdx, [r15+rax*8]
0x1400b547f  add     rdx, 8; Src
0x1400b5483  call    memmove
0x1400b5488  xor     r11d, r11d
0x1400b548b  inc     si
0x1400b548e  cmp     si, [rsp+240h+var_1FC]
0x1400b5493  jnb     short loc_1400B549D
0x1400b5495  movzx   r9d, [rsp+240h+var_200]
0x1400b549b  jmp     short loc_1400B544E
0x1400b549d  cmp     [rsp+240h+var_1F0], r11w
0x1400b54a3  jz      short loc_1400B54E7
0x1400b54a5  lea     rax, [rsp+240h+var_1D8]
0x1400b54aa  xor     edx, edx
0x1400b54ac  lea     r9, [rsp+240h+var_1F4]
0x1400b54b1  mov     [rsp+240h+UserData], rax
0x1400b54b6  mov     rcx, rdi
0x1400b54b9  call    FveNthPcrDataFromPcrUnsealInfo
0x1400b54be  xor     r11d, r11d
0x1400b54c1  mov     ebx, eax
0x1400b54c3  test    eax, eax
0x1400b54c5  js      loc_1400B55E3
0x1400b54cb  movzx   edx, [rsp+240h+var_1F4]; ulSubtrahend
0x1400b54d0  lea     r8, [rsp+240h+var_1E4]; pulResult
0x1400b54d5  movzx   ecx, word ptr [rdi]; ulMinuend
0x1400b54d8  call    RtlULongSub
0x1400b54dd  mov     ebx, eax
0x1400b54df  test    eax, eax
0x1400b54e1  js      loc_1400B55E3
0x1400b54e7  lea     rax, [rdi+0Ah]
0x1400b54eb  mov     qword ptr [rbp+140h+var_1B0.Size], 8
0x1400b54f3  mov     [rbp+140h+var_1B0.Ptr], rax
0x1400b54f7  lea     rdx, FVE_KEYRING_PCR_UNSEAL_INFO; EventDescriptor
0x1400b54fe  movzx   eax, byte ptr [rdi+12h]
0x1400b5502  mov     r9d, 0Ch; UserDataCount
0x1400b5508  mov     [rsp+240h+var_1E0], eax
0x1400b550c  xor     r8d, r8d; ActivityId
0x1400b550f  lea     rax, [rsp+240h+var_1E0]
0x1400b5514  mov     [rbp+140h+var_198], 4
0x1400b551c  mov     [rbp+140h+var_1A0], rax
0x1400b5520  lea     rax, [rsp+240h+var_1DC]
0x1400b5525  mov     [rbp+140h+var_190], rax
0x1400b5529  lea     rax, [rsp+240h+var_200]
0x1400b552e  mov     [rbp+140h+var_180], rax
0x1400b5532  lea     rax, [rdi+15h]
0x1400b5536  mov     [rbp+140h+var_170], rax
0x1400b553a  lea     rax, [rsp+240h+var_1FC]
0x1400b553f  mov     [rbp+140h+var_160], rax
0x1400b5543  lea     rax, [rsp+240h+var_1F0]
0x1400b5548  mov     [rbp+140h+var_140], rax
0x1400b554c  lea     rax, [rsp+240h+pulResult]
0x1400b5551  mov     [rbp+140h+var_130], rax
0x1400b5555  mov     eax, [rsp+240h+pulResult]
0x1400b5559  mov     [rbp+140h+var_118], eax
0x1400b555c  lea     rax, [rsp+240h+var_1E4]
0x1400b5561  mov     [rbp+140h+var_110], rax
0x1400b5565  mov     rax, [rsp+240h+var_1D8]
0x1400b556a  mov     [rbp+140h+var_100], rax
0x1400b556e  mov     eax, [rsp+240h+var_1E4]
0x1400b5572  mov     [rbp+140h+var_F8], eax
0x1400b5575  lea     rax, [rbp+140h+var_1B0]
0x1400b5579  mov     [rbp+140h+var_188], 4
0x1400b5581  mov     [rbp+140h+var_178], 2
0x1400b5589  mov     [rbp+140h+var_168], 4
0x1400b5591  mov     [rbp+140h+var_158], 2
0x1400b5599  mov     [rbp+140h+var_150], r12
0x1400b559d  mov     [rbp+140h+var_148], 4
0x1400b55a5  mov     [rbp+140h+var_138], 2
0x1400b55ad  mov     [rbp+140h+var_128], 4
0x1400b55b5  mov     [rbp+140h+var_120], r14
0x1400b55b9  mov     [rbp+140h+var_114], r11d
0x1400b55bd  mov     [rbp+140h+var_108], 4
0x1400b55c5  mov     [rbp+140h+var_F4], r11d
0x1400b55c9  mov     rcx, [r13+58h]; RegHandle
0x1400b55cd  mov     [rsp+240h+UserData], rax; UserData
0x1400b55d2  call    cs:__imp_EtwWrite
0x1400b55d9  nop     dword ptr [rax+rax+00h]
0x1400b55de  mov     ebx, eax
0x1400b55e0  xor     r11d, r11d
0x1400b55e3  test    rdi, rdi
0x1400b55e6  jz      loc_1400B573E
0x1400b55ec  mov     eax, cs:dword_140045040
0x1400b55f2  cmp     eax, 4
0x1400b55f5  jbe     loc_1400B573E
0x1400b55fb  mov     rdx, 400000000000h
0x1400b5605  lea     rcx, dword_140045040
0x1400b560c  call    _tlgKeywordOn
0x1400b5611  test    al, al
0x1400b5613  jz      loc_1400B573E
0x1400b5619  movzx   eax, word ptr [rdi+8]
0x1400b561d  lea     rdx, word_14003BDCA
0x1400b5624  mov     [rsp+240h+var_1F4], ax
0x1400b5629  xor     r9d, r9d
0x1400b562c  lea     rax, [rsp+240h+var_1F4]
0x1400b5631  mov     [rbp+140h+var_C8], 2
0x1400b5639  mov     [rbp+140h+var_D0], rax
0x1400b563d  xor     r8d, r8d
0x1400b5640  mov     rax, [rdi+0Ah]
0x1400b5644  mov     [rsp+240h+var_1C8], rax
0x1400b5649  lea     rax, [rsp+240h+var_1C8]
0x1400b564e  mov     [rbp+140h+var_C0], rax
0x1400b5655  mov     al, [rdi+12h]
0x1400b5658  mov     byte ptr [rsp+240h+pusResult], al
0x1400b565c  lea     rax, [rsp+240h+pusResult]
0x1400b5661  mov     [rbp+140h+var_B0], rax
0x1400b5668  movzx   eax, word ptr [rdi+13h]
0x1400b566c  mov     [rsp+240h+var_1E8], ax
0x1400b5671  lea     rax, [rsp+240h+var_1E8]
0x1400b5676  mov     [rbp+140h+var_A0], rax
0x1400b567d  mov     eax, [rdi+15h]
0x1400b5680  mov     dword ptr [rsp+240h+var_1D8], eax
0x1400b5684  lea     rax, [rsp+240h+var_1D8]
0x1400b5689  mov     [rbp+140h+var_90], rax
0x1400b5690  mov     eax, [rdi+19h]
0x1400b5693  mov     dword ptr [rsp+240h+var_1D0], eax
0x1400b5697  lea     rax, [rsp+240h+var_1D0]
0x1400b569c  mov     [rbp+140h+var_80], rax
0x1400b56a3  lea     rax, [rbp+140h+var_58]
0x1400b56aa  mov     [rbp+140h+var_70], rax
0x1400b56b1  movzx   eax, word ptr [rdi]
0x1400b56b4  mov     [rbp+140h+var_58], eax
0x1400b56ba  lea     rax, [rbp+140h+var_1C0]
0x1400b56be  mov     [rbp+140h+var_50], rax
0x1400b56c5  lea     rax, [rbp+140h+var_F0]
0x1400b56c9  mov     [rsp+240h+var_218], rax
0x1400b56ce  mov     dword ptr [rsp+240h+UserData], 0Bh
0x1400b56d6  mov     [rbp+140h+var_B8], 8
0x1400b56e1  mov     [rbp+140h+var_A8], 1
0x1400b56ec  mov     [rbp+140h+var_98], 2
0x1400b56f7  mov     [rbp+140h+var_88], 4
0x1400b5702  mov     [rbp+140h+var_78], 4
0x1400b570d  mov     [rbp+140h+var_68], 2
  ... truncated ...
```
