# ExtSelectClipRgnImpl(HDC__ *,HRGN__ *,int)

- ea: `0x1800726a0`
- end: `0x180072a66`
- name: `?ExtSelectClipRgnImpl@@YAHPEAUHDC__@@PEAUHRGN__@@H@Z`
- size: `966`
- prototype: `__int64 __fastcall(HDC hdc, HRGN, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180017610`
- `0x18003baec`
- `0x18005b584`
- `0x18006dcac`
- `0x1800710c4`
- `0x1800726a0`
- `0x1800a3010`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180072789`
- `GDI32!GdiGetEntry` at `0x1800727f4`
- `GDI32!GdiGetEntry` at `0x180072834`
- `GDI32!GdiGetEntry` at `0x180072789`
- `GDI32!GdiGetEntry` at `0x1800727f4`
- `GDI32!GdiGetEntry` at `0x180072834`
- `GDI32!GdiBatchLimit` at `0x180072a40`
- `GDI32!gW32PID` at `0x1800727b2`
- `GDI32!gW32PID` at `0x18007285d`
- `GDI32!gCookie` at `0x1800727cc`
- `GDI32!gCookie` at `0x180072877`
- `GDI32!gMaxGdiHandleCount` at `0x180072767`
- `GDI32!gMaxGdiHandleCount` at `0x180072816`
- `GDI32!pldcGet` at `0x1800726ed`
- `GDI32!pldcGet` at `0x1800726ed`
- `GDI32!GdiSetLastError` at `0x180072954`
- `GDI32!GdiSetLastError` at `0x180072954`
- `GDI32!DeleteObject` at `0x18007292e`
- `GDI32!DeleteObject` at `0x18007292e`
- `win32u!NtGdiExtSelectClipRgn` at `0x18007291d`
- `win32u!NtGdiExtSelectClipRgn` at `0x18007291d`
- `win32u!NtGdiFlush` at `0x180072a5b`
- `win32u!NtGdiFlush` at `0x180072a5b`

## pseudocode

```c
__int64 __fastcall ExtSelectClipRgnImpl(HDC hdc, HRGN a2, unsigned int a3)
{
  HRGN v3; // r12
  unsigned int v6; // r13d
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r15
  unsigned int v12; // eax
  __int64 v13; // r14
  unsigned int v14; // eax
  struct _TEB *v15; // rbx
  HDC v16; // rax
  __int64 v17; // rdx
  ULONG *v18; // rcx
  int v19; // eax
  ULONG Offset; // eax
  int v21; // ecx
  __int128 v22; // [rsp+20h] [rbp-30h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h]
  __int128 v24; // [rsp+38h] [rbp-18h] BYREF
  __int64 v25; // [rsp+48h] [rbp-8h]
  HRGN v26; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+50h]

  v27 = a3;
  v3 = 0;
  v26 = 0;
  v6 = 2;
  if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 )
  {
    if ( ((unsigned int)hdc & 0x7F0000) == 0x660000 )
      return MF16_SelectClipRgn();
    v8 = pldcGet(hdc);
    if ( !v8 )
    {
      GdiSetLastError(6);
      return 0;
    }
    if ( *(_DWORD *)(v8 + 12) == 2 && !(unsigned int)MF_ExtSelectClipRgn(hdc, a2, v27) )
      return 0;
  }
  if ( a2 )
  {
    if ( (GetLayout(hdc) & 1) != 0 )
    {
      v9 = MirrorRgnDC(hdc, a2, &v26);
      v3 = v26;
      if ( v9 )
      {
        if ( v26 )
          a2 = v26;
      }
    }
  }
  if ( v27 != 5 )
    goto LABEL_40;
  v25 = 0;
  v24 = 0;
  v10 = HANDLE_TO_INDEX(hdc);
  v11 = 0;
  if ( v10 < gMaxGdiHandleCount )
  {
    v23 = 0;
    v22 = 0;
    if ( (int)GdiGetEntry(v10, &v22) >= 0
      && BYTE14(v22) == 1
      && WORD6(v22) == WORD1(hdc)
      && (DWORD2(v22) & 0xFFFFFFFE) == gW32PID
      && v23 )
    {
      v11 = __ROR8__(v23, 64 - (gCookie & 0x3Fu)) ^ gCookie;
    }
  }
  v12 = HANDLE_TO_INDEX(hdc);
  if ( (int)GdiGetEntry(v12, &v24) < 0 )
    return 0;
  v13 = 0;
  if ( a2 )
  {
    v14 = HANDLE_TO_INDEX(a2);
    if ( v14 < gMaxGdiHandleCount )
    {
      v23 = 0;
      v22 = 0;
      if ( (int)GdiGetEntry(v14, &v22) >= 0
        && BYTE14(v22) == 4
        && WORD6(v22) == WORD1(a2)
        && (DWORD2(v22) & 0xFFFFFFFE) == gW32PID
        && v23 )
      {
        v13 = __ROR8__(v23, 64 - (gCookie & 0x3Fu)) ^ gCookie;
      }
    }
  }
  v15 = NtCurrentTeb();
  v16 = (HDC)v15->GdiTebBatch.HDC;
  if ( v16 && v16 != hdc || (v15->GdiTebBatch.Offset & 0x3FFFFFFF) + 24 > 0x4D8 || !v11 || (*(_BYTE *)v11 & 1) != 0 )
    goto LABEL_40;
  if ( (v15->GdiTebBatch.Offset & 0x40000000) != 0 )
    TraceLoggingGdiBatchInProcessing(5);
  v17 = v15->GdiTebBatch.Offset & 0x3FFFFFFF;
  *(ULONG *)((char *)v15->GdiTebBatch.Buffer + v17) = 327704;
  if ( !a2 )
  {
    v6 = 0;
    if ( (HIBYTE(v24) & 4) == 0 )
      v6 = *(_DWORD *)(v11 + 116);
    v18 = (ULONG *)(v13 + 16);
    if ( (HIBYTE(v24) & 4) != 0 )
      goto LABEL_40;
    goto LABEL_55;
  }
  if ( v13 && *(_DWORD *)(v13 + 4) == 2 && (*(_BYTE *)v13 & 1) == 0 && (HIBYTE(v24) & 4) == 0 )
  {
    v18 = (ULONG *)(v13 + 16);
    if ( *(_DWORD *)(v11 + 120) < *(_DWORD *)(v13 + 16)
      && *(_DWORD *)(v11 + 124) < *(_DWORD *)(v13 + 20)
      && *(_DWORD *)(v11 + 128) > *(_DWORD *)(v13 + 8)
      && *(_DWORD *)(v11 + 132) > *(_DWORD *)(v13 + 12) )
    {
      goto LABEL_57;
    }
    v6 = 1;
LABEL_55:
    if ( !a2 )
    {
      v19 = 134217733;
      goto LABEL_58;
    }
LABEL_57:
    *(ULONG *)((char *)&v15->GdiTebBatch.Buffer[2] + v17) = *(_DWORD *)(v13 + 8);
    *(ULONG *)((char *)&v15->GdiTebBatch.Buffer[3] + v17) = *(_DWORD *)(v13 + 12);
    *(ULONG *)((char *)&v15->GdiTebBatch.Buffer[4] + v17) = *v18;
    *(ULONG *)((char *)&v15->GdiTebBatch.Buffer[5] + v17) = *(_DWORD *)(v13 + 20);
    v19 = v27;
LABEL_58:
    *(ULONG *)((char *)&v15->GdiTebBatch.Buffer[1] + v17) = v19;
    if ( hdc )
    {
      v15->GdiTebBatch.HDC = hdc;
      if ( !*(_WORD *)((char *)v15->GdiTebBatch.Buffer + v17 + 2)
        || *(_WORD *)((char *)v15->GdiTebBatch.Buffer + v17 + 2) == 1
        || (unsigned int)*(unsigned __int16 *)((char *)v15->GdiTebBatch.Buffer + v17 + 2) - 2 <= 1 )
      {
        v15->GdiTebBatch.Offset |= 0x80000000;
      }
    }
    Offset = v15->GdiTebBatch.Offset;
    v21 = *(unsigned __int16 *)((char *)v15->GdiTebBatch.Buffer + v17);
    ++v15->GdiBatchCount;
    v15->GdiTebBatch.Offset = Offset ^ (Offset ^ (Offset + ((v21 + 7) & 0xFFFFFFF8))) & 0x3FFFFFFF;
    if ( v15->GdiBatchCount >= GdiBatchLimit )
      NtGdiFlush();
    goto LABEL_41;
  }
LABEL_40:
  v6 = NtGdiExtSelectClipRgn(hdc, a2, v27);
LABEL_41:
  if ( v3 )
    DeleteObject(v3);
  return v6;
}

```

## disassembly

```asm
0x1800726a0  mov     [rsp-38h+arg_8], rbx
0x1800726a5  mov     [rsp-38h+arg_10], r8d
0x1800726aa  push    rbp
0x1800726ab  push    rsi
0x1800726ac  push    rdi
0x1800726ad  push    r12
0x1800726af  push    r13
0x1800726b1  push    r14
0x1800726b3  push    r15
0x1800726b5  mov     rbp, rsp
0x1800726b8  sub     rsp, 50h
0x1800726bc  xor     r12d, r12d
0x1800726bf  mov     eax, ecx
0x1800726c1  and     eax, 7F0000h
0x1800726c6  mov     [rbp+arg_0], r12
0x1800726ca  mov     rdi, rdx
0x1800726cd  mov     rsi, rcx
0x1800726d0  lea     r13d, [r12+2]
0x1800726d5  cmp     eax, 10000h
0x1800726da  jz      short loc_180072719
0x1800726dc  cmp     eax, 660000h
0x1800726e1  jnz     short loc_1800726ED
0x1800726e3  call    MF16_SelectClipRgn
0x1800726e8  jmp     loc_180072937
0x1800726ed  call    cs:__imp_pldcGet
0x1800726f3  test    rax, rax
0x1800726f6  jz      loc_18007294F
0x1800726fc  cmp     [rax+0Ch], r13d
0x180072700  jnz     short loc_180072719
0x180072702  mov     r8d, [rbp+arg_10]
0x180072706  mov     rdx, rdi
0x180072709  mov     rcx, rsi
0x18007270c  call    MF_ExtSelectClipRgn
0x180072711  test    eax, eax
0x180072713  jz      loc_18007295A
0x180072719  test    rdi, rdi
0x18007271c  jz      short loc_180072748
0x18007271e  mov     rcx, rsi; hdc
0x180072721  call    GetLayout
0x180072726  test    al, 1
0x180072728  jz      short loc_180072748
0x18007272a  lea     r8, [rbp+arg_0]
0x18007272e  mov     rdx, rdi
0x180072731  mov     rcx, rsi
0x180072734  call    MirrorRgnDC
0x180072739  mov     r12, [rbp+arg_0]
0x18007273d  test    eax, eax
0x18007273f  jz      short loc_180072748
0x180072741  test    r12, r12
0x180072744  cmovnz  rdi, r12
0x180072748  cmp     [rbp+arg_10], 5
0x18007274c  jnz     loc_180072913
0x180072752  xor     eax, eax
0x180072754  xorps   xmm0, xmm0
0x180072757  mov     rcx, rsi
0x18007275a  mov     [rbp+var_8], rax
0x18007275e  movups  [rbp+var_18], xmm0
0x180072762  call    HANDLE_TO_INDEX
0x180072767  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18007276e  xor     r15d, r15d
0x180072771  lea     ebx, [r15+40h]
0x180072775  cmp     eax, [rcx]
0x180072777  jnb     short loc_1800727E6
0x180072779  xor     ecx, ecx
0x18007277b  lea     rdx, [rbp+var_30]
0x18007277f  mov     [rbp+var_20], rcx
0x180072783  mov     ecx, eax
0x180072785  movups  [rbp+var_30], xmm0
0x180072789  call    cs:__imp_GdiGetEntry
0x18007278f  test    eax, eax
0x180072791  js      short loc_1800727E6
0x180072793  cmp     byte ptr [rbp+var_30+0Eh], 1
0x180072797  jnz     short loc_1800727E6
0x180072799  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x18007279d  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x1800727a1  shl     cx, 8
0x1800727a5  or      cx, ax
0x1800727a8  mov     eax, esi
0x1800727aa  shr     eax, 10h
0x1800727ad  cmp     cx, ax
0x1800727b0  jnz     short loc_1800727E6
0x1800727b2  mov     rax, cs:__imp_gW32PID
0x1800727b9  mov     ecx, dword ptr [rbp+var_30+8]
0x1800727bc  and     ecx, 0FFFFFFFEh
0x1800727bf  cmp     ecx, [rax]
0x1800727c1  jnz     short loc_1800727E6
0x1800727c3  mov     rdx, [rbp+var_20]
0x1800727c7  test    rdx, rdx
0x1800727ca  jz      short loc_1800727E6
0x1800727cc  mov     rax, cs:__imp_gCookie
0x1800727d3  mov     ecx, ebx
0x1800727d5  mov     r15, [rax]
0x1800727d8  mov     eax, r15d
0x1800727db  and     eax, 3Fh
0x1800727de  sub     ecx, eax
0x1800727e0  ror     rdx, cl
0x1800727e3  xor     r15, rdx
0x1800727e6  mov     rcx, rsi
0x1800727e9  call    HANDLE_TO_INDEX
0x1800727ee  mov     ecx, eax
0x1800727f0  lea     rdx, [rbp+var_18]
0x1800727f4  call    cs:__imp_GdiGetEntry
0x1800727fa  test    eax, eax
0x1800727fc  js      loc_18007295A
0x180072802  xor     r14d, r14d
0x180072805  test    rdi, rdi
0x180072808  jz      loc_180072891
0x18007280e  mov     rcx, rdi
0x180072811  call    HANDLE_TO_INDEX
0x180072816  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18007281d  cmp     eax, [rcx]
0x18007281f  jnb     short loc_180072891
0x180072821  xor     ecx, ecx
0x180072823  lea     rdx, [rbp+var_30]
0x180072827  mov     [rbp+var_20], rcx
0x18007282b  xorps   xmm0, xmm0
0x18007282e  mov     ecx, eax
0x180072830  movups  [rbp+var_30], xmm0
0x180072834  call    cs:__imp_GdiGetEntry
0x18007283a  test    eax, eax
0x18007283c  js      short loc_180072891
0x18007283e  cmp     byte ptr [rbp+var_30+0Eh], 4
0x180072842  jnz     short loc_180072891
0x180072844  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x180072848  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x18007284c  shl     cx, 8
0x180072850  or      cx, ax
0x180072853  mov     eax, edi
0x180072855  shr     eax, 10h
0x180072858  cmp     cx, ax
0x18007285b  jnz     short loc_180072891
0x18007285d  mov     rax, cs:__imp_gW32PID
0x180072864  mov     edx, dword ptr [rbp+var_30+8]
0x180072867  and     edx, 0FFFFFFFEh
0x18007286a  cmp     edx, [rax]
0x18007286c  jnz     short loc_180072891
0x18007286e  mov     rdx, [rbp+var_20]
0x180072872  test    rdx, rdx
0x180072875  jz      short loc_180072891
0x180072877  mov     rax, cs:__imp_gCookie
0x18007287e  mov     r14, [rax]
0x180072881  mov     eax, r14d
0x180072884  and     eax, 3Fh
0x180072887  sub     ebx, eax
0x180072889  mov     cl, bl
0x18007288b  ror     rdx, cl
0x18007288e  xor     r14, rdx
0x180072891  mov     rbx, gs:30h
0x18007289a  mov     rax, [rbx+2F8h]
0x1800728a1  test    rax, rax
0x1800728a4  jz      short loc_1800728AB
0x1800728a6  cmp     rax, rsi
0x1800728a9  jnz     short loc_180072913
0x1800728ab  mov     ecx, [rbx+2F0h]
0x1800728b1  mov     eax, ecx
0x1800728b3  and     eax, 3FFFFFFFh
0x1800728b8  add     eax, 18h
0x1800728bb  cmp     eax, 4D8h
0x1800728c0  ja      short loc_180072913
0x1800728c2  test    r15, r15
0x1800728c5  jz      short loc_180072913
0x1800728c7  test    byte ptr [r15], 1
0x1800728cb  jnz     short loc_180072913
0x1800728cd  bt      ecx, 1Eh
0x1800728d1  jnb     short loc_1800728DD
0x1800728d3  mov     ecx, 5
0x1800728d8  call    TraceLoggingGdiBatchInProcessing
0x1800728dd  mov     edx, [rbx+2F0h]
0x1800728e3  and     edx, 3FFFFFFFh
0x1800728e9  mov     dword ptr [rdx+rbx+300h], 50018h
0x1800728f4  test    rdi, rdi
0x1800728f7  jnz     short loc_18007295E
0x1800728f9  mov     al, byte ptr [rbp+var_18+0Fh]
0x1800728fc  xor     r13d, r13d
0x1800728ff  and     al, 4
0x180072901  jnz     short loc_180072907
0x180072903  mov     r13d, [r15+74h]
0x180072907  lea     rcx, [r14+10h]
0x18007290b  test    al, al
0x18007290d  jz      loc_1800729AB
0x180072913  mov     r8d, [rbp+arg_10]
0x180072917  mov     rdx, rdi
0x18007291a  mov     rcx, rsi
0x18007291d  call    cs:__imp_NtGdiExtSelectClipRgn
0x180072923  mov     r13d, eax
0x180072926  test    r12, r12
0x180072929  jz      short loc_180072934
0x18007292b  mov     rcx, r12; ho
0x18007292e  call    cs:__imp_DeleteObject
0x180072934  mov     eax, r13d
0x180072937  mov     rbx, [rsp+50h+arg_8]
0x18007293f  add     rsp, 50h
0x180072943  pop     r15
0x180072945  pop     r14
0x180072947  pop     r13
0x180072949  pop     r12
0x18007294b  pop     rdi
0x18007294c  pop     rsi
0x18007294d  pop     rbp
0x18007294e  retn
0x18007294f  mov     ecx, 6
0x180072954  call    cs:__imp_GdiSetLastError
0x18007295a  xor     eax, eax
0x18007295c  jmp     short loc_180072937
0x18007295e  test    r14, r14
0x180072961  jz      short loc_180072913
0x180072963  cmp     [r14+4], r13d
0x180072967  jnz     short loc_180072913
0x180072969  test    byte ptr [r14], 1
0x18007296d  jnz     short loc_180072913
0x18007296f  test    byte ptr [rbp+var_18+0Fh], 4
0x180072973  jnz     short loc_180072913
0x180072975  lea     rcx, [r14+10h]
0x180072979  mov     eax, [rcx]
0x18007297b  cmp     [r15+78h], eax
0x18007297f  jge     short loc_1800729A5
0x180072981  mov     eax, [r14+14h]
0x180072985  cmp     [r15+7Ch], eax
0x180072989  jge     short loc_1800729A5
0x18007298b  mov     eax, [r14+8]
0x18007298f  cmp     [r15+80h], eax
0x180072996  jle     short loc_1800729A5
0x180072998  mov     eax, [r14+0Ch]
0x18007299c  cmp     [r15+84h], eax
0x1800729a3  jg      short loc_1800729B7
0x1800729a5  mov     r13d, 1
0x1800729ab  test    rdi, rdi
0x1800729ae  jnz     short loc_1800729B7
0x1800729b0  mov     eax, 8000005h
0x1800729b5  jmp     short loc_1800729E4
0x1800729b7  mov     eax, [r14+8]
0x1800729bb  mov     [rdx+rbx+308h], eax
0x1800729c2  mov     eax, [r14+0Ch]
0x1800729c6  mov     [rdx+rbx+30Ch], eax
0x1800729cd  mov     eax, [rcx]
0x1800729cf  mov     [rdx+rbx+310h], eax
0x1800729d6  mov     eax, [r14+14h]
0x1800729da  mov     [rdx+rbx+314h], eax
0x1800729e1  mov     eax, [rbp+arg_10]
0x1800729e4  mov     [rdx+rbx+304h], eax
0x1800729eb  test    rsi, rsi
0x1800729ee  jz      short loc_180072A1A
0x1800729f0  mov     [rbx+2F8h], rsi
0x1800729f7  movzx   ecx, word ptr [rdx+rbx+302h]
0x1800729ff  test    ecx, ecx
0x180072a01  jz      short loc_180072A12
0x180072a03  sub     ecx, 1
0x180072a06  jz      short loc_180072A12
0x180072a08  sub     ecx, 1
0x180072a0b  jz      short loc_180072A12
0x180072a0d  cmp     ecx, 1
0x180072a10  jnz     short loc_180072A1A
0x180072a12  bts     dword ptr [rbx+2F0h], 1Fh
0x180072a1a  mov     eax, [rbx+2F0h]
0x180072a20  movzx   ecx, word ptr [rdx+rbx+300h]
0x180072a28  inc     dword ptr [rbx+1740h]
0x180072a2e  add     ecx, 7
0x180072a31  and     ecx, 0FFFFFFF8h
0x180072a34  add     ecx, eax
0x180072a36  xor     ecx, eax
0x180072a38  and     ecx, 3FFFFFFFh
0x180072a3e  xor     ecx, eax
0x180072a40  mov     rax, cs:__imp_GdiBatchLimit
0x180072a47  mov     [rbx+2F0h], ecx
0x180072a4d  mov     ecx, [rbx+1740h]
0x180072a53  cmp     ecx, [rax]
0x180072a55  jb      loc_180072926
0x180072a5b  call    cs:__imp_NtGdiFlush
0x180072a61  jmp     loc_180072926
```
