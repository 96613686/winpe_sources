# CITEWcsTranslateColors

- ea: `0x180052410`
- end: `0x1800527eb`
- name: `CITEWcsTranslateColors`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18003e2d0`

## callees

- `0x18000fe30`
- `0x180018eb0`
- `0x18001b074`
- `0x1800286cc`
- `0x18002b058`
- `0x18002e5f0`
- `0x18002e670`
- `0x180052410`
- `0x180054924`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!_finite` at `0x18005251a`
- `api-ms-win-crt-math-l1-1-0!_finite` at `0x18005251a`
- `ntdll!EtwEventWrite` at `0x1800524ed`
- `ntdll!EtwEventWrite` at `0x1800524ed`

## pseudocode

```c
__int64 __fastcall CITEWcsTranslateColors(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        enum COLORDATATYPE a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        enum COLORDATATYPE a8,
        unsigned int a9,
        __int64 a10)
{
  unsigned int v11; // r12d
  ULONG v12; // r8d
  struct ICITEPixelConverter *v14; // rdi
  unsigned __int64 v15; // r14
  struct ICITEPixelConverter *v16; // rsi
  int v17; // ebx
  enum COLORDATATYPE v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // r12
  __int64 v21; // rdi
  void *v22; // rax
  void *v23; // rax
  __int64 v24; // r12
  void *v25; // rax
  __int64 *v26; // r13
  void (__fastcall **v27)(_QWORD, _QWORD); // rax
  __int64 v28; // rax
  __int64 v29; // r13
  ULONG pulResult[2]; // [rsp+40h] [rbp-61h] BYREF
  enum COLORDATATYPE v32[2]; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v33; // [rsp+50h] [rbp-51h]
  struct ICITEPixelConverter *v34; // [rsp+58h] [rbp-49h] BYREF
  __int64 v35; // [rsp+60h] [rbp-41h] BYREF
  struct ICITEPixelConverter *v36; // [rsp+68h] [rbp-39h] BYREF
  __int64 v37; // [rsp+70h] [rbp-31h]
  __int64 v38; // [rsp+78h] [rbp-29h]
  _QWORD v39[2]; // [rsp+80h] [rbp-21h] BYREF

  v11 = a7;
  v12 = 0;
  v32[0] = a4;
  v14 = 0;
  v15 = a2;
  v16 = 0;
  v37 = a6;
  v33 = a7;
  v38 = a10;
  v34 = 0;
  v36 = 0;
  if ( !a6
    || !a10
    || !a5
    || !a9
    || !a2
    || !a1
    || !a3
    || !a7
    || a3 > 8
    || a7 > 8
    || (v17 = 0, !(unsigned int)ValidHandle(a1, 1129599565)) )
  {
    v17 = -2147024809;
  }
  pulResult[0] = v12;
  v39[0] = pulResult;
  v39[1] = 4;
  EtwEventWrite(g_etwHandle, FLOATING_POINT_OR_INTEGER_LUT, 1, v39);
  v18 = v32[0];
  if ( v32[0] == COLOR_FLOAT )
  {
    v19 = v15 * a3;
    v20 = 0;
    pulResult[0] = v15 * a3;
    while ( (unsigned int)v20 < v19 )
    {
      if ( !_finite(*(float *)(v37 + 4 * v20)) )
      {
        v17 = -2147024809;
        goto LABEL_40;
      }
      v19 = pulResult[0];
      v20 = (unsigned int)(v20 + 1);
    }
    v11 = v33;
    v18 = v32[0];
  }
  if ( v17 >= 0 )
  {
    v21 = *(_QWORD *)((a1 ^ 0x49434D20) + 0x18);
    v39[0] = v21;
    v17 = CreateCITEPixelConverter(*(_DWORD *)(v21 + 20), a3, v18, v15, a5, &v34);
    if ( v17 >= 0 )
    {
      v17 = CreateCITEPixelConverter(*(_DWORD *)(v21 + 24), v11, a8, v15, a9, &v36);
      if ( v17 >= 0 )
      {
        if ( ULongLongToULong(v15 * 4 * a3, pulResult) >= 0 )
        {
          v17 = ULongLongToULong(v15 * 4 * v11, pulResult);
          if ( v17 >= 0 )
          {
            *(_QWORD *)v32 = 0;
            v35 = 0;
            v22 = operator new(saturated_mul((unsigned int)v15 * a3, 4u));
            NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(v32, (__int64)v22);
            v23 = operator new(saturated_mul((unsigned int)v15 * v11, 4u));
            NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(&v35, (__int64)v23);
            if ( !*(_QWORD *)v32 || !v35 )
              v17 = -2147024882;
            *(_QWORD *)pulResult = 0;
            NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(pulResult);
            v16 = v36;
            v24 = 0;
            *(_QWORD *)pulResult = 0;
            v14 = v34;
            if ( v17 >= 0 )
            {
              if ( (*(unsigned int (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v34 + 24LL))(v34)
                && (*(unsigned int (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v16 + 24LL))(v16)
                && (v25 = operator new(saturated_mul(v15, 4u)),
                    NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(pulResult, (__int64)v25),
                    (v24 = *(_QWORD *)pulResult) == 0) )
              {
                v17 = -2147024882;
              }
              else
              {
                v26 = *(__int64 **)v39[0];
                v27 = *(void (__fastcall ***)(_QWORD, _QWORD))v14;
                v39[0] = *(_QWORD *)v39[0];
                v17 = ((__int64 (__fastcall *)(struct ICITEPixelConverter *, __int64, _QWORD, __int64))v27[6])(
                        v14,
                        v37,
                        *(_QWORD *)v32,
                        v24);
                if ( v17 >= 0 )
                {
                  v28 = *v26;
                  v29 = v35;
                  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int64))(v28 + 32))(
                          v39[0],
                          (unsigned int)v15,
                          a3,
                          v33,
                          *(_QWORD *)v32,
                          v35);
                  if ( v17 >= 0 )
                    v17 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *, __int64, __int64, __int64))(*(_QWORD *)v16 + 40LL))(
                            v16,
                            v29,
                            v24,
                            v38);
                }
              }
            }
            NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(pulResult);
            NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v35);
            NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(v32);
            goto LABEL_40;
          }
        }
        v17 = -2147024809;
      }
      v16 = v36;
    }
    v14 = v34;
  }
LABEL_40:
  if ( v14 )
    (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v14)(v14, 1);
  if ( v16 )
    (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v16)(v16, 1);
  if ( v17 >= 0 )
    return 1;
  SetLastErrorFromHRESULT((unsigned int)v17, 2020);
  return 0;
}

```

## disassembly

```asm
0x180052410  push    rbp
0x180052412  push    rbx
0x180052413  push    rsi
0x180052414  push    rdi
0x180052415  push    r12
0x180052417  push    r13
0x180052419  push    r14
0x18005241b  push    r15
0x18005241d  lea     rbp, [rsp-7]
0x180052422  sub     rsp, 0A8h
0x180052429  mov     rax, cs:__security_cookie
0x180052430  xor     rax, rsp
0x180052433  mov     [rbp+3Fh+var_50], rax
0x180052437  mov     rax, [rbp+3Fh+arg_28]
0x18005243b  mov     r15d, r8d
0x18005243e  mov     r12d, [rbp+3Fh+arg_30]
0x180052442  xor     r8d, r8d
0x180052445  mov     [rbp+3Fh+var_98], r9d
0x180052449  mov     r13, rcx
0x18005244c  mov     rcx, [rbp+3Fh+arg_48]
0x180052453  mov     edi, r8d
0x180052456  mov     r14d, edx
0x180052459  mov     esi, r8d
0x18005245c  mov     [rbp+3Fh+var_70], rax
0x180052460  mov     [rbp+3Fh+var_90], r12d
0x180052464  mov     [rbp+3Fh+var_68], rcx
0x180052468  mov     [rbp+3Fh+var_88], r8
0x18005246c  mov     [rbp+3Fh+var_78], r8
0x180052470  test    rax, rax
0x180052473  jz      short loc_1800524BC
0x180052475  test    rcx, rcx
0x180052478  jz      short loc_1800524BC
0x18005247a  cmp     [rbp+3Fh+arg_20], r8d
0x18005247e  jz      short loc_1800524BC
0x180052480  cmp     [rbp+3Fh+arg_40], r8d
0x180052487  jz      short loc_1800524BC
0x180052489  test    edx, edx
0x18005248b  jz      short loc_1800524BC
0x18005248d  test    r13, r13
0x180052490  jz      short loc_1800524BC
0x180052492  test    r15d, r15d
0x180052495  jz      short loc_1800524BC
0x180052497  test    r12d, r12d
0x18005249a  jz      short loc_1800524BC
0x18005249c  cmp     r15d, 8
0x1800524a0  ja      short loc_1800524BC
0x1800524a2  cmp     r12d, 8
0x1800524a6  ja      short loc_1800524BC
0x1800524a8  mov     edx, 4354524Dh
0x1800524ad  mov     rcx, r13
0x1800524b0  mov     ebx, r8d
0x1800524b3  call    ValidHandle
0x1800524b8  test    eax, eax
0x1800524ba  jnz     short loc_1800524C1
0x1800524bc  mov     ebx, 80070057h
0x1800524c1  mov     rcx, cs:g_etwHandle
0x1800524c8  lea     rax, [rbp+3Fh+pulResult]
0x1800524cc  mov     [rbp+3Fh+pulResult], r8d
0x1800524d0  lea     r9, [rbp+3Fh+var_60]
0x1800524d4  mov     r8d, 1
0x1800524da  mov     [rbp+3Fh+var_60], rax
0x1800524de  lea     rdx, FLOATING_POINT_OR_INTEGER_LUT
0x1800524e5  mov     [rbp+3Fh+var_58], 4
0x1800524ed  call    cs:__imp_EtwEventWrite
0x1800524f3  mov     ecx, [rbp+3Fh+var_98]
0x1800524f6  cmp     ecx, 3
0x1800524f9  jnz     short loc_18005253D
0x1800524fb  mov     eax, r15d
0x1800524fe  imul    eax, r14d
0x180052502  xor     r12d, r12d
0x180052505  mov     [rbp+3Fh+pulResult], eax
0x180052508  cmp     r12d, eax
0x18005250b  jnb     short loc_180052536
0x18005250d  mov     rcx, [rbp+3Fh+var_70]
0x180052511  movss   xmm0, dword ptr [rcx+r12*4]
0x180052517  cvtps2pd xmm0, xmm0; X
0x18005251a  call    cs:__imp__finite
0x180052520  test    eax, eax
0x180052522  jz      short loc_18005252C
0x180052524  mov     eax, [rbp+3Fh+pulResult]
0x180052527  inc     r12d
0x18005252a  jmp     short loc_180052508
0x18005252c  mov     ebx, 80070057h
0x180052531  jmp     loc_180052782
0x180052536  mov     r12d, [rbp+3Fh+var_90]
0x18005253a  mov     ecx, [rbp+3Fh+var_98]
0x18005253d  test    ebx, ebx
0x18005253f  js      loc_180052782
0x180052545  lea     rax, [rbp+3Fh+var_88]
0x180052549  mov     r8d, ecx; enum COLORDATATYPE
0x18005254c  mov     [rsp+0E0h+var_B8], rax; struct ICITEPixelConverter **
0x180052551  xor     r13, 49434D20h
0x180052558  mov     eax, [rbp+3Fh+arg_20]
0x18005255b  mov     r9d, r14d; unsigned int
0x18005255e  mov     edx, r15d; unsigned int
0x180052561  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x180052565  mov     rdi, [r13+18h]
0x180052569  mov     [rbp+3Fh+var_60], rdi
0x18005256d  mov     ecx, [rdi+14h]; int
0x180052570  call    ?CreateCITEPixelConverter@@YAJHIW4COLORDATATYPE@@IIPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,uint,COLORDATATYPE,uint,uint,ICITEPixelConverter * *)
0x180052575  mov     ebx, eax
0x180052577  test    eax, eax
0x180052579  js      loc_18005277E
0x18005257f  mov     r8d, [rbp+3Fh+arg_38]; enum COLORDATATYPE
0x180052586  lea     rax, [rbp+3Fh+var_78]
0x18005258a  mov     ecx, [rdi+18h]; int
0x18005258d  mov     r9d, r14d; unsigned int
0x180052590  mov     [rsp+0E0h+var_B8], rax; struct ICITEPixelConverter **
0x180052595  mov     edx, r12d; unsigned int
0x180052598  mov     eax, [rbp+3Fh+arg_40]
0x18005259e  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x1800525a2  call    ?CreateCITEPixelConverter@@YAJHIW4COLORDATATYPE@@IIPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,uint,COLORDATATYPE,uint,uint,ICITEPixelConverter * *)
0x1800525a7  xor     edi, edi
0x1800525a9  mov     ebx, eax
0x1800525ab  test    eax, eax
0x1800525ad  js      loc_18005277A
0x1800525b3  lea     ecx, ds:0[r15*4]
0x1800525bb  mov     r13, r14
0x1800525be  imul    rcx, r14; ullOperand
0x1800525c2  lea     rdx, [rbp+3Fh+pulResult]; pulResult
0x1800525c6  call    ULongLongToULong
0x1800525cb  test    eax, eax
0x1800525cd  js      loc_180052775
0x1800525d3  lea     ecx, ds:0[r12*4]
0x1800525db  imul    rcx, r13; ullOperand
0x1800525df  lea     rdx, [rbp+3Fh+pulResult]; pulResult
0x1800525e3  call    ULongLongToULong
0x1800525e8  mov     ebx, eax
0x1800525ea  test    eax, eax
0x1800525ec  js      loc_180052775
0x1800525f2  mov     ecx, r15d
0x1800525f5  mov     qword ptr [rbp+3Fh+var_98], rdi
0x1800525f9  imul    ecx, r14d
0x1800525fd  lea     esi, [rdi+4]
0x180052600  mov     eax, esi
0x180052602  mov     [rbp+3Fh+var_80], rdi
0x180052606  mul     rcx
0x180052609  lea     rcx, [rdi-1]
0x18005260d  cmovb   rax, rcx
0x180052611  mov     rcx, rax; Size
0x180052614  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052619  mov     rdx, rax
0x18005261c  lea     rcx, [rbp+3Fh+var_98]
0x180052620  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x180052625  mov     ecx, r12d
0x180052628  mov     eax, esi
0x18005262a  imul    ecx, r14d
0x18005262e  mul     rcx
0x180052631  lea     rcx, [rdi-1]
0x180052635  cmovb   rax, rcx
0x180052639  mov     rcx, rax; Size
0x18005263c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052641  mov     rdx, rax
0x180052644  lea     rcx, [rbp+3Fh+var_80]
0x180052648  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x18005264d  cmp     qword ptr [rbp+3Fh+var_98], rdi
0x180052651  jz      short loc_180052659
0x180052653  cmp     [rbp+3Fh+var_80], rdi
0x180052657  jnz     short loc_18005265E
0x180052659  mov     ebx, 8007000Eh
0x18005265e  lea     rcx, [rbp+3Fh+pulResult]
0x180052662  mov     qword ptr [rbp+3Fh+pulResult], rdi
0x180052666  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x18005266b  mov     rsi, [rbp+3Fh+var_78]
0x18005266f  mov     r12, rdi
0x180052672  mov     qword ptr [rbp+3Fh+pulResult], rdi
0x180052676  mov     rdi, [rbp+3Fh+var_88]
0x18005267a  test    ebx, ebx
0x18005267c  js      loc_180052758
0x180052682  mov     rax, [rdi]
0x180052685  mov     rcx, rdi
0x180052688  mov     rax, [rax+18h]
0x18005268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052691  test    eax, eax
0x180052693  jz      short loc_1800526DF
0x180052695  mov     rcx, [rsi]
0x180052698  mov     rax, [rcx+18h]
0x18005269c  mov     rcx, rsi
0x18005269f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526a4  test    eax, eax
0x1800526a6  jz      short loc_1800526DF
0x1800526a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800526af  mov     eax, 4
0x1800526b4  mul     r13
0x1800526b7  cmovb   rax, rcx
0x1800526bb  mov     rcx, rax; Size
0x1800526be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800526c3  mov     rdx, rax
0x1800526c6  lea     rcx, [rbp+3Fh+pulResult]
0x1800526ca  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x1800526cf  mov     r12, qword ptr [rbp+3Fh+pulResult]
0x1800526d3  test    r12, r12
0x1800526d6  jnz     short loc_1800526DF
0x1800526d8  mov     ebx, 8007000Eh
0x1800526dd  jmp     short loc_180052758
0x1800526df  mov     rax, [rbp+3Fh+var_60]
0x1800526e3  mov     r9, r12
0x1800526e6  mov     r8, qword ptr [rbp+3Fh+var_98]
0x1800526ea  mov     rcx, rdi
0x1800526ed  mov     rdx, [rbp+3Fh+var_70]
0x1800526f1  mov     r13, [rax]
0x1800526f4  mov     rax, [rdi]
0x1800526f7  mov     [rbp+3Fh+var_60], r13
0x1800526fb  mov     rax, [rax+30h]
0x1800526ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052704  mov     ebx, eax
0x180052706  test    eax, eax
0x180052708  js      short loc_180052758
0x18005270a  mov     rax, [r13+0]
0x18005270e  mov     r8d, r15d
0x180052711  mov     rcx, qword ptr [rbp+3Fh+var_98]
0x180052715  mov     edx, r14d
0x180052718  mov     r13, [rbp+3Fh+var_80]
0x18005271c  mov     r9d, [rbp+3Fh+var_90]
0x180052720  mov     rax, [rax+20h]
0x180052724  mov     [rsp+0E0h+var_B8], r13
0x180052729  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18005272e  mov     rcx, [rbp+3Fh+var_60]
0x180052732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052737  mov     ebx, eax
0x180052739  test    eax, eax
0x18005273b  js      short loc_180052758
0x18005273d  mov     rax, [rsi]
0x180052740  mov     r8, r12
0x180052743  mov     r9, [rbp+3Fh+var_68]
0x180052747  mov     rdx, r13
0x18005274a  mov     rcx, rsi
0x18005274d  mov     rax, [rax+28h]
0x180052751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052756  mov     ebx, eax
0x180052758  lea     rcx, [rbp+3Fh+pulResult]
0x18005275c  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180052761  lea     rcx, [rbp+3Fh+var_80]
0x180052765  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x18005276a  lea     rcx, [rbp+3Fh+var_98]
0x18005276e  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180052773  jmp     short loc_180052782
0x180052775  mov     ebx, 80070057h
0x18005277a  mov     rsi, [rbp+3Fh+var_78]
0x18005277e  mov     rdi, [rbp+3Fh+var_88]
0x180052782  test    rdi, rdi
0x180052785  jz      short loc_18005279A
0x180052787  mov     rax, [rdi]
0x18005278a  mov     edx, 1
0x18005278f  mov     rcx, rdi
0x180052792  mov     rax, [rax]
0x180052795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005279a  test    rsi, rsi
0x18005279d  jz      short loc_1800527B2
0x18005279f  mov     rdx, [rsi]
0x1800527a2  mov     rcx, rsi
0x1800527a5  mov     rax, [rdx]
0x1800527a8  mov     edx, 1
0x1800527ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527b2  test    ebx, ebx
0x1800527b4  js      short loc_1800527BD
0x1800527b6  mov     eax, 1
0x1800527bb  jmp     short loc_1800527CB
0x1800527bd  mov     edx, 7E4h
0x1800527c2  mov     ecx, ebx
0x1800527c4  call    SetLastErrorFromHRESULT
0x1800527c9  xor     eax, eax
0x1800527cb  mov     rcx, [rbp+3Fh+var_50]
0x1800527cf  xor     rcx, rsp; StackCookie
0x1800527d2  call    __security_check_cookie
0x1800527d7  add     rsp, 0A8h
0x1800527de  pop     r15
0x1800527e0  pop     r14
0x1800527e2  pop     r13
0x1800527e4  pop     r12
0x1800527e6  pop     rdi
0x1800527e7  pop     rsi
0x1800527e8  pop     rbx
0x1800527e9  pop     rbp
0x1800527ea  retn
```
