# CAppImport::UpdateMethodTable(_GUID,__MIDL___MIDL_itf_registrar_0000_0000_0001,_GUID,ushort *,ulong)

- ea: `0x180040944`
- end: `0x180040ec4`
- name: `?UpdateMethodTable@CAppImport@@AEAAJU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@0PEAGK@Z`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003f538`

## callees

- `0x18001a6c8`
- `0x180040944`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180040a22`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180040b9b`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180040a22`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180040b9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040c5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040c5c`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateMethodTable(
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
    v11 = memcmp_0(tidCOMSERVICES_CLASSITFMETHOD_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSITFMETHOD_EXPORT,
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
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSITFMETHOD,
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
      v13 = CoTaskMemAlloc(0x68u);
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
          while ( v17 < 0xD )
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
0x180040944  push    rbp
0x180040946  push    rbx
0x180040947  push    rsi
0x180040948  push    rdi
0x180040949  push    r12
0x18004094b  push    r13
0x18004094d  push    r14
0x18004094f  push    r15
0x180040951  lea     rbp, [rsp-0B8h]
0x180040959  sub     rsp, 1B8h
0x180040960  mov     rax, cs:__security_cookie
0x180040967  xor     rax, rsp
0x18004096a  mov     [rbp+0F0h+var_50], rax
0x180040971  xor     r15d, r15d
0x180040974  mov     [rbp+0F0h+var_170], rdx
0x180040978  mov     rdi, rcx
0x18004097b  mov     [rsp+1F0h+var_198], r15
0x180040980  mov     rcx, [rbp+0F0h+arg_20]; unsigned __int16 *
0x180040987  mov     r13, r9
0x18004098a  mov     [rbp+0F0h+var_160], rcx
0x18004098e  mov     r14, rdx
0x180040991  mov     [rsp+1F0h+var_180], r8d
0x180040996  mov     [rbp+0F0h+var_158], r15d
0x18004099a  mov     [rbp+0F0h+var_154], 0F0000001h
0x1800409a1  mov     [rbp+0F0h+var_150], 82h
0x1800409a8  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800409ad  lea     r12d, [r15+48h]
0x1800409b1  mov     [rbp+0F0h+var_148], r14
0x1800409b5  lea     esi, [r15+10h]
0x1800409b9  mov     [rbp+0F0h+var_140], r15
0x1800409bd  mov     [rbp+0F0h+var_138], r12d
0x1800409c1  lea     eax, ds:2[rax*2]
0x1800409c8  mov     [rbp+0F0h+var_134], esi
0x1800409cb  mov     [rbp+0F0h+var_14C], eax
0x1800409ce  lea     rax, [rsp+1F0h+var_180]
0x1800409d3  mov     [rbp+0F0h+var_118], rax
0x1800409d7  mov     [rbp+0F0h+var_130], r9
0x1800409db  mov     [rbp+0F0h+var_128], r15d
0x1800409df  mov     [rbp+0F0h+var_124], 3
0x1800409e6  mov     [rbp+0F0h+var_120], r12d
0x1800409ea  mov     [rbp+0F0h+var_11C], esi
0x1800409ed  mov     [rbp+0F0h+var_110], r15d
0x1800409f1  mov     [rbp+0F0h+var_10C], 5
0x1800409f8  mov     [rbp+0F0h+var_108], 13h
0x1800409ff  mov     [rbp+0F0h+var_104], 4
0x180040a06  mov     [rsp+1F0h+var_188], r15
0x180040a0b  cmp     [rdi+48h], r15
0x180040a0f  jnz     short loc_180040A52
0x180040a11  lea     rdx, [rsp+1F0h+var_1A0]
0x180040a16  mov     [rsp+1F0h+var_1A0], r15
0x180040a1b  lea     rcx, IID_ISimpleTableDispenser
0x180040a22  call    cs:__imp_GetSimpleTableDispenser
0x180040a28  mov     ebx, eax
0x180040a2a  test    eax, eax
0x180040a2c  js      loc_180040AB5
0x180040a32  mov     rcx, [rsp+1F0h+var_1A0]
0x180040a37  xor     eax, eax
0x180040a39  lock cmpxchg [rdi+48h], rcx
0x180040a3f  jz      short loc_180040A52
0x180040a41  mov     rcx, [rsp+1F0h+var_1A0]
0x180040a46  mov     rax, [rcx]
0x180040a49  mov     rax, [rax+10h]
0x180040a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a52  mov     r8, rsi; Size
0x180040a55  lea     rdx, TID_APPLICATION; Buf2
0x180040a5c  lea     rcx, tidCOMSERVICES_CLASSITFMETHOD_EXPORT; Buf1
0x180040a63  call    memcmp_0
0x180040a68  mov     rcx, [rdi+48h]
0x180040a6c  lea     r9, [rsp+1F0h+var_188]
0x180040a71  mov     [rsp+1F0h+var_1B8], r9
0x180040a76  lea     r8, tidCOMSERVICES_CLASSITFMETHOD_EXPORT
0x180040a7d  neg     eax
0x180040a7f  lea     r9, [rbp+0F0h+var_160]
0x180040a83  mov     rax, [rcx]
0x180040a86  sbb     edx, edx
0x180040a88  and     edx, 2
0x180040a8b  add     edx, 5
0x180040a8e  mov     [rsp+1F0h+var_1C0], edx
0x180040a92  lea     rdx, didCOMSERVICES
0x180040a99  mov     rax, [rax+18h]
0x180040a9d  mov     [rsp+1F0h+var_1C8], 1
0x180040aa5  mov     [rsp+1F0h+var_1D0], 4
0x180040aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ab3  mov     ebx, eax
0x180040ab5  test    ebx, ebx
0x180040ab7  jnz     loc_180040E6E
0x180040abd  mov     rcx, [rsp+1F0h+var_188]
0x180040ac2  test    rcx, rcx
0x180040ac5  jnz     short loc_180040AD1
0x180040ac7  mov     ebx, 8007000Eh
0x180040acc  jmp     loc_180040E89
0x180040ad1  mov     rax, [rcx]
0x180040ad4  mov     rax, [rax+18h]
0x180040ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040add  mov     ebx, eax
0x180040adf  test    eax, eax
0x180040ae1  jnz     loc_180040E6E
0x180040ae7  mov     rcx, [rsp+1F0h+var_188]
0x180040aec  mov     rax, [rcx]
0x180040aef  mov     rax, [rax+20h]
0x180040af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040af8  mov     ebx, eax
0x180040afa  test    eax, eax
0x180040afc  jnz     loc_180040E6E
0x180040b02  lea     eax, [rbx+48h]
0x180040b05  mov     [rbp+0F0h+var_F0], r12d
0x180040b09  lea     r12, [rdi+60h]
0x180040b0d  mov     [rbp+0F0h+var_D8], eax
0x180040b10  lea     rcx, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x180040b17  mov     [rbp+0F0h+var_C0], eax
0x180040b1a  mov     [rbp+0F0h+var_A8], eax
0x180040b1d  lea     rax, [rsp+1F0h+var_180]
0x180040b22  mov     [rbp+0F0h+var_EC], esi
0x180040b25  mov     [rbp+0F0h+var_D4], esi
0x180040b28  mov     [rbp+0F0h+var_BC], esi
0x180040b2b  mov     [rbp+0F0h+var_A4], esi
0x180040b2e  lea     esi, [rbx+5]
0x180040b31  mov     [rbp+0F0h+var_A0], rax
0x180040b35  mov     [rbp+0F0h+var_100], r14
0x180040b39  mov     [rbp+0F0h+var_F8], r15
0x180040b3d  mov     [rbp+0F0h+var_E8], r12
0x180040b41  mov     [rbp+0F0h+var_E0], r15d
0x180040b45  mov     [rbp+0F0h+var_DC], 1
0x180040b4c  mov     [rbp+0F0h+var_D0], rcx
0x180040b50  mov     [rbp+0F0h+var_C8], r15d
0x180040b54  mov     [rbp+0F0h+var_C4], 2
0x180040b5b  mov     [rbp+0F0h+var_B8], r13
0x180040b5f  mov     [rbp+0F0h+var_B0], r15d
0x180040b63  mov     [rbp+0F0h+var_AC], 3
0x180040b6a  mov     [rbp+0F0h+var_98], r15d
0x180040b6e  mov     [rbp+0F0h+var_94], esi
0x180040b71  mov     [rbp+0F0h+var_90], 13h
0x180040b78  mov     [rbp+0F0h+var_8C], 4
0x180040b7f  mov     [rsp+1F0h+var_198], r15
0x180040b84  cmp     [rdi+48h], r15
0x180040b88  jnz     short loc_180040BC7
0x180040b8a  lea     rdx, [rsp+1F0h+var_1A0]
0x180040b8f  mov     [rsp+1F0h+var_1A0], r15
0x180040b94  lea     rcx, IID_ISimpleTableDispenser
0x180040b9b  call    cs:__imp_GetSimpleTableDispenser
0x180040ba1  mov     ebx, eax
0x180040ba3  test    eax, eax
0x180040ba5  js      short loc_180040C0A
0x180040ba7  mov     rcx, [rsp+1F0h+var_1A0]
0x180040bac  xor     eax, eax
0x180040bae  lock cmpxchg [rdi+48h], rcx
0x180040bb4  jz      short loc_180040BC7
0x180040bb6  mov     rcx, [rsp+1F0h+var_1A0]
0x180040bbb  mov     rax, [rcx]
0x180040bbe  mov     rax, [rax+10h]
0x180040bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bc7  mov     rcx, [rdi+48h]
0x180040bcb  lea     r8, [rsp+1F0h+var_198]
0x180040bd0  mov     [rsp+1F0h+var_1B8], r8
0x180040bd5  lea     r9, [rbp+0F0h+var_100]
0x180040bd9  mov     [rsp+1F0h+var_1C0], 800004h
0x180040be1  lea     r8, tidCOMSERVICES_CLASSITFMETHOD
0x180040be8  mov     [rsp+1F0h+var_1C8], 1
0x180040bf0  lea     rdx, didCOMSERVICES
0x180040bf7  mov     rax, [rcx]
0x180040bfa  mov     [rsp+1F0h+var_1D0], rsi
0x180040bff  mov     rax, [rax+18h]
0x180040c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c08  mov     ebx, eax
0x180040c0a  test    ebx, ebx
0x180040c0c  jnz     loc_180040E6E
0x180040c12  cmp     [rsp+1F0h+var_198], r15
0x180040c17  jnz     short loc_180040C23
0x180040c19  mov     ebx, 8007000Eh
0x180040c1e  jmp     loc_180040E6E
0x180040c23  mov     rcx, [rsp+1F0h+var_198]
0x180040c28  mov     rax, [rcx]
0x180040c2b  mov     rax, [rax+18h]
0x180040c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c34  mov     ebx, eax
0x180040c36  test    eax, eax
0x180040c38  jnz     loc_180040E6E
0x180040c3e  mov     rcx, [rsp+1F0h+var_198]
0x180040c43  mov     rax, [rcx]
0x180040c46  mov     rax, [rax+20h]
0x180040c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c4f  mov     ebx, eax
0x180040c51  test    eax, eax
0x180040c53  jnz     loc_180040E6E
0x180040c59  lea     ecx, [rax+68h]; cb
0x180040c5c  call    cs:__imp_CoTaskMemAlloc
0x180040c62  mov     rsi, rax
0x180040c65  test    rax, rax
0x180040c68  jz      short loc_180040C19
0x180040c6a  mov     rcx, [rsp+1F0h+var_188]
0x180040c6f  xorps   xmm0, xmm0
0x180040c72  mov     [rsp+1F0h+var_190], r15d
0x180040c77  mov     dword ptr [rsp+1F0h+var_1A0], r15d
0x180040c7c  movups  [rbp+0F0h+var_80], xmm0
0x180040c80  mov     [rsp+1F0h+var_178], r15
0x180040c85  movups  [rbp+0F0h+var_70], xmm0
0x180040c8c  movups  [rbp+0F0h+var_60], xmm0
0x180040c93  mov     rax, [rcx]
0x180040c96  mov     rax, [rax+28h]
0x180040c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c9f  mov     ebx, eax
0x180040ca1  cmp     eax, 80110801h
0x180040ca6  jz      loc_180040E48
0x180040cac  test    eax, eax
0x180040cae  jnz     loc_180040E60
0x180040cb4  mov     rcx, [rsp+1F0h+var_188]
0x180040cb9  lea     rdx, [rsp+1F0h+var_178]
0x180040cbe  mov     [rsp+1F0h+var_1D0], rdx
0x180040cc3  lea     r9, [rsp+1F0h+var_1A0]
0x180040cc8  lea     r8, [rsp+1F0h+var_190]
0x180040ccd  lea     edx, [rbx+4]
0x180040cd0  mov     rax, [rcx]
0x180040cd3  mov     rax, [rax+40h]
0x180040cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cdc  mov     ebx, eax
0x180040cde  test    eax, eax
0x180040ce0  jnz     loc_180040E60
0x180040ce6  mov     rcx, [rsp+1F0h+var_198]
0x180040ceb  lea     rax, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x180040cf2  mov     qword ptr [rbp+0F0h+var_70], rax
0x180040cf9  lea     r8, [rbp+0F0h+var_80]
0x180040cfd  mov     rax, [rsp+1F0h+var_178]
0x180040d02  xor     edx, edx
0x180040d04  mov     qword ptr [rbp+0F0h+var_60], rax
0x180040d0b  lea     rax, [rsp+1F0h+var_180]
0x180040d10  mov     qword ptr [rbp+0F0h+var_60+8], rax
0x180040d17  mov     qword ptr [rbp+0F0h+var_80], r14
0x180040d1b  mov     qword ptr [rbp+0F0h+var_80+8], r12
0x180040d1f  mov     qword ptr [rbp+0F0h+var_70+8], r13
0x180040d26  mov     rax, [rcx]
0x180040d29  mov     rax, [rax+38h]
0x180040d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d32  cmp     [rbp+0F0h+arg_28], r15d
0x180040d39  jz      short loc_180040D63
0x180040d3b  cmp     eax, 80110801h
0x180040d40  jnz     short loc_180040D63
0x180040d42  mov     rcx, [rsp+1F0h+var_198]
0x180040d47  mov     rax, [rcx]
0x180040d4a  mov     rax, [rax+78h]
0x180040d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d53  mov     ebx, eax
0x180040d55  test    eax, eax
0x180040d57  jnz     loc_180040E60
0x180040d5d  lea     r14d, [rax+1]
0x180040d61  jmp     short loc_180040D8C
0x180040d63  test    eax, eax
0x180040d65  jnz     loc_180040E41
0x180040d6b  mov     rcx, [rsp+1F0h+var_198]
0x180040d70  mov     r14d, r15d
0x180040d73  mov     rax, [rcx]
0x180040d76  mov     rax, [rax+80h]
0x180040d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d82  mov     ebx, eax
0x180040d84  test    eax, eax
0x180040d86  jnz     loc_180040E60
0x180040d8c  xor     eax, eax
0x180040d8e  mov     edi, r15d
0x180040d91  mov     [rsi], rax
0x180040d94  cmp     edi, 0Dh
0x180040d97  jnb     loc_180040E1E
0x180040d9d  mov     [rsp+1F0h+var_190], r15d
0x180040da2  mov     dword ptr [rsp+1F0h+var_1A0], r15d
0x180040da7  test    r14d, r14d
0x180040daa  jnz     short loc_180040DB1
0x180040dac  cmp     edi, 6
0x180040daf  jb      short loc_180040E17
0x180040db1  mov     rcx, [rsp+1F0h+var_188]
0x180040db6  lea     r9, [rsp+1F0h+var_1A0]
0x180040dbb  mov     eax, edi
0x180040dbd  lea     r8, [rsp+1F0h+var_190]
0x180040dc2  mov     edx, edi
0x180040dc4  lea     r15, [rsi+rax*8]
0x180040dc8  mov     rax, [rcx]
0x180040dcb  mov     [rsp+1F0h+var_1D0], r15
0x180040dd0  mov     rax, [rax+40h]
0x180040dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dd9  mov     ebx, eax
0x180040ddb  test    eax, eax
0x180040ddd  jnz     short loc_180040E5D
0x180040ddf  mov     r9, [r15]
0x180040de2  xor     r15d, r15d
0x180040de5  test    r9, r9
0x180040de8  jz      short loc_180040E17
0x180040dea  mov     rcx, [rsp+1F0h+var_198]
0x180040def  mov     r8d, r15d
0x180040df2  cmp     [rsp+1F0h+var_190], 80h
0x180040dfa  mov     edx, edi
0x180040dfc  cmovz   r8d, dword ptr [rsp+1F0h+var_1A0]
0x180040e02  mov     rax, [rcx]
0x180040e05  mov     rax, [rax+0A0h]
0x180040e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e11  mov     ebx, eax
0x180040e13  test    eax, eax
0x180040e15  jnz     short loc_180040E60
0x180040e17  inc     edi
0x180040e19  jmp     loc_180040D94
0x180040e1e  mov     rcx, [rsp+1F0h+var_198]
0x180040e23  mov     rax, [rcx]
0x180040e26  mov     rax, [rax+90h]
0x180040e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
