# FsmInit

- ea: `0x18000cf3c`
- end: `0x18000d447`
- name: `FsmInit`
- size: `1291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012104`
- `0x180016260`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000cf3c`
- `0x18000d450`
- `0x18000f780`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000cfd8`: `FsmInit called for protocol = %x, port = %d`
- `0x18000d1f6`: `FsmInit for protocol = %x Configuration 0x%x `
- `0x18000d278`: `FsmInit for protocol = %x Configuration 0x%x`
- `0x18000d35e`: `FsmInit for protocol = %x failed with error %d`

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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v59) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v59,
      L"FsmInit called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v7);
    if ( (byte_18004DF34 & 1) != 0 )
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
    v14 = &dword_18004DAD0;
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
    v22 = (dword_18004DAD0 & 0x400000) == 0;
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
  v36 = byte_18004DF34;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v37 = *(unsigned int *)(a1 + 184);
    LOWORD(v59) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v59,
      L"FsmInit for protocol = %x Configuration 0x%x ",
      *((unsigned int *)CpTable + 44 * v2),
      v37);
    v36 = byte_18004DF34;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v59);
      v36 = byte_18004DF34;
    }
  }
  if ( (*(_DWORD *)(a1 + 184) & 0x4000) != 0 && *(_WORD *)(a1 + 60) == 14 )
  {
    v50[0] |= 0x4000u;
    if ( (v36 & 1) != 0 )
    {
      LOWORD(v59) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v59,
        L"FsmInit for protocol = %x Configuration 0x%x",
        *((unsigned int *)CpTable + 44 * v2));
      if ( (byte_18004DF34 & 1) != 0 )
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
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v59) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v59,
        L"FsmInit for protocol = %x failed with error %d",
        *(unsigned int *)((char *)CpTable + v39),
        v41);
      if ( byte_18004DF33 < 0 )
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
        dword_18004D9F8 * *(_DWORD *)(a1 + 36));
  }
  v5[12] = 1;
  if ( !(unsigned int)FsmReset(a1, (unsigned int)v2) )
    goto LABEL_37;
  return 1;
}

```

## disassembly

```asm
0x18000cf3c  mov     [rsp-8+arg_10], rbx
0x18000cf41  mov     [rsp-8+arg_18], rsi
0x18000cf46  push    rbp
0x18000cf47  push    rdi
0x18000cf48  push    r13
0x18000cf4a  push    r14
0x18000cf4c  push    r15
0x18000cf4e  lea     rbp, [rsp-0C20h]
0x18000cf56  sub     rsp, 0D20h
0x18000cf5d  mov     rax, cs:__security_cookie
0x18000cf64  xor     rax, rsp
0x18000cf67  mov     [rbp+0C40h+var_30], rax
0x18000cf6e  mov     r15d, edx
0x18000cf71  mov     rbx, rcx
0x18000cf74  xor     eax, eax
0x18000cf76  lea     rcx, [rsp+0D40h+var_D00]; void *
0x18000cf7b  xor     edx, edx; Val
0x18000cf7d  mov     [rsp+0D40h+var_CFC], eax
0x18000cf81  mov     r8d, 4C4h; Size
0x18000cf87  call    memset_0
0x18000cf8c  mov     edx, r15d
0x18000cf8f  mov     rcx, rbx
0x18000cf92  call    GetPointerToCPCB
0x18000cf97  xor     ecx, ecx
0x18000cf99  xor     edx, edx; Val
0x18000cf9b  mov     [rbp+0C40h+var_830], ecx
0x18000cfa1  mov     r8d, 7FCh; Size
0x18000cfa7  lea     rcx, [rbp+0C40h+var_82C]; void *
0x18000cfae  mov     rdi, rax
0x18000cfb1  call    memset_0
0x18000cfb6  test    rdi, rdi
0x18000cfb9  jnz     short loc_18000CFC2
0x18000cfbb  xor     eax, eax
0x18000cfbd  jmp     loc_18000D41B
0x18000cfc2  mov     r13d, 1
0x18000cfc8  test    cs:byte_18004DF34, r13b
0x18000cfcf  jz      short loc_18000D026
0x18000cfd1  mov     r8, cs:CpTable
0x18000cfd8  lea     rdx, aFsminitCalledF; "FsmInit called for protocol = %x, port "...
0x18000cfdf  mov     r9, [rbx+10h]
0x18000cfe3  xor     eax, eax
0x18000cfe5  imul    rcx, r15, 0B0h
0x18000cfec  mov     word ptr [rbp+0C40h+var_830], ax
0x18000cff3  mov     r8d, [rcx+r8]
0x18000cff7  lea     rcx, [rbp+0C40h+var_830]
0x18000cffe  call    FormatRRASErrorString
0x18000d003  test    cs:byte_18004DF34, r13b
0x18000d00a  jz      short loc_18000D026
0x18000d00c  lea     r8, [rbp+0C40h+var_830]
0x18000d013  lea     rdx, RasPppTraceInfo
0x18000d01a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d021  call    McTemplateU0z_EventWriteTransfer
0x18000d026  mov     [rdi+38h], r13d
0x18000d02a  mov     r10d, 8
0x18000d030  mov     dword ptr [rdi+28h], 0
0x18000d037  mov     dword ptr [rdi], 0
0x18000d03d  mov     rcx, [rbx+8]
0x18000d041  mov     rax, [rbx+10h]
0x18000d045  mov     edx, [rbx+38h]
0x18000d048  mov     r8d, edx
0x18000d04b  mov     r9d, [rbx+3Ch]
0x18000d04f  and     r8d, 4
0x18000d053  mov     [rsp+0D40h+var_CF8], rax
0x18000d058  and     edx, r10d
0x18000d05b  lea     rax, CompletionRoutine
0x18000d062  mov     [rsp+0D40h+var_D00], r8d
0x18000d067  mov     [rsp+0D40h+var_CE8], rax
0x18000d06c  lea     rax, [rcx+540h]
0x18000d073  mov     [rsp+0D40h+var_CE0], rax
0x18000d078  mov     [rsp+0D40h+var_CF0], r9d
0x18000d07d  mov     [rsp+0D40h+var_CD8], edx
0x18000d081  mov     eax, [rcx+528h]
0x18000d087  mov     [rbp+0C40h+var_880], eax
0x18000d08d  lea     rax, [rcx+0D8h]
0x18000d094  mov     [rbp+0C40h+var_8A0], rax
0x18000d09b  lea     rax, [rbx+681h]
0x18000d0a2  mov     [rbp+0C40h+var_898], rax
0x18000d0a9  mov     rax, [rcx+28h]
0x18000d0ad  mov     [rbp+0C40h+var_890], rax
0x18000d0b4  mov     rax, [rbx+0A8h]
0x18000d0bb  test    rax, rax
0x18000d0be  jnz     short loc_18000D0C7
0x18000d0c0  mov     rax, [rbx+0A0h]
0x18000d0c7  test    r8d, r8d
0x18000d0ca  mov     [rbp+0C40h+var_878], rax
0x18000d0d1  mov     r8, r10
0x18000d0d4  mov     edx, 80h
0x18000d0d9  jz      loc_18000D171
0x18000d0df  lea     rax, [rsp+0D40h+var_CD4]
0x18000d0e4  lea     rcx, dword_18004DAD0
0x18000d0eb  movups  xmm0, xmmword ptr [rcx]
0x18000d0ee  movups  xmm1, xmmword ptr [rcx+10h]
0x18000d0f2  movups  xmmword ptr [rax], xmm0
0x18000d0f5  movups  xmm0, xmmword ptr [rcx+20h]
0x18000d0f9  movups  xmmword ptr [rax+10h], xmm1
0x18000d0fd  movups  xmm1, xmmword ptr [rcx+30h]
0x18000d101  movups  xmmword ptr [rax+20h], xmm0
0x18000d105  movups  xmm0, xmmword ptr [rcx+40h]
0x18000d109  movups  xmmword ptr [rax+30h], xmm1
0x18000d10d  movups  xmm1, xmmword ptr [rcx+50h]
0x18000d111  movups  xmmword ptr [rax+40h], xmm0
0x18000d115  movups  xmm0, xmmword ptr [rcx+60h]
0x18000d119  movups  xmmword ptr [rax+50h], xmm1
0x18000d11d  movups  xmm1, xmmword ptr [rcx+70h]
0x18000d121  add     rcx, rdx
0x18000d124  movups  xmmword ptr [rax+60h], xmm0
0x18000d128  movups  xmmword ptr [rax+70h], xmm1
0x18000d12c  add     rax, rdx
0x18000d12f  sub     r8, r13
0x18000d132  jnz     short loc_18000D0EB
0x18000d134  test    cs:dword_18004DAD0, 400000h
0x18000d13e  movups  xmm0, xmmword ptr [rcx]
0x18000d141  movups  xmm1, xmmword ptr [rcx+10h]
0x18000d145  movups  xmmword ptr [rax], xmm0
0x18000d148  movups  xmm0, xmmword ptr [rcx+20h]
0x18000d14c  movups  xmmword ptr [rax+10h], xmm1
0x18000d150  movups  xmmword ptr [rax+20h], xmm0
0x18000d154  jz      loc_18000D1DC
0x18000d15a  bt      r9d, 11h
0x18000d15f  jnb     short loc_18000D169
0x18000d161  bts     [rsp+0D40h+var_CD4], 0Eh
0x18000d167  jmp     short loc_18000D1DC
0x18000d169  btr     [rsp+0D40h+var_CD4], 16h
0x18000d16f  jmp     short loc_18000D1DC
0x18000d171  lea     rax, [rbx+0B8h]
0x18000d178  lea     rcx, [rsp+0D40h+var_CD4]
0x18000d17d  movups  xmm0, xmmword ptr [rax]
0x18000d180  movups  xmm1, xmmword ptr [rax+10h]
0x18000d184  movups  xmmword ptr [rcx], xmm0
0x18000d187  movups  xmm0, xmmword ptr [rax+20h]
0x18000d18b  movups  xmmword ptr [rcx+10h], xmm1
0x18000d18f  movups  xmm1, xmmword ptr [rax+30h]
0x18000d193  movups  xmmword ptr [rcx+20h], xmm0
0x18000d197  movups  xmm0, xmmword ptr [rax+40h]
0x18000d19b  movups  xmmword ptr [rcx+30h], xmm1
0x18000d19f  movups  xmm1, xmmword ptr [rax+50h]
0x18000d1a3  movups  xmmword ptr [rcx+40h], xmm0
0x18000d1a7  movups  xmm0, xmmword ptr [rax+60h]
0x18000d1ab  movups  xmmword ptr [rcx+50h], xmm1
0x18000d1af  movups  xmm1, xmmword ptr [rax+70h]
0x18000d1b3  add     rax, rdx
0x18000d1b6  movups  xmmword ptr [rcx+60h], xmm0
0x18000d1ba  movups  xmmword ptr [rcx+70h], xmm1
0x18000d1be  add     rcx, rdx
0x18000d1c1  sub     r8, r13
0x18000d1c4  jnz     short loc_18000D17D
0x18000d1c6  movups  xmm0, xmmword ptr [rax]
0x18000d1c9  movups  xmm1, xmmword ptr [rax+10h]
0x18000d1cd  movups  xmmword ptr [rcx], xmm0
0x18000d1d0  movups  xmm0, xmmword ptr [rax+20h]
0x18000d1d4  movups  xmmword ptr [rcx+10h], xmm1
0x18000d1d8  movups  xmmword ptr [rcx+20h], xmm0
0x18000d1dc  mov     cl, cs:byte_18004DF34
0x18000d1e2  mov     esi, 0B8h
0x18000d1e7  mov     r14, rbx
0x18000d1ea  test    r13b, cl
0x18000d1ed  jz      short loc_18000D24C
0x18000d1ef  mov     r8, cs:CpTable
0x18000d1f6  lea     rdx, aFsminitForProt; "FsmInit for protocol = %x Configuration"...
0x18000d1fd  mov     r9d, [rsi+rbx]
0x18000d201  xor     eax, eax
0x18000d203  imul    rcx, r15, 0B0h
0x18000d20a  mov     word ptr [rbp+0C40h+var_830], ax
0x18000d211  mov     r8d, [rcx+r8]
0x18000d215  lea     rcx, [rbp+0C40h+var_830]
0x18000d21c  call    FormatRRASErrorString
0x18000d221  mov     cl, cs:byte_18004DF34
0x18000d227  test    r13b, cl
0x18000d22a  jz      short loc_18000D24C
0x18000d22c  lea     r8, [rbp+0C40h+var_830]
0x18000d233  lea     rdx, RasPppTraceInfo
0x18000d23a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d241  call    McTemplateU0z_EventWriteTransfer
0x18000d246  mov     cl, cs:byte_18004DF34
0x18000d24c  test    dword ptr [rsi+r14], 4000h
0x18000d254  jz      short loc_18000D2C2
0x18000d256  cmp     word ptr [rbx+3Ch], 0Eh
0x18000d25b  jnz     short loc_18000D2C2
0x18000d25d  mov     r9d, [rsp+0D40h+var_CD4]
0x18000d262  bts     r9d, 0Eh
0x18000d267  mov     [rsp+0D40h+var_CD4], r9d
0x18000d26c  test    r13b, cl
0x18000d26f  jz      short loc_18000D2C2
0x18000d271  mov     r8, cs:CpTable
0x18000d278  lea     rdx, aFsminitForProt_0; "FsmInit for protocol = %x Configuration"...
0x18000d27f  imul    rcx, r15, 0B0h
0x18000d286  xor     eax, eax
0x18000d288  mov     word ptr [rbp+0C40h+var_830], ax
0x18000d28f  mov     r8d, [rcx+r8]
0x18000d293  lea     rcx, [rbp+0C40h+var_830]
0x18000d29a  call    FormatRRASErrorString
0x18000d29f  test    cs:byte_18004DF34, r13b
0x18000d2a6  jz      short loc_18000D2C2
0x18000d2a8  lea     r8, [rbp+0C40h+var_830]
0x18000d2af  lea     rdx, RasPppTraceInfo
0x18000d2b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d2bd  call    McTemplateU0z_EventWriteTransfer
0x18000d2c2  mov     rcx, [rbx+8]
0x18000d2c6  mov     r8, cs:CpTable
0x18000d2cd  imul    rsi, r15, 0B0h
0x18000d2d4  movups  xmm0, xmmword ptr [rcx+7B0h]
0x18000d2db  movdqu  [rbp+0C40h+var_868], xmm0
0x18000d2e3  movups  xmm1, xmmword ptr [rcx+7C0h]
0x18000d2ea  movups  xmmword ptr [rbp+0C40h+var_858], xmm1
0x18000d2f1  movups  xmm0, xmmword ptr [rcx+7CCh]
0x18000d2f8  movups  xmmword ptr [rbp+0C40h+var_858+0Ch], xmm0
0x18000d2ff  mov     edx, [rsi+r8]
0x18000d303  sub     edx, 8021h
0x18000d309  jz      short loc_18000D326
0x18000d30b  cmp     edx, 36h ; '6'
0x18000d30e  jz      short loc_18000D31D
0x18000d310  mov     [rbp+0C40h+var_888], 0FFFFFFFFFFFFFFFFh
0x18000d31b  jmp     short loc_18000D334
0x18000d31d  mov     rax, [rcx+538h]
0x18000d324  jmp     short loc_18000D32D
0x18000d326  mov     rax, [rcx+530h]
0x18000d32d  mov     [rbp+0C40h+var_888], rax
0x18000d334  mov     rax, [rsi+r8+20h]
0x18000d339  lea     rcx, [rdi+10h]
0x18000d33d  lea     rdx, [rsp+0D40h+var_D00]
0x18000d342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d347  mov     r14d, eax
0x18000d34a  test    eax, eax
0x18000d34c  jz      short loc_18000D3B4
0x18000d34e  cmp     cs:byte_18004DF33, 0
0x18000d355  jge     short loc_18000D3A4
0x18000d357  mov     r8, cs:CpTable
0x18000d35e  lea     rdx, aFsminitForProt_1; "FsmInit for protocol = %x failed with e"...
0x18000d365  xor     ecx, ecx
0x18000d367  mov     r9d, eax
0x18000d36a  mov     word ptr [rbp+0C40h+var_830], cx
0x18000d371  lea     rcx, [rbp+0C40h+var_830]
0x18000d378  mov     r8d, [rsi+r8]
0x18000d37c  call    FormatRRASErrorString
0x18000d381  cmp     cs:byte_18004DF33, 0
0x18000d388  jge     short loc_18000D3A4
0x18000d38a  lea     r8, [rbp+0C40h+var_830]
0x18000d391  lea     rdx, RasPppTraceError
0x18000d398  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d39f  call    McTemplateU0z_EventWriteTransfer
0x18000d3a4  mov     [rdi+28h], r14d
0x18000d3a8  mov     dword ptr [rdi+2Ch], 0
0x18000d3af  jmp     loc_18000CFBB
0x18000d3b4  test    byte ptr [rbx+38h], 4
0x18000d3b8  jnz     short loc_18000D405
0x18000d3ba  mov     rax, cs:CpTable
0x18000d3c1  mov     r9d, [rsi+rax]
0x18000d3c5  cmp     r9d, 8057h
0x18000d3cc  jz      short loc_18000D3D7
0x18000d3ce  cmp     r9d, 8021h
0x18000d3d5  jnz     short loc_18000D405
0x18000d3d7  mov     eax, [rbx+24h]
0x18000d3da  imul    eax, cs:dword_18004D9F8
0x18000d3e1  mov     r8d, [rdi+8]
0x18000d3e5  mov     rdx, [rbx+10h]
0x18000d3e9  mov     ecx, [rbx+40h]
0x18000d3ec  mov     [rsp+0D40h+var_D10], eax
0x18000d3f0  mov     [rsp+0D40h+var_D18], 8
0x18000d3f8  mov     [rsp+0D40h+var_D20], 0
0x18000d400  call    InsertInTimerQ
0x18000d405  mov     edx, r15d
0x18000d408  mov     [rdi+30h], r13d
0x18000d40c  mov     rcx, rbx
0x18000d40f  call    FsmReset
0x18000d414  test    eax, eax
0x18000d416  jz      short loc_18000D3A8
0x18000d418  mov     eax, r13d
0x18000d41b  mov     rcx, [rbp+0C40h+var_30]
0x18000d422  xor     rcx, rsp; StackCookie
0x18000d425  call    __security_check_cookie
0x18000d42a  lea     r11, [rsp+0D40h+var_20]
0x18000d432  mov     rbx, [r11+40h]
0x18000d436  mov     rsi, [r11+48h]
0x18000d43a  mov     rsp, r11
0x18000d43d  pop     r15
0x18000d43f  pop     r14
0x18000d441  pop     r13
0x18000d443  pop     rdi
0x18000d444  pop     rbp
0x18000d445  retn
```
