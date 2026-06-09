# COleScript::Clone(IActiveScript * *)

- ea: `0x180077820`
- end: `0x180077ed2`
- name: `?Clone@COleScript@@UEAAJPEAPEAUIActiveScript@@@Z`
- size: `1714`
- prototype: `__int64 __fastcall(COleScript *__hidden this, struct IActiveScript **)`
- caller_count: `0`
- callee_count: `19`
- tags: ``

## callees

- `0x1800165f0`
- `0x180019c60`
- `0x180019ce0`
- `0x180019e28`
- `0x18001a29c`
- `0x18001a950`
- `0x18002f314`
- `0x18002fb04`
- `0x1800304c0`
- `0x180030920`
- `0x180047f38`
- `0x1800576a0`
- `0x180066ca0`
- `0x180077820`
- `0x180077ed8`
- `0x18007b250`
- `0x180094282`
- `0x18009428e`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180077d5c`
- `KERNEL32!GetCurrentThreadId` at `0x180077d5c`

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
0x180077820  mov     [rsp-38h+arg_0], rbx
0x180077825  mov     [rsp-38h+arg_8], rdx
0x18007782a  push    rbp
0x18007782b  push    rsi
0x18007782c  push    rdi
0x18007782d  push    r12
0x18007782f  push    r13
0x180077831  push    r14
0x180077833  push    r15
0x180077835  mov     rbp, rsp
0x180077838  sub     rsp, 70h
0x18007783c  xor     r13d, r13d
0x18007783f  xorps   xmm0, xmm0
0x180077842  mov     r12, rdx
0x180077845  mov     rsi, rcx
0x180077848  movups  [rbp+Src], xmm0
0x18007784c  test    rdx, rdx
0x18007784f  jnz     short loc_180077858
0x180077851  mov     eax, 80004003h
0x180077856  jmp     short loc_1800778C0
0x180077858  mov     [rdx], r13
0x18007785b  cmp     dword ptr [rcx+0A8h], 4
0x180077862  jnz     short loc_18007786B
0x180077864  mov     eax, 8000FFFFh
0x180077869  jmp     short loc_1800778C0
0x18007786b  mov     ecx, 3F8h; Size
0x180077870  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077875  test    rax, rax
0x180077878  jz      short loc_1800778BB
0x18007787a  mov     r8, [rsi+0B8h]; unsigned __int16 *
0x180077881  mov     rcx, rax; this
0x180077884  mov     rdx, [rsi+0C0h]; struct _GUID *
0x18007788b  call    ??0COleScript@@QEAA@AEBU_GUID@@PEBG@Z; COleScript::COleScript(_GUID const &,ushort const *)
0x180077890  mov     rdi, rax
0x180077893  test    rax, rax
0x180077896  jz      short loc_1800778BB
0x180077898  mov     ecx, [rsi+3C0h]
0x18007789e  mov     [rax+3C0h], ecx
0x1800778a4  mov     rcx, rax; this
0x1800778a7  call    ?Initialize@COleScript@@QEAAHXZ; COleScript::Initialize(void)
0x1800778ac  test    eax, eax
0x1800778ae  jnz     short loc_1800778D8
0x1800778b0  lea     edx, [rax+1]; unsigned int
0x1800778b3  mov     rcx, rdi; this
0x1800778b6  call    ??_ECOleScript@@UEAAPEAXI@Z; COleScript::`vector deleting destructor'(uint)
0x1800778bb  mov     eax, 8007000Eh
0x1800778c0  mov     rbx, [rsp+70h+arg_0]
0x1800778c8  add     rsp, 70h
0x1800778cc  pop     r15
0x1800778ce  pop     r14
0x1800778d0  pop     r13
0x1800778d2  pop     r12
0x1800778d4  pop     rdi
0x1800778d5  pop     rsi
0x1800778d6  pop     rbp
0x1800778d7  retn
0x1800778d8  mov     rcx, rsi; this
0x1800778db  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800778e0  test    eax, eax
0x1800778e2  jnz     short loc_1800778EB
0x1800778e4  mov     eax, 80004005h
0x1800778e9  jmp     short loc_1800778C0
0x1800778eb  mov     eax, [rsi+108h]
0x1800778f1  lea     r14, [rdi+138h]
0x1800778f8  mov     [rdi+108h], eax
0x1800778fe  lea     rcx, [rsi+138h]; this
0x180077905  mov     eax, [rsi+2B0h]
0x18007790b  mov     rdx, r14; struct NamedItemList *
0x18007790e  mov     [rdi+2B0h], eax
0x180077914  call    ?Clone@NamedItemList@@QEAAJPEAV1@@Z; NamedItemList::Clone(NamedItemList *)
0x180077919  mov     ebx, eax
0x18007791b  test    eax, eax
0x18007791d  js      loc_180077EB1
0x180077923  mov     rcx, r14; this
0x180077926  call    ?FindHighestMod@NamedItemList@@QEAAKXZ; NamedItemList::FindHighestMod(void)
0x18007792b  mov     r14d, 1
0x180077931  lea     rbx, ??_7GL@@6B@; const GL::`vftable'
0x180077938  add     eax, r14d
0x18007793b  mov     [rdi+130h], eax
0x180077941  mov     rax, [rsi+2B8h]
0x180077948  test    rax, rax
0x18007794b  jz      loc_180077AAE
0x180077951  mov     eax, [rax+1Ch]
0x180077954  mov     [rbp+var_40], eax
0x180077957  test    eax, eax
0x180077959  jle     loc_180077AAE
0x18007795f  lea     r15, [rdi+2B8h]
0x180077966  mov     [rbp+var_28], r15
0x18007796a  cmp     [r15], r13
0x18007796d  jnz     short loc_18007799A
0x18007796f  lea     ecx, [r14+1Fh]; Size
0x180077973  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077978  test    rax, rax
0x18007797b  jz      loc_180077D01
0x180077981  mov     [rax], rbx
0x180077984  mov     [rax+8], r14d
0x180077988  mov     dword ptr [rax+0Ch], 10h
0x18007798f  mov     [rax+10h], r13
0x180077993  mov     [rax+18h], r13
0x180077997  mov     [r15], rax
0x18007799a  mov     r12d, r13d
0x18007799d  mov     rcx, [rsi+2B8h]
0x1800779a4  movsxd  rax, dword ptr [rcx+0Ch]
0x1800779a8  mov     r8, rax; Size
0x1800779ab  imul    eax, r12d
0x1800779af  movsxd  rdx, eax
0x1800779b2  add     rdx, [rcx+10h]; Src
0x1800779b6  lea     rcx, [rbp+Src]; void *
0x1800779ba  call    memcpy_0
0x1800779bf  test    byte ptr [rbp+Src], r14b
0x1800779c3  jz      loc_180077A9A
0x1800779c9  mov     rcx, qword ptr [rbp+Src+8]; this
0x1800779cd  mov     rdx, rdi; struct COleScript *
0x1800779d0  mov     dword ptr [rbp+Src], 3
0x1800779d7  call    ?PbodyClone@CScriptBody@@QEAAPEAV1@PEAVCOleScript@@@Z; CScriptBody::PbodyClone(COleScript *)
0x1800779dc  mov     qword ptr [rbp+Src+8], rax
0x1800779e0  mov     rbx, rax
0x1800779e3  test    rax, rax
0x1800779e6  jz      loc_180077D16
0x1800779ec  mov     r13, [r15]
0x1800779ef  mov     r9d, [r13+1Ch]
0x1800779f3  mov     edx, [r13+0Ch]
0x1800779f7  mov     dword ptr [rbp+arg_18], r9d
0x1800779fb  mov     [rbp+arg_10], edx
0x1800779fe  lea     r15d, [r9+1]
0x180077a02  imul    r15d, edx
0x180077a06  cmp     r15d, [r13+18h]
0x180077a0a  jle     short loc_180077A26
0x180077a0c  mov     edx, r15d; int
0x180077a0f  mov     rcx, r13; this
0x180077a12  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180077a17  test    eax, eax
0x180077a19  jz      loc_180077D0E
0x180077a1f  mov     edx, [rbp+arg_10]
0x180077a22  mov     r9d, dword ptr [rbp+arg_18]
0x180077a26  mov     rax, [r13+10h]
0x180077a2a  mov     r8d, edx
0x180077a2d  imul    r8d, r9d
0x180077a31  movsxd  rcx, r8d
0x180077a34  add     rax, rcx
0x180077a37  mov     [rbp+arg_18], rax
0x180077a3b  cmp     r9d, [r13+1Ch]
0x180077a3f  jge     short loc_180077A5F
0x180077a41  sub     r15d, r8d
0x180077a44  movsxd  rcx, edx
0x180077a47  sub     r15d, edx
0x180077a4a  add     rcx, rax; void *
0x180077a4d  movsxd  r8, r15d; Size
0x180077a50  mov     rdx, rax; Src
0x180077a53  call    memmove_0
0x180077a58  mov     edx, [rbp+arg_10]
0x180077a5b  mov     rax, [rbp+arg_18]
0x180077a5f  movsxd  r8, edx; Size
0x180077a62  mov     rcx, rax; void *
0x180077a65  lea     rdx, [rbp+Src]; Src
0x180077a69  call    memcpy_0
0x180077a6e  add     [r13+1Ch], r14d
0x180077a72  lea     rax, [rdi+390h]
0x180077a79  mov     rcx, [rax]
0x180077a7c  lea     rdx, [rbx+28h]
0x180077a80  xor     r13d, r13d
0x180077a83  mov     [rdx], rcx
0x180077a86  test    rcx, rcx
0x180077a89  jz      short loc_180077A8F
0x180077a8b  mov     [rcx+30h], rdx
0x180077a8f  mov     r15, [rbp+var_28]
0x180077a93  mov     [rbx+30h], rax
0x180077a97  mov     [rax], rbx
0x180077a9a  add     r12d, r14d
0x180077a9d  cmp     r12d, [rbp+var_40]
0x180077aa1  jl      loc_18007799D
0x180077aa7  lea     rbx, ??_7GL@@6B@; const GL::`vftable'
0x180077aae  mov     rax, [rsi+2C8h]
0x180077ab5  test    rax, rax
0x180077ab8  jz      loc_180077C05
0x180077abe  mov     eax, [rax+1Ch]
0x180077ac1  mov     [rbp+var_40], eax
0x180077ac4  test    eax, eax
0x180077ac6  jle     loc_180077C05
0x180077acc  lea     r12, [rdi+2C8h]
0x180077ad3  mov     [rbp+var_28], r13
0x180077ad7  mov     qword ptr [rbp+Src], r13
0x180077adb  cmp     [r12], r13
0x180077adf  jnz     short loc_180077B12
0x180077ae1  mov     ecx, 20h ; ' '; Size
0x180077ae6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077aeb  test    rax, rax
0x180077aee  jz      loc_180077D20
0x180077af4  mov     [rax], rbx
0x180077af7  mov     [rax+8], r14d
0x180077afb  mov     dword ptr [rax+0Ch], 8
0x180077b02  mov     [rax+10h], r13
0x180077b06  mov     qword ptr [rax+18h], 0
0x180077b0e  mov     [r12], rax
0x180077b12  mov     edx, r13d
0x180077b15  mov     [rbp+arg_10], edx
0x180077b18  mov     rcx, [rsi+2C8h]
0x180077b1f  movsxd  rax, dword ptr [rcx+0Ch]
0x180077b23  mov     r8, rax; Size
0x180077b26  imul    eax, edx
0x180077b29  movsxd  rdx, eax
0x180077b2c  add     rdx, [rcx+10h]; Src
0x180077b30  lea     rcx, [rbp+var_28]; void *
0x180077b34  call    memcpy_0
0x180077b39  mov     rbx, [rbp+var_28]
0x180077b3d  mov     rcx, rbx
0x180077b40  mov     rax, [rbx]
0x180077b43  mov     rax, [rax+28h]
0x180077b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b4c  test    eax, eax
0x180077b4e  jz      loc_180077BF3
0x180077b54  mov     rax, [rbx]
0x180077b57  lea     rdx, [rbp+Src]
0x180077b5b  mov     r8, rdi
0x180077b5e  mov     rcx, rbx
0x180077b61  mov     rax, [rax+38h]
0x180077b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b6a  mov     ebx, eax
0x180077b6c  test    eax, eax
0x180077b6e  js      loc_180077EAD
0x180077b74  mov     rbx, [r12]
0x180077b78  mov     r8d, [rbx+1Ch]
0x180077b7c  movsxd  r13, dword ptr [rbx+0Ch]
0x180077b80  mov     dword ptr [rbp+arg_18], r8d
0x180077b84  lea     r15d, [r8+1]
0x180077b88  imul    r15d, r13d
0x180077b8c  cmp     r15d, [rbx+18h]
0x180077b90  jle     short loc_180077BA9
0x180077b92  mov     edx, r15d; int
0x180077b95  mov     rcx, rbx; this
0x180077b98  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180077b9d  test    eax, eax
0x180077b9f  jz      loc_180077D26
0x180077ba5  mov     r8d, dword ptr [rbp+arg_18]
0x180077ba9  mov     rax, [rbx+10h]
0x180077bad  mov     edx, r13d
0x180077bb0  imul    edx, r8d
0x180077bb4  movsxd  rcx, edx
0x180077bb7  add     rax, rcx
0x180077bba  mov     [rbp+arg_18], rax
0x180077bbe  cmp     r8d, [rbx+1Ch]
0x180077bc2  jge     short loc_180077BDD
0x180077bc4  sub     r15d, edx
0x180077bc7  lea     rcx, [rax+r13]; void *
0x180077bcb  sub     r15d, r13d
0x180077bce  mov     rdx, rax; Src
0x180077bd1  movsxd  r8, r15d; Size
0x180077bd4  call    memmove_0
0x180077bd9  mov     rax, [rbp+arg_18]
0x180077bdd  mov     r8, r13; Size
0x180077be0  lea     rdx, [rbp+Src]; Src
0x180077be4  mov     rcx, rax; void *
0x180077be7  call    memcpy_0
0x180077bec  add     [rbx+1Ch], r14d
0x180077bf0  xor     r13d, r13d
0x180077bf3  mov     edx, [rbp+arg_10]
0x180077bf6  add     edx, r14d
0x180077bf9  mov     [rbp+arg_10], edx
0x180077bfc  cmp     edx, [rbp+var_40]
0x180077bff  jl      loc_180077B18
0x180077c05  cmp     [rsi+2D0h], r13
0x180077c0c  jz      loc_180077D41
0x180077c12  xor     eax, eax
0x180077c14  mov     [rbp+arg_10], r13d
0x180077c18  xorps   xmm0, xmm0
0x180077c1b  mov     qword ptr [rbp+Src], r13
0x180077c1f  mov     [rbp+arg_18], r13
0x180077c23  movups  [rbp+var_20], xmm0
0x180077c27  mov     [rbp+var_10], rax
0x180077c2b  cmp     [rdi+2D0h], r13
0x180077c32  jnz     short loc_180077C5F
0x180077c34  mov     ecx, 0A8h; Size
0x180077c39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077c3e  test    rax, rax
0x180077c41  jz      loc_180077D38
0x180077c47  mov     rcx, rax; this
0x180077c4a  call    ??0NameList@@QEAA@XZ; NameList::NameList(void)
0x180077c4f  mov     [rdi+2D0h], rax
0x180077c56  test    rax, rax
0x180077c59  jz      loc_180077D16
0x180077c5f  or      edx, 0FFFFFFFFh
0x180077c62  mov     [rbp+arg_10], edx
0x180077c65  mov     rcx, [rsi+2D0h]
0x180077c6c  lea     r8, [rbp+var_20]
0x180077c70  mov     qword ptr [rsp+70h+var_50], r8
0x180077c75  lea     r9, [rbp+Src]
0x180077c79  lea     r8, [rbp+arg_10]
0x180077c7d  mov     rax, [rcx]
0x180077c80  mov     rax, [rax+18h]
0x180077c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c89  test    eax, eax
0x180077c8b  jz      loc_180077D41
0x180077c91  mov     rcx, [rdi+2D0h]
0x180077c98  lea     r8, [rbp+arg_18]
0x180077c9c  xor     r9d, r9d
0x180077c9f  lea     rdx, [rbp+var_20]
0x180077ca3  mov     rax, [rcx]
0x180077ca6  mov     rax, [rax+8]
0x180077caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077caf  test    eax, eax
  ... truncated ...
```
