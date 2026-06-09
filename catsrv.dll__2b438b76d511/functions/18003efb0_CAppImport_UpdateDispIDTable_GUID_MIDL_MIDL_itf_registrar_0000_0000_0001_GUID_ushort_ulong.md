# CAppImport::UpdateDispIDTable(_GUID,__MIDL___MIDL_itf_registrar_0000_0000_0001,_GUID,ushort *,ulong)

- ea: `0x18003efb0`
- end: `0x18003f530`
- name: `?UpdateDispIDTable@CAppImport@@AEAAJU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@0PEAGK@Z`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003f538`

## callees

- `0x18001a6c8`
- `0x18003efb0`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f08e`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f207`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f08e`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f2c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f2c8`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateDispIDTable(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned __int16 *a5,
        int a6)
{
  __int64 v8; // r14
  __int64 v9; // r9
  int SimpleTableDispenser; // ebx
  int v11; // eax
  __int64 v12; // r12
  _QWORD *v13; // rsi
  int v14; // eax
  int v15; // eax
  int v16; // r14d
  unsigned int v17; // edi
  __int64 v18; // r8
  signed __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v27; // [rsp+90h] [rbp-70h] BYREF
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+BCh] [rbp-44h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+CCh] [rbp-34h]
  int v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+D4h] [rbp-2Ch]
  int *v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E4h] [rbp-1Ch]
  int v44; // [rsp+E8h] [rbp-18h]
  int v45; // [rsp+ECh] [rbp-14h]
  _QWORD v46[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v47; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+104h] [rbp+4h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  int v50; // [rsp+110h] [rbp+10h]
  int v51; // [rsp+114h] [rbp+14h]
  int v52; // [rsp+118h] [rbp+18h]
  int v53; // [rsp+11Ch] [rbp+1Ch]
  GUID *v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+128h] [rbp+28h]
  int v56; // [rsp+12Ch] [rbp+2Ch]
  int v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+134h] [rbp+34h]
  __int64 v59; // [rsp+138h] [rbp+38h]
  int v60; // [rsp+140h] [rbp+40h]
  int v61; // [rsp+144h] [rbp+44h]
  int v62; // [rsp+148h] [rbp+48h]
  int v63; // [rsp+14Ch] [rbp+4Ch]
  int *v64; // [rsp+150h] [rbp+50h]
  int v65; // [rsp+158h] [rbp+58h]
  int v66; // [rsp+15Ch] [rbp+5Ch]
  int v67; // [rsp+160h] [rbp+60h]
  int v68; // [rsp+164h] [rbp+64h]
  __int128 v69; // [rsp+170h] [rbp+70h] BYREF
  __int128 v70; // [rsp+180h] [rbp+80h]
  __int128 v71; // [rsp+190h] [rbp+90h]

  v26 = a2;
  v21 = 0;
  v27 = a5;
  v8 = a2;
  v24 = a3;
  v28 = 0;
  v29 = -268435455;
  v30 = 130;
  v32 = a2;
  v33 = 0;
  v34 = 72;
  v35 = 16;
  v31 = 2 * safe_lstrlenW(a5) + 2;
  v41 = &v24;
  v36 = v9;
  v37 = 0;
  v38 = 3;
  v39 = 72;
  v40 = 16;
  v42 = 0;
  v43 = 5;
  v44 = 19;
  v45 = 4;
  v23 = 0;
  if ( *(_QWORD *)(a1 + 72) )
  {
LABEL_5:
    v11 = memcmp_0(tidCOMSERVICES_CLASSITFDISPID_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSITFDISPID_EXPORT,
                             &v27,
                             4,
                             1,
                             v11 != 0 ? 7 : 5,
                             &v23);
    goto LABEL_6;
  }
  v20 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v20);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v20, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser )
    goto LABEL_46;
  if ( !v23 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_48;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
  if ( SimpleTableDispenser )
    goto LABEL_46;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
  if ( SimpleTableDispenser )
    goto LABEL_46;
  v47 = 72;
  v12 = a1 + 96;
  v52 = 72;
  v57 = 72;
  v62 = 72;
  v48 = 16;
  v53 = 16;
  v58 = 16;
  v63 = 16;
  v64 = &v24;
  v46[0] = v8;
  v46[1] = 0;
  v49 = a1 + 96;
  v50 = 0;
  v51 = 1;
  v54 = &g_guidAppIdForQuery;
  v55 = 0;
  v56 = 2;
  v59 = a4;
  v60 = 0;
  v61 = 3;
  v65 = 0;
  v66 = 5;
  v67 = 19;
  v68 = 4;
  v21 = 0;
  if ( *(_QWORD *)(a1 + 72) )
    goto LABEL_15;
  v20 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v20);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v20, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_15:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSITFDISPID,
                             v46,
                             5,
                             1,
                             8388612,
                             &v21);
  }
  if ( SimpleTableDispenser )
    goto LABEL_46;
  if ( !v21 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
  if ( !SimpleTableDispenser )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 32LL))(v21);
    if ( !SimpleTableDispenser )
    {
      v13 = CoTaskMemAlloc(0x38u);
      if ( v13 )
      {
        while ( 1 )
        {
          v22 = 0;
          LODWORD(v20) = 0;
          v69 = 0;
          v25 = 0;
          v70 = 0;
          v71 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
          SimpleTableDispenser = v14;
          if ( v14 == -2146367487 )
            break;
          if ( v14 )
            goto LABEL_45;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, signed __int64 *, __int64 *))(*(_QWORD *)v23 + 64LL))(
                                   v23,
                                   4,
                                   &v22,
                                   &v20,
                                   &v25);
          if ( SimpleTableDispenser )
            goto LABEL_45;
          *(_QWORD *)&v70 = &g_guidAppIdForQuery;
          *(_QWORD *)&v71 = v25;
          *((_QWORD *)&v71 + 1) = &v24;
          *(_QWORD *)&v69 = v8;
          *((_QWORD *)&v69 + 1) = v12;
          *((_QWORD *)&v70 + 1) = a4;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v21 + 56LL))(v21, 0, &v69);
          if ( a6 && v15 == -2146367487 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 120LL))(v21);
            if ( SimpleTableDispenser )
              goto LABEL_45;
            v16 = 1;
          }
          else
          {
            if ( v15 )
            {
              SimpleTableDispenser = -2146368488;
              goto LABEL_45;
            }
            v16 = 0;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 128LL))(v21);
            if ( SimpleTableDispenser )
              goto LABEL_45;
          }
          v17 = 0;
          *v13 = 0;
          while ( v17 < 7 )
          {
            v22 = 0;
            LODWORD(v20) = 0;
            if ( v16 || v17 >= 6 )
            {
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, signed __int64 *, _QWORD *))(*(_QWORD *)v23 + 64LL))(
                                       v23,
                                       v17,
                                       &v22,
                                       &v20,
                                       &v13[v17]);
              if ( SimpleTableDispenser )
                goto LABEL_45;
              if ( v13[v17] )
              {
                v18 = 0;
                if ( v22 == 128 )
                  v18 = (unsigned int)v20;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 160LL))(
                                         v21,
                                         v17,
                                         v18);
                if ( SimpleTableDispenser )
                  goto LABEL_45;
              }
            }
            ++v17;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 144LL))(v21);
          if ( SimpleTableDispenser )
            goto LABEL_45;
          v8 = v26;
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
LABEL_45:
        *v13 = 0;
        CoTaskMemFree(v13);
        goto LABEL_46;
      }
LABEL_18:
      SimpleTableDispenser = -2147024882;
    }
  }
LABEL_46:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
LABEL_48:
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18003efb0  push    rbp
0x18003efb2  push    rbx
0x18003efb3  push    rsi
0x18003efb4  push    rdi
0x18003efb5  push    r12
0x18003efb7  push    r13
0x18003efb9  push    r14
0x18003efbb  push    r15
0x18003efbd  lea     rbp, [rsp-0B8h]
0x18003efc5  sub     rsp, 1B8h
0x18003efcc  mov     rax, cs:__security_cookie
0x18003efd3  xor     rax, rsp
0x18003efd6  mov     [rbp+0F0h+var_50], rax
0x18003efdd  xor     r15d, r15d
0x18003efe0  mov     [rbp+0F0h+var_170], rdx
0x18003efe4  mov     rdi, rcx
0x18003efe7  mov     [rsp+1F0h+var_198], r15
0x18003efec  mov     rcx, [rbp+0F0h+arg_20]; unsigned __int16 *
0x18003eff3  mov     r13, r9
0x18003eff6  mov     [rbp+0F0h+var_160], rcx
0x18003effa  mov     r14, rdx
0x18003effd  mov     [rsp+1F0h+var_180], r8d
0x18003f002  mov     [rbp+0F0h+var_158], r15d
0x18003f006  mov     [rbp+0F0h+var_154], 0F0000001h
0x18003f00d  mov     [rbp+0F0h+var_150], 82h
0x18003f014  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003f019  lea     r12d, [r15+48h]
0x18003f01d  mov     [rbp+0F0h+var_148], r14
0x18003f021  lea     esi, [r15+10h]
0x18003f025  mov     [rbp+0F0h+var_140], r15
0x18003f029  mov     [rbp+0F0h+var_138], r12d
0x18003f02d  lea     eax, ds:2[rax*2]
0x18003f034  mov     [rbp+0F0h+var_134], esi
0x18003f037  mov     [rbp+0F0h+var_14C], eax
0x18003f03a  lea     rax, [rsp+1F0h+var_180]
0x18003f03f  mov     [rbp+0F0h+var_118], rax
0x18003f043  mov     [rbp+0F0h+var_130], r9
0x18003f047  mov     [rbp+0F0h+var_128], r15d
0x18003f04b  mov     [rbp+0F0h+var_124], 3
0x18003f052  mov     [rbp+0F0h+var_120], r12d
0x18003f056  mov     [rbp+0F0h+var_11C], esi
0x18003f059  mov     [rbp+0F0h+var_110], r15d
0x18003f05d  mov     [rbp+0F0h+var_10C], 5
0x18003f064  mov     [rbp+0F0h+var_108], 13h
0x18003f06b  mov     [rbp+0F0h+var_104], 4
0x18003f072  mov     [rsp+1F0h+var_188], r15
0x18003f077  cmp     [rdi+48h], r15
0x18003f07b  jnz     short loc_18003F0BE
0x18003f07d  lea     rdx, [rsp+1F0h+var_1A0]
0x18003f082  mov     [rsp+1F0h+var_1A0], r15
0x18003f087  lea     rcx, IID_ISimpleTableDispenser
0x18003f08e  call    cs:__imp_GetSimpleTableDispenser
0x18003f094  mov     ebx, eax
0x18003f096  test    eax, eax
0x18003f098  js      loc_18003F121
0x18003f09e  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f0a3  xor     eax, eax
0x18003f0a5  lock cmpxchg [rdi+48h], rcx
0x18003f0ab  jz      short loc_18003F0BE
0x18003f0ad  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f0b2  mov     rax, [rcx]
0x18003f0b5  mov     rax, [rax+10h]
0x18003f0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0be  mov     r8, rsi; Size
0x18003f0c1  lea     rdx, TID_APPLICATION; Buf2
0x18003f0c8  lea     rcx, tidCOMSERVICES_CLASSITFDISPID_EXPORT; Buf1
0x18003f0cf  call    memcmp_0
0x18003f0d4  mov     rcx, [rdi+48h]
0x18003f0d8  lea     r9, [rsp+1F0h+var_188]
0x18003f0dd  mov     [rsp+1F0h+var_1B8], r9
0x18003f0e2  lea     r8, tidCOMSERVICES_CLASSITFDISPID_EXPORT
0x18003f0e9  neg     eax
0x18003f0eb  lea     r9, [rbp+0F0h+var_160]
0x18003f0ef  mov     rax, [rcx]
0x18003f0f2  sbb     edx, edx
0x18003f0f4  and     edx, 2
0x18003f0f7  add     edx, 5
0x18003f0fa  mov     [rsp+1F0h+var_1C0], edx
0x18003f0fe  lea     rdx, didCOMSERVICES
0x18003f105  mov     rax, [rax+18h]
0x18003f109  mov     [rsp+1F0h+var_1C8], 1
0x18003f111  mov     [rsp+1F0h+var_1D0], 4
0x18003f11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f11f  mov     ebx, eax
0x18003f121  test    ebx, ebx
0x18003f123  jnz     loc_18003F4DA
0x18003f129  mov     rcx, [rsp+1F0h+var_188]
0x18003f12e  test    rcx, rcx
0x18003f131  jnz     short loc_18003F13D
0x18003f133  mov     ebx, 8007000Eh
0x18003f138  jmp     loc_18003F4F5
0x18003f13d  mov     rax, [rcx]
0x18003f140  mov     rax, [rax+18h]
0x18003f144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f149  mov     ebx, eax
0x18003f14b  test    eax, eax
0x18003f14d  jnz     loc_18003F4DA
0x18003f153  mov     rcx, [rsp+1F0h+var_188]
0x18003f158  mov     rax, [rcx]
0x18003f15b  mov     rax, [rax+20h]
0x18003f15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f164  mov     ebx, eax
0x18003f166  test    eax, eax
0x18003f168  jnz     loc_18003F4DA
0x18003f16e  lea     eax, [rbx+48h]
0x18003f171  mov     [rbp+0F0h+var_F0], r12d
0x18003f175  lea     r12, [rdi+60h]
0x18003f179  mov     [rbp+0F0h+var_D8], eax
0x18003f17c  lea     rcx, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x18003f183  mov     [rbp+0F0h+var_C0], eax
0x18003f186  mov     [rbp+0F0h+var_A8], eax
0x18003f189  lea     rax, [rsp+1F0h+var_180]
0x18003f18e  mov     [rbp+0F0h+var_EC], esi
0x18003f191  mov     [rbp+0F0h+var_D4], esi
0x18003f194  mov     [rbp+0F0h+var_BC], esi
0x18003f197  mov     [rbp+0F0h+var_A4], esi
0x18003f19a  lea     esi, [rbx+5]
0x18003f19d  mov     [rbp+0F0h+var_A0], rax
0x18003f1a1  mov     [rbp+0F0h+var_100], r14
0x18003f1a5  mov     [rbp+0F0h+var_F8], r15
0x18003f1a9  mov     [rbp+0F0h+var_E8], r12
0x18003f1ad  mov     [rbp+0F0h+var_E0], r15d
0x18003f1b1  mov     [rbp+0F0h+var_DC], 1
0x18003f1b8  mov     [rbp+0F0h+var_D0], rcx
0x18003f1bc  mov     [rbp+0F0h+var_C8], r15d
0x18003f1c0  mov     [rbp+0F0h+var_C4], 2
0x18003f1c7  mov     [rbp+0F0h+var_B8], r13
0x18003f1cb  mov     [rbp+0F0h+var_B0], r15d
0x18003f1cf  mov     [rbp+0F0h+var_AC], 3
0x18003f1d6  mov     [rbp+0F0h+var_98], r15d
0x18003f1da  mov     [rbp+0F0h+var_94], esi
0x18003f1dd  mov     [rbp+0F0h+var_90], 13h
0x18003f1e4  mov     [rbp+0F0h+var_8C], 4
0x18003f1eb  mov     [rsp+1F0h+var_198], r15
0x18003f1f0  cmp     [rdi+48h], r15
0x18003f1f4  jnz     short loc_18003F233
0x18003f1f6  lea     rdx, [rsp+1F0h+var_1A0]
0x18003f1fb  mov     [rsp+1F0h+var_1A0], r15
0x18003f200  lea     rcx, IID_ISimpleTableDispenser
0x18003f207  call    cs:__imp_GetSimpleTableDispenser
0x18003f20d  mov     ebx, eax
0x18003f20f  test    eax, eax
0x18003f211  js      short loc_18003F276
0x18003f213  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f218  xor     eax, eax
0x18003f21a  lock cmpxchg [rdi+48h], rcx
0x18003f220  jz      short loc_18003F233
0x18003f222  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f227  mov     rax, [rcx]
0x18003f22a  mov     rax, [rax+10h]
0x18003f22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f233  mov     rcx, [rdi+48h]
0x18003f237  lea     r8, [rsp+1F0h+var_198]
0x18003f23c  mov     [rsp+1F0h+var_1B8], r8
0x18003f241  lea     r9, [rbp+0F0h+var_100]
0x18003f245  mov     [rsp+1F0h+var_1C0], 800004h
0x18003f24d  lea     r8, tidCOMSERVICES_CLASSITFDISPID
0x18003f254  mov     [rsp+1F0h+var_1C8], 1
0x18003f25c  lea     rdx, didCOMSERVICES
0x18003f263  mov     rax, [rcx]
0x18003f266  mov     [rsp+1F0h+var_1D0], rsi
0x18003f26b  mov     rax, [rax+18h]
0x18003f26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f274  mov     ebx, eax
0x18003f276  test    ebx, ebx
0x18003f278  jnz     loc_18003F4DA
0x18003f27e  cmp     [rsp+1F0h+var_198], r15
0x18003f283  jnz     short loc_18003F28F
0x18003f285  mov     ebx, 8007000Eh
0x18003f28a  jmp     loc_18003F4DA
0x18003f28f  mov     rcx, [rsp+1F0h+var_198]
0x18003f294  mov     rax, [rcx]
0x18003f297  mov     rax, [rax+18h]
0x18003f29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2a0  mov     ebx, eax
0x18003f2a2  test    eax, eax
0x18003f2a4  jnz     loc_18003F4DA
0x18003f2aa  mov     rcx, [rsp+1F0h+var_198]
0x18003f2af  mov     rax, [rcx]
0x18003f2b2  mov     rax, [rax+20h]
0x18003f2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2bb  mov     ebx, eax
0x18003f2bd  test    eax, eax
0x18003f2bf  jnz     loc_18003F4DA
0x18003f2c5  lea     ecx, [rax+38h]; cb
0x18003f2c8  call    cs:__imp_CoTaskMemAlloc
0x18003f2ce  mov     rsi, rax
0x18003f2d1  test    rax, rax
0x18003f2d4  jz      short loc_18003F285
0x18003f2d6  mov     rcx, [rsp+1F0h+var_188]
0x18003f2db  xorps   xmm0, xmm0
0x18003f2de  mov     [rsp+1F0h+var_190], r15d
0x18003f2e3  mov     dword ptr [rsp+1F0h+var_1A0], r15d
0x18003f2e8  movups  [rbp+0F0h+var_80], xmm0
0x18003f2ec  mov     [rsp+1F0h+var_178], r15
0x18003f2f1  movups  [rbp+0F0h+var_70], xmm0
0x18003f2f8  movups  [rbp+0F0h+var_60], xmm0
0x18003f2ff  mov     rax, [rcx]
0x18003f302  mov     rax, [rax+28h]
0x18003f306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f30b  mov     ebx, eax
0x18003f30d  cmp     eax, 80110801h
0x18003f312  jz      loc_18003F4B4
0x18003f318  test    eax, eax
0x18003f31a  jnz     loc_18003F4CC
0x18003f320  mov     rcx, [rsp+1F0h+var_188]
0x18003f325  lea     rdx, [rsp+1F0h+var_178]
0x18003f32a  mov     [rsp+1F0h+var_1D0], rdx
0x18003f32f  lea     r9, [rsp+1F0h+var_1A0]
0x18003f334  lea     r8, [rsp+1F0h+var_190]
0x18003f339  lea     edx, [rbx+4]
0x18003f33c  mov     rax, [rcx]
0x18003f33f  mov     rax, [rax+40h]
0x18003f343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f348  mov     ebx, eax
0x18003f34a  test    eax, eax
0x18003f34c  jnz     loc_18003F4CC
0x18003f352  mov     rcx, [rsp+1F0h+var_198]
0x18003f357  lea     rax, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x18003f35e  mov     qword ptr [rbp+0F0h+var_70], rax
0x18003f365  lea     r8, [rbp+0F0h+var_80]
0x18003f369  mov     rax, [rsp+1F0h+var_178]
0x18003f36e  xor     edx, edx
0x18003f370  mov     qword ptr [rbp+0F0h+var_60], rax
0x18003f377  lea     rax, [rsp+1F0h+var_180]
0x18003f37c  mov     qword ptr [rbp+0F0h+var_60+8], rax
0x18003f383  mov     qword ptr [rbp+0F0h+var_80], r14
0x18003f387  mov     qword ptr [rbp+0F0h+var_80+8], r12
0x18003f38b  mov     qword ptr [rbp+0F0h+var_70+8], r13
0x18003f392  mov     rax, [rcx]
0x18003f395  mov     rax, [rax+38h]
0x18003f399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f39e  cmp     [rbp+0F0h+arg_28], r15d
0x18003f3a5  jz      short loc_18003F3CF
0x18003f3a7  cmp     eax, 80110801h
0x18003f3ac  jnz     short loc_18003F3CF
0x18003f3ae  mov     rcx, [rsp+1F0h+var_198]
0x18003f3b3  mov     rax, [rcx]
0x18003f3b6  mov     rax, [rax+78h]
0x18003f3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3bf  mov     ebx, eax
0x18003f3c1  test    eax, eax
0x18003f3c3  jnz     loc_18003F4CC
0x18003f3c9  lea     r14d, [rax+1]
0x18003f3cd  jmp     short loc_18003F3F8
0x18003f3cf  test    eax, eax
0x18003f3d1  jnz     loc_18003F4AD
0x18003f3d7  mov     rcx, [rsp+1F0h+var_198]
0x18003f3dc  mov     r14d, r15d
0x18003f3df  mov     rax, [rcx]
0x18003f3e2  mov     rax, [rax+80h]
0x18003f3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ee  mov     ebx, eax
0x18003f3f0  test    eax, eax
0x18003f3f2  jnz     loc_18003F4CC
0x18003f3f8  xor     eax, eax
0x18003f3fa  mov     edi, r15d
0x18003f3fd  mov     [rsi], rax
0x18003f400  cmp     edi, 7
0x18003f403  jnb     loc_18003F48A
0x18003f409  mov     [rsp+1F0h+var_190], r15d
0x18003f40e  mov     dword ptr [rsp+1F0h+var_1A0], r15d
0x18003f413  test    r14d, r14d
0x18003f416  jnz     short loc_18003F41D
0x18003f418  cmp     edi, 6
0x18003f41b  jb      short loc_18003F483
0x18003f41d  mov     rcx, [rsp+1F0h+var_188]
0x18003f422  lea     r9, [rsp+1F0h+var_1A0]
0x18003f427  mov     eax, edi
0x18003f429  lea     r8, [rsp+1F0h+var_190]
0x18003f42e  mov     edx, edi
0x18003f430  lea     r15, [rsi+rax*8]
0x18003f434  mov     rax, [rcx]
0x18003f437  mov     [rsp+1F0h+var_1D0], r15
0x18003f43c  mov     rax, [rax+40h]
0x18003f440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f445  mov     ebx, eax
0x18003f447  test    eax, eax
0x18003f449  jnz     short loc_18003F4C9
0x18003f44b  mov     r9, [r15]
0x18003f44e  xor     r15d, r15d
0x18003f451  test    r9, r9
0x18003f454  jz      short loc_18003F483
0x18003f456  mov     rcx, [rsp+1F0h+var_198]
0x18003f45b  mov     r8d, r15d
0x18003f45e  cmp     [rsp+1F0h+var_190], 80h
0x18003f466  mov     edx, edi
0x18003f468  cmovz   r8d, dword ptr [rsp+1F0h+var_1A0]
0x18003f46e  mov     rax, [rcx]
0x18003f471  mov     rax, [rax+0A0h]
0x18003f478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f47d  mov     ebx, eax
0x18003f47f  test    eax, eax
0x18003f481  jnz     short loc_18003F4CC
0x18003f483  inc     edi
0x18003f485  jmp     loc_18003F400
0x18003f48a  mov     rcx, [rsp+1F0h+var_198]
0x18003f48f  mov     rax, [rcx]
0x18003f492  mov     rax, [rax+90h]
0x18003f499  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
