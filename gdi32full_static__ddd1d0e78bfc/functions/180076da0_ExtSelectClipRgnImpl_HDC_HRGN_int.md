# ExtSelectClipRgnImpl(HDC__ *,HRGN__ *,int)

- ea: `0x180076da0`
- end: `0x180077197`
- name: `?ExtSelectClipRgnImpl@@YAHPEAUHDC__@@PEAUHRGN__@@H@Z`
- size: `1015`
- prototype: `__int64 __fastcall(HDC hdc, HRGN, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000e3e0`
- `0x1800473e4`
- `0x18005f820`
- `0x1800729a4`
- `0x1800756cc`
- `0x180076da0`
- `0x1800a6370`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180076e8f`
- `GDI32!GdiGetEntry` at `0x180076f00`
- `GDI32!GdiGetEntry` at `0x180076f46`
- `GDI32!GdiGetEntry` at `0x180076e8f`
- `GDI32!GdiGetEntry` at `0x180076f00`
- `GDI32!GdiGetEntry` at `0x180076f46`
- `GDI32!GdiBatchLimit` at `0x18007716b`
- `GDI32!gW32PID` at `0x180076ebe`
- `GDI32!gW32PID` at `0x180076f75`
- `GDI32!gCookie` at `0x180076ed8`
- `GDI32!gCookie` at `0x180076f8f`
- `GDI32!gMaxGdiHandleCount` at `0x180076e6d`
- `GDI32!gMaxGdiHandleCount` at `0x180076f28`
- `GDI32!pldcGet` at `0x180076ded`
- `GDI32!pldcGet` at `0x180076ded`
- `GDI32!GdiSetLastError` at `0x180077079`
- `GDI32!GdiSetLastError` at `0x180077079`
- `GDI32!DeleteObject` at `0x18007704c`
- `GDI32!DeleteObject` at `0x18007704c`
- `win32u!NtGdiExtSelectClipRgn` at `0x180077035`
- `win32u!NtGdiExtSelectClipRgn` at `0x180077035`
- `win32u!NtGdiFlush` at `0x180077186`
- `win32u!NtGdiFlush` at `0x180077186`

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
0x180076da0  mov     [rsp-38h+arg_8], rbx
0x180076da5  mov     [rsp-38h+arg_10], r8d
0x180076daa  push    rbp
0x180076dab  push    rsi
0x180076dac  push    rdi
0x180076dad  push    r12
0x180076daf  push    r13
0x180076db1  push    r14
0x180076db3  push    r15
0x180076db5  mov     rbp, rsp
0x180076db8  sub     rsp, 50h
0x180076dbc  xor     r12d, r12d
0x180076dbf  mov     eax, ecx
0x180076dc1  and     eax, 7F0000h
0x180076dc6  mov     [rbp+arg_0], r12
0x180076dca  mov     rdi, rdx
0x180076dcd  mov     rsi, rcx
0x180076dd0  lea     r13d, [r12+2]
0x180076dd5  cmp     eax, 10000h
0x180076dda  jz      short loc_180076E1F
0x180076ddc  cmp     eax, 660000h
0x180076de1  jnz     short loc_180076DED
0x180076de3  call    MF16_SelectClipRgn
0x180076de8  jmp     loc_18007705B
0x180076ded  call    cs:__imp_pldcGet
0x180076df4  nop     dword ptr [rax+rax+00h]
0x180076df9  test    rax, rax
0x180076dfc  jz      loc_180077074
0x180076e02  cmp     [rax+0Ch], r13d
0x180076e06  jnz     short loc_180076E1F
0x180076e08  mov     r8d, [rbp+arg_10]
0x180076e0c  mov     rdx, rdi
0x180076e0f  mov     rcx, rsi
0x180076e12  call    MF_ExtSelectClipRgn
0x180076e17  test    eax, eax
0x180076e19  jz      loc_180077085
0x180076e1f  test    rdi, rdi
0x180076e22  jz      short loc_180076E4E
0x180076e24  mov     rcx, rsi; hdc
0x180076e27  call    GetLayout
0x180076e2c  test    al, 1
0x180076e2e  jz      short loc_180076E4E
0x180076e30  lea     r8, [rbp+arg_0]
0x180076e34  mov     rdx, rdi
0x180076e37  mov     rcx, rsi
0x180076e3a  call    MirrorRgnDC
0x180076e3f  mov     r12, [rbp+arg_0]
0x180076e43  test    eax, eax
0x180076e45  jz      short loc_180076E4E
0x180076e47  test    r12, r12
0x180076e4a  cmovnz  rdi, r12
0x180076e4e  cmp     [rbp+arg_10], 5
0x180076e52  jnz     loc_18007702B
0x180076e58  xor     eax, eax
0x180076e5a  xorps   xmm0, xmm0
0x180076e5d  mov     rcx, rsi
0x180076e60  mov     [rbp+var_8], rax
0x180076e64  movups  [rbp+var_18], xmm0
0x180076e68  call    HANDLE_TO_INDEX
0x180076e6d  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180076e74  xor     r15d, r15d
0x180076e77  lea     ebx, [r15+40h]
0x180076e7b  cmp     eax, [rcx]
0x180076e7d  jnb     short loc_180076EF2
0x180076e7f  xor     ecx, ecx
0x180076e81  lea     rdx, [rbp+var_30]
0x180076e85  mov     [rbp+var_20], rcx
0x180076e89  mov     ecx, eax
0x180076e8b  movups  [rbp+var_30], xmm0
0x180076e8f  call    cs:__imp_GdiGetEntry
0x180076e96  nop     dword ptr [rax+rax+00h]
0x180076e9b  test    eax, eax
0x180076e9d  js      short loc_180076EF2
0x180076e9f  cmp     byte ptr [rbp+var_30+0Eh], 1
0x180076ea3  jnz     short loc_180076EF2
0x180076ea5  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x180076ea9  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x180076ead  shl     cx, 8
0x180076eb1  or      cx, ax
0x180076eb4  mov     eax, esi
0x180076eb6  shr     eax, 10h
0x180076eb9  cmp     cx, ax
0x180076ebc  jnz     short loc_180076EF2
0x180076ebe  mov     rax, cs:__imp_gW32PID
0x180076ec5  mov     ecx, dword ptr [rbp+var_30+8]
0x180076ec8  and     ecx, 0FFFFFFFEh
0x180076ecb  cmp     ecx, [rax]
0x180076ecd  jnz     short loc_180076EF2
0x180076ecf  mov     rdx, [rbp+var_20]
0x180076ed3  test    rdx, rdx
0x180076ed6  jz      short loc_180076EF2
0x180076ed8  mov     rax, cs:__imp_gCookie
0x180076edf  mov     ecx, ebx
0x180076ee1  mov     r15, [rax]
0x180076ee4  mov     eax, r15d
0x180076ee7  and     eax, 3Fh
0x180076eea  sub     ecx, eax
0x180076eec  ror     rdx, cl
0x180076eef  xor     r15, rdx
0x180076ef2  mov     rcx, rsi
0x180076ef5  call    HANDLE_TO_INDEX
0x180076efa  mov     ecx, eax
0x180076efc  lea     rdx, [rbp+var_18]
0x180076f00  call    cs:__imp_GdiGetEntry
0x180076f07  nop     dword ptr [rax+rax+00h]
0x180076f0c  test    eax, eax
0x180076f0e  js      loc_180077085
0x180076f14  xor     r14d, r14d
0x180076f17  test    rdi, rdi
0x180076f1a  jz      loc_180076FA9
0x180076f20  mov     rcx, rdi
0x180076f23  call    HANDLE_TO_INDEX
0x180076f28  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180076f2f  cmp     eax, [rcx]
0x180076f31  jnb     short loc_180076FA9
0x180076f33  xor     ecx, ecx
0x180076f35  lea     rdx, [rbp+var_30]
0x180076f39  mov     [rbp+var_20], rcx
0x180076f3d  xorps   xmm0, xmm0
0x180076f40  mov     ecx, eax
0x180076f42  movups  [rbp+var_30], xmm0
0x180076f46  call    cs:__imp_GdiGetEntry
0x180076f4d  nop     dword ptr [rax+rax+00h]
0x180076f52  test    eax, eax
0x180076f54  js      short loc_180076FA9
0x180076f56  cmp     byte ptr [rbp+var_30+0Eh], 4
0x180076f5a  jnz     short loc_180076FA9
0x180076f5c  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x180076f60  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x180076f64  shl     cx, 8
0x180076f68  or      cx, ax
0x180076f6b  mov     eax, edi
0x180076f6d  shr     eax, 10h
0x180076f70  cmp     cx, ax
0x180076f73  jnz     short loc_180076FA9
0x180076f75  mov     rax, cs:__imp_gW32PID
0x180076f7c  mov     edx, dword ptr [rbp+var_30+8]
0x180076f7f  and     edx, 0FFFFFFFEh
0x180076f82  cmp     edx, [rax]
0x180076f84  jnz     short loc_180076FA9
0x180076f86  mov     rdx, [rbp+var_20]
0x180076f8a  test    rdx, rdx
0x180076f8d  jz      short loc_180076FA9
0x180076f8f  mov     rax, cs:__imp_gCookie
0x180076f96  mov     r14, [rax]
0x180076f99  mov     eax, r14d
0x180076f9c  and     eax, 3Fh
0x180076f9f  sub     ebx, eax
0x180076fa1  mov     cl, bl
0x180076fa3  ror     rdx, cl
0x180076fa6  xor     r14, rdx
0x180076fa9  mov     rbx, gs:30h
0x180076fb2  mov     rax, [rbx+2F8h]
0x180076fb9  test    rax, rax
0x180076fbc  jz      short loc_180076FC3
0x180076fbe  cmp     rax, rsi
0x180076fc1  jnz     short loc_18007702B
0x180076fc3  mov     ecx, [rbx+2F0h]
0x180076fc9  mov     eax, ecx
0x180076fcb  and     eax, 3FFFFFFFh
0x180076fd0  add     eax, 18h
0x180076fd3  cmp     eax, 4D8h
0x180076fd8  ja      short loc_18007702B
0x180076fda  test    r15, r15
0x180076fdd  jz      short loc_18007702B
0x180076fdf  test    byte ptr [r15], 1
0x180076fe3  jnz     short loc_18007702B
0x180076fe5  bt      ecx, 1Eh
0x180076fe9  jnb     short loc_180076FF5
0x180076feb  mov     ecx, 5
0x180076ff0  call    TraceLoggingGdiBatchInProcessing
0x180076ff5  mov     edx, [rbx+2F0h]
0x180076ffb  and     edx, 3FFFFFFFh
0x180077001  mov     dword ptr [rdx+rbx+300h], 50018h
0x18007700c  test    rdi, rdi
0x18007700f  jnz     short loc_180077089
0x180077011  mov     al, byte ptr [rbp+var_18+0Fh]
0x180077014  xor     r13d, r13d
0x180077017  and     al, 4
0x180077019  jnz     short loc_18007701F
0x18007701b  mov     r13d, [r15+74h]
0x18007701f  lea     rcx, [r14+10h]
0x180077023  test    al, al
0x180077025  jz      loc_1800770D6
0x18007702b  mov     r8d, [rbp+arg_10]
0x18007702f  mov     rdx, rdi
0x180077032  mov     rcx, rsi
0x180077035  call    cs:__imp_NtGdiExtSelectClipRgn
0x18007703c  nop     dword ptr [rax+rax+00h]
0x180077041  mov     r13d, eax
0x180077044  test    r12, r12
0x180077047  jz      short loc_180077058
0x180077049  mov     rcx, r12; ho
0x18007704c  call    cs:__imp_DeleteObject
0x180077053  nop     dword ptr [rax+rax+00h]
0x180077058  mov     eax, r13d
0x18007705b  mov     rbx, [rsp+50h+arg_8]
0x180077063  add     rsp, 50h
0x180077067  pop     r15
0x180077069  pop     r14
0x18007706b  pop     r13
0x18007706d  pop     r12
0x18007706f  pop     rdi
0x180077070  pop     rsi
0x180077071  pop     rbp
0x180077072  retn
0x180077074  mov     ecx, 6
0x180077079  call    cs:__imp_GdiSetLastError
0x180077080  nop     dword ptr [rax+rax+00h]
0x180077085  xor     eax, eax
0x180077087  jmp     short loc_18007705B
0x180077089  test    r14, r14
0x18007708c  jz      short loc_18007702B
0x18007708e  cmp     [r14+4], r13d
0x180077092  jnz     short loc_18007702B
0x180077094  test    byte ptr [r14], 1
0x180077098  jnz     short loc_18007702B
0x18007709a  test    byte ptr [rbp+var_18+0Fh], 4
0x18007709e  jnz     short loc_18007702B
0x1800770a0  lea     rcx, [r14+10h]
0x1800770a4  mov     eax, [rcx]
0x1800770a6  cmp     [r15+78h], eax
0x1800770aa  jge     short loc_1800770D0
0x1800770ac  mov     eax, [r14+14h]
0x1800770b0  cmp     [r15+7Ch], eax
0x1800770b4  jge     short loc_1800770D0
0x1800770b6  mov     eax, [r14+8]
0x1800770ba  cmp     [r15+80h], eax
0x1800770c1  jle     short loc_1800770D0
0x1800770c3  mov     eax, [r14+0Ch]
0x1800770c7  cmp     [r15+84h], eax
0x1800770ce  jg      short loc_1800770E2
0x1800770d0  mov     r13d, 1
0x1800770d6  test    rdi, rdi
0x1800770d9  jnz     short loc_1800770E2
0x1800770db  mov     eax, 8000005h
0x1800770e0  jmp     short loc_18007710F
0x1800770e2  mov     eax, [r14+8]
0x1800770e6  mov     [rdx+rbx+308h], eax
0x1800770ed  mov     eax, [r14+0Ch]
0x1800770f1  mov     [rdx+rbx+30Ch], eax
0x1800770f8  mov     eax, [rcx]
0x1800770fa  mov     [rdx+rbx+310h], eax
0x180077101  mov     eax, [r14+14h]
0x180077105  mov     [rdx+rbx+314h], eax
0x18007710c  mov     eax, [rbp+arg_10]
0x18007710f  mov     [rdx+rbx+304h], eax
0x180077116  test    rsi, rsi
0x180077119  jz      short loc_180077145
0x18007711b  mov     [rbx+2F8h], rsi
0x180077122  movzx   ecx, word ptr [rdx+rbx+302h]
0x18007712a  test    ecx, ecx
0x18007712c  jz      short loc_18007713D
0x18007712e  sub     ecx, 1
0x180077131  jz      short loc_18007713D
0x180077133  sub     ecx, 1
0x180077136  jz      short loc_18007713D
0x180077138  cmp     ecx, 1
0x18007713b  jnz     short loc_180077145
0x18007713d  bts     dword ptr [rbx+2F0h], 1Fh
0x180077145  mov     eax, [rbx+2F0h]
0x18007714b  movzx   ecx, word ptr [rdx+rbx+300h]
0x180077153  inc     dword ptr [rbx+1740h]
0x180077159  add     ecx, 7
0x18007715c  and     ecx, 0FFFFFFF8h
0x18007715f  add     ecx, eax
0x180077161  xor     ecx, eax
0x180077163  and     ecx, 3FFFFFFFh
0x180077169  xor     ecx, eax
0x18007716b  mov     rax, cs:__imp_GdiBatchLimit
0x180077172  mov     [rbx+2F0h], ecx
0x180077178  mov     ecx, [rbx+1740h]
0x18007717e  cmp     ecx, [rax]
0x180077180  jb      loc_180077044
0x180077186  call    cs:__imp_NtGdiFlush
0x18007718d  nop     dword ptr [rax+rax+00h]
0x180077192  jmp     loc_180077044
```
