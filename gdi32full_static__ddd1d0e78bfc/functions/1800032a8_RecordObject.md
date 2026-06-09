# RecordObject

- ea: `0x1800032a8`
- end: `0x18000387f`
- name: `RecordObject`
- size: `1495`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800031c8`
- `0x180083a78`
- `0x180083e98`

## callees

- `0x1800032a8`
- `0x180003888`
- `0x1800039f0`
- `0x180004c00`
- `0x1800200a0`
- `0x18002841c`
- `0x18002cb60`
- `0x18007d5a8`
- `0x18007f800`
- `0x1800836f0`
- `0x18008406c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000348d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000374f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000381d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000348d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000374f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000381d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003474`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003474`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d0`
- `GDI32!DeleteDC` at `0x1800037ea`
- `GDI32!DeleteDC` at `0x1800037ea`
- `GDI32!GetRegionData` at `0x180003803`
- `GDI32!GetRegionData` at `0x18000383d`
- `GDI32!GetRegionData` at `0x180003803`
- `GDI32!GetRegionData` at `0x18000383d`
- `GDI32!GdiSetLastError` at `0x180003389`
- `GDI32!GdiSetLastError` at `0x180003389`
- `win32u!NtGdiGetObjectBitmapHandle` at `0x180003688`
- `win32u!NtGdiGetObjectBitmapHandle` at `0x180003688`
- `win32u!NtGdiMonoBitmap` at `0x1800036ba`
- `win32u!NtGdiMonoBitmap` at `0x1800036ba`

## pseudocode

```c
__int64 __fastcall RecordObject(__int64 a1, HRGN a2)
{
  HDC CompatibleDC; // r15
  unsigned int v3; // ebx
  int v6; // eax
  unsigned __int16 v7; // r12
  int v8; // edi
  HBITMAP *p_hbm; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  unsigned __int16 *v16; // rdi
  int v17; // r8d
  DWORD v18; // r10d
  unsigned __int16 v19; // r13
  unsigned __int16 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // r9
  unsigned __int16 v24; // cx
  struct _RGNDATA *v25; // rcx
  int LogPalette; // eax
  HBITMAP ObjectBitmapHandle; // rax
  HBITMAP v28; // rbx
  __int16 v29; // si
  __int64 v30; // r13
  unsigned int v31; // ebx
  char *v32; // rax
  void *v33; // r12
  HBITMAP v34; // rdx
  DWORD RegionData; // eax
  DWORD v36; // edi
  struct _RGNDATA *v37; // rax
  struct _RGNDATA *v38; // rbx
  UINT usage; // [rsp+40h] [rbp-59h] BYREF
  int v40; // [rsp+44h] [rbp-55h] BYREF
  _BYTE Size[6]; // [rsp+48h] [rbp-51h] BYREF
  __int16 Size_6; // [rsp+4Eh] [rbp-4Bh]
  int v43; // [rsp+50h] [rbp-49h] BYREF
  HBITMAP hbm; // [rsp+58h] [rbp-41h] BYREF
  __int16 v45; // [rsp+60h] [rbp-39h]
  __int128 pv; // [rsp+68h] [rbp-31h] BYREF
  __int128 v47; // [rsp+78h] [rbp-21h] BYREF
  __int128 v48; // [rsp+88h] [rbp-11h]
  __int128 v49; // [rsp+98h] [rbp-1h]
  __int16 v50; // [rsp+A8h] [rbp+Fh]

  CompatibleDC = 0;
  v3 = (unsigned int)a2 & 0x7F0000;
  v40 = 0;
  usage = 0;
  if ( ((unsigned int)a2 & 0x7F0000) != 0x100000 && v3 != 3145728 && v3 != 655360 && v3 != 0x40000 && v3 != 0x80000 )
  {
    GdiSetLastError(6);
    return 0xFFFF;
  }
  v6 = AddObjectToDCTable(a1, a2, &v40, 1);
  v7 = -1;
  v8 = v6;
  if ( v6 == -1 )
    return 0xFFFF;
  if ( v6 != 1 )
  {
    if ( v3 != 0x40000 )
    {
      if ( !(unsigned int)AddDCToObjectMetaList16(a1, a2) )
        return 0xFFFF;
      if ( v3 == 0x100000 )
      {
        pv = 0;
        if ( GetObjectA(a2, 16, &pv) )
        {
          if ( (unsigned int)pv > 2 )
          {
            if ( (_DWORD)pv != 3 && (unsigned int)(pv - 5) > 1 )
              return v7;
            *(_DWORD *)Size = 0;
            v43 = 0;
            *(_QWORD *)&v49 = 0;
            v47 = 0;
            v48 = 0;
            ObjectBitmapHandle = (HBITMAP)NtGdiGetObjectBitmapHandle(a2, &usage);
            hbm = ObjectBitmapHandle;
            v28 = ObjectBitmapHandle;
            if ( !ObjectBitmapHandle )
              return v7;
            v29 = 5;
            if ( (_DWORD)pv == 3 )
            {
              usage = 0;
              if ( (unsigned int)NtGdiMonoBitmap(ObjectBitmapHandle) )
                v29 = 3;
            }
            CompatibleDC = CreateCompatibleDC(0);
            if ( (unsigned int)bMetaGetDIBInfo(CompatibleDC, v28, &v47, Size, &v43, usage, 0, 1) )
            {
              if ( HIWORD(v47) == 24 )
                usage = 0;
              v30 = *(unsigned int *)Size;
              if ( *(_DWORD *)Size < (unsigned int)(-1 - v43) )
              {
                v31 = v43 + *(_DWORD *)Size;
                if ( (unsigned int)(v43 + *(_DWORD *)Size) < 0xFFFFFFFB )
                {
                  v32 = (char *)LocalAlloc(0, v31 + 4LL);
                  v33 = v32;
                  if ( v32 )
                  {
                    v34 = hbm;
                    *(_WORD *)v32 = v29;
                    *((_WORD *)v32 + 1) = usage;
                    *(_OWORD *)(v32 + 4) = v47;
                    *(_OWORD *)(v32 + 20) = v48;
                    *(_QWORD *)(v32 + 36) = v49;
                    if ( (unsigned int)GetBrushBits(
                                         CompatibleDC,
                                         v34,
                                         usage,
                                         (unsigned int)v30,
                                         &v32[v30 + 4],
                                         (LPBITMAPINFO)(v32 + 4)) )
                      v8 = RecordParms(a1, 322, (v31 >> 1) + 2, v33);
                    LocalFree(v33);
                  }
                  v7 = -1;
                }
              }
            }
          }
          else
          {
            *(_DWORD *)&Size[2] = DWORD1(pv);
            *(_WORD *)Size = pv;
            Size_6 = WORD4(pv);
            v8 = RecordParms(a1, 764, 4, Size);
          }
          if ( CompatibleDC )
            DeleteDC(CompatibleDC);
          goto LABEL_18;
        }
        return v7;
      }
      if ( v3 == 0x80000 )
      {
        LogPalette = MakeLogPalette(a1, a2, 247);
      }
      else
      {
        if ( v3 == 655360 )
        {
          v47 = 0;
          v50 = 0;
          v48 = 0;
          v49 = 0;
          GetObject16AndType(a2);
          p_hbm = (HBITMAP *)&v47;
          v11 = 763;
          v12 = 25;
        }
        else
        {
          hbm = 0;
          v45 = 0;
          GetObject16AndType(a2);
          p_hbm = &hbm;
          v11 = 762;
          v12 = 5;
        }
        LogPalette = RecordParms(a1, v11, v12, p_hbm);
      }
      v8 = LogPalette;
LABEL_18:
      if ( v8 == 1 )
        return (unsigned __int16)v40;
      return v7;
    }
    RegionData = GetRegionData(a2, 0, 0);
    v36 = RegionData;
    if ( !RegionData )
      return v7;
    v37 = (struct _RGNDATA *)LocalAlloc(0, RegionData);
    v38 = v37;
    if ( !v37 )
      return v7;
    if ( GetRegionData(a2, v36, v37) )
    {
      if ( !v38->rdh.nCount )
      {
        v8 = RecordParms(a1, 1791, 11, w3rgnEmpty);
        v25 = v38;
LABEL_38:
        LocalFree(v25);
        goto LABEL_18;
      }
      v13 = 12LL * v38->rdh.nCount;
      if ( v13 <= 0xFFFFFFFF && (int)v13 + 68 >= (unsigned int)v13 )
      {
        v14 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)(v13 + 68));
        v15 = v14;
        if ( v14 )
        {
          v16 = v14 + 11;
          v14[7] = v38->rdh.rcBound.left;
          v17 = 24;
          v18 = 0;
          v14[9] = v38->rdh.rcBound.right;
          v19 = 0;
          v14[8] = v38->rdh.rcBound.top;
          v14[10] = v38->rdh.rcBound.bottom;
          if ( v38->rdh.nCount )
          {
            do
            {
              v20 = 0;
              v16[1] = *((_WORD *)&v38[1].rdh.dwSize + 8 * v18);
              v16[2] = *((_WORD *)&v38[1].rdh.nCount + 8 * v18);
              do
              {
                v21 = v20;
                v20 += 2;
                v22 = v18++;
                v23 = 2 * v22;
                v16[v21 + 3] = *(_WORD *)&v38->Buffer[8 * v23];
                v16[v21 + 4] = *((_WORD *)&v38[1].rdh.iType + 4 * v23);
              }
              while ( v18 < v38->rdh.nCount
                   && *(&v38[1].rdh.dwSize + 2 * v23) == *(&v38[1].rdh.dwSize + 4 * v18)
                   && *(&v38[1].rdh.nCount + 2 * v23) == *(&v38[1].rdh.nCount + 4 * v18) );
              ++v19;
              *v16 = v20;
              v24 = v20;
              if ( v20 <= (unsigned __int16)CompatibleDC )
                v24 = (unsigned __int16)CompatibleDC;
              v16[v20 + 3] = v20;
              LOWORD(CompatibleDC) = v24;
              v17 += 2 * v20 + 8;
              v16 += (unsigned int)v20 + 4;
            }
            while ( v18 < v38->rdh.nCount );
            v7 = -1;
          }
          v14[4] = v17;
          *(_DWORD *)v14 = 393216;
          *((_DWORD *)v14 + 1) = 758;
          v14[5] = v19;
          v14[6] = (unsigned __int16)CompatibleDC;
          v8 = RecordParms(a1, 1791, (unsigned int)(v17 - 2) >> 1, v14);
          LocalFree(v38);
          v25 = (struct _RGNDATA *)v15;
          goto LABEL_38;
        }
      }
    }
    LocalFree(v38);
    return v7;
  }
  return (unsigned __int16)v40;
}

```

## disassembly

```asm
0x1800032a8  mov     [rsp-8+arg_10], rbx
0x1800032ad  push    rbp
0x1800032ae  push    rsi
0x1800032af  push    rdi
0x1800032b0  push    r12
0x1800032b2  push    r13
0x1800032b4  push    r14
0x1800032b6  push    r15
0x1800032b8  lea     rbp, [rsp-27h]
0x1800032bd  sub     rsp, 0C0h
0x1800032c4  mov     rax, cs:__security_cookie
0x1800032cb  xor     rax, rsp
0x1800032ce  mov     [rbp+57h+var_40], rax
0x1800032d2  xor     r15d, r15d
0x1800032d5  mov     ebx, edx
0x1800032d7  and     ebx, 7F0000h
0x1800032dd  mov     [rbp+57h+var_AC], r15d
0x1800032e1  mov     [rbp+57h+usage], r15d
0x1800032e5  mov     rsi, rdx
0x1800032e8  mov     r14, rcx
0x1800032eb  mov     r13d, 40000h
0x1800032f1  cmp     ebx, 100000h
0x1800032f7  jnz     short loc_180003363
0x1800032f9  mov     r9d, 1
0x1800032ff  lea     r8, [rbp+57h+var_AC]
0x180003303  call    AddObjectToDCTable
0x180003308  mov     r12d, 0FFFFFFFFh
0x18000330e  mov     edi, eax
0x180003310  cmp     eax, r12d
0x180003313  jz      short loc_180003336
0x180003315  cmp     eax, 1
0x180003318  jz      loc_1800035E8
0x18000331e  cmp     ebx, r13d
0x180003321  jz      loc_1800037FB
0x180003327  mov     rdx, rsi
0x18000332a  mov     rcx, r14
0x18000332d  call    AddDCToObjectMetaList16
0x180003332  test    eax, eax
0x180003334  jnz     short loc_180003397
0x180003336  mov     eax, 0FFFFh
0x18000333b  mov     rcx, [rbp+57h+var_40]
0x18000333f  xor     rcx, rsp; StackCookie
0x180003342  call    __security_check_cookie
0x180003347  mov     rbx, [rsp+0F0h+arg_10]
0x18000334f  add     rsp, 0C0h
0x180003356  pop     r15
0x180003358  pop     r14
0x18000335a  pop     r13
0x18000335c  pop     r12
0x18000335e  pop     rdi
0x18000335f  pop     rsi
0x180003360  pop     rbp
0x180003361  retn
0x180003363  cmp     ebx, 300000h
0x180003369  jz      short loc_1800032F9
0x18000336b  cmp     ebx, 0A0000h
0x180003371  jz      short loc_1800032F9
0x180003373  cmp     ebx, r13d
0x180003376  jz      short loc_1800032F9
0x180003378  cmp     ebx, 80000h
0x18000337e  jz      loc_1800032F9
0x180003384  mov     ecx, 6
0x180003389  call    cs:__imp_GdiSetLastError
0x180003390  nop     dword ptr [rax+rax+00h]
0x180003395  jmp     short loc_180003336
0x180003397  cmp     ebx, r13d
0x18000339a  jz      loc_1800037FB
0x1800033a0  cmp     ebx, 100000h
0x1800033a6  jnz     short loc_180003417
0x1800033a8  xorps   xmm0, xmm0
0x1800033ab  lea     r8, [rbp+57h+pv]; pv
0x1800033af  mov     edx, 10h; c
0x1800033b4  mov     rcx, rsi; h
0x1800033b7  movups  [rbp+57h+pv], xmm0
0x1800033bb  call    GetObjectA
0x1800033c0  test    eax, eax
0x1800033c2  jz      short loc_18000340E
0x1800033c4  mov     ecx, dword ptr [rbp+57h+pv]
0x1800033c7  mov     eax, ecx
0x1800033c9  test    ecx, ecx
0x1800033cb  jnz     loc_180003643
0x1800033d1  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800033d4  lea     r9, [rbp+57h+Size]
0x1800033d8  mov     dword ptr [rbp+57h+Size+2], eax
0x1800033db  mov     edx, 2FCh
0x1800033e0  movzx   eax, word ptr [rbp+57h+pv+8]
0x1800033e4  mov     r8d, 4
0x1800033ea  mov     word ptr [rbp+57h+Size], cx
0x1800033ee  mov     rcx, r14
0x1800033f1  mov     word ptr [rbp+57h+Size+6], ax
0x1800033f5  call    RecordParms
0x1800033fa  mov     edi, eax
0x1800033fc  test    r15, r15
0x1800033ff  jnz     loc_1800037E7
0x180003405  cmp     edi, 1
0x180003408  jnz     short loc_18000340E
0x18000340a  mov     r12d, [rbp+57h+var_AC]
0x18000340e  movzx   eax, r12w
0x180003412  jmp     loc_18000333B
0x180003417  cmp     ebx, 80000h
0x18000341d  jz      loc_18000362B
0x180003423  cmp     ebx, 0A0000h
0x180003429  jz      loc_1800035F1
0x18000342f  cmp     ebx, 300000h
0x180003435  jnz     short loc_18000340E
0x180003437  xor     eax, eax
0x180003439  lea     rdx, [rbp+57h+hbm]
0x18000343d  mov     rcx, rsi; h
0x180003440  mov     [rbp+57h+hbm], rax
0x180003444  mov     [rbp+57h+var_90], ax
0x180003448  call    GetObject16AndType
0x18000344d  lea     r9, [rbp+57h+hbm]
0x180003451  mov     edx, 2FAh
0x180003456  mov     r8d, 5
0x18000345c  jmp     loc_180003621
0x180003461  mov     eax, [rbx+8]
0x180003464  lea     rcx, [rax+rax*2]
0x180003468  shl     rcx, 2
0x18000346c  cmp     rcx, r12
0x18000346f  jbe     short loc_180003482
0x180003471  mov     rcx, rbx; hMem
0x180003474  call    cs:__imp_LocalFree
0x18000347b  nop     dword ptr [rax+rax+00h]
0x180003480  jmp     short loc_18000340E
0x180003482  lea     eax, [rcx+44h]
0x180003485  cmp     eax, ecx
0x180003487  jb      short loc_180003471
0x180003489  mov     edx, eax; uBytes
0x18000348b  xor     ecx, ecx; uFlags
0x18000348d  call    cs:__imp_LocalAlloc
0x180003494  nop     dword ptr [rax+rax+00h]
0x180003499  mov     rsi, rax
0x18000349c  test    rax, rax
0x18000349f  jz      short loc_180003471
0x1800034a1  movzx   eax, word ptr [rbx+10h]
0x1800034a5  lea     rdi, [rsi+16h]
0x1800034a9  mov     [rsi+0Eh], ax
0x1800034ad  mov     r8d, 18h
0x1800034b3  movzx   eax, word ptr [rbx+18h]
0x1800034b7  mov     r10d, r15d
0x1800034ba  mov     [rsi+12h], ax
0x1800034be  mov     r13d, r15d
0x1800034c1  movzx   eax, word ptr [rbx+14h]
0x1800034c5  mov     [rsi+10h], ax
0x1800034c9  movzx   eax, word ptr [rbx+1Ch]
0x1800034cd  mov     [rsi+14h], ax
0x1800034d1  cmp     [rbx+8], r15d
0x1800034d5  jbe     loc_180003590
0x1800034db  lea     edx, [r8-16h]
0x1800034df  lea     r12d, [r8-17h]
0x1800034e3  xor     r11d, r11d
0x1800034e6  mov     ecx, r10d
0x1800034e9  add     rcx, rcx
0x1800034ec  movzx   eax, word ptr [rbx+rcx*8+24h]
0x1800034f1  mov     [rdi+2], ax
0x1800034f5  movzx   eax, word ptr [rbx+rcx*8+2Ch]
0x1800034fa  mov     [rdi+4], ax
0x1800034fe  movzx   ecx, r11w
0x180003502  add     r11w, dx
0x180003506  mov     r9d, r10d
0x180003509  add     r10d, r12d
0x18000350c  add     r9, r9
0x18000350f  movzx   eax, word ptr [rbx+r9*8+20h]
0x180003515  mov     [rdi+rcx*2+6], ax
0x18000351a  movzx   eax, word ptr [rbx+r9*8+28h]
0x180003520  mov     [rdi+rcx*2+8], ax
0x180003525  cmp     r10d, [rbx+8]
0x180003529  jnb     short loc_180003547
0x18000352b  mov     ecx, r10d
0x18000352e  add     rcx, rcx
0x180003531  mov     eax, [rbx+rcx*8+24h]
0x180003535  cmp     [rbx+r9*8+24h], eax
0x18000353a  jnz     short loc_180003547
0x18000353c  mov     eax, [rbx+rcx*8+2Ch]
0x180003540  cmp     [rbx+r9*8+2Ch], eax
0x180003545  jz      short loc_1800034FE
0x180003547  movzx   eax, r11w
0x18000354b  add     r13w, r12w
0x18000354f  mov     [rdi], r11w
0x180003553  cmp     r11w, r15w
0x180003557  movzx   ecx, r11w
0x18000355b  cmovbe  cx, r15w
0x180003560  mov     [rdi+rax*2+6], r11w
0x180003566  movzx   r15d, cx
0x18000356a  movzx   eax, r11w
0x18000356e  lea     r8d, [r8+rax*2]
0x180003572  lea     eax, ds:8[rax*2]
0x180003579  add     r8d, 8
0x18000357d  add     rdi, rax
0x180003580  cmp     r10d, [rbx+8]
0x180003584  jb      loc_1800034E3
0x18000358a  mov     r12d, 0FFFFFFFFh
0x180003590  mov     [rsi+8], r8w
0x180003595  mov     r9, rsi
0x180003598  add     r8d, 0FFFFFFFEh
0x18000359c  mov     dword ptr [rsi], 60000h
0x1800035a2  shr     r8d, 1
0x1800035a5  mov     edx, 6FFh
0x1800035aa  mov     rcx, r14
0x1800035ad  mov     dword ptr [rsi+4], 2F6h
0x1800035b4  mov     [rsi+0Ah], r13w
0x1800035b9  mov     [rsi+0Ch], r15w
0x1800035be  call    RecordParms
0x1800035c3  mov     rcx, rbx; hMem
0x1800035c6  mov     edi, eax
0x1800035c8  call    cs:__imp_LocalFree
0x1800035cf  nop     dword ptr [rax+rax+00h]
0x1800035d4  mov     rcx, rsi; hMem
0x1800035d7  call    cs:__imp_LocalFree
0x1800035de  nop     dword ptr [rax+rax+00h]
0x1800035e3  jmp     loc_180003405
0x1800035e8  movzx   eax, word ptr [rbp+57h+var_AC]
0x1800035ec  jmp     loc_18000333B
0x1800035f1  xorps   xmm0, xmm0
0x1800035f4  lea     rdx, [rbp+57h+var_78]
0x1800035f8  xor     eax, eax
0x1800035fa  mov     rcx, rsi; h
0x1800035fd  movups  [rbp+57h+var_78], xmm0
0x180003601  mov     [rbp+57h+var_48], ax
0x180003605  movups  [rbp+57h+var_68], xmm0
0x180003609  movups  [rbp+57h+var_58], xmm0
0x18000360d  call    GetObject16AndType
0x180003612  lea     r9, [rbp+57h+var_78]
0x180003616  mov     edx, 2FBh
0x18000361b  mov     r8d, 19h
0x180003621  mov     rcx, r14
0x180003624  call    RecordParms
0x180003629  jmp     short loc_18000363C
0x18000362b  mov     r8d, 0F7h
0x180003631  mov     rdx, rsi
0x180003634  mov     rcx, r14
0x180003637  call    MakeLogPalette
0x18000363c  mov     edi, eax
0x18000363e  jmp     loc_180003405
0x180003643  sub     eax, 1
0x180003646  jz      loc_1800033D1
0x18000364c  sub     eax, 1
0x18000364f  jz      loc_1800033D1
0x180003655  sub     eax, 1
0x180003658  jz      short loc_180003668
0x18000365a  sub     eax, 2
0x18000365d  jz      short loc_180003668
0x18000365f  cmp     eax, 1
0x180003662  jnz     loc_18000340E
0x180003668  xorps   xmm0, xmm0
0x18000366b  mov     dword ptr [rbp+57h+Size], r15d
0x18000366f  xor     eax, eax
0x180003671  mov     [rbp+57h+var_A0], r15d
0x180003675  lea     rdx, [rbp+57h+usage]
0x180003679  mov     qword ptr [rbp+57h+var_58], rax
0x18000367d  mov     rcx, rsi
0x180003680  movups  [rbp+57h+var_78], xmm0
0x180003684  movups  [rbp+57h+var_68], xmm0
0x180003688  call    cs:__imp_NtGdiGetObjectBitmapHandle
0x18000368f  nop     dword ptr [rax+rax+00h]
0x180003694  mov     [rbp+57h+hbm], rax
0x180003698  mov     rbx, rax
0x18000369b  test    rax, rax
0x18000369e  jz      loc_18000340E
0x1800036a4  mov     esi, 5
0x1800036a9  lea     r13d, [rsi-2]
0x1800036ad  cmp     dword ptr [rbp+57h+pv], r13d
0x1800036b1  jnz     short loc_1800036CC
0x1800036b3  mov     rcx, rax
0x1800036b6  mov     [rbp+57h+usage], r15d
0x1800036ba  call    cs:__imp_NtGdiMonoBitmap
0x1800036c1  nop     dword ptr [rax+rax+00h]
0x1800036c6  test    eax, eax
0x1800036c8  cmovnz  esi, r13d
0x1800036cc  xor     ecx, ecx; hdc
0x1800036ce  call    CreateCompatibleDC
0x1800036d3  mov     ecx, [rbp+57h+usage]
0x1800036d6  lea     r9, [rbp+57h+Size]
0x1800036da  mov     [rsp+0F0h+var_B8], 1
0x1800036e2  lea     r8, [rbp+57h+var_78]
0x1800036e6  mov     r15, rax
0x1800036e9  mov     [rsp+0F0h+var_C0], 0
0x1800036f1  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x1800036f5  lea     rax, [rbp+57h+var_A0]
0x1800036f9  mov     rcx, r15
0x1800036fc  mov     [rsp+0F0h+var_D0], rax
0x180003701  mov     rdx, rbx
0x180003704  call    bMetaGetDIBInfo
0x180003709  test    eax, eax
0x18000370b  jz      loc_1800033FC
0x180003711  mov     r8d, 18h
0x180003717  cmp     word ptr [rbp+57h+var_78+0Eh], r8w
0x18000371c  jnz     short loc_180003725
0x18000371e  mov     [rbp+57h+usage], 0
0x180003725  mov     ecx, [rbp+57h+var_A0]
0x180003728  mov     eax, r12d
0x18000372b  mov     r13d, dword ptr [rbp+57h+Size]
0x18000372f  sub     eax, ecx
0x180003731  cmp     r13d, eax
0x180003734  jnb     loc_1800033FC
0x18000373a  lea     ebx, [rcx+r13]
0x18000373e  cmp     ebx, 0FFFFFFFBh
0x180003741  jnb     loc_1800033FC
0x180003747  mov     edx, ebx
0x180003749  xor     ecx, ecx; uFlags
  ... truncated ...
```
