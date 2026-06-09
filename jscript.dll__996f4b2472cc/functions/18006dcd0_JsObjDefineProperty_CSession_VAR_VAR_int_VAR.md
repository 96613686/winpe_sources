# JsObjDefineProperty(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x18006dcd0`
- end: `0x18006e50b`
- name: `?JsObjDefineProperty@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `2107`
- prototype: `__int64 __usercall@<rax>(struct CSession *this@<rcx>, struct VAR *@<rdx>, struct VAR *@<r8>, int@<r9d>, struct VAR *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180005070`
- `0x1800050a4`
- `0x180005660`
- `0x180006b60`
- `0x180007e9c`
- `0x18000826c`
- `0x18000da30`
- `0x1800132f8`
- `0x180033c3c`
- `0x18003477c`
- `0x180039ee4`
- `0x180039f20`
- `0x18003cb80`
- `0x18006dcd0`
- `0x180098010`

## string_xrefs

- `0x18006dfbd`: `configurable`
- `0x18006e2a7`: `configurable`

## pseudocode

```c
__int64 __fastcall JsObjDefineProperty(struct CSession *this, struct VAR *a2, struct VAR *a3, int a4, struct VAR *a5)
{
  int v6; // edi
  __int64 v7; // r13
  struct VAR *v8; // rbx
  struct VAR *v9; // rsi
  int v10; // r9d
  struct VAR *v11; // rax
  struct NameTbl *v12; // r12
  unsigned int (__fastcall *v13)(struct NameTbl *, struct SYM *, __int16 *); // rbx
  struct SYM *v14; // rax
  int v15; // r15d
  char v16; // al
  unsigned int (__fastcall *v17)(struct NameTbl *, struct SYM *, __int16 *); // rbx
  struct SYM *v18; // rax
  char v19; // al
  unsigned int (__fastcall *v20)(struct NameTbl *, struct SYM *, __int16 *); // rbx
  struct SYM *v21; // rax
  char v22; // r15
  unsigned int (__fastcall *v23)(struct NameTbl *, struct SYM *, _WORD *); // rbx
  struct SYM *v24; // rax
  const unsigned __int16 *v25; // r9
  int v26; // edx
  unsigned int (__fastcall *v27)(struct NameTbl *, struct SYM *, _WORD *); // rbx
  struct SYM *v28; // rax
  void (__fastcall *v29)(struct NameTbl *, struct SYM *, _WORD *); // rbx
  struct SYM *v30; // rax
  char v31; // r12
  struct SYM *v32; // rax
  int v33; // eax
  struct VAR *v34; // rax
  struct VAR *v35; // rax
  struct VAR *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  char v44; // [rsp+44h] [rbp-1C4h]
  char v45; // [rsp+48h] [rbp-1C0h]
  char v46; // [rsp+4Ch] [rbp-1BCh]
  struct VAR *v47; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-1A8h] BYREF
  __int16 v49; // [rsp+68h] [rbp-1A0h] BYREF
  __int16 v50; // [rsp+70h] [rbp-198h]
  struct NameTbl *v51; // [rsp+80h] [rbp-188h] BYREF
  __int128 v52; // [rsp+88h] [rbp-180h] BYREF
  __int64 v53; // [rsp+98h] [rbp-170h]
  _WORD v54[12]; // [rsp+A0h] [rbp-168h] BYREF
  _WORD v55[12]; // [rsp+B8h] [rbp-150h] BYREF
  VAR *v56; // [rsp+D0h] [rbp-138h]
  _WORD v57[12]; // [rsp+D8h] [rbp-130h] BYREF
  __int128 v58; // [rsp+F0h] [rbp-118h] BYREF
  __int64 v59; // [rsp+100h] [rbp-108h]
  __int128 v60; // [rsp+108h] [rbp-100h] BYREF
  __int64 v61; // [rsp+118h] [rbp-F0h]
  _WORD *v62; // [rsp+120h] [rbp-E8h] BYREF
  struct CSession *v63; // [rsp+128h] [rbp-E0h]
  _WORD **v64; // [rsp+130h] [rbp-D8h]
  _WORD *v65; // [rsp+138h] [rbp-D0h] BYREF
  struct CSession *v66; // [rsp+140h] [rbp-C8h]
  _WORD **v67; // [rsp+148h] [rbp-C0h]
  _WORD *v68; // [rsp+150h] [rbp-B8h] BYREF
  struct CSession *v69; // [rsp+158h] [rbp-B0h]
  _WORD **v70; // [rsp+160h] [rbp-A8h]
  _WORD *v71; // [rsp+168h] [rbp-A0h] BYREF
  struct CSession *v72; // [rsp+170h] [rbp-98h]
  __int16 **v73; // [rsp+178h] [rbp-90h]
  __int16 *v74; // [rsp+180h] [rbp-88h] BYREF
  struct CSession *v75; // [rsp+188h] [rbp-80h]
  VARIANTARG **v76; // [rsp+190h] [rbp-78h]
  VARIANTARG *v77; // [rsp+198h] [rbp-70h] BYREF
  struct CSession *v78; // [rsp+1A0h] [rbp-68h]
  __int64 v79; // [rsp+1A8h] [rbp-60h]
  _WORD v80[12]; // [rsp+1B0h] [rbp-58h] BYREF
  VARIANTARG v81; // [rsp+1C8h] [rbp-40h] BYREF
  struct NameTbl *v82; // [rsp+210h] [rbp+8h] BYREF
  struct VAR *v83; // [rsp+220h] [rbp+18h]

  v83 = a3;
  v47 = 0;
  v48 = 0;
  v52 = 0;
  v53 = 0;
  v46 = 0;
  v45 = 0;
  v51 = 0;
  v81.vt = 0;
  v78 = this;
  v77 = &v81;
  v79 = *((_QWORD *)this + 122);
  v49 = 0;
  v75 = this;
  v74 = &v49;
  v76 = &v77;
  v80[0] = 0;
  v72 = this;
  v71 = v80;
  v73 = &v74;
  v57[0] = 0;
  v69 = this;
  v68 = v57;
  v70 = &v71;
  v55[0] = 0;
  v66 = this;
  v65 = v55;
  v67 = &v68;
  v54[0] = 0;
  v63 = this;
  v62 = v54;
  v64 = &v65;
  *((_QWORD *)this + 122) = &v62;
  v44 = 0;
  LOBYTE(v82) = 0;
  if ( a4 < 3 )
  {
    v6 = -2146827839;
    goto LABEL_74;
  }
  v7 = a4;
  v8 = a5;
  v9 = VAR::PvarCutAll((struct VAR *)((char *)a5 + 24 * a4 - 24));
  v56 = v9;
  if ( !(unsigned int)VAR::IsObject(v9) )
    goto LABEL_4;
  v47 = (struct VAR *)((char *)v8 + 24 * v10 - 48);
  v6 = ConvertToString(this, (struct IDispatch ***)&v47, &v81, 1);
  if ( v6 >= 0 )
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))v9 + 1))(
           *((_QWORD *)v9 + 1),
           &IID_IHTMLDomConstructor,
           &v48) < 0 )
    {
LABEL_7:
      v6 = -2146827843;
      goto LABEL_74;
    }
    v11 = VAR::PvarCutAll((struct VAR *)((char *)v8 + 24 * v7 - 72));
    if ( !*(_WORD *)v11
      || (v6 = ConvertToObject(this, v11, (struct VAR *)v80, 0)) != 0
      || !(unsigned int)VAR::IsJsObj((VAR *)v80, &v51) )
    {
LABEL_4:
      v6 = -2146823281;
      goto LABEL_74;
    }
    v12 = v51;
    v13 = *(unsigned int (__fastcall **)(struct NameTbl *, struct SYM *, __int16 *))(*(_QWORD *)v51 + 224LL);
    v14 = SYM::InitFromPsz((SYM *)&v52, L"enumerable");
    v15 = v6 + 11;
    if ( !v13(v12, v14, &v49)
      && (v49 == (_WORD)v15 || !(unsigned int)ConvertToScalar(this, (struct VAR *)&v49, (struct VAR *)&v49, v15, 1)) )
    {
      v16 = -1;
      if ( v50 == -1 )
        v16 = 1;
      v46 = v16;
    }
    v17 = *(unsigned int (__fastcall **)(struct NameTbl *, struct SYM *, __int16 *))(*(_QWORD *)v12 + 224LL);
    v18 = SYM::InitFromPsz((SYM *)&v52, L"configurable");
    if ( !v17(v12, v18, &v49)
      && (v49 == (_WORD)v15 || !(unsigned int)ConvertToScalar(this, (struct VAR *)&v49, (struct VAR *)&v49, v15, 1)) )
    {
      v19 = -1;
      if ( v50 == -1 )
        v19 = 1;
      v45 = v19;
    }
    v20 = *(unsigned int (__fastcall **)(struct NameTbl *, struct SYM *, __int16 *))(*(_QWORD *)v12 + 224LL);
    v21 = SYM::InitFromPsz((SYM *)&v52, L"writable");
    if ( v20(v12, v21, &v49)
      || v49 != (_WORD)v15 && (unsigned int)ConvertToScalar(this, (struct VAR *)&v49, (struct VAR *)&v49, v15, 1) )
    {
      v22 = 0;
    }
    else
    {
      v22 = -1;
      if ( v50 == -1 )
        v22 = 1;
    }
    v23 = *(unsigned int (__fastcall **)(struct NameTbl *, struct SYM *, _WORD *))(*(_QWORD *)v12 + 224LL);
    v24 = SYM::InitFromPsz((SYM *)&v52, L"get");
    if ( !v23(v12, v24, v54) )
    {
      v51 = 0;
      if ( v54[0] && (unsigned int)VAR::IsJsObj((VAR *)v54) && !(unsigned int)VAR::IsFunction((VAR *)v54, &v51) )
      {
        v25 = L"get";
LABEL_35:
        v26 = -2146823286;
LABEL_36:
        v6 = CSession::RecordHr(this, v26, 0, v25, -1);
        goto LABEL_74;
      }
      v44 = 1;
    }
    v27 = *(unsigned int (__fastcall **)(struct NameTbl *, struct SYM *, _WORD *))(*(_QWORD *)v12 + 224LL);
    v28 = SYM::InitFromPsz((SYM *)&v52, L"set");
    if ( !v27(v12, v28, v55) )
    {
      v82 = 0;
      if ( v55[0] && (unsigned int)VAR::IsJsObj((VAR *)v55) && !(unsigned int)VAR::IsFunction((VAR *)v55, &v82) )
      {
        v25 = L"set";
        goto LABEL_35;
      }
      LOBYTE(v82) = 1;
    }
    v29 = *(void (__fastcall **)(struct NameTbl *, struct SYM *, _WORD *))(*(_QWORD *)v12 + 224LL);
    v30 = SYM::InitFromPsz((SYM *)&v52, L"value");
    v29(v12, v30, v57);
    v31 = (char)v82;
    if ( !v44 && !(_BYTE)v82 )
    {
      if ( v57[0] )
      {
        if ( v45 != -1 )
        {
          if ( v22 == -1 )
          {
LABEL_49:
            v25 = L"writable";
LABEL_55:
            v26 = -2146823251;
            goto LABEL_36;
          }
          if ( v46 == -1 )
          {
            v25 = L"enumerable";
            goto LABEL_55;
          }
          v32 = SYM::InitFromBstr((SYM *)&v52, *((const unsigned __int16 **)v47 + 1));
          v33 = VAR::InvokeByName(v56, this, v32, 0xCu, 0, 1, (struct VAR *)v57);
LABEL_71:
          v6 = v33;
          if ( v33 < 0 )
            goto LABEL_74;
          goto LABEL_72;
        }
LABEL_54:
        v25 = L"configurable";
        goto LABEL_55;
      }
LABEL_72:
      a2 = v83;
      if ( v83 )
      {
        v36 = a5;
        *(_OWORD *)v83 = *(_OWORD *)((char *)a5 + 24 * v7 - 24);
        *((_QWORD *)a2 + 2) = *((_QWORD *)v36 + 3 * v7 - 1);
      }
      goto LABEL_74;
    }
    if ( v45 == -1 )
      goto LABEL_54;
    if ( v46 == 1 )
    {
      v25 = L"enumerable";
LABEL_58:
      v26 = -2146823252;
      goto LABEL_36;
    }
    if ( v22 == 1 )
    {
      v25 = L"writable";
      goto LABEL_58;
    }
    if ( v22 == -1 )
      goto LABEL_49;
    if ( v57[0] )
      goto LABEL_7;
    if ( !v44 )
      goto LABEL_67;
    v34 = VAR::PvarCutAll((VAR *)v54);
    v58 = *(_OWORD *)v34;
    v59 = *((_QWORD *)v34 + 2);
    if ( (unsigned int)VAR::IsIDispatch((VAR *)&v58) )
      LOWORD(v58) = 9;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v48 + 80LL))(
           v48,
           *((_QWORD *)v47 + 1),
           &v58);
    if ( v6 >= 0 )
    {
LABEL_67:
      if ( v31 )
      {
        v35 = VAR::PvarCutAll((VAR *)v55);
        v60 = *(_OWORD *)v35;
        v61 = *((_QWORD *)v35 + 2);
        if ( (unsigned int)VAR::IsIDispatch((VAR *)&v60) )
          LOWORD(v60) = 9;
        v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v48 + 88LL))(
                v48,
                *((_QWORD *)v47 + 1),
                &v60);
        goto LABEL_71;
      }
      goto LABEL_72;
    }
  }
LABEL_74:
  if ( v48 )
    (*(void (__fastcall **)(__int64, struct VAR *))(*(_QWORD *)v48 + 16LL))(v48, a2);
  v37 = *((_QWORD *)v63 + 122);
  if ( v37 )
    *((_QWORD *)v63 + 122) = *(_QWORD *)(v37 + 16);
  v38 = *((_QWORD *)v66 + 122);
  if ( v38 )
    *((_QWORD *)v66 + 122) = *(_QWORD *)(v38 + 16);
  v39 = *((_QWORD *)v69 + 122);
  if ( v39 )
    *((_QWORD *)v69 + 122) = *(_QWORD *)(v39 + 16);
  v40 = *((_QWORD *)v72 + 122);
  if ( v40 )
    *((_QWORD *)v72 + 122) = *(_QWORD *)(v40 + 16);
  v41 = *((_QWORD *)v75 + 122);
  if ( v41 )
    *((_QWORD *)v75 + 122) = *(_QWORD *)(v41 + 16);
  v42 = *((_QWORD *)v78 + 122);
  if ( v42 )
    *((_QWORD *)v78 + 122) = *(_QWORD *)(v42 + 16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006dcd0  mov     r11, rsp
0x18006dcd3  mov     [r11+10h], rbx
0x18006dcd7  mov     [r11+20h], rsi
0x18006dcdb  mov     [r11+18h], r8
0x18006dcdf  push    rdi
0x18006dce0  push    r12
0x18006dce2  push    r13
0x18006dce4  push    r14
0x18006dce6  push    r15
0x18006dce8  sub     rsp, 1E0h
0x18006dcef  mov     r14, rcx
0x18006dcf2  xor     ebx, ebx
0x18006dcf4  mov     [rsp+208h+var_1B0], rbx
0x18006dcf9  mov     [rsp+208h+var_1A8], rbx
0x18006dcfe  xorps   xmm0, xmm0
0x18006dd01  xor     eax, eax
0x18006dd03  movups  [rsp+208h+var_180], xmm0
0x18006dd0b  mov     [r11-170h], rax
0x18006dd12  mov     byte ptr [rsp+208h+var_1BC], bl
0x18006dd16  mov     byte ptr [rsp+208h+var_1B8], bl
0x18006dd1a  mov     byte ptr [rsp+208h+var_1C0], bl
0x18006dd1e  mov     [r11-188h], rbx
0x18006dd25  mov     [r11-40h], bx
0x18006dd2a  mov     [r11-68h], rcx
0x18006dd2e  lea     rax, [r11-40h]
0x18006dd32  mov     [r11-70h], rax
0x18006dd36  mov     rax, [rcx+3D0h]
0x18006dd3d  mov     [r11-60h], rax
0x18006dd41  mov     [rsp+208h+var_1A0], bx
0x18006dd46  mov     [r11-80h], rcx
0x18006dd4a  lea     rax, [rsp+208h+var_1A0]
0x18006dd4f  mov     [r11-88h], rax
0x18006dd56  lea     rax, [r11-70h]
0x18006dd5a  mov     [r11-78h], rax
0x18006dd5e  mov     [r11-58h], bx
0x18006dd63  mov     [r11-98h], rcx
0x18006dd6a  lea     rax, [r11-58h]
0x18006dd6e  mov     [r11-0A0h], rax
0x18006dd75  lea     rax, [r11-88h]
0x18006dd7c  mov     [r11-90h], rax
0x18006dd83  mov     [rsp+208h+var_130], bx
0x18006dd8b  mov     [r11-0B0h], rcx
0x18006dd92  lea     rax, [r11-130h]
0x18006dd99  mov     [r11-0B8h], rax
0x18006dda0  lea     rax, [r11-0A0h]
0x18006dda7  mov     [r11-0A8h], rax
0x18006ddae  mov     [rsp+208h+var_150], bx
0x18006ddb6  mov     [r11-0C8h], rcx
0x18006ddbd  lea     rax, [r11-150h]
0x18006ddc4  mov     [r11-0D0h], rax
0x18006ddcb  lea     rax, [r11-0B8h]
0x18006ddd2  mov     [r11-0C0h], rax
0x18006ddd9  mov     [rsp+208h+var_168], bx
0x18006dde1  mov     [r11-0E0h], rcx
0x18006dde8  lea     rax, [r11-168h]
0x18006ddef  mov     [r11-0E8h], rax
0x18006ddf6  lea     rax, [r11-0D0h]
0x18006ddfd  mov     [r11-0D8h], rax
0x18006de04  lea     rax, [r11-0E8h]
0x18006de0b  mov     [rcx+3D0h], rax
0x18006de12  mov     al, bl
0x18006de14  mov     [rsp+208h+var_1C4], bl
0x18006de18  mov     [r11+8], bl
0x18006de1c  cmp     r9d, 3
0x18006de20  jge     short loc_18006DE30
0x18006de22  mov     edi, 800A01C1h
0x18006de27  mov     [rsp+208h+var_1C8], edi
0x18006de2b  jmp     loc_18006E41B
0x18006de30  movsxd  r13, r9d
0x18006de33  lea     rax, [r13-1]
0x18006de37  lea     rax, [rax+rax*2]
0x18006de3b  mov     rbx, [rsp+208h+arg_20]
0x18006de43  lea     rcx, [rbx+rax*8]; this
0x18006de47  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006de4c  mov     rsi, rax
0x18006de4f  mov     [rsp+208h+var_138], rax
0x18006de57  mov     rcx, rax; this
0x18006de5a  call    ?IsObject@VAR@@QEAAHXZ; VAR::IsObject(void)
0x18006de5f  test    eax, eax
0x18006de61  jnz     short loc_18006DE6A
0x18006de63  mov     edi, 800A138Fh
0x18006de68  jmp     short loc_18006DE27
0x18006de6a  movsxd  rax, r9d
0x18006de6d  sub     rax, 2
0x18006de71  lea     rax, [rax+rax*2]
0x18006de75  lea     rcx, [rbx+rax*8]
0x18006de79  mov     [rsp+208h+var_1B0], rcx
0x18006de7e  mov     r9d, 1; int
0x18006de84  lea     r8, [rsp+208h+var_40]; struct VAR *
0x18006de8c  lea     rdx, [rsp+208h+var_1B0]; struct VAR **
0x18006de91  mov     rcx, r14; struct CSession *
0x18006de94  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18006de99  mov     edi, eax
0x18006de9b  mov     [rsp+208h+var_1C8], eax
0x18006de9f  test    eax, eax
0x18006dea1  js      loc_18006E41B
0x18006dea7  mov     rcx, [rsi+8]
0x18006deab  mov     rax, [rcx]
0x18006deae  lea     r8, [rsp+208h+var_1A8]
0x18006deb3  lea     rdx, IID_IHTMLDomConstructor
0x18006deba  mov     rax, [rax]
0x18006debd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dec2  test    eax, eax
0x18006dec4  jns     short loc_18006DED0
0x18006dec6  mov     edi, 800A01BDh
0x18006decb  jmp     loc_18006DE27
0x18006ded0  lea     rax, [r13-3]
0x18006ded4  lea     rax, [rax+rax*2]
0x18006ded8  lea     rcx, [rbx+rax*8]; this
0x18006dedc  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006dee1  xor     ebx, ebx
0x18006dee3  cmp     [rax], bx
0x18006dee6  jz      loc_18006DE63
0x18006deec  xor     r9d, r9d; int
0x18006deef  lea     r8, [rsp+208h+var_58]; struct VAR *
0x18006def7  mov     rdx, rax; struct VAR *
0x18006defa  mov     rcx, r14; this
0x18006defd  call    ?ConvertToObject@@YAJPEAVCSession@@PEAVVAR@@1H@Z; ConvertToObject(CSession *,VAR *,VAR *,int)
0x18006df02  mov     edi, eax
0x18006df04  mov     [rsp+208h+var_1C8], eax
0x18006df08  test    eax, eax
0x18006df0a  jnz     loc_18006DE63
0x18006df10  lea     rdx, [rsp+208h+var_188]; struct NameTbl **
0x18006df18  lea     rcx, [rsp+208h+var_58]; this
0x18006df20  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006df25  test    eax, eax
0x18006df27  jz      loc_18006DE63
0x18006df2d  mov     r12, [rsp+208h+var_188]
0x18006df35  mov     rax, [r12]
0x18006df39  mov     rbx, [rax+0E0h]
0x18006df40  lea     rdx, aEnumerable; "enumerable"
0x18006df47  lea     rcx, [rsp+208h+var_180]; this
0x18006df4f  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006df54  lea     r8, [rsp+208h+var_1A0]
0x18006df59  mov     rdx, rax
0x18006df5c  mov     rcx, r12
0x18006df5f  mov     rax, rbx
0x18006df62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df67  lea     r15d, [rdi+0Bh]
0x18006df6b  test    eax, eax
0x18006df6d  jnz     short loc_18006DFAF
0x18006df6f  cmp     [rsp+208h+var_1A0], r15w
0x18006df75  jz      short loc_18006DF98
0x18006df77  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006df7f  mov     r9d, r15d; int
0x18006df82  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006df87  lea     rdx, [rsp+208h+var_1A0]; this
0x18006df8c  mov     rcx, r14; struct CSession *
0x18006df8f  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006df94  test    eax, eax
0x18006df96  jnz     short loc_18006DFAF
0x18006df98  or      eax, 0FFFFFFFFh
0x18006df9b  or      esi, 0FFFFFFFFh
0x18006df9e  cmp     [rsp+208h+var_198], si
0x18006dfa3  lea     ecx, [rsi+2]
0x18006dfa6  cmovz   eax, ecx
0x18006dfa9  mov     [rsp+208h+var_1BC], eax
0x18006dfad  jmp     short loc_18006DFB2
0x18006dfaf  or      esi, 0FFFFFFFFh
0x18006dfb2  mov     rax, [r12]
0x18006dfb6  mov     rbx, [rax+0E0h]
0x18006dfbd  lea     rdx, aConfigurable; "configurable"
0x18006dfc4  lea     rcx, [rsp+208h+var_180]; this
0x18006dfcc  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006dfd1  lea     r8, [rsp+208h+var_1A0]
0x18006dfd6  mov     rdx, rax
0x18006dfd9  mov     rcx, r12
0x18006dfdc  mov     rax, rbx
0x18006dfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfe4  test    eax, eax
0x18006dfe6  jnz     short loc_18006E025
0x18006dfe8  cmp     [rsp+208h+var_1A0], r15w
0x18006dfee  jz      short loc_18006E011
0x18006dff0  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006dff8  mov     r9d, r15d; int
0x18006dffb  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006e000  lea     rdx, [rsp+208h+var_1A0]; this
0x18006e005  mov     rcx, r14; struct CSession *
0x18006e008  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006e00d  test    eax, eax
0x18006e00f  jnz     short loc_18006E025
0x18006e011  or      eax, 0FFFFFFFFh
0x18006e014  cmp     [rsp+208h+var_198], si
0x18006e019  mov     ecx, 1
0x18006e01e  cmovz   eax, ecx
0x18006e021  mov     [rsp+208h+var_1C0], eax
0x18006e025  mov     rax, [r12]
0x18006e029  mov     rbx, [rax+0E0h]
0x18006e030  lea     rdx, aWritable; "writable"
0x18006e037  lea     rcx, [rsp+208h+var_180]; this
0x18006e03f  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006e044  lea     r8, [rsp+208h+var_1A0]
0x18006e049  mov     rdx, rax
0x18006e04c  mov     rcx, r12
0x18006e04f  mov     rax, rbx
0x18006e052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e057  test    eax, eax
0x18006e059  jnz     short loc_18006E098
0x18006e05b  cmp     [rsp+208h+var_1A0], r15w
0x18006e061  jz      short loc_18006E084
0x18006e063  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006e06b  mov     r9d, r15d; int
0x18006e06e  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006e073  lea     rdx, [rsp+208h+var_1A0]; this
0x18006e078  mov     rcx, r14; struct CSession *
0x18006e07b  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006e080  test    eax, eax
0x18006e082  jnz     short loc_18006E098
0x18006e084  or      r15d, 0FFFFFFFFh
0x18006e088  cmp     [rsp+208h+var_198], si
0x18006e08d  mov     eax, 1
0x18006e092  cmovz   r15d, eax
0x18006e096  jmp     short loc_18006E09D
0x18006e098  mov     r15d, [rsp+208h+var_1B8]
0x18006e09d  mov     rax, [r12]
0x18006e0a1  mov     rbx, [rax+0E0h]
0x18006e0a8  lea     rdx, aGet; "get"
0x18006e0af  lea     rcx, [rsp+208h+var_180]; this
0x18006e0b7  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006e0bc  lea     r8, [rsp+208h+var_168]
0x18006e0c4  mov     rdx, rax
0x18006e0c7  mov     rcx, r12
0x18006e0ca  mov     rax, rbx
0x18006e0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0d2  xor     ebx, ebx
0x18006e0d4  test    eax, eax
0x18006e0d6  jnz     short loc_18006E140
0x18006e0d8  mov     [rsp+208h+var_188], rbx
0x18006e0e0  cmp     [rsp+208h+var_168], bx
0x18006e0e8  jz      short loc_18006E13A
0x18006e0ea  lea     rcx, [rsp+208h+var_168]; this
0x18006e0f2  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x18006e0f7  test    eax, eax
0x18006e0f9  jz      short loc_18006E13A
0x18006e0fb  lea     rdx, [rsp+208h+var_188]; struct NameTbl **
0x18006e103  lea     rcx, [rsp+208h+var_168]; this
0x18006e10b  call    ?IsFunction@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsFunction(NameTbl * *)
0x18006e110  test    eax, eax
0x18006e112  jnz     short loc_18006E13A
0x18006e114  lea     r9, aGet; "get"
0x18006e11b  mov     edx, 800A138Ah; int
0x18006e120  mov     dword ptr [rsp+208h+pvarg], esi; int
0x18006e124  xor     r8d, r8d; struct VAR *
0x18006e127  mov     rcx, r14; this
0x18006e12a  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18006e12f  mov     edi, eax
0x18006e131  mov     [rsp+208h+var_1C8], eax
0x18006e135  jmp     loc_18006E41B
0x18006e13a  mov     al, 1
0x18006e13c  mov     [rsp+208h+var_1C4], al
0x18006e140  mov     rax, [r12]
0x18006e144  mov     rbx, [rax+0E0h]
0x18006e14b  lea     rdx, aSet; "set"
0x18006e152  lea     rcx, [rsp+208h+var_180]; this
0x18006e15a  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006e15f  lea     r8, [rsp+208h+var_150]
0x18006e167  mov     rdx, rax
0x18006e16a  mov     rcx, r12
0x18006e16d  mov     rax, rbx
0x18006e170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e175  xor     ebx, ebx
0x18006e177  test    eax, eax
0x18006e179  jnz     short loc_18006E1CB
0x18006e17b  mov     [rsp+208h+arg_0], rbx
0x18006e183  cmp     [rsp+208h+var_150], bx
0x18006e18b  jz      short loc_18006E1C3
0x18006e18d  lea     rcx, [rsp+208h+var_150]; this
0x18006e195  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x18006e19a  test    eax, eax
0x18006e19c  jz      short loc_18006E1C3
0x18006e19e  lea     rdx, [rsp+208h+arg_0]; struct NameTbl **
0x18006e1a6  lea     rcx, [rsp+208h+var_150]; this
0x18006e1ae  call    ?IsFunction@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsFunction(NameTbl * *)
0x18006e1b3  test    eax, eax
0x18006e1b5  jnz     short loc_18006E1C3
0x18006e1b7  lea     r9, aSet; "set"
0x18006e1be  jmp     loc_18006E11B
0x18006e1c3  mov     byte ptr [rsp+208h+arg_0], 1
0x18006e1cb  mov     rax, [r12]
0x18006e1cf  mov     rbx, [rax+0E0h]
0x18006e1d6  lea     rdx, aValue; "value"
0x18006e1dd  lea     rcx, [rsp+208h+var_180]; this
0x18006e1e5  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006e1ea  lea     r8, [rsp+208h+var_130]
0x18006e1f2  mov     rdx, rax
0x18006e1f5  mov     rcx, r12
0x18006e1f8  mov     rax, rbx
0x18006e1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e200  mov     al, [rsp+208h+var_1C4]
0x18006e204  xor     ebx, ebx
0x18006e206  mov     r12b, byte ptr [rsp+208h+arg_0]
0x18006e20e  test    al, al
0x18006e210  jnz     loc_18006E2A0
0x18006e216  test    r12b, r12b
0x18006e219  jnz     loc_18006E2A0
0x18006e21f  cmp     [rsp+208h+var_130], bx
0x18006e227  jz      loc_18006E3E8
0x18006e22d  cmp     byte ptr [rsp+208h+var_1C0], sil
0x18006e232  jz      short loc_18006E2A7
0x18006e234  cmp     r15b, sil
  ... truncated ...
```
