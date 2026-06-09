# CDetectURL::ScanAndUpdate(IUndoBuilder *)

- ea: `0x180016b44`
- end: `0x180017036`
- name: `?ScanAndUpdate@CDetectURL@@QEAAXPEAVIUndoBuilder@@@Z`
- size: `1266`
- prototype: `void __fastcall(CDetectURL *__hidden this, struct IUndoBuilder *)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ebcc`
- `0x18002cfd0`
- `0x1800300b0`
- `0x180030280`

## callees

- `0x180005480`
- `0x180016b44`
- `0x180017040`
- `0x180017860`
- `0x180017ef0`
- `0x18001f408`
- `0x180020770`
- `0x1800319c0`
- `0x180031a38`
- `0x180037bd0`
- `0x1800396fc`
- `0x180039b0c`
- `0x180092010`

## pseudocode

```c
void __fastcall CDetectURL::ScanAndUpdate(CDetectURL *this, struct IUndoBuilder *a2)
{
  CTxtEdit *v3; // rcx
  struct IUndoBuilder *v4; // r14
  CTxtRange *Sel; // rax
  int v6; // r12d
  CDetectURL *v7; // rcx
  int v8; // edi
  int v9; // eax
  int v10; // r13d
  int v11; // esi
  CDetectURL *v12; // rcx
  int v13; // ebx
  CDetectURL *v14; // rcx
  int v15; // eax
  int v16; // r15d
  int v17; // ebx
  int v18; // r14d
  unsigned __int64 v19; // rcx
  __int16 v20; // ax
  int v21; // r12d
  CDetectURL *v22; // rcx
  CDetectURL *v23; // rcx
  int v24; // eax
  CDetectURL *v25; // rcx
  int v26; // eax
  int v27; // r14d
  CDetectURL *v28; // rcx
  int v29; // r13d
  __int64 v30; // rsi
  int v31; // r12d
  int v32; // ecx
  int v33; // ebx
  int v34; // edi
  int v35; // r15d
  _DWORD *v36; // rdx
  int v37; // eax
  __int64 v38; // rcx
  __int16 v39; // dx
  __int64 *v40; // rax
  int v41; // edx
  _DWORD *v42; // rcx
  int v43; // ebx
  int v44; // [rsp+30h] [rbp-99h] BYREF
  int v45; // [rsp+34h] [rbp-95h] BYREF
  __int64 *v46; // [rsp+38h] [rbp-91h] BYREF
  _BYTE v47[24]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v48[16]; // [rsp+58h] [rbp-71h] BYREF
  int v49; // [rsp+68h] [rbp-61h]
  __int64 v50; // [rsp+78h] [rbp-51h]
  int v51; // [rsp+80h] [rbp-49h]
  int v52; // [rsp+84h] [rbp-45h]
  __int64 v53; // [rsp+88h] [rbp-41h]
  __int64 v54; // [rsp+90h] [rbp-39h]
  int v55; // [rsp+98h] [rbp-31h]
  __int16 v56; // [rsp+A2h] [rbp-27h]
  CTxtRange *v57; // [rsp+B0h] [rbp-19h]
  int v58; // [rsp+B8h] [rbp-11h] BYREF
  char v59; // [rsp+BCh] [rbp-Dh]
  int v62; // [rsp+140h] [rbp+77h] BYREF
  int v63; // [rsp+148h] [rbp+7Fh]

  v3 = (CTxtEdit *)*((_QWORD *)this + 2);
  v4 = a2;
  v62 = 0;
  v45 = 0;
  Sel = CTxtEdit::GetSel(v3);
  v57 = Sel;
  if ( Sel )
  {
    CTxtRange::CTxtRange((CTxtRange *)v47, Sel);
    v56 |= 8u;
    v44 = 0;
    v53 = 0;
    v54 = 0;
    if ( (unsigned int)CDetectURL::GetScanRegion(this, &v62, &v45) )
    {
      v63 = 0;
      v6 = 0;
      CTxtRange::Set((CTxtRange *)v47, v62, 0);
      v8 = v49;
      if ( v49 < v45 )
      {
        while ( 1 )
        {
          v9 = CDetectURL::MoveByDelimiters(v7, (const struct CTxtPtr *)v48, 1, 0x22u, 0);
          v10 = -v9;
          v11 = v8 + v9;
          CTxtRange::Set((CTxtRange *)v47, v8 + v9, 0);
          LOWORD(v62) = 32;
          v13 = CDetectURL::MoveByDelimiters(v12, (const struct CTxtPtr *)v48, 1, 9u, (unsigned __int16 *)&v62);
          v15 = CDetectURL::MoveByDelimiters(v14, (const struct CTxtPtr *)v48, 1, 1u, 0);
          v16 = v15;
          if ( v15 == v13 )
          {
            v17 = -v15;
          }
          else
          {
            v18 = (unsigned __int16)v62;
            CTxtRange::Set((CTxtRange *)v47, v11 + v15, 0);
            v19 = (unsigned int)(v18 - 34);
            if ( v18 == 34 || (v19 = (unsigned int)(v18 - 39), v18 == 39) )
            {
              v20 = v18;
            }
            else
            {
              v19 = (unsigned int)(v18 - 40);
              if ( v18 == 40 )
              {
                v20 = 41;
              }
              else
              {
                v19 = (unsigned int)(v18 - 60);
                if ( v18 == 60 )
                {
                  v20 = 62;
                }
                else
                {
                  v19 = (unsigned int)(v18 - 91);
                  if ( v18 == 91 )
                  {
                    v20 = 93;
                  }
                  else
                  {
                    v20 = 32;
                    if ( v18 == 123 )
                      v20 = 125;
                  }
                }
              }
            }
            LOWORD(v62) = v20;
            v21 = CDetectURL::MoveByDelimiters(
                    (CDetectURL *)v19,
                    (const struct CTxtPtr *)v48,
                    -1,
                    0x19u,
                    (unsigned __int16 *)&v62);
            if ( v18 == 60
              && (CTxtRange::Set((CTxtRange *)v47, v11 + v13, 0),
                  LOWORD(v62) = 62,
                  (int)CDetectURL::GetAngleBracket(v22, (struct CTxtPtr *)v48, 0) < 0)
              && (v24 = CDetectURL::MoveByDelimiters(
                          v23,
                          (const struct CTxtPtr *)v48,
                          1,
                          0x10u,
                          (unsigned __int16 *)&v62),
                  (_WORD)v62 == 62) )
            {
              v11 += v13;
              v17 = 1 - v24;
            }
            else
            {
              v11 += v13;
              v17 = v13 - v21 - v16;
            }
            v4 = a2;
            v6 = v63;
          }
          CTxtRange::Set((CTxtRange *)v47, v11, v17);
          if ( !v55 )
            break;
          LOBYTE(v26) = CDetectURL::IsURL(v25, (unsigned __int64)v47);
          if ( v26 )
          {
            v58 = 32;
            v59 = 0;
            CTxtRange::SetCharFormat((CTxtRange *)v47, (const struct CCharFormat *)&v58, 0x80000000, v4, 0x20u, 0x8000u);
            v27 = v49 - v55;
            if ( v49 > v8 )
            {
              CTxtRange::Set((CTxtRange *)v47, v8, v8 - v49);
              CDetectURL::CheckAndCleanBogusURL(this, (struct CTxtRange *)v47, &v44, a2);
              v63 = v44 | v6;
            }
            CTxtRange::Set((CTxtRange *)v47, v27, 0);
            v29 = -(int)CDetectURL::MoveByDelimiters(v28, (const struct CTxtPtr *)v48, 1, 1u, 0);
          }
          else
          {
            v29 = v10 - v16;
            v27 = v8;
          }
          v62 = v29;
          if ( v29 )
          {
            CTxtRange::Set((CTxtRange *)v47, v27, v29);
            v30 = v50;
            v59 = 0;
            v31 = 0;
            v44 = 0;
            if ( v50 )
            {
              v32 = *(_DWORD *)(v50 + 8);
              if ( v32 )
              {
                v33 = v51;
                v34 = -v55;
                v35 = v52;
                if ( v32 > 0 && v51 < v32 && *(_QWORD *)v50 && v51 >= 0 )
                  v36 = (_DWORD *)(*(_QWORD *)v50 + *(_DWORD *)(v50 + 16) * v51);
                else
                  v36 = 0;
                if ( *v36 == v52 && v51 < v32 - 1 )
                {
                  v33 = v51 + 1;
                  v35 = 0;
                }
                if ( v55 < 0 )
                {
                  while ( 1 )
                  {
                    v37 = *(_DWORD *)(v30 + 8);
                    if ( !v37 )
                      break;
                    if ( v37 > 0 && v33 < v37 && *(_QWORD *)v30 && v33 >= 0 )
                      v38 = *(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v33;
                    else
                      v38 = 0;
                    v39 = *(_WORD *)(v38 + 4);
                    v46 = 0;
                    if ( v39 < 0 )
                      goto LABEL_54;
LABEL_55:
                    if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int64 **))(*(_QWORD *)qword_1800A41F0
                                                                                          + 32LL))(
                           qword_1800A41F0,
                           (unsigned int)v39,
                           &v46) >= 0 )
                    {
                      v40 = v46;
                    }
                    else
                    {
                      v40 = g_defaultCF;
                      v46 = g_defaultCF;
                    }
                    if ( (*(_BYTE *)v40 & 0x20) == 0 )
                    {
                      v41 = *(_DWORD *)(v30 + 8);
                      if ( v41 > 0 && v33 < v41 && *(_QWORD *)v30 && v33 >= 0 )
                        v42 = (_DWORD *)(*(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v33);
                      else
                        v42 = 0;
                      v34 += v35 - *v42;
                      if ( v33 < v41 - 1 )
                      {
                        ++v33;
                        v35 = 0;
                      }
                      if ( v34 > 0 )
                        continue;
                    }
                    v29 = v62;
                    v31 = v44;
                    if ( v34 > 0 )
                    {
                      v58 = 0;
                      v31 = 1;
                      v44 = 1;
                      CTxtRange::SetCharFormat(
                        (CTxtRange *)v47,
                        (const struct CCharFormat *)&v58,
                        0x80000000,
                        a2,
                        0x20u,
                        0x8000u);
                    }
                    goto LABEL_70;
                  }
                  v46 = 0;
LABEL_54:
                  v39 = *(_WORD *)(*((_QWORD *)this + 2) + 276LL);
                  goto LABEL_55;
                }
              }
            }
LABEL_70:
            v43 = v31 | v63;
            v63 |= v31;
            CTxtRange::Set((CTxtRange *)v47, v27 - v29, 0);
          }
          else
          {
            v43 = v63;
          }
          v8 = v49;
          v4 = a2;
          if ( v49 >= v45 )
            goto LABEL_75;
          v6 = v63;
        }
        v43 = v63;
LABEL_75:
        if ( v43 )
        {
          if ( !*((_DWORD *)v57 + 22) )
            CTxtRange::Update_iFormat(v57, -1);
        }
      }
    }
    CTxtRange::~CTxtRange((CTxtRange *)v47);
  }
}

```

## disassembly

```asm
0x180016b44  mov     [rsp-8+arg_8], rdx
0x180016b49  mov     [rsp-8+arg_0], rcx
0x180016b4e  push    rbp
0x180016b4f  push    rbx
0x180016b50  push    rsi
0x180016b51  push    rdi
0x180016b52  push    r12
0x180016b54  push    r13
0x180016b56  push    r14
0x180016b58  push    r15
0x180016b5a  lea     rbp, [rsp-1Fh]
0x180016b5f  sub     rsp, 0E8h
0x180016b66  mov     rbx, rcx
0x180016b69  xor     esi, esi
0x180016b6b  mov     rcx, [rcx+10h]; this
0x180016b6f  mov     r14, rdx
0x180016b72  mov     [rbp+57h+arg_10], esi
0x180016b75  mov     [rsp+120h+var_EC], esi
0x180016b79  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x180016b7e  mov     [rbp+57h+var_70], rax
0x180016b82  test    rax, rax
0x180016b85  jz      loc_180017022
0x180016b8b  mov     rdx, rax; struct CTxtRange *
0x180016b8e  lea     rcx, [rsp+120h+var_E0]; this
0x180016b93  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x180016b98  or      [rbp+57h+var_7E], 8
0x180016b9d  lea     r8, [rsp+120h+var_EC]; int *
0x180016ba2  lea     rdx, [rbp+57h+arg_10]; int *
0x180016ba6  mov     [rsp+120h+var_F0], esi
0x180016baa  mov     rcx, rbx; this
0x180016bad  mov     [rbp+57h+var_98], rsi
0x180016bb1  mov     [rbp+57h+var_90], rsi
0x180016bb5  call    ?GetScanRegion@CDetectURL@@AEAAHAEAJ0@Z; CDetectURL::GetScanRegion(long &,long &)
0x180016bba  test    eax, eax
0x180016bbc  jz      loc_180017018
0x180016bc2  mov     edx, [rbp+57h+arg_10]; int
0x180016bc5  lea     rcx, [rsp+120h+var_E0]; this
0x180016bca  xor     r8d, r8d; int
0x180016bcd  mov     [rbp+57h+arg_18], esi
0x180016bd0  mov     r12d, esi
0x180016bd3  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016bd8  mov     edi, [rbp+57h+var_B8]
0x180016bdb  cmp     edi, [rsp+120h+var_EC]
0x180016bdf  jge     loc_180017018
0x180016be5  lea     r15d, [rsi+1]
0x180016be9  jmp     short loc_180016BEF
0x180016beb  mov     r12d, [rbp+57h+arg_18]
0x180016bef  mov     r9d, 22h ; '"'; unsigned int
0x180016bf5  mov     [rsp+120h+var_100], rsi; unsigned __int16 *
0x180016bfa  mov     r8d, r15d; int
0x180016bfd  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016c01  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016c06  mov     r13d, eax
0x180016c09  lea     rcx, [rsp+120h+var_E0]; this
0x180016c0e  neg     r13d
0x180016c11  mov     esi, edi
0x180016c13  sub     esi, r13d
0x180016c16  xor     r8d, r8d; int
0x180016c19  mov     edx, esi; int
0x180016c1b  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016c20  mov     eax, 20h ; ' '
0x180016c25  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016c29  mov     word ptr [rbp+57h+arg_10], ax
0x180016c2d  mov     r9d, 9; unsigned int
0x180016c33  lea     rax, [rbp+57h+arg_10]
0x180016c37  mov     r8d, r15d; int
0x180016c3a  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180016c3f  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016c44  mov     r9d, r15d; unsigned int
0x180016c47  mov     [rsp+120h+var_100], 0; unsigned __int16 *
0x180016c50  mov     r8d, r15d; int
0x180016c53  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016c57  mov     ebx, eax
0x180016c59  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016c5e  mov     r15d, eax
0x180016c61  cmp     eax, ebx
0x180016c63  jnz     short loc_180016C6E
0x180016c65  mov     ebx, eax
0x180016c67  neg     ebx
0x180016c69  jmp     loc_180016D5F
0x180016c6e  movzx   r14d, word ptr [rbp+57h+arg_10]
0x180016c73  lea     edx, [rsi+rax]; int
0x180016c76  xor     r8d, r8d; int
0x180016c79  lea     rcx, [rsp+120h+var_E0]; this
0x180016c7e  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016c83  mov     ecx, r14d
0x180016c86  sub     ecx, 22h ; '"'; this
0x180016c89  jz      short loc_180016CC4
0x180016c8b  sub     ecx, 5
0x180016c8e  jz      short loc_180016CC4
0x180016c90  sub     ecx, 1
0x180016c93  jz      short loc_180016CBD
0x180016c95  sub     ecx, 14h
0x180016c98  jz      short loc_180016CB6
0x180016c9a  sub     ecx, 1Fh
0x180016c9d  jz      short loc_180016CAF
0x180016c9f  mov     eax, 20h ; ' '
0x180016ca4  cmp     ecx, eax
0x180016ca6  jnz     short loc_180016CC8
0x180016ca8  mov     eax, 7Dh ; '}'
0x180016cad  jmp     short loc_180016CC8
0x180016caf  mov     eax, 5Dh ; ']'
0x180016cb4  jmp     short loc_180016CC8
0x180016cb6  mov     eax, 3Eh ; '>'
0x180016cbb  jmp     short loc_180016CC8
0x180016cbd  mov     eax, 29h ; ')'
0x180016cc2  jmp     short loc_180016CC8
0x180016cc4  movzx   eax, r14w
0x180016cc8  mov     word ptr [rbp+57h+arg_10], ax
0x180016ccc  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016cd0  lea     rax, [rbp+57h+arg_10]
0x180016cd4  mov     r9d, 19h; unsigned int
0x180016cda  or      r8d, 0FFFFFFFFh; int
0x180016cde  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180016ce3  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016ce8  mov     r12d, eax
0x180016ceb  cmp     r14d, 3Ch ; '<'
0x180016cef  jnz     short loc_180016D4F
0x180016cf1  lea     r14d, [rsi+rbx]
0x180016cf5  xor     r8d, r8d; int
0x180016cf8  mov     edx, r14d; int
0x180016cfb  lea     rcx, [rsp+120h+var_E0]; this
0x180016d00  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016d05  mov     eax, 3Eh ; '>'
0x180016d0a  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016d0e  xor     r8d, r8d; int
0x180016d11  mov     word ptr [rbp+57h+arg_10], ax
0x180016d15  call    ?GetAngleBracket@CDetectURL@@AEAAJAEAVCTxtPtr@@J@Z; CDetectURL::GetAngleBracket(CTxtPtr &,long)
0x180016d1a  test    eax, eax
0x180016d1c  jns     short loc_180016D4F
0x180016d1e  mov     r9d, 10h; unsigned int
0x180016d24  lea     rax, [rbp+57h+arg_10]
0x180016d28  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016d2c  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180016d31  lea     r8d, [r9-0Fh]; int
0x180016d35  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016d3a  mov     ecx, 3Eh ; '>'
0x180016d3f  cmp     word ptr [rbp+57h+arg_10], cx
0x180016d43  jnz     short loc_180016D4F
0x180016d45  lea     ebx, [rcx-3Dh]
0x180016d48  mov     esi, r14d
0x180016d4b  sub     ebx, eax
0x180016d4d  jmp     short loc_180016D57
0x180016d4f  add     esi, ebx
0x180016d51  sub     ebx, r12d
0x180016d54  sub     ebx, r15d
0x180016d57  mov     r14, [rbp+57h+arg_8]
0x180016d5b  mov     r12d, [rbp+57h+arg_18]
0x180016d5f  mov     r8d, ebx; int
0x180016d62  lea     rcx, [rsp+120h+var_E0]; this
0x180016d67  mov     edx, esi; int
0x180016d69  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016d6e  xor     esi, esi
0x180016d70  cmp     [rbp+57h+var_88], esi
0x180016d73  jz      loc_180017000
0x180016d79  lea     rdx, [rsp+120h+var_E0]; struct CTxtRange *
0x180016d7e  call    ?IsURL@CDetectURL@@AEAAHAEAVCTxtRange@@@Z; CDetectURL::IsURL(CTxtRange &)
0x180016d83  test    eax, eax
0x180016d85  jz      loc_180016E29
0x180016d8b  lea     eax, [rsi+20h]
0x180016d8e  mov     [rsp+120h+var_F8], 8000h; unsigned int
0x180016d96  mov     r9, r14; struct IUndoBuilder *
0x180016d99  mov     [rbp+57h+var_68], eax
0x180016d9c  mov     r8d, 80000000h; unsigned int
0x180016da2  mov     dword ptr [rsp+120h+var_100], eax; unsigned int
0x180016da6  lea     rdx, [rbp+57h+var_68]; struct CCharFormat *
0x180016daa  mov     [rbp+57h+var_64], sil
0x180016dae  lea     rcx, [rsp+120h+var_E0]; this
0x180016db3  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180016db8  mov     eax, [rbp+57h+var_B8]
0x180016dbb  mov     r14d, eax
0x180016dbe  sub     r14d, [rbp+57h+var_88]
0x180016dc2  cmp     eax, edi
0x180016dc4  jle     short loc_180016DF8
0x180016dc6  mov     r8d, edi
0x180016dc9  lea     rcx, [rsp+120h+var_E0]; this
0x180016dce  sub     r8d, eax; int
0x180016dd1  mov     edx, edi; int
0x180016dd3  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016dd8  mov     r9, [rbp+57h+arg_8]; struct IUndoBuilder *
0x180016ddc  lea     r8, [rsp+120h+var_F0]; int *
0x180016de1  mov     rcx, [rbp+57h+arg_0]; this
0x180016de5  lea     rdx, [rsp+120h+var_E0]; struct CTxtRange *
0x180016dea  call    ?CheckAndCleanBogusURL@CDetectURL@@AEAAXAEAVCTxtRange@@AEAHPEAVIUndoBuilder@@@Z; CDetectURL::CheckAndCleanBogusURL(CTxtRange &,int &,IUndoBuilder *)
0x180016def  or      r12d, [rsp+120h+var_F0]
0x180016df4  mov     [rbp+57h+arg_18], r12d
0x180016df8  xor     r8d, r8d; int
0x180016dfb  lea     rcx, [rsp+120h+var_E0]; this
0x180016e00  mov     edx, r14d; int
0x180016e03  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016e08  mov     eax, 1
0x180016e0d  mov     [rsp+120h+var_100], rsi; unsigned __int16 *
0x180016e12  mov     r9d, eax; unsigned int
0x180016e15  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180016e19  mov     r8d, eax; int
0x180016e1c  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180016e21  mov     r13d, eax
0x180016e24  neg     r13d
0x180016e27  jmp     short loc_180016E2F
0x180016e29  sub     r13d, r15d
0x180016e2c  mov     r14d, edi
0x180016e2f  mov     [rbp+57h+arg_10], r13d
0x180016e33  test    r13d, r13d
0x180016e36  jz      loc_180016FE4
0x180016e3c  mov     r8d, r13d; int
0x180016e3f  lea     rcx, [rsp+120h+var_E0]; this
0x180016e44  mov     edx, r14d; int
0x180016e47  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180016e4c  mov     rsi, [rbp+57h+var_A8]
0x180016e50  xor     r8d, r8d
0x180016e53  mov     [rbp+57h+var_64], r8b
0x180016e57  mov     r12d, r8d
0x180016e5a  mov     [rsp+120h+var_F0], r8d
0x180016e5f  test    rsi, rsi
0x180016e62  jz      loc_180016FC4
0x180016e68  mov     ecx, [rsi+8]
0x180016e6b  test    ecx, ecx
0x180016e6d  jz      loc_180016FC4
0x180016e73  mov     edi, [rbp+57h+var_88]
0x180016e76  mov     ebx, [rbp+57h+var_A0]
0x180016e79  neg     edi
0x180016e7b  mov     r15d, [rbp+57h+var_9C]
0x180016e7f  test    ecx, ecx
0x180016e81  jle     short loc_180016E9E
0x180016e83  cmp     ebx, ecx
0x180016e85  jge     short loc_180016E9E
0x180016e87  cmp     [rsi], r8
0x180016e8a  jz      short loc_180016E9E
0x180016e8c  test    ebx, ebx
0x180016e8e  js      short loc_180016E9E
0x180016e90  mov     eax, ebx
0x180016e92  imul    eax, [rsi+10h]
0x180016e96  movsxd  rdx, eax
0x180016e99  add     rdx, [rsi]
0x180016e9c  jmp     short loc_180016EA1
0x180016e9e  mov     rdx, r8
0x180016ea1  cmp     [rdx], r15d
0x180016ea4  jnz     short loc_180016EB2
0x180016ea6  lea     eax, [rcx-1]
0x180016ea9  cmp     ebx, eax
0x180016eab  jge     short loc_180016EB2
0x180016ead  inc     ebx
0x180016eaf  mov     r15d, r8d
0x180016eb2  test    edi, edi
0x180016eb4  jle     loc_180016FC4
0x180016eba  mov     r12, [rbp+57h+arg_0]
0x180016ebe  mov     eax, [rsi+8]
0x180016ec1  test    eax, eax
0x180016ec3  jz      short loc_180016EF5
0x180016ec5  jle     short loc_180016EE2
0x180016ec7  cmp     ebx, eax
0x180016ec9  jge     short loc_180016EE2
0x180016ecb  cmp     [rsi], r8
0x180016ece  jz      short loc_180016EE2
0x180016ed0  test    ebx, ebx
0x180016ed2  js      short loc_180016EE2
0x180016ed4  mov     eax, ebx
0x180016ed6  imul    eax, [rsi+10h]
0x180016eda  movsxd  rcx, eax
0x180016edd  add     rcx, [rsi]
0x180016ee0  jmp     short loc_180016EE5
0x180016ee2  mov     rcx, r8
0x180016ee5  movzx   edx, word ptr [rcx+4]
0x180016ee9  mov     [rsp+120h+var_E8], r8
0x180016eee  test    dx, dx
0x180016ef1  jns     short loc_180016F06
0x180016ef3  jmp     short loc_180016EFA
0x180016ef5  mov     [rsp+120h+var_E8], r8
0x180016efa  mov     rax, [r12+10h]
0x180016eff  movzx   edx, word ptr [rax+114h]
0x180016f06  mov     rcx, cs:qword_1800A41F0
0x180016f0d  lea     r8, [rsp+120h+var_E8]
0x180016f12  movsx   edx, dx
0x180016f15  mov     rax, [rcx]
0x180016f18  mov     rax, [rax+20h]
0x180016f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f21  xor     r8d, r8d
0x180016f24  test    eax, eax
0x180016f26  jns     short loc_180016F36
0x180016f28  lea     rax, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x180016f2f  mov     [rsp+120h+var_E8], rax
0x180016f34  jmp     short loc_180016F3B
0x180016f36  mov     rax, [rsp+120h+var_E8]
0x180016f3b  test    byte ptr [rax], 20h
0x180016f3e  jnz     short loc_180016F80
0x180016f40  mov     edx, [rsi+8]
0x180016f43  test    edx, edx
0x180016f45  jle     short loc_180016F62
0x180016f47  cmp     ebx, edx
0x180016f49  jge     short loc_180016F62
0x180016f4b  cmp     [rsi], r8
0x180016f4e  jz      short loc_180016F62
0x180016f50  test    ebx, ebx
0x180016f52  js      short loc_180016F62
0x180016f54  mov     eax, ebx
0x180016f56  imul    eax, [rsi+10h]
0x180016f5a  movsxd  rcx, eax
0x180016f5d  add     rcx, [rsi]
0x180016f60  jmp     short loc_180016F65
0x180016f62  mov     rcx, r8
  ... truncated ...
```
