# CAppExport::ExportMethodInfo(_GUID,_GUID,_GUID,__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort *,int,ulong)

- ea: `0x18004ba4c`
- end: `0x18004c260`
- name: `?ExportMethodInfo@CAppExport@@AEAAJU_GUID@@00W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAGHK@Z`
- size: `2068`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b534`

## callees

- `0x18001a6c8`
- `0x18004ba4c`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bb25`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bc8c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bdbe`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bec2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bb25`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bc8c`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bdbe`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004bec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bf8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bfa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bf8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bfa2`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportMethodInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int16 *a6,
        int a7,
        char a8)
{
  int SimpleTableDispenser; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  _QWORD *v19; // r14
  _QWORD *v20; // rsi
  unsigned int v21; // edi
  __int64 v22; // r8
  unsigned int v23; // edi
  __int64 v24; // r8
  signed __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  int v32; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v33; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  int v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 *v38; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+ACh] [rbp-54h]
  int v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B4h] [rbp-4Ch]
  _QWORD v43[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v44; // [rsp+D0h] [rbp-30h]
  int v45; // [rsp+D4h] [rbp-2Ch]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E4h] [rbp-1Ch]
  int v49; // [rsp+E8h] [rbp-18h]
  int v50; // [rsp+ECh] [rbp-14h]
  __int64 v51; // [rsp+F0h] [rbp-10h]
  int v52; // [rsp+F8h] [rbp-8h]
  int v53; // [rsp+FCh] [rbp-4h]
  int v54; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+104h] [rbp+4h]
  int *v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+110h] [rbp+10h]
  int v58; // [rsp+114h] [rbp+14h]
  int v59; // [rsp+118h] [rbp+18h]
  int v60; // [rsp+11Ch] [rbp+1Ch]
  _QWORD v61[2]; // [rsp+120h] [rbp+20h] BYREF
  int v62; // [rsp+130h] [rbp+30h]
  int v63; // [rsp+134h] [rbp+34h]
  __int64 v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+140h] [rbp+40h]
  int v66; // [rsp+144h] [rbp+44h]
  int v67; // [rsp+148h] [rbp+48h]
  int v68; // [rsp+14Ch] [rbp+4Ch]
  __int64 v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+158h] [rbp+58h]
  int v71; // [rsp+15Ch] [rbp+5Ch]
  int v72; // [rsp+160h] [rbp+60h]
  int v73; // [rsp+164h] [rbp+64h]
  int *v74; // [rsp+168h] [rbp+68h]
  int v75; // [rsp+170h] [rbp+70h]
  int v76; // [rsp+174h] [rbp+74h]
  int v77; // [rsp+178h] [rbp+78h]
  int v78; // [rsp+17Ch] [rbp+7Ch]

  v32 = a5;
  v29 = 0;
  v28 = 0;
  v44 = 72;
  v49 = 72;
  v54 = 72;
  v56 = &v32;
  v30 = 0;
  v43[0] = a2;
  v43[1] = 0;
  v45 = 16;
  v46 = a3;
  v47 = 0;
  v48 = 1;
  v50 = 16;
  v51 = a4;
  v52 = 0;
  v53 = 3;
  v55 = 16;
  v57 = 0;
  v58 = 5;
  v59 = 19;
  v60 = 4;
  v31 = 0;
  if ( *(_QWORD *)(a1 + 176) )
  {
LABEL_5:
    v13 = memcmp_0(&tidCOMSERVICES_CLASSITFMETHOD, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 176) + 24LL))(
                             *(_QWORD *)(a1 + 176),
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSITFMETHOD,
                             v43,
                             4,
                             1,
                             v13 != 0 ? 7 : 5,
                             &v31);
    goto LABEL_6;
  }
  v26 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v26, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  if ( !v31 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_72;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 32LL))(v31);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  v64 = a3;
  v62 = 72;
  v67 = 72;
  v69 = a4;
  v72 = 72;
  v61[0] = a2;
  v78 = 4;
  v61[1] = 0;
  v63 = 16;
  v65 = 0;
  v66 = 1;
  v68 = 16;
  v70 = 0;
  v71 = 3;
  v73 = 16;
  v74 = &v32;
  v75 = 0;
  v76 = 5;
  v77 = 19;
  v29 = 0;
  if ( !*(_QWORD *)(a1 + 176) )
  {
    v26 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_16;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v26, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v14 = memcmp_0(&tidCOMSERVICES_CLASSITFDISPID, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 176) + 24LL))(
                           *(_QWORD *)(a1 + 176),
                           didCOMSERVICES,
                           &tidCOMSERVICES_CLASSITFDISPID,
                           v61,
                           4,
                           1,
                           v14 != 0 ? 7 : 5,
                           &v29);
LABEL_16:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  if ( !v29 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 32LL))(v29);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  v33 = a6;
  v34 = 0;
  v35 = -268435455;
  v36 = 130;
  v15 = safe_lstrlenW(a6);
  v28 = 0;
  v37 = 2 * v15 + 2;
  if ( !*(_QWORD *)(a1 + 176) )
  {
    v26 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_26;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v26, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v16 = memcmp_0(tidCOMSERVICES_CLASSITFMETHOD_EXPORT, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 176) + 24LL))(
                           *(_QWORD *)(a1 + 176),
                           didCOMSERVICES,
                           tidCOMSERVICES_CLASSITFMETHOD_EXPORT,
                           &v33,
                           1,
                           1,
                           v16 != 0 ? 6 : 4,
                           &v28);
LABEL_26:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  if ( !v28 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  v38 = a6;
  v39 = 0;
  v40 = -268435455;
  v41 = 130;
  v17 = safe_lstrlenW(a6);
  v30 = 0;
  v42 = 2 * v17 + 2;
  if ( !*(_QWORD *)(a1 + 176) )
  {
    v26 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v26);
    if ( SimpleTableDispenser < 0 )
      goto LABEL_34;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 176), v26, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v18 = memcmp_0(tidCOMSERVICES_CLASSITFDISPID_EXPORT, &TID_APPLICATION, 0x10u);
  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 176) + 24LL))(
                           *(_QWORD *)(a1 + 176),
                           didCOMSERVICES,
                           tidCOMSERVICES_CLASSITFDISPID_EXPORT,
                           &v38,
                           1,
                           1,
                           v18 != 0 ? 6 : 4,
                           &v30);
LABEL_34:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_70;
  if ( !v30 )
  {
LABEL_18:
    SimpleTableDispenser = -2147024882;
    goto LABEL_70;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30);
  if ( SimpleTableDispenser >= 0 )
  {
    v19 = CoTaskMemAlloc(0x68u);
    if ( v19 )
    {
      v20 = CoTaskMemAlloc(0x38u);
      if ( v20 )
      {
        while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v31 + 40LL))(v31) != -2146367487 )
        {
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 120LL))(v28);
          if ( SimpleTableDispenser >= 0 )
          {
            v21 = 0;
            *v19 = 0;
            while ( v21 < 0xD )
            {
              v27 = 0;
              LODWORD(v26) = 0;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *, signed __int64 *, _QWORD *))(*(_QWORD *)v31 + 64LL))(
                                       v31,
                                       v21,
                                       &v27,
                                       &v26,
                                       &v19[v21]);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_68;
              if ( v19[v21] )
              {
                v22 = 0;
                if ( v27 == 128 )
                  v22 = (unsigned int)v26;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v28 + 160LL))(
                                         v28,
                                         v21,
                                         v22);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_68;
              }
              ++v21;
            }
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 144LL))(v28);
            if ( SimpleTableDispenser >= 0 )
              continue;
          }
          goto LABEL_68;
        }
        if ( a7 || (a8 & 0x80) == 0 )
        {
          while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v29 + 40LL))(v29) != -2146367487 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 120LL))(v30);
            if ( SimpleTableDispenser >= 0 )
            {
              v23 = 0;
              *v20 = 0;
              while ( v23 < 7 )
              {
                LODWORD(v26) = 0;
                v27 = 0;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)v29 + 64LL))(
                                         v29,
                                         v23,
                                         &v26,
                                         &v27,
                                         &v20[v23]);
                if ( SimpleTableDispenser < 0 )
                  goto LABEL_68;
                if ( v20[v23] )
                {
                  v24 = 0;
                  if ( (_DWORD)v26 == 128 )
                    v24 = v27;
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v30 + 160LL))(
                                           v30,
                                           v23,
                                           v24);
                  if ( SimpleTableDispenser < 0 )
                    goto LABEL_68;
                }
                ++v23;
              }
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 144LL))(v30);
              if ( SimpleTableDispenser >= 0 )
                continue;
            }
            goto LABEL_68;
          }
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
        if ( SimpleTableDispenser >= 0 )
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
      }
      else
      {
        SimpleTableDispenser = -2147024882;
      }
LABEL_68:
      *v19 = 0;
      CoTaskMemFree(v19);
      if ( v20 )
      {
        *v20 = 0;
        CoTaskMemFree(v20);
      }
      goto LABEL_70;
    }
    goto LABEL_18;
  }
LABEL_70:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
LABEL_72:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004ba4c  push    rbp
0x18004ba4e  push    rbx
0x18004ba4f  push    rsi
0x18004ba50  push    rdi
0x18004ba51  push    r12
0x18004ba53  push    r13
0x18004ba55  push    r14
0x18004ba57  push    r15
0x18004ba59  lea     rbp, [rsp-98h]
0x18004ba61  sub     rsp, 198h
0x18004ba68  mov     rax, cs:__security_cookie
0x18004ba6f  xor     rax, rsp
0x18004ba72  mov     [rbp+0D0h+var_50], rax
0x18004ba79  mov     eax, [rbp+0D0h+arg_20]
0x18004ba7f  xor     r12d, r12d
0x18004ba82  mov     rsi, r9
0x18004ba85  mov     [rbp+0D0h+var_150], eax
0x18004ba88  mov     r14, r8
0x18004ba8b  mov     r15, rdx
0x18004ba8e  mov     rdi, rcx
0x18004ba91  mov     [rsp+1D0h+var_168], r12
0x18004ba96  lea     eax, [r12+48h]
0x18004ba9b  mov     [rsp+1D0h+var_170], r12
0x18004baa0  lea     r13d, [r12+10h]
0x18004baa5  mov     [rbp+0D0h+var_100], eax
0x18004baa8  mov     [rbp+0D0h+var_E8], eax
0x18004baab  mov     [rbp+0D0h+var_D0], eax
0x18004baae  lea     rax, [rbp+0D0h+var_150]
0x18004bab2  mov     [rbp+0D0h+var_C8], rax
0x18004bab6  mov     [rsp+1D0h+var_160], r12
0x18004babb  mov     [rbp+0D0h+var_110], rdx
0x18004babf  mov     [rbp+0D0h+var_108], r12
0x18004bac3  mov     [rbp+0D0h+var_FC], r13d
0x18004bac7  mov     [rbp+0D0h+var_F8], r8
0x18004bacb  mov     [rbp+0D0h+var_F0], r12d
0x18004bacf  mov     [rbp+0D0h+var_EC], 1
0x18004bad6  mov     [rbp+0D0h+var_E4], r13d
0x18004bada  mov     [rbp+0D0h+var_E0], r9
0x18004bade  mov     [rbp+0D0h+var_D8], r12d
0x18004bae2  mov     [rbp+0D0h+var_D4], 3
0x18004bae9  mov     [rbp+0D0h+var_CC], r13d
0x18004baed  mov     [rbp+0D0h+var_C0], r12d
0x18004baf1  mov     [rbp+0D0h+var_BC], 5
0x18004baf8  mov     [rbp+0D0h+var_B8], 13h
0x18004baff  mov     [rbp+0D0h+var_B4], 4
0x18004bb06  mov     [rsp+1D0h+var_158], r12
0x18004bb0b  cmp     [rcx+0B0h], r12
0x18004bb12  jnz     short loc_18004BB58
0x18004bb14  lea     rdx, [rsp+1D0h+var_180]
0x18004bb19  mov     [rsp+1D0h+var_180], r12
0x18004bb1e  lea     rcx, IID_ISimpleTableDispenser
0x18004bb25  call    cs:__imp_GetSimpleTableDispenser
0x18004bb2b  mov     ebx, eax
0x18004bb2d  test    eax, eax
0x18004bb2f  js      loc_18004BBBE
0x18004bb35  mov     rcx, [rsp+1D0h+var_180]
0x18004bb3a  xor     eax, eax
0x18004bb3c  lock cmpxchg [rdi+0B0h], rcx
0x18004bb45  jz      short loc_18004BB58
0x18004bb47  mov     rcx, [rsp+1D0h+var_180]
0x18004bb4c  mov     rax, [rcx]
0x18004bb4f  mov     rax, [rax+10h]
0x18004bb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb58  mov     r8, r13; Size
0x18004bb5b  lea     rdx, TID_APPLICATION; Buf2
0x18004bb62  lea     rcx, tidCOMSERVICES_CLASSITFMETHOD; Buf1
0x18004bb69  call    memcmp_0
0x18004bb6e  mov     rcx, [rdi+0B0h]
0x18004bb75  lea     r9, [rsp+1D0h+var_158]
0x18004bb7a  mov     [rsp+1D0h+var_198], r9
0x18004bb7f  lea     r8, tidCOMSERVICES_CLASSITFMETHOD
0x18004bb86  neg     eax
0x18004bb88  lea     r9, [rbp+0D0h+var_110]
0x18004bb8c  mov     rax, [rcx]
0x18004bb8f  sbb     edx, edx
0x18004bb91  and     edx, 2
0x18004bb94  add     edx, 5
0x18004bb97  mov     [rsp+1D0h+var_1A0], edx
0x18004bb9b  lea     rdx, didCOMSERVICES
0x18004bba2  mov     rax, [rax+18h]
0x18004bba6  mov     [rsp+1D0h+var_1A8], 1
0x18004bbae  mov     [rsp+1D0h+var_1B0], 4
0x18004bbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbbc  mov     ebx, eax
0x18004bbbe  test    ebx, ebx
0x18004bbc0  js      loc_18004C1D4
0x18004bbc6  mov     rcx, [rsp+1D0h+var_158]
0x18004bbcb  test    rcx, rcx
0x18004bbce  jnz     short loc_18004BBDA
0x18004bbd0  mov     ebx, 8007000Eh
0x18004bbd5  jmp     loc_18004C1EF
0x18004bbda  mov     rax, [rcx]
0x18004bbdd  mov     rax, [rax+18h]
0x18004bbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbe6  mov     ebx, eax
0x18004bbe8  test    eax, eax
0x18004bbea  js      loc_18004C1D4
0x18004bbf0  mov     rcx, [rsp+1D0h+var_158]
0x18004bbf5  mov     rax, [rcx]
0x18004bbf8  mov     rax, [rax+20h]
0x18004bbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc01  mov     ebx, eax
0x18004bc03  test    eax, eax
0x18004bc05  js      loc_18004C1D4
0x18004bc0b  mov     eax, 48h ; 'H'
0x18004bc10  mov     [rbp+0D0h+var_98], r14
0x18004bc14  mov     [rbp+0D0h+var_A0], eax
0x18004bc17  mov     [rbp+0D0h+var_88], eax
0x18004bc1a  mov     [rbp+0D0h+var_80], rsi
0x18004bc1e  lea     r14d, [rax-47h]
0x18004bc22  mov     [rbp+0D0h+var_70], eax
0x18004bc25  lea     esi, [r14+3]
0x18004bc29  mov     [rbp+0D0h+var_B0], r15
0x18004bc2d  lea     rax, [rbp+0D0h+var_150]
0x18004bc31  mov     [rbp+0D0h+var_54], esi
0x18004bc34  mov     [rbp+0D0h+var_A8], r12
0x18004bc38  mov     [rbp+0D0h+var_9C], r13d
0x18004bc3c  mov     [rbp+0D0h+var_90], r12d
0x18004bc40  mov     [rbp+0D0h+var_8C], r14d
0x18004bc44  mov     [rbp+0D0h+var_84], r13d
0x18004bc48  mov     [rbp+0D0h+var_78], r12d
0x18004bc4c  mov     [rbp+0D0h+var_74], 3
0x18004bc53  mov     [rbp+0D0h+var_6C], r13d
0x18004bc57  mov     [rbp+0D0h+var_68], rax
0x18004bc5b  mov     [rbp+0D0h+var_60], r12d
0x18004bc5f  mov     [rbp+0D0h+var_5C], 5
0x18004bc66  mov     [rbp+0D0h+var_58], 13h
0x18004bc6d  mov     [rsp+1D0h+var_168], r12
0x18004bc72  cmp     [rdi+0B0h], r12
0x18004bc79  jnz     short loc_18004BCBF
0x18004bc7b  lea     rdx, [rsp+1D0h+var_180]
0x18004bc80  mov     [rsp+1D0h+var_180], r12
0x18004bc85  lea     rcx, IID_ISimpleTableDispenser
0x18004bc8c  call    cs:__imp_GetSimpleTableDispenser
0x18004bc92  mov     ebx, eax
0x18004bc94  test    eax, eax
0x18004bc96  js      loc_18004BD1E
0x18004bc9c  mov     rcx, [rsp+1D0h+var_180]
0x18004bca1  xor     eax, eax
0x18004bca3  lock cmpxchg [rdi+0B0h], rcx
0x18004bcac  jz      short loc_18004BCBF
0x18004bcae  mov     rcx, [rsp+1D0h+var_180]
0x18004bcb3  mov     rax, [rcx]
0x18004bcb6  mov     rax, [rax+10h]
0x18004bcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcbf  mov     r8, r13; Size
0x18004bcc2  lea     rdx, TID_APPLICATION; Buf2
0x18004bcc9  lea     rcx, tidCOMSERVICES_CLASSITFDISPID; Buf1
0x18004bcd0  call    memcmp_0
0x18004bcd5  mov     rcx, [rdi+0B0h]
0x18004bcdc  lea     r9, [rsp+1D0h+var_168]
0x18004bce1  mov     [rsp+1D0h+var_198], r9
0x18004bce6  lea     r8, tidCOMSERVICES_CLASSITFDISPID
0x18004bced  neg     eax
0x18004bcef  lea     r9, [rbp+0D0h+var_B0]
0x18004bcf3  mov     rax, [rcx]
0x18004bcf6  sbb     edx, edx
0x18004bcf8  and     edx, 2
0x18004bcfb  add     edx, 5
0x18004bcfe  mov     [rsp+1D0h+var_1A0], edx
0x18004bd02  lea     rdx, didCOMSERVICES
0x18004bd09  mov     rax, [rax+18h]
0x18004bd0d  mov     [rsp+1D0h+var_1A8], r14d
0x18004bd12  mov     [rsp+1D0h+var_1B0], rsi
0x18004bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd1c  mov     ebx, eax
0x18004bd1e  test    ebx, ebx
0x18004bd20  js      loc_18004C1D4
0x18004bd26  cmp     [rsp+1D0h+var_168], r12
0x18004bd2b  jnz     short loc_18004BD37
0x18004bd2d  mov     ebx, 8007000Eh
0x18004bd32  jmp     loc_18004C1D4
0x18004bd37  mov     rcx, [rsp+1D0h+var_168]
0x18004bd3c  mov     rax, [rcx]
0x18004bd3f  mov     rax, [rax+18h]
0x18004bd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd48  mov     ebx, eax
0x18004bd4a  test    eax, eax
0x18004bd4c  js      loc_18004C1D4
0x18004bd52  mov     rcx, [rsp+1D0h+var_168]
0x18004bd57  mov     rax, [rcx]
0x18004bd5a  mov     rax, [rax+20h]
0x18004bd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd63  mov     ebx, eax
0x18004bd65  test    eax, eax
0x18004bd67  js      loc_18004C1D4
0x18004bd6d  mov     rsi, [rbp+0D0h+arg_28]
0x18004bd74  mov     r15d, 0F0000001h
0x18004bd7a  mov     rcx, rsi; unsigned __int16 *
0x18004bd7d  mov     [rbp+0D0h+var_148], rsi
0x18004bd81  mov     [rbp+0D0h+var_140], r12d
0x18004bd85  mov     [rbp+0D0h+var_13C], r15d
0x18004bd89  mov     [rbp+0D0h+var_138], 82h
0x18004bd90  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004bd95  mov     [rsp+1D0h+var_170], r12
0x18004bd9a  lea     eax, ds:2[rax*2]
0x18004bda1  mov     [rbp+0D0h+var_134], eax
0x18004bda4  cmp     [rdi+0B0h], r12
0x18004bdab  jnz     short loc_18004BDF1
0x18004bdad  lea     rdx, [rsp+1D0h+var_180]
0x18004bdb2  mov     [rsp+1D0h+var_180], r12
0x18004bdb7  lea     rcx, IID_ISimpleTableDispenser
0x18004bdbe  call    cs:__imp_GetSimpleTableDispenser
0x18004bdc4  mov     ebx, eax
0x18004bdc6  test    eax, eax
0x18004bdc8  js      loc_18004BE50
0x18004bdce  mov     rcx, [rsp+1D0h+var_180]
0x18004bdd3  xor     eax, eax
0x18004bdd5  lock cmpxchg [rdi+0B0h], rcx
0x18004bdde  jz      short loc_18004BDF1
0x18004bde0  mov     rcx, [rsp+1D0h+var_180]
0x18004bde5  mov     rax, [rcx]
0x18004bde8  mov     rax, [rax+10h]
0x18004bdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdf1  mov     r8, r13; Size
0x18004bdf4  lea     rdx, TID_APPLICATION; Buf2
0x18004bdfb  lea     rcx, tidCOMSERVICES_CLASSITFMETHOD_EXPORT; Buf1
0x18004be02  call    memcmp_0
0x18004be07  mov     rcx, [rdi+0B0h]
0x18004be0e  lea     r9, [rsp+1D0h+var_170]
0x18004be13  mov     [rsp+1D0h+var_198], r9
0x18004be18  lea     r8, tidCOMSERVICES_CLASSITFMETHOD_EXPORT
0x18004be1f  neg     eax
0x18004be21  lea     r9, [rbp+0D0h+var_148]
0x18004be25  mov     rax, [rcx]
0x18004be28  sbb     edx, edx
0x18004be2a  and     edx, 2
0x18004be2d  add     edx, 4
0x18004be30  mov     [rsp+1D0h+var_1A0], edx
0x18004be34  lea     rdx, didCOMSERVICES
0x18004be3b  mov     rax, [rax+18h]
0x18004be3f  mov     [rsp+1D0h+var_1A8], r14d
0x18004be44  mov     [rsp+1D0h+var_1B0], r14
0x18004be49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be4e  mov     ebx, eax
0x18004be50  test    ebx, ebx
0x18004be52  js      loc_18004C1D4
0x18004be58  cmp     [rsp+1D0h+var_170], r12
0x18004be5d  jz      loc_18004BD2D
0x18004be63  mov     rcx, [rsp+1D0h+var_170]
0x18004be68  mov     rax, [rcx]
0x18004be6b  mov     rax, [rax+18h]
0x18004be6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be74  mov     ebx, eax
0x18004be76  test    eax, eax
0x18004be78  js      loc_18004C1D4
0x18004be7e  mov     rcx, rsi; unsigned __int16 *
0x18004be81  mov     [rbp+0D0h+var_130], rsi
0x18004be85  mov     [rbp+0D0h+var_128], r12d
0x18004be89  mov     [rbp+0D0h+var_124], r15d
0x18004be8d  mov     [rbp+0D0h+var_120], 82h
0x18004be94  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004be99  mov     [rsp+1D0h+var_160], r12
0x18004be9e  lea     eax, ds:2[rax*2]
0x18004bea5  mov     [rbp+0D0h+var_11C], eax
0x18004bea8  cmp     [rdi+0B0h], r12
0x18004beaf  jnz     short loc_18004BEF5
0x18004beb1  lea     rdx, [rsp+1D0h+var_180]
0x18004beb6  mov     [rsp+1D0h+var_180], r12
0x18004bebb  lea     rcx, IID_ISimpleTableDispenser
0x18004bec2  call    cs:__imp_GetSimpleTableDispenser
0x18004bec8  mov     ebx, eax
0x18004beca  test    eax, eax
0x18004becc  js      loc_18004BF58
0x18004bed2  mov     rcx, [rsp+1D0h+var_180]
0x18004bed7  xor     eax, eax
0x18004bed9  lock cmpxchg [rdi+0B0h], rcx
0x18004bee2  jz      short loc_18004BEF5
0x18004bee4  mov     rcx, [rsp+1D0h+var_180]
0x18004bee9  mov     rax, [rcx]
0x18004beec  mov     rax, [rax+10h]
0x18004bef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bef5  mov     r8, r13; Size
0x18004bef8  lea     rdx, TID_APPLICATION; Buf2
0x18004beff  lea     rcx, tidCOMSERVICES_CLASSITFDISPID_EXPORT; Buf1
0x18004bf06  call    memcmp_0
0x18004bf0b  mov     rcx, [rdi+0B0h]
0x18004bf12  lea     r10, [rsp+1D0h+var_160]
0x18004bf17  neg     eax
0x18004bf19  mov     [rsp+1D0h+var_198], r10
0x18004bf1e  lea     r8, tidCOMSERVICES_CLASSITFDISPID_EXPORT
0x18004bf25  sbb     r9d, r9d
0x18004bf28  lea     rdx, didCOMSERVICES
0x18004bf2f  mov     rax, [rcx]
0x18004bf32  and     r9d, 2
0x18004bf36  add     r9d, 4
0x18004bf3a  mov     [rsp+1D0h+var_1A0], r9d
0x18004bf3f  lea     r9, [rbp+0D0h+var_130]
0x18004bf43  mov     [rsp+1D0h+var_1A8], r14d
0x18004bf48  mov     rax, [rax+18h]
0x18004bf4c  mov     [rsp+1D0h+var_1B0], r14
0x18004bf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf56  mov     ebx, eax
0x18004bf58  test    ebx, ebx
0x18004bf5a  js      loc_18004C1D4
0x18004bf60  cmp     [rsp+1D0h+var_160], r12
0x18004bf65  jz      loc_18004BD2D
0x18004bf6b  mov     rcx, [rsp+1D0h+var_160]
0x18004bf70  mov     rax, [rcx]
0x18004bf73  mov     rax, [rax+18h]
  ... truncated ...
```
