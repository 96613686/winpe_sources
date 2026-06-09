# FsmInit

- ea: `0x18000cb10`
- end: `0x18000d01a`
- name: `FsmInit`
- size: `1290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b08`
- `0x180015ae0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000cb10`
- `0x18000d020`
- `0x18000f334`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000cbac`: `FsmInit called for protocol = %x, port = %d`
- `0x18000cdca`: `FsmInit for protocol = %x Configuration 0x%x `
- `0x18000ce4c`: `FsmInit for protocol = %x Configuration 0x%x`
- `0x18000cf32`: `FsmInit for protocol = %x failed with error %d`

## pseudocode

```c
__int64 __fastcall FsmInit(__int64 a1, unsigned int a2)
{
  __int64 v2; // r15
  __int64 PointerToCPCB; // rax
  _DWORD *v5; // rdi
  __int64 v7; // r9
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r9d
  __int64 v11; // rax
  __int64 v12; // r8
  _OWORD *v13; // rax
  int *v14; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  bool v22; // zf
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  _OWORD *v25; // rax
  _OWORD *v26; // rcx
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  char v36; // cl
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // rsi
  __int64 v40; // rax
  unsigned int v41; // eax
  unsigned int v42; // r14d
  int v43; // r9d
  _DWORD v44[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h]
  int v46; // [rsp+50h] [rbp-B0h]
  __int64 (__fastcall *v47)(); // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  int v49; // [rsp+68h] [rbp-98h]
  _DWORD v50[269]; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v51; // [rsp+4A0h] [rbp+3A0h]
  __int64 v52; // [rsp+4A8h] [rbp+3A8h]
  __int64 v53; // [rsp+4B0h] [rbp+3B0h]
  __int64 v54; // [rsp+4B8h] [rbp+3B8h]
  int v55; // [rsp+4C0h] [rbp+3C0h]
  __int64 v56; // [rsp+4C8h] [rbp+3C8h]
  __int128 v57; // [rsp+4D8h] [rbp+3D8h]
  _OWORD v58[2]; // [rsp+4E8h] [rbp+3E8h]
  int v59; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v60[2044]; // [rsp+514h] [rbp+414h] BYREF

  v2 = a2;
  v44[1] = 0;
  memset_0(v44, 0, 0x4C4u);
  PointerToCPCB = GetPointerToCPCB(a1, (unsigned int)v2);
  v59 = 0;
  v5 = (_DWORD *)PointerToCPCB;
  memset_0(v60, 0, sizeof(v60));
  if ( !v5 )
    return 0;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v59) = 0;
    FormatRRASErrorString(
      &v59,
      L"FsmInit called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v7);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v59);
  }
  v5[14] = 1;
  v5[10] = 0;
  *v5 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v9 = *(_DWORD *)(a1 + 56);
  v10 = *(_DWORD *)(a1 + 60);
  v45 = *(_QWORD *)(a1 + 16);
  v44[0] = v9 & 4;
  v47 = CompletionRoutine;
  v48 = v8 + 1344;
  v46 = v10;
  v49 = v9 & 8;
  v55 = *(_DWORD *)(v8 + 1320);
  v51 = v8 + 216;
  v52 = a1 + 1665;
  v53 = *(_QWORD *)(v8 + 40);
  v11 = *(_QWORD *)(a1 + 168);
  if ( !v11 )
    v11 = *(_QWORD *)(a1 + 160);
  v56 = v11;
  v12 = 8;
  if ( (v9 & 4) != 0 )
  {
    v13 = v50;
    v14 = &dword_18004CAD0;
    do
    {
      v15 = *((_OWORD *)v14 + 1);
      *v13 = *(_OWORD *)v14;
      v16 = *((_OWORD *)v14 + 2);
      v13[1] = v15;
      v17 = *((_OWORD *)v14 + 3);
      v13[2] = v16;
      v18 = *((_OWORD *)v14 + 4);
      v13[3] = v17;
      v19 = *((_OWORD *)v14 + 5);
      v13[4] = v18;
      v20 = *((_OWORD *)v14 + 6);
      v13[5] = v19;
      v21 = *((_OWORD *)v14 + 7);
      v14 += 32;
      v13[6] = v20;
      v13[7] = v21;
      v13 += 8;
      --v12;
    }
    while ( v12 );
    v22 = (dword_18004CAD0 & 0x400000) == 0;
    v23 = *((_OWORD *)v14 + 1);
    *v13 = *(_OWORD *)v14;
    v24 = *((_OWORD *)v14 + 2);
    v13[1] = v23;
    v13[2] = v24;
    if ( !v22 )
    {
      if ( (v10 & 0x20000) != 0 )
        v50[0] |= 0x4000u;
      else
        v50[0] &= ~0x400000u;
    }
  }
  else
  {
    v25 = (_OWORD *)(a1 + 184);
    v26 = v50;
    do
    {
      v27 = v25[1];
      *v26 = *v25;
      v28 = v25[2];
      v26[1] = v27;
      v29 = v25[3];
      v26[2] = v28;
      v30 = v25[4];
      v26[3] = v29;
      v31 = v25[5];
      v26[4] = v30;
      v32 = v25[6];
      v26[5] = v31;
      v33 = v25[7];
      v25 += 8;
      v26[6] = v32;
      v26[7] = v33;
      v26 += 8;
      --v12;
    }
    while ( v12 );
    v34 = v25[1];
    *v26 = *v25;
    v35 = v25[2];
    v26[1] = v34;
    v26[2] = v35;
  }
  v36 = byte_18004CF34;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v37 = *(unsigned int *)(a1 + 184);
    LOWORD(v59) = 0;
    FormatRRASErrorString(
      &v59,
      L"FsmInit for protocol = %x Configuration 0x%x ",
      *((unsigned int *)CpTable + 44 * v2),
      v37);
    v36 = byte_18004CF34;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v59);
      v36 = byte_18004CF34;
    }
  }
  if ( (*(_DWORD *)(a1 + 184) & 0x4000) != 0 && *(_WORD *)(a1 + 60) == 14 )
  {
    v50[0] |= 0x4000u;
    if ( (v36 & 1) != 0 )
    {
      LOWORD(v59) = 0;
      FormatRRASErrorString(&v59, L"FsmInit for protocol = %x Configuration 0x%x", *((unsigned int *)CpTable + 44 * v2));
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v59);
    }
  }
  v38 = *(_QWORD *)(a1 + 8);
  v39 = 176 * v2;
  v57 = *(_OWORD *)(v38 + 1968);
  v58[0] = *(_OWORD *)(v38 + 1984);
  *(_OWORD *)((char *)v58 + 12) = *(_OWORD *)(v38 + 1996);
  if ( *((_DWORD *)CpTable + 44 * v2) == 32801 )
  {
    v40 = *(_QWORD *)(v38 + 1328);
  }
  else
  {
    if ( *((_DWORD *)CpTable + 44 * v2) != 32855 )
    {
      v54 = -1;
      goto LABEL_32;
    }
    v40 = *(_QWORD *)(v38 + 1336);
  }
  v54 = v40;
LABEL_32:
  v41 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD *))((char *)CpTable + v39 + 32))(v5 + 4, v44);
  v42 = v41;
  if ( v41 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v59) = 0;
      FormatRRASErrorString(
        &v59,
        L"FsmInit for protocol = %x failed with error %d",
        *(unsigned int *)((char *)CpTable + v39),
        v41);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v59);
    }
    v5[10] = v42;
LABEL_37:
    v5[11] = 0;
    return 0;
  }
  if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
  {
    v43 = *(_DWORD *)((char *)CpTable + v39);
    if ( v43 == 32855 || v43 == 32801 )
      InsertInTimerQ(
        *(_DWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 16),
        v5[2],
        v43,
        0,
        8,
        dword_18004C9F8 * *(_DWORD *)(a1 + 36));
  }
  v5[12] = 1;
  if ( !(unsigned int)FsmReset(a1, (unsigned int)v2) )
    goto LABEL_37;
  return 1;
}

```

## disassembly

```asm
0x18000cb10  mov     [rsp-8+arg_10], rbx
0x18000cb15  mov     [rsp-8+arg_18], rsi
0x18000cb1a  push    rbp
0x18000cb1b  push    rdi
0x18000cb1c  push    r13
0x18000cb1e  push    r14
0x18000cb20  push    r15
0x18000cb22  lea     rbp, [rsp-0C20h]
0x18000cb2a  sub     rsp, 0D20h
0x18000cb31  mov     rax, cs:__security_cookie
0x18000cb38  xor     rax, rsp
0x18000cb3b  mov     [rbp+0C40h+var_30], rax
0x18000cb42  mov     r15d, edx
0x18000cb45  mov     rbx, rcx
0x18000cb48  xor     eax, eax
0x18000cb4a  lea     rcx, [rsp+0D40h+var_D00]; void *
0x18000cb4f  xor     edx, edx; Val
0x18000cb51  mov     [rsp+0D40h+var_CFC], eax
0x18000cb55  mov     r8d, 4C4h; Size
0x18000cb5b  call    memset_0
0x18000cb60  mov     edx, r15d
0x18000cb63  mov     rcx, rbx
0x18000cb66  call    GetPointerToCPCB
0x18000cb6b  xor     ecx, ecx
0x18000cb6d  xor     edx, edx; Val
0x18000cb6f  mov     [rbp+0C40h+var_830], ecx
0x18000cb75  mov     r8d, 7FCh; Size
0x18000cb7b  lea     rcx, [rbp+0C40h+var_82C]; void *
0x18000cb82  mov     rdi, rax
0x18000cb85  call    memset_0
0x18000cb8a  test    rdi, rdi
0x18000cb8d  jnz     short loc_18000CB96
0x18000cb8f  xor     eax, eax
0x18000cb91  jmp     loc_18000CFEF
0x18000cb96  mov     r13d, 1
0x18000cb9c  test    cs:byte_18004CF34, r13b
0x18000cba3  jz      short loc_18000CBFA
0x18000cba5  mov     r8, cs:CpTable
0x18000cbac  lea     rdx, aFsminitCalledF; "FsmInit called for protocol = %x, port "...
0x18000cbb3  mov     r9, [rbx+10h]
0x18000cbb7  xor     eax, eax
0x18000cbb9  imul    rcx, r15, 0B0h
0x18000cbc0  mov     word ptr [rbp+0C40h+var_830], ax
0x18000cbc7  mov     r8d, [rcx+r8]
0x18000cbcb  lea     rcx, [rbp+0C40h+var_830]
0x18000cbd2  call    FormatRRASErrorString
0x18000cbd7  test    cs:byte_18004CF34, r13b
0x18000cbde  jz      short loc_18000CBFA
0x18000cbe0  lea     r8, [rbp+0C40h+var_830]
0x18000cbe7  lea     rdx, RasPppTraceInfo
0x18000cbee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cbf5  call    McTemplateU0z_EventWriteTransfer
0x18000cbfa  mov     [rdi+38h], r13d
0x18000cbfe  mov     r10d, 8
0x18000cc04  mov     dword ptr [rdi+28h], 0
0x18000cc0b  mov     dword ptr [rdi], 0
0x18000cc11  mov     rcx, [rbx+8]
0x18000cc15  mov     rax, [rbx+10h]
0x18000cc19  mov     edx, [rbx+38h]
0x18000cc1c  mov     r8d, edx
0x18000cc1f  mov     r9d, [rbx+3Ch]
0x18000cc23  and     r8d, 4
0x18000cc27  mov     [rsp+0D40h+var_CF8], rax
0x18000cc2c  and     edx, r10d
0x18000cc2f  lea     rax, CompletionRoutine
0x18000cc36  mov     [rsp+0D40h+var_D00], r8d
0x18000cc3b  mov     [rsp+0D40h+var_CE8], rax
0x18000cc40  lea     rax, [rcx+540h]
0x18000cc47  mov     [rsp+0D40h+var_CE0], rax
0x18000cc4c  mov     [rsp+0D40h+var_CF0], r9d
0x18000cc51  mov     [rsp+0D40h+var_CD8], edx
0x18000cc55  mov     eax, [rcx+528h]
0x18000cc5b  mov     [rbp+0C40h+var_880], eax
0x18000cc61  lea     rax, [rcx+0D8h]
0x18000cc68  mov     [rbp+0C40h+var_8A0], rax
0x18000cc6f  lea     rax, [rbx+681h]
0x18000cc76  mov     [rbp+0C40h+var_898], rax
0x18000cc7d  mov     rax, [rcx+28h]
0x18000cc81  mov     [rbp+0C40h+var_890], rax
0x18000cc88  mov     rax, [rbx+0A8h]
0x18000cc8f  test    rax, rax
0x18000cc92  jnz     short loc_18000CC9B
0x18000cc94  mov     rax, [rbx+0A0h]
0x18000cc9b  test    r8d, r8d
0x18000cc9e  mov     [rbp+0C40h+var_878], rax
0x18000cca5  mov     r8, r10
0x18000cca8  mov     edx, 80h
0x18000ccad  jz      loc_18000CD45
0x18000ccb3  lea     rax, [rsp+0D40h+var_CD4]
0x18000ccb8  lea     rcx, dword_18004CAD0
0x18000ccbf  movups  xmm0, xmmword ptr [rcx]
0x18000ccc2  movups  xmm1, xmmword ptr [rcx+10h]
0x18000ccc6  movups  xmmword ptr [rax], xmm0
0x18000ccc9  movups  xmm0, xmmword ptr [rcx+20h]
0x18000cccd  movups  xmmword ptr [rax+10h], xmm1
0x18000ccd1  movups  xmm1, xmmword ptr [rcx+30h]
0x18000ccd5  movups  xmmword ptr [rax+20h], xmm0
0x18000ccd9  movups  xmm0, xmmword ptr [rcx+40h]
0x18000ccdd  movups  xmmword ptr [rax+30h], xmm1
0x18000cce1  movups  xmm1, xmmword ptr [rcx+50h]
0x18000cce5  movups  xmmword ptr [rax+40h], xmm0
0x18000cce9  movups  xmm0, xmmword ptr [rcx+60h]
0x18000cced  movups  xmmword ptr [rax+50h], xmm1
0x18000ccf1  movups  xmm1, xmmword ptr [rcx+70h]
0x18000ccf5  add     rcx, rdx
0x18000ccf8  movups  xmmword ptr [rax+60h], xmm0
0x18000ccfc  movups  xmmword ptr [rax+70h], xmm1
0x18000cd00  add     rax, rdx
0x18000cd03  sub     r8, r13
0x18000cd06  jnz     short loc_18000CCBF
0x18000cd08  test    cs:dword_18004CAD0, 400000h
0x18000cd12  movups  xmm0, xmmword ptr [rcx]
0x18000cd15  movups  xmm1, xmmword ptr [rcx+10h]
0x18000cd19  movups  xmmword ptr [rax], xmm0
0x18000cd1c  movups  xmm0, xmmword ptr [rcx+20h]
0x18000cd20  movups  xmmword ptr [rax+10h], xmm1
0x18000cd24  movups  xmmword ptr [rax+20h], xmm0
0x18000cd28  jz      loc_18000CDB0
0x18000cd2e  bt      r9d, 11h
0x18000cd33  jnb     short loc_18000CD3D
0x18000cd35  bts     [rsp+0D40h+var_CD4], 0Eh
0x18000cd3b  jmp     short loc_18000CDB0
0x18000cd3d  btr     [rsp+0D40h+var_CD4], 16h
0x18000cd43  jmp     short loc_18000CDB0
0x18000cd45  lea     rax, [rbx+0B8h]
0x18000cd4c  lea     rcx, [rsp+0D40h+var_CD4]
0x18000cd51  movups  xmm0, xmmword ptr [rax]
0x18000cd54  movups  xmm1, xmmword ptr [rax+10h]
0x18000cd58  movups  xmmword ptr [rcx], xmm0
0x18000cd5b  movups  xmm0, xmmword ptr [rax+20h]
0x18000cd5f  movups  xmmword ptr [rcx+10h], xmm1
0x18000cd63  movups  xmm1, xmmword ptr [rax+30h]
0x18000cd67  movups  xmmword ptr [rcx+20h], xmm0
0x18000cd6b  movups  xmm0, xmmword ptr [rax+40h]
0x18000cd6f  movups  xmmword ptr [rcx+30h], xmm1
0x18000cd73  movups  xmm1, xmmword ptr [rax+50h]
0x18000cd77  movups  xmmword ptr [rcx+40h], xmm0
0x18000cd7b  movups  xmm0, xmmword ptr [rax+60h]
0x18000cd7f  movups  xmmword ptr [rcx+50h], xmm1
0x18000cd83  movups  xmm1, xmmword ptr [rax+70h]
0x18000cd87  add     rax, rdx
0x18000cd8a  movups  xmmword ptr [rcx+60h], xmm0
0x18000cd8e  movups  xmmword ptr [rcx+70h], xmm1
0x18000cd92  add     rcx, rdx
0x18000cd95  sub     r8, r13
0x18000cd98  jnz     short loc_18000CD51
0x18000cd9a  movups  xmm0, xmmword ptr [rax]
0x18000cd9d  movups  xmm1, xmmword ptr [rax+10h]
0x18000cda1  movups  xmmword ptr [rcx], xmm0
0x18000cda4  movups  xmm0, xmmword ptr [rax+20h]
0x18000cda8  movups  xmmword ptr [rcx+10h], xmm1
0x18000cdac  movups  xmmword ptr [rcx+20h], xmm0
0x18000cdb0  mov     cl, cs:byte_18004CF34
0x18000cdb6  mov     esi, 0B8h
0x18000cdbb  mov     r14, rbx
0x18000cdbe  test    r13b, cl
0x18000cdc1  jz      short loc_18000CE20
0x18000cdc3  mov     r8, cs:CpTable
0x18000cdca  lea     rdx, aFsminitForProt; "FsmInit for protocol = %x Configuration"...
0x18000cdd1  mov     r9d, [rsi+rbx]
0x18000cdd5  xor     eax, eax
0x18000cdd7  imul    rcx, r15, 0B0h
0x18000cdde  mov     word ptr [rbp+0C40h+var_830], ax
0x18000cde5  mov     r8d, [rcx+r8]
0x18000cde9  lea     rcx, [rbp+0C40h+var_830]
0x18000cdf0  call    FormatRRASErrorString
0x18000cdf5  mov     cl, cs:byte_18004CF34
0x18000cdfb  test    r13b, cl
0x18000cdfe  jz      short loc_18000CE20
0x18000ce00  lea     r8, [rbp+0C40h+var_830]
0x18000ce07  lea     rdx, RasPppTraceInfo
0x18000ce0e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ce15  call    McTemplateU0z_EventWriteTransfer
0x18000ce1a  mov     cl, cs:byte_18004CF34
0x18000ce20  test    dword ptr [rsi+r14], 4000h
0x18000ce28  jz      short loc_18000CE96
0x18000ce2a  cmp     word ptr [rbx+3Ch], 0Eh
0x18000ce2f  jnz     short loc_18000CE96
0x18000ce31  mov     r9d, [rsp+0D40h+var_CD4]
0x18000ce36  bts     r9d, 0Eh
0x18000ce3b  mov     [rsp+0D40h+var_CD4], r9d
0x18000ce40  test    r13b, cl
0x18000ce43  jz      short loc_18000CE96
0x18000ce45  mov     r8, cs:CpTable
0x18000ce4c  lea     rdx, aFsminitForProt_0; "FsmInit for protocol = %x Configuration"...
0x18000ce53  imul    rcx, r15, 0B0h
0x18000ce5a  xor     eax, eax
0x18000ce5c  mov     word ptr [rbp+0C40h+var_830], ax
0x18000ce63  mov     r8d, [rcx+r8]
0x18000ce67  lea     rcx, [rbp+0C40h+var_830]
0x18000ce6e  call    FormatRRASErrorString
0x18000ce73  test    cs:byte_18004CF34, r13b
0x18000ce7a  jz      short loc_18000CE96
0x18000ce7c  lea     r8, [rbp+0C40h+var_830]
0x18000ce83  lea     rdx, RasPppTraceInfo
0x18000ce8a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ce91  call    McTemplateU0z_EventWriteTransfer
0x18000ce96  mov     rcx, [rbx+8]
0x18000ce9a  mov     r8, cs:CpTable
0x18000cea1  imul    rsi, r15, 0B0h
0x18000cea8  movups  xmm0, xmmword ptr [rcx+7B0h]
0x18000ceaf  movdqu  [rbp+0C40h+var_868], xmm0
0x18000ceb7  movups  xmm1, xmmword ptr [rcx+7C0h]
0x18000cebe  movups  xmmword ptr [rbp+0C40h+var_858], xmm1
0x18000cec5  movups  xmm0, xmmword ptr [rcx+7CCh]
0x18000cecc  movups  xmmword ptr [rbp+0C40h+var_858+0Ch], xmm0
0x18000ced3  mov     edx, [rsi+r8]
0x18000ced7  sub     edx, 8021h
0x18000cedd  jz      short loc_18000CEFA
0x18000cedf  cmp     edx, 36h ; '6'
0x18000cee2  jz      short loc_18000CEF1
0x18000cee4  mov     [rbp+0C40h+var_888], 0FFFFFFFFFFFFFFFFh
0x18000ceef  jmp     short loc_18000CF08
0x18000cef1  mov     rax, [rcx+538h]
0x18000cef8  jmp     short loc_18000CF01
0x18000cefa  mov     rax, [rcx+530h]
0x18000cf01  mov     [rbp+0C40h+var_888], rax
0x18000cf08  mov     rax, [rsi+r8+20h]
0x18000cf0d  lea     rcx, [rdi+10h]
0x18000cf11  lea     rdx, [rsp+0D40h+var_D00]
0x18000cf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1b  mov     r14d, eax
0x18000cf1e  test    eax, eax
0x18000cf20  jz      short loc_18000CF88
0x18000cf22  cmp     cs:byte_18004CF33, 0
0x18000cf29  jge     short loc_18000CF78
0x18000cf2b  mov     r8, cs:CpTable
0x18000cf32  lea     rdx, aFsminitForProt_1; "FsmInit for protocol = %x failed with e"...
0x18000cf39  xor     ecx, ecx
0x18000cf3b  mov     r9d, eax
0x18000cf3e  mov     word ptr [rbp+0C40h+var_830], cx
0x18000cf45  lea     rcx, [rbp+0C40h+var_830]
0x18000cf4c  mov     r8d, [rsi+r8]
0x18000cf50  call    FormatRRASErrorString
0x18000cf55  cmp     cs:byte_18004CF33, 0
0x18000cf5c  jge     short loc_18000CF78
0x18000cf5e  lea     r8, [rbp+0C40h+var_830]
0x18000cf65  lea     rdx, RasPppTraceError
0x18000cf6c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cf73  call    McTemplateU0z_EventWriteTransfer
0x18000cf78  mov     [rdi+28h], r14d
0x18000cf7c  mov     dword ptr [rdi+2Ch], 0
0x18000cf83  jmp     loc_18000CB8F
0x18000cf88  test    byte ptr [rbx+38h], 4
0x18000cf8c  jnz     short loc_18000CFD9
0x18000cf8e  mov     rax, cs:CpTable
0x18000cf95  mov     r9d, [rsi+rax]
0x18000cf99  cmp     r9d, 8057h
0x18000cfa0  jz      short loc_18000CFAB
0x18000cfa2  cmp     r9d, 8021h
0x18000cfa9  jnz     short loc_18000CFD9
0x18000cfab  mov     eax, [rbx+24h]
0x18000cfae  imul    eax, cs:dword_18004C9F8
0x18000cfb5  mov     r8d, [rdi+8]
0x18000cfb9  mov     rdx, [rbx+10h]
0x18000cfbd  mov     ecx, [rbx+40h]
0x18000cfc0  mov     [rsp+0D40h+var_D10], eax
0x18000cfc4  mov     [rsp+0D40h+var_D18], 8
0x18000cfcc  mov     [rsp+0D40h+var_D20], 0
0x18000cfd4  call    InsertInTimerQ
0x18000cfd9  mov     edx, r15d
0x18000cfdc  mov     [rdi+30h], r13d
0x18000cfe0  mov     rcx, rbx
0x18000cfe3  call    FsmReset
0x18000cfe8  test    eax, eax
0x18000cfea  jz      short loc_18000CF7C
0x18000cfec  mov     eax, r13d
0x18000cfef  mov     rcx, [rbp+0C40h+var_30]
0x18000cff6  xor     rcx, rsp; StackCookie
0x18000cff9  call    __security_check_cookie
0x18000cffe  lea     r11, [rsp+0D40h+var_20]
0x18000d006  mov     rbx, [r11+40h]
0x18000d00a  mov     rsi, [r11+48h]
0x18000d00e  mov     rsp, r11
0x18000d011  pop     r15
0x18000d013  pop     r14
0x18000d015  pop     r13
0x18000d017  pop     rdi
0x18000d018  pop     rbp
0x18000d019  retn
```
