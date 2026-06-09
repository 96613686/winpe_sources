# CMagellan::TrackUpdateMagellanMButtonDown(CTxtEdit &,tagPOINT)

- ea: `0x18013ad4c`
- end: `0x18013b17b`
- name: `?TrackUpdateMagellanMButtonDown@CMagellan@@QEAAXAEAVCTxtEdit@@UtagPOINT@@@Z`
- size: `1071`
- prototype: `void __fastcall(CMagellan *__hidden this, struct CTxtEdit *, struct tagPOINT)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1800e55cc`

## callees

- `0x18000f430`
- `0x1800387b0`
- `0x18004868c`
- `0x18004adc0`
- `0x18004aecc`
- `0x1800c1b90`
- `0x18012c7a0`
- `0x18013ad4c`
- `0x18013b184`
- `0x180162a6c`
- `0x180162e90`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x18013af53`
- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x18013af53`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18013af24`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18013af24`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18013b133`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18013b133`

## pseudocode

```c
void __fastcall CMagellan::TrackUpdateMagellanMButtonDown(CMagellan *this, struct CTxtEdit *a2, struct tagPOINT a3)
{
  int *v3; // rdi
  unsigned __int16 v6; // si
  int v7; // r12d
  int v8; // edx
  unsigned __int16 v9; // r15
  int IsUScrollEnabled; // eax
  int v11; // ebx
  int v12; // r12d
  __int16 v13; // ax
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rsi
  const WCHAR *v17; // rdx
  HINSTANCE v18; // rcx
  void ***v19; // r15
  int v20; // edx
  int v21; // esi
  int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // r11d
  int v26; // r14d
  __int64 v27; // r9
  __int64 v28; // r8
  void ***v29; // rcx
  bool v30; // zf
  void ***v31; // rcx
  void (__fastcall *v32)(void ***, HCURSOR, _QWORD); // rbx
  HCURSOR CursorW; // rax
  int v34; // [rsp+30h] [rbp-39h]
  int v35; // [rsp+30h] [rbp-39h]
  int v36; // [rsp+34h] [rbp-35h]
  __int64 v37; // [rsp+38h] [rbp-31h] BYREF
  __int64 v38; // [rsp+40h] [rbp-29h]
  __int128 v39; // [rsp+48h] [rbp-21h] BYREF
  _OWORD v40[6]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 v41; // [rsp+D8h] [rbp+6Fh]
  struct tagPOINT v42; // [rsp+E0h] [rbp+77h] BYREF
  int v43; // [rsp+E8h] [rbp+7Fh]

  v42 = a3;
  v3 = (int *)*((_QWORD *)a2 + 17);
  v37 = 0;
  if ( v3 )
  {
    v43 = 0;
    v6 = 0;
    CDisplay::PointuvFromPoint((CDisplay *)v3, (struct Ptls6::tagLSPOINTUV *)&v37, &v42);
    v34 = *((_DWORD *)this + 4);
    v7 = CW32System::MulDivFunc(60, v3[14], 1440);
    if ( (v3[29] & 0x400) != 0 )
    {
      v8 = *((_DWORD *)this + 5);
      v9 = 1;
      if ( SHIDWORD(v37) < v8 - v7 || SHIDWORD(v37) > v8 + v7 )
      {
        v43 = 1;
        if ( SHIDWORD(v37) >= v8 )
          v6 = 2;
        else
          v6 = 1;
      }
    }
    else
    {
      v9 = 0;
    }
    IsUScrollEnabled = CDisplay::IsUScrollEnabled((CDisplay *)v3);
    v11 = v37;
    if ( IsUScrollEnabled
      && (CTxtEdit::TxGetScrollBars(a2) & 0x100000) != 0
      && ((v9 |= 2u, v11 < v34 - v7) || v11 > v7 + v34) )
    {
      v12 = 1;
      v13 = 6;
      if ( v11 >= *((_DWORD *)this + 4) )
        v13 = 3;
      v6 += v13;
    }
    else
    {
      v12 = 0;
    }
    v14 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)v3 + 176LL))(v3);
    switch ( v14 )
    {
      case 1:
        v6 = *((unsigned __int8 *)&qword_1802C4220[2] + v6);
        break;
      case 2:
        v6 = *((unsigned __int8 *)qword_1802C4220 + v6);
        break;
      case 3:
        v6 = *((unsigned __int8 *)qword_1802C4200 + v6);
        break;
    }
    if ( ((*(__int64 (__fastcall **)(int *, struct HINSTANCE__ *))(*(_QWORD *)v3 + 176LL))(v3, &_ImageBase) & 1) != 0 )
    {
      if ( v9 == 2 )
      {
        v9 = 1;
      }
      else if ( v9 == 1 )
      {
        v9 = 2;
      }
    }
    v15 = v6;
    v16 = v9;
    v41 = word_1802C4240[v15];
    if ( word_1802C4218[v9] != *((_WORD *)this + 1) )
    {
      if ( *((_QWORD *)this + 1) )
      {
        CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 0, 0);
        DeleteObject(*((HGDIOBJ *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
      v17 = (const WCHAR *)(unsigned __int16)word_1802C4218[v9];
      v18 = hinstRE;
      *((_WORD *)this + 1) = (_WORD)v17;
      *((_QWORD *)this + 1) = LoadBitmapW(v18, v17);
      CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 1, 0);
    }
    v19 = &CITextHost2Ref::s_dummyHost;
    if ( v43 || v12 )
    {
      v39 = 0;
      CTxtEdit::TxGetClientRect(a2, (struct RECTUV *)&v39, 0);
      v20 = HIDWORD(v37) - *((_DWORD *)this + 5);
      v21 = HIDWORD(v39) - DWORD1(v39);
      v22 = v11 - *((_DWORD *)this + 4);
      v35 = (DWORD2(v39) - (int)v39) >> 1;
      LODWORD(v38) = v39 + v22 + v35;
      v36 = v20;
      v23 = CW32System::MulDivFunc(250 * v20, v20, 4 * (HIDWORD(v39) - DWORD1(v39)));
      v26 = v43;
      v27 = v23;
      if ( !v23 )
        v27 = 1;
      if ( v43 )
        CDisplay::SmoothVScroll((CDisplay *)v3, v25 - HIDWORD(v37), 0, v27, 10 * v21, 0);
      if ( v12 )
      {
        v28 = (unsigned int)(v35 - 2);
        HIDWORD(v38) = DWORD1(v39) + (v21 >> 1);
        if ( (unsigned int)v28 > 0xFFFF )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v24, 0);
        CDisplay::AutoScroll(v3, v38, v28, 0);
      }
      if ( (*((_BYTE *)a2 + 272) & 8) != 0 && (v12 || v26) )
      {
        memset(v40, 0, 44);
        if ( v12 )
        {
          DWORD2(v40[1]) = 276;
          v29 = &CITextHost2Ref::s_dummyHost;
          v30 = *((_QWORD *)a2 + 14) == 0;
          *(_QWORD *)((char *)&v40[1] + 12) = v22 > 0;
          if ( !v30 )
            v29 = (void ***)*((_QWORD *)a2 + 14);
          ((void (__fastcall *)(void ***, __int64, _OWORD *, __int64))(*v29)[38])(v29, 1792, v40, v27);
        }
        if ( v26 )
        {
          DWORD2(v40[1]) = 277;
          v31 = &CITextHost2Ref::s_dummyHost;
          v30 = *((_QWORD *)a2 + 14) == 0;
          *(_QWORD *)((char *)&v40[1] + 12) = v36 > 0;
          if ( !v30 )
            v31 = (void ***)*((_QWORD *)a2 + 14);
          ((void (__fastcall *)(void ***, __int64, _OWORD *, __int64))(*v31)[38])(v31, 1792, v40, v27);
        }
      }
    }
    else
    {
      v41 = word_1802C4210[v16];
      CDisplay::FinishSmoothVScroll((CDisplay *)v3);
    }
    if ( *((_QWORD *)a2 + 14) )
      v19 = (void ***)*((_QWORD *)a2 + 14);
    v32 = (void (__fastcall *)(void ***, HCURSOR, _QWORD))(*v19)[19];
    if ( v41 )
      CursorW = LoadCursorW(hinstRE, (LPCWSTR)v41);
    else
      CursorW = CTxtEdit::_hcurArrow;
    v32(v19, CursorW, 0);
  }
}

```

## disassembly

```asm
0x18013ad4c  mov     [rsp-8+arg_0], rbx
0x18013ad51  mov     qword ptr [rsp-8+arg_10.x], r8
0x18013ad56  push    rbp
0x18013ad57  push    rsi
0x18013ad58  push    rdi
0x18013ad59  push    r12
0x18013ad5b  push    r13
0x18013ad5d  push    r14
0x18013ad5f  push    r15
0x18013ad61  lea     rbp, [rsp-27h]
0x18013ad66  sub     rsp, 90h
0x18013ad6d  mov     rdi, [rdx+88h]
0x18013ad74  xor     ebx, ebx
0x18013ad76  mov     [rbp+57h+var_88], rbx
0x18013ad7a  mov     r13, rdx
0x18013ad7d  mov     r14, rcx
0x18013ad80  test    rdi, rdi
0x18013ad83  jz      loc_18013B15F
0x18013ad89  lea     r8, [rbp+57h+arg_10]; struct tagPOINT *
0x18013ad8d  mov     [rbp+57h+arg_8], ebx
0x18013ad90  lea     rdx, [rbp+57h+var_88]; struct Ptls6::tagLSPOINTUV *
0x18013ad94  mov     [rbp+57h+arg_18], ebx
0x18013ad97  mov     rcx, rdi; this
0x18013ad9a  mov     esi, ebx
0x18013ad9c  call    ?PointuvFromPoint@CDisplay@@QEBAXAEAUtagLSPOINTUV@Ptls6@@AEBUtagPOINT@@@Z; CDisplay::PointuvFromPoint(Ptls6::tagLSPOINTUV &,tagPOINT const &)
0x18013ada1  mov     eax, [r14+10h]
0x18013ada5  lea     ecx, [rbx+3Ch]; int
0x18013ada8  mov     edx, [rdi+38h]; int
0x18013adab  mov     r8d, 5A0h; int
0x18013adb1  mov     [rbp+57h+var_90], eax
0x18013adb4  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18013adb9  test    dword ptr [rdi+74h], 400h
0x18013adc0  lea     r9d, [rbx+1]
0x18013adc4  mov     r8d, dword ptr [rbp+57h+var_88+4]
0x18013adc8  mov     r12d, eax
0x18013adcb  lea     eax, [rbx+2]
0x18013adce  jz      short loc_18013AE02
0x18013add0  mov     edx, [r14+14h]
0x18013add4  movzx   r15d, r9w
0x18013add8  mov     ecx, edx
0x18013adda  sub     ecx, r12d
0x18013addd  cmp     r8d, ecx
0x18013ade0  jl      short loc_18013ADEE
0x18013ade2  lea     eax, [rdx+r12]
0x18013ade6  cmp     r8d, eax
0x18013ade9  jle     short loc_18013AE05
0x18013adeb  lea     eax, [rbx+2]
0x18013adee  mov     [rbp+57h+arg_18], r9d
0x18013adf2  cmp     r8d, edx
0x18013adf5  jge     short loc_18013ADFD
0x18013adf7  movzx   esi, r9w
0x18013adfb  jmp     short loc_18013AE05
0x18013adfd  movzx   esi, ax
0x18013ae00  jmp     short loc_18013AE05
0x18013ae02  mov     r15d, ebx
0x18013ae05  mov     rcx, rdi; this
0x18013ae08  call    ?IsUScrollEnabled@CDisplay@@QEAAHXZ; CDisplay::IsUScrollEnabled(void)
0x18013ae0d  mov     rbx, [rbp+57h+var_88]
0x18013ae11  test    eax, eax
0x18013ae13  jz      short loc_18013AE57
0x18013ae15  mov     rcx, r13; this
0x18013ae18  call    ?TxGetScrollBars@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetScrollBars(void)
0x18013ae1d  bt      eax, 14h
0x18013ae21  jnb     short loc_18013AE57
0x18013ae23  mov     ecx, [rbp+57h+var_90]
0x18013ae26  or      r15w, 2
0x18013ae2b  mov     eax, ecx
0x18013ae2d  sub     eax, r12d
0x18013ae30  cmp     ebx, eax
0x18013ae32  jl      short loc_18013AE3C
0x18013ae34  lea     eax, [r12+rcx]
0x18013ae38  cmp     ebx, eax
0x18013ae3a  jle     short loc_18013AE57
0x18013ae3c  mov     r12d, 1
0x18013ae42  lea     eax, [r12+5]
0x18013ae47  cmp     ebx, [r14+10h]
0x18013ae4b  jl      short loc_18013AE52
0x18013ae4d  lea     eax, [r12+2]
0x18013ae52  add     si, ax
0x18013ae55  jmp     short loc_18013AE5B
0x18013ae57  mov     r12d, [rbp+57h+arg_8]
0x18013ae5b  mov     rax, [rdi]
0x18013ae5e  mov     rcx, rdi
0x18013ae61  mov     rax, [rax+0B0h]
0x18013ae68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ae6d  movzx   ecx, al
0x18013ae70  lea     rdx, __ImageBase
0x18013ae77  sub     ecx, 1
0x18013ae7a  jz      short loc_18013AEA0
0x18013ae7c  sub     ecx, 1
0x18013ae7f  jz      short loc_18013AE93
0x18013ae81  cmp     ecx, 1
0x18013ae84  jnz     short loc_18013AEAB
0x18013ae86  movzx   eax, si
0x18013ae89  movzx   esi, byte ptr [rax+rdx+2C4200h]
0x18013ae91  jmp     short loc_18013AEAB
0x18013ae93  movzx   eax, si
0x18013ae96  movzx   esi, byte ptr [rax+rdx+2C4220h]
0x18013ae9e  jmp     short loc_18013AEAB
0x18013aea0  movzx   eax, si
0x18013aea3  movzx   esi, byte ptr [rax+rdx+2C4230h]
0x18013aeab  mov     rax, [rdi]
0x18013aeae  mov     rcx, rdi
0x18013aeb1  mov     rax, [rax+0B0h]
0x18013aeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013aebd  mov     ecx, 1
0x18013aec2  test    cl, al
0x18013aec4  jz      short loc_18013AEDF
0x18013aec6  lea     eax, [rcx+1]
0x18013aec9  cmp     r15w, ax
0x18013aecd  jnz     short loc_18013AED5
0x18013aecf  movzx   r15d, cx
0x18013aed3  jmp     short loc_18013AEDF
0x18013aed5  cmp     r15w, cx
0x18013aed9  jnz     short loc_18013AEDF
0x18013aedb  movzx   r15d, ax
0x18013aedf  movzx   eax, si
0x18013aee2  lea     rdx, __ImageBase
0x18013aee9  movzx   esi, r15w
0x18013aeed  movzx   ecx, ds:rva word_1802C4240[rdx+rax*2]
0x18013aef5  movzx   eax, word ptr [r14+2]
0x18013aefa  mov     word ptr [rbp+57h+arg_8], cx
0x18013aefe  cmp     ds:rva word_1802C4218[rdx+rsi*2], ax
0x18013af06  jz      short loc_18013AF7C
0x18013af08  cmp     qword ptr [r14+8], 0
0x18013af0d  jz      short loc_18013AF3F
0x18013af0f  xor     r9d, r9d; HDC
0x18013af12  xor     r8d, r8d; int
0x18013af15  mov     rdx, rdi; struct CDisplay *
0x18013af18  mov     rcx, r14; this
0x18013af1b  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x18013af20  mov     rcx, [r14+8]; ho
0x18013af24  call    cs:__imp_DeleteObject
0x18013af2b  nop     dword ptr [rax+rax+00h]
0x18013af30  lea     rdx, __ImageBase
0x18013af37  mov     qword ptr [r14+8], 0
0x18013af3f  movzx   edx, ds:rva word_1802C4218[rdx+rsi*2]; lpBitmapName
0x18013af47  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x18013af4e  mov     [r14+2], dx
0x18013af53  call    cs:__imp_LoadBitmapW
0x18013af5a  nop     dword ptr [rax+rax+00h]
0x18013af5f  xor     r9d, r9d; HDC
0x18013af62  mov     rdx, rdi; struct CDisplay *
0x18013af65  mov     rcx, r14; this
0x18013af68  mov     [r14+8], rax
0x18013af6c  lea     r8d, [r9+1]; int
0x18013af70  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x18013af75  lea     rdx, __ImageBase
0x18013af7c  xor     eax, eax
0x18013af7e  lea     r15, ?s_dummyHost@CITextHost2Ref@@0VCDummyHost@@A; CDummyHost CITextHost2Ref::s_dummyHost
0x18013af85  cmp     [rbp+57h+arg_18], eax
0x18013af88  jnz     short loc_18013AFA8
0x18013af8a  test    r12d, r12d
0x18013af8d  jnz     short loc_18013AFA8
0x18013af8f  movzx   ecx, ds:rva word_1802C4210[rdx+rsi*2]
0x18013af97  mov     word ptr [rbp+57h+arg_8], cx
0x18013af9b  mov     rcx, rdi; this
0x18013af9e  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x18013afa3  jmp     loc_18013B10C
0x18013afa8  xorps   xmm0, xmm0
0x18013afab  lea     rdx, [rbp+57h+var_78]; struct RECTUV *
0x18013afaf  xor     r8d, r8d; struct RECTUV *
0x18013afb2  mov     rcx, r13; this
0x18013afb5  movdqu  [rbp+57h+var_78], xmm0
0x18013afba  call    ?TxGetClientRect@CTxtEdit@@QEBAXAEAURECTUV@@PEAU2@@Z; CTxtEdit::TxGetClientRect(RECTUV &,RECTUV *)
0x18013afbf  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18013afc2  sub     eax, dword ptr [rbp+57h+var_78]
0x18013afc5  mov     edx, dword ptr [rbp+57h+var_88+4]
0x18013afc8  mov     esi, dword ptr [rbp+57h+var_78+0Ch]
0x18013afcb  mov     r11d, [r14+14h]
0x18013afcf  sub     edx, r11d; int
0x18013afd2  sub     esi, dword ptr [rbp+57h+var_78+4]
0x18013afd5  sub     ebx, [r14+10h]
0x18013afd9  sar     eax, 1
0x18013afdb  mov     [rbp+57h+var_90], eax
0x18013afde  add     eax, ebx
0x18013afe0  add     eax, dword ptr [rbp+57h+var_78]
0x18013afe3  lea     r8d, ds:0[rsi*4]; int
0x18013afeb  imul    ecx, edx, 0FAh; int
0x18013aff1  mov     dword ptr [rbp+57h+var_80], eax
0x18013aff4  mov     [rbp+57h+var_8C], edx
0x18013aff7  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18013affc  mov     r14d, [rbp+57h+arg_18]
0x18013b000  xor     edx, edx
0x18013b002  test    eax, eax
0x18013b004  mov     r9d, eax
0x18013b007  lea     eax, [rdx+1]
0x18013b00a  cmovz   r9d, eax; int
0x18013b00e  test    r14d, r14d
0x18013b011  jz      short loc_18013B034
0x18013b013  sub     r11d, dword ptr [rbp+57h+var_88+4]
0x18013b017  lea     eax, [rsi+rsi*4]
0x18013b01a  mov     [rsp+0C0h+var_98], edx; int
0x18013b01e  add     eax, eax
0x18013b020  xor     r8d, r8d; unsigned __int16
0x18013b023  mov     [rsp+0C0h+var_A0], eax; int
0x18013b027  mov     edx, r11d; int
0x18013b02a  mov     rcx, rdi; this
0x18013b02d  call    ?SmoothVScroll@CDisplay@@QEAAXHGHHH@Z; CDisplay::SmoothVScroll(int,ushort,int,int,int)
0x18013b032  xor     edx, edx
0x18013b034  test    r12d, r12d
0x18013b037  jz      short loc_18013B067
0x18013b039  mov     r8d, [rbp+57h+var_90]
0x18013b03d  sar     esi, 1
0x18013b03f  add     r8d, 0FFFFFFFEh
0x18013b043  add     esi, dword ptr [rbp+57h+var_78+4]
0x18013b046  mov     dword ptr [rbp+57h+var_80+4], esi
0x18013b049  cmp     r8d, 0FFFFh
0x18013b050  ja      loc_18013B141
0x18013b056  mov     rdx, [rbp+57h+var_80]
0x18013b05a  xor     r9d, r9d
0x18013b05d  mov     rcx, rdi
0x18013b060  call    ?AutoScroll@CDisplay@@QEAAHUtagLSPOINTUV@Ptls6@@GG@Z; CDisplay::AutoScroll(Ptls6::tagLSPOINTUV,ushort,ushort)
0x18013b065  xor     edx, edx
0x18013b067  test    byte ptr [r13+110h], 8
0x18013b06f  jz      loc_18013B10C
0x18013b075  test    r12d, r12d
0x18013b078  jnz     short loc_18013B083
0x18013b07a  test    r14d, r14d
0x18013b07d  jz      loc_18013B10C
0x18013b083  xorps   xmm0, xmm0
0x18013b086  mov     edi, 700h
0x18013b08b  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18013b08f  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x18013b093  movups  [rbp+57h+var_68], xmm0
0x18013b097  test    r12d, r12d
0x18013b09a  jz      short loc_18013B0D2
0x18013b09c  mov     rax, rdx
0x18013b09f  mov     dword ptr [rbp+57h+var_58+8], 114h
0x18013b0a6  test    ebx, ebx
0x18013b0a8  lea     r8, [rbp+57h+var_68]
0x18013b0ac  mov     rcx, r15
0x18013b0af  setnle  al
0x18013b0b2  cmp     [r13+70h], rdx
0x18013b0b6  mov     qword ptr [rbp+57h+var_58+0Ch], rax
0x18013b0ba  mov     edx, edi
0x18013b0bc  cmovnz  rcx, [r13+70h]
0x18013b0c1  mov     rax, [rcx]
0x18013b0c4  mov     rax, [rax+130h]
0x18013b0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b0d0  xor     edx, edx
0x18013b0d2  test    r14d, r14d
0x18013b0d5  jz      short loc_18013B10C
0x18013b0d7  cmp     [rbp+57h+var_8C], edx
0x18013b0da  lea     r8, [rbp+57h+var_68]
0x18013b0de  mov     rax, rdx
0x18013b0e1  mov     dword ptr [rbp+57h+var_58+8], 115h
0x18013b0e8  setnle  al
0x18013b0eb  mov     rcx, r15
0x18013b0ee  cmp     [r13+70h], rdx
0x18013b0f2  mov     edx, edi
0x18013b0f4  mov     qword ptr [rbp+57h+var_58+0Ch], rax
0x18013b0f8  cmovnz  rcx, [r13+70h]
0x18013b0fd  mov     rax, [rcx]
0x18013b100  mov     rax, [rax+130h]
0x18013b107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b10c  xor     ecx, ecx
0x18013b10e  cmp     [r13+70h], rcx
0x18013b112  cmovnz  r15, [r13+70h]
0x18013b117  mov     rax, [r15]
0x18013b11a  mov     rbx, [rax+98h]
0x18013b121  movzx   eax, word ptr [rbp+57h+arg_8]
0x18013b125  test    ax, ax
0x18013b128  jz      short loc_18013B147
0x18013b12a  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x18013b131  mov     edx, eax; lpCursorName
0x18013b133  call    cs:__imp_LoadCursorW
0x18013b13a  nop     dword ptr [rax+rax+00h]
0x18013b13f  jmp     short loc_18013B14E
0x18013b141  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18013b147  mov     rax, cs:?_hcurArrow@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurArrow
0x18013b14e  mov     rdx, rax
0x18013b151  xor     r8d, r8d
0x18013b154  mov     rax, rbx
0x18013b157  mov     rcx, r15
0x18013b15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b15f  mov     rbx, [rsp+0C0h+arg_0]
0x18013b167  add     rsp, 90h
0x18013b16e  pop     r15
0x18013b170  pop     r14
0x18013b172  pop     r13
0x18013b174  pop     r12
0x18013b176  pop     rdi
0x18013b177  pop     rsi
0x18013b178  pop     rbp
0x18013b179  retn
```
