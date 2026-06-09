# CAppImport::UpdateInterfaceTable(_GUID,__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort *,ulong)

- ea: `0x18003f538`
- end: `0x18003fb51`
- name: `?UpdateInterfaceTable@CAppImport@@AEAAJU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAGK@Z`
- size: `1561`
- prototype: `int __high(struct _GUID, enum __MIDL___MIDL_itf_registrar_0000_0000_0001, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011d74`

## callees

- `0x18001a6c8`
- `0x18003efb0`
- `0x18003f538`
- `0x180040944`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f613`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f793`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f613`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18003f793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f855`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateInterfaceTable(
        __int64 a1,
        _OWORD *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        int a5)
{
  _OWORD *v6; // rdi
  int v7; // eax
  bool v8; // zf
  int SimpleTableDispenser; // ebx
  int v10; // eax
  _QWORD *v11; // r14
  int v12; // r15d
  int v13; // eax
  __int128 v14; // xmm0
  int v15; // eax
  int v16; // r12d
  __int64 i; // rdi
  _QWORD *v18; // r15
  __int64 v19; // r8
  const unsigned __int16 *v20; // r12
  __int128 v21; // xmm1
  signed __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  __int128 *v28; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v29; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-30h]
  unsigned int *v36; // [rsp+E0h] [rbp-20h]
  const unsigned __int16 *v37; // [rsp+F0h] [rbp-10h] BYREF
  int v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+FCh] [rbp-4h]
  int v40; // [rsp+100h] [rbp+0h]
  int v41; // [rsp+104h] [rbp+4h]
  _OWORD *v42; // [rsp+108h] [rbp+8h]
  __int64 v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+118h] [rbp+18h]
  int v45; // [rsp+11Ch] [rbp+1Ch]
  unsigned int *v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+128h] [rbp+28h]
  int v48; // [rsp+12Ch] [rbp+2Ch]
  int v49; // [rsp+130h] [rbp+30h]
  int v50; // [rsp+134h] [rbp+34h]
  _QWORD v51[2]; // [rsp+140h] [rbp+40h] BYREF
  int v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+154h] [rbp+54h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  int v55; // [rsp+160h] [rbp+60h]
  int v56; // [rsp+164h] [rbp+64h]
  int v57; // [rsp+168h] [rbp+68h]
  int v58; // [rsp+16Ch] [rbp+6Ch]
  GUID *v59; // [rsp+170h] [rbp+70h]
  int v60; // [rsp+178h] [rbp+78h]
  int v61; // [rsp+17Ch] [rbp+7Ch]
  int v62; // [rsp+180h] [rbp+80h]
  int v63; // [rsp+184h] [rbp+84h]
  unsigned int *v64; // [rsp+188h] [rbp+88h]
  int v65; // [rsp+190h] [rbp+90h]
  int v66; // [rsp+194h] [rbp+94h]
  int v67; // [rsp+198h] [rbp+98h]
  int v68; // [rsp+19Ch] [rbp+9Ch]

  v30 = a4;
  v29 = a2;
  v6 = a2;
  v24 = 0;
  v25 = a3;
  v37 = a4;
  v38 = 0;
  v39 = -268435455;
  v40 = 130;
  v7 = safe_lstrlenW(a4);
  v8 = *(_QWORD *)(a1 + 72) == 0;
  v42 = v6;
  v43 = 0;
  v44 = 72;
  v41 = 2 * v7 + 2;
  v47 = 0;
  v46 = &v25;
  v45 = 16;
  v48 = 4;
  v49 = 19;
  v50 = 4;
  v27 = 0;
  if ( !v8 )
  {
LABEL_5:
    v10 = memcmp_0(tidCOMSERVICES_CLASSINTERFACE_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             tidCOMSERVICES_CLASSINTERFACE_EXPORT,
                             &v37,
                             3,
                             1,
                             v10 != 0 ? 7 : 5,
                             &v27);
    goto LABEL_6;
  }
  v23 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v23);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v23, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 16LL))(v23);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser )
    goto LABEL_51;
  if ( !v27 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_53;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  if ( SimpleTableDispenser )
    goto LABEL_51;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27);
  if ( SimpleTableDispenser )
    goto LABEL_51;
  v8 = *(_QWORD *)(a1 + 72) == 0;
  v55 = 0;
  v59 = &g_guidAppIdForQuery;
  v64 = &v25;
  v51[0] = v6;
  v51[1] = 0;
  v52 = 72;
  v53 = 16;
  v54 = a1 + 96;
  v56 = 1;
  v57 = 72;
  v58 = 16;
  v60 = 0;
  v61 = 2;
  v62 = 72;
  v63 = 16;
  v65 = 0;
  v66 = 4;
  v67 = 19;
  v68 = 4;
  v24 = 0;
  if ( !v8 )
    goto LABEL_15;
  v23 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v23);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v23, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_15:
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, _QWORD *, __int64, int, int, __int64 *))(**(_QWORD **)(a1 + 72) + 24LL))(
                             *(_QWORD *)(a1 + 72),
                             didCOMSERVICES,
                             &tidCOMSERVICES_CLASSINTERFACE,
                             v51,
                             4,
                             1,
                             8388612,
                             &v24);
  }
  if ( SimpleTableDispenser )
    goto LABEL_51;
  if ( !v24 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
  if ( !SimpleTableDispenser )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
    if ( !SimpleTableDispenser )
    {
      v11 = CoTaskMemAlloc(0x60u);
      if ( v11 )
      {
        v12 = a5;
        while ( 1 )
        {
          v36 = 0;
          v28 = 0;
          v33 = 0;
          v26 = 0;
          LODWORD(v23) = 0;
          v34 = 0;
          v35 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
          SimpleTableDispenser = v13;
          if ( v13 == -2146367487 )
            break;
          if ( v13 )
            goto LABEL_50;
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, signed __int64 *, __int128 **))(*(_QWORD *)v27 + 64LL))(
                                   v27,
                                   3,
                                   &v26,
                                   &v23,
                                   &v28);
          if ( SimpleTableDispenser )
            goto LABEL_50;
          v14 = *v28;
          *(_QWORD *)&v34 = v6;
          *(_QWORD *)&v35 = &g_guidAppIdForQuery;
          *((_QWORD *)&v35 + 1) = &v33;
          v36 = &v25;
          v33 = v14;
          *((_QWORD *)&v34 + 1) = a1 + 96;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v24 + 56LL))(v24, 0, &v34);
          if ( v12 && v15 == -2146367487 )
          {
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 120LL))(v24);
            if ( SimpleTableDispenser )
              goto LABEL_50;
            v16 = 1;
          }
          else
          {
            if ( v15 )
            {
              SimpleTableDispenser = -2146368488;
              goto LABEL_50;
            }
            v16 = 0;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 128LL))(v24);
            if ( SimpleTableDispenser )
              goto LABEL_50;
          }
          *v11 = 0;
          for ( i = 0; (unsigned int)i < 0xC; i = (unsigned int)(i + 1) )
          {
            v26 = 0;
            LODWORD(v23) = 0;
            if ( v16 || (unsigned int)i >= 5 )
            {
              v18 = &v11[i];
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, signed __int64 *, _QWORD *))(*(_QWORD *)v27 + 64LL))(
                                       v27,
                                       (unsigned int)i,
                                       &v26,
                                       &v23,
                                       v18);
              if ( SimpleTableDispenser )
                goto LABEL_50;
              if ( *v18 )
              {
                if ( (_DWORD)i == 1 )
                  *v18 = a1 + 96;
                v19 = 0;
                if ( v26 == 128 )
                  v19 = (unsigned int)v23;
                SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v24 + 160LL))(
                                         v24,
                                         (unsigned int)i,
                                         v19);
                if ( SimpleTableDispenser )
                  goto LABEL_50;
              }
            }
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 144LL))(v24);
          if ( !SimpleTableDispenser )
          {
            v6 = v29;
            v12 = a5;
            v20 = v30;
            v32 = *v29;
            v31 = v33;
            SimpleTableDispenser = CAppImport::UpdateMethodTable(a1, &v32, v25, &v31, v30, a5);
            if ( !SimpleTableDispenser )
            {
              v21 = *v6;
              v32 = v33;
              v31 = v21;
              SimpleTableDispenser = CAppImport::UpdateDispIDTable(a1, &v31, v25, &v32, v20, a5);
              if ( !SimpleTableDispenser )
                continue;
            }
          }
          goto LABEL_50;
        }
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24);
LABEL_50:
        *v11 = 0;
        CoTaskMemFree(v11);
        goto LABEL_51;
      }
LABEL_18:
      SimpleTableDispenser = -2147024882;
    }
  }
LABEL_51:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
LABEL_53:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18003f538  push    rbp
0x18003f53a  push    rbx
0x18003f53b  push    rsi
0x18003f53c  push    rdi
0x18003f53d  push    r12
0x18003f53f  push    r13
0x18003f541  push    r14
0x18003f543  push    r15
0x18003f545  lea     rbp, [rsp-0B8h]
0x18003f54d  sub     rsp, 1B8h
0x18003f554  mov     rax, cs:__security_cookie
0x18003f55b  xor     rax, rsp
0x18003f55e  mov     [rbp+0F0h+var_50], rax
0x18003f565  mov     rsi, rcx
0x18003f568  mov     [rbp+0F0h+var_170], r9
0x18003f56c  mov     rcx, r9; unsigned __int16 *
0x18003f56f  mov     [rsp+1F0h+var_178], rdx
0x18003f574  mov     rdi, rdx
0x18003f577  mov     [rsp+1F0h+var_198], 0
0x18003f580  mov     [rsp+1F0h+var_190], r8d
0x18003f585  mov     [rbp+0F0h+var_100], r9
0x18003f589  mov     [rbp+0F0h+var_F8], 0
0x18003f590  mov     [rbp+0F0h+var_F4], 0F0000001h
0x18003f597  mov     [rbp+0F0h+var_F0], 82h
0x18003f59e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003f5a3  cmp     qword ptr [rsi+48h], 0
0x18003f5a8  mov     r15d, 48h ; 'H'
0x18003f5ae  mov     [rbp+0F0h+var_E8], rdi
0x18003f5b2  mov     [rbp+0F0h+var_E0], 0
0x18003f5ba  lea     eax, ds:2[rax*2]
0x18003f5c1  mov     [rbp+0F0h+var_D8], r15d
0x18003f5c5  lea     r12d, [r15-44h]
0x18003f5c9  mov     [rbp+0F0h+var_EC], eax
0x18003f5cc  lea     rax, [rsp+1F0h+var_190]
0x18003f5d1  mov     [rbp+0F0h+var_C8], 0
0x18003f5d8  lea     r14d, [r15-38h]
0x18003f5dc  mov     [rbp+0F0h+var_D0], rax
0x18003f5e0  mov     [rbp+0F0h+var_D4], r14d
0x18003f5e4  mov     [rbp+0F0h+var_C4], r12d
0x18003f5e8  mov     [rbp+0F0h+var_C0], 13h
0x18003f5ef  mov     [rbp+0F0h+var_BC], r12d
0x18003f5f3  mov     [rsp+1F0h+var_188], 0
0x18003f5fc  jnz     short loc_18003F643
0x18003f5fe  lea     rdx, [rsp+1F0h+var_1A0]
0x18003f603  mov     [rsp+1F0h+var_1A0], 0
0x18003f60c  lea     rcx, IID_ISimpleTableDispenser
0x18003f613  call    cs:__imp_GetSimpleTableDispenser
0x18003f619  mov     ebx, eax
0x18003f61b  test    eax, eax
0x18003f61d  js      loc_18003F6A6
0x18003f623  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f628  xor     eax, eax
0x18003f62a  lock cmpxchg [rsi+48h], rcx
0x18003f630  jz      short loc_18003F643
0x18003f632  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f637  mov     rax, [rcx]
0x18003f63a  mov     rax, [rax+10h]
0x18003f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f643  mov     r8, r14; Size
0x18003f646  lea     rdx, TID_APPLICATION; Buf2
0x18003f64d  lea     rcx, tidCOMSERVICES_CLASSINTERFACE_EXPORT; Buf1
0x18003f654  call    memcmp_0
0x18003f659  mov     rcx, [rsi+48h]
0x18003f65d  lea     r9, [rsp+1F0h+var_188]
0x18003f662  mov     [rsp+1F0h+var_1B8], r9
0x18003f667  lea     r8, tidCOMSERVICES_CLASSINTERFACE_EXPORT
0x18003f66e  neg     eax
0x18003f670  lea     r9, [rbp+0F0h+var_100]
0x18003f674  mov     rax, [rcx]
0x18003f677  sbb     edx, edx
0x18003f679  and     edx, 2
0x18003f67c  add     edx, 5
0x18003f67f  mov     [rsp+1F0h+var_1C0], edx
0x18003f683  lea     rdx, didCOMSERVICES
0x18003f68a  mov     rax, [rax+18h]
0x18003f68e  mov     [rsp+1F0h+var_1C8], 1
0x18003f696  mov     [rsp+1F0h+var_1D0], 3
0x18003f69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6a4  mov     ebx, eax
0x18003f6a6  test    ebx, ebx
0x18003f6a8  jnz     loc_18003FAF7
0x18003f6ae  mov     rcx, [rsp+1F0h+var_188]
0x18003f6b3  test    rcx, rcx
0x18003f6b6  jnz     short loc_18003F6C2
0x18003f6b8  mov     ebx, 8007000Eh
0x18003f6bd  jmp     loc_18003FB16
0x18003f6c2  mov     rax, [rcx]
0x18003f6c5  mov     rax, [rax+18h]
0x18003f6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6ce  mov     ebx, eax
0x18003f6d0  test    eax, eax
0x18003f6d2  jnz     loc_18003FAF7
0x18003f6d8  mov     rcx, [rsp+1F0h+var_188]
0x18003f6dd  mov     rax, [rcx]
0x18003f6e0  mov     rax, [rax+20h]
0x18003f6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6e9  mov     ebx, eax
0x18003f6eb  test    eax, eax
0x18003f6ed  jnz     loc_18003FAF7
0x18003f6f3  cmp     qword ptr [rsi+48h], 0
0x18003f6f8  lea     r13, [rsi+60h]
0x18003f6fc  mov     [rbp+0F0h+var_90], eax
0x18003f6ff  lea     rax, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x18003f706  mov     [rbp+0F0h+var_80], rax
0x18003f70a  lea     rax, [rsp+1F0h+var_190]
0x18003f70f  mov     [rbp+0F0h+var_68], rax
0x18003f716  mov     [rbp+0F0h+var_B0], rdi
0x18003f71a  mov     [rbp+0F0h+var_A8], 0
0x18003f722  mov     [rbp+0F0h+var_A0], r15d
0x18003f726  mov     [rbp+0F0h+var_9C], r14d
0x18003f72a  mov     [rbp+0F0h+var_98], r13
0x18003f72e  mov     [rbp+0F0h+var_8C], 1
0x18003f735  mov     [rbp+0F0h+var_88], r15d
0x18003f739  mov     [rbp+0F0h+var_84], r14d
0x18003f73d  mov     [rbp+0F0h+var_78], ebx
0x18003f740  mov     [rbp+0F0h+var_74], 2
0x18003f747  mov     [rbp+0F0h+var_70], r15d
0x18003f74e  mov     [rbp+0F0h+var_6C], r14d
0x18003f755  mov     [rbp+0F0h+var_60], ebx
0x18003f75b  mov     [rbp+0F0h+var_5C], r12d
0x18003f762  mov     [rbp+0F0h+var_58], 13h
0x18003f76c  mov     [rbp+0F0h+var_54], r12d
0x18003f773  mov     [rsp+1F0h+var_198], 0
0x18003f77c  jnz     short loc_18003F7BF
0x18003f77e  lea     rdx, [rsp+1F0h+var_1A0]
0x18003f783  mov     [rsp+1F0h+var_1A0], 0
0x18003f78c  lea     rcx, IID_ISimpleTableDispenser
0x18003f793  call    cs:__imp_GetSimpleTableDispenser
0x18003f799  mov     ebx, eax
0x18003f79b  test    eax, eax
0x18003f79d  js      short loc_18003F802
0x18003f79f  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f7a4  xor     eax, eax
0x18003f7a6  lock cmpxchg [rsi+48h], rcx
0x18003f7ac  jz      short loc_18003F7BF
0x18003f7ae  mov     rcx, [rsp+1F0h+var_1A0]
0x18003f7b3  mov     rax, [rcx]
0x18003f7b6  mov     rax, [rax+10h]
0x18003f7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7bf  mov     rcx, [rsi+48h]
0x18003f7c3  lea     r8, [rsp+1F0h+var_198]
0x18003f7c8  mov     [rsp+1F0h+var_1B8], r8
0x18003f7cd  lea     r9, [rbp+0F0h+var_B0]
0x18003f7d1  mov     [rsp+1F0h+var_1C0], 800004h
0x18003f7d9  lea     r8, tidCOMSERVICES_CLASSINTERFACE
0x18003f7e0  mov     [rsp+1F0h+var_1C8], 1
0x18003f7e8  lea     rdx, didCOMSERVICES
0x18003f7ef  mov     rax, [rcx]
0x18003f7f2  mov     [rsp+1F0h+var_1D0], r12
0x18003f7f7  mov     rax, [rax+18h]
0x18003f7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f800  mov     ebx, eax
0x18003f802  test    ebx, ebx
0x18003f804  jnz     loc_18003FAF7
0x18003f80a  cmp     [rsp+1F0h+var_198], 0
0x18003f810  jnz     short loc_18003F81C
0x18003f812  mov     ebx, 8007000Eh
0x18003f817  jmp     loc_18003FAF7
0x18003f81c  mov     rcx, [rsp+1F0h+var_198]
0x18003f821  mov     rax, [rcx]
0x18003f824  mov     rax, [rax+18h]
0x18003f828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f82d  mov     ebx, eax
0x18003f82f  test    eax, eax
0x18003f831  jnz     loc_18003FAF7
0x18003f837  mov     rcx, [rsp+1F0h+var_198]
0x18003f83c  mov     rax, [rcx]
0x18003f83f  mov     rax, [rax+20h]
0x18003f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f848  mov     ebx, eax
0x18003f84a  test    eax, eax
0x18003f84c  jnz     loc_18003FAF7
0x18003f852  lea     ecx, [rax+60h]; cb
0x18003f855  call    cs:__imp_CoTaskMemAlloc
0x18003f85b  mov     r14, rax
0x18003f85e  test    rax, rax
0x18003f861  jz      short loc_18003F812
0x18003f863  mov     r15d, [rbp+0F0h+arg_20]
0x18003f86a  mov     rcx, [rsp+1F0h+var_188]
0x18003f86f  xor     eax, eax
0x18003f871  xorps   xmm0, xmm0
0x18003f874  mov     [rbp+0F0h+var_110], rax
0x18003f878  mov     [rsp+1F0h+var_180], rax
0x18003f87d  movups  [rbp+0F0h+var_140], xmm0
0x18003f881  mov     [rsp+1F0h+var_18C], 0
0x18003f889  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x18003f891  movups  [rbp+0F0h+var_130], xmm0
0x18003f895  movups  [rbp+0F0h+var_120], xmm0
0x18003f899  mov     rax, [rcx]
0x18003f89c  mov     rax, [rax+28h]
0x18003f8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8a5  mov     ebx, eax
0x18003f8a7  cmp     eax, 80110801h
0x18003f8ac  jz      loc_18003FAD6
0x18003f8b2  test    eax, eax
0x18003f8b4  jnz     loc_18003FAE9
0x18003f8ba  mov     rcx, [rsp+1F0h+var_188]
0x18003f8bf  lea     rdx, [rsp+1F0h+var_180]
0x18003f8c4  mov     [rsp+1F0h+var_1D0], rdx
0x18003f8c9  lea     r9, [rsp+1F0h+var_1A0]
0x18003f8ce  lea     r8, [rsp+1F0h+var_18C]
0x18003f8d3  lea     edx, [rbx+3]
0x18003f8d6  mov     rax, [rcx]
0x18003f8d9  mov     rax, [rax+40h]
0x18003f8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8e2  mov     ebx, eax
0x18003f8e4  test    eax, eax
0x18003f8e6  jnz     loc_18003FAE9
0x18003f8ec  mov     rax, [rsp+1F0h+var_180]
0x18003f8f1  lea     r8, [rbp+0F0h+var_130]
0x18003f8f5  mov     rcx, [rsp+1F0h+var_198]
0x18003f8fa  xor     edx, edx
0x18003f8fc  movups  xmm0, xmmword ptr [rax]
0x18003f8ff  lea     rax, ?g_guidAppIdForQuery@@3U_GUID@@A; _GUID g_guidAppIdForQuery
0x18003f906  mov     qword ptr [rbp+0F0h+var_130], rdi
0x18003f90a  mov     qword ptr [rbp+0F0h+var_120], rax
0x18003f90e  lea     rax, [rbp+0F0h+var_140]
0x18003f912  mov     qword ptr [rbp+0F0h+var_120+8], rax
0x18003f916  lea     rax, [rsp+1F0h+var_190]
0x18003f91b  mov     [rbp+0F0h+var_110], rax
0x18003f91f  movdqu  [rbp+0F0h+var_140], xmm0
0x18003f924  mov     qword ptr [rbp+0F0h+var_130+8], r13
0x18003f928  mov     rax, [rcx]
0x18003f92b  mov     rax, [rax+38h]
0x18003f92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f934  test    r15d, r15d
0x18003f937  jz      short loc_18003F961
0x18003f939  cmp     eax, 80110801h
0x18003f93e  jnz     short loc_18003F961
0x18003f940  mov     rcx, [rsp+1F0h+var_198]
0x18003f945  mov     rax, [rcx]
0x18003f948  mov     rax, [rax+78h]
0x18003f94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f951  mov     ebx, eax
0x18003f953  test    eax, eax
0x18003f955  jnz     loc_18003FAE9
0x18003f95b  lea     r12d, [rax+1]
0x18003f95f  jmp     short loc_18003F98A
0x18003f961  test    eax, eax
0x18003f963  jnz     loc_18003FACF
0x18003f969  mov     rcx, [rsp+1F0h+var_198]
0x18003f96e  xor     r12d, r12d
0x18003f971  mov     rax, [rcx]
0x18003f974  mov     rax, [rax+80h]
0x18003f97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f980  mov     ebx, eax
0x18003f982  test    eax, eax
0x18003f984  jnz     loc_18003FAE9
0x18003f98a  xor     eax, eax
0x18003f98c  mov     [r14], rax
0x18003f98f  xor     edi, edi
0x18003f991  cmp     edi, 0Ch
0x18003f994  jnb     loc_18003FA2F
0x18003f99a  mov     [rsp+1F0h+var_18C], 0
0x18003f9a2  mov     dword ptr [rsp+1F0h+var_1A0], 0
0x18003f9aa  test    r12d, r12d
0x18003f9ad  jnz     short loc_18003F9B4
0x18003f9af  cmp     edi, 5
0x18003f9b2  jb      short loc_18003FA28
0x18003f9b4  mov     rcx, [rsp+1F0h+var_188]
0x18003f9b9  lea     r15, [r14+rdi*8]
0x18003f9bd  lea     r9, [rsp+1F0h+var_1A0]
0x18003f9c2  mov     [rsp+1F0h+var_1D0], r15
0x18003f9c7  lea     r8, [rsp+1F0h+var_18C]
0x18003f9cc  mov     edx, edi
0x18003f9ce  mov     rax, [rcx]
0x18003f9d1  mov     rax, [rax+40h]
0x18003f9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9da  mov     ebx, eax
0x18003f9dc  test    eax, eax
0x18003f9de  jnz     loc_18003FAE9
0x18003f9e4  mov     r9, [r15]
0x18003f9e7  test    r9, r9
0x18003f9ea  jz      short loc_18003FA28
0x18003f9ec  cmp     edi, 1
0x18003f9ef  jnz     short loc_18003F9F7
0x18003f9f1  mov     r9, r13
0x18003f9f4  mov     [r15], r13
0x18003f9f7  mov     rcx, [rsp+1F0h+var_198]
0x18003f9fc  xor     r8d, r8d
0x18003f9ff  cmp     [rsp+1F0h+var_18C], 80h
0x18003fa07  mov     edx, edi
0x18003fa09  cmovz   r8d, dword ptr [rsp+1F0h+var_1A0]
0x18003fa0f  mov     rax, [rcx]
0x18003fa12  mov     rax, [rax+0A0h]
0x18003fa19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa1e  mov     ebx, eax
0x18003fa20  test    eax, eax
0x18003fa22  jnz     loc_18003FAE9
0x18003fa28  inc     edi
0x18003fa2a  jmp     loc_18003F991
0x18003fa2f  mov     rcx, [rsp+1F0h+var_198]
0x18003fa34  mov     rax, [rcx]
0x18003fa37  mov     rax, [rax+90h]
0x18003fa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa43  mov     ebx, eax
0x18003fa45  test    eax, eax
0x18003fa47  jnz     loc_18003FAE9
0x18003fa4d  movaps  xmm0, [rbp+0F0h+var_140]
0x18003fa51  lea     r9, [rbp+0F0h+var_160]
  ... truncated ...
```
