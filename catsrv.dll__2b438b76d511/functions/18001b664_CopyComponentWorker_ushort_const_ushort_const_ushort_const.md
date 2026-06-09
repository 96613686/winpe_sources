# CopyComponentWorker(ushort const *,ushort const *,ushort const *)

- ea: `0x18001b664`
- end: `0x18001bb68`
- name: `?CopyComponentWorker@@YAJPEBG00@Z`
- size: `1284`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b550`
- `0x18001bf9c`

## callees

- `0x18001b3a0`
- `0x18001b664`
- `0x18001c774`
- `0x18001c934`
- `0x18001cbdc`
- `0x180031000`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001b7c7`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001b7c7`
- `CLBCatQ!ServerGetApplicationType` at `0x18001b787`
- `CLBCatQ!ServerGetApplicationType` at `0x18001b867`
- `CLBCatQ!ServerGetApplicationType` at `0x18001b787`
- `CLBCatQ!ServerGetApplicationType` at `0x18001b867`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b709`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b709`

## pseudocode

```c
__int64 __fastcall CopyComponentWorker(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int Instance; // ebx
  unsigned int v7; // edi
  int v8; // eax
  int v9; // eax
  unsigned int i; // edi
  int v11; // eax
  struct _GUID *p_Buf2; // r9
  __int64 v13; // r8
  int v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID *v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  int v23; // [rsp+7Ch] [rbp-84h] BYREF
  int v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+84h] [rbp-7Ch] BYREF
  int v26; // [rsp+88h] [rbp-78h] BYREF
  int v27; // [rsp+8Ch] [rbp-74h] BYREF
  struct _GUID Buf2; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v29; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v30; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v31; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID Buf1; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v33[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F4h] [rbp-Ch]
  struct _GUID *p_Buf1; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+100h] [rbp+0h]
  int v38; // [rsp+104h] [rbp+4h]
  int v39; // [rsp+108h] [rbp+8h]
  int v40; // [rsp+10Ch] [rbp+Ch]
  int *v41; // [rsp+110h] [rbp+10h]
  int v42; // [rsp+118h] [rbp+18h]
  int v43; // [rsp+11Ch] [rbp+1Ch]
  int v44; // [rsp+120h] [rbp+20h]
  int v45; // [rsp+124h] [rbp+24h]

  ppv = 0;
  v26 = 0;
  v16 = 0;
  v19 = 0;
  v27 = 1;
  v18 = 1;
  v24 = 1;
  v25 = 0;
  v21 = 0;
  v20 = 0;
  v30 = 0;
  v23 = 0;
  v31 = 0;
  v22 = 0;
  v29 = 0;
  Buf1 = 0;
  Buf2 = 0;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ResolveAppIdFromName(ppv, a1, &v31, &Buf1);
    if ( Instance >= 0 )
    {
      Instance = ResolveAppIdFromName(ppv, a3, &v29, &Buf2);
      if ( Instance >= 0 )
      {
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          Instance = -2146367477;
          goto LABEL_52;
        }
        Instance = ServerGetApplicationType(ppv, &v31, &v18);
        if ( Instance >= 0 )
        {
          if ( v18 == 3 )
          {
LABEL_8:
            Instance = -2146367479;
            goto LABEL_52;
          }
          v24 = v18;
          v7 = 0x400000;
          if ( v18 == 1 )
            v7 = 0x200000;
          Instance = CLSIDFromStringByBitness(a2, &v30);
          if ( Instance >= 0 )
          {
            Instance = CheckSourceComponentExists(ppv, &Buf1, &v31, &v30, v7);
            if ( Instance >= 0 )
            {
              v8 = TargetComponentExists(ppv, &Buf2, &v29, &v30, v7, v15, (enum ECOMPONENTLOCATION *)&v22);
              Instance = v8;
              if ( v8 == -2146368455 )
              {
                if ( v22 != 1 )
                  goto LABEL_52;
              }
              else if ( v8 < 0 )
              {
                goto LABEL_52;
              }
              Instance = ValidateSourceAndDestinationApps(ppv, &v31, &v29);
              if ( Instance >= 0 )
              {
                Instance = ServerGetApplicationType(ppv, &v29, &v23);
                if ( Instance >= 0 )
                {
                  if ( (v23 & v18) == 0 )
                  {
                    Instance = -2146368382;
                    goto LABEL_52;
                  }
                  v33[1] = 0;
                  v34 = 72;
                  v33[0] = &v30;
                  p_Buf1 = &Buf1;
                  v39 = 72;
                  v41 = &v24;
                  v35 = 16;
                  v37 = 0;
                  v38 = 6;
                  v40 = 16;
                  v42 = 0;
                  v43 = 8;
                  v44 = 19;
                  v45 = 4;
                  Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64, int, unsigned int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                               ppv,
                               didCOMSERVICES,
                               tidCOMSERVICES_CLASSES,
                               v33,
                               3,
                               1,
                               v7,
                               &v16);
                  if ( Instance >= 0 )
                  {
                    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v16 + 72LL))(
                                 v16,
                                 0,
                                 0,
                                 0,
                                 0,
                                 0,
                                 0,
                                 0,
                                 &v20);
                    if ( Instance >= 0 )
                    {
                      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
                      if ( Instance >= 0 )
                      {
                        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 40LL))(v16);
                        Instance = v9;
                        if ( v9 == -2146367487 )
                          goto LABEL_8;
                        if ( v9 >= 0 )
                        {
                          Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 120LL))(v16);
                          if ( Instance >= 0 )
                          {
                            for ( i = 0; i < v20; ++i )
                            {
                              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, struct _GUID **))(*(_QWORD *)v16 + 64LL))(
                                           v16,
                                           i,
                                           &v25,
                                           &v19,
                                           &v21);
                              if ( Instance < 0 )
                                goto LABEL_52;
                              switch ( i )
                              {
                                case 6u:
                                  p_Buf2 = &Buf2;
                                  break;
                                case 9u:
                                  if ( !v21 )
                                  {
                                    Instance = -2147024809;
                                    goto LABEL_52;
                                  }
                                  p_Buf2 = &v29;
                                  break;
                                case 0x18u:
                                case 0x19u:
                                  p_Buf2 = 0;
                                  v21 = 0;
                                  v19 = 0;
                                  goto LABEL_43;
                                case 0x24u:
                                  v11 = memcmp_0(&Buf2, &GUID_DefaultAppPartition, 0x10u);
                                  p_Buf2 = (struct _GUID *)&v26;
                                  if ( v11 )
                                    p_Buf2 = (struct _GUID *)&v27;
                                  break;
                                default:
                                  p_Buf2 = v21;
                                  goto LABEL_43;
                              }
                              v21 = p_Buf2;
LABEL_43:
                              v13 = 0;
                              if ( v25 == 128 )
                                v13 = v19;
                              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct _GUID *))(*(_QWORD *)v16 + 160LL))(
                                           v16,
                                           i,
                                           v13,
                                           p_Buf2);
                              if ( Instance < 0 )
                                goto LABEL_52;
                            }
                            Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 144LL))(v16);
                            if ( Instance >= 0 )
                            {
                              Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 96LL))(v16);
                              if ( Instance >= 0 )
                              {
                                if ( v16 )
                                {
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                                  v16 = 0;
                                }
                                Instance = UpdateRelatedComponentInfo(ppv, v33, &Buf2, &v30, 1);
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
        }
      }
    }
  }
LABEL_52:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001b664  push    rbp
0x18001b666  push    rbx
0x18001b667  push    rsi
0x18001b668  push    rdi
0x18001b669  push    r12
0x18001b66b  push    r14
0x18001b66d  push    r15
0x18001b66f  lea     rbp, [rsp-40h]
0x18001b674  sub     rsp, 140h
0x18001b67b  mov     rax, cs:__security_cookie
0x18001b682  xor     rax, rsp
0x18001b685  mov     [rbp+70h+var_40], rax
0x18001b689  xor     r15d, r15d
0x18001b68c  lea     rax, [rsp+170h+var_118]
0x18001b691  xorps   xmm0, xmm0
0x18001b694  mov     [rsp+170h+var_118], r15
0x18001b699  xorps   xmm1, xmm1
0x18001b69c  mov     [rbp+70h+var_E8], r15d
0x18001b6a0  mov     rsi, r8
0x18001b6a3  mov     [rsp+170h+var_120], r15
0x18001b6a8  lea     r12d, [r15+1]
0x18001b6ac  mov     [rsp+170h+var_10C], r15d
0x18001b6b1  mov     r14, rdx
0x18001b6b4  mov     [rbp+70h+var_E4], r12d
0x18001b6b8  mov     rdi, rcx
0x18001b6bb  mov     [rsp+170h+var_110], r12d
0x18001b6c0  lea     r9, IID_ISimpleTableDispenser; riid
0x18001b6c7  mov     [rbp+70h+var_F0], r12d
0x18001b6cb  xor     edx, edx; pUnkOuter
0x18001b6cd  mov     [rbp+70h+var_EC], r15d
0x18001b6d1  lea     r8d, [r15+17h]; dwClsContext
0x18001b6d5  mov     [rsp+170h+var_100], r15
0x18001b6da  lea     rcx, CLSID_STDispenser; rclsid
0x18001b6e1  mov     [rsp+170h+var_108], r15d
0x18001b6e6  movups  xmmword ptr [rbp+70h+var_C0.Data1], xmm0
0x18001b6ea  mov     [rsp+170h+var_F4], r15d
0x18001b6ef  movups  xmmword ptr [rbp+70h+var_B0.Data1], xmm1
0x18001b6f3  mov     [rsp+170h+var_F8], r15d
0x18001b6f8  movups  xmmword ptr [rbp+70h+var_D0.Data1], xmm0
0x18001b6fc  mov     [rsp+170h+ppv], rax; ppv
0x18001b701  movups  [rbp+70h+Buf1], xmm1
0x18001b705  movups  [rbp+70h+Buf2], xmm0
0x18001b709  call    cs:__imp_CoCreateInstance
0x18001b70f  mov     ebx, eax
0x18001b711  test    eax, eax
0x18001b713  js      loc_18001BB10
0x18001b719  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001b71e  lea     r9, [rbp+70h+Buf1]; struct _GUID *
0x18001b722  lea     r8, [rbp+70h+var_B0]; struct _GUID *
0x18001b726  mov     rdx, rdi; unsigned __int16 *
0x18001b729  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001b72e  mov     ebx, eax
0x18001b730  test    eax, eax
0x18001b732  js      loc_18001BB10
0x18001b738  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001b73d  lea     r9, [rbp+70h+Buf2]; struct _GUID *
0x18001b741  lea     r8, [rbp+70h+var_D0]; struct _GUID *
0x18001b745  mov     rdx, rsi; unsigned __int16 *
0x18001b748  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001b74d  mov     ebx, eax
0x18001b74f  test    eax, eax
0x18001b751  js      loc_18001BB10
0x18001b757  lea     esi, [r15+10h]
0x18001b75b  mov     r8d, esi; Size
0x18001b75e  lea     rdx, [rbp+70h+Buf2]; Buf2
0x18001b762  lea     rcx, [rbp+70h+Buf1]; Buf1
0x18001b766  call    memcmp_0
0x18001b76b  test    eax, eax
0x18001b76d  jnz     short loc_18001B779
0x18001b76f  mov     ebx, 8011080Bh
0x18001b774  jmp     loc_18001BB10
0x18001b779  mov     rcx, [rsp+170h+var_118]
0x18001b77e  lea     r8, [rsp+170h+var_110]
0x18001b783  lea     rdx, [rbp+70h+var_B0]
0x18001b787  call    cs:__imp_ServerGetApplicationType
0x18001b78d  mov     ebx, eax
0x18001b78f  test    eax, eax
0x18001b791  js      loc_18001BB10
0x18001b797  mov     r8d, [rsp+170h+var_110]
0x18001b79c  cmp     r8d, 3
0x18001b7a0  jnz     short loc_18001B7AC
0x18001b7a2  mov     ebx, 80110809h
0x18001b7a7  jmp     loc_18001BB10
0x18001b7ac  cmp     r8d, r12d
0x18001b7af  mov     [rbp+70h+var_F0], r8d
0x18001b7b3  mov     eax, 200000h
0x18001b7b8  lea     rdx, [rbp+70h+var_C0]
0x18001b7bc  mov     edi, 400000h
0x18001b7c1  mov     rcx, r14
0x18001b7c4  cmovz   edi, eax
0x18001b7c7  call    cs:__imp_CLSIDFromStringByBitness
0x18001b7cd  mov     ebx, eax
0x18001b7cf  test    eax, eax
0x18001b7d1  js      loc_18001BB10
0x18001b7d7  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001b7dc  lea     r9, [rbp+70h+var_C0]; struct _GUID *
0x18001b7e0  lea     r8, [rbp+70h+var_B0]; struct _GUID *
0x18001b7e4  mov     dword ptr [rsp+170h+ppv], edi; unsigned int
0x18001b7e8  lea     rdx, [rbp+70h+Buf1]; struct _GUID *
0x18001b7ec  call    ?CheckSourceComponentExists@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11K@Z; CheckSourceComponentExists(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,ulong)
0x18001b7f1  mov     ebx, eax
0x18001b7f3  test    eax, eax
0x18001b7f5  js      loc_18001BB10
0x18001b7fb  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001b800  lea     rax, [rsp+170h+var_F8]
0x18001b805  mov     [rsp+170h+var_140], rax; enum ECOMPONENTLOCATION *
0x18001b80a  lea     r9, [rbp+70h+var_C0]; struct _GUID *
0x18001b80e  lea     r8, [rbp+70h+var_D0]; struct _GUID *
0x18001b812  mov     dword ptr [rsp+170h+ppv], edi; unsigned int
0x18001b816  lea     rdx, [rbp+70h+Buf2]; struct _GUID *
0x18001b81a  call    ?TargetComponentExists@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11KHPEAW4ECOMPONENTLOCATION@@@Z; TargetComponentExists(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,ulong,int,ECOMPONENTLOCATION *)
0x18001b81f  mov     ebx, eax
0x18001b821  cmp     eax, 80110439h
0x18001b826  jnz     short loc_18001B835
0x18001b828  cmp     [rsp+170h+var_F8], r12d
0x18001b82d  jnz     loc_18001BB10
0x18001b833  jmp     short loc_18001B83D
0x18001b835  test    eax, eax
0x18001b837  js      loc_18001BB10
0x18001b83d  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001b842  lea     r8, [rbp+70h+var_D0]; struct _GUID *
0x18001b846  lea     rdx, [rbp+70h+var_B0]; struct _GUID *
0x18001b84a  call    ?ValidateSourceAndDestinationApps@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@1@Z; ValidateSourceAndDestinationApps(ISimpleTableDispenser *,_GUID const &,_GUID const &)
0x18001b84f  mov     ebx, eax
0x18001b851  test    eax, eax
0x18001b853  js      loc_18001BB10
0x18001b859  mov     rcx, [rsp+170h+var_118]
0x18001b85e  lea     r8, [rsp+170h+var_F4]
0x18001b863  lea     rdx, [rbp+70h+var_D0]
0x18001b867  call    cs:__imp_ServerGetApplicationType
0x18001b86d  mov     ebx, eax
0x18001b86f  test    eax, eax
0x18001b871  js      loc_18001BB10
0x18001b877  mov     eax, [rsp+170h+var_F4]
0x18001b87b  test    [rsp+170h+var_110], eax
0x18001b87f  jnz     short loc_18001B88B
0x18001b881  mov     ebx, 80110482h
0x18001b886  jmp     loc_18001BB10
0x18001b88b  mov     ecx, 48h ; 'H'
0x18001b890  mov     [rbp+70h+var_88], r15
0x18001b894  mov     [rbp+70h+var_80], ecx
0x18001b897  lea     rax, [rbp+70h+var_C0]
0x18001b89b  mov     [rbp+70h+var_90], rax
0x18001b89f  lea     rdx, [rsp+170h+var_120]
0x18001b8a4  mov     [rsp+170h+var_138], rdx
0x18001b8a9  lea     rax, [rbp+70h+Buf1]
0x18001b8ad  mov     [rbp+70h+var_78], rax
0x18001b8b1  lea     r9, [rbp+70h+var_90]
0x18001b8b5  mov     [rbp+70h+var_68], ecx
0x18001b8b8  lea     rax, [rbp+70h+var_F0]
0x18001b8bc  mov     rcx, [rsp+170h+var_118]
0x18001b8c1  lea     r8, tidCOMSERVICES_CLASSES
0x18001b8c8  mov     [rbp+70h+var_60], rax
0x18001b8cc  lea     rdx, didCOMSERVICES
0x18001b8d3  mov     [rbp+70h+var_7C], esi
0x18001b8d6  mov     [rbp+70h+var_70], r15d
0x18001b8da  mov     [rbp+70h+var_6C], 6
0x18001b8e1  mov     [rbp+70h+var_64], esi
0x18001b8e4  mov     [rbp+70h+var_58], r15d
0x18001b8e8  mov     [rbp+70h+var_54], 8
0x18001b8ef  mov     [rbp+70h+var_50], 13h
0x18001b8f6  mov     [rbp+70h+var_4C], 4
0x18001b8fd  mov     rax, [rcx]
0x18001b900  mov     dword ptr [rsp+170h+var_140], edi
0x18001b904  mov     dword ptr [rsp+170h+var_148], r12d
0x18001b909  mov     [rsp+170h+ppv], 3
0x18001b912  mov     rax, [rax+18h]
0x18001b916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b91b  mov     ebx, eax
0x18001b91d  test    eax, eax
0x18001b91f  js      loc_18001BB10
0x18001b925  mov     rcx, [rsp+170h+var_120]
0x18001b92a  lea     rdx, [rsp+170h+var_108]
0x18001b92f  mov     [rsp+170h+var_130], rdx
0x18001b934  xor     r9d, r9d
0x18001b937  mov     [rsp+170h+var_138], r15
0x18001b93c  xor     r8d, r8d
0x18001b93f  mov     [rsp+170h+var_140], r15
0x18001b944  xor     edx, edx
0x18001b946  mov     rax, [rcx]
0x18001b949  mov     [rsp+170h+var_148], r15
0x18001b94e  mov     [rsp+170h+ppv], r15
0x18001b953  mov     rax, [rax+48h]
0x18001b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95c  mov     ebx, eax
0x18001b95e  test    eax, eax
0x18001b960  js      loc_18001BB10
0x18001b966  mov     rcx, [rsp+170h+var_120]
0x18001b96b  mov     rax, [rcx]
0x18001b96e  mov     rax, [rax+18h]
0x18001b972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b977  mov     ebx, eax
0x18001b979  test    eax, eax
0x18001b97b  js      loc_18001BB10
0x18001b981  mov     rcx, [rsp+170h+var_120]
0x18001b986  mov     rax, [rcx]
0x18001b989  mov     rax, [rax+28h]
0x18001b98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b992  mov     ebx, eax
0x18001b994  cmp     eax, 80110801h
0x18001b999  jz      loc_18001B7A2
0x18001b99f  test    eax, eax
0x18001b9a1  js      loc_18001BB10
0x18001b9a7  mov     rcx, [rsp+170h+var_120]
0x18001b9ac  mov     rax, [rcx]
0x18001b9af  mov     rax, [rax+78h]
0x18001b9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b8  mov     ebx, eax
0x18001b9ba  test    eax, eax
0x18001b9bc  js      loc_18001BB10
0x18001b9c2  mov     edi, r15d
0x18001b9c5  cmp     [rsp+170h+var_108], r15d
0x18001b9ca  jbe     loc_18001BAA7
0x18001b9d0  mov     rcx, [rsp+170h+var_120]
0x18001b9d5  lea     rdx, [rsp+170h+var_100]
0x18001b9da  mov     [rsp+170h+ppv], rdx
0x18001b9df  lea     r9, [rsp+170h+var_10C]
0x18001b9e4  lea     r8, [rbp+70h+var_EC]
0x18001b9e8  mov     edx, edi
0x18001b9ea  mov     rax, [rcx]
0x18001b9ed  mov     rax, [rax+40h]
0x18001b9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9f6  mov     ebx, eax
0x18001b9f8  test    eax, eax
0x18001b9fa  js      loc_18001BB10
0x18001ba00  mov     eax, edi
0x18001ba02  sub     eax, 6
0x18001ba05  jz      short loc_18001BA65
0x18001ba07  sub     eax, 3
0x18001ba0a  jz      short loc_18001BA54
0x18001ba0c  sub     eax, 0Fh
0x18001ba0f  jz      short loc_18001BA45
0x18001ba11  sub     eax, r12d
0x18001ba14  jz      short loc_18001BA45
0x18001ba16  cmp     eax, 0Bh
0x18001ba19  jnz     short loc_18001BA3E
0x18001ba1b  mov     r8, rsi; Size
0x18001ba1e  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18001ba25  lea     rcx, [rbp+70h+Buf2]; Buf1
0x18001ba29  call    memcmp_0
0x18001ba2e  test    eax, eax
0x18001ba30  lea     r9, [rbp+70h+var_E8]
0x18001ba34  lea     rcx, [rbp+70h+var_E4]
0x18001ba38  cmovnz  r9, rcx
0x18001ba3c  jmp     short loc_18001BA69
0x18001ba3e  mov     r9, [rsp+170h+var_100]
0x18001ba43  jmp     short loc_18001BA6E
0x18001ba45  mov     r9, r15
0x18001ba48  mov     [rsp+170h+var_100], r15
0x18001ba4d  mov     [rsp+170h+var_10C], r15d
0x18001ba52  jmp     short loc_18001BA6E
0x18001ba54  cmp     [rsp+170h+var_100], r15
0x18001ba59  jz      loc_18001BB61
0x18001ba5f  lea     r9, [rbp+70h+var_D0]
0x18001ba63  jmp     short loc_18001BA69
0x18001ba65  lea     r9, [rbp+70h+Buf2]
0x18001ba69  mov     [rsp+170h+var_100], r9
0x18001ba6e  mov     rcx, [rsp+170h+var_120]
0x18001ba73  mov     r8d, r15d
0x18001ba76  cmp     [rbp+70h+var_EC], 80h
0x18001ba7d  mov     edx, edi
0x18001ba7f  cmovz   r8d, [rsp+170h+var_10C]
0x18001ba85  mov     rax, [rcx]
0x18001ba88  mov     rax, [rax+0A0h]
0x18001ba8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba94  mov     ebx, eax
0x18001ba96  test    eax, eax
0x18001ba98  js      short loc_18001BB10
0x18001ba9a  add     edi, r12d
0x18001ba9d  cmp     edi, [rsp+170h+var_108]
0x18001baa1  jb      loc_18001B9D0
0x18001baa7  mov     rcx, [rsp+170h+var_120]
0x18001baac  mov     rax, [rcx]
0x18001baaf  mov     rax, [rax+90h]
0x18001bab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001babb  mov     ebx, eax
0x18001babd  test    eax, eax
0x18001babf  js      short loc_18001BB10
0x18001bac1  mov     rcx, [rsp+170h+var_120]
0x18001bac6  mov     rax, [rcx]
0x18001bac9  mov     rax, [rax+60h]
0x18001bacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad2  mov     ebx, eax
0x18001bad4  test    eax, eax
0x18001bad6  js      short loc_18001BB10
0x18001bad8  mov     rcx, [rsp+170h+var_120]
0x18001badd  test    rcx, rcx
0x18001bae0  jz      short loc_18001BAF3
0x18001bae2  mov     rax, [rcx]
0x18001bae5  mov     rax, [rax+10h]
0x18001bae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baee  mov     [rsp+170h+var_120], r15
0x18001baf3  mov     rcx, [rsp+170h+var_118]
0x18001baf8  lea     r9, [rbp+70h+var_C0]
0x18001bafc  lea     r8, [rbp+70h+Buf2]
0x18001bb00  mov     dword ptr [rsp+170h+ppv], r12d
0x18001bb05  lea     rdx, [rbp+70h+var_90]
0x18001bb09  call    ?UpdateRelatedComponentInfo@@YAJPEAUISimpleTableDispenser@@QEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@AEBU_GUID@@2W4EUPDATETYPE@@@Z; UpdateRelatedComponentInfo(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0002 * const,_GUID const &,_GUID const &,EUPDATETYPE)
0x18001bb0e  mov     ebx, eax
0x18001bb10  mov     rcx, [rsp+170h+var_120]
  ... truncated ...
```
