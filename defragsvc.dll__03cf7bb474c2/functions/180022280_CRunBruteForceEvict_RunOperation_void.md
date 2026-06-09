# CRunBruteForceEvict::RunOperation(void)

- ea: `0x180022280`
- end: `0x180022994`
- name: `?RunOperation@CRunBruteForceEvict@@UEAAJXZ`
- size: `1812`
- prototype: `__int64 __fastcall(CRunBruteForceEvict *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x180022280`
- `0x180026a24`
- `0x180038c3c`
- `0x18004aa24`
- `0x18004b1cc`
- `0x18004b410`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022984`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CRunBruteForceEvict::RunOperation(CRunBruteForceEvict *this)
{
  __int64 v2; // rsi
  __int128 v3; // xmm6
  struct IFreeSpaceManager *v4; // rcx
  int v5; // ebx
  __int16 v6; // ax
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rcx
  unsigned int v9; // r13d
  unsigned int v10; // r12d
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, __int64 *); // rax
  bool v12; // sf
  unsigned __int64 v13; // r14
  struct IFreeSpaceManager *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int16 v18; // ax
  int v19; // eax
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  struct IFreeSpaceManager *v21; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-B0h] BYREF
  int v23; // [rsp+60h] [rbp-A8h] BYREF
  __int16 v24; // [rsp+64h] [rbp-A4h]
  __int16 v25; // [rsp+66h] [rbp-A2h]
  __int64 v26; // [rsp+98h] [rbp-70h] BYREF
  int v27; // [rsp+A0h] [rbp-68h] BYREF
  int v28; // [rsp+A4h] [rbp-64h] BYREF
  int v29; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v30; // [rsp+ACh] [rbp-5Ch] BYREF
  int v31; // [rsp+B0h] [rbp-58h] BYREF
  int v32; // [rsp+B4h] [rbp-54h] BYREF
  int v33; // [rsp+B8h] [rbp-50h] BYREF
  int v34; // [rsp+BCh] [rbp-4Ch] BYREF
  __int64 v35; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v36; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-30h]
  struct _GUID v38; // [rsp+E0h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v40; // [rsp+108h] [rbp+0h]
  __int128 v41; // [rsp+118h] [rbp+10h]
  __int64 v42; // [rsp+128h] [rbp+20h]
  int v43; // [rsp+130h] [rbp+28h]
  __int16 v44; // [rsp+134h] [rbp+2Ch]
  __int128 v45; // [rsp+148h] [rbp+40h]
  __int64 v46; // [rsp+158h] [rbp+50h]
  __int64 v47; // [rsp+160h] [rbp+58h]
  __int64 v48; // [rsp+168h] [rbp+60h]
  __int64 v49; // [rsp+170h] [rbp+68h]
  int v50; // [rsp+178h] [rbp+70h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "CRunBruteForceEvict::RunOperation", 354, 1);
  v37 = 0;
  v22 = 0;
  v26 = 0;
  v21 = 0;
  LODWORD(v20) = 0;
  v29 = 0;
  v34 = 0;
  v30 = 0;
  v28 = 0;
  v33 = 0;
  v27 = 0;
  v32 = 0;
  v31 = 0;
  v35 = 0;
  *(_OWORD *)pv = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v38 = 0;
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 5) + 152LL))(*((_QWORD *)this + 5), &v38);
  v2 = *((_QWORD *)this + 93);
  if ( v2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(*((_QWORD *)this + 93));
  v37 = v2;
  if ( v2 )
  {
    v3 = *(_OWORD *)((char *)this + 760);
    *((_QWORD *)this + 24) = 0;
    v4 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), *((_QWORD *)this + 18), &v21);
    v23 = v5;
    v6 = 393;
    if ( v5 < 0 )
      goto LABEL_32;
    v24 = 393;
    v5 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *))(*(_QWORD *)v2 + 192LL))(
           v2,
           &v33,
           &v27,
           &v32,
           &v31);
    v23 = v5;
    v6 = 397;
    if ( v5 < 0 )
      goto LABEL_32;
    v24 = 397;
    if ( v27 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 6) + 56LL))(*((_QWORD *)this + 6), &v34);
      v23 = v5;
      v6 = 401;
      if ( v5 < 0 )
        goto LABEL_32;
      v24 = 401;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
           *((_QWORD *)this + 6),
           (char *)this + 56);
    v23 = v5;
    v6 = 406;
    if ( v5 >= 0 )
    {
      v24 = 406;
      v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v2 + 104LL);
      v8 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v5 = v7(v2, 0, &v22);
      v23 = v5;
      v6 = 409;
      if ( v5 >= 0 )
      {
        v24 = 409;
        v5 = CDefragOperation::_SetPhase(this, 4u);
        v23 = v5;
        v6 = 412;
        if ( v5 >= 0 )
        {
          v24 = 412;
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 64LL))(v22, &v30);
          CDefragOperation::_SetPercentComplete(this, 0);
          v36 = v3;
          v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, __int128 *))(*(_QWORD *)v21 + 48LL))(v21, &v36);
          v23 = v5;
          v6 = 423;
          if ( v5 >= 0 )
          {
            v24 = 423;
            v5 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v21 + 24LL))(v21);
            v23 = v5;
            v6 = 424;
            if ( v5 >= 0 )
            {
              v24 = 424;
              v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v20);
              v23 = v5;
              v6 = 427;
              if ( v5 >= 0 )
              {
                v9 = 0;
                v10 = 0;
                while ( 1 )
                {
                  v24 = v6;
                  if ( v5 == 1 )
                    break;
                  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v2 + 56LL);
                  if ( v26 )
                  {
                    v5 = v11(v2, (unsigned int)v20, v26, 0);
                    v23 = v5;
                    v12 = v5 < 0;
                    v6 = 433;
                  }
                  else
                  {
                    v5 = v11(v2, (unsigned int)v20, 0, &v26);
                    v23 = v5;
                    v12 = v5 < 0;
                    v6 = 437;
                  }
                  if ( v12 )
                    goto LABEL_32;
                  v24 = v6;
                  v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v26 + 64LL))(v26, 1, &v28);
                  v23 = v5;
                  v6 = 440;
                  if ( v5 < 0 )
                    goto LABEL_32;
                  v24 = 440;
                  if ( !v28 )
                  {
                    v36 = v3;
                    v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)v26 + 152LL))(
                           v26,
                           &v36,
                           &v29);
                    v23 = v5;
                    v6 = 446;
                    if ( v5 < 0 )
                      goto LABEL_32;
                    v24 = 446;
                    if ( v29 )
                    {
                      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          12,
                          WPP_66e17ae5f492370f443a7f44dd728b5e_Traceguids);
                      }
                      v36 = v3;
                      v19 = CRunBruteForceEvict::_BruteForceEvict(this, (unsigned int)v20, &v36, v26, v2, v21, &v35);
                      v5 = v19;
                      if ( v19 == -1996488682 || v19 == 1 )
                      {
                        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
                        {
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            13,
                            WPP_66e17ae5f492370f443a7f44dd728b5e_Traceguids);
                        }
                        if ( (int)SxFileLoggingSupport::Initialize(
                                    (__int64)pv,
                                    *((const unsigned __int16 **)this + 87),
                                    *((_QWORD *)this + 89),
                                    v35,
                                    *((_QWORD *)this + 95),
                                    (__int64)this + 56,
                                    2) >= 0 )
                        {
                          SxFileLoggingSupport::LogShrinkInhibitorFileInfo(
                            (SxFileLoggingSupport *)pv,
                            (struct CSxFunctionTracer *)&v23,
                            0x1D6u,
                            0x80000104,
                            2u);
                          SxFileLoggingSupport::LogShrinkInhibitorTelemetry((SxFileLoggingSupport *)pv, &v38);
                        }
                        v5 = -1996488671;
                        v18 = 475;
                        goto LABEL_48;
                      }
                      v23 = v19;
                      v12 = v19 < 0;
                      v6 = 479;
                      if ( v12 )
                        goto LABEL_32;
                      v24 = 479;
                    }
                  }
                  v5 = (*(__int64 (__fastcall **)(CRunBruteForceEvict *))(*(_QWORD *)this + 32LL))(this);
                  v23 = v5;
                  v6 = 487;
                  if ( v5 < 0 )
                    goto LABEL_32;
                  ++v10;
                  v24 = 487;
                  if ( v30 )
                  {
                    v13 = 100 * (unsigned __int64)v10 / v30;
                    if ( (unsigned int)v13 > 0x64 )
                      LODWORD(v13) = 100;
                  }
                  else
                  {
                    LODWORD(v13) = 100;
                  }
                  if ( (unsigned int)v13 > v9 )
                  {
                    v5 = CDefragOperation::_SetPercentComplete(this, v13);
                    v23 = v5;
                    if ( v5 < 0 )
                    {
                      v25 = 504;
                      goto LABEL_33;
                    }
                    v24 = 504;
                    v9 = v13;
                  }
                  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 56LL))(v22, &v20);
                  v23 = v5;
                  v6 = 508;
                  if ( v5 < 0 )
                    goto LABEL_32;
                }
                v5 = CDefragOperation::_SetPercentComplete(this, 0x64u);
                v23 = v5;
                v6 = 512;
                if ( v5 < 0 )
                  goto LABEL_32;
                v24 = 512;
                v5 = 0;
                goto LABEL_68;
              }
            }
          }
        }
      }
    }
LABEL_32:
    v25 = v6;
    goto LABEL_33;
  }
  v5 = -2147467259;
  v18 = 385;
LABEL_48:
  v25 = v18;
LABEL_68:
  v23 = v5;
LABEL_33:
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022280  mov     rax, rsp
0x180022283  push    rbp
0x180022284  push    rbx
0x180022285  push    rsi
0x180022286  push    rdi
0x180022287  push    r12
0x180022289  push    r13
0x18002228b  push    r14
0x18002228d  push    r15
0x18002228f  lea     rbp, [rax-0E8h]
0x180022296  sub     rsp, 1A8h
0x18002229d  movaps  xmmword ptr [rax-58h], xmm6
0x1800222a1  mov     rax, cs:__security_cookie
0x1800222a8  xor     rax, rsp
0x1800222ab  mov     [rbp+0E0h+var_60], rax
0x1800222b2  mov     rdi, rcx
0x1800222b5  mov     r9d, 1; unsigned __int16
0x1800222bb  mov     r8d, 162h; unsigned __int16
0x1800222c1  lea     rdx, aCrunbruteforce; "CRunBruteForceEvict::RunOperation"
0x1800222c8  lea     rcx, [rsp+1E0h+var_188]; this
0x1800222cd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800222d2  nop
0x1800222d3  xor     r14d, r14d
0x1800222d6  mov     [rbp+0E0h+var_110], r14
0x1800222da  mov     qword ptr [rsp+1E0h+var_190], r14
0x1800222df  mov     [rbp+0E0h+var_150], r14
0x1800222e3  mov     [rsp+1E0h+var_198], r14
0x1800222e8  mov     dword ptr [rsp+1E0h+var_1A0], r14d
0x1800222ed  mov     [rbp+0E0h+var_140], r14d
0x1800222f1  mov     [rbp+0E0h+var_12C], r14d
0x1800222f5  mov     [rbp+0E0h+var_13C], r14d
0x1800222f9  mov     [rbp+0E0h+var_144], r14d
0x1800222fd  mov     [rbp+0E0h+var_130], r14d
0x180022301  mov     [rbp+0E0h+var_148], r14d
0x180022305  mov     [rbp+0E0h+var_134], r14d
0x180022309  mov     [rbp+0E0h+var_138], r14d
0x18002230d  mov     [rbp+0E0h+var_128], r14
0x180022311  xorps   xmm0, xmm0
0x180022314  movdqa  xmmword ptr [rbp+0E0h+pv], xmm0
0x180022319  xorps   xmm1, xmm1
0x18002231c  movdqa  [rbp+0E0h+var_E0], xmm1
0x180022321  movdqa  [rbp+0E0h+var_D0], xmm0
0x180022326  mov     [rbp+0E0h+var_C0], r14
0x18002232a  mov     [rbp+0E0h+var_B8], r14d
0x18002232e  mov     [rbp+0E0h+var_B4], r14w
0x180022333  movdqa  [rbp+0E0h+var_A0], xmm0
0x180022338  mov     [rbp+0E0h+var_90], r14
0x18002233c  mov     [rbp+0E0h+var_88], r14
0x180022340  mov     [rbp+0E0h+var_80], r14
0x180022344  mov     [rbp+0E0h+var_78], r14
0x180022348  mov     [rbp+0E0h+var_70], r14d
0x18002234c  movups  xmmword ptr [rbp+0E0h+var_108.Data1], xmm0
0x180022350  mov     rcx, [rdi+28h]
0x180022354  mov     rax, [rcx]
0x180022357  lea     rdx, [rbp+0E0h+var_108]
0x18002235b  mov     rax, [rax+98h]
0x180022362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022367  mov     rsi, [rdi+2E8h]
0x18002236e  test    rsi, rsi
0x180022371  jz      short loc_180022383
0x180022373  mov     rax, [rsi]
0x180022376  mov     rcx, rsi
0x180022379  mov     rax, [rax+8]
0x18002237d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022382  nop
0x180022383  mov     [rbp+0E0h+var_110], rsi
0x180022387  test    rsi, rsi
0x18002238a  jz      loc_1800227A0
0x180022390  movups  xmm6, xmmword ptr [rdi+2F8h]
0x180022397  lea     r15, [rdi+38h]
0x18002239b  mov     [r15+88h], r14
0x1800223a2  mov     rcx, [rsp+1E0h+var_198]
0x1800223a7  test    rcx, rcx
0x1800223aa  jz      short loc_1800223BE
0x1800223ac  mov     [rsp+1E0h+var_198], r14
0x1800223b1  mov     rax, [rcx]
0x1800223b4  mov     rax, [rax+10h]
0x1800223b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223bd  nop
0x1800223be  lea     r8, [rsp+1E0h+var_198]; struct IFreeSpaceManager **
0x1800223c3  mov     rdx, [rdi+90h]; unsigned __int64
0x1800223ca  mov     rcx, [rdi+2B8h]; unsigned __int16 *
0x1800223d1  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x1800223d6  mov     ebx, eax
0x1800223d8  mov     [rsp+1E0h+var_188], eax
0x1800223dc  test    eax, eax
0x1800223de  mov     eax, 189h
0x1800223e3  js      loc_1800226C0
0x1800223e9  mov     [rsp+1E0h+var_184], ax
0x1800223ee  mov     rax, [rsi]
0x1800223f1  lea     rcx, [rbp+0E0h+var_138]
0x1800223f5  mov     qword ptr [rsp+1E0h+var_1C0], rcx
0x1800223fa  lea     r9, [rbp+0E0h+var_134]
0x1800223fe  lea     r8, [rbp+0E0h+var_148]
0x180022402  lea     rdx, [rbp+0E0h+var_130]
0x180022406  mov     rcx, rsi
0x180022409  mov     rax, [rax+0C0h]
0x180022410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022415  mov     ebx, eax
0x180022417  mov     [rsp+1E0h+var_188], eax
0x18002241b  test    eax, eax
0x18002241d  mov     eax, 18Dh
0x180022422  js      loc_1800226C0
0x180022428  mov     [rsp+1E0h+var_184], ax
0x18002242d  cmp     [rbp+0E0h+var_148], r14d
0x180022431  jnz     loc_1800227EC
0x180022437  mov     rcx, [rdi+30h]
0x18002243b  mov     rax, [rcx]
0x18002243e  mov     rdx, r15
0x180022441  mov     rax, [rax+18h]
0x180022445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002244a  mov     ebx, eax
0x18002244c  mov     [rsp+1E0h+var_188], eax
0x180022450  test    eax, eax
0x180022452  mov     eax, 196h
0x180022457  js      loc_1800226C0
0x18002245d  mov     [rsp+1E0h+var_184], ax
0x180022462  mov     rax, [rsi]
0x180022465  mov     rbx, [rax+68h]
0x180022469  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x18002246e  test    rcx, rcx
0x180022471  jz      short loc_180022485
0x180022473  mov     qword ptr [rsp+1E0h+var_190], r14
0x180022478  mov     rdx, [rcx]
0x18002247b  mov     rax, [rdx+10h]
0x18002247f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022484  nop
0x180022485  lea     r8, [rsp+1E0h+var_190]
0x18002248a  xor     edx, edx
0x18002248c  mov     rcx, rsi
0x18002248f  mov     rax, rbx
0x180022492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022497  mov     ebx, eax
0x180022499  mov     [rsp+1E0h+var_188], eax
0x18002249d  test    eax, eax
0x18002249f  mov     eax, 199h
0x1800224a4  js      loc_1800226C0
0x1800224aa  mov     [rsp+1E0h+var_184], ax
0x1800224af  mov     edx, 4
0x1800224b4  mov     rcx, rdi
0x1800224b7  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x1800224bc  mov     ebx, eax
0x1800224be  mov     [rsp+1E0h+var_188], eax
0x1800224c2  test    eax, eax
0x1800224c4  mov     eax, 19Ch
0x1800224c9  js      loc_1800226C0
0x1800224cf  mov     [rsp+1E0h+var_184], ax
0x1800224d4  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x1800224d9  mov     rax, [rcx]
0x1800224dc  lea     rdx, [rbp+0E0h+var_13C]
0x1800224e0  mov     rax, [rax+40h]
0x1800224e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e9  xor     edx, edx; unsigned int
0x1800224eb  mov     rcx, rdi; this
0x1800224ee  call    ?_SetPercentComplete@CDefragOperation@@IEAAJK@Z; CDefragOperation::_SetPercentComplete(ulong)
0x1800224f3  mov     rcx, [rsp+1E0h+var_198]
0x1800224f8  movdqa  [rbp+0E0h+var_120], xmm6
0x1800224fd  mov     rax, [rcx]
0x180022500  lea     rdx, [rbp+0E0h+var_120]
0x180022504  mov     rax, [rax+30h]
0x180022508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002250d  mov     ebx, eax
0x18002250f  mov     [rsp+1E0h+var_188], eax
0x180022513  test    eax, eax
0x180022515  mov     eax, 1A7h
0x18002251a  js      loc_1800226C0
0x180022520  mov     [rsp+1E0h+var_184], ax
0x180022525  mov     rcx, [rsp+1E0h+var_198]
0x18002252a  mov     rax, [rcx]
0x18002252d  mov     rax, [rax+18h]
0x180022531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022536  mov     ebx, eax
0x180022538  mov     [rsp+1E0h+var_188], eax
0x18002253c  test    eax, eax
0x18002253e  mov     eax, 1A8h
0x180022543  js      loc_1800226C0
0x180022549  mov     [rsp+1E0h+var_184], ax
0x18002254e  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x180022553  mov     rax, [rcx]
0x180022556  lea     rdx, [rsp+1E0h+var_1A0]
0x18002255b  mov     rax, [rax+30h]
0x18002255f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022564  mov     ebx, eax
0x180022566  mov     [rsp+1E0h+var_188], eax
0x18002256a  test    eax, eax
0x18002256c  mov     eax, 1ABh
0x180022571  js      loc_1800226C0
0x180022577  mov     r13d, r14d
0x18002257a  mov     r12d, r14d
0x18002257d  mov     [rsp+1E0h+var_184], ax
0x180022582  cmp     ebx, 1
0x180022585  jz      loc_180022953
0x18002258b  mov     rax, [rsi]
0x18002258e  mov     rax, [rax+38h]
0x180022592  mov     r8, [rbp+0E0h+var_150]
0x180022596  test    r8, r8
0x180022599  jz      loc_18002277B
0x18002259f  xor     r9d, r9d
0x1800225a2  mov     edx, dword ptr [rsp+1E0h+var_1A0]
0x1800225a6  mov     rcx, rsi
0x1800225a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225ae  mov     ebx, eax
0x1800225b0  mov     [rsp+1E0h+var_188], eax
0x1800225b4  test    eax, eax
0x1800225b6  mov     eax, 1B1h
0x1800225bb  js      loc_1800226C0
0x1800225c1  mov     [rsp+1E0h+var_184], ax
0x1800225c6  mov     rcx, [rbp+0E0h+var_150]
0x1800225ca  mov     rax, [rcx]
0x1800225cd  lea     r8, [rbp+0E0h+var_144]
0x1800225d1  mov     edx, 1
0x1800225d6  mov     rax, [rax+40h]
0x1800225da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225df  mov     ebx, eax
0x1800225e1  mov     [rsp+1E0h+var_188], eax
0x1800225e5  test    eax, eax
0x1800225e7  mov     eax, 1B8h
0x1800225ec  js      loc_1800226C0
0x1800225f2  mov     [rsp+1E0h+var_184], ax
0x1800225f7  cmp     [rbp+0E0h+var_144], r14d
0x1800225fb  jnz     short loc_18002263F
0x1800225fd  mov     rcx, [rbp+0E0h+var_150]
0x180022601  movdqa  [rbp+0E0h+var_120], xmm6
0x180022606  mov     rax, [rcx]
0x180022609  lea     r8, [rbp+0E0h+var_140]
0x18002260d  lea     rdx, [rbp+0E0h+var_120]
0x180022611  mov     rax, [rax+98h]
0x180022618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002261d  mov     ebx, eax
0x18002261f  mov     [rsp+1E0h+var_188], eax
0x180022623  test    eax, eax
0x180022625  mov     eax, 1BEh
0x18002262a  js      loc_1800226C0
0x180022630  mov     [rsp+1E0h+var_184], ax
0x180022635  cmp     [rbp+0E0h+var_140], r14d
0x180022639  jnz     loc_18002281D
0x18002263f  mov     rax, [rdi]
0x180022642  mov     rcx, rdi
0x180022645  mov     rax, [rax+20h]
0x180022649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002264e  mov     ebx, eax
0x180022650  mov     [rsp+1E0h+var_188], eax
0x180022654  test    eax, eax
0x180022656  mov     eax, 1E7h
0x18002265b  js      short loc_1800226C0
0x18002265d  inc     r12d
0x180022660  mov     [rsp+1E0h+var_184], ax
0x180022665  mov     ecx, [rbp+0E0h+var_13C]
0x180022668  test    ecx, ecx
0x18002266a  jz      loc_180022770
0x180022670  mov     eax, r12d
0x180022673  imul    rax, 64h ; 'd'
0x180022677  xor     edx, edx
0x180022679  div     rcx
0x18002267c  mov     r14, rax
0x18002267f  mov     eax, 64h ; 'd'
0x180022684  cmp     r14d, eax
0x180022687  cmova   r14d, eax
0x18002268b  cmp     r14d, r13d
0x18002268e  ja      loc_1800228A8
0x180022694  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x180022699  mov     rax, [rcx]
0x18002269c  lea     rdx, [rsp+1E0h+var_1A0]
0x1800226a1  mov     rax, [rax+38h]
0x1800226a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226aa  mov     ebx, eax
0x1800226ac  mov     [rsp+1E0h+var_188], eax
0x1800226b0  xor     r14d, r14d
0x1800226b3  test    eax, eax
0x1800226b5  mov     eax, 1FCh
0x1800226ba  jns     loc_18002257D
0x1800226c0  mov     [rsp+1E0h+var_182], ax
0x1800226c5  mov     rcx, [rbp+0E0h+pv]; pv
0x1800226c9  test    rcx, rcx
0x1800226cc  jnz     loc_180022984
0x1800226d2  mov     rcx, [rsp+1E0h+var_198]
0x1800226d7  test    rcx, rcx
0x1800226da  jz      short loc_1800226EE
0x1800226dc  mov     [rsp+1E0h+var_198], r14
0x1800226e1  mov     rax, [rcx]
0x1800226e4  mov     rax, [rax+10h]
0x1800226e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226ed  nop
0x1800226ee  mov     rcx, [rbp+0E0h+var_150]
0x1800226f2  test    rcx, rcx
0x1800226f5  jz      short loc_180022708
0x1800226f7  mov     [rbp+0E0h+var_150], r14
0x1800226fb  mov     rax, [rcx]
0x1800226fe  mov     rax, [rax+10h]
0x180022702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022707  nop
0x180022708  mov     rcx, qword ptr [rsp+1E0h+var_190]
0x18002270d  test    rcx, rcx
0x180022710  jz      short loc_180022724
0x180022712  mov     qword ptr [rsp+1E0h+var_190], r14
0x180022717  mov     rax, [rcx]
0x18002271a  mov     rax, [rax+10h]
0x18002271e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022723  nop
0x180022724  test    rsi, rsi
  ... truncated ...
```
