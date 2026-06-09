# CDetectURL::ScanAndUpdate(IUndoBuilder *)

- ea: `0x1800159d8`
- end: `0x180015ecb`
- name: `?ScanAndUpdate@CDetectURL@@QEAAXPEAVIUndoBuilder@@@Z`
- size: `1267`
- prototype: `void __fastcall(CDetectURL *__hidden this, struct IUndoBuilder *)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800238dc`
- `0x180027b20`
- `0x18002ac10`
- `0x18002ade0`

## callees

- `0x180005510`
- `0x1800159d8`
- `0x180015ee0`
- `0x180016700`
- `0x180016d90`
- `0x180021c30`
- `0x180023110`
- `0x18002c5d8`
- `0x18002c650`
- `0x180038970`
- `0x18003aa30`
- `0x18003aebc`
- `0x180095010`

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
  int v26; // r14d
  CDetectURL *v27; // rcx
  int v28; // r13d
  __int64 v29; // rsi
  int v30; // r12d
  int v31; // ecx
  int v32; // ebx
  int v33; // edi
  int v34; // r15d
  _DWORD *v35; // rdx
  int v36; // eax
  __int64 v37; // rcx
  __int16 v38; // dx
  __int64 *v39; // rax
  int v40; // edx
  _DWORD *v41; // rcx
  int v42; // ebx
  int v43; // [rsp+30h] [rbp-99h] BYREF
  int v44; // [rsp+34h] [rbp-95h] BYREF
  __int64 *v45; // [rsp+38h] [rbp-91h] BYREF
  _BYTE v46[24]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v47[16]; // [rsp+58h] [rbp-71h] BYREF
  int v48; // [rsp+68h] [rbp-61h]
  __int64 v49; // [rsp+78h] [rbp-51h]
  int v50; // [rsp+80h] [rbp-49h]
  int v51; // [rsp+84h] [rbp-45h]
  __int64 v52; // [rsp+88h] [rbp-41h]
  __int64 v53; // [rsp+90h] [rbp-39h]
  int v54; // [rsp+98h] [rbp-31h]
  __int16 v55; // [rsp+A2h] [rbp-27h]
  CTxtRange *v56; // [rsp+B0h] [rbp-19h]
  int v57; // [rsp+B8h] [rbp-11h] BYREF
  char v58; // [rsp+BCh] [rbp-Dh]
  int v61; // [rsp+140h] [rbp+77h] BYREF
  int v62; // [rsp+148h] [rbp+7Fh]

  v3 = (CTxtEdit *)*((_QWORD *)this + 2);
  v4 = a2;
  v61 = 0;
  v44 = 0;
  Sel = CTxtEdit::GetSel(v3);
  v56 = Sel;
  if ( Sel )
  {
    CTxtRange::CTxtRange((CTxtRange *)v46, Sel);
    v55 |= 8u;
    v43 = 0;
    v52 = 0;
    v53 = 0;
    if ( (unsigned int)CDetectURL::GetScanRegion(this, &v61, &v44) )
    {
      v62 = 0;
      v6 = 0;
      CTxtRange::Set((CTxtRange *)v46, v61, 0);
      v8 = v48;
      if ( v48 < v44 )
      {
        while ( 1 )
        {
          v9 = CDetectURL::MoveByDelimiters(v7, (const struct CTxtPtr *)v47, 1, 0x22u, 0);
          v10 = -v9;
          v11 = v8 + v9;
          CTxtRange::Set((CTxtRange *)v46, v8 + v9, 0);
          LOWORD(v61) = 32;
          v13 = CDetectURL::MoveByDelimiters(v12, (const struct CTxtPtr *)v47, 1, 9u, (unsigned __int16 *)&v61);
          v15 = CDetectURL::MoveByDelimiters(v14, (const struct CTxtPtr *)v47, 1, 1u, 0);
          v16 = v15;
          if ( v15 == v13 )
          {
            v17 = -v15;
          }
          else
          {
            v18 = (unsigned __int16)v61;
            CTxtRange::Set((CTxtRange *)v46, v11 + v15, 0);
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
            LOWORD(v61) = v20;
            v21 = CDetectURL::MoveByDelimiters(
                    (CDetectURL *)v19,
                    (const struct CTxtPtr *)v47,
                    -1,
                    0x19u,
                    (unsigned __int16 *)&v61);
            if ( v18 == 60
              && (CTxtRange::Set((CTxtRange *)v46, v11 + v13, 0),
                  LOWORD(v61) = 62,
                  (int)CDetectURL::GetAngleBracket(v22, (struct CTxtPtr *)v47, 0) < 0)
              && (v24 = CDetectURL::MoveByDelimiters(
                          v23,
                          (const struct CTxtPtr *)v47,
                          1,
                          0x10u,
                          (unsigned __int16 *)&v61),
                  (_WORD)v61 == 62) )
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
            v6 = v62;
          }
          CTxtRange::Set((CTxtRange *)v46, v11, v17);
          if ( !v54 )
            break;
          if ( (unsigned int)CDetectURL::IsURL(v25, (struct CTxtRange *)v46) )
          {
            v57 = 32;
            v58 = 0;
            CTxtRange::SetCharFormat((CTxtRange *)v46, (const struct CCharFormat *)&v57, 0x80000000, v4, 0x20u, 0x8000u);
            v26 = v48 - v54;
            if ( v48 > v8 )
            {
              CTxtRange::Set((CTxtRange *)v46, v8, v8 - v48);
              CDetectURL::CheckAndCleanBogusURL(this, (struct CTxtRange *)v46, &v43, a2);
              v62 = v43 | v6;
            }
            CTxtRange::Set((CTxtRange *)v46, v26, 0);
            v28 = -(int)CDetectURL::MoveByDelimiters(v27, (const struct CTxtPtr *)v47, 1, 1u, 0);
          }
          else
          {
            v28 = v10 - v16;
            v26 = v8;
          }
          v61 = v28;
          if ( v28 )
          {
            CTxtRange::Set((CTxtRange *)v46, v26, v28);
            v29 = v49;
            v58 = 0;
            v30 = 0;
            v43 = 0;
            if ( v49 )
            {
              v31 = *(_DWORD *)(v49 + 8);
              if ( v31 )
              {
                v32 = v50;
                v33 = -v54;
                v34 = v51;
                if ( v31 > 0 && v50 < v31 && *(_QWORD *)v49 && v50 >= 0 )
                  v35 = (_DWORD *)(*(_QWORD *)v49 + *(_DWORD *)(v49 + 16) * v50);
                else
                  v35 = 0;
                if ( *v35 == v51 && v50 < v31 - 1 )
                {
                  v32 = v50 + 1;
                  v34 = 0;
                }
                if ( v54 < 0 )
                {
                  while ( 1 )
                  {
                    v36 = *(_DWORD *)(v29 + 8);
                    if ( !v36 )
                      break;
                    if ( v36 > 0 && v32 < v36 && *(_QWORD *)v29 && v32 >= 0 )
                      v37 = *(_QWORD *)v29 + *(_DWORD *)(v29 + 16) * v32;
                    else
                      v37 = 0;
                    v38 = *(_WORD *)(v37 + 4);
                    v45 = 0;
                    if ( v38 < 0 )
                      goto LABEL_54;
LABEL_55:
                    if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int64 **))(*(_QWORD *)qword_1800A72D0
                                                                                          + 32LL))(
                           qword_1800A72D0,
                           (unsigned int)v38,
                           &v45) >= 0 )
                    {
                      v39 = v45;
                    }
                    else
                    {
                      v39 = g_defaultCF;
                      v45 = g_defaultCF;
                    }
                    if ( (*(_BYTE *)v39 & 0x20) == 0 )
                    {
                      v40 = *(_DWORD *)(v29 + 8);
                      if ( v40 > 0 && v32 < v40 && *(_QWORD *)v29 && v32 >= 0 )
                        v41 = (_DWORD *)(*(_QWORD *)v29 + *(_DWORD *)(v29 + 16) * v32);
                      else
                        v41 = 0;
                      v33 += v34 - *v41;
                      if ( v32 < v40 - 1 )
                      {
                        ++v32;
                        v34 = 0;
                      }
                      if ( v33 > 0 )
                        continue;
                    }
                    v28 = v61;
                    v30 = v43;
                    if ( v33 > 0 )
                    {
                      v57 = 0;
                      v30 = 1;
                      v43 = 1;
                      CTxtRange::SetCharFormat(
                        (CTxtRange *)v46,
                        (const struct CCharFormat *)&v57,
                        0x80000000,
                        a2,
                        0x20u,
                        0x8000u);
                    }
                    goto LABEL_70;
                  }
                  v45 = 0;
LABEL_54:
                  v38 = *(_WORD *)(*((_QWORD *)this + 2) + 276LL);
                  goto LABEL_55;
                }
              }
            }
LABEL_70:
            v42 = v30 | v62;
            v62 |= v30;
            CTxtRange::Set((CTxtRange *)v46, v26 - v28, 0);
          }
          else
          {
            v42 = v62;
          }
          v8 = v48;
          v4 = a2;
          if ( v48 >= v44 )
            goto LABEL_75;
          v6 = v62;
        }
        v42 = v62;
LABEL_75:
        if ( v42 )
        {
          if ( !*((_DWORD *)v56 + 22) )
            CTxtRange::Update_iFormat(v56, -1);
        }
      }
    }
    CTxtRange::~CTxtRange((CTxtRange *)v46);
  }
}

```

## disassembly

```asm
0x1800159d8  mov     [rsp-8+arg_8], rdx
0x1800159dd  mov     [rsp-8+arg_0], rcx
0x1800159e2  push    rbp
0x1800159e3  push    rbx
0x1800159e4  push    rsi
0x1800159e5  push    rdi
0x1800159e6  push    r12
0x1800159e8  push    r13
0x1800159ea  push    r14
0x1800159ec  push    r15
0x1800159ee  lea     rbp, [rsp-1Fh]
0x1800159f3  sub     rsp, 0E8h
0x1800159fa  mov     rbx, rcx
0x1800159fd  xor     esi, esi
0x1800159ff  mov     rcx, [rcx+10h]; this
0x180015a03  mov     r14, rdx
0x180015a06  mov     [rbp+57h+arg_10], esi
0x180015a09  mov     [rsp+120h+var_EC], esi
0x180015a0d  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x180015a12  mov     [rbp+57h+var_70], rax
0x180015a16  test    rax, rax
0x180015a19  jz      loc_180015EB6
0x180015a1f  mov     rdx, rax; struct CTxtRange *
0x180015a22  lea     rcx, [rsp+120h+var_E0]; this
0x180015a27  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x180015a2c  or      [rbp+57h+var_7E], 8
0x180015a31  lea     r8, [rsp+120h+var_EC]; int *
0x180015a36  lea     rdx, [rbp+57h+arg_10]; int *
0x180015a3a  mov     [rsp+120h+var_F0], esi
0x180015a3e  mov     rcx, rbx; this
0x180015a41  mov     [rbp+57h+var_98], rsi
0x180015a45  mov     [rbp+57h+var_90], rsi
0x180015a49  call    ?GetScanRegion@CDetectURL@@AEAAHAEAJ0@Z; CDetectURL::GetScanRegion(long &,long &)
0x180015a4e  test    eax, eax
0x180015a50  jz      loc_180015EAC
0x180015a56  mov     edx, [rbp+57h+arg_10]; int
0x180015a59  lea     rcx, [rsp+120h+var_E0]; this
0x180015a5e  xor     r8d, r8d; int
0x180015a61  mov     [rbp+57h+arg_18], esi
0x180015a64  mov     r12d, esi
0x180015a67  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015a6c  mov     edi, [rbp+57h+var_B8]
0x180015a6f  cmp     edi, [rsp+120h+var_EC]
0x180015a73  jge     loc_180015EAC
0x180015a79  lea     r15d, [rsi+1]
0x180015a7d  jmp     short loc_180015A83
0x180015a7f  mov     r12d, [rbp+57h+arg_18]
0x180015a83  mov     r9d, 22h ; '"'; unsigned int
0x180015a89  mov     [rsp+120h+var_100], rsi; unsigned __int16 *
0x180015a8e  mov     r8d, r15d; int
0x180015a91  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015a95  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015a9a  mov     r13d, eax
0x180015a9d  lea     rcx, [rsp+120h+var_E0]; this
0x180015aa2  neg     r13d
0x180015aa5  mov     esi, edi
0x180015aa7  sub     esi, r13d
0x180015aaa  xor     r8d, r8d; int
0x180015aad  mov     edx, esi; int
0x180015aaf  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015ab4  mov     eax, 20h ; ' '
0x180015ab9  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015abd  mov     word ptr [rbp+57h+arg_10], ax
0x180015ac1  mov     r9d, 9; unsigned int
0x180015ac7  lea     rax, [rbp+57h+arg_10]
0x180015acb  mov     r8d, r15d; int
0x180015ace  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180015ad3  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015ad8  mov     r9d, r15d; unsigned int
0x180015adb  mov     [rsp+120h+var_100], 0; unsigned __int16 *
0x180015ae4  mov     r8d, r15d; int
0x180015ae7  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015aeb  mov     ebx, eax
0x180015aed  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015af2  mov     r15d, eax
0x180015af5  cmp     eax, ebx
0x180015af7  jnz     short loc_180015B02
0x180015af9  mov     ebx, eax
0x180015afb  neg     ebx
0x180015afd  jmp     loc_180015BF3
0x180015b02  movzx   r14d, word ptr [rbp+57h+arg_10]
0x180015b07  lea     edx, [rsi+rax]; int
0x180015b0a  xor     r8d, r8d; int
0x180015b0d  lea     rcx, [rsp+120h+var_E0]; this
0x180015b12  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015b17  mov     ecx, r14d
0x180015b1a  sub     ecx, 22h ; '"'; this
0x180015b1d  jz      short loc_180015B58
0x180015b1f  sub     ecx, 5
0x180015b22  jz      short loc_180015B58
0x180015b24  sub     ecx, 1
0x180015b27  jz      short loc_180015B51
0x180015b29  sub     ecx, 14h
0x180015b2c  jz      short loc_180015B4A
0x180015b2e  sub     ecx, 1Fh
0x180015b31  jz      short loc_180015B43
0x180015b33  mov     eax, 20h ; ' '
0x180015b38  cmp     ecx, eax
0x180015b3a  jnz     short loc_180015B5C
0x180015b3c  mov     eax, 7Dh ; '}'
0x180015b41  jmp     short loc_180015B5C
0x180015b43  mov     eax, 5Dh ; ']'
0x180015b48  jmp     short loc_180015B5C
0x180015b4a  mov     eax, 3Eh ; '>'
0x180015b4f  jmp     short loc_180015B5C
0x180015b51  mov     eax, 29h ; ')'
0x180015b56  jmp     short loc_180015B5C
0x180015b58  movzx   eax, r14w
0x180015b5c  mov     word ptr [rbp+57h+arg_10], ax
0x180015b60  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015b64  lea     rax, [rbp+57h+arg_10]
0x180015b68  mov     r9d, 19h; unsigned int
0x180015b6e  or      r8d, 0FFFFFFFFh; int
0x180015b72  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180015b77  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015b7c  mov     r12d, eax
0x180015b7f  cmp     r14d, 3Ch ; '<'
0x180015b83  jnz     short loc_180015BE3
0x180015b85  lea     r14d, [rsi+rbx]
0x180015b89  xor     r8d, r8d; int
0x180015b8c  mov     edx, r14d; int
0x180015b8f  lea     rcx, [rsp+120h+var_E0]; this
0x180015b94  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015b99  mov     eax, 3Eh ; '>'
0x180015b9e  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015ba2  xor     r8d, r8d; int
0x180015ba5  mov     word ptr [rbp+57h+arg_10], ax
0x180015ba9  call    ?GetAngleBracket@CDetectURL@@AEAAJAEAVCTxtPtr@@J@Z; CDetectURL::GetAngleBracket(CTxtPtr &,long)
0x180015bae  test    eax, eax
0x180015bb0  jns     short loc_180015BE3
0x180015bb2  mov     r9d, 10h; unsigned int
0x180015bb8  lea     rax, [rbp+57h+arg_10]
0x180015bbc  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015bc0  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x180015bc5  lea     r8d, [r9-0Fh]; int
0x180015bc9  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015bce  mov     ecx, 3Eh ; '>'
0x180015bd3  cmp     word ptr [rbp+57h+arg_10], cx
0x180015bd7  jnz     short loc_180015BE3
0x180015bd9  lea     ebx, [rcx-3Dh]
0x180015bdc  mov     esi, r14d
0x180015bdf  sub     ebx, eax
0x180015be1  jmp     short loc_180015BEB
0x180015be3  add     esi, ebx
0x180015be5  sub     ebx, r12d
0x180015be8  sub     ebx, r15d
0x180015beb  mov     r14, [rbp+57h+arg_8]
0x180015bef  mov     r12d, [rbp+57h+arg_18]
0x180015bf3  mov     r8d, ebx; int
0x180015bf6  lea     rcx, [rsp+120h+var_E0]; this
0x180015bfb  mov     edx, esi; int
0x180015bfd  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015c02  xor     esi, esi
0x180015c04  cmp     [rbp+57h+var_88], esi
0x180015c07  jz      loc_180015E94
0x180015c0d  lea     rdx, [rsp+120h+var_E0]; struct CTxtRange *
0x180015c12  call    ?IsURL@CDetectURL@@AEAAHAEAVCTxtRange@@@Z; CDetectURL::IsURL(CTxtRange &)
0x180015c17  test    eax, eax
0x180015c19  jz      loc_180015CBD
0x180015c1f  lea     eax, [rsi+20h]
0x180015c22  mov     [rsp+120h+var_F8], 8000h; unsigned int
0x180015c2a  mov     r9, r14; struct IUndoBuilder *
0x180015c2d  mov     [rbp+57h+var_68], eax
0x180015c30  mov     r8d, 80000000h; unsigned int
0x180015c36  mov     dword ptr [rsp+120h+var_100], eax; unsigned int
0x180015c3a  lea     rdx, [rbp+57h+var_68]; struct CCharFormat *
0x180015c3e  mov     [rbp+57h+var_64], sil
0x180015c42  lea     rcx, [rsp+120h+var_E0]; this
0x180015c47  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180015c4c  mov     eax, [rbp+57h+var_B8]
0x180015c4f  mov     r14d, eax
0x180015c52  sub     r14d, [rbp+57h+var_88]
0x180015c56  cmp     eax, edi
0x180015c58  jle     short loc_180015C8C
0x180015c5a  mov     r8d, edi
0x180015c5d  lea     rcx, [rsp+120h+var_E0]; this
0x180015c62  sub     r8d, eax; int
0x180015c65  mov     edx, edi; int
0x180015c67  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015c6c  mov     r9, [rbp+57h+arg_8]; struct IUndoBuilder *
0x180015c70  lea     r8, [rsp+120h+var_F0]; int *
0x180015c75  mov     rcx, [rbp+57h+arg_0]; this
0x180015c79  lea     rdx, [rsp+120h+var_E0]; struct CTxtRange *
0x180015c7e  call    ?CheckAndCleanBogusURL@CDetectURL@@AEAAXAEAVCTxtRange@@AEAHPEAVIUndoBuilder@@@Z; CDetectURL::CheckAndCleanBogusURL(CTxtRange &,int &,IUndoBuilder *)
0x180015c83  or      r12d, [rsp+120h+var_F0]
0x180015c88  mov     [rbp+57h+arg_18], r12d
0x180015c8c  xor     r8d, r8d; int
0x180015c8f  lea     rcx, [rsp+120h+var_E0]; this
0x180015c94  mov     edx, r14d; int
0x180015c97  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015c9c  mov     eax, 1
0x180015ca1  mov     [rsp+120h+var_100], rsi; unsigned __int16 *
0x180015ca6  mov     r9d, eax; unsigned int
0x180015ca9  lea     rdx, [rbp+57h+var_C8]; struct CTxtPtr *
0x180015cad  mov     r8d, eax; int
0x180015cb0  call    ?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z; CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)
0x180015cb5  mov     r13d, eax
0x180015cb8  neg     r13d
0x180015cbb  jmp     short loc_180015CC3
0x180015cbd  sub     r13d, r15d
0x180015cc0  mov     r14d, edi
0x180015cc3  mov     [rbp+57h+arg_10], r13d
0x180015cc7  test    r13d, r13d
0x180015cca  jz      loc_180015E78
0x180015cd0  mov     r8d, r13d; int
0x180015cd3  lea     rcx, [rsp+120h+var_E0]; this
0x180015cd8  mov     edx, r14d; int
0x180015cdb  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180015ce0  mov     rsi, [rbp+57h+var_A8]
0x180015ce4  xor     r8d, r8d
0x180015ce7  mov     [rbp+57h+var_64], r8b
0x180015ceb  mov     r12d, r8d
0x180015cee  mov     [rsp+120h+var_F0], r8d
0x180015cf3  test    rsi, rsi
0x180015cf6  jz      loc_180015E58
0x180015cfc  mov     ecx, [rsi+8]
0x180015cff  test    ecx, ecx
0x180015d01  jz      loc_180015E58
0x180015d07  mov     edi, [rbp+57h+var_88]
0x180015d0a  mov     ebx, [rbp+57h+var_A0]
0x180015d0d  neg     edi
0x180015d0f  mov     r15d, [rbp+57h+var_9C]
0x180015d13  test    ecx, ecx
0x180015d15  jle     short loc_180015D32
0x180015d17  cmp     ebx, ecx
0x180015d19  jge     short loc_180015D32
0x180015d1b  cmp     [rsi], r8
0x180015d1e  jz      short loc_180015D32
0x180015d20  test    ebx, ebx
0x180015d22  js      short loc_180015D32
0x180015d24  mov     eax, ebx
0x180015d26  imul    eax, [rsi+10h]
0x180015d2a  movsxd  rdx, eax
0x180015d2d  add     rdx, [rsi]
0x180015d30  jmp     short loc_180015D35
0x180015d32  mov     rdx, r8
0x180015d35  cmp     [rdx], r15d
0x180015d38  jnz     short loc_180015D46
0x180015d3a  lea     eax, [rcx-1]
0x180015d3d  cmp     ebx, eax
0x180015d3f  jge     short loc_180015D46
0x180015d41  inc     ebx
0x180015d43  mov     r15d, r8d
0x180015d46  test    edi, edi
0x180015d48  jle     loc_180015E58
0x180015d4e  mov     r12, [rbp+57h+arg_0]
0x180015d52  mov     eax, [rsi+8]
0x180015d55  test    eax, eax
0x180015d57  jz      short loc_180015D89
0x180015d59  jle     short loc_180015D76
0x180015d5b  cmp     ebx, eax
0x180015d5d  jge     short loc_180015D76
0x180015d5f  cmp     [rsi], r8
0x180015d62  jz      short loc_180015D76
0x180015d64  test    ebx, ebx
0x180015d66  js      short loc_180015D76
0x180015d68  mov     eax, ebx
0x180015d6a  imul    eax, [rsi+10h]
0x180015d6e  movsxd  rcx, eax
0x180015d71  add     rcx, [rsi]
0x180015d74  jmp     short loc_180015D79
0x180015d76  mov     rcx, r8
0x180015d79  movzx   edx, word ptr [rcx+4]
0x180015d7d  mov     [rsp+120h+var_E8], r8
0x180015d82  test    dx, dx
0x180015d85  jns     short loc_180015D9A
0x180015d87  jmp     short loc_180015D8E
0x180015d89  mov     [rsp+120h+var_E8], r8
0x180015d8e  mov     rax, [r12+10h]
0x180015d93  movzx   edx, word ptr [rax+114h]
0x180015d9a  mov     rcx, cs:qword_1800A72D0
0x180015da1  lea     r8, [rsp+120h+var_E8]
0x180015da6  movsx   edx, dx
0x180015da9  mov     rax, [rcx]
0x180015dac  mov     rax, [rax+20h]
0x180015db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015db5  xor     r8d, r8d
0x180015db8  test    eax, eax
0x180015dba  jns     short loc_180015DCA
0x180015dbc  lea     rax, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x180015dc3  mov     [rsp+120h+var_E8], rax
0x180015dc8  jmp     short loc_180015DCF
0x180015dca  mov     rax, [rsp+120h+var_E8]
0x180015dcf  test    byte ptr [rax], 20h
0x180015dd2  jnz     short loc_180015E14
0x180015dd4  mov     edx, [rsi+8]
0x180015dd7  test    edx, edx
0x180015dd9  jle     short loc_180015DF6
0x180015ddb  cmp     ebx, edx
0x180015ddd  jge     short loc_180015DF6
0x180015ddf  cmp     [rsi], r8
0x180015de2  jz      short loc_180015DF6
0x180015de4  test    ebx, ebx
0x180015de6  js      short loc_180015DF6
0x180015de8  mov     eax, ebx
0x180015dea  imul    eax, [rsi+10h]
0x180015dee  movsxd  rcx, eax
0x180015df1  add     rcx, [rsi]
0x180015df4  jmp     short loc_180015DF9
0x180015df6  mov     rcx, r8
  ... truncated ...
```
