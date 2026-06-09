# CreateDIBitmap

- ea: `0x180035af0`
- end: `0x180035f07`
- name: `CreateDIBitmap`
- size: `1047`
- prototype: `HBITMAP __stdcall(HDC hdc, const BITMAPINFOHEADER *pbmih, DWORD flInit, const void *pjBits, const BITMAPINFO *pbmi, UINT iUsage)`
- caller_count: `9`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b040`
- `0x180034d80`
- `0x18004ac60`
- `0x18005a5b4`
- `0x18006c800`
- `0x18008d480`
- `0x180095e20`
- `0x1800963c0`
- `0x180097530`

## callees

- `0x1800292c8`
- `0x18002e130`
- `0x18002fda0`
- `0x180035af0`
- `0x180036734`
- `0x18003888c`
- `0x180038a34`
- `0x1800499a4`
- `0x1800756cc`
- `0x1800a68d4`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180035b6e`
- `GDI32!GdiGetEntry` at `0x180035b6e`
- `GDI32!gW32PID` at `0x180035b9d`
- `GDI32!gCookie` at `0x180035bb7`
- `GDI32!gMaxGdiHandleCount` at `0x180035b4e`
- `ntdll!RtlFreeHeap` at `0x180035dae`
- `ntdll!RtlFreeHeap` at `0x180035de1`
- `ntdll!RtlFreeHeap` at `0x180035eb0`
- `ntdll!RtlFreeHeap` at `0x180035ed9`
- `ntdll!RtlFreeHeap` at `0x180035dae`
- `ntdll!RtlFreeHeap` at `0x180035de1`
- `ntdll!RtlFreeHeap` at `0x180035eb0`
- `ntdll!RtlFreeHeap` at `0x180035ed9`
- `ntdll!RtlAllocateHeap` at `0x180035cc1`
- `ntdll!RtlAllocateHeap` at `0x180035cc1`
- `win32u!NtGdiCreateDIBitmapInternal` at `0x180035e66`
- `win32u!NtGdiCreateDIBitmapInternal` at `0x180035e66`

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
0x180035af0  mov     rax, rsp
0x180035af3  mov     [rax+20h], rbx
0x180035af7  mov     [rax+18h], r8d
0x180035afb  mov     [rax+8], rcx
0x180035aff  push    rbp
0x180035b00  push    rsi
0x180035b01  push    rdi
0x180035b02  push    r12
0x180035b04  push    r13
0x180035b06  push    r14
0x180035b08  push    r15
0x180035b0a  lea     rbp, [rax-4Fh]
0x180035b0e  sub     rsp, 0C0h
0x180035b15  xor     r11d, r11d
0x180035b18  mov     r12, r9
0x180035b1b  mov     [rbp+47h+arg_8], r11d
0x180035b1f  mov     r14d, r11d
0x180035b22  mov     dword ptr [rbp+47h+Size], r11d
0x180035b26  mov     esi, r8d
0x180035b29  mov     [rbp+47h+var_78], r11d
0x180035b2d  mov     rdi, rdx
0x180035b30  mov     dword ptr [rbp+47h+Size+4], r11d
0x180035b34  mov     rbx, rcx
0x180035b37  mov     [rbp+47h+var_58], r11
0x180035b3b  or      r15, 0FFFFFFFFFFFFFFFFh
0x180035b3f  mov     [rbp+47h+var_60], r11
0x180035b43  call    HANDLE_TO_INDEX
0x180035b48  mov     ecx, eax
0x180035b4a  mov     [rbp+47h+var_68], r11
0x180035b4e  mov     rax, cs:__imp_gMaxGdiHandleCount
0x180035b55  lea     r13d, [r11+1]
0x180035b59  cmp     ecx, [rax]
0x180035b5b  jnb     short loc_180035BDC
0x180035b5d  xorps   xmm0, xmm0
0x180035b60  lea     rdx, [rbp+47h+var_48]
0x180035b64  xor     eax, eax
0x180035b66  movups  [rbp+47h+var_48], xmm0
0x180035b6a  mov     [rbp+47h+var_38], rax
0x180035b6e  call    cs:__imp_GdiGetEntry
0x180035b75  nop     dword ptr [rax+rax+00h]
0x180035b7a  test    eax, eax
0x180035b7c  js      short loc_180035BDC
0x180035b7e  cmp     byte ptr [rbp+47h+var_48+0Eh], r13b
0x180035b82  jnz     short loc_180035BDC
0x180035b84  movzx   eax, byte ptr [rbp+47h+var_48+0Ch]
0x180035b88  movzx   ecx, byte ptr [rbp+47h+var_48+0Dh]
0x180035b8c  shl     cx, 8
0x180035b90  or      cx, ax
0x180035b93  mov     eax, ebx
0x180035b95  shr     eax, 10h
0x180035b98  cmp     cx, ax
0x180035b9b  jnz     short loc_180035BDC
0x180035b9d  mov     rax, cs:__imp_gW32PID
0x180035ba4  mov     ecx, dword ptr [rbp+47h+var_48+8]
0x180035ba7  and     ecx, 0FFFFFFFEh
0x180035baa  cmp     ecx, [rax]
0x180035bac  jnz     short loc_180035BDC
0x180035bae  mov     r8, [rbp+47h+var_38]
0x180035bb2  test    r8, r8
0x180035bb5  jz      short loc_180035BDC
0x180035bb7  mov     rax, cs:__imp_gCookie
0x180035bbe  lea     ecx, [r14+40h]
0x180035bc2  mov     rsi, r8
0x180035bc5  mov     rdx, [rax]
0x180035bc8  mov     eax, edx
0x180035bca  and     eax, 3Fh
0x180035bcd  sub     ecx, eax
0x180035bcf  ror     rsi, cl
0x180035bd2  xor     rsi, rdx
0x180035bd5  mov     [rbp+47h+var_68], rsi
0x180035bd9  mov     esi, [rbp+47h+arg_10]
0x180035bdc  mov     edx, [rbp+47h+iUsage]
0x180035bdf  lea     r8, [rbp+47h+arg_8]
0x180035be3  mov     rcx, [rbp+47h+pbmi]
0x180035be7  xor     r9d, r9d
0x180035bea  call    pbmiConvertInfo
0x180035bef  mov     rbx, rax
0x180035bf2  mov     eax, [rbp+47h+arg_8]
0x180035bf5  test    sil, 2
0x180035bf9  jz      short loc_180035C13
0x180035bfb  mov     rdi, [rbp+47h+pbmi]
0x180035bff  test    eax, eax
0x180035c01  jnz     short loc_180035C08
0x180035c03  xor     r15d, r15d
0x180035c06  jmp     short loc_180035C3C
0x180035c08  test    sil, 4
0x180035c0c  jz      short loc_180035C39
0x180035c0e  test    r12, r12
0x180035c11  jmp     short loc_180035C28
0x180035c13  test    sil, 4
0x180035c17  jz      short loc_180035C39
0x180035c19  test    r12, r12
0x180035c1c  jnz     short loc_180035C26
0x180035c1e  and     esi, 0FFFFFFFBh
0x180035c21  mov     [rbp+47h+arg_10], esi
0x180035c24  jmp     short loc_180035C3C
0x180035c26  test    eax, eax
0x180035c28  jz      short loc_180035C03
0x180035c2a  xor     edx, edx
0x180035c2c  mov     rcx, rbx
0x180035c2f  call    GdiGetBitmapBitsSizeSpecificHeight
0x180035c34  mov     dword ptr [rbp+47h+Size], eax
0x180035c37  jmp     short loc_180035C3C
0x180035c39  xor     r12d, r12d
0x180035c3c  mov     ecx, dword ptr [rbp+47h+Size]
0x180035c3f  xor     esi, esi
0x180035c41  cmp     ecx, 0FFFFFFFFh
0x180035c44  cmovnz  rsi, r15
0x180035c48  test    rbx, rbx
0x180035c4b  jz      short loc_180035C5F
0x180035c4d  cmp     dword ptr [rbx], 28h ; '('
0x180035c50  jb      short loc_180035C5F
0x180035c52  mov     eax, [rbx+10h]
0x180035c55  sub     eax, 4
0x180035c58  cmp     eax, r13d
0x180035c5b  ja      short loc_180035C5F
0x180035c5d  xor     esi, esi
0x180035c5f  test    rdi, rdi
0x180035c62  jz      short loc_180035C97
0x180035c64  cmp     dword ptr [rdi], 28h ; '('
0x180035c67  jb      short loc_180035C71
0x180035c69  mov     eax, [rdi+4]
0x180035c6c  mov     edx, [rdi+8]
0x180035c6f  jmp     short loc_180035C79
0x180035c71  movzx   eax, word ptr [rdi+4]
0x180035c75  movzx   edx, word ptr [rdi+6]
0x180035c79  mov     dword ptr [rbp+47h+Size+4], edx
0x180035c7c  mov     [rbp+47h+var_78], eax
0x180035c7f  test    eax, eax
0x180035c81  jz      short loc_180035C87
0x180035c83  test    edx, edx
0x180035c85  jnz     short loc_180035C97
0x180035c87  mov     ecx, 15h; i
0x180035c8c  call    GetStockObject
0x180035c91  mov     ecx, dword ptr [rbp+47h+Size]
0x180035c94  mov     rsi, rax
0x180035c97  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180035c9b  jnz     loc_180035EBC
0x180035ca1  xor     edi, edi
0x180035ca3  xor     r15d, r15d
0x180035ca6  test    r12b, 3
0x180035caa  jz      short loc_180035CE9
0x180035cac  mov     r15d, ecx
0x180035caf  xor     edx, edx; Flags
0x180035cb1  mov     rcx, gs:60h
0x180035cba  mov     r8d, r15d; Size
0x180035cbd  mov     rcx, [rcx+30h]; HeapHandle
0x180035cc1  call    cs:__imp_RtlAllocateHeap
0x180035cc8  nop     dword ptr [rax+rax+00h]
0x180035ccd  mov     rdi, rax
0x180035cd0  test    rax, rax
0x180035cd3  jz      short loc_180035CE6
0x180035cd5  mov     r8d, r15d; Size
0x180035cd8  mov     rdx, r12; Src
0x180035cdb  mov     rcx, rax; void *
0x180035cde  call    memcpy_0
0x180035ce3  mov     r12, rdi
0x180035ce6  mov     r15, r14
0x180035ce9  mov     rcx, [rbp+47h+var_68]
0x180035ced  test    rcx, rcx
0x180035cf0  jz      loc_180035E2B
0x180035cf6  mov     eax, [rcx+0F0h]
0x180035cfc  test    al, 3
0x180035cfe  jz      loc_180035E2B
0x180035d04  test    al, 10h
0x180035d06  jnz     loc_180035E2B
0x180035d0c  cmp     [rbp+47h+iUsage], r13d
0x180035d10  jz      loc_180035E2B
0x180035d16  test    r12, r12
0x180035d19  jz      loc_180035E2B
0x180035d1f  test    rbx, rbx
0x180035d22  jz      loc_180035E2B
0x180035d28  mov     r8d, dword ptr [rbp+47h+Size]
0x180035d2c  lea     rax, [rbp+47h+var_60]
0x180035d30  mov     [rsp+60h], rax
0x180035d35  mov     rdx, rcx
0x180035d38  mov     rcx, [rbp+47h+arg_0]
0x180035d3c  lea     rax, [rbp+47h+var_58]
0x180035d40  mov     [rsp+0F0h+var_98], rax
0x180035d45  mov     r9, r12
0x180035d48  mov     dword ptr [rsp+0F0h+var_A0], r13d
0x180035d4d  lea     rax, [rbp+47h+var_70]
0x180035d51  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x180035d59  mov     qword ptr [rsp+0F0h+var_B8], rax
0x180035d5e  lea     rax, [rbp+47h+var_50]
0x180035d62  mov     [rsp+0F0h+var_C0], rax
0x180035d67  lea     rax, [rbp+47h+var_68]
0x180035d6b  mov     [rsp+0F0h+var_C8], rbx
0x180035d70  mov     [rsp+0F0h+var_D0], rax
0x180035d75  mov     [rbp+47h+var_68], r14
0x180035d79  mov     [rbp+47h+var_50], r14
0x180035d7d  mov     [rbp+47h+var_70], r14d
0x180035d81  call    IcmTranslateDIB
0x180035d86  test    eax, eax
0x180035d88  jz      loc_180035E27
0x180035d8e  mov     r14, [rbp+47h+var_68]
0x180035d92  test    r14, r14
0x180035d95  jz      short loc_180035DC0
0x180035d97  test    rdi, rdi
0x180035d9a  jz      short loc_180035DBA
0x180035d9c  mov     rcx, gs:60h
0x180035da5  mov     r8, rdi; P
0x180035da8  xor     edx, edx; Flags
0x180035daa  mov     rcx, [rcx+30h]; HeapHandle
0x180035dae  call    cs:__imp_RtlFreeHeap
0x180035db5  nop     dword ptr [rax+rax+00h]
0x180035dba  mov     rdi, r14
0x180035dbd  mov     r12, r14
0x180035dc0  mov     r14, [rbp+47h+var_50]
0x180035dc4  test    r14, r14
0x180035dc7  jz      short loc_180035E10
0x180035dc9  cmp     rbx, [rbp+47h+pbmi]
0x180035dcd  jz      short loc_180035DED
0x180035dcf  mov     rcx, gs:60h
0x180035dd8  mov     r8, rbx; P
0x180035ddb  xor     edx, edx; Flags
0x180035ddd  mov     rcx, [rcx+30h]; HeapHandle
0x180035de1  call    cs:__imp_RtlFreeHeap
0x180035de8  nop     dword ptr [rax+rax+00h]
0x180035ded  xor     edx, edx
0x180035def  mov     rcx, r14
0x180035df2  mov     rbx, r14
0x180035df5  call    GdiGetBitmapBitsSizeSpecificHeight
0x180035dfa  xor     r13d, r13d
0x180035dfd  mov     dword ptr [rbp+47h+Size], eax
0x180035e00  cmp     eax, 0FFFFFFFFh
0x180035e03  mov     eax, [rbp+47h+var_70]
0x180035e06  mov     ecx, eax
0x180035e08  setnz   r13b
0x180035e0c  test    eax, eax
0x180035e0e  jnz     short loc_180035E13
0x180035e10  mov     ecx, [rbp+47h+arg_8]
0x180035e13  mov     r14, [rbp+47h+var_60]
0x180035e17  test    r14, r14
0x180035e1a  jz      short loc_180035E20
0x180035e1c  mov     r15, [r14+28h]
0x180035e20  test    r13d, r13d
0x180035e23  jnz     short loc_180035E2E
0x180035e25  jmp     short loc_180035E75
0x180035e27  mov     r14, [rbp+47h+var_60]
0x180035e2b  mov     ecx, [rbp+47h+arg_8]
0x180035e2e  mov     eax, dword ptr [rbp+47h+Size]
0x180035e31  mov     r9d, [rbp+47h+arg_10]
0x180035e35  mov     r8d, dword ptr [rbp+47h+Size+4]
0x180035e39  mov     edx, [rbp+47h+var_78]
0x180035e3c  mov     [rsp+0F0h+var_A0], r15
0x180035e41  mov     dword ptr [rsp+0F0h+var_A8], 0
0x180035e49  mov     [rsp+0F0h+var_B0], eax
0x180035e4d  mov     eax, [rbp+47h+iUsage]
0x180035e50  mov     [rsp+0F0h+var_B8], ecx
0x180035e54  mov     rcx, [rbp+47h+arg_0]
0x180035e58  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180035e5c  mov     [rsp+0F0h+var_C8], rbx
0x180035e61  mov     [rsp+0F0h+var_D0], r12
0x180035e66  call    cs:__imp_NtGdiCreateDIBitmapInternal
0x180035e6d  nop     dword ptr [rax+rax+00h]
0x180035e72  mov     rsi, rax
0x180035e75  cmp     [rbp+47h+var_58], 0
0x180035e7a  jz      short loc_180035E99
0x180035e7c  test    r14, r14
0x180035e7f  jz      short loc_180035E8B
0x180035e81  xor     edx, edx
0x180035e83  mov     rcx, r14
0x180035e86  call    IcmDeleteColorTransform
0x180035e8b  mov     rdx, [rbp+47h+var_58]
0x180035e8f  xor     r8d, r8d
0x180035e92  xor     ecx, ecx
0x180035e94  call    IcmReleaseColorSpace
0x180035e99  test    rdi, rdi
0x180035e9c  jz      short loc_180035EBC
0x180035e9e  mov     rcx, gs:60h
0x180035ea7  mov     r8, rdi; P
0x180035eaa  xor     edx, edx; Flags
0x180035eac  mov     rcx, [rcx+30h]; HeapHandle
0x180035eb0  call    cs:__imp_RtlFreeHeap
0x180035eb7  nop     dword ptr [rax+rax+00h]
0x180035ebc  test    rbx, rbx
0x180035ebf  jz      short loc_180035EE5
0x180035ec1  cmp     rbx, [rbp+47h+pbmi]
0x180035ec5  jz      short loc_180035EE5
0x180035ec7  mov     rcx, gs:60h
0x180035ed0  mov     r8, rbx; P
0x180035ed3  xor     edx, edx; Flags
0x180035ed5  mov     rcx, [rcx+30h]; HeapHandle
0x180035ed9  call    cs:__imp_RtlFreeHeap
0x180035ee0  nop     dword ptr [rax+rax+00h]
0x180035ee5  mov     rcx, rsi
0x180035ee8  mov     rbx, [rsp+0F0h+arg_18]
0x180035ef0  add     rsp, 0C0h
0x180035ef7  pop     r15
0x180035ef9  pop     r14
0x180035efb  pop     r13
0x180035efd  pop     r12
0x180035eff  pop     rdi
0x180035f00  pop     rsi
0x180035f01  pop     rbp
0x180035f02  jmp     GdiTrackHCreate
```
