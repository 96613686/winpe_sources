# COleControl::GetMetafileData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1801e9720`
- end: `0x1801e996e`
- name: `?GetMetafileData@COleControl@@IEAAHPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `590`
- prototype: `int __fastcall(COleControl *this, tagFORMATETC *lpFormatEtc, tagSTGMEDIUM *lpStgMedium)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1801ec2d0`

## callees

- `0x1801e9330`
- `0x1801e9630`
- `0x1801e9720`
- `0x18020f580`
- `0x18026bbc0`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af470`
- `0x1802af6a0`
- `0x1802af780`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1801e987b`
- `KERNEL32!GlobalAlloc` at `0x1801e987b`
- `KERNEL32!GlobalLock` at `0x1801e98eb`
- `KERNEL32!GlobalLock` at `0x1801e98eb`
- `KERNEL32!GlobalUnlock` at `0x1801e992e`
- `KERNEL32!GlobalUnlock` at `0x1801e992e`
- `KERNEL32!GlobalFree` at `0x1801e9905`
- `KERNEL32!GlobalFree` at `0x1801e9905`
- `GDI32!DeleteMetaFile` at `0x1801e988c`
- `GDI32!DeleteMetaFile` at `0x1801e98b7`
- `GDI32!DeleteMetaFile` at `0x1801e98fc`
- `GDI32!DeleteMetaFile` at `0x1801e988c`
- `GDI32!DeleteMetaFile` at `0x1801e98b7`
- `GDI32!DeleteMetaFile` at `0x1801e98fc`
- `GDI32!CloseMetaFile` at `0x1801e9865`
- `GDI32!CloseMetaFile` at `0x1801e98ae`
- `GDI32!CloseMetaFile` at `0x1801e9865`
- `GDI32!CloseMetaFile` at `0x1801e98ae`
- `GDI32!CreateMetaFileW` at `0x1801e977e`
- `GDI32!CreateMetaFileW` at `0x1801e977e`
- `GDI32!DeleteDC` at `0x1801e9853`
- `GDI32!DeleteDC` at `0x1801e98dd`
- `GDI32!DeleteDC` at `0x1801e9853`
- `GDI32!DeleteDC` at `0x1801e98dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall COleControl::GetMetafileData(
        COleControl *this,
        tagFORMATETC *lpFormatEtc,
        tagSTGMEDIUM *lpStgMedium)
{
  HDC MetaFileW; // rax
  HDC__ *v7; // r15
  int v8; // edi
  int x; // ebx
  HDC__ *m_hAttribDC; // rcx
  void (__fastcall *ReleaseAttribDC)(CDC *); // rax
  HDC v12; // rax
  HMETAFILE v13; // rdi
  HBITMAP__ *v14; // rax
  HBITMAP__ *v15; // rbx
  unsigned int v16; // ebx
  HDC__ *m_hDC; // rax
  HDC v18; // rax
  HMETAFILE v19; // rax
  HDC v20; // rax
  _QWORD *v22; // rax
  CMetaFileDC dc; // [rsp+20h] [rbp-50h] BYREF
  int pcx; // [rsp+40h] [rbp-30h] BYREF
  CPoint cy; // [rsp+44h] [rbp-2Ch] BYREF
  CRect rc; // [rsp+50h] [rbp-20h] BYREF

  if ( (lpFormatEtc->tymed & 0x20) == 0 || lpStgMedium->hBitmap )
    return 0;
  memset(&dc.m_hDC, 0, 20);
  dc.__vftable = (CMetaFileDC_vtbl *)CMetaFileDC::`vftable';
  MetaFileW = CreateMetaFileW(0);
  if ( CDC::Attach(&dc, MetaFileW) )
  {
    v7 = _AfxOleCreateDC(lpFormatEtc->ptd);
    CMetaFileDC::SetAttribDC(&dc, v7);
    COleControl::GetControlSize(this, &pcx, (int *)&cy);
    *(_QWORD *)&rc.left = 0;
    v8 = pcx;
    rc.right = pcx;
    x = cy.x;
    rc.bottom = cy.x;
    CDC::SetMapMode(&dc, 8);
    CDC::SetWindowOrg(&dc, &cy, 0, 0);
    CDC::SetWindowExt(&dc, (CSize *)&cy, v8, x);
    COleControl::DrawMetafile(this, &dc, &rc);
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
    DeleteDC(v7);
    v12 = CDC::Detach(&dc);
    v13 = CloseMetaFile(v12);
    if ( v13 )
    {
      v14 = (HBITMAP__ *)GlobalAlloc(2u, 0x18u);
      v15 = v14;
      if ( v14 )
      {
        v22 = GlobalLock(v14);
        if ( v22 )
        {
          *(_DWORD *)v22 = 8;
          v22[2] = v13;
          *((_DWORD *)v22 + 1) = this->m_cxExtent;
          *((_DWORD *)v22 + 2) = this->m_cyExtent;
          GlobalUnlock(v15);
          lpStgMedium->hBitmap = v15;
          lpStgMedium->tymed = 32;
          v16 = 1;
          goto LABEL_14;
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
  v16 = 0;
LABEL_14:
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
0x1801e9720  mov     [rsp-38h+arg_18], rbx
0x1801e9725  push    rbp
0x1801e9726  push    rsi
0x1801e9727  push    rdi
0x1801e9728  push    r12
0x1801e972a  push    r13
0x1801e972c  push    r14
0x1801e972e  push    r15
0x1801e9730  mov     rbp, rsp
0x1801e9733  sub     rsp, 70h
0x1801e9737  mov     rax, cs:__security_cookie
0x1801e973e  xor     rax, rsp
0x1801e9741  mov     [rbp+var_10], rax
0x1801e9745  mov     rsi, lpStgMedium
0x1801e9748  mov     rbx, lpFormatEtc
0x1801e974b  mov     r14, this
0x1801e974e  test    byte ptr [lpFormatEtc+18h], 20h
0x1801e9752  jz      loc_1801E9948
0x1801e9758  xor     r12d, r12d
0x1801e975b  cmp     [lpStgMedium+8], r12
0x1801e975f  jnz     loc_1801E9948
0x1801e9765  xorps   xmm0, xmm0
0x1801e9768  movdqu  xmmword ptr [rbp+dc.m_hDC], xmm0
0x1801e976d  mov     [rbp+dc.m_bPrinting], r12d
0x1801e9771  lea     r13, ??_7CMetaFileDC@@6B@; const CMetaFileDC::`vftable'
0x1801e9778  mov     [rbp+dc.__vftable], r13
0x1801e977c  xor     ecx, ecx; pszFile
0x1801e977e  call    cs:__imp_CreateMetaFileW
0x1801e9784  mov     lpFormatEtc, rax; hDC
0x1801e9787  lea     this, [rbp+dc]; this
0x1801e978b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1801e9790  test    eax, eax
0x1801e9792  jz      loc_1801E9892
0x1801e9798  mov     this, [rbx+8]; ptd
0x1801e979c  call    ?_AfxOleCreateDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _AfxOleCreateDC(tagDVTARGETDEVICE *)
0x1801e97a1  mov     r15, rax
0x1801e97a4  mov     lpFormatEtc, rax; hDC
0x1801e97a7  lea     this, [rbp+dc]; this
0x1801e97ab  call    ?SetAttribDC@CMetaFileDC@@UEAAXPEAUHDC__@@@Z; CMetaFileDC::SetAttribDC(HDC__ *)
0x1801e97b0  lea     lpStgMedium, [rbp+cy]; pcy
0x1801e97b4  lea     lpFormatEtc, [rbp+pcx]; pcx
0x1801e97b8  mov     this, r14; this
0x1801e97bb  call    ?GetControlSize@COleControl@@QEAAXPEAH0@Z; COleControl::GetControlSize(int *,int *)
0x1801e97c0  mov     qword ptr [rbp+rc.left], r12
0x1801e97c4  mov     edi, [rbp+pcx]
0x1801e97c7  mov     [rbp+rc.right], edi
0x1801e97ca  mov     ebx, [rbp+cy.x]
0x1801e97cd  mov     [rbp+rc.bottom], ebx
0x1801e97d0  lea     edx, [r12+8]; nMapMode
0x1801e97d5  lea     this, [rbp+dc]; this
0x1801e97d9  call    ?SetMapMode@CDC@@UEAAHH@Z; CDC::SetMapMode(int)
0x1801e97de  xor     r9d, r9d; y
0x1801e97e1  xor     r8d, r8d; x
0x1801e97e4  lea     lpFormatEtc, [rbp+cy]; result
0x1801e97e8  lea     this, [rbp+dc]; this
0x1801e97ec  call    ?SetWindowOrg@CDC@@QEAA?AVCPoint@@HH@Z; CDC::SetWindowOrg(int,int)
0x1801e97f1  mov     r9d, ebx; y
0x1801e97f4  mov     r8d, edi; x
0x1801e97f7  lea     lpFormatEtc, [rbp+cy]; result
0x1801e97fb  lea     this, [rbp+dc]; this
0x1801e97ff  call    ?SetWindowExt@CDC@@UEAA?AVCSize@@HH@Z; CDC::SetWindowExt(int,int)
0x1801e9804  lea     lpStgMedium, [rbp+rc]; rc
0x1801e9808  lea     lpFormatEtc, [rbp+dc]; pDC
0x1801e980c  mov     this, r14; this
0x1801e980f  call    ?DrawMetafile@COleControl@@IEAAXPEAVCDC@@AEAVCRect@@@Z; COleControl::DrawMetafile(CDC *,CRect &)
0x1801e9814  mov     this, [rbp+dc.m_hAttribDC]
0x1801e9818  mov     rax, [rbp+dc.m_hDC]
0x1801e981c  test    rax, rax
0x1801e981f  cmovnz  this, r12
0x1801e9823  mov     [rbp+dc.m_hAttribDC], this
0x1801e9827  cmp     rax, this
0x1801e982a  jnz     short loc_1801E9850
0x1801e982c  mov     rax, [rbp+dc.__vftable]
0x1801e9830  mov     rax, [rax+38h]
0x1801e9834  lea     this, ?ReleaseAttribDC@CDC@@UEAAXXZ; CDC::ReleaseAttribDC(void)
0x1801e983b  cmp     rax, this
0x1801e983e  jnz     short loc_1801E9846
0x1801e9840  mov     [rbp+dc.m_hAttribDC], r12
0x1801e9844  jmp     short loc_1801E9850
0x1801e9846  lea     this, [rbp+dc]
0x1801e984a  call    cs:__guard_dispatch_icall_fptr
0x1801e9850  mov     this, r15; hdc
0x1801e9853  call    cs:__imp_DeleteDC
0x1801e9859  lea     this, [rbp+dc]; this
0x1801e985d  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801e9862  mov     this, rax; hdc
0x1801e9865  call    cs:__imp_CloseMetaFile
0x1801e986b  mov     rdi, rax
0x1801e986e  test    rax, rax
0x1801e9871  jz      short loc_1801E9892
0x1801e9873  mov     edx, 18h; dwBytes
0x1801e9878  lea     ecx, [lpFormatEtc-16h]; uFlags
0x1801e987b  call    cs:__imp_GlobalAlloc
0x1801e9881  mov     rbx, rax
0x1801e9884  test    rax, rax
0x1801e9887  jnz     short loc_1801E98E8
0x1801e9889  mov     this, rdi; hmf
0x1801e988c  call    cs:__imp_DeleteMetaFile
0x1801e9892  mov     ebx, r12d
0x1801e9895  mov     [rbp+dc.__vftable], r13
0x1801e9899  mov     rax, [rbp+dc.m_hDC]
0x1801e989d  test    rax, rax
0x1801e98a0  jz      short loc_1801E98C1
0x1801e98a2  lea     this, [rbp+dc]; this
0x1801e98a6  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801e98ab  mov     this, rax; hdc
0x1801e98ae  call    cs:__imp_CloseMetaFile
0x1801e98b4  mov     this, rax; hmf
0x1801e98b7  call    cs:__imp_DeleteMetaFile
0x1801e98bd  mov     rax, [rbp+dc.m_hDC]
0x1801e98c1  lea     this, ??_7CDC@@6B@; const CDC::`vftable'
0x1801e98c8  mov     [rbp+dc.__vftable], this
0x1801e98cc  test    rax, rax
0x1801e98cf  jz      short loc_1801E98E4
0x1801e98d1  lea     this, [rbp+dc]; this
0x1801e98d5  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801e98da  mov     this, rax; hdc
0x1801e98dd  call    cs:__imp_DeleteDC
0x1801e98e3  nop
0x1801e98e4  mov     eax, ebx
0x1801e98e6  jmp     short loc_1801E994A
0x1801e98e8  mov     this, rbx; hMem
0x1801e98eb  call    cs:__imp_GlobalLock
0x1801e98f1  mov     this, rax
0x1801e98f4  test    rax, rax
0x1801e98f7  jnz     short loc_1801E990D
0x1801e98f9  mov     this, rdi; hmf
0x1801e98fc  call    cs:__imp_DeleteMetaFile
0x1801e9902  mov     this, rbx; hMem
0x1801e9905  call    cs:__imp_GlobalFree
0x1801e990b  jmp     short loc_1801E9892
0x1801e990d  mov     dword ptr [rax], 8
0x1801e9913  mov     [rax+10h], rdi
0x1801e9917  mov     eax, [r14+148h]
0x1801e991e  mov     [this+4], eax
0x1801e9921  mov     eax, [r14+14Ch]
0x1801e9928  mov     [this+8], eax
0x1801e992b  mov     this, rbx; hMem
0x1801e992e  call    cs:__imp_GlobalUnlock
0x1801e9934  mov     [rsi+8], rbx
0x1801e9938  mov     dword ptr [rsi], 20h ; ' '
0x1801e993e  mov     ebx, 1
0x1801e9943  jmp     loc_1801E9895
0x1801e9948  xor     eax, eax
0x1801e994a  mov     this, [rbp+var_10]
0x1801e994e  xor     this, rsp; StackCookie
0x1801e9951  call    __security_check_cookie
0x1801e9956  mov     rbx, [rsp+70h+arg_18]
0x1801e995e  add     rsp, 70h
0x1801e9962  pop     r15
0x1801e9964  pop     r14
0x1801e9966  pop     r13
0x1801e9968  pop     r12
0x1801e996a  pop     rdi
0x1801e996b  pop     rsi
0x1801e996c  pop     rbp
0x1801e996d  retn
```
