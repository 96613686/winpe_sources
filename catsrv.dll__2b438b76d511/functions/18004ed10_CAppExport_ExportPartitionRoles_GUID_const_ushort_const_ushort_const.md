# CAppExport::ExportPartitionRoles(_GUID const &,ushort const *,ushort const *)

- ea: `0x18004ed10`
- end: `0x18004f29e`
- name: `?ExportPartitionRoles@CAppExport@@AEAAJAEBU_GUID@@PEBG1@Z`
- size: `1422`
- prototype: `int(CAppExport *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004e994`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x18004ed10`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ed9e`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ee89`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f086`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ed9e`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ee89`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004f086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f23b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ef8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f23b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004efbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004efbd`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportPartitionRoles(
        CAppExport *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v8; // r14
  __int64 v9; // r15
  const unsigned __int16 *v10; // r9
  int SimpleTableDispenser; // ebx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  int v17; // eax
  __int64 (*i)(void); // rax
  int v19; // eax
  int j; // esi
  __int64 v21; // r8
  __int64 v22; // [rsp+50h] [rbp-69h] BYREF
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v25; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+70h] [rbp-49h]
  __int64 v27; // [rsp+78h] [rbp-41h] BYREF
  GUID *v28; // [rsp+80h] [rbp-39h] BYREF
  __int64 v29; // [rsp+88h] [rbp-31h]
  int v30; // [rsp+90h] [rbp-29h]
  int v31; // [rsp+94h] [rbp-25h]
  unsigned __int16 *v32; // [rsp+98h] [rbp-21h]
  int v33; // [rsp+A0h] [rbp-19h]
  int v34; // [rsp+A4h] [rbp-15h]
  int v35; // [rsp+A8h] [rbp-11h]
  int v36; // [rsp+ACh] [rbp-Dh]
  const unsigned __int16 *v37; // [rsp+B0h] [rbp-9h] BYREF
  int v38; // [rsp+B8h] [rbp-1h]
  int v39; // [rsp+BCh] [rbp+3h]
  int v40; // [rsp+C0h] [rbp+7h]
  int v41; // [rsp+C4h] [rbp+Bh]
  signed __int64 v42; // [rsp+130h] [rbp+77h] BYREF

  v23 = 0;
  v22 = 0;
  if ( !a3 )
    return 2147942487LL;
  v8 = 0;
  v9 = (int)safe_lstrlenW(a3);
  v37 = v10;
  v38 = 0;
  v39 = -268435455;
  v40 = 130;
  v24 = 0;
  v41 = 2 * safe_lstrlenW(v10) + 2;
  if ( *((_QWORD *)this + 22) )
    goto LABEL_7;
  v42 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v42);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v42, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_7:
    v12 = memcmp_0(&tidCOMSERVICES_ROLECONFIG_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLECONFIG_EXPORT,
                             &v37,
                             1,
                             1,
                             v12 != 0 ? 6 : 4,
                             &v24);
  }
  if ( SimpleTableDispenser < 0 )
    goto LABEL_53;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_53;
  v28 = a2;
  v31 = 16;
  v29 = 0;
  v30 = 72;
  v23 = 0;
  if ( *((_QWORD *)this + 22) )
    goto LABEL_14;
  v42 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v42);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v42, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_14:
    v13 = memcmp_0(tidCOMSERVICES_LT_PARTITIONROLES, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             tidCOMSERVICES_LT_PARTITIONROLES,
                             &v28,
                             1,
                             1,
                             v13 != 0 ? 7 : 5,
                             &v23);
  }
  if ( SimpleTableDispenser >= 0 )
  {
    SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    if ( SimpleTableDispenser >= 0 )
    {
LABEL_17:
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
      if ( v14 )
      {
        SimpleTableDispenser = 0;
        if ( v14 != -2146367487 )
          SimpleTableDispenser = v14;
        if ( SimpleTableDispenser >= 0 )
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 96LL))(v24);
      }
      else
      {
        v26 = 0;
        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 64LL))(v23, 1, 0);
        if ( SimpleTableDispenser >= 0 )
        {
          CoTaskMemFree(v8);
          v15 = v9 + (int)(safe_lstrlenW(v26) + 1) + 1LL;
          v16 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v15, 2u));
          v8 = v16;
          if ( v16 )
          {
            SimpleTableDispenser = StringCchCopyW(v16, v15, a3);
            if ( SimpleTableDispenser >= 0 )
            {
              SimpleTableDispenser = StringCchCatW(v8, v15, L"\\");
              if ( SimpleTableDispenser >= 0 )
              {
                SimpleTableDispenser = StringCchCatW(v8, v15, v26);
                if ( SimpleTableDispenser >= 0 )
                {
                  if ( v22 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                  v29 = 0;
                  v28 = &CLSID_SystemApplication;
                  v36 = 2 * v15;
                  v30 = 72;
                  v31 = 16;
                  v32 = v8;
                  v33 = 0;
                  v34 = 1;
                  v35 = 130;
                  v22 = 0;
                  if ( !*((_QWORD *)this + 22) )
                  {
                    v42 = 0;
                    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v42);
                    if ( SimpleTableDispenser < 0 )
                      goto LABEL_30;
                    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v42, 0) )
                      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v42 + 16LL))(v42);
                  }
                  v17 = memcmp_0(&tidCOMSERVICES_ROLECONFIG, &TID_APPLICATION, 0x10u);
                  SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                                           *((_QWORD *)this + 22),
                                           didCOMSERVICES,
                                           &tidCOMSERVICES_ROLECONFIG,
                                           &v28,
                                           2,
                                           1,
                                           v17 != 0 ? 7 : 5,
                                           &v22);
LABEL_30:
                  if ( SimpleTableDispenser >= 0 )
                  {
                    for ( i = *(__int64 (**)(void))(*(_QWORD *)v22 + 24LL);
                          ;
                          i = *(__int64 (**)(void))(*(_QWORD *)v24 + 144LL) )
                    {
                      SimpleTableDispenser = i();
                      if ( SimpleTableDispenser < 0 )
                        break;
                      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
                      if ( v19 )
                      {
                        SimpleTableDispenser = 0;
                        if ( v19 != -2146367487 )
                          SimpleTableDispenser = v19;
                        if ( SimpleTableDispenser >= 0 )
                          goto LABEL_17;
                        break;
                      }
                      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 120LL))(v24);
                      if ( SimpleTableDispenser < 0 )
                        break;
                      for ( j = 0; j < 4; ++j )
                      {
                        v27 = 0;
                        LODWORD(v42) = 0;
                        v25 = 0;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *, unsigned int *, __int64 *))(*(_QWORD *)v22 + 64LL))(
                                                 v22,
                                                 (unsigned int)j,
                                                 &v42,
                                                 &v25,
                                                 &v27);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_53;
                        v21 = 0;
                        if ( (_DWORD)v42 == 128 )
                          v21 = v25;
                        SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v24 + 160LL))(
                                                 v24,
                                                 (unsigned int)j,
                                                 v21,
                                                 v27);
                        if ( SimpleTableDispenser < 0 )
                          goto LABEL_53;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            SimpleTableDispenser = -2147024882;
          }
        }
      }
    }
  }
LABEL_53:
  CoTaskMemFree(v8);
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004ed10  push    rbp
0x18004ed12  push    rbx
0x18004ed13  push    rsi
0x18004ed14  push    rdi
0x18004ed15  push    r12
0x18004ed17  push    r13
0x18004ed19  push    r14
0x18004ed1b  push    r15
0x18004ed1d  lea     rbp, [rsp-1Fh]
0x18004ed22  sub     rsp, 0D8h
0x18004ed29  xor     r13d, r13d
0x18004ed2c  mov     r12, r8
0x18004ed2f  mov     [rbp+57h+var_B8], r13
0x18004ed33  mov     rsi, rdx
0x18004ed36  mov     [rbp+57h+var_C0], r13
0x18004ed3a  mov     rdi, rcx
0x18004ed3d  test    r8, r8
0x18004ed40  jnz     short loc_18004ED4C
0x18004ed42  mov     eax, 80070057h
0x18004ed47  jmp     loc_18004F28A
0x18004ed4c  mov     rcx, r12; unsigned __int16 *
0x18004ed4f  mov     r14, r13
0x18004ed52  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004ed57  mov     rcx, r9; unsigned __int16 *
0x18004ed5a  movsxd  r15, eax
0x18004ed5d  mov     [rbp+57h+var_60], r9
0x18004ed61  mov     [rbp+57h+var_58], r13d
0x18004ed65  mov     [rbp+57h+var_54], 0F0000001h
0x18004ed6c  mov     [rbp+57h+var_50], 82h
0x18004ed73  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004ed78  mov     [rbp+57h+var_B0], r13
0x18004ed7c  lea     eax, ds:2[rax*2]
0x18004ed83  mov     [rbp+57h+var_4C], eax
0x18004ed86  cmp     [rdi+0B0h], r13
0x18004ed8d  jnz     short loc_18004EDCF
0x18004ed8f  lea     rdx, [rbp+57h+arg_10]
0x18004ed93  mov     [rbp+57h+arg_10], r13
0x18004ed97  lea     rcx, IID_ISimpleTableDispenser
0x18004ed9e  call    cs:__imp_GetSimpleTableDispenser
0x18004eda4  mov     ebx, eax
0x18004eda6  test    eax, eax
0x18004eda8  js      loc_18004EE34
0x18004edae  mov     rcx, [rbp+57h+arg_10]
0x18004edb2  xor     eax, eax
0x18004edb4  lock cmpxchg [rdi+0B0h], rcx
0x18004edbd  jz      short loc_18004EDCF
0x18004edbf  mov     rcx, [rbp+57h+arg_10]
0x18004edc3  mov     rax, [rcx]
0x18004edc6  mov     rax, [rax+10h]
0x18004edca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edcf  mov     r8d, 10h; Size
0x18004edd5  lea     rdx, TID_APPLICATION; Buf2
0x18004eddc  lea     rcx, tidCOMSERVICES_ROLECONFIG_EXPORT; Buf1
0x18004ede3  call    memcmp_0
0x18004ede8  mov     rcx, [rdi+0B0h]
0x18004edef  lea     r9, [rbp+57h+var_B0]
0x18004edf3  mov     [rsp+110h+var_D8], r9
0x18004edf8  lea     r8, tidCOMSERVICES_ROLECONFIG_EXPORT
0x18004edff  neg     eax
0x18004ee01  lea     r9, [rbp+57h+var_60]
0x18004ee05  mov     rax, [rcx]
0x18004ee08  sbb     edx, edx
0x18004ee0a  and     edx, 2
0x18004ee0d  add     edx, 4
0x18004ee10  mov     [rsp+110h+var_E0], edx
0x18004ee14  mov     edx, 1
0x18004ee19  mov     rax, [rax+18h]
0x18004ee1d  mov     [rsp+110h+var_E8], edx
0x18004ee21  mov     [rsp+110h+var_F0], rdx
0x18004ee26  lea     rdx, didCOMSERVICES
0x18004ee2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee32  mov     ebx, eax
0x18004ee34  test    ebx, ebx
0x18004ee36  js      loc_18004F238
0x18004ee3c  mov     rcx, [rbp+57h+var_B0]
0x18004ee40  mov     rax, [rcx]
0x18004ee43  mov     rax, [rax+18h]
0x18004ee47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee4c  mov     ebx, eax
0x18004ee4e  test    eax, eax
0x18004ee50  js      loc_18004F238
0x18004ee56  mov     [rbp+57h+var_90], rsi
0x18004ee5a  mov     esi, 10h
0x18004ee5f  mov     [rbp+57h+var_7C], esi
0x18004ee62  mov     [rbp+57h+var_88], r13
0x18004ee66  mov     [rbp+57h+var_80], 48h ; 'H'
0x18004ee6d  mov     [rbp+57h+var_B8], r13
0x18004ee71  cmp     [rdi+0B0h], r13
0x18004ee78  jnz     short loc_18004EEBA
0x18004ee7a  lea     rdx, [rbp+57h+arg_10]
0x18004ee7e  mov     [rbp+57h+arg_10], r13
0x18004ee82  lea     rcx, IID_ISimpleTableDispenser
0x18004ee89  call    cs:__imp_GetSimpleTableDispenser
0x18004ee8f  mov     ebx, eax
0x18004ee91  test    eax, eax
0x18004ee93  js      loc_18004EF1F
0x18004ee99  mov     rcx, [rbp+57h+arg_10]
0x18004ee9d  xor     eax, eax
0x18004ee9f  lock cmpxchg [rdi+0B0h], rcx
0x18004eea8  jz      short loc_18004EEBA
0x18004eeaa  mov     rcx, [rbp+57h+arg_10]
0x18004eeae  mov     rax, [rcx]
0x18004eeb1  mov     rax, [rax+10h]
0x18004eeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeba  mov     r8, rsi; Size
0x18004eebd  lea     rdx, TID_APPLICATION; Buf2
0x18004eec4  lea     rcx, tidCOMSERVICES_LT_PARTITIONROLES; Buf1
0x18004eecb  call    memcmp_0
0x18004eed0  mov     rcx, [rdi+0B0h]
0x18004eed7  lea     r9, [rbp+57h+var_B8]
0x18004eedb  mov     [rsp+110h+var_D8], r9
0x18004eee0  lea     r8, tidCOMSERVICES_LT_PARTITIONROLES
0x18004eee7  neg     eax
0x18004eee9  lea     r9, [rbp+57h+var_90]
0x18004eeed  mov     rax, [rcx]
0x18004eef0  sbb     edx, edx
0x18004eef2  and     edx, 2
0x18004eef5  add     edx, 5
0x18004eef8  mov     [rsp+110h+var_E0], edx
0x18004eefc  lea     rdx, didCOMSERVICES
0x18004ef03  mov     rax, [rax+18h]
0x18004ef07  mov     [rsp+110h+var_E8], 1
0x18004ef0f  mov     [rsp+110h+var_F0], 1
0x18004ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef1d  mov     ebx, eax
0x18004ef1f  test    ebx, ebx
0x18004ef21  js      loc_18004F238
0x18004ef27  mov     rcx, [rbp+57h+var_B8]
0x18004ef2b  mov     rax, [rcx]
0x18004ef2e  mov     rax, [rax+18h]
0x18004ef32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef37  mov     ebx, eax
0x18004ef39  test    eax, eax
0x18004ef3b  js      loc_18004F238
0x18004ef41  mov     rcx, [rbp+57h+var_B8]
0x18004ef45  mov     rax, [rcx]
0x18004ef48  mov     rax, [rax+28h]
0x18004ef4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef51  test    eax, eax
0x18004ef53  jnz     loc_18004F217
0x18004ef59  mov     rcx, [rbp+57h+var_B8]
0x18004ef5d  lea     rdx, [rbp+57h+var_A0]
0x18004ef61  mov     [rbp+57h+var_A0], r13
0x18004ef65  xor     r9d, r9d
0x18004ef68  mov     [rsp+110h+var_F0], rdx
0x18004ef6d  xor     r8d, r8d
0x18004ef70  mov     rax, [rcx]
0x18004ef73  lea     edx, [r9+1]
0x18004ef77  mov     rax, [rax+40h]
0x18004ef7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef80  mov     ebx, eax
0x18004ef82  test    eax, eax
0x18004ef84  js      loc_18004F238
0x18004ef8a  mov     rcx, r14; pv
0x18004ef8d  call    cs:__imp_CoTaskMemFree
0x18004ef93  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x18004ef97  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004ef9c  inc     eax
0x18004ef9e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004efa5  movsxd  rsi, eax
0x18004efa8  mov     eax, 2
0x18004efad  inc     rsi
0x18004efb0  add     rsi, r15
0x18004efb3  mul     rsi
0x18004efb6  cmovb   rax, rcx
0x18004efba  mov     rcx, rax; cb
0x18004efbd  call    cs:__imp_CoTaskMemAlloc
0x18004efc3  mov     r14, rax
0x18004efc6  test    rax, rax
0x18004efc9  jz      loc_18004F210
0x18004efcf  mov     r8, r12; unsigned __int16 *
0x18004efd2  mov     rdx, rsi; unsigned __int64
0x18004efd5  mov     rcx, rax; unsigned __int16 *
0x18004efd8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004efdd  mov     ebx, eax
0x18004efdf  test    eax, eax
0x18004efe1  js      loc_18004F238
0x18004efe7  lea     r8, asc_18005D30C; "\\"
0x18004efee  mov     rdx, rsi; unsigned __int64
0x18004eff1  mov     rcx, r14; unsigned __int16 *
0x18004eff4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004eff9  mov     ebx, eax
0x18004effb  test    eax, eax
0x18004effd  js      loc_18004F238
0x18004f003  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x18004f007  mov     rdx, rsi; unsigned __int64
0x18004f00a  mov     rcx, r14; unsigned __int16 *
0x18004f00d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f012  mov     ebx, eax
0x18004f014  test    eax, eax
0x18004f016  js      loc_18004F238
0x18004f01c  mov     rcx, [rbp+57h+var_C0]
0x18004f020  test    rcx, rcx
0x18004f023  jz      short loc_18004F031
0x18004f025  mov     rax, [rcx]
0x18004f028  mov     rax, [rax+10h]
0x18004f02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f031  lea     rax, CLSID_SystemApplication
0x18004f038  mov     [rbp+57h+var_88], r13
0x18004f03c  mov     [rbp+57h+var_90], rax
0x18004f040  lea     eax, [rsi+rsi]
0x18004f043  mov     [rbp+57h+var_64], eax
0x18004f046  mov     [rbp+57h+var_80], 48h ; 'H'
0x18004f04d  mov     [rbp+57h+var_7C], 10h
0x18004f054  mov     [rbp+57h+var_78], r14
0x18004f058  mov     [rbp+57h+var_70], r13d
0x18004f05c  mov     [rbp+57h+var_6C], 1
0x18004f063  mov     [rbp+57h+var_68], 82h
0x18004f06a  mov     [rbp+57h+var_C0], r13
0x18004f06e  cmp     [rdi+0B0h], r13
0x18004f075  jnz     short loc_18004F0B7
0x18004f077  lea     rdx, [rbp+57h+arg_10]
0x18004f07b  mov     [rbp+57h+arg_10], r13
0x18004f07f  lea     rcx, IID_ISimpleTableDispenser
0x18004f086  call    cs:__imp_GetSimpleTableDispenser
0x18004f08c  mov     ebx, eax
0x18004f08e  test    eax, eax
0x18004f090  js      loc_18004F11F
0x18004f096  mov     rcx, [rbp+57h+arg_10]
0x18004f09a  xor     eax, eax
0x18004f09c  lock cmpxchg [rdi+0B0h], rcx
0x18004f0a5  jz      short loc_18004F0B7
0x18004f0a7  mov     rcx, [rbp+57h+arg_10]
0x18004f0ab  mov     rax, [rcx]
0x18004f0ae  mov     rax, [rax+10h]
0x18004f0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0b7  mov     r8d, 10h; Size
0x18004f0bd  lea     rdx, TID_APPLICATION; Buf2
0x18004f0c4  lea     rcx, tidCOMSERVICES_ROLECONFIG; Buf1
0x18004f0cb  call    memcmp_0
0x18004f0d0  mov     rcx, [rdi+0B0h]
0x18004f0d7  lea     r8, [rbp+57h+var_C0]
0x18004f0db  mov     [rsp+110h+var_D8], r8
0x18004f0e0  lea     r9, [rbp+57h+var_90]
0x18004f0e4  neg     eax
0x18004f0e6  lea     r8, tidCOMSERVICES_ROLECONFIG
0x18004f0ed  mov     rax, [rcx]
0x18004f0f0  sbb     edx, edx
0x18004f0f2  and     edx, 2
0x18004f0f5  add     edx, 5
0x18004f0f8  mov     [rsp+110h+var_E0], edx
0x18004f0fc  lea     rdx, didCOMSERVICES
0x18004f103  mov     rax, [rax+18h]
0x18004f107  mov     [rsp+110h+var_E8], 1
0x18004f10f  mov     [rsp+110h+var_F0], 2
0x18004f118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f11d  mov     ebx, eax
0x18004f11f  test    ebx, ebx
0x18004f121  js      loc_18004F238
0x18004f127  mov     rcx, [rbp+57h+var_C0]
0x18004f12b  mov     rax, [rcx]
0x18004f12e  mov     rax, [rax+18h]
0x18004f132  jmp     loc_18004F1EA
0x18004f137  mov     rcx, [rbp+57h+var_C0]
0x18004f13b  mov     rax, [rcx]
0x18004f13e  mov     rax, [rax+28h]
0x18004f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f147  test    eax, eax
0x18004f149  jnz     loc_18004F1FB
0x18004f14f  mov     rcx, [rbp+57h+var_B0]
0x18004f153  mov     rax, [rcx]
0x18004f156  mov     rax, [rax+78h]
0x18004f15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f15f  mov     ebx, eax
0x18004f161  test    eax, eax
0x18004f163  js      loc_18004F238
0x18004f169  mov     esi, r13d
0x18004f16c  cmp     esi, 4
0x18004f16f  jge     short loc_18004F1DC
0x18004f171  mov     rcx, [rbp+57h+var_C0]
0x18004f175  lea     rdx, [rbp+57h+var_98]
0x18004f179  mov     [rbp+57h+var_98], r13
0x18004f17d  lea     r9, [rbp+57h+var_A8]
0x18004f181  mov     dword ptr [rbp+57h+arg_10], r13d
0x18004f185  lea     r8, [rbp+57h+arg_10]
0x18004f189  mov     [rbp+57h+var_A8], r13d
0x18004f18d  mov     rax, [rcx]
0x18004f190  mov     [rsp+110h+var_F0], rdx
0x18004f195  mov     edx, esi
0x18004f197  mov     rax, [rax+40h]
0x18004f19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1a0  mov     ebx, eax
0x18004f1a2  test    eax, eax
0x18004f1a4  js      loc_18004F238
0x18004f1aa  mov     rcx, [rbp+57h+var_B0]
0x18004f1ae  mov     r8d, r13d
0x18004f1b1  cmp     dword ptr [rbp+57h+arg_10], 80h
0x18004f1b8  mov     edx, esi
0x18004f1ba  mov     r9, [rbp+57h+var_98]
0x18004f1be  cmovz   r8d, [rbp+57h+var_A8]
0x18004f1c3  mov     rax, [rcx]
0x18004f1c6  mov     rax, [rax+0A0h]
0x18004f1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1d2  mov     ebx, eax
0x18004f1d4  test    eax, eax
0x18004f1d6  js      short loc_18004F238
0x18004f1d8  inc     esi
0x18004f1da  jmp     short loc_18004F16C
0x18004f1dc  mov     rcx, [rbp+57h+var_B0]
0x18004f1e0  mov     rax, [rcx]
  ... truncated ...
```
