# IcmStretchBlt

- ea: `0x18008eb38`
- end: `0x18008ef4e`
- name: `IcmStretchBlt`
- size: `1046`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, HDC hdc, int, int, int, int SrcWidth, DWORD rop, SIZE_T Size, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18002a660`
- `0x18006cab0`

## callees

- `0x180004c00`
- `0x180006a28`
- `0x18001f090`
- `0x180028e90`
- `0x18002e130`
- `0x1800446d0`
- `0x1800461c4`
- `0x1800583e0`
- `0x18006c658`
- `0x180070288`
- `0x180074e68`
- `0x18007ff9c`
- `0x18008eb38`

## import_xrefs

- `GDI32!StretchDIBits` at `0x18008eec5`
- `GDI32!StretchDIBits` at `0x18008eec5`
- `ntdll!RtlFreeHeap` at `0x18008edf4`
- `ntdll!RtlFreeHeap` at `0x18008eef9`
- `ntdll!RtlFreeHeap` at `0x18008edf4`
- `ntdll!RtlFreeHeap` at `0x18008eef9`
- `ntdll!RtlAllocateHeap` at `0x18008ed86`
- `ntdll!RtlAllocateHeap` at `0x18008ed86`
- `win32u!NtGdiDeleteColorSpace` at `0x18008ef0d`
- `win32u!NtGdiDeleteColorSpace` at `0x18008ef0d`
- `win32u!NtGdiGetDIBitsInternal` at `0x18008edd0`
- `win32u!NtGdiGetDIBitsInternal` at `0x18008edd0`

## pseudocode

```c
_BOOL8 __fastcall IcmStretchBlt(
        HDC a1,
        int a2,
        int a3,
        DWORD a4,
        DWORD h,
        HDC hdc,
        LONG a7,
        LONG a8,
        int a9,
        int SrcWidth,
        DWORD rop,
        SIZE_T Size,
        __int64 a13)
{
  char *v14; // r14
  UINT cLines; // esi
  __int64 DCObject; // rax
  __int64 v17; // rdi
  void *v18; // r9
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 StockObject; // rdi
  const BITMAPINFO *lpbmi; // rbx
  __int64 v23; // r13
  __int64 v24; // rcx
  __int64 ColorSpaceInternalW; // rax
  int v26; // r12d
  int v27; // r15d
  PVOID Heap; // rax
  void *lpvBits; // r14
  __int64 v30; // r15
  int v31; // eax
  char *v33; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+80h] [rbp-19h]
  struct tagPOINT pt; // [rsp+88h] [rbp-11h] BYREF
  int v36; // [rsp+90h] [rbp-9h]
  int v37; // [rsp+94h] [rbp-5h]
  int v42; // [rsp+118h] [rbp+7Fh]
  LONG xSrc; // [rsp+120h] [rbp+87h]
  LONG y; // [rsp+128h] [rbp+8Fh]
  int SrcWidtha; // [rsp+130h] [rbp+97h]

  LODWORD(Size) = 0;
  v14 = (char *)operator new[](0x468u);
  v36 = a7 + a9;
  v33 = v14;
  v37 = a8 + SrcWidth;
  pt.x = a7;
  pt.y = a8;
  if ( !LPtoDP(hdc, &pt, 2) )
    goto LABEL_42;
  xSrc = pt.x;
  if ( pt.x < 0 )
    goto LABEL_42;
  y = pt.y;
  if ( pt.y < 0 )
    goto LABEL_42;
  SrcWidtha = v36 - pt.x;
  if ( v36 - pt.x < 0 )
    goto LABEL_42;
  cLines = v37 - pt.y;
  if ( v37 - pt.y < 0 )
    goto LABEL_42;
  if ( a4 != v36 - pt.x || (v42 = 1, h != cLines) )
    v42 = 0;
  DCObject = GetDCObject(hdc, 327680);
  v17 = a13;
  v34 = DCObject;
  if ( (unsigned int)bDIBSectionSelected(a13) )
  {
    if ( GetObjectA(v18, 104, v14) != 104 )
    {
LABEL_42:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v33);
      return 0;
    }
    if ( *((_WORD *)v14 + 9) <= 8u )
      GetDIBColorTable(hdc, 0, 0x100u, (RGBQUAD *)v14 + 18);
    if ( (*(_BYTE *)(v17 + 240) & 3) == 0
      || (v19 = *(_QWORD *)(v17 + 264)) == 0
      || (v20 = *(_QWORD *)(v19 + 48)) == 0
      || (StockObject = CreateColorSpaceInternalW(v20 + 88, 0)) == 0 )
    {
      StockObject = (__int64)GetStockObject(20);
    }
    lpbmi = (const BITMAPINFO *)(v14 + 32);
  }
  else
  {
    if ( (*(_BYTE *)(v17 + 240) & 0x10) == 0 || GetObjectA(v18, 32, v14) != 32 )
      goto LABEL_42;
    lpbmi = (const BITMAPINFO *)(v14 + 32);
    *((_DWORD *)v14 + 8) = 44;
    *((_DWORD *)v14 + 10) = *((_DWORD *)v14 + 2);
    *((_DWORD *)v14 + 9) = *((_DWORD *)v14 + 1);
    *(_QWORD *)(v14 + 44) = 1572865;
    *(_QWORD *)(v14 + 52) = 0;
    *(_QWORD *)(v14 + 60) = 0;
    *((_DWORD *)v14 + 17) = 0;
    v23 = *(_QWORD *)(v17 + 264);
    if ( v23 && (v24 = *(_QWORD *)(v23 + 40)) != 0 )
      ColorSpaceInternalW = CreateColorSpaceInternalW(v24 + 88, 0);
    else
      ColorSpaceInternalW = (__int64)GetStockObject(20);
    StockObject = ColorSpaceInternalW;
  }
  if ( (int)hrBitmapScanSize(lpbmi, cLines, &Size) < 0 )
    goto LABEL_42;
  v26 = 0;
  v27 = Size;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
  lpvBits = Heap;
  if ( Heap )
  {
    if ( (unsigned int)NtGdiGetDIBitsInternal(
                         hdc,
                         v34,
                         lpbmi->bmiHeader.biHeight - cLines - y,
                         cLines,
                         Heap,
                         lpbmi,
                         0,
                         v27,
                         0) )
    {
      lpbmi->bmiHeader.biHeight = cLines;
      v30 = 0;
      if ( StockObject )
        v30 = IcmSetSourceColorSpace(a1);
      if ( v42 && rop == 13369376 )
        v31 = SetDIBitsToDevice(a1, a2, a3, a4, h, xSrc, 0, 0, cLines, lpvBits, lpbmi, 0);
      else
        v31 = StretchDIBits(a1, a2, a3, a4, h, xSrc, 0, SrcWidtha, cLines, lpvBits, lpbmi, 0, rop);
      v26 = v31;
      if ( v30 )
        IcmSetSourceColorSpace(a1);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpvBits);
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpvBits);
      lpbmi->bmiHeader.biHeight = cLines;
    }
  }
  if ( StockObject )
    NtGdiDeleteColorSpace(StockObject);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v33);
  return v26 != 0;
}

```

## disassembly

```asm
0x18008eb38  mov     rax, rsp
0x18008eb3b  mov     [rax+20h], r9d
0x18008eb3f  mov     [rax+18h], r8d
0x18008eb43  mov     [rax+10h], edx
0x18008eb46  mov     [rax+8], rcx
0x18008eb4a  push    rbp
0x18008eb4b  push    rbx
0x18008eb4c  push    rsi
0x18008eb4d  push    rdi
0x18008eb4e  push    r12
0x18008eb50  push    r13
0x18008eb52  push    r14
0x18008eb54  push    r15
0x18008eb56  lea     rbp, [rax-47h]
0x18008eb5a  sub     rsp, 98h
0x18008eb61  xor     r15d, r15d
0x18008eb64  mov     ecx, 468h; unsigned __int64
0x18008eb69  mov     dword ptr [rbp+3Fh+Size], r15d
0x18008eb70  mov     edi, r9d
0x18008eb73  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008eb78  mov     r10d, [rbp+3Fh+arg_30]
0x18008eb7c  lea     r8d, [r15+2]; c
0x18008eb80  mov     r11d, [rbp+3Fh+arg_38]
0x18008eb87  mov     r14, rax
0x18008eb8a  mov     edx, [rbp+3Fh+arg_40]
0x18008eb90  mov     rbx, [rbp+3Fh+hdc]
0x18008eb94  add     edx, r10d
0x18008eb97  mov     [rbp+3Fh+var_48], edx
0x18008eb9a  mov     rcx, rbx; hdc
0x18008eb9d  mov     edx, [rbp+3Fh+SrcWidth]
0x18008eba3  add     edx, r11d
0x18008eba6  mov     [rbp+3Fh+var_60], rax
0x18008ebaa  mov     [rbp+3Fh+var_44], edx
0x18008ebad  lea     rdx, [rbp+3Fh+pt]; lppt
0x18008ebb1  mov     [rbp+3Fh+pt.x], r10d
0x18008ebb5  mov     [rbp+3Fh+pt.y], r11d
0x18008ebb9  call    LPtoDP
0x18008ebbe  test    eax, eax
0x18008ebc0  jz      loc_18008EF2E
0x18008ebc6  mov     ecx, [rbp+3Fh+pt.x]
0x18008ebc9  mov     [rbp+3Fh+arg_38], ecx
0x18008ebcf  test    ecx, ecx
0x18008ebd1  js      loc_18008EF2E
0x18008ebd7  mov     edx, [rbp+3Fh+pt.y]
0x18008ebda  mov     [rbp+3Fh+arg_40], edx
0x18008ebe0  test    edx, edx
0x18008ebe2  js      loc_18008EF2E
0x18008ebe8  mov     eax, [rbp+3Fh+var_48]
0x18008ebeb  sub     eax, ecx
0x18008ebed  mov     [rbp+3Fh+SrcWidth], eax
0x18008ebf3  js      loc_18008EF2E
0x18008ebf9  mov     esi, [rbp+3Fh+var_44]
0x18008ebfc  sub     esi, edx
0x18008ebfe  js      loc_18008EF2E
0x18008ec04  lea     r12d, [r15+1]
0x18008ec08  cmp     edi, eax
0x18008ec0a  jnz     short loc_18008EC15
0x18008ec0c  mov     [rbp+3Fh+arg_30], r12d
0x18008ec10  cmp     [rbp+3Fh+arg_20], esi
0x18008ec13  jz      short loc_18008EC19
0x18008ec15  mov     [rbp+3Fh+arg_30], r15d
0x18008ec19  mov     edx, 50000h
0x18008ec1e  mov     rcx, rbx
0x18008ec21  call    GetDCObject
0x18008ec26  mov     rdi, [rbp+3Fh+arg_60]
0x18008ec2d  mov     r9, rax
0x18008ec30  mov     rcx, rdi
0x18008ec33  mov     [rbp+3Fh+var_58], rax
0x18008ec37  call    bDIBSectionSelected
0x18008ec3c  test    eax, eax
0x18008ec3e  jz      loc_18008ECC9
0x18008ec44  mov     r8, r14; pv
0x18008ec47  mov     edx, 68h ; 'h'; c
0x18008ec4c  mov     rcx, r9; h
0x18008ec4f  call    GetObjectA
0x18008ec54  cmp     eax, 68h ; 'h'
0x18008ec57  jnz     loc_18008EF2E
0x18008ec5d  cmp     word ptr [r14+12h], 8
0x18008ec63  ja      short loc_18008EC79
0x18008ec65  lea     r9, [r14+48h]; prgbq
0x18008ec69  xor     edx, edx; iStart
0x18008ec6b  mov     r8d, 100h; cEntries
0x18008ec71  mov     rcx, rbx; hdc
0x18008ec74  call    GetDIBColorTable
0x18008ec79  test    byte ptr [rdi+0F0h], 3
0x18008ec80  jz      short loc_18008ECB0
0x18008ec82  mov     rbx, [rdi+108h]
0x18008ec89  test    rbx, rbx
0x18008ec8c  jz      short loc_18008ECB0
0x18008ec8e  mov     rcx, [rbx+30h]
0x18008ec92  test    rcx, rcx
0x18008ec95  jz      short loc_18008ECB0
0x18008ec97  add     rcx, 58h ; 'X'
0x18008ec9b  xor     edx, edx
0x18008ec9d  call    CreateColorSpaceInternalW
0x18008eca2  mov     rdi, rax
0x18008eca5  test    rax, rax
0x18008eca8  jz      short loc_18008ECB0
0x18008ecaa  mov     r13, [rbx+30h]
0x18008ecae  jmp     short loc_18008ECC0
0x18008ecb0  mov     ecx, 14h; i
0x18008ecb5  call    GetStockObject
0x18008ecba  mov     rdi, rax
0x18008ecbd  mov     r13, r15
0x18008ecc0  lea     rbx, [r14+20h]
0x18008ecc4  jmp     loc_18008ED51
0x18008ecc9  test    byte ptr [rdi+0F0h], 10h
0x18008ecd0  jz      loc_18008EF2E
0x18008ecd6  mov     r8, r14; pv
0x18008ecd9  mov     edx, 20h ; ' '; c
0x18008ecde  mov     rcx, r9; h
0x18008ece1  call    GetObjectA
0x18008ece6  cmp     eax, 20h ; ' '
0x18008ece9  jnz     loc_18008EF2E
0x18008ecef  lea     rbx, [r14+20h]
0x18008ecf3  mov     dword ptr [rbx], 2Ch ; ','
0x18008ecf9  mov     eax, [r14+8]
0x18008ecfd  mov     [rbx+8], eax
0x18008ed00  mov     eax, [r14+4]
0x18008ed04  mov     [rbx+4], eax
0x18008ed07  mov     qword ptr [rbx+0Ch], 180001h
0x18008ed0f  mov     [rbx+14h], r15
0x18008ed13  mov     [rbx+1Ch], r15
0x18008ed17  mov     [rbx+24h], r15d
0x18008ed1b  mov     r13, [rdi+108h]
0x18008ed22  test    r13, r13
0x18008ed25  jz      short loc_18008ED41
0x18008ed27  mov     rcx, [r13+28h]
0x18008ed2b  test    rcx, rcx
0x18008ed2e  jz      short loc_18008ED41
0x18008ed30  add     rcx, 58h ; 'X'
0x18008ed34  xor     edx, edx
0x18008ed36  call    CreateColorSpaceInternalW
0x18008ed3b  mov     r13, [r13+28h]
0x18008ed3f  jmp     short loc_18008ED4E
0x18008ed41  mov     ecx, 14h; i
0x18008ed46  call    GetStockObject
0x18008ed4b  mov     r13, r15
0x18008ed4e  mov     rdi, rax
0x18008ed51  lea     r8, [rbp+3Fh+Size]
0x18008ed58  mov     edx, esi
0x18008ed5a  mov     rcx, rbx
0x18008ed5d  call    hrBitmapScanSize
0x18008ed62  test    eax, eax
0x18008ed64  js      loc_18008EF2E
0x18008ed6a  mov     rcx, gs:60h
0x18008ed73  mov     r12d, r15d
0x18008ed76  mov     r15d, dword ptr [rbp+3Fh+Size]
0x18008ed7d  xor     edx, edx; Flags
0x18008ed7f  mov     r8d, r15d; Size
0x18008ed82  mov     rcx, [rcx+30h]; HeapHandle
0x18008ed86  call    cs:__imp_RtlAllocateHeap
0x18008ed8d  nop     dword ptr [rax+rax+00h]
0x18008ed92  mov     r14, rax
0x18008ed95  test    rax, rax
0x18008ed98  jz      loc_18008EF05
0x18008ed9e  mov     r8d, [rbx+8]
0x18008eda2  mov     r9d, esi
0x18008eda5  mov     rdx, [rbp+3Fh+var_58]
0x18008eda9  sub     r8d, esi
0x18008edac  sub     r8d, [rbp+3Fh+arg_40]
0x18008edb3  mov     rcx, [rbp+3Fh+hdc]
0x18008edb7  mov     [rsp+0D0h+cLines], r12d
0x18008edbc  mov     [rsp+0D0h+StartScan], r15d
0x18008edc1  mov     [rsp+0D0h+ySrc], r12d
0x18008edc6  mov     qword ptr [rsp+0D0h+xSrc], rbx
0x18008edcb  mov     qword ptr [rsp+0D0h+h], rax
0x18008edd0  call    cs:__imp_NtGdiGetDIBitsInternal
0x18008edd7  nop     dword ptr [rax+rax+00h]
0x18008eddc  xor     ecx, ecx
0x18008edde  test    eax, eax
0x18008ede0  jnz     short loc_18008EE08
0x18008ede2  mov     rcx, gs:60h
0x18008edeb  mov     r8, r14; P
0x18008edee  xor     edx, edx; Flags
0x18008edf0  mov     rcx, [rcx+30h]; HeapHandle
0x18008edf4  call    cs:__imp_RtlFreeHeap
0x18008edfb  nop     dword ptr [rax+rax+00h]
0x18008ee00  mov     [rbx+8], esi
0x18008ee03  jmp     loc_18008EF05
0x18008ee08  mov     [rbx+8], esi
0x18008ee0b  mov     r15, rcx
0x18008ee0e  test    rdi, rdi
0x18008ee11  jz      short loc_18008EE2C
0x18008ee13  mov     r8, r13
0x18008ee16  mov     rdx, rdi
0x18008ee19  mov     r13, [rbp+3Fh+arg_0]
0x18008ee1d  mov     rcx, r13; hdc
0x18008ee20  call    IcmSetSourceColorSpace
0x18008ee25  mov     r15, rax
0x18008ee28  xor     ecx, ecx
0x18008ee2a  jmp     short loc_18008EE30
0x18008ee2c  mov     r13, [rbp+3Fh+arg_0]
0x18008ee30  mov     eax, [rbp+3Fh+rop]
0x18008ee36  cmp     [rbp+3Fh+arg_30], ecx
0x18008ee39  jz      short loc_18008EE82
0x18008ee3b  cmp     eax, 0CC0020h
0x18008ee40  jnz     short loc_18008EE82
0x18008ee42  mov     eax, [rbp+3Fh+arg_38]
0x18008ee48  mov     r9d, [rbp+3Fh+w]; w
0x18008ee4c  mov     r8d, [rbp+3Fh+yDest]; yDest
0x18008ee50  mov     edx, [rbp+3Fh+xDest]; xDest
0x18008ee53  mov     [rsp+0D0h+ColorUse], ecx; ColorUse
0x18008ee57  mov     [rsp+0D0h+lpbmi], rbx; lpbmi
0x18008ee5c  mov     [rsp+0D0h+lpvBits], r14; lpvBits
0x18008ee61  mov     [rsp+0D0h+cLines], esi; cLines
0x18008ee65  mov     [rsp+0D0h+StartScan], ecx; StartScan
0x18008ee69  mov     [rsp+0D0h+ySrc], ecx; ySrc
0x18008ee6d  mov     rcx, r13; hdc
0x18008ee70  mov     [rsp+0D0h+xSrc], eax; xSrc
0x18008ee74  mov     eax, [rbp+3Fh+arg_20]
0x18008ee77  mov     [rsp+0D0h+h], eax; h
0x18008ee7b  call    SetDIBitsToDevice
0x18008ee80  jmp     short loc_18008EED1
0x18008ee82  mov     r9d, [rbp+3Fh+w]; DestWidth
0x18008ee86  mov     r8d, [rbp+3Fh+yDest]; yDest
0x18008ee8a  mov     edx, [rbp+3Fh+xDest]; xDest
0x18008ee8d  mov     [rsp+60h], eax; rop
0x18008ee91  mov     eax, [rbp+3Fh+SrcWidth]
0x18008ee97  mov     [rsp+0D0h+ColorUse], ecx; iUsage
0x18008ee9b  mov     [rsp+0D0h+lpbmi], rbx; lpbmi
0x18008eea0  mov     [rsp+0D0h+lpvBits], r14; lpBits
0x18008eea5  mov     [rsp+0D0h+cLines], esi; SrcHeight
0x18008eea9  mov     [rsp+0D0h+StartScan], eax; SrcWidth
0x18008eead  mov     eax, [rbp+3Fh+arg_38]
0x18008eeb3  mov     [rsp+0D0h+ySrc], ecx; ySrc
0x18008eeb7  mov     rcx, r13; hdc
0x18008eeba  mov     [rsp+0D0h+xSrc], eax; xSrc
0x18008eebe  mov     eax, [rbp+3Fh+arg_20]
0x18008eec1  mov     [rsp+0D0h+h], eax; DestHeight
0x18008eec5  call    cs:__imp_StretchDIBits
0x18008eecc  nop     dword ptr [rax+rax+00h]
0x18008eed1  mov     r12d, eax
0x18008eed4  test    r15, r15
0x18008eed7  jz      short loc_18008EEE7
0x18008eed9  xor     r8d, r8d
0x18008eedc  mov     rdx, r15
0x18008eedf  mov     rcx, r13; hdc
0x18008eee2  call    IcmSetSourceColorSpace
0x18008eee7  mov     rcx, gs:60h
0x18008eef0  mov     r8, r14; P
0x18008eef3  xor     edx, edx; Flags
0x18008eef5  mov     rcx, [rcx+30h]; HeapHandle
0x18008eef9  call    cs:__imp_RtlFreeHeap
0x18008ef00  nop     dword ptr [rax+rax+00h]
0x18008ef05  test    rdi, rdi
0x18008ef08  jz      short loc_18008EF19
0x18008ef0a  mov     rcx, rdi
0x18008ef0d  call    cs:__imp_NtGdiDeleteColorSpace
0x18008ef14  nop     dword ptr [rax+rax+00h]
0x18008ef19  xor     ebx, ebx
0x18008ef1b  lea     rcx, [rbp+3Fh+var_60]
0x18008ef1f  test    r12d, r12d
0x18008ef22  setnz   bl
0x18008ef25  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18008ef2a  mov     eax, ebx
0x18008ef2c  jmp     short loc_18008EF39
0x18008ef2e  lea     rcx, [rbp+3Fh+var_60]
0x18008ef32  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18008ef37  xor     eax, eax
0x18008ef39  add     rsp, 98h
0x18008ef40  pop     r15
0x18008ef42  pop     r14
0x18008ef44  pop     r13
0x18008ef46  pop     r12
0x18008ef48  pop     rdi
0x18008ef49  pop     rsi
0x18008ef4a  pop     rbx
0x18008ef4b  pop     rbp
0x18008ef4c  retn
```
