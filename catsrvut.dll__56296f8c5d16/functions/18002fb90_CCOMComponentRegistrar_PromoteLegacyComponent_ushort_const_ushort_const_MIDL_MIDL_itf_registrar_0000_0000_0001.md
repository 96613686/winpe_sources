# CCOMComponentRegistrar::PromoteLegacyComponent(ushort const *,ushort const *,__MIDL___MIDL_itf_registrar_0000_0000_0001)

- ea: `0x18002fb90`
- end: `0x1800300c5`
- name: `?PromoteLegacyComponent@CCOMComponentRegistrar@@UEAAJPEBG0W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `1333`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum __MIDL___MIDL_itf_registrar_0000_0000_0001)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002b3a4`
- `0x18002fb90`
- `0x180055822`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fc2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fc2c`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002fcb6`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002fcb6`
- `CLBCatQ!ServerGetApplicationType` at `0x18002fdd2`
- `CLBCatQ!ServerGetApplicationType` at `0x18002fdd2`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::PromoteLegacyComponent(
        _DWORD *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT Instance; // ebx
  int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+64h] [rbp-9Ch] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  int *v18; // [rsp+78h] [rbp-88h]
  struct _GUID v19; // [rsp+80h] [rbp-80h] BYREF
  __int128 v20; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID Buf1; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v22[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v23; // [rsp+C0h] [rbp-40h]
  int v24; // [rsp+C4h] [rbp-3Ch]
  struct _GUID *v25; // [rsp+C8h] [rbp-38h]
  int v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+D4h] [rbp-2Ch]
  int v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+DCh] [rbp-24h]
  unsigned int *v30; // [rsp+E0h] [rbp-20h]
  int v31; // [rsp+E8h] [rbp-18h]
  int v32; // [rsp+ECh] [rbp-14h]
  int v33; // [rsp+F0h] [rbp-10h]
  int v34; // [rsp+F4h] [rbp-Ch]
  _QWORD v35[2]; // [rsp+100h] [rbp+0h] BYREF
  int v36; // [rsp+110h] [rbp+10h]
  int v37; // [rsp+114h] [rbp+14h]
  struct _GUID *p_Buf1; // [rsp+118h] [rbp+18h]
  int v39; // [rsp+120h] [rbp+20h]
  int v40; // [rsp+124h] [rbp+24h]
  int v41; // [rsp+128h] [rbp+28h]
  int v42; // [rsp+12Ch] [rbp+2Ch]
  GUID *v43; // [rsp+130h] [rbp+30h]
  int v44; // [rsp+138h] [rbp+38h]
  int v45; // [rsp+13Ch] [rbp+3Ch]
  int v46; // [rsp+140h] [rbp+40h]
  int v47; // [rsp+144h] [rbp+44h]
  unsigned int *v48; // [rsp+148h] [rbp+48h]
  int v49; // [rsp+150h] [rbp+50h]
  int v50; // [rsp+154h] [rbp+54h]
  int v51; // [rsp+158h] [rbp+58h]
  int v52; // [rsp+15Ch] [rbp+5Ch]

  ppv = 0;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v18 = 0;
  v14 = 0;
  v17 = 0;
  v19 = 0;
  Buf1 = 0;
  v20 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ResolveAppIdFromName(ppv, a2, &v19, &Buf1);
    if ( Instance >= 0 )
    {
      if ( memcmp_0(&Buf1, &GUID_DefaultAppPartition, 0x10u) )
      {
        Instance = -2146367461;
        goto LABEL_39;
      }
      if ( a4 == 4096 )
      {
        a4 = 2;
      }
      else if ( a4 == 3 || !a4 )
      {
LABEL_38:
        Instance = -2147024809;
        goto LABEL_39;
      }
      a1[42] = a4;
      v14 = a4;
      Instance = CLSIDFromStringByBitness(a3, &v20, a4);
      if ( Instance < 0 )
        goto LABEL_39;
      v22[1] = 0;
      v23 = 72;
      v22[0] = &v20;
      v25 = &v19;
      v28 = 72;
      v30 = &v14;
      v32 = 1;
      v24 = 16;
      v26 = 0;
      v27 = 9;
      v29 = 16;
      v31 = 0;
      v33 = 19;
      v34 = 4;
      Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   &didCOMSERVICES,
                   &tidCOMSERVICES_LEGACYCLASSES,
                   v22,
                   3,
                   1,
                   0x800000,
                   &v12);
      if ( Instance < 0 )
        goto LABEL_39;
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
      if ( Instance < 0 )
        goto LABEL_39;
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
      if ( Instance < 0 )
        goto LABEL_39;
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
      Instance = v9;
      if ( v9 != -2146367487 )
      {
        if ( v9 >= 0 )
        {
          Instance = ServerGetApplicationType(ppv, &v19, &v17);
          if ( Instance >= 0 )
          {
            if ( (a4 & v17) != 0 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 5, 0);
              if ( Instance >= 0 )
              {
                if ( v18 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 8, 0);
                  if ( Instance >= 0 )
                  {
                    v15 = *v18;
                    Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 136LL))(v12);
                    if ( Instance >= 0 )
                    {
                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 96LL))(v12);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(_DWORD *, const unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
                                     a1,
                                     a2,
                                     a3,
                                     a4);
                        if ( Instance >= 0 && !v15 )
                        {
                          v35[1] = 0;
                          v36 = 72;
                          v35[0] = &v20;
                          p_Buf1 = &Buf1;
                          v41 = 72;
                          v46 = 72;
                          v43 = &GUID_NULL;
                          v48 = &v14;
                          v40 = 1;
                          v52 = 4;
                          v37 = 16;
                          v39 = 0;
                          v42 = 16;
                          v44 = 0;
                          v45 = 2;
                          v47 = 16;
                          v49 = 0;
                          v50 = 3;
                          v51 = 19;
                          Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                       ppv,
                                       &didCOMSERVICES,
                                       &tidCOMSERVICES_CLASSES_INTERNAL,
                                       v35,
                                       4,
                                       1,
                                       0x800000,
                                       &v13);
                          if ( Instance >= 0 )
                          {
                            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
                            if ( Instance >= 0 )
                            {
                              Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
                              if ( Instance >= 0 )
                              {
                                v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
                                Instance = v10;
                                if ( v10 == -2146367487 )
                                {
                                  Instance = -2147418113;
                                }
                                else if ( v10 >= 0 )
                                {
                                  Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 128LL))(v13);
                                  if ( Instance >= 0 )
                                  {
                                    Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v13 + 160LL))(
                                                 v13,
                                                 47,
                                                 0,
                                                 &v15);
                                    if ( Instance >= 0 )
                                    {
                                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 144LL))(v13);
                                      if ( Instance >= 0 )
                                        Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 96LL))(v13);
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  Instance = -2146368510;
                }
              }
            }
            else
            {
              Instance = -2146368382;
            }
          }
        }
        goto LABEL_39;
      }
      goto LABEL_38;
    }
  }
LABEL_39:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002fb90  push    rbp
0x18002fb92  push    rbx
0x18002fb93  push    rsi
0x18002fb94  push    rdi
0x18002fb95  push    r12
0x18002fb97  push    r13
0x18002fb99  push    r14
0x18002fb9b  push    r15
0x18002fb9d  lea     rbp, [rsp-78h]
0x18002fba2  sub     rsp, 178h
0x18002fba9  mov     rax, cs:__security_cookie
0x18002fbb0  xor     rax, rsp
0x18002fbb3  mov     [rbp+0B0h+var_50], rax
0x18002fbb7  xor     r12d, r12d
0x18002fbba  xorps   xmm0, xmm0
0x18002fbbd  mov     [rsp+1B0h+var_148], r12
0x18002fbc2  xorps   xmm1, xmm1
0x18002fbc5  mov     [rsp+1B0h+var_160], r12
0x18002fbca  mov     edi, r9d
0x18002fbcd  mov     [rsp+1B0h+var_158], r12
0x18002fbd2  mov     rsi, r8
0x18002fbd5  mov     [rsp+1B0h+var_14C], r12d
0x18002fbda  mov     r14, rdx
0x18002fbdd  mov     [rsp+1B0h+var_138], r12
0x18002fbe2  mov     r15, rcx
0x18002fbe5  mov     [rsp+1B0h+var_150], r12d
0x18002fbea  mov     [rsp+1B0h+var_140], r12d
0x18002fbef  movups  xmmword ptr [rbp+0B0h+var_130.Data1], xmm0
0x18002fbf3  movups  [rbp+0B0h+Buf1], xmm1
0x18002fbf7  movups  [rbp+0B0h+var_120], xmm0
0x18002fbfb  test    rdx, rdx
0x18002fbfe  jz      loc_1800300A0
0x18002fc04  test    r8, r8
0x18002fc07  jz      loc_1800300A0
0x18002fc0d  lea     rax, [rsp+1B0h+var_148]
0x18002fc12  xor     edx, edx; pUnkOuter
0x18002fc14  lea     r9, IID_ISimpleTableDispenser; riid
0x18002fc1b  mov     [rsp+1B0h+ppv], rax; ppv
0x18002fc20  lea     r8d, [r12+1]; dwClsContext
0x18002fc25  lea     rcx, CLSID_STDispenser; rclsid
0x18002fc2c  call    cs:__imp_CoCreateInstance
0x18002fc32  mov     ebx, eax
0x18002fc34  test    eax, eax
0x18002fc36  js      loc_18003005A
0x18002fc3c  mov     rcx, [rsp+1B0h+var_148]; struct ISimpleTableDispenser *
0x18002fc41  lea     r9, [rbp+0B0h+Buf1]; struct _GUID *
0x18002fc45  lea     r8, [rbp+0B0h+var_130]; struct _GUID *
0x18002fc49  mov     rdx, r14; unsigned __int16 *
0x18002fc4c  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18002fc51  mov     ebx, eax
0x18002fc53  test    eax, eax
0x18002fc55  js      loc_18003005A
0x18002fc5b  lea     r13d, [r12+10h]
0x18002fc60  mov     r8d, r13d; Size
0x18002fc63  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18002fc6a  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18002fc6e  call    memcmp_0
0x18002fc73  test    eax, eax
0x18002fc75  jz      short loc_18002FC81
0x18002fc77  mov     ebx, 8011081Bh
0x18002fc7c  jmp     loc_18003005A
0x18002fc81  cmp     edi, 1000h
0x18002fc87  jnz     short loc_18002FC90
0x18002fc89  mov     edi, 2
0x18002fc8e  jmp     short loc_18002FCA1
0x18002fc90  cmp     edi, 3
0x18002fc93  jz      loc_180030055
0x18002fc99  test    edi, edi
0x18002fc9b  jz      loc_180030055
0x18002fca1  mov     r8d, edi
0x18002fca4  mov     [r15+0A8h], edi
0x18002fcab  lea     rdx, [rbp+0B0h+var_120]
0x18002fcaf  mov     [rsp+1B0h+var_150], edi
0x18002fcb3  mov     rcx, rsi
0x18002fcb6  call    cs:__imp_CLSIDFromStringByBitness
0x18002fcbc  mov     ebx, eax
0x18002fcbe  test    eax, eax
0x18002fcc0  js      loc_18003005A
0x18002fcc6  mov     ecx, 48h ; 'H'
0x18002fccb  mov     [rbp+0B0h+var_F8], r12
0x18002fccf  mov     [rbp+0B0h+var_F0], ecx
0x18002fcd2  lea     rax, [rbp+0B0h+var_120]
0x18002fcd6  mov     [rbp+0B0h+var_100], rax
0x18002fcda  lea     rdx, [rsp+1B0h+var_160]
0x18002fcdf  mov     [rsp+1B0h+var_178], rdx
0x18002fce4  lea     rax, [rbp+0B0h+var_130]
0x18002fce8  lea     r8d, [rcx-47h]
0x18002fcec  mov     [rbp+0B0h+var_E8], rax
0x18002fcf0  mov     [rbp+0B0h+var_D8], ecx
0x18002fcf3  lea     rax, [rsp+1B0h+var_150]
0x18002fcf8  mov     rcx, [rsp+1B0h+var_148]
0x18002fcfd  lea     r9, [rbp+0B0h+var_100]
0x18002fd01  mov     [rbp+0B0h+var_D0], rax
0x18002fd05  lea     rdx, didCOMSERVICES
0x18002fd0c  mov     [rbp+0B0h+var_C4], r8d
0x18002fd10  mov     [rbp+0B0h+var_EC], r13d
0x18002fd14  mov     [rbp+0B0h+var_E0], r12d
0x18002fd18  mov     [rbp+0B0h+var_DC], 9
0x18002fd1f  mov     [rbp+0B0h+var_D4], r13d
0x18002fd23  mov     [rbp+0B0h+var_C8], r12d
0x18002fd27  mov     [rbp+0B0h+var_C0], 13h
0x18002fd2e  mov     [rbp+0B0h+var_BC], 4
0x18002fd35  mov     rax, [rcx]
0x18002fd38  mov     [rsp+1B0h+var_180], 800000h
0x18002fd40  mov     [rsp+1B0h+var_188], r8d
0x18002fd45  lea     r8, tidCOMSERVICES_LEGACYCLASSES
0x18002fd4c  mov     [rsp+1B0h+ppv], 3
0x18002fd55  mov     rax, [rax+18h]
0x18002fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd5e  mov     ebx, eax
0x18002fd60  test    eax, eax
0x18002fd62  js      loc_18003005A
0x18002fd68  mov     rcx, [rsp+1B0h+var_160]
0x18002fd6d  mov     rax, [rcx]
0x18002fd70  mov     rax, [rax+18h]
0x18002fd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd79  mov     ebx, eax
0x18002fd7b  test    eax, eax
0x18002fd7d  js      loc_18003005A
0x18002fd83  mov     rcx, [rsp+1B0h+var_160]
0x18002fd88  mov     rax, [rcx]
0x18002fd8b  mov     rax, [rax+20h]
0x18002fd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd94  mov     ebx, eax
0x18002fd96  test    eax, eax
0x18002fd98  js      loc_18003005A
0x18002fd9e  mov     rcx, [rsp+1B0h+var_160]
0x18002fda3  mov     rax, [rcx]
0x18002fda6  mov     rax, [rax+28h]
0x18002fdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdaf  mov     ebx, eax
0x18002fdb1  cmp     eax, 80110801h
0x18002fdb6  jz      loc_180030055
0x18002fdbc  test    eax, eax
0x18002fdbe  js      loc_18003005A
0x18002fdc4  mov     rcx, [rsp+1B0h+var_148]
0x18002fdc9  lea     r8, [rsp+1B0h+var_140]
0x18002fdce  lea     rdx, [rbp+0B0h+var_130]
0x18002fdd2  call    cs:__imp_ServerGetApplicationType
0x18002fdd8  mov     ebx, eax
0x18002fdda  test    eax, eax
0x18002fddc  js      loc_18003005A
0x18002fde2  test    [rsp+1B0h+var_140], edi
0x18002fde6  jnz     short loc_18002FDF2
0x18002fde8  mov     ebx, 80110482h
0x18002fded  jmp     loc_18003005A
0x18002fdf2  mov     rcx, [rsp+1B0h+var_160]
0x18002fdf7  lea     rdx, [rsp+1B0h+var_138]
0x18002fdfc  xor     r9d, r9d
0x18002fdff  mov     [rsp+1B0h+ppv], rdx
0x18002fe04  xor     r8d, r8d
0x18002fe07  mov     rax, [rcx]
0x18002fe0a  lea     edx, [r9+5]
0x18002fe0e  mov     rax, [rax+40h]
0x18002fe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe17  mov     ebx, eax
0x18002fe19  test    eax, eax
0x18002fe1b  js      loc_18003005A
0x18002fe21  cmp     [rsp+1B0h+var_138], r12
0x18002fe26  jnz     short loc_18002FE32
0x18002fe28  mov     ebx, 80110402h
0x18002fe2d  jmp     loc_18003005A
0x18002fe32  mov     rcx, [rsp+1B0h+var_160]
0x18002fe37  lea     rdx, [rsp+1B0h+var_138]
0x18002fe3c  xor     r9d, r9d
0x18002fe3f  mov     [rsp+1B0h+ppv], rdx
0x18002fe44  xor     r8d, r8d
0x18002fe47  mov     rax, [rcx]
0x18002fe4a  lea     edx, [r9+8]
0x18002fe4e  mov     rax, [rax+40h]
0x18002fe52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe57  mov     ebx, eax
0x18002fe59  test    eax, eax
0x18002fe5b  js      loc_18003005A
0x18002fe61  mov     rax, [rsp+1B0h+var_138]
0x18002fe66  mov     ecx, [rax]
0x18002fe68  mov     [rsp+1B0h+var_14C], ecx
0x18002fe6c  mov     rcx, [rsp+1B0h+var_160]
0x18002fe71  mov     rax, [rcx]
0x18002fe74  mov     rax, [rax+88h]
0x18002fe7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe80  mov     ebx, eax
0x18002fe82  test    eax, eax
0x18002fe84  js      loc_18003005A
0x18002fe8a  mov     rcx, [rsp+1B0h+var_160]
0x18002fe8f  mov     rax, [rcx]
0x18002fe92  mov     rax, [rax+60h]
0x18002fe96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe9b  mov     ebx, eax
0x18002fe9d  test    eax, eax
0x18002fe9f  js      loc_18003005A
0x18002fea5  mov     rax, [r15]
0x18002fea8  mov     r9d, edi
0x18002feab  mov     r8, rsi
0x18002feae  mov     rdx, r14
0x18002feb1  mov     rcx, r15
0x18002feb4  mov     rax, [rax+18h]
0x18002feb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002febd  mov     ebx, eax
0x18002febf  test    eax, eax
0x18002fec1  js      loc_18003005A
0x18002fec7  cmp     [rsp+1B0h+var_14C], r12d
0x18002fecc  jnz     loc_18003005A
0x18002fed2  mov     ecx, 48h ; 'H'
0x18002fed7  mov     [rbp+0B0h+var_A8], r12
0x18002fedb  mov     [rbp+0B0h+var_A0], ecx
0x18002fede  lea     rax, [rbp+0B0h+var_120]
0x18002fee2  mov     [rbp+0B0h+var_B0], rax
0x18002fee6  lea     r8, [rsp+1B0h+var_158]
0x18002feeb  mov     [rsp+1B0h+var_178], r8
0x18002fef0  lea     rax, [rbp+0B0h+Buf1]
0x18002fef4  mov     [rbp+0B0h+var_98], rax
0x18002fef8  lea     edx, [rcx-47h]
0x18002fefb  lea     r9d, [rcx-44h]
0x18002feff  mov     [rbp+0B0h+var_88], ecx
0x18002ff02  mov     [rbp+0B0h+var_70], ecx
0x18002ff05  lea     rax, GUID_NULL
0x18002ff0c  mov     rcx, [rsp+1B0h+var_148]
0x18002ff11  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x18002ff18  mov     [rbp+0B0h+var_80], rax
0x18002ff1c  lea     rax, [rsp+1B0h+var_150]
0x18002ff21  mov     [rbp+0B0h+var_68], rax
0x18002ff25  mov     [rbp+0B0h+var_8C], edx
0x18002ff28  mov     [rbp+0B0h+var_54], r9d
0x18002ff2c  mov     [rbp+0B0h+var_9C], r13d
0x18002ff30  mov     [rbp+0B0h+var_90], r12d
0x18002ff34  mov     [rbp+0B0h+var_84], r13d
0x18002ff38  mov     [rbp+0B0h+var_78], r12d
0x18002ff3c  mov     [rbp+0B0h+var_74], 2
0x18002ff43  mov     [rbp+0B0h+var_6C], r13d
0x18002ff47  mov     [rbp+0B0h+var_60], r12d
0x18002ff4b  mov     [rbp+0B0h+var_5C], 3
0x18002ff52  mov     [rbp+0B0h+var_58], 13h
0x18002ff59  mov     rax, [rcx]
0x18002ff5c  mov     [rsp+1B0h+var_180], 800000h
0x18002ff64  mov     [rsp+1B0h+var_188], edx
0x18002ff68  lea     rdx, didCOMSERVICES
0x18002ff6f  mov     [rsp+1B0h+ppv], r9
0x18002ff74  lea     r9, [rbp+0B0h+var_B0]
0x18002ff78  mov     rax, [rax+18h]
0x18002ff7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff81  mov     ebx, eax
0x18002ff83  test    eax, eax
0x18002ff85  js      loc_18003005A
0x18002ff8b  mov     rcx, [rsp+1B0h+var_158]
0x18002ff90  mov     rax, [rcx]
0x18002ff93  mov     rax, [rax+18h]
0x18002ff97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff9c  mov     ebx, eax
0x18002ff9e  test    eax, eax
0x18002ffa0  js      loc_18003005A
0x18002ffa6  mov     rcx, [rsp+1B0h+var_158]
0x18002ffab  mov     rax, [rcx]
0x18002ffae  mov     rax, [rax+20h]
0x18002ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffb7  mov     ebx, eax
0x18002ffb9  test    eax, eax
0x18002ffbb  js      loc_18003005A
0x18002ffc1  mov     rcx, [rsp+1B0h+var_158]
0x18002ffc6  mov     rax, [rcx]
0x18002ffc9  mov     rax, [rax+28h]
0x18002ffcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffd2  mov     ebx, eax
0x18002ffd4  cmp     eax, 80110801h
0x18002ffd9  jnz     short loc_18002FFE2
0x18002ffdb  mov     ebx, 8000FFFFh
0x18002ffe0  jmp     short loc_18003005A
0x18002ffe2  test    eax, eax
0x18002ffe4  js      short loc_18003005A
0x18002ffe6  mov     rcx, [rsp+1B0h+var_158]
0x18002ffeb  mov     rax, [rcx]
0x18002ffee  mov     rax, [rax+80h]
0x18002fff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fffa  mov     ebx, eax
0x18002fffc  test    eax, eax
0x18002fffe  js      short loc_18003005A
0x180030000  mov     rcx, [rsp+1B0h+var_158]
0x180030005  lea     r9, [rsp+1B0h+var_14C]
0x18003000a  xor     r8d, r8d
0x18003000d  mov     rax, [rcx]
0x180030010  lea     edx, [r8+2Fh]
0x180030014  mov     rax, [rax+0A0h]
0x18003001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030020  mov     ebx, eax
0x180030022  test    eax, eax
0x180030024  js      short loc_18003005A
0x180030026  mov     rcx, [rsp+1B0h+var_158]
0x18003002b  mov     rax, [rcx]
0x18003002e  mov     rax, [rax+90h]
0x180030035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003003a  mov     ebx, eax
0x18003003c  test    eax, eax
0x18003003e  js      short loc_18003005A
0x180030040  mov     rcx, [rsp+1B0h+var_158]
0x180030045  mov     rax, [rcx]
0x180030048  mov     rax, [rax+60h]
0x18003004c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030051  mov     ebx, eax
0x180030053  jmp     short loc_18003005A
0x180030055  mov     ebx, 80070057h
  ... truncated ...
```
