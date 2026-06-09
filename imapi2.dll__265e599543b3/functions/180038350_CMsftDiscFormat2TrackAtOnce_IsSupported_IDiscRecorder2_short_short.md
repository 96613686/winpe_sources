# CMsftDiscFormat2TrackAtOnce::IsSupported(IDiscRecorder2 *,short *,short)

- ea: `0x180038350`
- end: `0x1800389e3`
- name: `?IsSupported@CMsftDiscFormat2TrackAtOnce@@AEAAJPEAUIDiscRecorder2@@PEAFF@Z`
- size: `1683`
- prototype: `int(CMsftDiscFormat2TrackAtOnce *__hidden this, struct IDiscRecorder2 *, __int16 *, __int16)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180038330`
- `0x180038340`

## callees

- `0x180002fc8`
- `0x180007df8`
- `0x18000a5f0`
- `0x18000a86c`
- `0x1800140f4`
- `0x180016778`
- `0x180023790`
- `0x180038350`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180038684`
- `ole32!CoTaskMemFree` at `0x180038830`
- `ole32!CoTaskMemFree` at `0x180038684`
- `ole32!CoTaskMemFree` at `0x180038830`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::IsSupported(
        struct IDiscRecorder2Vtbl *this,
        struct IDiscRecorder2 *a2,
        unsigned __int8 *a3,
        __int16 a4)
{
  int v7; // ebx
  PVOID *v8; // rcx
  signed int IsRecorderSupported; // eax
  const struct _GUID *v10; // r8
  int v11; // eax
  __int16 v13; // si
  __int16 v14; // di
  __int16 v15; // r14
  PVOID *v16; // rcx
  int v17; // eax
  PVOID *v18; // rcx
  bool v19; // zf
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h]
  _QWORD v23[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IDiscRecorder2 v24; // [rsp+90h] [rbp+40h] BYREF
  struct IDiscRecorder2Ex *v25; // [rsp+98h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+50h] BYREF

  v24.lpVtbl = this;
  v25 = 0;
  v7 = 0;
  if ( a2 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 10, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147467261;
  }
  if ( !a3 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 348) & 4) != 0 && *((_BYTE *)v8 + 345) >= 3u )
      WPP_SF_(v8[42], 11, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    v7 = -2147467261;
LABEL_27:
    if ( v25 )
      ((void (__fastcall *)(struct IDiscRecorder2Ex *))v25->lpVtbl->Release)(v25);
    return (unsigned int)v7;
  }
  *(_WORD *)a3 = 0;
  if ( v7 < 0 )
    goto LABEL_25;
  LOBYTE(v24.lpVtbl) = 0;
  IsRecorderSupported = Imapi2Utility::IsRecorderSupported((Imapi2Utility *)a2, &v24, a3);
  v7 = IsRecorderSupported;
  if ( IsRecorderSupported < 0 || LOBYTE(v24.lpVtbl) )
  {
    if ( IsRecorderSupported >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, GUID *, struct IDiscRecorder2Ex **))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
              &v25);
      v7 = v11;
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            12,
            WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
            (unsigned int)v11);
        }
        goto LABEL_25;
      }
      pv = 0;
      LODWORD(v24.lpVtbl) = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, struct IDiscRecorder2 *))v25->lpVtbl->GetFeaturePage)(
             v25,
             45,
             0,
             &pv,
             &v24);
      if ( v7 == -1062600180 )
      {
        v7 = 0;
      }
      else if ( v7 == -1062600182 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 13, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
        }
        v15 = -1;
      }
      else if ( v7 >= 0 )
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 15, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, 45);
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        v13 = -1;
        if ( (*((_BYTE *)pv + 2) & 1) != 0 )
        {
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 348) & 4) != 0 && *((_BYTE *)v16 + 345) >= 4u )
            WPP_SF_d(v16[42], 16, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, 45);
          v14 = -1;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          14,
          WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
          (unsigned int)v7);
      }
      CoTaskMemFree(pv);
      if ( v7 < 0 )
        goto LABEL_25;
      if ( v15 )
      {
        pv = 0;
        LODWORD(v24.lpVtbl) = 0;
        v17 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, struct IDiscRecorder2 *))v25->lpVtbl->GetModePage)(
                v25,
                42,
                0,
                &pv,
                &v24);
        v7 = v17;
        if ( v17 != -1062600191 )
        {
          if ( v17 >= 0 )
          {
            if ( LODWORD(v24.lpVtbl) >= 6 )
            {
              if ( (*((_BYTE *)pv + 3) & 1) != 0 )
              {
                v18 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 4u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 42),
                    19,
                    WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
                    42);
                  v18 = (PVOID *)WPP_GLOBAL_Control;
                }
                v13 = -1;
                v14 = -1;
              }
              else
              {
                v18 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( (*((_BYTE *)pv + 3) & 2) != 0 )
              {
                if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 348) & 4) != 0 && *((_BYTE *)v18 + 345) >= 4u )
                  WPP_SF_d(v18[42], 20, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, 42);
                v13 = -1;
                v14 = -1;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 42),
                  18,
                  WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
                  LODWORD(v24.lpVtbl));
              }
              v7 = -2147467259;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              17,
              WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
              (unsigned int)v17);
          }
        }
        CoTaskMemFree(pv);
        if ( v7 < 0 )
          goto LABEL_25;
      }
      if ( v14 )
      {
        v19 = a4 == 0;
        if ( !a4 )
        {
LABEL_107:
          if ( !v19 )
            v13 = v14;
          *(_WORD *)a3 = v13;
          goto LABEL_27;
        }
        v14 = 0;
        v21 = 0;
        v22 = 0;
        v20 = CMsftDiscInformation::Init((CMsftDiscInformation *)&v21, v25);
        if ( v20 >= 0 )
        {
          if ( (*(_BYTE *)(v21 + 2) & 3) != 0 )
          {
            if ( (*(_BYTE *)(v21 + 2) & 3) == 1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 23, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 4u )
            {
              v23[0] = 0x7FFF;
              v23[1] = v21;
              if ( (unsigned int)v22 <= 0x7FFF )
                LOWORD(v23[0]) = v22;
              WPP_SF__HEX_(
                *((_QWORD *)WPP_GLOBAL_Control + 42),
                24,
                WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
                v23);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 22, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
            }
            v14 = -1;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            21,
            WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
            (unsigned int)v20);
        }
        CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v21);
      }
      v19 = a4 == 0;
      goto LABEL_107;
    }
LABEL_25:
    if ( v7 != -2147467261 )
      v7 = 1;
    goto LABEL_27;
  }
  *(_WORD *)a3 = 0;
  if ( (IsRecorderSupported & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(IsRecorderSupported, (int)&CLSID_MsftDiscFormat2TrackAtOnce, v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038350  mov     [rsp-38h+arg_18], rbx
0x180038355  mov     [rsp-38h+arg_0.lpVtbl], rcx
0x18003835a  push    rbp
0x18003835b  push    rsi
0x18003835c  push    rdi
0x18003835d  push    r12
0x18003835f  push    r13
0x180038361  push    r14
0x180038363  push    r15
0x180038365  mov     rbp, rsp
0x180038368  sub     rsp, 50h
0x18003836c  xor     r13d, r13d
0x18003836f  lea     r14, WPP_GLOBAL_Control
0x180038376  mov     [rbp+arg_8], r13
0x18003837a  movzx   r12d, r9w
0x18003837e  mov     r15, r8
0x180038381  mov     rdi, rdx
0x180038384  mov     ebx, r13d
0x180038387  mov     sil, 4
0x18003838a  test    rdx, rdx
0x18003838d  jnz     short loc_1800383D1
0x18003838f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038396  cmp     rcx, r14
0x180038399  jz      short loc_1800383CA
0x18003839b  test    [rcx+15Ch], sil
0x1800383a2  jz      short loc_1800383CA
0x1800383a4  cmp     byte ptr [rcx+159h], 3
0x1800383ab  jb      short loc_1800383CA
0x1800383ad  mov     rcx, [rcx+150h]
0x1800383b4  lea     edx, [rdi+0Ah]
0x1800383b7  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800383be  call    WPP_SF_
0x1800383c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383ca  mov     ebx, 80004003h
0x1800383cf  jmp     short loc_1800383D8
0x1800383d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383d8  test    r15, r15
0x1800383db  jnz     short loc_180038415
0x1800383dd  cmp     rcx, r14
0x1800383e0  jz      short loc_18003840B
0x1800383e2  test    [rcx+15Ch], sil
0x1800383e9  jz      short loc_18003840B
0x1800383eb  cmp     byte ptr [rcx+159h], 3
0x1800383f2  jb      short loc_18003840B
0x1800383f4  mov     rcx, [rcx+150h]
0x1800383fb  lea     edx, [r15+0Bh]
0x1800383ff  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038406  call    WPP_SF_
0x18003840b  mov     ebx, 80004003h
0x180038410  jmp     loc_1800384CF
0x180038415  mov     [r15], r13w
0x180038419  test    ebx, ebx
0x18003841b  js      loc_1800384C1
0x180038421  lea     rdx, [rbp+arg_0]; struct IDiscRecorder2 *
0x180038425  mov     byte ptr [rbp+arg_0.lpVtbl], r13b
0x180038429  mov     rcx, rdi; this
0x18003842c  call    ?IsRecorderSupported@Imapi2Utility@@YAJPEAUIDiscRecorder2@@PEAE@Z; Imapi2Utility::IsRecorderSupported(IDiscRecorder2 *,uchar *)
0x180038431  mov     ebx, eax
0x180038433  test    eax, eax
0x180038435  js      short loc_180038465
0x180038437  cmp     byte ptr [rbp+arg_0.lpVtbl], r13b
0x18003843b  jnz     short loc_180038465
0x18003843d  mov     ecx, eax
0x18003843f  mov     [r15], r13w
0x180038443  and     ecx, 80FF0000h
0x180038449  cmp     ecx, 80AA0000h
0x18003844f  jnz     loc_1800384E4
0x180038455  lea     rdx, CLSID_MsftDiscFormat2TrackAtOnce; int
0x18003845c  mov     ecx, eax; dwMessageId
0x18003845e  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180038463  jmp     short loc_1800384E4
0x180038465  test    ebx, ebx
0x180038467  js      short loc_1800384C1
0x180038469  mov     rax, [rdi]
0x18003846c  lea     r8, [rbp+arg_8]
0x180038470  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180038477  mov     rcx, rdi
0x18003847a  mov     rax, [rax]
0x18003847d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038482  mov     ebx, eax
0x180038484  test    eax, eax
0x180038486  jns     short loc_1800384FE
0x180038488  mov     rcx, cs:WPP_GLOBAL_Control
0x18003848f  cmp     rcx, r14
0x180038492  jz      short loc_1800384C1
0x180038494  test    [rcx+15Ch], sil
0x18003849b  jz      short loc_1800384C1
0x18003849d  cmp     byte ptr [rcx+159h], 3
0x1800384a4  jb      short loc_1800384C1
0x1800384a6  mov     rcx, [rcx+150h]
0x1800384ad  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800384b4  mov     edx, 0Ch
0x1800384b9  mov     r9d, eax
0x1800384bc  call    WPP_SF_d
0x1800384c1  cmp     ebx, 80004003h
0x1800384c7  mov     edi, 1
0x1800384cc  cmovnz  ebx, edi
0x1800384cf  mov     rcx, [rbp+arg_8]
0x1800384d3  test    rcx, rcx
0x1800384d6  jz      short loc_1800384E4
0x1800384d8  mov     rax, [rcx]
0x1800384db  mov     rax, [rax+10h]
0x1800384df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384e4  mov     eax, ebx
0x1800384e6  mov     rbx, [rsp+50h+arg_18]
0x1800384ee  add     rsp, 50h
0x1800384f2  pop     r15
0x1800384f4  pop     r14
0x1800384f6  pop     r13
0x1800384f8  pop     r12
0x1800384fa  pop     rdi
0x1800384fb  pop     rsi
0x1800384fc  pop     rbp
0x1800384fd  retn
0x1800384fe  mov     rcx, [rbp+arg_8]
0x180038502  lea     rdx, [rbp+arg_0]
0x180038506  mov     [rbp+pv], r13
0x18003850a  lea     r9, [rbp+pv]
0x18003850e  mov     dword ptr [rbp+arg_0.lpVtbl], r13d
0x180038512  xor     r8d, r8d
0x180038515  mov     [rsp+50h+var_30], rdx
0x18003851a  mov     esi, r13d
0x18003851d  mov     rax, [rcx]
0x180038520  mov     edi, r13d
0x180038523  mov     r14d, r13d
0x180038526  lea     edx, [r8+2Dh]
0x18003852a  mov     rax, [rax+60h]
0x18003852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038533  mov     ebx, eax
0x180038535  or      eax, 0FFFFFFFFh
0x180038538  cmp     ebx, 0C0AA020Ch
0x18003853e  jnz     short loc_180038548
0x180038540  mov     ebx, r13d
0x180038543  jmp     loc_180038680
0x180038548  cmp     ebx, 0C0AA020Ah
0x18003854e  jnz     short loc_180038596
0x180038550  mov     rcx, cs:WPP_GLOBAL_Control
0x180038557  lea     rax, WPP_GLOBAL_Control
0x18003855e  cmp     rcx, rax
0x180038561  jz      short loc_18003858D
0x180038563  test    byte ptr [rcx+15Ch], 4
0x18003856a  jz      short loc_18003858D
0x18003856c  cmp     byte ptr [rcx+159h], 3
0x180038573  jb      short loc_18003858D
0x180038575  mov     rcx, [rcx+150h]
0x18003857c  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038583  mov     edx, 0Dh
0x180038588  call    WPP_SF_
0x18003858d  or      r14d, 0FFFFFFFFh
0x180038591  jmp     loc_180038680
0x180038596  test    ebx, ebx
0x180038598  jns     short loc_1800385EB
0x18003859a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385a1  lea     rax, WPP_GLOBAL_Control
0x1800385a8  cmp     rcx, rax
0x1800385ab  jz      loc_180038680
0x1800385b1  test    byte ptr [rcx+15Ch], 4
0x1800385b8  jz      loc_180038680
0x1800385be  cmp     byte ptr [rcx+159h], 3
0x1800385c5  jb      loc_180038680
0x1800385cb  mov     rcx, [rcx+150h]
0x1800385d2  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800385d9  mov     edx, 0Eh
0x1800385de  mov     r9d, ebx
0x1800385e1  call    WPP_SF_d
0x1800385e6  jmp     loc_180038680
0x1800385eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385f2  lea     rdx, WPP_GLOBAL_Control
0x1800385f9  cmp     rcx, rdx
0x1800385fc  jz      short loc_18003863D
0x1800385fe  test    byte ptr [rcx+15Ch], 4
0x180038605  jz      short loc_18003863D
0x180038607  cmp     byte ptr [rcx+159h], 4
0x18003860e  jb      short loc_18003863D
0x180038610  mov     rcx, [rcx+150h]
0x180038617  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003861e  mov     edx, 0Fh
0x180038623  lea     r9d, [rdx+1Eh]
0x180038627  call    WPP_SF_d
0x18003862c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038633  lea     rdx, WPP_GLOBAL_Control
0x18003863a  or      eax, 0FFFFFFFFh
0x18003863d  movzx   esi, ax
0x180038640  mov     rax, [rbp+pv]
0x180038644  test    byte ptr [rax+2], 1
0x180038648  jz      short loc_180038680
0x18003864a  cmp     rcx, rdx
0x18003864d  jz      short loc_18003867D
0x18003864f  test    byte ptr [rcx+15Ch], 4
0x180038656  jz      short loc_18003867D
0x180038658  cmp     byte ptr [rcx+159h], 4
0x18003865f  jb      short loc_18003867D
0x180038661  mov     rcx, [rcx+150h]
0x180038668  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x18003866f  mov     edx, 10h
0x180038674  lea     r9d, [rdx+1Dh]
0x180038678  call    WPP_SF_d
0x18003867d  or      edi, 0FFFFFFFFh
0x180038680  mov     rcx, [rbp+pv]; pv
0x180038684  call    cs:__imp_CoTaskMemFree
0x18003868a  test    ebx, ebx
0x18003868c  js      loc_1800384C1
0x180038692  test    r14w, r14w
0x180038696  jz      loc_18003883E
0x18003869c  mov     rcx, [rbp+arg_8]
0x1800386a0  lea     rdx, [rbp+arg_0]
0x1800386a4  mov     [rbp+pv], r13
0x1800386a8  lea     r9, [rbp+pv]
0x1800386ac  mov     dword ptr [rbp+arg_0.lpVtbl], r13d
0x1800386b0  xor     r8d, r8d
0x1800386b3  mov     [rsp+50h+var_30], rdx
0x1800386b8  mov     rax, [rcx]
0x1800386bb  lea     edx, [r8+2Ah]
0x1800386bf  mov     rax, [rax+68h]
0x1800386c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386c8  mov     ebx, eax
0x1800386ca  cmp     eax, 0C0AA0201h
0x1800386cf  jz      loc_18003882C
0x1800386d5  test    eax, eax
0x1800386d7  jns     short loc_18003872A
0x1800386d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386e0  lea     r14, WPP_GLOBAL_Control
0x1800386e7  cmp     rcx, r14
0x1800386ea  jz      loc_18003882C
0x1800386f0  test    byte ptr [rcx+15Ch], 4
0x1800386f7  jz      loc_18003882C
0x1800386fd  cmp     byte ptr [rcx+159h], 3
0x180038704  jb      loc_18003882C
0x18003870a  mov     rcx, [rcx+150h]
0x180038711  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038718  mov     edx, 11h
0x18003871d  mov     r9d, eax
0x180038720  call    WPP_SF_d
0x180038725  jmp     loc_18003882C
0x18003872a  mov     r9d, dword ptr [rbp+arg_0.lpVtbl]
0x18003872e  cmp     r9d, 6
0x180038732  jnb     short loc_18003877B
0x180038734  mov     rcx, cs:WPP_GLOBAL_Control
0x18003873b  lea     rax, WPP_GLOBAL_Control
0x180038742  cmp     rcx, rax
0x180038745  jz      short loc_180038771
0x180038747  test    byte ptr [rcx+15Ch], 4
0x18003874e  jz      short loc_180038771
0x180038750  cmp     byte ptr [rcx+159h], 2
0x180038757  jb      short loc_180038771
0x180038759  mov     rcx, [rcx+150h]
0x180038760  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038767  mov     edx, 12h
0x18003876c  call    WPP_SF_d
0x180038771  mov     ebx, 80004005h
0x180038776  jmp     loc_18003882C
0x18003877b  mov     rax, [rbp+pv]
0x18003877f  test    byte ptr [rax+3], 1
0x180038783  jz      short loc_1800387D8
0x180038785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003878c  lea     r14, WPP_GLOBAL_Control
0x180038793  cmp     rcx, r14
0x180038796  jz      short loc_1800387CD
0x180038798  test    byte ptr [rcx+15Ch], 4
0x18003879f  jz      short loc_1800387CD
0x1800387a1  cmp     byte ptr [rcx+159h], 4
0x1800387a8  jb      short loc_1800387CD
0x1800387aa  mov     rcx, [rcx+150h]
0x1800387b1  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800387b8  mov     edx, 13h
0x1800387bd  lea     r9d, [rdx+17h]
0x1800387c1  call    WPP_SF_d
0x1800387c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387cd  or      eax, 0FFFFFFFFh
0x1800387d0  movzx   esi, ax
0x1800387d3  movzx   edi, ax
0x1800387d6  jmp     short loc_1800387E6
0x1800387d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387df  lea     r14, WPP_GLOBAL_Control
0x1800387e6  mov     rax, [rbp+pv]
0x1800387ea  test    byte ptr [rax+3], 2
0x1800387ee  jz      short loc_18003882C
0x1800387f0  cmp     rcx, r14
0x1800387f3  jz      short loc_180038823
0x1800387f5  test    byte ptr [rcx+15Ch], 4
0x1800387fc  jz      short loc_180038823
0x1800387fe  cmp     byte ptr [rcx+159h], 4
0x180038805  jb      short loc_180038823
0x180038807  mov     rcx, [rcx+150h]
0x18003880e  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180038815  mov     edx, 14h
0x18003881a  lea     r9d, [rdx+16h]
0x18003881e  call    WPP_SF_d
0x180038823  or      eax, 0FFFFFFFFh
0x180038826  movzx   esi, ax
0x180038829  movzx   edi, ax
0x18003882c  mov     rcx, [rbp+pv]; pv
0x180038830  call    cs:__imp_CoTaskMemFree
0x180038836  test    ebx, ebx
0x180038838  js      loc_1800384C1
0x18003883e  test    di, di
0x180038841  jz      loc_1800389D2
0x180038847  test    r12w, r12w
0x18003884b  jz      loc_1800389D6
0x180038851  mov     rdx, [rbp+arg_8]; struct IDiscRecorder2Ex *
  ... truncated ...
```
