# JsObjDefineProperty(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x18006c950`
- end: `0x18006d18a`
- name: `?JsObjDefineProperty@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `2106`
- prototype: `__int64 __usercall@<rax>(struct CSession *this@<rcx>, struct VAR *@<rdx>, struct VAR *@<r8>, int@<r9d>, struct VAR *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180001d90`
- `0x1800060b4`
- `0x180006bf0`
- `0x18000ad6c`
- `0x18000b130`
- `0x1800107c0`
- `0x180014b50`
- `0x180016498`
- `0x180016714`
- `0x180033c30`
- `0x180033c60`
- `0x18003813c`
- `0x180038180`
- `0x18006c950`
- `0x180096010`

## string_xrefs

- `0x18006cc3d`: `configurable`
- `0x18006cf27`: `configurable`

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
  _WORD **v76; // [rsp+190h] [rbp-78h]
  _WORD *v77; // [rsp+198h] [rbp-70h] BYREF
  struct CSession *v78; // [rsp+1A0h] [rbp-68h]
  __int64 v79; // [rsp+1A8h] [rbp-60h]
  _WORD v80[12]; // [rsp+1B0h] [rbp-58h] BYREF
  _WORD v81[12]; // [rsp+1C8h] [rbp-40h] BYREF
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
  v81[0] = 0;
  v78 = this;
  v77 = v81;
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
  v6 = ConvertToString(this, &v47, (struct VAR *)v81, 1);
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
0x18006c950  mov     r11, rsp
0x18006c953  mov     [r11+10h], rbx
0x18006c957  mov     [r11+20h], rsi
0x18006c95b  mov     [r11+18h], r8
0x18006c95f  push    rdi
0x18006c960  push    r12
0x18006c962  push    r13
0x18006c964  push    r14
0x18006c966  push    r15
0x18006c968  sub     rsp, 1E0h
0x18006c96f  mov     r14, rcx
0x18006c972  xor     ebx, ebx
0x18006c974  mov     [rsp+208h+var_1B0], rbx
0x18006c979  mov     [rsp+208h+var_1A8], rbx
0x18006c97e  xorps   xmm0, xmm0
0x18006c981  xor     eax, eax
0x18006c983  movups  [rsp+208h+var_180], xmm0
0x18006c98b  mov     [r11-170h], rax
0x18006c992  mov     byte ptr [rsp+208h+var_1BC], bl
0x18006c996  mov     byte ptr [rsp+208h+var_1B8], bl
0x18006c99a  mov     byte ptr [rsp+208h+var_1C0], bl
0x18006c99e  mov     [r11-188h], rbx
0x18006c9a5  mov     [r11-40h], bx
0x18006c9aa  mov     [r11-68h], rcx
0x18006c9ae  lea     rax, [r11-40h]
0x18006c9b2  mov     [r11-70h], rax
0x18006c9b6  mov     rax, [rcx+3D0h]
0x18006c9bd  mov     [r11-60h], rax
0x18006c9c1  mov     [rsp+208h+var_1A0], bx
0x18006c9c6  mov     [r11-80h], rcx
0x18006c9ca  lea     rax, [rsp+208h+var_1A0]
0x18006c9cf  mov     [r11-88h], rax
0x18006c9d6  lea     rax, [r11-70h]
0x18006c9da  mov     [r11-78h], rax
0x18006c9de  mov     [r11-58h], bx
0x18006c9e3  mov     [r11-98h], rcx
0x18006c9ea  lea     rax, [r11-58h]
0x18006c9ee  mov     [r11-0A0h], rax
0x18006c9f5  lea     rax, [r11-88h]
0x18006c9fc  mov     [r11-90h], rax
0x18006ca03  mov     [rsp+208h+var_130], bx
0x18006ca0b  mov     [r11-0B0h], rcx
0x18006ca12  lea     rax, [r11-130h]
0x18006ca19  mov     [r11-0B8h], rax
0x18006ca20  lea     rax, [r11-0A0h]
0x18006ca27  mov     [r11-0A8h], rax
0x18006ca2e  mov     [rsp+208h+var_150], bx
0x18006ca36  mov     [r11-0C8h], rcx
0x18006ca3d  lea     rax, [r11-150h]
0x18006ca44  mov     [r11-0D0h], rax
0x18006ca4b  lea     rax, [r11-0B8h]
0x18006ca52  mov     [r11-0C0h], rax
0x18006ca59  mov     [rsp+208h+var_168], bx
0x18006ca61  mov     [r11-0E0h], rcx
0x18006ca68  lea     rax, [r11-168h]
0x18006ca6f  mov     [r11-0E8h], rax
0x18006ca76  lea     rax, [r11-0D0h]
0x18006ca7d  mov     [r11-0D8h], rax
0x18006ca84  lea     rax, [r11-0E8h]
0x18006ca8b  mov     [rcx+3D0h], rax
0x18006ca92  mov     al, bl
0x18006ca94  mov     [rsp+208h+var_1C4], bl
0x18006ca98  mov     [r11+8], bl
0x18006ca9c  cmp     r9d, 3
0x18006caa0  jge     short loc_18006CAB0
0x18006caa2  mov     edi, 800A01C1h
0x18006caa7  mov     [rsp+208h+var_1C8], edi
0x18006caab  jmp     loc_18006D09B
0x18006cab0  movsxd  r13, r9d
0x18006cab3  lea     rax, [r13-1]
0x18006cab7  lea     rax, [rax+rax*2]
0x18006cabb  mov     rbx, [rsp+208h+arg_20]
0x18006cac3  lea     rcx, [rbx+rax*8]; this
0x18006cac7  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006cacc  mov     rsi, rax
0x18006cacf  mov     [rsp+208h+var_138], rax
0x18006cad7  mov     rcx, rax; this
0x18006cada  call    ?IsObject@VAR@@QEAAHXZ; VAR::IsObject(void)
0x18006cadf  test    eax, eax
0x18006cae1  jnz     short loc_18006CAEA
0x18006cae3  mov     edi, 800A138Fh
0x18006cae8  jmp     short loc_18006CAA7
0x18006caea  movsxd  rax, r9d
0x18006caed  sub     rax, 2
0x18006caf1  lea     rax, [rax+rax*2]
0x18006caf5  lea     rcx, [rbx+rax*8]
0x18006caf9  mov     [rsp+208h+var_1B0], rcx
0x18006cafe  mov     r9d, 1; int
0x18006cb04  lea     r8, [rsp+208h+var_40]; struct VAR *
0x18006cb0c  lea     rdx, [rsp+208h+var_1B0]; struct VAR **
0x18006cb11  mov     rcx, r14; struct CSession *
0x18006cb14  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18006cb19  mov     edi, eax
0x18006cb1b  mov     [rsp+208h+var_1C8], eax
0x18006cb1f  test    eax, eax
0x18006cb21  js      loc_18006D09B
0x18006cb27  mov     rcx, [rsi+8]
0x18006cb2b  mov     rax, [rcx]
0x18006cb2e  lea     r8, [rsp+208h+var_1A8]
0x18006cb33  lea     rdx, IID_IHTMLDomConstructor
0x18006cb3a  mov     rax, [rax]
0x18006cb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb42  test    eax, eax
0x18006cb44  jns     short loc_18006CB50
0x18006cb46  mov     edi, 800A01BDh
0x18006cb4b  jmp     loc_18006CAA7
0x18006cb50  lea     rax, [r13-3]
0x18006cb54  lea     rax, [rax+rax*2]
0x18006cb58  lea     rcx, [rbx+rax*8]; this
0x18006cb5c  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006cb61  xor     ebx, ebx
0x18006cb63  cmp     [rax], bx
0x18006cb66  jz      loc_18006CAE3
0x18006cb6c  xor     r9d, r9d; int
0x18006cb6f  lea     r8, [rsp+208h+var_58]; struct VAR *
0x18006cb77  mov     rdx, rax; struct VAR *
0x18006cb7a  mov     rcx, r14; this
0x18006cb7d  call    ?ConvertToObject@@YAJPEAVCSession@@PEAVVAR@@1H@Z; ConvertToObject(CSession *,VAR *,VAR *,int)
0x18006cb82  mov     edi, eax
0x18006cb84  mov     [rsp+208h+var_1C8], eax
0x18006cb88  test    eax, eax
0x18006cb8a  jnz     loc_18006CAE3
0x18006cb90  lea     rdx, [rsp+208h+var_188]; struct NameTbl **
0x18006cb98  lea     rcx, [rsp+208h+var_58]; this
0x18006cba0  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006cba5  test    eax, eax
0x18006cba7  jz      loc_18006CAE3
0x18006cbad  mov     r12, [rsp+208h+var_188]
0x18006cbb5  mov     rax, [r12]
0x18006cbb9  mov     rbx, [rax+0E0h]
0x18006cbc0  lea     rdx, aEnumerable; "enumerable"
0x18006cbc7  lea     rcx, [rsp+208h+var_180]; this
0x18006cbcf  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006cbd4  lea     r8, [rsp+208h+var_1A0]
0x18006cbd9  mov     rdx, rax
0x18006cbdc  mov     rcx, r12
0x18006cbdf  mov     rax, rbx
0x18006cbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbe7  lea     r15d, [rdi+0Bh]
0x18006cbeb  test    eax, eax
0x18006cbed  jnz     short loc_18006CC2F
0x18006cbef  cmp     [rsp+208h+var_1A0], r15w
0x18006cbf5  jz      short loc_18006CC18
0x18006cbf7  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006cbff  mov     r9d, r15d; int
0x18006cc02  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006cc07  lea     rdx, [rsp+208h+var_1A0]; this
0x18006cc0c  mov     rcx, r14; struct CSession *
0x18006cc0f  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006cc14  test    eax, eax
0x18006cc16  jnz     short loc_18006CC2F
0x18006cc18  or      eax, 0FFFFFFFFh
0x18006cc1b  or      esi, 0FFFFFFFFh
0x18006cc1e  cmp     [rsp+208h+var_198], si
0x18006cc23  lea     ecx, [rsi+2]
0x18006cc26  cmovz   eax, ecx
0x18006cc29  mov     [rsp+208h+var_1BC], eax
0x18006cc2d  jmp     short loc_18006CC32
0x18006cc2f  or      esi, 0FFFFFFFFh
0x18006cc32  mov     rax, [r12]
0x18006cc36  mov     rbx, [rax+0E0h]
0x18006cc3d  lea     rdx, aConfigurable; "configurable"
0x18006cc44  lea     rcx, [rsp+208h+var_180]; this
0x18006cc4c  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006cc51  lea     r8, [rsp+208h+var_1A0]
0x18006cc56  mov     rdx, rax
0x18006cc59  mov     rcx, r12
0x18006cc5c  mov     rax, rbx
0x18006cc5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc64  test    eax, eax
0x18006cc66  jnz     short loc_18006CCA5
0x18006cc68  cmp     [rsp+208h+var_1A0], r15w
0x18006cc6e  jz      short loc_18006CC91
0x18006cc70  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006cc78  mov     r9d, r15d; int
0x18006cc7b  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006cc80  lea     rdx, [rsp+208h+var_1A0]; this
0x18006cc85  mov     rcx, r14; struct CSession *
0x18006cc88  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006cc8d  test    eax, eax
0x18006cc8f  jnz     short loc_18006CCA5
0x18006cc91  or      eax, 0FFFFFFFFh
0x18006cc94  cmp     [rsp+208h+var_198], si
0x18006cc99  mov     ecx, 1
0x18006cc9e  cmovz   eax, ecx
0x18006cca1  mov     [rsp+208h+var_1C0], eax
0x18006cca5  mov     rax, [r12]
0x18006cca9  mov     rbx, [rax+0E0h]
0x18006ccb0  lea     rdx, aWritable; "writable"
0x18006ccb7  lea     rcx, [rsp+208h+var_180]; this
0x18006ccbf  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006ccc4  lea     r8, [rsp+208h+var_1A0]
0x18006ccc9  mov     rdx, rax
0x18006cccc  mov     rcx, r12
0x18006cccf  mov     rax, rbx
0x18006ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ccd7  test    eax, eax
0x18006ccd9  jnz     short loc_18006CD18
0x18006ccdb  cmp     [rsp+208h+var_1A0], r15w
0x18006cce1  jz      short loc_18006CD04
0x18006cce3  mov     dword ptr [rsp+208h+pvarg], 1; int
0x18006cceb  mov     r9d, r15d; int
0x18006ccee  lea     r8, [rsp+208h+var_1A0]; struct VAR *
0x18006ccf3  lea     rdx, [rsp+208h+var_1A0]; this
0x18006ccf8  mov     rcx, r14; struct CSession *
0x18006ccfb  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006cd00  test    eax, eax
0x18006cd02  jnz     short loc_18006CD18
0x18006cd04  or      r15d, 0FFFFFFFFh
0x18006cd08  cmp     [rsp+208h+var_198], si
0x18006cd0d  mov     eax, 1
0x18006cd12  cmovz   r15d, eax
0x18006cd16  jmp     short loc_18006CD1D
0x18006cd18  mov     r15d, [rsp+208h+var_1B8]
0x18006cd1d  mov     rax, [r12]
0x18006cd21  mov     rbx, [rax+0E0h]
0x18006cd28  lea     rdx, aGet; "get"
0x18006cd2f  lea     rcx, [rsp+208h+var_180]; this
0x18006cd37  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006cd3c  lea     r8, [rsp+208h+var_168]
0x18006cd44  mov     rdx, rax
0x18006cd47  mov     rcx, r12
0x18006cd4a  mov     rax, rbx
0x18006cd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd52  xor     ebx, ebx
0x18006cd54  test    eax, eax
0x18006cd56  jnz     short loc_18006CDC0
0x18006cd58  mov     [rsp+208h+var_188], rbx
0x18006cd60  cmp     [rsp+208h+var_168], bx
0x18006cd68  jz      short loc_18006CDBA
0x18006cd6a  lea     rcx, [rsp+208h+var_168]; this
0x18006cd72  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x18006cd77  test    eax, eax
0x18006cd79  jz      short loc_18006CDBA
0x18006cd7b  lea     rdx, [rsp+208h+var_188]; struct NameTbl **
0x18006cd83  lea     rcx, [rsp+208h+var_168]; this
0x18006cd8b  call    ?IsFunction@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsFunction(NameTbl * *)
0x18006cd90  test    eax, eax
0x18006cd92  jnz     short loc_18006CDBA
0x18006cd94  lea     r9, aGet; "get"
0x18006cd9b  mov     edx, 800A138Ah; int
0x18006cda0  mov     dword ptr [rsp+208h+pvarg], esi; int
0x18006cda4  xor     r8d, r8d; struct VAR *
0x18006cda7  mov     rcx, r14; this
0x18006cdaa  call    ?RecordHr@CSession@@QEAAJJPEAVVAR@@PEBGJ@Z; CSession::RecordHr(long,VAR *,ushort const *,long)
0x18006cdaf  mov     edi, eax
0x18006cdb1  mov     [rsp+208h+var_1C8], eax
0x18006cdb5  jmp     loc_18006D09B
0x18006cdba  mov     al, 1
0x18006cdbc  mov     [rsp+208h+var_1C4], al
0x18006cdc0  mov     rax, [r12]
0x18006cdc4  mov     rbx, [rax+0E0h]
0x18006cdcb  lea     rdx, aSet; "set"
0x18006cdd2  lea     rcx, [rsp+208h+var_180]; this
0x18006cdda  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006cddf  lea     r8, [rsp+208h+var_150]
0x18006cde7  mov     rdx, rax
0x18006cdea  mov     rcx, r12
0x18006cded  mov     rax, rbx
0x18006cdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cdf5  xor     ebx, ebx
0x18006cdf7  test    eax, eax
0x18006cdf9  jnz     short loc_18006CE4B
0x18006cdfb  mov     [rsp+208h+arg_0], rbx
0x18006ce03  cmp     [rsp+208h+var_150], bx
0x18006ce0b  jz      short loc_18006CE43
0x18006ce0d  lea     rcx, [rsp+208h+var_150]; this
0x18006ce15  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x18006ce1a  test    eax, eax
0x18006ce1c  jz      short loc_18006CE43
0x18006ce1e  lea     rdx, [rsp+208h+arg_0]; struct NameTbl **
0x18006ce26  lea     rcx, [rsp+208h+var_150]; this
0x18006ce2e  call    ?IsFunction@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsFunction(NameTbl * *)
0x18006ce33  test    eax, eax
0x18006ce35  jnz     short loc_18006CE43
0x18006ce37  lea     r9, aSet; "set"
0x18006ce3e  jmp     loc_18006CD9B
0x18006ce43  mov     byte ptr [rsp+208h+arg_0], 1
0x18006ce4b  mov     rax, [r12]
0x18006ce4f  mov     rbx, [rax+0E0h]
0x18006ce56  lea     rdx, aValue; "value"
0x18006ce5d  lea     rcx, [rsp+208h+var_180]; this
0x18006ce65  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006ce6a  lea     r8, [rsp+208h+var_130]
0x18006ce72  mov     rdx, rax
0x18006ce75  mov     rcx, r12
0x18006ce78  mov     rax, rbx
0x18006ce7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce80  mov     al, [rsp+208h+var_1C4]
0x18006ce84  xor     ebx, ebx
0x18006ce86  mov     r12b, byte ptr [rsp+208h+arg_0]
0x18006ce8e  test    al, al
0x18006ce90  jnz     loc_18006CF20
0x18006ce96  test    r12b, r12b
0x18006ce99  jnz     loc_18006CF20
0x18006ce9f  cmp     [rsp+208h+var_130], bx
0x18006cea7  jz      loc_18006D068
0x18006cead  cmp     byte ptr [rsp+208h+var_1C0], sil
0x18006ceb2  jz      short loc_18006CF27
0x18006ceb4  cmp     r15b, sil
  ... truncated ...
```
