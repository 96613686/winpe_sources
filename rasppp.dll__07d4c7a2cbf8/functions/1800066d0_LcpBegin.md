# LcpBegin

- ea: `0x1800066d0`
- end: `0x180006d65`
- name: `LcpBegin`
- size: `1685`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800066d0`
- `0x180010cfc`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000673c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000673c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000674e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000674e`

## string_xrefs

- `0x180006779`: `PPP ConfigMask 0x%x `
- `0x180006849`: `PPP ConfigMask = %x`
- `0x180006c3c`: `PPP ConfigMask = %x`
- `0x18000688e`: `Removing NegotiateMultilink due to registry override`

## pseudocode

```c
DWORD __fastcall LcpBegin(LPVOID *a1, __int64 a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v7; // r8
  unsigned int *v8; // r15
  __int64 v9; // rdx
  _OWORD *v10; // rax
  _OWORD *v11; // rcx
  __int64 v12; // r8
  __int128 v13; // xmm1
  bool v14; // zf
  char v15; // al
  __int64 v16; // rcx
  int v17; // edi
  int v18; // r14d
  int v19; // edi
  __int16 v20; // ax
  int v21; // eax
  size_t v22; // r8
  __int64 v23; // rax
  int v24; // eax
  int v25; // ecx
  int v26; // r12d
  unsigned int v27; // eax
  int v28; // eax
  __int128 v29; // [rsp+28h] [rbp-D8h] BYREF
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v31[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v30 = 0;
  v29 = 0;
  memset_0(v31, 0, sizeof(v31));
  v4 = HeapAlloc(hHeap, 8u, 0x5D8u);
  *a1 = v4;
  v5 = v4;
  if ( !v4 )
    return GetLastError();
  *((_DWORD *)v4 + 2) = *(_DWORD *)a2;
  *v4 = *(_QWORD *)(a2 + 8);
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v7 = *(unsigned int *)(a2 + 44);
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"PPP ConfigMask 0x%x ", v7);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v30);
  }
  v8 = (unsigned int *)(v5 + 3);
  v9 = 8;
  v10 = v5 + 3;
  v11 = (_OWORD *)(a2 + 44);
  v12 = 128;
  do
  {
    *v10 = *v11;
    v10[1] = v11[1];
    v10[2] = v11[2];
    v10[3] = v11[3];
    v10[4] = v11[4];
    v10[5] = v11[5];
    v10[6] = v11[6];
    v13 = v11[7];
    v11 += 8;
    v10[7] = v13;
    v10 += 8;
    --v9;
  }
  while ( v9 );
  *v10 = *v11;
  v10[1] = v11[1];
  v10[2] = v11[2];
  v14 = *(_DWORD *)(a2 + 1152) == 2;
  v5[2] = 2;
  *((_DWORD *)v5 + 3) = v14;
  v15 = byte_18004CF34;
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"PPP ConfigMask = %x", *v8);
    v15 = byte_18004CF34;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v30);
      v15 = byte_18004CF34;
    }
  }
  if ( dword_18004CA1C )
  {
    if ( (v15 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceInfo,
        L"Removing NegotiateMultilink due to registry override");
    *v8 &= ~0x400u;
  }
  v16 = *v5;
  *((_OWORD *)v5 + 70) = xmmword_180036AE0;
  *((_OWORD *)v5 + 71) = xmmword_180036AF0;
  *((_OWORD *)v5 + 72) = xmmword_180036B00;
  *((_OWORD *)v5 + 73) = xmmword_180036B10;
  *((_OWORD *)v5 + 74) = xmmword_180036B20;
  v5[150] = 0;
  *(_OWORD *)(v5 + 165) = xmmword_180036AE0;
  *(_OWORD *)(v5 + 167) = xmmword_180036AF0;
  *(_OWORD *)(v5 + 169) = xmmword_180036B00;
  *(_OWORD *)(v5 + 171) = xmmword_180036B10;
  *(_OWORD *)(v5 + 173) = xmmword_180036B20;
  v5[175] = 0;
  v17 = (*((__int64 (__fastcall **)(__int64, __int128 *, __int64))&xmmword_18004C480 + 1))(v16, &v29, v12);
  if ( v17 )
    goto LABEL_56;
  v18 = 422;
  *((_DWORD *)v5 + 274) = 422;
  *((_DWORD *)v5 + 324) = 422;
  *((_DWORD *)v5 + 281) = v29;
  *((_DWORD *)v5 + 331) = v29;
  *((_DWORD *)v5 + 280) = 32;
  v19 = 32;
  *((_DWORD *)v5 + 330) = 32;
  if ( (_DWORD)v29 != 1500 )
  {
    v19 = 34;
    *((_DWORD *)v5 + 280) = 34;
    *((_DWORD *)v5 + 330) = 34;
  }
  v20 = WORD4(v29);
  if ( (WORD4(v29) & 0x200) != 0 )
  {
    v19 |= 0x100u;
    *((_DWORD *)v5 + 290) = 1;
    *((_DWORD *)v5 + 280) = v19;
    *((_DWORD *)v5 + 330) = v19;
    *((_DWORD *)v5 + 340) = 1;
    v20 = WORD4(v29);
  }
  if ( (v20 & 0x400) != 0 )
  {
    v19 |= 0x80u;
    *((_DWORD *)v5 + 289) = 1;
    *((_DWORD *)v5 + 280) = v19;
    *((_DWORD *)v5 + 330) = v19;
    *((_DWORD *)v5 + 339) = 1;
    v20 = WORD4(v29);
  }
  if ( (v20 & 0x800) != 0 )
  {
    v21 = HIDWORD(v29);
    v19 |= 4u;
    *((_DWORD *)v5 + 280) = v19;
    *((_DWORD *)v5 + 282) = v21;
  }
  if ( (*v8 & 0x400) != 0 )
  {
    v22 = 7;
    if ( byte_18004CF10 == 1 )
      v22 = 21;
    *((_DWORD *)v5 + 300) = v22;
    memcpy_0(v5 + 147, &byte_18004CF10, v22);
    if ( (*(_DWORD *)(a2 + 16) & 0x10000) != 0 && !*(_DWORD *)a2 )
    {
      v23 = (unsigned int)(*((_DWORD *)v5 + 300) - 1);
      *((_BYTE *)v5 + v23 + 1176) += ++BCount;
    }
    *((_DWORD *)v5 + 280) |= 0x80000u;
    *((_DWORD *)v5 + 330) |= 0x80000u;
    v24 = DWORD1(v29);
    v19 = *((_DWORD *)v5 + 280) | 0x20000;
    v25 = *((_DWORD *)v5 + 330) | 0x20000;
    *((_DWORD *)v5 + 280) = v19;
    *((_DWORD *)v5 + 330) = v25;
    *((_DWORD *)v5 + 292) = v24;
    *((_DWORD *)v5 + 342) = 1500;
    if ( (BYTE8(v29) & 0x20) != 0 )
    {
      *((_DWORD *)v5 + 293) = 1;
      v19 |= 0x40000u;
      *((_DWORD *)v5 + 343) = 1;
      *((_DWORD *)v5 + 280) = v19;
      *((_DWORD *)v5 + 330) = v25 | 0x40000;
    }
    *((_DWORD *)v5 + 274) |= 0xE0000u;
    *((_DWORD *)v5 + 324) |= 0xE0000u;
    v26 = *((_DWORD *)v5 + 324);
    v18 = *((_DWORD *)v5 + 274);
  }
  else
  {
    v26 = 422;
  }
  if ( !*(_DWORD *)(a2 + 40) && (unsigned int)GetCpIndexFromProtocol(49193) != -1 )
  {
    if ( (*v8 & 0x200) != 0 )
    {
      *((_DWORD *)v5 + 291) = 6;
      *((_DWORD *)v5 + 280) = v19 | 0x2000;
    }
    *((_DWORD *)v5 + 274) = v18 | 0x2000;
    *((_DWORD *)v5 + 324) = v26 | 0x2000;
  }
  v27 = *v8;
  if ( (*v8 & 0x10000) != 0 )
  {
    *((_DWORD *)v5 + 275) |= 8u;
    *((_DWORD *)v5 + 325) |= 8u;
  }
  if ( (v27 & 0x20000) != 0 )
  {
    *((_DWORD *)v5 + 325) |= 4u;
    *((_DWORD *)v5 + 275) |= 4u;
  }
  if ( (v27 & 0x8000) != 0 )
  {
    *((_DWORD *)v5 + 325) |= 1u;
    *((_DWORD *)v5 + 275) |= 1u;
  }
  if ( (v27 & 0x800000) != 0 )
  {
    *((_DWORD *)v5 + 275) |= 2u;
    *((_DWORD *)v5 + 325) |= 2u;
  }
  if ( (v27 & 0x400000) != 0 )
  {
    *((_DWORD *)v5 + 275) = 0;
    *((_DWORD *)v5 + 325) = 0;
  }
  v28 = v27 & 0x4000;
  if ( !v28 || *((_DWORD *)v5 + 3) )
  {
    if ( !*((_DWORD *)v5 + 275) && !v28 && (*((_DWORD *)v5 + 2) || *((_DWORD *)v5 + 3)) )
    {
      v17 = 918;
LABEL_56:
      HeapFree(hHeap, 0, *a1);
      return v17;
    }
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"PPP ConfigMask = %x", *((unsigned int *)v5 + 6));
      if ( (byte_18004CF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v30);
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(&v30, L"APs available = %x", *((unsigned int *)v5 + 275));
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v30);
        }
      }
    }
    if ( *((_DWORD *)v5 + 275) && (*((_DWORD *)v5 + 2) || *((_DWORD *)v5 + 3) && (v5[3] & 0x800) != 0) )
    {
      *((_DWORD *)v5 + 280) |= 8u;
      *((_DWORD *)v5 + 274) |= 8u;
      *((_DWORD *)v5 + 306) = 0;
      v5[154] = 0;
    }
    if ( !*((_DWORD *)v5 + 2) && (*((_DWORD *)v5 + 325) & 0xFFFFFFFC) == 0 )
    {
      *((_DWORD *)v5 + 324) |= 8u;
      *((_DWORD *)v5 + 330) |= 8u;
      *((_DWORD *)v5 + 356) = 0;
      v5[179] = 0;
    }
    if ( *((_DWORD *)v5 + 325) )
    {
      *((_DWORD *)v5 + 324) |= 8u;
      *((_DWORD *)v5 + 356) = 0;
      v5[179] = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800066d0  mov     [rsp-8+arg_10], rbx
0x1800066d5  push    rbp
0x1800066d6  push    rsi
0x1800066d7  push    rdi
0x1800066d8  push    r12
0x1800066da  push    r13
0x1800066dc  push    r14
0x1800066de  push    r15
0x1800066e0  lea     rbp, [rsp-750h]
0x1800066e8  sub     rsp, 850h
0x1800066ef  mov     rax, cs:__security_cookie
0x1800066f6  xor     rax, rsp
0x1800066f9  mov     [rbp+780h+var_40], rax
0x180006700  mov     rsi, rdx
0x180006703  mov     r13, rcx
0x180006706  xorps   xmm0, xmm0
0x180006709  lea     rcx, [rsp+880h+var_83C]; void *
0x18000670e  xor     r12d, r12d
0x180006711  xor     edx, edx; Val
0x180006713  mov     r8d, 7FCh; Size
0x180006719  mov     [rsp+880h+var_840], r12d
0x18000671e  movups  [rsp+880h+var_858], xmm0
0x180006723  call    memset_0
0x180006728  mov     rcx, cs:hHeap; hHeap
0x18000672f  lea     edi, [r12+8]
0x180006734  mov     edx, edi; dwFlags
0x180006736  mov     r8d, 5D8h; dwBytes
0x18000673c  call    cs:__imp_HeapAlloc
0x180006742  mov     [r13+0], rax
0x180006746  mov     rbx, rax
0x180006749  test    rax, rax
0x18000674c  jnz     short loc_180006759
0x18000674e  call    cs:__imp_GetLastError
0x180006754  jmp     loc_180006D3B
0x180006759  mov     eax, [rsi]
0x18000675b  lea     r14, RasPppTraceInfo
0x180006762  mov     [rbx+8], eax
0x180006765  mov     rax, [rsi+8]
0x180006769  mov     [rbx], rax
0x18000676c  test    cs:byte_18004CF34, 1
0x180006773  jz      short loc_1800067AD
0x180006775  mov     r8d, [rsi+2Ch]
0x180006779  lea     rdx, aPppConfigmask0; "PPP ConfigMask 0x%x "
0x180006780  lea     rcx, [rsp+880h+var_840]
0x180006785  mov     word ptr [rsp+880h+var_840], r12w
0x18000678b  call    FormatRRASErrorString
0x180006790  test    cs:byte_18004CF34, 1
0x180006797  jz      short loc_1800067AD
0x180006799  lea     r8, [rsp+880h+var_840]
0x18000679e  mov     rdx, r14
0x1800067a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800067a8  call    McTemplateU0z_EventWriteTransfer
0x1800067ad  lea     r15, [rbx+18h]
0x1800067b1  mov     rdx, rdi
0x1800067b4  mov     rax, r15
0x1800067b7  lea     rcx, [rsi+2Ch]
0x1800067bb  mov     r8d, 80h
0x1800067c1  movups  xmm0, xmmword ptr [rcx]
0x1800067c4  movups  xmmword ptr [rax], xmm0
0x1800067c7  movups  xmm1, xmmword ptr [rcx+10h]
0x1800067cb  movups  xmmword ptr [rax+10h], xmm1
0x1800067cf  movups  xmm0, xmmword ptr [rcx+20h]
0x1800067d3  movups  xmmword ptr [rax+20h], xmm0
0x1800067d7  movups  xmm1, xmmword ptr [rcx+30h]
0x1800067db  movups  xmmword ptr [rax+30h], xmm1
0x1800067df  movups  xmm0, xmmword ptr [rcx+40h]
0x1800067e3  movups  xmmword ptr [rax+40h], xmm0
0x1800067e7  movups  xmm1, xmmword ptr [rcx+50h]
0x1800067eb  movups  xmmword ptr [rax+50h], xmm1
0x1800067ef  movups  xmm0, xmmword ptr [rcx+60h]
0x1800067f3  movups  xmmword ptr [rax+60h], xmm0
0x1800067f7  movups  xmm1, xmmword ptr [rcx+70h]
0x1800067fb  add     rcx, r8
0x1800067fe  movups  xmmword ptr [rax+70h], xmm1
0x180006802  add     rax, r8
0x180006805  sub     rdx, 1
0x180006809  jnz     short loc_1800067C1
0x18000680b  movups  xmm0, xmmword ptr [rcx]
0x18000680e  movups  xmmword ptr [rax], xmm0
0x180006811  movups  xmm1, xmmword ptr [rcx+10h]
0x180006815  movups  xmmword ptr [rax+10h], xmm1
0x180006819  movups  xmm0, xmmword ptr [rcx+20h]
0x18000681d  movups  xmmword ptr [rax+20h], xmm0
0x180006821  cmp     dword ptr [rsi+480h], 2
0x180006828  mov     eax, r12d
0x18000682b  mov     qword ptr [rbx+10h], 2
0x180006833  setz    al
0x180006836  mov     [rbx+0Ch], eax
0x180006839  mov     al, cs:byte_18004CF34
0x18000683f  test    al, 1
0x180006841  jz      short loc_180006881
0x180006843  mov     word ptr [rsp+880h+var_840], r12w
0x180006849  lea     rdx, aPppConfigmaskX; "PPP ConfigMask = %x"
0x180006850  mov     r8d, [r15]
0x180006853  lea     rcx, [rsp+880h+var_840]
0x180006858  call    FormatRRASErrorString
0x18000685d  mov     al, cs:byte_18004CF34
0x180006863  test    al, 1
0x180006865  jz      short loc_180006881
0x180006867  lea     r8, [rsp+880h+var_840]
0x18000686c  mov     rdx, r14
0x18000686f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006876  call    McTemplateU0z_EventWriteTransfer
0x18000687b  mov     al, cs:byte_18004CF34
0x180006881  cmp     cs:dword_18004CA1C, r12d
0x180006888  jz      short loc_1800068A9
0x18000688a  test    al, 1
0x18000688c  jz      short loc_1800068A4
0x18000688e  lea     r8, aRemovingNegoti; "Removing NegotiateMultilink due to regi"...
0x180006895  mov     rdx, r14
0x180006898  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000689f  call    McTemplateU0z_EventWriteTransfer
0x1800068a4  btr     dword ptr [r15], 0Ah
0x1800068a9  movaps  xmm0, cs:xmmword_180036AE0
0x1800068b0  lea     rdx, [rsp+880h+var_858]
0x1800068b5  mov     rcx, [rbx]
0x1800068b8  movups  xmmword ptr [rbx+460h], xmm0
0x1800068bf  movaps  xmm1, cs:xmmword_180036AF0
0x1800068c6  movups  xmmword ptr [rbx+470h], xmm1
0x1800068cd  movaps  xmm0, cs:xmmword_180036B00
0x1800068d4  movups  xmmword ptr [rbx+480h], xmm0
0x1800068db  movaps  xmm1, cs:xmmword_180036B10
0x1800068e2  movups  xmmword ptr [rbx+490h], xmm1
0x1800068e9  movaps  xmm0, cs:xmmword_180036B20
0x1800068f0  movups  xmmword ptr [rbx+4A0h], xmm0
0x1800068f7  movsd   xmm1, cs:qword_180036B30
0x1800068ff  movsd   qword ptr [rbx+4B0h], xmm1
0x180006907  movaps  xmm0, cs:xmmword_180036AE0
0x18000690e  movups  xmmword ptr [rbx+528h], xmm0
0x180006915  movaps  xmm1, cs:xmmword_180036AF0
0x18000691c  movups  xmmword ptr [rbx+538h], xmm1
0x180006923  movaps  xmm0, cs:xmmword_180036B00
0x18000692a  movups  xmmword ptr [rbx+548h], xmm0
0x180006931  movaps  xmm1, cs:xmmword_180036B10
0x180006938  movups  xmmword ptr [rbx+558h], xmm1
0x18000693f  movaps  xmm0, cs:xmmword_180036B20
0x180006946  movups  xmmword ptr [rbx+568h], xmm0
0x18000694d  movsd   xmm1, cs:qword_180036B30
0x180006955  movsd   qword ptr [rbx+578h], xmm1
0x18000695d  mov     rax, qword ptr cs:xmmword_18004C480+8
0x180006964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006969  mov     edi, eax
0x18000696b  test    eax, eax
0x18000696d  jnz     loc_180006C0F
0x180006973  mov     r14d, 1A6h
0x180006979  mov     [rbx+448h], r14d
0x180006980  mov     [rbx+510h], r14d
0x180006987  mov     eax, dword ptr [rsp+880h+var_858]
0x18000698b  mov     [rbx+464h], eax
0x180006991  mov     eax, dword ptr [rsp+880h+var_858]
0x180006995  mov     [rbx+52Ch], eax
0x18000699b  lea     eax, [rdi+20h]
0x18000699e  mov     [rbx+460h], eax
0x1800069a4  mov     edi, eax
0x1800069a6  mov     [rbx+528h], eax
0x1800069ac  cmp     dword ptr [rsp+880h+var_858], 5DCh
0x1800069b4  jz      short loc_1800069C5
0x1800069b6  lea     edi, [rax+2]
0x1800069b9  mov     [rbx+460h], edi
0x1800069bf  mov     [rbx+528h], edi
0x1800069c5  mov     eax, dword ptr [rsp+880h+var_858+8]
0x1800069c9  mov     edx, 1
0x1800069ce  bt      eax, 9
0x1800069d2  jnb     short loc_1800069F4
0x1800069d4  bts     edi, 8
0x1800069d8  mov     [rbx+488h], edx
0x1800069de  mov     [rbx+460h], edi
0x1800069e4  mov     [rbx+528h], edi
0x1800069ea  mov     [rbx+550h], edx
0x1800069f0  mov     eax, dword ptr [rsp+880h+var_858+8]
0x1800069f4  mov     ecx, 400h
0x1800069f9  test    ecx, eax
0x1800069fb  jz      short loc_180006A1D
0x1800069fd  bts     edi, 7
0x180006a01  mov     [rbx+484h], edx
0x180006a07  mov     [rbx+460h], edi
0x180006a0d  mov     [rbx+528h], edi
0x180006a13  mov     [rbx+54Ch], edx
0x180006a19  mov     eax, dword ptr [rsp+880h+var_858+8]
0x180006a1d  bt      eax, 0Bh
0x180006a21  jnb     short loc_180006A36
0x180006a23  mov     eax, dword ptr [rsp+880h+var_858+0Ch]
0x180006a27  or      edi, 4
0x180006a2a  mov     [rbx+460h], edi
0x180006a30  mov     [rbx+468h], eax
0x180006a36  test    [r15], ecx
0x180006a39  jz      loc_180006B31
0x180006a3f  cmp     cs:byte_18004CF10, dl
0x180006a45  mov     ecx, 15h
0x180006a4a  lea     rdx, byte_18004CF10; Src
0x180006a51  lea     r8d, [rcx-0Eh]
0x180006a55  cmovz   r8d, ecx; Size
0x180006a59  lea     rcx, [rbx+498h]; void *
0x180006a60  mov     [rbx+4B0h], r8d
0x180006a67  call    memcpy_0
0x180006a6c  test    dword ptr [rsi+10h], 10000h
0x180006a73  jz      short loc_180006A97
0x180006a75  cmp     [rsi], r12d
0x180006a78  jnz     short loc_180006A97
0x180006a7a  mov     eax, [rbx+4B0h]
0x180006a80  mov     dl, cs:BCount
0x180006a86  dec     eax
0x180006a88  inc     dl
0x180006a8a  mov     cs:BCount, dl
0x180006a90  add     [rax+rbx+498h], dl
0x180006a97  mov     eax, 80000h
0x180006a9c  mov     r8d, 20000h
0x180006aa2  or      [rbx+460h], eax
0x180006aa8  or      [rbx+528h], eax
0x180006aae  mov     eax, dword ptr [rsp+880h+var_858+4]
0x180006ab2  mov     edi, [rbx+460h]
0x180006ab8  mov     ecx, [rbx+528h]
0x180006abe  or      edi, r8d
0x180006ac1  or      ecx, r8d
0x180006ac4  mov     [rbx+460h], edi
0x180006aca  mov     [rbx+528h], ecx
0x180006ad0  mov     [rbx+490h], eax
0x180006ad6  mov     dword ptr [rbx+558h], 5DCh
0x180006ae0  test    byte ptr [rsp+880h+var_858+8], 20h
0x180006ae5  jz      short loc_180006B10
0x180006ae7  mov     eax, 40000h
0x180006aec  mov     dword ptr [rbx+494h], 1
0x180006af6  or      edi, eax
0x180006af8  mov     dword ptr [rbx+55Ch], 1
0x180006b02  or      ecx, eax
0x180006b04  mov     [rbx+460h], edi
0x180006b0a  mov     [rbx+528h], ecx
0x180006b10  mov     eax, 0E0000h
0x180006b15  or      [rbx+448h], eax
0x180006b1b  or      [rbx+510h], eax
0x180006b21  mov     r12d, [rbx+510h]
0x180006b28  mov     r14d, [rbx+448h]
0x180006b2f  jmp     short loc_180006B34
0x180006b31  mov     r12d, r14d
0x180006b34  cmp     dword ptr [rsi+28h], 0
0x180006b38  jnz     short loc_180006B7D
0x180006b3a  mov     ecx, 0C029h
0x180006b3f  call    GetCpIndexFromProtocol
0x180006b44  cmp     eax, 0FFFFFFFFh
0x180006b47  jz      short loc_180006B7D
0x180006b49  test    dword ptr [r15], 200h
0x180006b50  mov     eax, 2000h
0x180006b55  jz      short loc_180006B69
0x180006b57  or      edi, eax
0x180006b59  mov     dword ptr [rbx+48Ch], 6
0x180006b63  mov     [rbx+460h], edi
0x180006b69  or      r14d, eax
0x180006b6c  or      r12d, eax
0x180006b6f  mov     [rbx+448h], r14d
0x180006b76  mov     [rbx+510h], r12d
0x180006b7d  mov     eax, [r15]
0x180006b80  bt      eax, 10h
0x180006b84  jnb     short loc_180006B94
0x180006b86  or      dword ptr [rbx+44Ch], 8
0x180006b8d  or      dword ptr [rbx+514h], 8
0x180006b94  bt      eax, 11h
0x180006b98  jnb     short loc_180006BA8
0x180006b9a  or      dword ptr [rbx+514h], 4
0x180006ba1  or      dword ptr [rbx+44Ch], 4
0x180006ba8  bt      eax, 0Fh
0x180006bac  jnb     short loc_180006BBC
0x180006bae  or      dword ptr [rbx+514h], 1
0x180006bb5  or      dword ptr [rbx+44Ch], 1
0x180006bbc  bt      eax, 17h
0x180006bc0  jnb     short loc_180006BD0
0x180006bc2  or      dword ptr [rbx+44Ch], 2
0x180006bc9  or      dword ptr [rbx+514h], 2
0x180006bd0  xor     edi, edi
0x180006bd2  bt      eax, 16h
0x180006bd6  jnb     short loc_180006BE4
0x180006bd8  mov     [rbx+44Ch], edi
0x180006bde  mov     [rbx+514h], edi
0x180006be4  and     eax, 4000h
0x180006be9  jz      short loc_180006BF4
0x180006beb  cmp     [rbx+0Ch], edi
0x180006bee  jz      loc_180006D39
0x180006bf4  cmp     [rbx+44Ch], edi
0x180006bfa  jnz     short loc_180006C29
0x180006bfc  test    eax, eax
0x180006bfe  jnz     short loc_180006C29
0x180006c00  cmp     [rbx+8], edi
0x180006c03  jnz     short loc_180006C0A
0x180006c05  cmp     [rbx+0Ch], edi
0x180006c08  jz      short loc_180006C29
0x180006c0a  mov     edi, 396h
0x180006c0f  mov     r8, [r13+0]; lpMem
0x180006c13  xor     edx, edx; dwFlags
0x180006c15  mov     rcx, cs:hHeap; hHeap
0x180006c1c  call    cs:__imp_HeapFree
0x180006c22  mov     eax, edi
0x180006c24  jmp     loc_180006D3B
0x180006c29  mov     al, cs:byte_18004CF34
0x180006c2f  test    al, 1
0x180006c31  jz      loc_180006CBB
0x180006c37  mov     word ptr [rsp+880h+var_840], di
0x180006c3c  lea     rdx, aPppConfigmaskX; "PPP ConfigMask = %x"
0x180006c43  mov     r8d, [rbx+18h]
0x180006c47  lea     rcx, [rsp+880h+var_840]
0x180006c4c  call    FormatRRASErrorString
0x180006c51  mov     al, cs:byte_18004CF34
  ... truncated ...
```
