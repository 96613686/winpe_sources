# CCOMComponentRegistrar::ImportComponentAsLegacy(ushort const *,ushort const *,__MIDL___MIDL_itf_registrar_0000_0000_0001)

- ea: `0x18002f050`
- end: `0x18002f40e`
- name: `?ImportComponentAsLegacy@CCOMComponentRegistrar@@UEAAJPEBG0W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z`
- size: `958`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum __MIDL___MIDL_itf_registrar_0000_0000_0001)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007208`
- `0x18002b3a4`
- `0x18002f050`
- `0x18002f614`
- `0x18002f750`
- `0x180055822`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f0ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f0ec`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002f16c`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18002f16c`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::ImportComponentAsLegacy(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT Instance; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct ISimpleTableDispenser *v12; // [rsp+30h] [rbp-69h]
  __int64 v13; // [rsp+50h] [rbp-49h] BYREF
  int v14; // [rsp+58h] [rbp-41h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v16; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v17; // [rsp+6Ch] [rbp-2Dh] BYREF
  unsigned int v18; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v19; // [rsp+74h] [rbp-25h] BYREF
  int v20; // [rsp+78h] [rbp-21h] BYREF
  int v21; // [rsp+7Ch] [rbp-1Dh] BYREF
  struct _GUID Buf1; // [rsp+80h] [rbp-19h] BYREF
  __int128 v23; // [rsp+90h] [rbp-9h] BYREF
  struct _GUID v24; // [rsp+A0h] [rbp+7h] BYREF

  ppv = 0;
  v13 = 0;
  v14 = 0;
  v21 = 0;
  v20 = 1;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v24 = 0;
  Buf1 = 0;
  v23 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ResolveAppIdFromName(ppv, a2, &v24, &Buf1);
    if ( Instance >= 0 )
    {
      if ( memcmp_0(&Buf1, &GUID_DefaultAppPartition, 0x10u) )
        goto LABEL_18;
      if ( a4 == 4096 )
      {
        a4 = 2;
      }
      else if ( a4 == 3 || !a4 )
      {
        Instance = -2147024809;
        goto LABEL_34;
      }
      *(_DWORD *)(a1 + 168) = a4;
      v19 = a4;
      Instance = CLSIDFromStringByBitness(a3, &v23, a4);
      if ( Instance < 0 )
        goto LABEL_34;
      Instance = CCOMComponentRegistrar::IsClassComplusConfigured(v9, ppv, &v23, *(unsigned int *)(a1 + 168), &v14);
      if ( Instance < 0 )
        goto LABEL_34;
      if ( !v14 )
      {
        Instance = CCOMComponentRegistrar::IsClassLegacyConfigured(v10, ppv, &v23, *(unsigned int *)(a1 + 168), &v14);
        if ( Instance < 0 )
          goto LABEL_34;
        if ( !v14 )
        {
          Instance = GetSomeApplicationProperties(&v24, &Buf1, &v16, &v17, 0, &v18, v12, 0);
          if ( Instance < 0 )
            goto LABEL_34;
          if ( !memcmp_0(&Buf1, &GUID_DefaultAppPartition, 0x10u) )
          {
            if ( v16 || !v17 || v18 )
            {
              Instance = -2146368470;
            }
            else
            {
              Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                           ppv,
                           &didCOMSERVICES,
                           &tidCOMSERVICES_LEGACYCLASSES_INTERNAL,
                           0,
                           0,
                           1,
                           0x800000,
                           &v13);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
                if ( Instance >= 0 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 120LL))(v13);
                  if ( Instance >= 0 )
                  {
                    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v13 + 160LL))(
                                 v13,
                                 0,
                                 0,
                                 &v23);
                    if ( Instance >= 0 )
                    {
                      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v13 + 160LL))(
                                   v13,
                                   1,
                                   0,
                                   &v19);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct _GUID *))(*(_QWORD *)v13 + 160LL))(
                                     v13,
                                     2,
                                     0,
                                     &v24);
                        if ( Instance >= 0 )
                        {
                          Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v13 + 160LL))(
                                       v13,
                                       3,
                                       0,
                                       &v20);
                          if ( Instance >= 0 )
                          {
                            Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v13
                                                                                                  + 160LL))(
                                         v13,
                                         4,
                                         0,
                                         &v21);
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
            goto LABEL_34;
          }
LABEL_18:
          Instance = -2146367461;
          goto LABEL_34;
        }
      }
      Instance = -2146368508;
    }
  }
LABEL_34:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002f050  push    rbp
0x18002f052  push    rbx
0x18002f053  push    rsi
0x18002f054  push    rdi
0x18002f055  push    r12
0x18002f057  push    r14
0x18002f059  push    r15
0x18002f05b  lea     rbp, [rsp-27h]
0x18002f060  sub     rsp, 0C0h
0x18002f067  mov     rax, cs:__security_cookie
0x18002f06e  xor     rax, rsp
0x18002f071  mov     [rbp+57h+var_40], rax
0x18002f075  xor     r12d, r12d
0x18002f078  xorps   xmm0, xmm0
0x18002f07b  mov     [rbp+57h+var_90], r12
0x18002f07f  mov     r14, rcx
0x18002f082  mov     [rbp+57h+var_A0], r12
0x18002f086  xorps   xmm1, xmm1
0x18002f089  mov     [rbp+57h+var_98], r12d
0x18002f08d  mov     edi, r9d
0x18002f090  mov     [rbp+57h+var_74], r12d
0x18002f094  lea     ecx, [r12+1]
0x18002f099  mov     [rbp+57h+var_78], ecx
0x18002f09c  mov     rsi, r8
0x18002f09f  mov     [rbp+57h+var_88], r12d
0x18002f0a3  mov     r15, rdx
0x18002f0a6  mov     [rbp+57h+var_84], r12d
0x18002f0aa  mov     [rbp+57h+var_80], r12d
0x18002f0ae  mov     [rbp+57h+var_7C], r12d
0x18002f0b2  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18002f0b6  movups  [rbp+57h+Buf1], xmm1
0x18002f0ba  movups  [rbp+57h+var_60], xmm0
0x18002f0be  test    rdx, rdx
0x18002f0c1  jz      loc_18002F3EB
0x18002f0c7  test    r8, r8
0x18002f0ca  jz      loc_18002F3EB
0x18002f0d0  lea     rax, [rbp+57h+var_90]
0x18002f0d4  mov     r8d, ecx; dwClsContext
0x18002f0d7  lea     rcx, CLSID_STDispenser; rclsid
0x18002f0de  mov     [rsp+0F0h+ppv], rax; ppv
0x18002f0e3  lea     r9, IID_ISimpleTableDispenser; riid
0x18002f0ea  xor     edx, edx; pUnkOuter
0x18002f0ec  call    cs:__imp_CoCreateInstance
0x18002f0f2  mov     ebx, eax
0x18002f0f4  test    eax, eax
0x18002f0f6  js      loc_18002F3BD
0x18002f0fc  mov     rcx, [rbp+57h+var_90]; struct ISimpleTableDispenser *
0x18002f100  lea     r9, [rbp+57h+Buf1]; struct _GUID *
0x18002f104  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x18002f108  mov     rdx, r15; unsigned __int16 *
0x18002f10b  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18002f110  mov     ebx, eax
0x18002f112  test    eax, eax
0x18002f114  js      loc_18002F3BD
0x18002f11a  lea     r15d, [r12+10h]
0x18002f11f  mov     r8d, r15d; Size
0x18002f122  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18002f129  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002f12d  call    memcmp_0
0x18002f132  test    eax, eax
0x18002f134  jnz     loc_18002F229
0x18002f13a  cmp     edi, 1000h
0x18002f140  jnz     short loc_18002F147
0x18002f142  lea     edi, [rax+2]
0x18002f145  jmp     short loc_18002F158
0x18002f147  cmp     edi, 3
0x18002f14a  jz      loc_18002F3B8
0x18002f150  test    edi, edi
0x18002f152  jz      loc_18002F3B8
0x18002f158  mov     r8d, edi
0x18002f15b  mov     [r14+0A8h], edi
0x18002f162  lea     rdx, [rbp+57h+var_60]
0x18002f166  mov     [rbp+57h+var_7C], edi
0x18002f169  mov     rcx, rsi
0x18002f16c  call    cs:__imp_CLSIDFromStringByBitness
0x18002f172  mov     ebx, eax
0x18002f174  test    eax, eax
0x18002f176  js      loc_18002F3BD
0x18002f17c  mov     r9d, [r14+0A8h]
0x18002f183  lea     rax, [rbp+57h+var_98]
0x18002f187  mov     rdx, [rbp+57h+var_90]
0x18002f18b  lea     r8, [rbp+57h+var_60]
0x18002f18f  mov     [rsp+0F0h+ppv], rax
0x18002f194  call    ?IsClassComplusConfigured@CCOMComponentRegistrar@@AEAAJPEAUISimpleTableDispenser@@PEAU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAH@Z; CCOMComponentRegistrar::IsClassComplusConfigured(ISimpleTableDispenser *,_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001,int *)
0x18002f199  mov     ebx, eax
0x18002f19b  test    eax, eax
0x18002f19d  js      loc_18002F3BD
0x18002f1a3  cmp     [rbp+57h+var_98], r12d
0x18002f1a7  jz      short loc_18002F1B3
0x18002f1a9  mov     ebx, 80110404h
0x18002f1ae  jmp     loc_18002F3BD
0x18002f1b3  mov     r9d, [r14+0A8h]
0x18002f1ba  lea     rax, [rbp+57h+var_98]
0x18002f1be  mov     rdx, [rbp+57h+var_90]
0x18002f1c2  lea     r8, [rbp+57h+var_60]
0x18002f1c6  mov     [rsp+0F0h+ppv], rax
0x18002f1cb  call    ?IsClassLegacyConfigured@CCOMComponentRegistrar@@AEAAJPEAUISimpleTableDispenser@@PEAU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAH@Z; CCOMComponentRegistrar::IsClassLegacyConfigured(ISimpleTableDispenser *,_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001,int *)
0x18002f1d0  mov     ebx, eax
0x18002f1d2  test    eax, eax
0x18002f1d4  js      loc_18002F3BD
0x18002f1da  cmp     [rbp+57h+var_98], r12d
0x18002f1de  jnz     short loc_18002F1A9
0x18002f1e0  lea     rax, [rbp+57h+var_80]
0x18002f1e4  mov     [rsp+0F0h+var_B8], r12; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x18002f1e9  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18002f1ee  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18002f1f2  lea     r8, [rbp+57h+var_88]; unsigned int *
0x18002f1f6  mov     [rsp+0F0h+ppv], r12; unsigned int *
0x18002f1fb  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x18002f1ff  lea     rcx, [rbp+57h+var_50]; struct _GUID *
0x18002f203  call    ?GetSomeApplicationProperties@@YAJAEBU_GUID@@PEAU1@PEAK2222PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; GetSomeApplicationProperties(_GUID const &,_GUID *,ulong *,ulong *,ulong *,ulong *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x18002f208  mov     ebx, eax
0x18002f20a  test    eax, eax
0x18002f20c  js      loc_18002F3BD
0x18002f212  mov     r8, r15; Size
0x18002f215  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18002f21c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002f220  call    memcmp_0
0x18002f225  test    eax, eax
0x18002f227  jz      short loc_18002F233
0x18002f229  mov     ebx, 8011081Bh
0x18002f22e  jmp     loc_18002F3BD
0x18002f233  cmp     [rbp+57h+var_88], r12d
0x18002f237  jnz     loc_18002F3B1
0x18002f23d  cmp     [rbp+57h+var_84], r12d
0x18002f241  jz      loc_18002F3B1
0x18002f247  cmp     [rbp+57h+var_80], r12d
0x18002f24b  jnz     loc_18002F3B1
0x18002f251  mov     rcx, [rbp+57h+var_90]
0x18002f255  lea     rdx, [rbp+57h+var_A0]
0x18002f259  mov     [rsp+0F0h+var_B8], rdx
0x18002f25e  lea     r8, tidCOMSERVICES_LEGACYCLASSES_INTERNAL
0x18002f265  mov     dword ptr [rsp+0F0h+var_C0], 800000h
0x18002f26d  lea     rdx, didCOMSERVICES
0x18002f274  mov     edi, 1
0x18002f279  xor     r9d, r9d
0x18002f27c  mov     rax, [rcx]
0x18002f27f  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18002f283  mov     [rsp+0F0h+ppv], r12
0x18002f288  mov     rax, [rax+18h]
0x18002f28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f291  mov     ebx, eax
0x18002f293  test    eax, eax
0x18002f295  js      loc_18002F3BD
0x18002f29b  mov     rcx, [rbp+57h+var_A0]
0x18002f29f  mov     rax, [rcx]
0x18002f2a2  mov     rax, [rax+18h]
0x18002f2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ab  mov     ebx, eax
0x18002f2ad  test    eax, eax
0x18002f2af  js      loc_18002F3BD
0x18002f2b5  mov     rcx, [rbp+57h+var_A0]
0x18002f2b9  mov     rax, [rcx]
0x18002f2bc  mov     rax, [rax+78h]
0x18002f2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2c5  mov     ebx, eax
0x18002f2c7  test    eax, eax
0x18002f2c9  js      loc_18002F3BD
0x18002f2cf  mov     rcx, [rbp+57h+var_A0]
0x18002f2d3  lea     r9, [rbp+57h+var_60]
0x18002f2d7  xor     r8d, r8d
0x18002f2da  xor     edx, edx
0x18002f2dc  mov     rax, [rcx]
0x18002f2df  mov     rax, [rax+0A0h]
0x18002f2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2eb  mov     ebx, eax
0x18002f2ed  test    eax, eax
0x18002f2ef  js      loc_18002F3BD
0x18002f2f5  mov     rcx, [rbp+57h+var_A0]
0x18002f2f9  lea     r9, [rbp+57h+var_7C]
0x18002f2fd  xor     r8d, r8d
0x18002f300  mov     edx, edi
0x18002f302  mov     rax, [rcx]
0x18002f305  mov     rax, [rax+0A0h]
0x18002f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f311  mov     ebx, eax
0x18002f313  test    eax, eax
0x18002f315  js      loc_18002F3BD
0x18002f31b  mov     rcx, [rbp+57h+var_A0]
0x18002f31f  lea     r9, [rbp+57h+var_50]
0x18002f323  xor     r8d, r8d
0x18002f326  lea     edx, [rdi+1]
0x18002f329  mov     rax, [rcx]
0x18002f32c  mov     rax, [rax+0A0h]
0x18002f333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f338  mov     ebx, eax
0x18002f33a  test    eax, eax
0x18002f33c  js      short loc_18002F3BD
0x18002f33e  mov     rcx, [rbp+57h+var_A0]
0x18002f342  lea     r9, [rbp+57h+var_78]
0x18002f346  xor     r8d, r8d
0x18002f349  lea     edx, [rdi+2]
0x18002f34c  mov     rax, [rcx]
0x18002f34f  mov     rax, [rax+0A0h]
0x18002f356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f35b  mov     ebx, eax
0x18002f35d  test    eax, eax
0x18002f35f  js      short loc_18002F3BD
0x18002f361  mov     rcx, [rbp+57h+var_A0]
0x18002f365  lea     r9, [rbp+57h+var_74]
0x18002f369  xor     r8d, r8d
0x18002f36c  lea     edx, [rdi+3]
0x18002f36f  mov     rax, [rcx]
0x18002f372  mov     rax, [rax+0A0h]
0x18002f379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f37e  mov     ebx, eax
0x18002f380  test    eax, eax
0x18002f382  js      short loc_18002F3BD
0x18002f384  mov     rcx, [rbp+57h+var_A0]
0x18002f388  mov     rax, [rcx]
0x18002f38b  mov     rax, [rax+90h]
0x18002f392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f397  mov     ebx, eax
0x18002f399  test    eax, eax
0x18002f39b  js      short loc_18002F3BD
0x18002f39d  mov     rcx, [rbp+57h+var_A0]
0x18002f3a1  mov     rax, [rcx]
0x18002f3a4  mov     rax, [rax+60h]
0x18002f3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ad  mov     ebx, eax
0x18002f3af  jmp     short loc_18002F3BD
0x18002f3b1  mov     ebx, 8011042Ah
0x18002f3b6  jmp     short loc_18002F3BD
0x18002f3b8  mov     ebx, 80070057h
0x18002f3bd  mov     rcx, [rbp+57h+var_90]
0x18002f3c1  test    rcx, rcx
0x18002f3c4  jz      short loc_18002F3D2
0x18002f3c6  mov     rax, [rcx]
0x18002f3c9  mov     rax, [rax+10h]
0x18002f3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3d2  mov     rcx, [rbp+57h+var_A0]
0x18002f3d6  test    rcx, rcx
0x18002f3d9  jz      short loc_18002F3E7
0x18002f3db  mov     rax, [rcx]
0x18002f3de  mov     rax, [rax+10h]
0x18002f3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3e7  mov     eax, ebx
0x18002f3e9  jmp     short loc_18002F3F0
0x18002f3eb  mov     eax, 80070057h
0x18002f3f0  mov     rcx, [rbp+57h+var_40]
0x18002f3f4  xor     rcx, rsp; StackCookie
0x18002f3f7  call    __security_check_cookie
0x18002f3fc  add     rsp, 0C0h
0x18002f403  pop     r15
0x18002f405  pop     r14
0x18002f407  pop     r12
0x18002f409  pop     rdi
0x18002f40a  pop     rsi
0x18002f40b  pop     rbx
0x18002f40c  pop     rbp
0x18002f40d  retn
```
