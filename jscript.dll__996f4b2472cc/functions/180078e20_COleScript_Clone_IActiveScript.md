# COleScript::Clone(IActiveScript * *)

- ea: `0x180078e20`
- end: `0x1800794d9`
- name: `?Clone@COleScript@@UEAAJPEAPEAUIActiveScript@@@Z`
- size: `1721`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScript **)`
- caller_count: `0`
- callee_count: `19`
- tags: ``

## callees

- `0x180013450`
- `0x180016c84`
- `0x180016d00`
- `0x180016e68`
- `0x1800172e8`
- `0x1800179d0`
- `0x18002ef60`
- `0x180041358`
- `0x180041b54`
- `0x180041fdc`
- `0x180048c58`
- `0x1800585d0`
- `0x180067fd0`
- `0x180078e20`
- `0x1800794e0`
- `0x18007ca60`
- `0x180096692`
- `0x18009669e`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007935d`
- `KERNEL32!GetCurrentThreadId` at `0x18007935d`

## pseudocode

```c
__int64 __fastcall COleScript::Clone(COleScript *this, struct IActiveScript **a2)
{
  struct IActiveScript **v2; // r12
  COleScript *v5; // rax
  COleScript *v6; // rax
  COleScript *v7; // rdi
  int v8; // ebx
  __int64 v9; // rax
  char *v10; // r15
  _DWORD *v11; // rax
  int i; // r12d
  CScriptBody *v13; // rbx
  __int64 v14; // r13
  int v15; // r9d
  signed int v16; // edx
  int v17; // r15d
  struct VVAL *v18; // rax
  CScriptBody **v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  char *v22; // r12
  _DWORD *v23; // rax
  signed int v24; // edx
  char *v25; // rbx
  __int64 v26; // rbx
  int v27; // r8d
  size_t v28; // r13
  int v29; // r15d
  struct VVAL *v30; // rax
  NameList *v31; // rax
  NameList *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  struct VVAL *v35; // rcx
  int v36; // ebx
  _DWORD *v37; // rax
  __int64 v38; // rax
  int v39; // edx
  __int64 v40; // rbx
  int v41; // r8d
  size_t v42; // r13
  int v43; // r15d
  char *v44; // rax
  int v45; // edx
  int v46; // [rsp+30h] [rbp-40h]
  int v47; // [rsp+30h] [rbp-40h]
  int v48; // [rsp+30h] [rbp-40h]
  __int128 Src; // [rsp+38h] [rbp-38h] BYREF
  char *v50; // [rsp+48h] [rbp-28h] BYREF
  __int128 v51; // [rsp+50h] [rbp-20h] BYREF
  __int64 v52; // [rsp+60h] [rbp-10h]
  unsigned int j; // [rsp+C0h] [rbp+50h] BYREF
  struct VVAL *v55; // [rsp+C8h] [rbp+58h] BYREF

  v2 = a2;
  Src = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( *((_DWORD *)this + 42) == 4 )
    return 2147549183LL;
  v5 = (COleScript *)operator new(0x3F8u);
  if ( !v5 )
    return 2147942414LL;
  v6 = COleScript::COleScript(v5, *((const struct _GUID **)this + 24), *((const unsigned __int16 **)this + 23));
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *((_DWORD *)v6 + 240) = *((_DWORD *)this + 240);
  if ( !(unsigned int)COleScript::Initialize(v6) )
  {
    COleScript::`vector deleting destructor'(v7, 1u);
    return 2147942414LL;
  }
  if ( !(unsigned int)COleScript::DisableInterrupts(this) )
    return 2147500037LL;
  *((_DWORD *)v7 + 66) = *((_DWORD *)this + 66);
  *((_DWORD *)v7 + 172) = *((_DWORD *)this + 172);
  v8 = NamedItemList::Clone((COleScript *)((char *)this + 312), (COleScript *)((char *)v7 + 312));
  if ( v8 >= 0 )
  {
    *((_DWORD *)v7 + 76) = NamedItemList::FindHighestMod((COleScript *)((char *)v7 + 312)) + 1;
    v9 = *((_QWORD *)this + 87);
    if ( !v9 )
      goto LABEL_30;
    v46 = *(_DWORD *)(v9 + 28);
    if ( v46 <= 0 )
      goto LABEL_30;
    v10 = (char *)v7 + 696;
    v50 = (char *)v7 + 696;
    if ( *((_QWORD *)v7 + 87) )
    {
LABEL_18:
      for ( i = 0; i < v46; ++i )
      {
        memcpy_0(
          &Src,
          (const void *)(*(_QWORD *)(*((_QWORD *)this + 87) + 16LL) + i * *(_DWORD *)(*((_QWORD *)this + 87) + 12LL)),
          *(int *)(*((_QWORD *)this + 87) + 12LL));
        if ( (Src & 1) != 0 )
        {
          LODWORD(Src) = 3;
          *((_QWORD *)&Src + 1) = CScriptBody::PbodyClone(*((CScriptBody **)&Src + 1), v7);
          v13 = (CScriptBody *)*((_QWORD *)&Src + 1);
          if ( !*((_QWORD *)&Src + 1) )
            goto LABEL_56;
          v14 = *(_QWORD *)v10;
          v15 = *(_DWORD *)(*(_QWORD *)v10 + 28LL);
          v16 = *(_DWORD *)(*(_QWORD *)v10 + 12LL);
          LODWORD(v55) = v15;
          j = v16;
          v17 = v16 * (v15 + 1);
          if ( v17 > *(_DWORD *)(v14 + 24) )
          {
            if ( !(unsigned int)GL::FEnsureSize((GL *)v14, v17) )
            {
              CScriptBody::Release(v13);
              goto LABEL_56;
            }
            v16 = j;
            v15 = (int)v55;
          }
          v18 = (struct VVAL *)(v15 * v16 + *(_QWORD *)(v14 + 16));
          v55 = v18;
          if ( v15 < *(_DWORD *)(v14 + 28) )
          {
            memmove_0((char *)v18 + v16, v18, v17 - v15 * v16 - v16);
            v16 = j;
            v18 = v55;
          }
          memcpy_0(v18, &Src, v16);
          ++*(_DWORD *)(v14 + 28);
          v19 = (CScriptBody **)((char *)v7 + 912);
          v20 = *((_QWORD *)v7 + 114);
          *((_QWORD *)v13 + 5) = v20;
          if ( v20 )
            *(_QWORD *)(v20 + 48) = (char *)v13 + 40;
          v10 = v50;
          *((_QWORD *)v13 + 6) = v19;
          *v19 = v13;
        }
      }
LABEL_30:
      v21 = *((_QWORD *)this + 89);
      if ( v21 )
      {
        v47 = *(_DWORD *)(v21 + 28);
        if ( v47 > 0 )
        {
          v22 = (char *)v7 + 712;
          v50 = 0;
          *(_QWORD *)&Src = 0;
          if ( *((_QWORD *)v7 + 89) )
          {
LABEL_35:
            v24 = 0;
            j = 0;
            while ( 1 )
            {
              memcpy_0(
                &v50,
                (const void *)(*(_QWORD *)(*((_QWORD *)this + 89) + 16LL)
                             + v24 * *(_DWORD *)(*((_QWORD *)this + 89) + 12LL)),
                *(int *)(*((_QWORD *)this + 89) + 12LL));
              v25 = v50;
              if ( (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v50 + 40LL))(v50) )
              {
                v8 = (*(__int64 (__fastcall **)(char *, __int128 *, COleScript *))(*(_QWORD *)v25 + 56LL))(
                       v25,
                       &Src,
                       v7);
                if ( v8 < 0 )
                  goto LABEL_75;
                v26 = *(_QWORD *)v22;
                v27 = *(_DWORD *)(*(_QWORD *)v22 + 28LL);
                v28 = *(int *)(*(_QWORD *)v22 + 12LL);
                LODWORD(v55) = v27;
                v29 = v28 * (v27 + 1);
                if ( v29 > *(_DWORD *)(v26 + 24) )
                {
                  if ( !(unsigned int)GL::FEnsureSize((GL *)v26, v29) )
                  {
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Src + 8LL))(Src);
                    goto LABEL_56;
                  }
                  v27 = (int)v55;
                }
                v30 = (struct VVAL *)(v27 * (int)v28 + *(_QWORD *)(v26 + 16));
                v55 = v30;
                if ( v27 < *(_DWORD *)(v26 + 28) )
                {
                  memmove_0((char *)v30 + v28, v30, v29 - v27 * (int)v28 - (int)v28);
                  v30 = v55;
                }
                memcpy_0(v30, &Src, v28);
                ++*(_DWORD *)(v26 + 28);
              }
              v24 = j + 1;
              j = v24;
              if ( v24 >= v47 )
                goto LABEL_45;
            }
          }
          v23 = operator new(0x20u);
          if ( v23 )
          {
            *(_QWORD *)v23 = &GL::`vftable';
            v23[2] = 1;
            v23[3] = 8;
            *((_QWORD *)v23 + 2) = 0;
            *((_QWORD *)v23 + 3) = 0;
            *(_QWORD *)v22 = v23;
            goto LABEL_35;
          }
LABEL_57:
          *(_QWORD *)v22 = 0;
          goto LABEL_56;
        }
      }
LABEL_45:
      if ( *((_QWORD *)this + 90) )
      {
        j = 0;
        *(_QWORD *)&Src = 0;
        v55 = 0;
        v51 = 0;
        v52 = 0;
        if ( !*((_QWORD *)v7 + 90) )
        {
          v31 = (NameList *)operator new(0xA8u);
          if ( !v31 )
          {
            *((_QWORD *)v7 + 90) = 0;
LABEL_56:
            v8 = -2147024882;
LABEL_75:
            v2 = a2;
            goto LABEL_76;
          }
          v32 = NameList::NameList(v31);
          *((_QWORD *)v7 + 90) = v32;
          if ( !v32 )
            goto LABEL_56;
        }
        v33 = 0xFFFFFFFFLL;
        for ( j = -1;
              (*(unsigned int (__fastcall **)(_QWORD, __int64, unsigned int *, __int128 *, __int128 *))(**((_QWORD **)this + 90) + 24LL))(
                *((_QWORD *)this + 90),
                v33,
                &j,
                &Src,
                &v51);
              v33 = j )
        {
          if ( !(*(unsigned int (__fastcall **)(_QWORD, __int128 *, struct VVAL **, _QWORD))(**((_QWORD **)v7 + 90) + 8LL))(
                  *((_QWORD *)v7 + 90),
                  &v51,
                  &v55,
                  0)
            && !NameList::FCreateVval(*((NameList **)v7 + 90), (struct SYM *)&v51, &v55, 0, 0) )
          {
            goto LABEL_56;
          }
          v34 = Src;
          v35 = v55;
          *(_OWORD *)v55 = *(_OWORD *)Src;
          *((_QWORD *)v35 + 2) = *(_QWORD *)(v34 + 16);
          *((_DWORD *)v55 + 6) = *(_DWORD *)(Src + 24);
        }
      }
      *((_DWORD *)v7 + 252) = *((_DWORD *)this + 252);
      if ( *((_DWORD *)this + 65) != -1 )
      {
        v36 = *((_DWORD *)this + 65);
        if ( v36 != GetCurrentThreadId() )
          COleScript::LogTelemetryOnCloneMultithreading(this);
      }
      *((_DWORD *)v7 + 232) = *((_DWORD *)this + 232) ^ (*((_DWORD *)v7 + 232) ^ *((_DWORD *)this + 232)) & 0xFFFFFFFE;
      if ( *((_QWORD *)this + 88) )
      {
        v22 = (char *)v7 + 704;
        j = 0;
        if ( !*((_QWORD *)v7 + 88) )
        {
          v37 = operator new(0x20u);
          if ( !v37 )
            goto LABEL_57;
          v37[2] = 1;
          *(_QWORD *)v37 = &GL::`vftable';
          v37[3] = 4;
          *((_QWORD *)v37 + 2) = 0;
          *((_QWORD *)v37 + 3) = 0;
          *(_QWORD *)v22 = v37;
        }
        v38 = *((_QWORD *)this + 88);
        v39 = 0;
        LODWORD(v55) = 0;
        for ( LODWORD(Src) = *(_DWORD *)(v38 + 28); v39 < (int)Src; LODWORD(v55) = v39 )
        {
          memcpy_0(
            &j,
            (const void *)(*(_QWORD *)(*((_QWORD *)this + 88) + 16LL) + v39 * *(_DWORD *)(*((_QWORD *)this + 88) + 12LL)),
            *(int *)(*((_QWORD *)this + 88) + 12LL));
          v40 = *(_QWORD *)v22;
          v41 = *(_DWORD *)(*(_QWORD *)v22 + 28LL);
          v42 = *(int *)(*(_QWORD *)v22 + 12LL);
          v48 = v41;
          v43 = v42 * (v41 + 1);
          if ( v43 > *(_DWORD *)(*(_QWORD *)v22 + 24LL) )
          {
            if ( !(unsigned int)GL::FEnsureSize((GL *)v40, v43) )
              goto LABEL_56;
            v41 = v48;
          }
          v44 = (char *)(v41 * (int)v42 + *(_QWORD *)(v40 + 16));
          v50 = v44;
          if ( v41 < *(_DWORD *)(v40 + 28) )
          {
            memmove_0(&v44[v42], v44, v43 - (int)v42 - v41 * (int)v42);
            v44 = v50;
          }
          memcpy_0(v44, &j, v42);
          v45 = (int)v55;
          ++*(_DWORD *)(v40 + 28);
          v39 = v45 + 1;
        }
      }
      v8 = 0;
      goto LABEL_75;
    }
    v11 = operator new(0x20u);
    if ( v11 )
    {
      *(_QWORD *)v11 = &GL::`vftable';
      v11[2] = 1;
      v11[3] = 16;
      *((_QWORD *)v11 + 2) = 0;
      *((_QWORD *)v11 + 3) = 0;
      *(_QWORD *)v10 = v11;
      goto LABEL_18;
    }
    *(_QWORD *)v10 = 0;
    v8 = -2147024882;
  }
LABEL_76:
  COleScript::EnableInterrupts(this);
  if ( v8 >= 0 )
    *v2 = (struct IActiveScript *)v7;
  else
    COleScript::Release(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180078e20  mov     [rsp-38h+arg_0], rbx
0x180078e25  mov     [rsp-38h+arg_8], rdx
0x180078e2a  push    rbp
0x180078e2b  push    rsi
0x180078e2c  push    rdi
0x180078e2d  push    r12
0x180078e2f  push    r13
0x180078e31  push    r14
0x180078e33  push    r15
0x180078e35  mov     rbp, rsp
0x180078e38  sub     rsp, 70h
0x180078e3c  xor     r13d, r13d
0x180078e3f  xorps   xmm0, xmm0
0x180078e42  mov     r12, rdx
0x180078e45  mov     rsi, rcx
0x180078e48  movups  [rbp+Src], xmm0
0x180078e4c  test    rdx, rdx
0x180078e4f  jnz     short loc_180078E58
0x180078e51  mov     eax, 80004003h
0x180078e56  jmp     short loc_180078EC0
0x180078e58  mov     [rdx], r13
0x180078e5b  cmp     dword ptr [rcx+0A8h], 4
0x180078e62  jnz     short loc_180078E6B
0x180078e64  mov     eax, 8000FFFFh
0x180078e69  jmp     short loc_180078EC0
0x180078e6b  mov     ecx, 3F8h; Size
0x180078e70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078e75  test    rax, rax
0x180078e78  jz      short loc_180078EBB
0x180078e7a  mov     r8, [rsi+0B8h]; unsigned __int16 *
0x180078e81  mov     rcx, rax; this
0x180078e84  mov     rdx, [rsi+0C0h]; struct _GUID *
0x180078e8b  call    ??0COleScript@@QEAA@AEBU_GUID@@PEBG@Z; COleScript::COleScript(_GUID const &,ushort const *)
0x180078e90  mov     rdi, rax
0x180078e93  test    rax, rax
0x180078e96  jz      short loc_180078EBB
0x180078e98  mov     ecx, [rsi+3C0h]
0x180078e9e  mov     [rax+3C0h], ecx
0x180078ea4  mov     rcx, rax; this
0x180078ea7  call    ?Initialize@COleScript@@QEAAHXZ; COleScript::Initialize(void)
0x180078eac  test    eax, eax
0x180078eae  jnz     short loc_180078ED9
0x180078eb0  lea     edx, [rax+1]; unsigned int
0x180078eb3  mov     rcx, rdi; this
0x180078eb6  call    ??_ECOleScript@@UEAAPEAXI@Z; COleScript::`vector deleting destructor'(uint)
0x180078ebb  mov     eax, 8007000Eh
0x180078ec0  mov     rbx, [rsp+70h+arg_0]
0x180078ec8  add     rsp, 70h
0x180078ecc  pop     r15
0x180078ece  pop     r14
0x180078ed0  pop     r13
0x180078ed2  pop     r12
0x180078ed4  pop     rdi
0x180078ed5  pop     rsi
0x180078ed6  pop     rbp
0x180078ed7  retn
0x180078ed9  mov     rcx, rsi; this
0x180078edc  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180078ee1  test    eax, eax
0x180078ee3  jnz     short loc_180078EEC
0x180078ee5  mov     eax, 80004005h
0x180078eea  jmp     short loc_180078EC0
0x180078eec  mov     eax, [rsi+108h]
0x180078ef2  lea     r14, [rdi+138h]
0x180078ef9  mov     [rdi+108h], eax
0x180078eff  lea     rcx, [rsi+138h]; this
0x180078f06  mov     eax, [rsi+2B0h]
0x180078f0c  mov     rdx, r14; struct NamedItemList *
0x180078f0f  mov     [rdi+2B0h], eax
0x180078f15  call    ?Clone@NamedItemList@@QEAAJPEAV1@@Z; NamedItemList::Clone(NamedItemList *)
0x180078f1a  mov     ebx, eax
0x180078f1c  test    eax, eax
0x180078f1e  js      loc_1800794B8
0x180078f24  mov     rcx, r14; this
0x180078f27  call    ?FindHighestMod@NamedItemList@@QEAAKXZ; NamedItemList::FindHighestMod(void)
0x180078f2c  mov     r14d, 1
0x180078f32  lea     rbx, ??_7GL@@6B@; const GL::`vftable'
0x180078f39  add     eax, r14d
0x180078f3c  mov     [rdi+130h], eax
0x180078f42  mov     rax, [rsi+2B8h]
0x180078f49  test    rax, rax
0x180078f4c  jz      loc_1800790AF
0x180078f52  mov     eax, [rax+1Ch]
0x180078f55  mov     [rbp+var_40], eax
0x180078f58  test    eax, eax
0x180078f5a  jle     loc_1800790AF
0x180078f60  lea     r15, [rdi+2B8h]
0x180078f67  mov     [rbp+var_28], r15
0x180078f6b  cmp     [r15], r13
0x180078f6e  jnz     short loc_180078F9B
0x180078f70  lea     ecx, [r14+1Fh]; Size
0x180078f74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078f79  test    rax, rax
0x180078f7c  jz      loc_180079302
0x180078f82  mov     [rax], rbx
0x180078f85  mov     [rax+8], r14d
0x180078f89  mov     dword ptr [rax+0Ch], 10h
0x180078f90  mov     [rax+10h], r13
0x180078f94  mov     [rax+18h], r13
0x180078f98  mov     [r15], rax
0x180078f9b  mov     r12d, r13d
0x180078f9e  mov     rcx, [rsi+2B8h]
0x180078fa5  movsxd  rax, dword ptr [rcx+0Ch]
0x180078fa9  mov     r8, rax; Size
0x180078fac  imul    eax, r12d
0x180078fb0  movsxd  rdx, eax
0x180078fb3  add     rdx, [rcx+10h]; Src
0x180078fb7  lea     rcx, [rbp+Src]; void *
0x180078fbb  call    memcpy_0
0x180078fc0  test    byte ptr [rbp+Src], r14b
0x180078fc4  jz      loc_18007909B
0x180078fca  mov     rcx, qword ptr [rbp+Src+8]; this
0x180078fce  mov     rdx, rdi; struct COleScript *
0x180078fd1  mov     dword ptr [rbp+Src], 3
0x180078fd8  call    ?PbodyClone@CScriptBody@@QEAAPEAV1@PEAVCOleScript@@@Z; CScriptBody::PbodyClone(COleScript *)
0x180078fdd  mov     qword ptr [rbp+Src+8], rax
0x180078fe1  mov     rbx, rax
0x180078fe4  test    rax, rax
0x180078fe7  jz      loc_180079317
0x180078fed  mov     r13, [r15]
0x180078ff0  mov     r9d, [r13+1Ch]
0x180078ff4  mov     edx, [r13+0Ch]
0x180078ff8  mov     dword ptr [rbp+arg_18], r9d
0x180078ffc  mov     [rbp+arg_10], edx
0x180078fff  lea     r15d, [r9+1]
0x180079003  imul    r15d, edx
0x180079007  cmp     r15d, [r13+18h]
0x18007900b  jle     short loc_180079027
0x18007900d  mov     edx, r15d; int
0x180079010  mov     rcx, r13; this
0x180079013  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180079018  test    eax, eax
0x18007901a  jz      loc_18007930F
0x180079020  mov     edx, [rbp+arg_10]
0x180079023  mov     r9d, dword ptr [rbp+arg_18]
0x180079027  mov     rax, [r13+10h]
0x18007902b  mov     r8d, edx
0x18007902e  imul    r8d, r9d
0x180079032  movsxd  rcx, r8d
0x180079035  add     rax, rcx
0x180079038  mov     [rbp+arg_18], rax
0x18007903c  cmp     r9d, [r13+1Ch]
0x180079040  jge     short loc_180079060
0x180079042  sub     r15d, r8d
0x180079045  movsxd  rcx, edx
0x180079048  sub     r15d, edx
0x18007904b  add     rcx, rax; void *
0x18007904e  movsxd  r8, r15d; Size
0x180079051  mov     rdx, rax; Src
0x180079054  call    memmove_0
0x180079059  mov     edx, [rbp+arg_10]
0x18007905c  mov     rax, [rbp+arg_18]
0x180079060  movsxd  r8, edx; Size
0x180079063  mov     rcx, rax; void *
0x180079066  lea     rdx, [rbp+Src]; Src
0x18007906a  call    memcpy_0
0x18007906f  add     [r13+1Ch], r14d
0x180079073  lea     rax, [rdi+390h]
0x18007907a  mov     rcx, [rax]
0x18007907d  lea     rdx, [rbx+28h]
0x180079081  xor     r13d, r13d
0x180079084  mov     [rdx], rcx
0x180079087  test    rcx, rcx
0x18007908a  jz      short loc_180079090
0x18007908c  mov     [rcx+30h], rdx
0x180079090  mov     r15, [rbp+var_28]
0x180079094  mov     [rbx+30h], rax
0x180079098  mov     [rax], rbx
0x18007909b  add     r12d, r14d
0x18007909e  cmp     r12d, [rbp+var_40]
0x1800790a2  jl      loc_180078F9E
0x1800790a8  lea     rbx, ??_7GL@@6B@; const GL::`vftable'
0x1800790af  mov     rax, [rsi+2C8h]
0x1800790b6  test    rax, rax
0x1800790b9  jz      loc_180079206
0x1800790bf  mov     eax, [rax+1Ch]
0x1800790c2  mov     [rbp+var_40], eax
0x1800790c5  test    eax, eax
0x1800790c7  jle     loc_180079206
0x1800790cd  lea     r12, [rdi+2C8h]
0x1800790d4  mov     [rbp+var_28], r13
0x1800790d8  mov     qword ptr [rbp+Src], r13
0x1800790dc  cmp     [r12], r13
0x1800790e0  jnz     short loc_180079113
0x1800790e2  mov     ecx, 20h ; ' '; Size
0x1800790e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800790ec  test    rax, rax
0x1800790ef  jz      loc_180079321
0x1800790f5  mov     [rax], rbx
0x1800790f8  mov     [rax+8], r14d
0x1800790fc  mov     dword ptr [rax+0Ch], 8
0x180079103  mov     [rax+10h], r13
0x180079107  mov     qword ptr [rax+18h], 0
0x18007910f  mov     [r12], rax
0x180079113  mov     edx, r13d
0x180079116  mov     [rbp+arg_10], edx
0x180079119  mov     rcx, [rsi+2C8h]
0x180079120  movsxd  rax, dword ptr [rcx+0Ch]
0x180079124  mov     r8, rax; Size
0x180079127  imul    eax, edx
0x18007912a  movsxd  rdx, eax
0x18007912d  add     rdx, [rcx+10h]; Src
0x180079131  lea     rcx, [rbp+var_28]; void *
0x180079135  call    memcpy_0
0x18007913a  mov     rbx, [rbp+var_28]
0x18007913e  mov     rcx, rbx
0x180079141  mov     rax, [rbx]
0x180079144  mov     rax, [rax+28h]
0x180079148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007914d  test    eax, eax
0x18007914f  jz      loc_1800791F4
0x180079155  mov     rax, [rbx]
0x180079158  lea     rdx, [rbp+Src]
0x18007915c  mov     r8, rdi
0x18007915f  mov     rcx, rbx
0x180079162  mov     rax, [rax+38h]
0x180079166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007916b  mov     ebx, eax
0x18007916d  test    eax, eax
0x18007916f  js      loc_1800794B4
0x180079175  mov     rbx, [r12]
0x180079179  mov     r8d, [rbx+1Ch]
0x18007917d  movsxd  r13, dword ptr [rbx+0Ch]
0x180079181  mov     dword ptr [rbp+arg_18], r8d
0x180079185  lea     r15d, [r8+1]
0x180079189  imul    r15d, r13d
0x18007918d  cmp     r15d, [rbx+18h]
0x180079191  jle     short loc_1800791AA
0x180079193  mov     edx, r15d; int
0x180079196  mov     rcx, rbx; this
0x180079199  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18007919e  test    eax, eax
0x1800791a0  jz      loc_180079327
0x1800791a6  mov     r8d, dword ptr [rbp+arg_18]
0x1800791aa  mov     rax, [rbx+10h]
0x1800791ae  mov     edx, r13d
0x1800791b1  imul    edx, r8d
0x1800791b5  movsxd  rcx, edx
0x1800791b8  add     rax, rcx
0x1800791bb  mov     [rbp+arg_18], rax
0x1800791bf  cmp     r8d, [rbx+1Ch]
0x1800791c3  jge     short loc_1800791DE
0x1800791c5  sub     r15d, edx
0x1800791c8  lea     rcx, [rax+r13]; void *
0x1800791cc  sub     r15d, r13d
0x1800791cf  mov     rdx, rax; Src
0x1800791d2  movsxd  r8, r15d; Size
0x1800791d5  call    memmove_0
0x1800791da  mov     rax, [rbp+arg_18]
0x1800791de  mov     r8, r13; Size
0x1800791e1  lea     rdx, [rbp+Src]; Src
0x1800791e5  mov     rcx, rax; void *
0x1800791e8  call    memcpy_0
0x1800791ed  add     [rbx+1Ch], r14d
0x1800791f1  xor     r13d, r13d
0x1800791f4  mov     edx, [rbp+arg_10]
0x1800791f7  add     edx, r14d
0x1800791fa  mov     [rbp+arg_10], edx
0x1800791fd  cmp     edx, [rbp+var_40]
0x180079200  jl      loc_180079119
0x180079206  cmp     [rsi+2D0h], r13
0x18007920d  jz      loc_180079342
0x180079213  xor     eax, eax
0x180079215  mov     [rbp+arg_10], r13d
0x180079219  xorps   xmm0, xmm0
0x18007921c  mov     qword ptr [rbp+Src], r13
0x180079220  mov     [rbp+arg_18], r13
0x180079224  movups  [rbp+var_20], xmm0
0x180079228  mov     [rbp+var_10], rax
0x18007922c  cmp     [rdi+2D0h], r13
0x180079233  jnz     short loc_180079260
0x180079235  mov     ecx, 0A8h; Size
0x18007923a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007923f  test    rax, rax
0x180079242  jz      loc_180079339
0x180079248  mov     rcx, rax; this
0x18007924b  call    ??0NameList@@QEAA@XZ; NameList::NameList(void)
0x180079250  mov     [rdi+2D0h], rax
0x180079257  test    rax, rax
0x18007925a  jz      loc_180079317
0x180079260  or      edx, 0FFFFFFFFh
0x180079263  mov     [rbp+arg_10], edx
0x180079266  mov     rcx, [rsi+2D0h]
0x18007926d  lea     r8, [rbp+var_20]
0x180079271  mov     qword ptr [rsp+70h+var_50], r8
0x180079276  lea     r9, [rbp+Src]
0x18007927a  lea     r8, [rbp+arg_10]
0x18007927e  mov     rax, [rcx]
0x180079281  mov     rax, [rax+18h]
0x180079285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007928a  test    eax, eax
0x18007928c  jz      loc_180079342
0x180079292  mov     rcx, [rdi+2D0h]
0x180079299  lea     r8, [rbp+arg_18]
0x18007929d  xor     r9d, r9d
0x1800792a0  lea     rdx, [rbp+var_20]
0x1800792a4  mov     rax, [rcx]
0x1800792a7  mov     rax, [rax+8]
0x1800792ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800792b0  test    eax, eax
  ... truncated ...
```
