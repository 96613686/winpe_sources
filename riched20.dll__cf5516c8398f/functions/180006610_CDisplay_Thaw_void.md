# CDisplay::Thaw(void)

- ea: `0x180006610`
- end: `0x180006922`
- name: `?Thaw@CDisplay@@QEAAXXZ`
- size: `786`
- prototype: `void __fastcall(CDisplay *__hidden this)`
- caller_count: `23`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180005480`
- `0x180018390`
- `0x18001bc20`
- `0x18001cc3c`
- `0x18001d24c`
- `0x180026e40`
- `0x18002cfd0`
- `0x1800323d8`
- `0x180043190`
- `0x180043514`
- `0x180049814`
- `0x18004b528`
- `0x18005d98c`
- `0x18005e8f8`
- `0x18006cc4c`
- `0x18006fb98`
- `0x1800717b0`
- `0x1800809e0`
- `0x180083fc0`
- `0x1800843d0`
- `0x180084480`
- `0x180089840`
- `0x18008a800`

## callees

- `0x180006610`
- `0x18000c070`
- `0x18000e0b8`
- `0x180023010`
- `0x180031a38`
- `0x180048e54`
- `0x180092010`

## pseudocode

```c
void __fastcall CDisplay::Thaw(CDisplay *this)
{
  _DWORD *v1; // rax
  bool v3; // zf
  _DWORD *v4; // rcx
  unsigned int v5; // r12d
  unsigned int v6; // r15d
  int v7; // esi
  int v8; // edi
  int v9; // r14d
  int v10; // r13d
  int v11; // esi
  void *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r9
  int v15; // edx
  int v16; // r8d
  int v17; // ecx
  int *v18; // r8
  int v19; // eax
  unsigned int v20; // r10d
  CTxtEdit *v21; // rcx
  CTxtSelection *Sel; // rax
  _QWORD v23[3]; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int64 v24; // [rsp+48h] [rbp-1h]
  int v25; // [rsp+50h] [rbp+7h]
  __int64 v26; // [rsp+58h] [rbp+Fh]
  __int64 v27; // [rsp+60h] [rbp+17h]
  __int64 v28; // [rsp+68h] [rbp+1Fh]
  __int64 v29; // [rsp+70h] [rbp+27h]
  __int64 v30; // [rsp+78h] [rbp+2Fh]

  v1 = (_DWORD *)*((_QWORD *)this + 6);
  if ( v1 )
  {
    v3 = (*v1)-- == 1;
    if ( v3 )
    {
      v4 = (_DWORD *)*((_QWORD *)this + 6);
      v5 = 0;
      v6 = 0;
      if ( v4 )
      {
        v7 = v4[4];
        v8 = v4[1];
        v9 = v7 << 31 >> 31;
        v10 = v7 << 30 >> 31;
        v11 = v7 << 29 >> 31;
        if ( v8 != 0x3FFFFFFF )
        {
          v6 = v4[2] - v8;
          v5 = v6 + v4[3];
          v4[1] = 0x3FFFFFFF;
        }
      }
      else
      {
        v9 = 0;
        v11 = 0;
        v8 = 0x3FFFFFFF;
        v10 = 0;
      }
      v12 = (void *)*((_QWORD *)this + 6);
      if ( v12 )
        CW32System::FreePv(v12);
      *((_QWORD *)this + 6) = 0;
      if ( v8 == 0x3FFFFFFF )
        goto LABEL_26;
      v13 = *((_QWORD *)this + 2);
      if ( (*(_BYTE *)(v13 + 180) & 8) == 0 )
      {
        *((_DWORD *)this + 14) |= 0x80u;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v13 + 48) + 72LL))(*(_QWORD *)(v13 + 48), 0, 0);
        CTxtEdit::TxUpdateWindow(*((CTxtEdit **)this + 2));
        return;
      }
      v26 = *((_QWORD *)this + 2);
      v3 = v13 == -248;
      v14 = v13 + 248;
      v23[0] = &CRchTxtPtr::`vftable';
      v23[2] = v14;
      v24 = 0;
      v25 = 0;
      if ( !v3 && *(_DWORD *)(v14 + 8) )
      {
        v15 = 0;
        v24 = 0;
        if ( v8 )
        {
          v16 = *(_DWORD *)(v14 + 8);
          if ( v16 )
          {
            v17 = v8;
            if ( v8 < 0 )
            {
              v17 = v8;
              v24 = 0;
            }
            else
            {
              if ( v16 <= 0 || (v18 = *(int **)v14) == 0 )
                v18 = 0;
              while ( v17 > 0 )
              {
                v19 = *v18;
                HIDWORD(v24) = v17;
                if ( v17 < v19 )
                {
                  v17 = 0;
                  break;
                }
                v20 = v15;
                v17 -= v19;
                LODWORD(v24) = ++v15;
                if ( v15 >= *(_DWORD *)(v14 + 8) )
                {
                  v24 = __PAIR64__(v19, v20);
                  break;
                }
                HIDWORD(v24) = 0;
                v18 = (int *)((char *)v18 + *(int *)(v14 + 16));
              }
            }
            v8 -= v17;
          }
        }
        v25 = v8;
      }
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      CRchTxtPtr::InitRunPtrs((CRchTxtPtr *)v23);
      if ( (*(unsigned int (__fastcall **)(CDisplay *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)this + 248LL))(
             this,
             v23,
             v6,
             v5) )
      {
LABEL_26:
        if ( v11 )
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 72LL))(
            *(_QWORD *)(*((_QWORD *)this + 2) + 48LL),
            0,
            0);
        if ( v9 )
        {
          v21 = (CTxtEdit *)*((_QWORD *)this + 2);
          if ( (*((_BYTE *)v21 + 180) & 8) != 0 )
          {
            Sel = CTxtEdit::GetSel(v21);
            if ( Sel )
              CTxtSelection::UpdateCaret(Sel, v10, 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180006610  push    rbp
0x180006612  push    rbx
0x180006613  lea     rbp, [rsp-4Fh]
0x180006618  sub     rsp, 98h
0x18000661f  mov     rax, [rcx+30h]
0x180006623  mov     rbx, rcx
0x180006626  test    rax, rax
0x180006629  jz      short loc_180006630
0x18000662b  sub     dword ptr [rax], 1
0x18000662e  jz      short loc_18000663A
0x180006630  add     rsp, 98h
0x180006637  pop     rbx
0x180006638  pop     rbp
0x180006639  retn
0x18000663a  mov     rcx, [rcx+30h]
0x18000663e  xor     r11d, r11d
0x180006641  mov     [rsp+0A0h+arg_10], rdi
0x180006649  mov     [rsp+0A0h+arg_18], r12
0x180006651  mov     r12d, r11d
0x180006654  mov     [rsp+0A0h+var_20], r15
0x18000665c  mov     r15d, r11d
0x18000665f  mov     [rsp+0A0h+arg_8], rsi
0x180006667  mov     [rsp+0A0h+var_10], r13
0x18000666f  mov     [rsp+0A0h+var_18], r14
0x180006677  test    rcx, rcx
0x18000667a  jz      loc_1800068AD
0x180006680  mov     esi, [rcx+10h]
0x180006683  mov     r14d, esi
0x180006686  mov     edi, [rcx+4]
0x180006689  mov     r13d, esi
0x18000668c  shl     r14d, 1Fh
0x180006690  shl     r13d, 1Eh
0x180006694  shl     esi, 1Dh
0x180006697  sar     r14d, 1Fh
0x18000669b  sar     r13d, 1Fh
0x18000669f  sar     esi, 1Fh
0x1800066a2  cmp     edi, 3FFFFFFFh
0x1800066a8  jnz     loc_180006829
0x1800066ae  mov     rcx, [rbx+30h]; lpMem
0x1800066b2  test    rcx, rcx
0x1800066b5  jnz     loc_180006843
0x1800066bb  mov     [rbx+30h], r11
0x1800066bf  cmp     edi, 3FFFFFFFh
0x1800066c5  jz      loc_1800067C0
0x1800066cb  mov     r9, [rbx+10h]
0x1800066cf  test    byte ptr [r9+0B4h], 8
0x1800066d7  jz      loc_1800068CD
0x1800066dd  mov     [rbp+57h+var_48], r9
0x1800066e1  lea     rax, ??_7CRchTxtPtr@@6B@; const CRchTxtPtr::`vftable'
0x1800066e8  add     r9, 0F8h
0x1800066ef  mov     [rbp+57h+var_70], rax
0x1800066f3  mov     [rbp+57h+var_60], r9
0x1800066f7  mov     [rbp+57h+var_58], 0
0x1800066ff  mov     [rbp+57h+var_50], r11d
0x180006703  jz      short loc_18000677F
0x180006705  cmp     dword ptr [r9+8], 0
0x18000670a  jz      short loc_18000677F
0x18000670c  mov     edx, r11d
0x18000670f  mov     eax, r11d
0x180006712  mov     dword ptr [rbp+57h+var_58], edx
0x180006715  mov     dword ptr [rbp+57h+var_58+4], eax
0x180006718  test    edi, edi
0x18000671a  jz      short loc_18000677C
0x18000671c  mov     r8d, [r9+8]
0x180006720  test    r8d, r8d
0x180006723  jz      short loc_18000677C
0x180006725  mov     ecx, edi
0x180006727  test    edi, edi
0x180006729  js      loc_180006860
0x18000672f  test    r8d, r8d
0x180006732  jle     loc_1800068C5
0x180006738  mov     r8, [r9]
0x18000673b  test    r8, r8
0x18000673e  jz      loc_1800068C5
0x180006744  test    ecx, ecx
0x180006746  jle     short loc_18000677A
0x180006748  mov     eax, [r8]
0x18000674b  mov     dword ptr [rbp+57h+var_58+4], ecx
0x18000674e  cmp     ecx, eax
0x180006750  jl      short loc_180006777
0x180006752  mov     r10d, edx
0x180006755  sub     ecx, eax
0x180006757  inc     edx
0x180006759  mov     dword ptr [rbp+57h+var_58], edx
0x18000675c  cmp     edx, [r9+8]
0x180006760  jge     loc_180006850
0x180006766  mov     dword ptr [rbp+57h+var_58+4], r11d
0x18000676a  movsxd  rax, dword ptr [r9+10h]
0x18000676e  add     r8, rax
0x180006771  jmp     short loc_180006744
0x180006773  mov     dword ptr [rbp+57h+var_58+4], r8d
0x180006777  mov     ecx, r11d
0x18000677a  sub     edi, ecx
0x18000677c  mov     [rbp+57h+var_50], edi
0x18000677f  lea     rcx, [rbp+57h+var_70]; this
0x180006783  mov     [rbp+57h+var_40], r11
0x180006787  mov     [rbp+57h+var_38], 0
0x18000678f  mov     [rbp+57h+var_30], r11
0x180006793  mov     [rbp+57h+var_28], 0
0x18000679b  call    ?InitRunPtrs@CRchTxtPtr@@IEAAXXZ; CRchTxtPtr::InitRunPtrs(void)
0x1800067a0  mov     rax, [rbx]
0x1800067a3  lea     rdx, [rbp+57h+var_70]
0x1800067a7  mov     r9d, r12d
0x1800067aa  mov     r8d, r15d
0x1800067ad  mov     rcx, rbx
0x1800067b0  mov     rax, [rax+0F8h]
0x1800067b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067bc  test    eax, eax
0x1800067be  jz      short loc_1800067DA
0x1800067c0  test    esi, esi
0x1800067c2  jnz     loc_180006904
0x1800067c8  test    r14d, r14d
0x1800067cb  jz      short loc_1800067DA
0x1800067cd  mov     rcx, [rbx+10h]; this
0x1800067d1  test    byte ptr [rcx+0B4h], 8
0x1800067d8  jnz     short loc_18000680F
0x1800067da  mov     r14, [rsp+0A0h+var_18]
0x1800067e2  mov     r13, [rsp+0A0h+var_10]
0x1800067ea  mov     rsi, [rsp+0A0h+arg_8]
0x1800067f2  mov     rdi, [rsp+0A0h+arg_10]
0x1800067fa  mov     r12, [rsp+0A0h+arg_18]
0x180006802  mov     r15, [rsp+0A0h+var_20]
0x18000680a  jmp     loc_180006630
0x18000680f  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x180006814  test    rax, rax
0x180006817  jz      short loc_1800067DA
0x180006819  xor     r8d, r8d; int
0x18000681c  mov     edx, r13d; int
0x18000681f  mov     rcx, rax; this
0x180006822  call    ?UpdateCaret@CTxtSelection@@QEAAHHH@Z; CTxtSelection::UpdateCaret(int,int)
0x180006827  jmp     short loc_1800067DA
0x180006829  mov     r15d, [rcx+8]
0x18000682d  mov     r12d, [rcx+0Ch]
0x180006831  sub     r15d, edi
0x180006834  add     r12d, r15d
0x180006837  mov     dword ptr [rcx+4], 3FFFFFFFh
0x18000683e  jmp     loc_1800066AE
0x180006843  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180006848  xor     r11d, r11d
0x18000684b  jmp     loc_1800066BB
0x180006850  mov     dword ptr [rbp+57h+var_58], r10d
0x180006854  mov     dword ptr [rbp+57h+var_58+4], eax
0x180006857  jmp     loc_18000677A
0x180006860  test    ecx, ecx
0x180006862  jns     loc_18000677A
0x180006868  lea     r8d, [rax+rcx]
0x18000686c  neg     ecx
0x18000686e  cmp     ecx, eax
0x180006870  jle     loc_180006773
0x180006876  mov     ecx, r8d
0x180006879  test    edx, edx
0x18000687b  jle     short loc_1800068F7
0x18000687d  dec     edx
0x18000687f  mov     dword ptr [rbp+57h+var_58], edx
0x180006882  mov     eax, [r9+8]
0x180006886  test    eax, eax
0x180006888  jle     short loc_1800068C0
0x18000688a  cmp     edx, eax
0x18000688c  jge     short loc_1800068C0
0x18000688e  mov     r8, [r9]
0x180006891  test    r8, r8
0x180006894  jz      short loc_1800068C0
0x180006896  test    edx, edx
0x180006898  js      short loc_1800068C0
0x18000689a  mov     eax, edx
0x18000689c  imul    eax, [r9+10h]
0x1800068a1  cdqe
0x1800068a3  add     rax, r8
0x1800068a6  mov     eax, [rax]
0x1800068a8  mov     dword ptr [rbp+57h+var_58+4], eax
0x1800068ab  jmp     short loc_180006860
0x1800068ad  mov     r14d, r11d
0x1800068b0  mov     esi, r11d
0x1800068b3  mov     edi, 3FFFFFFFh
0x1800068b8  mov     r13d, r11d
0x1800068bb  jmp     loc_1800066AE
0x1800068c0  mov     rax, r11
0x1800068c3  jmp     short loc_1800068A6
0x1800068c5  mov     r8, r11
0x1800068c8  jmp     loc_180006744
0x1800068cd  or      dword ptr [rbx+38h], 80h
0x1800068d4  xor     r8d, r8d
0x1800068d7  mov     rcx, [r9+30h]
0x1800068db  xor     edx, edx
0x1800068dd  mov     rax, [rcx]
0x1800068e0  mov     rax, [rax+48h]
0x1800068e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e9  mov     rcx, [rbx+10h]; this
0x1800068ed  call    ?TxUpdateWindow@CTxtEdit@@QEAAXXZ; CTxtEdit::TxUpdateWindow(void)
0x1800068f2  jmp     loc_1800067DA
0x1800068f7  mov     [rbp+57h+var_58], 0
0x1800068ff  jmp     loc_18000677A
0x180006904  mov     rax, [rbx+10h]
0x180006908  xor     r8d, r8d
0x18000690b  xor     edx, edx
0x18000690d  mov     rcx, [rax+30h]
0x180006911  mov     rax, [rcx]
0x180006914  mov     rax, [rax+48h]
0x180006918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000691d  jmp     loc_1800067C8
```
