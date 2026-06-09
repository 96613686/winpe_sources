# DriverGdi::FillRegion(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpRegion const *,DpBrush const *)

- ea: `0x1800839b0`
- end: `0x180083be4`
- name: `?FillRegion@DriverGdi@@UEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpRegion@@PEBUDpBrush@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(DriverGdi *, __int64, struct DpBitmap *, _DWORD *, struct DpRegion *, _DWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180022450`
- `0x18003ad50`
- `0x18003b578`
- `0x18003b634`
- `0x1800839b0`
- `0x180083bf0`
- `0x180084de8`
- `0x1800e6db4`
- `0x1800e8f30`
- `0x180175010`

## import_xrefs

- `USER32!ReleaseDC` at `0x180083b54`
- `USER32!ReleaseDC` at `0x180083b54`
- `GDI32!FillRgn` at `0x180083b1d`
- `GDI32!FillRgn` at `0x180083b1d`
- `GDI32!DeleteObject` at `0x180083b72`
- `GDI32!DeleteObject` at `0x180083b72`

## pseudocode

```c
__int64 __fastcall DriverGdi::FillRegion(
        DriverGdi *a1,
        __int64 a2,
        struct DpBitmap *a3,
        _DWORD *a4,
        struct DpRegion *a5,
        _DWORD *a6)
{
  _DWORD *v6; // r14
  unsigned int v7; // ebx
  struct DpBitmap *v9; // r13
  int *v12; // rdi
  bool v13; // zf
  int v14; // edx
  int v15; // r8d
  int v16; // eax
  CopyOnWriteBitmap *Hdc; // rax
  HDC v18; // r13
  BOOL v19; // edi
  HWND v20; // rcx
  unsigned int v22; // [rsp+48h] [rbp-49h] BYREF
  HBRUSH hbr; // [rsp+50h] [rbp-41h]
  _DWORD v24[2]; // [rsp+58h] [rbp-39h] BYREF
  int v25; // [rsp+60h] [rbp-31h]
  int v26; // [rsp+64h] [rbp-2Dh]
  _DWORD v27[6]; // [rsp+68h] [rbp-29h] BYREF
  HRGN hrgn; // [rsp+80h] [rbp-11h]
  int v29; // [rsp+88h] [rbp-9h] BYREF
  unsigned int v30; // [rsp+8Ch] [rbp-5h]
  __m128i si128; // [rsp+90h] [rbp-1h]
  __int64 v32; // [rsp+A0h] [rbp+Fh]
  int v33; // [rsp+A8h] [rbp+17h]

  v6 = a6;
  v7 = 0;
  v9 = a3;
  if ( *a6 || !(unsigned int)DriverGdi::IsSolidColor(a1, a2, (unsigned int)a6[1]) )
  {
    v12 = (int *)a5;
  }
  else
  {
    v12 = (int *)a5;
    v32 = 0;
    v30 = v30 & 0xFFFFFFF8 | 1;
    v13 = (*((_BYTE *)a5 + 4) & 1) == 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v29 = 1733452849;
    v33 = 0;
    if ( !v13 )
    {
      v14 = *(_DWORD *)(a2 + 312);
      v15 = *(_DWORD *)(a2 + 316);
      v16 = *(_DWORD *)(a2 + 324) - v15;
      v25 = *(_DWORD *)(a2 + 320) - v14;
      v26 = v16;
      v24[0] = v14;
      v24[1] = v15;
      DpRegion::Set((DpRegion *)&v29, v14, v15, v25, v16);
      v12 = &v29;
      a4 = v24;
    }
    if ( (v12[1] & 2) != 0 )
      goto LABEL_12;
    ConvertRegionToGdi::ConvertRegionToGdi((ConvertRegionToGdi *)v27, (const struct DpRegion *)v12);
    if ( v27[0] == 1198932785 )
    {
      hbr = DriverGdi::GetBrush(
              a1,
              (*((unsigned __int8 *)v6 + 4) << 16)
            | (unsigned __int8)BYTE2(v6[1])
            | ((unsigned __int8)BYTE1(v6[1]) << 8));
      Hdc = DpContext::GetHdc((DpContext *)a2, v9);
      v22 = 0;
      v18 = (HDC)Hdc;
      LODWORD(a6) = 0;
      if ( Hdc )
      {
        (*(void (__fastcall **)(DriverGdi *, CopyOnWriteBitmap *, __int64, _DWORD *, unsigned int *, _DWORD **, _DWORD))(*(_QWORD *)a1 + 40LL))(
          a1,
          Hdc,
          a2,
          a4,
          &v22,
          &a6,
          0);
        v19 = FillRgn(v18, hrgn, hbr);
        (*(void (__fastcall **)(DriverGdi *, HDC, _QWORD, _QWORD))(*(_QWORD *)a1 + 48LL))(
          a1,
          v18,
          v22,
          (unsigned int)a6);
        v20 = *(HWND *)(a2 + 632);
        if ( v20 )
          ReleaseDC(v20, v18);
        LOBYTE(v7) = !v19;
        if ( v27[0] == 1198932785 )
          DeleteObject(hrgn);
LABEL_12:
        DpRegion::~DpRegion((DpRegion *)&v29);
        return v7;
      }
      v9 = a3;
    }
    ConvertRegionToGdi::~ConvertRegionToGdi((ConvertRegionToGdi *)v27);
    DpRegion::~DpRegion((DpRegion *)&v29);
  }
  return DpDriver::FillRegion(a1, a2, v9, a4, v12, v6);
}

```

## disassembly

```asm
0x1800839b0  mov     rax, rsp
0x1800839b3  mov     [rax+8], rbx
0x1800839b7  mov     [rax+10h], rsi
0x1800839bb  mov     [rax+20h], rdi
0x1800839bf  mov     [rax+18h], r8
0x1800839c3  push    rbp
0x1800839c4  push    r12
0x1800839c6  push    r13
0x1800839c8  push    r14
0x1800839ca  push    r15
0x1800839cc  lea     rbp, [rax-4Fh]
0x1800839d0  sub     rsp, 0B0h
0x1800839d7  mov     r14, [rbp+47h+arg_28]
0x1800839db  xor     ebx, ebx
0x1800839dd  mov     r12, r9
0x1800839e0  mov     r13, r8
0x1800839e3  mov     rsi, rdx
0x1800839e6  mov     r15, rcx
0x1800839e9  cmp     [r14], ebx
0x1800839ec  jnz     loc_180083BA3
0x1800839f2  mov     r8d, [r14+4]
0x1800839f6  call    ?IsSolidColor@DriverGdi@@AEAAHPEAVDpContext@@VGpColor@GpRuntime@@@Z; DriverGdi::IsSolidColor(DpContext *,GpRuntime::GpColor)
0x1800839fb  test    eax, eax
0x1800839fd  jz      loc_180083BA3
0x180083a03  mov     eax, [rbp+47h+var_4C]
0x180083a06  mov     rdi, [rbp+47h+arg_20]
0x180083a0a  and     eax, 0FFFFFFF9h
0x180083a0d  movdqa  xmm0, cs:__xmm@0040000000400000ffc00000ffc00000
0x180083a15  or      eax, 1
0x180083a18  mov     [rbp+47h+var_38], rbx
0x180083a1c  mov     [rbp+47h+var_4C], eax
0x180083a1f  test    byte ptr [rdi+4], 1
0x180083a23  movdqu  [rbp+47h+var_48], xmm0
0x180083a28  mov     [rbp+47h+var_50], 67526431h
0x180083a2f  mov     [rbp+47h+var_30], ebx
0x180083a32  jz      short loc_180083A77
0x180083a34  mov     edx, [rsi+138h]; int
0x180083a3a  lea     rcx, [rbp+47h+var_50]; this
0x180083a3e  mov     r8d, [rsi+13Ch]; int
0x180083a45  mov     r9d, [rsi+140h]
0x180083a4c  mov     eax, [rsi+144h]
0x180083a52  sub     r9d, edx; int
0x180083a55  sub     eax, r8d
0x180083a58  mov     [rbp+47h+var_78], r9d
0x180083a5c  mov     [rbp+47h+var_74], eax
0x180083a5f  mov     [rsp+0D0h+var_B0], eax; int
0x180083a63  mov     [rbp+47h+var_80], edx
0x180083a66  mov     [rbp+47h+var_7C], r8d
0x180083a6a  call    ?Set@DpRegion@@QEAAXHHHH@Z; DpRegion::Set(int,int,int,int)
0x180083a6f  lea     rdi, [rbp+47h+var_50]
0x180083a73  lea     r12, [rbp+47h+var_80]
0x180083a77  test    byte ptr [rdi+4], 2
0x180083a7b  jnz     loc_180083B7E
0x180083a81  mov     rdx, rdi; struct DpRegion *
0x180083a84  lea     rcx, [rbp+47h+var_70]; this
0x180083a88  call    ??0ConvertRegionToGdi@@QEAA@PEBVDpRegion@@@Z; ConvertRegionToGdi::ConvertRegionToGdi(DpRegion const *)
0x180083a8d  cmp     [rbp+47h+var_70], 47764331h
0x180083a94  jnz     loc_180083B8F
0x180083a9a  mov     ecx, [r14+4]
0x180083a9e  mov     eax, ecx
0x180083aa0  shr     eax, 8
0x180083aa3  movzx   edx, al
0x180083aa6  shr     ecx, 10h
0x180083aa9  movzx   eax, cl
0x180083aac  mov     rcx, r15; this
0x180083aaf  shl     edx, 8
0x180083ab2  or      edx, eax
0x180083ab4  movzx   eax, byte ptr [r14+4]
0x180083ab9  shl     eax, 10h
0x180083abc  or      edx, eax; unsigned int
0x180083abe  call    ?GetBrush@DriverGdi@@AEAAPEAUHBRUSH__@@K@Z; DriverGdi::GetBrush(ulong)
0x180083ac3  mov     rdx, r13; struct DpBitmap *
0x180083ac6  mov     [rbp+47h+hbr], rax
0x180083aca  mov     rcx, rsi; this
0x180083acd  call    ?GetHdc@DpContext@@QEAAPEAUHDC__@@PEAVDpBitmap@@@Z; DpContext::GetHdc(DpBitmap *)
0x180083ad2  mov     [rbp+47h+var_90], ebx
0x180083ad5  mov     r13, rax
0x180083ad8  mov     dword ptr [rbp+47h+arg_28], ebx
0x180083adb  test    rax, rax
0x180083ade  jz      loc_180083B8B
0x180083ae4  mov     rcx, [r15]
0x180083ae7  mov     r9, r12
0x180083aea  mov     [rsp+0D0h+var_A0], ebx
0x180083aee  mov     r8, rsi
0x180083af1  mov     rdx, r13
0x180083af4  mov     rax, [rcx+28h]
0x180083af8  lea     rcx, [rbp+47h+arg_28]
0x180083afc  mov     qword ptr [rsp+0D0h+var_A8], rcx
0x180083b01  lea     rcx, [rbp+47h+var_90]
0x180083b05  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180083b0a  mov     rcx, r15
0x180083b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b12  mov     r8, [rbp+47h+hbr]; hbr
0x180083b16  mov     rcx, r13; hdc
0x180083b19  mov     rdx, [rbp+47h+hrgn]; hrgn
0x180083b1d  call    cs:__imp_FillRgn
0x180083b24  nop     dword ptr [rax+rax+00h]
0x180083b29  mov     rcx, [r15]
0x180083b2c  mov     rdx, r13
0x180083b2f  mov     r9d, dword ptr [rbp+47h+arg_28]
0x180083b33  mov     edi, eax
0x180083b35  mov     r8d, [rbp+47h+var_90]
0x180083b39  mov     rax, [rcx+30h]
0x180083b3d  mov     rcx, r15
0x180083b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b45  mov     rcx, [rsi+278h]; hWnd
0x180083b4c  test    rcx, rcx
0x180083b4f  jz      short loc_180083B60
0x180083b51  mov     rdx, r13; hDC
0x180083b54  call    cs:__imp_ReleaseDC
0x180083b5b  nop     dword ptr [rax+rax+00h]
0x180083b60  test    edi, edi
0x180083b62  setz    bl
0x180083b65  cmp     [rbp+47h+var_70], 47764331h
0x180083b6c  jnz     short loc_180083B7E
0x180083b6e  mov     rcx, [rbp+47h+hrgn]; ho
0x180083b72  call    cs:__imp_DeleteObject
0x180083b79  nop     dword ptr [rax+rax+00h]
0x180083b7e  lea     rcx, [rbp+47h+var_50]; this
0x180083b82  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x180083b87  mov     eax, ebx
0x180083b89  jmp     short loc_180083BC2
0x180083b8b  mov     r13, [rbp+47h+arg_10]
0x180083b8f  lea     rcx, [rbp+47h+var_70]; this
0x180083b93  call    ??1ConvertRegionToGdi@@QEAA@XZ; ConvertRegionToGdi::~ConvertRegionToGdi(void)
0x180083b98  lea     rcx, [rbp+47h+var_50]; this
0x180083b9c  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x180083ba1  jmp     short loc_180083BA7
0x180083ba3  mov     rdi, [rbp+47h+arg_20]
0x180083ba7  mov     qword ptr [rsp+0D0h+var_A8], r14
0x180083bac  mov     r9, r12
0x180083baf  mov     r8, r13
0x180083bb2  mov     qword ptr [rsp+0D0h+var_B0], rdi
0x180083bb7  mov     rdx, rsi
0x180083bba  mov     rcx, r15
0x180083bbd  call    ?FillRegion@DpDriver@@UEAA?AW4Status@@PEAVDpContext@@PEAVDpBitmap@@PEBVGpRect@GpRuntime@@PEBVDpRegion@@PEBUDpBrush@@@Z; DpDriver::FillRegion(DpContext *,DpBitmap *,GpRuntime::GpRect const *,DpRegion const *,DpBrush const *)
0x180083bc2  lea     r11, [rsp+0D0h+var_20]
0x180083bca  mov     rbx, [r11+30h]
0x180083bce  mov     rsi, [r11+38h]
0x180083bd2  mov     rdi, [r11+48h]
0x180083bd6  mov     rsp, r11
0x180083bd9  pop     r15
0x180083bdb  pop     r14
0x180083bdd  pop     r13
0x180083bdf  pop     r12
0x180083be1  pop     rbp
0x180083be2  retn
```
