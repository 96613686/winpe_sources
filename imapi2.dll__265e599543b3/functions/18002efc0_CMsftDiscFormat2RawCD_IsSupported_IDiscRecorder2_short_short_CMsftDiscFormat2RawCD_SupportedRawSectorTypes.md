# CMsftDiscFormat2RawCD::IsSupported(IDiscRecorder2 *,short *,short,CMsftDiscFormat2RawCD::SupportedRawSectorTypes *)

- ea: `0x18002efc0`
- end: `0x18002f535`
- name: `?IsSupported@CMsftDiscFormat2RawCD@@AEAAJPEAUIDiscRecorder2@@PEAFFPEAUSupportedRawSectorTypes@1@@Z`
- size: `1397`
- prototype: `int(CMsftDiscFormat2RawCD *__hidden this, struct IDiscRecorder2 *, __int16 *, __int16, struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002e840`
- `0x18002ea20`
- `0x18002f540`
- `0x180031ad0`
- `0x1800320b0`

## callees

- `0x180002fc8`
- `0x180007df8`
- `0x1800140f4`
- `0x180016778`
- `0x18002efc0`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002f2ed`
- `ole32!CoTaskMemFree` at `0x18002f512`
- `ole32!CoTaskMemFree` at `0x18002f2ed`
- `ole32!CoTaskMemFree` at `0x18002f512`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2RawCD::IsSupported(
        CMsftDiscFormat2RawCD *this,
        struct IDiscRecorder2 *a2,
        unsigned __int8 *a3,
        __int16 a4,
        struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes *a5)
{
  __int16 v5; // r12
  PVOID *v8; // rdx
  int v10; // ebx
  PVOID *v11; // rcx
  struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes *v12; // rdi
  signed int IsRecorderSupported; // eax
  const struct _GUID *v14; // r8
  __int16 v16; // r14
  __int16 v17; // r15
  _BYTE *v18; // r14
  PVOID *v19; // rcx
  __int64 v20; // [rsp+78h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+50h] BYREF
  __int16 v22; // [rsp+88h] [rbp+58h]

  v22 = a4;
  v5 = 0;
  v20 = 0;
  v8 = &WPP_GLOBAL_Control;
  v10 = 0;
  if ( a2 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 27, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v8 = &WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  if ( a3 )
  {
    *(_WORD *)a3 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 388) & 4) != 0 && *((_BYTE *)v11 + 385) >= 3u )
    {
      WPP_SF_(v11[47], 28, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v8 = &WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  v12 = a5;
  if ( !a5 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 388) & 4) != 0 && *((_BYTE *)v11 + 385) >= 3u )
      WPP_SF_(v11[47], (unsigned int)((_DWORD)a5 + 29), &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v10 = -2147467261;
    goto LABEL_34;
  }
  *(_QWORD *)a5 = 0;
  *((_DWORD *)v12 + 2) = 0;
  if ( v10 < 0
    || (LOBYTE(a5) = 0,
        *((_DWORD *)this + 73) = 0,
        IsRecorderSupported = Imapi2Utility::IsRecorderSupported((Imapi2Utility *)a2, (struct IDiscRecorder2 *)&a5, a3),
        v10 = IsRecorderSupported,
        IsRecorderSupported < 0)
    || (_BYTE)a5 )
  {
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
              &v20);
      if ( v10 >= 0 )
      {
        pv = 0;
        LODWORD(a5) = 0;
        v16 = -1;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *, struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes **))(*(_QWORD *)v20 + 96LL))(
                v20,
                0,
                0,
                &pv,
                &a5);
        if ( v10 < 0 )
        {
          if ( v10 == -1062600180 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 32, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
            }
            v10 = 0;
          }
          else
          {
            v16 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 47),
                33,
                &WPP_465922b870433540ecd6931719c7292a_Traceguids,
                (unsigned int)v10);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 31, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
          }
          v16 = 0;
        }
        CoTaskMemFree(pv);
        if ( v10 >= 0 )
        {
          v17 = 0;
          if ( v16 )
            goto LABEL_89;
          pv = 0;
          LODWORD(a5) = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, struct CMsftDiscFormat2RawCD::SupportedRawSectorTypes **))(*(_QWORD *)v20 + 96LL))(
                  v20,
                  46,
                  0,
                  &pv,
                  &a5);
          if ( v10 == -1062600180 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 34, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
            }
            v10 = -1062599937;
          }
          else if ( v10 == -1062600182 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 35, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
            }
            v10 = 0;
          }
          else if ( v10 >= 0 )
          {
            v18 = pv;
            if ( (*((_BYTE *)pv + 4) & 8) != 0 )
            {
              v17 = -1;
              *(_DWORD *)v12 = 1;
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 37, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( (v18[4] & 1) != 0 )
              {
                *((_DWORD *)v12 + 1) = 1;
                *((_DWORD *)v12 + 2) = 1;
                v19 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 38, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
                  v19 = (PVOID *)WPP_GLOBAL_Control;
                }
              }
              if ( (v18[2] & 1) != 0 )
              {
                if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 388) & 4) != 0 && *((_BYTE *)v19 + 385) >= 4u )
                  WPP_SF_(v19[47], 39, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
                v5 = -1;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 47),
              36,
              &WPP_465922b870433540ecd6931719c7292a_Traceguids,
              (unsigned int)v10);
          }
          CoTaskMemFree(pv);
          if ( v10 >= 0 )
          {
LABEL_89:
            if ( v22 )
              v17 = v5;
            *(_WORD *)a3 = v17;
            goto LABEL_34;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 47),
          30,
          &WPP_465922b870433540ecd6931719c7292a_Traceguids,
          (unsigned int)v10);
      }
    }
    if ( v10 != -2147467261 )
      v10 = 1;
LABEL_34:
    if ( v20 )
      (*(void (__fastcall **)(__int64, PVOID *))(*(_QWORD *)v20 + 16LL))(v20, v8);
    return (unsigned int)v10;
  }
  *((_DWORD *)this + 73) = 1;
  *(_WORD *)a3 = 0;
  if ( (IsRecorderSupported & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(IsRecorderSupported, (int)&CLSID_MsftDiscFormat2RawCD, v14);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002efc0  mov     [rsp-38h+arg_0], rbx
0x18002efc5  mov     [rsp-38h+arg_18], r9w
0x18002efcb  push    rbp
0x18002efcc  push    rsi
0x18002efcd  push    rdi
0x18002efce  push    r12
0x18002efd0  push    r13
0x18002efd2  push    r14
0x18002efd4  push    r15
0x18002efd6  mov     rbp, rsp
0x18002efd9  sub     rsp, 30h
0x18002efdd  xor     r12d, r12d
0x18002efe0  mov     r14, rdx
0x18002efe3  mov     [rbp+arg_8], r12
0x18002efe7  mov     r13, r8
0x18002efea  lea     rdx, WPP_GLOBAL_Control
0x18002eff1  mov     r15, rcx
0x18002eff4  mov     ebx, r12d
0x18002eff7  mov     sil, 4
0x18002effa  mov     edi, 80004003h
0x18002efff  test    r14, r14
0x18002f002  jnz     short loc_18002F04C
0x18002f004  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f00b  cmp     rcx, rdx
0x18002f00e  jz      short loc_18002F048
0x18002f010  test    [rcx+184h], sil
0x18002f017  jz      short loc_18002F048
0x18002f019  cmp     byte ptr [rcx+181h], 3
0x18002f020  jb      short loc_18002F048
0x18002f022  mov     rcx, [rcx+178h]
0x18002f029  lea     edx, [r12+1Bh]
0x18002f02e  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f035  call    WPP_SF_
0x18002f03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f041  lea     rdx, WPP_GLOBAL_Control
0x18002f048  mov     ebx, edi
0x18002f04a  jmp     short loc_18002F053
0x18002f04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f053  test    r13, r13
0x18002f056  jnz     short loc_18002F098
0x18002f058  cmp     rcx, rdx
0x18002f05b  jz      short loc_18002F094
0x18002f05d  test    [rcx+184h], sil
0x18002f064  jz      short loc_18002F094
0x18002f066  cmp     byte ptr [rcx+181h], 3
0x18002f06d  jb      short loc_18002F094
0x18002f06f  mov     rcx, [rcx+178h]
0x18002f076  lea     edx, [r13+1Ch]
0x18002f07a  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f081  call    WPP_SF_
0x18002f086  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f08d  lea     rdx, WPP_GLOBAL_Control
0x18002f094  mov     ebx, edi
0x18002f096  jmp     short loc_18002F0A4
0x18002f098  mov     [r13+0], r12w
0x18002f09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0a4  mov     rdi, [rbp+arg_20.lpVtbl]
0x18002f0a8  test    rdi, rdi
0x18002f0ab  jnz     short loc_18002F0E4
0x18002f0ad  cmp     rcx, rdx
0x18002f0b0  jz      short loc_18002F0DA
0x18002f0b2  test    [rcx+184h], sil
0x18002f0b9  jz      short loc_18002F0DA
0x18002f0bb  cmp     byte ptr [rcx+181h], 3
0x18002f0c2  jb      short loc_18002F0DA
0x18002f0c4  mov     rcx, [rcx+178h]
0x18002f0cb  lea     edx, [rdi+1Dh]
0x18002f0ce  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f0d5  call    WPP_SF_
0x18002f0da  mov     ebx, 80004003h
0x18002f0df  jmp     loc_18002F1B8
0x18002f0e4  mov     [rdi], r12
0x18002f0e7  mov     [rdi+8], r12d
0x18002f0eb  test    ebx, ebx
0x18002f0ed  js      short loc_18002F149
0x18002f0ef  lea     rdx, [rbp+arg_20]; struct IDiscRecorder2 *
0x18002f0f3  mov     byte ptr [rbp+arg_20.lpVtbl], r12b
0x18002f0f7  mov     rcx, r14; this
0x18002f0fa  mov     [r15+124h], r12d
0x18002f101  call    ?IsRecorderSupported@Imapi2Utility@@YAJPEAUIDiscRecorder2@@PEAE@Z; Imapi2Utility::IsRecorderSupported(IDiscRecorder2 *,uchar *)
0x18002f106  mov     ebx, eax
0x18002f108  test    eax, eax
0x18002f10a  js      short loc_18002F149
0x18002f10c  cmp     byte ptr [rbp+arg_20.lpVtbl], r12b
0x18002f110  jnz     short loc_18002F149
0x18002f112  mov     ecx, eax
0x18002f114  mov     dword ptr [r15+124h], 1
0x18002f11f  and     ecx, 80FF0000h
0x18002f125  mov     [r13+0], r12w
0x18002f12a  cmp     ecx, 80AA0000h
0x18002f130  jnz     loc_18002F1CD
0x18002f136  lea     rdx, CLSID_MsftDiscFormat2RawCD; int
0x18002f13d  mov     ecx, eax; dwMessageId
0x18002f13f  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002f144  jmp     loc_18002F1CD
0x18002f149  mov     esi, 1
0x18002f14e  test    ebx, ebx
0x18002f150  js      short loc_18002F1AF
0x18002f152  mov     rax, [r14]
0x18002f155  lea     r8, [rbp+arg_8]
0x18002f159  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x18002f160  mov     rcx, r14
0x18002f163  mov     rax, [rax]
0x18002f166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f16b  mov     ebx, eax
0x18002f16d  test    eax, eax
0x18002f16f  jns     short loc_18002F1E4
0x18002f171  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f178  lea     rax, WPP_GLOBAL_Control
0x18002f17f  cmp     rcx, rax
0x18002f182  jz      short loc_18002F1AF
0x18002f184  test    byte ptr [rcx+184h], 4
0x18002f18b  jz      short loc_18002F1AF
0x18002f18d  cmp     byte ptr [rcx+181h], 3
0x18002f194  jb      short loc_18002F1AF
0x18002f196  mov     rcx, [rcx+178h]
0x18002f19d  lea     edx, [rsi+1Dh]
0x18002f1a0  mov     r9d, ebx
0x18002f1a3  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f1aa  call    WPP_SF_d
0x18002f1af  cmp     ebx, 80004003h
0x18002f1b5  cmovnz  ebx, esi
0x18002f1b8  mov     rcx, [rbp+arg_8]
0x18002f1bc  test    rcx, rcx
0x18002f1bf  jz      short loc_18002F1CD
0x18002f1c1  mov     rax, [rcx]
0x18002f1c4  mov     rax, [rax+10h]
0x18002f1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1cd  mov     eax, ebx
0x18002f1cf  mov     rbx, [rsp+30h+arg_0]
0x18002f1d4  add     rsp, 30h
0x18002f1d8  pop     r15
0x18002f1da  pop     r14
0x18002f1dc  pop     r13
0x18002f1de  pop     r12
0x18002f1e0  pop     rdi
0x18002f1e1  pop     rsi
0x18002f1e2  pop     rbp
0x18002f1e3  retn
0x18002f1e4  mov     rcx, [rbp+arg_8]
0x18002f1e8  lea     rdx, [rbp+arg_20]
0x18002f1ec  mov     [rbp+pv], r12
0x18002f1f0  lea     r9, [rbp+pv]
0x18002f1f4  mov     dword ptr [rbp+arg_20.lpVtbl], r12d
0x18002f1f8  xor     r8d, r8d
0x18002f1fb  mov     [rsp+30h+var_10], rdx
0x18002f200  xor     edx, edx
0x18002f202  mov     rax, [rcx]
0x18002f205  mov     rax, [rax+60h]
0x18002f209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f20e  or      r14d, 0FFFFFFFFh
0x18002f212  mov     ebx, eax
0x18002f214  test    eax, eax
0x18002f216  js      short loc_18002F25C
0x18002f218  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f21f  lea     rax, WPP_GLOBAL_Control
0x18002f226  cmp     rcx, rax
0x18002f229  jz      short loc_18002F254
0x18002f22b  test    byte ptr [rcx+184h], 4
0x18002f232  jz      short loc_18002F254
0x18002f234  cmp     byte ptr [rcx+181h], 4
0x18002f23b  jb      short loc_18002F254
0x18002f23d  mov     rcx, [rcx+178h]
0x18002f244  lea     edx, [r14+20h]
0x18002f248  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f24f  call    WPP_SF_
0x18002f254  mov     r14d, r12d
0x18002f257  jmp     loc_18002F2E9
0x18002f25c  cmp     ebx, 0C0AA020Ch
0x18002f262  jnz     short loc_18002F2A6
0x18002f264  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f26b  lea     rax, WPP_GLOBAL_Control
0x18002f272  cmp     rcx, rax
0x18002f275  jz      short loc_18002F2A1
0x18002f277  test    byte ptr [rcx+184h], 4
0x18002f27e  jz      short loc_18002F2A1
0x18002f280  cmp     byte ptr [rcx+181h], 4
0x18002f287  jb      short loc_18002F2A1
0x18002f289  mov     rcx, [rcx+178h]
0x18002f290  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f297  mov     edx, 20h ; ' '
0x18002f29c  call    WPP_SF_
0x18002f2a1  mov     ebx, r12d
0x18002f2a4  jmp     short loc_18002F2E9
0x18002f2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2ad  lea     rax, WPP_GLOBAL_Control
0x18002f2b4  mov     r14d, r12d
0x18002f2b7  cmp     rcx, rax
0x18002f2ba  jz      short loc_18002F2E9
0x18002f2bc  test    byte ptr [rcx+184h], 4
0x18002f2c3  jz      short loc_18002F2E9
0x18002f2c5  cmp     byte ptr [rcx+181h], 3
0x18002f2cc  jb      short loc_18002F2E9
0x18002f2ce  mov     rcx, [rcx+178h]
0x18002f2d5  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f2dc  mov     edx, 21h ; '!'
0x18002f2e1  mov     r9d, ebx
0x18002f2e4  call    WPP_SF_d
0x18002f2e9  mov     rcx, [rbp+pv]; pv
0x18002f2ed  call    cs:__imp_CoTaskMemFree
0x18002f2f3  test    ebx, ebx
0x18002f2f5  js      loc_18002F1AF
0x18002f2fb  xor     ecx, ecx
0x18002f2fd  mov     r15d, r12d
0x18002f300  test    r14w, r14w
0x18002f304  jnz     loc_18002F522
0x18002f30a  mov     [rbp+pv], rcx
0x18002f30e  lea     rdx, [rbp+arg_20]
0x18002f312  mov     dword ptr [rbp+arg_20.lpVtbl], ecx
0x18002f315  lea     r9, [rbp+pv]
0x18002f319  mov     rcx, [rbp+arg_8]
0x18002f31d  xor     r8d, r8d
0x18002f320  mov     [rsp+30h+var_10], rdx
0x18002f325  mov     rax, [rcx]
0x18002f328  lea     edx, [r8+2Eh]
0x18002f32c  mov     rax, [rax+60h]
0x18002f330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f335  mov     ebx, eax
0x18002f337  cmp     eax, 0C0AA020Ch
0x18002f33c  jnz     short loc_18002F385
0x18002f33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f345  lea     rax, WPP_GLOBAL_Control
0x18002f34c  cmp     rcx, rax
0x18002f34f  jz      short loc_18002F37B
0x18002f351  test    byte ptr [rcx+184h], 4
0x18002f358  jz      short loc_18002F37B
0x18002f35a  cmp     byte ptr [rcx+181h], 3
0x18002f361  jb      short loc_18002F37B
0x18002f363  mov     rcx, [rcx+178h]
0x18002f36a  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f371  mov     edx, 22h ; '"'
0x18002f376  call    WPP_SF_
0x18002f37b  mov     ebx, 0C0AA02FFh
0x18002f380  jmp     loc_18002F50E
0x18002f385  cmp     ebx, 0C0AA020Ah
0x18002f38b  jnz     short loc_18002F3D1
0x18002f38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f394  lea     rax, WPP_GLOBAL_Control
0x18002f39b  cmp     rcx, rax
0x18002f39e  jz      short loc_18002F3CA
0x18002f3a0  test    byte ptr [rcx+184h], 4
0x18002f3a7  jz      short loc_18002F3CA
0x18002f3a9  cmp     byte ptr [rcx+181h], 3
0x18002f3b0  jb      short loc_18002F3CA
0x18002f3b2  mov     rcx, [rcx+178h]
0x18002f3b9  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f3c0  mov     edx, 23h ; '#'
0x18002f3c5  call    WPP_SF_
0x18002f3ca  xor     ebx, ebx
0x18002f3cc  jmp     loc_18002F50E
0x18002f3d1  test    ebx, ebx
0x18002f3d3  jns     short loc_18002F426
0x18002f3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3dc  lea     rax, WPP_GLOBAL_Control
0x18002f3e3  cmp     rcx, rax
0x18002f3e6  jz      loc_18002F50E
0x18002f3ec  test    byte ptr [rcx+184h], 4
0x18002f3f3  jz      loc_18002F50E
0x18002f3f9  cmp     byte ptr [rcx+181h], 3
0x18002f400  jb      loc_18002F50E
0x18002f406  mov     rcx, [rcx+178h]
0x18002f40d  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f414  mov     edx, 24h ; '$'
0x18002f419  mov     r9d, ebx
0x18002f41c  call    WPP_SF_d
0x18002f421  jmp     loc_18002F50E
0x18002f426  mov     r14, [rbp+pv]
0x18002f42a  test    byte ptr [r14+4], 8
0x18002f42f  jz      loc_18002F50E
0x18002f435  or      r15d, 0FFFFFFFFh
0x18002f439  mov     [rdi], esi
0x18002f43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f442  lea     rax, WPP_GLOBAL_Control
0x18002f449  cmp     rcx, rax
0x18002f44c  jz      short loc_18002F485
0x18002f44e  test    byte ptr [rcx+184h], 4
0x18002f455  jz      short loc_18002F485
0x18002f457  cmp     byte ptr [rcx+181h], 4
0x18002f45e  jb      short loc_18002F485
0x18002f460  mov     rcx, [rcx+178h]
0x18002f467  lea     edx, [r15+26h]
0x18002f46b  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f472  call    WPP_SF_
0x18002f477  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f47e  lea     rax, WPP_GLOBAL_Control
0x18002f485  test    [r14+4], sil
0x18002f489  jz      short loc_18002F4CE
0x18002f48b  mov     [rdi+4], esi
0x18002f48e  mov     [rdi+8], esi
0x18002f491  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f498  cmp     rcx, rax
0x18002f49b  jz      short loc_18002F4CE
0x18002f49d  test    byte ptr [rcx+184h], 4
0x18002f4a4  jz      short loc_18002F4CE
0x18002f4a6  cmp     byte ptr [rcx+181h], 4
0x18002f4ad  jb      short loc_18002F4CE
0x18002f4af  mov     rcx, [rcx+178h]
0x18002f4b6  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18002f4bd  mov     edx, 26h ; '&'
0x18002f4c2  call    WPP_SF_
  ... truncated ...
```
