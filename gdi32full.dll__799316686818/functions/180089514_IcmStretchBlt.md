# IcmStretchBlt

- ea: `0x180089514`
- end: `0x180089905`
- name: `IcmStretchBlt`
- size: `1009`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, HDC hdc, int, int, int, int SrcWidth, DWORD rop, SIZE_T Size, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x1800218b0`
- `0x180068760`

## callees

- `0x18000d6c0`
- `0x18000e5a0`
- `0x18001f310`
- `0x1800201b0`
- `0x180025090`
- `0x18003a664`
- `0x18003a970`
- `0x180052830`
- `0x1800683b0`
- `0x18006b93c`
- `0x1800708c0`
- `0x18007b3ec`
- `0x180089514`

## import_xrefs

- `GDI32!StretchDIBits` at `0x18008988f`
- `GDI32!StretchDIBits` at `0x18008988f`
- `ntdll!RtlFreeHeap` at `0x1800897c4`
- `ntdll!RtlFreeHeap` at `0x1800898bd`
- `ntdll!RtlFreeHeap` at `0x1800897c4`
- `ntdll!RtlFreeHeap` at `0x1800898bd`
- `ntdll!RtlAllocateHeap` at `0x180089762`
- `ntdll!RtlAllocateHeap` at `0x180089762`
- `win32u!NtGdiDeleteColorSpace` at `0x1800898cb`
- `win32u!NtGdiDeleteColorSpace` at `0x1800898cb`
- `win32u!NtGdiGetDIBitsInternal` at `0x1800897a6`
- `win32u!NtGdiGetDIBitsInternal` at `0x1800897a6`

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
0x180089514  mov     rax, rsp
0x180089517  mov     [rax+20h], r9d
0x18008951b  mov     [rax+18h], r8d
0x18008951f  mov     [rax+10h], edx
0x180089522  mov     [rax+8], rcx
0x180089526  push    rbp
0x180089527  push    rbx
0x180089528  push    rsi
0x180089529  push    rdi
0x18008952a  push    r12
0x18008952c  push    r13
0x18008952e  push    r14
0x180089530  push    r15
0x180089532  lea     rbp, [rax-47h]
0x180089536  sub     rsp, 98h
0x18008953d  xor     r15d, r15d
0x180089540  mov     ecx, 468h; unsigned __int64
0x180089545  mov     dword ptr [rbp+3Fh+Size], r15d
0x18008954c  mov     edi, r9d
0x18008954f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089554  mov     r10d, [rbp+3Fh+arg_30]
0x180089558  lea     r8d, [r15+2]; c
0x18008955c  mov     r11d, [rbp+3Fh+arg_38]
0x180089563  mov     r14, rax
0x180089566  mov     edx, [rbp+3Fh+arg_40]
0x18008956c  mov     rbx, [rbp+3Fh+hdc]
0x180089570  add     edx, r10d
0x180089573  mov     [rbp+3Fh+var_48], edx
0x180089576  mov     rcx, rbx; hdc
0x180089579  mov     edx, [rbp+3Fh+SrcWidth]
0x18008957f  add     edx, r11d
0x180089582  mov     [rbp+3Fh+var_60], rax
0x180089586  mov     [rbp+3Fh+var_44], edx
0x180089589  lea     rdx, [rbp+3Fh+pt]; lppt
0x18008958d  mov     [rbp+3Fh+pt.x], r10d
0x180089591  mov     [rbp+3Fh+pt.y], r11d
0x180089595  call    LPtoDP
0x18008959a  test    eax, eax
0x18008959c  jz      loc_1800898E6
0x1800895a2  mov     ecx, [rbp+3Fh+pt.x]
0x1800895a5  mov     [rbp+3Fh+arg_38], ecx
0x1800895ab  test    ecx, ecx
0x1800895ad  js      loc_1800898E6
0x1800895b3  mov     edx, [rbp+3Fh+pt.y]
0x1800895b6  mov     [rbp+3Fh+arg_40], edx
0x1800895bc  test    edx, edx
0x1800895be  js      loc_1800898E6
0x1800895c4  mov     eax, [rbp+3Fh+var_48]
0x1800895c7  sub     eax, ecx
0x1800895c9  mov     [rbp+3Fh+SrcWidth], eax
0x1800895cf  js      loc_1800898E6
0x1800895d5  mov     esi, [rbp+3Fh+var_44]
0x1800895d8  sub     esi, edx
0x1800895da  js      loc_1800898E6
0x1800895e0  lea     r12d, [r15+1]
0x1800895e4  cmp     edi, eax
0x1800895e6  jnz     short loc_1800895F1
0x1800895e8  mov     [rbp+3Fh+arg_30], r12d
0x1800895ec  cmp     [rbp+3Fh+arg_20], esi
0x1800895ef  jz      short loc_1800895F5
0x1800895f1  mov     [rbp+3Fh+arg_30], r15d
0x1800895f5  mov     edx, 50000h
0x1800895fa  mov     rcx, rbx
0x1800895fd  call    GetDCObject
0x180089602  mov     rdi, [rbp+3Fh+arg_60]
0x180089609  mov     r9, rax
0x18008960c  mov     rcx, rdi
0x18008960f  mov     [rbp+3Fh+var_58], rax
0x180089613  call    bDIBSectionSelected
0x180089618  test    eax, eax
0x18008961a  jz      loc_1800896A5
0x180089620  mov     r8, r14; pv
0x180089623  mov     edx, 68h ; 'h'; c
0x180089628  mov     rcx, r9; h
0x18008962b  call    GetObjectA
0x180089630  cmp     eax, 68h ; 'h'
0x180089633  jnz     loc_1800898E6
0x180089639  cmp     word ptr [r14+12h], 8
0x18008963f  ja      short loc_180089655
0x180089641  lea     r9, [r14+48h]; prgbq
0x180089645  xor     edx, edx; iStart
0x180089647  mov     r8d, 100h; cEntries
0x18008964d  mov     rcx, rbx; hdc
0x180089650  call    GetDIBColorTable
0x180089655  test    byte ptr [rdi+0F0h], 3
0x18008965c  jz      short loc_18008968C
0x18008965e  mov     rbx, [rdi+108h]
0x180089665  test    rbx, rbx
0x180089668  jz      short loc_18008968C
0x18008966a  mov     rcx, [rbx+30h]
0x18008966e  test    rcx, rcx
0x180089671  jz      short loc_18008968C
0x180089673  add     rcx, 58h ; 'X'
0x180089677  xor     edx, edx
0x180089679  call    CreateColorSpaceInternalW
0x18008967e  mov     rdi, rax
0x180089681  test    rax, rax
0x180089684  jz      short loc_18008968C
0x180089686  mov     r13, [rbx+30h]
0x18008968a  jmp     short loc_18008969C
0x18008968c  mov     ecx, 14h; i
0x180089691  call    GetStockObject
0x180089696  mov     rdi, rax
0x180089699  mov     r13, r15
0x18008969c  lea     rbx, [r14+20h]
0x1800896a0  jmp     loc_18008972D
0x1800896a5  test    byte ptr [rdi+0F0h], 10h
0x1800896ac  jz      loc_1800898E6
0x1800896b2  mov     r8, r14; pv
0x1800896b5  mov     edx, 20h ; ' '; c
0x1800896ba  mov     rcx, r9; h
0x1800896bd  call    GetObjectA
0x1800896c2  cmp     eax, 20h ; ' '
0x1800896c5  jnz     loc_1800898E6
0x1800896cb  lea     rbx, [r14+20h]
0x1800896cf  mov     dword ptr [rbx], 2Ch ; ','
0x1800896d5  mov     eax, [r14+8]
0x1800896d9  mov     [rbx+8], eax
0x1800896dc  mov     eax, [r14+4]
0x1800896e0  mov     [rbx+4], eax
0x1800896e3  mov     qword ptr [rbx+0Ch], 180001h
0x1800896eb  mov     [rbx+14h], r15
0x1800896ef  mov     [rbx+1Ch], r15
0x1800896f3  mov     [rbx+24h], r15d
0x1800896f7  mov     r13, [rdi+108h]
0x1800896fe  test    r13, r13
0x180089701  jz      short loc_18008971D
0x180089703  mov     rcx, [r13+28h]
0x180089707  test    rcx, rcx
0x18008970a  jz      short loc_18008971D
0x18008970c  add     rcx, 58h ; 'X'
0x180089710  xor     edx, edx
0x180089712  call    CreateColorSpaceInternalW
0x180089717  mov     r13, [r13+28h]
0x18008971b  jmp     short loc_18008972A
0x18008971d  mov     ecx, 14h; i
0x180089722  call    GetStockObject
0x180089727  mov     r13, r15
0x18008972a  mov     rdi, rax
0x18008972d  lea     r8, [rbp+3Fh+Size]
0x180089734  mov     edx, esi
0x180089736  mov     rcx, rbx
0x180089739  call    hrBitmapScanSize
0x18008973e  test    eax, eax
0x180089740  js      loc_1800898E6
0x180089746  mov     rcx, gs:60h
0x18008974f  mov     r12d, r15d
0x180089752  mov     r15d, dword ptr [rbp+3Fh+Size]
0x180089759  xor     edx, edx; Flags
0x18008975b  mov     r8d, r15d; Size
0x18008975e  mov     rcx, [rcx+30h]; HeapHandle
0x180089762  call    cs:__imp_RtlAllocateHeap
0x180089768  mov     r14, rax
0x18008976b  test    rax, rax
0x18008976e  jz      loc_1800898C3
0x180089774  mov     r8d, [rbx+8]
0x180089778  mov     r9d, esi
0x18008977b  mov     rdx, [rbp+3Fh+var_58]
0x18008977f  sub     r8d, esi
0x180089782  sub     r8d, [rbp+3Fh+arg_40]
0x180089789  mov     rcx, [rbp+3Fh+hdc]
0x18008978d  mov     [rsp+0D0h+cLines], r12d
0x180089792  mov     [rsp+0D0h+StartScan], r15d
0x180089797  mov     [rsp+0D0h+ySrc], r12d
0x18008979c  mov     qword ptr [rsp+0D0h+xSrc], rbx
0x1800897a1  mov     qword ptr [rsp+0D0h+h], rax
0x1800897a6  call    cs:__imp_NtGdiGetDIBitsInternal
0x1800897ac  xor     ecx, ecx
0x1800897ae  test    eax, eax
0x1800897b0  jnz     short loc_1800897D2
0x1800897b2  mov     rcx, gs:60h
0x1800897bb  mov     r8, r14; P
0x1800897be  xor     edx, edx; Flags
0x1800897c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800897c4  call    cs:__imp_RtlFreeHeap
0x1800897ca  mov     [rbx+8], esi
0x1800897cd  jmp     loc_1800898C3
0x1800897d2  mov     [rbx+8], esi
0x1800897d5  mov     r15, rcx
0x1800897d8  test    rdi, rdi
0x1800897db  jz      short loc_1800897F6
0x1800897dd  mov     r8, r13
0x1800897e0  mov     rdx, rdi
0x1800897e3  mov     r13, [rbp+3Fh+arg_0]
0x1800897e7  mov     rcx, r13; hdc
0x1800897ea  call    IcmSetSourceColorSpace
0x1800897ef  mov     r15, rax
0x1800897f2  xor     ecx, ecx
0x1800897f4  jmp     short loc_1800897FA
0x1800897f6  mov     r13, [rbp+3Fh+arg_0]
0x1800897fa  mov     eax, [rbp+3Fh+rop]
0x180089800  cmp     [rbp+3Fh+arg_30], ecx
0x180089803  jz      short loc_18008984C
0x180089805  cmp     eax, 0CC0020h
0x18008980a  jnz     short loc_18008984C
0x18008980c  mov     eax, [rbp+3Fh+arg_38]
0x180089812  mov     r9d, [rbp+3Fh+w]; w
0x180089816  mov     r8d, [rbp+3Fh+yDest]; yDest
0x18008981a  mov     edx, [rbp+3Fh+xDest]; xDest
0x18008981d  mov     [rsp+0D0h+ColorUse], ecx; ColorUse
0x180089821  mov     [rsp+0D0h+lpbmi], rbx; lpbmi
0x180089826  mov     [rsp+0D0h+lpvBits], r14; lpvBits
0x18008982b  mov     [rsp+0D0h+cLines], esi; cLines
0x18008982f  mov     [rsp+0D0h+StartScan], ecx; StartScan
0x180089833  mov     [rsp+0D0h+ySrc], ecx; ySrc
0x180089837  mov     rcx, r13; hdc
0x18008983a  mov     [rsp+0D0h+xSrc], eax; xSrc
0x18008983e  mov     eax, [rbp+3Fh+arg_20]
0x180089841  mov     [rsp+0D0h+h], eax; h
0x180089845  call    SetDIBitsToDevice
0x18008984a  jmp     short loc_180089895
0x18008984c  mov     r9d, [rbp+3Fh+w]; DestWidth
0x180089850  mov     r8d, [rbp+3Fh+yDest]; yDest
0x180089854  mov     edx, [rbp+3Fh+xDest]; xDest
0x180089857  mov     [rsp+60h], eax; rop
0x18008985b  mov     eax, [rbp+3Fh+SrcWidth]
0x180089861  mov     [rsp+0D0h+ColorUse], ecx; iUsage
0x180089865  mov     [rsp+0D0h+lpbmi], rbx; lpbmi
0x18008986a  mov     [rsp+0D0h+lpvBits], r14; lpBits
0x18008986f  mov     [rsp+0D0h+cLines], esi; SrcHeight
0x180089873  mov     [rsp+0D0h+StartScan], eax; SrcWidth
0x180089877  mov     eax, [rbp+3Fh+arg_38]
0x18008987d  mov     [rsp+0D0h+ySrc], ecx; ySrc
0x180089881  mov     rcx, r13; hdc
0x180089884  mov     [rsp+0D0h+xSrc], eax; xSrc
0x180089888  mov     eax, [rbp+3Fh+arg_20]
0x18008988b  mov     [rsp+0D0h+h], eax; DestHeight
0x18008988f  call    cs:__imp_StretchDIBits
0x180089895  mov     r12d, eax
0x180089898  test    r15, r15
0x18008989b  jz      short loc_1800898AB
0x18008989d  xor     r8d, r8d
0x1800898a0  mov     rdx, r15
0x1800898a3  mov     rcx, r13; hdc
0x1800898a6  call    IcmSetSourceColorSpace
0x1800898ab  mov     rcx, gs:60h
0x1800898b4  mov     r8, r14; P
0x1800898b7  xor     edx, edx; Flags
0x1800898b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800898bd  call    cs:__imp_RtlFreeHeap
0x1800898c3  test    rdi, rdi
0x1800898c6  jz      short loc_1800898D1
0x1800898c8  mov     rcx, rdi
0x1800898cb  call    cs:__imp_NtGdiDeleteColorSpace
0x1800898d1  xor     ebx, ebx
0x1800898d3  lea     rcx, [rbp+3Fh+var_60]
0x1800898d7  test    r12d, r12d
0x1800898da  setnz   bl
0x1800898dd  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800898e2  mov     eax, ebx
0x1800898e4  jmp     short loc_1800898F1
0x1800898e6  lea     rcx, [rbp+3Fh+var_60]
0x1800898ea  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800898ef  xor     eax, eax
0x1800898f1  add     rsp, 98h
0x1800898f8  pop     r15
0x1800898fa  pop     r14
0x1800898fc  pop     r13
0x1800898fe  pop     r12
0x180089900  pop     rdi
0x180089901  pop     rsi
0x180089902  pop     rbx
0x180089903  pop     rbp
0x180089904  retn
```
