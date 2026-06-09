# COleServerItem::GetMetafileData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180275bd0`
- end: `0x180275e1b`
- name: `?GetMetafileData@COleServerItem@@MEAAHPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `587`
- prototype: `int __fastcall(COleServerItem *this, tagFORMATETC *lpFormatEtc, tagSTGMEDIUM *lpStgMedium)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18020f580`
- `0x18026bbc0`
- `0x180275bd0`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x180275cf6`
- `KERNEL32!GlobalAlloc` at `0x180275cf6`
- `KERNEL32!GlobalLock` at `0x180275d70`
- `KERNEL32!GlobalLock` at `0x180275d70`
- `KERNEL32!GlobalUnlock` at `0x180275de0`
- `KERNEL32!GlobalUnlock` at `0x180275de0`
- `KERNEL32!GlobalFree` at `0x180275d8a`
- `KERNEL32!GlobalFree` at `0x180275d8a`
- `GDI32!DeleteMetaFile` at `0x180275d07`
- `GDI32!DeleteMetaFile` at `0x180275d39`
- `GDI32!DeleteMetaFile` at `0x180275d81`
- `GDI32!DeleteMetaFile` at `0x180275d07`
- `GDI32!DeleteMetaFile` at `0x180275d39`
- `GDI32!DeleteMetaFile` at `0x180275d81`
- `GDI32!CloseMetaFile` at `0x180275cde`
- `GDI32!CloseMetaFile` at `0x180275d30`
- `GDI32!CloseMetaFile` at `0x180275cde`
- `GDI32!CloseMetaFile` at `0x180275d30`
- `GDI32!CreateMetaFileW` at `0x180275c28`
- `GDI32!CreateMetaFileW` at `0x180275c28`
- `GDI32!DeleteDC` at `0x180275cc8`
- `GDI32!DeleteDC` at `0x180275d5f`
- `GDI32!DeleteDC` at `0x180275cc8`
- `GDI32!DeleteDC` at `0x180275d5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall COleServerItem::GetMetafileData(
        COleServerItem *this,
        tagFORMATETC *lpFormatEtc,
        tagSTGMEDIUM *lpStgMedium)
{
  HDC MetaFileW; // rax
  HDC__ *v7; // rax
  HDC v8; // rbx
  int v9; // edi
  HDC__ *m_hAttribDC; // rdx
  void (__fastcall *ReleaseAttribDC)(CDC *); // rax
  HDC v12; // rax
  HMETAFILE v13; // rsi
  HBITMAP__ *v14; // rax
  HBITMAP__ *v15; // rdi
  unsigned int v16; // ebx
  HDC__ *m_hDC; // rax
  HDC v18; // rax
  HMETAFILE v19; // rax
  HDC v20; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  int cx; // eax
  int cy; // eax
  CMetaFileDC dc; // [rsp+30h] [rbp-20h] BYREF
  CSize size; // [rsp+88h] [rbp+38h] BYREF

  if ( (lpFormatEtc->tymed & 0x20) == 0 || lpStgMedium->hBitmap )
    return 0;
  memset(&dc.m_hDC, 0, 20);
  dc.__vftable = (CMetaFileDC_vtbl *)CMetaFileDC::`vftable';
  MetaFileW = CreateMetaFileW(0);
  if ( CDC::Attach(&dc, MetaFileW) )
  {
    v7 = _AfxOleCreateDC(lpFormatEtc->ptd);
    v8 = v7;
    if ( v7 )
    {
      CMetaFileDC::SetAttribDC(&dc, v7);
      size = 0;
      v9 = this->OnDrawEx(this, &dc, (tagDVASPECT)lpFormatEtc->dwAspect, &size);
      m_hAttribDC = dc.m_hAttribDC;
      if ( dc.m_hDC )
        m_hAttribDC = 0;
      dc.m_hAttribDC = m_hAttribDC;
      if ( dc.m_hDC == m_hAttribDC )
      {
        ReleaseAttribDC = dc.ReleaseAttribDC;
        if ( ReleaseAttribDC == CDC::ReleaseAttribDC )
          dc.m_hAttribDC = 0;
        else
          ReleaseAttribDC(&dc);
      }
      DeleteDC(v8);
      if ( v9 )
      {
        v12 = CDC::Detach(&dc);
        v13 = CloseMetaFile(v12);
        if ( v13 )
        {
          v14 = (HBITMAP__ *)GlobalAlloc(0x2002u, 0x18u);
          v15 = v14;
          if ( v14 )
          {
            v22 = GlobalLock(v14);
            v23 = v22;
            if ( v22 )
            {
              *(_DWORD *)v22 = 8;
              v22[2] = v13;
              cx = size.cx;
              if ( !size.cx && !size.cy )
              {
                this->OnGetExtent(this, (tagDVASPECT)lpFormatEtc->dwAspect, &size);
                cx = size.cx;
              }
              *((_DWORD *)v23 + 1) = cx;
              cy = size.cy;
              *((_DWORD *)v23 + 2) = size.cy;
              if ( cy < 0 )
                *((_DWORD *)v23 + 2) = -cy;
              GlobalUnlock(v15);
              lpStgMedium->hBitmap = v15;
              lpStgMedium->tymed = 32;
              v16 = 1;
              goto LABEL_16;
            }
            DeleteMetaFile(v13);
            GlobalFree(v15);
          }
          else
          {
            DeleteMetaFile(v13);
          }
        }
      }
    }
  }
  v16 = 0;
LABEL_16:
  dc.__vftable = (CMetaFileDC_vtbl *)CMetaFileDC::`vftable';
  m_hDC = dc.m_hDC;
  if ( dc.m_hDC )
  {
    v18 = CDC::Detach(&dc);
    v19 = CloseMetaFile(v18);
    DeleteMetaFile(v19);
    m_hDC = dc.m_hDC;
  }
  dc.__vftable = (CMetaFileDC_vtbl *)CDC::`vftable';
  if ( m_hDC )
  {
    v20 = CDC::Detach(&dc);
    DeleteDC(v20);
  }
  return v16;
}

```

## disassembly

```asm
0x180275bd0  mov     [rsp-28h+arg_0], rbx
0x180275bd5  mov     [rsp-28h+arg_10], rsi
0x180275bda  mov     [rsp-28h+arg_18], rdi
0x180275bdf  push    rbp
0x180275be0  push    r12
0x180275be2  push    r13
0x180275be4  push    r14
0x180275be6  push    r15
0x180275be8  mov     rbp, rsp
0x180275beb  sub     rsp, 50h
0x180275bef  mov     r14, lpStgMedium
0x180275bf2  mov     r15, lpFormatEtc
0x180275bf5  mov     r12, this
0x180275bf8  test    byte ptr [lpFormatEtc+18h], 20h
0x180275bfc  jz      loc_180275DFB
0x180275c02  xor     r13d, r13d
0x180275c05  cmp     [lpStgMedium+8], r13
0x180275c09  jnz     loc_180275DFB
0x180275c0f  xorps   xmm0, xmm0
0x180275c12  movdqu  xmmword ptr [rbp+dc.m_hDC], xmm0
0x180275c17  mov     [rbp+dc.m_bPrinting], r13d
0x180275c1b  lea     rax, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x180275c22  mov     [rbp+dc.__vftable], rax
0x180275c26  xor     ecx, ecx; pszFile
0x180275c28  call    cs:__imp_CreateMetaFileW
0x180275c2e  mov     lpFormatEtc, rax; hDC
0x180275c31  lea     this, [rbp+dc]; this
0x180275c35  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180275c3a  test    eax, eax
0x180275c3c  jz      loc_180275D0D
0x180275c42  mov     this, [r15+8]; ptd
0x180275c46  call    ?_AfxOleCreateDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _AfxOleCreateDC(tagDVTARGETDEVICE *)
0x180275c4b  mov     rbx, rax
0x180275c4e  test    rax, rax
0x180275c51  jz      loc_180275D0D
0x180275c57  mov     lpFormatEtc, rax; hDC
0x180275c5a  lea     this, [rbp+dc]; this
0x180275c5e  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x180275c63  mov     qword ptr [rbp+size.cx], r13
0x180275c67  mov     this, [r12]
0x180275c6b  mov     rax, [this+0C8h]
0x180275c72  lea     r9, [rbp+size]
0x180275c76  mov     r8d, [r15+10h]
0x180275c7a  lea     lpFormatEtc, [rbp+dc]
0x180275c7e  mov     this, r12
0x180275c81  call    cs:__guard_dispatch_icall_fptr
0x180275c87  mov     edi, eax
0x180275c89  mov     lpFormatEtc, [rbp+dc.m_hAttribDC]
0x180275c8d  mov     this, [rbp+dc.m_hDC]
0x180275c91  test    this, this
0x180275c94  cmovnz  lpFormatEtc, r13
0x180275c98  mov     [rbp+dc.m_hAttribDC], lpFormatEtc
0x180275c9c  cmp     this, lpFormatEtc
0x180275c9f  jnz     short loc_180275CC5
0x180275ca1  mov     this, [rbp+dc.__vftable]
0x180275ca5  mov     rax, [this+38h]
0x180275ca9  lea     this, ?ReleaseAttribDC@CDC@@UEAAXXZ; CDC::ReleaseAttribDC(void)
0x180275cb0  cmp     rax, this
0x180275cb3  jnz     short loc_180275CBB
0x180275cb5  mov     [rbp+dc.m_hAttribDC], r13
0x180275cb9  jmp     short loc_180275CC5
0x180275cbb  lea     this, [rbp+dc]
0x180275cbf  call    cs:__guard_dispatch_icall_fptr
0x180275cc5  mov     this, rbx; hdc
0x180275cc8  call    cs:__imp_DeleteDC
0x180275cce  test    edi, edi
0x180275cd0  jz      short loc_180275D0D
0x180275cd2  lea     this, [rbp+dc]; this
0x180275cd6  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180275cdb  mov     this, rax; hdc
0x180275cde  call    cs:__imp_CloseMetaFile
0x180275ce4  mov     rsi, rax
0x180275ce7  test    rax, rax
0x180275cea  jz      short loc_180275D0D
0x180275cec  mov     edx, 18h; dwBytes
0x180275cf1  mov     ecx, 2002h; uFlags
0x180275cf6  call    cs:__imp_GlobalAlloc
0x180275cfc  mov     rdi, rax
0x180275cff  test    rax, rax
0x180275d02  jnz     short loc_180275D6D
0x180275d04  mov     this, rsi; hmf
0x180275d07  call    cs:__imp_DeleteMetaFile
0x180275d0d  mov     ebx, r13d
0x180275d10  lea     rax, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x180275d17  mov     [rbp+dc.__vftable], rax
0x180275d1b  mov     rax, [rbp+dc.m_hDC]
0x180275d1f  test    rax, rax
0x180275d22  jz      short loc_180275D43
0x180275d24  lea     this, [rbp+dc]; this
0x180275d28  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180275d2d  mov     this, rax; hdc
0x180275d30  call    cs:__imp_CloseMetaFile
0x180275d36  mov     this, rax; hmf
0x180275d39  call    cs:__imp_DeleteMetaFile
0x180275d3f  mov     rax, [rbp+dc.m_hDC]
0x180275d43  lea     this, ??_7CDC@@6B@; const CDC::`vftable'
0x180275d4a  mov     [rbp+dc.__vftable], this
0x180275d4e  test    rax, rax
0x180275d51  jz      short loc_180275D66
0x180275d53  lea     this, [rbp+dc]; this
0x180275d57  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180275d5c  mov     this, rax; hdc
0x180275d5f  call    cs:__imp_DeleteDC
0x180275d65  nop
0x180275d66  mov     eax, ebx
0x180275d68  jmp     loc_180275DFD
0x180275d6d  mov     this, rdi; hMem
0x180275d70  call    cs:__imp_GlobalLock
0x180275d76  mov     rbx, rax
0x180275d79  test    rax, rax
0x180275d7c  jnz     short loc_180275D95
0x180275d7e  mov     this, rsi; hmf
0x180275d81  call    cs:__imp_DeleteMetaFile
0x180275d87  mov     this, rdi; hMem
0x180275d8a  call    cs:__imp_GlobalFree
0x180275d90  jmp     loc_180275D0D
0x180275d95  mov     dword ptr [rax], 8
0x180275d9b  mov     [rax+10h], rsi
0x180275d9f  mov     eax, [rbp+size.cx]
0x180275da2  test    eax, eax
0x180275da4  jnz     short loc_180275DCB
0x180275da6  cmp     [rbp+size.cy], r13d
0x180275daa  jnz     short loc_180275DCB
0x180275dac  mov     rax, [r12]
0x180275db0  lea     lpStgMedium, [rbp+size]
0x180275db4  mov     edx, [r15+10h]
0x180275db8  mov     this, r12
0x180275dbb  mov     rax, [rax+0D8h]
0x180275dc2  call    cs:__guard_dispatch_icall_fptr
0x180275dc8  mov     eax, [rbp+size.cx]
0x180275dcb  mov     [rbx+4], eax
0x180275dce  mov     eax, [rbp+size.cy]
0x180275dd1  mov     [rbx+8], eax
0x180275dd4  test    eax, eax
0x180275dd6  jns     short loc_180275DDD
0x180275dd8  neg     eax
0x180275dda  mov     [rbx+8], eax
0x180275ddd  mov     this, rdi; hMem
0x180275de0  call    cs:__imp_GlobalUnlock
0x180275de6  mov     [r14+8], rdi
0x180275dea  mov     dword ptr [r14], 20h ; ' '
0x180275df1  mov     ebx, 1
0x180275df6  jmp     loc_180275D10
0x180275dfb  xor     eax, eax
0x180275dfd  lea     r11, [rsp+50h+var_s0]
0x180275e02  mov     rbx, [r11+30h]
0x180275e06  mov     rsi, [r11+40h]
0x180275e0a  mov     rdi, [r11+48h]
0x180275e0e  mov     rsp, r11
0x180275e11  pop     r15
0x180275e13  pop     r14
0x180275e15  pop     r13
0x180275e17  pop     r12
0x180275e19  pop     rbp
0x180275e1a  retn
```
