# MoveComponentWorker(ushort const *,ushort const *,ushort const *)

- ea: `0x18001bf9c`
- end: `0x18001c529`
- name: `?MoveComponentWorker@@YAJPEBG00@Z`
- size: `1421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001be80`

## callees

- `0x18001b3a0`
- `0x18001b664`
- `0x18001bb70`
- `0x18001bf9c`
- `0x18001c530`
- `0x18001c934`
- `0x180031000`
- `0x180038e8c`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001c139`
- `CLBCatQ!CLSIDFromStringByBitness` at `0x18001c139`
- `CLBCatQ!ServerGetApplicationType` at `0x18001c0f7`
- `CLBCatQ!ServerGetApplicationType` at `0x18001c24e`
- `CLBCatQ!ServerGetApplicationType` at `0x18001c0f7`
- `CLBCatQ!ServerGetApplicationType` at `0x18001c24e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c09b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c09b`

## pseudocode

```c
__int64 __fastcall MoveComponentWorker(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int Instance; // ebx
  unsigned int v7; // edi
  int updated; // eax
  int v9; // edi
  struct _GUID *v11; // [rsp+28h] [rbp-D8h]
  struct ISimpleTableDispenser *ppv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v13; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v14; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v15; // [rsp+68h] [rbp-98h] BYREF
  int v16; // [rsp+6Ch] [rbp-94h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v19; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+7Ch] [rbp-84h] BYREF
  int v21; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[24]; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v23; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID Buf2; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v25; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v26; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v27[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v28; // [rsp+F0h] [rbp-10h]
  int v29; // [rsp+F4h] [rbp-Ch]
  _BYTE *v30; // [rsp+F8h] [rbp-8h]
  int v31; // [rsp+100h] [rbp+0h]
  int v32; // [rsp+104h] [rbp+4h]
  int v33; // [rsp+108h] [rbp+8h]
  int v34; // [rsp+10Ch] [rbp+Ch]
  int *v35; // [rsp+110h] [rbp+10h]
  int v36; // [rsp+118h] [rbp+18h]
  int v37; // [rsp+11Ch] [rbp+1Ch]
  int v38; // [rsp+120h] [rbp+20h]
  int v39; // [rsp+124h] [rbp+24h]

  v16 = 1;
  ppv = 0;
  v20 = 0;
  v21 = 0;
  v28 = 72;
  v27[0] = &v23;
  v33 = 72;
  v30 = &v22[8];
  memset(v22, 0, sizeof(v22));
  v35 = &v17;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v18 = 0;
  v17 = 1;
  v23 = 0;
  v27[1] = 0;
  v25 = 0;
  v29 = 16;
  v26 = 0;
  v31 = 0;
  v32 = 6;
  Buf2 = 0;
  v34 = 16;
  v36 = 0;
  v37 = 8;
  v38 = 19;
  v39 = 4;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ResolveAppIdFromName(ppv, a1, &v25, (struct _GUID *)&v22[8]);
    if ( Instance >= 0 )
    {
      Instance = ResolveAppIdFromName(ppv, a3, &v26, &Buf2);
      if ( Instance >= 0 )
      {
        Instance = ServerGetApplicationType(ppv, &v25, &v16);
        if ( Instance >= 0 )
        {
          if ( v16 == 3 )
          {
            Instance = -2146367479;
            goto LABEL_44;
          }
          v17 = v16;
          v7 = 0x400000;
          if ( v16 == 1 )
            v7 = 0x200000;
          Instance = CLSIDFromStringByBitness(a2, &v23);
          if ( Instance >= 0 )
          {
            Instance = CheckSourceComponentExists(ppv, (const struct _GUID *)&v22[8], &v25, &v23, v7);
            if ( Instance >= 0 )
            {
              Instance = GetAppProps(ppv, &v26, &Buf2, &v13, &v15, 0, &v14, &v19, 0);
              if ( Instance >= 0 )
              {
                if ( v13 || v14 || !v15 )
                {
                  Instance = -2146367459;
                }
                else
                {
                  Instance = GetAppProps(ppv, &v25, 0, &v13, &v15, 0, &v14, &v19, 0);
                  if ( Instance < 0 )
                    goto LABEL_44;
                  if ( v13 || v14 || !v15 )
                  {
                    Instance = -2146367460;
                  }
                  else
                  {
                    Instance = ServerGetApplicationType(ppv, &v26, &v18);
                    if ( Instance < 0 )
                      goto LABEL_44;
                    if ( (v18 & v16) == 0 )
                    {
                      Instance = -2146368382;
                      goto LABEL_44;
                    }
                    LODWORD(v11) = 1;
                    Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64))(*(_QWORD *)ppv + 24LL))(
                                 ppv,
                                 didCOMSERVICES,
                                 tidCOMSERVICES_CLASSES,
                                 v27,
                                 3);
                    if ( Instance >= 0 )
                    {
                      Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 24LL))(0);
                      if ( Instance >= 0 )
                      {
                        Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 32LL))(0);
                        if ( Instance >= 0 )
                        {
                          if ( (*(unsigned int (__fastcall **)(_QWORD))(MEMORY[0] + 40LL))(0) == -2146367487 )
                          {
                            Instance = -2147024809;
                            goto LABEL_44;
                          }
                          if ( !memcmp_0(&v22[8], &Buf2, 0x10u) )
                          {
                            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, int *))(MEMORY[0] + 64LL))(
                                         0,
                                         43,
                                         &v21,
                                         &v20);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            v9 = **(_DWORD **)v22;
                            Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 128LL))(0);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct _GUID *))(MEMORY[0] + 160LL))(
                                         0,
                                         9,
                                         0,
                                         &v26);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct _GUID *))(MEMORY[0] + 160LL))(
                                         0,
                                         6,
                                         0,
                                         &Buf2);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 144LL))(0);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            if ( v9 )
                            {
                              Instance = MoveEventClass(
                                           ppv,
                                           &v23,
                                           (const struct _GUID *)&v22[8],
                                           &Buf2,
                                           (const struct _GUID *)v22,
                                           v11);
                              if ( Instance < 0 )
                                goto LABEL_44;
                            }
                            Instance = DeleteSubscriptions(ppv, &v23, (const struct _GUID *)&v22[8], &v25);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 96LL))(0);
                            if ( Instance < 0 )
                              goto LABEL_44;
                            updated = UpdateRelatedComponentInfo(ppv, v27, &Buf2, &v23, 0);
                            goto LABEL_41;
                          }
                          Instance = CopyComponentWorker(a1, a2, a3);
                          if ( Instance >= 0 )
                          {
                            Instance = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 136LL))(0);
                            if ( Instance >= 0 )
                            {
                              updated = (*(__int64 (__fastcall **)(_QWORD))(MEMORY[0] + 96LL))(0);
LABEL_41:
                              Instance = updated;
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
LABEL_44:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001bf9c  push    rbp
0x18001bf9e  push    rbx
0x18001bf9f  push    rsi
0x18001bfa0  push    rdi
0x18001bfa1  push    r12
0x18001bfa3  push    r14
0x18001bfa5  push    r15
0x18001bfa7  lea     rbp, [rsp-40h]
0x18001bfac  sub     rsp, 140h
0x18001bfb3  mov     rax, cs:__security_cookie
0x18001bfba  xor     rax, rsp
0x18001bfbd  mov     [rbp+70h+var_40], rax
0x18001bfc1  xor     r12d, r12d
0x18001bfc4  mov     [rsp+170h+var_104], 1
0x18001bfcc  xorps   xmm0, xmm0
0x18001bfcf  mov     [rsp+170h+var_118], r12
0x18001bfd4  mov     rsi, rcx
0x18001bfd7  mov     [rsp+170h+var_120], r12
0x18001bfdc  xorps   xmm1, xmm1
0x18001bfdf  mov     [rsp+170h+var_F4], r12d
0x18001bfe4  lea     ecx, [r12+48h]
0x18001bfe9  mov     [rbp+70h+var_F0], r12d
0x18001bfed  lea     rax, [rbp+70h+var_D0]
0x18001bff1  mov     [rbp+70h+var_80], ecx
0x18001bff4  mov     [rbp+70h+var_90], rax
0x18001bff8  lea     r9, IID_ISimpleTableDispenser; riid
0x18001bfff  lea     rax, [rbp+70h+var_E8+8]
0x18001c003  mov     [rbp+70h+var_68], ecx
0x18001c006  mov     [rbp+70h+var_78], rax
0x18001c00a  lea     rcx, CLSID_STDispenser; rclsid
0x18001c011  lea     rax, [rsp+170h+var_100]
0x18001c016  mov     qword ptr [rbp+70h+var_E8], r12
0x18001c01a  mov     [rbp+70h+var_60], rax
0x18001c01e  mov     r14, r8
0x18001c021  lea     rax, [rsp+170h+var_118]
0x18001c026  mov     [rsp+170h+var_110], r12d
0x18001c02b  mov     r15, rdx
0x18001c02e  mov     [rsp+170h+ppv], rax; ppv
0x18001c033  xor     edx, edx; pUnkOuter
0x18001c035  mov     [rsp+170h+var_108], r12d
0x18001c03a  lea     r8d, [r12+17h]; dwClsContext
0x18001c03f  mov     [rsp+170h+var_10C], r12d
0x18001c044  mov     [rsp+170h+var_FC], r12d
0x18001c049  mov     [rsp+170h+var_100], 1
0x18001c051  movups  xmmword ptr [rbp+70h+var_D0.Data1], xmm0
0x18001c055  mov     [rbp+70h+var_88], r12
0x18001c059  movups  xmmword ptr [rbp+70h+var_B0.Data1], xmm1
0x18001c05d  mov     [rbp+70h+var_7C], 10h
0x18001c064  movups  xmmword ptr [rbp+70h+var_A0.Data1], xmm0
0x18001c068  mov     [rbp+70h+var_70], r12d
0x18001c06c  movups  xmmword ptr [rbp+70h+var_E8+8], xmm1
0x18001c070  mov     [rbp+70h+var_6C], 6
0x18001c077  movups  [rbp+70h+Buf2], xmm0
0x18001c07b  mov     [rbp+70h+var_64], 10h
0x18001c082  mov     [rbp+70h+var_58], r12d
0x18001c086  mov     [rbp+70h+var_54], 8
0x18001c08d  mov     [rbp+70h+var_50], 13h
0x18001c094  mov     [rbp+70h+var_4C], 4
0x18001c09b  call    cs:__imp_CoCreateInstance
0x18001c0a1  mov     ebx, eax
0x18001c0a3  test    eax, eax
0x18001c0a5  js      loc_18001C4D8
0x18001c0ab  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c0b0  lea     r9, [rbp+70h+var_E8+8]; struct _GUID *
0x18001c0b4  lea     r8, [rbp+70h+var_B0]; struct _GUID *
0x18001c0b8  mov     rdx, rsi; unsigned __int16 *
0x18001c0bb  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001c0c0  mov     ebx, eax
0x18001c0c2  test    eax, eax
0x18001c0c4  js      loc_18001C4D8
0x18001c0ca  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c0cf  lea     r9, [rbp+70h+Buf2]; struct _GUID *
0x18001c0d3  lea     r8, [rbp+70h+var_A0]; struct _GUID *
0x18001c0d7  mov     rdx, r14; unsigned __int16 *
0x18001c0da  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x18001c0df  mov     ebx, eax
0x18001c0e1  test    eax, eax
0x18001c0e3  js      loc_18001C4D8
0x18001c0e9  mov     rcx, [rsp+170h+var_118]
0x18001c0ee  lea     r8, [rsp+170h+var_104]
0x18001c0f3  lea     rdx, [rbp+70h+var_B0]
0x18001c0f7  call    cs:__imp_ServerGetApplicationType
0x18001c0fd  mov     ebx, eax
0x18001c0ff  test    eax, eax
0x18001c101  js      loc_18001C4D8
0x18001c107  mov     r8d, [rsp+170h+var_104]
0x18001c10c  cmp     r8d, 3
0x18001c110  jnz     short loc_18001C11C
0x18001c112  mov     ebx, 80110809h
0x18001c117  jmp     loc_18001C4D8
0x18001c11c  cmp     r8d, 1
0x18001c120  mov     [rsp+170h+var_100], r8d
0x18001c125  mov     eax, 200000h
0x18001c12a  lea     rdx, [rbp+70h+var_D0]
0x18001c12e  mov     edi, 400000h
0x18001c133  mov     rcx, r15
0x18001c136  cmovz   edi, eax
0x18001c139  call    cs:__imp_CLSIDFromStringByBitness
0x18001c13f  mov     ebx, eax
0x18001c141  test    eax, eax
0x18001c143  js      loc_18001C4D8
0x18001c149  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c14e  lea     r9, [rbp+70h+var_D0]; struct _GUID *
0x18001c152  lea     r8, [rbp+70h+var_B0]; struct _GUID *
0x18001c156  mov     dword ptr [rsp+170h+ppv], edi; unsigned int
0x18001c15a  lea     rdx, [rbp+70h+var_E8+8]; struct _GUID *
0x18001c15e  call    ?CheckSourceComponentExists@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11K@Z; CheckSourceComponentExists(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,ulong)
0x18001c163  mov     ebx, eax
0x18001c165  test    eax, eax
0x18001c167  js      loc_18001C4D8
0x18001c16d  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c172  lea     rax, [rsp+170h+var_F8]
0x18001c177  mov     [rsp+170h+var_130], r12; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x18001c17c  lea     r9, [rsp+170h+var_110]; unsigned int *
0x18001c181  mov     [rsp+170h+var_138], rax; unsigned int *
0x18001c186  lea     r8, [rbp+70h+Buf2]; struct _GUID *
0x18001c18a  lea     rax, [rsp+170h+var_10C]
0x18001c18f  mov     [rsp+170h+var_140], rax; unsigned int *
0x18001c194  lea     rdx, [rbp+70h+var_A0]; struct _GUID *
0x18001c198  lea     rax, [rsp+170h+var_108]
0x18001c19d  mov     [rsp+170h+var_148], r12; unsigned int *
0x18001c1a2  mov     [rsp+170h+ppv], rax; unsigned int *
0x18001c1a7  call    ?GetAppProps@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAU2@PEAK3333PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; GetAppProps(ISimpleTableDispenser *,_GUID const &,_GUID *,ulong *,ulong *,ulong *,ulong *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x18001c1ac  mov     ebx, eax
0x18001c1ae  test    eax, eax
0x18001c1b0  js      loc_18001C4D8
0x18001c1b6  cmp     [rsp+170h+var_110], r12d
0x18001c1bb  jnz     loc_18001C4D3
0x18001c1c1  cmp     [rsp+170h+var_10C], r12d
0x18001c1c6  jnz     loc_18001C4D3
0x18001c1cc  cmp     [rsp+170h+var_108], r12d
0x18001c1d1  jz      loc_18001C4D3
0x18001c1d7  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c1dc  lea     rax, [rsp+170h+var_F8]
0x18001c1e1  mov     [rsp+170h+var_130], r12; enum __MIDL___MIDL_itf_registrar_0000_0000_0001 *
0x18001c1e6  lea     r9, [rsp+170h+var_110]; unsigned int *
0x18001c1eb  mov     [rsp+170h+var_138], rax; unsigned int *
0x18001c1f0  lea     rdx, [rbp+70h+var_B0]; struct _GUID *
0x18001c1f4  lea     rax, [rsp+170h+var_10C]
0x18001c1f9  xor     r8d, r8d; struct _GUID *
0x18001c1fc  mov     [rsp+170h+var_140], rax; unsigned int *
0x18001c201  lea     rax, [rsp+170h+var_108]
0x18001c206  mov     [rsp+170h+var_148], r12; unsigned int *
0x18001c20b  mov     [rsp+170h+ppv], rax; unsigned int *
0x18001c210  call    ?GetAppProps@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAU2@PEAK3333PEAW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; GetAppProps(ISimpleTableDispenser *,_GUID const &,_GUID *,ulong *,ulong *,ulong *,ulong *,ulong *,__MIDL___MIDL_itf_registrar_0000_0000_0001 *)
0x18001c215  mov     ebx, eax
0x18001c217  test    eax, eax
0x18001c219  js      loc_18001C4D8
0x18001c21f  cmp     [rsp+170h+var_110], r12d
0x18001c224  jnz     loc_18001C4CC
0x18001c22a  cmp     [rsp+170h+var_10C], r12d
0x18001c22f  jnz     loc_18001C4CC
0x18001c235  cmp     [rsp+170h+var_108], r12d
0x18001c23a  jz      loc_18001C4CC
0x18001c240  mov     rcx, [rsp+170h+var_118]
0x18001c245  lea     r8, [rsp+170h+var_FC]
0x18001c24a  lea     rdx, [rbp+70h+var_A0]
0x18001c24e  call    cs:__imp_ServerGetApplicationType
0x18001c254  mov     ebx, eax
0x18001c256  test    eax, eax
0x18001c258  js      loc_18001C4D8
0x18001c25e  mov     eax, [rsp+170h+var_FC]
0x18001c262  test    [rsp+170h+var_104], eax
0x18001c266  jnz     short loc_18001C272
0x18001c268  mov     ebx, 80110482h
0x18001c26d  jmp     loc_18001C4D8
0x18001c272  mov     rcx, [rsp+170h+var_118]
0x18001c277  lea     rdx, [rsp+170h+var_120]
0x18001c27c  mov     [rsp+170h+var_138], rdx
0x18001c281  lea     r9, [rbp+70h+var_90]
0x18001c285  mov     dword ptr [rsp+170h+var_140], edi
0x18001c289  lea     r8, tidCOMSERVICES_CLASSES
0x18001c290  mov     dword ptr [rsp+170h+var_148], 1; struct _GUID *
0x18001c298  lea     rdx, didCOMSERVICES
0x18001c29f  mov     rax, [rcx]
0x18001c2a2  mov     [rsp+170h+ppv], 3
0x18001c2ab  mov     rax, [rax+18h]
0x18001c2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b4  mov     ebx, eax
0x18001c2b6  test    eax, eax
0x18001c2b8  js      loc_18001C4D8
0x18001c2be  mov     rcx, [rsp+170h+var_120]
0x18001c2c3  mov     rax, [rcx]
0x18001c2c6  mov     rax, [rax+18h]
0x18001c2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2cf  mov     ebx, eax
0x18001c2d1  test    eax, eax
0x18001c2d3  js      loc_18001C4D8
0x18001c2d9  mov     rcx, [rsp+170h+var_120]
0x18001c2de  mov     rax, [rcx]
0x18001c2e1  mov     rax, [rax+20h]
0x18001c2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ea  mov     ebx, eax
0x18001c2ec  test    eax, eax
0x18001c2ee  js      loc_18001C4D8
0x18001c2f4  mov     rcx, [rsp+170h+var_120]
0x18001c2f9  mov     rax, [rcx]
0x18001c2fc  mov     rax, [rax+28h]
0x18001c300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c305  cmp     eax, 80110801h
0x18001c30a  jnz     short loc_18001C316
0x18001c30c  mov     ebx, 80070057h
0x18001c311  jmp     loc_18001C4D8
0x18001c316  mov     r8d, 10h; Size
0x18001c31c  lea     rdx, [rbp+70h+Buf2]; Buf2
0x18001c320  lea     rcx, [rbp+70h+var_E8+8]; Buf1
0x18001c324  call    memcmp_0
0x18001c329  test    eax, eax
0x18001c32b  jz      short loc_18001C379
0x18001c32d  mov     r8, r14; unsigned __int16 *
0x18001c330  mov     rdx, r15; unsigned __int16 *
0x18001c333  mov     rcx, rsi; unsigned __int16 *
0x18001c336  call    ?CopyComponentWorker@@YAJPEBG00@Z; CopyComponentWorker(ushort const *,ushort const *,ushort const *)
0x18001c33b  mov     ebx, eax
0x18001c33d  test    eax, eax
0x18001c33f  js      loc_18001C4D8
0x18001c345  mov     rcx, [rsp+170h+var_120]
0x18001c34a  mov     rax, [rcx]
0x18001c34d  mov     rax, [rax+88h]
0x18001c354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c359  mov     ebx, eax
0x18001c35b  test    eax, eax
0x18001c35d  js      loc_18001C4D8
0x18001c363  mov     rcx, [rsp+170h+var_120]
0x18001c368  mov     rax, [rcx]
0x18001c36b  mov     rax, [rax+60h]
0x18001c36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c374  jmp     loc_18001C4C8
0x18001c379  mov     rcx, [rsp+170h+var_120]
0x18001c37e  lea     rdx, [rbp+70h+var_E8]
0x18001c382  mov     [rsp+170h+ppv], rdx; struct _GUID *
0x18001c387  lea     r9, [rsp+170h+var_F4]
0x18001c38c  lea     r8, [rbp+70h+var_F0]
0x18001c390  mov     edx, 2Bh ; '+'
0x18001c395  mov     rax, [rcx]
0x18001c398  mov     rax, [rax+40h]
0x18001c39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a1  mov     ebx, eax
0x18001c3a3  test    eax, eax
0x18001c3a5  js      loc_18001C4D8
0x18001c3ab  mov     rax, qword ptr [rbp+70h+var_E8]
0x18001c3af  mov     rcx, [rsp+170h+var_120]
0x18001c3b4  mov     edi, [rax]
0x18001c3b6  mov     rax, [rcx]
0x18001c3b9  mov     rax, [rax+80h]
0x18001c3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c5  mov     ebx, eax
0x18001c3c7  test    eax, eax
0x18001c3c9  js      loc_18001C4D8
0x18001c3cf  mov     rcx, [rsp+170h+var_120]
0x18001c3d4  lea     r9, [rbp+70h+var_A0]
0x18001c3d8  xor     r8d, r8d
0x18001c3db  mov     rax, [rcx]
0x18001c3de  lea     edx, [r8+9]
0x18001c3e2  mov     rax, [rax+0A0h]
0x18001c3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3ee  mov     ebx, eax
0x18001c3f0  test    eax, eax
0x18001c3f2  js      loc_18001C4D8
0x18001c3f8  mov     rcx, [rsp+170h+var_120]
0x18001c3fd  lea     r9, [rbp+70h+Buf2]
0x18001c401  xor     r8d, r8d
0x18001c404  mov     rax, [rcx]
0x18001c407  lea     edx, [r8+6]
0x18001c40b  mov     rax, [rax+0A0h]
0x18001c412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c417  mov     ebx, eax
0x18001c419  test    eax, eax
0x18001c41b  js      loc_18001C4D8
0x18001c421  mov     rcx, [rsp+170h+var_120]
0x18001c426  mov     rax, [rcx]
0x18001c429  mov     rax, [rax+90h]
0x18001c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c435  mov     ebx, eax
0x18001c437  test    eax, eax
0x18001c439  js      loc_18001C4D8
0x18001c43f  test    edi, edi
0x18001c441  jz      short loc_18001C45F
0x18001c443  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c448  lea     r9, [rbp+70h+Buf2]; struct _GUID *
0x18001c44c  lea     r8, [rbp+70h+var_E8+8]; struct _GUID *
0x18001c450  lea     rdx, [rbp+70h+var_D0]; struct _GUID *
0x18001c454  call    ?MoveEventClass@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@1111@Z; MoveEventClass(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &,_GUID const &,_GUID const &)
0x18001c459  mov     ebx, eax
0x18001c45b  test    eax, eax
0x18001c45d  js      short loc_18001C4D8
0x18001c45f  mov     rcx, [rsp+170h+var_118]; struct ISimpleTableDispenser *
0x18001c464  lea     r9, [rbp+70h+var_B0]; struct _GUID *
0x18001c468  lea     r8, [rbp+70h+var_E8+8]; struct _GUID *
0x18001c46c  lea     rdx, [rbp+70h+var_D0]; struct _GUID *
0x18001c470  call    ?DeleteSubscriptions@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@11@Z; DeleteSubscriptions(ISimpleTableDispenser *,_GUID const &,_GUID const &,_GUID const &)
0x18001c475  mov     ebx, eax
0x18001c477  test    eax, eax
0x18001c479  js      short loc_18001C4D8
0x18001c47b  mov     rcx, [rsp+170h+var_120]
0x18001c480  mov     rax, [rcx]
0x18001c483  mov     rax, [rax+60h]
0x18001c487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c48c  mov     ebx, eax
0x18001c48e  test    eax, eax
  ... truncated ...
```
