# RecordObject

- ea: `0x1800566ac`
- end: `0x180056c34`
- name: `RecordObject`
- size: `1416`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800565d8`
- `0x18007ed20`
- `0x18007f12c`

## callees

- `0x18000e5a0`
- `0x18001fe20`
- `0x180023be4`
- `0x1800566ac`
- `0x180056c3c`
- `0x180056d88`
- `0x18005ce70`
- `0x180078a80`
- `0x18007ac50`
- `0x18007e9b4`
- `0x18007f2e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056884`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056b28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056bde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056884`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056b28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180056bde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056871`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800569b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800569c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ba3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056871`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800569b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800569c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ba3`
- `GDI32!DeleteDC` at `0x180056bb7`
- `GDI32!DeleteDC` at `0x180056bb7`
- `GDI32!GetRegionData` at `0x180056bca`
- `GDI32!GetRegionData` at `0x180056bf8`
- `GDI32!GetRegionData` at `0x180056bca`
- `GDI32!GetRegionData` at `0x180056bf8`
- `GDI32!GdiSetLastError` at `0x18005678c`
- `GDI32!GdiSetLastError` at `0x18005678c`
- `win32u!NtGdiGetObjectBitmapHandle` at `0x180056a6d`
- `win32u!NtGdiGetObjectBitmapHandle` at `0x180056a6d`
- `win32u!NtGdiMonoBitmap` at `0x180056a99`
- `win32u!NtGdiMonoBitmap` at `0x180056a99`

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
0x1800566ac  mov     [rsp-8+arg_10], rbx
0x1800566b1  push    rbp
0x1800566b2  push    rsi
0x1800566b3  push    rdi
0x1800566b4  push    r12
0x1800566b6  push    r13
0x1800566b8  push    r14
0x1800566ba  push    r15
0x1800566bc  lea     rbp, [rsp-27h]
0x1800566c1  sub     rsp, 0C0h
0x1800566c8  mov     rax, cs:__security_cookie
0x1800566cf  xor     rax, rsp
0x1800566d2  mov     [rbp+57h+var_40], rax
0x1800566d6  xor     r15d, r15d
0x1800566d9  mov     ebx, edx
0x1800566db  and     ebx, 7F0000h
0x1800566e1  mov     [rbp+57h+var_AC], r15d
0x1800566e5  mov     [rbp+57h+usage], r15d
0x1800566e9  mov     rsi, rdx
0x1800566ec  mov     r14, rcx
0x1800566ef  mov     r13d, 40000h
0x1800566f5  cmp     ebx, 100000h
0x1800566fb  jnz     short loc_180056766
0x1800566fd  mov     r9d, 1
0x180056703  lea     r8, [rbp+57h+var_AC]
0x180056707  call    AddObjectToDCTable
0x18005670c  mov     r12d, 0FFFFFFFFh
0x180056712  mov     edi, eax
0x180056714  cmp     eax, r12d
0x180056717  jz      short loc_18005673A
0x180056719  cmp     eax, 1
0x18005671c  jz      loc_1800569CD
0x180056722  cmp     ebx, r13d
0x180056725  jz      loc_180056BC2
0x18005672b  mov     rdx, rsi
0x18005672e  mov     rcx, r14
0x180056731  call    AddDCToObjectMetaList16
0x180056736  test    eax, eax
0x180056738  jnz     short loc_180056794
0x18005673a  mov     eax, 0FFFFh
0x18005673f  mov     rcx, [rbp+57h+var_40]
0x180056743  xor     rcx, rsp; StackCookie
0x180056746  call    __security_check_cookie
0x18005674b  mov     rbx, [rsp+0F0h+arg_10]
0x180056753  add     rsp, 0C0h
0x18005675a  pop     r15
0x18005675c  pop     r14
0x18005675e  pop     r13
0x180056760  pop     r12
0x180056762  pop     rdi
0x180056763  pop     rsi
0x180056764  pop     rbp
0x180056765  retn
0x180056766  cmp     ebx, 300000h
0x18005676c  jz      short loc_1800566FD
0x18005676e  cmp     ebx, 0A0000h
0x180056774  jz      short loc_1800566FD
0x180056776  cmp     ebx, r13d
0x180056779  jz      short loc_1800566FD
0x18005677b  cmp     ebx, 80000h
0x180056781  jz      loc_1800566FD
0x180056787  mov     ecx, 6
0x18005678c  call    cs:__imp_GdiSetLastError
0x180056792  jmp     short loc_18005673A
0x180056794  cmp     ebx, r13d
0x180056797  jz      loc_180056BC2
0x18005679d  cmp     ebx, 100000h
0x1800567a3  jnz     short loc_180056814
0x1800567a5  xorps   xmm0, xmm0
0x1800567a8  lea     r8, [rbp+57h+pv]; pv
0x1800567ac  mov     edx, 10h; c
0x1800567b1  mov     rcx, rsi; h
0x1800567b4  movups  [rbp+57h+pv], xmm0
0x1800567b8  call    GetObjectA
0x1800567bd  test    eax, eax
0x1800567bf  jz      short loc_18005680B
0x1800567c1  mov     ecx, dword ptr [rbp+57h+pv]
0x1800567c4  mov     eax, ecx
0x1800567c6  test    ecx, ecx
0x1800567c8  jnz     loc_180056A28
0x1800567ce  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800567d1  lea     r9, [rbp+57h+Size]
0x1800567d5  mov     dword ptr [rbp+57h+Size+2], eax
0x1800567d8  mov     edx, 2FCh
0x1800567dd  movzx   eax, word ptr [rbp+57h+pv+8]
0x1800567e1  mov     r8d, 4
0x1800567e7  mov     word ptr [rbp+57h+Size], cx
0x1800567eb  mov     rcx, r14
0x1800567ee  mov     word ptr [rbp+57h+Size+6], ax
0x1800567f2  call    RecordParms
0x1800567f7  mov     edi, eax
0x1800567f9  test    r15, r15
0x1800567fc  jnz     loc_180056BB4
0x180056802  cmp     edi, 1
0x180056805  jnz     short loc_18005680B
0x180056807  mov     r12d, [rbp+57h+var_AC]
0x18005680b  movzx   eax, r12w
0x18005680f  jmp     loc_18005673F
0x180056814  cmp     ebx, 80000h
0x18005681a  jz      loc_180056A10
0x180056820  cmp     ebx, 0A0000h
0x180056826  jz      loc_1800569D6
0x18005682c  cmp     ebx, 300000h
0x180056832  jnz     short loc_18005680B
0x180056834  xor     eax, eax
0x180056836  lea     rdx, [rbp+57h+hbm]
0x18005683a  mov     rcx, rsi; h
0x18005683d  mov     [rbp+57h+hbm], rax
0x180056841  mov     [rbp+57h+var_90], ax
0x180056845  call    GetObject16AndType
0x18005684a  lea     r9, [rbp+57h+hbm]
0x18005684e  mov     edx, 2FAh
0x180056853  mov     r8d, 5
0x180056859  jmp     loc_180056A06
0x18005685e  mov     eax, [rbx+8]
0x180056861  lea     rcx, [rax+rax*2]
0x180056865  shl     rcx, 2
0x180056869  cmp     rcx, r12
0x18005686c  jbe     short loc_180056879
0x18005686e  mov     rcx, rbx; hMem
0x180056871  call    cs:__imp_LocalFree
0x180056877  jmp     short loc_18005680B
0x180056879  lea     eax, [rcx+44h]
0x18005687c  cmp     eax, ecx
0x18005687e  jb      short loc_18005686E
0x180056880  mov     edx, eax; uBytes
0x180056882  xor     ecx, ecx; uFlags
0x180056884  call    cs:__imp_LocalAlloc
0x18005688a  mov     rsi, rax
0x18005688d  test    rax, rax
0x180056890  jz      short loc_18005686E
0x180056892  movzx   eax, word ptr [rbx+10h]
0x180056896  lea     rdi, [rsi+16h]
0x18005689a  mov     [rsi+0Eh], ax
0x18005689e  mov     r8d, 18h
0x1800568a4  movzx   eax, word ptr [rbx+18h]
0x1800568a8  mov     r10d, r15d
0x1800568ab  mov     [rsi+12h], ax
0x1800568af  mov     r13d, r15d
0x1800568b2  movzx   eax, word ptr [rbx+14h]
0x1800568b6  mov     [rsi+10h], ax
0x1800568ba  movzx   eax, word ptr [rbx+1Ch]
0x1800568be  mov     [rsi+14h], ax
0x1800568c2  cmp     [rbx+8], r15d
0x1800568c6  jbe     loc_180056981
0x1800568cc  lea     edx, [r8-16h]
0x1800568d0  lea     r12d, [r8-17h]
0x1800568d4  xor     r11d, r11d
0x1800568d7  mov     ecx, r10d
0x1800568da  add     rcx, rcx
0x1800568dd  movzx   eax, word ptr [rbx+rcx*8+24h]
0x1800568e2  mov     [rdi+2], ax
0x1800568e6  movzx   eax, word ptr [rbx+rcx*8+2Ch]
0x1800568eb  mov     [rdi+4], ax
0x1800568ef  movzx   ecx, r11w
0x1800568f3  add     r11w, dx
0x1800568f7  mov     r9d, r10d
0x1800568fa  add     r10d, r12d
0x1800568fd  add     r9, r9
0x180056900  movzx   eax, word ptr [rbx+r9*8+20h]
0x180056906  mov     [rdi+rcx*2+6], ax
0x18005690b  movzx   eax, word ptr [rbx+r9*8+28h]
0x180056911  mov     [rdi+rcx*2+8], ax
0x180056916  cmp     r10d, [rbx+8]
0x18005691a  jnb     short loc_180056938
0x18005691c  mov     ecx, r10d
0x18005691f  add     rcx, rcx
0x180056922  mov     eax, [rbx+rcx*8+24h]
0x180056926  cmp     [rbx+r9*8+24h], eax
0x18005692b  jnz     short loc_180056938
0x18005692d  mov     eax, [rbx+rcx*8+2Ch]
0x180056931  cmp     [rbx+r9*8+2Ch], eax
0x180056936  jz      short loc_1800568EF
0x180056938  movzx   eax, r11w
0x18005693c  add     r13w, r12w
0x180056940  mov     [rdi], r11w
0x180056944  cmp     r11w, r15w
0x180056948  movzx   ecx, r11w
0x18005694c  cmovbe  cx, r15w
0x180056951  mov     [rdi+rax*2+6], r11w
0x180056957  movzx   r15d, cx
0x18005695b  movzx   eax, r11w
0x18005695f  lea     r8d, [r8+rax*2]
0x180056963  lea     eax, ds:8[rax*2]
0x18005696a  add     r8d, 8
0x18005696e  add     rdi, rax
0x180056971  cmp     r10d, [rbx+8]
0x180056975  jb      loc_1800568D4
0x18005697b  mov     r12d, 0FFFFFFFFh
0x180056981  mov     [rsi+8], r8w
0x180056986  mov     r9, rsi
0x180056989  add     r8d, 0FFFFFFFEh
0x18005698d  mov     dword ptr [rsi], 60000h
0x180056993  shr     r8d, 1
0x180056996  mov     edx, 6FFh
0x18005699b  mov     rcx, r14
0x18005699e  mov     dword ptr [rsi+4], 2F6h
0x1800569a5  mov     [rsi+0Ah], r13w
0x1800569aa  mov     [rsi+0Ch], r15w
0x1800569af  call    RecordParms
0x1800569b4  mov     rcx, rbx; hMem
0x1800569b7  mov     edi, eax
0x1800569b9  call    cs:__imp_LocalFree
0x1800569bf  mov     rcx, rsi; hMem
0x1800569c2  call    cs:__imp_LocalFree
0x1800569c8  jmp     loc_180056802
0x1800569cd  movzx   eax, word ptr [rbp+57h+var_AC]
0x1800569d1  jmp     loc_18005673F
0x1800569d6  xorps   xmm0, xmm0
0x1800569d9  lea     rdx, [rbp+57h+var_78]
0x1800569dd  xor     eax, eax
0x1800569df  mov     rcx, rsi; h
0x1800569e2  movups  [rbp+57h+var_78], xmm0
0x1800569e6  mov     [rbp+57h+var_48], ax
0x1800569ea  movups  [rbp+57h+var_68], xmm0
0x1800569ee  movups  [rbp+57h+var_58], xmm0
0x1800569f2  call    GetObject16AndType
0x1800569f7  lea     r9, [rbp+57h+var_78]
0x1800569fb  mov     edx, 2FBh
0x180056a00  mov     r8d, 19h
0x180056a06  mov     rcx, r14
0x180056a09  call    RecordParms
0x180056a0e  jmp     short loc_180056A21
0x180056a10  mov     r8d, 0F7h
0x180056a16  mov     rdx, rsi
0x180056a19  mov     rcx, r14
0x180056a1c  call    MakeLogPalette
0x180056a21  mov     edi, eax
0x180056a23  jmp     loc_180056802
0x180056a28  sub     eax, 1
0x180056a2b  jz      loc_1800567CE
0x180056a31  sub     eax, 1
0x180056a34  jz      loc_1800567CE
0x180056a3a  sub     eax, 1
0x180056a3d  jz      short loc_180056A4D
0x180056a3f  sub     eax, 2
0x180056a42  jz      short loc_180056A4D
0x180056a44  cmp     eax, 1
0x180056a47  jnz     loc_18005680B
0x180056a4d  xorps   xmm0, xmm0
0x180056a50  mov     dword ptr [rbp+57h+Size], r15d
0x180056a54  xor     eax, eax
0x180056a56  mov     [rbp+57h+var_A0], r15d
0x180056a5a  lea     rdx, [rbp+57h+usage]
0x180056a5e  mov     qword ptr [rbp+57h+var_58], rax
0x180056a62  mov     rcx, rsi
0x180056a65  movups  [rbp+57h+var_78], xmm0
0x180056a69  movups  [rbp+57h+var_68], xmm0
0x180056a6d  call    cs:__imp_NtGdiGetObjectBitmapHandle
0x180056a73  mov     [rbp+57h+hbm], rax
0x180056a77  mov     rbx, rax
0x180056a7a  test    rax, rax
0x180056a7d  jz      loc_18005680B
0x180056a83  mov     esi, 5
0x180056a88  lea     r13d, [rsi-2]
0x180056a8c  cmp     dword ptr [rbp+57h+pv], r13d
0x180056a90  jnz     short loc_180056AA5
0x180056a92  mov     rcx, rax
0x180056a95  mov     [rbp+57h+usage], r15d
0x180056a99  call    cs:__imp_NtGdiMonoBitmap
0x180056a9f  test    eax, eax
0x180056aa1  cmovnz  esi, r13d
0x180056aa5  xor     ecx, ecx; hdc
0x180056aa7  call    CreateCompatibleDC
0x180056aac  mov     ecx, [rbp+57h+usage]
0x180056aaf  lea     r9, [rbp+57h+Size]
0x180056ab3  mov     [rsp+0F0h+var_B8], 1
0x180056abb  lea     r8, [rbp+57h+var_78]
0x180056abf  mov     r15, rax
0x180056ac2  mov     [rsp+0F0h+var_C0], 0
0x180056aca  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x180056ace  lea     rax, [rbp+57h+var_A0]
0x180056ad2  mov     rcx, r15
0x180056ad5  mov     [rsp+0F0h+var_D0], rax
0x180056ada  mov     rdx, rbx
0x180056add  call    bMetaGetDIBInfo
0x180056ae2  test    eax, eax
0x180056ae4  jz      loc_1800567F9
0x180056aea  mov     r8d, 18h
0x180056af0  cmp     word ptr [rbp+57h+var_78+0Eh], r8w
0x180056af5  jnz     short loc_180056AFE
0x180056af7  mov     [rbp+57h+usage], 0
0x180056afe  mov     ecx, [rbp+57h+var_A0]
0x180056b01  mov     eax, r12d
0x180056b04  mov     r13d, dword ptr [rbp+57h+Size]
0x180056b08  sub     eax, ecx
0x180056b0a  cmp     r13d, eax
0x180056b0d  jnb     loc_1800567F9
0x180056b13  lea     ebx, [rcx+r13]
0x180056b17  cmp     ebx, 0FFFFFFFBh
0x180056b1a  jnb     loc_1800567F9
0x180056b20  mov     edx, ebx
0x180056b22  xor     ecx, ecx; uFlags
0x180056b24  add     rdx, 4; uBytes
0x180056b28  call    cs:__imp_LocalAlloc
0x180056b2e  mov     r12, rax
0x180056b31  test    rax, rax
0x180056b34  jz      short loc_180056BA9
0x180056b36  mov     rdx, [rbp+57h+hbm]; hbm
0x180056b3a  mov     r9d, r13d; Size
  ... truncated ...
```
