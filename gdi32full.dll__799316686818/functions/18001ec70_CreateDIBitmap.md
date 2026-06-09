# CreateDIBitmap

- ea: `0x18001ec70`
- end: `0x18001f05d`
- name: `CreateDIBitmap`
- size: `1005`
- prototype: `HBITMAP __stdcall(HDC hdc, const BITMAPINFOHEADER *pbmih, DWORD flInit, const void *pjBits, const BITMAPINFO *pbmi, UINT iUsage)`
- caller_count: `9`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e6a0`
- `0x180022230`
- `0x1800400d0`
- `0x180059230`
- `0x1800684d0`
- `0x180087f90`
- `0x180090360`
- `0x1800908c0`
- `0x180091990`

## callees

- `0x18001d4fc`
- `0x18001ec70`
- `0x1800205b8`
- `0x180025090`
- `0x180026cf0`
- `0x180032a24`
- `0x180032ba0`
- `0x18003e184`
- `0x1800710c4`
- `0x1800a3514`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18001ecee`
- `GDI32!GdiGetEntry` at `0x18001ecee`
- `GDI32!gW32PID` at `0x18001ed17`
- `GDI32!gCookie` at `0x18001ed31`
- `GDI32!gMaxGdiHandleCount` at `0x18001ecce`
- `ntdll!RtlFreeHeap` at `0x18001ef22`
- `ntdll!RtlFreeHeap` at `0x18001ef4f`
- `ntdll!RtlFreeHeap` at `0x18001f012`
- `ntdll!RtlFreeHeap` at `0x18001f035`
- `ntdll!RtlFreeHeap` at `0x18001ef22`
- `ntdll!RtlFreeHeap` at `0x18001ef4f`
- `ntdll!RtlFreeHeap` at `0x18001f012`
- `ntdll!RtlFreeHeap` at `0x18001f035`
- `ntdll!RtlAllocateHeap` at `0x18001ee3b`
- `ntdll!RtlAllocateHeap` at `0x18001ee3b`
- `win32u!NtGdiCreateDIBitmapInternal` at `0x18001efce`
- `win32u!NtGdiCreateDIBitmapInternal` at `0x18001efce`

## pseudocode

```c
HBITMAP __stdcall CreateDIBitmap(
        HDC hdc,
        const BITMAPINFOHEADER *pbmih,
        DWORD flInit,
        const void *pjBits,
        const BITMAPINFO *pbmi,
        UINT iUsage)
{
  __int64 v7; // r14
  DWORD v8; // esi
  __int16 v10; // ebx^2
  __int64 v11; // r15
  unsigned int v12; // eax
  _DWORD *v13; // r11
  __int64 v14; // r13
  unsigned __int64 biWidth_high; // rdx
  BITMAPINFO *v16; // rbx
  DWORD v17; // r8d
  const void *v18; // r9
  bool v19; // zf
  unsigned int v20; // ecx
  HDC DIBitmapInternal; // rsi
  LONG biWidth_low; // eax
  HDC StockObject; // rax
  void *v24; // rdi
  __int64 v25; // r15
  unsigned int v26; // r15d
  PVOID Heap; // rax
  int v28; // eax
  _DWORD *v29; // rdx
  void *v30; // r14
  BITMAPINFO *v31; // r14
  int v32; // ecx
  SIZE_T Size; // [rsp+78h] [rbp-39h]
  unsigned int v35; // [rsp+80h] [rbp-31h]
  int v36; // [rsp+88h] [rbp-29h] BYREF
  _DWORD *v37; // [rsp+90h] [rbp-21h] BYREF
  __int64 v38; // [rsp+98h] [rbp-19h]
  __int64 v39; // [rsp+A0h] [rbp-11h]
  BITMAPINFO *v40; // [rsp+A8h] [rbp-9h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-1h] BYREF
  __int64 v42; // [rsp+C0h] [rbp+Fh]
  int v44; // [rsp+110h] [rbp+5Fh] BYREF
  DWORD v45; // [rsp+118h] [rbp+67h]

  v45 = flInit;
  v44 = 0;
  v7 = 0;
  Size = 0;
  v8 = flInit;
  v35 = 0;
  v10 = WORD1(hdc);
  v39 = 0;
  v11 = -1;
  v38 = 0;
  v12 = HANDLE_TO_INDEX(hdc);
  v37 = v13;
  LODWORD(v14) = (_DWORD)v13 + 1;
  if ( v12 < gMaxGdiHandleCount )
  {
    v41 = 0;
    v42 = 0;
    if ( (int)GdiGetEntry(v12, &v41) >= 0
      && BYTE14(v41) == (_BYTE)v14
      && WORD6(v41) == v10
      && (DWORD2(v41) & 0xFFFFFFFE) == gW32PID
      && v42 )
    {
      v37 = (_DWORD *)(gCookie ^ __ROR8__(v42, 64 - (gCookie & 0x3Fu)));
      v8 = v45;
    }
  }
  v16 = (BITMAPINFO *)pbmiConvertInfo(pbmi, iUsage, &v44, 0);
  if ( (v8 & 2) == 0 )
  {
    if ( (v8 & 4) != 0 )
    {
      if ( !pjBits )
      {
        v45 = v8 & 0xFFFFFFFB;
        goto LABEL_20;
      }
      v19 = v44 == 0;
      goto LABEL_17;
    }
LABEL_19:
    pjBits = 0;
    goto LABEL_20;
  }
  pbmih = &pbmi->bmiHeader;
  if ( !v44 )
  {
LABEL_10:
    v11 = 0;
    goto LABEL_20;
  }
  if ( (v8 & 4) == 0 )
    goto LABEL_19;
  v19 = pjBits == 0;
LABEL_17:
  if ( v19 )
    goto LABEL_10;
  LODWORD(Size) = GdiGetBitmapBitsSizeSpecificHeight(v16, 0);
LABEL_20:
  v20 = Size;
  DIBitmapInternal = 0;
  if ( (_DWORD)Size != -1 )
    DIBitmapInternal = (HDC)v11;
  if ( v16 && v16->bmiHeader.biSize >= 0x28 && v16->bmiHeader.biCompression - 4 <= (unsigned int)v14 )
    DIBitmapInternal = 0;
  if ( pbmih )
  {
    if ( pbmih->biSize < 0x28 )
    {
      biWidth_low = LOWORD(pbmih->biWidth);
      biWidth_high = HIWORD(pbmih->biWidth);
    }
    else
    {
      biWidth_low = pbmih->biWidth;
      biWidth_high = (unsigned int)pbmih->biHeight;
    }
    HIDWORD(Size) = biWidth_high;
    v35 = biWidth_low;
    if ( !biWidth_low || !(_DWORD)biWidth_high )
    {
      StockObject = (HDC)GetStockObject(21);
      v20 = Size;
      DIBitmapInternal = StockObject;
    }
  }
  if ( DIBitmapInternal == (HDC)-1LL )
  {
    v24 = 0;
    v25 = 0;
    if ( ((unsigned __int8)pjBits & 3) != 0 )
    {
      v26 = v20;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      v24 = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, pjBits, v26);
        pjBits = v24;
      }
      v25 = 0;
    }
    if ( v37 )
    {
      v28 = v37[60];
      if ( (v28 & 3) != 0 && (v28 & 0x10) == 0 && iUsage != (_DWORD)v14 && pjBits && v16 )
      {
        v29 = v37;
        v37 = 0;
        v40 = 0;
        v36 = 0;
        if ( (unsigned int)IcmTranslateDIB(hdc, v29, (unsigned int)Size, pjBits, &v37, v16, &v40, &v36, -1) )
        {
          v30 = v37;
          if ( v37 )
          {
            if ( v24 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
            v24 = v30;
            pjBits = v30;
          }
          v31 = v40;
          if ( !v40 )
            goto LABEL_53;
          if ( v16 != pbmi )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
          v16 = v31;
          LODWORD(Size) = GdiGetBitmapBitsSizeSpecificHeight(v31, 0);
          v32 = v36;
          v14 = (_DWORD)Size != -1;
          if ( !v36 )
LABEL_53:
            v32 = v44;
          v7 = v38;
          if ( v38 )
            v25 = *(_QWORD *)(v38 + 40);
          if ( !(_DWORD)v14 )
            goto LABEL_61;
          goto LABEL_60;
        }
        v7 = v38;
      }
    }
    v32 = v44;
LABEL_60:
    DIBitmapInternal = (HDC)NtGdiCreateDIBitmapInternal(
                              hdc,
                              v35,
                              HIDWORD(Size),
                              v45,
                              pjBits,
                              v16,
                              iUsage,
                              v32,
                              Size,
                              0,
                              v25);
LABEL_61:
    if ( v39 )
    {
      if ( v7 )
        IcmDeleteColorTransform(v7, 0);
      IcmReleaseColorSpace(0, v39, 0);
    }
    if ( v24 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
  }
  if ( v16 && v16 != pbmi )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
  return GdiTrackHCreate(DIBitmapInternal, (const BITMAPINFOHEADER *)biWidth_high, v17, v18, pbmi, iUsage);
}

```

## disassembly

```asm
0x18001ec70  mov     rax, rsp
0x18001ec73  mov     [rax+20h], rbx
0x18001ec77  mov     [rax+18h], r8d
0x18001ec7b  mov     [rax+8], rcx
0x18001ec7f  push    rbp
0x18001ec80  push    rsi
0x18001ec81  push    rdi
0x18001ec82  push    r12
0x18001ec84  push    r13
0x18001ec86  push    r14
0x18001ec88  push    r15
0x18001ec8a  lea     rbp, [rax-4Fh]
0x18001ec8e  sub     rsp, 0C0h
0x18001ec95  xor     r11d, r11d
0x18001ec98  mov     r12, r9
0x18001ec9b  mov     [rbp+47h+arg_8], r11d
0x18001ec9f  mov     r14d, r11d
0x18001eca2  mov     dword ptr [rbp+47h+Size], r11d
0x18001eca6  mov     esi, r8d
0x18001eca9  mov     [rbp+47h+var_78], r11d
0x18001ecad  mov     rdi, rdx
0x18001ecb0  mov     dword ptr [rbp+47h+Size+4], r11d
0x18001ecb4  mov     rbx, rcx
0x18001ecb7  mov     [rbp+47h+var_58], r11
0x18001ecbb  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001ecbf  mov     [rbp+47h+var_60], r11
0x18001ecc3  call    HANDLE_TO_INDEX
0x18001ecc8  mov     ecx, eax
0x18001ecca  mov     [rbp+47h+var_68], r11
0x18001ecce  mov     rax, cs:__imp_gMaxGdiHandleCount
0x18001ecd5  lea     r13d, [r11+1]
0x18001ecd9  cmp     ecx, [rax]
0x18001ecdb  jnb     short loc_18001ED56
0x18001ecdd  xorps   xmm0, xmm0
0x18001ece0  lea     rdx, [rbp+47h+var_48]
0x18001ece4  xor     eax, eax
0x18001ece6  movups  [rbp+47h+var_48], xmm0
0x18001ecea  mov     [rbp+47h+var_38], rax
0x18001ecee  call    cs:__imp_GdiGetEntry
0x18001ecf4  test    eax, eax
0x18001ecf6  js      short loc_18001ED56
0x18001ecf8  cmp     byte ptr [rbp+47h+var_48+0Eh], r13b
0x18001ecfc  jnz     short loc_18001ED56
0x18001ecfe  movzx   eax, byte ptr [rbp+47h+var_48+0Ch]
0x18001ed02  movzx   ecx, byte ptr [rbp+47h+var_48+0Dh]
0x18001ed06  shl     cx, 8
0x18001ed0a  or      cx, ax
0x18001ed0d  mov     eax, ebx
0x18001ed0f  shr     eax, 10h
0x18001ed12  cmp     cx, ax
0x18001ed15  jnz     short loc_18001ED56
0x18001ed17  mov     rax, cs:__imp_gW32PID
0x18001ed1e  mov     ecx, dword ptr [rbp+47h+var_48+8]
0x18001ed21  and     ecx, 0FFFFFFFEh
0x18001ed24  cmp     ecx, [rax]
0x18001ed26  jnz     short loc_18001ED56
0x18001ed28  mov     r8, [rbp+47h+var_38]
0x18001ed2c  test    r8, r8
0x18001ed2f  jz      short loc_18001ED56
0x18001ed31  mov     rax, cs:__imp_gCookie
0x18001ed38  lea     ecx, [r14+40h]
0x18001ed3c  mov     rsi, r8
0x18001ed3f  mov     rdx, [rax]
0x18001ed42  mov     eax, edx
0x18001ed44  and     eax, 3Fh
0x18001ed47  sub     ecx, eax
0x18001ed49  ror     rsi, cl
0x18001ed4c  xor     rsi, rdx
0x18001ed4f  mov     [rbp+47h+var_68], rsi
0x18001ed53  mov     esi, [rbp+47h+arg_10]
0x18001ed56  mov     edx, [rbp+47h+iUsage]
0x18001ed59  lea     r8, [rbp+47h+arg_8]
0x18001ed5d  mov     rcx, [rbp+47h+pbmi]
0x18001ed61  xor     r9d, r9d
0x18001ed64  call    pbmiConvertInfo
0x18001ed69  mov     rbx, rax
0x18001ed6c  mov     eax, [rbp+47h+arg_8]
0x18001ed6f  test    sil, 2
0x18001ed73  jz      short loc_18001ED8D
0x18001ed75  mov     rdi, [rbp+47h+pbmi]
0x18001ed79  test    eax, eax
0x18001ed7b  jnz     short loc_18001ED82
0x18001ed7d  xor     r15d, r15d
0x18001ed80  jmp     short loc_18001EDB6
0x18001ed82  test    sil, 4
0x18001ed86  jz      short loc_18001EDB3
0x18001ed88  test    r12, r12
0x18001ed8b  jmp     short loc_18001EDA2
0x18001ed8d  test    sil, 4
0x18001ed91  jz      short loc_18001EDB3
0x18001ed93  test    r12, r12
0x18001ed96  jnz     short loc_18001EDA0
0x18001ed98  and     esi, 0FFFFFFFBh
0x18001ed9b  mov     [rbp+47h+arg_10], esi
0x18001ed9e  jmp     short loc_18001EDB6
0x18001eda0  test    eax, eax
0x18001eda2  jz      short loc_18001ED7D
0x18001eda4  xor     edx, edx
0x18001eda6  mov     rcx, rbx
0x18001eda9  call    GdiGetBitmapBitsSizeSpecificHeight
0x18001edae  mov     dword ptr [rbp+47h+Size], eax
0x18001edb1  jmp     short loc_18001EDB6
0x18001edb3  xor     r12d, r12d
0x18001edb6  mov     ecx, dword ptr [rbp+47h+Size]
0x18001edb9  xor     esi, esi
0x18001edbb  cmp     ecx, 0FFFFFFFFh
0x18001edbe  cmovnz  rsi, r15
0x18001edc2  test    rbx, rbx
0x18001edc5  jz      short loc_18001EDD9
0x18001edc7  cmp     dword ptr [rbx], 28h ; '('
0x18001edca  jb      short loc_18001EDD9
0x18001edcc  mov     eax, [rbx+10h]
0x18001edcf  sub     eax, 4
0x18001edd2  cmp     eax, r13d
0x18001edd5  ja      short loc_18001EDD9
0x18001edd7  xor     esi, esi
0x18001edd9  test    rdi, rdi
0x18001eddc  jz      short loc_18001EE11
0x18001edde  cmp     dword ptr [rdi], 28h ; '('
0x18001ede1  jb      short loc_18001EDEB
0x18001ede3  mov     eax, [rdi+4]
0x18001ede6  mov     edx, [rdi+8]
0x18001ede9  jmp     short loc_18001EDF3
0x18001edeb  movzx   eax, word ptr [rdi+4]
0x18001edef  movzx   edx, word ptr [rdi+6]
0x18001edf3  mov     dword ptr [rbp+47h+Size+4], edx
0x18001edf6  mov     [rbp+47h+var_78], eax
0x18001edf9  test    eax, eax
0x18001edfb  jz      short loc_18001EE01
0x18001edfd  test    edx, edx
0x18001edff  jnz     short loc_18001EE11
0x18001ee01  mov     ecx, 15h; i
0x18001ee06  call    GetStockObject
0x18001ee0b  mov     ecx, dword ptr [rbp+47h+Size]
0x18001ee0e  mov     rsi, rax
0x18001ee11  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001ee15  jnz     loc_18001F018
0x18001ee1b  xor     edi, edi
0x18001ee1d  xor     r15d, r15d
0x18001ee20  test    r12b, 3
0x18001ee24  jz      short loc_18001EE5D
0x18001ee26  mov     r15d, ecx
0x18001ee29  xor     edx, edx; Flags
0x18001ee2b  mov     rcx, gs:60h
0x18001ee34  mov     r8d, r15d; Size
0x18001ee37  mov     rcx, [rcx+30h]; HeapHandle
0x18001ee3b  call    cs:__imp_RtlAllocateHeap
0x18001ee41  mov     rdi, rax
0x18001ee44  test    rax, rax
0x18001ee47  jz      short loc_18001EE5A
0x18001ee49  mov     r8d, r15d; Size
0x18001ee4c  mov     rdx, r12; Src
0x18001ee4f  mov     rcx, rax; void *
0x18001ee52  call    memcpy_0
0x18001ee57  mov     r12, rdi
0x18001ee5a  mov     r15, r14
0x18001ee5d  mov     rcx, [rbp+47h+var_68]
0x18001ee61  test    rcx, rcx
0x18001ee64  jz      loc_18001EF93
0x18001ee6a  mov     eax, [rcx+0F0h]
0x18001ee70  test    al, 3
0x18001ee72  jz      loc_18001EF93
0x18001ee78  test    al, 10h
0x18001ee7a  jnz     loc_18001EF93
0x18001ee80  cmp     [rbp+47h+iUsage], r13d
0x18001ee84  jz      loc_18001EF93
0x18001ee8a  test    r12, r12
0x18001ee8d  jz      loc_18001EF93
0x18001ee93  test    rbx, rbx
0x18001ee96  jz      loc_18001EF93
0x18001ee9c  mov     r8d, dword ptr [rbp+47h+Size]
0x18001eea0  lea     rax, [rbp+47h+var_60]
0x18001eea4  mov     [rsp+60h], rax
0x18001eea9  mov     rdx, rcx
0x18001eeac  mov     rcx, [rbp+47h+arg_0]
0x18001eeb0  lea     rax, [rbp+47h+var_58]
0x18001eeb4  mov     [rsp+0F0h+var_98], rax
0x18001eeb9  mov     r9, r12
0x18001eebc  mov     dword ptr [rsp+0F0h+var_A0], r13d
0x18001eec1  lea     rax, [rbp+47h+var_70]
0x18001eec5  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x18001eecd  mov     qword ptr [rsp+0F0h+var_B8], rax
0x18001eed2  lea     rax, [rbp+47h+var_50]
0x18001eed6  mov     [rsp+0F0h+var_C0], rax
0x18001eedb  lea     rax, [rbp+47h+var_68]
0x18001eedf  mov     [rsp+0F0h+var_C8], rbx
0x18001eee4  mov     [rsp+0F0h+var_D0], rax
0x18001eee9  mov     [rbp+47h+var_68], r14
0x18001eeed  mov     [rbp+47h+var_50], r14
0x18001eef1  mov     [rbp+47h+var_70], r14d
0x18001eef5  call    IcmTranslateDIB
0x18001eefa  test    eax, eax
0x18001eefc  jz      loc_18001EF8F
0x18001ef02  mov     r14, [rbp+47h+var_68]
0x18001ef06  test    r14, r14
0x18001ef09  jz      short loc_18001EF2E
0x18001ef0b  test    rdi, rdi
0x18001ef0e  jz      short loc_18001EF28
0x18001ef10  mov     rcx, gs:60h
0x18001ef19  mov     r8, rdi; P
0x18001ef1c  xor     edx, edx; Flags
0x18001ef1e  mov     rcx, [rcx+30h]; HeapHandle
0x18001ef22  call    cs:__imp_RtlFreeHeap
0x18001ef28  mov     rdi, r14
0x18001ef2b  mov     r12, r14
0x18001ef2e  mov     r14, [rbp+47h+var_50]
0x18001ef32  test    r14, r14
0x18001ef35  jz      short loc_18001EF78
0x18001ef37  cmp     rbx, [rbp+47h+pbmi]
0x18001ef3b  jz      short loc_18001EF55
0x18001ef3d  mov     rcx, gs:60h
0x18001ef46  mov     r8, rbx; P
0x18001ef49  xor     edx, edx; Flags
0x18001ef4b  mov     rcx, [rcx+30h]; HeapHandle
0x18001ef4f  call    cs:__imp_RtlFreeHeap
0x18001ef55  xor     edx, edx
0x18001ef57  mov     rcx, r14
0x18001ef5a  mov     rbx, r14
0x18001ef5d  call    GdiGetBitmapBitsSizeSpecificHeight
0x18001ef62  xor     r13d, r13d
0x18001ef65  mov     dword ptr [rbp+47h+Size], eax
0x18001ef68  cmp     eax, 0FFFFFFFFh
0x18001ef6b  mov     eax, [rbp+47h+var_70]
0x18001ef6e  mov     ecx, eax
0x18001ef70  setnz   r13b
0x18001ef74  test    eax, eax
0x18001ef76  jnz     short loc_18001EF7B
0x18001ef78  mov     ecx, [rbp+47h+arg_8]
0x18001ef7b  mov     r14, [rbp+47h+var_60]
0x18001ef7f  test    r14, r14
0x18001ef82  jz      short loc_18001EF88
0x18001ef84  mov     r15, [r14+28h]
0x18001ef88  test    r13d, r13d
0x18001ef8b  jnz     short loc_18001EF96
0x18001ef8d  jmp     short loc_18001EFD7
0x18001ef8f  mov     r14, [rbp+47h+var_60]
0x18001ef93  mov     ecx, [rbp+47h+arg_8]
0x18001ef96  mov     eax, dword ptr [rbp+47h+Size]
0x18001ef99  mov     r9d, [rbp+47h+arg_10]
0x18001ef9d  mov     r8d, dword ptr [rbp+47h+Size+4]
0x18001efa1  mov     edx, [rbp+47h+var_78]
0x18001efa4  mov     [rsp+0F0h+var_A0], r15
0x18001efa9  mov     dword ptr [rsp+0F0h+var_A8], 0
0x18001efb1  mov     [rsp+0F0h+var_B0], eax
0x18001efb5  mov     eax, [rbp+47h+iUsage]
0x18001efb8  mov     [rsp+0F0h+var_B8], ecx
0x18001efbc  mov     rcx, [rbp+47h+arg_0]
0x18001efc0  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18001efc4  mov     [rsp+0F0h+var_C8], rbx
0x18001efc9  mov     [rsp+0F0h+var_D0], r12
0x18001efce  call    cs:__imp_NtGdiCreateDIBitmapInternal
0x18001efd4  mov     rsi, rax
0x18001efd7  cmp     [rbp+47h+var_58], 0
0x18001efdc  jz      short loc_18001EFFB
0x18001efde  test    r14, r14
0x18001efe1  jz      short loc_18001EFED
0x18001efe3  xor     edx, edx
0x18001efe5  mov     rcx, r14
0x18001efe8  call    IcmDeleteColorTransform
0x18001efed  mov     rdx, [rbp+47h+var_58]
0x18001eff1  xor     r8d, r8d
0x18001eff4  xor     ecx, ecx
0x18001eff6  call    IcmReleaseColorSpace
0x18001effb  test    rdi, rdi
0x18001effe  jz      short loc_18001F018
0x18001f000  mov     rcx, gs:60h
0x18001f009  mov     r8, rdi; P
0x18001f00c  xor     edx, edx; Flags
0x18001f00e  mov     rcx, [rcx+30h]; HeapHandle
0x18001f012  call    cs:__imp_RtlFreeHeap
0x18001f018  test    rbx, rbx
0x18001f01b  jz      short loc_18001F03B
0x18001f01d  cmp     rbx, [rbp+47h+pbmi]
0x18001f021  jz      short loc_18001F03B
0x18001f023  mov     rcx, gs:60h
0x18001f02c  mov     r8, rbx; P
0x18001f02f  xor     edx, edx; Flags
0x18001f031  mov     rcx, [rcx+30h]; HeapHandle
0x18001f035  call    cs:__imp_RtlFreeHeap
0x18001f03b  mov     rcx, rsi
0x18001f03e  mov     rbx, [rsp+0F0h+arg_18]
0x18001f046  add     rsp, 0C0h
0x18001f04d  pop     r15
0x18001f04f  pop     r14
0x18001f051  pop     r13
0x18001f053  pop     r12
0x18001f055  pop     rdi
0x18001f056  pop     rsi
0x18001f057  pop     rbp
0x18001f058  jmp     GdiTrackHCreate
```
