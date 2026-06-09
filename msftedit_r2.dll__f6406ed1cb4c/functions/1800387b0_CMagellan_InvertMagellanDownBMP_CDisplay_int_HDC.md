# CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)

- ea: `0x1800387b0`
- end: `0x180038996`
- name: `?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z`
- size: `486`
- prototype: `int(CMagellan *__hidden this, struct CDisplay *, int, HDC)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180036ec4`
- `0x1800bc77c`
- `0x18013ad4c`
- `0x1801fe3c8`

## callees

- `0x1800387b0`
- `0x1800501ac`
- `0x1800ee9f8`
- `0x18016a21c`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180038967`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180038967`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180038842`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180038842`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18003887a`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18003887a`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180038861`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180038861`
- `ext-ms-win-gdi-draw-l1-1-1!DPtoLP` at `0x1800388a7`
- `ext-ms-win-gdi-draw-l1-1-1!DPtoLP` at `0x1800388c8`
- `ext-ms-win-gdi-draw-l1-1-1!DPtoLP` at `0x1800388a7`
- `ext-ms-win-gdi-draw-l1-1-1!DPtoLP` at `0x1800388c8`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x18003893e`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x18003893e`

## pseudocode

```c
__int64 __fastcall CMagellan::InvertMagellanDownBMP(HGDIOBJ *this, struct CDisplay *a2, int a3, HDC a4)
{
  unsigned int v7; // edi
  CTxtEdit **v9; // rbx
  HDC HDC; // rsi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r15
  struct tagPOINT v13; // [rsp+50h] [rbp-30h] BYREF
  _OWORD pv[2]; // [rsp+58h] [rbp-28h] BYREF
  tagPOINT pt; // [rsp+C0h] [rbp+40h] BYREF
  struct tagPOINT x1; // [rsp+C8h] [rbp+48h] BYREF

  if ( a2 )
  {
    v7 = *(_WORD *)this & 1;
    if ( v7 != a3 && this[1] )
    {
      pt = 0;
      x1 = 0;
      v9 = (CTxtEdit **)((char *)a2 + 16);
      memset(pv, 0, sizeof(pv));
      if ( a4 )
      {
        HDC = a4;
LABEL_9:
        CompatibleDC = CreateCompatibleDC(HDC);
        hdcSrc = CompatibleDC;
        if ( CompatibleDC )
        {
          SelectObject(CompatibleDC, this[1]);
          if ( GetObjectW(this[1], 32, pv) )
          {
            pt = *(tagPOINT *)((char *)pv + 4);
            DPtoLP(HDC, &pt, 1);
            x1 = 0;
            DPtoLP(hdcSrc, &x1, 1);
            v13 = 0;
            CDisplay::PointFromPointuv(a2, &v13, (const struct Ptls6::tagLSPOINTUV *)(this + 2), 0, 0);
            BitBlt(HDC, v13.x - (pt.x >> 1) - 1, v13.y - (pt.y >> 1) + 1, pt.x, pt.y, hdcSrc, x1.x, x1.y, 0x990066u);
            *(_WORD *)this = *(_WORD *)this & 0xFFFE | v7 ^ 1;
          }
          DeleteDC(hdcSrc);
        }
        if ( !a4 )
        {
          if ( *((_BYTE *)v9 + 33) )
            CTxtEdit::TxReleaseDC(*v9, HDC);
          *((_BYTE *)v9 + 33) = 0;
        }
        return v7;
      }
      HDC = CDevDesc::GetHDC((struct CDisplay *)((char *)a2 + 16));
      if ( HDC )
        goto LABEL_9;
    }
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x1800387b0  mov     [rsp-38h+arg_10], rbx
0x1800387b5  push    rbp
0x1800387b6  push    rsi
0x1800387b7  push    rdi
0x1800387b8  push    r12
0x1800387ba  push    r13
0x1800387bc  push    r14
0x1800387be  push    r15
0x1800387c0  mov     rbp, rsp
0x1800387c3  sub     rsp, 80h
0x1800387ca  xor     r15d, r15d
0x1800387cd  mov     r12, r9
0x1800387d0  mov     r13, rdx
0x1800387d3  mov     r14, rcx
0x1800387d6  test    rdx, rdx
0x1800387d9  jz      short loc_180038804
0x1800387db  movzx   edi, word ptr [rcx]
0x1800387de  and     edi, 1
0x1800387e1  cmp     edi, r8d
0x1800387e4  jnz     short loc_180038808
0x1800387e6  mov     eax, edi
0x1800387e8  mov     rbx, [rsp+80h+arg_10]
0x1800387f0  add     rsp, 80h
0x1800387f7  pop     r15
0x1800387f9  pop     r14
0x1800387fb  pop     r13
0x1800387fd  pop     r12
0x1800387ff  pop     rdi
0x180038800  pop     rsi
0x180038801  pop     rbp
0x180038802  retn
0x180038804  xor     eax, eax
0x180038806  jmp     short loc_1800387E8
0x180038808  cmp     [rcx+8], r15
0x18003880c  jz      short loc_1800387E6
0x18003880e  mov     qword ptr [rbp+pt.x], r15
0x180038812  xorps   xmm0, xmm0
0x180038815  mov     qword ptr [rbp+arg_8.x], r15
0x180038819  lea     rbx, [rdx+10h]
0x18003881d  movups  [rbp+pv], xmm0
0x180038821  movups  [rbp+var_18], xmm0
0x180038825  test    r12, r12
0x180038828  jz      short loc_18003882F
0x18003882a  mov     rsi, r12
0x18003882d  jmp     short loc_18003883F
0x18003882f  mov     rcx, rbx; this
0x180038832  call    ?GetHDC@CDevDesc@@QEAAPEAUHDC__@@XZ; CDevDesc::GetHDC(void)
0x180038837  mov     rsi, rax
0x18003883a  test    rax, rax
0x18003883d  jz      short loc_1800387E6
0x18003883f  mov     rcx, rsi; hdc
0x180038842  call    cs:__imp_CreateCompatibleDC
0x180038849  nop     dword ptr [rax+rax+00h]
0x18003884e  mov     r15, rax
0x180038851  test    rax, rax
0x180038854  jz      loc_180038973
0x18003885a  mov     rdx, [r14+8]; h
0x18003885e  mov     rcx, rax; hdc
0x180038861  call    cs:__imp_SelectObject
0x180038868  nop     dword ptr [rax+rax+00h]
0x18003886d  mov     rcx, [r14+8]; h
0x180038871  lea     r8, [rbp+pv]; pv
0x180038875  mov     edx, 20h ; ' '; c
0x18003887a  call    cs:__imp_GetObjectW
0x180038881  nop     dword ptr [rax+rax+00h]
0x180038886  test    eax, eax
0x180038888  jz      loc_180038964
0x18003888e  mov     eax, dword ptr [rbp+pv+4]
0x180038891  lea     rdx, [rbp+pt]; lppt
0x180038895  mov     [rbp+pt.x], eax
0x180038898  mov     r8d, 1; c
0x18003889e  mov     eax, dword ptr [rbp+pv+8]
0x1800388a1  mov     rcx, rsi; hdc
0x1800388a4  mov     [rbp+pt.y], eax
0x1800388a7  call    cs:__imp_DPtoLP
0x1800388ae  nop     dword ptr [rax+rax+00h]
0x1800388b3  mov     r8d, 1; c
0x1800388b9  mov     qword ptr [rbp+arg_8.x], 0
0x1800388c1  lea     rdx, [rbp+arg_8]; lppt
0x1800388c5  mov     rcx, r15; hdc
0x1800388c8  call    cs:__imp_DPtoLP
0x1800388cf  nop     dword ptr [rax+rax+00h]
0x1800388d4  lea     r8, [r14+10h]; struct Ptls6::tagLSPOINTUV *
0x1800388d8  mov     qword ptr [rbp+var_30.x], 0
0x1800388e0  xor     r9d, r9d; bool
0x1800388e3  mov     byte ptr [rsp+80h+cy], 0; bool
0x1800388e8  lea     rdx, [rbp+var_30]; struct tagPOINT *
0x1800388ec  mov     rcx, r13; this
0x1800388ef  call    ?PointFromPointuv@CDisplay@@QEBAXAEAUtagPOINT@@AEBUtagLSPOINTUV@Ptls6@@_N2@Z; CDisplay::PointFromPointuv(tagPOINT &,Ptls6::tagLSPOINTUV const &,bool,bool)
0x1800388f4  mov     ecx, [rbp+pt.y]
0x1800388f7  mov     r13d, 1
0x1800388fd  mov     r8d, [rbp+var_30.y]
0x180038901  mov     eax, ecx
0x180038903  mov     r9d, [rbp+pt.x]; cx
0x180038907  mov     edx, [rbp+var_30.x]
0x18003890a  sar     eax, 1
0x18003890c  sub     r8d, eax
0x18003890f  mov     [rsp+80h+rop], 990066h; rop
0x180038917  mov     eax, r9d
0x18003891a  add     r8d, r13d; y
0x18003891d  sar     eax, 1
0x18003891f  sub     edx, eax
0x180038921  mov     eax, [rbp+arg_8.y]
0x180038924  mov     [rsp+80h+y1], eax; y1
0x180038928  sub     edx, r13d; x
0x18003892b  mov     eax, [rbp+arg_8.x]
0x18003892e  mov     [rsp+80h+x1], eax; x1
0x180038932  mov     [rsp+80h+hdcSrc], r15; hdcSrc
0x180038937  mov     [rsp+80h+cy], ecx; cy
0x18003893b  mov     rcx, rsi; hdc
0x18003893e  call    cs:__imp_BitBlt
0x180038945  nop     dword ptr [rax+rax+00h]
0x18003894a  movzx   eax, word ptr [r14]
0x18003894e  movzx   ecx, di
0x180038951  mov     edx, 0FFFEh
0x180038956  xor     cx, r13w
0x18003895a  and     ax, dx
0x18003895d  or      cx, ax
0x180038960  mov     [r14], cx
0x180038964  mov     rcx, r15; hdc
0x180038967  call    cs:__imp_DeleteDC
0x18003896e  nop     dword ptr [rax+rax+00h]
0x180038973  test    r12, r12
0x180038976  jnz     loc_1800387E6
0x18003897c  cmp     [rbx+21h], r12b
0x180038980  jz      short loc_18003898D
0x180038982  mov     rcx, [rbx]; this
0x180038985  mov     rdx, rsi; HDC
0x180038988  call    ?TxReleaseDC@CTxtEdit@@QEAAHPEAUHDC__@@@Z; CTxtEdit::TxReleaseDC(HDC__ *)
0x18003898d  mov     byte ptr [rbx+21h], 0
0x180038991  jmp     loc_1800387E6
```
